# sub_1801ADEB4

- ea: `0x1801adeb4`
- end: `0x1801ae3c6`
- name: `sub_1801ADEB4`
- size: `1298`
- prototype: `__int64 __fastcall(__int64, void *, const wchar_t *, __int16)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting`

## callers

- `0x1801ae8a8`

## callees

- `0x180001440`
- `0x180045ad0`
- `0x18011b15c`
- `0x18011b19c`
- `0x1801533d8`
- `0x1801ac0a8`
- `0x1801ac1ac`
- `0x1801ad300`
- `0x1801ad37c`
- `0x1801ad548`
- `0x1801ad7f8`
- `0x1801ad82c`
- `0x1801adac8`
- `0x1801adb7c`
- `0x1801adeb4`
- `0x1801af3c8`
- `0x1801af554`
- `0x1801b278c`
- `0x1801b28e8`
- `0x1801b2d5c`
- `0x1801d4f70`
- `0x1801d6010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1801ae2e0`
- `KERNEL32!GetTickCount` at `0x1801ae2e0`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1801ae162`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1801ae162`
- `Mso30Win32Client!Mso30Win32Client_55665` at `0x1801ae0b6`
- `Mso30Win32Client!Mso30Win32Client_55665` at `0x1801ae0b6`
- `ODBC32!SQLSetConnectOptionW` at `0x1801ae324`
- `ODBC32!SQLSetConnectOptionW` at `0x1801ae324`

## string_xrefs

- `0x1801ae0a8`: `sqlsrv32.dll`

## pseudocode

