# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800185f8`
- end: `0x18001866f`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `119`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800189a4`
- `0x180018ed0`
- `0x18001c448`
- `0x18001f030`
- `0x18001f28c`
- `0x18001f774`
- `0x1800238cc`

## callees

- `0x18000ed44`
- `0x1800185f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018632`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2,
        unsigned int a3)
{
  HSTRING *v3; // r9
  const WCHAR *v5; // rcx
  unsigned __int64 v6; // rdx
  HRESULT StringReference; // eax
  int v8; // edx
  unsigned int v9; // r8d

  v3 = (HSTRING *)&a1[1];
  a1[1].Reserved.Reserved1 = 0;
  v5 = *a2;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    __debugbreak();
  }
  if ( (int)v6 + 1 < (unsigned int)v6 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    JUMPOUT(0x18001866ELL);
  }
  StringReference = WindowsCreateStringReference(v5, v6, a1, v3);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v8, v9);
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x1800185f8  mov     [rsp+arg_0], rbx
0x1800185fd  push    rdi
0x1800185fe  sub     rsp, 20h
0x180018602  lea     r9, [rcx+18h]; string
0x180018606  xor     edi, edi
0x180018608  mov     [r9], rdi
0x18001860b  mov     rbx, rcx
0x18001860e  mov     rcx, [rdx]; sourceString
0x180018611  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180018615  inc     rdx; int
0x180018618  cmp     [rcx+rdx*2], di
0x18001861c  jnz     short loc_180018615
0x18001861e  mov     eax, 0FFFFFFFFh
0x180018623  cmp     rdx, rax
0x180018626  ja      short loc_180018659
0x180018628  lea     eax, [rdx+1]
0x18001862b  cmp     eax, edx
0x18001862d  jb      short loc_180018664
0x18001862f  mov     r8, rbx; hstringHeader
0x180018632  call    cs:__imp_WindowsCreateStringReference
0x180018639  nop     dword ptr [rax+rax+00h]
0x18001863e  test    eax, eax
0x180018640  js      short loc_180018651
0x180018642  mov     rax, rbx
0x180018645  mov     rbx, [rsp+28h+arg_0]
0x18001864a  add     rsp, 20h
0x18001864e  pop     rdi
0x18001864f  retn
0x180018651  mov     ecx, eax; this
0x180018653  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180018658  int     3; Trap to Debugger
0x180018659  mov     ecx, 80070216h; this
0x18001865e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180018663  int     3; Trap to Debugger
0x180018664  mov     ecx, 80070216h; this
0x180018669  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
