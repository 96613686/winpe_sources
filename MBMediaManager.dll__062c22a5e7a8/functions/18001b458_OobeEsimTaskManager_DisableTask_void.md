# OobeEsimTaskManager::DisableTask(void)

- ea: `0x18001b458`
- end: `0x18001b9aa`
- name: `?DisableTask@OobeEsimTaskManager@@AEAAJXZ`
- size: `1362`
- prototype: `__int64 __fastcall(OobeEsimTaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180036640`

## callees

- `0x180002150`
- `0x180006668`
- `0x18000ad20`
- `0x18001b458`
- `0x18001cb10`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b4dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b4dc`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b495`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b4aa`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b495`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b4aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b511`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b520`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b511`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b520`
- `OLEAUT32!__imp_VariantInit` at `0x18001b477`
- `OLEAUT32!__imp_VariantInit` at `0x18001b477`
- `OLEAUT32!__imp_VariantClear` at `0x18001b570`
- `OLEAUT32!__imp_VariantClear` at `0x18001b68e`
- `OLEAUT32!__imp_VariantClear` at `0x18001b752`
- `OLEAUT32!__imp_VariantClear` at `0x18001b816`
- `OLEAUT32!__imp_VariantClear` at `0x18001b8d1`
- `OLEAUT32!__imp_VariantClear` at `0x18001b968`
- `OLEAUT32!__imp_VariantClear` at `0x18001b570`
- `OLEAUT32!__imp_VariantClear` at `0x18001b68e`
- `OLEAUT32!__imp_VariantClear` at `0x18001b752`
- `OLEAUT32!__imp_VariantClear` at `0x18001b816`
- `OLEAUT32!__imp_VariantClear` at `0x18001b8d1`
- `OLEAUT32!__imp_VariantClear` at `0x18001b968`

## string_xrefs

- `0x18001b4f7`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001b62e`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001b6f2`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001b7b6`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001b871`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001b901`: `Completed Successfully`
- `0x18001b90d`: `OobeEsimTaskManager::DisableTask`

## pseudocode

```c
__int64 __fastcall OobeEsimTaskManager::DisableTask(OobeEsimTaskManager *this)
{
  OLECHAR *v1; // rbx
  OLECHAR *v2; // rdi
  HRESULT v3; // eax
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // rcx
  const char *v7; // r9
  LPVOID v8; // rcx
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rcx
  LPVOID v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  LPVOID v17; // rcx
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  LPVOID v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  LPVOID v25; // rcx
  __int64 v26; // rcx
  LPVOID v27; // rcx
  int ppv; // [rsp+20h] [rbp-D8h]
  OLECHAR *v29; // [rsp+30h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C0h] BYREF
  VARIANTARG v31; // [rsp+50h] [rbp-A8h] BYREF
  VARIANTARG v32; // [rsp+70h] [rbp-88h] BYREF
  VARIANTARG v33; // [rsp+90h] [rbp-68h] BYREF
  VARIANTARG v34; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  LPVOID v36; // [rsp+100h] [rbp+8h] BYREF
  __int64 v37; // [rsp+108h] [rbp+10h] BYREF
  __int64 v38; // [rsp+110h] [rbp+18h] BYREF
  OLECHAR *v39; // [rsp+118h] [rbp+20h] BYREF

  v36 = 0;
  VariantInit(&pvarg);
  v37 = 0;
  v38 = 0;
  v1 = SysAllocString(L"\\Microsoft\\Windows\\WwanSvc");
  v29 = v1;
  v2 = SysAllocString(L"OobeDiscovery");
  v39 = v2;
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v36);
  try
  {
    v4 = v3;
    if ( v3 >= 0 )
    {
      v31 = pvarg;
      v32 = pvarg;
      v33 = pvarg;
      v34 = pvarg;
      v10 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v36 + 80LL))(
              v36,
              &v34,
              &v33,
              &v32);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v36 + 56LL))(v36, v1, &v37);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v18 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v37 + 104LL))(v37, v2, &v38);
          v19 = v18;
          if ( v18 >= 0 )
          {
            v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 88LL))(v38, 0);
            v23 = v22;
            if ( v22 >= 0 )
            {
              MBSettingUXLogging::Info("OobeEsimTaskManager::DisableTask", 0x145u, "Completed Successfully");
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              v26 = v37;
              if ( v37 )
              {
                v37 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              VariantClear(&pvarg);
              v27 = v36;
              if ( v36 )
              {
                v36 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
              }
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x143,
                (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
                (const char *)(unsigned int)v22,
                (int)&v31);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
              v24 = v37;
              if ( v37 )
              {
                v37 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              }
              VariantClear(&pvarg);
              v25 = v36;
              if ( v36 )
              {
                v36 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
              }
              result = v23;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x142,
              (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
              (const char *)(unsigned int)v18,
              (int)&v31);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            v20 = v37;
            if ( v37 )
            {
              v37 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            }
            VariantClear(&pvarg);
            v21 = v36;
            if ( v36 )
            {
              v36 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
            }
            result = v19;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x141,
            (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
            (const char *)(unsigned int)v14,
            (int)&v31);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          v16 = v37;
          if ( v37 )
          {
            v37 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          VariantClear(&pvarg);
          v17 = v36;
          if ( v36 )
          {
            v36 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
          }
          result = v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x140,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
          (const char *)(unsigned int)v10,
          (int)&v31);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v12 = v37;
        if ( v37 )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        VariantClear(&pvarg);
        v13 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
        }
        result = v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v3,
        ppv);
      if ( v2 )
        SysFreeString(v2);
      if ( v1 )
        SysFreeString(v1);
      v5 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      v6 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      VariantClear(&pvarg);
      v8 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      }
      result = v4;
    }
  }
  catch ( ... )
  {
    LODWORD(v36) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x148,
                     (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
                     v7);
    return (unsigned int)v36;
  }
  return result;
}

