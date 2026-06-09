# Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(void)

- ea: `0x1800148c4`
- end: `0x180014967`
- name: `??0BackgroundTaskCapabilityWrapper@Broker@@QEAA@XZ`
- size: `163`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800110a0`
- `0x180016950`

## callees

- `0x180009e94`
- `0x1800148c4`
- `0x1800165da`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800148ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800148ea`

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
0x1800148c4  mov     [rsp+arg_0], rbx
0x1800148c9  push    rdi
0x1800148ca  sub     rsp, 60h
0x1800148ce  xor     edx, edx; pUnkOuter
0x1800148d0  mov     [rsp+68h+ppv], rcx; ppv
0x1800148d5  mov     rbx, rcx
0x1800148d8  lea     r9, _GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80; riid
0x1800148df  lea     rcx, _GUID_53067330_01ce_4027_947f_ff8580e92463; rclsid
0x1800148e6  lea     r8d, [rdx+1]; dwClsContext
0x1800148ea  call    cs:__imp_CoCreateInstance
0x1800148f0  mov     edi, eax
0x1800148f2  test    eax, eax
0x1800148f4  jns     short loc_180014959
0x1800148f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148fd  test    dword ptr [rcx+1Ch], 400h
0x180014904  jz      short loc_180014924
0x180014906  cmp     byte ptr [rcx+19h], 2
0x18001490a  jb      short loc_180014924
0x18001490c  mov     rcx, [rcx+10h]
0x180014910  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180014917  mov     edx, 0Fh
0x18001491c  mov     r9d, eax
0x18001491f  call    WPP_SF_d
0x180014924  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001492b  mov     [rsp+68h+var_20], 1
0x180014933  mov     [rsp+68h+pExceptionObject], rax
0x180014938  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001493f  movzx   eax, di
0x180014942  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180014947  xorps   xmm0, xmm0
0x18001494a  mov     [rsp+68h+var_18], eax
0x18001494e  movups  [rsp+68h+var_30], xmm0
0x180014953  call    _CxxThrowException_0
0x180014959  mov     rax, rbx
0x18001495c  mov     rbx, [rsp+68h+arg_0]
0x180014961  add     rsp, 60h
0x180014965  pop     rdi
0x180014966  retn
```