```c
__int64 __fastcall sub_1801ADEB4(__int64 a1, void *a2, const wchar_t *a3, __int16 a4)
{
  __int64 result; // rax
  __int64 v7; // r8
  unsigned int v8; // r13d
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // ecx
  char *v12; // rdi
  __int64 v13; // rsi
  _OWORD *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  __int128 v17; // xmm1
  bool v18; // zf
  char v19; // al
  __int64 v20; // r14
  __int64 v21; // rax
  __int64 v22; // rdx
  unsigned int v23; // esi
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // esi
  void **v27; // rsi
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rbx
  void **v31; // rsi
  __int64 v32; // rax
  size_t v33; // rbx
  SQLHDBC v34; // r14
  __int16 *v35; // rbx
  __int16 v36; // dx
  __int16 v37; // ax
  DWORD TickCount; // eax
  char v39; // cl
  int v40; // eax
  int v41; // eax
  unsigned __int16 v42; // ax
  int v43; // esi
  __int64 v44; // rbx
  _QWORD *v45; // rcx
  int v46; // [rsp+20h] [rbp-E0h]
  __int16 v47[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v48; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v49; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v50; // [rsp+3Ch] [rbp-C4h] BYREF
  __int16 v51; // [rsp+40h] [rbp-C0h]
  unsigned int v52; // [rsp+44h] [rbp-BCh] BYREF
  int v53; // [rsp+48h] [rbp-B8h]
  char *v54; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h]
  void *v56; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v57; // [rsp+68h] [rbp-98h]
  SQLHDBC hdbc; // [rsp+70h] [rbp-90h]
  char v59[1032]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t Str[512]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v61[1024]; // [rsp+890h] [rbp+790h] BYREF

  v51 = a4;
  hdbc = a2;
  v49 = 0;
  v52 = 0;
  v54 = 0;
  v56 = 0;
  v53 = 0;
  v48 = 0;
  v47[0] = 0;
  v50 = 0;
  v57 = qword_18025EC18;
  if ( !qword_18025EC18 )
  {
    result = sub_1801AD300();
    if ( (int)result < 0 )
      return result;
    v57 = qword_18025EC18;
  }
  if ( !a3 )
    return 4294966293LL;
  sub_180001440(8740);
  sub_1801AC1AC(a3, &v54, &v49);
  v8 = v49;
  if ( v49 )
  {
    Src = v54;
  }
  else
  {
    result = sub_1801ADB7C(a3, v61, v7, &v49, 0);
    if ( (int)result < 0 )
      return result;
    v8 = v49;
    Src = v61;
  }
  sub_1801AC0A8(a3, L"DATABASE=", &v56, &v52);
  v54 = (char *)sub_1801AD7F8(0, v9, v10);
  v12 = v54;
  v13 = (unsigned int)(v11 + 1);
  if ( !v54 )
  {
    v53 = v11 + 1;
    result = sub_18011B15C(qword_18025EC18, 0x1A0u, 0, (void **)&v54);
    if ( (int)result < 0 )
      return result;
    v12 = v54;
  }
  sub_1801AD548(v12);
  v14 = (_OWORD *)sub_1801B278C(v59);
  v15 = 8;
  v16 = Str;
  do
  {
    *(_OWORD *)v16 = *v14;
    *((_OWORD *)v16 + 1) = v14[1];
    *((_OWORD *)v16 + 2) = v14[2];
    *((_OWORD *)v16 + 3) = v14[3];
    *((_OWORD *)v16 + 4) = v14[4];
    *((_OWORD *)v16 + 5) = v14[5];
    *((_OWORD *)v16 + 6) = v14[6];
    v16 += 64;
    v17 = v14[7];
    v14 += 8;
    *((_OWORD *)v16 - 1) = v17;
    v15 -= v13;
  }
  while ( v15 );
  *(_DWORD *)v16 = *(_DWORD *)v14;
  if ( (unsigned __int8)sub_1801B28E8(Str)
    || (v18 = (unsigned int)Mso30Win32Client_55665(Str, L"sqlsrv32.dll", (unsigned int)v13) == 0, v19 = 0, !v18) )
  {
    v19 = v13;
  }
  v12[401] = v19;
  v12[400] = sub_1801B28E8(Str);
  v20 = -1;
  *((_QWORD *)v12 + 4) = sub_1801AF3C8(a1);
  v21 = -1;
  do
    ++v21;
  while ( a3[v21] );
  v22 = *((_QWORD *)v12 + 48);
  v23 = 2 * v21 + 2;
  if ( v22 )
  {
    v24 = -1;
    do
      ++v24;
    while ( a3[v24] );
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(v22 + 2 * v25) );
    if ( (unsigned int)v24 <= (unsigned int)v25 )
      goto LABEL_64;
  }
  result = sub_18011B19C(qword_18025EC18, v23, 0, (_QWORD *)v12 + 48);
  if ( (int)result >= 0 )
  {
LABEL_64:
    v26 = v23 >> 1;
    if ( v26 )
      wcsncpy_s(*((wchar_t **)v12 + 48), v26, a3, 0xFFFFFFFFFFFFFFFFuLL);
    v27 = (void **)(v12 + 368);
    v28 = *((_QWORD *)v12 + 46);
    if ( v28 )
    {
      v29 = -1;
      do
        ++v29;
      while ( *(_WORD *)(v28 + 2 * v29) );
      if ( v8 <= (unsigned int)v29 )
        goto LABEL_34;
    }
    result = sub_18011B19C(qword_18025EC18, 2 * v8 + 2, 0, (_QWORD *)v12 + 46);
    if ( (int)result >= 0 )
    {
LABEL_34:
      memcpy(*v27, Src, 2LL * v8);
      *((_WORD *)*v27 + v8) = 0;
      v30 = v52;
      if ( v52 )
      {
        v31 = (void **)(v12 + 376);
        v32 = *((_QWORD *)v12 + 47);
        if ( !v32 )
          goto LABEL_65;
        do
          ++v20;
        while ( *(_WORD *)(v32 + 2 * v20) );
        if ( v52 > (unsigned int)v20 )
        {
LABEL_65:
          result = sub_18011B19C(qword_18025EC18, 2 * v52 + 2, 0, (_QWORD *)v12 + 47);
          if ( (int)result < 0 )
            return result;
        }
        v33 = 2 * v30;
        memcpy(*v31, v56, v33);
        *(_WORD *)((char *)*v31 + v33) = 0;
      }
      v34 = hdbc;
      v35 = (__int16 *)(v12 + 18);
      result = sub_1801533D8(a1, (_DWORD)hdbc, (unsigned int)&v48, (int)v12 + 16, (__int64)(v12 + 18));
      if ( (int)result >= 0 )
      {
        LOWORD(v46) = 2;
        result = sub_1801B2D5C(a1, v34, 1, v47, v46, &v50);
        if ( (int)result >= 0 )
        {
          v36 = v47[0];
          if ( !v47[0] )
          {
            v36 = 10000;
            v47[0] = 10000;
          }
          if ( v36 > 1 && v48 >= 1 )
          {
            v37 = *((_WORD *)v12 + 8);
            if ( v37 >= *v35 )
              v37 = *v35;
            if ( v37 == 1 )
            {
              v36 = 1;
              v47[0] = 1;
            }
          }
          *((_DWORD *)v12 + 1) = *((_DWORD *)v12 + 1) & 0xFFFFFFFE | (v36 > 1);
          *((_QWORD *)v12 + 3) = v34;
          TickCount = GetTickCount();
          v39 = v51;
          *((_DWORD *)v12 + 5) = TickCount;
          *(_WORD *)v12 = 1;
          if ( (v39 & 1) != 0 )
          {
            v40 = *((_DWORD *)v12 + 1);
            if ( (v40 & 1) == 0 )
            {
              v41 = v40 | 2;
              *((_DWORD *)v12 + 1) = v41;
              if ( (v39 & 2) != 0 )
                *((_DWORD *)v12 + 1) = v41 | 4;
            }
          }
          if ( (v12[4] & 1) == 0 )
          {
            v42 = SQLSetConnectOptionW(v34, 0x65u, v39 & 1);
            if ( (int)sub_1801AF554(v42, v34, 0, a1) < 0 )
              sub_180045AD0(a1);
          }
          v43 = sub_1801AD82C(a1, v12);
          if ( v43 >= 0 )
          {
            if ( v53 )
            {
              v45 = v57;
              *((_QWORD *)v12 + 51) = v57[5];
              v45[5] = v12;
            }
            sub_1801ADAC8(a1, v12);
            return 0;
          }
          else
          {
            v44 = *((_QWORD *)v12 + 3);
            sub_1801AD548(v12);
            *((_QWORD *)v12 + 3) = 0;
            sub_1801AD37C(a1, v12);
            result = (unsigned int)v43;
            *((_QWORD *)v12 + 3) = v44;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801adeb4  push    rbp
0x1801adeb6  push    rbx
0x1801adeb7  push    rsi
0x1801adeb8  push    rdi
0x1801adeb9  push    r12
0x1801adebb  push    r13
0x1801adebd  push    r14
0x1801adebf  push    r15
0x1801adec1  lea     rbp, [rsp-0BA8h]
0x1801adec9  sub     rsp, 0CA8h
0x1801aded0  mov     rax, cs:__security_cookie
0x1801aded7  xor     rax, rsp
0x1801adeda  mov     [rbp+0BE0h+var_50], rax
0x1801adee1  mov     rax, cs:qword_18025EC18
0x1801adee8  xor     r12d, r12d
0x1801adeeb  mov     [rsp+0CE0h+var_CA0], r9w
0x1801adef1  mov     rbx, r8
0x1801adef4  mov     [rsp+0CE0h+hdbc], rdx
0x1801adef9  mov     r14, rdx
0x1801adefc  mov     [rsp+0CE0h+var_CA8], r12d
0x1801adf01  mov     r15, rcx
0x1801adf04  mov     [rsp+0CE0h+var_C9C], r12d
0x1801adf09  mov     [rsp+0CE0h+var_C90], r12
0x1801adf0e  mov     [rsp+0CE0h+var_C80], r12
0x1801adf13  mov     [rsp+0CE0h+var_C98], r12d
0x1801adf18  mov     [rsp+0CE0h+var_CAC], r12w
0x1801adf1e  mov     [rsp+0CE0h+var_CB0], r12w
0x1801adf24  mov     [rsp+0CE0h+var_CA4], r12w
0x1801adf2a  mov     [rsp+0CE0h+var_C78], rax
0x1801adf2f  test    rax, rax
0x1801adf32  jnz     short loc_1801ADF4D
0x1801adf34  call    sub_1801AD300
0x1801adf39  test    eax, eax
0x1801adf3b  js      loc_1801AE3A3
0x1801adf41  mov     rax, cs:qword_18025EC18
0x1801adf48  mov     [rsp+0CE0h+var_C78], rax
0x1801adf4d  test    rbx, rbx
0x1801adf50  jnz     short loc_1801ADF5C
0x1801adf52  mov     eax, 0FFFFFC15h
0x1801adf57  jmp     loc_1801AE3A3
0x1801adf5c  mov     ecx, 2224h
0x1801adf61  call    sub_180001440
0x1801adf66  lea     r8, [rsp+0CE0h+var_CA8]
0x1801adf6b  mov     rcx, rbx
0x1801adf6e  lea     rdx, [rsp+0CE0h+var_C90]
0x1801adf73  call    sub_1801AC1AC
0x1801adf78  mov     r13d, [rsp+0CE0h+var_CA8]
0x1801adf7d  test    r13d, r13d
0x1801adf80  jnz     short loc_1801ADFB6
0x1801adf82  lea     r9, [rsp+0CE0h+var_CA8]
0x1801adf87  mov     dword ptr [rsp+0CE0h+var_CC0], r12d
0x1801adf8c  lea     rdx, [rbp+0BE0h+var_450]
0x1801adf93  mov     rcx, rbx
0x1801adf96  call    sub_1801ADB7C
0x1801adf9b  test    eax, eax
0x1801adf9d  js      loc_1801AE3A3
0x1801adfa3  mov     r13d, [rsp+0CE0h+var_CA8]
0x1801adfa8  lea     rsi, [rbp+0BE0h+var_450]
0x1801adfaf  mov     [rsp+0CE0h+Src], rsi
0x1801adfb4  jmp     short loc_1801ADFC0
0x1801adfb6  mov     rax, [rsp+0CE0h+var_C90]
0x1801adfbb  mov     [rsp+0CE0h+Src], rax
0x1801adfc0  lea     r9, [rsp+0CE0h+var_C9C]
0x1801adfc5  mov     rcx, rbx
0x1801adfc8  lea     r8, [rsp+0CE0h+var_C80]
0x1801adfcd  lea     rdx, aDatabase_0; "DATABASE="
0x1801adfd4  call    sub_1801AC0A8
0x1801adfd9  xor     ecx, ecx
0x1801adfdb  call    sub_1801AD7F8
0x1801adfe0  mov     [rsp+0CE0h+var_C90], rax
0x1801adfe5  mov     rdi, rax
0x1801adfe8  lea     esi, [rcx+1]
0x1801adfeb  test    rax, rax
0x1801adfee  jnz     short loc_1801AE01A
0x1801adff0  mov     rcx, cs:qword_18025EC18
0x1801adff7  lea     r9, [rsp+0CE0h+var_C90]
0x1801adffc  xor     r8d, r8d
0x1801adfff  mov     [rsp+0CE0h+var_C98], esi
0x1801ae003  mov     edx, 1A0h
0x1801ae008  call    sub_18011B15C
0x1801ae00d  test    eax, eax
0x1801ae00f  js      loc_1801AE3A3
0x1801ae015  mov     rdi, [rsp+0CE0h+var_C90]
0x1801ae01a  mov     rcx, rdi
0x1801ae01d  call    sub_1801AD548
0x1801ae022  mov     rdx, r15
0x1801ae025  lea     rcx, [rsp+0CE0h+var_C68]; void *
0x1801ae02a  mov     r8, r14
0x1801ae02d  call    sub_1801B278C
0x1801ae032  mov     edx, 8
0x1801ae037  lea     rcx, [rbp+0BE0h+Str]
0x1801ae03e  lea     r8d, [rdx+78h]
0x1801ae042  movups  xmm0, xmmword ptr [rax]
0x1801ae045  movups  xmmword ptr [rcx], xmm0
0x1801ae048  movups  xmm1, xmmword ptr [rax+10h]
0x1801ae04c  movups  xmmword ptr [rcx+10h], xmm1
0x1801ae050  movups  xmm0, xmmword ptr [rax+20h]
0x1801ae054  movups  xmmword ptr [rcx+20h], xmm0
0x1801ae058  movups  xmm1, xmmword ptr [rax+30h]
0x1801ae05c  movups  xmmword ptr [rcx+30h], xmm1
0x1801ae060  movups  xmm0, xmmword ptr [rax+40h]
0x1801ae064  movups  xmmword ptr [rcx+40h], xmm0
0x1801ae068  movups  xmm1, xmmword ptr [rax+50h]
0x1801ae06c  movups  xmmword ptr [rcx+50h], xmm1
0x1801ae070  movups  xmm0, xmmword ptr [rax+60h]
0x1801ae074  movups  xmmword ptr [rcx+60h], xmm0
0x1801ae078  add     rcx, r8
0x1801ae07b  movups  xmm1, xmmword ptr [rax+70h]
0x1801ae07f  add     rax, r8
0x1801ae082  movups  xmmword ptr [rcx-10h], xmm1
0x1801ae086  sub     rdx, rsi
0x1801ae089  jnz     short loc_1801AE042
0x1801ae08b  mov     eax, [rax]
0x1801ae08d  mov     [rcx], eax
0x1801ae08f  lea     rcx, [rbp+0BE0h+Str]; Str
0x1801ae096  mov     edx, [rbp+0BE0h+var_460]
0x1801ae09c  call    sub_1801B28E8
0x1801ae0a1  test    al, al
0x1801ae0a3  jnz     short loc_1801AE0C3
0x1801ae0a5  mov     r8d, esi
0x1801ae0a8  lea     rdx, aSqlsrv32Dll; "sqlsrv32.dll"
0x1801ae0af  lea     rcx, [rbp+0BE0h+Str]
0x1801ae0b6  call    cs:Mso30Win32Client_55665
0x1801ae0bc  test    eax, eax
0x1801ae0be  mov     al, r12b
0x1801ae0c1  jz      short loc_1801AE0C6
0x1801ae0c3  mov     al, sil
0x1801ae0c6  mov     [rdi+191h], al
0x1801ae0cc  lea     rcx, [rbp+0BE0h+Str]; Str
0x1801ae0d3  mov     edx, [rbp+0BE0h+var_460]
0x1801ae0d9  call    sub_1801B28E8
0x1801ae0de  mov     rcx, r15
0x1801ae0e1  mov     [rdi+190h], al
0x1801ae0e7  call    sub_1801AF3C8
0x1801ae0ec  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801ae0f0  mov     [rdi+20h], rax
0x1801ae0f4  mov     rax, r14
0x1801ae0f7  inc     rax
0x1801ae0fa  cmp     [rbx+rax*2], r12w
0x1801ae0ff  jnz     short loc_1801AE0F7
0x1801ae101  lea     r12, [rdi+180h]
0x1801ae108  xor     r8d, r8d
0x1801ae10b  mov     rdx, [r12]
0x1801ae10f  lea     esi, ds:2[rax*2]
0x1801ae116  test    rdx, rdx
0x1801ae119  jz      short loc_1801AE139
0x1801ae11b  mov     rcx, r14
0x1801ae11e  inc     rcx
0x1801ae121  cmp     [rbx+rcx*2], r8w
0x1801ae126  jnz     short loc_1801AE11E
0x1801ae128  mov     rax, r14
0x1801ae12b  inc     rax
0x1801ae12e  cmp     [rdx+rax*2], r8w
0x1801ae133  jnz     short loc_1801AE12B
0x1801ae135  cmp     ecx, eax
0x1801ae137  jbe     short loc_1801AE152
0x1801ae139  mov     rcx, cs:qword_18025EC18; lpAddress
0x1801ae140  mov     r9, r12
0x1801ae143  mov     edx, esi
0x1801ae145  call    sub_18011B19C
0x1801ae14a  test    eax, eax
0x1801ae14c  js      loc_1801AE3A3
0x1801ae152  shr     esi, 1
0x1801ae154  jz      short loc_1801AE168
0x1801ae156  mov     rcx, [r12]; Destination
0x1801ae15a  mov     r9, r14; MaxCount
0x1801ae15d  mov     edx, esi; SizeInWords
0x1801ae15f  mov     r8, rbx; Source
0x1801ae162  call    cs:wcsncpy_s
0x1801ae168  lea     rsi, [rdi+170h]
0x1801ae16f  xor     r12d, r12d
0x1801ae172  mov     rcx, [rsi]
0x1801ae175  test    rcx, rcx
0x1801ae178  jz      short loc_1801AE18C
0x1801ae17a  mov     rax, r14
0x1801ae17d  inc     rax
0x1801ae180  cmp     [rcx+rax*2], r12w
0x1801ae185  jnz     short loc_1801AE17D
0x1801ae187  cmp     r13d, eax
0x1801ae18a  jbe     short loc_1801AE1AE
0x1801ae18c  mov     rcx, cs:qword_18025EC18; lpAddress
0x1801ae193  lea     edx, ds:2[r13*2]
0x1801ae19b  mov     r9, rsi
0x1801ae19e  xor     r8d, r8d
0x1801ae1a1  call    sub_18011B19C
0x1801ae1a6  test    eax, eax
0x1801ae1a8  js      loc_1801AE3A3
0x1801ae1ae  mov     rdx, [rsp+0CE0h+Src]; Src
0x1801ae1b3  mov     rcx, [rsi]; void *
0x1801ae1b6  mov     eax, r13d
0x1801ae1b9  lea     rbx, [rax+rax]
0x1801ae1bd  mov     r8, rbx; Size
0x1801ae1c0  call    memcpy
0x1801ae1c5  mov     rax, [rsi]
0x1801ae1c8  mov     [rbx+rax], r12w
0x1801ae1cd  mov     ebx, [rsp+0CE0h+var_C9C]
0x1801ae1d1  test    ebx, ebx
0x1801ae1d3  jz      short loc_1801AE22F
0x1801ae1d5  lea     rsi, [rdi+178h]
0x1801ae1dc  mov     rax, [rsi]
0x1801ae1df  test    rax, rax
0x1801ae1e2  jz      short loc_1801AE1F3
0x1801ae1e4  inc     r14
0x1801ae1e7  cmp     [rax+r14*2], r12w
0x1801ae1ec  jnz     short loc_1801AE1E4
0x1801ae1ee  cmp     ebx, r14d
0x1801ae1f1  jbe     short loc_1801AE214
0x1801ae1f3  mov     rcx, cs:qword_18025EC18; lpAddress
0x1801ae1fa  lea     edx, ds:2[rbx*2]
0x1801ae201  mov     r9, rsi
0x1801ae204  xor     r8d, r8d
0x1801ae207  call    sub_18011B19C
0x1801ae20c  test    eax, eax
0x1801ae20e  js      loc_1801AE3A3
0x1801ae214  mov     rdx, [rsp+0CE0h+var_C80]; Src
0x1801ae219  add     rbx, rbx
0x1801ae21c  mov     rcx, [rsi]; void *
0x1801ae21f  mov     r8, rbx; Size
0x1801ae222  call    memcpy
0x1801ae227  mov     rax, [rsi]
0x1801ae22a  mov     [rbx+rax], r12w
0x1801ae22f  mov     r14, [rsp+0CE0h+hdbc]
0x1801ae234  lea     rbx, [rdi+12h]
0x1801ae238  mov     rdx, r14
0x1801ae23b  mov     [rsp+0CE0h+var_CC0], rbx
0x1801ae240  lea     r9, [rdi+10h]
0x1801ae244  mov     rcx, r15
0x1801ae247  lea     r8, [rsp+0CE0h+var_CAC]
0x1801ae24c  call    sub_1801533D8
0x1801ae251  test    eax, eax
0x1801ae253  js      loc_1801AE3A3
0x1801ae259  lea     rax, [rsp+0CE0h+var_CA4]
0x1801ae25e  mov     r13d, 1
0x1801ae264  mov     [rsp+0CE0h+var_CB8], rax
0x1801ae269  lea     r9, [rsp+0CE0h+var_CB0]
0x1801ae26e  mov     r8d, r13d
0x1801ae271  mov     word ptr [rsp+0CE0h+var_CC0], 2
0x1801ae278  mov     rdx, r14
0x1801ae27b  mov     rcx, r15
0x1801ae27e  call    sub_1801B2D5C
0x1801ae283  test    eax, eax
0x1801ae285  js      loc_1801AE3A3
0x1801ae28b  movzx   edx, [rsp+0CE0h+var_CB0]
0x1801ae290  test    dx, dx
0x1801ae293  jnz     short loc_1801AE29F
0x1801ae295  mov     edx, 2710h
0x1801ae29a  mov     [rsp+0CE0h+var_CB0], dx
0x1801ae29f  cmp     dx, r13w
0x1801ae2a3  jle     short loc_1801AE2C7
0x1801ae2a5  cmp     [rsp+0CE0h+var_CAC], r13w
0x1801ae2ab  jl      short loc_1801AE2C7
0x1801ae2ad  movzx   eax, word ptr [rdi+10h]
0x1801ae2b1  cmp     ax, [rbx]
0x1801ae2b4  cmovge  ax, [rbx]
0x1801ae2b8  cmp     ax, r13w
0x1801ae2bc  jnz     short loc_1801AE2C7
0x1801ae2be  movzx   edx, r13w
0x1801ae2c2  mov     [rsp+0CE0h+var_CB0], dx
0x1801ae2c7  mov     eax, [rdi+4]
0x1801ae2ca  mov     ecx, r12d
0x1801ae2cd  cmp     dx, r13w
0x1801ae2d1  setnle  cl
0x1801ae2d4  and     eax, 0FFFFFFFEh
0x1801ae2d7  or      ecx, eax
0x1801ae2d9  mov     [rdi+4], ecx
0x1801ae2dc  mov     [rdi+18h], r14
0x1801ae2e0  call    cs:GetTickCount
0x1801ae2e6  movsx   ecx, [rsp+0CE0h+var_CA0]
0x1801ae2eb  mov     [rdi+14h], eax
0x1801ae2ee  mov     [rdi], r13w
0x1801ae2f2  test    r13b, cl
0x1801ae2f5  jz      short loc_1801AE310
0x1801ae2f7  mov     eax, [rdi+4]
0x1801ae2fa  test    r13b, al
0x1801ae2fd  jnz     short loc_1801AE310
0x1801ae2ff  or      eax, 2
0x1801ae302  mov     [rdi+4], eax
0x1801ae305  test    cl, 2
0x1801ae308  jz      short loc_1801AE310
0x1801ae30a  or      eax, 4
0x1801ae30d  mov     [rdi+4], eax
0x1801ae310  test    [rdi+4], r13b
0x1801ae314  jnz     short loc_1801AE347
0x1801ae316  mov     r8d, ecx
0x1801ae319  mov     edx, 65h ; 'e'; fOption
0x1801ae31e  and     r8d, r13d; vParam
0x1801ae321  mov     rcx, r14; hdbc
0x1801ae324  call    cs:SQLSetConnectOptionW
0x1801ae32a  mov     r9, r15
0x1801ae32d  xor     r8d, r8d
0x1801ae330  movzx   ecx, ax
0x1801ae333  mov     rdx, r14
0x1801ae336  call    sub_1801AF554
0x1801ae33b  test    eax, eax
0x1801ae33d  jns     short loc_1801AE347
0x1801ae33f  mov     rcx, r15
0x1801ae342  call    sub_180045AD0
0x1801ae347  mov     rdx, rdi
0x1801ae34a  mov     rcx, r15
0x1801ae34d  call    sub_1801AD82C
  ... truncated ...
```
