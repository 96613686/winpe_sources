# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180086cdc`
- end: `0x180086e85`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `425`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, DWORD dwFlags, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18008659c`
- `0x1800912fc`
- `0x1800922f0`
- `0x180092444`
- `0x18009d3a8`
- `0x18009e138`

## callees

- `0x180086570`
- `0x180086cdc`
- `0x180087188`
- `0x1800871b4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aad8`
- `0x18008af7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086d65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086e06`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086d65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086e06`

## string_xrefs

- `0x180086e3f`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180086d1b`: `RegReadStringValue`
- `0x180086d85`: `RegReadStringValue`
- `0x180086e38`: `RegReadStringValue`
- `0x180086e6b`: `RegReadStringValue`
- `0x180086db2`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x180086d7e`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadStringValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwFlags,
        unsigned __int16 **a6)
{
  LSTATUS ValueW; // eax
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *RegValueName; // rax
  unsigned __int16 *pvData; // rax
  unsigned __int16 *v16; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-68h]
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  DWORD v19[17]; // [rsp+44h] [rbp-44h] BYREF

  v19[0] = 0;
  pcbData = 0;
  if ( !a6 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
    return 87;
  }
  *a6 = 0;
  ValueW = RegGetValueW(hkey, lpSubKey, a3, dwFlags, v19, 0, &pcbData);
  v12 = ValueW;
  if ( ValueW != 2 )
  {
    if ( ValueW == 1630 )
    {
      RegValueName = GetRegValueName(a3);
      LODWORD(pdwType) = dwFlags;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
        L"RegReadStringValue",
        a4,
        RegValueName,
        pdwType);
      return 0;
    }
    if ( !ValueW || ValueW == 234 )
    {
      if ( pcbData )
      {
        pvData = (unsigned __int16 *)SafeAlloc(pcbData);
        *a6 = pvData;
        if ( !pvData )
        {
          v12 = 14;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
          goto LABEL_14;
        }
        v12 = RegGetValueW(hkey, lpSubKey, a3, dwFlags, v19, pvData, &pcbData);
      }
      if ( !v12 )
        return v12;
    }
LABEL_14:
    Logger::WriteRegistryFailureEvent(v12, L"RegGetValueW", a4, a3);
    v16 = GetRegValueName(a3);
    LODWORD(pdwType) = v12;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadStringValue",
      a4,
      v16,
      pdwType);
    SafeFree(*a6);
    *a6 = 0;
    return v12;
  }
  v13 = GetRegValueName(a3);
  LODWORD(pdwType) = 2;
  Logger::TraceWarning(
    L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
    L"RegReadStringValue",
    a4,
    v13,
    pdwType);
  return 0;
}

