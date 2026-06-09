# DeleteKeyContext

- ea: `0x18001c348`
- end: `0x18001c3b3`
- name: `DeleteKeyContext`
- size: `107`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a944`
- `0x18001ab00`
- `0x18001acf4`
- `0x18001b108`
- `0x18001b818`
- `0x18001bb2c`

## callees

- `0x18001c348`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c36e`
- `CRYPTSP!CryptDestroyKey` at `0x18001c364`
- `CRYPTSP!CryptDestroyKey` at `0x18001c364`

## pseudocode

```c
__int64 __fastcall DeleteKeyContext(__int64 a1)
{
  DWORD LastError; // edi
  HCRYPTKEY v3; // rcx
  int v5; // [rsp+30h] [rbp+8h] BYREF

  LastError = 0;
  v3 = *(_QWORD *)(a1 + 8);
  v5 = 0;
  if ( v3 )
  {
    if ( !CryptDestroyKey(v3) )
      LastError = GetLastError();
    *(_QWORD *)(a1 + 8) = 0;
  }
  if ( *(_QWORD *)(a1 + 32) && off_18003B020 )
  {
    off_18003B020((struct _KEY_CONTEXT *)a1, &v5);
    *(_QWORD *)(a1 + 32) = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001c348  mov     [rsp+arg_8], rbx
0x18001c34d  push    rdi
0x18001c34e  sub     rsp, 20h
0x18001c352  xor     edi, edi
0x18001c354  mov     rbx, rcx
0x18001c357  mov     rcx, [rcx+8]; hKey
0x18001c35b  mov     [rsp+28h+arg_0], edi
0x18001c35f  test    rcx, rcx
0x18001c362  jz      short loc_18001C37E
0x18001c364  call    cs:__imp_CryptDestroyKey
0x18001c36a  test    eax, eax
0x18001c36c  jnz     short loc_18001C376
0x18001c36e  call    cs:__imp_GetLastError
0x18001c374  mov     edi, eax
0x18001c376  mov     qword ptr [rbx+8], 0
0x18001c37e  cmp     qword ptr [rbx+20h], 0
0x18001c383  jz      short loc_18001C3A6
0x18001c385  mov     rax, cs:off_18003B020
0x18001c38c  test    rax, rax
0x18001c38f  jz      short loc_18001C3A6
0x18001c391  lea     rdx, [rsp+28h+arg_0]
0x18001c396  mov     rcx, rbx
0x18001c399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c39e  mov     qword ptr [rbx+20h], 0
0x18001c3a6  mov     rbx, [rsp+28h+arg_8]
0x18001c3ab  mov     eax, edi
0x18001c3ad  add     rsp, 20h
0x18001c3b1  pop     rdi
0x18001c3b2  retn
```
