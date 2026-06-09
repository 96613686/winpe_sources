# GenerateEndpointFriendlyName(int,ENDPOINT_DESCRIPTOR *)

- ea: `0x180022948`
- end: `0x180022afc`
- name: `?GenerateEndpointFriendlyName@@YAJHPEAUENDPOINT_DESCRIPTOR@@@Z`
- size: `436`
- prototype: `int(int, struct ENDPOINT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b790`

## callees

- `0x180006b0c`
- `0x180009650`
- `0x18000fa80`
- `0x18000fb60`
- `0x180010da8`
- `0x18001baa0`
- `0x180022948`
- `0x180022b04`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180022a8b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180022a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800229c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800229c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ae3`

## string_xrefs

- `0x180022997`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180022a4d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GenerateEndpointFriendlyName(int a1, struct ENDPOINT_DESCRIPTOR *a2)
{
  __int64 v3; // r14
  int v4; // eax
  int v5; // ebx
  __int64 v7; // rdi
  int (__fastcall *v8)(__int64, LPVOID *); // rbx
  void **cotaskmem_string_nothrow; // rax
  __int64 v10; // rdx
  LPVOID v11; // rax
  void *v12; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  LPVOID pv; // [rsp+58h] [rbp+38h] BYREF
  __int64 v16; // [rsp+60h] [rbp+40h] BYREF
  LPVOID v17; // [rsp+68h] [rbp+48h] BYREF

  v3 = a1;
  pv = 0;
  v16 = 0;
  if ( *((_DWORD *)a2 + 57) == 1 )
    goto LABEL_10;
  v16 = 0;
  v4 = wil::com_query_to_nothrow<IPart,IConnector * &>((_QWORD *)a2 + 1, (__int64)&v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DBE,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v4,
      savedregs);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_5;
  }
  v7 = v16;
  v8 = *(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v16 + 24LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  if ( v8(v7, &pv) < 0 || !*(_WORD *)pv )
  {
LABEL_10:
    cotaskmem_string_nothrow = (void **)wil::make_cotaskmem_string_nothrow((wil *)&v17, 0, 0x80u);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pv,
      cotaskmem_string_nothrow);
    if ( v17 )
      CoTaskMemFree(v17);
    if ( !pv )
    {
      v5 = -2147024882;
      v10 = 7624;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v5,
        savedregs);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
LABEL_5:
      if ( pv )
        CoTaskMemFree(pv);
      return (unsigned int)v5;
    }
    if ( !LoadStringW(g_hInstance, *((_DWORD *)&arDescriptorRoots + 12 * v3), (LPWSTR)pv, 128) )
    {
      v5 = StringCchCopyW((unsigned __int16 *)pv, 0x80u, *((const unsigned __int16 **)&arDescriptorRoots + 6 * v3 + 1));
      if ( v5 < 0 )
      {
        v10 = 7632;
        goto LABEL_14;
      }
    }
  }
  v11 = pv;
  v12 = 0;
  pv = 0;
  *((_QWORD *)a2 + 7) = v11;
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v12 = pv;
  }
  if ( v12 )
    CoTaskMemFree(v12);
  return 0;
}

```

## disassembly