```

## disassembly

```asm
0x180086cdc  push    rbx
0x180086cde  push    rbp
0x180086cdf  push    rsi
0x180086ce0  push    rdi
0x180086ce1  push    r12
0x180086ce3  push    r14
0x180086ce5  push    r15
0x180086ce7  sub     rsp, 50h
0x180086ceb  mov     rsi, [rsp+88h+arg_28]
0x180086cf3  mov     rbp, r9
0x180086cf6  mov     [rsp+88h+var_44], 0
0x180086cfe  mov     rdi, r8
0x180086d01  mov     [rsp+88h+var_48], 0
0x180086d09  mov     r15, rdx
0x180086d0c  mov     r12, rcx
0x180086d0f  test    rsi, rsi
0x180086d12  jnz     short loc_180086D36
0x180086d14  lea     r8, aPdata; "pData"
0x180086d1b  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180086d22  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180086d29  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086d2e  lea     eax, [rsi+57h]
0x180086d31  jmp     loc_180086E5C
0x180086d36  mov     r14d, [rsp+88h+dwFlags]
0x180086d3e  lea     rax, [rsp+88h+var_48]
0x180086d43  mov     [rsp+88h+pcbData], rax; pcbData
0x180086d48  mov     r9d, r14d; dwFlags
0x180086d4b  lea     rax, [rsp+88h+var_44]
0x180086d50  mov     [rsp+88h+pvData], 0; pvData
0x180086d59  mov     [rsp+88h+pdwType], rax; pdwType
0x180086d5e  mov     qword ptr [rsi], 0
0x180086d65  call    cs:__imp_RegGetValueW
0x180086d6b  mov     ebx, eax
0x180086d6d  cmp     eax, 2
0x180086d70  jnz     short loc_180086D9E
0x180086d72  mov     rcx, rdi; unsigned __int16 *
0x180086d75  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086d7a  mov     dword ptr [rsp+88h+pdwType], ebx
0x180086d7e  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x180086d85  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180086d8c  mov     r8, rbp
0x180086d8f  mov     r9, rax
0x180086d92  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180086d97  xor     ebx, ebx
0x180086d99  jmp     loc_180086E5A
0x180086d9e  cmp     eax, 65Eh
0x180086da3  jnz     short loc_180086DBB
0x180086da5  mov     rcx, rdi; unsigned __int16 *
0x180086da8  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086dad  mov     dword ptr [rsp+88h+pdwType], r14d
0x180086db2  lea     rcx, aSTheRegistryKe_4; "%s: The registry key value \"%s@%s\" is"...
0x180086db9  jmp     short loc_180086D85
0x180086dbb  test    eax, eax
0x180086dbd  jz      short loc_180086DC6
0x180086dbf  cmp     eax, 0EAh
0x180086dc4  jnz     short loc_180086E12
0x180086dc6  mov     eax, [rsp+88h+var_48]
0x180086dca  test    eax, eax
0x180086dcc  jz      short loc_180086E0E
0x180086dce  mov     ecx, eax; unsigned __int64
0x180086dd0  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180086dd5  mov     [rsi], rax
0x180086dd8  test    rax, rax
0x180086ddb  jz      loc_180086E6B
0x180086de1  lea     rcx, [rsp+88h+var_48]
0x180086de6  mov     r9d, r14d; dwFlags
0x180086de9  mov     [rsp+88h+pcbData], rcx; pcbData
0x180086dee  mov     r8, rdi; lpValue
0x180086df1  mov     [rsp+88h+pvData], rax; pvData
0x180086df6  mov     rdx, r15; lpSubKey
0x180086df9  lea     rax, [rsp+88h+var_44]
0x180086dfe  mov     rcx, r12; hkey
0x180086e01  mov     [rsp+88h+pdwType], rax; pdwType
0x180086e06  call    cs:__imp_RegGetValueW
0x180086e0c  mov     ebx, eax
0x180086e0e  test    ebx, ebx
0x180086e10  jz      short loc_180086E5A
0x180086e12  mov     r9, rdi; unsigned __int16 *
0x180086e15  lea     rdx, aReggetvaluew; "RegGetValueW"
0x180086e1c  mov     r8, rbp; unsigned __int16 *
0x180086e1f  mov     ecx, ebx; unsigned int
0x180086e21  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180086e26  mov     rcx, rdi; unsigned __int16 *
0x180086e29  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086e2e  mov     r9, rax
0x180086e31  mov     dword ptr [rsp+88h+pdwType], ebx
0x180086e35  mov     r8, rbp
0x180086e38  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180086e3f  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x180086e46  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180086e4b  mov     rcx, [rsi]; void *
0x180086e4e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180086e53  mov     qword ptr [rsi], 0
0x180086e5a  mov     eax, ebx
0x180086e5c  add     rsp, 50h
0x180086e60  pop     r15
0x180086e62  pop     r14
0x180086e64  pop     r12
0x180086e66  pop     rdi
0x180086e67  pop     rsi
0x180086e68  pop     rbp
0x180086e69  pop     rbx
0x180086e6a  retn
0x180086e6b  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180086e72  mov     ebx, 0Eh
0x180086e77  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180086e7e  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180086e83  jmp     short loc_180086E12
```
