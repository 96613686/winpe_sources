# Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x180063040`
- end: `0x1800630c8`
- name: `??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z`
- size: `136`
- prototype: `__int64 __fastcall(HSTRING *, __int64 *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009db0`
- `0x180017270`

## callees

- `0x18000a1a4`
- `0x180063040`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180063092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180063092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800630a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800630a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::String::Initialize<unsigned short const *>(HSTRING *a1, __int64 *a2, char a3)
{
  __int64 v3; // r9
  unsigned __int64 v5; // rcx
  HRESULT v6; // ebx
  const WCHAR *v7; // r9
  HSTRING v8; // rcx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF
  UINT32 length; // [rsp+40h] [rbp+18h] BYREF

  LOBYTE(length) = a3;
  v3 = *a2;
  if ( *a2 )
  {
    length = 0;
    v5 = -1;
    string = 0;
    do
      ++v5;
    while ( *(_WORD *)(v3 + 2 * v5) );
    v6 = ULongLongToUInt(v5, &length);
    if ( v6 >= 0 )
    {
      v6 = WindowsCreateString(v7, length, &string);
      if ( v6 >= 0 )
      {
        v8 = *a1;
        *a1 = string;
        WindowsDeleteString(v8);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180063040  mov     rax, rsp
0x180063043  mov     [rax+8], rbx
0x180063047  mov     [rax+20h], rsi
0x18006304b  mov     [rax+18h], r8b
0x18006304f  push    rdi
0x180063050  sub     rsp, 20h
0x180063054  mov     r9, [rdx]
0x180063057  xor     esi, esi
0x180063059  mov     rdi, rcx
0x18006305c  test    r9, r9
0x18006305f  jz      short loc_1800630B1
0x180063061  mov     [rax+18h], esi
0x180063064  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180063068  mov     [rax+10h], rsi
0x18006306c  inc     rcx; unsigned __int64
0x18006306f  cmp     [r9+rcx*2], si
0x180063074  jnz     short loc_18006306C
0x180063076  lea     rdx, [rsp+28h+length]; unsigned int *
0x18006307b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180063080  mov     ebx, eax
0x180063082  test    eax, eax
0x180063084  js      short loc_1800630B6
0x180063086  mov     edx, [rsp+28h+length]; length
0x18006308a  lea     r8, [rsp+28h+string]; string
0x18006308f  mov     rcx, r9; sourceString
0x180063092  call    cs:__imp_WindowsCreateString
0x180063098  mov     ebx, eax
0x18006309a  test    eax, eax
0x18006309c  js      short loc_1800630B6
0x18006309e  mov     rax, [rsp+28h+string]
0x1800630a3  mov     rcx, [rdi]; string
0x1800630a6  mov     [rdi], rax
0x1800630a9  call    cs:__imp_WindowsDeleteString
0x1800630af  jmp     short loc_1800630B6
0x1800630b1  mov     ebx, 80004003h
0x1800630b6  mov     rsi, [rsp+28h+arg_18]
0x1800630bb  mov     eax, ebx
0x1800630bd  mov     rbx, [rsp+28h+arg_0]
0x1800630c2  add     rsp, 20h
0x1800630c6  pop     rdi
0x1800630c7  retn
```
