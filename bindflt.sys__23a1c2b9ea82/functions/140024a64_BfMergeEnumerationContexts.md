# BfMergeEnumerationContexts

- ea: `0x140024a64`
- end: `0x140024e3b`
- name: `BfMergeEnumerationContexts`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024e50`

## callees

- `0x140004bc0`
- `0x140004be0`
- `0x14000f608`
- `0x14000f71c`
- `0x140022d98`
- `0x1400232a0`
- `0x140024a64`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024b9f`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024bc8`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024bf1`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024b9f`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024bc8`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140024bf1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c0b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c65`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024dc7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c0b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024c65`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140024dc7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140024aeb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140024aeb`

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
0x140024a64  mov     [rsp-38h+arg_0], rbx
0x140024a69  mov     [rsp-38h+arg_18], r9b
0x140024a6e  mov     [rsp-38h+arg_10], r8b
0x140024a73  push    rbp
0x140024a74  push    rsi
0x140024a75  push    rdi
0x140024a76  push    r12
0x140024a78  push    r13
0x140024a7a  push    r14
0x140024a7c  push    r15
0x140024a7e  mov     rbp, rsp
0x140024a81  sub     rsp, 70h
0x140024a85  xor     edi, edi
0x140024a87  lea     r8, [rbp+var_1C]
0x140024a8b  mov     rax, rdx
0x140024a8e  mov     [rbp+var_40], edi
0x140024a91  lea     rdx, [rbp+var_40]
0x140024a95  mov     [rbp+var_1C], edi
0x140024a98  mov     esi, edi
0x140024a9a  mov     [rbp+var_20], edi
0x140024a9d  mov     r12d, edi
0x140024aa0  call    BfGetFileInformationClassOffsets
0x140024aa5  mov     r13d, [rbp+var_40]
0x140024aa9  lea     rcx, [rbp+var_30]
0x140024aad  lea     rdx, [rbp+var_30]
0x140024ab1  mov     [rbp+var_30], rcx
0x140024ab5  mov     [rbp+Entry], rdx
0x140024ab9  cmp     r13d, [rbp+arg_20]
0x140024abd  jnb     loc_140024E04
0x140024ac3  add     rax, 60h ; '`'
0x140024ac7  mov     [rbp+var_8], rax
0x140024acb  mov     r15, rdi
0x140024ace  mov     [rbp+String2], rdi
0x140024ad2  mov     [rbp+var_3C], edi
0x140024ad5  mov     [rbp+Src], edi
0x140024ad8  mov     rdi, [rax]
0x140024adb  cmp     rdi, rax
0x140024ade  jz      loc_140024E02
0x140024ae4  lea     rcx, stru_14000B500; Lookaside
0x140024aeb  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140024af2  nop     dword ptr [rax+rax+00h]
0x140024af7  mov     rbx, rax
0x140024afa  test    rax, rax
0x140024afd  jz      loc_140024DF6
0x140024b03  mov     r14d, [rdi+30h]
0x140024b07  test    r14d, r14d
0x140024b0a  jz      loc_140024C5B
0x140024b10  mov     ecx, [rbp+var_1C]
0x140024b13  mov     esi, [rdi+34h]
0x140024b16  add     rsi, [rdi+40h]
0x140024b1a  mov     eax, [rcx+rsi]
0x140024b1d  lea     ecx, [rax+r13]
0x140024b21  cmp     ecx, r14d
0x140024b24  jbe     short loc_140024B2B
0x140024b26  sub     r14d, r13d
0x140024b29  jmp     short loc_140024B2E
0x140024b2b  mov     r14d, eax
0x140024b2e  test    rsi, rsi
0x140024b31  jz      loc_140024C5B
0x140024b37  add     r13, rsi
0x140024b3a  test    r15, r15
0x140024b3d  jnz     short loc_140024B7F
0x140024b3f  mov     [rbx+10h], rdi
0x140024b43  lea     rcx, [rbp+var_30]
0x140024b47  mov     eax, [rsi]
0x140024b49  mov     [rbx+18h], eax
0x140024b4c  mov     rax, [rbp+Entry]
0x140024b50  cmp     [rax], rcx
0x140024b53  jnz     loc_140024DEF
0x140024b59  lea     rcx, [rbp+var_30]
0x140024b5d  mov     [rbp+String2], r13
0x140024b61  mov     r13d, [rbp+var_40]
0x140024b65  mov     r15, rsi
0x140024b68  mov     [rbx], rcx
0x140024b6b  mov     [rbx+8], rax
0x140024b6f  mov     [rax], rbx
0x140024b72  mov     [rbp+Entry], rbx
0x140024b76  mov     [rbp+var_3C], r14d
0x140024b7a  jmp     loc_140024C75
0x140024b7f  mov     r9d, [rbp+var_3C]
0x140024b83  mov     rcx, r13; String1
0x140024b86  mov     r8, [rbp+String2]; String2
0x140024b8a  mov     eax, r14d
0x140024b8d  shr     rax, 1
0x140024b90  mov     rdx, rax; String1Length
0x140024b93  shr     r9, 1; String2Length
0x140024b96  mov     [rbp+String1Length], rax
0x140024b9a  mov     [rsp+70h+CaseInSensitive], 1; CaseInSensitive
0x140024b9f  call    cs:__imp_RtlCompareUnicodeStrings
0x140024ba6  nop     dword ptr [rax+rax+00h]
0x140024bab  test    eax, eax
0x140024bad  jle     short loc_140024C1D
0x140024baf  mov     rdx, [rbp+String1Length]; String1Length
0x140024bb3  lea     r8, String2; "."
0x140024bba  mov     r9d, 1; String2Length
0x140024bc0  mov     [rsp+70h+CaseInSensitive], 1; CaseInSensitive
0x140024bc5  mov     rcx, r13; String1
0x140024bc8  call    cs:__imp_RtlCompareUnicodeStrings
0x140024bcf  nop     dword ptr [rax+rax+00h]
0x140024bd4  test    eax, eax
0x140024bd6  jz      short loc_140024C1F
0x140024bd8  mov     rdx, [rbp+String1Length]; String1Length
0x140024bdc  lea     r8, asc_140008BA4; ".."
0x140024be3  mov     r9d, 2; String2Length
0x140024be9  mov     [rsp+70h+CaseInSensitive], 1; CaseInSensitive
0x140024bee  mov     rcx, r13; String1
0x140024bf1  call    cs:__imp_RtlCompareUnicodeStrings
0x140024bf8  nop     dword ptr [rax+rax+00h]
0x140024bfd  test    eax, eax
0x140024bff  jz      short loc_140024C1F
0x140024c01  mov     rdx, rbx; Entry
0x140024c04  lea     rcx, stru_14000B500; Lookaside
0x140024c0b  call    cs:__imp_ExFreeToPagedLookasideList
0x140024c12  nop     dword ptr [rax+rax+00h]
0x140024c17  mov     r13d, [rbp+var_40]
0x140024c1b  jmp     short loc_140024C71
0x140024c1d  jns     short loc_140024C2D
0x140024c1f  lea     rcx, [rbp+var_30]
0x140024c23  call    BfFreeEnumerationConflictList
0x140024c28  jmp     loc_140024B3F
0x140024c2d  mov     [rbx+10h], rdi
0x140024c31  lea     rcx, [rbp+var_30]
0x140024c35  mov     eax, [rsi]
0x140024c37  mov     [rbx+18h], eax
0x140024c3a  mov     rax, [rbp+Entry]
0x140024c3e  cmp     [rax], rcx
0x140024c41  jnz     loc_140024DEF
0x140024c47  mov     [rbx+8], rax
0x140024c4b  lea     rcx, [rbp+var_30]
0x140024c4f  mov     [rbx], rcx
0x140024c52  mov     [rax], rbx
0x140024c55  mov     [rbp+Entry], rbx
0x140024c59  jmp     short loc_140024C17
0x140024c5b  mov     rdx, rbx; Entry
0x140024c5e  lea     rcx, stru_14000B500; Lookaside
0x140024c65  call    cs:__imp_ExFreeToPagedLookasideList
0x140024c6c  nop     dword ptr [rax+rax+00h]
0x140024c71  mov     r14d, [rbp+var_3C]
0x140024c75  mov     rdi, [rdi]
0x140024c78  cmp     rdi, [rbp+var_8]
0x140024c7c  jnz     loc_140024AE4
0x140024c82  xor     edi, edi
0x140024c84  test    r15, r15
0x140024c87  jz      loc_140024DFD
0x140024c8d  mov     esi, [rbp+var_20]
0x140024c90  lea     ebx, [r14+r13]
0x140024c94  lea     eax, [rbx+rsi]
0x140024c97  cmp     eax, [rbp+arg_20]
0x140024c9a  ja      loc_140024E04
0x140024ca0  mov     r14b, [rbp+arg_18]
0x140024ca4  mov     r12d, esi
0x140024ca7  add     r12, [rbp+arg_28]
0x140024cab  mov     rdx, r15; Src
0x140024cae  cmp     [rbp+arg_10], 0
0x140024cb2  mov     rcx, r12; void *
0x140024cb5  mov     edi, ebx
0x140024cb7  mov     r8d, edi; Size
0x140024cba  jz      short loc_140024CC3
0x140024cbc  call    RtlCopyToUser
0x140024cc1  jmp     short loc_140024CC8
0x140024cc3  call    RtlCopyVolatileMemory
0x140024cc8  lea     eax, [rbx+7]
0x140024ccb  and     eax, 0FFFFFFF8h
0x140024cce  mov     [rbp+Src], eax
0x140024cd1  cmp     eax, [rbp+arg_20]
0x140024cd4  jbe     short loc_140024CDB
0x140024cd6  mov     [rbp+Src], ebx
0x140024cd9  mov     eax, ebx
0x140024cdb  sub     eax, ebx
0x140024cdd  lea     rcx, [rbx+r12]; void *
0x140024ce1  xor     edi, edi
0x140024ce3  mov     r8d, eax; Size
0x140024ce6  xor     edx, edx; Val
0x140024ce8  cmp     [rbp+arg_10], dil
0x140024cec  jz      short loc_140024D05
0x140024cee  call    RtlSetUserMemory
0x140024cf3  lea     r8d, [rdi+4]; Size
0x140024cf7  mov     rcx, r12; void *
0x140024cfa  lea     rdx, [rbp+Src]; Src
0x140024cfe  call    RtlCopyToUser
0x140024d03  jmp     short loc_140024D1C
0x140024d05  call    RtlSetVolatileMemory
0x140024d0a  mov     r8d, 4; Size
0x140024d10  lea     rdx, [rbp+Src]; Src
0x140024d14  mov     rcx, r12; void *
0x140024d17  call    RtlCopyVolatileMemory
0x140024d1c  add     esi, [rbp+Src]
0x140024d1f  mov     [rbp+var_20], esi
0x140024d22  lea     rax, [rbp+var_30]
0x140024d26  cmp     [rbp+var_30], rax
0x140024d2a  jz      loc_140024DD8
0x140024d30  mov     rdx, [rbp+Entry]; Entry
0x140024d34  lea     rax, [rbp+var_30]
0x140024d38  cmp     [rdx], rax
0x140024d3b  jnz     loc_140024DEF
0x140024d41  mov     rax, [rdx+8]
0x140024d45  cmp     [rax], rdx
0x140024d48  jnz     loc_140024DEF
0x140024d4e  mov     [rbp+Entry], rax
0x140024d52  lea     rcx, [rbp+var_30]
0x140024d56  mov     [rax], rcx
0x140024d59  mov     eax, [rdx+18h]
0x140024d5c  mov     rcx, [rdx+10h]
0x140024d60  test    eax, eax
0x140024d62  jnz     short loc_140024D83
0x140024d64  mov     eax, [rcx+30h]
0x140024d67  add     [rcx+34h], eax
0x140024d6a  mov     rax, [rdx+10h]
0x140024d6e  mov     [rax+30h], edi
0x140024d71  mov     rax, [rdx+10h]
0x140024d75  cmp     [rax+20h], rdi
0x140024d79  jz      short loc_140024DC0
0x140024d7b  cmp     [rax+11h], dil
0x140024d7f  jnz     short loc_140024DC0
0x140024d81  jmp     short loc_140024DBD
0x140024d83  mov     r8d, [rcx+30h]
0x140024d87  mov     r9d, [rcx+34h]
0x140024d8b  cmp     eax, r8d
0x140024d8e  jbe     short loc_140024D99
0x140024d90  lea     eax, [r8+r9]
0x140024d94  mov     [rcx+34h], eax
0x140024d97  jmp     short loc_140024D6A
0x140024d99  add     eax, r9d
0x140024d9c  mov     [rcx+34h], eax
0x140024d9f  mov     eax, [rdx+18h]
0x140024da2  mov     rcx, [rdx+10h]
0x140024da6  sub     [rcx+30h], eax
0x140024da9  mov     rax, [rdx+10h]
0x140024dad  cmp     [rax+30h], r13d
0x140024db1  jnb     short loc_140024DC0
0x140024db3  mov     [rax+30h], edi
0x140024db6  mov     rax, [rdx+10h]
0x140024dba  mov     [rax+34h], edi
0x140024dbd  mov     r14b, 1
0x140024dc0  lea     rcx, stru_14000B500; Lookaside
0x140024dc7  call    cs:__imp_ExFreeToPagedLookasideList
0x140024dce  nop     dword ptr [rax+rax+00h]
0x140024dd3  jmp     loc_140024D22
0x140024dd8  test    r14b, r14b
0x140024ddb  jnz     short loc_140024E04
0x140024ddd  lea     eax, [rsi+r13]
0x140024de1  cmp     eax, [rbp+arg_20]
0x140024de4  jnb     short loc_140024E04
0x140024de6  mov     rax, [rbp+var_8]
0x140024dea  jmp     loc_140024ACB
0x140024def  mov     ecx, 3
0x140024df4  int     29h; Win8: RtlFailFast(ecx)
0x140024df6  mov     ebx, 0C000009Ah
0x140024dfb  jmp     short loc_140024E17
0x140024dfd  mov     esi, [rbp+var_20]
0x140024e00  jmp     short loc_140024E04
0x140024e02  xor     edi, edi
0x140024e04  mov     rcx, [rbp+arg_30]
0x140024e08  mov     ebx, edi
0x140024e0a  mov     [rcx], esi
0x140024e0c  test    esi, esi
0x140024e0e  jz      short loc_140024E17
0x140024e10  mov     rcx, [rbp+arg_38]
0x140024e14  mov     [rcx], r12
0x140024e17  lea     rcx, [rbp+var_30]
0x140024e1b  call    BfFreeEnumerationConflictList
0x140024e20  mov     eax, ebx
0x140024e22  mov     rbx, [rsp+70h+arg_0]
0x140024e2a  add     rsp, 70h
0x140024e2e  pop     r15
0x140024e30  pop     r14
0x140024e32  pop     r13
0x140024e34  pop     r12
0x140024e36  pop     rdi
0x140024e37  pop     rsi
0x140024e38  pop     rbp
0x140024e39  retn
```
