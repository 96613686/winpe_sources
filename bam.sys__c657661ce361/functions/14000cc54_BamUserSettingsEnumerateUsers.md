# BamUserSettingsEnumerateUsers

- ea: `0x14000cc54`
- end: `0x14000ce0f`
- name: `BamUserSettingsEnumerateUsers`
- size: `443`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ce58`
- `0x14000f460`

## callees

- `0x1400026d0`
- `0x140002710`
- `0x140002ac0`
- `0x14000cc54`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd3d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cd3d`
- `ntoskrnl!ZwClose` at `0x14000cdb1`
- `ntoskrnl!ZwClose` at `0x14000cdd9`
- `ntoskrnl!ZwClose` at `0x14000cdb1`
- `ntoskrnl!ZwClose` at `0x14000cdd9`
- `ntoskrnl!ZwOpenKey` at `0x14000cd87`
- `ntoskrnl!ZwOpenKey` at `0x14000cd87`
- `ntoskrnl!ZwEnumerateKey` at `0x14000cd06`
- `ntoskrnl!ZwEnumerateKey` at `0x14000cd06`

## pseudocode

```c
__int64 __fastcall BamUserSettingsEnumerateUsers(
        void (__fastcall *a1)(void *, struct _UNICODE_STRING *, __int64),
        __int64 a2)
{
  unsigned int v4; // ebx
  ULONG i; // edi
  NTSTATUS v6; // eax
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD KeyInformation[100]; // [rsp+80h] [rbp-80h] BYREF

  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  memset(KeyInformation, 0, sizeof(KeyInformation));
  KeyHandle = 0;
  if ( BampUserSettingsContext )
  {
    if ( a1 )
    {
      for ( i = 0; ; ++i )
      {
        v6 = ZwEnumerateKey(BampUserSettingsContext, i, KeyBasicInformation, KeyInformation, 0x190u, &ResultLength);
        v4 = v6;
        if ( v6 == -2147483622 )
          break;
        if ( v6 < 0 )
          goto LABEL_12;
        *((_WORD *)&KeyInformation[4] + ((unsigned __int64)KeyInformation[3] >> 1)) = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)&KeyInformation[4]);
        ObjectAttributes.RootDirectory = BampUserSettingsContext;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0 )
        {
          a1(KeyHandle, &DestinationString, a2);
          ZwClose(KeyHandle);
          KeyHandle = 0;
        }
      }
      v4 = 0;
LABEL_12:
      if ( KeyHandle )
        ZwClose(KeyHandle);
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return v4;
}

```

## disassembly

