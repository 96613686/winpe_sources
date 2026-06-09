# Microsoft::WRL::Details::MakeAndInitialize<StorageUsageReportingTask,IUnknown,>(IUnknown * *)

- ea: `0x18000decc`
- end: `0x18000df8d`
- name: `??$MakeAndInitialize@VStorageUsageReportingTask@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800113b0`

## callees

- `0x180005158`
- `0x18000decc`
- `0x18000fcd0`
- `0x1800100cc`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<StorageUsageReportingTask,IUnknown,>(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // edi
  _QWORD *v6; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v6 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>(v2);
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v3 = &StorageUsageReportingTask::`vftable';
    v3[6] = 0;
    v6 = 0;
    v4 = ((__int64 (__fastcall *)(_QWORD *, GUID *, _QWORD *))StorageUsageReportingTask::`vftable')(
           v3,
           &GUID_00000000_0000_0000_c000_000000000046,
           a1);
    (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(&v6);
  return v4;
}

```

## disassembly

```asm
0x18000decc  mov     [rsp+arg_8], rbx
0x18000ded1  push    rdi
0x18000ded2  sub     rsp, 20h
0x18000ded6  mov     rdi, rcx
0x18000ded9  mov     qword ptr [rcx], 0
0x18000dee0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dee7  mov     ecx, 38h ; '8'; unsigned __int64
0x18000deec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000def1  mov     rbx, rax
0x18000def4  mov     [rsp+28h+arg_0], rax
0x18000def9  test    rax, rax
0x18000defc  jnz     short loc_18000DF05
0x18000defe  mov     edi, 8007000Eh
0x18000df03  jmp     short loc_18000DF76
0x18000df05  mov     rcx, rbx
0x18000df08  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler>(void)
0x18000df0d  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITaskHandler@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITaskHandler>::`vftable'
0x18000df14  mov     [rbx], rcx
0x18000df17  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000df1e  test    rcx, rcx
0x18000df21  jz      short loc_18000DF30
0x18000df23  mov     rax, [rcx]
0x18000df26  mov     rax, [rax+8]
0x18000df2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df2f  nop
0x18000df30  lea     rax, ??_7StorageUsageReportingTask@@6B@; const StorageUsageReportingTask::`vftable'
0x18000df37  mov     [rbx], rax
0x18000df3a  mov     qword ptr [rbx+30h], 0
0x18000df42  mov     [rsp+28h+arg_0], 0
0x18000df4b  mov     r8, rdi
0x18000df4e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000df55  mov     rcx, rbx
0x18000df58  mov     rax, cs:??_7StorageUsageReportingTask@@6B@; const StorageUsageReportingTask::`vftable'
0x18000df5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df64  mov     edi, eax
0x18000df66  mov     rcx, [rbx]
0x18000df69  mov     rax, [rcx+10h]
0x18000df6d  mov     rcx, rbx
0x18000df70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df75  nop
0x18000df76  lea     rcx, [rsp+28h+arg_0]
0x18000df7b  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(void)
0x18000df80  mov     eax, edi
0x18000df82  mov     rbx, [rsp+28h+arg_8]
0x18000df87  add     rsp, 20h
0x18000df8b  pop     rdi
0x18000df8c  retn
```
