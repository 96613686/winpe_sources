# FixupRemoteEndpointId(IMMDevice *,ulong,ushort const *,ushort * *)

- ea: `0x180027a10`
- end: `0x180027c20`
- name: `?FixupRemoteEndpointId@@YAJPEAUIMMDevice@@KPEBGPEAPEAG@Z`
- size: `528`
- prototype: `__int64 __fastcall(struct IMMDevice *, __int64, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004b00`
- `0x18003d7a0`
- `0x18003da60`

## callees

- `0x180006b0c`
- `0x180009650`
- `0x18000fa80`
- `0x180010da8`
- `0x180010dd0`
- `0x18001baa0`
- `0x180027a10`
- `0x18003e920`
- `0x180059578`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027be9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027be9`

## string_xrefs

- `0x180027a71`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180027ac4`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180027bcb`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FixupRemoteEndpointId(
        struct IMMDevice *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rdi
  __int64 cotaskmem_string_nothrow; // rax
  unsigned __int16 *v15; // rbx
  int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // rdx
  int v20; // [rsp+20h] [rbp-79h]
  int v21; // [rsp+20h] [rbp-79h]
  unsigned int v22; // [rsp+28h] [rbp-71h]
  __int64 v23; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 v29[32]; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v25 = 0;
  v24 = 0;
  v27 = 0;
  v23 = 0;
  v6 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
         &v23);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67C,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v6,
      v20);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    return v7;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 24LL))(v23, &v24);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = 1662;
LABEL_7:
    v10 = (unsigned int)v8;
    goto LABEL_8;
  }
  v22 = v24;
  v20 = 0;
  v8 = StringCchPrintfW(v29, 0x20u, L"{%x.%x.%x.%08X}.");
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = 1665;
    goto LABEL_7;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v29[v12] );
  do
    ++v11;
  while ( a3[v11] );
  v13 = v12 + v11 + 1;
  v26 = v13;
  cotaskmem_string_nothrow = wil::make_cotaskmem_string_nothrow((wil *)&pv, 0, v13);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v25,
    cotaskmem_string_nothrow);
  if ( pv )
    CoTaskMemFree(pv);
  v15 = v25;
  if ( v25 )
  {
    v16 = StringCchCopyExW(v25, v13, v29, &v27, &v26, v22);
    v17 = v16;
    if ( v16 >= 0 )
    {
      v16 = StringCchCopyW(v27, v26, a3);
      v17 = v16;
      if ( v16 >= 0 )
      {
        *a4 = v15;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        return 0;
      }
      v18 = 1677;
    }
    else
    {
      v18 = 1675;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v16,
      v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    CoTaskMemFree(v15);
    return v17;
  }
  v7 = -2147024882;
  v10 = 2147942414LL;
  v9 = 1671;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
    (const char *)v10,
    v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  return v7;
}

```

## disassembly

