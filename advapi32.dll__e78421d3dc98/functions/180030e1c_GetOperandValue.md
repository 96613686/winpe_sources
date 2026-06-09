# GetOperandValue

- ea: `0x180030e1c`
- end: `0x18003143c`
- name: `GetOperandValue`
- size: `1568`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003073c`
- `0x180030e1c`

## callees

- `0x18001ca94`
- `0x180030e1c`
- `0x180031444`
- `0x1800314f4`
- `0x18005340c`
- `0x1800538e0`
- `0x180053918`
- `0x180053970`
- `0x1800539ec`
- `0x180053bfc`
- `0x180065042`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180030eaa`
- `msvcrt!_wcsnicmp` at `0x18003110c`
- `msvcrt!_wcsnicmp` at `0x180030eaa`
- `msvcrt!_wcsnicmp` at `0x18003110c`
- `msvcrt!_wcstoui64` at `0x1800312c2`
- `msvcrt!_wcstoui64` at `0x18003132e`
- `msvcrt!_wcstoui64` at `0x1800312c2`
- `msvcrt!_wcstoui64` at `0x18003132e`
- `msvcrt!_errno` at `0x1800312b0`
- `msvcrt!_errno` at `0x1800312e8`
- `msvcrt!_errno` at `0x1800312fd`
- `msvcrt!_errno` at `0x1800312b0`
- `msvcrt!_errno` at `0x1800312e8`
- `msvcrt!_errno` at `0x1800312fd`
- `ntdll!RtlLengthSid` at `0x1800311cd`
- `ntdll!RtlLengthSid` at `0x1800311cd`
- `KERNELBASE!LocalAlloc` at `0x180030e76`
- `KERNELBASE!LocalAlloc` at `0x18003100d`
- `KERNELBASE!LocalAlloc` at `0x180031233`
- `KERNELBASE!LocalAlloc` at `0x18003139e`
- `KERNELBASE!LocalAlloc` at `0x180030e76`
- `KERNELBASE!LocalAlloc` at `0x18003100d`
- `KERNELBASE!LocalAlloc` at `0x180031233`
- `KERNELBASE!LocalAlloc` at `0x18003139e`
- `KERNEL32!LocalFree` at `0x180031419`
- `KERNEL32!LocalFree` at `0x180031419`

## pseudocode

