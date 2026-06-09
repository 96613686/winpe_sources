# CameraQueryDeviceCompatFlags(ushort const *,CAMERA_COMPAT_CLASS)

- ea: `0x18000f5c8`
- end: `0x18000f9c8`
- name: `?CameraQueryDeviceCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEBGW4CAMERA_COMPAT_CLASS@@@Z`
- size: `1024`
- prototype: `unsigned __int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800163d0`
- `0x180017b9c`

## callees

- `0x18000f518`
- `0x18000f5c8`
- `0x18000f9d0`
- `0x1800166e0`
- `0x1800169ac`
- `0x1800310f0`
- `0x180044f30`
- `0x1800458dc`
- `0x180045900`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f6b6`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f6b6`
- `ntdll!NtQuerySystemInformation` at `0x18000f790`
- `ntdll!NtQuerySystemInformation` at `0x18000f790`
- `ntdll!RtlInitUnicodeString` at `0x18000f75c`
- `ntdll!RtlInitUnicodeString` at `0x18000f76a`
- `ntdll!RtlInitUnicodeString` at `0x18000f75c`
- `ntdll!RtlInitUnicodeString` at `0x18000f76a`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000f7ce`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000f7e6`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000f7ce`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000f7e6`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000f883`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000f904`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000f883`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000f904`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18000f8ac`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18000f937`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18000f962`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18000f8ac`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18000f937`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18000f962`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000f6da`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000f6da`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000f70b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000f70b`

## pseudocode

```c
unsigned __int64 __fastcall CameraQueryDeviceCompatFlags(const unsigned __int16 *a1, int a2)
{
  const WCHAR *v4; // rsi
  unsigned __int64 DeviceCompatFlagsInternal; // rbx
  unsigned __int64 v7; // r14
  int v8; // eax
  int v9; // r15d
  __int64 v10; // rax
  wchar_t *i; // rdi
  __int64 Property; // rax
  __int64 v13; // rdi
  unsigned int v14; // r14d
  __int64 v15; // rax
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v23; // [rsp+78h] [rbp-88h] BYREF
  __int128 v24; // [rsp+88h] [rbp-78h]
  DEVPROPKEY v25; // [rsp+A0h] [rbp-60h] BYREF
  int v26; // [rsp+B4h] [rbp-4Ch]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  DEVPROPKEY v28; // [rsp+C0h] [rbp-40h]
  int v29; // [rsp+D4h] [rbp-2Ch]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v31[112]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SourceString[136]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v33[528]; // [rsp+2D0h] [rbp+1D0h] BYREF

  memset_0(v31, 0, 0xD2u);
  memset_0(SourceString, 0, 0x102u);
  if ( a2 )
  {
    if ( a2 == 1 )
      v4 = L"CamDevice";
    else
      v4 = L"Unknown";
  }
  else
  {
    v4 = L"CamAcpiRotation";
  }
  v16 = 0;
  v19 = 0;
  v17 = 0;
  v21 = 0;
  memset_0(v33, 0, 0x208u);
  DeviceCompatFlagsInternal = 0;
  if ( a1 )
  {
    if ( (int)GetFingerprintStringPrefixFromSensorGroup(a1, v31) >= 0
      || (v18 = 0, (int)CreateFingerprintStringPrefix(a1, v31, &v18) >= 0) )
    {
      v25 = DEVPKEY_Device_HardwareIds;
      v28 = DEVPKEY_Device_InstanceId;
      v26 = 0;
      v27 = 0;
      v29 = 0;
      v30 = 0;
      if ( (int)DevGetObjectProperties(1, a1, 0, 2, &v25, &v16, &v19) >= 0 )
      {
        Property = DevFindProperty(&DEVPKEY_Device_InstanceId, 0, 0, v16, v19);
        if ( !Property
          || *(_DWORD *)(Property + 32) != 18
          || (o_wcsncpy_s_0(v33, 260, *(_QWORD *)(Property + 40), -1),
              (int)DevGetObjectProperties(3, v33, 0, 2, &v25, &v17, &v21) >= 0) )
        {
          v13 = v21;
          v14 = v17;
          v15 = DevFindProperty(&DEVPKEY_Device_HardwareIds, 0, 0, v16, v19);
          if ( v15 && *(_DWORD *)(v15 + 32) == 8210
            || (v15 = DevFindProperty(&DEVPKEY_Device_HardwareIds, 0, 0, v14, v13)) != 0
            && *(_DWORD *)(v15 + 32) == 8210 )
          {
            for ( i = *(wchar_t **)(v15 + 40); *i; i += v10 + 1 )
            {
              v18 = 0;
              v7 = 0;
              v8 = wcsnlen(i, 0xC8u);
              phAlgorithm = 0;
              v9 = v8;
              if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0) >= 0 )
              {
                CameraGenerateDWORD64HashWithHandle((PUCHAR)i, 2 * v9, phAlgorithm, &v18);
                v7 = v18;
              }
              if ( phAlgorithm )
                BCryptCloseAlgorithmProvider(phAlgorithm, 0);
              if ( (int)StringCchPrintfW(SourceString, 0x81u, L"Camera:%ws%016I64X;", v31, v7) < 0 )
                break;
              v18 = 0;
              DestinationString = 0;
              v23 = 0;
              v24 = 0;
              RtlInitUnicodeString(&DestinationString, SourceString);
              RtlInitUnicodeString(&v23, v4);
              DWORD1(v24) = 8;
              *((_QWORD *)&v24 + 1) = &v18;
              NtQuerySystemInformation((SYSTEM_INFORMATION_CLASS)136, &DestinationString, 0x30u, 0);
              DeviceCompatFlagsInternal = v18;
              if ( v18 )
                break;
              v10 = -1;
              do
                ++v10;
              while ( i[v10] );
            }
          }
          else if ( (int)StringCchPrintfW(SourceString, 0x81u, L"Camera:%ws%016I64X;", v31, 0) >= 0 )
          {
            DeviceCompatFlagsInternal = CameraQueryDeviceCompatFlagsInternal(v4, SourceString);
          }
        }
      }
    }
    if ( v19 )
      DevFreeObjectProperties(v16);
    if ( v21 )
      DevFreeObjectProperties(v17);
  }
  return DeviceCompatFlagsInternal;
}

