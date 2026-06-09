# ApplicationSpecificEndpointInfo::GetPersistedDefaultAudioEndpoint(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,ushort * *)

- ea: `0x1800153c0`
- end: `0x180015578`
- name: `?GetPersistedDefaultAudioEndpoint@ApplicationSpecificEndpointInfo@@UEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEAPEAG@Z`
- size: `440`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001c74`
- `0x18000a384`
- `0x180015064`
- `0x1800150c0`
- `0x1800153c0`
- `0x18001a3fc`
- `0x1800463e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001543b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001543b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015504`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x180015528`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x180015528`

## pseudocode

```c
__int64 __fastcall ApplicationSpecificEndpointInfo::GetPersistedDefaultAudioEndpoint(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        _QWORD *a4)
{
  LPVOID v8; // rbx
  __int64 v9; // rdx
  __int64 v11; // rdx
  int updated; // eax
  unsigned int v13; // ebx
  LPVOID v14; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  v14 = 0;
  if ( a2 == 1 )
  {
    v11 = *(_QWORD *)(a1 + 8LL * (int)a3 + 96);
    if ( !v11 )
    {
LABEL_4:
      *a4 = v8;
      return 0;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      pv,
      v11,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v14,
      pv);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    v8 = v14;
    if ( !v14 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)0x8007000ELL,
        0);
      return 2147942414LL;
    }
  }
  else
  {
    if ( a2 )
      goto LABEL_4;
    v9 = *(_QWORD *)(a1 + 8LL * (int)a3 + 144);
    if ( !v9 )
      goto LABEL_4;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      pv,
      v9,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v14,
      pv);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    v8 = v14;
    if ( !v14 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)0x8007000ELL,
        0);
      return 2147942414LL;
    }
  }
  pv[0] = 0;
  if ( (int)mmdDevGetMMDeviceFromInterfaceId(v8, pv) >= 0 )
  {
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(pv);
    goto LABEL_4;
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(pv);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v14,
    0);
  updated = ApplicationSpecificEndpointInfo::AttemptToUpdateEndpointInterfaceId(a1, a2, a3, &v14);
  v13 = updated;
  if ( updated >= 0 )
  {
    v8 = v14;
    goto LABEL_4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD6,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
    (const char *)(unsigned int)updated,
    (int)v14);
  if ( v14 )
    CoTaskMemFree(v14);
  return v13;
}

