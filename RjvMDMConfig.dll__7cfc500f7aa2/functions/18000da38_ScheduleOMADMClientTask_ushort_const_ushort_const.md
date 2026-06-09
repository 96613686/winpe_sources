# ScheduleOMADMClientTask(ushort const *,ushort const *)

- ea: `0x18000da38`
- end: `0x18000db17`
- name: `?ScheduleOMADMClientTask@@YAJPEBG0@Z`
- size: `223`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fc24`

## callees

- `0x1800086c4`
- `0x18000c938`
- `0x18000da38`
- `0x18000db20`
- `0x18000e888`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000dae5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000daf8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000dae5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000daf8`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTask(unsigned __int16 *a1, const unsigned __int16 *a2)
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
    v4 = ScheduleOMADMClientTaskHelper((__int64)a1, a2, L"Schedule to run OMADMClient by server", 1);
    if ( v4 >= 0 )
    {
      v4 = ScheduleOMADMClientTaskHelper((__int64)a1, a2, L"Schedule to run OMADMClient by client", 0);
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
0x18000da38  mov     rax, rsp
0x18000da3b  mov     [rax+8], rbx
0x18000da3f  mov     [rax+10h], rsi
0x18000da43  push    rdi; int
0x18000da44  sub     rsp, 20h
0x18000da48  mov     rdi, rcx
0x18000da4b  mov     dword ptr [rax+18h], 0
0x18000da52  lea     rcx, [rax+18h]; this
0x18000da56  mov     rsi, rdx
0x18000da59  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x18000da5e  mov     ebx, eax
0x18000da60  test    eax, eax
0x18000da62  js      loc_18000DAF1
0x18000da68  mov     r9d, 1
0x18000da6e  lea     r8, aScheduleToRunO_0; "Schedule to run OMADMClient by server"
0x18000da75  mov     rdx, rsi
0x18000da78  mov     rcx, rdi
0x18000da7b  call    ScheduleOMADMClientTaskHelper
0x18000da80  mov     ebx, eax
0x18000da82  test    eax, eax
0x18000da84  js      short loc_18000DAF1
0x18000da86  xor     r9d, r9d
0x18000da89  lea     r8, aScheduleToRunO; "Schedule to run OMADMClient by client"
0x18000da90  mov     rdx, rsi
0x18000da93  mov     rcx, rdi
0x18000da96  call    ScheduleOMADMClientTaskHelper
0x18000da9b  mov     ebx, eax
0x18000da9d  test    eax, eax
0x18000da9f  js      short loc_18000DAF1
0x18000daa1  lea     rcx, [rsp+28h+arg_18]; this
0x18000daa6  mov     [rsp+28h+arg_18], 0
0x18000daae  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x18000dab3  mov     ebx, eax
0x18000dab5  test    eax, eax
0x18000dab7  jns     short loc_18000DAD4
0x18000dab9  mov     rcx, [rsp+28h]; this
0x18000dabe  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18000dac5  mov     r9d, eax; char *
0x18000dac8  mov     edx, 0AB4h; void *
0x18000dacd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dad2  jmp     short loc_18000DADE
0x18000dad4  mov     rcx, rdi
0x18000dad7  call    ScheduleProvisioningInitiatedSyncHelper
0x18000dadc  mov     ebx, eax
0x18000dade  cmp     [rsp+28h+arg_18], 0
0x18000dae3  jz      short loc_18000DAF1
0x18000dae5  call    cs:__imp_CoUninitialize
0x18000daec  nop     dword ptr [rax+rax+00h]
0x18000daf1  cmp     [rsp+28h+arg_10], 0
0x18000daf6  jz      short loc_18000DB04
0x18000daf8  call    cs:__imp_CoUninitialize
0x18000daff  nop     dword ptr [rax+rax+00h]
0x18000db04  mov     rsi, [rsp+28h+arg_8]
0x18000db09  mov     eax, ebx
0x18000db0b  mov     rbx, [rsp+28h+arg_0]
0x18000db10  add     rsp, 20h
0x18000db14  pop     rdi
0x18000db15  retn
```
