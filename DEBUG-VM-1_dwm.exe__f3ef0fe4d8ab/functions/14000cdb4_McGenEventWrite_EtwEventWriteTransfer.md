# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x14000cdb4`
- end: `0x14000ce06`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400023dc`
- `0x14000ce0c`

## callees

- `0x14000cdb4`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x14000cdfb`
- `ntdll!EtwEventWriteTransfer` at `0x14000cdfb`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_140018098;
  if ( qword_140018098 )
  {
    *(_QWORD *)a5 = qword_140018098;
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
  return EtwEventWriteTransfer(Microsoft_Windows_Dwm_Dwm_Provider_Context, a2, 0);
}

```

## disassembly

```asm
0x14000cdb4  sub     rsp, 38h
0x14000cdb8  mov     rcx, cs:qword_140018098
0x14000cdbf  mov     rax, [rsp+38h+arg_20]
0x14000cdc4  test    rcx, rcx
0x14000cdc7  jnz     short loc_14000CDD1
0x14000cdc9  mov     [rax], rcx
0x14000cdcc  xor     r8d, r8d
0x14000cdcf  jmp     short loc_14000CDDD
0x14000cdd1  mov     [rax], rcx
0x14000cdd4  mov     r8d, 2
0x14000cdda  movzx   ecx, word ptr [rcx]
0x14000cddd  mov     [rax+8], ecx
0x14000cde0  mov     [rax+0Ch], r8d
0x14000cde4  xor     r8d, r8d
0x14000cde7  mov     rcx, cs:Microsoft_Windows_Dwm_Dwm_Provider_Context
0x14000cdee  mov     [rsp+38h+var_10], rax
0x14000cdf3  mov     [rsp+38h+var_18], r9d
0x14000cdf8  xor     r9d, r9d
0x14000cdfb  call    cs:__imp_EtwEventWriteTransfer
0x14000ce01  add     rsp, 38h
0x14000ce05  retn
```
