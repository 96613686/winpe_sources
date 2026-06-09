# PimIMService::OnStarting(void)

- ea: `0x180008f30`
- end: `0x180008fd4`
- name: `?OnStarting@PimIMService@@UEAAJXZ`
- size: `164`
- prototype: `__int64 __fastcall(PimIMService *this, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002c08`
- `0x180002da8`
- `0x180002df4`
- `0x180005f20`
- `0x180008f30`

## import_xrefs

- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x180008f9e`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x180008f9e`

## string_xrefs

- `0x180008f7b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::OnStarting(PimIMService *this, __int64 a2)
{
  int v3; // ebx
  __int64 v4; // r9

  McGenEventRegister_EventRegister(
    MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE,
    a2,
    &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
    &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context);
  *((_DWORD *)this + 120) = 0;
  g_serviceShuttingDown = 0;
  v3 = PimIMService::DetectLocaleChange(this);
  if ( v3 < 0 )
  {
    v4 = 470;
LABEL_3:
    Log_HREvent(
      (unsigned int)v3,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v4);
    return (unsigned int)v3;
  }
  dword_18002D110 = *((_DWORD *)this + 124);
  v3 = UseEdgeBrowserComponentsForProcess();
  if ( v3 < 0 )
  {
    v4 = 475;
    goto LABEL_3;
  }
  v3 = RpcSetup(0);
  if ( v3 < 0 )
  {
    v4 = 478;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008f30  mov     [rsp+arg_0], rbx
0x180008f35  push    rdi
0x180008f36  sub     rsp, 30h
0x180008f3a  lea     r8, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x180008f41  mov     rdi, rcx
0x180008f44  mov     r9, r8
0x180008f47  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE
0x180008f4e  call    McGenEventRegister_EventRegister
0x180008f53  mov     rcx, rdi; this
0x180008f56  mov     dword ptr [rdi+1E0h], 0
0x180008f60  mov     cs:?g_serviceShuttingDown@@3HA, 0; int g_serviceShuttingDown
0x180008f6a  call    ?DetectLocaleChange@PimIMService@@QEAAJXZ; PimIMService::DetectLocaleChange(void)
0x180008f6f  mov     ebx, eax
0x180008f71  test    eax, eax
0x180008f73  jns     short loc_180008F92
0x180008f75  mov     r9d, 1D6h
0x180008f7b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008f82  mov     edx, 1
0x180008f87  mov     ecx, ebx
0x180008f89  call    Log_HREvent
0x180008f8e  mov     eax, ebx
0x180008f90  jmp     short loc_180008FC9
0x180008f92  mov     eax, [rdi+1F0h]
0x180008f98  mov     cs:dword_18002D110, eax
0x180008f9e  call    cs:__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ; UseEdgeBrowserComponentsForProcess(void)
0x180008fa4  mov     ebx, eax
0x180008fa6  test    eax, eax
0x180008fa8  jns     short loc_180008FB2
0x180008faa  mov     r9d, 1DBh
0x180008fb0  jmp     short loc_180008F7B
0x180008fb2  xor     ecx, ecx; pszSrc
0x180008fb4  call    ?RpcSetup@@YAJPEBG@Z; RpcSetup(ushort const *)
0x180008fb9  mov     ebx, eax
0x180008fbb  test    eax, eax
0x180008fbd  jns     short loc_180008FC7
0x180008fbf  mov     r9d, 1DEh
0x180008fc5  jmp     short loc_180008F7B
0x180008fc7  xor     eax, eax
0x180008fc9  mov     rbx, [rsp+38h+arg_0]
0x180008fce  add     rsp, 30h
0x180008fd2  pop     rdi
0x180008fd3  retn
```
