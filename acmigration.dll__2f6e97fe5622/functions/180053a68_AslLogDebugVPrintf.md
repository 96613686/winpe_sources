# AslLogDebugVPrintf

- ea: `0x180053a68`
- end: `0x18005421b`
- name: `AslLogDebugVPrintf`
- size: `1971`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000ae20`

## callees

- `0x180001cf0`
- `0x18000288c`
- `0x1800029a4`
- `0x180002a67`
- `0x180002a8b`
- `0x180002a97`
- `0x180002aaf`
- `0x180002adf`
- `0x180002aeb`
- `0x180002af7`
- `0x180002b33`
- `0x180050730`
- `0x180052e28`
- `0x180052fa8`
- `0x1800531ac`
- `0x1800532b8`
- `0x1800533c0`
- `0x180053484`
- `0x18005364c`
- `0x180053a68`
- `0x1800650c0`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x180053b72`
- `KERNEL32!GetModuleHandleExA` at `0x180053b72`
- `ntdll!EtwEventWrite` at `0x18005419b`
- `ntdll!EtwEventWrite` at `0x18005419b`

## string_xrefs

- `0x180053b69`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(__int64 *a1, int a2, const char *a3, __int64 a4, char *a5, va_list a6)
{
  __int64 v9; // rax
  char v10; // r15
  int v11; // r14d
  int v12; // ecx
  FARPROC ProcAddress; // rax
  HMODULE v14; // rcx
  HANDLE FileW_0; // rax
  DWORD LastError_0; // eax
  char v17; // al
  const wchar_t *v18; // rbx
  __int64 v19; // rcx
  wchar_t *v20; // rax
  const wchar_t *v21; // r8
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  wchar_t v24; // ax
  wchar_t *v25; // rcx
  int v26; // eax
  __int64 v27; // r13
  __int64 v28; // rcx
  WCHAR *v29; // rax
  __int64 v30; // rdx
  WCHAR *v31; // rcx
  wchar_t *v32; // r14
  int v33; // r12d
  unsigned __int64 v34; // rsi
  unsigned __int16 *v35; // rdi
  unsigned __int64 v36; // r15
  wchar_t *v37; // rdx
  unsigned __int64 v38; // rax
  int v39; // ecx
  unsigned __int64 v40; // rbx
  int v41; // eax
  __int64 v42; // rax
  const wchar_t *v43; // rdx
  wchar_t *v44; // rcx
  unsigned __int64 i; // rax
  unsigned __int16 v46; // cx
  __int64 v47; // r14
  unsigned __int64 v48; // rbx
  CHAR v49; // al
  int v50; // ecx
  const char *v51; // rax
  __int64 v52; // r15
  __int64 v53; // rax
  const char *v54; // r8
  unsigned __int64 v55; // rdx
  CHAR *v56; // rcx
  CHAR *v57; // rax
  __int64 v58; // rax
  CHAR *v59; // rdi
  unsigned __int64 v60; // rbx
  unsigned __int64 v61; // rsi
  int v62; // eax
  const char *v63; // rax
  unsigned __int64 v64; // rdx
  CHAR *v65; // rcx
  CHAR *v66; // rax
  unsigned __int64 v67; // r8
  struct _ASL_LOG *v68; // rbx
  __int64 v69; // rcx
  unsigned int v70; // edi
  void *v71; // rdx
  char v72; // [rsp+50h] [rbp-B0h]
  char v73; // [rsp+51h] [rbp-AFh]
  int v74; // [rsp+54h] [rbp-ACh]
  int v75; // [rsp+58h] [rbp-A8h]
  DWORD dwErrCode; // [rsp+60h] [rbp-A0h]
  wchar_t *Buffer; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v80; // [rsp+78h] [rbp-88h] BYREF
  va_list Args; // [rsp+80h] [rbp-80h]
  struct _ASL_LOG *v82; // [rsp+88h] [rbp-78h]
  __int64 v83; // [rsp+90h] [rbp-70h]
  char *v84; // [rsp+98h] [rbp-68h] BYREF
  int v85; // [rsp+A0h] [rbp-60h]
  int v86; // [rsp+A4h] [rbp-5Ch]
  CHAR MultiByteStr[1024]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Format[1024]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR WideCharStr[1024]; // [rsp+CB0h] [rbp+BB0h] BYREF

  v84 = a5;
  Args = a6;
  v83 = a4;
  v82 = (struct _ASL_LOG *)a1;
  if ( a1 )
  {
    dwErrCode = GetLastError_0();
    MultiByteStr[0] = 0;
    if ( a2 != 3 || (v9 = *a1, (*(_BYTE *)(*a1 + 80) & 0x10) != 0) )
    {
      v9 = *a1;
      v10 = 1;
      v72 = 1;
    }
    else
    {
      v10 = 0;
      v72 = 0;
    }
    v11 = 3;
    v12 = *(_DWORD *)(v9 + 80) & 0x100;
    v74 = v12;
    if ( a2 < 3 )
      v11 = a2;
    v75 = v11;
    if ( !a1[90] && qword_180097B28 )
    {
      dword_180097B3C = 0;
      qword_180097B28 = 0;
      qword_180097B50 = 0;
    }
    if ( !dword_180097B3C )
    {
      dword_180097B3C = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ProcAddress = WINRT_IMPL_GetProcAddress((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_180097B28 = (__int64)ProcAddress;
        qword_180097B50 = (__int64)WINRT_IMPL_GetProcAddress(v14, "WdsSetupLogMessageA");
      }
      FileW_0 = CreateFileW_0(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW_0 == (HANDLE)-1LL )
      {
        LastError_0 = GetLastError_0();
        v12 = v74;
        if ( LastError_0 == 231 )
          dword_180097B20 = 1;
      }
      else
      {
        dword_180097B20 = 1;
        CloseHandle_0(FileW_0);
        v12 = v74;
      }
    }
    if ( !qword_180097B28 || (v17 = 1, !qword_180097B50) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_180097B20 || v12 )
    {
      Buffer = WideCharStr;
      v80 = 1022;
      v18 = L"ASL_LOG FAIL: ";
      if ( (int)RtlStringCchPrintfW(Format, 1024, L"%hs", a5) < 0 )
      {
        v19 = 2147483646;
        v20 = Format;
        v21 = L"ASL_LOG FAIL: ";
        v22 = 1024;
        do
        {
          if ( !v19 )
            break;
          if ( !*v21 )
            break;
          *v20++ = *v21++;
          --v19;
          --v22;
        }
        while ( v22 );
        v23 = v20 - 1;
        if ( v22 )
          v23 = v20;
        *v23 = 0;
      }
      v24 = Format[0];
      if ( Format[0] )
      {
        v25 = Format;
        do
        {
          if ( v24 == 37 )
          {
            do
            {
              do
                ++v25;
              while ( *v25 == 46 );
            }
            while ( (unsigned __int16)(*v25 - 48) <= 9u );
            if ( *v25 == 115 )
            {
              *v25 = 83;
            }
            else if ( *v25 == 83 )
            {
              *v25 = 115;
            }
          }
          v24 = *++v25;
        }
        while ( *v25 );
      }
      v26 = a4;
      if ( a4 == -1 )
        v26 = 0;
      v27 = 2LL * v11;
      if ( (int)RtlStringCchPrintfExW(
                  WideCharStr,
                  0x3FEu,
                  &Buffer,
                  &v80,
                  0x100u,
                  L"%hs,%hs,%d,",
                  (&off_18006C128)[2 * v11],
                  a3,
                  v26) < 0 )
      {
        v28 = 2147483646;
        v29 = WideCharStr;
        v30 = 1024;
        do
        {
          if ( !v28 )
            break;
          if ( !*v18 )
            break;
          *v29++ = *v18++;
          --v28;
          --v30;
        }
        while ( v30 );
        v31 = v29 - 1;
        if ( v30 )
          v31 = v29;
        *v31 = 0;
      }
      v32 = Buffer;
      v33 = -2147483643;
      v34 = v80;
      v35 = Buffer;
      v36 = v80;
      if ( !Buffer && v80 || v80 > 0x7FFFFFFF )
      {
        *Buffer = 0;
LABEL_73:
        if ( v34 )
        {
          if ( v34 <= 0x7FFFFFFF )
          {
            v42 = 2147483646;
            v43 = L"Message too long!";
            do
            {
              if ( !v42 )
                break;
              if ( !*v43 )
                break;
              *v32++ = *v43++;
              --v42;
              --v34;
            }
            while ( v34 );
            v44 = v32 - 1;
            if ( v34 )
              v44 = v32;
            *v44 = 0;
          }
          else
          {
            *v32 = 0;
          }
        }
LABEL_83:
        for ( i = 0; i < v36; ++i )
        {
          v46 = v35[i];
          if ( !v46 )
            break;
          if ( v46 == 10 || v46 == 13 )
          {
            v35[i] = 35;
          }
          else if ( v46 == 44 )
          {
            v35[i] = 95;
          }
        }
        RtlStringCchCatW(v35, v36, L"\r\n");
        v47 = -1;
        v48 = -1;
        do
          ++v48;
        while ( WideCharStr[v48] );
        if ( dword_180097B20 )
          AslLogpWritePipe(WideCharStr, 2 * v48);
        if ( WideCharToMultiByte_0(0xFDE9u, 0, WideCharStr, -1, MultiByteStr, 1024, 0, 0) )
        {
          v49 = MultiByteStr[0];
        }
        else
        {
          v49 = 0;
          MultiByteStr[0] = 0;
        }
        if ( v49 )
        {
LABEL_136:
          v67 = -1;
          do
            ++v67;
          while ( MultiByteStr[v67] );
          if ( v72 || v74 )
          {
            v68 = v82;
            AslLogpWriteLog(v82, MultiByteStr, v67);
          }
          else
          {
            v68 = v82;
          }
          if ( a2 != 1 || (v69 = *((_QWORD *)v68 + 89)) == 0 )
          {
            v70 = v75;
            goto LABEL_152;
          }
          v84 = MultiByteStr;
          do
            ++v47;
          while ( MultiByteStr[v47] );
          v70 = v75;
          v85 = v47 + 1;
          v86 = 0;
          if ( v75 == 1 )
          {
            v71 = &AE_DEBUG_EVENT;
          }
          else
          {
            if ( v75 != 2 )
            {
LABEL_152:
              if ( v73 )
                AslLogpWritePanther(v68, v70, a3, v83, MultiByteStr);
              SetLastError_0(dwErrCode);
              if ( v70 == 1 && (*(_BYTE *)(*(_QWORD *)v68 + 80LL) & 2) != 0 )
              {
                if ( IsDebuggerPresent_0() )
                  DebugBreak_0();
              }
              return;
            }
            v71 = &AE_MARK_EVENT;
          }
          EtwEventWrite(v69, v71, 1, &v84);
          goto LABEL_152;
        }
        v50 = v83;
        if ( v83 == -1 )
          v50 = 0;
        v51 = a3;
        if ( !a3 )
          v51 = word_18006E07E;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_18006C128)[v27], v51, v50) < 0 && v48 )
        {
          v52 = 2147483646;
          if ( v48 <= 0x7FFFFFFF )
          {
            v53 = 2147483646;
            v54 = "ASL_LOG FAIL: ";
            v55 = v48;
            v56 = MultiByteStr;
            do
            {
              if ( !v53 )
                break;
              if ( !*v54 )
                break;
              *v56++ = *v54++;
              --v53;
              --v55;
            }
            while ( v55 );
            v57 = v56 - 1;
            if ( v55 )
              v57 = v56;
            *v57 = 0;
          }
          else
          {
            MultiByteStr[0] = 0;
          }
        }
        else
        {
          v52 = 2147483646;
        }
        v58 = -1;
        do
          ++v58;
        while ( MultiByteStr[v58] );
        v59 = &MultiByteStr[v58];
        v60 = v48 - v58;
        if ( v60 )
        {
          if ( v60 > 0x7FFFFFFF )
          {
            *v59 = 0;
            goto LABEL_126;
          }
          v61 = v60 - 1;
          v62 = vsnprintf(&MultiByteStr[v58], v60 - 1, v84, Args);
          if ( v62 < 0 || v62 > v61 || (v33 = 0, v62 == v61) )
            v59[v61] = 0;
          if ( v33 >= 0 )
            goto LABEL_135;
        }
        if ( !v60 )
        {
LABEL_135:
          AslLogpFinalizeBuffer(v59, v60 + 2);
          goto LABEL_136;
        }
LABEL_126:
        if ( v60 <= 0x7FFFFFFF )
        {
          v63 = "Message too long!";
          v64 = v60;
          v65 = v59;
          do
          {
            if ( !v52 )
              break;
            if ( !*v63 )
              break;
            *v65++ = *v63++;
            --v52;
            --v64;
          }
          while ( v64 );
          v66 = v65 - 1;
          if ( v64 )
            v66 = v65;
          *v66 = 0;
        }
        else
        {
          *v59 = 0;
        }
        goto LABEL_135;
      }
      if ( !v80 )
      {
        v37 = Buffer;
        v38 = 0;
        v39 = 0;
        if ( Format[0] )
        {
          if ( !Buffer )
          {
            v39 = -1073741811;
LABEL_71:
            if ( (int)(v39 + 0x80000000) < 0 || v39 == -2147483643 )
              goto LABEL_83;
            goto LABEL_73;
          }
          v39 = -2147483643;
        }
LABEL_70:
        v32 = v37;
        v34 = v38;
        goto LABEL_71;
      }
      v40 = v80 - 1;
      v41 = vsnwprintf(Buffer, v80 - 1, Format, Args);
      if ( v41 < 0 || v41 > v40 )
      {
        v39 = -2147483643;
      }
      else
      {
        v39 = 0;
        if ( v41 != v40 )
        {
          v40 = v41;
LABEL_69:
          v37 = &v32[v40];
          v38 = v36 - v40;
          goto LABEL_70;
        }
      }
      v32[v40] = 0;
      goto LABEL_69;
    }
  }
}