```

## disassembly

```asm
0x1800153c0  push    rbx
0x1800153c2  push    rbp
0x1800153c3  push    rsi
0x1800153c4  push    rdi
0x1800153c5  push    r14
0x1800153c7  sub     rsp, 30h
0x1800153cb  mov     rdi, r9
0x1800153ce  movsxd  rbp, r8d
0x1800153d1  mov     esi, edx
0x1800153d3  mov     r14, rcx
0x1800153d6  xor     ebx, ebx
0x1800153d8  mov     [rsp+58h+var_38], rbx; int
0x1800153dd  cmp     edx, 1
0x1800153e0  jz      short loc_180015407
0x1800153e2  test    edx, edx
0x1800153e4  jnz     short loc_1800153F7
0x1800153e6  mov     rdx, [rcx+rbp*8+90h]
0x1800153ee  test    rdx, rdx
0x1800153f1  jnz     loc_18001547B
0x1800153f7  mov     [rdi], rbx
0x1800153fa  xor     eax, eax
0x1800153fc  add     rsp, 30h
0x180015400  pop     r14
0x180015402  pop     rdi
0x180015403  pop     rsi
0x180015404  pop     rbp
0x180015405  pop     rbx
0x180015406  retn
0x180015407  mov     rdx, [rcx+rbp*8+60h]
0x18001540c  test    rdx, rdx
0x18001540f  jz      short loc_1800153F7
0x180015411  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180015418  lea     rcx, [rsp+58h+pv]
0x18001541d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180015422  lea     rdx, [rsp+58h+pv]
0x180015427  lea     rcx, [rsp+58h+var_38]
0x18001542c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015431  mov     rcx, [rsp+58h+pv]; pv
0x180015436  test    rcx, rcx
0x180015439  jz      short loc_180015441
0x18001543b  call    cs:__imp_CoTaskMemFree
0x180015441  mov     rbx, [rsp+58h+var_38]
0x180015446  test    rbx, rbx
0x180015449  jnz     loc_180015517
0x18001544f  mov     rcx, [rsp+58h]; this
0x180015454  mov     r9d, 8007000Eh; char *
0x18001545a  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180015461  mov     edx, 0BCh; void *
0x180015466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001546b  mov     eax, 8007000Eh
0x180015470  add     rsp, 30h
0x180015474  pop     r14
0x180015476  pop     rdi
0x180015477  pop     rsi
0x180015478  pop     rbp
0x180015479  pop     rbx
0x18001547a  retn
0x18001547b  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180015482  lea     rcx, [rsp+58h+pv]
0x180015487  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001548c  lea     rdx, [rsp+58h+pv]
0x180015491  lea     rcx, [rsp+58h+var_38]
0x180015496  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001549b  mov     rcx, [rsp+58h+pv]; pv
0x1800154a0  test    rcx, rcx
0x1800154a3  jz      short loc_1800154AB
0x1800154a5  call    cs:__imp_CoTaskMemFree
0x1800154ab  mov     rbx, [rsp+58h+var_38]
0x1800154b0  test    rbx, rbx
0x1800154b3  jnz     short loc_180015517
0x1800154b5  mov     rcx, [rsp+58h]; this
0x1800154ba  mov     r9d, 8007000Eh; char *
0x1800154c0  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x1800154c7  mov     edx, 0C4h; void *
0x1800154cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154d1  mov     eax, 8007000Eh
0x1800154d6  add     rsp, 30h
0x1800154da  pop     r14
0x1800154dc  pop     rdi
0x1800154dd  pop     rsi
0x1800154de  pop     rbp
0x1800154df  pop     rbx
0x1800154e0  retn
0x1800154e1  mov     rcx, [rsp+58h]; this
0x1800154e6  mov     r9d, ebx; char *
0x1800154e9  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x1800154f0  mov     edx, 0D6h; void *
0x1800154f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154fa  mov     rcx, [rsp+58h+var_38]; pv
0x1800154ff  test    rcx, rcx
0x180015502  jz      short loc_18001550A
0x180015504  call    cs:__imp_CoTaskMemFree
0x18001550a  mov     eax, ebx
0x18001550c  add     rsp, 30h
0x180015510  pop     r14
0x180015512  pop     rdi
0x180015513  pop     rsi
0x180015514  pop     rbp
0x180015515  pop     rbx
0x180015516  retn
0x180015517  mov     [rsp+58h+pv], 0
0x180015520  lea     rdx, [rsp+58h+pv]
0x180015525  mov     rcx, rbx
0x180015528  call    cs:__imp_mmdDevGetMMDeviceFromInterfaceId
0x18001552e  lea     rcx, [rsp+58h+pv]
0x180015533  test    eax, eax
0x180015535  js      short loc_180015541
0x180015537  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001553c  jmp     loc_1800153F7
0x180015541  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180015546  xor     edx, edx
0x180015548  lea     rcx, [rsp+58h+var_38]
0x18001554d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180015552  lea     r9, [rsp+58h+var_38]
0x180015557  mov     r8d, ebp
0x18001555a  mov     edx, esi
0x18001555c  mov     rcx, r14
0x18001555f  call    ?AttemptToUpdateEndpointInterfaceId@ApplicationSpecificEndpointInfo@@AEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEAPEAG@Z; ApplicationSpecificEndpointInfo::AttemptToUpdateEndpointInterfaceId(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,ushort * *)
0x180015564  mov     ebx, eax
0x180015566  test    eax, eax
0x180015568  js      loc_1800154E1
0x18001556e  mov     rbx, [rsp+58h+var_38]
0x180015573  jmp     loc_1800153F7
```
