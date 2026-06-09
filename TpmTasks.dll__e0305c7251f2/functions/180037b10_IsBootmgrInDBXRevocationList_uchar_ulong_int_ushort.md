# IsBootmgrInDBXRevocationList(uchar *,ulong,int *,ushort *)

- ea: `0x180037b10`
- end: `0x180037eb2`
- name: `?IsBootmgrInDBXRevocationList@@YAJPEAEKPEAHPEAG@Z`
- size: `930`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x180037338`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18001bd50`
- `0x18001bddc`
- `0x180034178`
- `0x1800359b8`
- `0x180036068`
- `0x180036f28`
- `0x18003720c`
- `0x180037b10`
- `0x1800394b0`
- `0x1800394dc`
- `0x1800397d0`
- `0x18003c0b8`
- `0x18003eda0`
- `0x1800466c0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180037bc2`
- `ntdll!NtQuerySystemInformation` at `0x180037bc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037e1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037e3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037e58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037e1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037e3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037e58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037e0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037e2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037e4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037e0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037e2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cda`

## string_xrefs

- `0x180037c49`: `GetSystemPartition`
- `0x180037c5f`: `systemPartitionNULL`
- `0x180037dfc`: `systemPartitionLength`
- `0x180037cef`: `hWinTrustDllNULL`
- `0x180037d4d`: `GetBootmgrPathInEFI`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsBootmgrInDBXRevocationList(unsigned __int8 *a1, unsigned int a2, int *a3, unsigned __int16 *a4)
{
  unsigned __int16 *v8; // rsi
  signed int SystemPartition; // ebx
  const unsigned __int16 *v10; // rdi
  NTSTATUS v11; // eax
  unsigned __int16 *v12; // r14
  unsigned __int64 v13; // rax
  unsigned int v14; // r11d
  HINSTANCE *v15; // rdx
  const unsigned __int16 *v16; // r8
  signed int LastError; // eax
  unsigned int v18; // r15d
  unsigned __int16 v19; // r13
  unsigned __int16 v20; // r12
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  struct _BOOTAPP_SVN *v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v28; // [rsp+38h] [rbp-C8h] BYREF
  struct _CRYPTOAPI_BLOB *v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v30; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  int *v33; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v34; // [rsp+68h] [rbp-98h]
  __int128 SystemInformation; // [rsp+70h] [rbp-90h] BYREF
  __int128 v36; // [rsp+80h] [rbp-80h]
  unsigned __int16 v37[264]; // [rsp+90h] [rbp-70h] BYREF

  v34 = a4;
  v33 = a3;
  v29 = 0;
  v27 = 0;
  lpMem = 0;
  v28 = 0;
  v26 = 0;
  v8 = 0;
  v30 = 0;
  memset_0(v37, 0, 0x208u);
  SystemInformation = 0;
  v36 = 0;
  v32 = 0;
  if ( !a3 )
  {
    SystemPartition = -2147024809;
    v10 = L"pbIsRevokedNULL";
LABEL_46:
    SBServicingLogMessage(
      (wchar_t *)L"IsBootmgrInDBXRevocationList failed with %x action:%ls",
      (unsigned int)SystemPartition,
      v10);
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"IsBootmgrInDBXRevocationList", v10);
    goto LABEL_47;
  }
  *a3 = 0;
  v11 = NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  SystemPartition = HResultFromNtStatus(v11);
  if ( SystemPartition < 0 )
  {
    v10 = L"NtQuerySystemInformation";
    goto LABEL_46;
  }
  if ( (_DWORD)v36 == 2 )
  {
    SystemPartition = SecureBootParseDBXFileContent(a1, a2, &v29, &v27, (struct _BOOTAPP_SVN *)&v26);
    if ( SystemPartition >= 0 )
    {
      if ( v27 )
      {
        SystemPartition = GetSystemPartition((unsigned __int16 **)&lpMem);
        v12 = (unsigned __int16 *)lpMem;
        if ( SystemPartition >= 0 )
        {
          if ( !lpMem )
          {
            SystemPartition = -2147467261;
            v10 = L"systemPartitionNULL";
            goto LABEL_40;
          }
          v13 = -1;
          do
            ++v13;
          while ( *((_WORD *)lpMem + v13) );
          if ( v13 <= 8 )
          {
            SystemPartition = -2147024809;
            v10 = L"systemPartitionLength";
          }
          else
          {
            v10 = L"Passed";
            SystemPartition = StringCchCopyW(v37, 0x104u, L"\\\\.\\");
            if ( SystemPartition >= 0 )
            {
              SystemPartition = StringCchCatW(v37, v14, v12 + 8);
              if ( SystemPartition >= 0 )
              {
                _AutoModulePtr::Bind((_AutoModulePtr *)&v32, v15, v16);
                if ( hWinTrustDll )
                {
                  SystemPartition = SearchRevokedBootmgr(v37, v29, v27, a3, a4);
                  if ( SystemPartition >= 0 )
                  {
                    v18 = HIWORD(v26);
                    if ( HIWORD(v26) )
                    {
                      SystemPartition = GetBootmgrPathInEFI(&v30);
                      v8 = v30;
                      if ( SystemPartition >= 0 )
                      {
                        if ( (unsigned int)BfspFileExists(v30) )
                        {
                          SystemPartition = GetBootmgrSVN(v8, &v28);
                          if ( SystemPartition >= 0 )
                          {
                            v19 = v28;
                            v20 = HIWORD(v28);
                            LODWORD(v25) = (unsigned __int16)v26;
                            SBServicingLogMessage(
                              (wchar_t *)L"BootMgrSVN.MajorSvn %hu dbxSVN.MajorSvn %hu BootMgrSVN.MinorSvn %hu dbxSVN.MinorSvn %hu",
                              HIWORD(v28),
                              v18,
                              (unsigned __int16)v28,
                              v25);
                            if ( v20 < (unsigned __int16)v18 || v19 < (unsigned __int16)v26 && v20 == (_WORD)v18 )
                            {
                              *v33 = 1;
                              if ( v34 )
                                StringCchCopyW(v34, 0x104u, v8);
                            }
                          }
                          else
                          {
                            v10 = L"GetBootmgrSVN";
                          }
                        }
                        else
                        {
                          SystemPartition = -2147024894;
                          v10 = L"BfspFileExists";
                        }
                      }
                      else
                      {
                        v10 = L"GetBootmgrPathInEFI";
                      }
                    }
                  }
                  else
                  {
                    v10 = L"SearchRevokedBootmgr";
                  }
                }
                else
                {
                  LastError = GetLastError();
                  SystemPartition = LastError;
                  if ( LastError > 0 )
                    SystemPartition = (unsigned __int16)LastError | 0x80070000;
                  v10 = L"hWinTrustDllNULL";
                }
              }
            }
          }
        }
        else
        {
          v10 = L"GetSystemPartition";
        }
        if ( v12 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v12);
        }
      }
      else
      {
        SystemPartition = -2147467259;
        v10 = L"HashBlobsCountZero";
      }
    }
    else
    {
      v10 = L"SecureBootParseDBXFileContent";
    }
