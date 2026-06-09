# GenerateUniqueFileNameWithPrefix

- ea: `0x1800309c4`
- end: `0x180030d76`
- name: `GenerateUniqueFileNameWithPrefix`
- size: `946`
- prototype: `unsigned __int64 __fastcall(__int64, const wchar_t *, __int64, const char *, unsigned __int16 *lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180036f80`

## callees

- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x180021530`
- `0x1800308e0`
- `0x1800309c4`
- `0x180031b1c`
- `0x18003d510`

## import_xrefs

- `msvcrt!_wcsnset` at `0x180030ae7`
- `msvcrt!_wcsnset` at `0x180030ae7`
- `msvcrt!wcsrchr` at `0x180030ac7`
- `msvcrt!wcsrchr` at `0x180030ac7`
- `KERNEL32!GetTempPath2W` at `0x180030a59`
- `KERNEL32!GetTempPath2W` at `0x180030a59`
- `KERNEL32!SystemTimeToFileTime` at `0x180030b32`
- `KERNEL32!SystemTimeToFileTime` at `0x180030b32`
- `KERNEL32!GetSystemTime` at `0x180030b1c`
- `KERNEL32!GetSystemTime` at `0x180030b1c`
- `KERNEL32!CloseHandle` at `0x180030cf0`
- `KERNEL32!CloseHandle` at `0x180030cf0`
- `KERNEL32!SetLastError` at `0x180030d3c`
- `KERNEL32!SetLastError` at `0x180030d3c`
- `KERNEL32!GetLastError` at `0x180030a8d`
- `KERNEL32!GetLastError` at `0x180030bc4`
- `KERNEL32!GetLastError` at `0x180030c20`
- `KERNEL32!GetLastError` at `0x180030c7b`
- `KERNEL32!GetLastError` at `0x180030a8d`
- `KERNEL32!GetLastError` at `0x180030bc4`
- `KERNEL32!GetLastError` at `0x180030c20`
- `KERNEL32!GetLastError` at `0x180030c7b`

## pseudocode

```c
unsigned __int64 __fastcall GenerateUniqueFileNameWithPrefix(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        const char *a4,
        unsigned __int16 *lpFileName)
{
  DWORD LastError; // eax
  wchar_t *v8; // rax
  const char *v9; // r12
  int v10; // edi
  unsigned __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // r9
  unsigned __int16 v14; // si
  void *File; // rax
  DWORD v16; // eax
  int v17; // r8d
  DWORD v18; // eax
  char v19; // al
  DWORD v20; // ecx
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[1040]; // [rsp+80h] [rbp-80h] BYREF

  memset(v24, 0, sizeof(v24));
  v25 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  if ( !a2 )
  {
    if ( !(unsigned int)GetTempPath2W(520, v26) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
      }
      return 0;
    }
    a2 = (const wchar_t *)v26;
  }
  v8 = wcsrchr(a2, 0x5Cu);
  if ( v8 && !v8[1] )
    _wcsnset(v8, 0, 1u);
  v9 = L"tif";
  v10 = 0;
  if ( a4 )
    v9 = a4;
  v11 = 0;
  while ( 1 )
  {
    FileTime = 0;
    SystemTime = 0;
    if ( !v10 )
    {
      GetSystemTime(&SystemTime);
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v18);
        }
        return 0;
      }
      v11 = *(unsigned __int64 *)&FileTime >> 8;
    }
    v12 = StringCchPrintfW(lpFileName, 0x104u, L"%s\\%s%s%I64X.%s", a2, &qword_1800435E8, v24, v11, v9);
    v14 = v12;
    if ( v12 < 0 )
      break;
    File = (void *)InternalSafeCreateFile(lpFileName, 0x40000000u, 0, v13, 1u, 128);
    if ( File != (void *)-1LL )
    {
      CloseHandle(File);
      return v11;
    }
    v16 = GetLastError();
    if ( v16 != 183 && v16 != 80 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
          (_DWORD)lpFileName,
          v19);
      }
      return 0;
    }
    ++v11;
    if ( (unsigned int)++v10 >= 0x100 )
    {
      if ( v10 == 256 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_diS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)&WPP_GLOBAL_Control,
            v17,
            256,
            v11,
            (__int64)lpFileName);
        }
        v20 = 4;
        goto LABEL_48;
      }
      return v11;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
      (unsigned __int16)v12);
  }
  v20 = v14;
