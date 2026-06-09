# MSCryptPqDsaSetProperty

- ea: `0x18006b2c0`
- end: `0x18006b3d2`
- name: `MSCryptPqDsaSetProperty`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18006b2c0`
- `0x18006ba68`
- `0x18006bcf8`
- `0x18007f765`

## string_xrefs

- `0x18006b3ac`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaSetProperty(__int64 a1, __int64 a2, const void *a3, unsigned int a4, int a5)
{
  __int64 v7; // r9
  __int64 v8; // rdi
  const wchar_t *v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 PqDsaParameterSetInfoFromName; // rax

  if ( !a1 )
  {
    v7 = 904;
LABEL_19:
    v11 = 3221225485LL;
    v10 = -1073741811;
    goto LABEL_20;
  }
  if ( !a2 )
  {
    v7 = 911;
    goto LABEL_19;
  }
  if ( !a3 || !a4 )
  {
    v7 = 918;
    goto LABEL_19;
  }
  if ( a5 )
  {
    v7 = 925;
    goto LABEL_19;
  }
  v8 = validatePqDsaKey(a1, 0);
  if ( !v8 )
  {
    v10 = -1073741816;
    v7 = 933;
    v11 = 3221225480LL;
LABEL_20:
    DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v7);
    return v10;
  }
  if ( wcscmp_0(v9, L"ParameterSetName") )
  {
    v10 = -1073741637;
    v7 = 961;
    v11 = 3221225659LL;
    goto LABEL_20;
  }
  if ( ((unsigned __int8)a3 & 1) != 0 )
  {
    v10 = -2147483646;
    v7 = 944;
    v11 = 2147483650LL;
    goto LABEL_20;
  }
  PqDsaParameterSetInfoFromName = getPqDsaParameterSetInfoFromName(*(_QWORD *)(v8 + 16), a3, a4);
  if ( !PqDsaParameterSetInfoFromName )
  {
    v7 = 952;
    goto LABEL_19;
  }
  *(_QWORD *)(v8 + 24) = PqDsaParameterSetInfoFromName;
  return 0;
}

```

## disassembly

```asm
0x18006b2c0  mov     [rsp+arg_0], rbx
0x18006b2c5  mov     [rsp+arg_8], rsi
0x18006b2ca  push    rdi
0x18006b2cb  sub     rsp, 20h
0x18006b2cf  mov     rbx, r8
0x18006b2d2  mov     r8, rdx
0x18006b2d5  mov     esi, r9d
0x18006b2d8  test    rcx, rcx
0x18006b2db  jnz     short loc_18006B2E8
0x18006b2dd  mov     r9d, 388h
0x18006b2e3  jmp     loc_18006B3A2
0x18006b2e8  test    r8, r8
0x18006b2eb  jnz     short loc_18006B2F8
0x18006b2ed  mov     r9d, 38Fh
0x18006b2f3  jmp     loc_18006B3A2
0x18006b2f8  test    rbx, rbx
0x18006b2fb  jz      loc_18006B39C
0x18006b301  test    esi, esi
0x18006b303  jz      loc_18006B39C
0x18006b309  cmp     [rsp+28h+arg_20], 0
0x18006b30e  jz      short loc_18006B31B
0x18006b310  mov     r9d, 39Dh
0x18006b316  jmp     loc_18006B3A2
0x18006b31b  xor     edx, edx
0x18006b31d  call    validatePqDsaKey
0x18006b322  mov     rdi, rax
0x18006b325  test    rax, rax
0x18006b328  jnz     short loc_18006B33C
0x18006b32a  mov     ebx, 0C0000008h
0x18006b32f  mov     r9d, 3A5h
0x18006b335  mov     ecx, 0C0000008h
0x18006b33a  jmp     short loc_18006B3AC
0x18006b33c  lea     rdx, aParametersetna; "ParameterSetName"
0x18006b343  mov     rcx, r8; String1
0x18006b346  call    wcscmp_0
0x18006b34b  test    eax, eax
0x18006b34d  jnz     short loc_18006B38A
0x18006b34f  test    bl, 1
0x18006b352  jz      short loc_18006B366
0x18006b354  mov     ebx, 80000002h
0x18006b359  mov     r9d, 3B0h
0x18006b35f  mov     ecx, 80000002h
0x18006b364  jmp     short loc_18006B3AC
0x18006b366  mov     rcx, [rdi+10h]
0x18006b36a  mov     r8d, esi
0x18006b36d  mov     rdx, rbx
0x18006b370  call    getPqDsaParameterSetInfoFromName
0x18006b375  test    rax, rax
0x18006b378  jnz     short loc_18006B382
0x18006b37a  mov     r9d, 3B8h
0x18006b380  jmp     short loc_18006B3A2
0x18006b382  mov     [rdi+18h], rax
0x18006b386  xor     ebx, ebx
0x18006b388  jmp     short loc_18006B3BF
0x18006b38a  mov     ebx, 0C00000BBh
0x18006b38f  mov     r9d, 3C1h
0x18006b395  mov     ecx, 0C00000BBh
0x18006b39a  jmp     short loc_18006B3AC
0x18006b39c  mov     r9d, 396h
0x18006b3a2  mov     ecx, 0C000000Dh
0x18006b3a7  mov     ebx, 0C000000Dh
0x18006b3ac  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006b3b3  lea     rdx, aStatus_0; "status"
0x18006b3ba  call    DebugTraceError
0x18006b3bf  mov     rsi, [rsp+28h+arg_8]
0x18006b3c4  mov     eax, ebx
0x18006b3c6  mov     rbx, [rsp+28h+arg_0]
0x18006b3cb  add     rsp, 20h
0x18006b3cf  pop     rdi
0x18006b3d0  retn
```
