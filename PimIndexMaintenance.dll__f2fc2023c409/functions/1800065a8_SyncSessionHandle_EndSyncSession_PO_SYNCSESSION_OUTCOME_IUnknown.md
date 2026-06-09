# SyncSessionHandle::EndSyncSession(PO_SYNCSESSION_OUTCOME,IUnknown * *)

- ea: `0x1800065a8`
- end: `0x1800066a5`
- name: `?EndSyncSession@SyncSessionHandle@@QEAAJW4PO_SYNCSESSION_OUTCOME@@PEAPEAUIUnknown@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004a7c`
- `0x18000523c`

## callees

- `0x180002da8`
- `0x180003468`
- `0x1800065a8`
- `0x1800086a0`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800065cf`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800065ea`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180006678`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall SyncSessionHandle::EndSyncSession(_DWORD *a1)
{
  int v2; // ebx
  __int64 v3; // rcx
  __int64 v4; // r8
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( a1[8] )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 168LL))(*(_QWORD *)a1);
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
        SYNC_SESSION_STOP,
        v4,
        1,
        v6);
    a1[8] = 0;
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
        PIMIndex_SyncSession_STOP,
        v4,
        1,
        v6);
    if ( v2 < 0 )
      Log_HREvent(
        (unsigned int)v2,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        207);
  }
  else
  {
    v2 = -2147024809;
    Log_HREvent(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      198);
    Log_AssertionEvent(
      v3,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      198);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800065a8  mov     [rsp+arg_18], rbx
0x1800065ad  push    rdi
0x1800065ae  sub     rsp, 50h
0x1800065b2  mov     rax, cs:__security_cookie
0x1800065b9  xor     rax, rsp
0x1800065bc  mov     [rsp+58h+var_18], rax
0x1800065c1  cmp     dword ptr [rcx+20h], 0
0x1800065c5  mov     rdi, rcx
0x1800065c8  jnz     short loc_1800065FB
0x1800065ca  mov     edi, 0C6h
0x1800065cf  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800065d6  mov     ebx, 80070057h
0x1800065db  mov     r9d, edi
0x1800065de  mov     ecx, ebx
0x1800065e0  xor     edx, edx
0x1800065e2  call    Log_HREvent
0x1800065e7  mov     r8d, edi
0x1800065ea  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800065f1  call    Log_AssertionEvent
0x1800065f6  jmp     loc_18000668B
0x1800065fb  mov     rcx, [rcx]
0x1800065fe  mov     rax, [rcx]
0x180006601  mov     rax, [rax+0A8h]
0x180006608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660d  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x180006614  mov     ebx, eax
0x180006616  jz      short loc_18000663B
0x180006618  lea     rax, [rsp+58h+var_28]
0x18000661d  mov     r9d, 1
0x180006623  lea     rdx, SYNC_SESSION_STOP
0x18000662a  mov     [rsp+58h+var_38], rax
0x18000662f  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180006636  call    McGenEventWrite_EventWriteTransfer
0x18000663b  mov     dword ptr [rdi+20h], 0
0x180006642  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 10h
0x180006649  jz      short loc_18000666E
0x18000664b  lea     rax, [rsp+58h+var_28]
0x180006650  mov     r9d, 1
0x180006656  lea     rdx, PIMIndex_SyncSession_STOP
0x18000665d  mov     [rsp+58h+var_38], rax
0x180006662  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180006669  call    McGenEventWrite_EventWriteTransfer
0x18000666e  test    ebx, ebx
0x180006670  jns     short loc_18000668B
0x180006672  mov     r9d, 0CFh
0x180006678  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000667f  mov     edx, 1
0x180006684  mov     ecx, ebx
0x180006686  call    Log_HREvent
0x18000668b  mov     eax, ebx
0x18000668d  mov     rcx, [rsp+58h+var_18]
0x180006692  xor     rcx, rsp; StackCookie
0x180006695  call    __security_check_cookie
0x18000669a  mov     rbx, [rsp+58h+arg_18]
0x18000669f  add     rsp, 50h
0x1800066a3  pop     rdi
0x1800066a4  retn
```
