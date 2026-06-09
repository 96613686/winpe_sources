# AslLogDebugVPrintf

- ea: `0x1800471a0`
- end: `0x180047954`
- name: `AslLogDebugVPrintf`
- size: `1972`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000b080`

## callees

- `0x180004ea0`
- `0x1800059d4`
- `0x180005a78`
- `0x180005b3c`
- `0x180005b90`
- `0x180005bc0`
- `0x180005be0`
- `0x180005c10`
- `0x180005c1c`
- `0x180005c28`
- `0x1800457d0`
- `0x180045950`
- `0x180045b54`
- `0x180045c60`
- `0x1800466f8`
- `0x1800467bc`
- `0x18004683c`
- `0x180046a04`
- `0x1800471a0`
- `0x1800e67d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800472aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800472aa`
- `ntdll!EtwEventWrite` at `0x1800478d4`
- `ntdll!EtwEventWrite` at `0x1800478d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047313`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047313`

## string_xrefs

- `0x1800472a1`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(__int64 *a1, int a2, __int64 a3, __int64 a4, char *a5, va_list a6)
{
  __int64 v9; // rax
  char v10; // r15
  int v11; // r14d
  int v12; // ecx
  FARPROC ConstructPartialMsgIfA; // rax
  HMODULE v14; // rcx
  HANDLE FileW; // rax
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
  size_t v67; // r8
  struct _ASL_LOG *v68; // rbx
  __int64 v69; // rcx
  int v70; // edi
  __int64 *v71; // rdx
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
    if ( !a1[90] && qword_18011BF20 )
    {
      dword_18011BF34 = 0;
      qword_18011BF20 = 0;
      WdsSetupLogMessageA = 0;
    }
    if ( !dword_18011BF34 )
    {
      dword_18011BF34 = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ConstructPartialMsgIfA = GetProcAddress_0((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_18011BF20 = (__int64)ConstructPartialMsgIfA;
        WdsSetupLogMessageA = (__int64)GetProcAddress_0(v14, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError_0 = GetLastError_0();
        v12 = v74;
        if ( LastError_0 == 231 )
          dword_18011BF18 = 1;
      }
      else
      {
        dword_18011BF18 = 1;
        CloseHandle_0(FileW);
        v12 = v74;
      }
    }
    if ( !qword_18011BF20 || (v17 = 1, !WdsSetupLogMessageA) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_18011BF18 || v12 )
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
                  (&off_1800EE9F8)[2 * v11],
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
        if ( dword_18011BF18 )
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
            v71 = AE_DEBUG_EVENT;
          }
          else
          {
            if ( v75 != 2 )
            {
LABEL_152:
              if ( v73 )
                AslLogpWritePanther((const char **)v68, v70, a3, v83, MultiByteStr);
              SetLastError_0(dwErrCode);
              if ( v70 == 1 && (*(_BYTE *)(*(_QWORD *)v68 + 80LL) & 2) != 0 )
              {
                if ( IsDebuggerPresent_0() )
                  DebugBreak_0();
              }
              return;
            }
            v71 = AE_MARK_EVENT;
          }
          EtwEventWrite(v69, v71, 1, &v84);
          goto LABEL_152;
        }
        v50 = v83;
        if ( v83 == -1 )
          v50 = 0;
        v51 = (const char *)a3;
        if ( !a3 )
          v51 = (const char *)&word_1800F2B62;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_1800EE9F8)[v27], v51, v50) < 0 && v48 )
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
0x1800471a0  push    rbp
0x1800471a2  push    rbx
0x1800471a3  push    rsi
0x1800471a4  push    rdi
0x1800471a5  push    r12
0x1800471a7  push    r13
0x1800471a9  push    r14
0x1800471ab  push    r15
0x1800471ad  lea     rbp, [rsp-13C8h]
0x1800471b5  mov     eax, 14C8h
0x1800471ba  call    _alloca_probe
0x1800471bf  sub     rsp, rax
0x1800471c2  mov     rax, cs:__security_cookie
0x1800471c9  xor     rax, rsp
0x1800471cc  mov     [rbp+1400h+var_50], rax
0x1800471d3  mov     r12, [rbp+1400h+arg_20]
0x1800471da  mov     r13, r9
0x1800471dd  mov     rax, [rbp+1400h+arg_28]
0x1800471e4  mov     esi, edx
0x1800471e6  mov     [rbp+1400h+var_1468], r12
0x1800471ea  mov     rbx, rcx
0x1800471ed  mov     [rbp+1400h+Args], rax
0x1800471f1  mov     [rbp+1400h+var_1470], r9
0x1800471f5  mov     [rsp+1500h+var_1498], r8
0x1800471fa  mov     [rsp+1500h+var_14A4], edx
0x1800471fe  mov     [rbp+1400h+var_1478], rcx
0x180047202  test    rcx, rcx
0x180047205  jz      loc_180047931
0x18004720b  call    GetLastError_0
0x180047210  xor     edx, edx
0x180047212  mov     [rsp+1500h+dwErrCode], eax
0x180047216  mov     [rbp+1400h+MultiByteStr], dl
0x180047219  cmp     esi, 3
0x18004721c  jnz     short loc_180047230
0x18004721e  mov     rax, [rbx]
0x180047221  test    byte ptr [rax+50h], 10h
0x180047225  jnz     short loc_180047230
0x180047227  mov     r15b, dl
0x18004722a  mov     [rsp+1500h+var_14B0], dl
0x18004722e  jmp     short loc_18004723B
0x180047230  mov     rax, [rbx]
0x180047233  mov     r15b, 1
0x180047236  mov     [rsp+1500h+var_14B0], r15b
0x18004723b  mov     ecx, [rax+50h]
0x18004723e  mov     r14d, 3
0x180047244  and     ecx, 100h
0x18004724a  cmp     esi, r14d
0x18004724d  mov     [rsp+1500h+var_14AC], ecx
0x180047251  cmovl   r14d, esi
0x180047255  mov     [rsp+1500h+var_14A8], r14d
0x18004725a  cmp     [rbx+2D0h], rdx
0x180047261  jnz     short loc_180047280
0x180047263  cmp     cs:qword_18011BF20, rdx
0x18004726a  jz      short loc_180047280
0x18004726c  mov     cs:dword_18011BF34, edx
0x180047272  mov     cs:qword_18011BF20, rdx
0x180047279  mov     cs:WdsSetupLogMessageA, rdx
0x180047280  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180047284  cmp     cs:dword_18011BF34, edx
0x18004728a  jnz     loc_180047354
0x180047290  lea     r8, [rbx+2D0h]; phModule
0x180047297  mov     cs:dword_18011BF34, 1
0x1800472a1  lea     rdx, aWdscoreDll; "wdscore.dll"
0x1800472a8  xor     ecx, ecx; dwFlags
0x1800472aa  call    cs:__imp_GetModuleHandleExA
0x1800472b0  test    eax, eax
0x1800472b2  jz      short loc_1800472E8
0x1800472b4  mov     rcx, [rbx+2D0h]; hModule
0x1800472bb  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x1800472c2  call    GetProcAddress_0
0x1800472c7  mov     rcx, [rbx+2D0h]; hModule
0x1800472ce  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x1800472d5  mov     cs:qword_18011BF20, rax
0x1800472dc  call    GetProcAddress_0
0x1800472e1  mov     cs:WdsSetupLogMessageA, rax
0x1800472e8  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x1800472f1  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x1800472f8  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180047300  xor     r9d, r9d; lpSecurityAttributes
0x180047303  xor     r8d, r8d; dwShareMode
0x180047306  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x18004730e  mov     edx, 40000000h; dwDesiredAccess
0x180047313  call    cs:__imp_CreateFileW
0x180047319  cmp     rax, rdi
0x18004731c  jnz     short loc_18004733C
0x18004731e  call    GetLastError_0
0x180047323  mov     ecx, [rsp+1500h+var_14AC]
0x180047327  xor     edx, edx
0x180047329  cmp     eax, 0E7h
0x18004732e  jnz     short loc_180047354
0x180047330  mov     cs:dword_18011BF18, 1
0x18004733a  jmp     short loc_180047354
0x18004733c  mov     rcx, rax; hObject
0x18004733f  mov     cs:dword_18011BF18, 1
0x180047349  call    CloseHandle_0
0x18004734e  mov     ecx, [rsp+1500h+var_14AC]
0x180047352  xor     edx, edx
0x180047354  cmp     cs:qword_18011BF20, rdx
0x18004735b  jz      short loc_180047368
0x18004735d  cmp     cs:WdsSetupLogMessageA, rdx
0x180047364  mov     al, 1
0x180047366  jnz     short loc_18004736A
0x180047368  mov     al, dl
0x18004736a  mov     [rsp+1500h+var_14AF], al
0x18004736e  test    r15b, r15b
0x180047371  jnz     short loc_18004738C
0x180047373  cmp     esi, 1
0x180047376  jz      short loc_18004738C
0x180047378  test    al, al
0x18004737a  jnz     short loc_18004738C
0x18004737c  cmp     cs:dword_18011BF18, edx
0x180047382  jnz     short loc_18004738C
0x180047384  test    ecx, ecx
0x180047386  jz      loc_180047931
0x18004738c  mov     r15d, 3FEh
0x180047392  lea     rax, [rbp+1400h+WideCharStr]
0x180047399  mov     r9, r12
0x18004739c  mov     [rsp+1500h+Buffer], rax
0x1800473a1  lea     r8, aHs_1; "%hs"
0x1800473a8  mov     [rsp+1500h+var_1488], r15
0x1800473ad  lea     rcx, [rbp+1400h+Format]
0x1800473b4  lea     r12d, [r15+2]
0x1800473b8  mov     edx, r12d
0x1800473bb  call    RtlStringCchPrintfW
0x1800473c0  xor     r10d, r10d
0x1800473c3  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x1800473ca  mov     esi, 7FFFFFFEh
0x1800473cf  test    eax, eax
0x1800473d1  jns     short loc_180047415
0x1800473d3  mov     ecx, esi
0x1800473d5  lea     rax, [rbp+1400h+Format]
0x1800473dc  mov     r8, rbx
0x1800473df  mov     edx, r12d
0x1800473e2  test    rcx, rcx
0x1800473e5  jz      short loc_180047406
0x1800473e7  movzx   r9d, word ptr [r8]
0x1800473eb  test    r9w, r9w
0x1800473ef  jz      short loc_180047406
0x1800473f1  mov     [rax], r9w
0x1800473f5  add     r8, 2
0x1800473f9  add     rax, 2
0x1800473fd  dec     rcx
0x180047400  sub     rdx, 1
0x180047404  jnz     short loc_1800473E2
0x180047406  test    rdx, rdx
0x180047409  lea     rcx, [rax-2]
0x18004740d  cmovnz  rcx, rax
0x180047411  mov     [rcx], r10w
0x180047415  movzx   eax, [rbp+1400h+Format]
0x18004741c  test    ax, ax
0x18004741f  jz      short loc_18004746E
0x180047421  mov     edx, 53h ; 'S'
0x180047426  lea     rcx, [rbp+1400h+Format]
0x18004742d  lea     r8d, [rdx+20h]
0x180047431  cmp     ax, 25h ; '%'
0x180047435  jnz     short loc_180047462
0x180047437  add     rcx, 2
0x18004743b  cmp     word ptr [rcx], 2Eh ; '.'
0x18004743f  jz      short loc_180047437
0x180047441  movzx   eax, word ptr [rcx]
0x180047444  sub     ax, 30h ; '0'
0x180047448  cmp     ax, 9
0x18004744c  jbe     short loc_180047437
0x18004744e  cmp     [rcx], r8w
0x180047452  jnz     short loc_180047459
0x180047454  mov     [rcx], dx
0x180047457  jmp     short loc_180047462
0x180047459  cmp     [rcx], dx
0x18004745c  jnz     short loc_180047462
0x18004745e  mov     [rcx], r8w
0x180047462  add     rcx, 2
0x180047466  movzx   eax, word ptr [rcx]
0x180047469  test    ax, ax
0x18004746c  jnz     short loc_180047431
0x18004746e  mov     eax, r13d
0x180047471  cmp     r13, rdi
0x180047474  jnz     short loc_180047479
0x180047476  mov     eax, r10d
0x180047479  mov     [rsp+1500h+var_14C0], eax
0x18004747d  lea     rcx, off_1800EE9F8; "PRINT"
0x180047484  mov     rax, [rsp+1500h+var_1498]
0x180047489  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x18004748e  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x180047493  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x180047498  movsxd  r13, r14d
0x18004749b  mov     rdx, r15; unsigned __int64
0x18004749e  add     r13, r13
0x1800474a1  mov     rax, [rcx+r13*8]
0x1800474a5  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x1800474ac  mov     [rsp+1500h+hTemplateFile], rax
0x1800474b1  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x1800474b8  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800474bd  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x1800474c5  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800474ca  xor     r9d, r9d
0x1800474cd  test    eax, eax
0x1800474cf  jns     short loc_180047511
0x1800474d1  mov     rcx, rsi
0x1800474d4  lea     rax, [rbp+1400h+WideCharStr]
0x1800474db  mov     rdx, r12
0x1800474de  test    rcx, rcx
0x1800474e1  jz      short loc_180047502
0x1800474e3  movzx   r8d, word ptr [rbx]
0x1800474e7  test    r8w, r8w
0x1800474eb  jz      short loc_180047502
0x1800474ed  mov     [rax], r8w
0x1800474f1  add     rbx, 2
0x1800474f5  add     rax, 2
0x1800474f9  dec     rcx
0x1800474fc  sub     rdx, 1
0x180047500  jnz     short loc_1800474DE
0x180047502  test    rdx, rdx
0x180047505  lea     rcx, [rax-2]
0x180047509  cmovnz  rcx, rax
0x18004750d  mov     [rcx], r9w
0x180047511  mov     r14, [rsp+1500h+Buffer]
0x180047516  mov     r12d, 80000005h
0x18004751c  mov     rsi, [rsp+1500h+var_1488]
0x180047521  mov     rdi, r14
0x180047524  mov     r15, rsi
0x180047527  test    r14, r14
0x18004752a  jnz     short loc_180047531
0x18004752c  test    rsi, rsi
0x18004752f  jnz     short loc_18004753A
0x180047531  cmp     r15, 7FFFFFFFh
0x180047538  jbe     short loc_180047543
0x18004753a  mov     [r14], r9w
0x18004753e  jmp     loc_1800475D0
0x180047543  test    r15, r15
0x180047546  jnz     short loc_18004756C
0x180047548  mov     rdx, rdi
0x18004754b  mov     rax, r15
0x18004754e  mov     ecx, r9d
0x180047551  cmp     [rbp+1400h+Format], r9w
0x180047559  jz      short loc_1800475B9
0x18004755b  test    rdi, rdi
0x18004755e  jnz     short loc_180047567
0x180047560  mov     ecx, 0C000000Dh
0x180047565  jmp     short loc_1800475BF
0x180047567  mov     ecx, r12d
0x18004756a  jmp     short loc_1800475B9
0x18004756c  mov     r9, [rbp+1400h+Args]; Args
0x180047570  lea     rbx, [rsi-1]
0x180047574  mov     rdx, rbx; BufferCount
0x180047577  lea     r8, [rbp+1400h+Format]; Format
0x18004757e  mov     rcx, rdi; Buffer
0x180047581  call    _vsnwprintf
0x180047586  xor     r9d, r9d
0x180047589  test    eax, eax
0x18004758b  js      short loc_18004759E
0x18004758d  cdqe
0x18004758f  cmp     rax, rbx
0x180047592  ja      short loc_18004759E
0x180047594  mov     ecx, r9d
0x180047597  jz      short loc_1800475A1
0x180047599  mov     rbx, rax
0x18004759c  jmp     short loc_1800475A6
0x18004759e  mov     ecx, r12d
0x1800475a1  mov     [r14+rbx*2], r9w
0x1800475a6  mov     rax, r15
0x1800475a9  lea     rdx, [r14+rbx*2]
0x1800475ad  sub     rax, rbx
0x1800475b0  test    ecx, ecx
0x1800475b2  jns     short loc_1800475B9
0x1800475b4  cmp     ecx, r12d
0x1800475b7  jnz     short loc_1800475BF
0x1800475b9  mov     r14, rdx
0x1800475bc  mov     rsi, rax
0x1800475bf  mov     edx, 80000000h
0x1800475c4  lea     eax, [rcx+rdx]
0x1800475c7  test    edx, eax
0x1800475c9  jnz     short loc_180047626
0x1800475cb  cmp     ecx, r12d
0x1800475ce  jz      short loc_180047626
0x1800475d0  test    rsi, rsi
0x1800475d3  jz      short loc_180047626
0x1800475d5  cmp     rsi, 7FFFFFFFh
0x1800475dc  jbe     short loc_1800475E6
0x1800475de  xor     esi, esi
0x1800475e0  mov     [r14], si
0x1800475e4  jmp     short loc_180047628
0x1800475e6  mov     eax, 7FFFFFFEh
0x1800475eb  lea     rdx, aMessageTooLong; "Message too long!"
0x1800475f2  test    rax, rax
0x1800475f5  jz      short loc_180047614
0x1800475f7  movzx   ecx, word ptr [rdx]
0x1800475fa  test    cx, cx
0x1800475fd  jz      short loc_180047614
0x1800475ff  mov     [r14], cx
0x180047603  add     rdx, 2
0x180047607  add     r14, 2
0x18004760b  dec     rax
0x18004760e  sub     rsi, 1
0x180047612  jnz     short loc_1800475F2
0x180047614  test    rsi, rsi
0x180047617  lea     rcx, [r14-2]
0x18004761b  cmovnz  rcx, r14
0x18004761f  xor     esi, esi
0x180047621  mov     [rcx], si
0x180047624  jmp     short loc_180047628
  ... truncated ...
```
