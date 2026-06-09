# PimIMService_Resume

- ea: `0x18000cc80`
- end: `0x18000cd4b`
- name: `PimIMService_Resume`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x1800089c4`
- `0x18000cc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cce4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccee`

## string_xrefs

- `0x18000cca5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000cd09`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService_Resume(__int64 a1, _DWORD *a2)
{
  int v3; // ebx
  __int64 v4; // r9
  signed __int32 v6; // eax
  signed int LastError; // eax

  v3 = PimIMService::OnLoad((struct _RTL_CRITICAL_SECTION *)&myService);
  if ( v3 < 0 )
  {
    v4 = 3738;
LABEL_3:
    Log_HREvent(
      (unsigned int)v3,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v4);
    return (unsigned int)v3;
  }
  v6 = _InterlockedCompareExchange((volatile signed __int32 *)&dword_18002DD8C, (signed __int32)dword_18002DD8C, 0);
  if ( !v6 )
  {
    v3 = -2147418113;
LABEL_11:
    v4 = 3739;
    goto LABEL_3;
  }
  if ( v6 != 1 || SetEvent(hEvent) )
  {
    _InterlockedDecrement((volatile signed __int32 *)&dword_18002DD8C);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(
      (unsigned int)v3,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3285);
    if ( v3 < 0 )
      goto LABEL_11;
  }
  *a2 = _InterlockedCompareExchange((volatile signed __int32 *)&dword_18002DD8C, (signed __int32)dword_18002DD8C, 0);
  return 0;
}

```

## disassembly

```asm
0x18000cc80  mov     [rsp+arg_0], rbx
0x18000cc85  push    rdi
0x18000cc86  sub     rsp, 30h
0x18000cc8a  lea     rcx, ?myService@@3VPimIMService@@A; pv
0x18000cc91  mov     rdi, rdx
0x18000cc94  call    ?OnLoad@PimIMService@@QEAAJXZ; PimIMService::OnLoad(void)
0x18000cc99  mov     ebx, eax
0x18000cc9b  test    eax, eax
0x18000cc9d  jns     short loc_18000CCBF
0x18000cc9f  mov     r9d, 0E9Ah
0x18000cca5  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ccac  mov     edx, 1
0x18000ccb1  mov     ecx, ebx
0x18000ccb3  call    Log_HREvent
0x18000ccb8  mov     eax, ebx
0x18000ccba  jmp     loc_18000CD40
0x18000ccbf  mov     ecx, cs:dword_18002DD8C
0x18000ccc5  xor     eax, eax
0x18000ccc7  lock cmpxchg cs:dword_18002DD8C, ecx
0x18000cccf  jnz     short loc_18000CCD8
0x18000ccd1  mov     ebx, 8000FFFFh
0x18000ccd6  jmp     short loc_18000CD1D
0x18000ccd8  cmp     eax, 1
0x18000ccdb  jnz     short loc_18000CD25
0x18000ccdd  mov     rcx, qword ptr cs:hEvent; hEvent
0x18000cce4  call    cs:__imp_SetEvent
0x18000ccea  test    eax, eax
0x18000ccec  jnz     short loc_18000CD25
0x18000ccee  call    cs:__imp_GetLastError
0x18000ccf4  mov     ebx, eax
0x18000ccf6  test    eax, eax
0x18000ccf8  jle     short loc_18000CD03
0x18000ccfa  movzx   ebx, ax
0x18000ccfd  or      ebx, 80070000h
0x18000cd03  mov     r9d, 0CD5h
0x18000cd09  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000cd10  xor     edx, edx
0x18000cd12  mov     ecx, ebx
0x18000cd14  call    Log_HREvent
0x18000cd19  test    ebx, ebx
0x18000cd1b  jns     short loc_18000CD2C
0x18000cd1d  mov     r9d, 0E9Bh
0x18000cd23  jmp     short loc_18000CCA5
0x18000cd25  lock dec cs:dword_18002DD8C
0x18000cd2c  mov     ecx, cs:dword_18002DD8C
0x18000cd32  xor     eax, eax
0x18000cd34  lock cmpxchg cs:dword_18002DD8C, ecx
0x18000cd3c  mov     [rdi], eax
0x18000cd3e  xor     eax, eax
0x18000cd40  mov     rbx, [rsp+38h+arg_0]
0x18000cd45  add     rsp, 30h
0x18000cd49  pop     rdi
0x18000cd4a  retn
```
