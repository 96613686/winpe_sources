# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x14000dba0`
- end: `0x14000dbef`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000dc00`

## callees

- `0x14000dba0`
- `0x14000df28`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 44), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x14000dba0  push    rbx
0x14000dba2  sub     rsp, 20h
0x14000dba6  mov     r10, rcx
0x14000dba9  add     rcx, 2Ch ; ','; this
0x14000dbad  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x14000dbb2  mov     ebx, eax
0x14000dbb4  test    eax, eax
0x14000dbb6  jnz     short loc_14000DBE7
0x14000dbb8  test    r10, r10
0x14000dbbb  jz      short loc_14000DBCF
0x14000dbbd  mov     rdx, [r10]
0x14000dbc0  mov     rcx, r10
0x14000dbc3  mov     rax, [rdx+20h]
0x14000dbc7  lea     edx, [rbx+1]
0x14000dbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbcf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000dbd6  test    rcx, rcx
0x14000dbd9  jz      short loc_14000DBE7
0x14000dbdb  mov     rax, [rcx]
0x14000dbde  mov     rax, [rax+10h]
0x14000dbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbe7  mov     eax, ebx
0x14000dbe9  add     rsp, 20h
0x14000dbed  pop     rbx
0x14000dbee  retn
```
