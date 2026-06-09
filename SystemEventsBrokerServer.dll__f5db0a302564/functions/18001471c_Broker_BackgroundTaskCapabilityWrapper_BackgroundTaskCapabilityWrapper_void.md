# Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(void)

- ea: `0x18001471c`
- end: `0x1800147bf`
- name: `??0BackgroundTaskCapabilityWrapper@Broker@@QEAA@XZ`
- size: `163`
- prototype: `LPVOID *__fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014618`

## callees

- `0x1800030e0`
- `0x18001471c`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014742`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014742`

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
0x18001471c  mov     [rsp+arg_0], rbx
0x180014721  push    rdi
0x180014722  sub     rsp, 60h
0x180014726  xor     edx, edx; pUnkOuter
0x180014728  mov     [rsp+68h+ppv], rcx; ppv
0x18001472d  mov     rbx, rcx
0x180014730  lea     r9, _GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80; riid
0x180014737  lea     rcx, _GUID_53067330_01ce_4027_947f_ff8580e92463; rclsid
0x18001473e  lea     r8d, [rdx+1]; dwClsContext
0x180014742  call    cs:__imp_CoCreateInstance
0x180014748  mov     edi, eax
0x18001474a  test    eax, eax
0x18001474c  jns     short loc_1800147B1
0x18001474e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014755  test    dword ptr [rcx+1Ch], 400h
0x18001475c  jz      short loc_18001477C
0x18001475e  cmp     byte ptr [rcx+19h], 2
0x180014762  jb      short loc_18001477C
0x180014764  mov     rcx, [rcx+10h]
0x180014768  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x18001476f  mov     edx, 0Fh
0x180014774  mov     r9d, eax
0x180014777  call    WPP_SF_d
0x18001477c  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180014783  mov     [rsp+68h+var_20], 1
0x18001478b  mov     [rsp+68h+pExceptionObject], rax
0x180014790  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180014797  movzx   eax, di
0x18001479a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001479f  xorps   xmm0, xmm0
0x1800147a2  mov     [rsp+68h+var_18], eax
0x1800147a6  movups  [rsp+68h+var_30], xmm0
0x1800147ab  call    _CxxThrowException_0
0x1800147b1  mov     rax, rbx
0x1800147b4  mov     rbx, [rsp+68h+arg_0]
0x1800147b9  add     rsp, 60h
0x1800147bd  pop     rdi
0x1800147be  retn
```
