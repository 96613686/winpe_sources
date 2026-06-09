# Windows::Internal::StringReference::_ConstructorHelper(ushort const *)

- ea: `0x18001b218`
- end: `0x18001b27e`
- name: `?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z`
- size: `102`
- prototype: `void __fastcall(Windows::Internal::StringReference *__hidden this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a224`
- `0x18001e4a0`
- `0x18001f424`
- `0x1800225a0`
- `0x180022728`
- `0x180022a4c`
- `0x180024440`

## callees

- `0x18001b218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b256`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b277`

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
0x18001b218  mov     [rsp+arg_0], rbx
0x18001b21d  mov     [rsp+arg_8], rsi
0x18001b222  push    rdi
0x18001b223  sub     rsp, 20h
0x18001b227  mov     rdi, rdx
0x18001b22a  mov     rsi, rcx
0x18001b22d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b231  inc     rbx
0x18001b234  cmp     word ptr [rdx+rbx*2], 0
0x18001b239  jnz     short loc_18001B231
0x18001b23b  mov     eax, 0FFFFFFFFh
0x18001b240  cmp     rbx, rax
0x18001b243  jbe     short loc_18001B25C
0x18001b245  xor     r9d, r9d; lpArguments
0x18001b248  xor     r8d, r8d; nNumberOfArguments
0x18001b24b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001b250  mov     ebx, eax
0x18001b252  lea     edx, [r9+1]; dwExceptionFlags
0x18001b256  call    cs:__imp_RaiseException
0x18001b25c  lea     r8, [rsi+8]
0x18001b260  mov     r9, rsi
0x18001b263  mov     edx, ebx
0x18001b265  mov     rcx, rdi
0x18001b268  mov     rbx, [rsp+28h+arg_0]
0x18001b26d  mov     rsi, [rsp+28h+arg_8]
0x18001b272  add     rsp, 20h
0x18001b276  pop     rdi
0x18001b277  jmp     cs:__imp_WindowsCreateStringReference
```
