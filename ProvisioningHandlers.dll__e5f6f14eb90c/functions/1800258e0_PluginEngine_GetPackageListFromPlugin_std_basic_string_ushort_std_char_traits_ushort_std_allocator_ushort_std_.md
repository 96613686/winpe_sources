# PluginEngine::GetPackageListFromPlugin(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>,std::allocator<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>>> *)

- ea: `0x1800258e0`
- end: `0x180025d54`
- name: `?GetPackageListFromPlugin@PluginEngine@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@3@@Z`
- size: `1140`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800020d0`
- `0x1800087ec`
- `0x18000f4fc`
- `0x18000f534`
- `0x18001085c`
- `0x18001ec4c`
- `0x18001fbfc`
- `0x180021d10`
- `0x1800227b4`
- `0x1800245ec`
- `0x1800246bc`
- `0x1800258e0`
- `0x180027da0`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025cd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025c5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025cd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ce9`

## string_xrefs

- `0x180025951`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002599e`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180025a3a`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180025ae3`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180025c0c`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PluginEngine::GetPackageListFromPlugin(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v6)(_QWORD *, __int64, unsigned int *); // rbx
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 result; // rax
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  __int64 **v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // r14d
  __int64 v18; // rcx
  unsigned int v19; // edi
  __int64 v20; // rdx
  const char *v21; // r9
  __int64 v22; // rcx
  unsigned int v23; // r14d
  __int64 v24; // rdx
  unsigned int i; // ebx
  void *v26; // rdi
  __int64 v27; // r12
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned int j; // edi
  __int64 v31; // rdx
  unsigned int k; // edi
  __int64 v33; // rdx
  __int64 v34; // rdx
  int v35; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v36; // [rsp+28h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C0h] BYREF
  __int64 *v39; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B0h] BYREF
  char v41; // [rsp+50h] [rbp-A8h]
  _QWORD v42[2]; // [rsp+60h] [rbp-98h] BYREF
  char v43; // [rsp+70h] [rbp-88h]
  __int64 **v44; // [rsp+80h] [rbp-78h]
  char v45[32]; // [rsp+90h] [rbp-68h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v46 = a2;
  v37 = 0;
  v6 = *(__int64 (__fastcall **)(_QWORD *, __int64, unsigned int *))(*a1 + 80LL);
  v7 = std::wstring::wstring(v42);
  v8 = v6(a1, v7, &v37);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v12 = (__int64)(a1[2] - a1[1]) >> 3;
    if ( v37 < v12 )
    {
      try
      {
        v35 = 0;
        v36 = 0;
        v42[0] = &v36;
        v42[1] = &v35;
        v43 = 1;
        v14 = (__int64 **)std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at();
        v15 = *v14;
        v16 = **v14;
        v39 = &v36;
        v40 = 0;
        v41 = 1;
        v17 = (*(__int64 (__fastcall **)(__int64 *, int *, __int64 *))(v16 + 32))(v15, &v35, &v40);
        wil::details::out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v39);
        if ( v17 >= 0 )
        {
          if ( v36 || !v35 )
          {
            std::vector<std::unique_ptr<ProvPackageInfo>>::clear(a3);
            for ( i = 0; i < v35; ++i )
            {
              v26 = operator new(0x60u);
              v38 = (__int64)v26;
              if ( v26 )
              {
                v44 = &v39;
                v27 = std::wstring::wstring(&v39, *(_QWORD *)(v36 + 24LL * i + 8));
                v28 = std::wstring::wstring(v45, *(_QWORD *)(v36 + 24LL * i));
                v29 = ProvPackageInfo::ProvPackageInfo(v26, v28, v27);
              }
              else
              {
                v29 = 0;
              }
              v38 = v29;
              if ( !v29 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x80,
                  (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                  (const char *)0x8007000ELL,
                  v35);
                std::unique_ptr<ProvPackageInfo>::_Delete(&v38);
                if ( v36 && v35 )
                {
                  for ( j = 0; j < v35; ++j )
                  {
                    CoTaskMemFree(*(LPVOID *)(v36 + 24LL * j));
                    CoTaskMemFree(*(LPVOID *)(v36 + 24LL * j + 8));
                  }
                }
                wistd::unique_ptr<unsigned int,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
                  &v36,
                  0);
                LOBYTE(v31) = 1;
                std::wstring::_Tidy(a2, v31, 0);
                result = 2147942414LL;
                goto LABEL_39;
              }
              std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(a3, &v38);
              std::unique_ptr<ProvPackageInfo>::_Delete(&v38);
            }
            if ( v36 && v35 )
            {
              for ( k = 0; k < v35; ++k )
              {
                CoTaskMemFree(*(LPVOID *)(v36 + 24LL * k));
                CoTaskMemFree(*(LPVOID *)(v36 + 24LL * k + 8));
              }
            }
            wistd::unique_ptr<unsigned int,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &v36,
              0);
            LOBYTE(v33) = 1;
            std::wstring::_Tidy(a2, v33, 0);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
              (const char *)0x80070057LL,
              v35);
            v22 = v36;
            if ( v36 )
            {
              v23 = 0;
              if ( v35 )
              {
                while ( 1 )
                {
                  CoTaskMemFree(*(LPVOID *)(v22 + 24LL * v23));
                  CoTaskMemFree(*(LPVOID *)(v36 + 24LL * v23++ + 8));
                  if ( v23 >= v35 )
                    break;
                  v22 = v36;
                }
              }
            }
            wistd::unique_ptr<unsigned int,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &v36,
              0);
            LOBYTE(v24) = 1;
            std::wstring::_Tidy(a2, v24, 0);
            result = 2147942487LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73,
            (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
            (const char *)(unsigned int)v17,
            v35);
          v18 = v36;
          if ( v36 )
          {
            v19 = 0;
            if ( v35 )
            {
              while ( 1 )
              {
                CoTaskMemFree(*(LPVOID *)(v18 + 24LL * v19));
                CoTaskMemFree(*(LPVOID *)(v36 + 24LL * v19++ + 8));
                if ( v19 >= v35 )
                  break;
                v18 = v36;
              }
            }
          }
          wistd::unique_ptr<unsigned int,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &v36,
            0);
          LOBYTE(v20) = 1;
          std::wstring::_Tidy(a2, v20, 0);
          result = (unsigned int)v17;
        }
      }
      catch ( ... )
      {
        v35 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x85,
                (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                v21);
        LOBYTE(v34) = 1;
        std::wstring::_Tidy(v46, v34, 0);
        result = (unsigned int)v35;
      }
