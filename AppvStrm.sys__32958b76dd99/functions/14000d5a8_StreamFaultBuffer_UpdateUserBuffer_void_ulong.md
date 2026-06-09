# StreamFaultBuffer::UpdateUserBuffer(void *,ulong)

- ea: `0x14000d5a8`
- end: `0x14000d67b`
- name: `?UpdateUserBuffer@StreamFaultBuffer@@QEAAJPEAXK@Z`
- size: `211`
- prototype: `__int64 __fastcall(StreamFaultBuffer *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000c4ac`

## callees

- `0x1400010b0`
- `0x14000d5a8`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015c00`

## string_xrefs

- `0x14000d63d`: `StreamFaultBuffer::UpdateUserBuffer() - Stream fault failed because of a bad user buffer. File name: %s, Offset: %lld , Length %ld, Status 0x%08X.`

## pseudocode

```c
__int64 __fastcall StreamFaultBuffer::UpdateUserBuffer(StreamFaultBuffer *this, void *a2, unsigned int a3)
{
  unsigned int v3; // edi
  __int64 v5; // r9

  v3 = a3;
  if ( !*(_QWORD *)this )
    return 3221225701LL;
  v5 = *((_QWORD *)this + 3);
  if ( !v5 )
    return 3221225701LL;
  if ( a3 > *((_DWORD *)this + 3) )
    v3 = *((_DWORD *)this + 3);
  memmove((void *)(v5 + *((unsigned int *)this + 4)), a2, v3);
  *((_DWORD *)this + 4) += v3;
  *((_DWORD *)this + 3) -= v3;
  return 0;
}

```

## disassembly

```asm
0x14000d5a8  mov     [rsp+arg_0], rcx
0x14000d5ad  push    rbx
0x14000d5ae  push    rsi
0x14000d5af  push    rdi
0x14000d5b0  push    r14
0x14000d5b2  sub     rsp, 68h
0x14000d5b6  mov     edi, r8d
0x14000d5b9  mov     rbx, rcx
0x14000d5bc  xor     r14d, r14d
0x14000d5bf  cmp     [rcx], r14
0x14000d5c2  jz      loc_14000D66B
0x14000d5c8  mov     r9, [rcx+18h]
0x14000d5cc  test    r9, r9
0x14000d5cf  jz      loc_14000D66B
0x14000d5d5  mov     eax, [rcx+0Ch]
0x14000d5d8  cmp     r8d, eax
0x14000d5db  cmova   edi, eax
0x14000d5de  mov     r8d, edi; Size
0x14000d5e1  mov     ecx, [rcx+10h]
0x14000d5e4  add     rcx, r9; void *
0x14000d5e7  call    memmove
0x14000d5ec  add     [rbx+10h], edi
0x14000d5ef  sub     [rbx+0Ch], edi
0x14000d5f2  jmp     short loc_14000D666
0x14000d5f4  mov     r14d, eax
0x14000d5f7  mov     rdx, [rsp+88h+arg_0]
0x14000d5ff  mov     rax, [rdx]
0x14000d602  mov     rcx, [rax+10h]
0x14000d606  mov     esi, [rcx+18h]
0x14000d609  mov     rdi, [rcx+28h]
0x14000d60d  mov     rdx, [rdx+28h]
0x14000d611  add     rdx, 10h
0x14000d615  lea     rcx, [rsp+88h+var_38]
0x14000d61a  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000d61f  mov     rbx, [rax]
0x14000d622  lea     rcx, [rsp+88h+var_48]
0x14000d627  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000d62c  mov     [rsp+88h+var_58], r14d
0x14000d631  mov     [rsp+88h+var_60], esi
0x14000d635  mov     [rsp+88h+var_68], rdi
0x14000d63a  mov     r9, rbx
0x14000d63d  lea     r8, aStreamfaultbuf; "StreamFaultBuffer::UpdateUserBuffer() -"...
0x14000d644  mov     rdx, [rax]
0x14000d647  mov     ecx, 2
0x14000d64c  call    LogWrite
0x14000d651  lea     rcx, [rsp+88h+var_48]
0x14000d656  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x14000d65b  lea     rcx, [rsp+88h+var_38]
0x14000d660  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x14000d665  nop
0x14000d666  mov     eax, r14d
0x14000d669  jmp     short loc_14000D670
0x14000d66b  mov     eax, 0C00000E5h
0x14000d670  add     rsp, 68h
0x14000d674  pop     r14
0x14000d676  pop     rdi
0x14000d677  pop     rsi
0x14000d678  pop     rbx
0x14000d679  retn
```
