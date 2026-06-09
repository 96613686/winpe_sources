# CreateIfIdString

- ea: `0x180004678`
- end: `0x1800046cf`
- name: `CreateIfIdString`
- size: `87`
- prototype: `__int64 __fastcall(RPC_UUID *, RPC_UUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012c4`

## callees

- `0x180004678`
- `0x1800046d8`

## pseudocode

```c
__int64 __fastcall CreateIfIdString(RPC_UUID *a1, RPC_UUID *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v4; // rax

  if ( !a1 || !a2 || !a3 )
    return 2147549200LL;
  v4 = RPC_UUID::ConvertToString(a1, a3);
  if ( *(_DWORD *)a2 || *((_DWORD *)a2 + 1) || *((_DWORD *)a2 + 2) || *((_DWORD *)a2 + 3) )
  {
    *v4 = 58;
    RPC_UUID::ConvertToString(a2, v4 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180004678  push    rbx
0x18000467a  sub     rsp, 20h
0x18000467e  mov     rbx, rdx
0x180004681  test    rcx, rcx
0x180004684  jz      short loc_1800046C8
0x180004686  test    rdx, rdx
0x180004689  jz      short loc_1800046C8
0x18000468b  test    r8, r8
0x18000468e  jz      short loc_1800046C8
0x180004690  mov     rdx, r8; unsigned __int16 *
0x180004693  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x180004698  cmp     dword ptr [rbx], 0
0x18000469b  jnz     short loc_1800046AF
0x18000469d  cmp     dword ptr [rbx+4], 0
0x1800046a1  jnz     short loc_1800046AF
0x1800046a3  cmp     dword ptr [rbx+8], 0
0x1800046a7  jnz     short loc_1800046AF
0x1800046a9  cmp     dword ptr [rbx+0Ch], 0
0x1800046ad  jz      short loc_1800046C0
0x1800046af  lea     rdx, [rax+2]; unsigned __int16 *
0x1800046b3  mov     word ptr [rax], 3Ah ; ':'
0x1800046b8  mov     rcx, rbx; this
0x1800046bb  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x1800046c0  xor     eax, eax
0x1800046c2  add     rsp, 20h
0x1800046c6  pop     rbx
0x1800046c7  retn
0x1800046c8  mov     eax, 80010010h
0x1800046cd  jmp     short loc_1800046C2
```
