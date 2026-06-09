# WdipETWRegister

- ea: `0x180017840`
- end: `0x1800178a1`
- name: `WdipETWRegister`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b0a0`

## callees

- `0x180009090`
- `0x180017840`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180017859`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180017859`

## string_xrefs

- `0x180017887`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`

## pseudocode

```c
__int64 WdipETWRegister()
{
  signed int v0; // eax
  signed int v1; // ebx
  char Args[4]; // [rsp+20h] [rbp-18h]

  v0 = EventRegister(&WDI_DPS_PROVIDER, 0, 0, &g_hETW);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 < 0 )
  {
    *(_DWORD *)Args = (unsigned __int16)v1;
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
      (__int64)L"WdipETWRegister",
      772,
      (const wchar_t *)L"Error = %d",
      *(_DWORD *)Args);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180017840  push    rbx
0x180017842  sub     rsp, 30h
0x180017846  lea     r9, g_hETW; RegHandle
0x18001784d  xor     r8d, r8d; CallbackContext
0x180017850  xor     edx, edx; EnableCallback
0x180017852  lea     rcx, WDI_DPS_PROVIDER; ProviderId
0x180017859  call    cs:__imp_EventRegister
0x18001785f  mov     ebx, eax
0x180017861  test    eax, eax
0x180017863  jle     short loc_18001786E
0x180017865  movzx   ebx, ax
0x180017868  or      ebx, 80070000h
0x18001786e  test    ebx, ebx
0x180017870  jns     short loc_180017899
0x180017872  movzx   ecx, bx
0x180017875  lea     r9, aErrorD; "Error = %d"
0x18001787c  mov     dword ptr [rsp+38h+Args], ecx; Args
0x180017880  lea     rdx, aWdipetwregiste; "WdipETWRegister"
0x180017887  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001788e  mov     r8d, 304h; int
0x180017894  call    WdipTraceError
0x180017899  mov     eax, ebx
0x18001789b  add     rsp, 30h
0x18001789f  pop     rbx
0x1800178a0  retn
```
