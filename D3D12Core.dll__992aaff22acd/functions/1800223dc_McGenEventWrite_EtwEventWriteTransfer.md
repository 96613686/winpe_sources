# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x1800223dc`
- end: `0x18002242e`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `42`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180022020`
- `0x1800220b4`
- `0x180022150`
- `0x1800221bc`
- `0x180022248`
- `0x18002232c`
- `0x180022388`
- `0x18009dd50`
- `0x1800a1a34`
- `0x1800a6314`
- `0x1800b4440`
- `0x1800b7468`
- `0x1800ea83c`
- `0x1800ea88c`
- `0x18010292c`
- `0x180102984`
- `0x180102a50`
- `0x180102ad0`
- `0x180102c0c`
- `0x180102c98`
- `0x180102d74`
- `0x180102dfc`
- `0x180102ea8`
- `0x180102f34`
- `0x18011d658`
- `0x18011d750`
- `0x18011d810`
- `0x180128698`
- `0x1801289c4`
- `0x18012e790`
- `0x18012e8a8`
- `0x1801323e0`
- `0x180143a18`
- `0x180144df0`
- `0x180144fb4`
- `0x180145150`
- `0x180145acc`
- `0x180145c74`
- `0x180149824`
- `0x18014b378`
- `0x18014c258`
- `0x18014cd40`

## callees

- `0x1800223dc`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180022415`
- `ntdll!EtwEventWriteTransfer` at `0x180022415`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180324AD8;
  if ( qword_180324AD8 )
  {
    *(_QWORD *)a5 = qword_180324AD8;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(Direct3D12EtwProviderGuid_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x1800223dc  sub     rsp, 38h
0x1800223e0  mov     rcx, cs:qword_180324AD8
0x1800223e7  mov     rax, [rsp+38h+arg_20]
0x1800223ec  test    rcx, rcx
0x1800223ef  jnz     short loc_180022420
0x1800223f1  mov     [rax], rcx
0x1800223f4  xor     r8d, r8d
0x1800223f7  mov     [rax+8], ecx
0x1800223fa  mov     [rax+0Ch], r8d
0x1800223fe  xor     r8d, r8d
0x180022401  mov     rcx, cs:Direct3D12EtwProviderGuid_Context
0x180022408  mov     [rsp+38h+var_10], rax
0x18002240d  mov     [rsp+38h+var_18], r9d
0x180022412  xor     r9d, r9d
0x180022415  call    cs:__imp_EtwEventWriteTransfer
0x18002241b  add     rsp, 38h
0x18002241f  retn
0x180022420  mov     [rax], rcx
0x180022423  mov     r8d, 2
0x180022429  movzx   ecx, word ptr [rcx]
0x18002242c  jmp     short loc_1800223F7
```
