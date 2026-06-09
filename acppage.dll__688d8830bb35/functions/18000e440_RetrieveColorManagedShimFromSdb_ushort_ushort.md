# RetrieveColorManagedShimFromSdb(ushort *,ushort)

- ea: `0x18000e440`
- end: `0x18000e605`
- name: `?RetrieveColorManagedShimFromSdb@@YAHPEAGG@Z`
- size: `453`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c630`

## callees

- `0x18000e440`
- `0x18001623a`
- `0x180016280`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e5bf`
- `msvcrt!_wcsicmp` at `0x18000e5bf`
- `apphelp!SdbTagRefToTagID` at `0x18000e566`
- `apphelp!SdbTagRefToTagID` at `0x18000e566`
- `apphelp!SdbGetStringTagPtr` at `0x18000e5aa`
- `apphelp!SdbGetStringTagPtr` at `0x18000e5aa`
- `apphelp!SdbGetPathSystemSdb` at `0x18000e4b3`
- `apphelp!SdbGetPathSystemSdb` at `0x18000e4b3`
- `apphelp!SdbFindNextTag` at `0x18000e5d5`
- `apphelp!SdbFindNextTag` at `0x18000e5d5`
- `apphelp!SdbFindFirstTag` at `0x18000e584`
- `apphelp!SdbFindFirstTag` at `0x18000e599`
- `apphelp!SdbFindFirstTag` at `0x18000e584`
- `apphelp!SdbFindFirstTag` at `0x18000e599`
- `apphelp!SdbInitDatabase` at `0x18000e4c9`
- `apphelp!SdbInitDatabase` at `0x18000e4c9`
- `apphelp!SdbGetMatchingExe` at `0x18000e4f5`
- `apphelp!SdbGetMatchingExe` at `0x18000e4f5`
- `apphelp!SdbReleaseDatabase` at `0x18000e502`
- `apphelp!SdbReleaseDatabase` at `0x18000e5f7`
- `apphelp!SdbReleaseDatabase` at `0x18000e502`
- `apphelp!SdbReleaseDatabase` at `0x18000e5f7`

## pseudocode

```c
__int64 __fastcall RetrieveColorManagedShimFromSdb(unsigned __int16 *a1, __int16 a2)
{
  __int64 inited; // rbx
  unsigned int v5; // r14d
  __int64 v6; // rdi
  __int64 v7; // rdx
  unsigned int i; // eax
  unsigned int FirstTag; // eax
  const wchar_t *StringTagPtr; // rax
  unsigned int v11; // esi
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v15[116]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[528]; // [rsp+220h] [rbp+120h] BYREF

  LOWORD(v12) = a2;
  memset_0(v15, 0, 0x1C8u);
  memset_0(v16, 0, 0x208u);
  if ( !(unsigned int)SdbGetPathSystemSdb(v16, 260, 1, &v12) )
    return 0;
  inited = SdbInitDatabase(3, v16);
  if ( !inited )
    return 0;
  if ( !(unsigned int)SdbGetMatchingExe(inited, a1, 0, 0, 2, v15, v12) )
  {
    SdbReleaseDatabase(inited);
    return 0;
  }
  v5 = 0;
  v6 = 0;
  do
  {
    if ( v5 )
      break;
    v7 = (unsigned int)v15[v6];
    v14 = 0;
    v13 = 0;
    if ( (_DWORD)v7 && (unsigned int)SdbTagRefToTagID(inited, v7, &v14, &v13) && v14 )
    {
      for ( i = SdbFindFirstTag(v14, v13, 28693); ; i = SdbFindNextTag(v14, v13, v11) )
      {
        v11 = i;
        if ( !i )
          break;
        FirstTag = SdbFindFirstTag(v14, i, 24577);
        if ( FirstTag )
        {
          StringTagPtr = (const wchar_t *)SdbGetStringTagPtr(v14, FirstTag);
          if ( StringTagPtr )
          {
            if ( !_wcsicmp(StringTagPtr, L"TransformLegacyColorManagedWindows") )
            {
              v5 = 1;
              break;
            }
          }
        }
      }
    }
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (unsigned int)v6 < 0x10 );
  SdbReleaseDatabase(inited);
  return v5;
}

```

## disassembly

