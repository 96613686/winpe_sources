# CKernelReport::LoadQueuedReports(HKEY__ *)

- ea: `0x140038af0`
- end: `0x140038fca`
- name: `?LoadQueuedReports@CKernelReport@@AEAAJPEAUHKEY__@@@Z`
- size: `1242`
- prototype: `__int64 __fastcall(CKernelReport *this, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140039614`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x14000c8a0`
- `0x14000fa08`
- `0x140034d9c`
- `0x140038af0`
- `0x14003b828`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140038c75`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140038c75`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140038b85`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140038b85`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140038cb8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140038f48`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140038cb8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140038f48`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140038ece`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140038ece`

## string_xrefs

- `0x140038f4e`: `Invalid type found in the queue, entry deleted`
- `0x140038cd1`: `Minidump %ws does not exist, entry deleted`
- `0x140038d24`: `Failed to copy the dump path in the list`
- `0x140038d50`: `Read queued report: path: %ws`
- `0x140038d86`: `Read queued report: creation time: %08X:%08X`
- `0x140038e18`: `Read queued report: report UUID: %08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x`
- `0x140038e47`: `Read queued report: IptEnabled: 0x%x`
- `0x140038e76`: `Read queued report: BootId: 0x%x`
- `0x140038ea5`: `Read queued report: DumpType: 0x%x`

## pseudocode

```c
__int64 __fastcall CKernelReport::LoadQueuedReports(CKernelReport *this, HKEY a2)
{
  HKEY v2; // rdi
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  const char *v5; // rax
  __int64 v6; // rdx
  DWORD v7; // r13d
  __int64 v8; // r8
  __int64 *v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rdx
  wil::details *lpcSubKeys; // [rsp+20h] [rbp-F0h]
  wil::details *lpcSubKeysa; // [rsp+20h] [rbp-F0h]
  wil::details *lpcSubKeysb; // [rsp+20h] [rbp-F0h]
  wil::details *lpcSubKeysc; // [rsp+20h] [rbp-F0h]
  wil::details *lpcSubKeysd; // [rsp+20h] [rbp-F0h]
  wil::details *lpcSubKeyse; // [rsp+20h] [rbp-F0h]
  wil::details *lpcSubKeysf; // [rsp+20h] [rbp-F0h]
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-E8h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLena; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLenb; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLenc; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLend; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLene; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLenf; // [rsp+30h] [rbp-E0h]
  LPDWORD lpcValues; // [rsp+38h] [rbp-D8h]
  LPDWORD lpcValuesa; // [rsp+38h] [rbp-D8h]
  LPDWORD lpcbMaxValueNameLen; // [rsp+40h] [rbp-D0h]
  LPDWORD lpcbMaxValueLen; // [rsp+48h] [rbp-C8h]
  LPDWORD lpcbSecurityDescriptor; // [rsp+50h] [rbp-C0h]
  PFILETIME lpftLastWriteTime; // [rsp+58h] [rbp-B8h]
  __int64 v34; // [rsp+60h] [rbp-B0h]
  __int64 v35; // [rsp+68h] [rbp-A8h]
  __int64 v36; // [rsp+70h] [rbp-A0h]
  __int64 v37; // [rsp+78h] [rbp-98h]
  __int64 v38; // [rsp+80h] [rbp-90h]
  DWORD cchValueName; // [rsp+90h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+94h] [rbp-7Ch] BYREF
  DWORD cValues; // [rsp+98h] [rbp-78h] BYREF
  DWORD Type; // [rsp+9Ch] [rbp-74h] BYREF
  FILETIME FileTime2; // [rsp+A0h] [rbp-70h] BYREF
  CKernelReport *v44; // [rsp+A8h] [rbp-68h]
  HKEY v45; // [rsp+B0h] [rbp-60h]
  _BYTE v46[8]; // [rsp+B8h] [rbp-58h] BYREF
  _BYTE v47[16]; // [rsp+C0h] [rbp-50h] BYREF
  void *v48[2]; // [rsp+D0h] [rbp-40h] BYREF
  _WORD v49[8]; // [rsp+E0h] [rbp-30h] BYREF
  BYTE Data[16]; // [rsp+F0h] [rbp-20h] BYREF
  char *v51[2]; // [rsp+100h] [rbp-10h]
  char *v52; // [rsp+110h] [rbp+0h]
  WCHAR ValueName[264]; // [rsp+120h] [rbp+10h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+378h] [rbp+268h]

  v2 = a2;
  v45 = a2;
  v44 = this;
  memset_0(ValueName, 0, 0x20Au);
  cchValueName = 0;
  Type = 0;
  cbData = 0;
  FileTime2 = 0;
  cValues = 0;
  v3 = RegQueryInfoKeyW(v2, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = "RegQueryInfoKey failed.";
    v6 = 665;
    goto LABEL_5;
  }
  v7 = cValues;
  if ( cValues )
  {
    FileTime2 = 0;
    while ( 1 )
    {
      cchValueName = 260;
      cbData = 36;
      v48[0] = v49;
      ValueName[0] = 0;
      v48[1] = v49;
      v49[0] = 0;
      v52 = 0;
      --v7;
      *(_OWORD *)Data = 0;
      *(_OWORD *)v51 = 0;
      if ( !RegEnumValueW(v2, v7, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
      {
        if ( Type != 3 || cchValueName > 0x105 || cbData != 36 )
        {
          RegDeleteValueW(v2, ValueName);
          v11 = 710;
          lpcbMaxSubKeyLen = "Invalid type found in the queue, entry deleted";
          LODWORD(lpcSubKeysa) = 0x80000000;
          goto LABEL_25;
        }
        if ( UtilFileExists(ValueName) )
        {
          v8 = -1;
          do
            ++v8;
          while ( ValueName[v8] );
          if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                  v48,
                                  ValueName,
                                  v8) )
          {
            LODWORD(lpcSubKeysa) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2DF,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeysa,
              (int)"Read queued report: path: %ws",
              (const char *)ValueName);
            LODWORD(lpcValues) = *(_DWORD *)Data;
            LODWORD(lpcbMaxClassLenb) = *(_DWORD *)&Data[4];
            LODWORD(lpcSubKeysb) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2E2,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeysb,
              (int)"Read queued report: creation time: %08X:%08X",
              lpcbMaxClassLenb,
              lpcValues);
            LODWORD(v38) = HIBYTE(v51[0]);
            LODWORD(v37) = BYTE6(v51[0]);
            LODWORD(v36) = BYTE5(v51[0]);
            LODWORD(v35) = BYTE4(v51[0]);
            LODWORD(v34) = BYTE3(v51[0]);
            LODWORD(lpftLastWriteTime) = BYTE2(v51[0]);
            LODWORD(lpcbSecurityDescriptor) = BYTE1(v51[0]);
            LODWORD(lpcbMaxValueLen) = LOBYTE(v51[0]);
            LODWORD(lpcbMaxValueNameLen) = *(unsigned __int16 *)&Data[14];
            LODWORD(lpcValuesa) = *(unsigned __int16 *)&Data[12];
            LODWORD(lpcbMaxClassLenc) = *(_DWORD *)&Data[8];
            LODWORD(lpcSubKeysc) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2EE,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeysc,
              (int)"Read queued report: report UUID: %08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
              lpcbMaxClassLenc,
              lpcValuesa,
              lpcbMaxValueNameLen,
              lpcbMaxValueLen,
              lpcbSecurityDescriptor,
              lpftLastWriteTime,
              v34,
              v35,
              v36,
              v37,
              v38);
            LODWORD(lpcbMaxClassLend) = v51[1];
            LODWORD(lpcSubKeysd) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2EF,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeysd,
              (int)"Read queued report: IptEnabled: 0x%x",
              lpcbMaxClassLend);
            LODWORD(lpcbMaxClassLene) = HIDWORD(v51[1]);
            LODWORD(lpcSubKeyse) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2F0,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeyse,
              (int)"Read queued report: BootId: 0x%x",
              lpcbMaxClassLene);
            LODWORD(lpcbMaxClassLenf) = (_DWORD)v52;
            LODWORD(lpcSubKeysf) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2F1,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeysf,
              (int)"Read queued report: DumpType: 0x%x",
              lpcbMaxClassLenf);
            v9 = (__int64 *)((char *)v44 + 656);
            if ( CompareFileTime((const FILETIME *)Data, &FileTime2) <= 0 )
            {
              if ( !*(_QWORD *)utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::insert(
                                 v9,
                                 v47,
                                 v9,
                                 v48) )
              {
                v11 = 776;
                lpcbMaxSubKeyLen = "Add to tail failed";
                LODWORD(lpcSubKeysa) = -2147024882;
                goto LABEL_25;
              }
            }
            else
            {
              v10 = *v9;
              FileTime2 = *(FILETIME *)Data;
              if ( !*(_QWORD *)utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::insert(
                                 v9,
                                 v46,
                                 v10,
                                 v48) )
              {
                v11 = 767;
                lpcbMaxSubKeyLen = "Add to head failed";
                LODWORD(lpcSubKeysa) = -2147024882;
LABEL_25:
                wil::details::in1diag4::Log_HrMsg(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                  "CKernelReport::LoadQueuedReports",
                  lpcSubKeysa,
                  (int)lpcbMaxSubKeyLen,
                  lpcbMaxClassLena);
              }
            }
          }
          else
          {
            LODWORD(lpcSubKeysa) = -2147024882;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2DA,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeysa,
              (int)"Failed to copy the dump path in the list",
              lpcbMaxClassLena);
          }
        }
        else
        {
          RegDeleteValueW(v2, ValueName);
          LODWORD(lpcSubKeysa) = 0x80000000;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x2D0,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::LoadQueuedReports",
            lpcSubKeysa,
            (int)"Minidump %ws does not exist, entry deleted",
            (const char *)ValueName);
        }
      }
      if ( v48[0] != v49 )
        operator delete(v48[0], (const struct std::nothrow_t *)&std::nothrow);
      v2 = v45;
      if ( !v7 )
        return 0;
    }
  }
  v4 = -2147467259;
  v5 = "RegQueryInfoKey returned 0 values";
  v6 = 673;
