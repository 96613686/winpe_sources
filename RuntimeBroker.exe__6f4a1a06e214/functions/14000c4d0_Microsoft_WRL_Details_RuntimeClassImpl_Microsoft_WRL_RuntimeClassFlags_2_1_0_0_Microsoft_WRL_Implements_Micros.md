# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::Release(void)

- ea: `0x14000c4d0`
- end: `0x14000c531`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006580`
- `0x14000a250`
- `0x14000c540`

## callees

- `0x14000c4d0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 15);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 15, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 32LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x14000c4d0  push    rbx
0x14000c4d2  sub     rsp, 20h
0x14000c4d6  mov     r9d, 7FFFFFFFh
0x14000c4dc  jmp     short loc_14000C4EC
0x14000c4de  lea     edx, [r8-1]
0x14000c4e2  mov     eax, r8d
0x14000c4e5  lock cmpxchg [rcx+3Ch], edx
0x14000c4ea  jz      short loc_14000C4F5
0x14000c4ec  mov     r8d, [rcx+3Ch]
0x14000c4f0  cmp     r8d, r9d
0x14000c4f3  jnz     short loc_14000C4DE
0x14000c4f5  lea     ebx, [r8-1]
0x14000c4f9  test    ebx, ebx
0x14000c4fb  jnz     short loc_14000C529
0x14000c4fd  test    rcx, rcx
0x14000c500  jz      short loc_14000C511
0x14000c502  mov     rax, [rcx]
0x14000c505  lea     edx, [rbx+1]
0x14000c508  mov     rax, [rax+20h]
0x14000c50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c511  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000c518  test    rcx, rcx
0x14000c51b  jz      short loc_14000C529
0x14000c51d  mov     rdx, [rcx]
0x14000c520  mov     rax, [rdx+10h]
0x14000c524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c529  mov     eax, ebx
0x14000c52b  add     rsp, 20h
0x14000c52f  pop     rbx
0x14000c530  retn
```
