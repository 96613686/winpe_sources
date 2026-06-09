# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18002ce54`
- end: `0x18002cec4`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `112`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d050`
- `0x18002f2bc`
- `0x1800322d8`
- `0x180034270`

## callees

- `0x18002ce54`
- `0x18002fbb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ce8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ce8e`

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
    JUMPOUT(0x18002CEC3LL);
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
0x18002ce54  mov     [rsp+arg_0], rbx
0x18002ce59  push    rdi
0x18002ce5a  sub     rsp, 20h
0x18002ce5e  lea     r9, [rcx+18h]; string
0x18002ce62  xor     edi, edi
0x18002ce64  mov     [r9], rdi
0x18002ce67  mov     rbx, rcx
0x18002ce6a  mov     rcx, [rdx]; sourceString
0x18002ce6d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002ce71  inc     rdx; int
0x18002ce74  cmp     [rcx+rdx*2], di
0x18002ce78  jnz     short loc_18002CE71
0x18002ce7a  mov     eax, 0FFFFFFFFh
0x18002ce7f  cmp     rdx, rax
0x18002ce82  ja      short loc_18002CEAE
0x18002ce84  lea     eax, [rdx+1]
0x18002ce87  cmp     eax, edx
0x18002ce89  jb      short loc_18002CEB9
0x18002ce8b  mov     r8, rbx; hstringHeader
0x18002ce8e  call    cs:__imp_WindowsCreateStringReference
0x18002ce94  test    eax, eax
0x18002ce96  js      short loc_18002CEA6
0x18002ce98  mov     rax, rbx
0x18002ce9b  mov     rbx, [rsp+28h+arg_0]
0x18002cea0  add     rsp, 20h
0x18002cea4  pop     rdi
0x18002cea5  retn
0x18002cea6  mov     ecx, eax; this
0x18002cea8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002cead  int     3; Trap to Debugger
0x18002ceae  mov     ecx, 80070216h; this
0x18002ceb3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002ceb8  int     3; Trap to Debugger
0x18002ceb9  mov     ecx, 80070216h; this
0x18002cebe  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