LABEL_5:
  LODWORD(lpcSubKeys) = v4;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::LoadQueuedReports",
    lpcSubKeys,
    (int)v5,
    lpcbMaxClassLen);
  return v4;
}

```

## disassembly

```asm
0x140038af0  mov     [rsp-8+arg_10], rbx
0x140038af5  push    rbp
0x140038af6  push    rsi
0x140038af7  push    rdi
0x140038af8  push    r12
0x140038afa  push    r13
0x140038afc  push    r14
0x140038afe  push    r15
0x140038b00  lea     rbp, [rsp-230h]
0x140038b08  sub     rsp, 340h
0x140038b0f  mov     rax, cs:__security_cookie
0x140038b16  xor     rax, rsp
0x140038b19  mov     [rbp+260h+var_40], rax
0x140038b20  mov     rdi, rdx
0x140038b23  mov     [rbp+260h+var_2C0], rdx
0x140038b27  mov     [rbp+260h+var_2C8], rcx
0x140038b2b  xor     edx, edx; Val
0x140038b2d  lea     rcx, [rbp+260h+ValueName]; void *
0x140038b31  mov     r8d, 20Ah; Size
0x140038b37  call    memset_0
0x140038b3c  xor     esi, esi
0x140038b3e  lea     rax, [rbp+260h+cValues]
0x140038b42  mov     [rsp+370h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x140038b47  xor     r9d, r9d; lpReserved
0x140038b4a  mov     [rsp+370h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x140038b4f  xor     r8d, r8d; lpcchClass
0x140038b52  mov     [rsp+370h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x140038b57  xor     edx, edx; lpClass
0x140038b59  mov     [rsp+370h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x140038b5e  mov     rcx, rdi; hKey
0x140038b61  mov     [rsp+370h+lpcValues], rax; lpcValues
0x140038b66  mov     [rsp+370h+lpcbMaxClassLen], rsi; char *
0x140038b6b  mov     [rsp+370h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x140038b70  mov     [rsp+370h+lpcSubKeys], rsi; lpcSubKeys
0x140038b75  mov     [rbp+260h+cchValueName], esi
0x140038b78  mov     [rbp+260h+Type], esi
0x140038b7b  mov     [rbp+260h+cbData], esi
0x140038b7e  mov     qword ptr [rbp+260h+FileTime2.dwLowDateTime], rsi
0x140038b82  mov     [rbp+260h+cValues], esi
0x140038b85  call    cs:__imp_RegQueryInfoKeyW
0x140038b8b  mov     ebx, eax
0x140038b8d  test    eax, eax
0x140038b8f  jz      short loc_140038BD0
0x140038b91  jle     short loc_140038B9C
0x140038b93  movzx   ebx, ax
0x140038b96  or      ebx, 80070000h
0x140038b9c  lea     rax, aRegqueryinfoke; "RegQueryInfoKey failed."
0x140038ba3  mov     edx, 299h; void *
0x140038ba8  mov     rcx, [rbp+268h]; this
0x140038baf  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038bb6  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038bbb  lea     r9, aCkernelreportL; "CKernelReport::LoadQueuedReports"
0x140038bc2  mov     dword ptr [rsp+370h+lpcSubKeys], ebx; wil::details *
0x140038bc6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038bcb  jmp     loc_140038F9E
0x140038bd0  mov     r13d, [rbp+260h+cValues]
0x140038bd4  test    r13d, r13d
0x140038bd7  jnz     short loc_140038BEC
0x140038bd9  mov     ebx, 80004005h
0x140038bde  lea     rax, aRegqueryinfoke_0; "RegQueryInfoKey returned 0 values"
0x140038be5  mov     edx, 2A1h
0x140038bea  jmp     short loc_140038BA8
0x140038bec  mov     qword ptr [rbp+260h+FileTime2.dwLowDateTime], rsi
0x140038bf0  test    r13d, r13d
0x140038bf3  jz      loc_140038F9C
0x140038bf9  lea     r15, aCkernelreportL; "CKernelReport::LoadQueuedReports"
0x140038c00  mov     r14d, 80000000h
0x140038c06  lea     r12, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038c0d  xorps   xmm0, xmm0
0x140038c10  mov     [rbp+260h+cchValueName], 104h
0x140038c17  lea     rax, [rbp+260h+var_290]
0x140038c1b  mov     [rbp+260h+cbData], 24h ; '$'
0x140038c22  mov     [rbp+260h+var_2A0], rax
0x140038c26  lea     r9, [rbp+260h+cchValueName]; lpcchValueName
0x140038c2a  lea     rax, [rbp+260h+var_290]
0x140038c2e  mov     [rbp+260h+ValueName], si
0x140038c32  mov     [rbp+260h+var_298], rax
0x140038c36  lea     r8, [rbp+260h+ValueName]; lpValueName
0x140038c3a  xor     eax, eax
0x140038c3c  mov     [rbp+260h+var_290], si
0x140038c40  mov     [rbp+260h+var_260], rax
0x140038c44  dec     r13d
0x140038c47  lea     rax, [rbp+260h+cbData]
0x140038c4b  mov     edx, r13d; dwIndex
0x140038c4e  mov     [rsp+370h+lpcValues], rax; lpcbData
0x140038c53  mov     rcx, rdi; hKey
0x140038c56  lea     rax, [rbp+260h+Data]
0x140038c5a  mov     [rsp+370h+lpcbMaxClassLen], rax; char *
0x140038c5f  lea     rax, [rbp+260h+Type]
0x140038c63  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; lpType
0x140038c68  mov     [rsp+370h+lpcSubKeys], rsi; lpReserved
0x140038c6d  movups  xmmword ptr [rbp+260h+Data], xmm0
0x140038c71  movups  xmmword ptr [rbp+260h+var_270], xmm0
0x140038c75  call    cs:__imp_RegEnumValueW
0x140038c7b  test    eax, eax
0x140038c7d  jnz     loc_140038F76
0x140038c83  cmp     [rbp+260h+Type], 3
0x140038c87  jnz     loc_140038F41
0x140038c8d  cmp     [rbp+260h+cchValueName], 105h
0x140038c94  ja      loc_140038F41
0x140038c9a  cmp     [rbp+260h+cbData], 24h ; '$'
0x140038c9e  jnz     loc_140038F41
0x140038ca4  lea     rcx, [rbp+260h+ValueName]; wchar_t *
0x140038ca8  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x140038cad  test    al, al
0x140038caf  jnz     short loc_140038CF4
0x140038cb1  lea     rdx, [rbp+260h+ValueName]; lpValueName
0x140038cb5  mov     rcx, rdi; hKey
0x140038cb8  call    cs:__imp_RegDeleteValueW
0x140038cbe  mov     rcx, [rbp+268h]; this
0x140038cc5  lea     rax, [rbp+260h+ValueName]
0x140038cc9  mov     [rsp+370h+lpcbMaxClassLen], rax; char *
0x140038cce  mov     r9, r15; char *
0x140038cd1  lea     rax, aMinidumpWsDoes; "Minidump %ws does not exist, entry dele"...
0x140038cd8  mov     r8, r12; unsigned int
0x140038cdb  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038ce0  mov     edx, 2D0h; void *
0x140038ce5  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038cea  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038cef  jmp     loc_140038F76
0x140038cf4  lea     rax, [rbp+260h+ValueName]
0x140038cf8  or      r8, 0FFFFFFFFFFFFFFFFh
0x140038cfc  inc     r8
0x140038cff  cmp     [rax+r8*2], si
0x140038d04  jnz     short loc_140038CFC
0x140038d06  lea     rdx, [rbp+260h+ValueName]
0x140038d0a  lea     rcx, [rbp+260h+var_2A0]
0x140038d0e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140038d13  mov     rcx, [rbp+268h]; this
0x140038d1a  mov     r9, r15; char *
0x140038d1d  mov     r8, r12; unsigned int
0x140038d20  test    al, al
0x140038d22  jnz     short loc_140038D42
0x140038d24  lea     rax, aFailedToCopyTh; "Failed to copy the dump path in the lis"...
0x140038d2b  mov     edx, 2DAh
0x140038d30  mov     [rsp+370h+lpcbMaxSubKeyLen], rax
0x140038d35  mov     dword ptr [rsp+370h+lpcSubKeys], 8007000Eh
0x140038d3d  jmp     loc_140038F71
0x140038d42  lea     rax, [rbp+260h+ValueName]
0x140038d46  mov     edx, 2DFh; void *
0x140038d4b  mov     [rsp+370h+lpcbMaxClassLen], rax; char *
0x140038d50  lea     rax, aReadQueuedRepo_1; "Read queued report: path: %ws"
0x140038d57  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038d5c  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038d61  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038d66  mov     eax, dword ptr [rbp+260h+Data]
0x140038d69  mov     r9, r15; char *
0x140038d6c  mov     rcx, [rbp+268h]; this
0x140038d73  mov     r8, r12; unsigned int
0x140038d76  mov     dword ptr [rsp+370h+lpcValues], eax
0x140038d7a  mov     edx, 2E2h; void *
0x140038d7f  mov     eax, dword ptr [rbp+260h+Data+4]
0x140038d82  mov     dword ptr [rsp+370h+lpcbMaxClassLen], eax; char *
0x140038d86  lea     rax, aReadQueuedRepo; "Read queued report: creation time: %08X"...
0x140038d8d  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038d92  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038d97  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038d9c  movzx   eax, byte ptr [rbp+260h+var_270+7]
0x140038da0  movzx   edx, byte ptr [rbp+260h+var_270+6]
0x140038da4  movzx   r8d, byte ptr [rbp+260h+var_270+5]
0x140038da9  movzx   r9d, byte ptr [rbp+260h+var_270+4]
0x140038dae  movzx   r14d, word ptr [rbp+260h+Data+0Ch]
0x140038db3  movzx   r10d, byte ptr [rbp+260h+var_270+3]
0x140038db8  movzx   r11d, byte ptr [rbp+260h+var_270+2]
0x140038dbd  movzx   ebx, byte ptr [rbp+260h+var_270+1]
0x140038dc1  movzx   edi, byte ptr [rbp+260h+var_270]
0x140038dc5  movzx   esi, word ptr [rbp+260h+Data+0Eh]
0x140038dc9  mov     rcx, [rbp+268h]; this
0x140038dd0  mov     [rsp+370h+var_2F0], eax
0x140038dd7  mov     eax, dword ptr [rbp+260h+Data+8]
0x140038dda  mov     dword ptr [rsp+370h+var_2F8], edx
0x140038dde  mov     edx, 2EEh; void *
0x140038de3  mov     dword ptr [rsp+370h+var_300], r8d
0x140038de8  mov     r8, r12; unsigned int
0x140038deb  mov     dword ptr [rsp+370h+var_308], r9d
0x140038df0  mov     r9, r15; char *
0x140038df3  mov     dword ptr [rsp+370h+var_310], r10d
0x140038df8  mov     dword ptr [rsp+370h+lpftLastWriteTime], r11d
0x140038dfd  mov     dword ptr [rsp+370h+lpcbSecurityDescriptor], ebx
0x140038e01  mov     dword ptr [rsp+370h+lpcbMaxValueLen], edi
0x140038e05  mov     dword ptr [rsp+370h+lpcbMaxValueNameLen], esi
0x140038e09  mov     dword ptr [rsp+370h+lpcValues], r14d
0x140038e0e  mov     r14d, 80000000h
0x140038e14  mov     dword ptr [rsp+370h+lpcbMaxClassLen], eax; char *
0x140038e18  lea     rax, aReadQueuedRepo_2; "Read queued report: report UUID: %08x-%"...
0x140038e1f  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038e24  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038e29  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038e2e  mov     eax, dword ptr [rbp+260h+var_270+8]
0x140038e31  mov     r9, r15; char *
0x140038e34  mov     rcx, [rbp+268h]; this
0x140038e3b  mov     r8, r12; unsigned int
0x140038e3e  mov     dword ptr [rsp+370h+lpcbMaxClassLen], eax; char *
0x140038e42  mov     edx, 2EFh; void *
0x140038e47  lea     rax, aReadQueuedRepo_4; "Read queued report: IptEnabled: 0x%x"
0x140038e4e  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038e53  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038e58  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038e5d  mov     eax, dword ptr [rbp+260h+var_270+0Ch]
0x140038e60  mov     r9, r15; char *
0x140038e63  mov     rcx, [rbp+268h]; this
0x140038e6a  mov     r8, r12; unsigned int
0x140038e6d  mov     dword ptr [rsp+370h+lpcbMaxClassLen], eax; char *
0x140038e71  mov     edx, 2F0h; void *
0x140038e76  lea     rax, aReadQueuedRepo_0; "Read queued report: BootId: 0x%x"
0x140038e7d  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038e82  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038e87  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038e8c  mov     eax, dword ptr [rbp+260h+var_260]
0x140038e8f  mov     r9, r15; char *
0x140038e92  mov     rcx, [rbp+268h]; this
0x140038e99  mov     r8, r12; unsigned int
0x140038e9c  mov     dword ptr [rsp+370h+lpcbMaxClassLen], eax; char *
0x140038ea0  mov     edx, 2F1h; void *
0x140038ea5  lea     rax, aReadQueuedRepo_3; "Read queued report: DumpType: 0x%x"
0x140038eac  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038eb1  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038eb6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038ebb  mov     rbx, [rbp+260h+var_2C8]
0x140038ebf  lea     rdx, [rbp+260h+FileTime2]; lpFileTime2
0x140038ec3  add     rbx, 290h
0x140038eca  lea     rcx, [rbp+260h+Data]; lpFileTime1
0x140038ece  call    cs:__imp_CompareFileTime
0x140038ed4  xor     esi, esi
0x140038ed6  lea     r9, [rbp+260h+var_2A0]
0x140038eda  mov     rcx, rbx
0x140038edd  test    eax, eax
0x140038edf  jle     short loc_140038F15
0x140038ee1  mov     rax, qword ptr [rbp+260h+Data]
0x140038ee5  lea     rdx, [rbp+260h+var_2B8]
0x140038ee9  mov     r8, [rbx]
0x140038eec  mov     qword ptr [rbp+260h+FileTime2.dwLowDateTime], rax
0x140038ef0  call    ?insert@?$list@UKERNEL_QUEUED_REPORT@@V?$allocator@UKERNEL_QUEUED_REPORT@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@V?$_DlistConstIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@$$QEAUKERNEL_QUEUED_REPORT@@@Z; utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::insert(utl::_DlistConstIt<utl::_DlistNode<KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT &&)
0x140038ef5  cmp     [rax], rsi
0x140038ef8  jnz     short loc_140038F76
0x140038efa  lea     rax, aAddToHeadFaile; "Add to head failed"
0x140038f01  mov     edx, 2FFh
0x140038f06  mov     [rsp+370h+lpcbMaxSubKeyLen], rax
0x140038f0b  mov     dword ptr [rsp+370h+lpcSubKeys], 8007000Eh
0x140038f13  jmp     short loc_140038F64
0x140038f15  mov     r8, rbx
0x140038f18  lea     rdx, [rbp+260h+var_2B0]
0x140038f1c  call    ?insert@?$list@UKERNEL_QUEUED_REPORT@@V?$allocator@UKERNEL_QUEUED_REPORT@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@V?$_DlistConstIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@$$QEAUKERNEL_QUEUED_REPORT@@@Z; utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::insert(utl::_DlistConstIt<utl::_DlistNode<KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT &&)
0x140038f21  cmp     [rax], rsi
0x140038f24  jnz     short loc_140038F76
0x140038f26  lea     rax, aAddToTailFaile; "Add to tail failed"
0x140038f2d  mov     edx, 308h
0x140038f32  mov     [rsp+370h+lpcbMaxSubKeyLen], rax
0x140038f37  mov     dword ptr [rsp+370h+lpcSubKeys], 8007000Eh
0x140038f3f  jmp     short loc_140038F64
0x140038f41  lea     rdx, [rbp+260h+ValueName]; lpValueName
0x140038f45  mov     rcx, rdi; hKey
0x140038f48  call    cs:__imp_RegDeleteValueW
0x140038f4e  lea     rax, aInvalidTypeFou; "Invalid type found in the queue, entry "...
0x140038f55  mov     edx, 2C6h; void *
0x140038f5a  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; int
0x140038f5f  mov     dword ptr [rsp+370h+lpcSubKeys], r14d; wil::details *
0x140038f64  mov     rcx, [rbp+268h]; this
0x140038f6b  mov     r9, r15; char *
0x140038f6e  mov     r8, r12; unsigned int
0x140038f71  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038f76  mov     rcx, [rbp+260h+var_2A0]; void *
0x140038f7a  lea     rax, [rbp+260h+var_290]
0x140038f7e  cmp     rcx, rax
0x140038f81  jz      short loc_140038F8F
0x140038f83  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140038f8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140038f8f  mov     rdi, [rbp+260h+var_2C0]
0x140038f93  test    r13d, r13d
0x140038f96  jnz     loc_140038C0D
0x140038f9c  mov     ebx, esi
0x140038f9e  mov     eax, ebx
0x140038fa0  mov     rcx, [rbp+260h+var_40]
0x140038fa7  xor     rcx, rsp; StackCookie
0x140038faa  call    __security_check_cookie
0x140038faf  mov     rbx, [rsp+370h+arg_10]
0x140038fb7  add     rsp, 340h
0x140038fbe  pop     r15
0x140038fc0  pop     r14
0x140038fc2  pop     r13
0x140038fc4  pop     r12
0x140038fc6  pop     rdi
0x140038fc7  pop     rsi
0x140038fc8  pop     rbp
0x140038fc9  retn
```
