# CCommandHandler::GetCanonicalName(_GUID *)

- ea: `0x180004e00`
- end: `0x180004e2c`
- name: `?GetCanonicalName@CCommandHandler@@UEAAJPEAU_GUID@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(CCommandHandler *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004e00`

## pseudocode

```c
__int64 __fastcall CCommandHandler::GetCanonicalName(CCommandHandler *this, struct _GUID *a2)
{
  unsigned int v2; // r8d
  struct _GUID *v3; // rcx

  v2 = -2147467259;
  v3 = (struct _GUID *)*((_QWORD *)&off_18000D378 + 4 * *((int *)this + 16));
  if ( v3 )
  {
    v2 = 0;
    *a2 = *v3;
  }
  return v2;
}

```

## disassembly

```asm
0x180004e00  movsxd  rax, dword ptr [rcx+40h]
0x180004e04  mov     r8d, 80004005h
0x180004e0a  shl     rax, 5
0x180004e0e  lea     rcx, off_18000D378
0x180004e15  mov     rcx, [rax+rcx]
0x180004e19  test    rcx, rcx
0x180004e1c  jz      short loc_180004E28
0x180004e1e  movups  xmm0, xmmword ptr [rcx]
0x180004e21  xor     r8d, r8d
0x180004e24  movdqu  xmmword ptr [rdx], xmm0
0x180004e28  mov     eax, r8d
0x180004e2b  retn
```
