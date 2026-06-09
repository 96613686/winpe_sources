# OpenGlobalizationUserSettingsKey_ForSingleUserModel

- ea: `0x18000d074`
- end: `0x18000d2bb`
- name: `OpenGlobalizationUserSettingsKey_ForSingleUserModel`
- size: `583`
- prototype: `__int64 __fastcall(ULONG, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800064c0`
- `0x18000cd80`

## callees

- `0x18000cd34`
- `0x18000cd5c`
- `0x18000d074`
- `0x18000d2c4`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18000d20d`
- `ntdll!RtlCopyUnicodeString` at `0x18000d26f`
- `ntdll!RtlCopyUnicodeString` at `0x18000d20d`
- `ntdll!RtlCopyUnicodeString` at `0x18000d26f`
- `ntdll!RtlInitUnicodeString` at `0x18000d0a5`
- `ntdll!RtlInitUnicodeString` at `0x18000d0d8`
- `ntdll!RtlInitUnicodeString` at `0x18000d111`
- `ntdll!RtlInitUnicodeString` at `0x18000d1c5`
- `ntdll!RtlInitUnicodeString` at `0x18000d0a5`
- `ntdll!RtlInitUnicodeString` at `0x18000d0d8`
- `ntdll!RtlInitUnicodeString` at `0x18000d111`
- `ntdll!RtlInitUnicodeString` at `0x18000d1c5`
- `ntdll!ZwQueryValueKey` at `0x18000d13d`
- `ntdll!ZwQueryValueKey` at `0x18000d195`
- `ntdll!ZwQueryValueKey` at `0x18000d13d`
- `ntdll!ZwQueryValueKey` at `0x18000d195`
- `ntdll!ZwClose` at `0x18000d29c`
- `ntdll!ZwClose` at `0x18000d29c`

## string_xrefs

- `0x18000d0c9`: `\Registry\Machine\System\CurrentControlSet\Control\CommonGlobUserSettings\`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForSingleUserModel(ULONG a1, _QWORD *a2)
{
  __int64 v3; // rcx
  NTSTATUS v4; // ebx
  __int64 v5; // rcx
  NTSTATUS v6; // eax
  WCHAR *Memory; // rdi
  __int64 v8; // rcx
  HANDLE v9; // rax
  HANDLE v10; // rax
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING v13; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+90h] [rbp+20h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+30h] BYREF
  void *v18; // [rsp+A8h] [rbp+38h] BYREF

  ResultLength = a1;
  if ( dword_1800136A4 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, &word_1800136B0);
    return (unsigned int)OpenRegistryKey(v3, &DestinationString, a2);
  }
  KeyHandle = 0;
  v13 = 0;
  RtlInitUnicodeString(&v13, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CommonGlobUserSettings\\");
  v4 = OpenRegistryKey(v5, &v13, &KeyHandle);
  if ( v4 >= 0 )
  {
    ResultLength = 0;
    ValueName = 0;
    RtlInitUnicodeString(&ValueName, L"RedirectedKey");
    v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( !ResultLength || v6 != -1073741789 && v6 != -2147483643 )
    {
      *(_QWORD *)&DestinationString.Length = 11141120;
      DestinationString.Buffer = &word_1800136B0;
      if ( v13.Length <= 0xAAu )
      {
        RtlCopyUnicodeString(&DestinationString, &v13);
        dword_1800136A4 = 1;
      }
      v10 = KeyHandle;
      KeyHandle = 0;
      v4 = 0;
      *a2 = v10;
      goto LABEL_21;
    }
    Memory = (WCHAR *)AllocateMemory(ResultLength);
    if ( Memory )
    {
      v4 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Memory, ResultLength, &ResultLength);
      if ( v4 >= 0 )
      {
        if ( *((_DWORD *)Memory + 1) != 1 )
        {
          v9 = KeyHandle;
          KeyHandle = 0;
LABEL_15:
          *a2 = v9;
          goto LABEL_16;
        }
        v18 = 0;
        SourceString = 0;
        RtlInitUnicodeString(&SourceString, Memory + 6);
        v4 = OpenRegistryKey(v8, &SourceString, &v18);
        if ( v4 >= 0 )
        {
          *(_QWORD *)&DestinationString.Length = 11141120;
          DestinationString.Buffer = &word_1800136B0;
          if ( SourceString.Length <= 0xAAu )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            dword_1800136A4 = 1;
          }
          v9 = v18;
          goto LABEL_15;
        }
      }
LABEL_16:
      FreeMemory(Memory);
      goto LABEL_21;
    }
    v4 = -1073741801;
  }
LABEL_21:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d074  mov     [rsp-18h+arg_8], rbx
0x18000d079  mov     [rsp-18h+arg_0], ecx
0x18000d07d  push    rbp
0x18000d07e  push    rsi
0x18000d07f  push    rdi
0x18000d080  mov     rbp, rsp
0x18000d083  sub     rsp, 70h
0x18000d087  cmp     cs:dword_1800136A4, 0
0x18000d08e  mov     rsi, rdx
0x18000d091  xorps   xmm0, xmm0
0x18000d094  jz      short loc_18000D0C4
0x18000d096  lea     rdx, word_1800136B0; SourceString
0x18000d09d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d0a1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000d0a5  call    cs:__imp_RtlInitUnicodeString
0x18000d0ac  nop     dword ptr [rax+rax+00h]
0x18000d0b1  mov     r8, rsi
0x18000d0b4  lea     rdx, [rbp+DestinationString]
0x18000d0b8  call    OpenRegistryKey
0x18000d0bd  mov     ebx, eax
0x18000d0bf  jmp     loc_18000D2A8
0x18000d0c4  and     [rbp+KeyHandle], 0
0x18000d0c9  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000d0d0  lea     rcx, [rbp+var_30]; DestinationString
0x18000d0d4  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x18000d0d8  call    cs:__imp_RtlInitUnicodeString
0x18000d0df  nop     dword ptr [rax+rax+00h]
0x18000d0e4  lea     r8, [rbp+KeyHandle]
0x18000d0e8  lea     rdx, [rbp+var_30]
0x18000d0ec  call    OpenRegistryKey
0x18000d0f1  mov     ebx, eax
0x18000d0f3  test    eax, eax
0x18000d0f5  js      loc_18000D293
0x18000d0fb  and     [rbp+arg_0], 0
0x18000d0ff  lea     rdx, aRedirectedkey; "RedirectedKey"
0x18000d106  xorps   xmm0, xmm0
0x18000d109  lea     rcx, [rbp+ValueName]; DestinationString
0x18000d10d  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18000d111  call    cs:__imp_RtlInitUnicodeString
0x18000d118  nop     dword ptr [rax+rax+00h]
0x18000d11d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000d121  lea     rax, [rbp+arg_0]
0x18000d125  xor     r9d, r9d; KeyValueInformation
0x18000d128  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18000d12d  and     [rsp+70h+Length], 0
0x18000d132  lea     rdx, [rbp+ValueName]; ValueName
0x18000d136  lea     ebx, [r9+2]
0x18000d13a  mov     r8d, ebx; KeyValueInformationClass
0x18000d13d  call    cs:__imp_ZwQueryValueKey
0x18000d144  nop     dword ptr [rax+rax+00h]
0x18000d149  mov     ecx, [rbp+arg_0]
0x18000d14c  test    ecx, ecx
0x18000d14e  jz      loc_18000D246
0x18000d154  cmp     eax, 0C0000023h
0x18000d159  jz      short loc_18000D166
0x18000d15b  cmp     eax, 80000005h
0x18000d160  jnz     loc_18000D246
0x18000d166  call    AllocateMemory
0x18000d16b  mov     rdi, rax
0x18000d16e  test    rax, rax
0x18000d171  jz      loc_18000D23F
0x18000d177  mov     ecx, [rbp+arg_0]
0x18000d17a  lea     rax, [rbp+arg_0]
0x18000d17e  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18000d183  lea     rdx, [rbp+ValueName]; ValueName
0x18000d187  mov     [rsp+70h+Length], ecx; Length
0x18000d18b  mov     r9, rdi; KeyValueInformation
0x18000d18e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000d192  mov     r8d, ebx; KeyValueInformationClass
0x18000d195  call    cs:__imp_ZwQueryValueKey
0x18000d19c  nop     dword ptr [rax+rax+00h]
0x18000d1a1  mov     ebx, eax
0x18000d1a3  test    eax, eax
0x18000d1a5  js      loc_18000D235
0x18000d1ab  cmp     dword ptr [rdi+4], 1
0x18000d1af  jnz     short loc_18000D229
0x18000d1b1  and     [rbp+arg_18], 0
0x18000d1b6  lea     rdx, [rdi+0Ch]; SourceString
0x18000d1ba  xorps   xmm0, xmm0
0x18000d1bd  lea     rcx, [rbp+SourceString]; DestinationString
0x18000d1c1  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x18000d1c5  call    cs:__imp_RtlInitUnicodeString
0x18000d1cc  nop     dword ptr [rax+rax+00h]
0x18000d1d1  lea     r8, [rbp+arg_18]
0x18000d1d5  lea     rdx, [rbp+SourceString]
0x18000d1d9  call    OpenRegistryKey
0x18000d1de  mov     ebx, eax
0x18000d1e0  test    eax, eax
0x18000d1e2  js      short loc_18000D235
0x18000d1e4  mov     eax, 0AAh
0x18000d1e9  lea     rcx, word_1800136B0
0x18000d1f0  xorps   xmm0, xmm0
0x18000d1f3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000d1f7  mov     [rbp+DestinationString.MaximumLength], ax
0x18000d1fb  mov     [rbp+DestinationString.Buffer], rcx
0x18000d1ff  cmp     ax, [rbp+SourceString.Length]
0x18000d203  jb      short loc_18000D223
0x18000d205  lea     rdx, [rbp+SourceString]; SourceString
0x18000d209  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d20d  call    cs:__imp_RtlCopyUnicodeString
0x18000d214  nop     dword ptr [rax+rax+00h]
0x18000d219  mov     cs:dword_1800136A4, 1
0x18000d223  mov     rax, [rbp+arg_18]
0x18000d227  jmp     short loc_18000D232
0x18000d229  mov     rax, [rbp+KeyHandle]
0x18000d22d  and     [rbp+KeyHandle], 0
0x18000d232  mov     [rsi], rax
0x18000d235  mov     rcx, rdi
0x18000d238  call    FreeMemory
0x18000d23d  jmp     short loc_18000D293
0x18000d23f  mov     ebx, 0C0000017h
0x18000d244  jmp     short loc_18000D293
0x18000d246  mov     eax, 0AAh
0x18000d24b  lea     rcx, word_1800136B0
0x18000d252  xorps   xmm0, xmm0
0x18000d255  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000d259  mov     [rbp+DestinationString.MaximumLength], ax
0x18000d25d  mov     [rbp+DestinationString.Buffer], rcx
0x18000d261  cmp     ax, [rbp+var_30.Length]
0x18000d265  jb      short loc_18000D285
0x18000d267  lea     rdx, [rbp+var_30]; SourceString
0x18000d26b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d26f  call    cs:__imp_RtlCopyUnicodeString
0x18000d276  nop     dword ptr [rax+rax+00h]
0x18000d27b  mov     cs:dword_1800136A4, 1
0x18000d285  mov     rax, [rbp+KeyHandle]
0x18000d289  and     [rbp+KeyHandle], 0
0x18000d28e  xor     ebx, ebx
0x18000d290  mov     [rsi], rax
0x18000d293  mov     rcx, [rbp+KeyHandle]; Handle
0x18000d297  test    rcx, rcx
0x18000d29a  jz      short loc_18000D2A8
0x18000d29c  call    cs:__imp_ZwClose
0x18000d2a3  nop     dword ptr [rax+rax+00h]
0x18000d2a8  mov     eax, ebx
0x18000d2aa  mov     rbx, [rsp+70h+arg_8]
0x18000d2b2  add     rsp, 70h
0x18000d2b6  pop     rdi
0x18000d2b7  pop     rsi
0x18000d2b8  pop     rbp
0x18000d2b9  retn
```
