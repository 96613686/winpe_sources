# Smb2OplockSendComplete

- ea: `0x14002c6d0`
- end: `0x14002c7e9`
- name: `Smb2OplockSendComplete`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004960`
- `0x140005070`
- `0x14002bdac`
- `0x14002c6d0`
- `0x14002d4dc`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002c796`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002c796`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002c7b1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002c7b1`

## string_xrefs

- `0x14002c777`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Smb2OplockSendComplete(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  bool v5; // zf
  __int64 v6; // rbx
  __int64 v7; // rbx
  PSLIST_ENTRY v8; // rax
  int v10; // [rsp+20h] [rbp-18h]

  v3 = *(_QWORD *)(a3 + 24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      &WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids,
      *(_QWORD *)(v3 + 144),
      v3,
      a1);
  }
  if ( (int)(a1 + 0x80000000) < 0 || a1 == -1073741108 || *(_QWORD *)(v3 + 304) == v3 + 304 )
  {
    LODWORD(v8) = Smb2DereferenceOplockBreak((PVOID)v3);
  }
  else
  {
    v5 = *(_DWORD *)(v3 + 8) == 5;
    *(_QWORD *)(v3 + 48) = Smb2OplockRetryBreakSend;
    *(_DWORD *)(v3 + 72) = 0;
    if ( v5 )
    {
      LOBYTE(v10) = 1;
      LOBYTE(a2) = 1;
      SRV2_PERF_ENTER_EX(v3 + 584, a2, 391, "Srv2PostToThreadPool", v10);
    }
    v6 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 136LL);
    v7 = *(_QWORD *)(v6 + 8LL * KeGetCurrentNodeNumber() + 8);
    v8 = ExpInterlockedPushEntrySList((PSLIST_HEADER)v7, (PSLIST_ENTRY)(v3 + 32));
    if ( !v8 && *(_WORD *)(v7 + 66) )
      LODWORD(v8) = RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v7);
  }
  return (int)v8;
}

```

## disassembly

```asm
0x14002c6d0  mov     [rsp+arg_0], rbx
0x14002c6d5  push    rdi
0x14002c6d6  sub     rsp, 30h
0x14002c6da  mov     rdi, [r8+18h]
0x14002c6de  mov     ebx, ecx
0x14002c6e0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c6e7  lea     rax, WPP_GLOBAL_Control
0x14002c6ee  cmp     rcx, rax
0x14002c6f1  jz      short loc_14002C727
0x14002c6f3  test    dword ptr [rcx+2Ch], 400000h
0x14002c6fa  jz      short loc_14002C727
0x14002c6fc  cmp     byte ptr [rcx+29h], 2
0x14002c700  jb      short loc_14002C727
0x14002c702  mov     r9, [rdi+90h]
0x14002c709  lea     r8, WPP_cd88c939257b3d437242ae5a960c8d69_Traceguids
0x14002c710  mov     rcx, [rcx+18h]
0x14002c714  mov     edx, 1Ch
0x14002c719  mov     [rsp+38h+var_10], ebx
0x14002c71d  mov     [rsp+38h+var_18], rdi
0x14002c722  call    WPP_SF_qqD
0x14002c727  mov     ecx, 80000000h
0x14002c72c  lea     eax, [rbx+rcx]
0x14002c72f  test    ecx, eax
0x14002c731  jnz     loc_14002C7D5
0x14002c737  cmp     ebx, 0C00002CCh
0x14002c73d  jz      loc_14002C7D5
0x14002c743  lea     rax, [rdi+130h]
0x14002c74a  cmp     [rax], rax
0x14002c74d  jz      loc_14002C7D5
0x14002c753  cmp     dword ptr [rdi+8], 5
0x14002c757  lea     rax, Smb2OplockRetryBreakSend
0x14002c75e  mov     [rdi+30h], rax
0x14002c762  mov     dword ptr [rdi+48h], 0
0x14002c769  jnz     short loc_14002C78B
0x14002c76b  lea     rcx, [rdi+248h]
0x14002c772  mov     byte ptr [rsp+38h+var_18], 1
0x14002c777  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14002c77e  mov     r8d, 187h
0x14002c784  mov     dl, 1
0x14002c786  call    SRV2_PERF_ENTER_EX
0x14002c78b  mov     rax, [rdi+40h]
0x14002c78f  mov     rbx, [rax+88h]
0x14002c796  call    cs:__imp_KeGetCurrentNodeNumber
0x14002c79d  nop     dword ptr [rax+rax+00h]
0x14002c7a2  movzx   eax, ax
0x14002c7a5  lea     rdx, [rdi+20h]; ListEntry
0x14002c7a9  mov     rbx, [rbx+rax*8+8]
0x14002c7ae  mov     rcx, rbx; ListHead
0x14002c7b1  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002c7b8  nop     dword ptr [rax+rax+00h]
0x14002c7bd  test    rax, rax
0x14002c7c0  jnz     short loc_14002C7DD
0x14002c7c2  movzx   edx, word ptr [rbx+42h]
0x14002c7c6  cmp     ax, dx
0x14002c7c9  jz      short loc_14002C7DD
0x14002c7cb  mov     rcx, rbx
0x14002c7ce  call    RfspThreadPoolNodeWakeIdleWorker
0x14002c7d3  jmp     short loc_14002C7DD
0x14002c7d5  mov     rcx, rdi; P
0x14002c7d8  call    Smb2DereferenceOplockBreak
0x14002c7dd  mov     rbx, [rsp+38h+arg_0]
0x14002c7e2  add     rsp, 30h
0x14002c7e6  pop     rdi
0x14002c7e7  retn
```