```

## disassembly

```asm
0x180053a68  push    rbp
0x180053a6a  push    rbx
0x180053a6b  push    rsi
0x180053a6c  push    rdi
0x180053a6d  push    r12
0x180053a6f  push    r13
0x180053a71  push    r14
0x180053a73  push    r15
0x180053a75  lea     rbp, [rsp-13C8h]
0x180053a7d  mov     eax, 14C8h
0x180053a82  call    _alloca_probe
0x180053a87  sub     rsp, rax
0x180053a8a  mov     rax, cs:__security_cookie
0x180053a91  xor     rax, rsp
0x180053a94  mov     [rbp+1400h+var_50], rax
0x180053a9b  mov     r12, [rbp+1400h+arg_20]
0x180053aa2  mov     r13, r9
0x180053aa5  mov     rax, [rbp+1400h+arg_28]
0x180053aac  mov     esi, edx
0x180053aae  mov     [rbp+1400h+var_1468], r12
0x180053ab2  mov     rbx, rcx
0x180053ab5  mov     [rbp+1400h+Args], rax
0x180053ab9  mov     [rbp+1400h+var_1470], r9
0x180053abd  mov     [rsp+1500h+var_1498], r8
0x180053ac2  mov     [rsp+1500h+var_14A4], edx
0x180053ac6  mov     [rbp+1400h+var_1478], rcx
0x180053aca  test    rcx, rcx
0x180053acd  jz      loc_1800541F8
0x180053ad3  call    GetLastError_0
0x180053ad8  xor     edx, edx
0x180053ada  mov     [rsp+1500h+dwErrCode], eax
0x180053ade  mov     [rbp+1400h+MultiByteStr], dl
0x180053ae1  cmp     esi, 3
0x180053ae4  jnz     short loc_180053AF8
0x180053ae6  mov     rax, [rbx]
0x180053ae9  test    byte ptr [rax+50h], 10h
0x180053aed  jnz     short loc_180053AF8
0x180053aef  mov     r15b, dl
0x180053af2  mov     [rsp+1500h+var_14B0], dl
0x180053af6  jmp     short loc_180053B03
0x180053af8  mov     rax, [rbx]
0x180053afb  mov     r15b, 1
0x180053afe  mov     [rsp+1500h+var_14B0], r15b
0x180053b03  mov     ecx, [rax+50h]
0x180053b06  mov     r14d, 3
0x180053b0c  and     ecx, 100h
0x180053b12  cmp     esi, r14d
0x180053b15  mov     [rsp+1500h+var_14AC], ecx
0x180053b19  cmovl   r14d, esi
0x180053b1d  mov     [rsp+1500h+var_14A8], r14d
0x180053b22  cmp     [rbx+2D0h], rdx
0x180053b29  jnz     short loc_180053B48
0x180053b2b  cmp     cs:qword_180097B28, rdx
0x180053b32  jz      short loc_180053B48
0x180053b34  mov     cs:dword_180097B3C, edx
0x180053b3a  mov     cs:qword_180097B28, rdx
0x180053b41  mov     cs:qword_180097B50, rdx
0x180053b48  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180053b4c  cmp     cs:dword_180097B3C, edx
0x180053b52  jnz     loc_180053C1B
0x180053b58  lea     r8, [rbx+2D0h]; phModule
0x180053b5f  mov     cs:dword_180097B3C, 1
0x180053b69  lea     rdx, aWdscoreDll; "wdscore.dll"
0x180053b70  xor     ecx, ecx; dwFlags
0x180053b72  call    cs:__imp_GetModuleHandleExA
0x180053b78  test    eax, eax
0x180053b7a  jz      short loc_180053BB0
0x180053b7c  mov     rcx, [rbx+2D0h]; hModule
0x180053b83  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x180053b8a  call    WINRT_IMPL_GetProcAddress
0x180053b8f  mov     rcx, [rbx+2D0h]; hModule
0x180053b96  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x180053b9d  mov     cs:qword_180097B28, rax
0x180053ba4  call    WINRT_IMPL_GetProcAddress
0x180053ba9  mov     cs:qword_180097B50, rax
0x180053bb0  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x180053bb9  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180053bc0  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180053bc8  xor     r9d, r9d; lpSecurityAttributes
0x180053bcb  xor     r8d, r8d; dwShareMode
0x180053bce  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x180053bd6  mov     edx, 40000000h; dwDesiredAccess
0x180053bdb  call    CreateFileW_0
0x180053be0  cmp     rax, rdi
0x180053be3  jnz     short loc_180053C03
0x180053be5  call    GetLastError_0
0x180053bea  mov     ecx, [rsp+1500h+var_14AC]
0x180053bee  xor     edx, edx
0x180053bf0  cmp     eax, 0E7h
0x180053bf5  jnz     short loc_180053C1B
0x180053bf7  mov     cs:dword_180097B20, 1
0x180053c01  jmp     short loc_180053C1B
0x180053c03  mov     rcx, rax; hObject
0x180053c06  mov     cs:dword_180097B20, 1
0x180053c10  call    CloseHandle_0
0x180053c15  mov     ecx, [rsp+1500h+var_14AC]
0x180053c19  xor     edx, edx
0x180053c1b  cmp     cs:qword_180097B28, rdx
0x180053c22  jz      short loc_180053C2F
0x180053c24  cmp     cs:qword_180097B50, rdx
0x180053c2b  mov     al, 1
0x180053c2d  jnz     short loc_180053C31
0x180053c2f  mov     al, dl
0x180053c31  mov     [rsp+1500h+var_14AF], al
0x180053c35  test    r15b, r15b
0x180053c38  jnz     short loc_180053C53
0x180053c3a  cmp     esi, 1
0x180053c3d  jz      short loc_180053C53
0x180053c3f  test    al, al
0x180053c41  jnz     short loc_180053C53
0x180053c43  cmp     cs:dword_180097B20, edx
0x180053c49  jnz     short loc_180053C53
0x180053c4b  test    ecx, ecx
0x180053c4d  jz      loc_1800541F8
0x180053c53  mov     r15d, 3FEh
0x180053c59  lea     rax, [rbp+1400h+WideCharStr]
0x180053c60  mov     r9, r12
0x180053c63  mov     [rsp+1500h+Buffer], rax
0x180053c68  lea     r8, aHs_1; "%hs"
0x180053c6f  mov     [rsp+1500h+var_1488], r15
0x180053c74  lea     rcx, [rbp+1400h+Format]
0x180053c7b  lea     r12d, [r15+2]
0x180053c7f  mov     edx, r12d
0x180053c82  call    RtlStringCchPrintfW
0x180053c87  xor     r10d, r10d
0x180053c8a  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x180053c91  mov     esi, 7FFFFFFEh
0x180053c96  test    eax, eax
0x180053c98  jns     short loc_180053CDC
0x180053c9a  mov     ecx, esi
0x180053c9c  lea     rax, [rbp+1400h+Format]
0x180053ca3  mov     r8, rbx
0x180053ca6  mov     edx, r12d
0x180053ca9  test    rcx, rcx
0x180053cac  jz      short loc_180053CCD
0x180053cae  movzx   r9d, word ptr [r8]
0x180053cb2  test    r9w, r9w
0x180053cb6  jz      short loc_180053CCD
0x180053cb8  mov     [rax], r9w
0x180053cbc  add     r8, 2
0x180053cc0  add     rax, 2
0x180053cc4  dec     rcx
0x180053cc7  sub     rdx, 1
0x180053ccb  jnz     short loc_180053CA9
0x180053ccd  test    rdx, rdx
0x180053cd0  lea     rcx, [rax-2]
0x180053cd4  cmovnz  rcx, rax
0x180053cd8  mov     [rcx], r10w
0x180053cdc  movzx   eax, [rbp+1400h+Format]
0x180053ce3  test    ax, ax
0x180053ce6  jz      short loc_180053D35
0x180053ce8  mov     edx, 53h ; 'S'
0x180053ced  lea     rcx, [rbp+1400h+Format]
0x180053cf4  lea     r8d, [rdx+20h]
0x180053cf8  cmp     ax, 25h ; '%'
0x180053cfc  jnz     short loc_180053D29
0x180053cfe  add     rcx, 2
0x180053d02  cmp     word ptr [rcx], 2Eh ; '.'
0x180053d06  jz      short loc_180053CFE
0x180053d08  movzx   eax, word ptr [rcx]
0x180053d0b  sub     ax, 30h ; '0'
0x180053d0f  cmp     ax, 9
0x180053d13  jbe     short loc_180053CFE
0x180053d15  cmp     [rcx], r8w
0x180053d19  jnz     short loc_180053D20
0x180053d1b  mov     [rcx], dx
0x180053d1e  jmp     short loc_180053D29
0x180053d20  cmp     [rcx], dx
0x180053d23  jnz     short loc_180053D29
0x180053d25  mov     [rcx], r8w
0x180053d29  add     rcx, 2
0x180053d2d  movzx   eax, word ptr [rcx]
0x180053d30  test    ax, ax
0x180053d33  jnz     short loc_180053CF8
0x180053d35  mov     eax, r13d
0x180053d38  cmp     r13, rdi
0x180053d3b  jnz     short loc_180053D40
0x180053d3d  mov     eax, r10d
0x180053d40  mov     [rsp+1500h+var_14C0], eax
0x180053d44  lea     rcx, off_18006C128; "PRINT"
0x180053d4b  mov     rax, [rsp+1500h+var_1498]
0x180053d50  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x180053d55  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x180053d5a  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x180053d5f  movsxd  r13, r14d
0x180053d62  mov     rdx, r15; unsigned __int64
0x180053d65  add     r13, r13
0x180053d68  mov     rax, [rcx+r13*8]
0x180053d6c  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x180053d73  mov     [rsp+1500h+hTemplateFile], rax
0x180053d78  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x180053d7f  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180053d84  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x180053d8c  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180053d91  xor     r9d, r9d
0x180053d94  test    eax, eax
0x180053d96  jns     short loc_180053DD8
0x180053d98  mov     rcx, rsi
0x180053d9b  lea     rax, [rbp+1400h+WideCharStr]
0x180053da2  mov     rdx, r12
0x180053da5  test    rcx, rcx
0x180053da8  jz      short loc_180053DC9
0x180053daa  movzx   r8d, word ptr [rbx]
0x180053dae  test    r8w, r8w
0x180053db2  jz      short loc_180053DC9
0x180053db4  mov     [rax], r8w
0x180053db8  add     rbx, 2
0x180053dbc  add     rax, 2
0x180053dc0  dec     rcx
0x180053dc3  sub     rdx, 1
0x180053dc7  jnz     short loc_180053DA5
0x180053dc9  test    rdx, rdx
0x180053dcc  lea     rcx, [rax-2]
0x180053dd0  cmovnz  rcx, rax
0x180053dd4  mov     [rcx], r9w
0x180053dd8  mov     r14, [rsp+1500h+Buffer]
0x180053ddd  mov     r12d, 80000005h
0x180053de3  mov     rsi, [rsp+1500h+var_1488]
0x180053de8  mov     rdi, r14
0x180053deb  mov     r15, rsi
0x180053dee  test    r14, r14
0x180053df1  jnz     short loc_180053DF8
0x180053df3  test    rsi, rsi
0x180053df6  jnz     short loc_180053E01
0x180053df8  cmp     r15, 7FFFFFFFh
0x180053dff  jbe     short loc_180053E0A
0x180053e01  mov     [r14], r9w
0x180053e05  jmp     loc_180053E97
0x180053e0a  test    r15, r15
0x180053e0d  jnz     short loc_180053E33
0x180053e0f  mov     rdx, rdi
0x180053e12  mov     rax, r15
0x180053e15  mov     ecx, r9d
0x180053e18  cmp     [rbp+1400h+Format], r9w
0x180053e20  jz      short loc_180053E80
0x180053e22  test    rdi, rdi
0x180053e25  jnz     short loc_180053E2E
0x180053e27  mov     ecx, 0C000000Dh
0x180053e2c  jmp     short loc_180053E86
0x180053e2e  mov     ecx, r12d
0x180053e31  jmp     short loc_180053E80
0x180053e33  mov     r9, [rbp+1400h+Args]; Args
0x180053e37  lea     rbx, [rsi-1]
0x180053e3b  mov     rdx, rbx; BufferCount
0x180053e3e  lea     r8, [rbp+1400h+Format]; Format
0x180053e45  mov     rcx, rdi; Buffer
0x180053e48  call    _vsnwprintf
0x180053e4d  xor     r9d, r9d
0x180053e50  test    eax, eax
0x180053e52  js      short loc_180053E65
0x180053e54  cdqe
0x180053e56  cmp     rax, rbx
0x180053e59  ja      short loc_180053E65
0x180053e5b  mov     ecx, r9d
0x180053e5e  jz      short loc_180053E68
0x180053e60  mov     rbx, rax
0x180053e63  jmp     short loc_180053E6D
0x180053e65  mov     ecx, r12d
0x180053e68  mov     [r14+rbx*2], r9w
0x180053e6d  mov     rax, r15
0x180053e70  lea     rdx, [r14+rbx*2]
0x180053e74  sub     rax, rbx
0x180053e77  test    ecx, ecx
0x180053e79  jns     short loc_180053E80
0x180053e7b  cmp     ecx, r12d
0x180053e7e  jnz     short loc_180053E86
0x180053e80  mov     r14, rdx
0x180053e83  mov     rsi, rax
0x180053e86  mov     edx, 80000000h
0x180053e8b  lea     eax, [rcx+rdx]
0x180053e8e  test    edx, eax
0x180053e90  jnz     short loc_180053EED
0x180053e92  cmp     ecx, r12d
0x180053e95  jz      short loc_180053EED
0x180053e97  test    rsi, rsi
0x180053e9a  jz      short loc_180053EED
0x180053e9c  cmp     rsi, 7FFFFFFFh
0x180053ea3  jbe     short loc_180053EAD
0x180053ea5  xor     esi, esi
0x180053ea7  mov     [r14], si
0x180053eab  jmp     short loc_180053EEF
0x180053ead  mov     eax, 7FFFFFFEh
0x180053eb2  lea     rdx, aMessageTooLong; "Message too long!"
0x180053eb9  test    rax, rax
0x180053ebc  jz      short loc_180053EDB
0x180053ebe  movzx   ecx, word ptr [rdx]
0x180053ec1  test    cx, cx
0x180053ec4  jz      short loc_180053EDB
0x180053ec6  mov     [r14], cx
0x180053eca  add     rdx, 2
0x180053ece  add     r14, 2
0x180053ed2  dec     rax
0x180053ed5  sub     rsi, 1
0x180053ed9  jnz     short loc_180053EB9
0x180053edb  test    rsi, rsi
0x180053ede  lea     rcx, [r14-2]
0x180053ee2  cmovnz  rcx, r14
0x180053ee6  xor     esi, esi
0x180053ee8  mov     [rcx], si
0x180053eeb  jmp     short loc_180053EEF
  ... truncated ...
```