```c
__int64 __fastcall GetOperandValue(
        wchar_t *a1,
        char a2,
        char a3,
        HLOCAL *a4,
        unsigned int *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9)
{
  unsigned int *v9; // r15
  char v13; // r13
  HLOCAL v14; // rax
  unsigned int AttributeName; // edi
  unsigned int StringOperandValue; // eax
  HLOCAL v17; // rbx
  _BYTE *v18; // rax
  char v19; // r12
  unsigned int v20; // ecx
  wchar_t *v21; // rcx
  __int64 v22; // rcx
  char v23; // al
  __int64 v24; // rcx
  __int64 v25; // r10
  _DWORD *v26; // rdx
  char v27; // r13
  unsigned int v28; // r9d
  unsigned int v29; // r10d
  unsigned int v30; // r14d
  __int64 v31; // rax
  _QWORD *v32; // rdi
  HLOCAL v33; // rax
  __int64 v34; // r8
  wchar_t v35; // dx
  char v36; // r14
  __int64 v37; // r14
  bool v38; // zf
  PSID v39; // rcx
  ULONG v40; // eax
  _DWORD *v41; // rcx
  unsigned int v42; // r13d
  _BYTE *v43; // rax
  __int64 v44; // r14
  HLOCAL v45; // rax
  __int64 v46; // r8
  __int64 v47; // r8
  __int64 v48; // r9
  int v49; // r8d
  __int64 v50; // r10
  __int64 v51; // r12
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // r15
  wchar_t v54; // ax
  unsigned __int64 v55; // rax
  __int16 v56; // r13
  _BYTE *v57; // rax
  _QWORD *v58; // rax
  _QWORD *v59; // rcx
  char v61; // [rsp+50h] [rbp-30h] BYREF
  char v62[3]; // [rsp+51h] [rbp-2Fh] BYREF
  unsigned int v63; // [rsp+54h] [rbp-2Ch] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-28h]
  HLOCAL v65; // [rsp+60h] [rbp-20h] BYREF
  wchar_t *EndPtr; // [rsp+68h] [rbp-18h] BYREF
  PSID Sid; // [rsp+70h] [rbp-10h] BYREF
  __int64 v68; // [rsp+78h] [rbp-8h] BYREF
  char v70; // [rsp+D8h] [rbp+58h] BYREF

  v9 = a5;
  v63 = 0;
  v62[0] = 0;
  v61 = 0;
  EndPtr = 0;
  hMem = 0;
  v13 = a3;
  Sid = 0;
  v70 = 0;
  v65 = 0;
  v68 = 0;
  *a5 = 0;
  v14 = LocalAlloc(0x40u, 0x10u);
  *a4 = v14;
  if ( !v14 )
    goto LABEL_2;
  if ( a2 || !_wcsnicmp(a1, L"@", 1u) )
  {
    AttributeName = GetAttributeName(a1);
    if ( AttributeName )
      goto LABEL_76;
    goto LABEL_78;
  }
  if ( *a1 == 34 )
  {
    StringOperandValue = GetStringOperandValue(a1, a4, v9);
    v17 = hMem;
    AttributeName = StringOperandValue;
    if ( !StringOperandValue )
      goto LABEL_79;
    goto LABEL_77;
  }
  AttributeName = 0;
  if ( *a1 == 123 )
  {
    v18 = *a4;
    v19 = 0;
    v63 = 1;
    v20 = 1;
    v18[1] = 80;
    while ( a1[v20] )
    {
      AttributeName = GetNextNoneWhiteSpace(a1, &v63);
      if ( AttributeName )
        goto LABEL_76;
      v21 = &a1[v63];
      if ( *v21 == 123 )
        goto LABEL_31;
      AttributeName = GetOperandValue((_DWORD)v21, 0, 0, (unsigned int)&v65, (__int64)v9, a6, a7, a8, a9);
      if ( AttributeName )
        goto LABEL_76;
      if ( v13 )
      {
        if ( v19 && v19 != *((_BYTE *)v65 + 1) )
          goto LABEL_31;
        v19 = *((_BYTE *)v65 + 1);
      }
      LOBYTE(v22) = *((_BYTE *)v65 + 1);
      v23 = IsValueSizeFixed(v22);
      v26 = *a4;
      v27 = v23;
      v28 = v23 != 0 ? 1 : 5;
      if ( *((_QWORD *)*a4 + 1) )
      {
        v29 = v26[1] + *(_DWORD *)(v25 + 4);
        if ( v29 < v26[1] || (v30 = v29 + v28, v29 + v28 < v29) )
        {
LABEL_32:
          AttributeName = 534;
          goto LABEL_76;
        }
        LOBYTE(v24) = -v23;
        v31 = SddlpReAlloc(v24, v30);
        v32 = *a4;
        *((_QWORD *)*a4 + 1) = v31;
        if ( !v31 )
          goto LABEL_2;
      }
      else
      {
        v30 = v28 + *(_DWORD *)(v25 + 4);
        if ( v30 < v28 )
          goto LABEL_32;
        v33 = LocalAlloc(0x40u, v30);
        v32 = *a4;
        *((_QWORD *)*a4 + 1) = v33;
      }
      v34 = v32[1];
      if ( !v34 )
        goto LABEL_2;
      *(_BYTE *)(*((unsigned int *)v32 + 1) + v34) = *((_BYTE *)v65 + 1);
      if ( !v27 )
        *(_DWORD *)(*((unsigned int *)v32 + 1) + v32[1] + 1LL) = *((_DWORD *)v65 + 1);
      memcpy_0(
        (void *)(v32[1] + *((unsigned int *)v32 + 1) + (-(__int64)(v27 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 5),
        *((const void **)v65 + 1),
        *((unsigned int *)v65 + 1));
      *((_DWORD *)v32 + 1) = v30;
      FreeOperandValue(v65);
      v63 += *v9;
      v65 = 0;
      AttributeName = GetNextNoneWhiteSpace(a1, &v63);
      if ( AttributeName )
        goto LABEL_76;
      v35 = a1[v63];
      if ( v35 != 44 )
      {
        v17 = hMem;
        if ( v35 != 125 )
          goto LABEL_35;
        *v9 = v63 + 1;
        goto LABEL_79;
      }
      v13 = a3;
      v20 = ++v63;
    }
    goto LABEL_78;
  }
  v36 = 3;
  if ( !_wcsnicmp(a1, L"SID", 3u) )
  {
    v63 = 3;
    AttributeName = GetNextNoneWhiteSpace(a1, &v63);
    if ( AttributeName )
      goto LABEL_76;
    if ( a1[v63] == 40 )
    {
      v37 = v63 + 1;
      AttributeName = LocalGetSidForString(
                        2 * (int)v37 + (int)a1,
                        (unsigned int)&Sid,
                        (unsigned int)&v68,
                        (unsigned int)&v70,
                        a6,
                        a7,
                        a8,
                        a9);
      if ( AttributeName
        || (v63 = v37 + ((v68 - 2 * v37 - (__int64)a1) >> 1), (AttributeName = GetNextNoneWhiteSpace(a1, &v63)) != 0) )
      {
        v17 = Sid;
      }
      else
      {
        v38 = a1[v63] == 41;
        v17 = Sid;
        if ( v38 )
        {
          v39 = Sid;
          *v9 = v63 + 1;
          *((_BYTE *)*a4 + 1) = 81;
          v40 = RtlLengthSid(v39);
          v41 = *a4;
          v41[1] = v40;
          *((_QWORD *)v41 + 1) = v17;
          v17 = 0;
          *(_BYTE *)v41 = v70 == 0;
          goto LABEL_79;
        }
LABEL_35:
        AttributeName = 1336;
      }
      goto LABEL_77;
    }
    goto LABEL_31;
  }
  GetBinaryOperandLen(a1, &v63);
  if ( *a1 != 35 )
  {
    v51 = v63;
    if ( !v63 )
      goto LABEL_31;
    *v9 = v63;
    *_errno() = 0;
    v52 = _wcstoui64(a1, &EndPtr, 0);
    v53 = v52;
    if ( EndPtr == a1 && !v52 )
      goto LABEL_31;
    if ( EndPtr != &a1[v51] || *_errno() == 34 && v53 != -1 || *_errno() == 34 && v53 == -1 )
      goto LABEL_31;
    v54 = *a1;
    if ( *a1 == 45 )
    {
      v55 = _wcstoui64(++a1, &EndPtr, 0);
      if ( v55 >= v53 && v55 )
        goto LABEL_31;
      v54 = *a1;
      v56 = 2;
    }
    else if ( v54 == 43 )
    {
      ++a1;
      v56 = 1;
      v54 = *a1;
    }
    else
    {
      v56 = 3;
    }
    if ( v54 == 48 )
    {
      if ( a1 + 1 >= EndPtr || ((a1[1] - 88) & 0xFFDF) != 0 )
        v36 = 1;
    }
    else
    {
      v36 = 2;
    }
    v57 = *a4;
    v57[1] = 4;
    *((_DWORD *)v57 + 1) = 10;
    v58 = LocalAlloc(0x40u, 0xAu);
    v59 = *a4;
    v17 = hMem;
    *((_QWORD *)*a4 + 1) = v58;
    if ( v58 )
    {
      *v58 = v53;
      *(_WORD *)(v59[1] + 8LL) = v56;
      *(_BYTE *)(v59[1] + 9LL) = v36;
      goto LABEL_79;
    }
    AttributeName = 8;
    goto LABEL_77;
  }
  v42 = v63;
  if ( v63 < 2 )
  {
LABEL_31:
    AttributeName = 1336;
    goto LABEL_76;
  }
  v43 = *a4;
  *v9 = v63;
  LODWORD(v44) = v42 >> 1;
  v43[1] = 24;
  *((_DWORD *)v43 + 1) = v42 >> 1;
  v45 = LocalAlloc(0x40u, v42 >> 1);
  *((_QWORD *)*a4 + 1) = v45;
  if ( !v45 )
  {
LABEL_2:
    AttributeName = 8;
LABEL_76:
    v17 = hMem;
LABEL_77:
    FreeOperandValue(*a4);
    *a4 = 0;
    goto LABEL_79;
  }
  v46 = v42 - 1;
  while ( (int)v46 >= 1 )
  {
    if ( !(unsigned __int8)GetDigitFromChar(a1[(int)v46], v62, v46)
      || !(unsigned __int8)GetDigitFromChar(a1[v48 - 1], &v61, v47) )
    {
      goto LABEL_2;
    }
    v44 = (unsigned int)(v44 - 1);
    v46 = (unsigned int)(v49 - 2);
    *(_BYTE *)(v44 + *(_QWORD *)(v50 + 8)) = v62[0] | (16 * v61);
  }
LABEL_78:
  v17 = hMem;
LABEL_79:
  if ( v65 )
    FreeOperandValue(v65);
  if ( v17 && v70 )
    LocalFree(v17);
  return AttributeName;
}

```

