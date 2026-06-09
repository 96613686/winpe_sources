# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18003137c`
- end: `0x1800313ec`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `112`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031c98`

## callees

- `0x18003137c`
- `0x18003381c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800313b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800313b6`

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
    JUMPOUT(0x1800313EBLL);
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
0x18003137c  mov     [rsp+arg_0], rbx
0x180031381  push    rdi
0x180031382  sub     rsp, 20h
0x180031386  lea     r9, [rcx+18h]; string
0x18003138a  xor     edi, edi
0x18003138c  mov     [r9], rdi
0x18003138f  mov     rbx, rcx
0x180031392  mov     rcx, [rdx]; sourceString
0x180031395  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180031399  inc     rdx; int
0x18003139c  cmp     [rcx+rdx*2], di
0x1800313a0  jnz     short loc_180031399
0x1800313a2  mov     eax, 0FFFFFFFFh
0x1800313a7  cmp     rdx, rax
0x1800313aa  ja      short loc_1800313D6
0x1800313ac  lea     eax, [rdx+1]
0x1800313af  cmp     eax, edx
0x1800313b1  jb      short loc_1800313E1
0x1800313b3  mov     r8, rbx; hstringHeader
0x1800313b6  call    cs:__imp_WindowsCreateStringReference
0x1800313bc  test    eax, eax
0x1800313be  js      short loc_1800313CE
0x1800313c0  mov     rax, rbx
0x1800313c3  mov     rbx, [rsp+28h+arg_0]
0x1800313c8  add     rsp, 20h
0x1800313cc  pop     rdi
0x1800313cd  retn
0x1800313ce  mov     ecx, eax; this
0x1800313d0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800313d5  int     3; Trap to Debugger
0x1800313d6  mov     ecx, 80070216h; this
0x1800313db  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800313e0  int     3; Trap to Debugger
0x1800313e1  mov     ecx, 80070216h; this
0x1800313e6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
