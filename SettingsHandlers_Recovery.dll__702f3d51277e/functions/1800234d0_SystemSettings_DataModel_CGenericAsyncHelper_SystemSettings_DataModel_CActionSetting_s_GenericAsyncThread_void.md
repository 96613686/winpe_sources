# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::s_GenericAsyncThread(void *)

- ea: `0x1800234d0`
- end: `0x180023535`
- name: `?s_GenericAsyncThread@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z`
- size: `101`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callees

- `0x18000282c`
- `0x180013e04`
- `0x1800234d0`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::s_GenericAsyncThread(
        _QWORD *Parameter)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(
    *Parameter,
    Parameter[1]);
  v2 = Parameter[1];
  if ( v2 )
  {
    Parameter[1] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *Parameter;
  if ( *Parameter )
  {
    *Parameter = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  operator delete(Parameter);
  return 0;
}

```

## disassembly

```asm
0x1800234d0  push    rbx
0x1800234d2  sub     rsp, 20h
0x1800234d6  mov     rbx, rcx
0x1800234d9  mov     rdx, [rcx+8]
0x1800234dd  mov     rcx, [rcx]
0x1800234e0  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x1800234e5  nop
0x1800234e6  mov     rcx, [rbx+8]
0x1800234ea  test    rcx, rcx
0x1800234ed  jz      short loc_180023504
0x1800234ef  mov     qword ptr [rbx+8], 0
0x1800234f7  mov     rax, [rcx]
0x1800234fa  mov     rax, [rax+10h]
0x1800234fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023503  nop
0x180023504  mov     rcx, [rbx]
0x180023507  test    rcx, rcx
0x18002350a  jz      short loc_180023520
0x18002350c  mov     qword ptr [rbx], 0
0x180023513  mov     rax, [rcx]
0x180023516  mov     rax, [rax+10h]
0x18002351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002351f  nop
0x180023520  mov     edx, 18h
0x180023525  mov     rcx, rbx; Block
0x180023528  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002352d  xor     eax, eax
0x18002352f  add     rsp, 20h
0x180023533  pop     rbx
0x180023534  retn
```
