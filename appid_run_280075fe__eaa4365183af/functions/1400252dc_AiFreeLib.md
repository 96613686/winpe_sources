# AiFreeLib

- ea: `0x1400252dc`
- end: `0x1400253a5`
- name: `AiFreeLib`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140021d30`
- `0x140038a54`

## callees

- `0x140002ec0`
- `0x1400252dc`
- `0x1400254e8`
- `0x140027c48`
- `0x14002920c`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x140025358`
- `ntoskrnl!ZwWaitForSingleObject` at `0x140025358`
- `ntoskrnl!ZwAlertThread` at `0x140025340`
- `ntoskrnl!ZwAlertThread` at `0x140025340`
- `ntoskrnl!ZwClose` at `0x14002536b`
- `ntoskrnl!ZwClose` at `0x140025383`
- `ntoskrnl!ZwClose` at `0x14002536b`
- `ntoskrnl!ZwClose` at `0x140025383`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14002530d`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14002530d`

## pseudocode

```c
__int64 AiFreeLib()
{
  __int64 i; // rbx
  void *v1; // rcx

  AipkFreeAppxInMemoryCache();
  AipkUnloadRegCache();
  if ( AppHashAlgInitialized )
  {
    for ( i = 0; i != 2; ++i )
    {
      v1 = *(&AppHashAlgHandle + i);
      if ( v1 )
      {
        BCryptCloseAlgorithmProvider(v1, 0);
        *(&AppHashAlgHandle + i) = 0;
      }
    }
    AppHashAlgInitialized = 0;
  }
  if ( ThreadHandle )
  {
    ZwAlertThread(ThreadHandle);
    ZwWaitForSingleObject(ThreadHandle, 0, 0);
    ZwClose(ThreadHandle);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  AiFreeCertStore();
  return AiFreePathMacroList();
}

```

## disassembly

```asm
0x1400252dc  mov     [rsp+arg_0], rbx
0x1400252e1  push    rsi
0x1400252e2  sub     rsp, 20h
0x1400252e6  call    AipkFreeAppxInMemoryCache
0x1400252eb  call    AipkUnloadRegCache
0x1400252f0  cmp     cs:AppHashAlgInitialized, 0
0x1400252f7  jz      short loc_140025334
0x1400252f9  xor     ebx, ebx
0x1400252fb  lea     rsi, AppHashAlgHandle
0x140025302  mov     rcx, [rsi+rbx*8]; hAlgorithm
0x140025306  test    rcx, rcx
0x140025309  jz      short loc_140025321
0x14002530b  xor     edx, edx; dwFlags
0x14002530d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140025314  nop     dword ptr [rax+rax+00h]
0x140025319  mov     qword ptr [rsi+rbx*8], 0
0x140025321  inc     rbx
0x140025324  cmp     rbx, 2
0x140025328  jnz     short loc_1400252FB
0x14002532a  mov     cs:AppHashAlgInitialized, 0
0x140025334  mov     rcx, cs:ThreadHandle; ThreadHandle
0x14002533b  test    rcx, rcx
0x14002533e  jz      short loc_140025377
0x140025340  call    cs:__imp_ZwAlertThread
0x140025347  nop     dword ptr [rax+rax+00h]
0x14002534c  mov     rcx, cs:ThreadHandle; Handle
0x140025353  xor     r8d, r8d; Timeout
0x140025356  xor     edx, edx; Alertable
0x140025358  call    cs:__imp_ZwWaitForSingleObject
0x14002535f  nop     dword ptr [rax+rax+00h]
0x140025364  mov     rcx, cs:ThreadHandle; Handle
0x14002536b  call    cs:__imp_ZwClose
0x140025372  nop     dword ptr [rax+rax+00h]
0x140025377  mov     rcx, cs:FileHandle; Handle
0x14002537e  test    rcx, rcx
0x140025381  jz      short loc_14002538F
0x140025383  call    cs:__imp_ZwClose
0x14002538a  nop     dword ptr [rax+rax+00h]
0x14002538f  call    AiFreeCertStore
0x140025394  call    AiFreePathMacroList
0x140025399  mov     rbx, [rsp+28h+arg_0]
0x14002539e  add     rsp, 20h
0x1400253a2  pop     rsi
0x1400253a3  retn
```
