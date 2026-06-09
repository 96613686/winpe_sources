# Srv2DereferenceConnection

- ea: `0x14000ae60`
- end: `0x14000af4f`
- name: `Srv2DereferenceConnection`
- size: `239`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x140006218`
- `0x14000ac30`
- `0x14000ad08`
- `0x14000af58`
- `0x14000b3f0`
- `0x14000bbb8`
- `0x140015af8`
- `0x140016368`
- `0x1400220c0`
- `0x14002c4a0`
- `0x14002f0a4`
- `0x140085260`
- `0x14008fab8`
- `0x140094870`

## callees

- `0x140004960`
- `0x140005070`
- `0x14000ae60`
- `0x140060320`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000aee1`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000aee1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000af2e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000af2e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000aefc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000aefc`

## string_xrefs

- `0x14000aec2`: `Srv2PostToThreadPool`

## pseudocode

```c
int __fastcall Srv2DereferenceConnection(char *P)
{
  PSLIST_ENTRY v2; // rax
  bool v3; // zf
  __int64 v4; // rbx
  union _SLIST_HEADER *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8

  v2 = (PSLIST_ENTRY)_InterlockedDecrement64((volatile signed __int64 *)P);
  if ( v2 == (PSLIST_ENTRY)-1LL )
  {
    __int2c();
  }
  else if ( !v2 )
  {
    if ( KeGetCurrentIrql() )
    {
      v3 = *((_DWORD *)P + 2) == 5;
      *((_QWORD *)P + 6) = Srv2FreeConnection;
      *((_DWORD *)P + 18) = 0;
      if ( v3 )
      {
        LOBYTE(v6) = 1;
        SRV2_PERF_ENTER_EX(P + 584, v6, 391, "Srv2PostToThreadPool", 1);
      }
      v4 = *(_QWORD *)(*((_QWORD *)P + 8) + 136LL);
      v5 = *(union _SLIST_HEADER **)(v4 + 8LL * KeGetCurrentNodeNumber() + 8);
      v2 = ExpInterlockedPushEntrySList(v5, (PSLIST_ENTRY)P + 2);
      if ( !v2 && *((_WORD *)&v5[4].Header8 + 1) )
        LODWORD(v2) = RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v5);
    }
    else
    {
      LODWORD(v2) = Srv2FreeConnection(P, v6, v7);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x14000ae60  push    rdi
0x14000ae62  sub     rsp, 30h
0x14000ae66  mov     rdi, rcx
0x14000ae69  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000ae70  lock xadd [rcx], rax
0x14000ae75  dec     rax
0x14000ae78  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ae7c  jnb     loc_14000AF27
0x14000ae82  test    rax, rax
0x14000ae85  jz      loc_14000AF2E
0x14000ae8b  add     rsp, 30h
0x14000ae8f  pop     rdi
0x14000ae90  retn
0x14000ae92  mov     rbx, [rsp+38h+arg_0]
0x14000ae97  jmp     short loc_14000AE8B
0x14000ae99  cmp     dword ptr [rdi+8], 5
0x14000ae9d  lea     rax, Srv2FreeConnection
0x14000aea4  mov     [rdi+30h], rax
0x14000aea8  mov     [rsp+38h+arg_0], rbx
0x14000aead  mov     dword ptr [rdi+48h], 0
0x14000aeb4  jnz     short loc_14000AED6
0x14000aeb6  lea     rcx, [rdi+248h]
0x14000aebd  mov     [rsp+38h+var_18], 1
0x14000aec2  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14000aec9  mov     r8d, 187h
0x14000aecf  mov     dl, 1
0x14000aed1  call    SRV2_PERF_ENTER_EX
0x14000aed6  mov     rax, [rdi+40h]
0x14000aeda  mov     rbx, [rax+88h]
0x14000aee1  call    cs:__imp_KeGetCurrentNodeNumber
0x14000aee8  nop     dword ptr [rax+rax+00h]
0x14000aeed  movzx   eax, ax
0x14000aef0  lea     rdx, [rdi+20h]; ListEntry
0x14000aef4  mov     rbx, [rbx+rax*8+8]
0x14000aef9  mov     rcx, rbx; ListHead
0x14000aefc  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000af03  nop     dword ptr [rax+rax+00h]
0x14000af08  test    rax, rax
0x14000af0b  jnz     short loc_14000AE92
0x14000af0d  movzx   edx, word ptr [rbx+42h]
0x14000af11  cmp     ax, dx
0x14000af14  jz      loc_14000AE92
0x14000af1a  mov     rcx, rbx
0x14000af1d  call    RfspThreadPoolNodeWakeIdleWorker
0x14000af22  jmp     loc_14000AE92
0x14000af27  int     2Ch; Windows NT - assertion failure
0x14000af29  jmp     loc_14000AE8B
0x14000af2e  call    cs:__imp_KeGetCurrentIrql
0x14000af35  nop     dword ptr [rax+rax+00h]
0x14000af3a  test    al, al
0x14000af3c  jnz     loc_14000AE99
0x14000af42  mov     rcx, rdi; P
0x14000af45  call    Srv2FreeConnection
0x14000af4a  jmp     loc_14000AE8B
```