```asm
0x180022948  mov     [rsp-28h+arg_0], rbx
0x18002294d  push    rbp
0x18002294e  push    rsi
0x18002294f  push    rdi
0x180022950  push    r14
0x180022952  push    r15; int
0x180022954  mov     rbp, rsp
0x180022957  sub     rsp, 20h
0x18002295b  mov     rsi, rdx
0x18002295e  movsxd  r14, ecx
0x180022961  xor     r15d, r15d
0x180022964  mov     [rbp+pv], r15
0x180022968  mov     [rbp+arg_10], r15
0x18002296c  cmp     dword ptr [rdx+0E4h], 1
0x180022973  jz      loc_180022A0C
0x180022979  mov     [rbp+arg_10], r15
0x18002297d  lea     rcx, [rdx+8]
0x180022981  lea     rdx, [rbp+arg_10]
0x180022985  call    ??$com_query_to_nothrow@UIPart@@AEAPEAUIConnector@@@wil@@YAJAEAPEAUIConnector@@PEAPEAUIPart@@@Z; wil::com_query_to_nothrow<IPart,IConnector * &>(IConnector * &,IPart * *)
0x18002298a  mov     ebx, eax
0x18002298c  test    eax, eax
0x18002298e  jns     short loc_1800229D5
0x180022990  mov     rcx, [rbp+28h]; this
0x180022994  mov     r9d, eax; char *
0x180022997  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002299e  mov     edx, 1DBEh; void *
0x1800229a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800229a8  nop
0x1800229a9  mov     rcx, [rbp+arg_10]
0x1800229ad  test    rcx, rcx
0x1800229b0  jz      short loc_1800229BF
0x1800229b2  mov     rax, [rcx]
0x1800229b5  mov     rax, [rax+10h]
0x1800229b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229be  nop
0x1800229bf  mov     rcx, [rbp+pv]; pv
0x1800229c3  test    rcx, rcx
0x1800229c6  jz      short loc_1800229CE
0x1800229c8  call    cs:__imp_CoTaskMemFree
0x1800229ce  mov     eax, ebx
0x1800229d0  jmp     loc_180022AEB
0x1800229d5  mov     rdi, [rbp+arg_10]
0x1800229d9  mov     rax, [rdi]
0x1800229dc  mov     rbx, [rax+18h]
0x1800229e0  xor     edx, edx
0x1800229e2  lea     rcx, [rbp+pv]
0x1800229e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800229eb  lea     rdx, [rbp+pv]
0x1800229ef  mov     rcx, rdi
0x1800229f2  mov     rax, rbx
0x1800229f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229fa  test    eax, eax
0x1800229fc  js      short loc_180022A0C
0x1800229fe  mov     rax, [rbp+pv]
0x180022a02  cmp     [rax], r15w
0x180022a06  jnz     loc_180022AB3
0x180022a0c  mov     edi, 80h
0x180022a11  mov     r8d, edi; unsigned __int64
0x180022a14  xor     edx, edx; unsigned __int16 *
0x180022a16  lea     rcx, [rbp+arg_18]; this
0x180022a1a  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180022a1f  mov     rdx, rax
0x180022a22  lea     rcx, [rbp+pv]
0x180022a26  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180022a2b  mov     rcx, [rbp+arg_18]; pv
0x180022a2f  test    rcx, rcx
0x180022a32  jz      short loc_180022A3A
0x180022a34  call    cs:__imp_CoTaskMemFree
0x180022a3a  mov     r8, [rbp+pv]; lpBuffer
0x180022a3e  test    r8, r8
0x180022a41  jnz     short loc_180022A6F
0x180022a43  mov     ebx, 8007000Eh
0x180022a48  mov     edx, 1DC8h; void *
0x180022a4d  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180022a54  mov     r9d, ebx; char *
0x180022a57  mov     rcx, [rbp+28h]; this
0x180022a5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a60  nop
0x180022a61  lea     rcx, [rbp+arg_10]
0x180022a65  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180022a6a  jmp     loc_1800229BF
0x180022a6f  lea     rbx, [r14+r14*2]
0x180022a73  add     rbx, rbx
0x180022a76  lea     r14, ?arDescriptorRoots@@3QBUENDPOINT_FORMFACTOR_DESC@@B; ENDPOINT_FORMFACTOR_DESC const near * const arDescriptorRoots
0x180022a7d  mov     r9d, edi; cchBufferMax
0x180022a80  mov     edx, [r14+rbx*8]; uID
0x180022a84  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180022a8b  call    cs:__imp_LoadStringW
0x180022a91  test    eax, eax
0x180022a93  jnz     short loc_180022AB3
0x180022a95  mov     r8, [r14+rbx*8+8]; unsigned __int16 *
0x180022a9a  mov     rdx, rdi; unsigned __int64
0x180022a9d  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180022aa1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022aa6  mov     ebx, eax
0x180022aa8  test    eax, eax
0x180022aaa  jns     short loc_180022AB3
0x180022aac  mov     edx, 1DD0h
0x180022ab1  jmp     short loc_180022A4D
0x180022ab3  mov     rax, [rbp+pv]
0x180022ab7  mov     rcx, r15
0x180022aba  mov     [rbp+pv], rcx
0x180022abe  mov     [rsi+38h], rax
0x180022ac2  mov     rdx, [rbp+arg_10]
0x180022ac6  test    rdx, rdx
0x180022ac9  jz      short loc_180022ADE
0x180022acb  mov     rax, [rdx]
0x180022ace  mov     rcx, rdx
0x180022ad1  mov     rax, [rax+10h]
0x180022ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ada  mov     rcx, [rbp+pv]; pv
0x180022ade  test    rcx, rcx
0x180022ae1  jz      short loc_180022AE9
0x180022ae3  call    cs:__imp_CoTaskMemFree
0x180022ae9  xor     eax, eax
0x180022aeb  mov     rbx, [rsp+20h+arg_0]
0x180022af0  add     rsp, 20h
0x180022af4  pop     r15
0x180022af6  pop     r14
0x180022af8  pop     rdi
0x180022af9  pop     rsi
0x180022afa  pop     rbp
0x180022afb  retn
```
