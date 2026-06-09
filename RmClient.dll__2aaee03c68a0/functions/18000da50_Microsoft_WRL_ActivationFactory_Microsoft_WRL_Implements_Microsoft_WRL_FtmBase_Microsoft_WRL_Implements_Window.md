# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)

- ea: `0x18000da50`
- end: `0x18000daa9`
- name: `?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIMemoryManagerStatics@System@Windows@@UIMemoryManagerStatics2@23@UIMemoryManagerStatics3@23@UIMemoryManagerStatics4@23@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `89`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014cb0`
- `0x180014cc0`
- `0x180014cd0`
- `0x180014ce0`
- `0x180014cf0`

## callees

- `0x18000da50`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(
        __int64 a1)
{
  signed __int32 v1; // eax
  unsigned int v2; // ebx

  v1 = *(_DWORD *)(a1 + 108);
  if ( v1 == 0x7FFFFFFF )
  {
LABEL_9:
    v2 = 0x7FFFFFFF;
  }
  else
  {
    while ( 1 )
    {
      v2 = v1 + 1;
      if ( v1 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 108), v1 + 1, v1) )
        break;
      v1 = *(_DWORD *)(a1 + 108);
      if ( v1 == 0x7FFFFFFF )
        goto LABEL_9;
    }
  }
  if ( (*(_BYTE *)(a1 + 128) & 4) == 0 && v2 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return v2;
}

```

## disassembly

```asm
0x18000da50  push    rbx
0x18000da52  sub     rsp, 20h
0x18000da56  mov     eax, [rcx+6Ch]
0x18000da59  cmp     eax, 7FFFFFFFh
0x18000da5e  jz      short loc_18000DAA2
0x18000da60  lea     ebx, [rax+1]
0x18000da63  lock cmpxchg [rcx+6Ch], ebx
0x18000da68  jnz     short loc_18000DA98
0x18000da6a  test    byte ptr [rcx+80h], 4
0x18000da71  jnz     short loc_18000DA90
0x18000da73  cmp     ebx, 2
0x18000da76  jnz     short loc_18000DA90
0x18000da78  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000da7f  test    rcx, rcx
0x18000da82  jz      short loc_18000DA90
0x18000da84  mov     rdx, [rcx]
0x18000da87  mov     rax, [rdx+8]
0x18000da8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da90  mov     eax, ebx
0x18000da92  add     rsp, 20h
0x18000da96  pop     rbx
0x18000da97  retn
0x18000da98  mov     eax, [rcx+6Ch]
0x18000da9b  cmp     eax, 7FFFFFFFh
0x18000daa0  jnz     short loc_18000DA60
0x18000daa2  mov     ebx, 7FFFFFFFh
0x18000daa7  jmp     short loc_18000DA6A
```