```

## disassembly

```asm
0x18001b458  mov     rax, rsp
0x18001b45b  mov     [rax+8], rcx
0x18001b45f  push    rbx
0x18001b460  push    rsi
0x18001b461  push    rdi
0x18001b462  push    r14
0x18001b464  sub     rsp, 0D8h
0x18001b46b  xor     r14d, r14d
0x18001b46e  mov     [rax+8], r14
0x18001b472  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18001b477  call    cs:__imp_VariantInit
0x18001b47d  nop
0x18001b47e  mov     [rsp+0F8h+arg_8], r14
0x18001b486  mov     [rsp+0F8h+arg_10], r14
0x18001b48e  lea     rcx, psz; "\\Microsoft\\Windows\\WwanSvc"
0x18001b495  call    cs:__imp_SysAllocString
0x18001b49b  mov     rbx, rax
0x18001b49e  mov     [rsp+0F8h+var_C8], rax
0x18001b4a3  lea     rcx, aOobediscovery; "OobeDiscovery"
0x18001b4aa  call    cs:__imp_SysAllocString
0x18001b4b0  mov     rdi, rax
0x18001b4b3  mov     [rsp+0F8h+arg_18], rax
0x18001b4bb  lea     rax, [rsp+0F8h+arg_0]
0x18001b4c3  mov     qword ptr [rsp+0F8h+ppv], rax; int
0x18001b4c8  lea     r9, IID_ITaskService; riid
0x18001b4cf  xor     edx, edx; pUnkOuter
0x18001b4d1  lea     r8d, [r14+1]; dwClsContext
0x18001b4d5  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001b4dc  call    cs:__imp_CoCreateInstance
0x18001b4e2  mov     esi, eax
0x18001b4e4  test    eax, eax
0x18001b4e6  jns     loc_18001B5A0
0x18001b4ec  mov     rcx, [rsp+0F8h]; this
0x18001b4f4  mov     r9d, eax; char *
0x18001b4f7  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001b4fe  mov     edx, 13Fh; void *
0x18001b503  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b508  nop
0x18001b509  test    rdi, rdi
0x18001b50c  jz      short loc_18001B518
0x18001b50e  mov     rcx, rdi; bstrString
0x18001b511  call    cs:__imp_SysFreeString
0x18001b517  nop
0x18001b518  test    rbx, rbx
0x18001b51b  jz      short loc_18001B527
0x18001b51d  mov     rcx, rbx; bstrString
0x18001b520  call    cs:__imp_SysFreeString
0x18001b526  nop
0x18001b527  mov     rcx, [rsp+0F8h+arg_10]
0x18001b52f  test    rcx, rcx
0x18001b532  jz      short loc_18001B549
0x18001b534  mov     [rsp+0F8h+arg_10], r14
0x18001b53c  mov     rax, [rcx]
0x18001b53f  mov     rax, [rax+10h]
0x18001b543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b548  nop
0x18001b549  mov     rcx, [rsp+0F8h+arg_8]
0x18001b551  test    rcx, rcx
0x18001b554  jz      short loc_18001B56B
0x18001b556  mov     [rsp+0F8h+arg_8], r14
0x18001b55e  mov     rax, [rcx]
0x18001b561  mov     rax, [rax+10h]
0x18001b565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b56a  nop
0x18001b56b  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18001b570  call    cs:__imp_VariantClear
0x18001b576  nop
0x18001b577  mov     rcx, [rsp+0F8h+arg_0]
0x18001b57f  test    rcx, rcx
0x18001b582  jz      short loc_18001B599
0x18001b584  mov     [rsp+0F8h+arg_0], r14
0x18001b58c  mov     rax, [rcx]
0x18001b58f  mov     rax, [rax+10h]
0x18001b593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b598  nop
0x18001b599  mov     eax, esi
0x18001b59b  jmp     loc_18001B99C
0x18001b5a0  mov     rcx, [rsp+0F8h+arg_0]
0x18001b5a8  movups  xmm1, xmmword ptr [rsp+0F8h+pvarg]
0x18001b5ad  movsd   xmm0, qword ptr [rsp+0F8h+pvarg+10h]
0x18001b5b3  movaps  xmmword ptr [rsp+0F8h+var_A8], xmm1
0x18001b5b8  movsd   [rsp+0F8h+var_98], xmm0
0x18001b5be  movaps  [rsp+0F8h+var_88], xmm1
0x18001b5c3  movsd   [rsp+0F8h+var_78], xmm0
0x18001b5cc  movaps  [rsp+0F8h+var_68], xmm1
0x18001b5d4  movsd   [rsp+0F8h+var_58], xmm0
0x18001b5dd  movaps  [rsp+0F8h+var_48], xmm1
0x18001b5e5  movsd   [rsp+0F8h+var_38], xmm0
0x18001b5ee  mov     rax, [rcx]
0x18001b5f1  lea     rdx, [rsp+0F8h+var_A8]
0x18001b5f6  mov     qword ptr [rsp+0F8h+ppv], rdx; int
0x18001b5fb  lea     r9, [rsp+0F8h+var_88]
0x18001b600  lea     r8, [rsp+0F8h+var_68]
0x18001b608  lea     rdx, [rsp+0F8h+var_48]
0x18001b610  mov     rax, [rax+50h]
0x18001b614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b619  mov     esi, eax
0x18001b61b  test    eax, eax
0x18001b61d  jns     loc_18001B6BE
0x18001b623  mov     rcx, [rsp+0F8h]; this
0x18001b62b  mov     r9d, eax; char *
0x18001b62e  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001b635  mov     edx, 140h; void *
0x18001b63a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b63f  nop
0x18001b640  lea     rcx, [rsp+0F8h+arg_18]
0x18001b648  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b64d  nop
0x18001b64e  lea     rcx, [rsp+0F8h+var_C8]
0x18001b653  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b658  nop
0x18001b659  lea     rcx, [rsp+0F8h+arg_10]
0x18001b661  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b666  nop
0x18001b667  mov     rcx, [rsp+0F8h+arg_8]
0x18001b66f  test    rcx, rcx
0x18001b672  jz      short loc_18001B689
0x18001b674  mov     [rsp+0F8h+arg_8], r14
0x18001b67c  mov     rax, [rcx]
0x18001b67f  mov     rax, [rax+10h]
0x18001b683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b688  nop
0x18001b689  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18001b68e  call    cs:__imp_VariantClear
0x18001b694  nop
0x18001b695  mov     rcx, [rsp+0F8h+arg_0]
0x18001b69d  test    rcx, rcx
0x18001b6a0  jz      short loc_18001B6B7
0x18001b6a2  mov     [rsp+0F8h+arg_0], r14
0x18001b6aa  mov     rax, [rcx]
0x18001b6ad  mov     rax, [rax+10h]
0x18001b6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6b6  nop
0x18001b6b7  mov     eax, esi
0x18001b6b9  jmp     loc_18001B99C
0x18001b6be  mov     rcx, [rsp+0F8h+arg_0]
0x18001b6c6  mov     rax, [rcx]
0x18001b6c9  lea     r8, [rsp+0F8h+arg_8]
0x18001b6d1  mov     rdx, rbx
0x18001b6d4  mov     rax, [rax+38h]
0x18001b6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6dd  mov     ebx, eax
0x18001b6df  test    eax, eax
0x18001b6e1  jns     loc_18001B782
0x18001b6e7  mov     rcx, [rsp+0F8h]; this
0x18001b6ef  mov     r9d, eax; char *
0x18001b6f2  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001b6f9  mov     edx, 141h; void *
0x18001b6fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b703  nop
0x18001b704  lea     rcx, [rsp+0F8h+arg_18]
0x18001b70c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b711  nop
0x18001b712  lea     rcx, [rsp+0F8h+var_C8]
0x18001b717  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b71c  nop
0x18001b71d  lea     rcx, [rsp+0F8h+arg_10]
0x18001b725  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b72a  nop
0x18001b72b  mov     rcx, [rsp+0F8h+arg_8]
0x18001b733  test    rcx, rcx
0x18001b736  jz      short loc_18001B74D
0x18001b738  mov     [rsp+0F8h+arg_8], r14
0x18001b740  mov     rax, [rcx]
0x18001b743  mov     rax, [rax+10h]
0x18001b747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b74c  nop
0x18001b74d  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18001b752  call    cs:__imp_VariantClear
0x18001b758  nop
0x18001b759  mov     rcx, [rsp+0F8h+arg_0]
0x18001b761  test    rcx, rcx
0x18001b764  jz      short loc_18001B77B
0x18001b766  mov     [rsp+0F8h+arg_0], r14
0x18001b76e  mov     rax, [rcx]
0x18001b771  mov     rax, [rax+10h]
0x18001b775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b77a  nop
0x18001b77b  mov     eax, ebx
0x18001b77d  jmp     loc_18001B99C
0x18001b782  mov     rcx, [rsp+0F8h+arg_8]
0x18001b78a  mov     rax, [rcx]
0x18001b78d  lea     r8, [rsp+0F8h+arg_10]
0x18001b795  mov     rdx, rdi
0x18001b798  mov     rax, [rax+68h]
0x18001b79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7a1  mov     ebx, eax
0x18001b7a3  test    eax, eax
0x18001b7a5  jns     loc_18001B846
0x18001b7ab  mov     rcx, [rsp+0F8h]; this
0x18001b7b3  mov     r9d, eax; char *
0x18001b7b6  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001b7bd  mov     edx, 142h; void *
0x18001b7c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b7c7  nop
0x18001b7c8  lea     rcx, [rsp+0F8h+arg_18]
0x18001b7d0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b7d5  nop
0x18001b7d6  lea     rcx, [rsp+0F8h+var_C8]
0x18001b7db  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b7e0  nop
0x18001b7e1  lea     rcx, [rsp+0F8h+arg_10]
0x18001b7e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b7ee  nop
0x18001b7ef  mov     rcx, [rsp+0F8h+arg_8]
0x18001b7f7  test    rcx, rcx
0x18001b7fa  jz      short loc_18001B811
0x18001b7fc  mov     [rsp+0F8h+arg_8], r14
0x18001b804  mov     rax, [rcx]
0x18001b807  mov     rax, [rax+10h]
0x18001b80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b810  nop
0x18001b811  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18001b816  call    cs:__imp_VariantClear
0x18001b81c  nop
0x18001b81d  mov     rcx, [rsp+0F8h+arg_0]
0x18001b825  test    rcx, rcx
0x18001b828  jz      short loc_18001B83F
0x18001b82a  mov     [rsp+0F8h+arg_0], r14
0x18001b832  mov     rax, [rcx]
0x18001b835  mov     rax, [rax+10h]
0x18001b839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b83e  nop
0x18001b83f  mov     eax, ebx
0x18001b841  jmp     loc_18001B99C
0x18001b846  mov     rcx, [rsp+0F8h+arg_10]
0x18001b84e  mov     rax, [rcx]
0x18001b851  xor     edx, edx
0x18001b853  mov     rax, [rax+58h]
0x18001b857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b85c  mov     ebx, eax
0x18001b85e  test    eax, eax
0x18001b860  jns     loc_18001B901
0x18001b866  mov     rcx, [rsp+0F8h]; this
0x18001b86e  mov     r9d, eax; char *
0x18001b871  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001b878  mov     edx, 143h; void *
0x18001b87d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b882  nop
0x18001b883  lea     rcx, [rsp+0F8h+arg_18]
0x18001b88b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b890  nop
0x18001b891  lea     rcx, [rsp+0F8h+var_C8]
0x18001b896  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b89b  nop
0x18001b89c  lea     rcx, [rsp+0F8h+arg_10]
0x18001b8a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b8a9  nop
0x18001b8aa  mov     rcx, [rsp+0F8h+arg_8]
0x18001b8b2  test    rcx, rcx
0x18001b8b5  jz      short loc_18001B8CC
0x18001b8b7  mov     [rsp+0F8h+arg_8], r14
0x18001b8bf  mov     rax, [rcx]
0x18001b8c2  mov     rax, [rax+10h]
0x18001b8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8cb  nop
0x18001b8cc  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18001b8d1  call    cs:__imp_VariantClear
0x18001b8d7  nop
0x18001b8d8  mov     rcx, [rsp+0F8h+arg_0]
0x18001b8e0  test    rcx, rcx
0x18001b8e3  jz      short loc_18001B8FA
0x18001b8e5  mov     [rsp+0F8h+arg_0], r14
0x18001b8ed  mov     rax, [rcx]
0x18001b8f0  mov     rax, [rax+10h]
0x18001b8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8f9  nop
0x18001b8fa  mov     eax, ebx
0x18001b8fc  jmp     loc_18001B99C
0x18001b901  lea     r8, aCompletedSucce; "Completed Successfully"
0x18001b908  mov     edx, 145h; unsigned int
0x18001b90d  lea     rcx, aOobeesimtaskma_3; "OobeEsimTaskManager::DisableTask"
0x18001b914  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001b919  nop
0x18001b91a  lea     rcx, [rsp+0F8h+arg_18]
0x18001b922  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b927  nop
0x18001b928  lea     rcx, [rsp+0F8h+var_C8]
0x18001b92d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001b932  nop
0x18001b933  lea     rcx, [rsp+0F8h+arg_10]
0x18001b93b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b940  nop
0x18001b941  mov     rcx, [rsp+0F8h+arg_8]
0x18001b949  test    rcx, rcx
0x18001b94c  jz      short loc_18001B963
0x18001b94e  mov     [rsp+0F8h+arg_8], r14
0x18001b956  mov     rax, [rcx]
0x18001b959  mov     rax, [rax+10h]
0x18001b95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b962  nop
0x18001b963  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18001b968  call    cs:__imp_VariantClear
0x18001b96e  nop
0x18001b96f  mov     rcx, [rsp+0F8h+arg_0]
0x18001b977  test    rcx, rcx
0x18001b97a  jz      short loc_18001B991
0x18001b97c  mov     [rsp+0F8h+arg_0], r14
0x18001b984  mov     rax, [rcx]
0x18001b987  mov     rax, [rax+10h]
  ... truncated ...
```
