# Log_AssertionEvent_6

- ea: `0x180020024`
- end: `0x18002005b`
- name: `Log_AssertionEvent_6`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f5f8`
- `0x18001f69c`
- `0x18001f7cc`
- `0x18001f8d4`
- `0x18001f98c`
- `0x18001fb0c`
- `0x18001fbe0`
- `0x18001fcc8`
- `0x18001fee4`
- `0x18002009c`
- `0x1800201e8`

## callees

- `0x1800034bc`
- `0x180020024`

## string_xrefs

- `0x180020036`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indextokenizer.cpp`

## pseudocode

```c
__int64 __fastcall Log_AssertionEvent_6(__int64 a1, __int64 a2, char a3)
{
  __int64 result; // rax

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 1) != 0 )
    return McTemplateU0dsq_EventWriteTransfer(
             (unsigned int)&MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
             (unsigned int)CommsErrorOriginateEvent,
             -2147418113,
             (unsigned int)"onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indextokenizer.cpp",
             a3);
  return result;
}

```

## disassembly

```asm
0x180020024  sub     rsp, 38h
0x180020028  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 1
0x18002002f  jz      short loc_180020056
0x180020031  mov     [rsp+38h+var_18], r8d
0x180020036  lea     r9, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002003d  mov     r8d, 8000FFFFh
0x180020043  lea     rdx, CommsErrorOriginateEvent
0x18002004a  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180020051  call    McTemplateU0dsq_EventWriteTransfer
0x180020056  add     rsp, 38h
0x18002005a  retn
```
