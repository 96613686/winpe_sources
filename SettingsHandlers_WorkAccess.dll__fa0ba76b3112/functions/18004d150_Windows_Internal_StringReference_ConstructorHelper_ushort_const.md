# Windows::Internal::StringReference::_ConstructorHelper(ushort const *)

- ea: `0x18004d150`
- end: `0x18004d1c0`
- name: `?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z`
- size: `112`
- prototype: `void __fastcall(Windows::Internal::StringReference *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`
- `0x18004cc34`

## callees

- `0x1800176bc`
- `0x18004d150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d190`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d1b4`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::_ConstructorHelper(
        Windows::Internal::StringReference *this,
        const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rcx
  const ULONG_PTR *v5; // r9
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( (int)ULongLongToUInt(v3, &v6) < 0 )
    RaiseException(0xC000000D, 1u, 0, v5);
  WindowsCreateStringReference(a2, v6, (HSTRING_HEADER *)((char *)this + 8), (HSTRING *)this);
}

```

## disassembly

```asm
0x18004d150  mov     [rsp+arg_8], rbx
0x18004d155  push    rdi
0x18004d156  sub     rsp, 20h
0x18004d15a  xor     r9d, r9d
0x18004d15d  mov     rbx, rcx
0x18004d160  mov     [rsp+28h+arg_0], r9d
0x18004d165  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d169  mov     rdi, rdx
0x18004d16c  inc     rcx; unsigned __int64
0x18004d16f  cmp     [rdx+rcx*2], r9w
0x18004d174  jnz     short loc_18004D16C
0x18004d176  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x18004d17b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004d180  test    eax, eax
0x18004d182  jns     short loc_18004D19C
0x18004d184  xor     r8d, r8d; nNumberOfArguments
0x18004d187  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d18c  lea     edx, [r8+1]; dwExceptionFlags
0x18004d190  call    cs:__imp_RaiseException
0x18004d197  nop     dword ptr [rax+rax+00h]
0x18004d19c  mov     edx, [rsp+28h+arg_0]
0x18004d1a0  lea     r8, [rbx+8]
0x18004d1a4  mov     r9, rbx
0x18004d1a7  mov     rcx, rdi
0x18004d1aa  mov     rbx, [rsp+28h+arg_8]
0x18004d1af  add     rsp, 20h
0x18004d1b3  pop     rdi
0x18004d1b4  jmp     cs:__imp_WindowsCreateStringReference
```
