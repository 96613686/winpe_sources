# RepairJoinInfo(ushort const *)

- ea: `0x18007ca54`
- end: `0x18007cc24`
- name: `?RepairJoinInfo@@YAJPEBG@Z`
- size: `464`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18007bcb0`

## callees

- `0x180071e14`
- `0x18007ca54`
- `0x18009433c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007cb03`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007cb03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ca73`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007ca73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cb5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cc11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007cc11`

## string_xrefs

- `0x18007cbd2`: `DsrBeginRepairDeviceJoinInfo failed`
- `0x18007cba8`: `WaitForSingleObject timed out for DsrBeginRepairDeviceJoinInfo`
- `0x18007cb86`: `WaitForSingleObject failed for DsrBeginRepairDeviceJoinInfo`
- `0x18007cb2d`: `WaitForSingleObject returned unexpected wait status for DsrBeginRepairDeviceJoinInfo`

## pseudocode

```c
__int64 __fastcall RepairJoinInfo(const unsigned __int16 *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  signed int LastError; // eax
  signed int v5; // ebx
  DWORD v6; // eax
  signed int v7; // eax
  int v9; // [rsp+30h] [rbp-38h]
  int v10; // [rsp+30h] [rbp-38h]
  const char *v11; // [rsp+38h] [rbp-30h]
  const char *v12; // [rsp+38h] [rbp-30h]
  HANDLE hHandle[3]; // [rsp+50h] [rbp-18h] BYREF

  hHandle[0] = 0;
  hHandle[1] = CreateEventW(0, 0, 0, 0);
  if ( hHandle[1] )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v11 = "HRESULT";
      v9 = 37;
LABEL_20:
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v5, "clouddomainhelper.cpp", v9, v11, &base);
      goto LABEL_21;
    }
  }
  v5 = DsrBeginRepairDeviceJoinInfo(a1, v2, v3, hHandle);
  if ( v5 < 0 )
  {
    v11 = "HRESULT";
    v9 = 43;
    goto LABEL_20;
  }
  v6 = WaitForSingleObject(hHandle[1], 0x1D4C0u);
  if ( v6 )
  {
    if ( v6 == 258 )
    {
      v12 = "WaitForSingleObject timed out for DsrBeginRepairDeviceJoinInfo";
      v10 = 57;
      goto LABEL_12;
    }
    if ( v6 != -1 )
    {
      v12 = "WaitForSingleObject returned unexpected wait status for DsrBeginRepairDeviceJoinInfo";
      v10 = 67;
LABEL_12:
      v5 = -2147023436;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -2147023436, "clouddomainhelper.cpp", v10, v12, &base);
      goto LABEL_21;
    }
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 < 0 )
    {
      v11 = "WaitForSingleObject failed for DsrBeginRepairDeviceJoinInfo";
      v9 = 62;
      goto LABEL_20;
    }
  }
  else
  {
    v5 = (signed int)hHandle[0];
    if ( SLODWORD(hHandle[0]) < 0 )
    {
      v11 = "DsrBeginRepairDeviceJoinInfo failed";
      v9 = 52;
      goto LABEL_20;
    }
  }
