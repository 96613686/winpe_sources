# Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::InternalRelease(void)

- ea: `0x18000edd8`
- end: `0x18000ee37`
- name: `?InternalRelease@?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c830`
- `0x1800108b0`

## callees

- `0x18000edd8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::InternalRelease(
        __int64 *a1)
{
  unsigned int v2; // [rsp+20h] [rbp-28h]
  __int64 v3; // [rsp+28h] [rbp-20h]

  v2 = 0;
  v3 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000edd8  mov     [rsp+arg_0], rcx
0x18000eddd  sub     rsp, 48h
0x18000ede1  mov     [rsp+48h+var_28], 0
0x18000ede9  mov     rax, [rsp+48h+arg_0]
0x18000edee  mov     rax, [rax]
0x18000edf1  mov     [rsp+48h+var_20], rax
0x18000edf6  cmp     [rsp+48h+var_20], 0
0x18000edfc  jz      short loc_18000EE2E
0x18000edfe  mov     rax, [rsp+48h+arg_0]
0x18000ee03  mov     qword ptr [rax], 0
0x18000ee0a  mov     rax, [rsp+48h+var_20]
0x18000ee0f  mov     rax, [rax]
0x18000ee12  mov     rax, [rax+10h]
0x18000ee16  mov     [rsp+48h+var_18], rax
0x18000ee1b  mov     rcx, [rsp+48h+var_20]
0x18000ee20  mov     rax, [rsp+48h+var_18]
0x18000ee25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee2a  mov     [rsp+48h+var_28], eax
0x18000ee2e  mov     eax, [rsp+48h+var_28]
0x18000ee32  add     rsp, 48h
0x18000ee36  retn
```
