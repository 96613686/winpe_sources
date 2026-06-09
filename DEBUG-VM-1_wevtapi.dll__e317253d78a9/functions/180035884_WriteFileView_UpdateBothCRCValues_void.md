# WriteFileView::UpdateBothCRCValues(void)

- ea: `0x180035884`
- end: `0x1800358d1`
- name: `?UpdateBothCRCValues@WriteFileView@@QEAAXXZ`
- size: `77`
- prototype: `void __fastcall(WriteFileView *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180031754`
- `0x180033cec`

## callees

- `0x180034ba4`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x1800358a8`
- `ntdll!RtlComputeCrc32` at `0x1800358a8`

## pseudocode

```c
void __fastcall WriteFileView::UpdateBothCRCValues(WriteFileView *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8

  *(_DWORD *)(*((_QWORD *)this + 1) + 52LL) = RtlComputeCrc32(
                                                0,
                                                (PUCHAR)(*((_QWORD *)this + 3) + 512LL),
                                                *(_DWORD *)(*((_QWORD *)this + 1) + 48LL) - 512);
  *(_DWORD *)(*((_QWORD *)this + 1) + 124LL) = CalcGeneralHeaderCRC(*((PUCHAR *)this + 1), v2, v3, 512);
}

```

## disassembly

```asm
0x180035884  push    rbx
0x180035886  sub     rsp, 20h
0x18003588a  mov     r9, [rcx+18h]
0x18003588e  mov     rbx, rcx
0x180035891  mov     rax, [rcx+8]
0x180035895  xor     ecx, ecx; InitialCrc
0x180035897  lea     rdx, [r9+200h]; Buffer
0x18003589e  mov     r8d, [rax+30h]
0x1800358a2  sub     r8d, edx
0x1800358a5  add     r8d, r9d; Length
0x1800358a8  call    cs:__imp_RtlComputeCrc32
0x1800358ae  mov     rcx, [rbx+8]
0x1800358b2  mov     r9d, 200h; unsigned int
0x1800358b8  mov     [rcx+34h], eax
0x1800358bb  mov     rcx, [rbx+8]; Buffer
0x1800358bf  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x1800358c4  mov     rcx, [rbx+8]
0x1800358c8  mov     [rcx+7Ch], eax
0x1800358cb  add     rsp, 20h
0x1800358cf  pop     rbx
0x1800358d0  retn
```
