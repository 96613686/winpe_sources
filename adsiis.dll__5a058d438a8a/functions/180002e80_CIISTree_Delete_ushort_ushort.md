# CIISTree::Delete(ushort *,ushort *)

- ea: `0x180002e80`
- end: `0x180002ec3`
- name: `?Delete@CIISTree@@UEAAJPEAG0@Z`
- size: `67`
- prototype: `__int64 __fastcall(CIISTree *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002e80`
- `0x1800151fc`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsStr` at `0x180002eb5`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180002eb5`

## pseudocode

```c
__int64 __fastcall CIISTree::Delete(CIISTree *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v4; // rcx
  unsigned int v5; // ebx
  LPWSTR pStr; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147500035LL;
  v4 = (unsigned __int16 *)*((_QWORD *)this - 6);
  pStr = 0;
  v5 = BuildIISPathFromADsPath(v4, &pStr);
  if ( pStr )
    FreeADsStr(pStr);
  return v5;
}

```

## disassembly

```asm
0x180002e80  push    rbx
0x180002e82  sub     rsp, 20h
0x180002e86  test    r8, r8
0x180002e89  jnz     short loc_180002E92
0x180002e8b  mov     eax, 80004003h
0x180002e90  jmp     short loc_180002EBD
0x180002e92  mov     rcx, [rcx-30h]; unsigned __int16 *
0x180002e96  lea     rdx, [rsp+28h+pStr]; unsigned __int16 **
0x180002e9b  mov     [rsp+28h+pStr], 0
0x180002ea4  call    ?BuildIISPathFromADsPath@@YAJPEAGPEAPEAG@Z; BuildIISPathFromADsPath(ushort *,ushort * *)
0x180002ea9  mov     ebx, eax
0x180002eab  mov     rcx, [rsp+28h+pStr]; pStr
0x180002eb0  test    rcx, rcx
0x180002eb3  jz      short loc_180002EBB
0x180002eb5  call    cs:__imp_FreeADsStr
0x180002ebb  mov     eax, ebx
0x180002ebd  add     rsp, 20h
0x180002ec1  pop     rbx
0x180002ec2  retn
```