```asm
0x14000cc54  mov     [rsp-8+arg_10], rbx
0x14000cc59  mov     [rsp-8+arg_18], rsi
0x14000cc5e  push    rbp
0x14000cc5f  push    rdi
0x14000cc60  push    r14
0x14000cc62  lea     rbp, [rsp-120h]
0x14000cc6a  sub     rsp, 220h
0x14000cc71  mov     rax, cs:__security_cookie
0x14000cc78  xor     rax, rsp
0x14000cc7b  mov     [rbp+130h+var_20], rax
0x14000cc82  xorps   xmm0, xmm0
0x14000cc85  mov     r14, rdx
0x14000cc88  mov     rsi, rcx
0x14000cc8b  xor     eax, eax
0x14000cc8d  movups  xmmword ptr [rsp+230h+ObjectAttributes.ObjectName], xmm0
0x14000cc92  xor     edx, edx; Val
0x14000cc94  mov     [rsp+230h+var_1F8], eax
0x14000cc98  mov     r8d, 190h; Size
0x14000cc9e  lea     rcx, [rbp+130h+KeyInformation]; void *
0x14000cca2  movups  xmmword ptr [rsp+230h+ObjectAttributes+1Ch], xmm0
0x14000cca7  movups  xmmword ptr [rsp+230h+ObjectAttributes.Length], xmm0
0x14000ccac  movups  xmmword ptr [rsp+230h+DestinationString.Length], xmm0
0x14000ccb1  call    memset
0x14000ccb6  cmp     qword ptr cs:BampUserSettingsContext, 0
0x14000ccbe  mov     [rsp+230h+KeyHandle], 0
0x14000ccc7  jnz     short loc_14000CCD3
0x14000ccc9  mov     ebx, 0C0000001h
0x14000ccce  jmp     loc_14000CDE5
0x14000ccd3  test    rsi, rsi
0x14000ccd6  jnz     short loc_14000CCE2
0x14000ccd8  mov     ebx, 0C000000Dh
0x14000ccdd  jmp     loc_14000CDE5
0x14000cce2  xor     edi, edi
0x14000cce4  mov     rcx, qword ptr cs:BampUserSettingsContext; KeyHandle
0x14000cceb  lea     rax, [rsp+230h+var_1F8]
0x14000ccf0  mov     [rsp+230h+ResultLength], rax; ResultLength
0x14000ccf5  lea     r9, [rbp+130h+KeyInformation]; KeyInformation
0x14000ccf9  xor     r8d, r8d; KeyInformationClass
0x14000ccfc  mov     [rsp+230h+Length], 190h; Length
0x14000cd04  mov     edx, edi; Index
0x14000cd06  call    cs:__imp_ZwEnumerateKey
0x14000cd0d  nop     dword ptr [rax+rax+00h]
0x14000cd12  mov     ebx, eax
0x14000cd14  cmp     eax, 8000001Ah
0x14000cd19  jz      loc_14000CDCD
0x14000cd1f  test    eax, eax
0x14000cd21  js      loc_14000CDCF
0x14000cd27  mov     ecx, [rbp+130h+var_1A4]
0x14000cd2a  lea     rdx, [rbp+130h+SourceString]; SourceString
0x14000cd2e  shr     rcx, 1
0x14000cd31  xor     eax, eax
0x14000cd33  mov     [rbp+rcx*2+130h+SourceString], ax
0x14000cd38  lea     rcx, [rsp+230h+DestinationString]; DestinationString
0x14000cd3d  call    cs:__imp_RtlInitUnicodeString
0x14000cd44  nop     dword ptr [rax+rax+00h]
0x14000cd49  mov     rax, qword ptr cs:BampUserSettingsContext
0x14000cd50  lea     r8, [rsp+230h+ObjectAttributes]; ObjectAttributes
0x14000cd55  mov     [rsp+230h+ObjectAttributes.RootDirectory], rax
0x14000cd5a  lea     rcx, [rsp+230h+KeyHandle]; KeyHandle
0x14000cd5f  lea     rax, [rsp+230h+DestinationString]
0x14000cd64  mov     [rsp+230h+ObjectAttributes.Length], 30h ; '0'
0x14000cd6c  xorps   xmm0, xmm0
0x14000cd6f  mov     [rsp+230h+ObjectAttributes.ObjectName], rax
0x14000cd74  mov     edx, 0F003Fh; DesiredAccess
0x14000cd79  mov     [rsp+230h+ObjectAttributes.Attributes], 240h
0x14000cd81  movdqu  xmmword ptr [rsp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000cd87  call    cs:__imp_ZwOpenKey
0x14000cd8e  nop     dword ptr [rax+rax+00h]
0x14000cd93  test    eax, eax
0x14000cd95  js      short loc_14000CDC6
0x14000cd97  mov     rcx, [rsp+230h+KeyHandle]
0x14000cd9c  lea     rdx, [rsp+230h+DestinationString]
0x14000cda1  mov     r8, r14
0x14000cda4  mov     rax, rsi
0x14000cda7  call    _guard_dispatch_icall
0x14000cdac  mov     rcx, [rsp+230h+KeyHandle]; Handle
0x14000cdb1  call    cs:__imp_ZwClose
0x14000cdb8  nop     dword ptr [rax+rax+00h]
0x14000cdbd  mov     [rsp+230h+KeyHandle], 0
0x14000cdc6  inc     edi
0x14000cdc8  jmp     loc_14000CCE4
0x14000cdcd  xor     ebx, ebx
0x14000cdcf  mov     rcx, [rsp+230h+KeyHandle]; Handle
0x14000cdd4  test    rcx, rcx
0x14000cdd7  jz      short loc_14000CDE5
0x14000cdd9  call    cs:__imp_ZwClose
0x14000cde0  nop     dword ptr [rax+rax+00h]
0x14000cde5  mov     eax, ebx
0x14000cde7  mov     rcx, [rbp+130h+var_20]
0x14000cdee  xor     rcx, rsp; StackCookie
0x14000cdf1  call    __security_check_cookie
0x14000cdf6  lea     r11, [rsp+230h+var_10]
0x14000cdfe  mov     rbx, [r11+30h]
0x14000ce02  mov     rsi, [r11+38h]
0x14000ce06  mov     rsp, r11
0x14000ce09  pop     r14
0x14000ce0b  pop     rdi
0x14000ce0c  pop     rbp
0x14000ce0d  retn
```
