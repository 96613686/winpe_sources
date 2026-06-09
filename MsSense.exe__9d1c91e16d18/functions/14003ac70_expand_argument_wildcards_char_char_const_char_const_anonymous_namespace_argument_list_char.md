# expand_argument_wildcards<char>(char * const,char * const,`anonymous namespace'::argument_list<char> &)

- ea: `0x14003ac70`
- end: `0x14003b1b4`
- name: `??$expand_argument_wildcards@D@@YAHQEAD0AEAV?$argument_list@D@?A0x5f5c8891@@@Z`
- size: `1348`
- prototype: `__int64 __fastcall(__int64, char, FILETIME, char, char, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14003ac70`
- `0x140040e28`

## callees

- `0x14000254c`
- `0x140003dec`
- `0x140016354`
- `0x140018140`
- `0x140018340`
- `0x140028ae8`
- `0x14002c240`
- `0x14003ab10`
- `0x14003ac70`
- `0x140051ba0`
- `0x140066a40`
- `0x14006c4a0`
- `0x1400802f0`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x14003ae7d`
- `KERNEL32!CompareFileTime` at `0x14003ae7d`
- `KERNEL32!FindClose` at `0x14003b177`
- `KERNEL32!FindClose` at `0x14003b177`
- `KERNEL32!FindFirstFileW` at `0x14003adb8`
- `KERNEL32!FindFirstFileW` at `0x14003adb8`
- `KERNEL32!FindNextFileW` at `0x14003afda`
- `KERNEL32!FindNextFileW` at `0x14003afda`
- `KERNEL32!GetLastError` at `0x14003b0e5`
- `KERNEL32!GetLastError` at `0x14003b0e5`

## string_xrefs

- `0x14003aed3`: `LastWriteTime is fresh. Skip deleting the file`

## pseudocode

```c
__int64 __fastcall expand_argument_wildcards<char>(__int64 a1, char a2, FILETIME a3, char a4, char a5, int a6)
{
  char v6; // r14
  _QWORD *v7; // rdi
  char v8; // r12
  __int64 v9; // r8
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rdx
  const WCHAR *v14; // rcx
  char *FirstFileW; // rbx
  unsigned int v16; // esi
  int v17; // edx
  int v18; // r9d
  DWORD dwLowDateTime; // r8d
  _DWORD *v20; // rcx
  WCHAR *v21; // rax
  int v22; // eax
  int v23; // r14d
  _DWORD *v24; // rcx
  WCHAR *v25; // rax
  _QWORD *v26; // rdi
  __int64 v27; // r14
  __int64 v28; // rax
  int v29; // r14d
  _DWORD *v30; // rcx
  signed int LastError; // r14d
  _DWORD *v32; // rcx
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39[2]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR ExistingFileName[8]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v41; // [rsp+88h] [rbp-78h]
  FILETIME FileTime2; // [rsp+98h] [rbp-68h] BYREF
  __int128 v43; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  LPCWSTR lpFileName[4]; // [rsp+C0h] [rbp-40h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF

  v6 = a2;
  v7 = (_QWORD *)a1;
  v37 = a1;
  FileTime2 = a3;
  if ( a3.dwLowDateTime != -1 || (v8 = 1, a3.dwHighDateTime != -1) )
    v8 = 0;
  v9 = *(_QWORD *)(a1 + 16);
  if ( !v9 )
    return 2147942487LL;
  v43 = 0;
  si128 = _mm_load_si128((const __m128i *)&xmmword_14008B6E0);
  LOWORD(v43) = 0;
  v11 = a1;
  if ( *(_QWORD *)(a1 + 24) > 7u )
    v11 = *(_QWORD *)a1;
  if ( *(_WORD *)(v11 + 2 * v9 - 2) == 92 )
  {
    if ( &v43 != (__int128 *)a1 )
    {
      v13 = a1;
      if ( *(_QWORD *)(a1 + 24) > 7u )
        v13 = *(_QWORD *)a1;
      sub_140028AE8(&v43, v13, v9);
    }
  }
  else
  {
    v12 = sub_14002C240(ExistingFileName, a1, "\\");
    if ( &v43 != (__int128 *)v12 )
    {
      sub_140018140(&v43);
      v43 = *(_OWORD *)v12;
      si128 = *(__m128i *)(v12 + 16);
      *(_QWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 24) = 7;
      *(_WORD *)v12 = 0;
    }
    sub_140018140(ExistingFileName);
  }
  sub_14002C240(lpFileName, &v43, L"*");
  sub_1400802F0(&FindFileData, 0, 592);
  v14 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v14 = lpFileName[0];
  FirstFileW = (char *)FindFirstFileW(v14, &FindFileData);
  v39[1] = (__int64)FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v32 = *(_DWORD **)(sub_140018340(&stru_1400C1280, sub_140015AD0) + 8);
    if ( *v32 > 3u )
    {
      LODWORD(v35) = LastError;
      if ( v7[3] > 7u )
        v7 = (_QWORD *)*v7;
      v37 = (__int64)v7;
      v36 = (__int64)L"Failed deleting folder content";
      sub_14000254C((int)v32, (int)&qword_1400ADF80, 0, 0, (__int64)&v36, (__int64)&v37, (__int64)&v35);
    }
    v16 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v16 = LastError;
  }
  else
  {
    v16 = 0;
    do
    {
      sub_14002C240(ExistingFileName, &v43, FindFileData.cFileName);
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        if ( (unsigned int)sub_14006C4A0(FindFileData.cFileName, &qword_14008C8E0)
          && (unsigned int)sub_14006C4A0(FindFileData.cFileName, L"..")
          && a4 )
        {
          LOBYTE(v18) = 1;
          if ( v8 )
          {
            dwLowDateTime = -1;
            LOBYTE(v17) = 1;
          }
          else
          {
            dwLowDateTime = FileTime2.dwLowDateTime;
            LOBYTE(v17) = v6;
          }
          expand_argument_wildcards<char>((unsigned int)ExistingFileName, v17, dwLowDateTime, v18, a5, a6);
        }
      }
      else if ( v8 || CompareFileTime(&FindFileData.ftLastWriteTime, &FileTime2) != 1 )
      {
        v22 = sub_14003AB10(ExistingFileName);
        v23 = v22;
        if ( (v22 & 0xFFFFFFFC) != 0 || v22 == 1 )
        {
          v16 = (unsigned __int16)v22 | 0x80070000;
          if ( v22 <= 0 )
            v16 = v22;
          v24 = *(_DWORD **)(sub_140018340(&stru_1400C1280, sub_140015AD0) + 8);
          if ( *v24 > 3u )
          {
            LODWORD(v35) = v23;
            v25 = ExistingFileName;
            if ( *((_QWORD *)&v41 + 1) > 7u )
              v25 = *(WCHAR **)ExistingFileName;
            v36 = (__int64)v25;
            v38 = (__int64)L"Failed deleting file";
            sub_14000254C((int)v24, (int)&byte_1400AE00B, 0, 0, (__int64)&v38, (__int64)&v36, (__int64)&v35);
          }
        }
        v6 = a2;
      }
      else
      {
        v20 = *(_DWORD **)(sub_140018340(&stru_1400C1280, sub_140015AD0) + 8);
        if ( *v20 > 4u )
        {
          v35 = (__int64)FileTime2;
          v39[0] = (__int64)FindFileData.ftLastWriteTime;
          v21 = ExistingFileName;
          if ( *((_QWORD *)&v41 + 1) > 7u )
            v21 = *(WCHAR **)ExistingFileName;
          v38 = (__int64)v21;
          v36 = (__int64)L"LastWriteTime is fresh. Skip deleting the file";
          sub_140003DEC((int)v20, (int)&byte_1400ADFBB, 0, 0, (__int64)&v36, (__int64)&v38, (__int64)v39, (__int64)&v35);
        }
      }
      sub_140018140(ExistingFileName);
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    v26 = (_QWORD *)v37;
    if ( v6 )
    {
      v27 = v37;
      if ( *(_QWORD *)(v37 + 24) > 7u )
        v27 = *(_QWORD *)v37;
      *(_OWORD *)ExistingFileName = 0;
      v41 = 0;
      v28 = sub_140066A40(v27);
      sub_140016354(ExistingFileName, v27, v28);
      v29 = sub_14003AB10(ExistingFileName);
      sub_140018140(ExistingFileName);
      if ( (v29 & 0xFFFFFFFC) != 0 || v29 == 1 )
      {
        v16 = (unsigned __int16)v29 | 0x80070000;
        if ( v29 <= 0 )
          v16 = v29;
        v30 = *(_DWORD **)(sub_140018340(&stru_1400C1280, sub_140015AD0) + 8);
        if ( *v30 > 3u )
        {
          LODWORD(v35) = v29;
          if ( v26[3] > 7u )
            v26 = (_QWORD *)*v26;
          v37 = (__int64)v26;
          v36 = (__int64)L"Failed deleting folder";
          sub_14000254C((int)v30, (int)&byte_1400AE047, 0, 0, (__int64)&v36, (__int64)&v37, (__int64)&v35);
        }
      }
    }
  }
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  sub_140018140(lpFileName);
  sub_140018140(&v43);
  return v16;
}

