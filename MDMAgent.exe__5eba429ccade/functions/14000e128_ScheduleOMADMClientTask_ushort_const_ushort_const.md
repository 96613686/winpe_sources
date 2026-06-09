# ScheduleOMADMClientTask(ushort const *,ushort const *)

- ea: `0x14000e128`
- end: `0x14000e1fa`
- name: `?ScheduleOMADMClientTask@@YAJPEBG0@Z`
- size: `210`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010000`

## callees

- `0x140006984`
- `0x140009cd8`
- `0x14000e128`
- `0x14000e200`
- `0x14000ef04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e1d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e1e2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e1d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e1e2`

## pseudocode

```c
__int64 __fastcall ScheduleOMADMClientTask(unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v4; // ebx
  HRESULT v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v8; // [rsp+40h] [rbp+18h] BYREF
  int v9; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v8);
  if ( v4 >= 0 )
  {
    v4 = ScheduleOMADMClientTaskHelper(a1, a2, L"Schedule to run OMADMClient by server", 1);
    if ( v4 >= 0 )
    {
      v4 = ScheduleOMADMClientTaskHelper(a1, a2, L"Schedule to run OMADMClient by client", 0);
      if ( v4 >= 0 )
      {
        v9 = 0;
        v5 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v9);
        v4 = v5;
        if ( v5 >= 0 )
          v4 = ScheduleProvisioningInitiatedSyncHelper(a1);
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAB4,
            (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)(unsigned int)v5);
        if ( v9 )
          CoUninitialize();
      }
    }
  }
  if ( v8 )
    CoUninitialize();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000e128  mov     rax, rsp
0x14000e12b  mov     [rax+8], rbx
0x14000e12f  mov     [rax+10h], rsi
0x14000e133  push    rdi; int
0x14000e134  sub     rsp, 20h
0x14000e138  mov     rdi, rcx
0x14000e13b  mov     dword ptr [rax+18h], 0
0x14000e142  lea     rcx, [rax+18h]; this
0x14000e146  mov     rsi, rdx
0x14000e149  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000e14e  mov     ebx, eax
0x14000e150  test    eax, eax
0x14000e152  js      loc_14000E1DB
0x14000e158  mov     r9d, 1
0x14000e15e  lea     r8, aScheduleToRunO_0; "Schedule to run OMADMClient by server"
0x14000e165  mov     rdx, rsi; unsigned __int16 *
0x14000e168  mov     rcx, rdi; unsigned __int16 *
0x14000e16b  call    ScheduleOMADMClientTaskHelper
0x14000e170  mov     ebx, eax
0x14000e172  test    eax, eax
0x14000e174  js      short loc_14000E1DB
0x14000e176  xor     r9d, r9d
0x14000e179  lea     r8, aScheduleToRunO; "Schedule to run OMADMClient by client"
0x14000e180  mov     rdx, rsi; unsigned __int16 *
0x14000e183  mov     rcx, rdi; unsigned __int16 *
0x14000e186  call    ScheduleOMADMClientTaskHelper
0x14000e18b  mov     ebx, eax
0x14000e18d  test    eax, eax
0x14000e18f  js      short loc_14000E1DB
0x14000e191  lea     rcx, [rsp+28h+arg_18]; this
0x14000e196  mov     [rsp+28h+arg_18], 0
0x14000e19e  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x14000e1a3  mov     ebx, eax
0x14000e1a5  test    eax, eax
0x14000e1a7  jns     short loc_14000E1C4
0x14000e1a9  mov     rcx, [rsp+28h]; this
0x14000e1ae  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000e1b5  mov     r9d, eax; char *
0x14000e1b8  mov     edx, 0AB4h; void *
0x14000e1bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e1c2  jmp     short loc_14000E1CE
0x14000e1c4  mov     rcx, rdi; unsigned __int16 *
0x14000e1c7  call    ScheduleProvisioningInitiatedSyncHelper
0x14000e1cc  mov     ebx, eax
0x14000e1ce  cmp     [rsp+28h+arg_18], 0
0x14000e1d3  jz      short loc_14000E1DB
0x14000e1d5  call    cs:__imp_CoUninitialize
0x14000e1db  cmp     [rsp+28h+arg_10], 0
0x14000e1e0  jz      short loc_14000E1E8
0x14000e1e2  call    cs:__imp_CoUninitialize
0x14000e1e8  mov     rsi, [rsp+28h+arg_8]
0x14000e1ed  mov     eax, ebx
0x14000e1ef  mov     rbx, [rsp+28h+arg_0]
0x14000e1f4  add     rsp, 20h
0x14000e1f8  pop     rdi
0x14000e1f9  retn
```