```

## disassembly

```asm
0x18000f5c8  mov     [rsp-8+arg_8], rbx
0x18000f5cd  mov     [rsp-8+arg_10], rsi
0x18000f5d2  push    rbp
0x18000f5d3  push    rdi
0x18000f5d4  push    r12
0x18000f5d6  push    r14
0x18000f5d8  push    r15
0x18000f5da  lea     rbp, [rsp-3F0h]
0x18000f5e2  sub     rsp, 4F0h
0x18000f5e9  mov     rax, cs:__security_cookie
0x18000f5f0  xor     rax, rsp
0x18000f5f3  mov     [rbp+410h+var_30], rax
0x18000f5fa  mov     ebx, edx
0x18000f5fc  mov     rdi, rcx
0x18000f5ff  xor     edx, edx; Val
0x18000f601  lea     rcx, [rbp+410h+var_430]; void *
0x18000f605  mov     r8d, 0D2h; Size
0x18000f60b  call    memset_0
0x18000f610  xor     edx, edx; Val
0x18000f612  lea     rcx, [rbp+410h+SourceString]; void *
0x18000f619  mov     r8d, 102h; Size
0x18000f61f  call    memset_0
0x18000f624  xor     r12d, r12d
0x18000f627  test    ebx, ebx
0x18000f629  jz      short loc_18000F69D
0x18000f62b  cmp     ebx, 1
0x18000f62e  jnz     loc_18000F9BC
0x18000f634  lea     rsi, aCamdevice; "CamDevice"
0x18000f63b  xor     edx, edx; Val
0x18000f63d  mov     [rsp+510h+var_4D0], r12d
0x18000f642  mov     r8d, 208h; Size
0x18000f648  mov     [rsp+510h+var_4C0], r12
0x18000f64d  lea     rcx, [rbp+410h+var_240]; void *
0x18000f654  mov     [rsp+510h+var_4CC], r12d
0x18000f659  mov     [rsp+510h+var_4B0], r12
0x18000f65e  call    memset_0
0x18000f663  mov     rbx, r12
0x18000f666  test    rdi, rdi
0x18000f669  jnz     loc_18000F7F1
0x18000f66f  mov     rax, rbx
0x18000f672  mov     rcx, [rbp+410h+var_30]
0x18000f679  xor     rcx, rsp; StackCookie
0x18000f67c  call    __security_check_cookie
0x18000f681  lea     r11, [rsp+510h+var_20]
0x18000f689  mov     rbx, [r11+38h]
0x18000f68d  mov     rsi, [r11+40h]
0x18000f691  mov     rsp, r11
0x18000f694  pop     r15
0x18000f696  pop     r14
0x18000f698  pop     r12
0x18000f69a  pop     rdi
0x18000f69b  pop     rbp
0x18000f69c  retn
0x18000f69d  lea     rsi, aCamacpirotatio; "CamAcpiRotation"
0x18000f6a4  jmp     short loc_18000F63B
0x18000f6a6  mov     edx, 0C8h; MaxCount
0x18000f6ab  mov     [rsp+510h+var_4C8], r12
0x18000f6b0  mov     rcx, rdi; Source
0x18000f6b3  mov     r14, r12
0x18000f6b6  call    cs:__imp_wcsnlen
0x18000f6bc  xor     r9d, r9d; dwFlags
0x18000f6bf  mov     [rsp+510h+phAlgorithm], r12
0x18000f6c4  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000f6cb  mov     r15, rax
0x18000f6ce  lea     rdx, pszAlgId; "SHA256"
0x18000f6d5  lea     rcx, [rsp+510h+phAlgorithm]; phAlgorithm
0x18000f6da  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000f6e0  test    eax, eax
0x18000f6e2  js      short loc_18000F6FF
0x18000f6e4  mov     r8, [rsp+510h+phAlgorithm]; hObject
0x18000f6e9  lea     edx, [r15+r15]; cbInput
0x18000f6ed  lea     r9, [rsp+510h+var_4C8]; unsigned __int64 *
0x18000f6f2  mov     rcx, rdi; pbInput
0x18000f6f5  call    ?CameraGenerateDWORD64HashWithHandle@@YAJPEAEKPEAXPEA_K@Z; CameraGenerateDWORD64HashWithHandle(uchar *,ulong,void *,unsigned __int64 *)
0x18000f6fa  mov     r14, [rsp+510h+var_4C8]
0x18000f6ff  mov     rcx, [rsp+510h+phAlgorithm]; hAlgorithm
0x18000f704  test    rcx, rcx
0x18000f707  jz      short loc_18000F711
0x18000f709  xor     edx, edx; dwFlags
0x18000f70b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000f711  lea     r9, [rbp+410h+var_430]
0x18000f715  mov     [rsp+510h+var_4F0], r14
0x18000f71a  lea     r8, aCameraWs016i64; "Camera:%ws%016I64X;"
0x18000f721  mov     edx, 81h; unsigned __int64
0x18000f726  lea     rcx, [rbp+410h+SourceString]; unsigned __int16 *
0x18000f72d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f732  test    eax, eax
0x18000f734  js      loc_18000F7C0
0x18000f73a  xorps   xmm0, xmm0
0x18000f73d  mov     [rsp+510h+var_4C8], r12
0x18000f742  lea     rdx, [rbp+410h+SourceString]; SourceString
0x18000f749  lea     rcx, [rsp+510h+DestinationString]; DestinationString
0x18000f74e  movups  xmmword ptr [rsp+510h+DestinationString.Length], xmm0
0x18000f753  movups  xmmword ptr [rsp+510h+var_498.Length], xmm0
0x18000f758  movups  [rbp+410h+var_488], xmm0
0x18000f75c  call    cs:__imp_RtlInitUnicodeString
0x18000f762  mov     rdx, rsi; SourceString
0x18000f765  lea     rcx, [rsp+510h+var_498]; DestinationString
0x18000f76a  call    cs:__imp_RtlInitUnicodeString
0x18000f770  xor     r9d, r9d; ReturnLength
0x18000f773  mov     dword ptr [rbp+410h+var_488+4], 8
0x18000f77a  lea     rax, [rsp+510h+var_4C8]
0x18000f77f  lea     rdx, [rsp+510h+DestinationString]; SystemInformation
0x18000f784  mov     qword ptr [rbp+410h+var_488+8], rax
0x18000f788  lea     r8d, [r9+30h]; SystemInformationLength
0x18000f78c  lea     ecx, [r8+58h]; SystemInformationClass
0x18000f790  call    cs:__imp_NtQuerySystemInformation
0x18000f796  mov     rbx, [rsp+510h+var_4C8]
0x18000f79b  test    rbx, rbx
0x18000f79e  jnz     short loc_18000F7C0
0x18000f7a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f7a4  inc     rax
0x18000f7a7  cmp     [rdi+rax*2], r12w
0x18000f7ac  jnz     short loc_18000F7A4
0x18000f7ae  lea     rdi, [rdi+rax*2]
0x18000f7b2  add     rdi, 2
0x18000f7b6  cmp     [rdi], r12w
0x18000f7ba  jnz     loc_18000F6A6
0x18000f7c0  mov     rdx, [rsp+510h+var_4C0]
0x18000f7c5  test    rdx, rdx
0x18000f7c8  jz      short loc_18000F7D4
0x18000f7ca  mov     ecx, [rsp+510h+var_4D0]
0x18000f7ce  call    cs:__imp_DevFreeObjectProperties
0x18000f7d4  mov     rdx, [rsp+510h+var_4B0]
0x18000f7d9  test    rdx, rdx
0x18000f7dc  jz      loc_18000F66F
0x18000f7e2  mov     ecx, [rsp+510h+var_4CC]
0x18000f7e6  call    cs:__imp_DevFreeObjectProperties
0x18000f7ec  jmp     loc_18000F66F
0x18000f7f1  lea     rdx, [rbp+410h+var_430]; unsigned __int16 *
0x18000f7f5  mov     rcx, rdi; unsigned __int16 *
0x18000f7f8  call    ?GetFingerprintStringPrefixFromSensorGroup@@YAJPEBGPEAGK@Z; GetFingerprintStringPrefixFromSensorGroup(ushort const *,ushort *,ulong)
0x18000f7fd  test    eax, eax
0x18000f7ff  jns     short loc_18000F81B
0x18000f801  lea     r8, [rsp+510h+var_4C8]; unsigned __int64 *
0x18000f806  mov     [rsp+510h+var_4C8], r12
0x18000f80b  lea     rdx, [rbp+410h+var_430]; unsigned __int16 *
0x18000f80f  mov     rcx, rdi; unsigned __int16 *
0x18000f812  call    ?CreateFingerprintStringPrefix@@YAJPEBGPEAGPEA_K@Z; CreateFingerprintStringPrefix(ushort const *,ushort *,unsigned __int64 *)
0x18000f817  test    eax, eax
0x18000f819  js      short loc_18000F7C0
0x18000f81b  mov     eax, cs:DEVPKEY_Device_HardwareIds.pid
0x18000f821  mov     r14d, 2
0x18000f827  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_HardwareIds.fmtid.Data1
0x18000f82e  mov     [rbp+410h+var_460], eax
0x18000f831  mov     r9d, r14d
0x18000f834  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x18000f83a  xor     r8d, r8d
0x18000f83d  mov     [rbp+410h+var_440], eax
0x18000f840  lea     ecx, [r14-1]
0x18000f844  lea     rax, [rsp+510h+var_4C0]
0x18000f849  movaps  [rbp+410h+var_470], xmm0
0x18000f84d  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x18000f854  mov     [rsp+510h+var_4E0], rax
0x18000f859  mov     rdx, rdi
0x18000f85c  lea     rax, [rsp+510h+var_4D0]
0x18000f861  mov     [rbp+410h+var_45C], r12d
0x18000f865  mov     [rsp+510h+var_4E8], rax
0x18000f86a  lea     rax, [rbp+410h+var_470]
0x18000f86e  mov     [rsp+510h+var_4F0], rax
0x18000f873  mov     [rbp+410h+var_458], r12
0x18000f877  movaps  [rbp+410h+var_450], xmm0
0x18000f87b  mov     [rbp+410h+var_43C], r12d
0x18000f87f  mov     [rbp+410h+var_438], r12
0x18000f883  call    cs:__imp_DevGetObjectProperties
0x18000f889  test    eax, eax
0x18000f88b  js      loc_18000F7C0
0x18000f891  mov     rax, [rsp+510h+var_4C0]
0x18000f896  lea     rcx, DEVPKEY_Device_InstanceId
0x18000f89d  mov     r9d, [rsp+510h+var_4D0]
0x18000f8a2  xor     r8d, r8d
0x18000f8a5  xor     edx, edx
0x18000f8a7  mov     [rsp+510h+var_4F0], rax
0x18000f8ac  call    cs:__imp_DevFindProperty
0x18000f8b2  test    rax, rax
0x18000f8b5  jz      short loc_18000F912
0x18000f8b7  cmp     dword ptr [rax+20h], 12h
0x18000f8bb  jnz     short loc_18000F912
0x18000f8bd  mov     r8, [rax+28h]
0x18000f8c1  lea     rcx, [rbp+410h+var_240]
0x18000f8c8  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f8cc  mov     edx, 104h
0x18000f8d1  call    _o_wcsncpy_s_0
0x18000f8d6  lea     rax, [rsp+510h+var_4B0]
0x18000f8db  mov     r9d, r14d
0x18000f8de  mov     [rsp+510h+var_4E0], rax
0x18000f8e3  lea     rdx, [rbp+410h+var_240]
0x18000f8ea  lea     rax, [rsp+510h+var_4CC]
0x18000f8ef  xor     r8d, r8d
0x18000f8f2  mov     [rsp+510h+var_4E8], rax
0x18000f8f7  lea     ecx, [r14+1]
0x18000f8fb  lea     rax, [rbp+410h+var_470]
0x18000f8ff  mov     [rsp+510h+var_4F0], rax
0x18000f904  call    cs:__imp_DevGetObjectProperties
0x18000f90a  test    eax, eax
0x18000f90c  js      loc_18000F7C0
0x18000f912  mov     rax, [rsp+510h+var_4C0]
0x18000f917  lea     rcx, DEVPKEY_Device_HardwareIds
0x18000f91e  mov     r9d, [rsp+510h+var_4D0]
0x18000f923  xor     r8d, r8d
0x18000f926  mov     rdi, [rsp+510h+var_4B0]
0x18000f92b  xor     edx, edx
0x18000f92d  mov     r14d, [rsp+510h+var_4CC]
0x18000f932  mov     [rsp+510h+var_4F0], rax
0x18000f937  call    cs:__imp_DevFindProperty
0x18000f93d  mov     r15d, 2012h
0x18000f943  test    rax, rax
0x18000f946  jz      short loc_18000F94E
0x18000f948  cmp     [rax+20h], r15d
0x18000f94c  jz      short loc_18000F973
0x18000f94e  mov     r9d, r14d
0x18000f951  mov     [rsp+510h+var_4F0], rdi
0x18000f956  xor     r8d, r8d
0x18000f959  lea     rcx, DEVPKEY_Device_HardwareIds
0x18000f960  xor     edx, edx
0x18000f962  call    cs:__imp_DevFindProperty
0x18000f968  test    rax, rax
0x18000f96b  jz      short loc_18000F97C
0x18000f96d  cmp     [rax+20h], r15d
0x18000f971  jnz     short loc_18000F97C
0x18000f973  mov     rdi, [rax+28h]
0x18000f977  jmp     loc_18000F7B6
0x18000f97c  lea     r9, [rbp+410h+var_430]
0x18000f980  mov     [rsp+510h+var_4F0], r12
0x18000f985  lea     r8, aCameraWs016i64; "Camera:%ws%016I64X;"
0x18000f98c  mov     edx, 81h; unsigned __int64
0x18000f991  lea     rcx, [rbp+410h+SourceString]; unsigned __int16 *
0x18000f998  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f99d  test    eax, eax
0x18000f99f  js      loc_18000F7C0
0x18000f9a5  lea     rdx, [rbp+410h+SourceString]
0x18000f9ac  mov     rcx, rsi
0x18000f9af  call    ?CameraQueryDeviceCompatFlagsInternal@@YA?ATCAMERA_DEVICE_FLAGS@@PEBGPEAG@Z; CameraQueryDeviceCompatFlagsInternal(ushort const *,ushort *)
0x18000f9b4  mov     rbx, rax
0x18000f9b7  jmp     loc_18000F7C0
0x18000f9bc  lea     rsi, aUnknown_0; "Unknown"
0x18000f9c3  jmp     loc_18000F63B
```
