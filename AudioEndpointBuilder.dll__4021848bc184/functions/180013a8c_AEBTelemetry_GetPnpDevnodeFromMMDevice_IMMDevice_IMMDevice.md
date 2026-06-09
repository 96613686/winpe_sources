# AEBTelemetry::GetPnpDevnodeFromMMDevice(IMMDevice *,IMMDevice * *)

- ea: `0x180013a8c`
- end: `0x180013e0c`
- name: `?GetPnpDevnodeFromMMDevice@AEBTelemetry@@CAJPEAUIMMDevice@@PEAPEAU2@@Z`
- size: `896`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct IMMDevice **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000af84`
- `0x180059c54`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180013a8c`
- `0x180021030`
- `0x180025340`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013afe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013cad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dad`

## string_xrefs

- `0x180013b15`: `avcore\audiocore\server\audioendpointbuilder\dll\aebtelemetry.cpp`
- `0x180013c4b`: `avcore\audiocore\server\audioendpointbuilder\dll\aebtelemetry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall AEBTelemetry::GetPnpDevnodeFromMMDevice(struct IMMDevice *a1, struct IMMDevice **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rbx
  int v7; // eax
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(_QWORD, _QWORD, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, LPVOID *); // rbx
  __int64 (__fastcall *v12)(LPVOID, LPVOID, __int64 *); // rdi
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, struct IMMDevice **)); // rbx
  int ppv; // [rsp+20h] [rbp-40h]
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  int v19[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, struct IMMDevice **); // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v22; // [rsp+50h] [rbp-10h] BYREF
  __int64 v23; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  LPVOID pv; // [rsp+90h] [rbp+30h] BYREF
  __int64 v26; // [rsp+98h] [rbp+38h] BYREF

  *(_QWORD *)v19 = 0;
  v21 = 0;
  v18 = 0;
  v26 = 0;
  v20 = 0;
  v23 = 0;
  pv = 0;
  v22 = 0;
  v4 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &v22);
  v5 = v4;
  if ( v4 >= 0 )
  {
    Activate = a1->lpVtbl->Activate;
    *(_QWORD *)v19 = 0;
    v7 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))Activate)(
           a1,
           &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
           23);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v9 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v19 + 32LL);
      wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v21);
      v7 = v9(*(_QWORD *)v19, 0, &v21);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v10 = v21;
        v11 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v21 + 80LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v7 = v11(v10, &pv);
        v5 = v7;
        if ( v7 >= 0 )
        {
          v12 = *(__int64 (__fastcall **)(LPVOID, LPVOID, __int64 *))(*(_QWORD *)v22 + 40LL);
          v18 = 0;
          v7 = v12(v22, pv, &v18);
          v5 = v7;
          if ( v7 >= 0 )
          {
            v13 = v26;
            v26 = 0;
            if ( v13 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            v7 = wil::com_query_to_nothrow<IPnpInterface,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
                   &v18,
                   (__int64)&v26);
            v5 = v7;
            if ( v7 >= 0 )
            {
              v14 = v26;
              v15 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, struct IMMDevice **)))(*(_QWORD *)v26 + 24LL);
              wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v20);
              v7 = v15(v14, &v20);
              v5 = v7;
              if ( v7 >= 0 )
              {
                v7 = (**v20)(v20, &GUID_d666063f_1587_4e43_81f1_b948e807363f, a2);
                v5 = v7;
                if ( v7 >= 0 )
                {
                  if ( pv )
                    CoTaskMemFree(pv);
                  v5 = 0;
                  goto LABEL_34;
                }
                v8 = 591;
              }
              else
              {
                v8 = 588;
              }
            }
            else
            {
              v8 = 585;
            }
          }
          else
          {
            v8 = 582;
          }
        }
        else
        {
          if ( v7 == -2147023728 )
          {
            if ( pv )
              CoTaskMemFree(pv);
            v5 = -2147023728;
            goto LABEL_34;
          }
          v8 = 579;
        }
      }
      else
      {
        v8 = 575;
      }
    }
    else
    {
      v8 = 572;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\aebtelemetry.cpp",
      (const char *)(unsigned int)v7,
      (int)v19);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_34:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v19);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x239,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\aebtelemetry.cpp",
    (const char *)(unsigned int)v4,
    ppv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v22 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  return v5;
}

