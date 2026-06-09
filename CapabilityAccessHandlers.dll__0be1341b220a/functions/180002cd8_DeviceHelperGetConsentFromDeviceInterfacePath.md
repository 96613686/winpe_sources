# DeviceHelperGetConsentFromDeviceInterfacePath

- ea: `0x180002cd8`
- end: `0x180003026`
- name: `DeviceHelperGetConsentFromDeviceInterfacePath`
- size: `846`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a2d0`
- `0x18000a310`

## callees

- `0x180002cd8`
- `0x180003dc0`
- `0x180003fbc`
- `0x180004c70`
- `0x1800056e0`
- `0x180012460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002e8f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002fa5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002e8f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180002fa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003004`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180002fdf`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180002ff2`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180002fdf`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180002ff2`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180002dd9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180002ed8`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180002dd9`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180002ed8`

## pseudocode

```c
__int64 __fastcall DeviceHelperGetConsentFromDeviceInterfacePath(
        unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  int ObjectProperties; // ebx
  LPVOID pv[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v7; // [rsp+68h] [rbp-98h]
  GUID rguid; // [rsp+78h] [rbp-88h]
  DEVPROPKEY v9; // [rsp+88h] [rbp-78h]
  int v10; // [rsp+9Ch] [rbp-64h]
  __int64 v11; // [rsp+A0h] [rbp-60h]
  DEVPROPKEY v12; // [rsp+B0h] [rbp-50h]
  int v13; // [rsp+C4h] [rbp-3Ch]
  __int64 v14; // [rsp+C8h] [rbp-38h]
  DEVPROPKEY v15; // [rsp+D0h] [rbp-30h]
  int v16; // [rsp+E4h] [rbp-1Ch]
  __int64 v17; // [rsp+E8h] [rbp-18h]
  OLECHAR sz[40]; // [rsp+F0h] [rbp-10h] BYREF

  v9 = DEVPKEY_Device_ContainerId;
  v12 = DEVPKEY_NAME;
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v15 = DEVPKEY_Device_ModelId;
  v7 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  pv[1] = 0;
  rguid = 0;
  memset_0(sz, 0, sizeof(sz));
  pv[0] = 0;
  ObjectProperties = _DeviceHelperValidateInterfacePath(a1, (unsigned __int16 **)pv);
  if ( ObjectProperties >= 0 )
  {
    ObjectProperties = DevGetObjectProperties(1, pv[0], 0);
    if ( ObjectProperties >= 0 )
      ObjectProperties = -2147023728;
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x180002cd8  push    rbp
0x180002cda  push    rbx
0x180002cdb  push    rsi
0x180002cdc  push    rdi
0x180002cdd  push    r15
0x180002cdf  lea     rbp, [rsp-50h]
0x180002ce4  sub     rsp, 150h
0x180002ceb  mov     rax, cs:__security_cookie
0x180002cf2  xor     rax, rsp
0x180002cf5  mov     [rbp+70h+var_30], rax
0x180002cf9  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180002d00  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180002d06  xor     r15d, r15d
0x180002d09  mov     [rbp+70h+var_D8], eax
0x180002d0c  mov     rdi, r8
0x180002d0f  mov     eax, cs:DEVPKEY_NAME.pid
0x180002d15  mov     rsi, rdx
0x180002d18  movups  [rbp+70h+var_E8], xmm0
0x180002d1c  mov     rbx, rcx
0x180002d1f  mov     [rbp+70h+var_B0], eax
0x180002d22  movups  xmm0, xmmword ptr cs:DEVPKEY_NAME.fmtid.Data1
0x180002d29  mov     eax, cs:DEVPKEY_Device_ModelId.pid
0x180002d2f  lea     r8d, [r15+50h]; Size
0x180002d33  xorps   xmm1, xmm1
0x180002d36  mov     [rbp+70h+var_D4], r15d
0x180002d3a  movaps  [rbp+70h+var_C0], xmm0
0x180002d3e  lea     rcx, [rbp+70h+sz]; void *
0x180002d42  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ModelId.fmtid.Data1
0x180002d49  xor     edx, edx; Val
0x180002d4b  mov     [rbp+70h+var_D0], r15
0x180002d4f  mov     [rbp+70h+var_AC], r15d
0x180002d53  movaps  [rbp+70h+var_A0], xmm0
0x180002d57  xorps   xmm0, xmm0
0x180002d5a  movups  [rsp+170h+var_108], xmm0
0x180002d5f  mov     [rbp+70h+var_A8], r15
0x180002d63  mov     [rbp+70h+var_90], eax
0x180002d66  mov     [rbp+70h+var_8C], r15d
0x180002d6a  mov     [rbp+70h+var_88], r15
0x180002d6e  mov     [rsp+170h+var_130], r15d
0x180002d73  mov     [rsp+170h+var_128], r15
0x180002d78  mov     [rsp+170h+var_110], r15
0x180002d7d  mov     [rsp+170h+var_12C], r15d
0x180002d82  mov     [rsp+170h+var_120], r15
0x180002d87  movups  xmmword ptr [rsp+170h+rguid.Data1], xmm1
0x180002d8c  call    memset_0
0x180002d91  lea     rdx, [rsp+170h+pv]; unsigned __int16 **
0x180002d96  mov     [rsp+170h+pv], r15
0x180002d9b  mov     rcx, rbx; unsigned __int16 *
0x180002d9e  call    ?_DeviceHelperValidateInterfacePath@@YAJPEBGPEAPEAG@Z; _DeviceHelperValidateInterfacePath(ushort const *,ushort * *)
0x180002da3  mov     ebx, eax
0x180002da5  test    eax, eax
0x180002da7  js      loc_180002FD2
0x180002dad  mov     rdx, [rsp+170h+pv]
0x180002db2  lea     rax, [rsp+170h+var_128]
0x180002db7  mov     [rsp+170h+var_140], rax
0x180002dbc  lea     r9d, [r15+1]
0x180002dc0  lea     rax, [rsp+170h+var_130]
0x180002dc5  xor     r8d, r8d
0x180002dc8  mov     [rsp+170h+var_148], rax
0x180002dcd  mov     ecx, r9d
0x180002dd0  lea     rax, [rbp+70h+var_E8]
0x180002dd4  mov     [rsp+170h+var_150], rax
0x180002dd9  call    cs:__imp_DevGetObjectProperties
0x180002ddf  mov     ebx, eax
0x180002de1  test    eax, eax
0x180002de3  js      loc_180002FD2
0x180002de9  mov     ecx, [rsp+170h+var_130]
0x180002ded  test    ecx, ecx
0x180002def  jz      loc_180002FCD
0x180002df5  cmp     [rsp+170h+var_128], r15
0x180002dfa  jz      loc_180002FCD
0x180002e00  mov     r9d, r15d
0x180002e03  test    ecx, ecx
0x180002e05  jz      loc_180002FC6
0x180002e0b  mov     r8d, r15d
0x180002e0e  cmp     r8d, 1
0x180002e12  jnb     short loc_180002E48
0x180002e14  mov     eax, r9d
0x180002e17  lea     rdx, [rbp+70h+var_E8]
0x180002e1b  mov     r10d, r8d
0x180002e1e  lea     rcx, [rax+rax*2]
0x180002e22  mov     eax, r8d
0x180002e25  shl     rax, 5
0x180002e29  shl     rcx, 4
0x180002e2d  add     rdx, rax
0x180002e30  add     rcx, [rsp+170h+var_128]
0x180002e35  call    ??8@YA_NAEBU_DEVPROPKEY@@0@Z; operator==(_DEVPROPKEY const &,_DEVPROPKEY const &)
0x180002e3a  test    al, al
0x180002e3c  jnz     short loc_180002E43
0x180002e3e  inc     r8d
0x180002e41  jmp     short loc_180002E0E
0x180002e43  mov     [rsp+r10*8+170h+var_110], rcx
0x180002e48  inc     r9d
0x180002e4b  cmp     r9d, [rsp+170h+var_130]
0x180002e50  jb      short loc_180002E0B
0x180002e52  mov     rax, [rsp+170h+var_110]
0x180002e57  test    rax, rax
0x180002e5a  jz      loc_180002FC6
0x180002e60  cmp     dword ptr [rax+20h], 0Dh
0x180002e64  jnz     loc_180002FC6
0x180002e6a  mov     rcx, [rax+28h]
0x180002e6e  test    rcx, rcx
0x180002e71  jz      loc_180002FC6
0x180002e77  movups  xmm0, xmmword ptr [rcx]
0x180002e7a  mov     r8d, 28h ; '('; cchMax
0x180002e80  lea     rdx, [rbp+70h+sz]; lpsz
0x180002e84  lea     rcx, [rsp+170h+rguid]; rguid
0x180002e89  movdqu  xmmword ptr [rsp+170h+rguid.Data1], xmm0
0x180002e8f  call    cs:__imp_StringFromGUID2
0x180002e95  mov     ecx, eax
0x180002e97  neg     ecx
0x180002e99  sbb     ebx, ebx
0x180002e9b  not     ebx
0x180002e9d  and     ebx, 80004005h
0x180002ea3  test    eax, eax
0x180002ea5  jz      loc_180002FD2
0x180002eab  lea     rax, [rsp+170h+var_120]
0x180002eb0  mov     r9d, 2
0x180002eb6  mov     [rsp+170h+var_140], rax
0x180002ebb  lea     rdx, [rbp+70h+sz]
0x180002ebf  lea     rax, [rsp+170h+var_12C]
0x180002ec4  xor     r8d, r8d
0x180002ec7  mov     [rsp+170h+var_148], rax
0x180002ecc  mov     ecx, r9d
0x180002ecf  lea     rax, [rbp+70h+var_C0]
0x180002ed3  mov     [rsp+170h+var_150], rax
0x180002ed8  call    cs:__imp_DevGetObjectProperties
0x180002ede  mov     ebx, eax
0x180002ee0  test    eax, eax
0x180002ee2  js      loc_180002FD2
0x180002ee8  mov     ecx, [rsp+170h+var_12C]
0x180002eec  test    ecx, ecx
0x180002eee  jz      loc_180002FCD
0x180002ef4  cmp     [rsp+170h+var_120], r15
0x180002ef9  jz      loc_180002FCD
0x180002eff  mov     r9d, r15d
0x180002f02  test    ecx, ecx
0x180002f04  jz      short loc_180002F4D
0x180002f06  mov     r8d, r15d
0x180002f09  cmp     r8d, 2
0x180002f0d  jnb     short loc_180002F43
0x180002f0f  mov     eax, r9d
0x180002f12  lea     rdx, [rbp+70h+var_C0]
0x180002f16  mov     r10d, r8d
0x180002f19  lea     rcx, [rax+rax*2]
0x180002f1d  mov     eax, r8d
0x180002f20  shl     rax, 5
0x180002f24  shl     rcx, 4
0x180002f28  add     rdx, rax
0x180002f2b  add     rcx, [rsp+170h+var_120]
0x180002f30  call    ??8@YA_NAEBU_DEVPROPKEY@@0@Z; operator==(_DEVPROPKEY const &,_DEVPROPKEY const &)
0x180002f35  test    al, al
0x180002f37  jnz     short loc_180002F3E
0x180002f39  inc     r8d
0x180002f3c  jmp     short loc_180002F09
0x180002f3e  mov     qword ptr [rsp+r10*8+170h+var_108], rcx
0x180002f43  inc     r9d
0x180002f46  cmp     r9d, [rsp+170h+var_12C]
0x180002f4b  jb      short loc_180002F06
0x180002f4d  test    rdi, rdi
0x180002f50  jz      short loc_180002F7D
0x180002f52  mov     rax, qword ptr [rsp+170h+var_108]
0x180002f57  test    rax, rax
0x180002f5a  jz      short loc_180002F6B
0x180002f5c  cmp     dword ptr [rax+20h], 12h
0x180002f60  jnz     short loc_180002F6B
0x180002f62  mov     rcx, [rax+28h]
0x180002f66  test    rcx, rcx
0x180002f69  jnz     short loc_180002F6F
0x180002f6b  lea     rcx, [rbp+70h+sz]; unsigned __int16 *
0x180002f6f  mov     rdx, rdi; unsigned __int16 **
0x180002f72  call    ?_DeviceHelperMakeStringCopy@@YAJPEBGPEAPEAG@Z; _DeviceHelperMakeStringCopy(ushort const *,ushort * *)
0x180002f77  mov     ebx, eax
0x180002f79  test    eax, eax
0x180002f7b  js      short loc_180002FD2
0x180002f7d  test    rsi, rsi
0x180002f80  jz      short loc_180002FD2
0x180002f82  mov     rax, qword ptr [rsp+170h+var_108+8]
0x180002f87  test    rax, rax
0x180002f8a  jz      short loc_180002FAF
0x180002f8c  cmp     dword ptr [rax+20h], 0Dh
0x180002f90  jnz     short loc_180002FAF
0x180002f92  mov     rcx, [rax+28h]; rguid
0x180002f96  test    rcx, rcx
0x180002f99  jz      short loc_180002FAF
0x180002f9b  mov     r8d, 28h ; '('; cchMax
0x180002fa1  lea     rdx, [rbp+70h+sz]; lpsz
0x180002fa5  call    cs:__imp_StringFromGUID2
0x180002fab  test    eax, eax
0x180002fad  jz      short loc_180002FBF
0x180002faf  mov     rdx, rsi; unsigned __int16 **
0x180002fb2  lea     rcx, [rbp+70h+sz]; unsigned __int16 *
0x180002fb6  call    ?_DeviceHelperMakeStringCopy@@YAJPEBGPEAPEAG@Z; _DeviceHelperMakeStringCopy(ushort const *,ushort * *)
0x180002fbb  mov     ebx, eax
0x180002fbd  jmp     short loc_180002FD2
0x180002fbf  mov     ebx, 80004005h
0x180002fc4  jmp     short loc_180002FD2
0x180002fc6  mov     ebx, 80070057h
0x180002fcb  jmp     short loc_180002FD2
0x180002fcd  mov     ebx, 80070490h
0x180002fd2  mov     ecx, [rsp+170h+var_130]
0x180002fd6  test    ecx, ecx
0x180002fd8  jz      short loc_180002FE5
0x180002fda  mov     rdx, [rsp+170h+var_128]
0x180002fdf  call    cs:__imp_DevFreeObjectProperties
0x180002fe5  mov     ecx, [rsp+170h+var_12C]
0x180002fe9  test    ecx, ecx
0x180002feb  jz      short loc_180002FF8
0x180002fed  mov     rdx, [rsp+170h+var_120]
0x180002ff2  call    cs:__imp_DevFreeObjectProperties
0x180002ff8  cmp     [rsp+170h+pv], r15
0x180002ffd  jz      short loc_18000300A
0x180002fff  mov     rcx, [rsp+170h+pv]; pv
0x180003004  call    cs:__imp_CoTaskMemFree
0x18000300a  mov     eax, ebx
0x18000300c  mov     rcx, [rbp+70h+var_30]
0x180003010  xor     rcx, rsp; StackCookie
0x180003013  call    __security_check_cookie
0x180003018  add     rsp, 150h
0x18000301f  pop     r15
0x180003021  pop     rdi
0x180003022  pop     rsi
0x180003023  pop     rbx
0x180003024  pop     rbp
0x180003025  retn
```
