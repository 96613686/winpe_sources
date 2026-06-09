# RegReadQwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,__int64 *,__int64)

- ea: `0x180086b90`
- end: `0x180086cd3`
- name: `?RegReadQwordValue@@YAKPEAUHKEY__@@PEBG11PEA_J_J@Z`
- size: `323`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800923dc`

## callees

- `0x180086570`
- `0x180086b90`
- `0x18008aa28`
- `0x18008aad8`
- `0x18008af7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086c1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086c1c`

## string_xrefs

- `0x180086cc5`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180086bcd`: `RegReadQwordValue`
- `0x180086c76`: `RegReadQwordValue`
- `0x180086cbe`: `RegReadQwordValue`
- `0x180086c35`: `%s: The registry key value "%s@%s" does not exist. Using default value %I64d. Error code: 0x%08x.`
- `0x180086c60`: `%s: The registry key value "%s@%s" is not of type QWORD. Using default value %I64d. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadQwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int64 *a5,
        __int64 pcbData)
{
  __int64 *v6; // rsi
  LSTATUS ValueW; // eax
  unsigned int v10; // ebx
  unsigned __int16 *RegValueName; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  PVOID pvData; // [rsp+28h] [rbp-50h]
  __int64 v16[7]; // [rsp+40h] [rbp-38h] BYREF
  DWORD v17; // [rsp+90h] [rbp+18h] BYREF
  int v18; // [rsp+94h] [rbp+1Ch]

  v18 = HIDWORD(a3);
  v6 = a5;
  v17 = 0;
  LODWORD(pcbData) = 8;
  v16[0] = 0;
  if ( !a5 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadQwordValue", L"pData");
    return 87;
  }
  ValueW = RegGetValueW(a1, a2, L"LastSyncTime", 0xFFFFu, &v17, v16, (LPDWORD)&pcbData);
  v10 = ValueW;
  if ( ValueW == 2 )
  {
    RegValueName = GetRegValueName(L"LastSyncTime");
    LODWORD(pvData) = 2;
    Logger::TraceWarning(
      L"%s: The registry key value \"%s@%s\" does not exist. Using default value %I64d. Error code: 0x%08x.",
      L"RegReadQwordValue",
      a4,
      RegValueName,
      0,
      pvData);
LABEL_9:
    v10 = 0;
    goto LABEL_10;
  }
  if ( ValueW == 234 )
    goto LABEL_8;
  if ( ValueW )
  {
    Logger::WriteRegistryFailureEvent(ValueW, L"RegGetValueW", a4, L"LastSyncTime");
    v13 = GetRegValueName(L"LastSyncTime");
    LODWORD(pdwType) = v10;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadQwordValue",
      a4,
      v13,
      pdwType);
    goto LABEL_10;
  }
  if ( v17 != 11 )
  {
LABEL_8:
    v12 = GetRegValueName(L"LastSyncTime");
    LODWORD(pvData) = v10;
    Logger::TraceWarning(
      L"%s: The registry key value \"%s@%s\" is not of type QWORD. Using default value %I64d. Error code: 0x%08x.",
      L"RegReadQwordValue",
      a4,
      v12,
      0,
      pvData);
    goto LABEL_9;
  }
LABEL_10:
  *v6 = v16[0];
  return v10;
}

```

## disassembly

```asm
0x180086b90  mov     rax, rsp
0x180086b93  mov     [rax+18h], r8
0x180086b97  push    rbx
0x180086b98  push    rsi
0x180086b99  push    rdi
0x180086b9a  push    r14
0x180086b9c  sub     rsp, 58h
0x180086ba0  mov     rsi, [rsp+78h+arg_20]
0x180086ba8  mov     rdi, r9
0x180086bab  mov     dword ptr [rax+18h], 0
0x180086bb2  mov     dword ptr [rax+30h], 8
0x180086bb9  mov     qword ptr [rax-38h], 0
0x180086bc1  test    rsi, rsi
0x180086bc4  jnz     short loc_180086BE8
0x180086bc6  lea     r8, aPdata; "pData"
0x180086bcd  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x180086bd4  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180086bdb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086be0  lea     eax, [rsi+57h]
0x180086be3  jmp     loc_180086C8E
0x180086be8  lea     rax, [rsp+78h+arg_28]
0x180086bf0  mov     r9d, 0FFFFh; dwFlags
0x180086bf6  mov     [rsp+78h+pcbData], rax; pcbData
0x180086bfb  lea     r14, ValueName; "LastSyncTime"
0x180086c02  lea     rax, [rsp+78h+var_38]
0x180086c07  mov     r8, r14; lpValue
0x180086c0a  mov     [rsp+78h+pvData], rax; pvData
0x180086c0f  lea     rax, [rsp+78h+arg_10]
0x180086c17  mov     [rsp+78h+pdwType], rax; pdwType
0x180086c1c  call    cs:__imp_RegGetValueW
0x180086c22  mov     ebx, eax
0x180086c24  cmp     eax, 2
0x180086c27  jnz     short loc_180086C3E
0x180086c29  mov     rcx, r14; unsigned __int16 *
0x180086c2c  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086c31  mov     dword ptr [rsp+78h+pvData], ebx
0x180086c35  lea     rcx, aSTheRegistryKe_1; "%s: The registry key value \"%s@%s\" do"...
0x180086c3c  jmp     short loc_180086C67
0x180086c3e  cmp     ebx, 0EAh
0x180086c44  jz      short loc_180086C54
0x180086c46  test    ebx, ebx
0x180086c48  jnz     short loc_180086C98
0x180086c4a  cmp     [rsp+78h+arg_10], 0Bh
0x180086c52  jz      short loc_180086C84
0x180086c54  mov     rcx, r14; unsigned __int16 *
0x180086c57  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086c5c  mov     dword ptr [rsp+78h+pvData], ebx
0x180086c60  lea     rcx, aSTheRegistryKe_3; "%s: The registry key value \"%s@%s\" is"...
0x180086c67  mov     r9, rax
0x180086c6a  mov     [rsp+78h+pdwType], 0
0x180086c73  mov     r8, rdi
0x180086c76  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x180086c7d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180086c82  xor     ebx, ebx
0x180086c84  mov     rax, [rsp+78h+var_38]
0x180086c89  mov     [rsi], rax
0x180086c8c  mov     eax, ebx
0x180086c8e  add     rsp, 58h
0x180086c92  pop     r14
0x180086c94  pop     rdi
0x180086c95  pop     rsi
0x180086c96  pop     rbx
0x180086c97  retn
0x180086c98  mov     r9, r14; unsigned __int16 *
0x180086c9b  lea     rdx, aReggetvaluew; "RegGetValueW"
0x180086ca2  mov     r8, rdi; unsigned __int16 *
0x180086ca5  mov     ecx, ebx; unsigned int
0x180086ca7  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180086cac  mov     rcx, r14; unsigned __int16 *
0x180086caf  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086cb4  mov     r9, rax
0x180086cb7  mov     dword ptr [rsp+78h+pdwType], ebx
0x180086cbb  mov     r8, rdi
0x180086cbe  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x180086cc5  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x180086ccc  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180086cd1  jmp     short loc_180086C84
```
