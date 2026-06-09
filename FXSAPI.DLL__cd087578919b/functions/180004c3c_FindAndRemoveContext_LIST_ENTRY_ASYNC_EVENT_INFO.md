# FindAndRemoveContext(_LIST_ENTRY *,_ASYNC_EVENT_INFO *)

- ea: `0x180004c3c`
- end: `0x180004cac`
- name: `?FindAndRemoveContext@@YAXPEAU_LIST_ENTRY@@PEAU_ASYNC_EVENT_INFO@@@Z`
- size: `112`
- prototype: `void __fastcall(struct _LIST_ENTRY *, struct _ASYNC_EVENT_INFO *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004394`
- `0x18000a140`
- `0x18000aa00`

## callees

- `0x180004c3c`
- `0x180004cb4`
- `0x18000abe4`
- `0x18002bb58`

## pseudocode

```c
void __fastcall FindAndRemoveContext(struct _LIST_ENTRY *a1, struct _ASYNC_EVENT_INFO *a2)
{
  struct _CONTEXT_NODE *ContextNode; // rax
  _QWORD *v3; // rcx
  __int64 v4; // rdx

  ContextNode = FindContextNode(a1, a2);
  if ( ContextNode )
  {
    v3 = (_QWORD *)*((_QWORD *)ContextNode + 1);
    v4 = *(_QWORD *)ContextNode;
    *v3 = *(_QWORD *)ContextNode;
    *(_QWORD *)(v4 + 8) = v3;
    *(_QWORD *)ContextNode = 0;
    *((_QWORD *)ContextNode + 1) = 0;
    pMemFree(ContextNode);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x180004c3c  sub     rsp, 28h
0x180004c40  call    ?FindContextNode@@YAPEAU_CONTEXT_NODE@@PEAU_LIST_ENTRY@@PEAU_ASYNC_EVENT_INFO@@@Z; FindContextNode(_LIST_ENTRY *,_ASYNC_EVENT_INFO *)
0x180004c45  test    rax, rax
0x180004c48  jz      short loc_180004CA6
0x180004c4a  mov     rcx, [rax+8]
0x180004c4e  mov     rdx, [rax]
0x180004c51  mov     [rcx], rdx
0x180004c54  mov     [rdx+8], rcx
0x180004c58  mov     rcx, rax; lpMem
0x180004c5b  mov     qword ptr [rax], 0
0x180004c62  mov     qword ptr [rax+8], 0
0x180004c6a  call    pMemFree
0x180004c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c76  lea     rax, WPP_GLOBAL_Control
0x180004c7d  cmp     rcx, rax
0x180004c80  jz      short loc_180004CA6
0x180004c82  test    dword ptr [rcx+1Ch], 1000h
0x180004c89  jz      short loc_180004CA6
0x180004c8b  cmp     byte ptr [rcx+19h], 5
0x180004c8f  jb      short loc_180004CA6
0x180004c91  mov     rcx, [rcx+10h]
0x180004c95  lea     r8, WPP_152912f6797533292abcfca723f93957_Traceguids
0x180004c9c  mov     edx, 0Ch
0x180004ca1  call    WPP_SF_
0x180004ca6  add     rsp, 28h
0x180004caa  retn
```
