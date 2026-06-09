# RegReadQwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,__int64 *,__int64)

- ea: `0x1800799d4`
- end: `0x180079b10`
- name: `?RegReadQwordValue@@YAKPEAUHKEY__@@PEBG11PEA_J_J@Z`
- size: `316`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180081d48`

## callees

- `0x1800794d8`
- `0x1800799d4`
- `0x18007d1b8`
- `0x18007d268`
- `0x18007d344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079a60`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180079a60`

## string_xrefs

- `0x180079b02`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180079aa4`: `%s: The registry key value "%s@%s" is not of type QWORD. Using default value %I64d. Error code: 0x%08x.`
- `0x180079a11`: `RegReadQwordValue`
- `0x180079aba`: `RegReadQwordValue`
- `0x180079afb`: `RegReadQwordValue`
- `0x180079a79`: `%s: The registry key value "%s@%s" does not exist. Using default value %I64d. Error code: 0x%08x.`

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
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // ebx
  unsigned __int16 *RegValueName; // rax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  PVOID pvData; // [rsp+28h] [rbp-50h]
  __int64 v17[7]; // [rsp+40h] [rbp-38h] BYREF
  DWORD v18; // [rsp+90h] [rbp+18h] BYREF
  int v19; // [rsp+94h] [rbp+1Ch]

  v19 = HIDWORD(a3);
  v6 = a5;
  v18 = 0;
  LODWORD(pcbData) = 8;
  v17[0] = 0;
  if ( !a5 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadQwordValue", L"pData");
    return 87;
  }
  ValueW = RegGetValueW(a1, a2, L"LastSyncTime", 0xFFFFu, &v18, v17, (LPDWORD)&pcbData);
  v11 = ValueW;
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
    v11 = 0;
    goto LABEL_10;
  }
  if ( ValueW == 234 )
    goto LABEL_8;
  if ( ValueW )
  {
    Logger::WriteRegistryFailureEvent(ValueW, v10, a4, L"LastSyncTime");
    v14 = GetRegValueName(L"LastSyncTime");
    LODWORD(pdwType) = v11;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadQwordValue",
      a4,
      v14,
      pdwType);
    goto LABEL_10;
  }
  if ( v18 != 11 )
  {
LABEL_8:
    v13 = GetRegValueName(L"LastSyncTime");
    LODWORD(pvData) = v11;
    Logger::TraceWarning(
      L"%s: The registry key value \"%s@%s\" is not of type QWORD. Using default value %I64d. Error code: 0x%08x.",
      L"RegReadQwordValue",
      a4,
      v13,
      0,
      pvData);
    goto LABEL_9;
  }
LABEL_10:
  *v6 = v17[0];
  return v11;
}

```

## disassembly

```asm
0x1800799d4  mov     rax, rsp
0x1800799d7  mov     [rax+18h], r8
0x1800799db  push    rbx
0x1800799dc  push    rsi
0x1800799dd  push    rdi
0x1800799de  push    r14
0x1800799e0  sub     rsp, 58h
0x1800799e4  mov     rsi, [rsp+78h+arg_20]
0x1800799ec  mov     rdi, r9
0x1800799ef  mov     dword ptr [rax+18h], 0
0x1800799f6  mov     dword ptr [rax+30h], 8
0x1800799fd  mov     qword ptr [rax-38h], 0
0x180079a05  test    rsi, rsi
0x180079a08  jnz     short loc_180079A2C
0x180079a0a  lea     r8, aPdata; "pData"
0x180079a11  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x180079a18  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180079a1f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180079a24  lea     eax, [rsi+57h]
0x180079a27  jmp     loc_180079AD2
0x180079a2c  lea     rax, [rsp+78h+arg_28]
0x180079a34  mov     r9d, 0FFFFh; dwFlags
0x180079a3a  mov     [rsp+78h+pcbData], rax; pcbData
0x180079a3f  lea     r14, aLastsynctime; "LastSyncTime"
0x180079a46  lea     rax, [rsp+78h+var_38]
0x180079a4b  mov     r8, r14; lpValue
0x180079a4e  mov     [rsp+78h+pvData], rax; pvData
0x180079a53  lea     rax, [rsp+78h+arg_10]
0x180079a5b  mov     [rsp+78h+pdwType], rax; pdwType
0x180079a60  call    cs:__imp_RegGetValueW
0x180079a66  mov     ebx, eax
0x180079a68  cmp     eax, 2
0x180079a6b  jnz     short loc_180079A82
0x180079a6d  mov     rcx, r14; unsigned __int16 *
0x180079a70  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180079a75  mov     dword ptr [rsp+78h+pvData], ebx
0x180079a79  lea     rcx, aSTheRegistryKe_1; "%s: The registry key value \"%s@%s\" do"...
0x180079a80  jmp     short loc_180079AAB
0x180079a82  cmp     ebx, 0EAh
0x180079a88  jz      short loc_180079A98
0x180079a8a  test    ebx, ebx
0x180079a8c  jnz     short loc_180079ADC
0x180079a8e  cmp     [rsp+78h+arg_10], 0Bh
0x180079a96  jz      short loc_180079AC8
0x180079a98  mov     rcx, r14; unsigned __int16 *
0x180079a9b  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180079aa0  mov     dword ptr [rsp+78h+pvData], ebx
0x180079aa4  lea     rcx, aSTheRegistryKe_3; "%s: The registry key value \"%s@%s\" is"...
0x180079aab  mov     r9, rax
0x180079aae  mov     [rsp+78h+pdwType], 0
0x180079ab7  mov     r8, rdi
0x180079aba  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x180079ac1  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180079ac6  xor     ebx, ebx
0x180079ac8  mov     rax, [rsp+78h+var_38]
0x180079acd  mov     [rsi], rax
0x180079ad0  mov     eax, ebx
0x180079ad2  add     rsp, 58h
0x180079ad6  pop     r14
0x180079ad8  pop     rdi
0x180079ad9  pop     rsi
0x180079ada  pop     rbx
0x180079adb  retn
0x180079adc  mov     r9, r14; unsigned __int16 *
0x180079adf  mov     r8, rdi; unsigned __int16 *
0x180079ae2  mov     ecx, ebx; unsigned int
0x180079ae4  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180079ae9  mov     rcx, r14; unsigned __int16 *
0x180079aec  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180079af1  mov     r9, rax
0x180079af4  mov     dword ptr [rsp+78h+pdwType], ebx
0x180079af8  mov     r8, rdi
0x180079afb  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x180079b02  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x180079b09  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180079b0e  jmp     short loc_180079AC8
```
