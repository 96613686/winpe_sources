# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800136cc`
- end: `0x180013709`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `61`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b46c`
- `0x180017e98`
- `0x18001f080`
- `0x180023ff0`
- `0x180024100`

## callees

- `0x1800136cc`
- `0x18001b068`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800136eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800136eb`

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
0x1800136cc  sub     rsp, 28h
0x1800136d0  mov     eax, r9d
0x1800136d3  mov     r10, rdx
0x1800136d6  cmp     r9d, r8d
0x1800136d9  jb      short loc_1800136DF
0x1800136db  lea     eax, [r8-1]
0x1800136df  lea     r9, [rcx+18h]; string
0x1800136e3  mov     r8, rcx; hstringHeader
0x1800136e6  mov     rcx, r10; sourceString
0x1800136e9  mov     edx, eax; length
0x1800136eb  call    cs:__imp_WindowsCreateStringReference
0x1800136f2  nop     dword ptr [rax+rax+00h]
0x1800136f7  test    eax, eax
0x1800136f9  jns     short loc_180013703
0x1800136fb  mov     ecx, eax; this
0x1800136fd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180013702  int     3; Trap to Debugger
0x180013703  add     rsp, 28h
0x180013707  retn
```
