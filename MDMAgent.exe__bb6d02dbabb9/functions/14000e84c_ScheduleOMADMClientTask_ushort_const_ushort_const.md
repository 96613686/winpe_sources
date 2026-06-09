# ScheduleOMADMClientTask(ushort const *,ushort const *)

- ea: `0x14000e84c`
- end: `0x14000e92b`
- name: `?ScheduleOMADMClientTask@@YAJPEBG0@Z`
- size: `223`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010818`

## callees

- `0x140006bf4`
- `0x14000a134`
- `0x14000e84c`
- `0x14000e934`
- `0x14000f69c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e8f9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e90c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e8f9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e90c`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTask(unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v4; // ebx
  unsigned int v5; // edx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v10; // [rsp+40h] [rbp+18h] BYREF
  int v11; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v10, (unsigned int)a2);
  if ( v4 >= 0 )
  {
    v4 = ScheduleOMADMClientTaskHelper(a1, a2, L"Schedule to run OMADMClient by server", 1);
    if ( v4 >= 0 )
    {
      v4 = ScheduleOMADMClientTaskHelper(a1, a2, L"Schedule to run OMADMClient by client", 0);
      if ( v4 >= 0 )
      {
        v11 = 0;
        v6 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v11, v5);
        v4 = v6;
        if ( v6 >= 0 )
          v4 = ScheduleProvisioningInitiatedSyncHelper(a1);
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAB4,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)(unsigned int)v6,
            v8);
        if ( v11 )
          CoUninitialize();
      }
    }
  }
  if ( v10 )
    CoUninitialize();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000e84c  mov     rax, rsp
0x14000e84f  mov     [rax+8], rbx
0x14000e853  mov     [rax+10h], rsi
0x14000e857  push    rdi; int
0x14000e858  sub     rsp, 20h
0x14000e85c  mov     rdi, rcx
0x14000e85f  mov     dword ptr [rax+18h], 0
0x14000e866  lea     rcx, [rax+18h]; this
0x14000e86a  mov     rsi, rdx
0x14000e86d  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000e872  mov     ebx, eax
0x14000e874  test    eax, eax
0x14000e876  js      loc_14000E905
0x14000e87c  mov     r9d, 1
0x14000e882  lea     r8, aScheduleToRunO_0; "Schedule to run OMADMClient by server"
0x14000e889  mov     rdx, rsi; unsigned __int16 *
0x14000e88c  mov     rcx, rdi; unsigned __int16 *
0x14000e88f  call    ScheduleOMADMClientTaskHelper
0x14000e894  mov     ebx, eax
0x14000e896  test    eax, eax
0x14000e898  js      short loc_14000E905
0x14000e89a  xor     r9d, r9d
0x14000e89d  lea     r8, aScheduleToRunO; "Schedule to run OMADMClient by client"
0x14000e8a4  mov     rdx, rsi; unsigned __int16 *
0x14000e8a7  mov     rcx, rdi; unsigned __int16 *
0x14000e8aa  call    ScheduleOMADMClientTaskHelper
0x14000e8af  mov     ebx, eax
0x14000e8b1  test    eax, eax
0x14000e8b3  js      short loc_14000E905
0x14000e8b5  lea     rcx, [rsp+28h+arg_18]; this
0x14000e8ba  mov     [rsp+28h+arg_18], 0
0x14000e8c2  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000e8c7  mov     ebx, eax
0x14000e8c9  test    eax, eax
0x14000e8cb  jns     short loc_14000E8E8
0x14000e8cd  mov     rcx, [rsp+28h]; this
0x14000e8d2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000e8d9  mov     r9d, eax; char *
0x14000e8dc  mov     edx, 0AB4h; void *
0x14000e8e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e8e6  jmp     short loc_14000E8F2
0x14000e8e8  mov     rcx, rdi; unsigned __int16 *
0x14000e8eb  call    ScheduleProvisioningInitiatedSyncHelper
0x14000e8f0  mov     ebx, eax
0x14000e8f2  cmp     [rsp+28h+arg_18], 0
0x14000e8f7  jz      short loc_14000E905
0x14000e8f9  call    cs:__imp_CoUninitialize
0x14000e900  nop     dword ptr [rax+rax+00h]
0x14000e905  cmp     [rsp+28h+arg_10], 0
0x14000e90a  jz      short loc_14000E918
0x14000e90c  call    cs:__imp_CoUninitialize
0x14000e913  nop     dword ptr [rax+rax+00h]
0x14000e918  mov     rsi, [rsp+28h+arg_8]
0x14000e91d  mov     eax, ebx
0x14000e91f  mov     rbx, [rsp+28h+arg_0]
0x14000e924  add     rsp, 20h
0x14000e928  pop     rdi
0x14000e929  retn
```
