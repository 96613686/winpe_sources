# Log_HREvent_2

- ea: `0x1800104b8`
- end: `0x180010502`
- name: `Log_HREvent_2`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008fe0`
- `0x18000e838`
- `0x18000ee40`
- `0x18000f730`
- `0x18000f7e0`
- `0x18000fa6c`
- `0x18000fbcc`
- `0x18001122c`
- `0x18001134c`
- `0x18001146c`
- `0x180011b6c`
- `0x180011f70`
- `0x180012264`
- `0x180012384`

## callees

- `0x1800034bc`
- `0x1800104b8`

## string_xrefs

- `0x1800104ea`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esedatasource.cpp`

## pseudocode

```c
__int64 __fastcall Log_HREvent_2(int a1, int a2, __int64 a3, char a4)
{
  __int64 *v4; // rdx
  __int64 result; // rax

  if ( a2 )
  {
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 2) == 0 )
      return result;
    v4 = CommsErrorPropagateEvent;
  }
  else
  {
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 1) == 0 )
      return result;
    v4 = CommsErrorOriginateEvent;
  }
  return McTemplateU0dsq_EventWriteTransfer(
           (unsigned int)&MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
           (_DWORD)v4,
           a1,
           (unsigned int)"onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esedatasource.cpp",
           a4);
}

```

## disassembly

```asm
0x1800104b8  sub     rsp, 38h
0x1800104bc  test    edx, edx
0x1800104be  jz      short loc_1800104D2
0x1800104c0  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 2
0x1800104c7  jz      short loc_1800104FD
0x1800104c9  lea     rdx, CommsErrorPropagateEvent
0x1800104d0  jmp     short loc_1800104E2
0x1800104d2  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 1
0x1800104d9  jz      short loc_1800104FD
0x1800104db  lea     rdx, CommsErrorOriginateEvent
0x1800104e2  mov     [rsp+38h+var_18], r9d
0x1800104e7  mov     r8d, ecx
0x1800104ea  lea     r9, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800104f1  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x1800104f8  call    McTemplateU0dsq_EventWriteTransfer
0x1800104fd  add     rsp, 38h
0x180010501  retn
```
