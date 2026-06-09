# Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey(wistd::function<long (ushort const *)> &&)

- ea: `0x18002aa34`
- end: `0x18002aeaf`
- name: `?ForEachActiveMMKey@NetworkUXManager@UX@Networking@Windows@@AEAAX$$QEAV?$function@$$A6AJPEBG@Z@wistd@@@Z`
- size: `1147`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task`

## callers

- `0x180033538`
- `0x180033a88`

## callees

- `0x180002520`
- `0x18000a70c`
- `0x18000f054`
- `0x18000f0b0`
- `0x18001a2d0`
- `0x18001fcb4`
- `0x180025b60`
- `0x180026d94`
- `0x180027078`
- `0x1800270ec`
- `0x180028470`
- `0x180028588`
- `0x1800299b4`
- `0x1800299ec`
- `0x18002aa34`
- `0x18002d900`
- `0x180035eec`
- `0x180037c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad98`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ac9b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ad8a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ac9b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ad8a`

## string_xrefs

- `0x18002ae9c`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Networking::UX::NetworkUXManager::ForEachActiveMMKey(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // r15
  const WCHAR *v7; // r8
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // r10
  __int64 v15; // rdx
  _DWORD *v16; // rdx
  _DWORD *v17; // rax
  signed int LastError; // eax
  SC_HANDLE v19; // rcx
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rdx
  const char *v22; // rbx
  unsigned int v23; // eax
  __int64 v24; // r9
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  SC_HANDLE v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  wil::reg::reg_view_details *v32; // [rsp+20h] [rbp-178h]
  int v33[2]; // [rsp+30h] [rbp-168h] BYREF
  int v34[2]; // [rsp+38h] [rbp-160h] BYREF
  int v35; // [rsp+40h] [rbp-158h] BYREF
  char v36; // [rsp+44h] [rbp-154h]
  int v37; // [rsp+48h] [rbp-150h] BYREF
  char v38; // [rsp+4Ch] [rbp-14Ch]
  _BYTE ServiceStatus[32]; // [rsp+50h] [rbp-148h] BYREF
  __int64 v40; // [rsp+70h] [rbp-128h]
  int v41; // [rsp+78h] [rbp-120h]
  int v42; // [rsp+7Ch] [rbp-11Ch]
  __int64 v43; // [rsp+80h] [rbp-118h]
  _BYTE v44[32]; // [rsp+88h] [rbp-110h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-F0h]
  int v46; // [rsp+B0h] [rbp-E8h]
  _BYTE v47[32]; // [rsp+C0h] [rbp-D8h] BYREF
  __int64 v48; // [rsp+E0h] [rbp-B8h]
  int v49; // [rsp+E8h] [rbp-B0h]
  _BYTE v50[56]; // [rsp+100h] [rbp-98h] BYREF
  _BYTE v51[56]; // [rsp+138h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v4 = *(_QWORD *)(a1 + 144);
  if ( !v4 )
    return;
  try
  {
    *(_QWORD *)v34 = ServiceStatus;
    v42 = 0;
    memset(ServiceStatus, 0, 24);
    *(_QWORD *)&ServiceStatus[24] = 7;
    *(_WORD *)ServiceStatus = 0;
    v40 = 0;
    v41 = -1;
    v43 = 0;
    v5 = wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
           (__int64)v47,
           v4);
    wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(v50, v5, ServiceStatus);
    wil::reg::key_iterator_data<std::wstring>::key_iterator_data<std::wstring>(v44, v50);
    wil::reg::key_iterator_data<std::wstring>::key_iterator_data<std::wstring>(v47, v51);
    v6 = v48;
    while ( 1 )
    {
      if ( (v46 == -1 || v49 == -1 || v45 == v6) && v46 == v49 )
      {
        std::wstring::_Tidy_deallocate(v47);
        std::wstring::_Tidy_deallocate(v44);
        wil::details::pointer_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(v50);
        return;
      }
      if ( v46 == -1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6FF,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
          v30);
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44, v28, v29);
      wil::reg::open_unique_key((int)v33, *(HKEY *)(a1 + 144), v7);
      *(_QWORD *)v34 = *(_QWORD *)v33;
      LODWORD(v32) = 16;
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned long>(
        (__int64)v34,
        (__int64)&v37,
        v8,
        (__int64)L"Active",
        v32);
      if ( v38 && v37 )
      {
        *(_QWORD *)v34 = *(_QWORD *)v33;
        LODWORD(v32) = 16;
        wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned long>(
          (__int64)v34,
          (__int64)&v35,
          v10,
          (__int64)L"MediaType",
          v32);
        if ( v36 )
        {
          v16 = *(_DWORD **)(a1 + 160);
          v17 = *(_DWORD **)(a1 + 152);
          if ( v17 != v16 )
          {
            while ( *v17 != v35 )
            {
              if ( ++v17 == v16 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44, v16, v12);
                  v15 = 39;
                  goto LABEL_50;
                }
                goto LABEL_51;
              }
            }
          }
          if ( v35 == 1 )
          {
            LastError = -2147467259;
            memset(ServiceStatus, 0, 28);
            v19 = *(SC_HANDLE *)(a1 + 872);
            if ( v19 )
            {
              if ( QueryServiceStatus(v19, (LPSERVICE_STATUS)ServiceStatus) )
              {
                LastError = 0;
              }
              else
              {
                LastError = GetLastError();
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
              }
            }
            v20 = retaddr;
            if ( LastError < 0 )
            {
              v21 = 602;
LABEL_28:
              wil::details::in1diag3::_Log_Hr(
                v20,
                (void *)v21,
                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                (const char *)(unsigned int)LastError,
                (int)v32);
LABEL_29:
              v22 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44, v16, v12);
              v23 = wistd::function<long (unsigned short const *)>::operator()(a2, v22);
              wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x273,
                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                (const char *)v23,
                (int)"Callback for %ls failed",
                v22);
              goto LABEL_51;
            }
            v24 = *(unsigned int *)&ServiceStatus[4];
            if ( *(_DWORD *)&ServiceStatus[4] == 4 )
              goto LABEL_29;
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v26 = 40;
LABEL_46:
              WPP_SF_d(v25[2], v26, &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids, v24);
            }
          }
          else
          {
            if ( v35 != 2 )
              goto LABEL_29;
            LastError = -2147467259;
            memset(ServiceStatus, 0, 28);
            v27 = *(SC_HANDLE *)(a1 + 1432);
            if ( v27 )
            {
              if ( QueryServiceStatus(v27, (LPSERVICE_STATUS)ServiceStatus) )
              {
                LastError = 0;
              }
              else
              {
                LastError = GetLastError();
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
              }
            }
            v20 = retaddr;
            if ( LastError < 0 )
            {
              v21 = 615;
              goto LABEL_28;
            }
            v24 = *(unsigned int *)&ServiceStatus[4];
            if ( *(_DWORD *)&ServiceStatus[4] == 4 )
              goto LABEL_29;
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v26 = 41;
              goto LABEL_46;
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44, v11, v12);
          v15 = 38;
