# CChangeApplier::GetFilterForgottenKnowledgeCompleteHandler(ulong)

- ea: `0x18003c750`
- end: `0x18003c891`
- name: `?GetFilterForgottenKnowledgeCompleteHandler@CChangeApplier@@AEAAJK@Z`
- size: `321`
- prototype: `__int64 __fastcall(CChangeApplier *this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180034e84`
- `0x180035724`
- `0x18003c750`
- `0x180046160`
- `0x180065570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c814`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c814`

## string_xrefs

- `0x18003c781`: `CChangeApplier::GetFilterForgottenKnowledgeCompleteHandler`
- `0x18003c86a`: `CChangeApplier::GetFilterForgottenKnowledgeCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetFilterForgottenKnowledgeCompleteHandler(CChangeApplier *this, int a2)
{
  unsigned int v4; // esi
  int inited; // ebx
  void *v6; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetFilterForgottenKnowledgeCompleteHandler");
  }
  v4 = a2 + 1;
  if ( v4 >= *((_DWORD *)this + 60) )
  {
    if ( v4 != *((_DWORD *)this + 60) )
    {
      inited = -2147217379;
      goto LABEL_19;
    }
    inited = CChangeApplier::ChangeState((__int64)this, 4);
    if ( inited >= 0 )
      inited = CSyncChangeBatchWrapper::InitCustomFilteringInfo(
                 *((_QWORD *)this + 62),
                 *((_QWORD *)this + 65),
                 *((_QWORD *)this + 33),
                 *((_DWORD *)this + 60),
                 *((_QWORD *)this + 32));
    v6 = (void *)*((_QWORD *)this + 34);
    if ( v6 )
      SetEvent(v6);
  }
  else
  {
    inited = CChangeApplier::ChangeState((__int64)this, 4);
    if ( inited >= 0 )
      inited = CChangeApplier::BeginGetFilterForgottenKnowledge(this, v4);
  }
  if ( inited != -2147467260 )
  {
    if ( inited >= 0 )
      goto LABEL_20;
LABEL_19:
    inited = CChangeApplier::SetError(this, *((struct ISyncCallback **)this + 50), inited);
    goto LABEL_20;
  }
  if ( !*((_DWORD *)this + 170) )
    goto LABEL_19;
  inited = 0;
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      120,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetFilterForgottenKnowledgeCompleteHandler",
      inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18003c750  push    rbx
0x18003c752  push    rbp
0x18003c753  push    rsi
0x18003c754  push    rdi
0x18003c755  sub     rsp, 38h
0x18003c759  mov     esi, edx
0x18003c75b  mov     rdi, rcx
0x18003c75e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c765  lea     rbp, WPP_GLOBAL_Control
0x18003c76c  cmp     rcx, rbp
0x18003c76f  jz      short loc_18003C799
0x18003c771  test    byte ptr [rcx+1Ch], 8
0x18003c775  jz      short loc_18003C799
0x18003c777  cmp     byte ptr [rcx+19h], 5
0x18003c77b  jb      short loc_18003C799
0x18003c77d  mov     rcx, [rcx+10h]
0x18003c781  lea     r9, aCchangeapplier_44; "CChangeApplier::GetFilterForgottenKnowl"...
0x18003c788  mov     edx, 77h ; 'w'
0x18003c78d  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003c794  call    WPP_SF_s
0x18003c799  inc     esi
0x18003c79b  cmp     esi, [rdi+0F0h]
0x18003c7a1  jnb     short loc_18003C7C4
0x18003c7a3  mov     edx, 4
0x18003c7a8  mov     rcx, rdi
0x18003c7ab  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x18003c7b0  mov     ebx, eax
0x18003c7b2  test    eax, eax
0x18003c7b4  js      short loc_18003C81A
0x18003c7b6  mov     edx, esi; unsigned int
0x18003c7b8  mov     rcx, rdi; this
0x18003c7bb  call    ?BeginGetFilterForgottenKnowledge@CChangeApplier@@AEAAJK@Z; CChangeApplier::BeginGetFilterForgottenKnowledge(ulong)
0x18003c7c0  mov     ebx, eax
0x18003c7c2  jmp     short loc_18003C81A
0x18003c7c4  jnz     short loc_18003C835
0x18003c7c6  mov     edx, 4
0x18003c7cb  mov     rcx, rdi
0x18003c7ce  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x18003c7d3  mov     ebx, eax
0x18003c7d5  test    eax, eax
0x18003c7d7  js      short loc_18003C808
0x18003c7d9  mov     rax, [rdi+100h]
0x18003c7e0  mov     r9d, [rdi+0F0h]
0x18003c7e7  mov     r8, [rdi+108h]
0x18003c7ee  mov     rdx, [rdi+208h]
0x18003c7f5  mov     rcx, [rdi+1F0h]
0x18003c7fc  mov     [rsp+58h+var_38], rax
0x18003c801  call    ?InitCustomFilteringInfo@CSyncChangeBatchWrapper@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAV?$RefCountedHashTable@KK@@@Z; CSyncChangeBatchWrapper::InitCustomFilteringInfo(ISyncKnowledge *,IEnumItemIds *,ulong,RefCountedHashTable<ulong,ulong> *)
0x18003c806  mov     ebx, eax
0x18003c808  mov     rcx, [rdi+110h]; hEvent
0x18003c80f  test    rcx, rcx
0x18003c812  jz      short loc_18003C81A
0x18003c814  call    cs:__imp_SetEvent
0x18003c81a  cmp     ebx, 80004004h
0x18003c820  jnz     short loc_18003C82F
0x18003c822  cmp     dword ptr [rdi+2A8h], 0
0x18003c829  jz      short loc_18003C83A
0x18003c82b  xor     ebx, ebx
0x18003c82d  jmp     short loc_18003C84E
0x18003c82f  test    ebx, ebx
0x18003c831  jns     short loc_18003C84E
0x18003c833  jmp     short loc_18003C83A
0x18003c835  mov     ebx, 8004101Dh
0x18003c83a  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x18003c841  mov     r8d, ebx; int
0x18003c844  mov     rcx, rdi; this
0x18003c847  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18003c84c  mov     ebx, eax
0x18003c84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c855  cmp     rcx, rbp
0x18003c858  jz      short loc_18003C886
0x18003c85a  test    byte ptr [rcx+1Ch], 8
0x18003c85e  jz      short loc_18003C886
0x18003c860  cmp     byte ptr [rcx+19h], 5
0x18003c864  jb      short loc_18003C886
0x18003c866  mov     rcx, [rcx+10h]
0x18003c86a  lea     r9, aCchangeapplier_44; "CChangeApplier::GetFilterForgottenKnowl"...
0x18003c871  mov     edx, 78h ; 'x'
0x18003c876  mov     dword ptr [rsp+58h+var_38], ebx
0x18003c87a  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003c881  call    WPP_SF_sD
0x18003c886  mov     eax, ebx
0x18003c888  add     rsp, 38h
0x18003c88c  pop     rdi
0x18003c88d  pop     rsi
0x18003c88e  pop     rbp
0x18003c88f  pop     rbx
0x18003c890  retn
```
