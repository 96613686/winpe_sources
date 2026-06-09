# _PROG_RESOURCES::_RevokeBackup(tagComCallData *)

- ea: `0x18000b560`
- end: `0x18000b5b7`
- name: `?_RevokeBackup@_PROG_RESOURCES@@SAJPEAUtagComCallData@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b560`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000b57f`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000b57f`

## pseudocode

```c
__int64 __fastcall _PROG_RESOURCES::_RevokeBackup(struct tagComCallData *a1)
{
  __int64 v1; // rcx

  v1 = (__int64)*(&pUnk + 1);
  if ( *(&pUnk + 1) )
  {
    if ( dword_180032A28 )
    {
      CoRevokeClassObject(*(&dwRegister + 1));
      v1 = (__int64)*(&pUnk + 1);
    }
    *(&dwRegister + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
    *(&pUnk + 1) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000b560  sub     rsp, 28h
0x18000b564  mov     rcx, qword ptr cs:pUnk+8
0x18000b56b  test    rcx, rcx
0x18000b56e  jz      short loc_18000B5AD
0x18000b570  cmp     cs:dword_180032A28, 0
0x18000b577  jz      short loc_18000B58C
0x18000b579  mov     ecx, dword ptr cs:dwRegister+4; dwRegister
0x18000b57f  call    cs:__imp_CoRevokeClassObject
0x18000b585  mov     rcx, qword ptr cs:pUnk+8
0x18000b58c  mov     dword ptr cs:dwRegister+4, 0
0x18000b596  mov     rax, [rcx]
0x18000b599  mov     rax, [rax+10h]
0x18000b59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a2  mov     qword ptr cs:pUnk+8, 0
0x18000b5ad  mov     eax, 1
0x18000b5b2  add     rsp, 28h
0x18000b5b6  retn
```
