# __acrt_errno_map_os_error_ptd

- ea: `0x140006854`
- end: `0x140006876`
- name: `__acrt_errno_map_os_error_ptd`
- size: `34`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bfc8`
- `0x14000c568`
- `0x14000ca98`

## callees

- `0x140006784`

## pseudocode

```c
__int64 __fastcall _acrt_errno_map_os_error_ptd(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  *(_BYTE *)(a2 + 56) = 1;
  *(_DWORD *)(a2 + 52) = a1;
  result = sub_140006784(a1);
  *(_DWORD *)(a2 + 44) = result;
  *(_BYTE *)(a2 + 48) = 1;
  return result;
}

```

## disassembly

```asm
0x140006854  push    rbx
0x140006856  sub     rsp, 20h
0x14000685a  mov     rbx, rdx
0x14000685d  mov     byte ptr [rdx+38h], 1
0x140006861  mov     [rdx+34h], ecx
0x140006864  call    sub_140006784
0x140006869  mov     [rbx+2Ch], eax
0x14000686c  mov     byte ptr [rbx+30h], 1
0x140006870  add     rsp, 20h
0x140006874  pop     rbx
0x140006875  retn
```