```asm
0x180027a10  push    rbp
0x180027a12  push    rbx
0x180027a13  push    rsi
0x180027a14  push    rdi
0x180027a15  push    r14
0x180027a17  push    r15
0x180027a19  lea     rbp, [rsp-2Fh]
0x180027a1e  sub     rsp, 0C8h
0x180027a25  mov     rax, cs:__security_cookie
0x180027a2c  xor     rax, rsp
0x180027a2f  mov     [rbp+57h+var_40], rax
0x180027a33  mov     r14, r9
0x180027a36  mov     rsi, r8
0x180027a39  mov     edi, edx
0x180027a3b  xor     r15d, r15d
0x180027a3e  mov     [rbp+57h+var_A0], r15
0x180027a42  mov     [rbp+57h+var_A8], r15d
0x180027a46  mov     [rbp+57h+var_90], r15
0x180027a4a  mov     [rbp+57h+var_B0], r15
0x180027a4e  mov     rax, [rcx]
0x180027a51  lea     r8, [rbp+57h+var_B0]
0x180027a55  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x180027a5c  mov     rax, [rax]
0x180027a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a64  mov     ebx, eax
0x180027a66  test    eax, eax
0x180027a68  jns     short loc_180027A9E
0x180027a6a  mov     rcx, [rbp+5Fh]; this
0x180027a6e  mov     r9d, eax; char *
0x180027a71  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180027a78  mov     edx, 67Ch; void *
0x180027a7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a82  nop
0x180027a83  mov     rcx, [rbp+57h+var_B0]
0x180027a87  test    rcx, rcx
0x180027a8a  jz      short loc_180027A99
0x180027a8c  mov     rax, [rcx]
0x180027a8f  mov     rax, [rax+10h]
0x180027a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a98  nop
0x180027a99  jmp     loc_180027C02
0x180027a9e  mov     rcx, [rbp+57h+var_B0]
0x180027aa2  mov     rax, [rcx]
0x180027aa5  lea     rdx, [rbp+57h+var_A8]
0x180027aa9  mov     rax, [rax+18h]
0x180027aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ab2  mov     ebx, eax
0x180027ab4  test    eax, eax
0x180027ab6  jns     short loc_180027ADF
0x180027ab8  mov     edx, 67Eh; void *
0x180027abd  mov     r9d, eax; char *
0x180027ac0  mov     rcx, [rbp+5Fh]; this
0x180027ac4  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180027acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ad0  nop
0x180027ad1  lea     rcx, [rbp+57h+var_B0]
0x180027ad5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027ada  jmp     loc_180027C02
0x180027adf  mov     [rsp+0F0h+var_C0], edi
0x180027ae3  mov     eax, [rbp+57h+var_A8]
0x180027ae6  mov     [rsp+0F0h+var_C8], eax; unsigned int
0x180027aea  mov     [rsp+0F0h+var_D0], r15
0x180027aef  mov     r9d, 3
0x180027af5  lea     r8, aXXX08x; "{%x.%x.%x.%08X}."
0x180027afc  lea     edx, [r9+1Dh]; unsigned __int64
0x180027b00  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180027b04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027b09  mov     ebx, eax
0x180027b0b  test    eax, eax
0x180027b0d  jns     short loc_180027B16
0x180027b0f  mov     edx, 681h
0x180027b14  jmp     short loc_180027ABD
0x180027b16  lea     rdx, [rbp+57h+var_80]
0x180027b1a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027b1e  mov     rcx, rax
0x180027b21  inc     rcx
0x180027b24  cmp     [rdx+rcx*2], r15w
0x180027b29  jnz     short loc_180027B21
0x180027b2b  inc     rax
0x180027b2e  cmp     [rsi+rax*2], r15w
0x180027b33  jnz     short loc_180027B2B
0x180027b35  lea     rdi, [rax+1]
0x180027b39  add     rdi, rcx
0x180027b3c  mov     [rbp+57h+var_98], rdi
0x180027b40  mov     r8, rdi; unsigned __int64
0x180027b43  xor     edx, edx; unsigned __int16 *
0x180027b45  lea     rcx, [rbp+57h+pv]; this
0x180027b49  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180027b4e  mov     rdx, rax
0x180027b51  lea     rcx, [rbp+57h+var_A0]
0x180027b55  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180027b5a  mov     rcx, [rbp+57h+pv]; pv
0x180027b5e  test    rcx, rcx
0x180027b61  jz      short loc_180027B69
0x180027b63  call    cs:__imp_CoTaskMemFree
0x180027b69  mov     rbx, [rbp+57h+var_A0]
0x180027b6d  test    rbx, rbx
0x180027b70  jnz     short loc_180027B84
0x180027b72  mov     ebx, 8007000Eh
0x180027b77  mov     r9d, ebx
0x180027b7a  mov     edx, 687h
0x180027b7f  jmp     loc_180027AC0
0x180027b84  lea     rax, [rbp+57h+var_98]
0x180027b88  mov     [rsp+0F0h+var_D0], rax; int
0x180027b8d  lea     r9, [rbp+57h+var_90]; unsigned __int16 **
0x180027b91  lea     r8, [rbp+57h+var_80]; unsigned __int16 *
0x180027b95  mov     rdx, rdi; unsigned __int64
0x180027b98  mov     rcx, rbx; unsigned __int16 *
0x180027b9b  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180027ba0  mov     edi, eax
0x180027ba2  test    eax, eax
0x180027ba4  jns     short loc_180027BAD
0x180027ba6  mov     edx, 68Bh
0x180027bab  jmp     short loc_180027BC8
0x180027bad  mov     r8, rsi; unsigned __int16 *
0x180027bb0  mov     rdx, [rbp+57h+var_98]; unsigned __int64
0x180027bb4  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180027bb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027bbd  mov     edi, eax
0x180027bbf  test    eax, eax
0x180027bc1  jns     short loc_180027BF3
0x180027bc3  mov     edx, 68Dh; void *
0x180027bc8  mov     r9d, eax; char *
0x180027bcb  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180027bd2  mov     rcx, [rbp+5Fh]; this
0x180027bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027bdb  nop
0x180027bdc  lea     rcx, [rbp+57h+var_B0]
0x180027be0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027be5  nop
0x180027be6  mov     rcx, rbx; pv
0x180027be9  call    cs:__imp_CoTaskMemFree
0x180027bef  mov     eax, edi
0x180027bf1  jmp     short loc_180027C04
0x180027bf3  mov     [r14], rbx
0x180027bf6  lea     rcx, [rbp+57h+var_B0]
0x180027bfa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027bff  mov     ebx, r15d
0x180027c02  mov     eax, ebx
0x180027c04  mov     rcx, [rbp+57h+var_40]
0x180027c08  xor     rcx, rsp; StackCookie
0x180027c0b  call    __security_check_cookie
0x180027c10  add     rsp, 0C8h
0x180027c17  pop     r15
0x180027c19  pop     r14
0x180027c1b  pop     rdi
0x180027c1c  pop     rsi
0x180027c1d  pop     rbx
0x180027c1e  pop     rbp
0x180027c1f  retn
```
