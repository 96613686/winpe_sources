# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18002a0b0`
- end: `0x18002a2c4`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `532`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, SIZE_T dwBytes, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180016560`
- `0x18001a130`
- `0x1800aae48`
- `0x1800ac598`

## callees

- `0x1800215e4`
- `0x18002a0b0`
- `0x18004aa08`
- `0x18004ccd8`
- `0x18004d79c`
- `0x180052938`
- `0x1800ab8ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a13a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a13a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a14b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a14b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a109`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a188`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a109`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a188`

## string_xrefs

- `0x18002a1de`: `RegReadStringValue`
- `0x18002a20c`: `RegReadStringValue`
- `0x18002a22e`: `RegReadStringValue`
- `0x18002a26a`: `RegReadStringValue`
- `0x18002a2a1`: `RegReadStringValue`
- `0x18002a1e5`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18002a213`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18002a2a8`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadStringValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        SIZE_T dwBytes,
        unsigned __int16 **a6)
{
  void **v6; // rdi
  LSTATUS ValueW; // eax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rax
  BOOL v18; // eax
  const wchar_t *v19; // r9
  unsigned __int16 *RegValueName; // rax
  unsigned __int16 *v21; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-68h]
  DWORD v23[18]; // [rsp+40h] [rbp-48h] BYREF

  v6 = (void **)a6;
  v23[0] = 0;
  LODWORD(dwBytes) = 0;
  if ( a6 )
  {
    *a6 = 0;
    ValueW = RegGetValueW(hkey, lpSubKey, a3, 2u, v23, 0, (LPDWORD)&dwBytes);
    v13 = ValueW;
    switch ( ValueW )
    {
      case 2:
        RegValueName = GetRegValueName(a3);
        LODWORD(pdwType) = 2;
        Logger::TraceWarning(
          L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
          L"RegReadStringValue",
          a4,
          RegValueName,
          pdwType);
        return 0;
      case 1630:
        v18 = !a3 || !*a3;
        LODWORD(pdwType) = 2;
        v19 = L"(default)";
        if ( !v18 )
          v19 = a3;
        Logger::TraceWarning(
          L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
          L"RegReadStringValue",
          a4,
          v19,
          pdwType);
        return 0;
      case 0:
      case 234:
        if ( (_DWORD)dwBytes )
        {
          v14 = dwBytes;
          ProcessHeap = GetProcessHeap();
          pvData = HeapAlloc(ProcessHeap, 8u, v14);
          *v6 = pvData;
          if ( !pvData )
          {
            v13 = 14;
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
            break;
          }
          v13 = RegGetValueW(hkey, lpSubKey, a3, 2u, v23, pvData, (LPDWORD)&dwBytes);
        }
        if ( !v13 )
          return v13;
        break;
    }
    Logger::WriteRegistryFailureEvent(v13, v12, a4, a3);
    v21 = GetRegValueName(a3);
    LODWORD(pdwType) = v13;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadStringValue",
      a4,
      v21,
      pdwType);
    SafeFree(*v6);
    *v6 = 0;
    return v13;
  }
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
  return 87;
}

