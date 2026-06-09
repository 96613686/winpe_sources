# CAdapter::ReadRegDword(ushort *,ushort *,ulong *)

- ea: `0x140032580`
- end: `0x1400327bb`
- name: `?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z`
- size: `571`
- prototype: `int(CAdapter *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `5`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140033378`
- `0x14006b040`
- `0x1400c9144`
- `0x1400c9274`
- `0x1400d1010`

## callees

- `0x140004d48`
- `0x14000c778`
- `0x14000d054`
- `0x140032580`
- `0x1400327c4`
- `0x140059a30`
- `0x1400dfd00`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140032747`
- `ntoskrnl!ZwClose` at `0x140032747`
- `ntoskrnl!ZwQueryValueKey` at `0x14003270a`
- `ntoskrnl!ZwQueryValueKey` at `0x14003270a`
- `ntoskrnl!ZwOpenKey` at `0x140032687`
- `ntoskrnl!ZwOpenKey` at `0x140032687`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003264c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400326dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003264c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400326dc`

## pseudocode

```c
__int64 __fastcall CAdapter::ReadRegDword(CAdapter *this, unsigned __int16 *a2, unsigned __int16 *a3, unsigned int *a4)
{
  int v7; // edx
  unsigned int v9; // r15d
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // ebx
  int v14; // r9d
  NTSTATUS v15; // eax
  unsigned __int16 *ResultLength; // [rsp+28h] [rbp-71h]
  char v17; // [rsp+30h] [rbp-69h]
  ULONG v18; // [rsp+40h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  __int128 KeyValueInformation; // [rsp+A0h] [rbp+7h] BYREF
  int v24; // [rsp+B0h] [rbp+17h]

  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(this) )
    return CRegistryHelper::ReadRegDword(a2, a3, a4);
  v9 = *a4;
  KeyHandle = 0;
  v18 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v24 = 0;
  DestinationString = 0;
  ValueName = 0;
  KeyValueInformation = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      18,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v13 = v10;
  if ( v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = v10;
      v14 = 19;
      ResultLength = a2;
LABEL_10:
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_SD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v12,
        v14,
        (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
        (__int64)ResultLength,
        v17);
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, a3);
    v15 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &v18);
    v13 = v15;
    if ( !v15 )
    {
      v9 = HIDWORD(KeyValueInformation);
      goto LABEL_15;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = v15;
      v14 = 20;
      ResultLength = a3;
      goto LABEL_10;
    }
  }
LABEL_15:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  *a4 = v9;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      21,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x140032580  mov     [rsp-8+arg_0], rbx
0x140032585  push    rbp
0x140032586  push    rsi
0x140032587  push    rdi
0x140032588  push    r12
0x14003258a  push    r13
0x14003258c  push    r14
0x14003258e  push    r15
0x140032590  lea     rbp, [rsp-27h]
0x140032595  sub     rsp, 0C0h
0x14003259c  mov     rax, cs:__security_cookie
0x1400325a3  xor     rax, rsp
0x1400325a6  mov     [rbp+57h+var_38], rax
0x1400325aa  mov     rsi, r9
0x1400325ad  mov     r14, r8
0x1400325b0  mov     rdi, rdx
0x1400325b3  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400325b8  xor     r12d, r12d
0x1400325bb  test    eax, eax
0x1400325bd  jz      short loc_1400325D2
0x1400325bf  mov     r8, rsi; unsigned int *
0x1400325c2  mov     rdx, r14; PCWSTR
0x1400325c5  mov     rcx, rdi; SourceString
0x1400325c8  call    ?ReadRegDword@CRegistryHelper@@SAJPEAG0PEAK@Z; CRegistryHelper::ReadRegDword(ushort *,ushort *,ulong *)
0x1400325cd  jmp     loc_140032793
0x1400325d2  mov     r15d, [rsi]
0x1400325d5  xorps   xmm0, xmm0
0x1400325d8  xorps   xmm1, xmm1
0x1400325db  mov     [rbp+57h+KeyHandle], r12
0x1400325df  xor     eax, eax
0x1400325e1  mov     [rbp+57h+var_B0], r12d
0x1400325e5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400325e9  mov     [rbp+57h+var_40], eax
0x1400325ec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400325f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400325f4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400325f8  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1400325fc  movups  [rbp+57h+KeyValueInformation], xmm0
0x140032600  lea     r13, WPP_RECORDER_INITIALIZED
0x140032607  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003260e  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x140032615  jz      short loc_140032645
0x140032617  mov     rcx, cs:WPP_GLOBAL_Control
0x14003261e  cmp     byte ptr [rcx+29h], 5
0x140032622  jnb     short loc_14003262B
0x140032624  cmp     [rcx+48h], r12w
0x140032629  jz      short loc_140032645
0x14003262b  mov     rcx, [rcx+40h]
0x14003262f  mov     r9d, 12h
0x140032635  mov     dl, 5
0x140032637  mov     qword ptr [rsp+0F0h+Length], rax
0x14003263c  lea     r8d, [r9-11h]
0x140032640  call    WPP_RECORDER_SF_
0x140032645  mov     rdx, rdi; SourceString
0x140032648  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003264c  call    cs:__imp_RtlInitUnicodeString
0x140032653  nop     dword ptr [rax+rax+00h]
0x140032658  lea     rax, [rbp+57h+DestinationString]
0x14003265c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140032663  xorps   xmm0, xmm0
0x140032666  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14003266a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14003266e  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140032672  mov     edx, 20019h; DesiredAccess
0x140032677  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14003267e  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140032682  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140032687  call    cs:__imp_ZwOpenKey
0x14003268e  nop     dword ptr [rax+rax+00h]
0x140032693  mov     ebx, eax
0x140032695  test    eax, eax
0x140032697  jz      short loc_1400326D5
0x140032699  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400326a0  jz      loc_140032737
0x1400326a6  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1400326aa  mov     r9d, 13h
0x1400326b0  mov     [rsp+0F0h+ResultLength], rdi
0x1400326b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400326bc  lea     rdi, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x1400326c3  mov     dl, 4
0x1400326c5  mov     qword ptr [rsp+0F0h+Length], rdi
0x1400326ca  mov     rcx, [rcx+40h]
0x1400326ce  call    WPP_RECORDER_SF_SD
0x1400326d3  jmp     short loc_14003273E
0x1400326d5  mov     rdx, r14; SourceString
0x1400326d8  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400326dc  call    cs:__imp_RtlInitUnicodeString
0x1400326e3  nop     dword ptr [rax+rax+00h]
0x1400326e8  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400326ec  lea     rax, [rbp+57h+var_B0]
0x1400326f0  mov     edi, 14h
0x1400326f5  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x1400326fa  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400326fe  mov     [rsp+0F0h+Length], edi; Length
0x140032702  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140032706  lea     r8d, [rdi-12h]; KeyValueInformationClass
0x14003270a  call    cs:__imp_ZwQueryValueKey
0x140032711  nop     dword ptr [rax+rax+00h]
0x140032716  mov     ebx, eax
0x140032718  test    eax, eax
0x14003271a  jz      short loc_140032733
0x14003271c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140032723  jz      short loc_140032737
0x140032725  mov     dword ptr [rsp+0F0h+var_C0], eax
0x140032729  mov     r9d, edi
0x14003272c  mov     [rsp+0F0h+ResultLength], r14
0x140032731  jmp     short loc_1400326B5
0x140032733  mov     r15d, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140032737  lea     rdi, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14003273e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140032742  test    rcx, rcx
0x140032745  jz      short loc_140032753
0x140032747  call    cs:__imp_ZwClose
0x14003274e  nop     dword ptr [rax+rax+00h]
0x140032753  mov     [rsi], r15d
0x140032756  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003275d  jz      short loc_140032791
0x14003275f  mov     rcx, cs:WPP_GLOBAL_Control
0x140032766  cmp     byte ptr [rcx+29h], 5
0x14003276a  jnb     short loc_140032773
0x14003276c  cmp     [rcx+48h], r12w
0x140032771  jz      short loc_140032791
0x140032773  mov     rcx, [rcx+40h]
0x140032777  mov     r9d, 15h
0x14003277d  mov     dword ptr [rsp+0F0h+ResultLength], ebx
0x140032781  mov     dl, 5
0x140032783  mov     qword ptr [rsp+0F0h+Length], rdi
0x140032788  lea     r8d, [r9-14h]
0x14003278c  call    WPP_RECORDER_SF_d
0x140032791  mov     eax, ebx
0x140032793  mov     rcx, [rbp+57h+var_38]
0x140032797  xor     rcx, rsp; StackCookie
0x14003279a  call    __security_check_cookie
0x14003279f  mov     rbx, [rsp+0F0h+arg_0]
0x1400327a7  add     rsp, 0C0h
0x1400327ae  pop     r15
0x1400327b0  pop     r14
0x1400327b2  pop     r13
0x1400327b4  pop     r12
0x1400327b6  pop     rdi
0x1400327b7  pop     rsi
0x1400327b8  pop     rbp
0x1400327b9  retn
```
