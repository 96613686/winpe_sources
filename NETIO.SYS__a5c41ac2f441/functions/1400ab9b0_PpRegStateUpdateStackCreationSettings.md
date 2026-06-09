# PpRegStateUpdateStackCreationSettings

- ea: `0x1400ab9b0`
- end: `0x1400abb24`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400aa8c0`

## callees

- `0x140076dc8`
- `0x1400ab4c8`
- `0x1400ab9b0`
- `0x1400abcd8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400aba94`
- `ntoskrnl!ZwClose` at `0x1400abb05`
- `ntoskrnl!ZwClose` at `0x1400aba94`
- `ntoskrnl!ZwClose` at `0x1400abb05`
- `ntoskrnl!ZwSetValueKey` at `0x1400abaf3`
- `ntoskrnl!ZwSetValueKey` at `0x1400abaf3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400abaa8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400abaa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aba3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aba3e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400aba1e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400aba1e`

## string_xrefs

- `0x1400abab8`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !PiRegStateDiscriptor )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        PiRegStateDiscriptor = 2;
      }
      else
      {
        PiRegStateDiscriptor = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( PiRegStateDiscriptor != 1 )
      v6 = 0;
    P = v6;
    WstrKey = CmRegUtilCreateWstrKey(
                (_DWORD)Handle,
                (unsigned int)L"Properties",
                v4,
                v5,
                (__int64)v6,
                0,
                (__int64)&KeyHandle);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      WstrKey = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( WstrKey >= 0 )
        WstrKey = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x1400ab9b0  mov     [rsp-8+arg_0], rbx
0x1400ab9b5  mov     [rsp-8+arg_8], rdi
0x1400ab9ba  push    rbp
0x1400ab9bb  mov     rbp, rsp
0x1400ab9be  sub     rsp, 60h
0x1400ab9c2  lea     rax, [rbp+Handle]
0x1400ab9c6  mov     [rbp+P], 0
0x1400ab9ce  xor     r9d, r9d
0x1400ab9d1  mov     [rsp+60h+Data], rax
0x1400ab9d6  xor     r8d, r8d
0x1400ab9d9  mov     [rbp+KeyHandle], 0
0x1400ab9e1  mov     rdi, rdx
0x1400ab9e4  mov     [rbp+Handle], 0
0x1400ab9ec  call    PiRegStateOpenClassKey
0x1400ab9f1  test    eax, eax
0x1400ab9f3  js      loc_1400ABB13
0x1400ab9f9  cmp     cs:PiRegStateDiscriptor, 0
0x1400aba00  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400aba07  jnz     short loc_1400ABA56
0x1400aba09  xor     edx, edx
0x1400aba0b  lea     rax, [rbp+P]
0x1400aba0f  mov     r9b, 1
0x1400aba12  mov     [rsp+60h+Data], rax
0x1400aba17  mov     rcx, rbx
0x1400aba1a  lea     r8d, [rdx+1]
0x1400aba1e  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400aba25  nop     dword ptr [rax+rax+00h]
0x1400aba2a  test    eax, eax
0x1400aba2c  js      short loc_1400ABA4C
0x1400aba2e  mov     rcx, [rbp+P]; P
0x1400aba32  xor     edx, edx; Tag
0x1400aba34  mov     cs:PiRegStateDiscriptor, 1
0x1400aba3e  call    cs:__imp_ExFreePoolWithTag
0x1400aba45  nop     dword ptr [rax+rax+00h]
0x1400aba4a  jmp     short loc_1400ABA56
0x1400aba4c  mov     cs:PiRegStateDiscriptor, 2
0x1400aba56  mov     rcx, [rbp+Handle]
0x1400aba5a  lea     rdx, aProperties; "Properties"
0x1400aba61  xor     eax, eax
0x1400aba63  cmp     cs:PiRegStateDiscriptor, 1
0x1400aba6a  cmovnz  rbx, rax
0x1400aba6e  lea     rax, [rbp+KeyHandle]
0x1400aba72  mov     [rsp+60h+var_30], rax
0x1400aba77  mov     qword ptr [rsp+60h+DataSize], 0
0x1400aba80  mov     [rsp+60h+Data], rbx
0x1400aba85  mov     [rbp+P], rbx
0x1400aba89  call    CmRegUtilCreateWstrKey
0x1400aba8e  mov     rcx, [rbp+Handle]; Handle
0x1400aba92  mov     ebx, eax
0x1400aba94  call    cs:__imp_ZwClose
0x1400aba9b  nop     dword ptr [rax+rax+00h]
0x1400abaa0  test    ebx, ebx
0x1400abaa2  js      short loc_1400ABB11
0x1400abaa4  mov     rcx, [rdi+8]; SecurityDescriptor
0x1400abaa8  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400abaaf  nop     dword ptr [rax+rax+00h]
0x1400abab4  mov     r11, [rdi+8]
0x1400abab8  lea     rdx, aSecurity; "Security"
0x1400ababf  xorps   xmm0, xmm0
0x1400abac2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400abac6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400abaca  mov     r10d, eax
0x1400abacd  call    WdmlibRtlInitUnicodeStringEx
0x1400abad2  mov     ebx, eax
0x1400abad4  test    eax, eax
0x1400abad6  js      short loc_1400ABB01
0x1400abad8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400abadc  lea     rdx, [rbp+DestinationString]; ValueName
0x1400abae0  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400abae5  mov     r9d, 3; Type
0x1400abaeb  xor     r8d, r8d; TitleIndex
0x1400abaee  mov     [rsp+60h+Data], r11; Data
0x1400abaf3  call    cs:__imp_ZwSetValueKey
0x1400abafa  nop     dword ptr [rax+rax+00h]
0x1400abaff  mov     ebx, eax
0x1400abb01  mov     rcx, [rbp+KeyHandle]; Handle
0x1400abb05  call    cs:__imp_ZwClose
0x1400abb0c  nop     dword ptr [rax+rax+00h]
0x1400abb11  mov     eax, ebx
0x1400abb13  mov     rbx, [rsp+60h+arg_0]
0x1400abb18  mov     rdi, [rsp+60h+arg_8]
0x1400abb1d  add     rsp, 60h
0x1400abb21  pop     rbp
0x1400abb22  retn
```