```

## disassembly

```asm
0x14003ac70  push    rbp
0x14003ac72  push    rbx
0x14003ac73  push    rsi
0x14003ac74  push    rdi
0x14003ac75  push    r12
0x14003ac77  push    r13
0x14003ac79  push    r14
0x14003ac7b  lea     rbp, [rsp-240h]
0x14003ac83  sub     rsp, 340h
0x14003ac8a  mov     rax, cs:__security_cookie
0x14003ac91  xor     rax, rsp
0x14003ac94  mov     [rbp+270h+var_40], rax
0x14003ac9b  mov     [rsp+370h+var_32F], r9b
0x14003aca0  mov     r14b, dl
0x14003aca3  mov     [rsp+370h+var_330], dl
0x14003aca7  mov     rdi, rcx
0x14003acaa  mov     [rsp+370h+var_318], rcx
0x14003acaf  mov     qword ptr [rbp+270h+FileTime2.dwLowDateTime], r8
0x14003acb3  xor     r13d, r13d
0x14003acb6  or      eax, 0FFFFFFFFh
0x14003acb9  cmp     r8d, eax
0x14003acbc  jnz     short loc_14003ACCA
0x14003acbe  shr     r8, 20h
0x14003acc2  cmp     r8d, eax
0x14003acc5  mov     r12b, 1
0x14003acc8  jz      short loc_14003ACCD
0x14003acca  mov     r12b, r13b
0x14003accd  mov     r8, [rcx+10h]
0x14003acd1  test    r8, r8
0x14003acd4  jnz     short loc_14003ACE0
0x14003acd6  mov     eax, 80070057h
0x14003acdb  jmp     loc_14003B193
0x14003ace0  xorps   xmm0, xmm0
0x14003ace3  movups  [rbp+270h+var_2D0], xmm0
0x14003ace7  movdqa  xmm1, cs:xmmword_14008B6E0
0x14003acef  movdqu  [rbp+270h+var_2C0], xmm1
0x14003acf4  mov     word ptr [rbp+270h+var_2D0], r13w
0x14003acf9  mov     rax, rdi
0x14003acfc  mov     esi, 7
0x14003ad01  cmp     [rcx+18h], rsi
0x14003ad05  jbe     short loc_14003AD0A
0x14003ad07  mov     rax, [rcx]
0x14003ad0a  cmp     word ptr [rax+r8*2-2], 5Ch ; '\'
0x14003ad11  jz      short loc_14003AD63
0x14003ad13  lea     r8, SubBlock
0x14003ad1a  mov     rdx, rdi
0x14003ad1d  lea     rcx, [rsp+370h+ExistingFileName]
0x14003ad22  call    sub_14002C240
0x14003ad27  mov     rbx, rax
0x14003ad2a  lea     rax, [rbp+270h+var_2D0]
0x14003ad2e  cmp     rax, rbx
0x14003ad31  jz      short loc_14003AD57
0x14003ad33  lea     rcx, [rbp+270h+var_2D0]
0x14003ad37  call    sub_140018140
0x14003ad3c  movups  xmm0, xmmword ptr [rbx]
0x14003ad3f  movups  [rbp+270h+var_2D0], xmm0
0x14003ad43  movups  xmm1, xmmword ptr [rbx+10h]
0x14003ad47  movups  [rbp+270h+var_2C0], xmm1
0x14003ad4b  mov     [rbx+10h], r13
0x14003ad4f  mov     [rbx+18h], rsi
0x14003ad53  mov     [rbx], r13w
0x14003ad57  lea     rcx, [rsp+370h+ExistingFileName]
0x14003ad5c  call    sub_140018140
0x14003ad61  jmp     short loc_14003AD81
0x14003ad63  lea     rax, [rbp+270h+var_2D0]
0x14003ad67  cmp     rax, rdi
0x14003ad6a  jz      short loc_14003AD81
0x14003ad6c  mov     rdx, rdi
0x14003ad6f  cmp     [rcx+18h], rsi
0x14003ad73  jbe     short loc_14003AD78
0x14003ad75  mov     rdx, [rcx]
0x14003ad78  lea     rcx, [rbp+270h+var_2D0]
0x14003ad7c  call    sub_140028AE8
0x14003ad81  lea     r8, asc_1400906B8
0x14003ad88  lea     rdx, [rbp+270h+var_2D0]
0x14003ad8c  lea     rcx, [rbp+270h+lpFileName]
0x14003ad90  call    sub_14002C240
0x14003ad95  nop
0x14003ad96  xor     edx, edx
0x14003ad98  mov     r8d, 250h
0x14003ad9e  lea     rcx, [rbp+270h+FindFileData]
0x14003ada2  call    sub_1400802F0
0x14003ada7  lea     rcx, [rbp+270h+lpFileName]
0x14003adab  cmp     [rbp+270h+var_298], rsi
0x14003adaf  cmova   rcx, [rbp+270h+lpFileName]; lpFileName
0x14003adb4  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x14003adb8  call    cs:FindFirstFileW
0x14003adbe  mov     rbx, rax
0x14003adc1  mov     [rsp+370h+var_300], rax
0x14003adc6  dec     rax
0x14003adc9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003adcd  ja      loc_14003B0E5
0x14003add3  mov     esi, r13d
0x14003add6  mov     r13d, [rbp+270h+arg_28]
0x14003addd  mov     dil, [rbp+270h+arg_20]
0x14003ade4  lea     r8, [rbp+270h+FindFileData.cFileName]
0x14003ade8  lea     rdx, [rbp+270h+var_2D0]
0x14003adec  lea     rcx, [rsp+370h+ExistingFileName]
0x14003adf1  call    sub_14002C240
0x14003adf6  nop
0x14003adf7  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x14003adfb  jz      short loc_14003AE6C
0x14003adfd  lea     rdx, qword_14008C8E0
0x14003ae04  lea     rcx, [rbp+270h+FindFileData.cFileName]
0x14003ae08  call    sub_14006C4A0
0x14003ae0d  test    eax, eax
0x14003ae0f  jz      loc_14003AFC9
0x14003ae15  lea     rdx, asc_140090738
0x14003ae1c  lea     rcx, [rbp+270h+FindFileData.cFileName]
0x14003ae20  call    sub_14006C4A0
0x14003ae25  test    eax, eax
0x14003ae27  jz      loc_14003AFC9
0x14003ae2d  cmp     [rsp+370h+var_32F], 0
0x14003ae32  jz      loc_14003AFC9
0x14003ae38  mov     dword ptr [rsp+370h+var_348], r13d
0x14003ae3d  mov     r9b, 1
0x14003ae40  lea     rcx, [rsp+370h+ExistingFileName]
0x14003ae45  mov     byte ptr [rsp+370h+var_350], dil
0x14003ae4a  test    r12b, r12b
0x14003ae4d  jz      short loc_14003AE5B
0x14003ae4f  mov     r8, cs:qword_1400906C0
0x14003ae56  mov     dl, r9b
0x14003ae59  jmp     short loc_14003AE62
0x14003ae5b  mov     r8, qword ptr [rbp+270h+FileTime2.dwLowDateTime]
0x14003ae5f  mov     dl, r14b
0x14003ae62  call    ??$expand_argument_wildcards@D@@YAHQEAD0AEAV?$argument_list@D@?A0x5f5c8891@@@Z
0x14003ae67  jmp     loc_14003AFC9
0x14003ae6c  test    r12b, r12b
0x14003ae6f  jnz     loc_14003AF1E
0x14003ae75  lea     rdx, [rbp+270h+FileTime2]; lpFileTime2
0x14003ae79  lea     rcx, [rbp+270h+FindFileData.ftLastWriteTime]; lpFileTime1
0x14003ae7d  call    cs:CompareFileTime
0x14003ae83  cmp     eax, 1
0x14003ae86  jnz     loc_14003AF1E
0x14003ae8c  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003ae93  lea     rcx, stru_1400C1280; lpInitOnce
0x14003ae9a  call    sub_140018340
0x14003ae9f  mov     rcx, [rax+8]; int
0x14003aea3  cmp     dword ptr [rcx], 4
0x14003aea6  jbe     loc_14003AFC9
0x14003aeac  mov     rax, qword ptr [rbp+270h+FileTime2.dwLowDateTime]
0x14003aeb0  mov     [rsp+370h+var_328], rax
0x14003aeb5  mov     rax, qword ptr [rbp+270h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x14003aeb9  mov     [rsp+370h+var_308], rax
0x14003aebe  lea     rax, [rsp+370h+ExistingFileName]
0x14003aec3  cmp     [rbp+270h+var_2E0], 7
0x14003aec8  cmova   rax, qword ptr [rsp+370h+ExistingFileName]
0x14003aece  mov     [rsp+370h+var_310], rax
0x14003aed3  lea     rax, aLastwritetimeI
0x14003aeda  mov     [rsp+370h+var_320], rax
0x14003aedf  lea     rax, [rsp+370h+var_328]
0x14003aee4  mov     [rsp+370h+var_338], rax; __int64
0x14003aee9  lea     rax, [rsp+370h+var_308]
0x14003aeee  mov     [rsp+370h+var_340], rax; __int64
0x14003aef3  lea     rax, [rsp+370h+var_310]
0x14003aef8  mov     [rsp+370h+var_348], rax; __int64
0x14003aefd  lea     rax, [rsp+370h+var_320]
0x14003af02  mov     [rsp+370h+var_350], rax; __int64
0x14003af07  xor     r9d, r9d; int
0x14003af0a  xor     r8d, r8d; int
0x14003af0d  lea     rdx, byte_1400ADFBB; int
0x14003af14  call    sub_140003DEC
0x14003af19  jmp     loc_14003AFC9
0x14003af1e  mov     r8b, dil
0x14003af21  mov     edx, r13d
0x14003af24  lea     rcx, [rsp+370h+ExistingFileName]; lpExistingFileName
0x14003af29  call    sub_14003AB10
0x14003af2e  mov     r14d, eax
0x14003af31  test    eax, 0FFFFFFFCh
0x14003af36  jnz     short loc_14003AF41
0x14003af38  cmp     eax, 1
0x14003af3b  jnz     loc_14003AFC4
0x14003af41  movzx   esi, r14w
0x14003af45  or      esi, 80070000h
0x14003af4b  test    r14d, r14d
0x14003af4e  cmovle  esi, r14d
0x14003af52  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003af59  lea     rcx, stru_1400C1280; lpInitOnce
0x14003af60  call    sub_140018340
0x14003af65  mov     rcx, [rax+8]; int
0x14003af69  cmp     dword ptr [rcx], 3
0x14003af6c  jbe     short loc_14003AFC4
0x14003af6e  mov     dword ptr [rsp+370h+var_328], r14d
0x14003af73  lea     rax, [rsp+370h+ExistingFileName]
0x14003af78  cmp     [rbp+270h+var_2E0], 7
0x14003af7d  cmova   rax, qword ptr [rsp+370h+ExistingFileName]
0x14003af83  mov     [rsp+370h+var_320], rax
0x14003af88  lea     rax, aFailedDeleting
0x14003af8f  mov     [rsp+370h+var_310], rax
0x14003af94  lea     rax, [rsp+370h+var_328]
0x14003af99  mov     [rsp+370h+var_340], rax; __int64
0x14003af9e  lea     rax, [rsp+370h+var_320]
0x14003afa3  mov     [rsp+370h+var_348], rax; __int64
0x14003afa8  lea     rax, [rsp+370h+var_310]
0x14003afad  mov     [rsp+370h+var_350], rax; __int64
0x14003afb2  xor     r9d, r9d; int
0x14003afb5  xor     r8d, r8d; int
0x14003afb8  lea     rdx, byte_1400AE00B; int
0x14003afbf  call    sub_14000254C
0x14003afc4  mov     r14b, [rsp+370h+var_330]
0x14003afc9  lea     rcx, [rsp+370h+ExistingFileName]
0x14003afce  call    sub_140018140
0x14003afd3  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x14003afd7  mov     rcx, rbx; hFindFile
0x14003afda  call    cs:FindNextFileW
0x14003afe0  test    eax, eax
0x14003afe2  jnz     loc_14003ADE4
0x14003afe8  test    r14b, r14b
0x14003afeb  mov     rdi, [rsp+370h+var_318]
0x14003aff0  jz      loc_14003B16A
0x14003aff6  mov     r14, rdi
0x14003aff9  cmp     qword ptr [rdi+18h], 7
0x14003affe  jbe     short loc_14003B003
0x14003b000  mov     r14, [rdi]
0x14003b003  xorps   xmm0, xmm0
0x14003b006  movups  xmmword ptr [rsp+370h+ExistingFileName], xmm0
0x14003b00b  xorps   xmm1, xmm1
0x14003b00e  movdqu  xmmword ptr [rbp-78h], xmm1
0x14003b013  mov     rcx, r14
0x14003b016  call    sub_140066A40
0x14003b01b  mov     r8, rax
0x14003b01e  mov     rdx, r14
0x14003b021  lea     rcx, [rsp+370h+ExistingFileName]
0x14003b026  call    sub_140016354
0x14003b02b  mov     r8b, [rbp+270h+arg_20]
0x14003b032  mov     edx, r13d
0x14003b035  lea     rcx, [rsp+370h+ExistingFileName]; lpExistingFileName
0x14003b03a  call    sub_14003AB10
0x14003b03f  mov     r14d, eax
0x14003b042  lea     rcx, [rsp+370h+ExistingFileName]
0x14003b047  call    sub_140018140
0x14003b04c  test    r14d, 0FFFFFFFCh
0x14003b053  jnz     short loc_14003B05F
0x14003b055  cmp     r14d, 1
0x14003b059  jnz     loc_14003B16A
0x14003b05f  movzx   esi, r14w
0x14003b063  or      esi, 80070000h
0x14003b069  test    r14d, r14d
0x14003b06c  cmovle  esi, r14d
0x14003b070  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003b077  lea     rcx, stru_1400C1280; lpInitOnce
0x14003b07e  call    sub_140018340
0x14003b083  mov     rcx, [rax+8]; int
0x14003b087  cmp     dword ptr [rcx], 3
0x14003b08a  jbe     loc_14003B16A
0x14003b090  mov     dword ptr [rsp+370h+var_328], r14d
0x14003b095  cmp     qword ptr [rdi+18h], 7
0x14003b09a  jbe     short loc_14003B09F
0x14003b09c  mov     rdi, [rdi]
0x14003b09f  mov     [rsp+370h+var_318], rdi
0x14003b0a4  lea     rax, aFailedDeleting_0
0x14003b0ab  mov     [rsp+370h+var_320], rax
0x14003b0b0  lea     rax, [rsp+370h+var_328]
0x14003b0b5  mov     [rsp+370h+var_340], rax; __int64
0x14003b0ba  lea     rax, [rsp+370h+var_318]
0x14003b0bf  mov     [rsp+370h+var_348], rax; __int64
0x14003b0c4  lea     rax, [rsp+370h+var_320]
0x14003b0c9  mov     [rsp+370h+var_350], rax; __int64
0x14003b0ce  xor     r9d, r9d; int
0x14003b0d1  xor     r8d, r8d; int
0x14003b0d4  lea     rdx, byte_1400AE047; int
0x14003b0db  call    sub_14000254C
0x14003b0e0  jmp     loc_14003B16A
0x14003b0e5  call    cs:GetLastError
0x14003b0eb  mov     r14d, eax
0x14003b0ee  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003b0f5  lea     rcx, stru_1400C1280; lpInitOnce
0x14003b0fc  call    sub_140018340
0x14003b101  mov     rcx, [rax+8]; int
0x14003b105  cmp     dword ptr [rcx], 3
0x14003b108  jbe     short loc_14003B159
0x14003b10a  mov     dword ptr [rsp+370h+var_328], r14d
0x14003b10f  cmp     [rdi+18h], rsi
0x14003b113  jbe     short loc_14003B118
0x14003b115  mov     rdi, [rdi]
0x14003b118  mov     [rsp+370h+var_318], rdi
0x14003b11d  lea     rax, aFailedDeleting_1
0x14003b124  mov     [rsp+370h+var_320], rax
0x14003b129  lea     rax, [rsp+370h+var_328]
0x14003b12e  mov     [rsp+370h+var_340], rax; __int64
0x14003b133  lea     rax, [rsp+370h+var_318]
0x14003b138  mov     [rsp+370h+var_348], rax; __int64
0x14003b13d  lea     rax, [rsp+370h+var_320]
0x14003b142  mov     [rsp+370h+var_350], rax; __int64
0x14003b147  xor     r9d, r9d; int
0x14003b14a  xor     r8d, r8d; int
0x14003b14d  lea     rdx, qword_1400ADF80; int
0x14003b154  call    sub_14000254C
0x14003b159  movzx   esi, r14w
0x14003b15d  or      esi, 80070000h
0x14003b163  test    r14d, r14d
0x14003b166  cmovle  esi, r14d
0x14003b16a  lea     rcx, [rbx-1]
0x14003b16e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14003b172  ja      short loc_14003B17E
0x14003b174  mov     rcx, rbx; hFindFile
0x14003b177  call    cs:FindClose
0x14003b17d  nop
0x14003b17e  lea     rcx, [rbp+270h+lpFileName]
0x14003b182  call    sub_140018140
  ... truncated ...
```