LABEL_50:
          WPP_SF_S(*(_QWORD *)(v14 + 16), v15, &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids, v13);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44, v9, v10);
        v15 = 37;
        goto LABEL_50;
      }
LABEL_51:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v33);
      wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator+=((__int64)v44);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x277,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
      v31);
  }
}

```

## disassembly

```asm
0x18002aa34  mov     [rsp+arg_10], rbx
0x18002aa39  push    rdi
0x18002aa3a  push    r14
0x18002aa3c  push    r15
0x18002aa3e  sub     rsp, 180h
0x18002aa45  mov     rax, cs:__security_cookie
0x18002aa4c  xor     rax, rsp
0x18002aa4f  mov     [rsp+198h+var_28], rax
0x18002aa57  mov     r14, rdx
0x18002aa5a  mov     rdi, rcx
0x18002aa5d  mov     rdx, [rcx+90h]
0x18002aa64  test    rdx, rdx
0x18002aa67  jnz     short loc_18002AA6E
0x18002aa69  jmp     loc_18002AE77
0x18002aa6e  lea     rax, [rsp+198h+ServiceStatus]
0x18002aa73  mov     qword ptr [rsp+198h+var_160], rax
0x18002aa78  mov     [rsp+198h+var_11C], 0
0x18002aa80  xorps   xmm0, xmm0
0x18002aa83  movups  xmmword ptr [rsp+198h+ServiceStatus], xmm0
0x18002aa88  mov     qword ptr [rsp+198h+ServiceStatus+10h], 0
0x18002aa91  mov     qword ptr [rsp+198h+ServiceStatus+18h], 7
0x18002aa9a  xor     eax, eax
0x18002aa9c  mov     word ptr [rsp+198h+ServiceStatus], ax
0x18002aaa1  mov     [rsp+198h+var_128], rax
0x18002aaa6  mov     [rsp+198h+var_120], 0FFFFFFFFh
0x18002aaae  mov     [rsp+198h+var_118], rax
0x18002aab6  lea     rcx, [rsp+198h+var_D8]
0x18002aabe  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@QEAA@PEAUHKEY__@@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(HKEY__ *)
0x18002aac3  nop
0x18002aac4  lea     r8, [rsp+198h+ServiceStatus]
0x18002aac9  mov     rdx, rax
0x18002aacc  lea     rcx, [rsp+198h+var_98]
0x18002aad4  call    ??$make_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_t@V?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>,wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>)
0x18002aad9  nop
0x18002aada  lea     rdx, [rsp+198h+var_98]
0x18002aae2  lea     rcx, [rsp+198h+var_110]
0x18002aaea  call    ??0?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::key_iterator_data<std::wstring>::key_iterator_data<std::wstring>(wil::reg::key_iterator_data<std::wstring> const &)
0x18002aaef  nop
0x18002aaf0  lea     rdx, [rsp+198h+var_60]
0x18002aaf8  lea     rcx, [rsp+198h+var_D8]
0x18002ab00  call    ??0?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::key_iterator_data<std::wstring>::key_iterator_data<std::wstring>(wil::reg::key_iterator_data<std::wstring> const &)
0x18002ab05  nop
0x18002ab06  lea     rbx, WPP_GLOBAL_Control
0x18002ab0d  mov     r15, [rsp+198h+var_B8]
0x18002ab15  mov     eax, [rsp+198h+var_E8]
0x18002ab1c  or      ecx, 0FFFFFFFFh
0x18002ab1f  cmp     eax, ecx
0x18002ab21  jz      short loc_18002AB36
0x18002ab23  cmp     [rsp+198h+var_B0], ecx
0x18002ab2a  jz      short loc_18002AB36
0x18002ab2c  cmp     [rsp+198h+var_F0], r15
0x18002ab34  jnz     short loc_18002AB43
0x18002ab36  cmp     eax, [rsp+198h+var_B0]
0x18002ab3d  jz      loc_18002AE4D
0x18002ab43  cmp     eax, ecx
0x18002ab45  setz    al
0x18002ab48  mov     rcx, [rsp+198h]; this
0x18002ab50  test    al, al
0x18002ab52  jnz     loc_18002AE9C
0x18002ab58  lea     rcx, [rsp+198h+var_110]
0x18002ab60  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ab65  mov     r8, rax; lpSubKey
0x18002ab68  mov     rdx, [rdi+90h]; hKey
0x18002ab6f  lea     rcx, [rsp+198h+var_168]; int
0x18002ab74  call    ?open_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::open_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x18002ab79  nop
0x18002ab7a  mov     rax, qword ptr [rsp+198h+var_168]
0x18002ab7f  mov     qword ptr [rsp+198h+var_160], rax
0x18002ab84  mov     dword ptr [rsp+198h+var_178], 10h; wil::reg::reg_view_details *
0x18002ab8c  lea     r9, ValueName; "Active"
0x18002ab93  lea     rdx, [rsp+198h+var_150]; int
0x18002ab98  lea     rcx, [rsp+198h+var_160]; int
0x18002ab9d  call    ??$try_get_value@K@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@K@std@@PEBG0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<ulong>(ushort const *,ushort const *,ulong)
0x18002aba2  cmp     [rsp+198h+var_14C], 0
0x18002aba7  jz      loc_18002ADF8
0x18002abad  cmp     [rsp+198h+var_150], 0
0x18002abb2  jz      loc_18002ADF8
0x18002abb8  mov     rax, qword ptr [rsp+198h+var_168]
0x18002abbd  mov     qword ptr [rsp+198h+var_160], rax
0x18002abc2  mov     dword ptr [rsp+198h+var_178], 10h; int
0x18002abca  lea     r9, aMediatype; "MediaType"
0x18002abd1  lea     rdx, [rsp+198h+var_158]; int
0x18002abd6  lea     rcx, [rsp+198h+var_160]; int
0x18002abdb  call    ??$try_get_value@K@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@K@std@@PEBG0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<ulong>(ushort const *,ushort const *,ulong)
0x18002abe0  cmp     [rsp+198h+var_154], 0
0x18002abe5  jnz     short loc_18002AC19
0x18002abe7  mov     r10, cs:WPP_GLOBAL_Control
0x18002abee  cmp     r10, rbx
0x18002abf1  jz      loc_18002AE31
0x18002abf7  test    byte ptr [r10+1Ch], 8
0x18002abfc  jz      loc_18002AE31
0x18002ac02  lea     rcx, [rsp+198h+var_110]
0x18002ac0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ac0f  mov     edx, 26h ; '&'
0x18002ac14  jmp     loc_18002AE1D
0x18002ac19  mov     ecx, [rsp+198h+var_158]
0x18002ac1d  mov     rdx, [rdi+0A0h]
0x18002ac24  mov     rax, [rdi+98h]
0x18002ac2b  cmp     rax, rdx
0x18002ac2e  jz      short loc_18002AC6F
0x18002ac30  cmp     [rax], ecx
0x18002ac32  jz      short loc_18002AC6F
0x18002ac34  add     rax, 4
0x18002ac38  cmp     rax, rdx
0x18002ac3b  jnz     short loc_18002AC30
0x18002ac3d  mov     r10, cs:WPP_GLOBAL_Control
0x18002ac44  cmp     r10, rbx
0x18002ac47  jz      loc_18002AE31
0x18002ac4d  test    byte ptr [r10+1Ch], 8
0x18002ac52  jz      loc_18002AE31
0x18002ac58  lea     rcx, [rsp+198h+var_110]
0x18002ac60  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ac65  mov     edx, 27h ; '''
0x18002ac6a  jmp     loc_18002AE1D
0x18002ac6f  cmp     ecx, 1
0x18002ac72  jnz     loc_18002AD5E
0x18002ac78  mov     eax, 80004005h
0x18002ac7d  xorps   xmm0, xmm0
0x18002ac80  movups  xmmword ptr [rsp+198h+ServiceStatus], xmm0
0x18002ac85  movups  xmmword ptr [rsp+198h+ServiceStatus+0Ch], xmm0
0x18002ac8a  mov     rcx, [rdi+368h]; hService
0x18002ac91  test    rcx, rcx
0x18002ac94  jz      short loc_18002ACBB
0x18002ac96  lea     rdx, [rsp+198h+ServiceStatus]; lpServiceStatus
0x18002ac9b  call    cs:__imp_QueryServiceStatus
0x18002aca1  test    eax, eax
0x18002aca3  jz      short loc_18002ACA9
0x18002aca5  xor     eax, eax
0x18002aca7  jmp     short loc_18002ACBB
0x18002aca9  call    cs:__imp_GetLastError
0x18002acaf  test    eax, eax
0x18002acb1  jle     short loc_18002ACBB
0x18002acb3  movzx   eax, ax
0x18002acb6  or      eax, 80070000h
0x18002acbb  mov     rcx, [rsp+198h]; this
0x18002acc3  test    eax, eax
0x18002acc5  jns     short loc_18002AD2F
0x18002acc7  mov     edx, 25Ah; void *
0x18002accc  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002acd3  mov     r9d, eax; char *
0x18002acd6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002acdb  lea     rcx, [rsp+198h+var_110]
0x18002ace3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ace8  mov     rbx, rax
0x18002aceb  mov     rdx, rax
0x18002acee  mov     rcx, r14
0x18002acf1  call    ??R?$function@$$A6AJPEBG@Z@wistd@@QEBAJPEBG@Z; wistd::function<long (ushort const *)>::operator()(ushort const *)
0x18002acf6  mov     rcx, [rsp+198h]; this
0x18002acfe  mov     [rsp+198h+var_170], rbx; char *
0x18002ad03  lea     rdx, aCallbackForLsF; "Callback for %ls failed"
0x18002ad0a  mov     [rsp+198h+var_178], rdx; int
0x18002ad0f  mov     r9d, eax; char *
0x18002ad12  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002ad19  mov     edx, 273h; void *
0x18002ad1e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ad23  lea     rbx, WPP_GLOBAL_Control
0x18002ad2a  jmp     loc_18002AE31
0x18002ad2f  mov     r9d, dword ptr [rsp+198h+ServiceStatus+4]
0x18002ad34  cmp     r9d, 4
0x18002ad38  jz      short loc_18002ACDB
0x18002ad3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad41  cmp     rcx, rbx
0x18002ad44  jz      loc_18002AE31
0x18002ad4a  test    byte ptr [rcx+1Ch], 8
0x18002ad4e  jz      loc_18002AE31
0x18002ad54  mov     edx, 28h ; '('
0x18002ad59  jmp     loc_18002ADE6
0x18002ad5e  cmp     ecx, 2
0x18002ad61  jnz     loc_18002ACDB
0x18002ad67  mov     eax, 80004005h
0x18002ad6c  xorps   xmm0, xmm0
0x18002ad6f  movups  xmmword ptr [rsp+198h+ServiceStatus], xmm0
0x18002ad74  movups  xmmword ptr [rsp+198h+ServiceStatus+0Ch], xmm0
0x18002ad79  mov     rcx, [rdi+598h]; hService
0x18002ad80  test    rcx, rcx
0x18002ad83  jz      short loc_18002ADAA
0x18002ad85  lea     rdx, [rsp+198h+ServiceStatus]; lpServiceStatus
0x18002ad8a  call    cs:__imp_QueryServiceStatus
0x18002ad90  test    eax, eax
0x18002ad92  jz      short loc_18002AD98
0x18002ad94  xor     eax, eax
0x18002ad96  jmp     short loc_18002ADAA
0x18002ad98  call    cs:__imp_GetLastError
0x18002ad9e  test    eax, eax
0x18002ada0  jle     short loc_18002ADAA
0x18002ada2  movzx   eax, ax
0x18002ada5  or      eax, 80070000h
0x18002adaa  mov     rcx, [rsp+198h]
0x18002adb2  test    eax, eax
0x18002adb4  jns     short loc_18002ADC0
0x18002adb6  mov     edx, 267h
0x18002adbb  jmp     loc_18002ACCC
0x18002adc0  mov     r9d, dword ptr [rsp+198h+ServiceStatus+4]
0x18002adc5  cmp     r9d, 4
0x18002adc9  jz      loc_18002ACDB
0x18002adcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002add6  cmp     rcx, rbx
0x18002add9  jz      short loc_18002AE31
0x18002addb  test    byte ptr [rcx+1Ch], 8
0x18002addf  jz      short loc_18002AE31
0x18002ade1  mov     edx, 29h ; ')'
0x18002ade6  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x18002aded  mov     rcx, [rcx+10h]
0x18002adf1  call    WPP_SF_d
0x18002adf6  jmp     short loc_18002AE31
0x18002adf8  mov     r10, cs:WPP_GLOBAL_Control
0x18002adff  cmp     r10, rbx
0x18002ae02  jz      short loc_18002AE31
0x18002ae04  test    byte ptr [r10+1Ch], 8
0x18002ae09  jz      short loc_18002AE31
0x18002ae0b  lea     rcx, [rsp+198h+var_110]
0x18002ae13  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ae18  mov     edx, 25h ; '%'
0x18002ae1d  mov     r9, rax
0x18002ae20  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x18002ae27  mov     rcx, [r10+10h]
0x18002ae2b  call    WPP_SF_S
0x18002ae30  nop
0x18002ae31  lea     rcx, [rsp+198h+var_168]
0x18002ae36  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ae3b  lea     rcx, [rsp+198h+var_110]
0x18002ae43  call    ??Y?$iterator_t@V?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@QEAAAEAV012@_K@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator+=(unsigned __int64)
0x18002ae48  jmp     loc_18002AB15
0x18002ae4d  lea     rcx, [rsp+198h+var_D8]
0x18002ae55  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae5a  nop
0x18002ae5b  lea     rcx, [rsp+198h+var_110]
0x18002ae63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae68  nop
0x18002ae69  lea     rcx, [rsp+198h+var_98]
0x18002ae71  call    ??1?$pointer_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@@details@wil@@QEAA@XZ; wil::details::pointer_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>::~pointer_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(void)
0x18002ae76  nop
0x18002ae77  mov     rcx, [rsp+198h+var_28]
0x18002ae7f  xor     rcx, rsp; StackCookie
0x18002ae82  call    __security_check_cookie
0x18002ae87  mov     rbx, [rsp+198h+arg_10]
0x18002ae8f  add     rsp, 180h
0x18002ae96  pop     r15
0x18002ae98  pop     r14
0x18002ae9a  pop     rdi
0x18002ae9b  retn
0x18002ae9c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002aea3  mov     edx, 6FFh; void *
0x18002aea8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
