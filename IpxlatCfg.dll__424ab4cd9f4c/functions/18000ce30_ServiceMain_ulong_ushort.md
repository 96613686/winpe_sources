# ServiceMain(ulong,ushort * *)

- ea: `0x18000ce30`
- end: `0x18000cec7`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `151`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001d40`
- `0x18000ba4c`
- `0x18000c224`
- `0x18000c314`
- `0x18000ce30`
- `0x18000cfd8`
- `0x18000d010`

## string_xrefs

- `0x18000ce72`: `IPxlatCfgSvc service start failed.`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  IPxlatSvcControl *Instance; // rbx
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // [rsp+30h] [rbp-48h] BYREF
  char v7[16]; // [rsp+38h] [rbp-40h] BYREF
  const char *v8; // [rsp+48h] [rbp-30h]
  __int64 v9; // [rsp+50h] [rbp-28h]
  unsigned int *v10; // [rsp+58h] [rbp-20h]
  __int64 v11; // [rsp+60h] [rbp-18h]

  Instance = IPxlatSvcControl::GetInstance();
  McGenEventRegister_EventRegister();
  v3 = IPxlatSvcControl::Start(Instance);
  if ( v3 && (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
  {
    v6 = v3;
    v9 = 35;
    v8 = "IPxlatCfgSvc service start failed.";
    v11 = 4;
    v10 = &v6;
    McGenEventWrite_EventWriteTransfer(v4, IPXLATCFG_ERROR_EVENT, v5, 3, v7);
  }
  McGenEventUnregister_EventUnregister();
}

```

## disassembly

```asm
0x18000ce30  push    rbx
0x18000ce32  sub     rsp, 70h
0x18000ce36  mov     rax, cs:__security_cookie
0x18000ce3d  xor     rax, rsp
0x18000ce40  mov     [rsp+78h+var_10], rax
0x18000ce45  call    ?GetInstance@IPxlatSvcControl@@SAAEAV1@XZ; IPxlatSvcControl::GetInstance(void)
0x18000ce4a  mov     rbx, rax
0x18000ce4d  call    McGenEventRegister_EventRegister
0x18000ce52  mov     rcx, rbx; this
0x18000ce55  call    ?Start@IPxlatSvcControl@@QEAAKXZ; IPxlatSvcControl::Start(void)
0x18000ce5a  test    eax, eax
0x18000ce5c  jz      short loc_18000CEAF
0x18000ce5e  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18000ce65  jz      short loc_18000CEAF
0x18000ce67  mov     [rsp+78h+var_48], eax
0x18000ce6b  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000ce72  lea     rax, aIpxlatcfgsvcSe; "IPxlatCfgSvc service start failed."
0x18000ce79  mov     [rsp+78h+var_28], 23h ; '#'
0x18000ce82  mov     [rsp+78h+var_30], rax
0x18000ce87  mov     r9d, 3
0x18000ce8d  lea     rax, [rsp+78h+var_48]
0x18000ce92  mov     [rsp+78h+var_18], 4
0x18000ce9b  mov     [rsp+78h+var_20], rax
0x18000cea0  lea     rax, [rsp+78h+var_40]
0x18000cea5  mov     [rsp+78h+var_58], rax
0x18000ceaa  call    McGenEventWrite_EventWriteTransfer
0x18000ceaf  call    McGenEventUnregister_EventUnregister
0x18000ceb4  mov     rcx, [rsp+78h+var_10]
0x18000ceb9  xor     rcx, rsp; StackCookie
0x18000cebc  call    __security_check_cookie
0x18000cec1  add     rsp, 70h
0x18000cec5  pop     rbx
0x18000cec6  retn
```
