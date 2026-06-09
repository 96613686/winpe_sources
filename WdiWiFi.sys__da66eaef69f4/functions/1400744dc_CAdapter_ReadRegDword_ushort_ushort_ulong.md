# CAdapter::ReadRegDword(ushort *,ushort *,ulong *)

- ea: `0x1400744dc`
- end: `0x140074708`
- name: `?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z`
- size: `556`
- prototype: `int(CAdapter *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140077e34`
- `0x1400aa060`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x1400744dc`
- `0x1400a4630`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140074694`
- `ntoskrnl!ZwClose` at `0x140074694`
- `ntoskrnl!ZwQueryValueKey` at `0x14007464b`
- `ntoskrnl!ZwQueryValueKey` at `0x14007464b`
- `ntoskrnl!ZwOpenKey` at `0x1400745c7`
- `ntoskrnl!ZwOpenKey` at `0x1400745c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007458c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007461c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007458c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007461c`

## pseudocode

```c
__int64 __fastcall CAdapter::ReadRegDword(CAdapter *this, unsigned __int16 *a2, unsigned __int16 *a3, unsigned int *a4)
{
  unsigned int v4; // edi
  const WCHAR *v7; // rsi
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // ebx
  int v12; // r9d
  NTSTATUS v13; // eax
  PULONG ResultLength; // [rsp+28h] [rbp-71h]
  PULONG ResultLengtha; // [rsp+28h] [rbp-71h]
  char v17; // [rsp+30h] [rbp-69h]
  ULONG v18; // [rsp+40h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  __int128 KeyValueInformation; // [rsp+A0h] [rbp+7h] BYREF
  int v24; // [rsp+B0h] [rbp+17h]

  v4 = *a4;
  KeyHandle = 0;
  v24 = 0;
  v18 = 0;
  v7 = a2;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  KeyValueInformation = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      64,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  RtlInitUnicodeString(&DestinationString, v7);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v11 = v8;
  if ( v8 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v17 = v8;
    v12 = 65;
    ResultLengtha = (PULONG)v7;
    goto LABEL_8;
  }
  RtlInitUnicodeString(&ValueName, a3);
  v13 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &v18);
  v11 = v13;
  if ( v13 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v17 = v13;
      v12 = 66;
      ResultLengtha = (PULONG)a3;
LABEL_8:
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_SD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        v12,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        (__int64)ResultLengtha,
        v17);
    }
  }
  else
  {
    v4 = HIDWORD(KeyValueInformation);
  }
LABEL_13:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  *a4 = v4;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(ResultLength) = v11;
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      67,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      ResultLength);
  }
  return v11;
}

```

## disassembly

