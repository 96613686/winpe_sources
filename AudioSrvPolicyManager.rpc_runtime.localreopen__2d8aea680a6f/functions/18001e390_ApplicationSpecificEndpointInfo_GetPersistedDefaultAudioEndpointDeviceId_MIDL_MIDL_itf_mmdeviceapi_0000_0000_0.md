# ApplicationSpecificEndpointInfo::GetPersistedDefaultAudioEndpointDeviceId(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,ushort * *)

- ea: `0x18001e390`
- end: `0x18001e4d2`
- name: `?GetPersistedDefaultAudioEndpointDeviceId@ApplicationSpecificEndpointInfo@@UEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEAPEAG@Z`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001c74`
- `0x18000a384`
- `0x18001e390`
- `0x18003a5fc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e43e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e43e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e446`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x18001e486`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x18001e486`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplicationSpecificEndpointInfo::GetPersistedDefaultAudioEndpointDeviceId(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v5; // eax
  unsigned int v6; // edi
  void *v7; // rcx
  LPVOID v8; // rax
  int v10; // eax
  int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-20h] BYREF
  LPVOID v14[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v16; // [rsp+60h] [rbp+8h] BYREF

  pv = 0;
  v14[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, LPVOID *))(*(_QWORD *)a1 + 32LL))(a1, a2, a3, &pv);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)(unsigned int)v5,
      v11);
    if ( v14[0] )
      CoTaskMemFree(v14[0]);
    if ( pv )
      CoTaskMemFree(pv);
    return v6;
  }
  else
  {
    v7 = pv;
    if ( pv )
    {
      v12 = 0;
      if ( (int)mmdDevGetMMDeviceFromInterfaceId(pv, &v12) >= 0 )
      {
        v16 = 0;
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 48LL))(v12, &v16) >= 0 && v16 == 1 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 40LL))(v12, v14);
          if ( v10 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xFC,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
              (const char *)(unsigned int)v10,
              v11);
        }
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v12);
      v7 = pv;
    }
    v8 = v14[0];
    v14[0] = 0;
    *a4 = v8;
    if ( v7 )
      CoTaskMemFree(v7);
    return 0;
  }
}

```

## disassembly

```asm
0x18001e390  mov     [rsp+arg_8], rbx
0x18001e395  mov     [rsp+arg_10], rsi
0x18001e39a  push    rdi
0x18001e39b  sub     rsp, 50h
0x18001e39f  mov     rbx, r9
0x18001e3a2  xor     esi, esi
0x18001e3a4  mov     [rsp+58h+pv], rsi
0x18001e3a9  mov     [rsp+58h+var_18], rsi
0x18001e3ae  mov     rax, [rcx]
0x18001e3b1  lea     r9, [rsp+58h+pv]
0x18001e3b6  mov     rax, [rax+20h]
0x18001e3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3bf  mov     edi, eax
0x18001e3c1  test    eax, eax
0x18001e3c3  js      short loc_18001E3FF
0x18001e3c5  mov     rcx, [rsp+58h+pv]; pv
0x18001e3ca  test    rcx, rcx
0x18001e3cd  jnz     loc_18001E47C
0x18001e3d3  mov     rax, [rsp+58h+var_18]
0x18001e3d8  mov     [rsp+58h+var_18], rsi
0x18001e3dd  mov     [rbx], rax
0x18001e3e0  test    rcx, rcx
0x18001e3e3  jnz     short loc_18001E3F7
0x18001e3e5  xor     eax, eax
0x18001e3e7  mov     rbx, [rsp+58h+arg_8]
0x18001e3ec  mov     rsi, [rsp+58h+arg_10]
0x18001e3f1  add     rsp, 50h
0x18001e3f5  pop     rdi
0x18001e3f6  retn
0x18001e3f7  call    cs:__imp_CoTaskMemFree
0x18001e3fd  jmp     short loc_18001E3E5
0x18001e3ff  mov     rcx, [rsp+58h]; this
0x18001e404  mov     r9d, edi; char *
0x18001e407  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18001e40e  mov     edx, 0EFh; void *
0x18001e413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e418  mov     rcx, [rsp+58h+var_18]; pv
0x18001e41d  test    rcx, rcx
0x18001e420  jnz     short loc_18001E43E
0x18001e422  mov     rcx, [rsp+58h+pv]; pv
0x18001e427  test    rcx, rcx
0x18001e42a  jnz     short loc_18001E446
0x18001e42c  mov     eax, edi
0x18001e42e  mov     rbx, [rsp+58h+arg_8]
0x18001e433  mov     rsi, [rsp+58h+arg_10]
0x18001e438  add     rsp, 50h
0x18001e43c  pop     rdi
0x18001e43d  retn
0x18001e43e  call    cs:__imp_CoTaskMemFree
0x18001e444  jmp     short loc_18001E422
0x18001e446  call    cs:__imp_CoTaskMemFree
0x18001e44c  jmp     short loc_18001E42C
0x18001e44e  mov     rcx, [rsp+58h+var_28]
0x18001e453  mov     rax, [rcx]
0x18001e456  lea     rdx, [rsp+58h+var_18]
0x18001e45b  mov     rax, [rax+28h]
0x18001e45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e464  test    eax, eax
0x18001e466  js      short loc_18001E4B7
0x18001e468  lea     rcx, [rsp+58h+var_28]
0x18001e46d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001e472  mov     rcx, [rsp+58h+pv]
0x18001e477  jmp     loc_18001E3D3
0x18001e47c  mov     [rsp+58h+var_28], rsi
0x18001e481  lea     rdx, [rsp+58h+var_28]
0x18001e486  call    cs:__imp_mmdDevGetMMDeviceFromInterfaceId
0x18001e48c  test    eax, eax
0x18001e48e  js      short loc_18001E468
0x18001e490  mov     [rsp+58h+arg_0], esi
0x18001e494  mov     rcx, [rsp+58h+var_28]
0x18001e499  mov     rax, [rcx]
0x18001e49c  lea     rdx, [rsp+58h+arg_0]
0x18001e4a1  mov     rax, [rax+30h]
0x18001e4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4aa  test    eax, eax
0x18001e4ac  js      short loc_18001E468
0x18001e4ae  cmp     [rsp+58h+arg_0], 1
0x18001e4b3  jnz     short loc_18001E468
0x18001e4b5  jmp     short loc_18001E44E
0x18001e4b7  mov     rcx, [rsp+58h]; this
0x18001e4bc  mov     r9d, eax; char *
0x18001e4bf  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18001e4c6  mov     edx, 0FCh; void *
0x18001e4cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e4d0  jmp     short loc_18001E468
```