LABEL_48:
  SetLastError(v20);
  return 0;
}

```

## disassembly

```asm
0x1800309c4  mov     [rsp-8+arg_0], rbx
0x1800309c9  mov     [rsp-8+arg_10], rsi
0x1800309ce  push    rbp
0x1800309cf  push    rdi
0x1800309d0  push    r12
0x1800309d2  push    r14
0x1800309d4  push    r15
0x1800309d6  lea     rbp, [rsp-3A0h]
0x1800309de  sub     rsp, 4A0h
0x1800309e5  mov     rax, cs:__security_cookie
0x1800309ec  xor     rax, rsp
0x1800309ef  mov     [rbp+3C0h+var_30], rax
0x1800309f6  mov     r15, [rbp+3C0h+lpFileName]
0x1800309fd  xorps   xmm0, xmm0
0x180030a00  xor     eax, eax
0x180030a02  mov     rbx, r9
0x180030a05  movups  [rsp+4C0h+var_468], xmm0
0x180030a0a  mov     [rsp+4C0h+var_448], rax
0x180030a0f  mov     r14, rdx
0x180030a12  movups  [rsp+4C0h+var_458], xmm0
0x180030a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a1e  lea     rdi, WPP_GLOBAL_Control
0x180030a25  cmp     rcx, rdi
0x180030a28  jz      short loc_180030A49
0x180030a2a  test    byte ptr [rcx+1Ch], 2
0x180030a2e  jz      short loc_180030A49
0x180030a30  cmp     byte ptr [rcx+19h], 5
0x180030a34  jb      short loc_180030A49
0x180030a36  mov     rcx, [rcx+10h]
0x180030a3a  lea     edx, [rax+11h]
0x180030a3d  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180030a44  call    WPP_SF_
0x180030a49  xor     esi, esi
0x180030a4b  test    r14, r14
0x180030a4e  jnz     short loc_180030ABF
0x180030a50  lea     rdx, [rbp+3C0h+var_440]
0x180030a54  mov     ecx, 208h
0x180030a59  call    cs:__imp_GetTempPath2W
0x180030a60  nop     dword ptr [rax+rax+00h]
0x180030a65  test    eax, eax
0x180030a67  jnz     short loc_180030ABB
0x180030a69  mov     rax, cs:WPP_GLOBAL_Control
0x180030a70  cmp     rax, rdi
0x180030a73  jz      loc_180030D48
0x180030a79  test    byte ptr [rax+1Ch], 2
0x180030a7d  jz      loc_180030D48
0x180030a83  cmp     byte ptr [rax+19h], 2
0x180030a87  jb      loc_180030D48
0x180030a8d  call    cs:__imp_GetLastError
0x180030a94  nop     dword ptr [rax+rax+00h]
0x180030a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180030aa0  lea     edx, [rsi+12h]
0x180030aa3  mov     r9d, eax
0x180030aa6  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180030aad  mov     rcx, [rcx+10h]
0x180030ab1  call    WPP_SF_d
0x180030ab6  jmp     loc_180030D48
0x180030abb  lea     r14, [rbp+3C0h+var_440]
0x180030abf  mov     edx, 5Ch ; '\'; Ch
0x180030ac4  mov     rcx, r14; Str
0x180030ac7  call    cs:__imp_wcsrchr
0x180030ace  nop     dword ptr [rax+rax+00h]
0x180030ad3  test    rax, rax
0x180030ad6  jz      short loc_180030AF3
0x180030ad8  cmp     [rax+2], si
0x180030adc  jnz     short loc_180030AF3
0x180030ade  xor     edx, edx; Value
0x180030ae0  mov     rcx, rax; String
0x180030ae3  lea     r8d, [rdx+1]; MaxCount
0x180030ae7  call    cs:__imp__wcsnset
0x180030aee  nop     dword ptr [rax+rax+00h]
0x180030af3  test    rbx, rbx
0x180030af6  lea     r12, aTif; "tif"
0x180030afd  mov     edi, esi
0x180030aff  cmovnz  r12, rbx
0x180030b03  mov     rbx, rsi
0x180030b06  mov     qword ptr [rsp+4C0h+FileTime.dwLowDateTime], rsi
0x180030b0b  xorps   xmm0, xmm0
0x180030b0e  movups  xmmword ptr [rsp+4C0h+SystemTime.wYear], xmm0
0x180030b13  test    edi, edi
0x180030b15  jnz     short loc_180030B59
0x180030b17  lea     rcx, [rsp+4C0h+SystemTime]; lpSystemTime
0x180030b1c  call    cs:__imp_GetSystemTime
0x180030b23  nop     dword ptr [rax+rax+00h]
0x180030b28  lea     rdx, [rsp+4C0h+FileTime]; lpFileTime
0x180030b2d  lea     rcx, [rsp+4C0h+SystemTime]; lpSystemTime
0x180030b32  call    cs:__imp_SystemTimeToFileTime
0x180030b39  nop     dword ptr [rax+rax+00h]
0x180030b3e  test    eax, eax
0x180030b40  jz      loc_180030BF5
0x180030b46  mov     ebx, [rsp+4C0h+FileTime.dwHighDateTime]
0x180030b4a  mov     eax, [rsp+4C0h+FileTime.dwLowDateTime]
0x180030b4e  shl     rbx, 20h
0x180030b52  or      rbx, rax
0x180030b55  shr     rbx, 8
0x180030b59  mov     [rsp+4C0h+var_488], r12
0x180030b5e  lea     rax, [rsp+4C0h+var_468]
0x180030b63  mov     [rsp+4C0h+var_490], rbx
0x180030b68  lea     r8, aSSSI64xS; "%s\\%s%s%I64X.%s"
0x180030b6f  mov     qword ptr [rsp+4C0h+var_498], rax
0x180030b74  mov     r9, r14
0x180030b77  lea     rax, qword_1800435E8
0x180030b7e  mov     edx, 104h; unsigned __int64
0x180030b83  mov     rcx, r15; unsigned __int16 *
0x180030b86  mov     qword ptr [rsp+4C0h+var_4A0], rax
0x180030b8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030b90  mov     esi, eax
0x180030b92  test    eax, eax
0x180030b94  js      loc_180030D01
0x180030b9a  mov     [rsp+4C0h+var_498], 80h; int
0x180030ba2  xor     r8d, r8d; dwShareMode
0x180030ba5  mov     edx, 40000000h; dwDesiredAccess
0x180030baa  mov     [rsp+4C0h+var_4A0], 1; DWORD
0x180030bb2  mov     rcx, r15; lpFileName
0x180030bb5  call    InternalSafeCreateFile
0x180030bba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030bbe  jnz     loc_180030CED
0x180030bc4  call    cs:__imp_GetLastError
0x180030bcb  nop     dword ptr [rax+rax+00h]
0x180030bd0  cmp     eax, 0B7h
0x180030bd5  jz      short loc_180030BDC
0x180030bd7  cmp     eax, 50h ; 'P'
0x180030bda  jnz     short loc_180030C50
0x180030bdc  inc     rbx
0x180030bdf  inc     edi
0x180030be1  mov     eax, 100h
0x180030be6  cmp     edi, eax
0x180030be8  jnb     loc_180030CAF
0x180030bee  xor     esi, esi
0x180030bf0  jmp     loc_180030B06
0x180030bf5  mov     rax, cs:WPP_GLOBAL_Control
0x180030bfc  lea     rdx, WPP_GLOBAL_Control
0x180030c03  cmp     rax, rdx
0x180030c06  jz      loc_180030D48
0x180030c0c  test    byte ptr [rax+1Ch], 2
0x180030c10  jz      loc_180030D48
0x180030c16  cmp     byte ptr [rax+19h], 2
0x180030c1a  jb      loc_180030D48
0x180030c20  call    cs:__imp_GetLastError
0x180030c27  nop     dword ptr [rax+rax+00h]
0x180030c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c33  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180030c3a  mov     edx, 14h
0x180030c3f  mov     r9d, eax
0x180030c42  mov     rcx, [rcx+10h]
0x180030c46  call    WPP_SF_d
0x180030c4b  jmp     loc_180030D48
0x180030c50  mov     rax, cs:WPP_GLOBAL_Control
0x180030c57  lea     rdx, WPP_GLOBAL_Control
0x180030c5e  cmp     rax, rdx
0x180030c61  jz      loc_180030D48
0x180030c67  test    byte ptr [rax+1Ch], 2
0x180030c6b  jz      loc_180030D48
0x180030c71  cmp     byte ptr [rax+19h], 2
0x180030c75  jb      loc_180030D48
0x180030c7b  call    cs:__imp_GetLastError
0x180030c82  nop     dword ptr [rax+rax+00h]
0x180030c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c8e  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180030c95  mov     edx, 16h
0x180030c9a  mov     [rsp+4C0h+var_4A0], eax
0x180030c9e  mov     r9, r15
0x180030ca1  mov     rcx, [rcx+10h]
0x180030ca5  call    WPP_SF_Sd
0x180030caa  jmp     loc_180030D48
0x180030caf  jnz     short loc_180030CFC
0x180030cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cb8  lea     rdx, WPP_GLOBAL_Control
0x180030cbf  cmp     rcx, rdx
0x180030cc2  jz      short loc_180030CE6
0x180030cc4  test    byte ptr [rcx+1Ch], 2
0x180030cc8  jz      short loc_180030CE6
0x180030cca  cmp     byte ptr [rcx+19h], 2
0x180030cce  jb      short loc_180030CE6
0x180030cd0  mov     rcx, [rcx+10h]
0x180030cd4  mov     r9d, eax
0x180030cd7  mov     qword ptr [rsp+4C0h+var_498], r15
0x180030cdc  mov     qword ptr [rsp+4C0h+var_4A0], rbx
0x180030ce1  call    WPP_SF_diS
0x180030ce6  mov     ecx, 4
0x180030ceb  jmp     short loc_180030D3C
0x180030ced  mov     rcx, rax; hObject
0x180030cf0  call    cs:__imp_CloseHandle
0x180030cf7  nop     dword ptr [rax+rax+00h]
0x180030cfc  mov     rax, rbx
0x180030cff  jmp     short loc_180030D4A
0x180030d01  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d08  lea     rdx, WPP_GLOBAL_Control
0x180030d0f  cmp     rcx, rdx
0x180030d12  jz      short loc_180030D39
0x180030d14  test    byte ptr [rcx+1Ch], 2
0x180030d18  jz      short loc_180030D39
0x180030d1a  cmp     byte ptr [rcx+19h], 2
0x180030d1e  jb      short loc_180030D39
0x180030d20  mov     rcx, [rcx+10h]
0x180030d24  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x180030d2b  movzx   r9d, si
0x180030d2f  mov     edx, 15h
0x180030d34  call    WPP_SF_d
0x180030d39  movzx   ecx, si; dwErrCode
0x180030d3c  call    cs:__imp_SetLastError
0x180030d43  nop     dword ptr [rax+rax+00h]
0x180030d48  xor     eax, eax
0x180030d4a  mov     rcx, [rbp+3C0h+var_30]
0x180030d51  xor     rcx, rsp; StackCookie
0x180030d54  call    __security_check_cookie
0x180030d59  lea     r11, [rsp+4C0h+var_20]
0x180030d61  mov     rbx, [r11+30h]
0x180030d65  mov     rsi, [r11+40h]
0x180030d69  mov     rsp, r11
0x180030d6c  pop     r15
0x180030d6e  pop     r14
0x180030d70  pop     r12
0x180030d72  pop     rdi
0x180030d73  pop     rbp
0x180030d74  retn
```
