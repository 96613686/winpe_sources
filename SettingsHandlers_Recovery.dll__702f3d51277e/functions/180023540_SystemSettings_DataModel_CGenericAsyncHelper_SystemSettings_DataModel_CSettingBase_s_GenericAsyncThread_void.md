# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::s_GenericAsyncThread(void *)

- ea: `0x180023540`
- end: `0x1800235a5`
- name: `?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z`
- size: `101`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callees

- `0x18000282c`
- `0x180013eac`
- `0x180023540`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::s_GenericAsyncThread(
        _QWORD *Parameter)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(
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
0x180023540  push    rbx
0x180023542  sub     rsp, 20h
0x180023546  mov     rbx, rcx
0x180023549  mov     rdx, [rcx+8]
0x18002354d  mov     rcx, [rcx]
0x180023550  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x180023555  nop
0x180023556  mov     rcx, [rbx+8]
0x18002355a  test    rcx, rcx
0x18002355d  jz      short loc_180023574
0x18002355f  mov     qword ptr [rbx+8], 0
0x180023567  mov     rax, [rcx]
0x18002356a  mov     rax, [rax+10h]
0x18002356e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023573  nop
0x180023574  mov     rcx, [rbx]
0x180023577  test    rcx, rcx
0x18002357a  jz      short loc_180023590
0x18002357c  mov     qword ptr [rbx], 0
0x180023583  mov     rax, [rcx]
0x180023586  mov     rax, [rax+10h]
0x18002358a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002358f  nop
0x180023590  mov     edx, 18h
0x180023595  mov     rcx, rbx; Block
0x180023598  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002359d  xor     eax, eax
0x18002359f  add     rsp, 20h
0x1800235a3  pop     rbx
0x1800235a4  retn
```