LABEL_39:
      ;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)0x80070057LL,
        v35);
      LOBYTE(v13) = 1;
      std::wstring::_Tidy(a2, v13, 0);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v8,
      v35);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(a2, v10, 0);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800258e0  mov     r11, rsp
0x1800258e3  push    rbx
0x1800258e4  push    rsi
0x1800258e5  push    rdi
0x1800258e6  push    r12
0x1800258e8  push    r13
0x1800258ea  push    r14
0x1800258ec  push    r15
0x1800258ee  sub     rsp, 0C0h
0x1800258f5  mov     rax, cs:__security_cookie
0x1800258fc  xor     rax, rsp
0x1800258ff  mov     [rsp+0F8h+var_40], rax
0x180025907  mov     r15, r8
0x18002590a  mov     rsi, rdx
0x18002590d  mov     rdi, rcx
0x180025910  mov     [r11-48h], rdx
0x180025914  xor     r13d, r13d
0x180025917  mov     [rsp+0F8h+var_C8], r13d
0x18002591c  mov     rax, [rcx]
0x18002591f  mov     rbx, [rax+50h]
0x180025923  lea     rcx, [rsp+0F8h+var_98]
0x180025928  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002592d  lea     r8, [rsp+0F8h+var_C8]
0x180025932  mov     rdx, rax
0x180025935  mov     rcx, rdi
0x180025938  mov     rax, rbx
0x18002593b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025940  mov     ebx, eax
0x180025942  test    eax, eax
0x180025944  jns     short loc_180025976
0x180025946  mov     rcx, [rsp+0F8h]; this
0x18002594e  mov     r9d, eax; char *
0x180025951  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180025958  lea     edx, [r13+5Ch]; void *
0x18002595c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025961  nop
0x180025962  xor     r8d, r8d
0x180025965  mov     dl, 1
0x180025967  mov     rcx, rsi
0x18002596a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002596f  mov     eax, ebx
0x180025971  jmp     loc_180025D30
0x180025976  lea     rcx, [rdi+8]
0x18002597a  mov     edx, [rsp+0F8h+var_C8]
0x18002597e  mov     rax, [rcx+8]
0x180025982  sub     rax, [rcx]
0x180025985  sar     rax, 3
0x180025989  cmp     rdx, rax
0x18002598c  jb      short loc_1800259C4
0x18002598e  mov     rcx, [rsp+0F8h]; this
0x180025996  mov     edi, 80070057h
0x18002599b  mov     r9d, edi; char *
0x18002599e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800259a5  mov     edx, 61h ; 'a'; void *
0x1800259aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800259af  nop
0x1800259b0  xor     r8d, r8d
0x1800259b3  mov     dl, 1
0x1800259b5  mov     rcx, rsi
0x1800259b8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800259bd  mov     eax, edi
0x1800259bf  jmp     loc_180025D30
0x1800259c4  mov     [rsp+0F8h+var_D8], r13d; int
0x1800259c9  mov     [rsp+0F8h+var_D0], r13
0x1800259ce  lea     r12, [rsp+0F8h+var_D0]
0x1800259d3  mov     [rsp+0F8h+var_98], r12
0x1800259d8  lea     rdi, [rsp+0F8h+var_D8]
0x1800259dd  mov     [rsp+0F8h+var_90], rdi
0x1800259e2  mov     [rsp+0F8h+var_88], 1
0x1800259e7  call    ?at@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(unsigned __int64)
0x1800259ec  mov     rcx, [rax]
0x1800259ef  mov     rax, [rcx]
0x1800259f2  lea     rdx, [rsp+0F8h+var_D0]
0x1800259f7  mov     [rsp+0F8h+var_B8], rdx
0x1800259fc  mov     [rsp+0F8h+var_B0], r13
0x180025a01  mov     [rsp+0F8h+var_A8], 1
0x180025a06  lea     r8, [rsp+0F8h+var_B0]
0x180025a0b  lea     rdx, [rsp+0F8h+var_D8]
0x180025a10  mov     rax, [rax+20h]
0x180025a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a19  mov     r14d, eax
0x180025a1c  lea     rcx, [rsp+0F8h+var_B8]
0x180025a21  call    ??1?$out_param_t@V?$unique_ptr@UProvisioningResult@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180025a26  test    r14d, r14d
0x180025a29  jns     loc_180025ABD
0x180025a2f  mov     rcx, [rsp+0F8h]; this
0x180025a37  mov     r9d, r14d; char *
0x180025a3a  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180025a41  mov     edx, 73h ; 's'; void *
0x180025a46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025a4b  nop
0x180025a4c  mov     rcx, [rsp+0F8h+var_D0]
0x180025a51  test    rcx, rcx
0x180025a54  jz      short loc_180025A9B
0x180025a56  mov     edi, r13d
0x180025a59  cmp     [rsp+0F8h+var_D8], r13d
0x180025a5e  jbe     short loc_180025A9B
0x180025a60  mov     eax, edi
0x180025a62  lea     rbx, [rax+rax*2]
0x180025a66  mov     rcx, [rcx+rbx*8]; pv
0x180025a6a  call    cs:__imp_CoTaskMemFree
0x180025a71  nop     dword ptr [rax+rax+00h]
0x180025a76  mov     rcx, [rsp+0F8h+var_D0]
0x180025a7b  mov     rcx, [rcx+rbx*8+8]; pv
0x180025a80  call    cs:__imp_CoTaskMemFree
0x180025a87  nop     dword ptr [rax+rax+00h]
0x180025a8c  inc     edi
0x180025a8e  cmp     edi, [rsp+0F8h+var_D8]
0x180025a92  jnb     short loc_180025A9B
0x180025a94  mov     rcx, [rsp+0F8h+var_D0]
0x180025a99  jmp     short loc_180025A60
0x180025a9b  xor     edx, edx
0x180025a9d  lea     rcx, [rsp+0F8h+var_D0]
0x180025aa2  call    ?reset@?$unique_ptr@IU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAI@Z; wistd::unique_ptr<uint,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uint *)
0x180025aa7  nop
0x180025aa8  xor     r8d, r8d
0x180025aab  mov     dl, 1
0x180025aad  mov     rcx, rsi
0x180025ab0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025ab5  mov     eax, r14d
0x180025ab8  jmp     loc_180025D30
0x180025abd  cmp     [rsp+0F8h+var_D0], r13
0x180025ac2  jnz     loc_180025B68
0x180025ac8  cmp     [rsp+0F8h+var_D8], r13d
0x180025acd  jz      loc_180025B68
0x180025ad3  mov     rcx, [rsp+0F8h]; this
0x180025adb  mov     edi, 80070057h
0x180025ae0  mov     r9d, edi; char *
0x180025ae3  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180025aea  mov     edx, 76h ; 'v'; void *
0x180025aef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025af4  nop
0x180025af5  mov     rcx, [rsp+0F8h+var_D0]
0x180025afa  test    rcx, rcx
0x180025afd  jz      short loc_180025B47
0x180025aff  mov     r14d, r13d
0x180025b02  cmp     [rsp+0F8h+var_D8], r13d
0x180025b07  jbe     short loc_180025B47
0x180025b09  mov     eax, r14d
0x180025b0c  lea     rbx, [rax+rax*2]
0x180025b10  mov     rcx, [rcx+rbx*8]; pv
0x180025b14  call    cs:__imp_CoTaskMemFree
0x180025b1b  nop     dword ptr [rax+rax+00h]
0x180025b20  mov     rcx, [rsp+0F8h+var_D0]
0x180025b25  mov     rcx, [rcx+rbx*8+8]; pv
0x180025b2a  call    cs:__imp_CoTaskMemFree
0x180025b31  nop     dword ptr [rax+rax+00h]
0x180025b36  inc     r14d
0x180025b39  cmp     r14d, [rsp+0F8h+var_D8]
0x180025b3e  jnb     short loc_180025B47
0x180025b40  mov     rcx, [rsp+0F8h+var_D0]
0x180025b45  jmp     short loc_180025B09
0x180025b47  xor     edx, edx
0x180025b49  lea     rcx, [rsp+0F8h+var_D0]
0x180025b4e  call    ?reset@?$unique_ptr@IU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAI@Z; wistd::unique_ptr<uint,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uint *)
0x180025b53  nop
0x180025b54  xor     r8d, r8d
0x180025b57  mov     dl, 1
0x180025b59  mov     rcx, rsi
0x180025b5c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025b61  mov     eax, edi
0x180025b63  jmp     loc_180025D30
0x180025b68  mov     rcx, r15
0x180025b6b  call    ?clear@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<ProvPackageInfo>>::clear(void)
0x180025b70  mov     ebx, r13d
0x180025b73  cmp     ebx, [rsp+0F8h+var_D8]
0x180025b77  jnb     loc_180025CB3
0x180025b7d  mov     ecx, 60h ; '`'; Size
0x180025b82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025b87  mov     rdi, rax
0x180025b8a  mov     [rsp+0F8h+var_C0], rax
0x180025b8f  test    rax, rax
0x180025b92  jz      short loc_180025BEA
0x180025b94  lea     rax, [rsp+0F8h+var_B8]
0x180025b99  mov     [rsp+0F8h+var_78], rax
0x180025ba1  mov     ecx, ebx
0x180025ba3  lea     r14, [rcx+rcx*2]
0x180025ba7  mov     rdx, [rsp+0F8h+var_D0]
0x180025bac  mov     rdx, [rdx+r14*8+8]
0x180025bb1  lea     rcx, [rsp+0F8h+var_B8]
0x180025bb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180025bbb  mov     r12, rax
0x180025bbe  mov     rdx, [rsp+0F8h+var_D0]
0x180025bc3  mov     rdx, [rdx+r14*8]
0x180025bc7  lea     rcx, [rsp+0F8h+var_68]
0x180025bcf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180025bd4  nop
0x180025bd5  mov     r8, r12
0x180025bd8  mov     rdx, rax
0x180025bdb  mov     rcx, rdi
0x180025bde  call    ??0ProvPackageInfo@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackageInfo::ProvPackageInfo(std::wstring,std::wstring)
0x180025be3  lea     r12, [rsp+0F8h+var_D0]
0x180025be8  jmp     short loc_180025BED
0x180025bea  mov     rax, r13
0x180025bed  mov     [rsp+0F8h+var_C0], rax
0x180025bf2  test    rax, rax
0x180025bf5  jnz     loc_180025C94
0x180025bfb  mov     rcx, [rsp+0F8h]; this
0x180025c03  mov     r15d, 8007000Eh
0x180025c09  mov     r9d, r15d; char *
0x180025c0c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180025c13  mov     edx, 80h; void *
0x180025c18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c1d  nop
0x180025c1e  lea     rcx, [rsp+0F8h+var_C0]
0x180025c23  call    ?_Delete@?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@AEAAXXZ; std::unique_ptr<ProvPackageInfo>::_Delete(void)
0x180025c28  nop
0x180025c29  cmp     [r12], r13
0x180025c2d  jz      short loc_180025C72
0x180025c2f  lea     r14, [rsp+0F8h+var_D8]
0x180025c34  cmp     [r14], r13d
0x180025c37  jbe     short loc_180025C72
0x180025c39  mov     edi, r13d
0x180025c3c  mov     eax, edi
0x180025c3e  lea     rbx, [rax+rax*2]
0x180025c42  mov     rcx, [r12]
0x180025c46  mov     rcx, [rcx+rbx*8]; pv
0x180025c4a  call    cs:__imp_CoTaskMemFree
0x180025c51  nop     dword ptr [rax+rax+00h]
0x180025c56  mov     rcx, [r12]
0x180025c5a  mov     rcx, [rcx+rbx*8+8]; pv
0x180025c5f  call    cs:__imp_CoTaskMemFree
0x180025c66  nop     dword ptr [rax+rax+00h]
0x180025c6b  inc     edi
0x180025c6d  cmp     edi, [r14]
0x180025c70  jb      short loc_180025C3C
0x180025c72  xor     edx, edx
0x180025c74  lea     rcx, [rsp+0F8h+var_D0]
0x180025c79  call    ?reset@?$unique_ptr@IU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAI@Z; wistd::unique_ptr<uint,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uint *)
0x180025c7e  nop
0x180025c7f  xor     r8d, r8d
0x180025c82  mov     dl, 1
0x180025c84  mov     rcx, rsi
0x180025c87  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025c8c  mov     eax, r15d
0x180025c8f  jmp     loc_180025D30
0x180025c94  lea     rdx, [rsp+0F8h+var_C0]
0x180025c99  mov     rcx, r15
0x180025c9c  call    ??$emplace_back@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@1@@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(std::unique_ptr<ProvPackageInfo> &&)
0x180025ca1  nop
0x180025ca2  lea     rcx, [rsp+0F8h+var_C0]
0x180025ca7  call    ?_Delete@?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@AEAAXXZ; std::unique_ptr<ProvPackageInfo>::_Delete(void)
0x180025cac  inc     ebx
0x180025cae  jmp     loc_180025B73
0x180025cb3  cmp     [r12], r13
0x180025cb7  jz      short loc_180025CFC
0x180025cb9  lea     r14, [rsp+0F8h+var_D8]
0x180025cbe  cmp     [r14], r13d
0x180025cc1  jbe     short loc_180025CFC
0x180025cc3  mov     edi, r13d
0x180025cc6  mov     eax, edi
0x180025cc8  lea     rbx, [rax+rax*2]
0x180025ccc  mov     rcx, [r12]
0x180025cd0  mov     rcx, [rcx+rbx*8]; pv
0x180025cd4  call    cs:__imp_CoTaskMemFree
0x180025cdb  nop     dword ptr [rax+rax+00h]
0x180025ce0  mov     rcx, [r12]
0x180025ce4  mov     rcx, [rcx+rbx*8+8]; pv
0x180025ce9  call    cs:__imp_CoTaskMemFree
0x180025cf0  nop     dword ptr [rax+rax+00h]
0x180025cf5  inc     edi
0x180025cf7  cmp     edi, [r14]
0x180025cfa  jb      short loc_180025CC6
0x180025cfc  xor     edx, edx
0x180025cfe  lea     rcx, [rsp+0F8h+var_D0]
0x180025d03  call    ?reset@?$unique_ptr@IU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAI@Z; wistd::unique_ptr<uint,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uint *)
0x180025d08  nop
0x180025d09  xor     r8d, r8d
0x180025d0c  mov     dl, 1
0x180025d0e  mov     rcx, rsi
0x180025d11  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025d16  xor     eax, eax
0x180025d18  jmp     short loc_180025D30
0x180025d1a  xor     r8d, r8d
0x180025d1d  mov     dl, 1
0x180025d1f  mov     rcx, [rsp+0F8h+var_48]
0x180025d27  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180025d2c  mov     eax, [rsp+0F8h+var_D8]
0x180025d30  mov     rcx, [rsp+0F8h+var_40]
0x180025d38  xor     rcx, rsp; StackCookie
0x180025d3b  call    __security_check_cookie
0x180025d40  add     rsp, 0C0h
0x180025d47  pop     r15
0x180025d49  pop     r14
0x180025d4b  pop     r13
0x180025d4d  pop     r12
0x180025d4f  pop     rdi
0x180025d50  pop     rsi
0x180025d51  pop     rbx
0x180025d52  retn
```
