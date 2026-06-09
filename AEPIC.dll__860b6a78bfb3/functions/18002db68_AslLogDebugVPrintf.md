# AslLogDebugVPrintf

- ea: `0x18002db68`
- end: `0x18002e0ec`
- name: `AslLogDebugVPrintf`
- size: `1412`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180022f40`

## callees

- `0x180005890`
- `0x18002b538`
- `0x18002b590`
- `0x18002cd84`
- `0x18002ce14`
- `0x18002cf30`
- `0x18002d134`
- `0x18002d240`
- `0x18002d3d8`
- `0x18002d414`
- `0x18002d458`
- `0x18002d5e4`
- `0x18002d64c`
- `0x18002db68`
- `0x1800e4d80`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002e077`
- `ntdll!EtwEventWrite` at `0x18002e077`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002dc6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002dc6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dc7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dc96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dc7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dc96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0a5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002e0c3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002e0c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e0b9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002e0b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dcfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dcfd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002df28`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002df28`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002dcc8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002dcc8`

## string_xrefs

- `0x18002dc62`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(HMODULE *a1, int a2, const char *a3, __int64 a4, char *a5, char *a6)
{
  HMODULE v9; // rax
  char v10; // r15
  HMODULE *v11; // rbx
  int v12; // ecx
  unsigned int v13; // r12d
  __int64 v14; // rsi
  FARPROC ProcAddress; // rax
  HMODULE v16; // rcx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  char v19; // al
  unsigned __int16 v20; // ax
  unsigned __int16 *v21; // rcx
  int v22; // eax
  unsigned __int16 *v23; // rbx
  unsigned __int64 v24; // rdi
  int v25; // eax
  unsigned __int64 v26; // rbx
  CHAR v27; // al
  int v28; // ecx
  const char *v29; // rax
  __int64 v30; // rax
  char *v31; // rdi
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // r8
  HMODULE v34; // rcx
  __int64 *v35; // rdx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char v37; // [rsp+50h] [rbp-B0h]
  char v38; // [rsp+51h] [rbp-AFh]
  int v39; // [rsp+54h] [rbp-ACh]
  unsigned __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v41; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwErrCode; // [rsp+68h] [rbp-98h]
  const char *v43; // [rsp+70h] [rbp-90h]
  char *v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  char *v46; // [rsp+88h] [rbp-78h] BYREF
  int v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+94h] [rbp-6Ch]
  CHAR MultiByteStr[1024]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR WideCharStr[1024]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v51[1024]; // [rsp+CA0h] [rbp+BA0h] BYREF

  v46 = a5;
  v44 = a6;
  v45 = a4;
  v43 = a3;
  if ( a1 )
  {
    MultiByteStr[0] = 0;
    dwErrCode = GetLastError();
    if ( a2 != 3 || (v9 = *a1, ((_BYTE)(*a1)[20] & 0x10) != 0) )
    {
      v9 = *a1;
      v10 = 1;
      v37 = 1;
    }
    else
    {
      v10 = 0;
      v37 = 0;
    }
    v11 = a1 + 90;
    v12 = (_DWORD)v9[20] & 0x100;
    v13 = 3;
    v39 = v12;
    if ( a2 < 3 )
      v13 = a2;
    if ( !*v11 && qword_1801228B8 )
    {
      dword_1801228C4 = 0;
      qword_1801228B8 = 0;
      qword_1801228D0 = 0;
    }
    v14 = -1;
    if ( !dword_1801228C4 )
    {
      dword_1801228C4 = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", a1 + 90) )
      {
        ProcAddress = GetProcAddress(*v11, "ConstructPartialMsgIfA");
        v16 = *v11;
        qword_1801228B8 = (__int64)ProcAddress;
        qword_1801228D0 = (__int64)GetProcAddress(v16, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v12 = v39;
        if ( LastError == 231 )
          dword_1801228B0 = 1;
      }
      else
      {
        dword_1801228B0 = 1;
        CloseHandle(FileW);
        v12 = v39;
      }
    }
    if ( !qword_1801228B8 || (v19 = 1, !qword_1801228D0) )
      v19 = 0;
    v38 = v19;
    if ( v10 || a2 == 1 || v19 || dword_1801228B0 || v12 )
    {
      v41 = WideCharStr;
      v40 = 1022;
      if ( (int)RtlStringCchPrintfW(v51, 0x400u, L"%hs", v46) < 0 )
        RtlStringCchCopyW(v51, 0x400u, L"ASL_LOG FAIL: ");
      v20 = v51[0];
      if ( v51[0] )
      {
        v21 = v51;
        do
        {
          if ( v20 == 37 )
          {
            do
            {
              do
                ++v21;
              while ( *v21 == 46 );
            }
            while ( (unsigned __int16)(*v21 - 48) <= 9u );
            if ( *v21 == 115 )
            {
              *v21 = 83;
            }
            else if ( *v21 == 83 )
            {
              *v21 = 115;
            }
          }
          v20 = *++v21;
        }
        while ( *v21 );
      }
      v22 = a4;
      if ( a4 == -1 )
        v22 = 0;
      if ( (int)RtlStringCchPrintfExW(
                  WideCharStr,
                  0x3FEu,
                  &v41,
                  &v40,
                  0x100u,
                  L"%hs,%hs,%d,",
                  (&off_1800EE818)[2 * (int)v13],
                  v43,
                  v22) < 0 )
        RtlStringCchCopyW(WideCharStr, 0x400u, L"ASL_LOG FAIL: ");
      v23 = v41;
      v24 = v40;
      v25 = RtlStringCchVPrintfExW(v41, v40, &v41, &v40, dwCreationDisposition, v51, v44);
      if ( (int)(v25 + 0x80000000) >= 0 && v25 != -2147483643 )
        RtlStringCchCopyW(v41, v40, L"Message too long!");
      AslLogpFinalizeBufferW(v23, v24);
      v26 = -1;
      do
        ++v26;
      while ( WideCharStr[v26] );
      if ( dword_1801228B0 )
        AslLogpWritePipe(WideCharStr, 2 * v26);
      if ( WideCharToMultiByte(0xFDE9u, 0, WideCharStr, -1, MultiByteStr, 1024, 0, 0) )
      {
        v27 = MultiByteStr[0];
      }
      else
      {
        v27 = 0;
        MultiByteStr[0] = 0;
      }
      if ( !v27 )
      {
        v28 = v45;
        if ( v45 == -1 )
          v28 = 0;
        v29 = v43;
        if ( !v43 )
          v29 = (const char *)&qword_1800F3280;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v26, "%s,%s,%d,", (&off_1800EE818)[2 * (int)v13], v29, v28) < 0 )
          RtlStringCchCopyA(MultiByteStr, v26, "ASL_LOG FAIL: ");
        v30 = -1;
        do
          ++v30;
        while ( MultiByteStr[v30] );
        v31 = &MultiByteStr[v30];
        v32 = v26 - v30;
        if ( (int)RtlStringCchVPrintfA(&MultiByteStr[v30], v32, v46, v44) < 0 )
          RtlStringCchCopyA(v31, v32, "Message too long!");
        AslLogpFinalizeBuffer(v31, v32 + 2);
      }
      v33 = -1;
      do
        ++v33;
      while ( MultiByteStr[v33] );
      if ( v37 || v39 )
        AslLogpWriteLog((struct _ASL_LOG *)a1, MultiByteStr, v33);
      if ( a2 != 1 )
        goto LABEL_78;
      v34 = a1[89];
      if ( !v34 )
        goto LABEL_78;
      v46 = MultiByteStr;
      do
        ++v14;
      while ( MultiByteStr[v14] );
      v48 = 0;
      v47 = v14 + 1;
      if ( v13 == 1 )
      {
        v35 = AE_DEBUG_EVENT;
      }
      else
      {
        if ( v13 != 2 )
        {
LABEL_78:
          if ( v38 )
            AslLogpWritePanther(a1, v13, v43, v45, MultiByteStr);
          SetLastError(dwErrCode);
          if ( v13 == 1 && ((_BYTE)(*a1)[20] & 2) != 0 )
          {
            if ( IsDebuggerPresent() )
              DebugBreak();
          }
          return;
        }
        v35 = AE_MARK_EVENT;
      }
      EtwEventWrite(v34, v35, 1, &v46);
      goto LABEL_78;
    }
  }
}

```

