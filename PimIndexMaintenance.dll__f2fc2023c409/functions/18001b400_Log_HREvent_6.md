# Log_HREvent_6

- ea: `0x18001b400`
- end: `0x18001b44a`
- name: `Log_HREvent_6`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ab40`
- `0x18001abb8`
- `0x18001ad00`
- `0x18001ad50`
- `0x18001af50`
- `0x18001b0d0`
- `0x18001b1d4`
- `0x18001b288`
- `0x18001b5f0`
- `0x18001b830`
- `0x18001b930`

## callees

- `0x1800034bc`
- `0x18001b400`

## string_xrefs

- `0x18001b432`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\unifiedstoreaggregatedatasource.cpp`

## pseudocode

```c
__int64 __fastcall Log_HREvent_6(int a1, int a2, __int64 a3, char a4)
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
           (unsigned int)"onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\unified"
                         "storeaggregatedatasource.cpp",
           a4);
}

```

## disassembly

```asm
0x18001b400  sub     rsp, 38h
0x18001b404  test    edx, edx
0x18001b406  jz      short loc_18001B41A
0x18001b408  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 2
0x18001b40f  jz      short loc_18001B445
0x18001b411  lea     rdx, CommsErrorPropagateEvent
0x18001b418  jmp     short loc_18001B42A
0x18001b41a  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 1
0x18001b421  jz      short loc_18001B445
0x18001b423  lea     rdx, CommsErrorOriginateEvent
0x18001b42a  mov     [rsp+38h+var_18], r9d
0x18001b42f  mov     r8d, ecx
0x18001b432  lea     r9, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001b439  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18001b440  call    McTemplateU0dsq_EventWriteTransfer
0x18001b445  add     rsp, 38h
0x18001b449  retn
```
