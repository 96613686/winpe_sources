# Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskWlanToCDS,WlanSyncTaskWlanToCDS,>(WlanSyncTaskWlanToCDS * *)

- ea: `0x18001f998`
- end: `0x18001fa30`
- name: `??$MakeAndInitialize@VWlanSyncTaskWlanToCDS@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVWlanSyncTaskWlanToCDS@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028748`

## callees

- `0x180012570`
- `0x180014380`
- `0x18001f5f4`
- `0x18001f998`
- `0x180026a50`
- `0x18002a448`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskWlanToCDS,WlanSyncTaskWlanToCDS,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  _QWORD *v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::FtmBase>(v2);
  v5 = v3;
  *v3 = &WlanSyncTaskWlanToCDS::`vftable';
  v6 = 0;
  v3[1] = &WlanSyncTaskCDSToWlan::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'};
  v3[5] = &WlanSyncTaskCDSToWlan::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'};
  Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalAddRef(&v5);
  *a1 = v3;
  Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(&v5);
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(&v6);
  return 0;
}

```

## disassembly

```asm
0x18001f998  mov     [rsp+arg_10], rbx
0x18001f99d  push    rdi
0x18001f99e  sub     rsp, 20h
0x18001f9a2  mov     rdi, rcx
0x18001f9a5  mov     qword ptr [rcx], 0
0x18001f9ac  mov     ecx, 40h ; '@'; unsigned __int64
0x18001f9b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f9b8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f9bd  mov     rbx, rax
0x18001f9c0  test    rax, rax
0x18001f9c3  jnz     short loc_18001F9CC
0x18001f9c5  mov     eax, 8007000Eh
0x18001f9ca  jmp     short loc_18001FA25
0x18001f9cc  mov     rcx, rbx
0x18001f9cf  call    ??0?$RuntimeClass@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::FtmBase>(void)
0x18001f9d4  lea     rax, ??_7WlanSyncTaskWlanToCDS@@6B@; const WlanSyncTaskWlanToCDS::`vftable'
0x18001f9db  mov     [rsp+28h+arg_0], rbx
0x18001f9e0  mov     [rbx], rax
0x18001f9e3  lea     rcx, [rsp+28h+arg_0]
0x18001f9e8  lea     rax, ??_7WlanSyncTaskCDSToWlan@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@@Details@23@@Details@WRL@Microsoft@@@; const WlanSyncTaskCDSToWlan::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'}
0x18001f9ef  mov     [rsp+28h+arg_8], 0
0x18001f9f8  mov     [rbx+8], rax
0x18001f9fc  lea     rax, ??_7WlanSyncTaskCDSToWlan@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@@234@@Details@WRL@Microsoft@@@; const WlanSyncTaskCDSToWlan::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'}
0x18001fa03  mov     [rbx+28h], rax
0x18001fa07  call    ?InternalAddRef@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalAddRef(void)
0x18001fa0c  lea     rcx, [rsp+28h+arg_0]
0x18001fa11  mov     [rdi], rbx
0x18001fa14  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x18001fa19  lea     rcx, [rsp+28h+arg_8]
0x18001fa1e  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x18001fa23  xor     eax, eax
0x18001fa25  mov     rbx, [rsp+28h+arg_10]
0x18001fa2a  add     rsp, 20h
0x18001fa2e  pop     rdi
0x18001fa2f  retn
```
