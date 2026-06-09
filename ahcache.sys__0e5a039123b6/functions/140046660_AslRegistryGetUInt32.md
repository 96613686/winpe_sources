# AslRegistryGetUInt32

- ea: `0x140046660`
- end: `0x140046775`
- name: `AslRegistryGetUInt32`
- size: `277`
- prototype: `__int64 __fastcall(_DWORD *, void *, const WCHAR *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400046e8`
- `0x14002e270`
- `0x140041638`
- `0x140046180`
- `0x14004634c`

## callees

- `0x14000447b`
- `0x14000449f`
- `0x1400079f0`
- `0x14003e364`
- `0x140046660`

## string_xrefs

- `0x140046708`: `AslRegistryGetUInt32`
- `0x140046744`: `AslRegistryGetUInt32_UStr`
- `0x14004675a`: `AslRegistryGetUInt32_UStr`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32(_DWORD *a1, void *a2, const WCHAR *a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  const char *v10; // rdx
  __int64 Length; // [rsp+20h] [rbp-68h]
  ULONG ResultLength; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-50h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-40h] BYREF
  int v15; // [rsp+58h] [rbp-30h]

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx_0(&DestinationString, a3);
  v6 = inited;
  if ( inited < 0 )
  {
    v8 = "RtlInitUnicodeStringEx failed [%x]";
    v9 = 1148;
    v10 = "AslRegistryGetUInt32";
    goto LABEL_6;
  }
  v15 = 0;
  ResultLength = 0;
  *a1 = 0;
  KeyValueInformation = 0;
  inited = ZwQueryValueKey_0(
             a2,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             &ResultLength);
  v6 = inited;
  if ( inited < 0 )
  {
    if ( inited == -1073741772 )
      return v6;
    v8 = "Failed to query key value [%x]";
    v9 = 1091;
    v10 = "AslRegistryGetUInt32_UStr";
LABEL_6:
    LODWORD(Length) = inited;
    AslLogCallPrintf(1, v10, v9, v8, Length);
    return v6;
  }
  if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
  {
    v6 = 0;
    *a1 = HIDWORD(KeyValueInformation);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1098, "Invalid value type");
    return (unsigned int)-1073741788;
  }
  return v6;
}

```

## disassembly

```asm
0x140046660  push    rbx
0x140046662  push    rsi
0x140046663  push    rdi
0x140046664  sub     rsp, 70h
0x140046668  mov     rax, cs:__security_cookie
0x14004666f  xor     rax, rsp
0x140046672  mov     [rsp+88h+var_28], rax
0x140046677  mov     rsi, rdx
0x14004667a  mov     rdi, rcx
0x14004667d  xorps   xmm0, xmm0
0x140046680  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x140046685  mov     rdx, r8; SourceString
0x140046688  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14004668d  call    RtlInitUnicodeStringEx_0
0x140046692  mov     ebx, eax
0x140046694  test    eax, eax
0x140046696  js      short loc_1400466FB
0x140046698  xor     eax, eax
0x14004669a  lea     r9, [rsp+88h+KeyValueInformation]; KeyValueInformation
0x14004669f  mov     [rsp+88h+var_30], eax
0x1400466a3  lea     rdx, [rsp+88h+DestinationString]; ValueName
0x1400466a8  mov     [rsp+88h+var_58], eax
0x1400466ac  xorps   xmm0, xmm0
0x1400466af  mov     [rdi], eax
0x1400466b1  mov     r8d, 2; KeyValueInformationClass
0x1400466b7  lea     rax, [rsp+88h+var_58]
0x1400466bc  mov     rcx, rsi; KeyHandle
0x1400466bf  mov     [rsp+88h+ResultLength], rax; ResultLength
0x1400466c4  mov     dword ptr [rsp+88h+Length], 14h; Length
0x1400466cc  movups  [rsp+88h+KeyValueInformation], xmm0
0x1400466d1  call    ZwQueryValueKey_0
0x1400466d6  mov     ebx, eax
0x1400466d8  test    eax, eax
0x1400466da  jns     short loc_14004671F
0x1400466dc  cmp     eax, 0C0000034h
0x1400466e1  jnz     short loc_140046737
0x1400466e3  mov     eax, ebx
0x1400466e5  mov     rcx, [rsp+88h+var_28]
0x1400466ea  xor     rcx, rsp; StackCookie
0x1400466ed  call    __security_check_cookie
0x1400466f2  add     rsp, 70h
0x1400466f6  pop     rdi
0x1400466f7  pop     rsi
0x1400466f8  pop     rbx
0x1400466f9  retn
0x1400466fb  lea     r9, aRtlinitunicode_0; "RtlInitUnicodeStringEx failed [%x]"
0x140046702  mov     r8d, 47Ch
0x140046708  lea     rdx, aAslregistryget_5; "AslRegistryGetUInt32"
0x14004670f  mov     ecx, 1
0x140046714  mov     dword ptr [rsp+88h+Length], eax
0x140046718  call    AslLogCallPrintf
0x14004671d  jmp     short loc_1400466E3
0x14004671f  cmp     dword ptr [rsp+88h+KeyValueInformation+4], 4
0x140046724  jnz     short loc_14004674D
0x140046726  cmp     dword ptr [rsp+88h+KeyValueInformation+8], 4
0x14004672b  jnz     short loc_14004674D
0x14004672d  mov     eax, dword ptr [rsp+88h+KeyValueInformation+0Ch]
0x140046731  xor     ebx, ebx
0x140046733  mov     [rdi], eax
0x140046735  jmp     short loc_1400466E3
0x140046737  lea     r9, aFailedToQueryK_0; "Failed to query key value [%x]"
0x14004673e  mov     r8d, 443h
0x140046744  lea     rdx, aAslregistryget_1; "AslRegistryGetUInt32_UStr"
0x14004674b  jmp     short loc_14004670F
0x14004674d  lea     r9, aInvalidValueTy; "Invalid value type"
0x140046754  mov     r8d, 44Ah
0x14004675a  lea     rdx, aAslregistryget_1; "AslRegistryGetUInt32_UStr"
0x140046761  mov     ecx, 1
0x140046766  call    AslLogCallPrintf
0x14004676b  mov     ebx, 0C0000024h
0x140046770  jmp     loc_1400466E3
```
