# PimIMService_UpdateStores

- ea: `0x18000d020`
- end: `0x18000d0c2`
- name: `PimIMService_UpdateStores`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x180007190`
- `0x18000746c`
- `0x1800089c4`
- `0x18000a670`
- `0x18000d020`

## string_xrefs

- `0x18000d045`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000d06e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService_UpdateStores(__int64 a1, unsigned int *a2)
{
  PimIMService *v3; // rcx
  int TpWork; // ebx
  __int64 v5; // r9
  int UpdateCookie; // eax
  PimIMService *v8; // rcx
  struct TpWorkInfo *v9; // [rsp+50h] [rbp+18h] BYREF

  TpWork = PimIMService::OnLoad((struct _RTL_CRITICAL_SECTION *)&myService);
  if ( TpWork < 0 )
  {
    v5 = 3709;
LABEL_3:
    Log_HREvent(
      (unsigned int)TpWork,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v5);
    return (unsigned int)TpWork;
  }
  UpdateCookie = PimIMService::GetUpdateCookie(v3, a2);
  if ( UpdateCookie < 0 )
    Log_HREvent(
      (unsigned int)UpdateCookie,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3711);
  v9 = 0;
  TpWork = PimIMService::GetTpWork((PimIMService *)&myService, 1, &v9);
  if ( TpWork < 0 )
  {
    v5 = 3714;
    goto LABEL_3;
  }
  PimIMService::SubmitTpWork(v8, v9);
  return 0;
}

```

## disassembly

```asm
0x18000d020  mov     [rsp+arg_0], rbx
0x18000d025  push    rdi
0x18000d026  sub     rsp, 30h
0x18000d02a  lea     rcx, ?myService@@3VPimIMService@@A; pv
0x18000d031  mov     rdi, rdx
0x18000d034  call    ?OnLoad@PimIMService@@QEAAJXZ; PimIMService::OnLoad(void)
0x18000d039  mov     ebx, eax
0x18000d03b  test    eax, eax
0x18000d03d  jns     short loc_18000D05C
0x18000d03f  mov     r9d, 0E7Dh
0x18000d045  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000d04c  mov     edx, 1
0x18000d051  mov     ecx, ebx
0x18000d053  call    Log_HREvent
0x18000d058  mov     eax, ebx
0x18000d05a  jmp     short loc_18000D0B7
0x18000d05c  mov     rdx, rdi; unsigned int *
0x18000d05f  call    ?GetUpdateCookie@PimIMService@@QEAAJPEAK@Z; PimIMService::GetUpdateCookie(ulong *)
0x18000d064  test    eax, eax
0x18000d066  jns     short loc_18000D07E
0x18000d068  mov     r9d, 0E7Fh
0x18000d06e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000d075  xor     edx, edx
0x18000d077  mov     ecx, eax
0x18000d079  call    Log_HREvent
0x18000d07e  lea     r8, [rsp+38h+arg_10]; struct TpWorkInfo **
0x18000d083  mov     [rsp+38h+arg_10], 0
0x18000d08c  mov     edx, 1; unsigned int
0x18000d091  lea     rcx, ?myService@@3VPimIMService@@A; this
0x18000d098  call    ?GetTpWork@PimIMService@@UEAAJKPEAPEAUTpWorkInfo@@@Z; PimIMService::GetTpWork(ulong,TpWorkInfo * *)
0x18000d09d  mov     ebx, eax
0x18000d09f  test    eax, eax
0x18000d0a1  jns     short loc_18000D0AB
0x18000d0a3  mov     r9d, 0E82h
0x18000d0a9  jmp     short loc_18000D045
0x18000d0ab  mov     rdx, [rsp+38h+arg_10]; struct TpWorkInfo *
0x18000d0b0  call    ?SubmitTpWork@PimIMService@@QEAAXPEAUTpWorkInfo@@@Z; PimIMService::SubmitTpWork(TpWorkInfo *)
0x18000d0b5  xor     eax, eax
0x18000d0b7  mov     rbx, [rsp+38h+arg_0]
0x18000d0bc  add     rsp, 30h
0x18000d0c0  pop     rdi
0x18000d0c1  retn
```
