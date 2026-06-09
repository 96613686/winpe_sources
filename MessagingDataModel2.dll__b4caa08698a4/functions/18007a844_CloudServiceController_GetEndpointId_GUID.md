# CloudServiceController::_GetEndpointId(_GUID *)

- ea: `0x18007a844`
- end: `0x18007aa72`
- name: `?_GetEndpointId@CloudServiceController@@AEAAJPEAU_GUID@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(CloudServiceController *__hidden this, struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180078470`
- `0x18007e84c`

## callees

- `0x1800016a0`
- `0x180008870`
- `0x18000b7d4`
- `0x180015050`
- `0x18004e184`
- `0x1800774d0`
- `0x180077acc`
- `0x18007a844`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007a94e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007a94e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa33`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007a9a8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007a9a8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007a981`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007a981`

## string_xrefs

- `0x18007a964`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007a9c1`: `onecoreuap\base\appmodel\messagingom\cloudservices\cloudservicecontroller.cpp`
- `0x18007a87e`: `CloudServiceController::_GetEndpointId`

## pseudocode

```c
__int64 __fastcall CloudServiceController::_GetEndpointId(CloudServiceController *this, struct _GUID *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  HRESULT v8; // eax
  unsigned int v9; // ebx
  HRESULT v10; // eax
  int v11; // ecx
  LPOLESTR v13; // [rsp+30h] [rbp-D0h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+4Ah] [rbp-B6h]
  int v17; // [rsp+52h] [rbp-AEh]
  __int16 v18; // [rsp+56h] [rbp-AAh]
  GUID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v20[256]; // [rsp+70h] [rbp-90h] BYREF

  StringCchPrintfW(v20, 0x100u, L"%S(%d):%s", "CloudServiceController::_GetEndpointId", 853, L"Enter");
  if ( (unsigned int)dword_1800FD5F0 > 5 )
  {
    v13 = v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v4,
      (int)byte_1800EF59B,
      v5,
      v6,
      (const OLECHAR **)&v13);
  }
  v7 = *((_QWORD *)this + 16);
  v16 = 0;
  v18 = 0;
  v17 = 0;
  lpsz[0] = (LPCOLESTR)&v15;
  lpsz[1] = (LPCOLESTR)&v15;
  v15 = 0;
  LODWORD(v13) = 0;
  v8 = ConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Get(
         v7 + 720,
         lpsz,
         &v13);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_6;
  pclsid = GUID_NULL;
  if ( (_DWORD)v13 )
  {
    v8 = CLSIDFromString(lpsz[0], &pclsid);
    v9 = v8;
    if ( v8 < 0 )
    {
LABEL_6:
      Log_HREvent_58(v8);
      goto LABEL_18;
    }
LABEL_17:
    v9 = 0;
    *a2 = pclsid;
    goto LABEL_18;
  }
  v8 = CoCreateGuid(&pclsid);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_6;
  v13 = 0;
  v10 = StringFromCLSID(&pclsid, &v13);
  v9 = v10;
  if ( v10 < 0 )
    goto LABEL_9;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpsz,
                          v13) )
  {
    v10 = ConfigValue<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Set(
            *((_QWORD *)this + 16) + 720LL,
            lpsz);
    v9 = v10;
    if ( v10 >= 0 )
    {
      if ( v13 )
        CoTaskMemFree(v13);
      goto LABEL_17;
    }
LABEL_9:
    v11 = v10;
    goto LABEL_10;
  }
  v9 = -2147024882;
  v11 = -2147024882;
LABEL_10:
  Log_HREvent_58(v11);
  if ( v13 )
    CoTaskMemFree(v13);
LABEL_18:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpsz);
  return v9;
}

```

## disassembly