## disassembly

```asm
0x18002db68  push    rbp
0x18002db6a  push    rbx
0x18002db6b  push    rsi
0x18002db6c  push    rdi
0x18002db6d  push    r12
0x18002db6f  push    r13
0x18002db71  push    r14
0x18002db73  push    r15
0x18002db75  lea     rbp, [rsp-13B8h]
0x18002db7d  mov     eax, 14B8h
0x18002db82  call    _alloca_probe
0x18002db87  sub     rsp, rax
0x18002db8a  mov     rax, cs:__security_cookie
0x18002db91  xor     rax, rsp
0x18002db94  mov     [rbp+13F0h+var_50], rax
0x18002db9b  mov     rax, [rbp+13F0h+arg_20]
0x18002dba2  xor     esi, esi
0x18002dba4  mov     [rbp+13F0h+var_1468], rax
0x18002dba8  mov     rdi, r9
0x18002dbab  mov     rax, [rbp+13F0h+arg_28]
0x18002dbb2  mov     r13d, edx
0x18002dbb5  mov     [rsp+14F0h+var_1478], rax
0x18002dbba  mov     r14, rcx
0x18002dbbd  mov     [rbp+13F0h+var_1470], r9
0x18002dbc1  mov     [rsp+14F0h+var_1480], r8
0x18002dbc6  test    rcx, rcx
0x18002dbc9  jz      loc_18002E0C9
0x18002dbcf  call    cs:__imp_GetLastError
0x18002dbd5  mov     [rbp+13F0h+MultiByteStr], sil
0x18002dbd9  mov     [rsp+14F0h+dwErrCode], eax
0x18002dbdd  cmp     r13d, 3
0x18002dbe1  jnz     short loc_18002DBF6
0x18002dbe3  mov     rax, [r14]
0x18002dbe6  test    byte ptr [rax+50h], 10h
0x18002dbea  jnz     short loc_18002DBF6
0x18002dbec  mov     r15b, sil
0x18002dbef  mov     [rsp+14F0h+var_14A0], sil
0x18002dbf4  jmp     short loc_18002DC01
0x18002dbf6  mov     rax, [r14]
0x18002dbf9  mov     r15b, 1
0x18002dbfc  mov     [rsp+14F0h+var_14A0], r15b
0x18002dc01  mov     ecx, [rax+50h]
0x18002dc04  lea     rbx, [r14+2D0h]
0x18002dc0b  and     ecx, 100h
0x18002dc11  mov     r12d, 3
0x18002dc17  cmp     r13d, r12d
0x18002dc1a  mov     [rsp+14F0h+var_149C], ecx
0x18002dc1e  cmovl   r12d, r13d
0x18002dc22  cmp     [rbx], rsi
0x18002dc25  jnz     short loc_18002DC44
0x18002dc27  cmp     cs:qword_1801228B8, rsi
0x18002dc2e  jz      short loc_18002DC44
0x18002dc30  mov     cs:dword_1801228C4, esi
0x18002dc36  mov     cs:qword_1801228B8, rsi
0x18002dc3d  mov     cs:qword_1801228D0, rsi
0x18002dc44  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002dc48  cmp     cs:dword_1801228C4, 0
0x18002dc4f  jnz     loc_18002DD09
0x18002dc55  mov     r8, rbx; phModule
0x18002dc58  mov     cs:dword_1801228C4, 1
0x18002dc62  lea     rdx, aWdscoreDll; "wdscore.dll"
0x18002dc69  xor     ecx, ecx; dwFlags
0x18002dc6b  call    cs:__imp_GetModuleHandleExA
0x18002dc71  test    eax, eax
0x18002dc73  jz      short loc_18002DCA3
0x18002dc75  mov     rcx, [rbx]; hModule
0x18002dc78  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x18002dc7f  call    cs:__imp_GetProcAddress
0x18002dc85  mov     rcx, [rbx]; hModule
0x18002dc88  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x18002dc8f  mov     cs:qword_1801228B8, rax
0x18002dc96  call    cs:__imp_GetProcAddress
0x18002dc9c  mov     cs:qword_1801228D0, rax
0x18002dca3  xor     ebx, ebx
0x18002dca5  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18002dcac  mov     [rsp+14F0h+hTemplateFile], rbx; hTemplateFile
0x18002dcb1  xor     r9d, r9d; lpSecurityAttributes
0x18002dcb4  mov     [rsp+14F0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18002dcb8  xor     r8d, r8d; dwShareMode
0x18002dcbb  mov     edx, 40000000h; dwDesiredAccess
0x18002dcc0  mov     [rsp+14F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002dcc8  call    cs:__imp_CreateFileW
0x18002dcce  cmp     rax, rsi
0x18002dcd1  jnz     short loc_18002DCF0
0x18002dcd3  call    cs:__imp_GetLastError
0x18002dcd9  mov     ecx, [rsp+14F0h+var_149C]
0x18002dcdd  cmp     eax, 0E7h
0x18002dce2  jnz     short loc_18002DD0B
0x18002dce4  mov     cs:dword_1801228B0, 1
0x18002dcee  jmp     short loc_18002DD0B
0x18002dcf0  mov     rcx, rax; hObject
0x18002dcf3  mov     cs:dword_1801228B0, 1
0x18002dcfd  call    cs:__imp_CloseHandle
0x18002dd03  mov     ecx, [rsp+14F0h+var_149C]
0x18002dd07  jmp     short loc_18002DD0B
0x18002dd09  xor     ebx, ebx
0x18002dd0b  cmp     cs:qword_1801228B8, rbx
0x18002dd12  jz      short loc_18002DD1F
0x18002dd14  cmp     cs:qword_1801228D0, rbx
0x18002dd1b  mov     al, 1
0x18002dd1d  jnz     short loc_18002DD21
0x18002dd1f  mov     al, bl
0x18002dd21  mov     [rsp+14F0h+var_149F], al
0x18002dd25  test    r15b, r15b
0x18002dd28  jnz     short loc_18002DD44
0x18002dd2a  cmp     r13d, 1
0x18002dd2e  jz      short loc_18002DD44
0x18002dd30  test    al, al
0x18002dd32  jnz     short loc_18002DD44
0x18002dd34  cmp     cs:dword_1801228B0, ebx
0x18002dd3a  jnz     short loc_18002DD44
0x18002dd3c  test    ecx, ecx
0x18002dd3e  jz      loc_18002E0C9
0x18002dd44  mov     r9, [rbp+13F0h+var_1468]
0x18002dd48  lea     rax, [rbp+13F0h+WideCharStr]
0x18002dd4f  mov     r15d, 400h
0x18002dd55  mov     [rsp+14F0h+var_1490], rax
0x18002dd5a  mov     edx, r15d; unsigned __int64
0x18002dd5d  mov     [rsp+14F0h+var_1498], 3FEh
0x18002dd66  lea     r8, aHs_1; "%hs"
0x18002dd6d  lea     rcx, [rbp+13F0h+var_850]; unsigned __int16 *
0x18002dd74  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dd79  test    eax, eax
0x18002dd7b  jns     short loc_18002DD93
0x18002dd7d  lea     r8, aAslLogFail; "ASL_LOG FAIL: "
0x18002dd84  mov     edx, r15d; unsigned __int64
0x18002dd87  lea     rcx, [rbp+13F0h+var_850]; unsigned __int16 *
0x18002dd8e  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dd93  movzx   eax, [rbp+13F0h+var_850]
0x18002dd9a  test    ax, ax
0x18002dd9d  jz      short loc_18002DDEC
0x18002dd9f  mov     edx, 53h ; 'S'
0x18002dda4  lea     rcx, [rbp+13F0h+var_850]
0x18002ddab  lea     r8d, [rdx+20h]
0x18002ddaf  cmp     ax, 25h ; '%'
0x18002ddb3  jnz     short loc_18002DDE0
0x18002ddb5  add     rcx, 2
0x18002ddb9  cmp     word ptr [rcx], 2Eh ; '.'
0x18002ddbd  jz      short loc_18002DDB5
0x18002ddbf  movzx   eax, word ptr [rcx]
0x18002ddc2  sub     ax, 30h ; '0'
0x18002ddc6  cmp     ax, 9
0x18002ddca  jbe     short loc_18002DDB5
0x18002ddcc  cmp     [rcx], r8w
0x18002ddd0  jnz     short loc_18002DDD7
0x18002ddd2  mov     [rcx], dx
0x18002ddd5  jmp     short loc_18002DDE0
0x18002ddd7  cmp     [rcx], dx
0x18002ddda  jnz     short loc_18002DDE0
0x18002dddc  mov     [rcx], r8w
0x18002dde0  add     rcx, 2
0x18002dde4  movzx   eax, word ptr [rcx]
0x18002dde7  test    ax, ax
0x18002ddea  jnz     short loc_18002DDAF
0x18002ddec  mov     eax, edi
0x18002ddee  cmp     rdi, rsi
0x18002ddf1  jnz     short loc_18002DDF5
0x18002ddf3  mov     eax, ebx
0x18002ddf5  mov     [rsp+14F0h+var_14B0], eax
0x18002ddf9  lea     rcx, off_1800EE818; "PRINT"
0x18002de00  mov     rax, [rsp+14F0h+var_1480]
0x18002de05  lea     r9, [rsp+14F0h+var_1498]; unsigned __int64 *
0x18002de0a  mov     [rsp+14F0h+lpUsedDefaultChar], rax
0x18002de0f  lea     r8, [rsp+14F0h+var_1490]; unsigned __int16 **
0x18002de14  movsxd  r15, r12d
0x18002de17  mov     edx, 3FEh; unsigned __int64
0x18002de1c  add     r15, r15
0x18002de1f  mov     rax, [rcx+r15*8]
0x18002de23  lea     rcx, [rbp+13F0h+WideCharStr]; unsigned __int16 *
0x18002de2a  mov     [rsp+14F0h+hTemplateFile], rax
0x18002de2f  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x18002de36  mov     qword ptr [rsp+14F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18002de3b  mov     [rsp+14F0h+dwCreationDisposition], 100h; unsigned int
0x18002de43  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18002de48  test    eax, eax
0x18002de4a  jns     short loc_18002DE64
0x18002de4c  lea     r8, aAslLogFail; "ASL_LOG FAIL: "
0x18002de53  mov     edx, 400h; unsigned __int64
0x18002de58  lea     rcx, [rbp+13F0h+WideCharStr]; unsigned __int16 *
0x18002de5f  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002de64  mov     rax, [rsp+14F0h+var_1478]
0x18002de69  lea     r9, [rsp+14F0h+var_1498]; unsigned __int64 *
0x18002de6e  mov     rbx, [rsp+14F0h+var_1490]
0x18002de73  lea     r8, [rsp+14F0h+var_1490]; unsigned __int16 **
0x18002de78  mov     rdi, [rsp+14F0h+var_1498]
0x18002de7d  mov     rcx, rbx; unsigned __int16 *
0x18002de80  mov     [rsp+14F0h+hTemplateFile], rax; char *
0x18002de85  mov     rdx, rdi; unsigned __int64
0x18002de88  lea     rax, [rbp+13F0h+var_850]
0x18002de8f  mov     qword ptr [rsp+14F0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18002de94  call    ?RtlStringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; RtlStringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x18002de99  mov     ecx, 80000000h
0x18002de9e  lea     r8d, [rax+rcx]
0x18002dea2  test    ecx, r8d
0x18002dea5  jnz     short loc_18002DEC4
0x18002dea7  cmp     eax, 80000005h
0x18002deac  jz      short loc_18002DEC4
0x18002deae  mov     rdx, [rsp+14F0h+var_1498]; unsigned __int64
0x18002deb3  lea     r8, aMessageTooLong; "Message too long!"
0x18002deba  mov     rcx, [rsp+14F0h+var_1490]; unsigned __int16 *
0x18002debf  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dec4  mov     rdx, rdi; unsigned __int64
0x18002dec7  mov     rcx, rbx; unsigned __int16 *
0x18002deca  call    ?AslLogpFinalizeBufferW@@YAXPEAG_K@Z; AslLogpFinalizeBufferW(ushort *,unsigned __int64)
0x18002decf  lea     rax, [rbp+13F0h+WideCharStr]
0x18002ded6  xor     edi, edi
0x18002ded8  mov     rbx, rsi
0x18002dedb  inc     rbx
0x18002dede  cmp     [rax+rbx*2], di
0x18002dee2  jnz     short loc_18002DEDB
0x18002dee4  cmp     cs:dword_1801228B0, edi
0x18002deea  jz      short loc_18002DEFC
0x18002deec  lea     rdx, [rbx+rbx]; nNumberOfBytesToWrite
0x18002def0  lea     rcx, [rbp+13F0h+WideCharStr]; lpBuffer
0x18002def7  call    ?AslLogpWritePipe@@YAXPEAX_K@Z; AslLogpWritePipe(void *,unsigned __int64)
0x18002defc  mov     [rsp+14F0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18002df01  lea     rax, [rbp+13F0h+MultiByteStr]
0x18002df05  mov     [rsp+14F0h+hTemplateFile], rdi; lpDefaultChar
0x18002df0a  lea     r8, [rbp+13F0h+WideCharStr]; lpWideCharStr
0x18002df11  mov     [rsp+14F0h+dwFlagsAndAttributes], 400h; cbMultiByte
0x18002df19  mov     r9d, esi; cchWideChar
0x18002df1c  xor     edx, edx; dwFlags
0x18002df1e  mov     qword ptr [rsp+14F0h+dwCreationDisposition], rax; lpMultiByteStr
0x18002df23  mov     ecx, 0FDE9h; CodePage
0x18002df28  call    cs:__imp_WideCharToMultiByte
0x18002df2e  test    eax, eax
0x18002df30  jnz     short loc_18002DF3A
0x18002df32  mov     al, dil
0x18002df35  mov     [rbp+13F0h+MultiByteStr], al
0x18002df38  jmp     short loc_18002DF3D
0x18002df3a  mov     al, [rbp+13F0h+MultiByteStr]
0x18002df3d  test    al, al
0x18002df3f  jnz     loc_18002DFF8
0x18002df45  mov     rax, [rbp+13F0h+var_1470]
0x18002df49  mov     ecx, eax
0x18002df4b  cmp     rax, rsi
0x18002df4e  jnz     short loc_18002DF52
0x18002df50  mov     ecx, edi
0x18002df52  mov     rdx, [rsp+14F0h+var_1480]
0x18002df57  lea     r8, qword_1800F3280
0x18002df5e  test    rdx, rdx
0x18002df61  mov     [rsp+14F0h+dwFlagsAndAttributes], ecx
0x18002df65  mov     rax, rdx
0x18002df68  lea     r9, off_1800EE818; "PRINT"
0x18002df6f  mov     r9, [r9+r15*8]
0x18002df73  lea     rcx, [rbp+13F0h+MultiByteStr]; char *
0x18002df77  cmovz   rax, r8
0x18002df7b  mov     rdx, rbx; unsigned __int64
0x18002df7e  lea     r8, aSSD; "%s,%s,%d,"
0x18002df85  mov     qword ptr [rsp+14F0h+dwCreationDisposition], rax
0x18002df8a  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002df8f  test    eax, eax
0x18002df91  jns     short loc_18002DFA6
0x18002df93  lea     r8, aAslLogFail_0; "ASL_LOG FAIL: "
0x18002df9a  mov     rdx, rbx; unsigned __int64
0x18002df9d  lea     rcx, [rbp+13F0h+MultiByteStr]; char *
0x18002dfa1  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x18002dfa6  lea     rcx, [rbp+13F0h+MultiByteStr]
0x18002dfaa  mov     rax, rsi
0x18002dfad  inc     rax
0x18002dfb0  cmp     [rcx+rax], dil
0x18002dfb4  jnz     short loc_18002DFAD
0x18002dfb6  mov     r9, [rsp+14F0h+var_1478]; char *
0x18002dfbb  lea     rdi, [rbp+13F0h+MultiByteStr]
0x18002dfbf  mov     r8, [rbp+13F0h+var_1468]; char *
0x18002dfc3  add     rdi, rax
0x18002dfc6  sub     rbx, rax
0x18002dfc9  mov     rcx, rdi; char *
0x18002dfcc  mov     rdx, rbx; unsigned __int64
0x18002dfcf  call    ?RtlStringCchVPrintfA@@YAJPEAD_KPEBD0@Z; RtlStringCchVPrintfA(char *,unsigned __int64,char const *,char *)
0x18002dfd4  test    eax, eax
0x18002dfd6  jns     short loc_18002DFEA
0x18002dfd8  lea     r8, aMessageTooLong_0; "Message too long!"
0x18002dfdf  mov     rdx, rbx; unsigned __int64
0x18002dfe2  mov     rcx, rdi; char *
0x18002dfe5  call    ?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z; RtlStringCchCopyA(char *,unsigned __int64,char const *)
0x18002dfea  lea     rdx, [rbx+2]; unsigned __int64
0x18002dfee  mov     rcx, rdi; char *
0x18002dff1  call    ?AslLogpFinalizeBuffer@@YAXPEAD_K@Z; AslLogpFinalizeBuffer(char *,unsigned __int64)
0x18002dff6  xor     edi, edi
0x18002dff8  lea     rax, [rbp+13F0h+MultiByteStr]
0x18002dffc  mov     r8, rsi
0x18002dfff  inc     r8; unsigned __int64
0x18002e002  cmp     [rax+r8], dil
0x18002e006  jnz     short loc_18002DFFF
0x18002e008  cmp     [rsp+14F0h+var_14A0], dil
0x18002e00d  jnz     short loc_18002E015
0x18002e00f  cmp     [rsp+14F0h+var_149C], edi
0x18002e013  jz      short loc_18002E021
0x18002e015  lea     rdx, [rbp+13F0h+MultiByteStr]; char *
0x18002e019  mov     rcx, r14; struct _ASL_LOG *
0x18002e01c  call    ?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z; AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)
0x18002e021  mov     ebx, 1
0x18002e026  cmp     r13d, ebx
0x18002e029  jnz     short loc_18002E07D
0x18002e02b  mov     rcx, [r14+2C8h]
0x18002e032  test    rcx, rcx
0x18002e035  jz      short loc_18002E07D
0x18002e037  lea     rax, [rbp+13F0h+MultiByteStr]
0x18002e03b  mov     [rbp+13F0h+var_1468], rax
  ... truncated ...
```
