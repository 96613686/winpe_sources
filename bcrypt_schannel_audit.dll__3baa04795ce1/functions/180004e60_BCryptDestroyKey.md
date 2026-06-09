# BCryptDestroyKey

- ea: `0x180004e60`
- end: `0x180005058`
- name: `BCryptDestroyKey`
- size: `504`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004e60`
- `0x180005060`
- `0x1800050b0`
- `0x18000d948`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004f48`
- `ntdll!RtlFreeHeap` at `0x180004f96`
- `ntdll!RtlFreeHeap` at `0x180004f48`
- `ntdll!RtlFreeHeap` at `0x180004f96`

## string_xrefs

- `0x180004e9e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180005016`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000503e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDestroyKey(BCRYPT_KEY_HANDLE hKey)
{
  __int64 v1; // r8
  __int64 v4; // rdi
  void *v5; // r14
  int v6; // eax
  __int64 (__fastcall *v7)(_QWORD); // rax
  int v8; // ebp
  int v9; // eax
  NTSTATUS v10; // esi
  __int64 v11; // rcx
  _BYTE *v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v1);
  if ( !hKey || *(_DWORD *)hKey < 0x20u || *((_DWORD *)hKey + 1) != 1431655762 )
  {
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return -1073741816;
  }
  v4 = *((_QWORD *)hKey + 1);
  v5 = 0;
  v6 = *(_DWORD *)(v4 + 36);
  if ( v6 == 3 )
    goto LABEL_7;
  v8 = 0;
  v13 = v6 - 1;
  if ( !v13 )
  {
    v5 = (void *)*((_QWORD *)hKey + 3);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(v4 + 136))(*((_QWORD *)hKey + 2));
    goto LABEL_9;
  }
  v14 = v13 - 3;
  if ( !v14 )
  {
    v7 = *(__int64 (__fastcall **)(_QWORD))(v4 + 144);
    goto LABEL_8;
  }
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_7;
  v16 = v15 - 2;
  if ( !v16 )
  {
    v5 = (void *)*((_QWORD *)hKey + 3);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(v4 + 96))(*((_QWORD *)hKey + 2));
LABEL_9:
    v10 = v9;
    if ( v9 < 0 )
    {
      DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    }
    else
    {
      v11 = *(unsigned int *)hKey;
      v12 = hKey;
      if ( *(_DWORD *)hKey )
      {
        do
        {
          *v12++ = 0;
          --v11;
        }
        while ( v11 );
      }
      if ( v8 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, hKey);
      if ( v5 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    }
    goto LABEL_16;
  }
  if ( v16 == 1 )
  {
LABEL_7:
    v7 = *(__int64 (__fastcall **)(_QWORD))(v4 + 136);
LABEL_8:
    v8 = 1;
    v9 = v7(*((_QWORD *)hKey + 2));
    goto LABEL_9;
  }
  v10 = -1073741816;
  DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
LABEL_16:
  if ( v4 )
  {
    if ( v10 >= 0 )
      DecrementReferenceCount((PVOID)v4);
  }
  return v10;
}

