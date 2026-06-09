# Windows::Internal::StringReference::_ConstructorHelper(ushort const *)

- ea: `0x180014260`
- end: `0x1800142c6`
- name: `?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z`
- size: `102`
- prototype: `void __fastcall(Windows::Internal::StringReference *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f64`

## callees

- `0x180014260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001429e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001429e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800142bf`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::_ConstructorHelper(
        Windows::Internal::StringReference *this,
        const unsigned __int16 *a2)
{
  unsigned __int64 v4; // rbx

  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    LODWORD(v4) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v4, (HSTRING_HEADER *)((char *)this + 8), (HSTRING *)this);
}

```

## disassembly

```asm
0x180014260  mov     [rsp+arg_0], rbx
0x180014265  mov     [rsp+arg_8], rsi
0x18001426a  push    rdi
0x18001426b  sub     rsp, 20h
0x18001426f  mov     rdi, rdx
0x180014272  mov     rsi, rcx
0x180014275  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014279  inc     rbx
0x18001427c  cmp     word ptr [rdx+rbx*2], 0
0x180014281  jnz     short loc_180014279
0x180014283  mov     eax, 0FFFFFFFFh
0x180014288  cmp     rbx, rax
0x18001428b  jbe     short loc_1800142A4
0x18001428d  xor     r9d, r9d; lpArguments
0x180014290  xor     r8d, r8d; nNumberOfArguments
0x180014293  mov     ecx, 0C000000Dh; dwExceptionCode
0x180014298  mov     ebx, eax
0x18001429a  lea     edx, [r9+1]; dwExceptionFlags
0x18001429e  call    cs:__imp_RaiseException
0x1800142a4  lea     r8, [rsi+8]
0x1800142a8  mov     r9, rsi
0x1800142ab  mov     edx, ebx
0x1800142ad  mov     rcx, rdi
0x1800142b0  mov     rbx, [rsp+28h+arg_0]
0x1800142b5  mov     rsi, [rsp+28h+arg_8]
0x1800142ba  add     rsp, 20h
0x1800142be  pop     rdi
0x1800142bf  jmp     cs:__imp_WindowsCreateStringReference
```
