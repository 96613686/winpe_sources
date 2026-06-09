# PCPStorageProviderKey::DeleteKey(ulong)

- ea: `0x18007ee74`
- end: `0x18007eeb6`
- name: `?DeleteKey@PCPStorageProviderKey@@QEAAJK@Z`
- size: `66`
- prototype: `__int64 __fastcall(PCPStorageProviderKey *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180059ea0`

## callees

- `0x18000f858`
- `0x18007ee74`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007ee80`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007ee80`

## pseudocode

```c
__int64 __fastcall PCPStorageProviderKey::DeleteKey(const WCHAR *this)
{
  const char *v1; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( DeleteFileW(this + 44) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xD69,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
             v1);
}

```

## disassembly

```asm
0x18007ee74  mov     [rsp+arg_8], edx
0x18007ee78  sub     rsp, 28h
0x18007ee7c  add     rcx, 58h ; 'X'; lpFileName
0x18007ee80  call    cs:__imp_DeleteFileW
0x18007ee87  nop     dword ptr [rax+rax+00h]
0x18007ee8c  test    eax, eax
0x18007ee8e  jnz     short loc_18007EEA8
0x18007ee90  mov     rcx, [rsp+28h]; this
0x18007ee95  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007ee9c  mov     edx, 0D69h; void *
0x18007eea1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007eea6  jmp     short loc_18007EEB0
0x18007eea8  xor     eax, eax
0x18007eeaa  jmp     short loc_18007EEB0
0x18007eeac  mov     eax, [rsp+28h+arg_8]
0x18007eeb0  add     rsp, 28h
0x18007eeb4  retn
```
