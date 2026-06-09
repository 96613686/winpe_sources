# PimIMService::WaitForContactsIndexingReady(void)

- ea: `0x18000b2b8`
- end: `0x18000b335`
- name: `?WaitForContactsIndexingReady@PimIMService@@QEAAXXZ`
- size: `125`
- prototype: `void __fastcall(PimIMService *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ca60`
- `0x18000cd60`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x18000b2b8`
- `0x18000c800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b2c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b2c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b304`

## string_xrefs

- `0x18000b2df`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\PimIMService.h`
- `0x18000b320`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\PimIMService.h`

## pseudocode

```c
void __fastcall PimIMService::WaitForContactsIndexingReady(PimIMService *this)
{
  DWORD v1; // eax
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  signed int LastError; // eax
  bool v6; // sf

  v1 = WaitForSingleObject(*(&hEvent + 1), 0x7530u);
  if ( v1 )
  {
    if ( v1 == 258 )
    {
      Log_AssertionEvent(
        v2,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\PimIMService.h",
        386);
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
        McTemplateU0s_EventWriteTransfer(v4, v3, "Contacts search clients timeout");
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = LastError < 0;
      }
      if ( v6 )
        Log_HREvent(
          (unsigned int)LastError,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\PimIMService.h",
          392);
    }
  }
}

```

## disassembly

```asm
0x18000b2b8  sub     rsp, 38h
0x18000b2bc  mov     rcx, qword ptr cs:hEvent+8; hHandle
0x18000b2c3  mov     edx, 7530h; dwMilliseconds
0x18000b2c8  call    cs:__imp_WaitForSingleObject
0x18000b2ce  test    eax, eax
0x18000b2d0  jz      short loc_18000B330
0x18000b2d2  cmp     eax, 102h
0x18000b2d7  jnz     short loc_18000B304
0x18000b2d9  mov     r8d, 182h
0x18000b2df  lea     rdx, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b2e6  call    Log_AssertionEvent
0x18000b2eb  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x18000b2f2  jge     short loc_18000B330
0x18000b2f4  lea     r8, aContactsSearch; "Contacts search clients timeout"
0x18000b2fb  add     rsp, 38h
0x18000b2ff  jmp     McTemplateU0s_EventWriteTransfer
0x18000b304  call    cs:__imp_GetLastError
0x18000b30a  test    eax, eax
0x18000b30c  jle     short loc_18000B318
0x18000b30e  movzx   eax, ax
0x18000b311  or      eax, 80070000h
0x18000b316  test    eax, eax
0x18000b318  jns     short loc_18000B330
0x18000b31a  mov     r9d, 188h
0x18000b320  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b327  xor     edx, edx
0x18000b329  mov     ecx, eax
0x18000b32b  call    Log_HREvent
0x18000b330  add     rsp, 38h
0x18000b334  retn
```
