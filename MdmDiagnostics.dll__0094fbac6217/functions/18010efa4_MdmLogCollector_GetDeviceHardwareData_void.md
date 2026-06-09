# MdmLogCollector::GetDeviceHardwareData(void)

- ea: `0x18010efa4`
- end: `0x18010f488`
- name: `?GetDeviceHardwareData@MdmLogCollector@@AEAAJXZ`
- size: `1252`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x18001981c`
- `0x18001a0a0`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800e7aa8`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x1800f9534`
- `0x1800f9558`
- `0x18010440c`
- `0x180107e60`
- `0x1801089c0`
- `0x18010efa4`
- `0x18010f704`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010f0a7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010f0a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010f223`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010f223`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010f3de`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010f3de`
- `OLEAUT32!__imp_VariantInit` at `0x18010f0d1`
- `OLEAUT32!__imp_VariantInit` at `0x18010f0d1`
- `OLEAUT32!__imp_VariantClear` at `0x18010f13c`
- `OLEAUT32!__imp_VariantClear` at `0x18010f426`
- `OLEAUT32!__imp_VariantClear` at `0x18010f13c`
- `OLEAUT32!__imp_VariantClear` at `0x18010f426`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010f112`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010f112`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010f316`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010f38f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010f316`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010f38f`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18010f284`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18010f284`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18010eff8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18010eff8`

## string_xrefs

- `0x18010f006`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f06a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f126`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f23b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f32e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f3a5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f3ec`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MdmLogCollector::GetDeviceHardwareData(MdmLogCollector *this)
{
  const char *v2; // r9
  __int64 v4; // rcx
  int TemporaryOutputPath; // eax
  unsigned int LastError; // ebx
  const WCHAR *v7; // rax
  __int64 v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  LPVOID v12; // rbx
  __int64 (__fastcall *v13)(LPVOID, const wchar_t *, __int64 *); // rdi
  __int64 v14; // rcx
  const WCHAR *v15; // rax
  HANDLE FileW; // rbx
  const char *v17; // r9
  const WCHAR *v18; // rdx
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  int v21; // esi
  unsigned __int16 *v22; // rdi
  const WCHAR *v23; // rax
  int v24; // eax
  const char *v25; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  LPVOID v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v32; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v34; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  DWORD nSize; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v38[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v39[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v40[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v41[32]; // [rsp+108h] [rbp+8h] BYREF
  WCHAR Buffer[8]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v43; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  wprintf(L"Collecting hardware hash information.\n");
  *(_OWORD *)Buffer = 0;
  v43 = 0;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6C7,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
             v2);
  std::wstring::wstring(v39, L"\\DeviceHash_");
  std::wstring::append(v39, Buffer);
  std::wstring::append(v39, L".csv");
  std::wstring::wstring(v41);
  TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v4, v41);
  LastError = TemporaryOutputPath;
  if ( TemporaryOutputPath >= 0 )
  {
    std::wstring::wstring(v37, v41);
    std::wstring::append(v37, v39);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
    DeleteFileW(v7);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
    MdmLogCollector::AddEntry(v8, (__int64 *)this + 4);
    v31 = 0;
    VariantInit(&pvarg);
    v30 = 0;
    v9 = CoCreateInstance(
           &GUID_66d0db14_5638_475f_a386_629522d8c461,
           0,
           1u,
           &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
           &v30);
    LastError = v9;
    if ( v9 >= 0 )
    {
      v12 = v30;
      v13 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v30 + 80LL);
      v14 = v31;
      v31 = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v9 = v13(v12, L"./DevDetail/Ext/DeviceHardwareData", &v31);
      LastError = v9;
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v31 + 104LL))(v31, &pvarg);
        LastError = v9;
        if ( v9 >= 0 )
        {
          if ( pvarg.vt == 8 )
          {
            v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
            FileW = CreateFileW(v15, 0x10000000u, 0, 0, 2u, 0, 0);
            v34 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x6F1,
                            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                            v17);
            }
            else
            {
              std::wstring::wstring(v38, L"Device Serial Number,Windows Product ID,Hardware Hash\r\n");
              v32 = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v32,
                0);
              if ( (int)DmGetSmbiosSerialNumber(&v32) < 0 )
              {
                v18 = &Name;
              }
              else
              {
                v18 = v32;
                v32 = 0;
              }
              std::wstring::wstring(v40, v18);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
              std::wstring::append(v38, v40);
              std::wstring::_Tidy_deallocate(v40);
              std::wstring::append(v38, L",,");
              std::wstring::append(v38, pvarg.llVal);
              v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
              v20 = WideCharToMultiByte(0xFDE9u, 0, v19, -1, 0, 0, 0, 0);
              v21 = v20;
              if ( v20 )
              {
                v22 = (unsigned __int16 *)operator new[](v20, (const struct std::nothrow_t *)std::nothrow);
                v32 = v22;
                v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
                v24 = WideCharToMultiByte(0xFDE9u, 0, v23, -1, (LPSTR)v22, v21, 0, 0);
                if ( v24 )
                {
                  NumberOfBytesWritten = 0;
                  if ( WriteFile(FileW, v22, v24 - 1, &NumberOfBytesWritten, 0) )
                  {
                    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v32);
                    std::wstring::_Tidy_deallocate(v38);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
                    VariantClear(&pvarg);
                    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v30);
                    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v31);
                    std::wstring::_Tidy_deallocate(v37);
                    LastError = 0;
                    goto LABEL_33;
                  }
                  LastError = wil::details::in1diag3::Return_GetLastError(
                                retaddr,
                                (void *)0x707,
                                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                                v25);
                }
                else
                {
                  LastError = -2147418113;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x700,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                    (const char *)0x8000FFFFLL,
                    ppvc);
                }
                std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v32);
              }
              else
              {
                LastError = -2147418113;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x6FB,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                  (const char *)0x8000FFFFLL,
                  ppvb);
              }
              std::wstring::_Tidy_deallocate(v38);
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
            goto LABEL_9;
          }
          LastError = -2147418113;
          v11 = 2147549183LL;
          v10 = 1766;
LABEL_8:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
            (const char *)v11,
            ppva);
LABEL_9:
          VariantClear(&pvarg);
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v30);
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v31);
          std::wstring::_Tidy_deallocate(v37);
          goto LABEL_33;
        }
        v10 = 1765;
      }
      else
      {
        v10 = 1764;
      }
    }
    else
    {
      v10 = 1763;
    }
    v11 = (unsigned int)v9;
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6CE,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
    (const char *)(unsigned int)TemporaryOutputPath,
    ppv);
LABEL_33:
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v39);
  return LastError;
}

```

