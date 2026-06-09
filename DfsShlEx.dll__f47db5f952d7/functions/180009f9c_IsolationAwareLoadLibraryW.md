# IsolationAwareLoadLibraryW

- ea: `0x180009f9c`
- end: `0x18000a04c`
- name: `IsolationAwareLoadLibraryW`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008920`

## callees

- `0x180006dfc`
- `0x180009f9c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000a041`
- `KERNEL32!SetLastError` at `0x18000b165`
- `KERNEL32!SetLastError` at `0x18000a041`
- `KERNEL32!SetLastError` at `0x18000b165`
- `KERNEL32!DeactivateActCtx` at `0x18000a035`
- `KERNEL32!DeactivateActCtx` at `0x18000b159`
- `KERNEL32!DeactivateActCtx` at `0x18000a035`
- `KERNEL32!DeactivateActCtx` at `0x18000b159`
- `KERNEL32!GetLastError` at `0x18000a020`
- `KERNEL32!GetLastError` at `0x18000b145`
- `KERNEL32!GetLastError` at `0x18000a020`
- `KERNEL32!GetLastError` at `0x18000b145`
- `KERNEL32!LoadLibraryW` at `0x180009ff8`
- `KERNEL32!LoadLibraryW` at `0x180009ff8`

## string_xrefs

- `0x180009ff1`: `netmsg.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryW()
{
  HMODULE LibraryW; // rax
  HMODULE v2; // rbx
  int v3; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  LibraryW = LoadLibraryW(L"netmsg.dll");
  v2 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
    {
      v3 = 0;
      LastError = 0;
    }
    else
    {
      v3 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v3 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180009f9c  mov     rax, rsp
0x180009f9f  mov     [rax+10h], rbx
0x180009fa3  mov     [rax+18h], rsi
0x180009fa7  mov     [rax+8], rcx
0x180009fab  push    rdi
0x180009fac  sub     rsp, 30h
0x180009fb0  mov     qword ptr [rax-18h], 0
0x180009fb8  mov     qword ptr [rax+8], 0
0x180009fc0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180009fc7  jnz     short loc_180009FF1
0x180009fc9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180009fd0  jnz     short loc_180009FF1
0x180009fd2  lea     rcx, [rax+8]; lpCookie
0x180009fd6  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180009fdb  test    eax, eax
0x180009fdd  jnz     short loc_180009FF1
0x180009fdf  xor     eax, eax
0x180009fe1  mov     rbx, [rsp+38h+arg_8]
0x180009fe6  mov     rsi, [rsp+38h+arg_10]
0x180009feb  add     rsp, 30h
0x180009fef  pop     rdi
0x180009ff0  retn
0x180009ff1  lea     rcx, aNetmsgDll; "netmsg.dll"
0x180009ff8  call    cs:__imp_LoadLibraryW
0x180009ffe  mov     rbx, rax
0x18000a001  mov     [rsp+38h+var_18], rax
0x18000a006  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000a00d  jz      short loc_18000A018
0x18000a00f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000a016  jnz     short loc_18000A047
0x18000a018  test    rbx, rbx
0x18000a01b  jnz     short loc_18000A02A
0x18000a01d  lea     esi, [rbx+1]
0x18000a020  call    cs:__imp_GetLastError
0x18000a026  mov     edi, eax
0x18000a028  jmp     short loc_18000A02E
0x18000a02a  xor     esi, esi
0x18000a02c  xor     edi, edi
0x18000a02e  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000a033  xor     ecx, ecx; dwFlags
0x18000a035  call    cs:__imp_DeactivateActCtx
0x18000a03b  test    esi, esi
0x18000a03d  jz      short loc_18000A047
0x18000a03f  mov     ecx, edi; dwErrCode
0x18000a041  call    cs:__imp_SetLastError
0x18000a047  mov     rax, rbx
0x18000a04a  jmp     short loc_180009FE1
0x18000b11c  push    rbx
0x18000b11e  push    rbp
0x18000b11f  push    rdi
0x18000b120  sub     rsp, 20h
0x18000b124  mov     rbp, rdx
0x18000b127  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000b12e  jz      short loc_18000B139
0x18000b130  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000b137  jnz     short loc_18000B16C
0x18000b139  cmp     qword ptr [rbp+20h], 0
0x18000b13e  jnz     short loc_18000B14F
0x18000b140  mov     edi, 1
0x18000b145  call    cs:__imp_GetLastError
0x18000b14b  mov     ebx, eax
0x18000b14d  jmp     short loc_18000B153
0x18000b14f  xor     edi, edi
0x18000b151  xor     ebx, ebx
0x18000b153  mov     rdx, [rbp+40h]; ulCookie
0x18000b157  xor     ecx, ecx; dwFlags
0x18000b159  call    cs:__imp_DeactivateActCtx
0x18000b15f  test    edi, edi
0x18000b161  jz      short loc_18000B16C
0x18000b163  mov     ecx, ebx; dwErrCode
0x18000b165  call    cs:__imp_SetLastError
0x18000b16b  nop
0x18000b16c  add     rsp, 20h
0x18000b170  pop     rdi
0x18000b171  pop     rbp
0x18000b172  pop     rbx
0x18000b173  retn
```
