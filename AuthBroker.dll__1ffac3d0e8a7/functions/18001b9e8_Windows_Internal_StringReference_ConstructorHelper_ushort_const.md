# Windows::Internal::StringReference::_ConstructorHelper(ushort const *)

- ea: `0x18001b9e8`
- end: `0x18001ba50`
- name: `?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z`
- size: `104`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t *stringRef)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054bc`
- `0x18001ed50`

## callees

- `0x180004a00`
- `0x18001b9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ba2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ba2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ba49`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::_ConstructorHelper(
        Windows::Internal::StringReference *this,
        const wchar_t *stringRef)
{
  unsigned __int64 v3; // rcx
  unsigned int length; // [rsp+30h] [rbp+8h] BYREF

  length = 0;
  v3 = -1;
  do
    ++v3;
  while ( stringRef[v3] );
  if ( ULongLongToUInt(v3, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(stringRef, length, &this->_header, &this->_hstring);
}

```

## disassembly

```asm
0x18001b9e8  mov     [rsp+arg_8], rbx
0x18001b9ed  push    rdi
0x18001b9ee  sub     rsp, 20h
0x18001b9f2  xor     r11d, r11d
0x18001b9f5  mov     rbx, this
0x18001b9f8  mov     [rsp+28h+length], r11d
0x18001b9fd  or      this, 0FFFFFFFFFFFFFFFFh
0x18001ba01  mov     rdi, stringRef
0x18001ba04  inc     this; ullOperand
0x18001ba07  cmp     [stringRef+this*2], r11w
0x18001ba0c  jnz     short loc_18001BA04
0x18001ba0e  lea     stringRef, [rsp+28h+length]; puResult
0x18001ba13  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001ba18  test    eax, eax
0x18001ba1a  jns     short loc_18001BA31
0x18001ba1c  xor     r9d, r9d; lpArguments
0x18001ba1f  xor     r8d, r8d; nNumberOfArguments
0x18001ba22  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001ba27  lea     edx, [r9+1]; dwExceptionFlags
0x18001ba2b  call    cs:__imp_RaiseException
0x18001ba31  mov     edx, [rsp+28h+length]
0x18001ba35  lea     r8, [rbx+8]
0x18001ba39  mov     r9, rbx
0x18001ba3c  mov     this, rdi
0x18001ba3f  mov     rbx, [rsp+28h+arg_8]
0x18001ba44  add     rsp, 20h
0x18001ba48  pop     rdi
0x18001ba49  jmp     cs:__imp_WindowsCreateStringReference
```