```

## disassembly

```asm
0x180013a8c  mov     [rsp-18h+arg_0], rbx
0x180013a91  push    rbp
0x180013a92  push    rsi
0x180013a93  push    rdi
0x180013a94  mov     rbp, rsp
0x180013a97  sub     rsp, 60h
0x180013a9b  mov     rsi, rdx
0x180013a9e  mov     rdi, rcx
0x180013aa1  mov     qword ptr [rbp+var_28], 0
0x180013aa9  mov     [rbp+var_18], 0
0x180013ab1  mov     [rbp+var_30], 0
0x180013ab9  mov     [rbp+arg_18], 0
0x180013ac1  mov     [rbp+var_20], 0
0x180013ac9  mov     [rbp+var_8], 0
0x180013ad1  mov     [rbp+pv], 0
0x180013ad9  mov     [rbp+var_10], 0
0x180013ae1  lea     rax, [rbp+var_10]
0x180013ae5  mov     qword ptr [rsp+60h+ppv], rax; int
0x180013aea  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180013af1  xor     edx, edx; pUnkOuter
0x180013af3  lea     r8d, [rdx+17h]; dwClsContext
0x180013af7  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x180013afe  call    cs:__imp_CoCreateInstance
0x180013b04  mov     ebx, eax
0x180013b06  test    eax, eax
0x180013b08  jns     loc_180013BC0
0x180013b0e  mov     rcx, [rbp+18h]; this
0x180013b12  mov     r9d, eax; char *
0x180013b15  lea     r8, aAvcoreAudiocor_17; "avcore\\audiocore\\server\\audioendpoin"...
0x180013b1c  mov     edx, 239h; void *
0x180013b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b26  nop
0x180013b27  mov     rcx, [rbp+pv]; pv
0x180013b2b  test    rcx, rcx
0x180013b2e  jz      short loc_180013B37
0x180013b30  call    cs:__imp_CoTaskMemFree
0x180013b36  nop
0x180013b37  mov     rcx, [rbp+var_20]
0x180013b3b  test    rcx, rcx
0x180013b3e  jz      short loc_180013B4D
0x180013b40  mov     rax, [rcx]
0x180013b43  mov     rax, [rax+10h]
0x180013b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b4c  nop
0x180013b4d  mov     rcx, [rbp+arg_18]
0x180013b51  test    rcx, rcx
0x180013b54  jz      short loc_180013B63
0x180013b56  mov     rax, [rcx]
0x180013b59  mov     rax, [rax+10h]
0x180013b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b62  nop
0x180013b63  mov     rcx, [rbp+var_30]
0x180013b67  test    rcx, rcx
0x180013b6a  jz      short loc_180013B79
0x180013b6c  mov     rax, [rcx]
0x180013b6f  mov     rax, [rax+10h]
0x180013b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b78  nop
0x180013b79  mov     rcx, [rbp+var_18]
0x180013b7d  test    rcx, rcx
0x180013b80  jz      short loc_180013B8F
0x180013b82  mov     rax, [rcx]
0x180013b85  mov     rax, [rax+10h]
0x180013b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b8e  nop
0x180013b8f  mov     rcx, qword ptr [rbp+var_28]
0x180013b93  test    rcx, rcx
0x180013b96  jz      short loc_180013BA5
0x180013b98  mov     rax, [rcx]
0x180013b9b  mov     rax, [rax+10h]
0x180013b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ba4  nop
0x180013ba5  mov     rcx, [rbp+var_10]
0x180013ba9  test    rcx, rcx
0x180013bac  jz      short loc_180013BBB
0x180013bae  mov     rax, [rcx]
0x180013bb1  mov     rax, [rax+10h]
0x180013bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bba  nop
0x180013bbb  jmp     loc_180013DFA
0x180013bc0  mov     rax, [rdi]
0x180013bc3  mov     rbx, [rax+18h]
0x180013bc7  mov     rcx, qword ptr [rbp+var_28]
0x180013bcb  mov     qword ptr [rbp+var_28], 0
0x180013bd3  test    rcx, rcx
0x180013bd6  jz      short loc_180013BE5
0x180013bd8  mov     rax, [rcx]
0x180013bdb  mov     rax, [rax+10h]
0x180013bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013be4  nop
0x180013be5  lea     rax, [rbp+var_28]
0x180013be9  mov     qword ptr [rsp+60h+ppv], rax; int
0x180013bee  xor     r9d, r9d
0x180013bf1  lea     r8d, [r9+17h]
0x180013bf5  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180013bfc  mov     rcx, rdi
0x180013bff  mov     rax, rbx
0x180013c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c07  mov     ebx, eax
0x180013c09  test    eax, eax
0x180013c0b  jns     short loc_180013C14
0x180013c0d  mov     edx, 23Ch
0x180013c12  jmp     short loc_180013C44
0x180013c14  mov     rdi, qword ptr [rbp+var_28]
0x180013c18  mov     rax, [rdi]
0x180013c1b  mov     rbx, [rax+20h]
0x180013c1f  lea     rcx, [rbp+var_18]
0x180013c23  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180013c28  lea     r8, [rbp+var_18]
0x180013c2c  xor     edx, edx
0x180013c2e  mov     rcx, rdi
0x180013c31  mov     rax, rbx
0x180013c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c39  mov     ebx, eax
0x180013c3b  test    eax, eax
0x180013c3d  jns     short loc_180013C70
0x180013c3f  mov     edx, 23Fh; void *
0x180013c44  mov     rcx, [rbp+18h]; this
0x180013c48  mov     r9d, eax; char *
0x180013c4b  lea     r8, aAvcoreAudiocor_17; "avcore\\audiocore\\server\\audioendpoin"...
0x180013c52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c57  nop
0x180013c58  mov     rcx, [rbp+pv]; pv
0x180013c5c  test    rcx, rcx
0x180013c5f  jz      loc_180013DB5
0x180013c65  call    cs:__imp_CoTaskMemFree
0x180013c6b  jmp     loc_180013DB5
0x180013c70  mov     rdi, [rbp+var_18]
0x180013c74  mov     rax, [rdi]
0x180013c77  mov     rbx, [rax+50h]
0x180013c7b  xor     edx, edx
0x180013c7d  lea     rcx, [rbp+pv]
0x180013c81  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013c86  lea     rdx, [rbp+pv]
0x180013c8a  mov     rcx, rdi
0x180013c8d  mov     rax, rbx
0x180013c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c95  mov     ebx, eax
0x180013c97  test    eax, eax
0x180013c99  jns     short loc_180013CC1
0x180013c9b  mov     edi, 80070490h
0x180013ca0  cmp     eax, edi
0x180013ca2  jnz     short loc_180013CBA
0x180013ca4  mov     rcx, [rbp+pv]; pv
0x180013ca8  test    rcx, rcx
0x180013cab  jz      short loc_180013CB3
0x180013cad  call    cs:__imp_CoTaskMemFree
0x180013cb3  mov     ebx, edi
0x180013cb5  jmp     loc_180013DB5
0x180013cba  mov     edx, 243h
0x180013cbf  jmp     short loc_180013C44
0x180013cc1  mov     rbx, [rbp+var_10]
0x180013cc5  mov     rax, [rbx]
0x180013cc8  mov     rdi, [rax+28h]
0x180013ccc  mov     rcx, [rbp+var_30]
0x180013cd0  mov     [rbp+var_30], 0
0x180013cd8  test    rcx, rcx
0x180013cdb  jz      short loc_180013CEA
0x180013cdd  mov     rdx, [rcx]
0x180013ce0  mov     rax, [rdx+10h]
0x180013ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ce9  nop
0x180013cea  lea     r8, [rbp+var_30]
0x180013cee  mov     rdx, [rbp+pv]
0x180013cf2  mov     rcx, rbx
0x180013cf5  mov     rax, rdi
0x180013cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cfd  mov     ebx, eax
0x180013cff  test    eax, eax
0x180013d01  jns     short loc_180013D0D
0x180013d03  mov     edx, 246h
0x180013d08  jmp     loc_180013C44
0x180013d0d  mov     rcx, [rbp+arg_18]
0x180013d11  mov     [rbp+arg_18], 0
0x180013d19  test    rcx, rcx
0x180013d1c  jz      short loc_180013D2B
0x180013d1e  mov     rax, [rcx]
0x180013d21  mov     rax, [rax+10h]
0x180013d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d2a  nop
0x180013d2b  lea     rdx, [rbp+arg_18]
0x180013d2f  lea     rcx, [rbp+var_30]
0x180013d33  call    ??$com_query_to_nothrow@UIPnpInterface@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIPnpInterface@@@Z; wil::com_query_to_nothrow<IPnpInterface,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IPnpInterface * *)
0x180013d38  mov     ebx, eax
0x180013d3a  test    eax, eax
0x180013d3c  jns     short loc_180013D48
0x180013d3e  mov     edx, 249h
0x180013d43  jmp     loc_180013C44
0x180013d48  mov     rdi, [rbp+arg_18]
0x180013d4c  mov     rax, [rdi]
0x180013d4f  mov     rbx, [rax+18h]
0x180013d53  lea     rcx, [rbp+var_20]
0x180013d57  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180013d5c  lea     rdx, [rbp+var_20]
0x180013d60  mov     rcx, rdi
0x180013d63  mov     rax, rbx
0x180013d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d6b  mov     ebx, eax
0x180013d6d  test    eax, eax
0x180013d6f  jns     short loc_180013D7B
0x180013d71  mov     edx, 24Ch
0x180013d76  jmp     loc_180013C44
0x180013d7b  mov     rcx, [rbp+var_20]
0x180013d7f  mov     rax, [rcx]
0x180013d82  mov     r8, rsi
0x180013d85  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x180013d8c  mov     rax, [rax]
0x180013d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d94  mov     ebx, eax
0x180013d96  test    eax, eax
0x180013d98  jns     short loc_180013DA4
0x180013d9a  mov     edx, 24Fh
0x180013d9f  jmp     loc_180013C44
0x180013da4  mov     rcx, [rbp+pv]; pv
0x180013da8  test    rcx, rcx
0x180013dab  jz      short loc_180013DB3
0x180013dad  call    cs:__imp_CoTaskMemFree
0x180013db3  xor     ebx, ebx
0x180013db5  lea     rcx, [rbp+var_8]
0x180013db9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013dbe  nop
0x180013dbf  lea     rcx, [rbp+var_20]
0x180013dc3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013dc8  nop
0x180013dc9  lea     rcx, [rbp+arg_18]
0x180013dcd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013dd2  nop
0x180013dd3  lea     rcx, [rbp+var_30]
0x180013dd7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013ddc  nop
0x180013ddd  lea     rcx, [rbp+var_18]
0x180013de1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013de6  nop
0x180013de7  lea     rcx, [rbp+var_28]
0x180013deb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013df0  nop
0x180013df1  lea     rcx, [rbp+var_10]
0x180013df5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013dfa  mov     eax, ebx
0x180013dfc  mov     rbx, [rsp+60h+arg_0]
0x180013e04  add     rsp, 60h
0x180013e08  pop     rdi
0x180013e09  pop     rsi
0x180013e0a  pop     rbp
0x180013e0b  retn
```
