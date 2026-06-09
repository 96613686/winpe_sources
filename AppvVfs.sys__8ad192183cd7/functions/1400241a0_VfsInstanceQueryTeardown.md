# VfsInstanceQueryTeardown

- ea: `0x1400241a0`
- end: `0x140024243`
- name: `VfsInstanceQueryTeardown`
- size: `163`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140012acc`
- `0x1400241a0`

## import_xrefs

- `FLTMGR!FltGetInstanceContext` at `0x1400241bf`
- `FLTMGR!FltGetInstanceContext` at `0x1400241bf`
- `FLTMGR!FltReleaseContext` at `0x140024233`
- `FLTMGR!FltReleaseContext` at `0x14002602b`
- `FLTMGR!FltReleaseContext` at `0x140024233`
- `FLTMGR!FltReleaseContext` at `0x14002602b`

## string_xrefs

- `0x140024218`: `VfsInstanceQueryTeardown() - VFS volume detach is not allowed for volume: %wZ\n because of opened files: %d`

## pseudocode

```c
__int64 __fastcall VfsInstanceQueryTeardown(__int64 a1)
{
  NTSTATUS InstanceContext; // eax
  unsigned int v3; // ebx
  signed __int32 v5; // eax
  NTSTATUS v6; // [rsp+20h] [rbp-18h]
  signed __int32 v7; // [rsp+20h] [rbp-18h]
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+8h] BYREF

  Context = 0;
  InstanceContext = FltGetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), &Context);
  v3 = InstanceContext;
  if ( InstanceContext >= 0 )
  {
    v5 = _InterlockedCompareExchange((volatile signed __int32 *)Context + 6, 0, 0);
    if ( v5 )
    {
      v7 = v5;
      LogWrite(
        3,
        0,
        L"VfsInstanceQueryTeardown() - VFS volume detach is not allowed for volume: %wZ\n because of opened files: %d",
        (char *)Context + 8,
        v7);
      v3 = -1071906800;
    }
    FltReleaseContext(Context);
    return v3;
  }
  else
  {
    v6 = InstanceContext;
    LogWrite(
      1,
      0,
      L"VfsInstanceQueryTeardown() - Failed to get instance context for instance: %p\n Status: 0x%08X",
      *(_QWORD *)(a1 + 24),
      v6);
    return 3223060496LL;
  }
}

```

## disassembly

```asm
0x1400241a0  mov     [rsp+arg_8], rbx
0x1400241a5  push    rdi
0x1400241a6  sub     rsp, 30h
0x1400241aa  mov     rdi, rcx
0x1400241ad  mov     [rsp+38h+Context], 0
0x1400241b6  lea     rdx, [rsp+38h+Context]; Context
0x1400241bb  mov     rcx, [rcx+18h]; Instance
0x1400241bf  call    cs:__imp_FltGetInstanceContext
0x1400241c6  nop     dword ptr [rax+rax+00h]
0x1400241cb  mov     ebx, eax
0x1400241cd  test    eax, eax
0x1400241cf  jns     short loc_1400241FB
0x1400241d1  mov     [rsp+38h+var_18], eax
0x1400241d5  mov     r9, [rdi+18h]
0x1400241d9  lea     r8, aVfsinstanceque; "VfsInstanceQueryTeardown() - Failed to "...
0x1400241e0  xor     edx, edx
0x1400241e2  lea     ecx, [rdx+1]
0x1400241e5  call    LogWrite
0x1400241ea  mov     eax, 0C01C0010h
0x1400241ef  mov     rbx, [rsp+38h+arg_8]
0x1400241f4  add     rsp, 30h
0x1400241f8  pop     rdi
0x1400241f9  retn
0x1400241fb  mov     rdx, [rsp+38h+Context]
0x140024200  xor     ecx, ecx
0x140024202  xor     eax, eax
0x140024204  lock cmpxchg [rdx+18h], ecx
0x140024209  jz      short loc_14002422E
0x14002420b  mov     r9, [rsp+38h+Context]
0x140024210  add     r9, 8
0x140024214  mov     [rsp+38h+var_18], eax
0x140024218  lea     r8, aVfsinstanceque_0; "VfsInstanceQueryTeardown() - VFS volume"...
0x14002421f  xor     edx, edx
0x140024221  lea     ecx, [rdx+3]
0x140024224  call    LogWrite
0x140024229  mov     ebx, 0C01C0010h
0x14002422e  mov     rcx, [rsp+38h+Context]; Context
0x140024233  call    cs:__imp_FltReleaseContext
0x14002423a  nop     dword ptr [rax+rax+00h]
0x14002423f  mov     eax, ebx
0x140024241  jmp     short loc_1400241EF
0x14002601e  push    rbp
0x140026020  sub     rsp, 30h
0x140026024  mov     rbp, rdx
0x140026027  mov     rcx, [rbp+40h]; Context
0x14002602b  call    cs:__imp_FltReleaseContext
0x140026032  nop     dword ptr [rax+rax+00h]
0x140026037  nop
0x140026038  add     rsp, 30h
0x14002603c  pop     rbp
0x14002603d  retn
```
