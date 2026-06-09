# BfMergeEnumerationContexts

- ea: `0x140024a58`
- end: `0x140024e2f`
- name: `BfMergeEnumerationContexts`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024e40`

## callees

- `0x140004bc0`
- `0x140004be0`
- `0x14000f608`
- `0x14000f71c`
- `0x140022e88`
- `0x140023390`
- `0x140024a58`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024b93`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024bbc`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024be5`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024b93`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024bbc`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024be5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024bff`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c59`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024dbb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024bff`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c59`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024dbb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140024adf`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140024adf`

## pseudocode

```c
__int64 __fastcall BfMergeEnumerationContexts(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        unsigned int a5,
        __int64 a6,
        unsigned int *a7,
        _QWORD *a8)
{
  unsigned int v8; // esi
  char *v9; // r12
  __int64 FileInformationClassOffsets; // rax
  __int64 v11; // r13
  _QWORD *v12; // rax
  void *v13; // r15
  _QWORD *v14; // rdi
  _QWORD *v15; // rbx
  unsigned int v16; // r14d
  _DWORD *v17; // rsi
  unsigned int v18; // r14d
  const WCHAR *v19; // r13
  _QWORD *v20; // rax
  LONG v21; // eax
  _QWORD *v22; // rax
  __int64 v23; // rbx
  char v24; // r14
  unsigned int v25; // eax
  char *v26; // rcx
  _DWORD *v27; // rdx
  PVOID *v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned int v32; // r8d
  int v33; // r9d
  __int64 v34; // rax
  unsigned int v35; // ebx
  unsigned int v37; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v38; // [rsp+34h] [rbp-3Ch]
  unsigned int Src; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v40; // [rsp+40h] [rbp-30h] BYREF
  PVOID Entry; // [rsp+48h] [rbp-28h]
  unsigned int v42; // [rsp+50h] [rbp-20h]
  unsigned int v43; // [rsp+54h] [rbp-1Ch] BYREF
  PCWCH String2; // [rsp+58h] [rbp-18h]
  SIZE_T String1Length; // [rsp+60h] [rbp-10h]
  _QWORD *v46; // [rsp+68h] [rbp-8h]

  v37 = 0;
  v43 = 0;
  v8 = 0;
  v42 = 0;
  v9 = 0;
  FileInformationClassOffsets = BfGetFileInformationClassOffsets(a1, &v37, &v43);
  v11 = v37;
  v40 = &v40;
  Entry = &v40;
  if ( v37 < a5 )
  {
    v12 = (_QWORD *)(FileInformationClassOffsets + 96);
    v46 = v12;
LABEL_3:
    v13 = 0;
    String2 = 0;
    v38 = 0;
    Src = 0;
    v14 = (_QWORD *)*v12;
    if ( (_QWORD *)*v12 != v12 )
    {
      while ( 1 )
      {
        v15 = ExAllocateFromPagedLookasideList(&stru_14000B500);
        if ( !v15 )
        {
          v35 = -1073741670;
          goto LABEL_58;
        }
        v16 = *((_DWORD *)v14 + 12);
        if ( v16
          && ((v17 = (_DWORD *)(v14[8] + *((unsigned int *)v14 + 13)), *(_DWORD *)((char *)v17 + v43) + (int)v11 <= v16)
            ? (v18 = *(_DWORD *)((char *)v17 + v43))
            : (v18 = v16 - v11),
              v17) )
        {
          v19 = (const WCHAR *)((char *)v17 + v11);
          if ( !v13 )
            goto LABEL_11;
          String1Length = (unsigned __int64)v18 >> 1;
          v21 = RtlCompareUnicodeStrings(v19, String1Length, String2, (unsigned __int64)v38 >> 1, 1u);
          if ( v21 <= 0 )
          {
            if ( v21 < 0 )
              goto LABEL_19;
            v15[2] = v14;
            *((_DWORD *)v15 + 6) = *v17;
            v22 = Entry;
            if ( *(_QWORD ***)Entry != &v40 )
LABEL_53:
              __fastfail(3u);
            v15[1] = Entry;
            *v15 = &v40;
            *v22 = v15;
            Entry = v15;
          }
          else
          {
            if ( !RtlCompareUnicodeStrings(v19, String1Length, L".", 1u, 1u)
              || !RtlCompareUnicodeStrings(v19, String1Length, L"..", 2u, 1u) )
            {
LABEL_19:
              BfFreeEnumerationConflictList(&v40);
LABEL_11:
              v15[2] = v14;
              *((_DWORD *)v15 + 6) = *v17;
              v20 = Entry;
              if ( *(_QWORD ***)Entry != &v40 )
                goto LABEL_53;
              String2 = v19;
              v11 = v37;
              v13 = v17;
              *v15 = &v40;
              v15[1] = v20;
              *v20 = v15;
              Entry = v15;
              v38 = v18;
              goto LABEL_24;
            }
            ExFreeToPagedLookasideList(&stru_14000B500, v15);
          }
          v11 = v37;
        }
        else
        {
          ExFreeToPagedLookasideList(&stru_14000B500, v15);
        }
        v18 = v38;
LABEL_24:
        v14 = (_QWORD *)*v14;
        if ( v14 == v46 )
        {
          if ( !v13 )
          {
            v8 = v42;
            break;
          }
          v8 = v42;
          v23 = v18 + (unsigned int)v11;
          if ( (unsigned int)v23 + v42 > a5 )
            break;
          v24 = a4;
          v9 = (char *)(a6 + v42);
          if ( a3 )
            RtlCopyToUser(v9, v13, (unsigned int)v23);
          else
            RtlCopyVolatileMemory(v9, v13, (unsigned int)v23);
          v25 = (v23 + 7) & 0xFFFFFFF8;
          Src = v25;
          if ( v25 > a5 )
          {
            Src = v23;
            v25 = v23;
          }
          v26 = &v9[v23];
          if ( a3 )
          {
            RtlSetUserMemory(v26);
            RtlCopyToUser(v9, &Src, 4u);
          }
          else
          {
            RtlSetVolatileMemory(v26, 0, v25 - (unsigned int)v23);
            RtlCopyVolatileMemory(v9, &Src, 4u);
          }
          v8 += Src;
          v42 = v8;
LABEL_36:
          if ( v40 == &v40 )
          {
            if ( !v24 && v8 + (unsigned int)v11 < a5 )
            {
              v12 = v46;
              goto LABEL_3;
            }
            break;
          }
          v27 = Entry;
          if ( *(_QWORD ***)Entry != &v40 )
            goto LABEL_53;
          v28 = (PVOID *)*((_QWORD *)Entry + 1);
          if ( *v28 != Entry )
            goto LABEL_53;
          Entry = (PVOID)*((_QWORD *)Entry + 1);
          *v28 = &v40;
          v29 = v27[6];
          v30 = *((_QWORD *)v27 + 2);
          if ( v29 )
          {
            v32 = *(_DWORD *)(v30 + 48);
            v33 = *(_DWORD *)(v30 + 52);
            if ( v29 > v32 )
            {
              *(_DWORD *)(v30 + 52) = v32 + v33;
              goto LABEL_41;
            }
            *(_DWORD *)(v30 + 52) = v33 + v29;
            *(_DWORD *)(*((_QWORD *)v27 + 2) + 48LL) -= v27[6];
            v34 = *((_QWORD *)v27 + 2);
            if ( *(_DWORD *)(v34 + 48) < (unsigned int)v11 )
            {
              *(_DWORD *)(v34 + 48) = 0;
              *(_DWORD *)(*((_QWORD *)v27 + 2) + 52LL) = 0;
              goto LABEL_48;
            }
          }
          else
          {
            *(_DWORD *)(v30 + 52) += *(_DWORD *)(v30 + 48);
LABEL_41:
            *(_DWORD *)(*((_QWORD *)v27 + 2) + 48LL) = 0;
            v31 = *((_QWORD *)v27 + 2);
            if ( *(_QWORD *)(v31 + 32) && !*(_BYTE *)(v31 + 17) )
LABEL_48:
              v24 = 1;
          }
          ExFreeToPagedLookasideList(&stru_14000B500, v27);
          goto LABEL_36;
        }
      }
    }
  }
  v35 = 0;
  *a7 = v8;
  if ( v8 )
    *a8 = v9;
LABEL_58:
  BfFreeEnumerationConflictList(&v40);
  return v35;
}

```

