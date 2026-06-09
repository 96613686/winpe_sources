# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x18000b4b0`
- end: `0x18000b559`
- name: `?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIMemoryManagerStatics@System@Windows@@UIMemoryManagerStatics2@23@UIMemoryManagerStatics3@23@UIMemoryManagerStatics4@23@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `169`
- prototype: `__int64 __fastcall(signed __int32 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800151a0`
- `0x1800151b0`
- `0x1800151c0`
- `0x1800151d0`
- `0x1800151e0`

## callees

- `0x18000b4b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::IMemoryManagerStatics,Windows::System::IMemoryManagerStatics2,Windows::System::IMemoryManagerStatics3,Windows::System::IMemoryManagerStatics4>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v2; // edi
  int v3; // ebx
  void (*v4)(void); // rax

  for ( i = a1[27]; i != 0x7FFFFFFF; i = a1[27] )
  {
    if ( i == _InterlockedCompareExchange(a1 + 27, i - 1, i) )
      break;
  }
  v2 = i - 1;
  v3 = a1[32] & 4;
  if ( i == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(signed __int32 *, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1);
    if ( v3 && Microsoft::WRL::Details::ModuleBase::module_ )
    {
      v4 = *(void (**)(void))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL);
LABEL_9:
      v4();
    }
  }
  else if ( !v3 && i == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
  {
    v4 = *(void (**)(void))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL);
    goto LABEL_9;
  }
  return v2;
}

```

## disassembly

```asm
0x18000b4b0  mov     [rsp+arg_0], rbx
0x18000b4b5  push    rdi
0x18000b4b6  sub     rsp, 20h
0x18000b4ba  mov     r8d, [rcx+6Ch]
0x18000b4be  cmp     r8d, 7FFFFFFFh
0x18000b4c5  jz      short loc_18000B4D5
0x18000b4c7  lea     edx, [r8-1]
0x18000b4cb  mov     eax, r8d
0x18000b4ce  lock cmpxchg [rcx+6Ch], edx
0x18000b4d3  jnz     short loc_18000B543
0x18000b4d5  mov     ebx, [rcx+80h]
0x18000b4db  lea     edi, [r8-1]
0x18000b4df  and     ebx, 4
0x18000b4e2  test    edi, edi
0x18000b4e4  jnz     short loc_18000B525
0x18000b4e6  test    rcx, rcx
0x18000b4e9  jz      short loc_18000B4FC
0x18000b4eb  mov     rax, [rcx]
0x18000b4ee  mov     edx, 1
0x18000b4f3  mov     rax, [rax+38h]
0x18000b4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4fc  test    ebx, ebx
0x18000b4fe  jz      short loc_18000B518
0x18000b500  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b507  test    rcx, rcx
0x18000b50a  jz      short loc_18000B518
0x18000b50c  mov     rdx, [rcx]
0x18000b50f  mov     rax, [rdx+10h]
0x18000b513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b518  mov     rbx, [rsp+28h+arg_0]
0x18000b51d  mov     eax, edi
0x18000b51f  add     rsp, 20h
0x18000b523  pop     rdi
0x18000b524  retn
0x18000b525  test    ebx, ebx
0x18000b527  jnz     short loc_18000B518
0x18000b529  cmp     edi, 1
0x18000b52c  jnz     short loc_18000B518
0x18000b52e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b535  test    rcx, rcx
0x18000b538  jz      short loc_18000B518
0x18000b53a  mov     rax, [rcx]
0x18000b53d  mov     rax, [rax+10h]
0x18000b541  jmp     short loc_18000B513
0x18000b543  mov     r8d, [rcx+6Ch]
0x18000b547  cmp     r8d, 7FFFFFFFh
0x18000b54e  jnz     loc_18000B4C7
0x18000b554  jmp     loc_18000B4D5
```