```

## disassembly

```asm
0x180004e60  push    rbx
0x180004e62  sub     rsp, 20h
0x180004e66  mov     rbx, rcx
0x180004e69  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e70  lea     rax, WPP_GLOBAL_Control
0x180004e77  cmp     rcx, rax
0x180004e7a  jnz     loc_180004FA4
0x180004e80  mov     [rsp+28h+arg_8], rsi
0x180004e85  test    rbx, rbx
0x180004e88  jz      short loc_180004E98
0x180004e8a  cmp     dword ptr [rbx], 20h ; ' '
0x180004e8d  jb      short loc_180004E98
0x180004e8f  cmp     dword ptr [rbx+4], 55555552h
0x180004e96  jz      short loc_180004EC9
0x180004e98  mov     r9d, 15CFh
0x180004e9e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004ea5  lea     rdx, aStatus; "Status"
0x180004eac  mov     ecx, 0C0000008h
0x180004eb1  mov     esi, 0C0000008h
0x180004eb6  call    DebugTraceError
0x180004ebb  mov     eax, esi
0x180004ebd  mov     rsi, [rsp+28h+arg_8]
0x180004ec2  add     rsp, 20h
0x180004ec6  pop     rbx
0x180004ec7  retn
0x180004ec9  mov     [rsp+28h+arg_10], rdi
0x180004ece  mov     rdi, [rbx+8]
0x180004ed2  mov     [rsp+28h+arg_18], r14
0x180004ed7  xor     r14d, r14d
0x180004eda  mov     [rsp+28h+arg_0], rbp
0x180004edf  mov     eax, [rdi+24h]
0x180004ee2  cmp     eax, 3
0x180004ee5  jnz     loc_180004FC4
0x180004eeb  mov     rax, [rdi+88h]
0x180004ef2  mov     ebp, 1
0x180004ef7  mov     rcx, [rbx+10h]
0x180004efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f00  mov     esi, eax
0x180004f02  test    eax, eax
0x180004f04  js      loc_180005038
0x180004f0a  mov     ecx, [rbx]
0x180004f0c  mov     rax, rbx
0x180004f0f  test    rcx, rcx
0x180004f12  jz      short loc_180004F2D
0x180004f14  nop     dword ptr [rax+00h]
0x180004f18  nop     dword ptr [rax+rax+00000000h]
0x180004f20  mov     byte ptr [rax], 0
0x180004f23  lea     rax, [rax+1]
0x180004f27  sub     rcx, 1
0x180004f2b  jnz     short loc_180004F20
0x180004f2d  test    ebp, ebp
0x180004f2f  jnz     short loc_180004F84
0x180004f31  test    r14, r14
0x180004f34  jz      short loc_180004F54
0x180004f36  mov     rcx, gs:60h
0x180004f3f  mov     r8, r14; P
0x180004f42  xor     edx, edx; Flags
0x180004f44  mov     rcx, [rcx+30h]; HeapHandle
0x180004f48  call    cs:__imp_RtlFreeHeap
0x180004f4f  nop     dword ptr [rax+rax+00h]
0x180004f54  mov     r14, [rsp+28h+arg_18]
0x180004f59  mov     rbp, [rsp+28h+arg_0]
0x180004f5e  test    rdi, rdi
0x180004f61  jnz     short loc_180004F76
0x180004f63  mov     rdi, [rsp+28h+arg_10]
0x180004f68  mov     eax, esi
0x180004f6a  mov     rsi, [rsp+28h+arg_8]
0x180004f6f  add     rsp, 20h
0x180004f73  pop     rbx
0x180004f74  retn
0x180004f76  test    esi, esi
0x180004f78  js      short loc_180004F63
0x180004f7a  mov     rcx, rdi; P
0x180004f7d  call    DecrementReferenceCount
0x180004f82  jmp     short loc_180004F63
0x180004f84  mov     rcx, gs:60h
0x180004f8d  mov     r8, rbx; P
0x180004f90  xor     edx, edx; Flags
0x180004f92  mov     rcx, [rcx+30h]; HeapHandle
0x180004f96  call    cs:__imp_RtlFreeHeap
0x180004f9d  nop     dword ptr [rax+rax+00h]
0x180004fa2  jmp     short loc_180004F31
0x180004fa4  test    byte ptr [rcx+1Ch], 4
0x180004fa8  jz      loc_180004E80
0x180004fae  mov     rcx, [rcx+10h]
0x180004fb2  mov     edx, 1Fh
0x180004fb7  mov     r9, rbx
0x180004fba  call    WPP_SF_q
0x180004fbf  jmp     loc_180004E80
0x180004fc4  xor     ebp, ebp
0x180004fc6  sub     eax, 1
0x180004fc9  jnz     short loc_180004FDB
0x180004fcb  mov     rax, [rdi+88h]
0x180004fd2  mov     r14, [rbx+18h]
0x180004fd6  jmp     loc_180004EF7
0x180004fdb  sub     eax, 3
0x180004fde  jnz     short loc_180004FEC
0x180004fe0  mov     rax, [rdi+90h]
0x180004fe7  jmp     loc_180004EF2
0x180004fec  sub     eax, 1
0x180004fef  jz      loc_180004EEB
0x180004ff5  sub     eax, 2
0x180004ff8  jnz     short loc_180005007
0x180004ffa  mov     rax, [rdi+60h]
0x180004ffe  mov     r14, [rbx+18h]
0x180005002  jmp     loc_180004EF7
0x180005007  cmp     eax, 1
0x18000500a  jz      loc_180004EEB
0x180005010  mov     r9d, 1600h
0x180005016  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000501d  lea     rdx, aStatus; "Status"
0x180005024  mov     ecx, 0C0000008h
0x180005029  mov     esi, 0C0000008h
0x18000502e  call    DebugTraceError
0x180005033  jmp     loc_180004F54
0x180005038  mov     r9d, 1609h
0x18000503e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005045  lea     rdx, aStatus; "Status"
0x18000504c  mov     ecx, eax
0x18000504e  call    DebugTraceError
0x180005053  jmp     loc_180004F54
```
