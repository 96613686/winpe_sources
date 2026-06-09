# RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)

- ea: `0x180086a54`
- end: `0x180086b88`
- name: `?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z`
- size: `308`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800912fc`
- `0x180092364`
- `0x18009e2e0`

## callees

- `0x180086570`
- `0x180086a54`
- `0x18008aa28`
- `0x18008aad8`
- `0x18008af7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086ad6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180086ad6`

## string_xrefs

- `0x180086a93`: `RegReadDwordValue`
- `0x180086b28`: `RegReadDwordValue`
- `0x180086b73`: `RegReadDwordValue`
- `0x180086aef`: `%s: The registry key value "%s@%s" does not exist. Using default value %lu. Error code: 0x%08x.`
- `0x180086b7a`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180086b17`: `%s: The registry key value "%s@%s" is not of type DWORD. Using default value %lu. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int v7; // ebp
  LSTATUS ValueW; // eax
  unsigned int v11; // ebx
  unsigned __int16 *RegValueName; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  PVOID pvData; // [rsp+28h] [rbp-50h]
  DWORD v17; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcbData[13]; // [rsp+44h] [rbp-34h] BYREF

  v7 = a6;
  v17 = 0;
  pcbData[0] = 4;
  if ( !a5 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadDwordValue", L"pData");
    return 87;
  }
  ValueW = RegGetValueW(a1, a2, a3, 0xFFFFu, &v17, &a6, pcbData);
  v11 = ValueW;
  if ( ValueW == 2 )
  {
    RegValueName = GetRegValueName(a3);
    LODWORD(pvData) = 2;
    v13 = L"%s: The registry key value \"%s@%s\" does not exist. Using default value %lu. Error code: 0x%08x.";
LABEL_9:
    LODWORD(pdwType) = v7;
    Logger::TraceWarning(v13, L"RegReadDwordValue", a4, RegValueName, pdwType, pvData);
    v11 = 0;
    goto LABEL_10;
  }
  if ( ValueW == 234 )
    goto LABEL_8;
  if ( ValueW )
  {
    Logger::WriteRegistryFailureEvent(ValueW, L"RegGetValueW", a4, a3);
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
  if ( v17 != 4 )
  {
LABEL_8:
    RegValueName = GetRegValueName(a3);
    LODWORD(pvData) = v11;
    v13 = L"%s: The registry key value \"%s@%s\" is not of type DWORD. Using default value %lu. Error code: 0x%08x.";
    goto LABEL_9;
  }
LABEL_10:
  *a5 = a6;
  return v11;
}

```

## disassembly

```asm
0x180086a54  mov     rax, rsp
0x180086a57  push    rbx
0x180086a58  push    rbp
0x180086a59  push    rsi
0x180086a5a  push    rdi
0x180086a5b  push    r14
0x180086a5d  sub     rsp, 50h
0x180086a61  mov     r14, [rsp+78h+arg_20]
0x180086a69  mov     rsi, r9
0x180086a6c  mov     ebp, [rsp+78h+arg_28]
0x180086a73  mov     rdi, r8
0x180086a76  mov     dword ptr [rax-38h], 0
0x180086a7d  mov     [rax+30h], ebp
0x180086a80  mov     dword ptr [rax-34h], 4
0x180086a87  test    r14, r14
0x180086a8a  jnz     short loc_180086AAF
0x180086a8c  lea     r8, aPdata; "pData"
0x180086a93  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x180086a9a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180086aa1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180086aa6  lea     eax, [r14+57h]
0x180086aaa  jmp     loc_180086B42
0x180086aaf  lea     rax, [rsp+78h+var_34]
0x180086ab4  mov     r9d, 0FFFFh; dwFlags
0x180086aba  mov     [rsp+78h+pcbData], rax; pcbData
0x180086abf  lea     rax, [rsp+78h+arg_28]
0x180086ac7  mov     [rsp+78h+pvData], rax; pvData
0x180086acc  lea     rax, [rsp+78h+var_38]
0x180086ad1  mov     [rsp+78h+pdwType], rax; pdwType
0x180086ad6  call    cs:__imp_RegGetValueW
0x180086adc  mov     ebx, eax
0x180086ade  cmp     eax, 2
0x180086ae1  jnz     short loc_180086AF8
0x180086ae3  mov     rcx, rdi; unsigned __int16 *
0x180086ae6  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086aeb  mov     dword ptr [rsp+78h+pvData], ebx
0x180086aef  lea     rcx, aSTheRegistryKe_2; "%s: The registry key value \"%s@%s\" do"...
0x180086af6  jmp     short loc_180086B1E
0x180086af8  cmp     ebx, 0EAh
0x180086afe  jz      short loc_180086B0B
0x180086b00  test    ebx, ebx
0x180086b02  jnz     short loc_180086B4D
0x180086b04  cmp     [rsp+78h+var_38], 4
0x180086b09  jz      short loc_180086B36
0x180086b0b  mov     rcx, rdi; unsigned __int16 *
0x180086b0e  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086b13  mov     dword ptr [rsp+78h+pvData], ebx
0x180086b17  lea     rcx, aSTheRegistryKe_6; "%s: The registry key value \"%s@%s\" is"...
0x180086b1e  mov     r9, rax
0x180086b21  mov     dword ptr [rsp+78h+pdwType], ebp
0x180086b25  mov     r8, rsi
0x180086b28  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x180086b2f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180086b34  xor     ebx, ebx
0x180086b36  mov     eax, [rsp+78h+arg_28]
0x180086b3d  mov     [r14], eax
0x180086b40  mov     eax, ebx
0x180086b42  add     rsp, 50h
0x180086b46  pop     r14
0x180086b48  pop     rdi
0x180086b49  pop     rsi
0x180086b4a  pop     rbp
0x180086b4b  pop     rbx
0x180086b4c  retn
0x180086b4d  mov     r9, rdi; unsigned __int16 *
0x180086b50  lea     rdx, aReggetvaluew; "RegGetValueW"
0x180086b57  mov     r8, rsi; unsigned __int16 *
0x180086b5a  mov     ecx, ebx; unsigned int
0x180086b5c  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180086b61  mov     rcx, rdi; unsigned __int16 *
0x180086b64  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x180086b69  mov     r9, rax
0x180086b6c  mov     dword ptr [rsp+78h+pdwType], ebx
0x180086b70  mov     r8, rsi
0x180086b73  lea     rdx, aRegreaddwordva; "RegReadDwordValue"
0x180086b7a  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x180086b81  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180086b86  jmp     short loc_180086B36
```
