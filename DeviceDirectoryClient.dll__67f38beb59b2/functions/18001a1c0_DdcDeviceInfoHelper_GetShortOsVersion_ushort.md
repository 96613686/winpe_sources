# DdcDeviceInfoHelper::GetShortOsVersion(ushort * *)

- ea: `0x18001a1c0`
- end: `0x18001a329`
- name: `?GetShortOsVersion@DdcDeviceInfoHelper@@CAJPEAPEAG@Z`
- size: `361`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016aa4`

## callees

- `0x1800028d4`
- `0x180003288`
- `0x1800050b8`
- `0x18000d79c`
- `0x18001a1c0`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001a29d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001a29d`

## string_xrefs

- `0x18001a209`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001a2f6`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c

```

## disassembly

```asm
0x18001a1c0  mov     r11, rsp
0x18001a1c3  mov     [r11+10h], rbx
0x18001a1c7  mov     [r11+18h], rsi
0x18001a1cb  push    rdi
0x18001a1cc  sub     rsp, 40h
0x18001a1d0  mov     qword ptr [r11+8], 0
0x18001a1d8  mov     rdi, rcx
0x18001a1db  test    rcx, rcx
0x18001a1de  jnz     short loc_18001A21A
0x18001a1e0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a1e7  mov     r8d, 80070057h
0x18001a1ed  mov     ebx, r8d
0x18001a1f0  jz      loc_18001A317
0x18001a1f6  lea     rax, aCprPpwszshorto; "CPR(ppwszShortOsVersion)"
0x18001a1fd  mov     [r11-20h], rax
0x18001a201  mov     [rsp+48h+var_28], 435h
0x18001a209  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001a210  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a215  jmp     loc_18001A317
0x18001a21a  cmp     qword ptr [rcx], 0
0x18001a21e  jz      short loc_18001A24C
0x18001a220  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a227  mov     r8d, 80070057h
0x18001a22d  mov     ebx, r8d
0x18001a230  jz      loc_18001A317
0x18001a236  lea     rax, aCbrPpwszshorto; "CBR(*ppwszShortOsVersion == nullptr)"
0x18001a23d  mov     [rsp+48h+var_20], rax
0x18001a242  mov     [rsp+48h+var_28], 436h
0x18001a24a  jmp     short loc_18001A209
0x18001a24c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a253  mov     ecx, 30h ; '0'; unsigned __int64
0x18001a258  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a25d  mov     rsi, rax
0x18001a260  test    rax, rax
0x18001a263  jnz     short loc_18001A293
0x18001a265  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a26c  mov     ebx, 8007000Eh
0x18001a271  jz      loc_18001A317
0x18001a277  lea     rax, aCprPwszshortos; "CPR(pwszShortOsVersion)"
0x18001a27e  mov     r8d, ebx
0x18001a281  mov     [rsp+48h+var_20], rax
0x18001a286  mov     [rsp+48h+var_28], 439h
0x18001a28e  jmp     loc_18001A209
0x18001a293  xor     r8d, r8d
0x18001a296  lea     rcx, [rsp+48h+arg_0]
0x18001a29b  xor     edx, edx
0x18001a29d  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001a2a3  movzx   ecx, [rsp+48h+arg_2]
0x18001a2a8  lea     r8, aUUUU; "%u.%u.%u.%u"
0x18001a2af  movzx   edx, [rsp+48h+arg_4]
0x18001a2b4  movzx   eax, [rsp+48h+arg_0]
0x18001a2b9  movzx   r9d, [rsp+48h+arg_6]
0x18001a2bf  mov     [rsp+48h+var_18], eax
0x18001a2c3  mov     dword ptr [rsp+48h+var_20], ecx
0x18001a2c7  mov     rcx, rsi; unsigned __int16 *
0x18001a2ca  mov     [rsp+48h+var_28], edx
0x18001a2ce  mov     edx, 18h; unsigned __int64
0x18001a2d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a2d8  mov     ebx, eax
0x18001a2da  test    eax, eax
0x18001a2dc  jns     short loc_18001A314
0x18001a2de  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a2e5  jz      short loc_18001A30A
0x18001a2e7  lea     rax, aChrStringcchpr_5; "CHR(StringCchPrintfW( pwszShortOsVersio"...
0x18001a2ee  mov     r8d, ebx
0x18001a2f1  mov     [rsp+48h+var_20], rax
0x18001a2f6  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001a2fd  mov     [rsp+48h+var_28], 44Ch
0x18001a305  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a30a  mov     rcx, rsi; Block
0x18001a30d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a312  jmp     short loc_18001A317
0x18001a314  mov     [rdi], rsi
0x18001a317  mov     rsi, [rsp+48h+arg_10]
0x18001a31c  mov     eax, ebx
0x18001a31e  mov     rbx, [rsp+48h+arg_8]
0x18001a323  add     rsp, 40h
0x18001a327  pop     rdi
0x18001a328  retn
```
