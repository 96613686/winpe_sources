# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x180004220`
- end: `0x1800042b2`
- name: `?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `146`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800029f0`
- `0x180002ce0`
- `0x180003130`
- `0x1800032d0`
- `0x1800042c0`
- `0x180004430`

## callees

- `0x180004220`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
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
    v3 = *(unsigned int *)(a1 + 36);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 36), a2, v3) );
  v4 = v3 - 1;
  v5 = *(_DWORD *)(a1 + 56) & 4;
  if ( (_DWORD)v3 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1, v3, 0x7FFFFFFF);
    if ( v5 && Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        a2,
        v3,
        v2);
  }
  else if ( !v5 && (_DWORD)v3 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
  {
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
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
0x180004220  mov     [rsp+arg_0], rbx
0x180004225  push    rdi
0x180004226  sub     rsp, 20h
0x18000422a  mov     r9d, 7FFFFFFFh
0x180004230  jmp     short loc_180004240
0x180004232  lea     edx, [r8-1]
0x180004236  mov     eax, r8d
0x180004239  lock cmpxchg [rcx+24h], edx
0x18000423e  jz      short loc_180004249
0x180004240  mov     r8d, [rcx+24h]
0x180004244  cmp     r8d, r9d
0x180004247  jnz     short loc_180004232
0x180004249  mov     ebx, [rcx+38h]
0x18000424c  lea     edi, [r8-1]
0x180004250  and     ebx, 4
0x180004253  test    edi, edi
0x180004255  jnz     short loc_180004284
0x180004257  test    rcx, rcx
0x18000425a  jz      short loc_18000426B
0x18000425c  mov     rax, [rcx]
0x18000425f  lea     edx, [rdi+1]
0x180004262  mov     rax, [rax+38h]
0x180004266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000426b  test    ebx, ebx
0x18000426d  jz      short loc_1800042A5
0x18000426f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004276  test    rcx, rcx
0x180004279  jz      short loc_1800042A5
0x18000427b  mov     rax, [rcx]
0x18000427e  mov     rax, [rax+10h]
0x180004282  jmp     short loc_1800042A0
0x180004284  test    ebx, ebx
0x180004286  jnz     short loc_1800042A5
0x180004288  cmp     edi, 1
0x18000428b  jnz     short loc_1800042A5
0x18000428d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004294  test    rcx, rcx
0x180004297  jz      short loc_1800042A5
0x180004299  mov     rdx, [rcx]
0x18000429c  mov     rax, [rdx+10h]
0x1800042a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a5  mov     rbx, [rsp+28h+arg_0]
0x1800042aa  mov     eax, edi
0x1800042ac  add     rsp, 20h
0x1800042b0  pop     rdi
0x1800042b1  retn
```
