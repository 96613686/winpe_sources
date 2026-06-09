# SetAllParameters

- ea: `0x180016438`
- end: `0x1800164b6`
- name: `SetAllParameters`
- size: `126`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180015dfc`
- `0x180015f68`
- `0x1800160f8`
- `0x180016274`

## callees

- `0x18001bcba`

## import_xrefs

- `NSI!NsiSetAllParametersEx` at `0x1800164a2`
- `NSI!NsiSetAllParametersEx` at `0x1800164a2`

## pseudocode

```c
__int64 __fastcall SetAllParameters(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6, int a7, int a8)
{
  _BYTE v11[16]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+38h] [rbp-40h]
  int v14; // [rsp+40h] [rbp-38h]
  int v15; // [rsp+44h] [rbp-34h]
  __int64 v16; // [rsp+48h] [rbp-30h]
  int v17; // [rsp+50h] [rbp-28h]
  __int64 v18; // [rsp+58h] [rbp-20h]
  int v19; // [rsp+60h] [rbp-18h]

  memset_0(v11, 0, 0x48u);
  v15 = a8;
  v17 = a5;
  v18 = a6;
  v12 = a2;
  v13 = 16;
  v14 = 1;
  v16 = a4;
  v19 = 32;
  return NsiSetAllParametersEx(v11);
}

```

## disassembly

```asm
0x180016438  mov     [rsp+arg_0], rbx
0x18001643d  push    rdi
0x18001643e  sub     rsp, 70h
0x180016442  mov     rbx, rdx
0x180016445  lea     rcx, [rsp+78h+var_58]; void *
0x18001644a  xor     edx, edx; Val
0x18001644c  mov     rdi, r9
0x18001644f  lea     r8d, [rdx+48h]; Size
0x180016453  call    memset_0
0x180016458  mov     eax, [rsp+78h+arg_38]
0x18001645f  lea     rcx, [rsp+78h+var_58]
0x180016464  mov     [rsp+78h+var_34], eax
0x180016468  mov     eax, [rsp+78h+arg_20]
0x18001646f  mov     [rsp+78h+var_28], eax
0x180016473  mov     rax, [rsp+78h+arg_28]
0x18001647b  mov     [rsp+78h+var_20], rax
0x180016480  mov     [rsp+78h+var_48], rbx
0x180016485  mov     [rsp+78h+var_40], 10h
0x18001648d  mov     [rsp+78h+var_38], 1
0x180016495  mov     [rsp+78h+var_30], rdi
0x18001649a  mov     [rsp+78h+var_18], 20h ; ' '
0x1800164a2  call    cs:__imp_NsiSetAllParametersEx
0x1800164a8  mov     rbx, [rsp+78h+arg_0]
0x1800164b0  add     rsp, 70h
0x1800164b4  pop     rdi
0x1800164b5  retn
```
