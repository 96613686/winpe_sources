# GetRegistryValue

- ea: `0x180018a34`
- end: `0x180018b27`
- name: `GetRegistryValue`
- size: `243`
- prototype: `HRESULT __fastcall(HREG hkey, const wchar_t *wszValue, _KEY_VALUE_FULL_INFORMATION **ppinfo, unsigned int hkey)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014090`
- `0x180015464`
- `0x180016b10`
- `0x180068b44`

## callees

- `0x180017894`
- `0x180018a34`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018a60`
- `ntdll!RtlInitUnicodeString` at `0x180018a60`
- `ntdll!ZwQueryValueKey` at `0x180018a87`
- `ntdll!ZwQueryValueKey` at `0x180018aee`
- `ntdll!ZwQueryValueKey` at `0x180018a87`
- `ntdll!ZwQueryValueKey` at `0x180018aee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ab6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ab6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b1a`

## pseudocode

```c
HRESULT __fastcall GetRegistryValue(
        HREG hkey,
        const wchar_t *wszValue,
        _KEY_VALUE_FULL_INFORMATION **ppinfo,
        unsigned int a4)
{
  NTSTATUS v6; // eax
  int v7; // ecx
  _KEY_VALUE_FULL_INFORMATION *v9; // rax
  _KEY_VALUE_FULL_INFORMATION *v10; // rdi
  NTSTATUS v11; // ebx
  _UNICODE_STRING unicodeString; // [rsp+30h] [rbp-18h] BYREF
  unsigned int keyValueLength; // [rsp+68h] [rbp+20h] BYREF

  keyValueLength = 0;
  unicodeString = 0;
  RtlInitUnicodeString(&unicodeString, wszValue);
  v6 = ZwQueryValueKey(hkey.h, &unicodeString, KeyValueFullInformation, 0, 0, &keyValueLength);
  if ( v6 != -2147483643 && v6 != -1073741789 )
  {
    v7 = v6;
    return HrNt(v7);
  }
  v9 = (_KEY_VALUE_FULL_INFORMATION *)CoTaskMemAlloc(keyValueLength);
  v10 = v9;
  if ( !v9 )
  {
    v7 = -1073741670;
    return HrNt(v7);
  }
  v11 = ZwQueryValueKey(hkey.h, &unicodeString, KeyValueFullInformation, v9, keyValueLength, &keyValueLength);
  if ( v11 < 0 )
  {
    CoTaskMemFree(v10);
    v7 = v11;
    return HrNt(v7);
  }
  if ( v10->Type == 1 )
  {
    *ppinfo = v10;
    return 0;
  }
  else
  {
    CoTaskMemFree(v10);
    return -2147221165;
  }
}

```

## disassembly

```asm
0x180018a34  mov     rax, rsp
0x180018a37  mov     [rax+8], rbx
0x180018a3b  mov     [rax+10h], rsi
0x180018a3f  mov     [rax+20h], r9d
0x180018a43  push    rdi
0x180018a44  sub     rsp, 40h
0x180018a48  mov     rbx, hkey
0x180018a4b  mov     dword ptr [rax+20h], 0
0x180018a52  xorps   xmm0, xmm0
0x180018a55  lea     hkey, [rax-18h]; DestinationString
0x180018a59  movups  xmmword ptr [rax-18h], xmm0
0x180018a5d  mov     rsi, ppinfo
0x180018a60  call    cs:__imp_RtlInitUnicodeString
0x180018a66  xor     r9d, r9d; KeyValueInformation
0x180018a69  lea     rax, [rsp+48h+keyValueLength]
0x180018a6e  mov     [rsp+48h+ResultLength], rax; ResultLength
0x180018a73  lea     wszValue, [rsp+48h+unicodeString]; ValueName
0x180018a78  mov     hkey, rbx; KeyHandle
0x180018a7b  mov     [rsp+48h+Length], 0; Length
0x180018a83  lea     r8d, [r9+1]; KeyValueInformationClass
0x180018a87  call    cs:__imp_ZwQueryValueKey
0x180018a8d  cmp     eax, 80000005h
0x180018a92  jz      short loc_180018AB2
0x180018a94  cmp     eax, 0C0000023h
0x180018a99  jz      short loc_180018AB2
0x180018a9b  mov     ecx, eax; status
0x180018a9d  call    HrNt
0x180018aa2  mov     rbx, [rsp+48h+arg_0]
0x180018aa7  mov     rsi, [rsp+48h+arg_8]
0x180018aac  add     rsp, 40h
0x180018ab0  pop     rdi
0x180018ab1  retn
0x180018ab2  mov     ecx, [rsp+48h+keyValueLength]; cb
0x180018ab6  call    cs:__imp_CoTaskMemAlloc
0x180018abc  mov     rdi, rax
0x180018abf  test    rax, rax
0x180018ac2  jnz     short loc_180018ACB
0x180018ac4  mov     ecx, 0C000009Ah
0x180018ac9  jmp     short loc_180018A9D
0x180018acb  lea     rax, [rsp+48h+keyValueLength]
0x180018ad0  mov     r9, rdi; KeyValueInformation
0x180018ad3  mov     [rsp+48h+ResultLength], rax; ResultLength
0x180018ad8  lea     wszValue, [rsp+48h+unicodeString]; ValueName
0x180018add  mov     eax, [rsp+48h+keyValueLength]
0x180018ae1  mov     r8d, 1; KeyValueInformationClass
0x180018ae7  mov     hkey, rbx; KeyHandle
0x180018aea  mov     [rsp+48h+Length], eax; Length
0x180018aee  call    cs:__imp_ZwQueryValueKey
0x180018af4  mov     ebx, eax
0x180018af6  test    eax, eax
0x180018af8  js      short loc_180018B17
0x180018afa  cmp     dword ptr [rdi+4], 1
0x180018afe  jz      short loc_180018B10
0x180018b00  mov     hkey, rdi; pv
0x180018b03  call    cs:__imp_CoTaskMemFree
0x180018b09  mov     eax, 80040153h
0x180018b0e  jmp     short loc_180018AA2
0x180018b10  mov     [rsi], rdi
0x180018b13  xor     eax, eax
0x180018b15  jmp     short loc_180018AA2
0x180018b17  mov     hkey, rdi; pv
0x180018b1a  call    cs:__imp_CoTaskMemFree
0x180018b20  mov     ecx, ebx
0x180018b22  jmp     loc_180018A9D
```
