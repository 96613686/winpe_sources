# FltpCleanupDeviceHintEcp

- ea: `0x18005c3b0`
- end: `0x18005c447`
- name: `FltpCleanupDeviceHintEcp`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bf00`
- `0x18005aa30`
- `0x18005c450`
- `0x18005d2b0`

## callees

- `0x180009f20`
- `0x18005c3b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005c406`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005c406`
- `ntoskrnl!ObfDereferenceObject` at `0x18005c434`
- `ntoskrnl!ObfDereferenceObject` at `0x18005c434`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005c3cc`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005c3cc`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x18005c422`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x18005c422`

## pseudocode

```c
void __fastcall FltpCleanupDeviceHintEcp(struct _ECP_LIST *a1)
{
  unsigned int v1; // eax
  PVOID *v2; // rax
  void *v3; // rcx
  PVOID EcpContext; // [rsp+38h] [rbp+10h] BYREF

  EcpContext = 0;
  v1 = FsRtlRemoveExtraCreateParameter(a1, &GUID_ECP_IO_DEVICE_HINT, &EcpContext, 0);
  if ( (int)FltpDbgStatus(v1, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2340, 0) >= 0 )
  {
    v2 = (PVOID *)EcpContext;
    v3 = (void *)*((_QWORD *)EcpContext + 2);
    if ( v3 )
    {
      ExFreePoolWithTag(v3, 0x68644D46u);
      v2 = (PVOID *)EcpContext;
    }
    if ( *v2 )
    {
      ObfDereferenceObject(*v2);
      v2 = (PVOID *)EcpContext;
    }
    FsRtlFreeExtraCreateParameter(v2);
  }
}

```

## disassembly

```asm
0x18005c3b0  sub     rsp, 28h
0x18005c3b4  xor     r9d, r9d; EcpContextSize
0x18005c3b7  mov     [rsp+28h+EcpContext], 0
0x18005c3c0  lea     r8, [rsp+28h+EcpContext]; EcpContext
0x18005c3c5  lea     rdx, GUID_ECP_IO_DEVICE_HINT; EcpType
0x18005c3cc  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x18005c3d3  nop     dword ptr [rax+rax+00h]
0x18005c3d8  mov     r8d, 924h
0x18005c3de  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005c3e5  mov     ecx, eax
0x18005c3e7  xor     r9d, r9d
0x18005c3ea  call    FltpDbgStatus
0x18005c3ef  test    eax, eax
0x18005c3f1  js      short loc_18005C42E
0x18005c3f3  mov     rax, [rsp+28h+EcpContext]
0x18005c3f8  mov     rcx, [rax+10h]; P
0x18005c3fc  test    rcx, rcx
0x18005c3ff  jz      short loc_18005C417
0x18005c401  mov     edx, 68644D46h; Tag
0x18005c406  call    cs:__imp_ExFreePoolWithTag
0x18005c40d  nop     dword ptr [rax+rax+00h]
0x18005c412  mov     rax, [rsp+28h+EcpContext]
0x18005c417  mov     rcx, [rax]; Object
0x18005c41a  test    rcx, rcx
0x18005c41d  jnz     short loc_18005C434
0x18005c41f  mov     rcx, rax; EcpContext
0x18005c422  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x18005c429  nop     dword ptr [rax+rax+00h]
0x18005c42e  add     rsp, 28h
0x18005c432  retn
0x18005c434  call    cs:__imp_ObfDereferenceObject
0x18005c43b  nop     dword ptr [rax+rax+00h]
0x18005c440  mov     rax, [rsp+28h+EcpContext]
0x18005c445  jmp     short loc_18005C41F
```