```asm
0x1400744dc  mov     [rsp-8+arg_0], rbx
0x1400744e1  push    rbp
0x1400744e2  push    rsi
0x1400744e3  push    rdi
0x1400744e4  push    r12
0x1400744e6  push    r13
0x1400744e8  push    r14
0x1400744ea  push    r15
0x1400744ec  lea     rbp, [rsp-27h]
0x1400744f1  sub     rsp, 0C0h
0x1400744f8  mov     rax, cs:__security_cookie
0x1400744ff  xor     rax, rsp
0x140074502  mov     [rbp+57h+var_38], rax
0x140074506  mov     edi, [r9]
0x140074509  xorps   xmm0, xmm0
0x14007450c  xor     r12d, r12d
0x14007450f  xorps   xmm1, xmm1
0x140074512  xor     eax, eax
0x140074514  mov     [rbp+57h+KeyHandle], r12
0x140074518  mov     [rbp+57h+var_40], eax
0x14007451b  mov     r15, r9
0x14007451e  mov     r14, r8
0x140074521  mov     [rbp+57h+var_B0], r12d
0x140074525  mov     rsi, rdx
0x140074528  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14007452c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140074530  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140074534  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140074538  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x14007453c  movups  [rbp+57h+KeyValueInformation], xmm0
0x140074540  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140074547  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007454e  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140074555  jz      short loc_140074585
0x140074557  mov     rcx, cs:WPP_GLOBAL_Control
0x14007455e  cmp     byte ptr [rcx+29h], 5
0x140074562  jnb     short loc_14007456B
0x140074564  cmp     [rcx+48h], r12w
0x140074569  jz      short loc_140074585
0x14007456b  mov     rcx, [rcx+40h]
0x14007456f  mov     r9d, 40h ; '@'
0x140074575  mov     dl, 5
0x140074577  mov     qword ptr [rsp+0F0h+Length], rax
0x14007457c  lea     r8d, [r9-3Fh]
0x140074580  call    WPP_RECORDER_SF_
0x140074585  mov     rdx, rsi; SourceString
0x140074588  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14007458c  call    cs:__imp_RtlInitUnicodeString
0x140074593  nop     dword ptr [rax+rax+00h]
0x140074598  lea     rax, [rbp+57h+DestinationString]
0x14007459c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400745a3  xorps   xmm0, xmm0
0x1400745a6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400745aa  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400745ae  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1400745b2  mov     edx, 20019h; DesiredAccess
0x1400745b7  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400745be  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400745c2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400745c7  call    cs:__imp_ZwOpenKey
0x1400745ce  nop     dword ptr [rax+rax+00h]
0x1400745d3  mov     ebx, eax
0x1400745d5  test    eax, eax
0x1400745d7  jz      short loc_140074615
0x1400745d9  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400745e0  jz      loc_140074684
0x1400745e6  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1400745ea  mov     r9d, 41h ; 'A'
0x1400745f0  mov     [rsp+0F0h+ResultLength], rsi
0x1400745f5  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400745fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140074603  mov     dl, 4
0x140074605  mov     qword ptr [rsp+0F0h+Length], rsi
0x14007460a  mov     rcx, [rcx+40h]
0x14007460e  call    WPP_RECORDER_SF_SD
0x140074613  jmp     short loc_14007468B
0x140074615  mov     rdx, r14; SourceString
0x140074618  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14007461c  call    cs:__imp_RtlInitUnicodeString
0x140074623  nop     dword ptr [rax+rax+00h]
0x140074628  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14007462c  lea     rax, [rbp+57h+var_B0]
0x140074630  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x140074635  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140074639  mov     r8d, 2; KeyValueInformationClass
0x14007463f  mov     [rsp+0F0h+Length], 14h; Length
0x140074647  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14007464b  call    cs:__imp_ZwQueryValueKey
0x140074652  nop     dword ptr [rax+rax+00h]
0x140074657  mov     ebx, eax
0x140074659  test    eax, eax
0x14007465b  jz      short loc_140074681
0x14007465d  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140074664  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x14007466b  jz      short loc_14007468B
0x14007466d  mov     dword ptr [rsp+0F0h+var_C0], eax
0x140074671  mov     r9d, 42h ; 'B'
0x140074677  mov     [rsp+0F0h+ResultLength], r14
0x14007467c  jmp     loc_1400745FC
0x140074681  mov     edi, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140074684  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x14007468b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14007468f  test    rcx, rcx
0x140074692  jz      short loc_1400746A0
0x140074694  call    cs:__imp_ZwClose
0x14007469b  nop     dword ptr [rax+rax+00h]
0x1400746a0  mov     [r15], edi
0x1400746a3  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400746aa  jz      short loc_1400746DE
0x1400746ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400746b3  cmp     byte ptr [rcx+29h], 5
0x1400746b7  jnb     short loc_1400746C0
0x1400746b9  cmp     [rcx+48h], r12w
0x1400746be  jz      short loc_1400746DE
0x1400746c0  mov     rcx, [rcx+40h]
0x1400746c4  mov     r9d, 43h ; 'C'
0x1400746ca  mov     dword ptr [rsp+0F0h+ResultLength], ebx
0x1400746ce  mov     dl, 5
0x1400746d0  mov     qword ptr [rsp+0F0h+Length], rsi
0x1400746d5  lea     r8d, [r9-42h]
0x1400746d9  call    WPP_RECORDER_SF_D
0x1400746de  mov     eax, ebx
0x1400746e0  mov     rcx, [rbp+57h+var_38]
0x1400746e4  xor     rcx, rsp; StackCookie
0x1400746e7  call    __security_check_cookie
0x1400746ec  mov     rbx, [rsp+0F0h+arg_0]
0x1400746f4  add     rsp, 0C0h
0x1400746fb  pop     r15
0x1400746fd  pop     r14
0x1400746ff  pop     r13
0x140074701  pop     r12
0x140074703  pop     rdi
0x140074704  pop     rsi
0x140074705  pop     rbp
0x140074706  retn
```
