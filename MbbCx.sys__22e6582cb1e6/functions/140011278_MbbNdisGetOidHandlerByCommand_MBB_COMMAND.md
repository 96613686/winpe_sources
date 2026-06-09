# MbbNdisGetOidHandlerByCommand(_MBB_COMMAND *)

- ea: `0x140011278`
- end: `0x14001131f`
- name: `?MbbNdisGetOidHandlerByCommand@@YAPEAU_MBB_OID_HANDLER_ENTRY@@PEAU_MBB_COMMAND@@@Z`
- size: `167`
- prototype: `struct _MBB_OID_HANDLER_ENTRY *__fastcall(struct _MBB_COMMAND *)`
- caller_count: `17`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002024`
- `0x140002278`
- `0x1400024cc`
- `0x140003744`
- `0x140003ab0`
- `0x140003d30`
- `0x140004004`
- `0x14000431c`
- `0x14000459c`
- `0x140004844`
- `0x140005028`
- `0x14000514c`
- `0x140009720`
- `0x140011dd0`
- `0x14001ea18`
- `0x14002ec90`
- `0x14002f228`

## callees

- `0x140011278`

## pseudocode

```c
struct _MBB_OID_HANDLER_ENTRY near **__fastcall MbbNdisGetOidHandlerByCommand(struct _MBB_COMMAND *a1)
{
  int v1; // edi
  struct _MBB_OID_HANDLER_ENTRY near **v3; // rbx
  unsigned int i; // r8d
  struct _MBB_OID_HANDLER_ENTRY near **v5; // r9
  __int64 v6; // r11
  struct _MBB_OID_HANDLER_ENTRY near **v7; // r10

  v1 = *((_DWORD *)a1 + 4);
  if ( !v1 && MBB_UUID_INVALID == *(_QWORD *)a1 && !*((_QWORD *)a1 + 1) )
    return 0;
  v3 = 0;
  for ( i = 0; i < 2; ++i )
  {
    v5 = &MbbOidHandlerTable;
    if ( i )
      v5 = &MbbSpecialOidHandlerTable;
    if ( *(_DWORD *)v5 )
    {
      v6 = 0;
      while ( 1 )
      {
        v7 = &v5[12 * v6];
        if ( v1 == *((_DWORD *)v7 + 16)
          && v7[6] == *(struct _MBB_OID_HANDLER_ENTRY near **)a1
          && v7[7] == *((struct _MBB_OID_HANDLER_ENTRY near **)a1 + 1) )
        {
          break;
        }
        v6 = (unsigned int)(v6 + 1);
        if ( !LODWORD(v5[12 * v6]) )
          goto LABEL_16;
      }
      v3 = &v5[12 * v6];
    }
LABEL_16:
    ;
  }
  return v3;
}

```

## disassembly

```asm
0x140011278  mov     [rsp+arg_0], rbx
0x14001127d  mov     [rsp+arg_8], rdi
0x140011282  mov     edi, [rcx+10h]
0x140011285  mov     rdx, rcx
0x140011288  test    edi, edi
0x14001128a  jnz     short loc_1400112A9
0x14001128c  mov     rax, cs:MBB_UUID_INVALID
0x140011293  cmp     rax, [rcx]
0x140011296  jnz     short loc_1400112A9
0x140011298  mov     rax, cs:qword_14004E848
0x14001129f  cmp     rax, [rcx+8]
0x1400112a3  jnz     short loc_1400112A9
0x1400112a5  xor     eax, eax
0x1400112a7  jmp     short loc_140011313
0x1400112a9  xor     ebx, ebx
0x1400112ab  xor     r8d, r8d
0x1400112ae  test    r8d, r8d
0x1400112b1  lea     rax, ?MbbSpecialOidHandlerTable@@3PAU_MBB_OID_HANDLER_ENTRY@@A; _MBB_OID_HANDLER_ENTRY near * MbbSpecialOidHandlerTable
0x1400112b8  lea     r9, ?MbbOidHandlerTable@@3PAU_MBB_OID_HANDLER_ENTRY@@A; _MBB_OID_HANDLER_ENTRY near * MbbOidHandlerTable
0x1400112bf  cmovnz  r9, rax
0x1400112c3  cmp     dword ptr [r9], 0
0x1400112c7  jz      short loc_140011307
0x1400112c9  xor     r11d, r11d
0x1400112cc  lea     r10, [r11+r11*2]
0x1400112d0  shl     r10, 5
0x1400112d4  add     r10, r9
0x1400112d7  cmp     edi, [r10+40h]
0x1400112db  jnz     short loc_1400112F0
0x1400112dd  mov     rax, [r10+30h]
0x1400112e1  cmp     rax, [rdx]
0x1400112e4  jnz     short loc_1400112F0
0x1400112e6  mov     rax, [r10+38h]
0x1400112ea  cmp     rax, [rdx+8]
0x1400112ee  jz      short loc_140011304
0x1400112f0  inc     r11d
0x1400112f3  lea     rcx, [r11+r11*2]
0x1400112f7  shl     rcx, 5
0x1400112fb  cmp     dword ptr [rcx+r9], 0
0x140011300  jnz     short loc_1400112CC
0x140011302  jmp     short loc_140011307
0x140011304  mov     rbx, r10
0x140011307  inc     r8d
0x14001130a  cmp     r8d, 2
0x14001130e  jb      short loc_1400112AE
0x140011310  mov     rax, rbx
0x140011313  mov     rbx, [rsp+arg_0]
0x140011318  mov     rdi, [rsp+arg_8]
0x14001131d  retn
```
