# TsSessionConsiderForPrimaryConsoleAudioSession(TSSession *)

- ea: `0x180002d68`
- end: `0x180002dfc`
- name: `?TsSessionConsiderForPrimaryConsoleAudioSession@@YAXPEAVTSSession@@@Z`
- size: `148`
- prototype: `void __fastcall(struct TSSession *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180006fdc`

## callees

- `0x180002d68`
- `0x180002e80`
- `0x18002890c`
- `0x18002ca34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002df5`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180002d8b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180002d8b`

## pseudocode

```c
void __fastcall TsSessionConsiderForPrimaryConsoleAudioSession(struct TSSession *a1)
{
  int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // r14
  __int64 v5; // rbp
  __int64 *i; // rbx
  __int64 v7; // rax

  EnterCriticalSection(&stru_180064458);
  if ( !*((_DWORD *)a1 + 1) )
  {
    v2 = *(_DWORD *)a1;
    if ( v2 != (unsigned int)RtlGetCurrentServiceSessionId() )
    {
      v3 = TsSessionLogonConnectTime(a1);
      v4 = qword_180064488;
      v5 = v3;
      for ( i = *(__int64 **)qword_180064488;
            i != (__int64 *)v4 && !(unsigned int)TSSession::IsPrimaryConsoleAudioSession((TSSession *)i[3]);
            i = (__int64 *)*i )
      {
        ;
      }
      if ( i == (__int64 *)qword_180064488 )
        v7 = 0;
      else
        v7 = TsSessionLogonConnectTime((struct TSSession *)i[3]);
      if ( v5 > v7 )
        TsSessionNewPrimaryConsoleAudioSession(a1);
    }
  }
  LeaveCriticalSection(&stru_180064458);
}

```

## disassembly

```asm
0x180002d68  push    rbx
0x180002d6a  push    rbp
0x180002d6b  push    rsi
0x180002d6c  push    rdi
0x180002d6d  push    r14
0x180002d6f  sub     rsp, 20h
0x180002d73  mov     rdi, rcx
0x180002d76  lea     rcx, stru_180064458; lpCriticalSection
0x180002d7d  call    cs:__imp_EnterCriticalSection
0x180002d83  cmp     dword ptr [rdi+4], 0
0x180002d87  jnz     short loc_180002DE4
0x180002d89  mov     ebx, [rdi]
0x180002d8b  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180002d91  cmp     ebx, eax
0x180002d93  jz      short loc_180002DE4
0x180002d95  mov     rcx, rdi; struct TSSession *
0x180002d98  call    ?TsSessionLogonConnectTime@@YA_JPEAVTSSession@@@Z; TsSessionLogonConnectTime(TSSession *)
0x180002d9d  mov     r14, cs:qword_180064488
0x180002da4  mov     rbp, rax
0x180002da7  mov     rbx, [r14]
0x180002daa  cmp     rbx, r14
0x180002dad  jz      short loc_180002DC1
0x180002daf  mov     rcx, [rbx+18h]; this
0x180002db3  call    ?IsPrimaryConsoleAudioSession@TSSession@@QEAAHXZ; TSSession::IsPrimaryConsoleAudioSession(void)
0x180002db8  test    eax, eax
0x180002dba  jnz     short loc_180002DC1
0x180002dbc  mov     rbx, [rbx]
0x180002dbf  jmp     short loc_180002DAA
0x180002dc1  cmp     rbx, cs:qword_180064488
0x180002dc8  jz      short loc_180002DD5
0x180002dca  mov     rcx, [rbx+18h]; struct TSSession *
0x180002dce  call    ?TsSessionLogonConnectTime@@YA_JPEAVTSSession@@@Z; TsSessionLogonConnectTime(TSSession *)
0x180002dd3  jmp     short loc_180002DD7
0x180002dd5  xor     eax, eax
0x180002dd7  cmp     rbp, rax
0x180002dda  jle     short loc_180002DE4
0x180002ddc  mov     rcx, rdi; struct TSSession *
0x180002ddf  call    ?TsSessionNewPrimaryConsoleAudioSession@@YAXPEAVTSSession@@@Z; TsSessionNewPrimaryConsoleAudioSession(TSSession *)
0x180002de4  lea     rcx, stru_180064458
0x180002deb  add     rsp, 20h
0x180002def  pop     r14
0x180002df1  pop     rdi
0x180002df2  pop     rsi
0x180002df3  pop     rbp
0x180002df4  pop     rbx
0x180002df5  jmp     cs:__imp_LeaveCriticalSection
```
