# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release(void)

- ea: `0x18001df60`
- end: `0x18001dfc2`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dfd0`

## callees

- `0x18001df60`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 5);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 5, v2 - 1, v2) );
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
0x18001df60  push    rbx
0x18001df62  sub     rsp, 20h
0x18001df66  mov     r9d, 7FFFFFFFh
0x18001df6c  jmp     short loc_18001DF7C
0x18001df6e  lea     edx, [r8-1]
0x18001df72  mov     eax, r8d
0x18001df75  lock cmpxchg [rcx+14h], edx
0x18001df7a  jz      short loc_18001DF85
0x18001df7c  mov     r8d, [rcx+14h]
0x18001df80  cmp     r8d, r9d
0x18001df83  jnz     short loc_18001DF6E
0x18001df85  lea     ebx, [r8-1]
0x18001df89  test    ebx, ebx
0x18001df8b  jnz     short loc_18001DFB9
0x18001df8d  test    rcx, rcx
0x18001df90  jz      short loc_18001DFA1
0x18001df92  mov     rax, [rcx]
0x18001df95  lea     edx, [rbx+1]
0x18001df98  mov     rax, [rax+20h]
0x18001df9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001dfa8  test    rcx, rcx
0x18001dfab  jz      short loc_18001DFB9
0x18001dfad  mov     rdx, [rcx]
0x18001dfb0  mov     rax, [rdx+10h]
0x18001dfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfb9  mov     eax, ebx
0x18001dfbb  add     rsp, 20h
0x18001dfbf  pop     rbx
0x18001dfc0  retn
```
