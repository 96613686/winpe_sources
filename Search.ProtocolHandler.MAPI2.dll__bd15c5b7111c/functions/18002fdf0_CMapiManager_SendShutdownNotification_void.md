# CMapiManager::SendShutdownNotification(void)

- ea: `0x18002fdf0`
- end: `0x18002ff70`
- name: `?SendShutdownNotification@CMapiManager@@AEAAXXZ`
- size: `384`
- prototype: `void __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002f9cc`

## callees

- `0x18000ad14`
- `0x18000ebac`
- `0x18000fd58`
- `0x180011884`
- `0x1800122d8`
- `0x180013c20`
- `0x180025768`
- `0x18002beb0`
- `0x18002ce28`
- `0x18002fdf0`
- `0x18003f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002fe91`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fe9c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff35`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fe91`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fe9c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ff35`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fe34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fe34`

## string_xrefs

- `0x18002fea4`: `CMapiManager::SendShutdownNotification failed to create gather notify`

## pseudocode

```c
void __fastcall CMapiManager::SendShutdownNotification(CMapiManager *this)
{
  HRESULT v1; // eax
  int v2; // ebx
  const wchar_t **URL; // rax
  OLECHAR *v4; // rbx
  __int128 v5; // [rsp+30h] [rbp-29h] BYREF
  __int64 v6; // [rsp+40h] [rbp-19h]
  _BYTE v7[40]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v8[56]; // [rsp+78h] [rbp+1Fh] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+67h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp+6Fh] BYREF
  BSTR v11; // [rsp+D0h] [rbp+77h] BYREF

  if ( *((_DWORD *)this + 42) )
  {
    ppv = 0;
    v1 = CoCreateInstance(
           &GUID_9e175b6d_f52a_11d8_b9a5_505054503030,
           0,
           0x15u,
           &GUID_b05651f9_9b10_425e_b616_1fcd828db3b1,
           &ppv);
    v2 = v1;
    if ( v1 < 0 )
    {
      CLogger::Error(v1, L"CMapiManager::SendShutdownNotification failed to create gather notify");
    }
    else
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v11, L"Windows");
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SystemIndex");
      v5 = 0;
      v6 = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR, __int128 *))(*(_QWORD *)ppv + 56LL))(
             ppv,
             v11,
             bstrString,
             &v5);
      SysFreeString(bstrString);
      SysFreeString(v11);
    }
    if ( v2 < 0 )
    {
      CLogger::Error(v2, L"CMapiManager::SendShutdownNotification failed to initialize gather notify");
    }
    else
    {
      CMapiUrl::CMapiUrl((CMapiUrl *)v7);
      ATL::CSimpleStringT<wchar_t,0>::SetString(v8, L"private", 7);
      CMapiUrl::SetStore((CMapiUrl *)v7, L"MAPIPH-Shutdown-Notify");
      URL = (const wchar_t **)CMapiUrl::GetURL(v7, &bstrString);
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v11, *URL);
      ATL::CStringData::Release((ATL::CStringData *)(bstrString - 12));
      v4 = v11;
      (*(void (__fastcall **)(LPVOID, __int64, BSTR, BSTR))(*(_QWORD *)ppv + 80LL))(ppv, 8388610, v11, v11);
      SysFreeString(v4);
      CMapiUrl::~CMapiUrl((CMapiUrl *)v7);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  }
}

```

## disassembly

