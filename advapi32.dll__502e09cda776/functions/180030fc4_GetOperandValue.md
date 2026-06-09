# GetOperandValue

- ea: `0x180030fc4`
- end: `0x180031633`
- name: `GetOperandValue`
- size: `1647`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180030854`
- `0x180030fc4`

## callees

- `0x18001b630`
- `0x180030fc4`
- `0x18003163c`
- `0x1800316f0`
- `0x18005ef14`
- `0x18005f468`
- `0x18005f4ac`
- `0x18005f508`
- `0x18005f584`
- `0x18005f7d4`
- `0x180072042`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180031058`
- `msvcrt!_wcsnicmp` at `0x1800312c6`
- `msvcrt!_wcsnicmp` at `0x180031058`
- `msvcrt!_wcsnicmp` at `0x1800312c6`
- `msvcrt!_wcstoui64` at `0x180031494`
- `msvcrt!_wcstoui64` at `0x180031512`
- `msvcrt!_wcstoui64` at `0x180031494`
- `msvcrt!_wcstoui64` at `0x180031512`
- `msvcrt!_errno` at `0x18003147c`
- `msvcrt!_errno` at `0x1800314c0`
- `msvcrt!_errno` at `0x1800314db`
- `msvcrt!_errno` at `0x18003147c`
- `msvcrt!_errno` at `0x1800314c0`
- `msvcrt!_errno` at `0x1800314db`
- `ntdll!RtlLengthSid` at `0x18003138d`
- `ntdll!RtlLengthSid` at `0x18003138d`
- `KERNELBASE!LocalAlloc` at `0x18003101e`
- `KERNELBASE!LocalAlloc` at `0x1800311c1`
- `KERNELBASE!LocalAlloc` at `0x1800313f9`
- `KERNELBASE!LocalAlloc` at `0x180031588`
- `KERNELBASE!LocalAlloc` at `0x18003101e`
- `KERNELBASE!LocalAlloc` at `0x1800311c1`
- `KERNELBASE!LocalAlloc` at `0x1800313f9`
- `KERNELBASE!LocalAlloc` at `0x180031588`
- `KERNEL32!LocalFree` at `0x180031609`
- `KERNEL32!LocalFree` at `0x180031609`

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
0x180030fc4  mov     [rsp-38h+arg_0], rbx
0x180030fc9  mov     [rsp-38h+arg_10], r8b
0x180030fce  push    rbp
0x180030fcf  push    rsi
0x180030fd0  push    rdi
0x180030fd1  push    r12
0x180030fd3  push    r13
0x180030fd5  push    r14
0x180030fd7  push    r15
0x180030fd9  mov     rbp, rsp
0x180030fdc  sub     rsp, 80h
0x180030fe3  mov     r15, [rbp+arg_20]
0x180030fe7  xor     eax, eax
0x180030fe9  mov     dil, dl
0x180030fec  mov     [rbp+var_2C], eax
0x180030fef  mov     rbx, rcx
0x180030ff2  mov     [rbp+var_2F], al
0x180030ff5  mov     rsi, r9
0x180030ff8  mov     [rbp+var_30], al
0x180030ffb  lea     edx, [rax+10h]; uBytes
0x180030ffe  mov     [rbp+EndPtr], rax
0x180031002  lea     ecx, [rax+40h]; uFlags
0x180031005  mov     [rbp+hMem], rax
0x180031009  mov     r13b, r8b
0x18003100c  mov     [rbp+Sid], rax
0x180031010  mov     [rbp+arg_18], al
0x180031013  mov     [rbp+var_20], rax
0x180031017  mov     [rbp+var_8], rax
0x18003101b  mov     [r15], eax
0x18003101e  call    cs:__imp_LocalAlloc
0x180031025  nop     dword ptr [rax+rax+00h]
0x18003102a  mov     [rsi], rax
0x18003102d  test    rax, rax
0x180031030  jnz     short loc_18003103C
0x180031032  mov     edi, 8
0x180031037  jmp     loc_1800315D3
0x18003103c  test    dil, dil
0x18003103f  jnz     loc_1800315BF
0x180031045  mov     r14d, 1
0x18003104b  lea     rdx, asc_18008BDA8; "@"
0x180031052  mov     r8d, r14d; MaxCount
0x180031055  mov     rcx, rbx; String1
0x180031058  call    cs:__imp__wcsnicmp
0x18003105f  nop     dword ptr [rax+rax+00h]
0x180031064  xor     ecx, ecx
0x180031066  test    eax, eax
0x180031068  jz      loc_1800315BF
0x18003106e  lea     eax, [rcx+22h]
0x180031071  cmp     [rbx], ax
0x180031074  jnz     short loc_180031097
0x180031076  mov     r8, r15
0x180031079  mov     rdx, rsi
0x18003107c  mov     rcx, rbx
0x18003107f  call    GetStringOperandValue
0x180031084  mov     rbx, [rbp+hMem]
0x180031088  mov     edi, eax
0x18003108a  test    eax, eax
0x18003108c  jz      loc_1800315EC
0x180031092  jmp     loc_1800315D7
0x180031097  cmp     word ptr [rbx], 7Bh ; '{'
0x18003109b  mov     edi, ecx
0x18003109d  jnz     loc_1800312B3
0x1800310a3  mov     rax, [rsi]
0x1800310a6  mov     r12b, cl
0x1800310a9  mov     [rbp+var_2C], r14d
0x1800310ad  mov     ecx, r14d
0x1800310b0  mov     byte ptr [rax+1], 50h ; 'P'
0x1800310b4  mov     eax, ecx
0x1800310b6  xor     r11d, r11d
0x1800310b9  cmp     [rbx+rax*2], r11w
0x1800310be  jz      loc_1800315E8
0x1800310c4  lea     rdx, [rbp+var_2C]
0x1800310c8  mov     rcx, rbx
0x1800310cb  call    GetNextNoneWhiteSpace
0x1800310d0  mov     edi, eax
0x1800310d2  test    eax, eax
0x1800310d4  jnz     loc_1800315D3
0x1800310da  mov     eax, [rbp+var_2C]
0x1800310dd  lea     rcx, [rbx+rax*2]
0x1800310e1  cmp     word ptr [rcx], 7Bh ; '{'
0x1800310e5  jz      loc_180031280
0x1800310eb  mov     al, [rbp+arg_40]
0x1800310f1  lea     r9, [rbp+var_20]
0x1800310f5  mov     [rsp+80h+var_40], al
0x1800310f9  xor     r8d, r8d
0x1800310fc  mov     rax, [rbp+arg_38]
0x180031100  xor     edx, edx
0x180031102  mov     [rsp+80h+var_48], rax
0x180031107  mov     rax, [rbp+arg_30]
0x18003110b  mov     [rsp+80h+var_50], rax
0x180031110  mov     rax, [rbp+arg_28]
0x180031114  mov     [rsp+80h+var_58], rax
0x180031119  mov     [rsp+80h+var_60], r15
0x18003111e  call    GetOperandValue
0x180031123  mov     edi, eax
0x180031125  test    eax, eax
0x180031127  jnz     loc_1800315D3
0x18003112d  mov     r10, [rbp+var_20]
0x180031131  test    r13b, r13b
0x180031134  jz      short loc_180031149
0x180031136  test    r12b, r12b
0x180031139  jz      short loc_180031145
0x18003113b  cmp     r12b, [r10+1]
0x18003113f  jnz     loc_180031280
0x180031145  mov     r12b, [r10+1]
0x180031149  mov     cl, [r10+1]
0x18003114d  call    IsValueSizeFixed
0x180031152  mov     rdx, [rsi]
0x180031155  mov     cl, al
0x180031157  neg     cl
0x180031159  mov     r13b, al
0x18003115c  sbb     r9d, r9d
0x18003115f  mov     r8, [rdx+8]
0x180031163  and     r9d, 0FFFFFFFCh
0x180031167  add     r9d, 5
0x18003116b  test    r8, r8
0x18003116e  jz      short loc_1800311A9
0x180031170  mov     r10d, [r10+4]
0x180031174  add     r10d, [rdx+4]
0x180031178  cmp     r10d, [rdx+4]
0x18003117c  jb      loc_18003128A
0x180031182  lea     r14d, [r10+r9]
0x180031186  cmp     r14d, r10d
0x180031189  jb      loc_18003128A
0x18003118f  mov     edx, r14d
0x180031192  call    SddlpReAlloc
0x180031197  mov     rdi, [rsi]
0x18003119a  mov     [rdi+8], rax
0x18003119e  test    rax, rax
0x1800311a1  jz      loc_180031032
0x1800311a7  jmp     short loc_1800311D4
0x1800311a9  mov     r14d, [r10+4]
0x1800311ad  add     r14d, r9d
0x1800311b0  cmp     r14d, r9d
0x1800311b3  jb      loc_18003128A
0x1800311b9  mov     edx, r14d; uBytes
0x1800311bc  mov     ecx, 40h ; '@'; uFlags
0x1800311c1  call    cs:__imp_LocalAlloc
0x1800311c8  nop     dword ptr [rax+rax+00h]
0x1800311cd  mov     rdi, [rsi]
0x1800311d0  mov     [rdi+8], rax
0x1800311d4  mov     r8, [rdi+8]
0x1800311d8  test    r8, r8
0x1800311db  jz      loc_180031032
0x1800311e1  mov     rax, [rbp+var_20]
0x1800311e5  mov     edx, [rdi+4]
0x1800311e8  mov     cl, [rax+1]
0x1800311eb  mov     [rdx+r8], cl
0x1800311ef  test    r13b, r13b
0x1800311f2  jnz     short loc_180031208
0x1800311f4  mov     rax, [rbp+var_20]
0x1800311f8  mov     r8d, [rdi+4]
0x1800311fc  mov     rdx, [rdi+8]
0x180031200  mov     ecx, [rax+4]
0x180031203  mov     [r8+rdx+1], ecx
0x180031208  mov     rdx, [rbp+var_20]
0x18003120c  neg     r13b
0x18003120f  mov     eax, [rdi+4]
0x180031212  sbb     rcx, rcx
0x180031215  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180031219  mov     r8d, [rdx+4]; Size
0x18003121d  add     rcx, 5
0x180031221  mov     rdx, [rdx+8]; Src
0x180031225  add     rcx, rax
0x180031228  add     rcx, [rdi+8]; void *
0x18003122c  call    memcpy_0
0x180031231  mov     [rdi+4], r14d
0x180031235  mov     rcx, [rbp+var_20]; hMem
0x180031239  call    FreeOperandValue
0x18003123e  mov     eax, [rbp+var_2C]
0x180031241  lea     rdx, [rbp+var_2C]
0x180031245  add     eax, [r15]
0x180031248  mov     rcx, rbx
0x18003124b  mov     [rbp+var_2C], eax
0x18003124e  mov     [rbp+var_20], 0
0x180031256  call    GetNextNoneWhiteSpace
0x18003125b  mov     edi, eax
0x18003125d  test    eax, eax
0x18003125f  jnz     loc_1800315D3
0x180031265  mov     ecx, [rbp+var_2C]
0x180031268  movzx   edx, word ptr [rbx+rcx*2]
0x18003126c  cmp     dx, 2Ch ; ','
0x180031270  jnz     short loc_180031294
0x180031272  mov     r13b, [rbp+arg_10]
0x180031276  inc     ecx
0x180031278  mov     [rbp+var_2C], ecx
0x18003127b  jmp     loc_1800310B4
0x180031280  mov     edi, 538h
0x180031285  jmp     loc_1800315D3
0x18003128a  mov     edi, 216h
0x18003128f  jmp     loc_1800315D3
0x180031294  mov     rbx, [rbp+hMem]
0x180031298  cmp     dx, 7Dh ; '}'
0x18003129c  jnz     short loc_1800312A9
0x18003129e  lea     eax, [rcx+1]
0x1800312a1  mov     [r15], eax
0x1800312a4  jmp     loc_1800315EC
0x1800312a9  mov     edi, 538h
0x1800312ae  jmp     loc_1800315D7
0x1800312b3  mov     r14d, 3
0x1800312b9  lea     rdx, aSid_0; "SID"
0x1800312c0  mov     r8d, r14d; MaxCount
0x1800312c3  mov     rcx, rbx; String1
0x1800312c6  call    cs:__imp__wcsnicmp
0x1800312cd  nop     dword ptr [rax+rax+00h]
0x1800312d2  lea     rdx, [rbp+var_2C]
0x1800312d6  mov     rcx, rbx
0x1800312d9  test    eax, eax
0x1800312db  jnz     loc_1800313BB
0x1800312e1  mov     [rbp+var_2C], r14d
0x1800312e5  call    GetNextNoneWhiteSpace
0x1800312ea  mov     edi, eax
0x1800312ec  test    eax, eax
0x1800312ee  jnz     loc_1800315D3
0x1800312f4  mov     ecx, [rbp+var_2C]
0x1800312f7  cmp     word ptr [rbx+rcx*2], 28h ; '('
0x1800312fc  jnz     short loc_180031280
0x1800312fe  mov     al, [rbp+arg_40]
0x180031304  lea     r14d, [rcx+1]
0x180031308  mov     byte ptr [rsp+80h+var_48], al
0x18003130c  lea     r12, [r14+r14]
0x180031310  mov     rax, [rbp+arg_38]
0x180031314  lea     rcx, [r12+rbx]
0x180031318  mov     [rsp+80h+var_50], rax
0x18003131d  lea     r9, [rbp+arg_18]
0x180031321  mov     rax, [rbp+arg_30]
0x180031325  lea     r8, [rbp+var_8]
0x180031329  mov     [rsp+80h+var_58], rax
0x18003132e  lea     rdx, [rbp+Sid]
0x180031332  mov     rax, [rbp+arg_28]
0x180031336  mov     [rsp+80h+var_60], rax
0x18003133b  call    LocalGetSidForString
0x180031340  mov     edi, eax
0x180031342  test    eax, eax
0x180031344  jnz     short loc_1800313B2
0x180031346  mov     rax, [rbp+var_8]
0x18003134a  lea     rdx, [rbp+var_2C]
0x18003134e  sub     rax, r12
0x180031351  mov     rcx, rbx
0x180031354  sub     rax, rbx
0x180031357  sar     rax, 1
0x18003135a  add     eax, r14d
0x18003135d  mov     [rbp+var_2C], eax
0x180031360  call    GetNextNoneWhiteSpace
0x180031365  mov     edi, eax
0x180031367  test    eax, eax
0x180031369  jnz     short loc_1800313B2
0x18003136b  mov     ecx, [rbp+var_2C]
0x18003136e  cmp     word ptr [rbx+rcx*2], 29h ; ')'
0x180031373  mov     rbx, [rbp+Sid]
0x180031377  jnz     loc_1800312A9
0x18003137d  lea     eax, [rcx+1]
0x180031380  mov     rcx, rbx; Sid
0x180031383  mov     [r15], eax
0x180031386  mov     rax, [rsi]
0x180031389  mov     byte ptr [rax+1], 51h ; 'Q'
0x18003138d  call    cs:__imp_RtlLengthSid
0x180031394  nop     dword ptr [rax+rax+00h]
0x180031399  mov     rcx, [rsi]
0x18003139c  mov     [rcx+4], eax
0x18003139f  mov     [rcx+8], rbx
0x1800313a3  xor     ebx, ebx
0x1800313a5  cmp     [rbp+arg_18], bl
0x1800313a8  setz    al
0x1800313ab  mov     [rcx], al
0x1800313ad  jmp     loc_1800315EC
0x1800313b2  mov     rbx, [rbp+Sid]
0x1800313b6  jmp     loc_1800315D7
0x1800313bb  call    GetBinaryOperandLen
0x1800313c0  cmp     word ptr [rbx], 23h ; '#'
0x1800313c4  jnz     loc_18003146C
0x1800313ca  mov     r13d, [rbp+var_2C]
0x1800313ce  mov     r12d, 2
0x1800313d4  cmp     r13d, r12d
0x1800313d7  jb      loc_180031280
0x1800313dd  mov     rax, [rsi]
0x1800313e0  lea     ecx, [r12+3Eh]; uFlags
0x1800313e5  mov     r14d, r13d
0x1800313e8  mov     [r15], r13d
0x1800313eb  shr     r14d, 1
0x1800313ee  mov     edx, r14d; uBytes
0x1800313f1  mov     byte ptr [rax+1], 18h
0x1800313f5  mov     [rax+4], r14d
0x1800313f9  call    cs:__imp_LocalAlloc
0x180031400  nop     dword ptr [rax+rax+00h]
0x180031405  mov     r10, [rsi]
0x180031408  mov     [r10+8], rax
0x18003140c  test    rax, rax
0x18003140f  jz      loc_180031032
0x180031415  lea     r8d, [r13-1]
0x180031419  cmp     r8d, 1
0x18003141d  jl      loc_1800315E8
0x180031423  movsxd  r9, r8d
0x180031426  lea     rdx, [rbp+var_2F]
0x18003142a  movzx   ecx, word ptr [rbx+r9*2]
0x18003142f  call    GetDigitFromChar
0x180031434  test    al, al
0x180031436  jz      loc_180031032
0x18003143c  movzx   ecx, word ptr [rbx+r9*2-2]
0x180031442  lea     rdx, [rbp+var_30]
  ... truncated ...
```
