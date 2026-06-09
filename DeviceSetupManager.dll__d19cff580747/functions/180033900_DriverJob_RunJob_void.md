# DriverJob::RunJob(void)

- ea: `0x180033900`
- end: `0x180033a50`
- name: `?RunJob@DriverJob@@UEAA?AW4TASK_COMPLETION_STATUS@@XZ`
- size: `336`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d0dc`
- `0x18000d2e0`
- `0x180014df0`
- `0x180018678`
- `0x180033900`
- `0x18003493c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800339d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800339d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DriverJob::RunJob(__int64 a1)
{
  unsigned int v3; // esi
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *v5; // rcx
  unsigned int v6; // eax
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 72) )
    return 8;
  v3 = DriverJob::_RunJob();
  v4 = (const unsigned __int16 **)(a1 + 40);
  if ( v3 == 3 )
  {
    if ( *(_QWORD *)(a1 + 64) <= 7u )
      v5 = (const unsigned __int16 *)(a1 + 40);
    else
      v5 = *v4;
    v6 = GetDeviceUINT(v5, &DEVPKEY_DeviceSetup_HardErrorCount) + 1;
    if ( *(_QWORD *)(a1 + 64) <= 7u )
      v7 = (const unsigned __int16 *)(a1 + 40);
    else
      v7 = *v4;
    LODWORD(ppv) = v6;
    SetDeviceObjectProperty(3, v7, &DEVPKEY_DeviceSetup_HardErrorCount);
  }
  if ( *(_BYTE *)(a1 + 144) && v3 - 1 <= 2 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&ppv);
    if ( CoCreateInstance(
           &GUID_6d93c83d_31c1_490e_b5f9_068a80e3d7cb,
           0,
           1u,
           &GUID_612118c1_b1d3_4d55_80f2_4488b55cf623,
           &ppv) >= 0 )
    {
      v8 = *(_QWORD *)(a1 + 64) <= 7u ? a1 + 40 : (__int64)*v4;
      if ( (*(int (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, v8) >= 0 )
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 48LL))(ppv, 0);
    }
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&ppv);
  }
  v9 = *(_QWORD *)(a1 + 152);
  if ( v9 )
  {
    if ( *(_QWORD *)(a1 + 64) > 7u )
      v4 = (const unsigned __int16 **)*v4;
    DriverRecoveryRecord::UpdateBlockingDeviceStatus(v9, v4, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180033900  mov     [rsp+arg_8], rbx
0x180033905  mov     [rsp+arg_10], rsi
0x18003390a  push    rdi
0x18003390b  sub     rsp, 30h
0x18003390f  mov     rdi, rcx
0x180033912  mov     eax, [rcx+48h]
0x180033915  test    eax, eax
0x180033917  jz      short loc_180033923
0x180033919  mov     eax, 8
0x18003391e  jmp     loc_180033A40
0x180033923  call    ?_RunJob@DriverJob@@AEAA?AW4TASK_COMPLETION_STATUS@@XZ; DriverJob::_RunJob(void)
0x180033928  mov     esi, eax
0x18003392a  lea     rbx, [rdi+28h]
0x18003392e  cmp     eax, 3
0x180033931  jnz     short loc_18003398B
0x180033933  cmp     qword ptr [rbx+18h], 7
0x180033938  jbe     short loc_18003393F
0x18003393a  mov     rcx, [rbx]
0x18003393d  jmp     short loc_180033942
0x18003393f  mov     rcx, rbx; unsigned __int16 *
0x180033942  lea     rdx, DEVPKEY_DeviceSetup_HardErrorCount; struct _DEVPROPKEY *
0x180033949  call    ?GetDeviceUINT@@YAIPEBGAEBU_DEVPROPKEY@@@Z; GetDeviceUINT(ushort const *,_DEVPROPKEY const &)
0x18003394e  inc     eax
0x180033950  cmp     qword ptr [rbx+18h], 7
0x180033955  jbe     short loc_18003395C
0x180033957  mov     rdx, [rbx]
0x18003395a  jmp     short loc_18003395F
0x18003395c  mov     rdx, rbx
0x18003395f  mov     dword ptr [rsp+38h+arg_0], eax
0x180033963  mov     [rsp+38h+var_10], 4
0x18003396b  lea     rax, [rsp+38h+arg_0]
0x180033970  mov     [rsp+38h+ppv], rax
0x180033975  mov     r9d, 7
0x18003397b  lea     r8, DEVPKEY_DeviceSetup_HardErrorCount
0x180033982  lea     ecx, [r9-4]
0x180033986  call    ?SetDeviceObjectProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@KPEBXK@Z; SetDeviceObjectProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,ulong,void const *,ulong)
0x18003398b  cmp     byte ptr [rdi+90h], 0
0x180033992  jz      loc_180033A1D
0x180033998  lea     eax, [rsi-1]
0x18003399b  cmp     eax, 2
0x18003399e  ja      short loc_180033A1D
0x1800339a0  mov     [rsp+38h+arg_0], 0
0x1800339a9  lea     rcx, [rsp+38h+arg_0]
0x1800339ae  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x1800339b3  lea     rax, [rsp+38h+arg_0]
0x1800339b8  mov     [rsp+38h+ppv], rax; ppv
0x1800339bd  lea     r9, _GUID_612118c1_b1d3_4d55_80f2_4488b55cf623; riid
0x1800339c4  xor     edx, edx; pUnkOuter
0x1800339c6  lea     r8d, [rdx+1]; dwClsContext
0x1800339ca  lea     rcx, _GUID_6d93c83d_31c1_490e_b5f9_068a80e3d7cb; rclsid
0x1800339d1  call    cs:__imp_CoCreateInstance
0x1800339d7  test    eax, eax
0x1800339d9  js      short loc_180033A13
0x1800339db  mov     rcx, [rsp+38h+arg_0]
0x1800339e0  mov     rax, [rcx]
0x1800339e3  cmp     qword ptr [rbx+18h], 7
0x1800339e8  jbe     short loc_1800339EF
0x1800339ea  mov     rdx, [rbx]
0x1800339ed  jmp     short loc_1800339F2
0x1800339ef  mov     rdx, rbx
0x1800339f2  mov     rax, [rax+18h]
0x1800339f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339fb  test    eax, eax
0x1800339fd  js      short loc_180033A13
0x1800339ff  mov     rcx, [rsp+38h+arg_0]
0x180033a04  mov     rax, [rcx]
0x180033a07  xor     edx, edx
0x180033a09  mov     rax, [rax+30h]
0x180033a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a12  nop
0x180033a13  lea     rcx, [rsp+38h+arg_0]
0x180033a18  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x180033a1d  mov     rcx, [rdi+98h]
0x180033a24  test    rcx, rcx
0x180033a27  jz      short loc_180033A3E
0x180033a29  cmp     qword ptr [rbx+18h], 7
0x180033a2e  jbe     short loc_180033A33
0x180033a30  mov     rbx, [rbx]
0x180033a33  mov     r8d, esi
0x180033a36  mov     rdx, rbx
0x180033a39  call    ?UpdateBlockingDeviceStatus@DriverRecoveryRecord@@QEAAXPEBGW4TASK_COMPLETION_STATUS@@@Z; DriverRecoveryRecord::UpdateBlockingDeviceStatus(ushort const *,TASK_COMPLETION_STATUS)
0x180033a3e  mov     eax, esi
0x180033a40  mov     rbx, [rsp+38h+arg_8]
0x180033a45  mov     rsi, [rsp+38h+arg_10]
0x180033a4a  add     rsp, 30h
0x180033a4e  pop     rdi
0x180033a4f  retn
```