## disassembly

```asm
0x18010efa4  mov     [rsp-8+arg_8], rbx
0x18010efa9  mov     [rsp-8+arg_10], rsi
0x18010efae  push    rbp
0x18010efaf  push    rdi
0x18010efb0  push    r14
0x18010efb2  lea     rbp, [rsp-50h]
0x18010efb7  sub     rsp, 150h
0x18010efbe  mov     rax, cs:__security_cookie
0x18010efc5  xor     rax, rsp
0x18010efc8  mov     [rbp+60h+var_18], rax
0x18010efcc  mov     rdi, rcx
0x18010efcf  xor     r14d, r14d
0x18010efd2  lea     rcx, aCollectingHard; "Collecting hardware hash information.\n"
0x18010efd9  call    wprintf
0x18010efde  xorps   xmm0, xmm0
0x18010efe1  movups  xmmword ptr [rbp+60h+Buffer], xmm0
0x18010efe5  movups  [rbp+60h+var_28], xmm0
0x18010efe9  mov     [rbp+60h+nSize], 10h
0x18010eff0  lea     rdx, [rbp+60h+nSize]; nSize
0x18010eff4  lea     rcx, [rbp+60h+Buffer]; lpBuffer
0x18010eff8  call    cs:__imp_GetComputerNameW
0x18010effe  test    eax, eax
0x18010f000  jnz     short loc_18010F01C
0x18010f002  mov     rcx, [rbp+68h]; this
0x18010f006  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f00d  mov     edx, 6C7h; void *
0x18010f012  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010f017  jmp     loc_18010F464
0x18010f01c  lea     rdx, aDevicehash; "\\DeviceHash_"
0x18010f023  lea     rcx, [rbp+60h+var_98]
0x18010f027  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f02c  nop
0x18010f02d  lea     rdx, [rbp+60h+Buffer]
0x18010f031  lea     rcx, [rbp+60h+var_98]
0x18010f035  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010f03a  lea     rdx, aCsv; ".csv"
0x18010f041  lea     rcx, [rbp+60h+var_98]
0x18010f045  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010f04a  lea     rcx, [rbp+60h+var_58]
0x18010f04e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010f053  nop
0x18010f054  lea     rdx, [rbp+60h+var_58]
0x18010f058  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010f05d  mov     ebx, eax
0x18010f05f  test    eax, eax
0x18010f061  jns     short loc_18010F080
0x18010f063  mov     rcx, [rbp+68h]; this
0x18010f067  mov     r9d, eax; char *
0x18010f06a  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f071  mov     edx, 6CEh; void *
0x18010f076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f07b  jmp     loc_18010F44F
0x18010f080  lea     rdx, [rbp+60h+var_58]
0x18010f084  lea     rcx, [rbp+60h+var_D8]
0x18010f088  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010f08d  nop
0x18010f08e  lea     rdx, [rbp+60h+var_98]
0x18010f092  lea     rcx, [rbp+60h+var_D8]
0x18010f096  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18010f09b  lea     rcx, [rbp+60h+var_D8]
0x18010f09f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f0a4  mov     rcx, rax; lpFileName
0x18010f0a7  call    cs:__imp_DeleteFileW
0x18010f0ad  lea     rcx, [rbp+60h+var_D8]
0x18010f0b1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f0b6  mov     rcx, rax
0x18010f0b9  lea     rdx, [rdi+20h]
0x18010f0bd  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x18010f0c2  mov     [rsp+160h+var_118], r14
0x18010f0c7  mov     [rsp+160h+var_120], r14
0x18010f0cc  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18010f0d1  call    cs:__imp_VariantInit
0x18010f0d7  nop
0x18010f0d8  mov     rcx, [rsp+160h+var_120]
0x18010f0dd  mov     [rsp+160h+var_120], r14
0x18010f0e2  test    rcx, rcx
0x18010f0e5  jz      short loc_18010F0F4
0x18010f0e7  mov     rax, [rcx]
0x18010f0ea  mov     rax, [rax+10h]
0x18010f0ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f0f3  nop
0x18010f0f4  lea     rax, [rsp+160h+var_120]
0x18010f0f9  mov     [rsp+160h+ppv], rax; int
0x18010f0fe  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18010f105  xor     edx, edx; pUnkOuter
0x18010f107  lea     r8d, [rdx+1]; dwClsContext
0x18010f10b  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18010f112  call    cs:__imp_CoCreateInstance
0x18010f118  mov     ebx, eax
0x18010f11a  test    eax, eax
0x18010f11c  jns     short loc_18010F167
0x18010f11e  mov     edx, 6E3h; void *
0x18010f123  mov     r9d, eax; char *
0x18010f126  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f12d  mov     rcx, [rbp+68h]; this
0x18010f131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f136  nop
0x18010f137  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18010f13c  call    cs:__imp_VariantClear
0x18010f142  nop
0x18010f143  lea     rcx, [rsp+160h+var_120]
0x18010f148  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010f14d  nop
0x18010f14e  lea     rcx, [rsp+160h+var_118]
0x18010f153  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010f158  nop
0x18010f159  lea     rcx, [rbp+60h+var_D8]
0x18010f15d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f162  jmp     loc_18010F44F
0x18010f167  mov     rbx, [rsp+160h+var_120]
0x18010f16c  mov     rax, [rbx]
0x18010f16f  mov     rdi, [rax+50h]
0x18010f173  mov     rcx, [rsp+160h+var_118]
0x18010f178  mov     [rsp+160h+var_118], r14
0x18010f17d  test    rcx, rcx
0x18010f180  jz      short loc_18010F18F
0x18010f182  mov     rdx, [rcx]
0x18010f185  mov     rax, [rdx+10h]
0x18010f189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f18e  nop
0x18010f18f  lea     r8, [rsp+160h+var_118]
0x18010f194  lea     rdx, aDevdetailExtDe; "./DevDetail/Ext/DeviceHardwareData"
0x18010f19b  mov     rcx, rbx
0x18010f19e  mov     rax, rdi
0x18010f1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f1a6  mov     ebx, eax
0x18010f1a8  test    eax, eax
0x18010f1aa  jns     short loc_18010F1B6
0x18010f1ac  mov     edx, 6E4h
0x18010f1b1  jmp     loc_18010F123
0x18010f1b6  mov     rcx, [rsp+160h+var_118]
0x18010f1bb  mov     rax, [rcx]
0x18010f1be  lea     rdx, [rsp+160h+pvarg]
0x18010f1c3  mov     rax, [rax+68h]
0x18010f1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f1cc  mov     ebx, eax
0x18010f1ce  test    eax, eax
0x18010f1d0  jns     short loc_18010F1DC
0x18010f1d2  mov     edx, 6E5h
0x18010f1d7  jmp     loc_18010F123
0x18010f1dc  mov     eax, 8
0x18010f1e1  cmp     ax, word ptr [rsp+160h+pvarg]
0x18010f1e6  jz      short loc_18010F1FA
0x18010f1e8  mov     ebx, 8000FFFFh
0x18010f1ed  mov     r9d, ebx
0x18010f1f0  mov     edx, 6E6h
0x18010f1f5  jmp     loc_18010F126
0x18010f1fa  lea     rcx, [rbp+60h+var_D8]
0x18010f1fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f203  mov     rcx, rax; lpFileName
0x18010f206  mov     [rsp+160h+hTemplateFile], r14; hTemplateFile
0x18010f20b  mov     [rsp+160h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18010f210  mov     dword ptr [rsp+160h+ppv], 2; dwCreationDisposition
0x18010f218  xor     r9d, r9d; lpSecurityAttributes
0x18010f21b  xor     r8d, r8d; dwShareMode
0x18010f21e  mov     edx, 10000000h; dwDesiredAccess
0x18010f223  call    cs:__imp_CreateFileW
0x18010f229  mov     rbx, rax
0x18010f22c  mov     [rsp+160h+var_100], rax
0x18010f231  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010f235  jnz     short loc_18010F25D
0x18010f237  mov     rcx, [rbp+68h]; this
0x18010f23b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f242  mov     edx, 6F1h; void *
0x18010f247  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010f24c  mov     ebx, eax
0x18010f24e  lea     rcx, [rsp+160h+var_100]
0x18010f253  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010f258  jmp     loc_18010F137
0x18010f25d  lea     rdx, aDeviceSerialNu; "Device Serial Number,Windows Product ID"...
0x18010f264  lea     rcx, [rbp+60h+var_B8]
0x18010f268  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f26d  nop
0x18010f26e  mov     [rsp+160h+var_110], r14
0x18010f273  xor     edx, edx
0x18010f275  lea     rcx, [rsp+160h+var_110]
0x18010f27a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010f27f  lea     rcx, [rsp+160h+var_110]
0x18010f284  call    cs:__imp_?DmGetSmbiosSerialNumber@@YAJPEAPEAG@Z; DmGetSmbiosSerialNumber(ushort * *)
0x18010f28a  lea     rcx, [rbp+60h+var_78]
0x18010f28e  test    eax, eax
0x18010f290  js      short loc_18010F29E
0x18010f292  mov     rdx, [rsp+160h+var_110]
0x18010f297  mov     [rsp+160h+var_110], r14
0x18010f29c  jmp     short loc_18010F2A5
0x18010f29e  lea     rdx, Name
0x18010f2a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f2aa  nop
0x18010f2ab  lea     rcx, [rsp+160h+var_110]
0x18010f2b0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010f2b5  nop
0x18010f2b6  lea     rdx, [rbp+60h+var_78]
0x18010f2ba  lea     rcx, [rbp+60h+var_B8]
0x18010f2be  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18010f2c3  nop
0x18010f2c4  lea     rcx, [rbp+60h+var_78]
0x18010f2c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f2cd  lea     rdx, asc_1801D29E4; ",,"
0x18010f2d4  lea     rcx, [rbp+60h+var_B8]
0x18010f2d8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010f2dd  mov     rdx, qword ptr [rsp+160h+pvarg+8]
0x18010f2e2  lea     rcx, [rbp+60h+var_B8]
0x18010f2e6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010f2eb  lea     rcx, [rbp+60h+var_B8]
0x18010f2ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f2f4  mov     r8, rax; lpWideCharStr
0x18010f2f7  mov     [rsp+160h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18010f2fc  mov     [rsp+160h+hTemplateFile], r14; lpDefaultChar
0x18010f301  mov     [rsp+160h+dwFlagsAndAttributes], r14d; cbMultiByte
0x18010f306  mov     [rsp+160h+ppv], r14; int
0x18010f30b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18010f30f  xor     edx, edx; dwFlags
0x18010f311  mov     ecx, 0FDE9h; CodePage
0x18010f316  call    cs:__imp_WideCharToMultiByte
0x18010f31c  mov     esi, eax
0x18010f31e  test    eax, eax
0x18010f320  jnz     short loc_18010F34E
0x18010f322  mov     rcx, [rbp+68h]; this
0x18010f326  mov     ebx, 8000FFFFh
0x18010f32b  mov     r9d, ebx; char *
0x18010f32e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f335  mov     edx, 6FBh; void *
0x18010f33a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f33f  nop
0x18010f340  lea     rcx, [rbp+60h+var_B8]
0x18010f344  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f349  jmp     loc_18010F24E
0x18010f34e  mov     rcx, rsi; unsigned __int64
0x18010f351  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010f358  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18010f35d  mov     rdi, rax
0x18010f360  mov     [rsp+160h+var_110], rax
0x18010f365  lea     rcx, [rbp+60h+var_B8]
0x18010f369  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f36e  mov     r8, rax; lpWideCharStr
0x18010f371  mov     [rsp+160h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18010f376  mov     [rsp+160h+hTemplateFile], r14; lpDefaultChar
0x18010f37b  mov     [rsp+160h+dwFlagsAndAttributes], esi; cbMultiByte
0x18010f37f  mov     [rsp+160h+ppv], rdi; int
0x18010f384  or      r9d, 0FFFFFFFFh; cchWideChar
0x18010f388  xor     edx, edx; dwFlags
0x18010f38a  mov     ecx, 0FDE9h; CodePage
0x18010f38f  call    cs:__imp_WideCharToMultiByte
0x18010f395  test    eax, eax
0x18010f397  jnz     short loc_18010F3C5
0x18010f399  mov     rcx, [rbp+68h]; this
0x18010f39d  mov     ebx, 8000FFFFh
0x18010f3a2  mov     r9d, ebx; char *
0x18010f3a5  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f3ac  mov     edx, 700h; void *
0x18010f3b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f3b6  lea     rcx, [rsp+160h+var_110]
0x18010f3bb  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010f3c0  jmp     loc_18010F340
0x18010f3c5  mov     [rsp+160h+NumberOfBytesWritten], r14d
0x18010f3ca  lea     r8d, [rax-1]; nNumberOfBytesToWrite
0x18010f3ce  mov     [rsp+160h+ppv], r14; lpOverlapped
0x18010f3d3  lea     r9, [rsp+160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18010f3d8  mov     rdx, rdi; lpBuffer
0x18010f3db  mov     rcx, rbx; hFile
0x18010f3de  call    cs:__imp_WriteFile
0x18010f3e4  test    eax, eax
0x18010f3e6  jnz     short loc_18010F401
0x18010f3e8  mov     rcx, [rbp+68h]; this
0x18010f3ec  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f3f3  mov     edx, 707h; void *
0x18010f3f8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010f3fd  mov     ebx, eax
0x18010f3ff  jmp     short loc_18010F3B6
0x18010f401  lea     rcx, [rsp+160h+var_110]
0x18010f406  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010f40b  nop
0x18010f40c  lea     rcx, [rbp+60h+var_B8]
0x18010f410  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f415  nop
0x18010f416  lea     rcx, [rsp+160h+var_100]
0x18010f41b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010f420  nop
0x18010f421  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18010f426  call    cs:__imp_VariantClear
0x18010f42c  nop
0x18010f42d  lea     rcx, [rsp+160h+var_120]
0x18010f432  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010f437  nop
0x18010f438  lea     rcx, [rsp+160h+var_118]
0x18010f43d  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010f442  nop
0x18010f443  lea     rcx, [rbp+60h+var_D8]
0x18010f447  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f44c  mov     ebx, r14d
0x18010f44f  lea     rcx, [rbp+60h+var_58]
0x18010f453  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f458  nop
0x18010f459  lea     rcx, [rbp+60h+var_98]
0x18010f45d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f462  mov     eax, ebx
0x18010f464  mov     rcx, [rbp+60h+var_18]
0x18010f468  xor     rcx, rsp; StackCookie
0x18010f46b  call    __security_check_cookie
0x18010f470  lea     r11, [rsp+160h+var_10]
  ... truncated ...
```
