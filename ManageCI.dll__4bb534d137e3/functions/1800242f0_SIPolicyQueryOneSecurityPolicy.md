# SIPolicyQueryOneSecurityPolicy

- ea: `0x1800242f0`
- end: `0x18002453e`
- name: `SIPolicyQueryOneSecurityPolicy`
- size: `590`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017b84`
- `0x180017ca8`
- `0x1800239e4`
- `0x180025288`
- `0x180029198`

## callees

- `0x180003834`
- `0x180003870`
- `0x1800242f0`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180024330`
- `ntdll!RtlEqualUnicodeString` at `0x180024347`
- `ntdll!RtlEqualUnicodeString` at `0x180024330`
- `ntdll!RtlEqualUnicodeString` at `0x180024347`

## pseudocode

```c
__int64 __fastcall SIPolicyQueryOneSecurityPolicy(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _DWORD *a6,
        int *a7)
{
  int v7; // eax
  __int128 v9; // rdi
  unsigned int v11; // ebx
  size_t v12; // r8
  const void *v13; // rdx
  const void **v14; // rdi
  size_t v15; // r8
  const void *v16; // rdx
  size_t v17; // r8
  const void *v18; // rdx
  int v19; // edx
  __int64 v20; // rdx
  unsigned int v21; // ecx
  int *v22; // rsi
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // ecx
  __int128 Key; // [rsp+30h] [rbp-20h] BYREF
  __int128 v28; // [rsp+40h] [rbp-10h]

  v7 = *(_DWORD *)(a1 + 768);
  *((_QWORD *)&v9 + 1) = a3;
  *(_QWORD *)&v9 = a2;
  Key = 0;
  v28 = 0;
  if ( (v7 & 1) != 0
    || !RtlEqualUnicodeString(a2, &String2, 1u)
    || !RtlEqualUnicodeString(*((PCUNICODE_STRING *)&v9 + 1), &stru_18002D450, 1u) )
  {
    v12 = *(unsigned int *)(a1 + 688);
    v13 = *(const void **)(a1 + 696);
    Key = v9;
    *(_QWORD *)&v28 = a4;
    v14 = (const void **)bsearch(
                           &Key,
                           v13,
                           v12,
                           0x48u,
                           (_CoreCrtNonSecureSearchSortCompareFunction)SIPolicySecureSettingSearchCompare);
    if ( v14 )
      goto LABEL_8;
    v15 = *(unsigned int *)(a1 + 688);
    v16 = *(const void **)(a1 + 696);
    *(_QWORD *)&v28 = a4;
    *((_QWORD *)&Key + 1) = &g_AnyFileWildCardString;
    v14 = (const void **)bsearch(
                           &Key,
                           v16,
                           v15,
                           0x48u,
                           (_CoreCrtNonSecureSearchSortCompareFunction)SIPolicySecureSettingSearchCompare);
    if ( v14
      || (v17 = *(unsigned int *)(a1 + 688),
          v18 = *(const void **)(a1 + 696),
          *((_QWORD *)&Key + 1) = *((_QWORD *)&v9 + 1),
          *(_QWORD *)&v28 = &g_AnyFileWildCardString,
          (v14 = (const void **)bsearch(
                                  &Key,
                                  v18,
                                  v17,
                                  0x48u,
                                  (_CoreCrtNonSecureSearchSortCompareFunction)SIPolicySecureSettingSearchCompare)) != 0) )
    {
LABEL_8:
      v19 = *(_DWORD *)v14;
      v11 = 0;
      if ( *(_DWORD *)v14 )
      {
        if ( *(_DWORD *)v14 != 1 )
        {
          if ( *(_DWORD *)v14 == 2 )
          {
            *a5 = v19;
            v21 = *((_DWORD *)v14 + 14);
            if ( !a6 )
              goto LABEL_19;
            v22 = a7;
            if ( *a7 < v21 )
            {
              v11 = -1073741789;
              *a7 = v21;
              return v11;
            }
            memcpy_0(a6, v14[8], *((unsigned int *)v14 + 14));
            v23 = *((_DWORD *)v14 + 14);
          }
          else
          {
            if ( *(_DWORD *)v14 != 3 )
              return (unsigned int)-1058471933;
            *a5 = v19;
            v20 = *((unsigned __int16 *)v14 + 28);
            if ( !a6 )
            {
              v21 = v20 + 2;
LABEL_19:
              *a7 = v21;
              return v11;
            }
            v22 = a7;
            if ( (unsigned int)*a7 >= (unsigned __int64)(v20 + 2) )
            {
              memcpy_0(a6, v14[8], *((unsigned __int16 *)v14 + 28));
              *((_WORD *)a6 + ((unsigned __int64)*((unsigned __int16 *)v14 + 28) >> 1)) = 0;
              v23 = *((unsigned __int16 *)v14 + 28) + 2;
            }
            else
            {
              v11 = -1073741789;
              v23 = v20 + 2;
            }
          }
          *v22 = v23;
          return v11;
        }
        *a5 = v19;
        if ( !a6 )
        {
          *a7 = 4;
          return v11;
        }
        v24 = *a7;
        *a7 = 4;
        if ( v24 >= 4 )
        {
          *a6 = *((_DWORD *)v14 + 14);
          return v11;
        }
      }
      else
      {
        *a5 = 0;
        if ( !a6 )
        {
          *a7 = 1;
          return v11;
        }
        v25 = *a7;
        *a7 = 1;
        if ( v25 )
        {
          *(_BYTE *)a6 = *((_BYTE *)v14 + 56);
          return v11;
        }
      }
      return (unsigned int)-1073741789;
    }
  }
  return (unsigned int)-1073741275;
}

```