## disassembly

```asm
0x180030e1c  mov     [rsp-38h+arg_0], rbx
0x180030e21  mov     [rsp-38h+arg_10], r8b
0x180030e26  push    rbp
0x180030e27  push    rsi
0x180030e28  push    rdi
0x180030e29  push    r12
0x180030e2b  push    r13
0x180030e2d  push    r14
0x180030e2f  push    r15
0x180030e31  mov     rbp, rsp
0x180030e34  sub     rsp, 80h
0x180030e3b  mov     r15, [rbp+arg_20]
0x180030e3f  xor     eax, eax
0x180030e41  mov     dil, dl
0x180030e44  mov     [rbp+var_2C], eax
0x180030e47  mov     rbx, rcx
0x180030e4a  mov     [rbp+var_2F], al
0x180030e4d  mov     rsi, r9
0x180030e50  mov     [rbp+var_30], al
0x180030e53  lea     edx, [rax+10h]; uBytes
0x180030e56  mov     [rbp+EndPtr], rax
0x180030e5a  lea     ecx, [rax+40h]; uFlags
0x180030e5d  mov     [rbp+hMem], rax
0x180030e61  mov     r13b, r8b
0x180030e64  mov     [rbp+Sid], rax
0x180030e68  mov     [rbp+arg_18], al
0x180030e6b  mov     [rbp+var_20], rax
0x180030e6f  mov     [rbp+var_8], rax
0x180030e73  mov     [r15], eax
0x180030e76  call    cs:__imp_LocalAlloc
0x180030e7c  mov     [rsi], rax
0x180030e7f  test    rax, rax
0x180030e82  jnz     short loc_180030E8E
0x180030e84  mov     edi, 8
0x180030e89  jmp     loc_1800313E3
0x180030e8e  test    dil, dil
0x180030e91  jnz     loc_1800313CF
0x180030e97  mov     r14d, 1
0x180030e9d  lea     rdx, asc_18007E024; "@"
0x180030ea4  mov     r8d, r14d; MaxCount
0x180030ea7  mov     rcx, rbx; String1
0x180030eaa  call    cs:__imp__wcsnicmp
0x180030eb0  xor     ecx, ecx
0x180030eb2  test    eax, eax
0x180030eb4  jz      loc_1800313CF
0x180030eba  lea     eax, [rcx+22h]
0x180030ebd  cmp     [rbx], ax
0x180030ec0  jnz     short loc_180030EE3
0x180030ec2  mov     r8, r15
0x180030ec5  mov     rdx, rsi
0x180030ec8  mov     rcx, rbx
0x180030ecb  call    GetStringOperandValue
0x180030ed0  mov     rbx, [rbp+hMem]
0x180030ed4  mov     edi, eax
0x180030ed6  test    eax, eax
0x180030ed8  jz      loc_1800313FC
0x180030ede  jmp     loc_1800313E7
0x180030ee3  cmp     word ptr [rbx], 7Bh ; '{'
0x180030ee7  mov     edi, ecx
0x180030ee9  jnz     loc_1800310F9
0x180030eef  mov     rax, [rsi]
0x180030ef2  mov     r12b, cl
0x180030ef5  mov     [rbp+var_2C], r14d
0x180030ef9  mov     ecx, r14d
0x180030efc  mov     byte ptr [rax+1], 50h ; 'P'
0x180030f00  mov     eax, ecx
0x180030f02  xor     r11d, r11d
0x180030f05  cmp     [rbx+rax*2], r11w
0x180030f0a  jz      loc_1800313F8
0x180030f10  lea     rdx, [rbp+var_2C]
0x180030f14  mov     rcx, rbx
0x180030f17  call    GetNextNoneWhiteSpace
0x180030f1c  mov     edi, eax
0x180030f1e  test    eax, eax
0x180030f20  jnz     loc_1800313E3
0x180030f26  mov     eax, [rbp+var_2C]
0x180030f29  lea     rcx, [rbx+rax*2]
0x180030f2d  cmp     word ptr [rcx], 7Bh ; '{'
0x180030f31  jz      loc_1800310C6
0x180030f37  mov     al, [rbp+arg_40]
0x180030f3d  lea     r9, [rbp+var_20]
0x180030f41  mov     [rsp+80h+var_40], al
0x180030f45  xor     r8d, r8d
0x180030f48  mov     rax, [rbp+arg_38]
0x180030f4c  xor     edx, edx
0x180030f4e  mov     [rsp+80h+var_48], rax
0x180030f53  mov     rax, [rbp+arg_30]
0x180030f57  mov     [rsp+80h+var_50], rax
0x180030f5c  mov     rax, [rbp+arg_28]
0x180030f60  mov     [rsp+80h+var_58], rax
0x180030f65  mov     [rsp+80h+var_60], r15
0x180030f6a  call    GetOperandValue
0x180030f6f  mov     edi, eax
0x180030f71  test    eax, eax
0x180030f73  jnz     loc_1800313E3
0x180030f79  mov     r10, [rbp+var_20]
0x180030f7d  test    r13b, r13b
0x180030f80  jz      short loc_180030F95
0x180030f82  test    r12b, r12b
0x180030f85  jz      short loc_180030F91
0x180030f87  cmp     r12b, [r10+1]
0x180030f8b  jnz     loc_1800310C6
0x180030f91  mov     r12b, [r10+1]
0x180030f95  mov     cl, [r10+1]
0x180030f99  call    IsValueSizeFixed
0x180030f9e  mov     rdx, [rsi]
0x180030fa1  mov     cl, al
0x180030fa3  neg     cl
0x180030fa5  mov     r13b, al
0x180030fa8  sbb     r9d, r9d
0x180030fab  mov     r8, [rdx+8]
0x180030faf  and     r9d, 0FFFFFFFCh
0x180030fb3  add     r9d, 5
0x180030fb7  test    r8, r8
0x180030fba  jz      short loc_180030FF5
0x180030fbc  mov     r10d, [r10+4]
0x180030fc0  add     r10d, [rdx+4]
0x180030fc4  cmp     r10d, [rdx+4]
0x180030fc8  jb      loc_1800310D0
0x180030fce  lea     r14d, [r10+r9]
0x180030fd2  cmp     r14d, r10d
0x180030fd5  jb      loc_1800310D0
0x180030fdb  mov     edx, r14d
0x180030fde  call    SddlpReAlloc
0x180030fe3  mov     rdi, [rsi]
0x180030fe6  mov     [rdi+8], rax
0x180030fea  test    rax, rax
0x180030fed  jz      loc_180030E84
0x180030ff3  jmp     short loc_18003101A
0x180030ff5  mov     r14d, [r10+4]
0x180030ff9  add     r14d, r9d
0x180030ffc  cmp     r14d, r9d
0x180030fff  jb      loc_1800310D0
0x180031005  mov     edx, r14d; uBytes
0x180031008  mov     ecx, 40h ; '@'; uFlags
0x18003100d  call    cs:__imp_LocalAlloc
0x180031013  mov     rdi, [rsi]
0x180031016  mov     [rdi+8], rax
0x18003101a  mov     r8, [rdi+8]
0x18003101e  test    r8, r8
0x180031021  jz      loc_180030E84
0x180031027  mov     rax, [rbp+var_20]
0x18003102b  mov     edx, [rdi+4]
0x18003102e  mov     cl, [rax+1]
0x180031031  mov     [rdx+r8], cl
0x180031035  test    r13b, r13b
0x180031038  jnz     short loc_18003104E
0x18003103a  mov     rax, [rbp+var_20]
0x18003103e  mov     r8d, [rdi+4]
0x180031042  mov     rdx, [rdi+8]
0x180031046  mov     ecx, [rax+4]
0x180031049  mov     [r8+rdx+1], ecx
0x18003104e  mov     rdx, [rbp+var_20]
0x180031052  neg     r13b
0x180031055  mov     eax, [rdi+4]
0x180031058  sbb     rcx, rcx
0x18003105b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18003105f  mov     r8d, [rdx+4]; Size
0x180031063  add     rcx, 5
0x180031067  mov     rdx, [rdx+8]; Src
0x18003106b  add     rcx, rax
0x18003106e  add     rcx, [rdi+8]; void *
0x180031072  call    memcpy_0
0x180031077  mov     [rdi+4], r14d
0x18003107b  mov     rcx, [rbp+var_20]; hMem
0x18003107f  call    FreeOperandValue
0x180031084  mov     eax, [rbp+var_2C]
0x180031087  lea     rdx, [rbp+var_2C]
0x18003108b  add     eax, [r15]
0x18003108e  mov     rcx, rbx
0x180031091  mov     [rbp+var_2C], eax
0x180031094  mov     [rbp+var_20], 0
0x18003109c  call    GetNextNoneWhiteSpace
0x1800310a1  mov     edi, eax
0x1800310a3  test    eax, eax
0x1800310a5  jnz     loc_1800313E3
0x1800310ab  mov     ecx, [rbp+var_2C]
0x1800310ae  movzx   edx, word ptr [rbx+rcx*2]
0x1800310b2  cmp     dx, 2Ch ; ','
0x1800310b6  jnz     short loc_1800310DA
0x1800310b8  mov     r13b, [rbp+arg_10]
0x1800310bc  inc     ecx
0x1800310be  mov     [rbp+var_2C], ecx
0x1800310c1  jmp     loc_180030F00
0x1800310c6  mov     edi, 538h
0x1800310cb  jmp     loc_1800313E3
0x1800310d0  mov     edi, 216h
0x1800310d5  jmp     loc_1800313E3
0x1800310da  mov     rbx, [rbp+hMem]
0x1800310de  cmp     dx, 7Dh ; '}'
0x1800310e2  jnz     short loc_1800310EF
0x1800310e4  lea     eax, [rcx+1]
0x1800310e7  mov     [r15], eax
0x1800310ea  jmp     loc_1800313FC
0x1800310ef  mov     edi, 538h
0x1800310f4  jmp     loc_1800313E7
0x1800310f9  mov     r14d, 3
0x1800310ff  lea     rdx, aSid_0; "SID"
0x180031106  mov     r8d, r14d; MaxCount
0x180031109  mov     rcx, rbx; String1
0x18003110c  call    cs:__imp__wcsnicmp
0x180031112  lea     rdx, [rbp+var_2C]
0x180031116  mov     rcx, rbx
0x180031119  test    eax, eax
0x18003111b  jnz     loc_1800311F5
0x180031121  mov     [rbp+var_2C], r14d
0x180031125  call    GetNextNoneWhiteSpace
0x18003112a  mov     edi, eax
0x18003112c  test    eax, eax
0x18003112e  jnz     loc_1800313E3
0x180031134  mov     ecx, [rbp+var_2C]
0x180031137  cmp     word ptr [rbx+rcx*2], 28h ; '('
0x18003113c  jnz     short loc_1800310C6
0x18003113e  mov     al, [rbp+arg_40]
0x180031144  lea     r14d, [rcx+1]
0x180031148  mov     byte ptr [rsp+80h+var_48], al
0x18003114c  lea     r12, [r14+r14]
0x180031150  mov     rax, [rbp+arg_38]
0x180031154  lea     rcx, [r12+rbx]
0x180031158  mov     [rsp+80h+var_50], rax
0x18003115d  lea     r9, [rbp+arg_18]
0x180031161  mov     rax, [rbp+arg_30]
0x180031165  lea     r8, [rbp+var_8]
0x180031169  mov     [rsp+80h+var_58], rax
0x18003116e  lea     rdx, [rbp+Sid]
0x180031172  mov     rax, [rbp+arg_28]
0x180031176  mov     [rsp+80h+var_60], rax
0x18003117b  call    LocalGetSidForString
0x180031180  mov     edi, eax
0x180031182  test    eax, eax
0x180031184  jnz     short loc_1800311EC
0x180031186  mov     rax, [rbp+var_8]
0x18003118a  lea     rdx, [rbp+var_2C]
0x18003118e  sub     rax, r12
0x180031191  mov     rcx, rbx
0x180031194  sub     rax, rbx
0x180031197  sar     rax, 1
0x18003119a  add     eax, r14d
0x18003119d  mov     [rbp+var_2C], eax
0x1800311a0  call    GetNextNoneWhiteSpace
0x1800311a5  mov     edi, eax
0x1800311a7  test    eax, eax
0x1800311a9  jnz     short loc_1800311EC
0x1800311ab  mov     ecx, [rbp+var_2C]
0x1800311ae  cmp     word ptr [rbx+rcx*2], 29h ; ')'
0x1800311b3  mov     rbx, [rbp+Sid]
0x1800311b7  jnz     loc_1800310EF
0x1800311bd  lea     eax, [rcx+1]
0x1800311c0  mov     rcx, rbx; Sid
0x1800311c3  mov     [r15], eax
0x1800311c6  mov     rax, [rsi]
0x1800311c9  mov     byte ptr [rax+1], 51h ; 'Q'
0x1800311cd  call    cs:__imp_RtlLengthSid
0x1800311d3  mov     rcx, [rsi]
0x1800311d6  mov     [rcx+4], eax
0x1800311d9  mov     [rcx+8], rbx
0x1800311dd  xor     ebx, ebx
0x1800311df  cmp     [rbp+arg_18], bl
0x1800311e2  setz    al
0x1800311e5  mov     [rcx], al
0x1800311e7  jmp     loc_1800313FC
0x1800311ec  mov     rbx, [rbp+Sid]
0x1800311f0  jmp     loc_1800313E7
0x1800311f5  call    GetBinaryOperandLen
0x1800311fa  cmp     word ptr [rbx], 23h ; '#'
0x1800311fe  jnz     loc_1800312A0
0x180031204  mov     r13d, [rbp+var_2C]
0x180031208  mov     r12d, 2
0x18003120e  cmp     r13d, r12d
0x180031211  jb      loc_1800310C6
0x180031217  mov     rax, [rsi]
0x18003121a  lea     ecx, [r12+3Eh]; uFlags
0x18003121f  mov     r14d, r13d
0x180031222  mov     [r15], r13d
0x180031225  shr     r14d, 1
0x180031228  mov     edx, r14d; uBytes
0x18003122b  mov     byte ptr [rax+1], 18h
0x18003122f  mov     [rax+4], r14d
0x180031233  call    cs:__imp_LocalAlloc
0x180031239  mov     r10, [rsi]
0x18003123c  mov     [r10+8], rax
0x180031240  test    rax, rax
0x180031243  jz      loc_180030E84
0x180031249  lea     r8d, [r13-1]
0x18003124d  cmp     r8d, 1
0x180031251  jl      loc_1800313F8
0x180031257  movsxd  r9, r8d
0x18003125a  lea     rdx, [rbp+var_2F]
0x18003125e  movzx   ecx, word ptr [rbx+r9*2]
0x180031263  call    GetDigitFromChar
0x180031268  test    al, al
0x18003126a  jz      loc_180030E84
0x180031270  movzx   ecx, word ptr [rbx+r9*2-2]
0x180031276  lea     rdx, [rbp+var_30]
0x18003127a  call    GetDigitFromChar
0x18003127f  test    al, al
0x180031281  jz      loc_180030E84
0x180031287  mov     dl, [rbp+var_30]
0x18003128a  dec     r14d
0x18003128d  mov     rax, [r10+8]
  ... truncated ...
```
