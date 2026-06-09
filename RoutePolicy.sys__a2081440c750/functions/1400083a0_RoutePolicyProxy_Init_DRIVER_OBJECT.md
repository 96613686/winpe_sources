# RoutePolicyProxy::Init(_DRIVER_OBJECT *)

- ea: `0x1400083a0`
- end: `0x140008654`
- name: `?Init@RoutePolicyProxy@@YAJPEAU_DRIVER_OBJECT@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001903c`

## callees

- `0x140001008`
- `0x1400083a0`
- `0x14000a680`
- `0x140017140`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x1400085e0`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400085e0`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1400083dd`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1400083dd`
- `ntoskrnl!IoDeleteDevice` at `0x14000854c`
- `ntoskrnl!IoDeleteDevice` at `0x1400085ac`
- `ntoskrnl!IoDeleteDevice` at `0x14000854c`
- `ntoskrnl!IoDeleteDevice` at `0x1400085ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400084e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400085cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400084e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400085cc`

## string_xrefs

- `0x140008405`: `SeConvertStringSecurityDescriptorToSecurityDescriptor failed`
- `0x140008567`: `IoCreateDeviceSecure failed`
- `0x1400085fd`: `IoCreateSymbolicLink failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyProxy::Init(PDRIVER_OBJECT DriverObject, struct _DRIVER_OBJECT *a2)
{
  int v3; // eax
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // edi
  ULONG v8; // edx
  ULONG v9; // r9d
  struct _DEVICE_OBJECT *v10; // rcx
  NTSTATUS v11; // ebx
  int v12; // r8d
  int v13; // r9d
  const char *v14; // rax
  int *v15; // rdx
  struct _DEVICE_OBJECT *v16; // rcx
  ULONG v17; // [rsp+20h] [rbp-E0h]
  BOOLEAN v18; // [rsp+28h] [rbp-D8h]
  const GUID *v19; // [rsp+38h] [rbp-C8h]
  NTSTATUS v20; // [rsp+50h] [rbp-B0h] BYREF
  const char *v21; // [rsp+58h] [rbp-A8h] BYREF
  PDEVICE_OBJECT *v22; // [rsp+60h] [rbp-A0h]
  PDEVICE_OBJECT DeviceObject; // [rsp+68h] [rbp-98h] BYREF
  char v24; // [rsp+70h] [rbp-90h]
  UNICODE_STRING DefaultSDDLString; // [rsp+78h] [rbp-88h] BYREF
  PDEVICE_OBJECT v26; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v29[12]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+170h] [rbp+70h]

  v3 = SeConvertStringSecurityDescriptorToSecurityDescriptor(
         L"D:P(A;;FA;;;S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888)",
         1,
         &SecurityDescriptor);
  v6 = v3;
  if ( v3 >= 0 )
  {
    v29[0] = *(_OWORD *)L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888)";
    v30 = *(_QWORD *)L"88)";
    v29[2] = *(_OWORD *)L"A;;GA;;;SY)(A;;GA;;;S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888)";
    *(_QWORD *)&DefaultSDDLString.Length = 13107398;
    v29[1] = *(_OWORD *)L"A;;;BA)(A;;GA;;;SY)(A;;GA;;;S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888)";
    DefaultSDDLString.Buffer = (wchar_t *)v29;
    v29[4] = *(_OWORD *)L"A;;;S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888)";
    v29[3] = *(_OWORD *)L"SY)(A;;GA;;;S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888)";
    v29[6] = *(_OWORD *)L"5767994-3874329934-3800885181-2130851812-726865888)";
    v29[5] = *(_OWORD *)L"5-80-4155767994-3874329934-3800885181-2130851812-726865888)";
    v29[8] = *(_OWORD *)L"34-3800885181-2130851812-726865888)";
    v29[7] = *(_OWORD *)L"3874329934-3800885181-2130851812-726865888)";
    v29[10] = *(_OWORD *)L"30851812-726865888)";
    v29[9] = *(_OWORD *)L"85181-2130851812-726865888)";
    DestinationString = 0;
    v29[11] = *(_OWORD *)L"-726865888)";
    RtlInitUnicodeString(&DestinationString, L"\\Device\\RoutePolicy");
    v26 = 0;
    v22 = &v26;
    DeviceObject = 0;
    v24 = 1;
    v11 = WdmlibIoCreateDeviceSecure(
            DriverObject,
            v8,
            &DestinationString,
            v9,
            v17,
            v18,
            &DefaultSDDLString,
            v19,
            &DeviceObject);
    if ( v24 )
    {
      v10 = *v22;
      *v22 = DeviceObject;
      if ( v10 )
        IoDeleteDevice(v10);
    }
    if ( v11 >= 0 )
    {
      SymbolicLinkName = 0;
      RtlInitUnicodeString(&SymbolicLinkName, L"\\??\\RoutePolicy");
      v11 = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
      if ( v11 >= 0 )
      {
        v26->Flags |= 4u;
        memset64(DriverObject->MajorFunction, (unsigned __int64)RoutePolicyProxyDispatch, 0x1Cu);
        ::DeviceObject = v26;
        return (unsigned int)v11;
      }
      LODWORD(v10) = dword_140012050;
      if ( (unsigned int)dword_140012050 <= 2 )
      {
LABEL_12:
        v16 = v26;
        v26 = 0;
        if ( v16 )
          IoDeleteDevice(v16);
        return (unsigned int)v11;
      }
      v14 = "IoCreateSymbolicLink failed";
      v15 = (int *)byte_140010809;
    }
    else
    {
      if ( (unsigned int)dword_140012050 <= 2 )
        goto LABEL_12;
      v14 = "IoCreateDeviceSecure failed";
      v15 = &dword_140010A64;
    }
    v21 = v14;
    v20 = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v10,
      (_DWORD)v15,
      v12,
      v13,
      (__int64)&v21,
      (__int64)&v20);
    goto LABEL_12;
  }
  if ( (unsigned int)dword_140012050 > 2 )
  {
    v20 = v3;
    v21 = "SeConvertStringSecurityDescriptorToSecurityDescriptor failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_140012050,
      (unsigned int)byte_1400108FD,
      v4,
      v5,
      (__int64)&v21,
      (__int64)&v20);
  }
  return v6;
}

```

