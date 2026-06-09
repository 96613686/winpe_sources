# Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x14003cfb0`
- end: `0x14003d020`
- name: `??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z`
- size: `112`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003bf88`
- `0x14003f590`
- `0x14003f96c`

## callees

- `0x14003cf98`
- `0x14003cfb0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003cfea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003cfea`

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
    JUMPOUT(0x14003D01FLL);
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
0x14003cfb0  mov     [rsp+arg_0], rbx
0x14003cfb5  push    rdi
0x14003cfb6  sub     rsp, 20h
0x14003cfba  lea     r9, [rcx+18h]; string
0x14003cfbe  xor     edi, edi
0x14003cfc0  mov     [r9], rdi
0x14003cfc3  mov     rbx, rcx
0x14003cfc6  mov     rcx, [rdx]; sourceString
0x14003cfc9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003cfcd  inc     rdx; int
0x14003cfd0  cmp     [rcx+rdx*2], di
0x14003cfd4  jnz     short loc_14003CFCD
0x14003cfd6  mov     eax, 0FFFFFFFFh
0x14003cfdb  cmp     rdx, rax
0x14003cfde  ja      short loc_14003D00A
0x14003cfe0  lea     eax, [rdx+1]
0x14003cfe3  cmp     eax, edx
0x14003cfe5  jb      short loc_14003D015
0x14003cfe7  mov     r8, rbx; hstringHeader
0x14003cfea  call    cs:__imp_WindowsCreateStringReference
0x14003cff0  test    eax, eax
0x14003cff2  js      short loc_14003D002
0x14003cff4  mov     rax, rbx
0x14003cff7  mov     rbx, [rsp+28h+arg_0]
0x14003cffc  add     rsp, 20h
0x14003d000  pop     rdi
0x14003d001  retn
0x14003d002  mov     ecx, eax; this
0x14003d004  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14003d009  int     3; Trap to Debugger
0x14003d00a  mov     ecx, 80070216h; this
0x14003d00f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14003d014  int     3; Trap to Debugger
0x14003d015  mov     ecx, 80070216h; this
0x14003d01a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