```asm
0x18007a844  mov     [rsp-8+arg_10], rbx
0x18007a849  push    rbp
0x18007a84a  push    rsi
0x18007a84b  push    rdi
0x18007a84c  lea     rbp, [rsp-180h]
0x18007a854  sub     rsp, 280h
0x18007a85b  mov     rax, cs:__security_cookie
0x18007a862  xor     rax, rsp
0x18007a865  mov     [rbp+190h+var_20], rax
0x18007a86c  lea     rax, aEnter; "Enter"
0x18007a873  mov     rsi, rdx
0x18007a876  mov     rdi, rcx
0x18007a879  mov     [rsp+290h+var_268], rax
0x18007a87e  lea     r9, aCloudserviceco_29; "CloudServiceController::_GetEndpointId"
0x18007a885  mov     dword ptr [rsp+290h+var_270], 355h
0x18007a88d  lea     r8, aSDS; "%S(%d):%s"
0x18007a894  mov     edx, 100h; unsigned __int64
0x18007a899  lea     rcx, [rsp+290h+var_220]; unsigned __int16 *
0x18007a89e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a8a3  mov     eax, cs:dword_1800FD5F0
0x18007a8a9  cmp     eax, 5
0x18007a8ac  jbe     short loc_18007A8CE
0x18007a8ae  lea     rax, [rsp+290h+var_220]
0x18007a8b3  mov     [rsp+290h+var_260], rax
0x18007a8b8  lea     rdx, byte_1800EF59B
0x18007a8bf  lea     rax, [rsp+290h+var_260]
0x18007a8c4  mov     [rsp+290h+var_270], rax
0x18007a8c9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007a8ce  mov     rcx, [rdi+80h]
0x18007a8d5  lea     r8, [rsp+290h+var_260]
0x18007a8da  xor     eax, eax
0x18007a8dc  mov     [rsp+290h+var_246], 0
0x18007a8e5  mov     [rsp+290h+var_23A], ax
0x18007a8ea  lea     rdx, [rsp+290h+lpsz]
0x18007a8ef  lea     rax, [rsp+290h+var_248]
0x18007a8f4  mov     [rsp+290h+var_23E], 0
0x18007a8fc  mov     [rsp+290h+lpsz], rax
0x18007a901  add     rcx, 2D0h
0x18007a908  lea     rax, [rsp+290h+var_248]
0x18007a90d  mov     [rsp+290h+var_250], rax
0x18007a912  xor     eax, eax
0x18007a914  mov     [rsp+290h+var_248], ax
0x18007a919  mov     dword ptr [rsp+290h+var_260], eax
0x18007a91d  call    ?Get@?$ConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z; ConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Get(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)
0x18007a922  mov     ebx, eax
0x18007a924  test    eax, eax
0x18007a926  jns     short loc_18007A930
0x18007a928  mov     r9d, 359h
0x18007a92e  jmp     short loc_18007A964
0x18007a930  cmp     dword ptr [rsp+290h+var_260], 0
0x18007a935  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007a93c  movdqu  xmmword ptr [rsp+290h+pclsid.Data1], xmm0
0x18007a942  jz      short loc_18007A97C
0x18007a944  mov     rcx, [rsp+290h+lpsz]; lpsz
0x18007a949  lea     rdx, [rsp+290h+pclsid]; pclsid
0x18007a94e  call    cs:__imp_CLSIDFromString
0x18007a954  mov     ebx, eax
0x18007a956  test    eax, eax
0x18007a958  jns     loc_18007AA39
0x18007a95e  mov     r9d, 35Eh
0x18007a964  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007a96b  mov     edx, 1
0x18007a970  mov     ecx, eax; int
0x18007a972  call    Log_HREvent_58
0x18007a977  jmp     loc_18007AA44
0x18007a97c  lea     rcx, [rsp+290h+pclsid]; pguid
0x18007a981  call    cs:__imp_CoCreateGuid
0x18007a987  mov     ebx, eax
0x18007a989  test    eax, eax
0x18007a98b  jns     short loc_18007A995
0x18007a98d  mov     r9d, 362h
0x18007a993  jmp     short loc_18007A964
0x18007a995  lea     rdx, [rsp+290h+var_260]; lplpsz
0x18007a99a  mov     [rsp+290h+var_260], 0
0x18007a9a3  lea     rcx, [rsp+290h+pclsid]; rclsid
0x18007a9a8  call    cs:__imp_StringFromCLSID
0x18007a9ae  mov     ebx, eax
0x18007a9b0  test    eax, eax
0x18007a9b2  jns     short loc_18007A9DF
0x18007a9b4  mov     r9d, 365h
0x18007a9ba  mov     edx, 1
0x18007a9bf  mov     ecx, eax; int
0x18007a9c1  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\appmodel\\messagingom"...
0x18007a9c8  call    Log_HREvent_58
0x18007a9cd  mov     rcx, [rsp+290h+var_260]; pv
0x18007a9d2  test    rcx, rcx
0x18007a9d5  jz      short loc_18007AA44
0x18007a9d7  call    cs:__imp_CoTaskMemFree
0x18007a9dd  jmp     short loc_18007AA44
0x18007a9df  mov     rdx, [rsp+290h+var_260]
0x18007a9e4  lea     rcx, [rsp+290h+lpsz]
0x18007a9e9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18007a9ee  test    al, al
0x18007a9f0  jnz     short loc_18007AA03
0x18007a9f2  mov     ebx, 8007000Eh
0x18007a9f7  mov     r9d, 367h
0x18007a9fd  mov     ecx, ebx
0x18007a9ff  xor     edx, edx
0x18007aa01  jmp     short loc_18007A9C1
0x18007aa03  mov     rcx, [rdi+80h]
0x18007aa0a  lea     rdx, [rsp+290h+lpsz]
0x18007aa0f  add     rcx, 2D0h
0x18007aa16  call    ?Set@?$ConfigValue@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ConfigValue<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Set(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18007aa1b  mov     ebx, eax
0x18007aa1d  test    eax, eax
0x18007aa1f  jns     short loc_18007AA29
0x18007aa21  mov     r9d, 368h
0x18007aa27  jmp     short loc_18007A9BA
0x18007aa29  mov     rcx, [rsp+290h+var_260]; pv
0x18007aa2e  test    rcx, rcx
0x18007aa31  jz      short loc_18007AA39
0x18007aa33  call    cs:__imp_CoTaskMemFree
0x18007aa39  movups  xmm0, xmmword ptr [rsp+290h+pclsid.Data1]
0x18007aa3e  xor     ebx, ebx
0x18007aa40  movdqu  xmmword ptr [rsi], xmm0
0x18007aa44  lea     rcx, [rsp+290h+lpsz]
0x18007aa49  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18007aa4e  mov     eax, ebx
0x18007aa50  mov     rcx, [rbp+190h+var_20]
0x18007aa57  xor     rcx, rsp; StackCookie
0x18007aa5a  call    __security_check_cookie
0x18007aa5f  mov     rbx, [rsp+290h+arg_10]
0x18007aa67  add     rsp, 280h
0x18007aa6e  pop     rdi
0x18007aa6f  pop     rsi
0x18007aa70  pop     rbp
0x18007aa71  retn
```
