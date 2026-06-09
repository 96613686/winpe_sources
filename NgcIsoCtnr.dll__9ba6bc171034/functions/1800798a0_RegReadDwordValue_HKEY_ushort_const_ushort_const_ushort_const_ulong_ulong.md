# RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)

- ea: `0x1800798a0`
- end: `0x1800799cc`
- name: `?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z`
- size: `300`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180081084`
- `0x180081cdc`

## callees

- `0x1800794d8`
- `0x1800798a0`
- `0x18007d1b8`
- `0x18007d268`
- `0x18007d344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007991e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007991e`

## string_xrefs

- `0x1800798db`: `RegReadDwordValue`
- `0x180079977`: `RegReadDwordValue`
- `0x1800799b7`: `RegReadDwordValue`
- `0x1800799be`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180079937`: `%s: The registry key value "%s@%s" does not exist. Using default value %lu. Error code: 0x%08x.`
- `0x180079962`: `%s: The registry key value "%s@%s" is not of type DWORD. Using default value %lu. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        DWORD a6)
{
  LSTATUS ValueW; // eax
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // ebx
  unsigned __int16 *RegValueName; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  PVOID pvData; // [rsp+28h] [rbp-50h]
  unsigned int v17; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcbData[13]; // [rsp+44h] [rbp-34h] BYREF

  a6 = 0;
  v17 = 0;
  pcbData[0] = 4;
  if ( !a5 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadDwordValue", L"pData");
    return 87;
  }
  ValueW = RegGetValueW(a1, a2, a3, 0xFFFFu, &a6, &v17, pcbData);
  v11 = ValueW;
  if ( ValueW == 2 )
  {
    RegValueName = GetRegValueName(a3);
    LODWORD(pvData) = 2;
    v13 = L"%s: The registry key value \"%s@%s\" does not exist. Using default value %lu. Error code: 0x%08x.";
LABEL_9:
    LODWORD(pdwType) = 0;
    Logger::TraceWarning(v13, L"RegReadDwordValue", a4, RegValueName, pdwType, pvData);
    v11 = 0;
    goto LABEL_10;
  }
  if ( ValueW == 234 )
    goto LABEL_8;
  if ( ValueW )
  {
    Logger::WriteRegistryFailureEvent(ValueW, v10, a4, a3);
    v14 = GetRegValueName(a3);
    LODWORD(pdwType) = v11;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadDwordValue",
      a4,
      v14,
      pdwType);
    goto LABEL_10;
  }
  if ( a6 != 4 )
  {
LABEL_8:
    RegValueName = GetRegValueName(a3);
    LODWORD(pvData) = v11;
    v13 = L"%s: The registry key value \"%s@%s\" is not of type DWORD. Using default value %lu. Error code: 0x%08x.";
    goto LABEL_9;
  }
LABEL_10:
  *a5 = v17;
  return v11;
}

```

## disassembly

```asm
0x1800798a0  mov     rax, rsp
0x1800798a3  push    rbx
0x1800798a4  push    rsi
0x1800798a5  push    rdi
0x1800798a6  push    r14
0x1800798a8  sub     rsp, 58h
0x1800798ac  mov     r14, [rsp+78h+arg_20]
0x1800798b4  mov     rsi, r9
0x1800798b7  mov     dword ptr [rax+30h], 0
0x1800798be  mov     rdi, r8
0x1800798c1  mov     dword ptr [rax-38h], 0
0x1800798c8  mov     dword ptr [rax-34h], 4
0x1800798cf  test    r14, r14
0x1800798d2  jnz     short loc_1800798F7
0x1800798d4  lea     r8, aPdata; "pData"
0x1800798db  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x1800798e2  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800798e9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800798ee  lea     eax, [r14+57h]
0x1800798f2  jmp     loc_18007998E
0x1800798f7  lea     rax, [rsp+78h+var_34]
0x1800798fc  mov     r9d, 0FFFFh; dwFlags
0x180079902  mov     [rsp+78h+pcbData], rax; pcbData
0x180079907  lea     rax, [rsp+78h+var_38]
0x18007990c  mov     [rsp+78h+pvData], rax; pvData
0x180079911  lea     rax, [rsp+78h+arg_28]
0x180079919  mov     [rsp+78h+pdwType], rax; pdwType
0x18007991e  call    cs:__imp_RegGetValueW
0x180079924  mov     ebx, eax
0x180079926  cmp     eax, 2
0x180079929  jnz     short loc_180079940
0x18007992b  mov     rcx, rdi; unsigned __int16 *
0x18007992e  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180079933  mov     dword ptr [rsp+78h+pvData], ebx
0x180079937  lea     rcx, aSTheRegistryKe_2; "%s: The registry key value \"%s@%s\" do"...
0x18007993e  jmp     short loc_180079969
0x180079940  cmp     ebx, 0EAh
0x180079946  jz      short loc_180079956
0x180079948  test    ebx, ebx
0x18007994a  jnz     short loc_180079998
0x18007994c  cmp     [rsp+78h+arg_28], 4
0x180079954  jz      short loc_180079985
0x180079956  mov     rcx, rdi; unsigned __int16 *
0x180079959  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18007995e  mov     dword ptr [rsp+78h+pvData], ebx
0x180079962  lea     rcx, aSTheRegistryKe_6; "%s: The registry key value \"%s@%s\" is"...
0x180079969  mov     r9, rax
0x18007996c  mov     dword ptr [rsp+78h+pdwType], 0
0x180079974  mov     r8, rsi
0x180079977  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x18007997e  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180079983  xor     ebx, ebx
0x180079985  mov     eax, [rsp+78h+var_38]
0x180079989  mov     [r14], eax
0x18007998c  mov     eax, ebx
0x18007998e  add     rsp, 58h
0x180079992  pop     r14
0x180079994  pop     rdi
0x180079995  pop     rsi
0x180079996  pop     rbx
0x180079997  retn
0x180079998  mov     r9, rdi; unsigned __int16 *
0x18007999b  mov     r8, rsi; unsigned __int16 *
0x18007999e  mov     ecx, ebx; unsigned int
0x1800799a0  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x1800799a5  mov     rcx, rdi; unsigned __int16 *
0x1800799a8  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x1800799ad  mov     r9, rax
0x1800799b0  mov     dword ptr [rsp+78h+pdwType], ebx
0x1800799b4  mov     r8, rsi
0x1800799b7  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x1800799be  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x1800799c5  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800799ca  jmp     short loc_180079985
```
