# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180079b18`
- end: `0x180079cbc`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `420`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, DWORD, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180079504`
- `0x180081084`
- `0x180081db0`

## callees

- `0x18006b2c0`
- `0x1800794d8`
- `0x180079b18`
- `0x180079de0`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d268`
- `0x18007d344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079c46`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079b9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079c46`

## string_xrefs

- `0x180079c78`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180079b55`: `RegReadStringValue`
- `0x180079bb9`: `RegReadStringValue`
- `0x180079c71`: `RegReadStringValue`
- `0x180079ca2`: `RegReadStringValue`
- `0x180079bb2`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x180079be9`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`

## pseudocode

```c
__int64 __fastcall RegReadStringValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD pcbData,
        unsigned __int16 **a6)
{
  void **v6; // rsi
  LSTATUS ValueW; // eax
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // ebx
  unsigned __int16 *RegValueName; // rax
  const unsigned __int16 *v16; // rcx
  void *pvData; // rax
  unsigned __int16 *v18; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-68h]
  DWORD v20[18]; // [rsp+40h] [rbp-48h] BYREF

  v6 = (void **)a6;
  v20[0] = 0;
  pcbData = 0;
  if ( !a6 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
    return 87;
  }
  *a6 = 0;
  ValueW = RegGetValueW(hkey, lpSubKey, a3, 2u, v20, 0, &pcbData);
  v14 = ValueW;
  if ( ValueW != 2 )
  {
    if ( ValueW == 1630 )
    {
      RegValueName = GetRegValueName(a3);
      v16 = L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.";
      goto LABEL_5;
    }
    if ( !ValueW || ValueW == 234 )
    {
      if ( pcbData )
      {
        pvData = MIDL_user_allocate(pcbData);
        *v6 = pvData;
        if ( !pvData )
        {
          v14 = 14;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
          goto LABEL_14;
        }
        v14 = RegGetValueW(hkey, lpSubKey, a3, 2u, v20, pvData, &pcbData);
      }
      if ( !v14 )
        return v14;
    }
LABEL_14:
    Logger::WriteRegistryFailureEvent(v14, v13, a4, a3);
    v18 = GetRegValueName(a3);
    LODWORD(pdwType) = v14;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadStringValue",
      a4,
      v18,
      pdwType);
    SafeFree(*v6);
    *v6 = 0;
    return v14;
  }
  RegValueName = GetRegValueName(a3);
  v16 = L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.";
LABEL_5:
  LODWORD(pdwType) = 2;
  Logger::TraceWarning(v16, L"RegReadStringValue", a4, RegValueName, pdwType);
  return 0;
}

```

## disassembly

```asm
0x180079b18  mov     rax, rsp
0x180079b1b  push    rbx
0x180079b1c  push    rbp
0x180079b1d  push    rsi
0x180079b1e  push    rdi
0x180079b1f  push    r14
0x180079b21  push    r15
0x180079b23  sub     rsp, 58h
0x180079b27  mov     rsi, [rsp+88h+arg_28]
0x180079b2f  mov     rbp, r9
0x180079b32  mov     dword ptr [rax-48h], 0
0x180079b39  mov     rdi, r8
0x180079b3c  mov     dword ptr [rax+28h], 0
0x180079b43  mov     r14, rdx
0x180079b46  mov     r15, rcx
0x180079b49  test    rsi, rsi
0x180079b4c  jnz     short loc_180079B70
0x180079b4e  lea     r8, aPdata; "pData"
0x180079b55  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180079b5c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180079b63  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180079b68  lea     eax, [rsi+57h]
0x180079b6b  jmp     loc_180079C95
0x180079b70  lea     rax, [rsp+88h+arg_20]
0x180079b78  mov     qword ptr [rsi], 0
0x180079b7f  mov     [rsp+88h+pcbData], rax; pcbData
0x180079b84  mov     r9d, 2; dwFlags
0x180079b8a  lea     rax, [rsp+88h+var_48]
0x180079b8f  mov     [rsp+88h+pvData], 0; pvData
0x180079b98  mov     [rsp+88h+pdwType], rax; pdwType
0x180079b9d  call    cs:__imp_RegGetValueW
0x180079ba3  mov     ebx, eax
0x180079ba5  cmp     eax, 2
0x180079ba8  jnz     short loc_180079BDA
0x180079baa  mov     rcx, rdi; unsigned __int16 *
0x180079bad  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180079bb2  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x180079bb9  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180079bc0  mov     dword ptr [rsp+88h+pdwType], 2
0x180079bc8  mov     r8, rbp
0x180079bcb  mov     r9, rax
0x180079bce  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180079bd3  xor     ebx, ebx
0x180079bd5  jmp     loc_180079C93
0x180079bda  cmp     eax, 65Eh
0x180079bdf  jnz     short loc_180079BF2
0x180079be1  mov     rcx, rdi; unsigned __int16 *
0x180079be4  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180079be9  lea     rcx, aSTheRegistryKe_4; "%s: The registry key value \"%s@%s\" is"...
0x180079bf0  jmp     short loc_180079BB9
0x180079bf2  test    eax, eax
0x180079bf4  jz      short loc_180079BFD
0x180079bf6  cmp     eax, 0EAh
0x180079bfb  jnz     short loc_180079C52
0x180079bfd  mov     eax, [rsp+88h+arg_20]
0x180079c04  test    eax, eax
0x180079c06  jz      short loc_180079C4E
0x180079c08  mov     ecx, eax; size
0x180079c0a  call    MIDL_user_allocate
0x180079c0f  mov     [rsi], rax
0x180079c12  test    rax, rax
0x180079c15  jz      loc_180079CA2
0x180079c1b  lea     rcx, [rsp+88h+arg_20]
0x180079c23  mov     r9d, 2; dwFlags
0x180079c29  mov     [rsp+88h+pcbData], rcx; pcbData
0x180079c2e  mov     r8, rdi; lpValue
0x180079c31  mov     [rsp+88h+pvData], rax; pvData
0x180079c36  mov     rdx, r14; lpSubKey
0x180079c39  lea     rax, [rsp+88h+var_48]
0x180079c3e  mov     rcx, r15; hkey
0x180079c41  mov     [rsp+88h+pdwType], rax; pdwType
0x180079c46  call    cs:__imp_RegGetValueW
0x180079c4c  mov     ebx, eax
0x180079c4e  test    ebx, ebx
0x180079c50  jz      short loc_180079C93
0x180079c52  mov     r9, rdi; unsigned __int16 *
0x180079c55  mov     r8, rbp; unsigned __int16 *
0x180079c58  mov     ecx, ebx; unsigned int
0x180079c5a  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180079c5f  mov     rcx, rdi; unsigned __int16 *
0x180079c62  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180079c67  mov     r9, rax
0x180079c6a  mov     dword ptr [rsp+88h+pdwType], ebx
0x180079c6e  mov     r8, rbp
0x180079c71  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180079c78  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x180079c7f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180079c84  mov     rcx, [rsi]; void *
0x180079c87  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180079c8c  mov     qword ptr [rsi], 0
0x180079c93  mov     eax, ebx
0x180079c95  add     rsp, 58h
0x180079c99  pop     r15
0x180079c9b  pop     r14
0x180079c9d  pop     rdi
0x180079c9e  pop     rsi
0x180079c9f  pop     rbp
0x180079ca0  pop     rbx
0x180079ca1  retn
0x180079ca2  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180079ca9  mov     ebx, 0Eh
0x180079cae  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180079cb5  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180079cba  jmp     short loc_180079C52
```
