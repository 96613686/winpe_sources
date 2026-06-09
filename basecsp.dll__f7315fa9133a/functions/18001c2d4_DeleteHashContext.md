# DeleteHashContext

- ea: `0x18001c2d4`
- end: `0x18001c33f`
- name: `DeleteHashContext`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a674`
- `0x18001aab0`
- `0x18001ab74`

## callees

- `0x18001c2d4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2fa`
- `CRYPTSP!CryptDestroyHash` at `0x18001c2f0`
- `CRYPTSP!CryptDestroyHash` at `0x18001c2f0`

## pseudocode

```c
__int64 __fastcall DeleteHashContext(__int64 a1)
{
  DWORD LastError; // edi
  HCRYPTHASH v3; // rcx
  int v5; // [rsp+30h] [rbp+8h] BYREF

  LastError = 0;
  v3 = *(_QWORD *)(a1 + 8);
  v5 = 0;
  if ( v3 )
  {
    if ( !CryptDestroyHash(v3) )
      LastError = GetLastError();
    *(_QWORD *)(a1 + 8) = 0;
  }
  if ( *(_QWORD *)(a1 + 24) && qword_18003B098 )
  {
    qword_18003B098(a1, &v5);
    *(_QWORD *)(a1 + 24) = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001c2d4  mov     [rsp+arg_8], rbx
0x18001c2d9  push    rdi
0x18001c2da  sub     rsp, 20h
0x18001c2de  xor     edi, edi
0x18001c2e0  mov     rbx, rcx
0x18001c2e3  mov     rcx, [rcx+8]; hHash
0x18001c2e7  mov     [rsp+28h+arg_0], edi
0x18001c2eb  test    rcx, rcx
0x18001c2ee  jz      short loc_18001C30A
0x18001c2f0  call    cs:__imp_CryptDestroyHash
0x18001c2f6  test    eax, eax
0x18001c2f8  jnz     short loc_18001C302
0x18001c2fa  call    cs:__imp_GetLastError
0x18001c300  mov     edi, eax
0x18001c302  mov     qword ptr [rbx+8], 0
0x18001c30a  cmp     qword ptr [rbx+18h], 0
0x18001c30f  jz      short loc_18001C332
0x18001c311  mov     rax, cs:qword_18003B098
0x18001c318  test    rax, rax
0x18001c31b  jz      short loc_18001C332
0x18001c31d  lea     rdx, [rsp+28h+arg_0]
0x18001c322  mov     rcx, rbx
0x18001c325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c32a  mov     qword ptr [rbx+18h], 0
0x18001c332  mov     rbx, [rsp+28h+arg_8]
0x18001c337  mov     eax, edi
0x18001c339  add     rsp, 20h
0x18001c33d  pop     rdi
0x18001c33e  retn
```
