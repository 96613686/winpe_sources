# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::Release(void)

- ea: `0x180006f70`
- end: `0x180006fd1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$MixIn@VDiskFolder@@VRfbShellFolderBase@@$00@23@UIResolveShellLink@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007050`
- `0x180009df0`
- `0x180016400`

## callees

- `0x180006f70`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<DiskFolder,RfbShellFolderBase,1>,IResolveShellLink>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 3);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 3, v2 - 1, v2) );
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
0x180006f70  push    rbx
0x180006f72  sub     rsp, 20h
0x180006f76  mov     r9d, 7FFFFFFFh
0x180006f7c  jmp     short loc_180006F8C
0x180006f7e  lea     edx, [r8-1]
0x180006f82  mov     eax, r8d
0x180006f85  lock cmpxchg [rcx+0Ch], edx
0x180006f8a  jz      short loc_180006F95
0x180006f8c  mov     r8d, [rcx+0Ch]
0x180006f90  cmp     r8d, r9d
0x180006f93  jnz     short loc_180006F7E
0x180006f95  lea     ebx, [r8-1]
0x180006f99  test    ebx, ebx
0x180006f9b  jnz     short loc_180006FC9
0x180006f9d  test    rcx, rcx
0x180006fa0  jz      short loc_180006FB1
0x180006fa2  mov     rax, [rcx]
0x180006fa5  lea     edx, [rbx+1]
0x180006fa8  mov     rax, [rax+20h]
0x180006fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fb1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006fb8  test    rcx, rcx
0x180006fbb  jz      short loc_180006FC9
0x180006fbd  mov     rdx, [rcx]
0x180006fc0  mov     rax, [rdx+10h]
0x180006fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc9  mov     eax, ebx
0x180006fcb  add     rsp, 20h
0x180006fcf  pop     rbx
0x180006fd0  retn
```
