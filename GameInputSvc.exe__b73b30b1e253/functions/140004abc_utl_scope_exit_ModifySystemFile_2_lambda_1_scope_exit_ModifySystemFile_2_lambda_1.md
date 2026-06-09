# utl::scope_exit__ModifySystemFile_::_2_::_lambda_1___::_scope_exit__ModifySystemFile_::_2_::_lambda_1___

- ea: `0x140004abc`
- end: `0x140004b3f`
- name: `utl::scope_exit__ModifySystemFile_::_2_::_lambda_1___::_scope_exit__ModifySystemFile_::_2_::_lambda_1___`
- size: `131`
- prototype: `HLOCAL *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140004c20`

## callees

- `0x140004abc`
- `0x14000563c`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140004aed`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140004aed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004b21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004b33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004b21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004b33`

## pseudocode

```c
HLOCAL *__fastcall utl::scope_exit__ModifySystemFile_::_2_::_lambda_1___::_scope_exit__ModifySystemFile_::_2_::_lambda_1___(
        __int64 a1)
{
  HLOCAL *result; // rax
  void *v3; // rcx

  if ( *(_BYTE *)(a1 + 64) )
  {
    if ( !**(_DWORD **)a1 )
    {
      if ( **(_DWORD **)(a1 + 8) )
        MoveFileExW(*(LPCWSTR *)(a1 + 16), **(LPCWSTR **)(a1 + 24), 1u);
      if ( **(_DWORD **)(a1 + 32) )
        SetFileAttributesAndAcl(**(LPWSTR **)(a1 + 24), **(_DWORD **)(a1 + 40), **(void ***)(a1 + 48));
    }
    v3 = **(void ***)(a1 + 48);
    if ( v3 )
      LocalFree(v3);
    result = *(HLOCAL **)(a1 + 56);
    if ( *result )
      return (HLOCAL *)LocalFree(*result);
  }
  return result;
}

```

## disassembly

```asm
0x140004abc  push    rbx
0x140004abe  sub     rsp, 20h
0x140004ac2  cmp     byte ptr [rcx+40h], 0
0x140004ac6  mov     rbx, rcx
0x140004ac9  jz      short loc_140004B39
0x140004acb  mov     rax, [rcx]
0x140004ace  cmp     dword ptr [rax], 0
0x140004ad1  jnz     short loc_140004B15
0x140004ad3  mov     rax, [rcx+8]
0x140004ad7  cmp     dword ptr [rax], 0
0x140004ada  jz      short loc_140004AF3
0x140004adc  mov     rdx, [rcx+18h]
0x140004ae0  mov     r8d, 1; dwFlags
0x140004ae6  mov     rcx, [rcx+10h]; lpExistingFileName
0x140004aea  mov     rdx, [rdx]; lpNewFileName
0x140004aed  call    cs:__imp_MoveFileExW
0x140004af3  mov     rax, [rbx+20h]
0x140004af7  cmp     dword ptr [rax], 0
0x140004afa  jz      short loc_140004B15
0x140004afc  mov     r8, [rbx+30h]
0x140004b00  mov     rdx, [rbx+28h]
0x140004b04  mov     rcx, [rbx+18h]
0x140004b08  mov     r8, [r8]; void *
0x140004b0b  mov     edx, [rdx]; unsigned int
0x140004b0d  mov     rcx, [rcx]; pObjectName
0x140004b10  call    ?SetFileAttributesAndAcl@@YAJPEBGKPEAX@Z; SetFileAttributesAndAcl(ushort const *,ulong,void *)
0x140004b15  mov     rax, [rbx+30h]
0x140004b19  mov     rcx, [rax]; hMem
0x140004b1c  test    rcx, rcx
0x140004b1f  jz      short loc_140004B27
0x140004b21  call    cs:__imp_LocalFree
0x140004b27  mov     rax, [rbx+38h]
0x140004b2b  mov     rcx, [rax]; hMem
0x140004b2e  test    rcx, rcx
0x140004b31  jz      short loc_140004B39
0x140004b33  call    cs:__imp_LocalFree
0x140004b39  add     rsp, 20h
0x140004b3d  pop     rbx
0x140004b3e  retn
```
