# utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::~vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>(void)

- ea: `0x140001ed0`
- end: `0x140001f3e`
- name: `??1?$vector@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@V?$allocator@V?$unique_ptr@U_URB@@U?$default_delete@U_URB@@@utl@@@utl@@@2@@utl@@QEAA@XZ`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400021f0`
- `0x140002944`

## callees

- `0x140001ed0`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x140001f08`
- `ntoskrnl!ExFreePool` at `0x140001f21`
- `ntoskrnl!ExFreePool` at `0x140001f08`
- `ntoskrnl!ExFreePool` at `0x140001f21`

## pseudocode

```c
void __fastcall utl::vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>::~vector<utl::unique_ptr<_URB,utl::default_delete<_URB>>,utl::allocator<utl::unique_ptr<_URB,utl::default_delete<_URB>>>>(
        __int64 a1)
{
  _QWORD *v1; // rsi
  __int64 v3; // rbx
  __int64 v4; // rbx
  void *v5; // rcx

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    v4 = v3 >> 3;
    while ( v4 )
    {
      v5 = (void *)v1[--v4];
      if ( v5 )
        ExFreePool(v5);
    }
    if ( *(_QWORD *)a1 )
      ExFreePool(*(PVOID *)a1);
  }
}

```

## disassembly

```asm
0x140001ed0  mov     [rsp+arg_0], rbx
0x140001ed5  mov     [rsp+arg_8], rsi
0x140001eda  push    rdi
0x140001edb  sub     rsp, 20h
0x140001edf  mov     rsi, [rcx]
0x140001ee2  mov     rdi, rcx
0x140001ee5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140001ee9  jz      short loc_140001F2D
0x140001eeb  mov     rbx, [rcx+8]
0x140001eef  sub     rbx, rsi
0x140001ef2  mov     [rcx+8], rsi
0x140001ef6  sar     rbx, 3
0x140001efa  jmp     short loc_140001F14
0x140001efc  dec     rbx
0x140001eff  mov     rcx, [rsi+rbx*8]; P
0x140001f03  test    rcx, rcx
0x140001f06  jz      short loc_140001F14
0x140001f08  call    cs:__imp_ExFreePool
0x140001f0f  nop     dword ptr [rax+rax+00h]
0x140001f14  test    rbx, rbx
0x140001f17  jnz     short loc_140001EFC
0x140001f19  mov     rcx, [rdi]; P
0x140001f1c  test    rcx, rcx
0x140001f1f  jz      short loc_140001F2D
0x140001f21  call    cs:__imp_ExFreePool
0x140001f28  nop     dword ptr [rax+rax+00h]
0x140001f2d  mov     rbx, [rsp+28h+arg_0]
0x140001f32  mov     rsi, [rsp+28h+arg_8]
0x140001f37  add     rsp, 20h
0x140001f3b  pop     rdi
0x140001f3c  retn
```