```asm
0x18000e440  mov     [rsp-8+arg_10], rbx
0x18000e445  mov     [rsp-8+arg_18], rsi
0x18000e44a  push    rbp
0x18000e44b  push    rdi
0x18000e44c  push    r14
0x18000e44e  lea     rbp, [rsp-340h]
0x18000e456  sub     rsp, 440h
0x18000e45d  mov     rax, cs:__security_cookie
0x18000e464  xor     rax, rsp
0x18000e467  mov     [rbp+350h+var_20], rax
0x18000e46e  mov     rdi, rcx
0x18000e471  mov     word ptr [rsp+450h+var_420], dx
0x18000e476  xor     edx, edx; Val
0x18000e478  lea     rcx, [rsp+450h+var_400]; void *
0x18000e47d  mov     r8d, 1C8h; Size
0x18000e483  call    memset_0
0x18000e488  xor     edx, edx; Val
0x18000e48a  lea     rcx, [rbp+350h+var_230]; void *
0x18000e491  mov     r8d, 208h; Size
0x18000e497  call    memset_0
0x18000e49c  lea     r9, [rsp+450h+var_420]
0x18000e4a1  mov     edx, 104h
0x18000e4a6  mov     r8d, 1
0x18000e4ac  lea     rcx, [rbp+350h+var_230]
0x18000e4b3  call    cs:__imp_SdbGetPathSystemSdb
0x18000e4b9  test    eax, eax
0x18000e4bb  jz      short loc_18000E508
0x18000e4bd  lea     rdx, [rbp+350h+var_230]
0x18000e4c4  mov     ecx, 3
0x18000e4c9  call    cs:__imp_SdbInitDatabase
0x18000e4cf  mov     rbx, rax
0x18000e4d2  test    rax, rax
0x18000e4d5  jz      short loc_18000E508
0x18000e4d7  lea     rax, [rsp+450h+var_400]
0x18000e4dc  xor     r9d, r9d
0x18000e4df  mov     [rsp+450h+var_428], rax
0x18000e4e4  xor     r8d, r8d
0x18000e4e7  mov     rdx, rdi
0x18000e4ea  mov     [rsp+450h+var_430], 2
0x18000e4f2  mov     rcx, rbx
0x18000e4f5  call    cs:__imp_SdbGetMatchingExe
0x18000e4fb  test    eax, eax
0x18000e4fd  jnz     short loc_18000E531
0x18000e4ff  mov     rcx, rbx
0x18000e502  call    cs:__imp_SdbReleaseDatabase
0x18000e508  xor     eax, eax
0x18000e50a  mov     rcx, [rbp+350h+var_20]
0x18000e511  xor     rcx, rsp; StackCookie
0x18000e514  call    __security_check_cookie
0x18000e519  lea     r11, [rsp+450h+var_10]
0x18000e521  mov     rbx, [r11+30h]
0x18000e525  mov     rsi, [r11+38h]
0x18000e529  mov     rsp, r11
0x18000e52c  pop     r14
0x18000e52e  pop     rdi
0x18000e52f  pop     rbp
0x18000e530  retn
0x18000e531  xor     r14d, r14d
0x18000e534  xor     edi, edi
0x18000e536  test    r14d, r14d
0x18000e539  jnz     loc_18000E5F4
0x18000e53f  mov     edx, [rsp+rdi*4+450h+var_400]
0x18000e543  mov     [rsp+450h+var_410], 0
0x18000e54c  mov     [rsp+450h+var_418], r14d
0x18000e551  test    edx, edx
0x18000e553  jz      loc_18000E5E9
0x18000e559  lea     r9, [rsp+450h+var_418]
0x18000e55e  mov     rcx, rbx
0x18000e561  lea     r8, [rsp+450h+var_410]
0x18000e566  call    cs:__imp_SdbTagRefToTagID
0x18000e56c  test    eax, eax
0x18000e56e  jz      short loc_18000E5E9
0x18000e570  mov     rcx, [rsp+450h+var_410]
0x18000e575  test    rcx, rcx
0x18000e578  jz      short loc_18000E5E9
0x18000e57a  mov     edx, [rsp+450h+var_418]
0x18000e57e  mov     r8d, 7015h
0x18000e584  call    cs:__imp_SdbFindFirstTag
0x18000e58a  jmp     short loc_18000E5DB
0x18000e58c  mov     rcx, [rsp+450h+var_410]
0x18000e591  mov     r8d, 6001h
0x18000e597  mov     edx, esi
0x18000e599  call    cs:__imp_SdbFindFirstTag
0x18000e59f  test    eax, eax
0x18000e5a1  jz      short loc_18000E5C9
0x18000e5a3  mov     rcx, [rsp+450h+var_410]
0x18000e5a8  mov     edx, eax
0x18000e5aa  call    cs:__imp_SdbGetStringTagPtr
0x18000e5b0  test    rax, rax
0x18000e5b3  jz      short loc_18000E5C9
0x18000e5b5  lea     rdx, aTransformlegac_0; "TransformLegacyColorManagedWindows"
0x18000e5bc  mov     rcx, rax; String1
0x18000e5bf  call    cs:__imp__wcsicmp
0x18000e5c5  test    eax, eax
0x18000e5c7  jz      short loc_18000E5E3
0x18000e5c9  mov     edx, [rsp+450h+var_418]
0x18000e5cd  mov     r8d, esi
0x18000e5d0  mov     rcx, [rsp+450h+var_410]
0x18000e5d5  call    cs:__imp_SdbFindNextTag
0x18000e5db  mov     esi, eax
0x18000e5dd  test    eax, eax
0x18000e5df  jnz     short loc_18000E58C
0x18000e5e1  jmp     short loc_18000E5E9
0x18000e5e3  mov     r14d, 1
0x18000e5e9  inc     edi
0x18000e5eb  cmp     edi, 10h
0x18000e5ee  jb      loc_18000E536
0x18000e5f4  mov     rcx, rbx
0x18000e5f7  call    cs:__imp_SdbReleaseDatabase
0x18000e5fd  mov     eax, r14d
0x18000e600  jmp     loc_18000E50A
```
