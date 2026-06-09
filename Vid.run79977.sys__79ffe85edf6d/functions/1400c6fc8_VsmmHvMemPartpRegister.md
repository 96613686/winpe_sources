# VsmmHvMemPartpRegister

- ea: `0x1400c6fc8`
- end: `0x1400c716a`
- name: `VsmmHvMemPartpRegister`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400c7170`

## callees

- `0x140021db0`
- `0x140024a90`
- `0x1400250ec`
- `0x14002f724`
- `0x140091de0`
- `0x140091e78`
- `0x140092304`
- `0x1400c64a4`
- `0x1400c6fc8`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c70a4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c70a4`
- `ntoskrnl!PsPartitionType` at `0x1400c7088`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1400c6ff7`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1400c6ff7`

## string_xrefs

- `0x1400c70e9`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Hypervisor\MetadataMemoryPartition`

## pseudocode

```c
__int64 __fastcall VsmmHvMemPartpRegister(__int64 a1)
{
  __int64 UINT64WithDefault; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  NTSTATUS v5; // eax
  __int64 v6; // rdx
  int v7; // r9d
  unsigned int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v14; // [rsp+70h] [rbp+18h] BYREF
  void *Handle; // [rsp+78h] [rbp+20h] BYREF

  Handle = 0;
  v14 = 0;
  v13 = 0;
  UINT64WithDefault = 0;
  if ( (int)KsrGetFirmwareInformation(&v14) < 0 || *v14 < 3u )
    v3 = 0;
  else
    v3 = (unsigned int)v14[58];
  if ( (int)VsmmHvMemPartpOpenHvMemPartKey(131097, &v13) < 0 )
    VidTraceInfoInternal0("VsmmHvMemPartpRegister", "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c", 2048);
  v4 = v13;
  if ( v13 )
    UINT64WithDefault = VidRegistryQueryUINT64WithDefault(v13, L"SoftRestartCount", 0);
  if ( v3 != UINT64WithDefault || !v3 )
  {
    v5 = ObOpenObjectByPointer(*(PVOID *)(a1 + 88), 0x200u, 0, 0x1F0003u, PsPartitionType, 0, &Handle);
    v8 = v5;
    if ( v5 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmHvMemPartpRegister",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
        2081,
        (unsigned int)v5);
      goto LABEL_22;
    }
    if ( v4 )
      goto LABEL_18;
    if ( (int)VidRegistryCreateSubkey(
                0,
                (unsigned int)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Hypervisor\\MetadataMemoryPartition",
                2,
                v7,
                (__int64)&v13) >= 0 )
      v4 = v13;
    else
      VidTraceWarningInternal0(v9, v6, 2099);
    if ( v4 )
    {
LABEL_18:
      if ( (int)VidRegistryAssignUINT64(v4, v6, v3) < 0 )
        VidTraceWarningInternal0(v11, v10, 2112);
    }
    *(_QWORD *)(a1 + 440) = Handle;
  }
  v8 = 0;
LABEL_22:
  if ( v4 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v4);
  return v8;
}