LABEL_40:
    if ( v29 && v27 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v29);
    }
    if ( v8 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v8);
    }
    if ( SystemPartition < 0 )
      goto LABEL_46;
  }
LABEL_47:
  _AutoModulePtr::~_AutoModulePtr((_AutoModulePtr *)&v32);
  return (unsigned int)SystemPartition;
}

```

## disassembly

```asm
0x180037b10  push    rbp
0x180037b12  push    rbx
0x180037b13  push    rsi
0x180037b14  push    rdi
0x180037b15  push    r12
0x180037b17  push    r13
0x180037b19  push    r14
0x180037b1b  push    r15
0x180037b1d  lea     rbp, [rsp-1B8h]
0x180037b25  sub     rsp, 2B8h
0x180037b2c  mov     rax, cs:__security_cookie
0x180037b33  xor     rax, rsp
0x180037b36  mov     [rbp+1F0h+var_50], rax
0x180037b3d  mov     r12, r9
0x180037b40  mov     [rsp+2F0h+var_288], r9
0x180037b45  mov     r15, r8
0x180037b48  mov     [rsp+2F0h+var_290], r8
0x180037b4d  mov     r14d, edx
0x180037b50  mov     rdi, rcx
0x180037b53  xor     r13d, r13d
0x180037b56  mov     [rsp+2F0h+var_2B0], r13
0x180037b5b  mov     [rsp+2F0h+var_2BC], r13d
0x180037b60  mov     [rsp+2F0h+lpMem], r13
0x180037b65  mov     [rsp+2F0h+var_2B8], r13d
0x180037b6a  mov     [rsp+2F0h+var_2C0], r13d
0x180037b6f  mov     esi, r13d
0x180037b72  mov     [rsp+2F0h+var_2A8], r13
0x180037b77  xor     edx, edx; Val
0x180037b79  mov     r8d, 208h; Size
0x180037b7f  lea     rcx, [rbp+1F0h+var_260]; void *
0x180037b83  call    memset_0
0x180037b88  xorps   xmm0, xmm0
0x180037b8b  movups  [rsp+2F0h+SystemInformation], xmm0
0x180037b90  movups  [rbp+1F0h+var_270], xmm0
0x180037b94  mov     [rsp+2F0h+var_298], r13
0x180037b99  test    r15, r15
0x180037b9c  jnz     short loc_180037BAF
0x180037b9e  mov     ebx, 80070057h
0x180037ba3  lea     rdi, aPbisrevokednul; "pbIsRevokedNULL"
0x180037baa  jmp     loc_180037E62
0x180037baf  mov     [r15], r13d
0x180037bb2  xor     r9d, r9d; ReturnLength
0x180037bb5  lea     r8d, [r9+20h]; SystemInformationLength
0x180037bb9  lea     rdx, [rsp+2F0h+SystemInformation]; SystemInformation
0x180037bbe  lea     ecx, [r9+5Ah]; SystemInformationClass
0x180037bc2  call    cs:__imp_NtQuerySystemInformation
0x180037bc8  mov     ecx, eax; int
0x180037bca  call    ?HResultFromNtStatus@@YAJJ@Z; HResultFromNtStatus(long)
0x180037bcf  mov     ebx, eax
0x180037bd1  test    eax, eax
0x180037bd3  jns     short loc_180037BE1
0x180037bd5  lea     rdi, aNtquerysystemi; "NtQuerySystemInformation"
0x180037bdc  jmp     loc_180037E62
0x180037be1  cmp     dword ptr [rbp+1F0h+var_270], 2
0x180037be5  jnz     loc_180037E83
0x180037beb  lea     rax, [rsp+2F0h+var_2C0]
0x180037bf0  mov     [rsp+2F0h+var_2D0], rax; struct _BOOTAPP_SVN *
0x180037bf5  lea     r9, [rsp+2F0h+var_2BC]; unsigned int *
0x180037bfa  lea     r8, [rsp+2F0h+var_2B0]; struct _CRYPTOAPI_BLOB **
0x180037bff  mov     edx, r14d; unsigned int
0x180037c02  mov     rcx, rdi; unsigned __int8 *
0x180037c05  call    ?SecureBootParseDBXFileContent@@YAJPEAEKPEAPEAU_CRYPTOAPI_BLOB@@PEAKPEAU_BOOTAPP_SVN@@@Z; SecureBootParseDBXFileContent(uchar *,ulong,_CRYPTOAPI_BLOB * *,ulong *,_BOOTAPP_SVN *)
0x180037c0a  mov     ebx, eax
0x180037c0c  test    eax, eax
0x180037c0e  jns     short loc_180037C1C
0x180037c10  lea     rdi, aSecurebootpars; "SecureBootParseDBXFileContent"
0x180037c17  jmp     loc_180037E21
0x180037c1c  cmp     [rsp+2F0h+var_2BC], r13d
0x180037c21  ja      short loc_180037C34
0x180037c23  mov     ebx, 80004005h
0x180037c28  lea     rdi, aHashblobscount; "HashBlobsCountZero"
0x180037c2f  jmp     loc_180037E21
0x180037c34  lea     rcx, [rsp+2F0h+lpMem]; unsigned __int16 **
0x180037c39  call    ?GetSystemPartition@@YAJPEAPEAG@Z; GetSystemPartition(ushort * *)
0x180037c3e  mov     ebx, eax
0x180037c40  mov     r14, [rsp+2F0h+lpMem]
0x180037c45  test    eax, eax
0x180037c47  jns     short loc_180037C55
0x180037c49  lea     rdi, aGetsystemparti; "GetSystemPartition"
0x180037c50  jmp     loc_180037E08
0x180037c55  test    r14, r14
0x180037c58  jnz     short loc_180037C6B
0x180037c5a  mov     ebx, 80004003h
0x180037c5f  lea     rdi, aSystempartitio_1; "systemPartitionNULL"
0x180037c66  jmp     loc_180037E21
0x180037c6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037c6f  inc     rax
0x180037c72  cmp     [r14+rax*2], r13w
0x180037c77  jnz     short loc_180037C6F
0x180037c79  cmp     rax, 8
0x180037c7d  jbe     loc_180037DF7
0x180037c83  lea     rdi, aPassed; "Passed"
0x180037c8a  lea     r8, asc_18006FFE8; "\\\\.\\"
0x180037c91  mov     r11d, 104h
0x180037c97  mov     edx, r11d; unsigned __int64
0x180037c9a  lea     rcx, [rbp+1F0h+var_260]; unsigned __int16 *
0x180037c9e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037ca3  mov     ebx, eax
0x180037ca5  test    eax, eax
0x180037ca7  js      loc_180037E08
0x180037cad  lea     r8, [r14+10h]; unsigned __int16 *
0x180037cb1  mov     edx, r11d; unsigned __int64
0x180037cb4  lea     rcx, [rbp+1F0h+var_260]; unsigned __int16 *
0x180037cb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037cbd  mov     ebx, eax
0x180037cbf  test    eax, eax
0x180037cc1  js      loc_180037E08
0x180037cc7  lea     rcx, [rsp+2F0h+var_298]; this
0x180037ccc  call    ?Bind@_AutoModulePtr@@QEAAXAEAPEAUHINSTANCE__@@PEBG@Z; _AutoModulePtr::Bind(HINSTANCE__ * &,ushort const *)
0x180037cd1  cmp     cs:?hWinTrustDll@@3PEAUHINSTANCE__@@EA, r13; HINSTANCE__ * hWinTrustDll
0x180037cd8  jnz     short loc_180037CFB
0x180037cda  call    cs:__imp_GetLastError
0x180037ce0  mov     ebx, eax
0x180037ce2  test    eax, eax
0x180037ce4  jle     short loc_180037CEF
0x180037ce6  movzx   ebx, ax
0x180037ce9  or      ebx, 80070000h
0x180037cef  lea     rdi, aHwintrustdllnu; "hWinTrustDllNULL"
0x180037cf6  jmp     loc_180037E08
0x180037cfb  mov     [rsp+2F0h+var_2D0], r12; unsigned __int16 *
0x180037d00  mov     r9, r15; int *
0x180037d03  mov     r8d, [rsp+2F0h+var_2BC]; unsigned int
0x180037d08  mov     rdx, [rsp+2F0h+var_2B0]; struct _CRYPTOAPI_BLOB *
0x180037d0d  lea     rcx, [rbp+1F0h+var_260]; unsigned __int16 *
0x180037d11  call    ?SearchRevokedBootmgr@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@KPEAHPEAG@Z; SearchRevokedBootmgr(ushort const *,_CRYPTOAPI_BLOB *,ulong,int *,ushort *)
0x180037d16  mov     ebx, eax
0x180037d18  test    eax, eax
0x180037d1a  jns     short loc_180037D28
0x180037d1c  lea     rdi, aSearchrevokedb; "SearchRevokedBootmgr"
0x180037d23  jmp     loc_180037E08
0x180037d28  movzx   r15d, word ptr [rsp+2F0h+var_2C0+2]
0x180037d2e  test    r15w, r15w
0x180037d32  jz      loc_180037E08
0x180037d38  lea     rcx, [rsp+2F0h+var_2A8]; unsigned __int16 **
0x180037d3d  call    ?GetBootmgrPathInEFI@@YAJPEAPEAG@Z; GetBootmgrPathInEFI(ushort * *)
0x180037d42  mov     ebx, eax
0x180037d44  mov     rsi, [rsp+2F0h+var_2A8]
0x180037d49  test    eax, eax
0x180037d4b  jns     short loc_180037D59
0x180037d4d  lea     rdi, aGetbootmgrpath_0; "GetBootmgrPathInEFI"
0x180037d54  jmp     loc_180037E08
0x180037d59  mov     rcx, rsi
0x180037d5c  call    BfspFileExists
0x180037d61  test    eax, eax
0x180037d63  jnz     short loc_180037D76
0x180037d65  mov     ebx, 80070002h
0x180037d6a  lea     rdi, aBfspfileexists; "BfspFileExists"
0x180037d71  jmp     loc_180037E08
0x180037d76  lea     rdx, [rsp+2F0h+var_2B8]; unsigned int *
0x180037d7b  mov     rcx, rsi; unsigned __int16 *
0x180037d7e  call    ?GetBootmgrSVN@@YAJPEBGPEAI@Z; GetBootmgrSVN(ushort const *,uint *)
0x180037d83  mov     ebx, eax
0x180037d85  test    eax, eax
0x180037d87  jns     short loc_180037D92
0x180037d89  lea     rdi, aGetbootmgrsvn; "GetBootmgrSVN"
0x180037d90  jmp     short loc_180037E08
0x180037d92  movzx   r13d, word ptr [rsp+2F0h+var_2B8]
0x180037d98  movzx   r12d, word ptr [rsp+2F0h+var_2B8+2]
0x180037d9e  movzx   eax, word ptr [rsp+2F0h+var_2C0]
0x180037da3  mov     r9d, r13d
0x180037da6  mov     r8d, r15d
0x180037da9  mov     edx, r12d
0x180037dac  mov     dword ptr [rsp+2F0h+var_2D0], eax
0x180037db0  lea     rcx, aBootmgrsvnMajo; "BootMgrSVN.MajorSvn %hu dbxSVN.MajorSvn"...
0x180037db7  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180037dbc  cmp     r12w, r15w
0x180037dc0  jb      short loc_180037DD0
0x180037dc2  cmp     r13w, word ptr [rsp+2F0h+var_2C0]
0x180037dc8  jnb     short loc_180037E05
0x180037dca  cmp     r12w, r15w
0x180037dce  jnz     short loc_180037E05
0x180037dd0  mov     rax, [rsp+2F0h+var_290]
0x180037dd5  mov     dword ptr [rax], 1
0x180037ddb  mov     rcx, [rsp+2F0h+var_288]; unsigned __int16 *
0x180037de0  xor     r13d, r13d
0x180037de3  test    rcx, rcx
0x180037de6  jz      short loc_180037E08
0x180037de8  mov     r8, rsi; unsigned __int16 *
0x180037deb  mov     edx, 104h; unsigned __int64
0x180037df0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037df5  jmp     short loc_180037E08
0x180037df7  mov     ebx, 80070057h
0x180037dfc  lea     rdi, aSystempartitio_0; "systemPartitionLength"
0x180037e03  jmp     short loc_180037E08
0x180037e05  xor     r13d, r13d
0x180037e08  test    r14, r14
0x180037e0b  jz      short loc_180037E21
0x180037e0d  call    cs:__imp_GetProcessHeap
0x180037e13  mov     r8, r14; lpMem
0x180037e16  xor     edx, edx; dwFlags
0x180037e18  mov     rcx, rax; hHeap
0x180037e1b  call    cs:__imp_HeapFree
0x180037e21  cmp     [rsp+2F0h+var_2B0], r13
0x180037e26  jz      short loc_180037E45
0x180037e28  cmp     [rsp+2F0h+var_2BC], r13d
0x180037e2d  jbe     short loc_180037E45
0x180037e2f  call    cs:__imp_GetProcessHeap
0x180037e35  mov     r8, [rsp+2F0h+var_2B0]; lpMem
0x180037e3a  xor     edx, edx; dwFlags
0x180037e3c  mov     rcx, rax; hHeap
0x180037e3f  call    cs:__imp_HeapFree
0x180037e45  test    rsi, rsi
0x180037e48  jz      short loc_180037E5E
0x180037e4a  call    cs:__imp_GetProcessHeap
0x180037e50  mov     r8, rsi; lpMem
0x180037e53  xor     edx, edx; dwFlags
0x180037e55  mov     rcx, rax; hHeap
0x180037e58  call    cs:__imp_HeapFree
0x180037e5e  test    ebx, ebx
0x180037e60  jns     short loc_180037E83
0x180037e62  mov     r8, rdi
0x180037e65  mov     edx, ebx
0x180037e67  lea     rcx, aIsbootmgrindbx; "IsBootmgrInDBXRevocationList failed wit"...
0x180037e6e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180037e73  mov     rdx, rdi; unsigned __int16 *
0x180037e76  lea     rcx, aIsbootmgrindbx_0; "IsBootmgrInDBXRevocationList"
0x180037e7d  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x180037e82  nop
0x180037e83  lea     rcx, [rsp+2F0h+var_298]; this
0x180037e88  call    ??1_AutoModulePtr@@QEAA@XZ; _AutoModulePtr::~_AutoModulePtr(void)
0x180037e8d  mov     eax, ebx
0x180037e8f  mov     rcx, [rbp+1F0h+var_50]
0x180037e96  xor     rcx, rsp; StackCookie
0x180037e99  call    __security_check_cookie
0x180037e9e  add     rsp, 2B8h
0x180037ea5  pop     r15
0x180037ea7  pop     r14
0x180037ea9  pop     r13
0x180037eab  pop     r12
0x180037ead  pop     rdi
0x180037eae  pop     rsi
0x180037eaf  pop     rbx
0x180037eb0  pop     rbp
0x180037eb1  retn
```