```asm
0x18002fdf0  mov     [rsp-8+arg_18], rbx
0x18002fdf5  push    rbp
0x18002fdf6  lea     rbp, [rsp-57h]
0x18002fdfb  sub     rsp, 0B0h
0x18002fe02  cmp     dword ptr [rcx+0A8h], 0
0x18002fe09  jz      loc_18002FF5F
0x18002fe0f  mov     [rbp+57h+arg_0], 0
0x18002fe17  lea     rax, [rbp+57h+arg_0]
0x18002fe1b  mov     [rsp+0B0h+ppv], rax; ppv
0x18002fe20  lea     r9, _GUID_b05651f9_9b10_425e_b616_1fcd828db3b1; riid
0x18002fe27  xor     edx, edx; pUnkOuter
0x18002fe29  lea     r8d, [rdx+15h]; dwClsContext
0x18002fe2d  lea     rcx, _GUID_9e175b6d_f52a_11d8_b9a5_505054503030; rclsid
0x18002fe34  call    cs:__imp_CoCreateInstance
0x18002fe3a  mov     ebx, eax
0x18002fe3c  test    eax, eax
0x18002fe3e  js      short loc_18002FEA4
0x18002fe40  lea     rdx, aWindows; "Windows"
0x18002fe47  lea     rcx, [rbp+57h+arg_10]; this
0x18002fe4b  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x18002fe50  nop
0x18002fe51  lea     rdx, aSystemindex; "SystemIndex"
0x18002fe58  lea     rcx, [rbp+57h+bstrString]; this
0x18002fe5c  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x18002fe61  nop
0x18002fe62  xorps   xmm0, xmm0
0x18002fe65  xor     eax, eax
0x18002fe67  mov     rcx, [rbp+57h+arg_0]
0x18002fe6b  movaps  [rbp+57h+var_80], xmm0
0x18002fe6f  mov     [rbp+57h+var_70], rax
0x18002fe73  mov     rax, [rcx]
0x18002fe76  lea     r9, [rbp+57h+var_80]
0x18002fe7a  mov     r8, [rbp+57h+bstrString]
0x18002fe7e  mov     rdx, [rbp+57h+arg_10]
0x18002fe82  mov     rax, [rax+38h]
0x18002fe86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe8b  mov     ebx, eax
0x18002fe8d  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002fe91  call    cs:__imp_SysFreeString
0x18002fe97  nop
0x18002fe98  mov     rcx, [rbp+57h+arg_10]; bstrString
0x18002fe9c  call    cs:__imp_SysFreeString
0x18002fea2  jmp     short loc_18002FEB2
0x18002fea4  lea     rdx, aCmapimanagerSe; "CMapiManager::SendShutdownNotification "...
0x18002feab  mov     ecx, eax; int
0x18002fead  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002feb2  test    ebx, ebx
0x18002feb4  js      loc_18002FF47
0x18002feba  lea     rcx, [rbp+57h+var_60]; this
0x18002febe  call    ??0CMapiUrl@@QEAA@XZ; CMapiUrl::CMapiUrl(void)
0x18002fec3  nop
0x18002fec4  mov     r8d, 7
0x18002feca  lea     rdx, aPrivate; "private"
0x18002fed1  lea     rcx, [rbp+57h+var_38]
0x18002fed5  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002feda  lea     rdx, aMapiphShutdown; "MAPIPH-Shutdown-Notify"
0x18002fee1  lea     rcx, [rbp+57h+var_60]; this
0x18002fee5  call    ?SetStore@CMapiUrl@@QEAAXPEB_W@Z; CMapiUrl::SetStore(wchar_t const *)
0x18002feea  lea     rdx, [rbp+57h+bstrString]
0x18002feee  lea     rcx, [rbp+57h+var_60]
0x18002fef2  call    ?GetURL@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::GetURL(void)
0x18002fef7  nop
0x18002fef8  mov     rdx, [rax]; wchar_t *
0x18002fefb  lea     rcx, [rbp+57h+arg_10]; this
0x18002feff  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x18002ff04  nop
0x18002ff05  mov     rcx, [rbp+57h+bstrString]
0x18002ff09  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002ff0d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002ff12  mov     rcx, [rbp+57h+arg_0]
0x18002ff16  mov     rax, [rcx]
0x18002ff19  mov     rbx, [rbp+57h+arg_10]
0x18002ff1d  mov     r9, rbx
0x18002ff20  mov     r8, rbx
0x18002ff23  mov     edx, 800002h
0x18002ff28  mov     rax, [rax+50h]
0x18002ff2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff31  nop
0x18002ff32  mov     rcx, rbx; bstrString
0x18002ff35  call    cs:__imp_SysFreeString
0x18002ff3b  nop
0x18002ff3c  lea     rcx, [rbp+57h+var_60]; this
0x18002ff40  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18002ff45  jmp     short loc_18002FF56
0x18002ff47  lea     rdx, aCmapimanagerSe_0; "CMapiManager::SendShutdownNotification "...
0x18002ff4e  mov     ecx, ebx; int
0x18002ff50  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002ff55  nop
0x18002ff56  lea     rcx, [rbp+57h+arg_0]
0x18002ff5a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ff5f  mov     rbx, [rsp+0B0h+arg_18]
0x18002ff67  add     rsp, 0B0h
0x18002ff6e  pop     rbp
0x18002ff6f  retn
```
