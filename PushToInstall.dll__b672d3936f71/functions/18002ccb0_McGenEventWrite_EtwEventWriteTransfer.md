# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18002ccb0`
- end: `0x18002ccfd`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c938`
- `0x18002cd04`

## callees

- `0x18002ccb0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18002ccf2`
- `ntdll!EtwEventWriteTransfer` at `0x18002ccf2`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    *(_QWORD *)a5 = v5;
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
  return EtwEventWriteTransfer(*a1, a2, 0);
}

```

## disassembly

```asm
0x18002ccb0  sub     rsp, 38h
0x18002ccb4  mov     r8, [rcx+8]
0x18002ccb8  mov     rax, [rsp+38h+arg_20]
0x18002ccbd  test    r8, r8
0x18002ccc0  jnz     short loc_18002CCCA
0x18002ccc2  mov     [rax], r8
0x18002ccc5  xor     r10d, r10d
0x18002ccc8  jmp     short loc_18002CCD7
0x18002ccca  mov     [rax], r8
0x18002cccd  mov     r10d, 2
0x18002ccd3  movzx   r8d, word ptr [r8]
0x18002ccd7  mov     [rax+8], r8d
0x18002ccdb  xor     r8d, r8d
0x18002ccde  mov     [rsp+38h+var_10], rax
0x18002cce3  mov     [rax+0Ch], r10d
0x18002cce7  mov     rcx, [rcx]
0x18002ccea  mov     [rsp+38h+var_18], r9d
0x18002ccef  xor     r9d, r9d
0x18002ccf2  call    cs:__imp_EtwEventWriteTransfer
0x18002ccf8  add     rsp, 38h
0x18002ccfc  retn
```
