# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x140005a8c`
- end: `0x140005afc`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `112`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012a38`

## callees

- `0x140005a8c`
- `0x14000ff44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005ac6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005ac6`

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
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(v5, v6, a1, v3);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v8, v9);
    JUMPOUT(0x140005AFBLL);
  }
  return a1;
}

```

## disassembly

```asm
0x140005a8c  mov     [rsp+arg_0], rbx
0x140005a91  push    rdi
0x140005a92  sub     rsp, 20h
0x140005a96  lea     r9, [rcx+18h]; string
0x140005a9a  xor     edi, edi
0x140005a9c  mov     [r9], rdi
0x140005a9f  mov     rbx, rcx
0x140005aa2  mov     rcx, [rdx]; sourceString
0x140005aa5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140005aa9  inc     rdx; int
0x140005aac  cmp     [rcx+rdx*2], di
0x140005ab0  jnz     short loc_140005AA9
0x140005ab2  mov     eax, 0FFFFFFFFh
0x140005ab7  cmp     rdx, rax
0x140005aba  ja      short loc_140005ADE
0x140005abc  lea     eax, [rdx+1]
0x140005abf  cmp     eax, edx
0x140005ac1  jb      short loc_140005AE9
0x140005ac3  mov     r8, rbx; hstringHeader
0x140005ac6  call    cs:__imp_WindowsCreateStringReference
0x140005acc  test    eax, eax
0x140005ace  js      short loc_140005AF4
0x140005ad0  mov     rax, rbx
0x140005ad3  mov     rbx, [rsp+28h+arg_0]
0x140005ad8  add     rsp, 20h
0x140005adc  pop     rdi
0x140005add  retn
0x140005ade  mov     ecx, 80070216h; this
0x140005ae3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140005ae8  int     3; Trap to Debugger
0x140005ae9  mov     ecx, 80070216h; this
0x140005aee  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140005af3  int     3; Trap to Debugger
0x140005af4  mov     ecx, eax; this
0x140005af6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
