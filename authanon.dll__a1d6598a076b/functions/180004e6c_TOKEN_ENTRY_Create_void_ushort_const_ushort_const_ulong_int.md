# TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)

- ea: `0x180004e6c`
- end: `0x180004f1d`
- name: `?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z`
- size: `177`
- prototype: `int(TOKEN_ENTRY *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800043b8`
- `0x180005354`

## callees

- `0x180004e6c`
- `0x180004f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ee5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004edb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004edb`

## pseudocode

```c
int __fastcall TOKEN_ENTRY::Create(
        TOKEN_ENTRY *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6)
{
  bool v9; // zf
  int result; // eax
  DWORD ReturnLength; // [rsp+40h] [rbp+8h] BYREF

  if ( a5 == 3 || a5 == 8 )
  {
    v9 = a6 == 0;
    *((_QWORD *)this + 2) = a2;
    if ( !v9 )
      *((_DWORD *)this + 65) |= 1u;
  }
  else
  {
    v9 = a6 == 0;
    *((_QWORD *)this + 3) = a2;
    if ( !v9 )
      *((_DWORD *)this + 65) |= 2u;
  }
  ReturnLength = 84;
  if ( GetTokenInformation(a2, TokenUser, (char *)this + 32, 0x54u, &ReturnLength) )
    return TOKEN_KEY::CreateCacheKey((TOKEN_ENTRY *)((char *)this + 120), a3, a4, a5);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004e6c  mov     [rsp+arg_8], rbx
0x180004e71  mov     [rsp+arg_10], rbp
0x180004e76  push    rsi
0x180004e77  sub     rsp, 30h
0x180004e7b  cmp     [rsp+38h+arg_20], 3
0x180004e80  mov     rax, rdx
0x180004e83  mov     edx, 1; TokenInformationClass
0x180004e88  mov     rsi, r9
0x180004e8b  mov     rbp, r8
0x180004e8e  mov     rbx, rcx
0x180004e91  jz      short loc_180004EAE
0x180004e93  cmp     [rsp+38h+arg_20], 8
0x180004e98  jz      short loc_180004EAE
0x180004e9a  cmp     [rsp+38h+arg_28], 0
0x180004e9f  mov     [rcx+18h], rax
0x180004ea3  jz      short loc_180004EBF
0x180004ea5  or      dword ptr [rcx+104h], 2
0x180004eac  jmp     short loc_180004EBF
0x180004eae  cmp     [rsp+38h+arg_28], 0
0x180004eb3  mov     [rcx+10h], rax
0x180004eb7  jz      short loc_180004EBF
0x180004eb9  or      [rcx+104h], edx
0x180004ebf  lea     r8, [rcx+20h]; TokenInformation
0x180004ec3  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180004ec9  lea     rcx, [rsp+38h+arg_0]
0x180004ece  mov     [rsp+38h+arg_0], r9d
0x180004ed3  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180004ed8  mov     rcx, rax; TokenHandle
0x180004edb  call    cs:__imp_GetTokenInformation
0x180004ee1  test    eax, eax
0x180004ee3  jnz     short loc_180004EF9
0x180004ee5  call    cs:__imp_GetLastError
0x180004eeb  test    eax, eax
0x180004eed  jle     short loc_180004F0D
0x180004eef  movzx   eax, ax
0x180004ef2  or      eax, 80070000h
0x180004ef7  jmp     short loc_180004F0D
0x180004ef9  mov     r9d, [rsp+38h+arg_20]; unsigned int
0x180004efe  lea     rcx, [rbx+78h]; this
0x180004f02  mov     r8, rsi; unsigned __int16 *
0x180004f05  mov     rdx, rbp; unsigned __int16 *
0x180004f08  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180004f0d  mov     rbx, [rsp+38h+arg_8]
0x180004f12  mov     rbp, [rsp+38h+arg_10]
0x180004f17  add     rsp, 30h
0x180004f1b  pop     rsi
0x180004f1c  retn
```