LABEL_21:
  CloseHandle(hHandle[1]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007ca54  mov     [rsp+arg_0], rbx
0x18007ca59  push    rdi
0x18007ca5a  sub     rsp, 60h
0x18007ca5e  mov     rdi, rcx
0x18007ca61  xorps   xmm0, xmm0
0x18007ca64  xor     ecx, ecx; lpEventAttributes
0x18007ca66  xor     r9d, r9d; lpName
0x18007ca69  xor     r8d, r8d; bInitialState
0x18007ca6c  xor     edx, edx; bManualReset
0x18007ca6e  movups  xmmword ptr [rsp+68h+hHandle], xmm0
0x18007ca73  call    cs:__imp_CreateEventW
0x18007ca79  mov     [rsp+68h+hHandle+8], rax
0x18007ca7e  test    rax, rax
0x18007ca81  jz      short loc_18007CAC1
0x18007ca83  call    cs:__imp_GetLastError
0x18007ca89  mov     ebx, eax
0x18007ca8b  test    eax, eax
0x18007ca8d  jle     short loc_18007CA98
0x18007ca8f  movzx   ebx, ax
0x18007ca92  or      ebx, 80070000h
0x18007ca98  test    ebx, ebx
0x18007ca9a  jns     short loc_18007CAC1
0x18007ca9c  lea     rax, base
0x18007caa3  mov     [rsp+68h+var_28], rax
0x18007caa8  lea     rax, aHresult; "HRESULT"
0x18007caaf  mov     [rsp+68h+var_30], rax
0x18007cab4  mov     [rsp+68h+var_38], 25h ; '%'
0x18007cabc  jmp     loc_18007CBE6
0x18007cac1  lea     r9, [rsp+68h+hHandle]
0x18007cac6  mov     rcx, rdi
0x18007cac9  call    DsrBeginRepairDeviceJoinInfo
0x18007cace  mov     ebx, eax
0x18007cad0  test    eax, eax
0x18007cad2  jns     short loc_18007CAF9
0x18007cad4  lea     rax, base
0x18007cadb  mov     [rsp+68h+var_28], rax
0x18007cae0  lea     rax, aHresult; "HRESULT"
0x18007cae7  mov     [rsp+68h+var_30], rax
0x18007caec  mov     [rsp+68h+var_38], 2Bh ; '+'
0x18007caf4  jmp     loc_18007CBE6
0x18007caf9  mov     rcx, [rsp+68h+hHandle+8]; hHandle
0x18007cafe  mov     edx, 1D4C0h; dwMilliseconds
0x18007cb03  call    cs:__imp_WaitForSingleObject
0x18007cb09  test    eax, eax
0x18007cb0b  jz      loc_18007CBBE
0x18007cb11  cmp     eax, 102h
0x18007cb16  jz      loc_18007CB9C
0x18007cb1c  cmp     eax, 0FFFFFFFFh
0x18007cb1f  jz      short loc_18007CB5D
0x18007cb21  lea     rax, base
0x18007cb28  mov     [rsp+68h+var_28], rax
0x18007cb2d  lea     rax, aWaitforsingleo_1; "WaitForSingleObject returned unexpected"...
0x18007cb34  mov     [rsp+68h+var_30], rax
0x18007cb39  mov     [rsp+68h+var_38], 43h ; 'C'
0x18007cb41  mov     ecx, 800705B4h
0x18007cb46  lea     rax, aOnecoreuapDsEx_13+20h; "clouddomainhelper.cpp"
0x18007cb4d  mov     [rsp+68h+var_40], rax
0x18007cb52  mov     ebx, ecx
0x18007cb54  mov     [rsp+68h+var_48], ecx
0x18007cb58  jmp     loc_18007CBF6
0x18007cb5d  call    cs:__imp_GetLastError
0x18007cb63  mov     ebx, eax
0x18007cb65  test    eax, eax
0x18007cb67  jle     short loc_18007CB72
0x18007cb69  movzx   ebx, ax
0x18007cb6c  or      ebx, 80070000h
0x18007cb72  test    ebx, ebx
0x18007cb74  jns     loc_18007CC0C
0x18007cb7a  lea     rax, base
0x18007cb81  mov     [rsp+68h+var_28], rax
0x18007cb86  lea     rax, aWaitforsingleo; "WaitForSingleObject failed for DsrBegin"...
0x18007cb8d  mov     [rsp+68h+var_30], rax
0x18007cb92  mov     [rsp+68h+var_38], 3Eh ; '>'
0x18007cb9a  jmp     short loc_18007CBE6
0x18007cb9c  lea     rax, base
0x18007cba3  mov     [rsp+68h+var_28], rax
0x18007cba8  lea     rax, aWaitforsingleo_0; "WaitForSingleObject timed out for DsrBe"...
0x18007cbaf  mov     [rsp+68h+var_30], rax
0x18007cbb4  mov     [rsp+68h+var_38], 39h ; '9'
0x18007cbbc  jmp     short loc_18007CB41
0x18007cbbe  mov     ebx, dword ptr [rsp+68h+hHandle]
0x18007cbc2  test    ebx, ebx
0x18007cbc4  jns     short loc_18007CC0C
0x18007cbc6  lea     rax, base
0x18007cbcd  mov     [rsp+68h+var_28], rax
0x18007cbd2  lea     rax, aDsrbeginrepair; "DsrBeginRepairDeviceJoinInfo failed"
0x18007cbd9  mov     [rsp+68h+var_30], rax
0x18007cbde  mov     [rsp+68h+var_38], 34h ; '4'
0x18007cbe6  lea     rax, aOnecoreuapDsEx_13+20h; "clouddomainhelper.cpp"
0x18007cbed  mov     [rsp+68h+var_40], rax
0x18007cbf2  mov     [rsp+68h+var_48], ebx
0x18007cbf6  mov     ecx, 2
0x18007cbfb  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007cc02  mov     r9d, ecx
0x18007cc05  xor     edx, edx
0x18007cc07  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007cc0c  mov     rcx, [rsp+68h+hHandle+8]; hObject
0x18007cc11  call    cs:__imp_CloseHandle
0x18007cc17  mov     eax, ebx
0x18007cc19  mov     rbx, [rsp+68h+arg_0]
0x18007cc1e  add     rsp, 60h
0x18007cc22  pop     rdi
0x18007cc23  retn
```