```

## disassembly

```asm
0x1400c6fc8  mov     rax, rsp
0x1400c6fcb  mov     [rax+8], rbx
0x1400c6fcf  push    rbp
0x1400c6fd0  push    rsi
0x1400c6fd1  push    rdi
0x1400c6fd2  sub     rsp, 40h
0x1400c6fd6  mov     rbp, rcx
0x1400c6fd9  mov     qword ptr [rax+20h], 0
0x1400c6fe1  lea     rcx, [rax+18h]
0x1400c6fe5  mov     qword ptr [rax+18h], 0
0x1400c6fed  mov     qword ptr [rax+10h], 0
0x1400c6ff5  xor     edi, edi
0x1400c6ff7  call    cs:__imp_KsrGetFirmwareInformation
0x1400c6ffe  nop     dword ptr [rax+rax+00h]
0x1400c7003  test    eax, eax
0x1400c7005  js      short loc_1400C7019
0x1400c7007  mov     rax, [rsp+58h+arg_10]
0x1400c700c  cmp     dword ptr [rax], 3
0x1400c700f  jb      short loc_1400C7019
0x1400c7011  mov     esi, [rax+0E8h]
0x1400c7017  jmp     short loc_1400C701B
0x1400c7019  xor     esi, esi
0x1400c701b  lea     rdx, [rsp+58h+arg_8]
0x1400c7020  mov     ecx, 20019h
0x1400c7025  call    VsmmHvMemPartpOpenHvMemPartKey
0x1400c702a  test    eax, eax
0x1400c702c  jns     short loc_1400C7047
0x1400c702e  mov     r8d, 800h
0x1400c7034  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c703b  lea     rcx, aVsmmhvmempartp_3; "VsmmHvMemPartpRegister"
0x1400c7042  call    VidTraceInfoInternal0
0x1400c7047  mov     rbx, [rsp+58h+arg_8]
0x1400c704c  test    rbx, rbx
0x1400c704f  jz      short loc_1400C7066
0x1400c7051  xor     r8d, r8d
0x1400c7054  lea     rdx, aSoftrestartcou; "SoftRestartCount"
0x1400c705b  mov     rcx, rbx
0x1400c705e  call    VidRegistryQueryUINT64WithDefault
0x1400c7063  mov     rdi, rax
0x1400c7066  cmp     rsi, rdi
0x1400c7069  jnz     short loc_1400C7074
0x1400c706b  test    rsi, rsi
0x1400c706e  jnz     loc_1400C7136
0x1400c7074  mov     rcx, [rbp+58h]; Object
0x1400c7078  lea     rax, [rsp+58h+arg_18]
0x1400c707d  mov     [rsp+58h+Handle], rax; Handle
0x1400c7082  mov     r9d, 1F0003h; DesiredAccess
0x1400c7088  mov     rax, cs:__imp_PsPartitionType
0x1400c708f  mov     edx, 200h; HandleAttributes
0x1400c7094  mov     [rsp+58h+AccessMode], 0; AccessMode
0x1400c7099  mov     r8, [rax]
0x1400c709c  mov     [rsp+58h+ObjectType], r8; ObjectType
0x1400c70a1  xor     r8d, r8d; PassedAccessState
0x1400c70a4  call    cs:__imp_ObOpenObjectByPointer
0x1400c70ab  nop     dword ptr [rax+rax+00h]
0x1400c70b0  mov     edi, eax
0x1400c70b2  test    eax, eax
0x1400c70b4  jns     short loc_1400C70D4
0x1400c70b6  mov     r9d, eax
0x1400c70b9  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c70c0  mov     r8d, 821h
0x1400c70c6  lea     rcx, aVsmmhvmempartp_3; "VsmmHvMemPartpRegister"
0x1400c70cd  call    VidTraceErrorStatusInternal0
0x1400c70d2  jmp     short loc_1400C7138
0x1400c70d4  test    rbx, rbx
0x1400c70d7  jnz     short loc_1400C7110
0x1400c70d9  lea     rax, [rsp+58h+arg_8]
0x1400c70de  xor     ecx, ecx
0x1400c70e0  lea     r8d, [rbx+2]
0x1400c70e4  mov     [rsp+58h+ObjectType], rax
0x1400c70e9  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1400c70f0  call    VidRegistryCreateSubkey
0x1400c70f5  test    eax, eax
0x1400c70f7  jns     short loc_1400C7106
0x1400c70f9  mov     r8d, 833h
0x1400c70ff  call    VidTraceWarningInternal0
0x1400c7104  jmp     short loc_1400C710B
0x1400c7106  mov     rbx, [rsp+58h+arg_8]
0x1400c710b  test    rbx, rbx
0x1400c710e  jz      short loc_1400C712A
0x1400c7110  mov     r8, rsi
0x1400c7113  mov     rcx, rbx
0x1400c7116  call    VidRegistryAssignUINT64
0x1400c711b  test    eax, eax
0x1400c711d  jns     short loc_1400C712A
0x1400c711f  mov     r8d, 840h
0x1400c7125  call    VidTraceWarningInternal0
0x1400c712a  mov     rax, [rsp+58h+arg_18]
0x1400c712f  mov     [rbp+1B8h], rax
0x1400c7136  xor     edi, edi
0x1400c7138  test    rbx, rbx
0x1400c713b  jz      short loc_1400C715A
0x1400c713d  mov     rax, cs:WdfFunctions_01015
0x1400c7144  mov     rdx, rbx
0x1400c7147  mov     rcx, cs:WdfDriverGlobals
0x1400c714e  mov     rax, [rax+738h]
0x1400c7155  call    _guard_dispatch_icall
0x1400c715a  mov     rbx, [rsp+58h+arg_0]
0x1400c715f  mov     eax, edi
0x1400c7161  add     rsp, 40h
0x1400c7165  pop     rdi
0x1400c7166  pop     rsi
0x1400c7167  pop     rbp
0x1400c7168  retn
```
