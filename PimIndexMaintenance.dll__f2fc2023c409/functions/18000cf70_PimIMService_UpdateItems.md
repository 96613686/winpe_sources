# PimIMService_UpdateItems

- ea: `0x18000cf70`
- end: `0x18000d012`
- name: `PimIMService_UpdateItems`
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
- `0x18000cf70`

## string_xrefs

- `0x18000cf95`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000cfbe`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService_UpdateItems(__int64 a1, unsigned int *a2)
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
    v5 = 3693;
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
      3695);
  v9 = 0;
  TpWork = PimIMService::GetTpWork((PimIMService *)&myService, 2, &v9);
  if ( TpWork < 0 )
  {
    v5 = 3698;
    goto LABEL_3;
  }
  PimIMService::SubmitTpWork(v8, v9);
  return 0;
}

```

## disassembly

```asm
0x18000cf70  mov     [rsp+arg_0], rbx
0x18000cf75  push    rdi
0x18000cf76  sub     rsp, 30h
0x18000cf7a  lea     rcx, ?myService@@3VPimIMService@@A; pv
0x18000cf81  mov     rdi, rdx
0x18000cf84  call    ?OnLoad@PimIMService@@QEAAJXZ; PimIMService::OnLoad(void)
0x18000cf89  mov     ebx, eax
0x18000cf8b  test    eax, eax
0x18000cf8d  jns     short loc_18000CFAC
0x18000cf8f  mov     r9d, 0E6Dh
0x18000cf95  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000cf9c  mov     edx, 1
0x18000cfa1  mov     ecx, ebx
0x18000cfa3  call    Log_HREvent
0x18000cfa8  mov     eax, ebx
0x18000cfaa  jmp     short loc_18000D007
0x18000cfac  mov     rdx, rdi; unsigned int *
0x18000cfaf  call    ?GetUpdateCookie@PimIMService@@QEAAJPEAK@Z; PimIMService::GetUpdateCookie(ulong *)
0x18000cfb4  test    eax, eax
0x18000cfb6  jns     short loc_18000CFCE
0x18000cfb8  mov     r9d, 0E6Fh
0x18000cfbe  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000cfc5  xor     edx, edx
0x18000cfc7  mov     ecx, eax
0x18000cfc9  call    Log_HREvent
0x18000cfce  lea     r8, [rsp+38h+arg_10]; struct TpWorkInfo **
0x18000cfd3  mov     [rsp+38h+arg_10], 0
0x18000cfdc  mov     edx, 2; unsigned int
0x18000cfe1  lea     rcx, ?myService@@3VPimIMService@@A; this
0x18000cfe8  call    ?GetTpWork@PimIMService@@UEAAJKPEAPEAUTpWorkInfo@@@Z; PimIMService::GetTpWork(ulong,TpWorkInfo * *)
0x18000cfed  mov     ebx, eax
0x18000cfef  test    eax, eax
0x18000cff1  jns     short loc_18000CFFB
0x18000cff3  mov     r9d, 0E72h
0x18000cff9  jmp     short loc_18000CF95
0x18000cffb  mov     rdx, [rsp+38h+arg_10]; struct TpWorkInfo *
0x18000d000  call    ?SubmitTpWork@PimIMService@@QEAAXPEAUTpWorkInfo@@@Z; PimIMService::SubmitTpWork(TpWorkInfo *)
0x18000d005  xor     eax, eax
0x18000d007  mov     rbx, [rsp+38h+arg_0]
0x18000d00c  add     rsp, 30h
0x18000d010  pop     rdi
0x18000d011  retn
```