## disassembly

```asm
0x1800242f0  push    rbp
0x1800242f2  push    rbx
0x1800242f3  push    rsi
0x1800242f4  push    rdi
0x1800242f5  push    r12
0x1800242f7  push    r13
0x1800242f9  push    r14
0x1800242fb  mov     rbp, rsp
0x1800242fe  sub     rsp, 50h
0x180024302  mov     eax, [rcx+300h]
0x180024308  xorps   xmm0, xmm0
0x18002430b  mov     r14, r9
0x18002430e  mov     rsi, r8
0x180024311  mov     rdi, rdx
0x180024314  mov     rbx, rcx
0x180024317  movups  [rbp+Key], xmm0
0x18002431b  movups  [rbp+var_10], xmm0
0x18002431f  test    al, 1
0x180024321  jnz     short loc_18002435B
0x180024323  mov     r8b, 1; CaseInsensitive
0x180024326  lea     rdx, String2; String2
0x18002432d  mov     rcx, rdi; String1
0x180024330  call    cs:__imp_RtlEqualUnicodeString
0x180024336  test    al, al
0x180024338  jz      short loc_18002435B
0x18002433a  mov     r8b, 1; CaseInsensitive
0x18002433d  lea     rdx, stru_18002D450; String2
0x180024344  mov     rcx, rsi; String1
0x180024347  call    cs:__imp_RtlEqualUnicodeString
0x18002434d  test    al, al
0x18002434f  jz      short loc_18002435B
0x180024351  mov     ebx, 0C0000225h
0x180024356  jmp     loc_18002452D
0x18002435b  mov     r8d, [rbx+2B0h]; NumOfElements
0x180024362  lea     r13, SIPolicySecureSettingSearchCompare
0x180024369  mov     rdx, [rbx+2B8h]; Base
0x180024370  lea     rcx, [rbp+Key]; Key
0x180024374  mov     r12d, 48h ; 'H'
0x18002437a  mov     qword ptr [rbp+Key], rdi
0x18002437e  mov     r9d, r12d; SizeOfElements
0x180024381  mov     qword ptr [rbp+Key+8], rsi
0x180024385  mov     qword ptr [rbp+var_10], r14
0x180024389  mov     [rsp+50h+CompareFunction], r13; CompareFunction
0x18002438e  call    bsearch
0x180024393  mov     rdi, rax
0x180024396  test    rax, rax
0x180024399  jnz     short loc_180024404
0x18002439b  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800243a2  lea     rcx, [rbp+Key]; Key
0x1800243a6  mov     rdx, [rbx+2B8h]; Base
0x1800243ad  mov     r9d, r12d; SizeOfElements
0x1800243b0  mov     qword ptr [rbp+var_10], r14
0x1800243b4  lea     r14, g_AnyFileWildCardString
0x1800243bb  mov     qword ptr [rbp+Key+8], r14
0x1800243bf  mov     [rsp+50h+CompareFunction], r13; CompareFunction
0x1800243c4  call    bsearch
0x1800243c9  mov     rdi, rax
0x1800243cc  test    rax, rax
0x1800243cf  jnz     short loc_180024404
0x1800243d1  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800243d8  lea     rcx, [rbp+Key]; Key
0x1800243dc  mov     rdx, [rbx+2B8h]; Base
0x1800243e3  mov     r9d, r12d; SizeOfElements
0x1800243e6  mov     qword ptr [rbp+Key+8], rsi
0x1800243ea  mov     qword ptr [rbp+var_10], r14
0x1800243ee  mov     [rsp+50h+CompareFunction], r13; CompareFunction
0x1800243f3  call    bsearch
0x1800243f8  mov     rdi, rax
0x1800243fb  test    rax, rax
0x1800243fe  jz      loc_180024351
0x180024404  mov     edx, [rdi]
0x180024406  xor     ebx, ebx
0x180024408  mov     ecx, edx
0x18002440a  test    edx, edx
0x18002440c  jz      loc_1800244F9
0x180024412  sub     ecx, 1
0x180024415  jz      loc_1800244CA
0x18002441b  sub     ecx, 1
0x18002441e  jz      short loc_180024486
0x180024420  cmp     ecx, 1
0x180024423  jz      short loc_18002442F
0x180024425  mov     ebx, 0C0E90003h
0x18002442a  jmp     loc_18002452D
0x18002442f  mov     rax, [rbp+arg_20]
0x180024433  mov     r14, [rbp+arg_28]
0x180024437  mov     [rax], edx
0x180024439  movzx   edx, word ptr [rdi+38h]
0x18002443d  test    r14, r14
0x180024440  jnz     short loc_180024447
0x180024442  lea     ecx, [rdx+2]
0x180024445  jmp     short loc_180024498
0x180024447  mov     rsi, [rbp+arg_30]
0x18002444b  lea     rcx, [rdx+2]
0x18002444f  mov     r8, rdx; Size
0x180024452  mov     eax, [rsi]
0x180024454  cmp     rax, rcx
0x180024457  jnb     short loc_180024463
0x180024459  mov     ebx, 0C0000023h
0x18002445e  lea     eax, [rdx+2]
0x180024461  jmp     short loc_1800244C6
0x180024463  mov     rdx, [rdi+40h]; Src
0x180024467  mov     rcx, r14; void *
0x18002446a  call    memcpy_0
0x18002446f  movzx   ecx, word ptr [rdi+38h]
0x180024473  xor     eax, eax
0x180024475  shr     rcx, 1
0x180024478  mov     [r14+rcx*2], ax
0x18002447d  movzx   eax, word ptr [rdi+38h]
0x180024481  add     eax, 2
0x180024484  jmp     short loc_1800244C6
0x180024486  mov     rax, [rbp+arg_20]
0x18002448a  mov     [rax], edx
0x18002448c  mov     rax, [rbp+arg_28]
0x180024490  mov     ecx, [rdi+38h]
0x180024493  test    rax, rax
0x180024496  jnz     short loc_1800244A3
0x180024498  mov     rax, [rbp+arg_30]
0x18002449c  mov     [rax], ecx
0x18002449e  jmp     loc_18002452D
0x1800244a3  mov     rsi, [rbp+arg_30]
0x1800244a7  cmp     [rsi], ecx
0x1800244a9  jnb     short loc_1800244B4
0x1800244ab  mov     ebx, 0C0000023h
0x1800244b0  mov     [rsi], ecx
0x1800244b2  jmp     short loc_18002452D
0x1800244b4  mov     rdx, [rdi+40h]; Src
0x1800244b8  mov     r8, rcx; Size
0x1800244bb  mov     rcx, rax; void *
0x1800244be  call    memcpy_0
0x1800244c3  mov     eax, [rdi+38h]
0x1800244c6  mov     [rsi], eax
0x1800244c8  jmp     short loc_18002452D
0x1800244ca  mov     rax, [rbp+arg_20]
0x1800244ce  mov     [rax], edx
0x1800244d0  mov     rdx, [rbp+arg_28]
0x1800244d4  mov     rax, [rbp+arg_30]
0x1800244d8  test    rdx, rdx
0x1800244db  jnz     short loc_1800244E5
0x1800244dd  mov     dword ptr [rax], 4
0x1800244e3  jmp     short loc_18002452D
0x1800244e5  mov     ecx, [rax]
0x1800244e7  mov     dword ptr [rax], 4
0x1800244ed  cmp     ecx, 4
0x1800244f0  jb      short loc_180024521
0x1800244f2  mov     eax, [rdi+38h]
0x1800244f5  mov     [rdx], eax
0x1800244f7  jmp     short loc_18002452D
0x1800244f9  mov     rax, [rbp+arg_20]
0x1800244fd  mov     [rax], edx
0x1800244ff  mov     rdx, [rbp+arg_28]
0x180024503  mov     rax, [rbp+arg_30]
0x180024507  test    rdx, rdx
0x18002450a  jnz     short loc_180024514
0x18002450c  mov     dword ptr [rax], 1
0x180024512  jmp     short loc_18002452D
0x180024514  mov     ecx, [rax]
0x180024516  mov     dword ptr [rax], 1
0x18002451c  cmp     ecx, 1
0x18002451f  jnb     short loc_180024528
0x180024521  mov     ebx, 0C0000023h
0x180024526  jmp     short loc_18002452D
0x180024528  mov     cl, [rdi+38h]
0x18002452b  mov     [rdx], cl
0x18002452d  mov     eax, ebx
0x18002452f  add     rsp, 50h
0x180024533  pop     r14
0x180024535  pop     r13
0x180024537  pop     r12
0x180024539  pop     rdi
0x18002453a  pop     rsi
0x18002453b  pop     rbx
0x18002453c  pop     rbp
0x18002453d  retn
```
