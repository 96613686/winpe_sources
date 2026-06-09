# CDPComDeviceCache::RuntimeClassInitialize(void)

- ea: `0x180034a80`
- end: `0x180034b03`
- name: `?RuntimeClassInitialize@CDPComDeviceCache@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(CDPComDeviceCache *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180017d24`
- `0x18001ddf8`
- `0x18002d2b0`
- `0x180034a80`

## import_xrefs

- `cdp!CDPGetDeviceCacheInternal` at `0x180034ad5`
- `cdp!CDPGetDeviceCacheInternal` at `0x180034ad5`

## string_xrefs

- `0x180034aac`: `.\cdpcomdevicecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComDeviceCache::RuntimeClassInitialize(CDPComDeviceCache *this)
{
  int v2; // eax
  int v3; // edx
  int v4; // ecx
  int v6; // ebx
  _QWORD v7[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v8; // [rsp+58h] [rbp+18h] BYREF
  int v9; // [rsp+60h] [rbp+20h] BYREF

  v2 = cdp::RelayActivatableRuntimeClassBase<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPComMessagingHost,IFastRundown>>::RuntimeClassInitialize();
  if ( v2 < 0 )
  {
    v8 = v2;
    v9 = 14;
LABEL_3:
    Log<long &,char const (&)[28],int>(
      v4,
      v3,
      (unsigned int)&v8,
      (unsigned int)".\\cdpcomdevicecache.cpp",
      (__int64)&v9);
    return v8;
  }
  v7[0] = 0;
  v7[1] = (char *)this + 24;
  v6 = CDPGetDeviceCacheInternal(v7);
  cdp::detail::address_of<ICDPDeviceCache>::~address_of<ICDPDeviceCache>(v7);
  if ( v6 < 0 )
  {
    v8 = v6;
    v9 = 16;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180034a80  mov     [rsp-8+arg_0], rbx
0x180034a85  push    rbp
0x180034a86  mov     rbp, rsp
0x180034a89  sub     rsp, 40h
0x180034a8d  mov     rbx, rcx
0x180034a90  call    ?RuntimeClassInitialize@?$RelayActivatableRuntimeClassBase@V?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICDPComMessagingHost@@UIFastRundown@@@WRL@Microsoft@@@cdp@@UEAAJXZ; cdp::RelayActivatableRuntimeClassBase<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPComMessagingHost,IFastRundown>>::RuntimeClassInitialize(void)
0x180034a95  test    eax, eax
0x180034a97  jns     short loc_180034AC1
0x180034a99  mov     [rbp+arg_8], eax
0x180034a9c  mov     [rbp+arg_10], 0Eh
0x180034aa3  lea     rax, [rbp+arg_10]
0x180034aa7  mov     [rsp+40h+var_20], rax
0x180034aac  lea     r9, aCdpcomdeviceca; ".\\cdpcomdevicecache.cpp"
0x180034ab3  lea     r8, [rbp+arg_8]
0x180034ab7  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x180034abc  mov     eax, [rbp+arg_8]
0x180034abf  jmp     short loc_180034AF8
0x180034ac1  mov     [rbp+var_10], 0
0x180034ac9  lea     rax, [rbx+18h]
0x180034acd  mov     [rbp+var_8], rax
0x180034ad1  lea     rcx, [rbp+var_10]
0x180034ad5  call    cs:__imp_CDPGetDeviceCacheInternal
0x180034adb  mov     ebx, eax
0x180034add  lea     rcx, [rbp+var_10]
0x180034ae1  call    ??1?$address_of@VICDPDeviceCache@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDeviceCache>::~address_of<ICDPDeviceCache>(void)
0x180034ae6  test    ebx, ebx
0x180034ae8  jns     short loc_180034AF6
0x180034aea  mov     [rbp+arg_8], ebx
0x180034aed  mov     [rbp+arg_10], 10h
0x180034af4  jmp     short loc_180034AA3
0x180034af6  xor     eax, eax
0x180034af8  mov     rbx, [rsp+40h+arg_0]
0x180034afd  add     rsp, 40h
0x180034b01  pop     rbp
0x180034b02  retn
```
