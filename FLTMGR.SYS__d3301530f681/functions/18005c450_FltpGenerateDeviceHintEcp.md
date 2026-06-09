# FltpGenerateDeviceHintEcp

- ea: `0x18005c450`
- end: `0x18005c58e`
- name: `FltpGenerateDeviceHintEcp`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001bf00`
- `0x18005aa30`
- `0x18005d2b0`

## callees

- `0x180009f20`
- `0x18005c3b0`
- `0x18005c450`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005c525`
- `ntoskrnl!ExAllocatePool2` at `0x18005c525`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005c4d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005c4d3`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18005c49b`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18005c49b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005c4ef`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005c4ef`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x18005c571`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x18005c571`

## pseudocode

```c
__int64 __fastcall FltpGenerateDeviceHintEcp(PVOID *a1, unsigned __int16 a2, struct _ECP_LIST *a3)
{
  unsigned int v3; // ebx
  unsigned int Parameter; // esi
  __int64 Pool2; // rax
  _QWORD *v8; // rcx
  PVOID EcpContext; // [rsp+68h] [rbp+20h] BYREF

  v3 = a2;
  EcpContext = 0;
  Parameter = FsRtlAllocateExtraCreateParameterFromLookasideList(
                &GUID_ECP_IO_DEVICE_HINT,
                0x18u,
                0,
                0,
                qword_18003F040,
                &EcpContext);
  if ( (int)FltpDbgStatus(Parameter, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2203, 0) < 0 )
    return Parameter;
  RtlInitUnicodeString((PUNICODE_STRING)((char *)EcpContext + 8), 0);
  *(_QWORD *)EcpContext = 0;
  Parameter = FsRtlInsertExtraCreateParameter(a3, EcpContext);
  if ( (int)FltpDbgStatus(Parameter, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 2218, 0) < 0 )
  {
    FsRtlFreeExtraCreateParameter(EcpContext);
    return Parameter;
  }
  Pool2 = ExAllocatePool2(256, v3, 1751403846);
  if ( Pool2 )
  {
    v8 = EcpContext;
    *(_OWORD *)((char *)EcpContext + 8) = 0;
    v8[2] = Pool2;
    *((_WORD *)v8 + 5) = v3;
    *a1 = EcpContext;
    return 0;
  }
  else
  {
    FltpCleanupDeviceHintEcp(a3);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x18005c450  mov     [rsp+arg_0], rbx
0x18005c455  mov     [rsp+arg_8], rbp
0x18005c45a  push    rsi
0x18005c45b  push    rdi
0x18005c45c  push    r14
0x18005c45e  sub     rsp, 30h
0x18005c462  lea     rax, [rsp+48h+arg_18]
0x18005c467  movzx   ebx, dx
0x18005c46a  mov     [rsp+48h+EcpContext], rax; EcpContext
0x18005c46f  mov     rbp, r8
0x18005c472  lea     rax, qword_18003F040
0x18005c479  mov     rdi, rcx
0x18005c47c  xor     r14d, r14d
0x18005c47f  mov     [rsp+48h+LookasideList], rax; LookasideList
0x18005c484  xor     r9d, r9d; CleanupCallback
0x18005c487  mov     [rsp+48h+arg_18], r14
0x18005c48c  xor     r8d, r8d; Flags
0x18005c48f  lea     rcx, GUID_ECP_IO_DEVICE_HINT; EcpType
0x18005c496  mov     edx, 18h; SizeOfContext
0x18005c49b  call    cs:__imp_FsRtlAllocateExtraCreateParameterFromLookasideList
0x18005c4a2  nop     dword ptr [rax+rax+00h]
0x18005c4a7  mov     r8d, 89Bh
0x18005c4ad  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005c4b4  mov     ecx, eax
0x18005c4b6  xor     r9d, r9d
0x18005c4b9  mov     esi, eax
0x18005c4bb  call    FltpDbgStatus
0x18005c4c0  test    eax, eax
0x18005c4c2  js      loc_18005C568
0x18005c4c8  mov     rcx, [rsp+48h+arg_18]
0x18005c4cd  xor     edx, edx; SourceString
0x18005c4cf  add     rcx, 8; DestinationString
0x18005c4d3  call    cs:__imp_RtlInitUnicodeString
0x18005c4da  nop     dword ptr [rax+rax+00h]
0x18005c4df  mov     rax, [rsp+48h+arg_18]
0x18005c4e4  mov     rcx, rbp; EcpList
0x18005c4e7  mov     [rax], r14
0x18005c4ea  mov     rdx, [rsp+48h+arg_18]; EcpContext
0x18005c4ef  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18005c4f6  nop     dword ptr [rax+rax+00h]
0x18005c4fb  mov     r8d, 8AAh
0x18005c501  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005c508  mov     ecx, eax
0x18005c50a  xor     r9d, r9d
0x18005c50d  mov     esi, eax
0x18005c50f  call    FltpDbgStatus
0x18005c514  test    eax, eax
0x18005c516  js      short loc_18005C56C
0x18005c518  mov     edx, ebx
0x18005c51a  mov     ecx, 100h
0x18005c51f  mov     r8d, 68644D46h
0x18005c525  call    cs:__imp_ExAllocatePool2
0x18005c52c  nop     dword ptr [rax+rax+00h]
0x18005c531  test    rax, rax
0x18005c534  jz      short loc_18005C57F
0x18005c536  mov     rcx, [rsp+48h+arg_18]
0x18005c53b  xorps   xmm0, xmm0
0x18005c53e  movups  xmmword ptr [rcx+8], xmm0
0x18005c542  mov     [rcx+10h], rax
0x18005c546  mov     [rcx+0Ah], bx
0x18005c54a  mov     rax, [rsp+48h+arg_18]
0x18005c54f  mov     [rdi], rax
0x18005c552  xor     eax, eax
0x18005c554  mov     rbx, [rsp+48h+arg_0]
0x18005c559  mov     rbp, [rsp+48h+arg_8]
0x18005c55e  add     rsp, 30h
0x18005c562  pop     r14
0x18005c564  pop     rdi
0x18005c565  pop     rsi
0x18005c566  retn
0x18005c568  mov     eax, esi
0x18005c56a  jmp     short loc_18005C554
0x18005c56c  mov     rcx, [rsp+48h+arg_18]; EcpContext
0x18005c571  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x18005c578  nop     dword ptr [rax+rax+00h]
0x18005c57d  jmp     short loc_18005C568
0x18005c57f  mov     rcx, rbp
0x18005c582  call    FltpCleanupDeviceHintEcp
0x18005c587  mov     eax, 0C000009Ah
0x18005c58c  jmp     short loc_18005C554
```