## disassembly

```asm
0x1400083a0  push    rbp
0x1400083a2  push    rbx
0x1400083a3  push    rsi
0x1400083a4  push    rdi
0x1400083a5  lea     rbp, [rsp-98h]
0x1400083ad  sub     rsp, 198h
0x1400083b4  mov     rax, cs:__security_cookie
0x1400083bb  xor     rax, rsp
0x1400083be  mov     [rbp+0B0h+var_30], rax
0x1400083c5  xor     r9d, r9d
0x1400083c8  lea     r8, SecurityDescriptor
0x1400083cf  mov     rsi, rcx
0x1400083d2  lea     rcx, aDPAFaS15804155; "D:P(A;;FA;;;S-1-5-80-4155767994-3874329"...
0x1400083d9  lea     edx, [r9+1]
0x1400083dd  call    cs:__imp_SeConvertStringSecurityDescriptorToSecurityDescriptor
0x1400083e4  nop     dword ptr [rax+rax+00h]
0x1400083e9  mov     edi, eax
0x1400083eb  test    eax, eax
0x1400083ed  jns     short loc_140008431
0x1400083ef  mov     ecx, cs:dword_140012050
0x1400083f5  cmp     ecx, 2
0x1400083f8  jbe     short loc_14000842A
0x1400083fa  mov     [rsp+1B0h+var_160], eax
0x1400083fe  lea     rdx, byte_1400108FD
0x140008405  lea     rax, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x14000840c  mov     [rsp+1B0h+var_158], rax
0x140008411  lea     rax, [rsp+1B0h+var_160]
0x140008416  mov     [rsp+1B0h+var_188], rax
0x14000841b  lea     rax, [rsp+1B0h+var_158]
0x140008420  mov     [rsp+1B0h+var_190], rax
0x140008425  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000842a  mov     eax, edi
0x14000842c  jmp     loc_140008638
0x140008431  movaps  xmm0, xmmword ptr cs:aDPAGaBaAGaSyAG; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;S-1"...
0x140008438  lea     rdx, aDeviceRoutepol; "\\Device\\RoutePolicy"
0x14000843f  movaps  xmm1, xmmword ptr cs:aDPAGaBaAGaSyAG+10h; "A;;;BA)(A;;GA;;;SY)(A;;GA;;;S-1-5-80-41"...
0x140008446  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14000844a  mov     rax, qword ptr cs:aDPAGaBaAGaSyAG+0C0h; "88)"
0x140008451  movups  [rbp+0B0h+var_100], xmm0
0x140008455  mov     [rbp+0B0h+var_40], rax
0x140008459  lea     rax, [rbp+0B0h+var_100]
0x14000845d  movaps  xmm0, xmmword ptr cs:aDPAGaBaAGaSyAG+20h; "A;;GA;;;SY)(A;;GA;;;S-1-5-80-4155767994"...
0x140008464  movups  [rbp+0B0h+var_E0], xmm0
0x140008468  mov     qword ptr [rsp+1B0h+var_138.Length], 0C800C6h
0x140008471  movaps  xmm0, xmmword ptr cs:aDPAGaBaAGaSyAG+40h; "A;;;S-1-5-80-4155767994-3874329934-3800"...
0x140008478  movups  [rbp+0B0h+var_F0], xmm1
0x14000847c  mov     [rbp+0B0h+var_138.Buffer], rax
0x140008480  movaps  xmm1, xmmword ptr cs:aDPAGaBaAGaSyAG+30h; "SY)(A;;GA;;;S-1-5-80-4155767994-3874329"...
0x140008487  movups  [rbp+0B0h+var_C0], xmm0
0x14000848b  movaps  xmm0, xmmword ptr cs:aDPAGaBaAGaSyAG+60h; "5767994-3874329934-3800885181-213085181"...
0x140008492  movups  [rbp+0B0h+var_D0], xmm1
0x140008496  movaps  xmm1, xmmword ptr cs:aDPAGaBaAGaSyAG+50h; "5-80-4155767994-3874329934-3800885181-2"...
0x14000849d  movups  [rbp+0B0h+var_A0], xmm0
0x1400084a1  movaps  xmm0, xmmword ptr cs:aDPAGaBaAGaSyAG+80h; "34-3800885181-2130851812-726865888)"
0x1400084a8  movups  [rbp+0B0h+var_B0], xmm1
0x1400084ac  movaps  xmm1, xmmword ptr cs:aDPAGaBaAGaSyAG+70h; "3874329934-3800885181-2130851812-726865"...
0x1400084b3  movups  [rbp+0B0h+var_80], xmm0
0x1400084b7  movaps  xmm0, xmmword ptr cs:aDPAGaBaAGaSyAG+0A0h; "30851812-726865888)"
0x1400084be  movups  [rbp+0B0h+var_90], xmm1
0x1400084c2  movaps  xmm1, xmmword ptr cs:aDPAGaBaAGaSyAG+90h; "85181-2130851812-726865888)"
0x1400084c9  movups  [rbp+0B0h+var_60], xmm0
0x1400084cd  movups  [rbp+0B0h+var_70], xmm1
0x1400084d1  movaps  xmm1, xmmword ptr cs:aDPAGaBaAGaSyAG+0B0h; "-726865888)"
0x1400084d8  xorps   xmm0, xmm0
0x1400084db  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x1400084df  movups  [rbp+0B0h+var_50], xmm1
0x1400084e3  call    cs:__imp_RtlInitUnicodeString
0x1400084ea  nop     dword ptr [rax+rax+00h]
0x1400084ef  lea     rax, [rbp+0B0h+var_128]
0x1400084f3  mov     [rbp+0B0h+var_128], 0
0x1400084fb  mov     [rsp+1B0h+var_150], rax
0x140008500  lea     r8, [rbp+0B0h+DestinationString]; DeviceName
0x140008504  lea     rax, [rsp+1B0h+var_148]
0x140008509  mov     [rsp+1B0h+var_148], 0
0x140008512  mov     [rsp+1B0h+DeviceObject], rax; DeviceObject
0x140008517  mov     rcx, rsi; DriverObject
0x14000851a  lea     rax, [rsp+1B0h+var_138]
0x14000851f  mov     [rsp+1B0h+var_140], 1
0x140008524  mov     [rsp+1B0h+DefaultSDDLString], rax; DefaultSDDLString
0x140008529  call    WdmlibIoCreateDeviceSecure
0x14000852e  cmp     [rsp+1B0h+var_140], 0
0x140008533  mov     ebx, eax
0x140008535  jz      short loc_140008558
0x140008537  mov     rdi, [rsp+1B0h+var_150]
0x14000853c  mov     rdx, [rsp+1B0h+var_148]
0x140008541  mov     rcx, [rdi]; DeviceObject
0x140008544  mov     [rdi], rdx
0x140008547  test    rcx, rcx
0x14000854a  jz      short loc_140008558
0x14000854c  call    cs:__imp_IoDeleteDevice
0x140008553  nop     dword ptr [rax+rax+00h]
0x140008558  test    ebx, ebx
0x14000855a  jns     short loc_1400085BA
0x14000855c  mov     eax, cs:dword_140012050
0x140008562  cmp     eax, 2
0x140008565  jbe     short loc_140008597
0x140008567  lea     rax, aIocreatedevice_0; "IoCreateDeviceSecure failed"
0x14000856e  lea     rdx, dword_140010A64
0x140008575  mov     [rsp+1B0h+var_158], rax
0x14000857a  lea     rax, [rsp+1B0h+var_160]
0x14000857f  mov     [rsp+1B0h+var_188], rax
0x140008584  lea     rax, [rsp+1B0h+var_158]
0x140008589  mov     [rsp+1B0h+var_190], rax
0x14000858e  mov     [rsp+1B0h+var_160], ebx
0x140008592  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140008597  mov     rcx, [rbp+0B0h+var_128]; DeviceObject
0x14000859b  mov     [rbp+0B0h+var_128], 0
0x1400085a3  test    rcx, rcx
0x1400085a6  jz      loc_140008636
0x1400085ac  call    cs:__imp_IoDeleteDevice
0x1400085b3  nop     dword ptr [rax+rax+00h]
0x1400085b8  jmp     short loc_140008636
0x1400085ba  xorps   xmm0, xmm0
0x1400085bd  lea     rdx, SourceString; "\\??\\RoutePolicy"
0x1400085c4  lea     rcx, [rbp+0B0h+SymbolicLinkName]; DestinationString
0x1400085c8  movups  xmmword ptr [rbp+0B0h+SymbolicLinkName.Length], xmm0
0x1400085cc  call    cs:__imp_RtlInitUnicodeString
0x1400085d3  nop     dword ptr [rax+rax+00h]
0x1400085d8  lea     rdx, [rbp+0B0h+DestinationString]; DeviceName
0x1400085dc  lea     rcx, [rbp+0B0h+SymbolicLinkName]; SymbolicLinkName
0x1400085e0  call    cs:__imp_IoCreateSymbolicLink
0x1400085e7  nop     dword ptr [rax+rax+00h]
0x1400085ec  mov     ebx, eax
0x1400085ee  test    eax, eax
0x1400085f0  jns     short loc_140008610
0x1400085f2  mov     ecx, cs:dword_140012050
0x1400085f8  cmp     ecx, 2
0x1400085fb  jbe     short loc_140008597
0x1400085fd  lea     rax, aIocreatesymbol; "IoCreateSymbolicLink failed"
0x140008604  lea     rdx, byte_140010809
0x14000860b  jmp     loc_140008575
0x140008610  mov     rax, [rbp+0B0h+var_128]
0x140008614  lea     rdi, [rsi+70h]
0x140008618  mov     ecx, 1Ch
0x14000861d  or      dword ptr [rax+30h], 4
0x140008621  lea     rax, ?RoutePolicyProxyDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; RoutePolicyProxyDispatch(_DEVICE_OBJECT *,_IRP *)
0x140008628  rep stosq
0x14000862b  mov     rax, [rbp+0B0h+var_128]
0x14000862f  mov     cs:DeviceObject, rax
0x140008636  mov     eax, ebx
0x140008638  mov     rcx, [rbp+0B0h+var_30]
0x14000863f  xor     rcx, rsp; StackCookie
0x140008642  call    __security_check_cookie
0x140008647  add     rsp, 198h
0x14000864e  pop     rdi
0x14000864f  pop     rsi
0x140008650  pop     rbx
0x140008651  pop     rbp
0x140008652  retn
```
