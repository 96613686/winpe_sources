# KfdStartModuleEx

- ea: `0x1400aa388`
- end: `0x1400aa52a`
- name: `KfdStartModuleEx`
- size: `418`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x140061590`
- `0x1400aa310`

## callees

- `0x140051228`
- `0x1400512d8`
- `0x1400641bc`
- `0x140064214`
- `0x14006ad28`
- `0x14006b8a8`
- `0x14006bbb8`
- `0x14006bccc`
- `0x14006bf4c`
- `0x1400aa16c`
- `0x1400aa388`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400aa513`
- `ntoskrnl!ZwClose` at `0x1400aa513`

## string_xrefs

- `0x1400aa47c`: `\Registry\Machine\System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x1400aa406`: `\Registry\Machine\System\CurrentControlSet\Services\BFE\Parameters`

## pseudocode

```c
__int64 __fastcall KfdStartModuleEx(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  int v3; // ebx
  __int64 v4; // rax
  int v5; // eax
  HANDLE Handle; // [rsp+38h] [rbp-8h] BYREF

  Handle = 0;
  v2 = FeInit(a1, a2, (unsigned int)a1);
  v3 = WfpErrorToNtStatus(v2);
  if ( v3 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b01cdfbe5b713f7df60bd2463f5d4bb6_Traceguids);
    }
    v4 = KfdProcessBoottimePolicy();
    v5 = WfpErrorToNtStatus(v4);
    v3 = 0;
    if ( v5 >= 0 )
      v3 = v5;
    WfpRegOpenKey(&Handle);
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400aa388  push    rbp
0x1400aa38a  push    rbx
0x1400aa38b  push    rdi
0x1400aa38c  mov     rbp, rsp
0x1400aa38f  sub     rsp, 40h
0x1400aa393  xor     edi, edi
0x1400aa395  mov     r8d, ecx
0x1400aa398  mov     [rbp+Handle], rdi
0x1400aa39c  mov     [rbp+arg_18], edi
0x1400aa39f  mov     [rbp+arg_8], edi
0x1400aa3a2  mov     [rbp+arg_10], edi
0x1400aa3a5  call    FeInit
0x1400aa3aa  mov     rcx, rax
0x1400aa3ad  call    WfpErrorToNtStatus
0x1400aa3b2  mov     ebx, eax
0x1400aa3b4  test    eax, eax
0x1400aa3b6  js      loc_1400AA50A
0x1400aa3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa3c3  lea     rax, WPP_GLOBAL_Control
0x1400aa3ca  cmp     rcx, rax
0x1400aa3cd  jz      short loc_1400AA3F1
0x1400aa3cf  cmp     byte ptr [rcx+29h], 4
0x1400aa3d3  jb      short loc_1400AA3F1
0x1400aa3d5  test    dword ptr [rcx+2Ch], 2000h
0x1400aa3dc  jz      short loc_1400AA3F1
0x1400aa3de  mov     rcx, [rcx+18h]
0x1400aa3e2  lea     edx, [rdi+0Ch]
0x1400aa3e5  lea     r8, WPP_b01cdfbe5b713f7df60bd2463f5d4bb6_Traceguids
0x1400aa3ec  call    WPP_SF_
0x1400aa3f1  call    KfdProcessBoottimePolicy
0x1400aa3f6  mov     rcx, rax
0x1400aa3f9  call    WfpErrorToNtStatus
0x1400aa3fe  test    eax, eax
0x1400aa400  lea     r8, [rbp+arg_18]
0x1400aa404  mov     ebx, edi
0x1400aa406  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400aa40d  lea     rcx, [rbp+Handle]; KeyHandle
0x1400aa411  cmovns  ebx, eax
0x1400aa414  call    WfpRegOpenKey
0x1400aa419  test    rax, rax
0x1400aa41c  jnz     loc_1400AA50A
0x1400aa422  cmp     [rbp+arg_18], edi
0x1400aa425  jz      loc_1400AA50A
0x1400aa42b  mov     rcx, [rbp+Handle]; KeyHandle
0x1400aa42f  lea     r9, [rbp+arg_8]
0x1400aa433  lea     r8, [rbp+arg_10]
0x1400aa437  lea     rdx, aAledebugenable; "AleDebugEnabled"
0x1400aa43e  call    WfpRegGetUint32Value
0x1400aa443  test    rax, rax
0x1400aa446  jnz     loc_1400AA50A
0x1400aa44c  cmp     [rbp+arg_8], edi
0x1400aa44f  jz      short loc_1400AA458
0x1400aa451  mov     cs:gAleDebugEnabled, 1
0x1400aa458  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext
0x1400aa45e  test    al, 10h
0x1400aa460  jz      short loc_1400AA467
0x1400aa462  and     eax, 1
0x1400aa465  jmp     short loc_1400AA46C
0x1400aa467  call    Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline
0x1400aa46c  test    eax, eax
0x1400aa46e  jnz     loc_1400AA50A
0x1400aa474  lea     r8, [rbp+arg_18]
0x1400aa478  mov     [rbp+KeyHandle], rdi
0x1400aa47c  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400aa483  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400aa487  call    WfpRegOpenKey
0x1400aa48c  test    rax, rax
0x1400aa48f  jnz     short loc_1400AA50A
0x1400aa491  mov     [rbp+arg_10], edi
0x1400aa494  mov     [rbp+arg_8], edi
0x1400aa497  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceObjectExtension
0x1400aa49d  test    al, 10h
0x1400aa49f  jz      short loc_1400AA4A6
0x1400aa4a1  and     eax, 1
0x1400aa4a4  jmp     short loc_1400AA4AB
0x1400aa4a6  call    Feature_Firewall_BugFixes_25D_AuditMode_regKey_exists__private_IsEnabledDeviceUsageNoInline
0x1400aa4ab  test    eax, eax
0x1400aa4ad  jz      short loc_1400AA4E0
0x1400aa4af  cmp     [rbp+arg_18], edi
0x1400aa4b2  jz      short loc_1400AA50A
0x1400aa4b4  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400aa4b8  lea     r9, [rbp+arg_8]
0x1400aa4bc  lea     r8, [rbp+arg_10]
0x1400aa4c0  lea     rdx, aEnableauditmod; "EnableAuditMode"
0x1400aa4c7  call    WfpRegGetUint32Value
0x1400aa4cc  cmp     [rbp+arg_8], edi
0x1400aa4cf  jz      short loc_1400AA4D9
0x1400aa4d1  mov     ecx, [rbp+arg_10]
0x1400aa4d4  call    WfpSetAuditMode
0x1400aa4d9  call    WfpRegNotifyCreate
0x1400aa4de  jmp     short loc_1400AA50A
0x1400aa4e0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400aa4e4  lea     r9, [rbp+arg_8]
0x1400aa4e8  lea     r8, [rbp+arg_10]
0x1400aa4ec  lea     rdx, aEnableauditmod; "EnableAuditMode"
0x1400aa4f3  call    WfpRegGetUint32Value
0x1400aa4f8  cmp     [rbp+arg_8], edi
0x1400aa4fb  jz      short loc_1400AA505
0x1400aa4fd  mov     ecx, [rbp+arg_10]
0x1400aa500  call    WfpSetAuditMode
0x1400aa505  call    WfpRegNotifyCreate
0x1400aa50a  mov     rcx, [rbp+Handle]; Handle
0x1400aa50e  test    rcx, rcx
0x1400aa511  jz      short loc_1400AA51F
0x1400aa513  call    cs:__imp_ZwClose
0x1400aa51a  nop     dword ptr [rax+rax+00h]
0x1400aa51f  mov     eax, ebx
0x1400aa521  add     rsp, 40h
0x1400aa525  pop     rdi
0x1400aa526  pop     rbx
0x1400aa527  pop     rbp
0x1400aa528  retn
```
