# BypassIoctlGetDescriptor

- ea: `0x140007dc0`
- end: `0x140008166`
- name: `BypassIoctlGetDescriptor`
- size: `934`
- prototype: `NTSTATUS __fastcall(struct WDFDEVICE__ *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x1400044dc`
- `0x140006654`
- `0x140007dc0`
- `0x14000a464`
- `0x14001adc0`
- `0x14001ae00`
- `0x14002c1a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400080c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400080f7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400080c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400080f7`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140007f5d`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140007f5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008134`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008134`
- `btampm!BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg` at `0x14000806d`
- `btampm!BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg` at `0x14000806d`

## string_xrefs

- `0x14000804e`: `@System32\drivers\bthhfenum.sys`

## pseudocode

```c
NTSTATUS __fastcall BypassIoctlGetDescriptor(struct WDFDEVICE__ *a1, __int64 a2, _QWORD *a3)
{
  int v6; // edx
  _DWORD *v7; // rsi
  int v8; // r8d
  NTSTATUS result; // eax
  int v10; // edi
  struct _DEVICE_OBJECT *v11; // rax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  bool v18; // zf
  unsigned __int16 v19[2]; // [rsp+50h] [rbp-39h] BYREF
  ULONG Type; // [rsp+54h] [rbp-35h] BYREF
  ULONG RequiredSize; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int64 v22; // [rsp+60h] [rbp-29h] BYREF
  __int64 v23; // [rsp+68h] [rbp-21h] BYREF
  NTSTRSAFE_PCWSTR pszSrc; // [rsp+70h] [rbp-19h] BYREF
  __int64 v25; // [rsp+78h] [rbp-11h] BYREF
  __int128 Data; // [rsp+80h] [rbp-9h] BYREF
  struct _GUID v27; // [rsp+90h] [rbp+7h] BYREF
  struct _GUID v28; // [rsp+A0h] [rbp+17h] BYREF

  Type = 0;
  RequiredSize = 0;
  v25 = 0;
  Data = 0;
  v22 = 0;
  v27 = 0;
  v28 = 0;
  v7 = (_DWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015
                                                                                                 + 1616))(
                   WdfDriverGlobals,
                   a1,
                   off_1400220B0);
  pszSrc = 0;
  v23 = 0;
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      33,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64 *, unsigned __int64 *))(WdfFunctions_01015 + 2160))(
             WdfDriverGlobals,
             a2,
             0,
             &v25,
             &v22);
  v10 = -1073741789;
  if ( (int)(result + 0x80000000) < 0 || result == -1073741789 )
  {
    v11 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *))(WdfFunctions_01015 + 264))(
                                     WdfDriverGlobals,
                                     a1);
    result = IoGetDevicePropertyData(v11, &DEVPKEY_Device_ContainerId, 0, 0, 0x10u, &Data, &RequiredSize, &Type);
    if ( result >= 0 )
    {
      LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          1,
          34,
          (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
          (__int64)&Data);
      }
      GetKsNodeTypesForRoleAndCOD(v7[104], v7[110], &v27, &v28);
      if ( (v7[106] & 4) != 0 )
      {
        v14 = v7[104] != 0 ? 0xFFFFFFFE : 0;
        v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER))(WdfFunctions_01015 + 944))(
                WdfDriverGlobals,
                WdfDriverGlobals->Driver);
        BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg(
          *(_QWORD *)(v15 + 24),
          v14 + 4,
          L"@System32\\drivers\\bthhfenum.sys",
          v7 + 111,
          248,
          1179145282,
          &pszSrc,
          &v23);
      }
      v16 = v23 + 82;
      if ( v22 >= v23 + 82 )
      {
        v17 = v25;
        v19[0] = 0;
        *(_OWORD *)(v25 + 32) = Data;
        *(struct _GUID *)v17 = v27;
        *(struct _GUID *)(v17 + 16) = v28;
        v18 = v7[44] == 1;
        *(_DWORD *)(v17 + 52) = 80;
        *(_DWORD *)(v17 + 48) = v18;
        RtlInitUnicodeString((PUNICODE_STRING)(v17 + 56), 0);
        if ( pszSrc )
        {
          RtlStringCbCopyW((NTSTRSAFE_PWSTR)(v17 + 80), v22 - 80, pszSrc);
          RtlInitUnicodeString((PUNICODE_STRING)(v17 + 56), (PCWSTR)(v17 + 80));
        }
        ScoStreamGetSDPRecordSupportedFeatures(a1, v19);
        v10 = 0;
        *(_DWORD *)(v17 + 72) = v19[0] & 1;
        v16 = v23 + 82;
      }
      *a3 = v16;
      if ( pszSrc )
        ExFreePoolWithTag((PVOID)pszSrc, 0x46485442u);
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007dc0  mov     [rsp-8+arg_18], rbx
0x140007dc5  push    rbp
0x140007dc6  push    rsi
0x140007dc7  push    rdi
0x140007dc8  push    r14
0x140007dca  push    r15
0x140007dcc  lea     rbp, [rsp-37h]
0x140007dd1  sub     rsp, 0C0h
0x140007dd8  mov     rax, cs:__security_cookie
0x140007ddf  xor     rax, rsp
0x140007de2  mov     [rbp+57h+var_30], rax
0x140007de6  mov     rax, cs:WdfFunctions_01015
0x140007ded  xorps   xmm0, xmm0
0x140007df0  xorps   xmm1, xmm1
0x140007df3  mov     [rbp+57h+var_8C], 0
0x140007dfa  mov     rbx, rdx
0x140007dfd  mov     [rbp+57h+var_88], 0
0x140007e04  mov     r15, r8
0x140007e07  mov     [rbp+57h+var_68], 0
0x140007e0f  mov     r8, cs:off_1400220B0
0x140007e16  mov     r14, rcx
0x140007e19  movups  [rbp+57h+var_60], xmm0
0x140007e1d  mov     [rbp+57h+var_80], 0
0x140007e25  mov     rdx, rcx
0x140007e28  mov     rcx, cs:WdfDriverGlobals
0x140007e2f  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x140007e33  movups  xmmword ptr [rbp+57h+var_40.Data1], xmm1
0x140007e37  mov     rax, [rax+650h]
0x140007e3e  call    _guard_dispatch_icall
0x140007e43  mov     rsi, rax
0x140007e46  mov     [rbp+57h+pszSrc], 0
0x140007e4e  mov     [rbp+57h+var_78], 0
0x140007e56  mov     r10, cs:WPP_GLOBAL_Control
0x140007e5d  lea     rax, WPP_GLOBAL_Control
0x140007e64  cmp     r10, rax
0x140007e67  jz      short loc_140007E7D
0x140007e69  mov     ecx, [r10+2Ch]
0x140007e6d  test    cl, 1
0x140007e70  jz      short loc_140007E7D
0x140007e72  cmp     byte ptr [r10+29h], 4
0x140007e77  jb      short loc_140007E7D
0x140007e79  mov     dl, 1
0x140007e7b  jmp     short loc_140007E7F
0x140007e7d  xor     dl, dl
0x140007e7f  lea     rax, WPP_RECORDER_INITIALIZED
0x140007e86  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007e8d  lea     rcx, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140007e94  setnz   r8b
0x140007e98  test    dl, dl
0x140007e9a  jnz     short loc_140007EA1
0x140007e9c  test    r8b, r8b
0x140007e9f  jz      short loc_140007EC7
0x140007ea1  mov     r9, [r10+40h]
0x140007ea5  mov     [rsp+0E0h+Type], rcx
0x140007eaa  mov     rcx, [r10+18h]
0x140007eae  mov     word ptr [rsp+0E0h+RequiredSize], 21h ; '!'
0x140007eb5  mov     dword ptr [rsp+0E0h+Data], 1
0x140007ebd  mov     byte ptr [rsp+0E0h+Size], 4
0x140007ec2  call    WPP_RECORDER_AND_TRACE_SF_
0x140007ec7  mov     rax, cs:WdfFunctions_01015
0x140007ece  lea     rcx, [rbp+57h+var_80]
0x140007ed2  mov     qword ptr [rsp+0E0h+Size], rcx
0x140007ed7  lea     r9, [rbp+57h+var_68]
0x140007edb  mov     rcx, cs:WdfDriverGlobals
0x140007ee2  xor     r8d, r8d
0x140007ee5  mov     rdx, rbx
0x140007ee8  mov     rax, [rax+870h]
0x140007eef  call    _guard_dispatch_icall
0x140007ef4  mov     edx, 80000000h
0x140007ef9  mov     edi, 0C0000023h
0x140007efe  lea     ecx, [rax+rdx]
0x140007f01  test    edx, ecx
0x140007f03  jnz     short loc_140007F0D
0x140007f05  cmp     eax, edi
0x140007f07  jnz     loc_140008142
0x140007f0d  mov     rax, cs:WdfFunctions_01015
0x140007f14  mov     rdx, r14
0x140007f17  mov     rcx, cs:WdfDriverGlobals
0x140007f1e  mov     rax, [rax+108h]
0x140007f25  call    _guard_dispatch_icall
0x140007f2a  lea     rcx, [rbp+57h+var_8C]
0x140007f2e  xor     r9d, r9d; Flags
0x140007f31  mov     [rsp+0E0h+Type], rcx; Type
0x140007f36  lea     rdx, DEVPKEY_Device_ContainerId; PropertyKey
0x140007f3d  lea     rcx, [rbp+57h+var_88]
0x140007f41  xor     r8d, r8d; Lcid
0x140007f44  mov     [rsp+0E0h+RequiredSize], rcx; RequiredSize
0x140007f49  lea     rcx, [rbp+57h+var_60]
0x140007f4d  mov     [rsp+0E0h+Data], rcx; Data
0x140007f52  mov     rcx, rax; Pdo
0x140007f55  mov     [rsp+0E0h+Size], 10h; Size
0x140007f5d  call    cs:__imp_IoGetDevicePropertyData
0x140007f64  nop     dword ptr [rax+rax+00h]
0x140007f69  test    eax, eax
0x140007f6b  js      loc_140008142
0x140007f71  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f78  lea     rax, WPP_GLOBAL_Control
0x140007f7f  cmp     rcx, rax
0x140007f82  jz      short loc_140007F95
0x140007f84  mov     eax, [rcx+2Ch]
0x140007f87  test    al, 1
0x140007f89  jz      short loc_140007F95
0x140007f8b  cmp     byte ptr [rcx+29h], 4
0x140007f8f  jb      short loc_140007F95
0x140007f91  mov     dl, 1
0x140007f93  jmp     short loc_140007F97
0x140007f95  xor     dl, dl
0x140007f97  lea     rax, WPP_RECORDER_INITIALIZED
0x140007f9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007fa5  setnz   r8b
0x140007fa9  test    dl, dl
0x140007fab  jnz     short loc_140007FB2
0x140007fad  test    r8b, r8b
0x140007fb0  jz      short loc_140007FE8
0x140007fb2  mov     r9, [rcx+40h]
0x140007fb6  lea     rax, [rbp+57h+var_60]
0x140007fba  mov     rcx, [rcx+18h]
0x140007fbe  mov     [rsp+0E0h+var_A0], rax
0x140007fc3  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140007fca  mov     [rsp+0E0h+Type], rax
0x140007fcf  mov     word ptr [rsp+0E0h+RequiredSize], 22h ; '"'
0x140007fd6  mov     dword ptr [rsp+0E0h+Data], 1
0x140007fde  mov     byte ptr [rsp+0E0h+Size], 4
0x140007fe3  call    WPP_RECORDER_AND_TRACE_SF__guid_
0x140007fe8  mov     edx, [rsi+1B8h]; unsigned int
0x140007fee  lea     r9, [rbp+57h+var_40]; struct _GUID *
0x140007ff2  mov     ecx, [rsi+1A0h]; int
0x140007ff8  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x140007ffc  call    ?GetKsNodeTypesForRoleAndCOD@@YAXHKPEAU_GUID@@0@Z; GetKsNodeTypesForRoleAndCOD(int,ulong,_GUID *,_GUID *)
0x140008001  mov     eax, [rsi+1A8h]
0x140008007  test    al, 4
0x140008009  jz      short loc_140008079
0x14000800b  mov     eax, [rsi+1A0h]
0x140008011  mov     rcx, cs:WdfDriverGlobals
0x140008018  neg     eax
0x14000801a  mov     rax, cs:WdfFunctions_01015
0x140008021  sbb     ebx, ebx
0x140008023  and     ebx, 0FFFFFFFEh
0x140008026  mov     rdx, [rcx]
0x140008029  mov     rax, [rax+3B0h]
0x140008030  call    _guard_dispatch_icall
0x140008035  lea     rcx, [rbp+57h+var_78]
0x140008039  mov     [rsp+0E0h+Type], rcx
0x14000803e  lea     r9, [rsi+1BCh]
0x140008045  lea     rcx, [rbp+57h+pszSrc]
0x140008049  mov     [rsp+0E0h+RequiredSize], rcx
0x14000804e  lea     r8, aSystem32Driver; "@System32\\drivers\\bthhfenum.sys"
0x140008055  mov     rcx, [rax+18h]
0x140008059  lea     edx, [rbx+4]
0x14000805c  mov     dword ptr [rsp+0E0h+Data], 46485442h
0x140008064  mov     qword ptr [rsp+0E0h+Size], 0F8h
0x14000806d  call    cs:__imp_BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg
0x140008074  nop     dword ptr [rax+rax+00h]
0x140008079  mov     rax, [rbp+57h+var_78]
0x14000807d  add     rax, 52h ; 'R'
0x140008081  cmp     [rbp+57h+var_80], rax
0x140008085  jb      loc_140008123
0x14000808b  mov     rbx, [rbp+57h+var_68]
0x14000808f  xor     eax, eax
0x140008091  movups  xmm0, [rbp+57h+var_60]
0x140008095  mov     [rbp+57h+var_90], ax
0x140008099  movdqu  xmmword ptr [rbx+20h], xmm0
0x14000809e  lea     rcx, [rbx+38h]; DestinationString
0x1400080a2  movups  xmm1, xmmword ptr [rbp+57h+var_50.Data1]
0x1400080a6  movdqu  xmmword ptr [rbx], xmm1
0x1400080aa  movups  xmm0, xmmword ptr [rbp+57h+var_40.Data1]
0x1400080ae  movdqu  xmmword ptr [rbx+10h], xmm0
0x1400080b3  cmp     dword ptr [rsi+0B0h], 1
0x1400080ba  mov     dword ptr [rbx+34h], 50h ; 'P'
0x1400080c1  setz    al
0x1400080c4  xor     edx, edx; SourceString
0x1400080c6  mov     [rbx+30h], eax
0x1400080c9  call    cs:__imp_RtlInitUnicodeString
0x1400080d0  nop     dword ptr [rax+rax+00h]
0x1400080d5  mov     r8, [rbp+57h+pszSrc]; pszSrc
0x1400080d9  test    r8, r8
0x1400080dc  jz      short loc_140008103
0x1400080de  mov     rdx, [rbp+57h+var_80]
0x1400080e2  lea     rcx, [rbx+50h]; pszDest
0x1400080e6  add     rdx, 0FFFFFFFFFFFFFFB0h; cbDest
0x1400080ea  call    RtlStringCbCopyW
0x1400080ef  lea     rdx, [rbx+50h]; SourceString
0x1400080f3  lea     rcx, [rbx+38h]; DestinationString
0x1400080f7  call    cs:__imp_RtlInitUnicodeString
0x1400080fe  nop     dword ptr [rax+rax+00h]
0x140008103  lea     rdx, [rbp+57h+var_90]
0x140008107  mov     rcx, r14; struct WDFDEVICE__ *
0x14000810a  call    ScoStreamGetSDPRecordSupportedFeatures
0x14000810f  movzx   eax, [rbp+57h+var_90]
0x140008113  xor     edi, edi
0x140008115  and     eax, 1
0x140008118  mov     [rbx+48h], eax
0x14000811b  mov     rax, [rbp+57h+var_78]
0x14000811f  add     rax, 52h ; 'R'
0x140008123  mov     [r15], rax
0x140008126  mov     rcx, [rbp+57h+pszSrc]; P
0x14000812a  test    rcx, rcx
0x14000812d  jz      short loc_140008140
0x14000812f  mov     edx, 46485442h; Tag
0x140008134  call    cs:__imp_ExFreePoolWithTag
0x14000813b  nop     dword ptr [rax+rax+00h]
0x140008140  mov     eax, edi
0x140008142  mov     rcx, [rbp+57h+var_30]
0x140008146  xor     rcx, rsp; StackCookie
0x140008149  call    __security_check_cookie
0x14000814e  mov     rbx, [rsp+0E0h+arg_18]
0x140008156  add     rsp, 0C0h
0x14000815d  pop     r15
0x14000815f  pop     r14
0x140008161  pop     rdi
0x140008162  pop     rsi
0x140008163  pop     rbp
0x140008164  retn
```
