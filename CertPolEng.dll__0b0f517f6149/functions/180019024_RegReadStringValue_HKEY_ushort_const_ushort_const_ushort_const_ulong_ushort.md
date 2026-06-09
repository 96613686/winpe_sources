# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180019024`
- end: `0x1800191c8`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `420`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, DWORD pcbData, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018f50`

## callees

- `0x1800088f0`
- `0x18000b3c4`
- `0x18000ca74`
- `0x180019024`
- `0x1800191d0`
- `0x180019bd8`
- `0x180019c4c`
- `0x180019c88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800190a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019152`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800190a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019152`

## string_xrefs

- `0x180019184`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x1800190be`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x180019061`: `RegReadStringValue`
- `0x1800190c5`: `RegReadStringValue`
- `0x18001917d`: `RegReadStringValue`
- `0x1800191ae`: `RegReadStringValue`
- `0x1800190f5`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`

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
    Logger::TraceError((const unsigned __int16 *)&stru_18001E5B8.hCertStore, L"RegReadStringValue", L"pData");
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
        pvData = SafeAlloc(pcbData);
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
0x180019024  mov     rax, rsp
0x180019027  push    rbx
0x180019028  push    rbp
0x180019029  push    rsi
0x18001902a  push    rdi
0x18001902b  push    r14
0x18001902d  push    r15
0x18001902f  sub     rsp, 58h
0x180019033  mov     rsi, [rsp+88h+arg_28]
0x18001903b  mov     rbp, r9
0x18001903e  mov     dword ptr [rax-48h], 0
0x180019045  mov     rdi, r8
0x180019048  mov     dword ptr [rax+28h], 0
0x18001904f  mov     r14, rdx
0x180019052  mov     r15, rcx
0x180019055  test    rsi, rsi
0x180019058  jnz     short loc_18001907C
0x18001905a  lea     r8, aPdata; "pData"
0x180019061  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180019068  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x18001906f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180019074  lea     eax, [rsi+57h]
0x180019077  jmp     loc_1800191A1
0x18001907c  lea     rax, [rsp+88h+arg_20]
0x180019084  mov     qword ptr [rsi], 0
0x18001908b  mov     [rsp+88h+pcbData], rax; pcbData
0x180019090  mov     r9d, 2; dwFlags
0x180019096  lea     rax, [rsp+88h+var_48]
0x18001909b  mov     [rsp+88h+pvData], 0; pvData
0x1800190a4  mov     [rsp+88h+pdwType], rax; pdwType
0x1800190a9  call    cs:__imp_RegGetValueW
0x1800190af  mov     ebx, eax
0x1800190b1  cmp     eax, 2
0x1800190b4  jnz     short loc_1800190E6
0x1800190b6  mov     rcx, rdi; unsigned __int16 *
0x1800190b9  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x1800190be  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x1800190c5  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800190cc  mov     dword ptr [rsp+88h+pdwType], 2
0x1800190d4  mov     r8, rbp
0x1800190d7  mov     r9, rax
0x1800190da  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800190df  xor     ebx, ebx
0x1800190e1  jmp     loc_18001919F
0x1800190e6  cmp     eax, 65Eh
0x1800190eb  jnz     short loc_1800190FE
0x1800190ed  mov     rcx, rdi; unsigned __int16 *
0x1800190f0  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x1800190f5  lea     rcx, aSTheRegistryKe_0; "%s: The registry key value \"%s@%s\" is"...
0x1800190fc  jmp     short loc_1800190C5
0x1800190fe  test    eax, eax
0x180019100  jz      short loc_180019109
0x180019102  cmp     eax, 0EAh
0x180019107  jnz     short loc_18001915E
0x180019109  mov     eax, [rsp+88h+arg_20]
0x180019110  test    eax, eax
0x180019112  jz      short loc_18001915A
0x180019114  mov     ecx, eax; unsigned __int64
0x180019116  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18001911b  mov     [rsi], rax
0x18001911e  test    rax, rax
0x180019121  jz      loc_1800191AE
0x180019127  lea     rcx, [rsp+88h+arg_20]
0x18001912f  mov     r9d, 2; dwFlags
0x180019135  mov     [rsp+88h+pcbData], rcx; pcbData
0x18001913a  mov     r8, rdi; lpValue
0x18001913d  mov     [rsp+88h+pvData], rax; pvData
0x180019142  mov     rdx, r14; lpSubKey
0x180019145  lea     rax, [rsp+88h+var_48]
0x18001914a  mov     rcx, r15; hkey
0x18001914d  mov     [rsp+88h+pdwType], rax; pdwType
0x180019152  call    cs:__imp_RegGetValueW
0x180019158  mov     ebx, eax
0x18001915a  test    ebx, ebx
0x18001915c  jz      short loc_18001919F
0x18001915e  mov     r9, rdi; unsigned __int16 *
0x180019161  mov     r8, rbp; unsigned __int16 *
0x180019164  mov     ecx, ebx; unsigned int
0x180019166  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18001916b  mov     rcx, rdi; unsigned __int16 *
0x18001916e  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180019173  mov     r9, rax
0x180019176  mov     dword ptr [rsp+88h+pdwType], ebx
0x18001917a  mov     r8, rbp
0x18001917d  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x180019184  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18001918b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180019190  mov     rcx, [rsi]; void *
0x180019193  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180019198  mov     qword ptr [rsi], 0
0x18001919f  mov     eax, ebx
0x1800191a1  add     rsp, 58h
0x1800191a5  pop     r15
0x1800191a7  pop     r14
0x1800191a9  pop     rdi
0x1800191aa  pop     rsi
0x1800191ab  pop     rbp
0x1800191ac  pop     rbx
0x1800191ad  retn
0x1800191ae  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x1800191b5  mov     ebx, 0Eh
0x1800191ba  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800191c1  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800191c6  jmp     short loc_18001915E
```
