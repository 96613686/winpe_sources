# TransformOldFileImageForPatching

- ea: `0x180004940`
- end: `0x1800049fb`
- name: `TransformOldFileImageForPatching`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001d10`
- `0x180002720`

## callees

- `0x180004940`
- `0x180004d10`
- `0x18000541c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049e7`

## pseudocode

```c
__int64 __fastcall TransformOldFileImageForPatching(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v5; // r15d
  int v6; // edi
  int v7; // esi
  unsigned int v9; // ebx
  __int64 NtHeader; // rax
  DWORD dwErrCode; // [rsp+40h] [rbp-38h]

  v5 = a4;
  v6 = a3;
  v7 = a2;
  v9 = 1;
  if ( a2 )
  {
    dwErrCode = 0;
    if ( (_DWORD)a3 )
    {
      NtHeader = GetNtHeader(a2, (unsigned int)a3, a3, a4);
      if ( NtHeader )
      {
        *a1 |= 0x20000000u;
        v9 = TransformCoffImage((_DWORD)a1, NtHeader, v7, v6, v5, a5);
        if ( !v9 )
          dwErrCode = GetLastError();
      }
      if ( !v9 && dwErrCode )
        SetLastError(dwErrCode);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180004940  push    rbx
0x180004942  push    rsi
0x180004943  push    rdi
0x180004944  push    r14
0x180004946  push    r15
0x180004948  sub     rsp, 50h
0x18000494c  mov     r15d, r9d
0x18000494f  mov     edi, r8d
0x180004952  mov     rsi, rdx
0x180004955  mov     r14, rcx
0x180004958  mov     ebx, 1
0x18000495d  test    rdx, rdx
0x180004960  jz      loc_1800049ED
0x180004966  mov     [rsp+78h+dwErrCode], 0
0x18000496e  test    r8d, r8d
0x180004971  jz      short loc_1800049ED
0x180004973  mov     edx, r8d
0x180004976  mov     rcx, rsi
0x180004979  call    GetNtHeader
0x18000497e  mov     rdx, rax
0x180004981  test    rax, rax
0x180004984  jz      short loc_1800049C8
0x180004986  bts     dword ptr [r14], 1Dh
0x18000498b  mov     [rsp+78h+var_48], 0
0x180004994  mov     rax, [rsp+78h+arg_20]
0x18000499c  mov     [rsp+78h+var_50], rax
0x1800049a1  mov     [rsp+78h+var_58], r15d
0x1800049a6  mov     r9d, edi
0x1800049a9  mov     r8, rsi
0x1800049ac  mov     rcx, r14
0x1800049af  call    TransformCoffImage
0x1800049b4  mov     ebx, eax
0x1800049b6  mov     [rsp+78h+var_34], eax
0x1800049ba  test    eax, eax
0x1800049bc  jnz     short loc_1800049C8
0x1800049be  call    cs:__imp_GetLastError
0x1800049c4  mov     [rsp+78h+dwErrCode], eax
0x1800049c8  jmp     short loc_1800049DB
0x1800049ca  cmp     eax, 0E0000001h
0x1800049cf  jz      short loc_1800049D5
0x1800049d1  mov     [rsp+78h+dwErrCode], eax
0x1800049d5  xor     ebx, ebx
0x1800049d7  mov     [rsp+78h+var_34], ebx
0x1800049db  test    ebx, ebx
0x1800049dd  jnz     short loc_1800049ED
0x1800049df  mov     ecx, [rsp+78h+dwErrCode]; dwErrCode
0x1800049e3  test    ecx, ecx
0x1800049e5  jz      short loc_1800049ED
0x1800049e7  call    cs:__imp_SetLastError
0x1800049ed  mov     eax, ebx
0x1800049ef  add     rsp, 50h
0x1800049f3  pop     r15
0x1800049f5  pop     r14
0x1800049f7  pop     rdi
0x1800049f8  pop     rsi
0x1800049f9  pop     rbx
0x1800049fa  retn
```
