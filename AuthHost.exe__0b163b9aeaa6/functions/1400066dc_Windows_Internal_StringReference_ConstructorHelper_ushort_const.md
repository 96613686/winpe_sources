# Windows::Internal::StringReference::_ConstructorHelper(ushort const *)

- ea: `0x1400066dc`
- end: `0x140006742`
- name: `?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z`
- size: `102`
- prototype: `void __fastcall(Windows::Internal::StringReference *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400051f0`
- `0x140005dbc`
- `0x14000a4b0`
- `0x14000a858`
- `0x14000ad80`
- `0x14000b840`

## callees

- `0x1400066dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000671a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000671a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000673b`

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
0x1400066dc  mov     [rsp+arg_0], rbx
0x1400066e1  mov     [rsp+arg_8], rsi
0x1400066e6  push    rdi
0x1400066e7  sub     rsp, 20h
0x1400066eb  mov     rdi, rdx
0x1400066ee  mov     rsi, rcx
0x1400066f1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400066f5  inc     rbx
0x1400066f8  cmp     word ptr [rdx+rbx*2], 0
0x1400066fd  jnz     short loc_1400066F5
0x1400066ff  mov     eax, 0FFFFFFFFh
0x140006704  cmp     rbx, rax
0x140006707  jbe     short loc_140006720
0x140006709  xor     r9d, r9d; lpArguments
0x14000670c  xor     r8d, r8d; nNumberOfArguments
0x14000670f  mov     ecx, 0C000000Dh; dwExceptionCode
0x140006714  mov     ebx, eax
0x140006716  lea     edx, [r9+1]; dwExceptionFlags
0x14000671a  call    cs:__imp_RaiseException
0x140006720  lea     r8, [rsi+8]
0x140006724  mov     r9, rsi
0x140006727  mov     edx, ebx
0x140006729  mov     rcx, rdi
0x14000672c  mov     rbx, [rsp+28h+arg_0]
0x140006731  mov     rsi, [rsp+28h+arg_8]
0x140006736  add     rsp, 20h
0x14000673a  pop     rdi
0x14000673b  jmp     cs:__imp_WindowsCreateStringReference
```
