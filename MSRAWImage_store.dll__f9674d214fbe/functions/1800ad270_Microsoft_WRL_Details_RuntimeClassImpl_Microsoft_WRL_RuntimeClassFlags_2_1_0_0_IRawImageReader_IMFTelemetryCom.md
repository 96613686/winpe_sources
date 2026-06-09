# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x1800ad270`
- end: `0x1800ad2c0`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `80`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a444c`
- `0x1800a525c`
- `0x1800a9850`
- `0x1800ad2d0`
- `0x1800ad2e0`
- `0x1800af770`

## callees

- `0x180096d20`
- `0x1800ad270`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 52), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 72LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x1800ad270  push    rbx
0x1800ad272  sub     rsp, 20h
0x1800ad276  mov     r10, rcx
0x1800ad279  add     rcx, 34h ; '4'; this
0x1800ad27d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x1800ad282  mov     ebx, eax
0x1800ad284  test    eax, eax
0x1800ad286  jnz     short loc_1800AD2B7
0x1800ad288  test    r10, r10
0x1800ad28b  jz      short loc_1800AD29F
0x1800ad28d  mov     rdx, [r10]
0x1800ad290  mov     rcx, r10
0x1800ad293  mov     rax, [rdx+48h]
0x1800ad297  lea     edx, [rbx+1]
0x1800ad29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad29f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800ad2a6  test    rcx, rcx
0x1800ad2a9  jz      short loc_1800AD2B7
0x1800ad2ab  mov     rax, [rcx]
0x1800ad2ae  mov     rax, [rax+10h]
0x1800ad2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad2b7  mov     eax, ebx
0x1800ad2b9  add     rsp, 20h
0x1800ad2bd  pop     rbx
0x1800ad2be  retn
```
