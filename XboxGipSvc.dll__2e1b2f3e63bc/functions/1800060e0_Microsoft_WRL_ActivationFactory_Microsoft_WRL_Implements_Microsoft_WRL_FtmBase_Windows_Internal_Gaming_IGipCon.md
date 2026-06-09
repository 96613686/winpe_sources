# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x1800060e0`
- end: `0x180006172`
- name: `?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ea0`
- `0x180003050`
- `0x180006180`
- `0x180006190`
- `0x1800061a0`

## callees

- `0x1800060e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // r8
  unsigned int v4; // edi
  int v5; // ebx

  v2 = 0x7FFFFFFF;
  do
  {
    v3 = *(unsigned int *)(a1 + 68);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 68), a2, v3) );
  v4 = v3 - 1;
  v5 = *(_DWORD *)(a1 + 88) & 4;
  if ( (_DWORD)v3 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1, v3, 0x7FFFFFFF);
    if ( v5 && Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                   + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        a2,
        v3,
        v2);
  }
  else if ( !v5 && (_DWORD)v3 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
  {
    (*(void (__fastcall **)(Microsoft::WRL::Details *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                + 16LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
      v3,
      0x7FFFFFFF);
  }
  return v4;
}

```

## disassembly

```asm
0x1800060e0  mov     [rsp+arg_0], rbx
0x1800060e5  push    rdi
0x1800060e6  sub     rsp, 20h
0x1800060ea  mov     r9d, 7FFFFFFFh
0x1800060f0  jmp     short loc_180006100
0x1800060f2  lea     edx, [r8-1]
0x1800060f6  mov     eax, r8d
0x1800060f9  lock cmpxchg [rcx+44h], edx
0x1800060fe  jz      short loc_180006109
0x180006100  mov     r8d, [rcx+44h]
0x180006104  cmp     r8d, r9d
0x180006107  jnz     short loc_1800060F2
0x180006109  mov     ebx, [rcx+58h]
0x18000610c  lea     edi, [r8-1]
0x180006110  and     ebx, 4
0x180006113  test    edi, edi
0x180006115  jnz     short loc_180006144
0x180006117  test    rcx, rcx
0x18000611a  jz      short loc_18000612B
0x18000611c  mov     rax, [rcx]
0x18000611f  lea     edx, [rdi+1]
0x180006122  mov     rax, [rax+38h]
0x180006126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612b  test    ebx, ebx
0x18000612d  jz      short loc_180006165
0x18000612f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006136  test    rcx, rcx
0x180006139  jz      short loc_180006165
0x18000613b  mov     rax, [rcx]
0x18000613e  mov     rax, [rax+10h]
0x180006142  jmp     short loc_180006160
0x180006144  test    ebx, ebx
0x180006146  jnz     short loc_180006165
0x180006148  cmp     edi, 1
0x18000614b  jnz     short loc_180006165
0x18000614d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006154  test    rcx, rcx
0x180006157  jz      short loc_180006165
0x180006159  mov     rdx, [rcx]
0x18000615c  mov     rax, [rdx+10h]
0x180006160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006165  mov     rbx, [rsp+28h+arg_0]
0x18000616a  mov     eax, edi
0x18000616c  add     rsp, 20h
0x180006170  pop     rdi
0x180006171  retn
```
