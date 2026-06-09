# CNetworkExplorerFolderViewCB::UpdateProgressBar(void)

- ea: `0x1800066f4`
- end: `0x180006742`
- name: `?UpdateProgressBar@CNetworkExplorerFolderViewCB@@QEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(CNetworkExplorerFolderViewCB *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800066c0`

## callees

- `0x1800066f4`
- `0x18000693c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::UpdateProgressBar(CNetworkExplorerFolderViewCB *this)
{
  int v2; // ebx
  int v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 8) + 96LL))(*((_QWORD *)this + 8), &v4);
  if ( v2 < 0 || v4 )
    CNetworkExplorerFolderViewCB::_StopProgressBar(this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800066f4  mov     [rsp+arg_8], rbx
0x1800066f9  push    rdi
0x1800066fa  sub     rsp, 20h
0x1800066fe  mov     rdi, rcx
0x180006701  mov     [rsp+28h+arg_0], 0
0x180006709  mov     rcx, [rcx+40h]
0x18000670d  lea     rdx, [rsp+28h+arg_0]
0x180006712  mov     rax, [rcx]
0x180006715  mov     rax, [rax+60h]
0x180006719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000671e  mov     ebx, eax
0x180006720  test    eax, eax
0x180006722  js      short loc_180006738
0x180006724  cmp     [rsp+28h+arg_0], 0
0x180006729  jnz     short loc_180006738
0x18000672b  mov     eax, ebx
0x18000672d  mov     rbx, [rsp+28h+arg_8]
0x180006732  add     rsp, 20h
0x180006736  pop     rdi
0x180006737  retn
0x180006738  mov     rcx, rdi; this
0x18000673b  call    ?_StopProgressBar@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StopProgressBar(void)
0x180006740  jmp     short loc_18000672B
```
