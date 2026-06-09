# CRegistryChangeListener::s_RegistryChangeCB(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180009720`
- end: `0x1800097f9`
- name: `?s_RegistryChangeCB@CRegistryChangeListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `217`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009720`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800097ed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800097ed`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180009730`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180009730`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009765`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009765`

## pseudocode

```c
void __fastcall CRegistryChangeListener::s_RegistryChangeCB(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  unsigned int v4; // ebx
  __int64 v5; // [rsp+40h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-10h] BYREF

  v4 = (unsigned int)Context;
  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      v5 = 0;
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 40LL))(
             ppv,
             v4,
             &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
             &v5) >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v5 + 32LL))(
          v5,
          &qword_18000F428,
          0,
          0,
          0,
          0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x180009720  push    rbx
0x180009722  sub     rsp, 50h
0x180009726  mov     rbx, rdx
0x180009729  xor     ecx, ecx; pvReserved
0x18000972b  mov     edx, 6; dwCoInit
0x180009730  call    cs:__imp_CoInitializeEx
0x180009736  test    eax, eax
0x180009738  js      loc_1800097F3
0x18000973e  xor     edx, edx; pUnkOuter
0x180009740  mov     [rsp+58h+var_10], 0
0x180009749  lea     rax, [rsp+58h+var_10]
0x18000974e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009755  mov     [rsp+58h+ppv], rax; ppv
0x18000975a  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009761  lea     r8d, [rdx+1]; dwClsContext
0x180009765  call    cs:__imp_CoCreateInstance
0x18000976b  test    eax, eax
0x18000976d  js      short loc_1800097ED
0x18000976f  mov     rcx, [rsp+58h+var_10]
0x180009774  lea     r9, [rsp+58h+var_18]
0x180009779  mov     [rsp+58h+var_18], 0
0x180009782  lea     r8, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x180009789  mov     edx, ebx
0x18000978b  mov     rax, [rcx]
0x18000978e  mov     rax, [rax+28h]
0x180009792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009797  test    eax, eax
0x180009799  js      short loc_1800097DC
0x18000979b  mov     rcx, [rsp+58h+var_18]
0x1800097a0  lea     rdx, qword_18000F428
0x1800097a7  mov     [rsp+58h+var_30], 0
0x1800097b0  xor     r9d, r9d
0x1800097b3  xor     r8d, r8d
0x1800097b6  mov     [rsp+58h+ppv], 0
0x1800097bf  mov     rax, [rcx]
0x1800097c2  mov     rax, [rax+20h]
0x1800097c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097cb  mov     rcx, [rsp+58h+var_18]
0x1800097d0  mov     rax, [rcx]
0x1800097d3  mov     rax, [rax+10h]
0x1800097d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097dc  mov     rcx, [rsp+58h+var_10]
0x1800097e1  mov     rax, [rcx]
0x1800097e4  mov     rax, [rax+10h]
0x1800097e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ed  call    cs:__imp_CoUninitialize
0x1800097f3  add     rsp, 50h
0x1800097f7  pop     rbx
0x1800097f8  retn
```
