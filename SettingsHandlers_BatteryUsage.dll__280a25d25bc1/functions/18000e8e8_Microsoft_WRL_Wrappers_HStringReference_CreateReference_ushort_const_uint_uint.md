# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000e8e8`
- end: `0x18000e929`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c990`
- `0x18000f320`
- `0x180011224`
- `0x180011cb8`
- `0x180017074`
- `0x180036f90`
- `0x180045528`
- `0x18004568c`
- `0x1800462a0`
- `0x18004640c`
- `0x1800516f8`

## callees

- `0x18000e8e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e91d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e91d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e907`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  HRESULT StringReference; // eax

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18000e8e8  sub     rsp, 28h
0x18000e8ec  mov     eax, r9d
0x18000e8ef  mov     r10, rdx
0x18000e8f2  cmp     r9d, r8d
0x18000e8f5  jb      short loc_18000E8FB
0x18000e8f7  lea     eax, [r8-1]
0x18000e8fb  lea     r9, [rcx+18h]; string
0x18000e8ff  mov     r8, rcx; hstringHeader
0x18000e902  mov     rcx, r10; sourceString
0x18000e905  mov     edx, eax; length
0x18000e907  call    cs:__imp_WindowsCreateStringReference
0x18000e90d  test    eax, eax
0x18000e90f  jns     short loc_18000E924
0x18000e911  xor     r9d, r9d; lpArguments
0x18000e914  xor     r8d, r8d; nNumberOfArguments
0x18000e917  mov     ecx, eax; dwExceptionCode
0x18000e919  lea     edx, [r9+1]; dwExceptionFlags
0x18000e91d  call    cs:__imp_RaiseException
0x18000e923  int     3; Trap to Debugger
0x18000e924  add     rsp, 28h
0x18000e928  retn
```
