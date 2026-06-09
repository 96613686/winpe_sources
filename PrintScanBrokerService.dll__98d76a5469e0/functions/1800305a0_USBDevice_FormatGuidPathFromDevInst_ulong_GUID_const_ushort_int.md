# USBDevice::_FormatGuidPathFromDevInst(ulong,_GUID const *,ushort *,int)

- ea: `0x1800305a0`
- end: `0x1800306d1`
- name: `?_FormatGuidPathFromDevInst@USBDevice@@AEAAHKPEBU_GUID@@PEAGH@Z`
- size: `305`
- prototype: `__int64 __fastcall(USBDevice *this, DEVINST, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003010c`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000e5f4`
- `0x18000f760`
- `0x1800305a0`

## import_xrefs

- `SETUPAPI!CM_Get_Device_IDW` at `0x1800305f2`
- `SETUPAPI!CM_Get_Device_IDW` at `0x1800305f2`
- `RPCRT4!RpcStringFreeW` at `0x18003068a`
- `RPCRT4!RpcStringFreeW` at `0x18003068a`
- `RPCRT4!UuidToStringW` at `0x180030637`
- `RPCRT4!UuidToStringW` at `0x180030637`

## string_xrefs

- `0x180030679`: `USBDevice::_FormatGuidPathFromDevInst`
- `0x18003069e`: `USBDevice::_FormatGuidPathFromDevInst`

## pseudocode

```c
// Hidden C++ exception states: #wind=111
__int64 __fastcall USBDevice::_FormatGuidPathFromDevInst(
        USBDevice *this,
        DEVINST a2,
        const struct _GUID *a3,
        unsigned __int16 *a4)
{
  CONFIGRET Device_IDW; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  WCHAR v9; // cx
  int v10; // eax
  RPC_WSTR StringUuid[2]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  StringUuid[0] = 0;
  memset_0(Buffer, 0, 0x208u);
  Device_IDW = CM_Get_Device_IDW(a2, Buffer, 0x104u, 0);
  if ( Device_IDW )
  {
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "USBDevice::_FormatGuidPathFromDevInst",
      L"CM_Get_DeviceID failed 0x%x",
      Device_IDW);
    return 0;
  }
  v7 = 0;
  v8 = 1;
  do
  {
    v9 = Buffer[v7];
    if ( !v9 )
      break;
    if ( v9 == 92 )
      Buffer[v7] = 35;
    ++v7;
  }
  while ( v7 < 0x104 );
  if ( UuidToStringW(&Uuid, StringUuid) )
    return 0;
  v10 = StringCchPrintfW(a4, 0x104u, L"\\\\?\\%ws#{%ws}", Buffer, StringUuid[0]);
  if ( v10 < 0 )
  {
    v8 = 0;
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "USBDevice::_FormatGuidPathFromDevInst",
      L"StringCchPrintf for %ws failed 0x%x",
      Buffer,
      (unsigned int)v10);
  }
  RpcStringFreeW(StringUuid);
  return v8;
}

```

## disassembly

```asm
0x1800305a0  mov     [rsp+arg_0], rbx
0x1800305a5  mov     [rsp+arg_10], rsi
0x1800305aa  push    rdi
0x1800305ab  sub     rsp, 260h
0x1800305b2  mov     rax, cs:__security_cookie
0x1800305b9  xor     rax, rsp
0x1800305bc  mov     [rsp+268h+var_18], rax
0x1800305c4  mov     ebx, edx
0x1800305c6  lea     rcx, [rsp+268h+Buffer]; void *
0x1800305cb  xor     esi, esi
0x1800305cd  xor     edx, edx; Val
0x1800305cf  mov     r8d, 208h; Size
0x1800305d5  mov     [rsp+268h+StringUuid], rsi
0x1800305da  mov     rdi, r9
0x1800305dd  call    memset_0
0x1800305e2  xor     r9d, r9d; ulFlags
0x1800305e5  lea     rdx, [rsp+268h+Buffer]; Buffer
0x1800305ea  mov     r8d, 104h; BufferLen
0x1800305f0  mov     ecx, ebx; dnDevInst
0x1800305f2  call    cs:__imp_CM_Get_Device_IDW
0x1800305f8  test    eax, eax
0x1800305fa  jnz     loc_180030694
0x180030600  mov     eax, esi
0x180030602  lea     ebx, [rsi+1]
0x180030605  movsxd  rdx, eax
0x180030608  movzx   ecx, [rsp+rdx*2+268h+Buffer]
0x18003060d  test    cx, cx
0x180030610  jz      short loc_18003062B
0x180030612  cmp     cx, 5Ch ; '\'
0x180030616  jnz     short loc_180030622
0x180030618  mov     ecx, 23h ; '#'
0x18003061d  mov     [rsp+rdx*2+268h+Buffer], cx
0x180030622  add     eax, ebx
0x180030624  cmp     eax, 104h
0x180030629  jb      short loc_180030605
0x18003062b  lea     rdx, [rsp+268h+StringUuid]; StringUuid
0x180030630  lea     rcx, Uuid; Uuid
0x180030637  call    cs:__imp_UuidToStringW
0x18003063d  test    eax, eax
0x18003063f  jnz     short loc_1800306AA
0x180030641  mov     rax, [rsp+268h+StringUuid]
0x180030646  lea     r9, [rsp+268h+Buffer]
0x18003064b  lea     r8, aWsWs; "\\\\?\\%ws#{%ws}"
0x180030652  mov     [rsp+268h+var_248], rax
0x180030657  mov     edx, 104h; unsigned __int64
0x18003065c  mov     rcx, rdi; unsigned __int16 *
0x18003065f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030664  test    eax, eax
0x180030666  jns     short loc_180030685
0x180030668  mov     r9d, eax
0x18003066b  lea     r8, [rsp+268h+Buffer]
0x180030670  lea     rdx, aStringcchprint; "StringCchPrintf for %ws failed 0x%x"
0x180030677  mov     ebx, esi
0x180030679  lea     rcx, aUsbdeviceForma; "USBDevice::_FormatGuidPathFromDevInst"
0x180030680  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180030685  lea     rcx, [rsp+268h+StringUuid]; String
0x18003068a  call    cs:__imp_RpcStringFreeW
0x180030690  mov     eax, ebx
0x180030692  jmp     short loc_1800306AC
0x180030694  mov     r8d, eax
0x180030697  lea     rdx, aCmGetDeviceidF; "CM_Get_DeviceID failed 0x%x"
0x18003069e  lea     rcx, aUsbdeviceForma; "USBDevice::_FormatGuidPathFromDevInst"
0x1800306a5  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800306aa  xor     eax, eax
0x1800306ac  mov     rcx, [rsp+268h+var_18]
0x1800306b4  xor     rcx, rsp; StackCookie
0x1800306b7  call    __security_check_cookie
0x1800306bc  lea     r11, [rsp+268h+var_8]
0x1800306c4  mov     rbx, [r11+10h]
0x1800306c8  mov     rsi, [r11+20h]
0x1800306cc  mov     rsp, r11
0x1800306cf  pop     rdi
0x1800306d0  retn
```
