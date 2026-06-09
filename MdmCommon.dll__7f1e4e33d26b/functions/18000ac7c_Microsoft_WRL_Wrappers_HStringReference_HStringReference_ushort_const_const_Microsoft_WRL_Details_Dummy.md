# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18000ac7c`
- end: `0x18000acec`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `112`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ae24`
- `0x18000ba7c`
- `0x18000c38c`
- `0x18000e97c`

## callees

- `0x18000ac7c`
- `0x180011414`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000acb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000acb6`

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
    JUMPOUT(0x18000ACEBLL);
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
0x18000ac7c  mov     [rsp+arg_0], rbx
0x18000ac81  push    rdi
0x18000ac82  sub     rsp, 20h
0x18000ac86  lea     r9, [rcx+18h]; string
0x18000ac8a  xor     edi, edi
0x18000ac8c  mov     [r9], rdi
0x18000ac8f  mov     rbx, rcx
0x18000ac92  mov     rcx, [rdx]; sourceString
0x18000ac95  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ac99  inc     rdx; int
0x18000ac9c  cmp     [rcx+rdx*2], di
0x18000aca0  jnz     short loc_18000AC99
0x18000aca2  mov     eax, 0FFFFFFFFh
0x18000aca7  cmp     rdx, rax
0x18000acaa  ja      short loc_18000ACD6
0x18000acac  lea     eax, [rdx+1]
0x18000acaf  cmp     eax, edx
0x18000acb1  jb      short loc_18000ACE1
0x18000acb3  mov     r8, rbx; hstringHeader
0x18000acb6  call    cs:__imp_WindowsCreateStringReference
0x18000acbc  test    eax, eax
0x18000acbe  js      short loc_18000ACCE
0x18000acc0  mov     rax, rbx
0x18000acc3  mov     rbx, [rsp+28h+arg_0]
0x18000acc8  add     rsp, 20h
0x18000accc  pop     rdi
0x18000accd  retn
0x18000acce  mov     ecx, eax; this
0x18000acd0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000acd5  int     3; Trap to Debugger
0x18000acd6  mov     ecx, 80070216h; this
0x18000acdb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000ace0  int     3; Trap to Debugger
0x18000ace1  mov     ecx, 80070216h; this
0x18000ace6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
