# Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(void)

- ea: `0x18000c7b8`
- end: `0x18000c85b`
- name: `??0BackgroundTaskCapabilityWrapper@Broker@@QEAA@XZ`
- size: `163`
- prototype: `LPVOID *__fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c69c`

## callees

- `0x180003800`
- `0x18000c7b8`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c7de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c7de`

## pseudocode

```c
LPVOID *__fastcall Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(LPVOID *ppv)
{
  HRESULT Instance; // eax
  unsigned __int16 v3; // di
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v6; // [rsp+38h] [rbp-30h]
  int v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+50h] [rbp-18h]

  Instance = CoCreateInstance(
               &GUID_53067330_01ce_4027_947f_ff8580e92463,
               0,
               1u,
               &GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80,
               ppv);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids,
        (unsigned int)Instance);
    v7 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v8 = v3;
    v6 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x18000c7b8  mov     [rsp+arg_0], rbx
0x18000c7bd  push    rdi
0x18000c7be  sub     rsp, 60h
0x18000c7c2  xor     edx, edx; pUnkOuter
0x18000c7c4  mov     [rsp+68h+ppv], rcx; ppv
0x18000c7c9  mov     rbx, rcx
0x18000c7cc  lea     r9, _GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80; riid
0x18000c7d3  lea     rcx, _GUID_53067330_01ce_4027_947f_ff8580e92463; rclsid
0x18000c7da  lea     r8d, [rdx+1]; dwClsContext
0x18000c7de  call    cs:__imp_CoCreateInstance
0x18000c7e4  mov     edi, eax
0x18000c7e6  test    eax, eax
0x18000c7e8  js      short loc_18000C7F8
0x18000c7ea  mov     rax, rbx
0x18000c7ed  mov     rbx, [rsp+68h+arg_0]
0x18000c7f2  add     rsp, 60h
0x18000c7f6  pop     rdi
0x18000c7f7  retn
0x18000c7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7ff  test    dword ptr [rcx+1Ch], 400h
0x18000c806  jz      short loc_18000C826
0x18000c808  cmp     byte ptr [rcx+19h], 2
0x18000c80c  jb      short loc_18000C826
0x18000c80e  mov     rcx, [rcx+10h]
0x18000c812  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x18000c819  mov     edx, 0Fh
0x18000c81e  mov     r9d, edi
0x18000c821  call    WPP_SF_d
0x18000c826  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000c82d  mov     [rsp+68h+var_20], 1
0x18000c835  mov     [rsp+68h+pExceptionObject], rax
0x18000c83a  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000c841  movzx   eax, di
0x18000c844  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000c849  xorps   xmm0, xmm0
0x18000c84c  mov     [rsp+68h+var_18], eax
0x18000c850  movups  [rsp+68h+var_30], xmm0
0x18000c855  call    _CxxThrowException_0
```
