# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800180a8`
- end: `0x180018118`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `112`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018430`
- `0x18001891c`
- `0x18001bcf8`
- `0x18001e7b4`
- `0x18001ea04`
- `0x18001eee0`
- `0x180022d84`

## callees

- `0x18000ec40`
- `0x1800180a8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800180e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800180e2`

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
    JUMPOUT(0x180018117LL);
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
0x1800180a8  mov     [rsp+arg_0], rbx
0x1800180ad  push    rdi
0x1800180ae  sub     rsp, 20h
0x1800180b2  lea     r9, [rcx+18h]; string
0x1800180b6  xor     edi, edi
0x1800180b8  mov     [r9], rdi
0x1800180bb  mov     rbx, rcx
0x1800180be  mov     rcx, [rdx]; sourceString
0x1800180c1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800180c5  inc     rdx; int
0x1800180c8  cmp     [rcx+rdx*2], di
0x1800180cc  jnz     short loc_1800180C5
0x1800180ce  mov     eax, 0FFFFFFFFh
0x1800180d3  cmp     rdx, rax
0x1800180d6  ja      short loc_180018102
0x1800180d8  lea     eax, [rdx+1]
0x1800180db  cmp     eax, edx
0x1800180dd  jb      short loc_18001810D
0x1800180df  mov     r8, rbx; hstringHeader
0x1800180e2  call    cs:__imp_WindowsCreateStringReference
0x1800180e8  test    eax, eax
0x1800180ea  js      short loc_1800180FA
0x1800180ec  mov     rax, rbx
0x1800180ef  mov     rbx, [rsp+28h+arg_0]
0x1800180f4  add     rsp, 20h
0x1800180f8  pop     rdi
0x1800180f9  retn
0x1800180fa  mov     ecx, eax; this
0x1800180fc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180018101  int     3; Trap to Debugger
0x180018102  mov     ecx, 80070216h; this
0x180018107  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001810c  int     3; Trap to Debugger
0x18001810d  mov     ecx, 80070216h; this
0x180018112  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
