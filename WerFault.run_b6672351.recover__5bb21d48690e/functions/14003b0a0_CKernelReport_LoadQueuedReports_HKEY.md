# CKernelReport::LoadQueuedReports(HKEY__ *)

- ea: `0x14003b0a0`
- end: `0x14003b507`
- name: `?LoadQueuedReports@CKernelReport@@AEAAJPEAUHKEY__@@@Z`
- size: `1127`
- prototype: `int(CKernelReport *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003bbd4`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x14000ca20`
- `0x140010034`
- `0x1400372dc`
- `0x14003b0a0`
- `0x14003e0e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14003b224`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14003b224`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b135`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b135`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003b26d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003b47a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003b26d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003b47a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003b3f6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003b3f6`

## string_xrefs

- `0x14003b486`: `Invalid type found in the queue, entry deleted`
- `0x14003b28c`: `Minidump %ws does not exist, entry deleted`
- `0x14003b2de`: `Failed to copy the dump path in the list`
- `0x14003b30a`: `Read queued report: path: %ws`
- `0x14003b33f`: `Read queued report: creation time: %08X:%08X`
- `0x14003b3ca`: `Read queued report: report UUID: %08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x`

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
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-E8h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLena; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLenb; // [rsp+30h] [rbp-E0h]
  const char *lpcbMaxClassLenc; // [rsp+30h] [rbp-E0h]
  LPDWORD lpcValues; // [rsp+38h] [rbp-D8h]
  LPDWORD lpcValuesa; // [rsp+38h] [rbp-D8h]
  LPDWORD lpcbMaxValueNameLen; // [rsp+40h] [rbp-D0h]
  LPDWORD lpcbMaxValueLen; // [rsp+48h] [rbp-C8h]
  LPDWORD lpcbSecurityDescriptor; // [rsp+50h] [rbp-C0h]
  PFILETIME lpftLastWriteTime; // [rsp+58h] [rbp-B8h]
  __int64 v28; // [rsp+60h] [rbp-B0h]
  __int64 v29; // [rsp+68h] [rbp-A8h]
  __int64 v30; // [rsp+70h] [rbp-A0h]
  __int64 v31; // [rsp+78h] [rbp-98h]
  __int64 v32; // [rsp+80h] [rbp-90h]
  DWORD cchValueName; // [rsp+90h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+94h] [rbp-7Ch] BYREF
  DWORD cValues; // [rsp+98h] [rbp-78h] BYREF
  DWORD Type; // [rsp+9Ch] [rbp-74h] BYREF
  FILETIME FileTime2; // [rsp+A0h] [rbp-70h] BYREF
  CKernelReport *v38; // [rsp+A8h] [rbp-68h]
  HKEY v39; // [rsp+B0h] [rbp-60h]
  _BYTE v40[8]; // [rsp+B8h] [rbp-58h] BYREF
  _BYTE v41[16]; // [rsp+C0h] [rbp-50h] BYREF
  void *v42[2]; // [rsp+D0h] [rbp-40h] BYREF
  _WORD v43[8]; // [rsp+E0h] [rbp-30h] BYREF
  BYTE Data[16]; // [rsp+F0h] [rbp-20h] BYREF
  __int128 v45; // [rsp+100h] [rbp-10h]
  WCHAR ValueName[264]; // [rsp+110h] [rbp+0h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+368h] [rbp+258h]

  v2 = a2;
  v39 = a2;
  v38 = this;
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
    v6 = 666;
    goto LABEL_5;
  }
  v7 = cValues;
  if ( cValues )
  {
    FileTime2 = 0;
    while ( 1 )
    {
      cchValueName = 260;
      cbData = 28;
      v42[0] = v43;
      ValueName[0] = 0;
      v42[1] = v43;
      v43[0] = 0;
      --v7;
      *(_OWORD *)Data = 0;
      v45 = 0;
      if ( !RegEnumValueW(v2, v7, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
      {
        if ( Type != 3 || cchValueName > 0x105 || cbData != 28 )
        {
          RegDeleteValueW(v2, ValueName);
          v11 = 711;
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
                                  v42,
                                  ValueName) )
          {
            LODWORD(lpcSubKeysa) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2E0,
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
              (void *)0x2E3,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::LoadQueuedReports",
              lpcSubKeysb,
              (int)"Read queued report: creation time: %08X:%08X",
              lpcbMaxClassLenb,
              lpcValues);
            LODWORD(v32) = BYTE7(v45);
            LODWORD(v31) = BYTE6(v45);
            LODWORD(v30) = BYTE5(v45);
            LODWORD(v29) = BYTE4(v45);
            LODWORD(v28) = BYTE3(v45);
            LODWORD(lpftLastWriteTime) = BYTE2(v45);
            LODWORD(lpcbSecurityDescriptor) = BYTE1(v45);
            LODWORD(lpcbMaxValueLen) = (unsigned __int8)v45;
            LODWORD(lpcbMaxValueNameLen) = *(unsigned __int16 *)&Data[14];
            LODWORD(lpcValuesa) = *(unsigned __int16 *)&Data[12];
            LODWORD(lpcbMaxClassLenc) = *(_DWORD *)&Data[8];
            LODWORD(lpcSubKeysc) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x2EF,
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
              v28,
              v29,
              v30,
              v31,
              v32);
            v9 = (__int64 *)((char *)v38 + 656);
            if ( CompareFileTime((const FILETIME *)Data, &FileTime2) <= 0 )
            {
              if ( !*(_QWORD *)utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::insert(
                                 v9,
                                 v41,
                                 v9,
                                 v42) )
              {
                v11 = 774;
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
                                 v40,
                                 v10,
                                 v42) )
              {
                v11 = 765;
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
              (void *)0x2DB,
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
            (void *)0x2D1,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::LoadQueuedReports",
            lpcSubKeysa,
            (int)"Minidump %ws does not exist, entry deleted",
            (const char *)ValueName);
        }
      }
      if ( v42[0] != v43 )
        operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
      v2 = v39;
      if ( !v7 )
        return 0;
    }
  }
  v4 = -2147467259;
  v5 = "RegQueryInfoKey returned 0 values";
  v6 = 674;
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
0x14003b0a0  mov     [rsp-8+arg_10], rbx
0x14003b0a5  push    rbp
0x14003b0a6  push    rsi
0x14003b0a7  push    rdi
0x14003b0a8  push    r12
0x14003b0aa  push    r13
0x14003b0ac  push    r14
0x14003b0ae  push    r15
0x14003b0b0  lea     rbp, [rsp-220h]
0x14003b0b8  sub     rsp, 330h
0x14003b0bf  mov     rax, cs:__security_cookie
0x14003b0c6  xor     rax, rsp
0x14003b0c9  mov     [rbp+250h+var_40], rax
0x14003b0d0  mov     rdi, rdx
0x14003b0d3  mov     [rbp+250h+var_2B0], rdx
0x14003b0d7  mov     [rbp+250h+var_2B8], rcx
0x14003b0db  xor     edx, edx; Val
0x14003b0dd  lea     rcx, [rbp+250h+ValueName]; void *
0x14003b0e1  mov     r8d, 20Ah; Size
0x14003b0e7  call    memset_0
0x14003b0ec  xor     esi, esi
0x14003b0ee  lea     rax, [rbp+250h+cValues]
0x14003b0f2  mov     [rsp+360h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x14003b0f7  xor     r9d, r9d; lpReserved
0x14003b0fa  mov     [rsp+360h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x14003b0ff  xor     r8d, r8d; lpcchClass
0x14003b102  mov     [rsp+360h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x14003b107  xor     edx, edx; lpClass
0x14003b109  mov     [rsp+360h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x14003b10e  mov     rcx, rdi; hKey
0x14003b111  mov     [rsp+360h+lpcValues], rax; lpcValues
0x14003b116  mov     [rsp+360h+lpcbMaxClassLen], rsi; char *
0x14003b11b  mov     [rsp+360h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x14003b120  mov     [rsp+360h+lpcSubKeys], rsi; lpcSubKeys
0x14003b125  mov     [rbp+250h+cchValueName], esi
0x14003b128  mov     [rbp+250h+Type], esi
0x14003b12b  mov     [rbp+250h+cbData], esi
0x14003b12e  mov     qword ptr [rbp+250h+FileTime2.dwLowDateTime], rsi
0x14003b132  mov     [rbp+250h+cValues], esi
0x14003b135  call    cs:__imp_RegQueryInfoKeyW
0x14003b13c  nop     dword ptr [rax+rax+00h]
0x14003b141  mov     ebx, eax
0x14003b143  test    eax, eax
0x14003b145  jz      short loc_14003B186
0x14003b147  jle     short loc_14003B152
0x14003b149  movzx   ebx, ax
0x14003b14c  or      ebx, 80070000h
0x14003b152  lea     rax, aRegqueryinfoke; "RegQueryInfoKey failed."
0x14003b159  mov     edx, 29Ah; void *
0x14003b15e  mov     rcx, [rbp+258h]; this
0x14003b165  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003b16c  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; int
0x14003b171  lea     r9, aCkernelreportL; "CKernelReport::LoadQueuedReports"
0x14003b178  mov     dword ptr [rsp+360h+lpcSubKeys], ebx; wil::details *
0x14003b17c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b181  jmp     loc_14003B4DA
0x14003b186  mov     r13d, [rbp+250h+cValues]
0x14003b18a  test    r13d, r13d
0x14003b18d  jnz     short loc_14003B1A2
0x14003b18f  mov     ebx, 80004005h
0x14003b194  lea     rax, aRegqueryinfoke_0; "RegQueryInfoKey returned 0 values"
0x14003b19b  mov     edx, 2A2h
0x14003b1a0  jmp     short loc_14003B15E
0x14003b1a2  mov     qword ptr [rbp+250h+FileTime2.dwLowDateTime], rsi
0x14003b1a6  test    r13d, r13d
0x14003b1a9  jz      loc_14003B4D8
0x14003b1af  lea     r15, aCkernelreportL; "CKernelReport::LoadQueuedReports"
0x14003b1b6  mov     ebx, 80000000h
0x14003b1bb  lea     r12, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003b1c2  xorps   xmm0, xmm0
0x14003b1c5  mov     [rbp+250h+cchValueName], 104h
0x14003b1cc  lea     rax, [rbp+250h+var_280]
0x14003b1d0  mov     [rbp+250h+cbData], 1Ch
0x14003b1d7  mov     [rbp+250h+var_290], rax
0x14003b1db  lea     r9, [rbp+250h+cchValueName]; lpcchValueName
0x14003b1df  lea     rax, [rbp+250h+var_280]
0x14003b1e3  mov     [rbp+250h+ValueName], si
0x14003b1e7  mov     [rbp+250h+var_288], rax
0x14003b1eb  lea     r8, [rbp+250h+ValueName]; lpValueName
0x14003b1ef  lea     rax, [rbp+250h+cbData]
0x14003b1f3  mov     [rbp+250h+var_280], si
0x14003b1f7  mov     [rsp+360h+lpcValues], rax; lpcbData
0x14003b1fc  dec     r13d
0x14003b1ff  lea     rax, [rbp+250h+Data]
0x14003b203  mov     edx, r13d; dwIndex
0x14003b206  mov     [rsp+360h+lpcbMaxClassLen], rax; char *
0x14003b20b  mov     rcx, rdi; hKey
0x14003b20e  lea     rax, [rbp+250h+Type]
0x14003b212  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; lpType
0x14003b217  mov     [rsp+360h+lpcSubKeys], rsi; lpReserved
0x14003b21c  movups  xmmword ptr [rbp+250h+Data], xmm0
0x14003b220  movups  [rbp+250h+var_260], xmm0
0x14003b224  call    cs:__imp_RegEnumValueW
0x14003b22b  nop     dword ptr [rax+rax+00h]
0x14003b230  test    eax, eax
0x14003b232  jnz     loc_14003B4AD
0x14003b238  cmp     [rbp+250h+Type], 3
0x14003b23c  jnz     loc_14003B473
0x14003b242  cmp     [rbp+250h+cchValueName], 105h
0x14003b249  ja      loc_14003B473
0x14003b24f  cmp     [rbp+250h+cbData], 1Ch
0x14003b253  jnz     loc_14003B473
0x14003b259  lea     rcx, [rbp+250h+ValueName]; wchar_t *
0x14003b25d  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x14003b262  test    al, al
0x14003b264  jnz     short loc_14003B2AE
0x14003b266  lea     rdx, [rbp+250h+ValueName]; lpValueName
0x14003b26a  mov     rcx, rdi; hKey
0x14003b26d  call    cs:__imp_RegDeleteValueW
0x14003b274  nop     dword ptr [rax+rax+00h]
0x14003b279  mov     rcx, [rbp+258h]; this
0x14003b280  lea     rax, [rbp+250h+ValueName]
0x14003b284  mov     [rsp+360h+lpcbMaxClassLen], rax; char *
0x14003b289  mov     r9, r15; char *
0x14003b28c  lea     rax, aMinidumpWsDoes; "Minidump %ws does not exist, entry dele"...
0x14003b293  mov     r8, r12; unsigned int
0x14003b296  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; int
0x14003b29b  mov     edx, 2D1h; void *
0x14003b2a0  mov     dword ptr [rsp+360h+lpcSubKeys], ebx; wil::details *
0x14003b2a4  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b2a9  jmp     loc_14003B4AD
0x14003b2ae  lea     rax, [rbp+250h+ValueName]
0x14003b2b2  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003b2b6  inc     r8
0x14003b2b9  cmp     [rax+r8*2], si
0x14003b2be  jnz     short loc_14003B2B6
0x14003b2c0  lea     rdx, [rbp+250h+ValueName]
0x14003b2c4  lea     rcx, [rbp+250h+var_290]
0x14003b2c8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003b2cd  mov     rcx, [rbp+258h]; this
0x14003b2d4  mov     r9, r15; char *
0x14003b2d7  mov     r8, r12; unsigned int
0x14003b2da  test    al, al
0x14003b2dc  jnz     short loc_14003B2FC
0x14003b2de  lea     rax, aFailedToCopyTh; "Failed to copy the dump path in the lis"...
0x14003b2e5  mov     edx, 2DBh
0x14003b2ea  mov     [rsp+360h+lpcbMaxSubKeyLen], rax
0x14003b2ef  mov     dword ptr [rsp+360h+lpcSubKeys], 8007000Eh
0x14003b2f7  jmp     loc_14003B4A8
0x14003b2fc  lea     rax, [rbp+250h+ValueName]
0x14003b300  mov     edx, 2E0h; void *
0x14003b305  mov     [rsp+360h+lpcbMaxClassLen], rax; char *
0x14003b30a  lea     rax, aReadQueuedRepo_0; "Read queued report: path: %ws"
0x14003b311  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; int
0x14003b316  mov     dword ptr [rsp+360h+lpcSubKeys], ebx; wil::details *
0x14003b31a  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b31f  mov     eax, dword ptr [rbp+250h+Data]
0x14003b322  mov     r9, r15; char *
0x14003b325  mov     rcx, [rbp+258h]; this
0x14003b32c  mov     r8, r12; unsigned int
0x14003b32f  mov     dword ptr [rsp+360h+lpcValues], eax
0x14003b333  mov     edx, 2E3h; void *
0x14003b338  mov     eax, dword ptr [rbp+250h+Data+4]
0x14003b33b  mov     dword ptr [rsp+360h+lpcbMaxClassLen], eax; char *
0x14003b33f  lea     rax, aReadQueuedRepo; "Read queued report: creation time: %08X"...
0x14003b346  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; int
0x14003b34b  mov     dword ptr [rsp+360h+lpcSubKeys], ebx; wil::details *
0x14003b34f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b354  movzx   eax, byte ptr [rbp+250h+var_260+7]
0x14003b358  movzx   edx, byte ptr [rbp+250h+var_260+6]
0x14003b35c  movzx   r8d, byte ptr [rbp+250h+var_260+5]
0x14003b361  movzx   r9d, byte ptr [rbp+250h+var_260+4]
0x14003b366  movzx   r10d, byte ptr [rbp+250h+var_260+3]
0x14003b36b  movzx   r11d, byte ptr [rbp+250h+var_260+2]
0x14003b370  movzx   ebx, byte ptr [rbp+250h+var_260+1]
0x14003b374  movzx   edi, byte ptr [rbp+250h+var_260]
0x14003b378  movzx   esi, word ptr [rbp+250h+Data+0Eh]
0x14003b37c  movzx   r14d, word ptr [rbp+250h+Data+0Ch]
0x14003b381  mov     rcx, [rbp+258h]; this
0x14003b388  mov     [rsp+360h+var_2E0], eax
0x14003b38f  mov     eax, dword ptr [rbp+250h+Data+8]
0x14003b392  mov     dword ptr [rsp+360h+var_2E8], edx
0x14003b396  mov     edx, 2EFh; void *
0x14003b39b  mov     dword ptr [rsp+360h+var_2F0], r8d
0x14003b3a0  mov     r8, r12; unsigned int
0x14003b3a3  mov     dword ptr [rsp+360h+var_2F8], r9d
0x14003b3a8  mov     r9, r15; char *
0x14003b3ab  mov     dword ptr [rsp+360h+var_300], r10d
0x14003b3b0  mov     dword ptr [rsp+360h+lpftLastWriteTime], r11d
0x14003b3b5  mov     dword ptr [rsp+360h+lpcbSecurityDescriptor], ebx
0x14003b3b9  mov     dword ptr [rsp+360h+lpcbMaxValueLen], edi
0x14003b3bd  mov     dword ptr [rsp+360h+lpcbMaxValueNameLen], esi
0x14003b3c1  mov     dword ptr [rsp+360h+lpcValues], r14d
0x14003b3c6  mov     dword ptr [rsp+360h+lpcbMaxClassLen], eax; char *
0x14003b3ca  lea     rax, aReadQueuedRepo_1; "Read queued report: report UUID: %08x-%"...
0x14003b3d1  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; int
0x14003b3d6  mov     dword ptr [rsp+360h+lpcSubKeys], 80000000h; wil::details *
0x14003b3de  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b3e3  mov     rbx, [rbp+250h+var_2B8]
0x14003b3e7  lea     rdx, [rbp+250h+FileTime2]; lpFileTime2
0x14003b3eb  lea     rcx, [rbp+250h+Data]; lpFileTime1
0x14003b3ef  add     rbx, 290h
0x14003b3f6  call    cs:__imp_CompareFileTime
0x14003b3fd  nop     dword ptr [rax+rax+00h]
0x14003b402  xor     esi, esi
0x14003b404  lea     r9, [rbp+250h+var_290]
0x14003b408  mov     rcx, rbx
0x14003b40b  test    eax, eax
0x14003b40d  jle     short loc_14003B447
0x14003b40f  mov     rax, qword ptr [rbp+250h+Data]
0x14003b413  lea     rdx, [rbp+250h+var_2A8]
0x14003b417  mov     r8, [rbx]
0x14003b41a  mov     qword ptr [rbp+250h+FileTime2.dwLowDateTime], rax
0x14003b41e  call    ?insert@?$list@UKERNEL_QUEUED_REPORT@@V?$allocator@UKERNEL_QUEUED_REPORT@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@V?$_DlistConstIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@$$QEAUKERNEL_QUEUED_REPORT@@@Z; utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::insert(utl::_DlistConstIt<utl::_DlistNode<KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT &&)
0x14003b423  cmp     [rax], rsi
0x14003b426  jnz     loc_14003B4AD
0x14003b42c  lea     rax, aAddToHeadFaile; "Add to head failed"
0x14003b433  mov     edx, 2FDh
0x14003b438  mov     [rsp+360h+lpcbMaxSubKeyLen], rax
0x14003b43d  mov     dword ptr [rsp+360h+lpcSubKeys], 8007000Eh
0x14003b445  jmp     short loc_14003B49B
0x14003b447  mov     r8, rbx
0x14003b44a  lea     rdx, [rbp+250h+var_2A0]
0x14003b44e  call    ?insert@?$list@UKERNEL_QUEUED_REPORT@@V?$allocator@UKERNEL_QUEUED_REPORT@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@V?$_DlistConstIt@U?$_DlistNode@UKERNEL_QUEUED_REPORT@@@utl@@UKERNEL_QUEUED_REPORT@@@2@$$QEAUKERNEL_QUEUED_REPORT@@@Z; utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::insert(utl::_DlistConstIt<utl::_DlistNode<KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT>,KERNEL_QUEUED_REPORT &&)
0x14003b453  cmp     [rax], rsi
0x14003b456  jnz     short loc_14003B4AD
0x14003b458  lea     rax, aAddToTailFaile; "Add to tail failed"
0x14003b45f  mov     edx, 306h
0x14003b464  mov     [rsp+360h+lpcbMaxSubKeyLen], rax
0x14003b469  mov     dword ptr [rsp+360h+lpcSubKeys], 8007000Eh
0x14003b471  jmp     short loc_14003B49B
0x14003b473  lea     rdx, [rbp+250h+ValueName]; lpValueName
0x14003b477  mov     rcx, rdi; hKey
0x14003b47a  call    cs:__imp_RegDeleteValueW
0x14003b481  nop     dword ptr [rax+rax+00h]
0x14003b486  lea     rax, aInvalidTypeFou; "Invalid type found in the queue, entry "...
0x14003b48d  mov     edx, 2C7h; void *
0x14003b492  mov     [rsp+360h+lpcbMaxSubKeyLen], rax; int
0x14003b497  mov     dword ptr [rsp+360h+lpcSubKeys], ebx; wil::details *
0x14003b49b  mov     rcx, [rbp+258h]; this
0x14003b4a2  mov     r9, r15; char *
0x14003b4a5  mov     r8, r12; unsigned int
0x14003b4a8  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003b4ad  mov     rcx, [rbp+250h+var_290]; void *
0x14003b4b1  lea     rax, [rbp+250h+var_280]
0x14003b4b5  cmp     rcx, rax
0x14003b4b8  jz      short loc_14003B4C6
0x14003b4ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003b4c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003b4c6  mov     rdi, [rbp+250h+var_2B0]
0x14003b4ca  mov     ebx, 80000000h
0x14003b4cf  test    r13d, r13d
0x14003b4d2  jnz     loc_14003B1C2
0x14003b4d8  mov     ebx, esi
0x14003b4da  mov     eax, ebx
0x14003b4dc  mov     rcx, [rbp+250h+var_40]
0x14003b4e3  xor     rcx, rsp; StackCookie
0x14003b4e6  call    __security_check_cookie
0x14003b4eb  mov     rbx, [rsp+360h+arg_10]
0x14003b4f3  add     rsp, 330h
0x14003b4fa  pop     r15
0x14003b4fc  pop     r14
0x14003b4fe  pop     r13
0x14003b500  pop     r12
0x14003b502  pop     rdi
0x14003b503  pop     rsi
0x14003b504  pop     rbp
0x14003b505  retn
```
