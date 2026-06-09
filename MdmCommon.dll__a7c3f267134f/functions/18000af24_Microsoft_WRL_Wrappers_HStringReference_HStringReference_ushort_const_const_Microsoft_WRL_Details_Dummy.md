# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18000af24`
- end: `0x18000af9b`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `119`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b0e4`
- `0x18000bd94`
- `0x18000c6e8`
- `0x18000edc0`

## callees

- `0x18000af24`
- `0x1800117e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000af5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000af5e`

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
    JUMPOUT(0x18000AF9ALL);
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
0x18000af24  mov     [rsp+arg_0], rbx
0x18000af29  push    rdi
0x18000af2a  sub     rsp, 20h
0x18000af2e  lea     r9, [rcx+18h]; string
0x18000af32  xor     edi, edi
0x18000af34  mov     [r9], rdi
0x18000af37  mov     rbx, rcx
0x18000af3a  mov     rcx, [rdx]; sourceString
0x18000af3d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000af41  inc     rdx; int
0x18000af44  cmp     [rcx+rdx*2], di
0x18000af48  jnz     short loc_18000AF41
0x18000af4a  mov     eax, 0FFFFFFFFh
0x18000af4f  cmp     rdx, rax
0x18000af52  ja      short loc_18000AF85
0x18000af54  lea     eax, [rdx+1]
0x18000af57  cmp     eax, edx
0x18000af59  jb      short loc_18000AF90
0x18000af5b  mov     r8, rbx; hstringHeader
0x18000af5e  call    cs:__imp_WindowsCreateStringReference
0x18000af65  nop     dword ptr [rax+rax+00h]
0x18000af6a  test    eax, eax
0x18000af6c  js      short loc_18000AF7D
0x18000af6e  mov     rax, rbx
0x18000af71  mov     rbx, [rsp+28h+arg_0]
0x18000af76  add     rsp, 20h
0x18000af7a  pop     rdi
0x18000af7b  retn
0x18000af7d  mov     ecx, eax; this
0x18000af7f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000af84  int     3; Trap to Debugger
0x18000af85  mov     ecx, 80070216h; this
0x18000af8a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000af8f  int     3; Trap to Debugger
0x18000af90  mov     ecx, 80070216h; this
0x18000af95  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
