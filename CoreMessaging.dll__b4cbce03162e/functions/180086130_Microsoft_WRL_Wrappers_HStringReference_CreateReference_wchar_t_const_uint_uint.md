# Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)

- ea: `0x180086130`
- end: `0x180086173`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180068d50`
- `0x18006ad30`
- `0x18006ae7c`
- `0x1800849a0`
- `0x1800c5680`

## callees

- `0x180086130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008616c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008616c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008614b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008614b`

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
    JUMPOUT(0x180086172LL);
  }
}

```

## disassembly

```asm
0x180086130  sub     rsp, 28h
0x180086134  mov     eax, r9d
0x180086137  mov     r10, rdx
0x18008613a  cmp     r9d, r8d
0x18008613d  jnb     short loc_18008615A
0x18008613f  lea     r9, [rcx+18h]; string
0x180086143  mov     r8, rcx; hstringHeader
0x180086146  mov     rcx, r10; sourceString
0x180086149  mov     edx, eax; length
0x18008614b  call    cs:__imp_WindowsCreateStringReference
0x180086151  test    eax, eax
0x180086153  js      short loc_180086160
0x180086155  add     rsp, 28h
0x180086159  retn
0x18008615a  lea     eax, [r8-1]
0x18008615e  jmp     short loc_18008613F
0x180086160  xor     r9d, r9d; lpArguments
0x180086163  xor     r8d, r8d; nNumberOfArguments
0x180086166  mov     ecx, eax; dwExceptionCode
0x180086168  lea     edx, [r9+1]; dwExceptionFlags
0x18008616c  call    cs:__imp_RaiseException
```
