# AddDeploymentCallbacks(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *)

- ea: `0x1800150f8`
- end: `0x18001514e`
- name: `?AddDeploymentCallbacks@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@23@@Z`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800169b8`
- `0x180017378`

## callees

- `0x1800150f8`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall AddDeploymentCallbacks(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  if ( !a1 )
    return 2147942487LL;
  result = 0;
  if ( !a2 || (result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1), (int)result >= 0) )
  {
    if ( a3 )
      return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 64LL))(a1, a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800150f8  mov     [rsp+arg_0], rbx
0x1800150fd  push    rdi
0x1800150fe  sub     rsp, 20h
0x180015102  mov     rdi, r8
0x180015105  mov     rbx, rcx
0x180015108  test    rcx, rcx
0x18001510b  jnz     short loc_180015114
0x18001510d  mov     eax, 80070057h
0x180015112  jmp     short loc_180015142
0x180015114  xor     eax, eax
0x180015116  test    rdx, rdx
0x180015119  jz      short loc_18001512B
0x18001511b  mov     rax, [rcx]
0x18001511e  mov     rax, [rax+30h]
0x180015122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015127  test    eax, eax
0x180015129  js      short loc_180015142
0x18001512b  test    rdi, rdi
0x18001512e  jz      short loc_180015142
0x180015130  mov     rax, [rbx]
0x180015133  mov     rdx, rdi
0x180015136  mov     rcx, rbx
0x180015139  mov     rax, [rax+40h]
0x18001513d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015142  mov     rbx, [rsp+28h+arg_0]
0x180015147  add     rsp, 20h
0x18001514b  pop     rdi
0x18001514c  retn
```
