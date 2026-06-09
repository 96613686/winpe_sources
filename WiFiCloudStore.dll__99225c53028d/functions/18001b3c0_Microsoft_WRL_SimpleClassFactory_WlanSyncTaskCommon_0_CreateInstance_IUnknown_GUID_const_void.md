# Microsoft::WRL::SimpleClassFactory<WlanSyncTaskCommon,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001b3c0`
- end: `0x18001b49b`
- name: `?CreateInstance@?$SimpleClassFactory@VWlanSyncTaskCommon@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006b88`
- `0x18001b3c0`
- `0x18001b4a4`
- `0x18001b550`
- `0x18001b5d4`
- `0x18002a448`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001b491`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001b491`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<WlanSyncTaskCommon,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  int v8; // edi
  void *v9; // rbx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  if ( !a2 )
  {
    v11 = 0;
    v6 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>((__int64)v6);
      *v7 = &WlanSyncTaskCommon::`vftable'{for `ITaskHandler'};
      v7[1] = &WlanSyncTaskCommon::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      v8 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>>(
             (__int64)v7,
             (__int64)&GUID_00000000_0000_0000_c000_000000000046,
             (void **)&v11);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(v7);
      if ( v8 >= 0 )
      {
        v9 = v11;
        v8 = (**v11)(v11, a3, a4);
        if ( v9 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
        return (unsigned int)v8;
      }
    }
    else
    {
      v8 = -2147024882;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
    return (unsigned int)v8;
  }
  RoOriginateError(2147746064LL, 0);
  return 2147746064LL;
}

```

## disassembly

```asm
0x18001b3c0  push    rbx
0x18001b3c2  push    rbp
0x18001b3c3  push    rsi
0x18001b3c4  push    rdi
0x18001b3c5  sub     rsp, 28h
0x18001b3c9  mov     rsi, r9
0x18001b3cc  mov     rbp, r8
0x18001b3cf  mov     qword ptr [r9], 0
0x18001b3d6  test    rdx, rdx
0x18001b3d9  jnz     loc_18001B488
0x18001b3df  mov     [rsp+48h+arg_8], rdx
0x18001b3e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b3eb  mov     ecx, 30h ; '0'; unsigned __int64
0x18001b3f0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b3f5  mov     rbx, rax
0x18001b3f8  test    rax, rax
0x18001b3fb  jz      short loc_18001B477
0x18001b3fd  mov     rcx, rax
0x18001b400  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITaskHandler@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler,Microsoft::WRL::FtmBase>(void)
0x18001b405  lea     rax, ??_7WlanSyncTaskCommon@@6BITaskHandler@@@; const WlanSyncTaskCommon::`vftable'{for `ITaskHandler'}
0x18001b40c  mov     [rbx], rax
0x18001b40f  lea     rax, ??_7WlanSyncTaskCommon@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const WlanSyncTaskCommon::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001b416  mov     [rbx+8], rax
0x18001b41a  lea     r8, [rsp+48h+arg_8]
0x18001b41f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001b426  mov     rcx, rbx
0x18001b429  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18001b42e  mov     edi, eax
0x18001b430  mov     rcx, rbx
0x18001b433  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(void)
0x18001b438  test    edi, edi
0x18001b43a  js      short loc_18001B47C
0x18001b43c  mov     rbx, [rsp+48h+arg_8]
0x18001b441  mov     rax, [rbx]
0x18001b444  mov     r8, rsi
0x18001b447  mov     rdx, rbp
0x18001b44a  mov     rcx, rbx
0x18001b44d  mov     rax, [rax]
0x18001b450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b455  mov     edi, eax
0x18001b457  test    rbx, rbx
0x18001b45a  jz      short loc_18001B46C
0x18001b45c  mov     rdx, [rbx]
0x18001b45f  mov     rcx, rbx
0x18001b462  mov     rax, [rdx+10h]
0x18001b466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b46b  nop
0x18001b46c  mov     eax, edi
0x18001b46e  add     rsp, 28h
0x18001b472  pop     rdi
0x18001b473  pop     rsi
0x18001b474  pop     rbp
0x18001b475  pop     rbx
0x18001b476  retn
0x18001b477  mov     edi, 8007000Eh
0x18001b47c  lea     rcx, [rsp+48h+arg_8]
0x18001b481  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b486  jmp     short loc_18001B46C
0x18001b488  xor     edx, edx
0x18001b48a  mov     ebx, 80040110h
0x18001b48f  mov     ecx, ebx
0x18001b491  call    cs:__imp_RoOriginateError
0x18001b497  mov     eax, ebx
0x18001b499  jmp     short loc_18001B46E
```
