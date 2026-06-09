# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18006fc00`
- end: `0x18006fc3d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `61`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006ed58`
- `0x1800704a0`
- `0x1800717f0`
- `0x1800759c0`

## callees

- `0x18006fc00`
- `0x1800724d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fc1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fc1f`

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
  int v6; // edx
  unsigned int v7; // r8d

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v6, v7);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18006fc00  sub     rsp, 28h
0x18006fc04  mov     eax, r9d
0x18006fc07  mov     r10, rdx
0x18006fc0a  cmp     r9d, r8d
0x18006fc0d  jb      short loc_18006FC13
0x18006fc0f  lea     eax, [r8-1]
0x18006fc13  lea     r9, [rcx+18h]; string
0x18006fc17  mov     r8, rcx; hstringHeader
0x18006fc1a  mov     rcx, r10; sourceString
0x18006fc1d  mov     edx, eax; length
0x18006fc1f  call    cs:__imp_WindowsCreateStringReference
0x18006fc26  nop     dword ptr [rax+rax+00h]
0x18006fc2b  test    eax, eax
0x18006fc2d  jns     short loc_18006FC37
0x18006fc2f  mov     ecx, eax; this
0x18006fc31  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006fc36  int     3; Trap to Debugger
0x18006fc37  add     rsp, 28h
0x18006fc3b  retn
```
