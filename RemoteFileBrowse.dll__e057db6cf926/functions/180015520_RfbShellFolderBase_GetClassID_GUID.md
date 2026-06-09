# RfbShellFolderBase::GetClassID(_GUID *)

- ea: `0x180015520`
- end: `0x180015536`
- name: `?GetClassID@RfbShellFolderBase@@UEAAJPEAU_GUID@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(struct _GUID *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180005f60`

## callees

- `0x180015520`

## pseudocode

```c
__int64 __fastcall RfbShellFolderBase::GetClassID(struct _GUID *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  result = 0;
  *a2 = this[4];
  return result;
}

```

## disassembly

```asm
0x180015520  test    rdx, rdx
0x180015523  jnz     short loc_18001552B
0x180015525  mov     eax, 80070057h
0x18001552a  retn
0x18001552b  movups  xmm0, xmmword ptr [rcx+40h]
0x18001552f  xor     eax, eax
0x180015531  movdqu  xmmword ptr [rdx], xmm0
0x180015535  retn
```