```

## disassembly

```asm
0x18002a0b0  mov     r11, rsp
0x18002a0b3  push    rbp
0x18002a0b4  push    rsi
0x18002a0b5  push    rdi
0x18002a0b6  push    r12
0x18002a0b8  push    r14
0x18002a0ba  push    r15
0x18002a0bc  sub     rsp, 58h
0x18002a0c0  mov     rdi, [rsp+88h+arg_28]
0x18002a0c8  xor     r12d, r12d
0x18002a0cb  mov     [r11-48h], r12d
0x18002a0cf  mov     r15, r9
0x18002a0d2  mov     [r11+28h], r12d
0x18002a0d6  mov     rsi, r8
0x18002a0d9  mov     rbp, rdx
0x18002a0dc  mov     r14, rcx
0x18002a0df  test    rdi, rdi
0x18002a0e2  jz      loc_18002A227
0x18002a0e8  lea     rax, [r11+28h]
0x18002a0ec  mov     [r11+8], rbx
0x18002a0f0  mov     [r11-58h], rax
0x18002a0f4  mov     r9d, 2; dwFlags
0x18002a0fa  lea     rax, [r11-48h]
0x18002a0fe  mov     [r11-60h], r12
0x18002a102  mov     [r11-68h], rax
0x18002a106  mov     [rdi], r12
0x18002a109  call    cs:__imp_RegGetValueW
0x18002a10f  mov     ebx, eax
0x18002a111  cmp     eax, 2
0x18002a114  jz      loc_18002A1F6
0x18002a11a  cmp     eax, 65Eh
0x18002a11f  jz      loc_18002A1B0
0x18002a125  test    eax, eax
0x18002a127  jnz     loc_18002A25E
0x18002a12d  mov     eax, dword ptr [rsp+88h+dwBytes]
0x18002a134  test    eax, eax
0x18002a136  jz      short loc_18002A190
0x18002a138  mov     ebx, eax
0x18002a13a  call    cs:__imp_GetProcessHeap
0x18002a140  mov     r8d, ebx; dwBytes
0x18002a143  mov     edx, 8; dwFlags
0x18002a148  mov     rcx, rax; hHeap
0x18002a14b  call    cs:__imp_HeapAlloc
0x18002a151  mov     [rdi], rax
0x18002a154  test    rax, rax
0x18002a157  jz      loc_18002A26A
0x18002a15d  lea     rcx, [rsp+88h+dwBytes]
0x18002a165  mov     r9d, 2; dwFlags
0x18002a16b  mov     [rsp+88h+pcbData], rcx; pcbData
0x18002a170  mov     r8, rsi; lpValue
0x18002a173  mov     [rsp+88h+pvData], rax; pvData
0x18002a178  mov     rdx, rbp; lpSubKey
0x18002a17b  lea     rax, [rsp+88h+var_48]
0x18002a180  mov     rcx, r14; hkey
0x18002a183  mov     [rsp+88h+pdwType], rax; pdwType
0x18002a188  call    cs:__imp_RegGetValueW
0x18002a18e  mov     ebx, eax
0x18002a190  test    ebx, ebx
0x18002a192  jnz     loc_18002A282
0x18002a198  mov     eax, ebx
0x18002a19a  mov     rbx, [rsp+88h+arg_0]
0x18002a1a2  add     rsp, 58h
0x18002a1a6  pop     r15
0x18002a1a8  pop     r14
0x18002a1aa  pop     r12
0x18002a1ac  pop     rdi
0x18002a1ad  pop     rsi
0x18002a1ae  pop     rbp
0x18002a1af  retn
0x18002a1b0  test    rsi, rsi
0x18002a1b3  jz      loc_18002A254
0x18002a1b9  cmp     [rsi], r12w
0x18002a1bd  jz      loc_18002A254
0x18002a1c3  mov     eax, r12d
0x18002a1c6  test    eax, eax
0x18002a1c8  mov     dword ptr [rsp+88h+pdwType], 2
0x18002a1d0  lea     r9, aDefault; "(default)"
0x18002a1d7  mov     r8, r15
0x18002a1da  cmovz   r9, rsi
0x18002a1de  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18002a1e5  lea     rcx, aSTheRegistryKe_4; "%s: The registry key value \"%s@%s\" is"...
0x18002a1ec  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002a1f1  mov     ebx, r12d
0x18002a1f4  jmp     short loc_18002A198
0x18002a1f6  mov     rcx, rsi; unsigned __int16 *
0x18002a1f9  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18002a1fe  mov     r9, rax
0x18002a201  mov     dword ptr [rsp+88h+pdwType], 2
0x18002a209  mov     r8, r15
0x18002a20c  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18002a213  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18002a21a  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002a21f  mov     ebx, r12d
0x18002a222  jmp     loc_18002A198
0x18002a227  lea     r8, aPdata; "pData"
0x18002a22e  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18002a235  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002a23c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002a241  mov     eax, 57h ; 'W'
0x18002a246  add     rsp, 58h
0x18002a24a  pop     r15
0x18002a24c  pop     r14
0x18002a24e  pop     r12
0x18002a250  pop     rdi
0x18002a251  pop     rsi
0x18002a252  pop     rbp
0x18002a253  retn
0x18002a254  mov     eax, 1
0x18002a259  jmp     loc_18002A1C6
0x18002a25e  cmp     eax, 0EAh
0x18002a263  jnz     short loc_18002A282
0x18002a265  jmp     loc_18002A12D
0x18002a26a  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18002a271  mov     ebx, 0Eh
0x18002a276  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18002a27d  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18002a282  mov     r9, rsi; unsigned __int16 *
0x18002a285  mov     r8, r15; unsigned __int16 *
0x18002a288  mov     ecx, ebx; unsigned int
0x18002a28a  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18002a28f  mov     rcx, rsi; unsigned __int16 *
0x18002a292  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18002a297  mov     r9, rax
0x18002a29a  mov     dword ptr [rsp+88h+pdwType], ebx
0x18002a29e  mov     r8, r15
0x18002a2a1  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18002a2a8  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18002a2af  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002a2b4  mov     rcx, [rdi]; void *
0x18002a2b7  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002a2bc  mov     [rdi], r12
0x18002a2bf  jmp     loc_18002A198
```
