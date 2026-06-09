# Log_HREvent_7

- ea: `0x18001cb30`
- end: `0x18001cb7a`
- name: `Log_HREvent_7`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bce0`
- `0x18001bd20`
- `0x18001be30`
- `0x18001bf58`
- `0x18001c200`
- `0x18001c330`
- `0x18001c400`
- `0x18001c460`
- `0x18001c6c0`
- `0x18001ca40`
- `0x18001cb80`
- `0x18001ce80`
- `0x18001cec0`
- `0x18001cf00`
- `0x18001d1f0`

## callees

- `0x1800034bc`
- `0x18001cb30`

## string_xrefs

- `0x18001cb62`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`

## pseudocode

```c
__int64 __fastcall Log_HREvent_7(int a1, int a2, __int64 a3, char a4)
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
           (unsigned int)"onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
           a4);
}

```

## disassembly

```asm
0x18001cb30  sub     rsp, 38h
0x18001cb34  test    edx, edx
0x18001cb36  jz      short loc_18001CB4A
0x18001cb38  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 2
0x18001cb3f  jz      short loc_18001CB75
0x18001cb41  lea     rdx, CommsErrorPropagateEvent
0x18001cb48  jmp     short loc_18001CB5A
0x18001cb4a  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 1
0x18001cb51  jz      short loc_18001CB75
0x18001cb53  lea     rdx, CommsErrorOriginateEvent
0x18001cb5a  mov     [rsp+38h+var_18], r9d
0x18001cb5f  mov     r8d, ecx
0x18001cb62  lea     r9, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001cb69  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18001cb70  call    McTemplateU0dsq_EventWriteTransfer
0x18001cb75  add     rsp, 38h
0x18001cb79  retn
```
