# Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x18005b814`
- end: `0x18005b89c`
- name: `??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005c450`
- `0x18005d010`

## callees

- `0x18001de54`
- `0x18005b814`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b87d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b87d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005b866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005b866`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize<unsigned short *>(HSTRING *a1, __int64 *a2, char a3)
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
0x18005b814  mov     rax, rsp
0x18005b817  mov     [rax+8], rbx
0x18005b81b  mov     [rax+20h], rsi
0x18005b81f  mov     [rax+18h], r8b
0x18005b823  push    rdi
0x18005b824  sub     rsp, 20h
0x18005b828  mov     r9, [rdx]
0x18005b82b  xor     esi, esi
0x18005b82d  mov     rdi, rcx
0x18005b830  test    r9, r9
0x18005b833  jz      short loc_18005B885
0x18005b835  mov     [rax+18h], esi
0x18005b838  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005b83c  mov     [rax+10h], rsi
0x18005b840  inc     rcx; unsigned __int64
0x18005b843  cmp     [r9+rcx*2], si
0x18005b848  jnz     short loc_18005B840
0x18005b84a  lea     rdx, [rsp+28h+length]; unsigned int *
0x18005b84f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18005b854  mov     ebx, eax
0x18005b856  test    eax, eax
0x18005b858  js      short loc_18005B88A
0x18005b85a  mov     edx, [rsp+28h+length]; length
0x18005b85e  lea     r8, [rsp+28h+string]; string
0x18005b863  mov     rcx, r9; sourceString
0x18005b866  call    cs:__imp_WindowsCreateString
0x18005b86c  mov     ebx, eax
0x18005b86e  test    eax, eax
0x18005b870  js      short loc_18005B88A
0x18005b872  mov     rax, [rsp+28h+string]
0x18005b877  mov     rcx, [rdi]; string
0x18005b87a  mov     [rdi], rax
0x18005b87d  call    cs:__imp_WindowsDeleteString
0x18005b883  jmp     short loc_18005B88A
0x18005b885  mov     ebx, 80004003h
0x18005b88a  mov     rsi, [rsp+28h+arg_18]
0x18005b88f  mov     eax, ebx
0x18005b891  mov     rbx, [rsp+28h+arg_0]
0x18005b896  add     rsp, 20h
0x18005b89a  pop     rdi
0x18005b89b  retn
```
