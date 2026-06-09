# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[21])

- ea: `0x18000aea4`
- end: `0x18000af1c`
- name: `??$?0$0BF@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BF@G@Z`
- size: `120`
- prototype: `__int64 __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f3b8`

## callees

- `0x18000aea4`
- `0x1800117e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000aedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000aedf`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        unsigned int a3)
{
  unsigned __int64 v5; // rdx
  HRESULT StringReference; // eax
  int v7; // edx
  unsigned int v8; // r8d

  v5 = -1;
  do
    ++v5;
  while ( sourceString[v5] );
  if ( v5 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, a3);
    __debugbreak();
  }
  if ( (int)v5 + 1 < (unsigned int)v5 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, a3);
    JUMPOUT(0x18000AF1BLL);
  }
  StringReference = WindowsCreateStringReference(sourceString, v5, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v7, v8);
    __debugbreak();
  }
  return hstringHeader;
}

```

## disassembly

```asm
0x18000aea4  mov     [rsp+arg_0], rbx
0x18000aea9  push    rdi
0x18000aeaa  sub     rsp, 20h
0x18000aeae  mov     r10, rdx
0x18000aeb1  mov     rbx, rcx
0x18000aeb4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000aeb8  xor     edi, edi
0x18000aeba  inc     rdx; int
0x18000aebd  cmp     [r10+rdx*2], di
0x18000aec2  jnz     short loc_18000AEBA
0x18000aec4  mov     eax, 0FFFFFFFFh
0x18000aec9  cmp     rdx, rax
0x18000aecc  ja      short loc_18000AF06
0x18000aece  lea     eax, [rdx+1]
0x18000aed1  cmp     eax, edx
0x18000aed3  jb      short loc_18000AF11
0x18000aed5  lea     r9, [rcx+18h]; string
0x18000aed9  mov     r8, rbx; hstringHeader
0x18000aedc  mov     rcx, r10; sourceString
0x18000aedf  call    cs:__imp_WindowsCreateStringReference
0x18000aee6  nop     dword ptr [rax+rax+00h]
0x18000aeeb  test    eax, eax
0x18000aeed  js      short loc_18000AEFE
0x18000aeef  mov     rax, rbx
0x18000aef2  mov     rbx, [rsp+28h+arg_0]
0x18000aef7  add     rsp, 20h
0x18000aefb  pop     rdi
0x18000aefc  retn
0x18000aefe  mov     ecx, eax; this
0x18000af00  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000af05  int     3; Trap to Debugger
0x18000af06  mov     ecx, 80070216h; this
0x18000af0b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000af10  int     3; Trap to Debugger
0x18000af11  mov     ecx, 80070216h; this
0x18000af16  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
