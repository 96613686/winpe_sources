# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180005918`
- end: `0x180005988`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006860`

## callees

- `0x180005918`
- `0x180007874`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005952`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2,
        unsigned int a3)
{
  HSTRING *v4; // r9
  const WCHAR *v5; // rcx
  unsigned __int64 v6; // rdx
  HRESULT StringReference; // eax
  int v8; // edx
  unsigned int v9; // r8d

  v4 = (HSTRING *)&a1[1];
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
    JUMPOUT(0x180005987LL);
  }
  StringReference = WindowsCreateStringReference(v5, v6, a1, v4);
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
0x180005918  mov     [rsp+arg_0], rbx
0x18000591d  push    rdi
0x18000591e  sub     rsp, 20h
0x180005922  mov     rbx, rcx
0x180005925  lea     r9, [rcx+18h]; string
0x180005929  xor     edi, edi
0x18000592b  mov     [r9], rdi
0x18000592e  mov     rcx, [rdx]; sourceString
0x180005931  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005935  inc     rdx; int
0x180005938  cmp     [rcx+rdx*2], di
0x18000593c  jnz     short loc_180005935
0x18000593e  mov     eax, 0FFFFFFFFh
0x180005943  cmp     rdx, rax
0x180005946  ja      short loc_180005972
0x180005948  lea     eax, [rdx+1]
0x18000594b  cmp     eax, edx
0x18000594d  jb      short loc_18000597D
0x18000594f  mov     r8, rbx; hstringHeader
0x180005952  call    cs:__imp_WindowsCreateStringReference
0x180005958  test    eax, eax
0x18000595a  js      short loc_18000596A
0x18000595c  mov     rax, rbx
0x18000595f  mov     rbx, [rsp+28h+arg_0]
0x180005964  add     rsp, 20h
0x180005968  pop     rdi
0x180005969  retn
0x18000596a  mov     ecx, eax; this
0x18000596c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180005971  int     3; Trap to Debugger
0x180005972  mov     ecx, 80070216h; this
0x180005977  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000597c  int     3; Trap to Debugger
0x18000597d  mov     ecx, 80070216h; this
0x180005982  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
