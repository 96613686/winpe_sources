# PimIMService::OnStarted(void)

- ea: `0x180008da0`
- end: `0x180008f0d`
- name: `?OnStarted@PimIMService@@UEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002d20`

## callees

- `0x180002da8`
- `0x180003468`
- `0x1800089c4`
- `0x180008da0`
- `0x18000a670`
- `0x18000c800`
- `0x180021240`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180008ec7`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180008ec7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180008e80`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180008e80`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008eed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008eed`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008dc0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008dc0`

## string_xrefs

- `0x180008dea`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180008edb`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180008dd2`: `onecoreuap\internal\base\inc\CComInit.h`

## pseudocode

```c
__int64 __fastcall PimIMService::OnStarted(char *pv)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  PimIMService *v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r8
  _BYTE v11[16]; // [rsp+40h] [rbp-28h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = PimIMService::OnLoad((struct _RTL_CRITICAL_SECTION *)pv);
    v3 = v4;
    if ( v4 >= 0 )
    {
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
        McTemplateU0s_EventWriteTransfer(v6, v5, "Submitting OnBoot work");
      PimIMService::SubmitTpWork(v6, (struct TpWorkInfo *)(pv + 608));
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
          THREAD_PREP_STOP,
          v9,
          1,
          v11);
      if ( *((_QWORD *)pv + 63) )
        RtlUnsubscribeWnfNotificationWaitForCompletion();
      *((_QWORD *)pv + 63) = 0;
      v4 = RtlSubscribeWnfStateChangeNotification(
             pv + 504,
             WNF_UDA_CONTACT_SORT_CHANGED,
             0,
             SortOrderChangeWnfCallback,
             0,
             0,
             0,
             0);
      v3 = v4;
      if ( v4 >= 0 )
      {
        v3 = 0;
        goto LABEL_15;
      }
      v7 = 513;
      v8 = 0;
    }
    else
    {
      v7 = 493;
      v8 = 1;
    }
    Log_HREvent(
      (unsigned int)v4,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v7);
LABEL_15:
    CoUninitialize();
    return v3;
  }
  Log_HREvent((unsigned int)v2, 1, "onecoreuap\\internal\\base\\inc\\CComInit.h", 37);
  Log_HREvent(
    v3,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    491);
  return v3;
}

```

## disassembly

```asm
0x180008da0  mov     [rsp+arg_8], rbx
0x180008da5  push    rdi
0x180008da6  sub     rsp, 60h
0x180008daa  mov     rax, cs:__security_cookie
0x180008db1  xor     rax, rsp
0x180008db4  mov     [rsp+68h+var_18], rax
0x180008db9  mov     rdi, rcx
0x180008dbc  xor     edx, edx; dwCoInit
0x180008dbe  xor     ecx, ecx; pvReserved
0x180008dc0  call    cs:__imp_CoInitializeEx
0x180008dc6  mov     ebx, eax
0x180008dc8  test    eax, eax
0x180008dca  jns     short loc_180008E02
0x180008dcc  mov     r9d, 25h ; '%'
0x180008dd2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\CComIn"...
0x180008dd9  mov     ecx, eax
0x180008ddb  lea     edx, [r9-24h]
0x180008ddf  call    Log_HREvent
0x180008de4  mov     r9d, 1EBh
0x180008dea  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008df1  mov     edx, 1
0x180008df6  mov     ecx, ebx
0x180008df8  call    Log_HREvent
0x180008dfd  jmp     loc_180008EF3
0x180008e02  mov     rcx, rdi; pv
0x180008e05  call    ?OnLoad@PimIMService@@QEAAJXZ; PimIMService::OnLoad(void)
0x180008e0a  mov     ebx, eax
0x180008e0c  test    eax, eax
0x180008e0e  jns     short loc_180008E20
0x180008e10  mov     r9d, 1EDh
0x180008e16  mov     edx, 1
0x180008e1b  jmp     loc_180008EDB
0x180008e20  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 80h
0x180008e27  jz      short loc_180008E35
0x180008e29  lea     r8, aSubmittingOnbo; "Submitting OnBoot work"
0x180008e30  call    McTemplateU0s_EventWriteTransfer
0x180008e35  lea     rdx, [rdi+260h]; struct TpWorkInfo *
0x180008e3c  call    ?SubmitTpWork@PimIMService@@QEAAXPEAUTpWorkInfo@@@Z; PimIMService::SubmitTpWork(TpWorkInfo *)
0x180008e41  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x180008e48  jz      short loc_180008E6D
0x180008e4a  lea     rax, [rsp+68h+var_28]
0x180008e4f  mov     r9d, 1
0x180008e55  lea     rdx, THREAD_PREP_STOP
0x180008e5c  mov     [rsp+68h+var_48], rax
0x180008e61  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180008e68  call    McGenEventWrite_EventWriteTransfer
0x180008e6d  mov     rcx, [rdi+1F8h]
0x180008e74  mov     rbx, cs:WNF_UDA_CONTACT_SORT_CHANGED
0x180008e7b  test    rcx, rcx
0x180008e7e  jz      short loc_180008E86
0x180008e80  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180008e86  mov     [rsp+68h+var_30], 0
0x180008e8e  lea     r9, SortOrderChangeWnfCallback
0x180008e95  mov     [rsp+68h+var_38], 0
0x180008e9d  lea     rcx, [rdi+1F8h]
0x180008ea4  mov     [rsp+68h+var_40], 0
0x180008ead  xor     r8d, r8d
0x180008eb0  mov     rdx, rbx
0x180008eb3  mov     [rsp+68h+var_48], 0
0x180008ebc  mov     qword ptr [rdi+1F8h], 0
0x180008ec7  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180008ecd  mov     ebx, eax
0x180008ecf  test    eax, eax
0x180008ed1  jns     short loc_180008EEB
0x180008ed3  mov     r9d, 201h
0x180008ed9  xor     edx, edx
0x180008edb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008ee2  mov     ecx, eax
0x180008ee4  call    Log_HREvent
0x180008ee9  jmp     short loc_180008EED
0x180008eeb  xor     ebx, ebx
0x180008eed  call    cs:__imp_CoUninitialize
0x180008ef3  mov     eax, ebx
0x180008ef5  mov     rcx, [rsp+68h+var_18]
0x180008efa  xor     rcx, rsp; StackCookie
0x180008efd  call    __security_check_cookie
0x180008f02  mov     rbx, [rsp+68h+arg_8]
0x180008f07  add     rsp, 60h
0x180008f0b  pop     rdi
0x180008f0c  retn
```