## disassembly

```asm
0x140024a58  mov     [rsp-38h+arg_0], rbx
0x140024a5d  mov     [rsp-38h+arg_18], r9b
0x140024a62  mov     [rsp-38h+arg_10], r8b
0x140024a67  push    rbp
0x140024a68  push    rsi
0x140024a69  push    rdi
0x140024a6a  push    r12
0x140024a6c  push    r13
0x140024a6e  push    r14
0x140024a70  push    r15
0x140024a72  mov     rbp, rsp
0x140024a75  sub     rsp, 70h
0x140024a79  xor     edi, edi
0x140024a7b  lea     r8, [rbp+var_1C]
0x140024a7f  mov     rax, rdx
0x140024a82  mov     [rbp+var_40], edi
0x140024a85  lea     rdx, [rbp+var_40]
0x140024a89  mov     [rbp+var_1C], edi
0x140024a8c  mov     esi, edi
0x140024a8e  mov     [rbp+var_20], edi
0x140024a91  mov     r12d, edi
0x140024a94  call    BfGetFileInformationClassOffsets
0x140024a99  mov     r13d, [rbp+var_40]
0x140024a9d  lea     rcx, [rbp+var_30]
0x140024aa1  lea     rdx, [rbp+var_30]
0x140024aa5  mov     [rbp+var_30], rcx
0x140024aa9  mov     [rbp+Entry], rdx
0x140024aad  cmp     r13d, [rbp+arg_20]
0x140024ab1  jnb     loc_140024DF8
0x140024ab7  add     rax, 60h ; '`'
0x140024abb  mov     [rbp+var_8], rax
0x140024abf  mov     r15, rdi
0x140024ac2  mov     [rbp+String2], rdi
0x140024ac6  mov     [rbp+var_3C], edi
0x140024ac9  mov     [rbp+Src], edi
0x140024acc  mov     rdi, [rax]
0x140024acf  cmp     rdi, rax
0x140024ad2  jz      loc_140024DF6
0x140024ad8  lea     rcx, stru_14000B500; Lookaside
0x140024adf  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140024ae6  nop     dword ptr [rax+rax+00h]
0x140024aeb  mov     rbx, rax
0x140024aee  test    rax, rax
0x140024af1  jz      loc_140024DEA
0x140024af7  mov     r14d, [rdi+30h]
0x140024afb  test    r14d, r14d
0x140024afe  jz      loc_140024C4F
0x140024b04  mov     ecx, [rbp+var_1C]
0x140024b07  mov     esi, [rdi+34h]
0x140024b0a  add     rsi, [rdi+40h]
0x140024b0e  mov     eax, [rcx+rsi]
0x140024b11  lea     ecx, [rax+r13]
0x140024b15  cmp     ecx, r14d
0x140024b18  jbe     short loc_140024B1F
0x140024b1a  sub     r14d, r13d
0x140024b1d  jmp     short loc_140024B22
0x140024b1f  mov     r14d, eax
0x140024b22  test    rsi, rsi
0x140024b25  jz      loc_140024C4F
0x140024b2b  add     r13, rsi
0x140024b2e  test    r15, r15
0x140024b31  jnz     short loc_140024B73
0x140024b33  mov     [rbx+10h], rdi
0x140024b37  lea     rcx, [rbp+var_30]
0x140024b3b  mov     eax, [rsi]
0x140024b3d  mov     [rbx+18h], eax
0x140024b40  mov     rax, [rbp+Entry]
0x140024b44  cmp     [rax], rcx
0x140024b47  jnz     loc_140024DE3
0x140024b4d  lea     rcx, [rbp+var_30]
0x140024b51  mov     [rbp+String2], r13
0x140024b55  mov     r13d, [rbp+var_40]
0x140024b59  mov     r15, rsi
0x140024b5c  mov     [rbx], rcx
0x140024b5f  mov     [rbx+8], rax
0x140024b63  mov     [rax], rbx
0x140024b66  mov     [rbp+Entry], rbx
0x140024b6a  mov     [rbp+var_3C], r14d
0x140024b6e  jmp     loc_140024C69
0x140024b73  mov     r9d, [rbp+var_3C]
0x140024b77  mov     rcx, r13; String1
0x140024b7a  mov     r8, [rbp+String2]; String2
0x140024b7e  mov     eax, r14d
0x140024b81  shr     rax, 1
0x140024b84  mov     rdx, rax; String1Length
0x140024b87  shr     r9, 1; String2Length
0x140024b8a  mov     [rbp+String1Length], rax
0x140024b8e  mov     [rsp+70h+CaseInSensitive], 1; CaseInSensitive
0x140024b93  call    cs:__imp_RtlCompareUnicodeStrings
0x140024b9a  nop     dword ptr [rax+rax+00h]
0x140024b9f  test    eax, eax
0x140024ba1  jle     short loc_140024C11
0x140024ba3  mov     rdx, [rbp+String1Length]; String1Length
0x140024ba7  lea     r8, String2; "."
0x140024bae  mov     r9d, 1; String2Length
0x140024bb4  mov     [rsp+70h+CaseInSensitive], 1; CaseInSensitive
0x140024bb9  mov     rcx, r13; String1
0x140024bbc  call    cs:__imp_RtlCompareUnicodeStrings
0x140024bc3  nop     dword ptr [rax+rax+00h]
0x140024bc8  test    eax, eax
0x140024bca  jz      short loc_140024C13
0x140024bcc  mov     rdx, [rbp+String1Length]; String1Length
0x140024bd0  lea     r8, asc_140008BA4; ".."
0x140024bd7  mov     r9d, 2; String2Length
0x140024bdd  mov     [rsp+70h+CaseInSensitive], 1; CaseInSensitive
0x140024be2  mov     rcx, r13; String1
0x140024be5  call    cs:__imp_RtlCompareUnicodeStrings
0x140024bec  nop     dword ptr [rax+rax+00h]
0x140024bf1  test    eax, eax
0x140024bf3  jz      short loc_140024C13
0x140024bf5  mov     rdx, rbx; Entry
0x140024bf8  lea     rcx, stru_14000B500; Lookaside
0x140024bff  call    cs:__imp_ExFreeToPagedLookasideList
0x140024c06  nop     dword ptr [rax+rax+00h]
0x140024c0b  mov     r13d, [rbp+var_40]
0x140024c0f  jmp     short loc_140024C65
0x140024c11  jns     short loc_140024C21
0x140024c13  lea     rcx, [rbp+var_30]
0x140024c17  call    BfFreeEnumerationConflictList
0x140024c1c  jmp     loc_140024B33
0x140024c21  mov     [rbx+10h], rdi
0x140024c25  lea     rcx, [rbp+var_30]
0x140024c29  mov     eax, [rsi]
0x140024c2b  mov     [rbx+18h], eax
0x140024c2e  mov     rax, [rbp+Entry]
0x140024c32  cmp     [rax], rcx
0x140024c35  jnz     loc_140024DE3
0x140024c3b  mov     [rbx+8], rax
0x140024c3f  lea     rcx, [rbp+var_30]
0x140024c43  mov     [rbx], rcx
0x140024c46  mov     [rax], rbx
0x140024c49  mov     [rbp+Entry], rbx
0x140024c4d  jmp     short loc_140024C0B
0x140024c4f  mov     rdx, rbx; Entry
0x140024c52  lea     rcx, stru_14000B500; Lookaside
0x140024c59  call    cs:__imp_ExFreeToPagedLookasideList
0x140024c60  nop     dword ptr [rax+rax+00h]
0x140024c65  mov     r14d, [rbp+var_3C]
0x140024c69  mov     rdi, [rdi]
0x140024c6c  cmp     rdi, [rbp+var_8]
0x140024c70  jnz     loc_140024AD8
0x140024c76  xor     edi, edi
0x140024c78  test    r15, r15
0x140024c7b  jz      loc_140024DF1
0x140024c81  mov     esi, [rbp+var_20]
0x140024c84  lea     ebx, [r14+r13]
0x140024c88  lea     eax, [rbx+rsi]
0x140024c8b  cmp     eax, [rbp+arg_20]
0x140024c8e  ja      loc_140024DF8
0x140024c94  mov     r14b, [rbp+arg_18]
0x140024c98  mov     r12d, esi
0x140024c9b  add     r12, [rbp+arg_28]
0x140024c9f  mov     rdx, r15; Src
0x140024ca2  cmp     [rbp+arg_10], 0
0x140024ca6  mov     rcx, r12; void *
0x140024ca9  mov     edi, ebx
0x140024cab  mov     r8d, edi; Size
0x140024cae  jz      short loc_140024CB7
0x140024cb0  call    RtlCopyToUser
0x140024cb5  jmp     short loc_140024CBC
0x140024cb7  call    RtlCopyVolatileMemory
0x140024cbc  lea     eax, [rbx+7]
0x140024cbf  and     eax, 0FFFFFFF8h
0x140024cc2  mov     [rbp+Src], eax
0x140024cc5  cmp     eax, [rbp+arg_20]
0x140024cc8  jbe     short loc_140024CCF
0x140024cca  mov     [rbp+Src], ebx
0x140024ccd  mov     eax, ebx
0x140024ccf  sub     eax, ebx
0x140024cd1  lea     rcx, [rbx+r12]; void *
0x140024cd5  xor     edi, edi
0x140024cd7  mov     r8d, eax; Size
0x140024cda  xor     edx, edx; Val
0x140024cdc  cmp     [rbp+arg_10], dil
0x140024ce0  jz      short loc_140024CF9
0x140024ce2  call    RtlSetUserMemory
0x140024ce7  lea     r8d, [rdi+4]; Size
0x140024ceb  mov     rcx, r12; void *
0x140024cee  lea     rdx, [rbp+Src]; Src
0x140024cf2  call    RtlCopyToUser
0x140024cf7  jmp     short loc_140024D10
0x140024cf9  call    RtlSetVolatileMemory
0x140024cfe  mov     r8d, 4; Size
0x140024d04  lea     rdx, [rbp+Src]; Src
0x140024d08  mov     rcx, r12; void *
0x140024d0b  call    RtlCopyVolatileMemory
0x140024d10  add     esi, [rbp+Src]
0x140024d13  mov     [rbp+var_20], esi
0x140024d16  lea     rax, [rbp+var_30]
0x140024d1a  cmp     [rbp+var_30], rax
0x140024d1e  jz      loc_140024DCC
0x140024d24  mov     rdx, [rbp+Entry]; Entry
0x140024d28  lea     rax, [rbp+var_30]
0x140024d2c  cmp     [rdx], rax
0x140024d2f  jnz     loc_140024DE3
0x140024d35  mov     rax, [rdx+8]
0x140024d39  cmp     [rax], rdx
0x140024d3c  jnz     loc_140024DE3
0x140024d42  mov     [rbp+Entry], rax
0x140024d46  lea     rcx, [rbp+var_30]
0x140024d4a  mov     [rax], rcx
0x140024d4d  mov     eax, [rdx+18h]
0x140024d50  mov     rcx, [rdx+10h]
0x140024d54  test    eax, eax
0x140024d56  jnz     short loc_140024D77
0x140024d58  mov     eax, [rcx+30h]
0x140024d5b  add     [rcx+34h], eax
0x140024d5e  mov     rax, [rdx+10h]
0x140024d62  mov     [rax+30h], edi
0x140024d65  mov     rax, [rdx+10h]
0x140024d69  cmp     [rax+20h], rdi
0x140024d6d  jz      short loc_140024DB4
0x140024d6f  cmp     [rax+11h], dil
0x140024d73  jnz     short loc_140024DB4
0x140024d75  jmp     short loc_140024DB1
0x140024d77  mov     r8d, [rcx+30h]
0x140024d7b  mov     r9d, [rcx+34h]
0x140024d7f  cmp     eax, r8d
0x140024d82  jbe     short loc_140024D8D
0x140024d84  lea     eax, [r8+r9]
0x140024d88  mov     [rcx+34h], eax
0x140024d8b  jmp     short loc_140024D5E
0x140024d8d  add     eax, r9d
0x140024d90  mov     [rcx+34h], eax
0x140024d93  mov     eax, [rdx+18h]
0x140024d96  mov     rcx, [rdx+10h]
0x140024d9a  sub     [rcx+30h], eax
0x140024d9d  mov     rax, [rdx+10h]
0x140024da1  cmp     [rax+30h], r13d
0x140024da5  jnb     short loc_140024DB4
0x140024da7  mov     [rax+30h], edi
0x140024daa  mov     rax, [rdx+10h]
0x140024dae  mov     [rax+34h], edi
0x140024db1  mov     r14b, 1
0x140024db4  lea     rcx, stru_14000B500; Lookaside
0x140024dbb  call    cs:__imp_ExFreeToPagedLookasideList
0x140024dc2  nop     dword ptr [rax+rax+00h]
0x140024dc7  jmp     loc_140024D16
0x140024dcc  test    r14b, r14b
0x140024dcf  jnz     short loc_140024DF8
0x140024dd1  lea     eax, [rsi+r13]
0x140024dd5  cmp     eax, [rbp+arg_20]
0x140024dd8  jnb     short loc_140024DF8
0x140024dda  mov     rax, [rbp+var_8]
0x140024dde  jmp     loc_140024ABF
0x140024de3  mov     ecx, 3
0x140024de8  int     29h; Win8: RtlFailFast(ecx)
0x140024dea  mov     ebx, 0C000009Ah
0x140024def  jmp     short loc_140024E0B
0x140024df1  mov     esi, [rbp+var_20]
0x140024df4  jmp     short loc_140024DF8
0x140024df6  xor     edi, edi
0x140024df8  mov     rcx, [rbp+arg_30]
0x140024dfc  mov     ebx, edi
0x140024dfe  mov     [rcx], esi
0x140024e00  test    esi, esi
0x140024e02  jz      short loc_140024E0B
0x140024e04  mov     rcx, [rbp+arg_38]
0x140024e08  mov     [rcx], r12
0x140024e0b  lea     rcx, [rbp+var_30]
0x140024e0f  call    BfFreeEnumerationConflictList
0x140024e14  mov     eax, ebx
0x140024e16  mov     rbx, [rsp+70h+arg_0]
0x140024e1e  add     rsp, 70h
0x140024e22  pop     r15
0x140024e24  pop     r14
0x140024e26  pop     r13
0x140024e28  pop     r12
0x140024e2a  pop     rdi
0x140024e2b  pop     rsi
0x140024e2c  pop     rbp
0x140024e2d  retn
```
