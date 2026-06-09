# CRemoteReadCtx::~CRemoteReadCtx(void)

- ea: `0x180086508`
- end: `0x180086618`
- name: `??1CRemoteReadCtx@@EEAA@XZ`
- size: `272`
- prototype: `void __fastcall(CRemoteReadCtx *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800866c0`

## callees

- `0x18001a790`
- `0x1800404ac`
- `0x1800852d4`
- `0x180086508`
- `0x180088bb0`
- `0x18008b63c`

## import_xrefs

- `msvcrt!free` at `0x180086599`
- `msvcrt!free` at `0x1800865e1`
- `msvcrt!free` at `0x180086599`
- `msvcrt!free` at `0x1800865e1`
- `KERNEL32!DeleteCriticalSection` at `0x1800865b7`
- `KERNEL32!DeleteCriticalSection` at `0x1800865ff`
- `KERNEL32!DeleteCriticalSection` at `0x1800865b7`
- `KERNEL32!DeleteCriticalSection` at `0x1800865ff`

## pseudocode

```c
void __fastcall CRemoteReadCtx::~CRemoteReadCtx(CRemoteReadCtx *this)
{
  CContextHandler *v2; // rcx
  char v3; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CRemoteReadCtx::`vftable';
  v2 = (CContextHandler *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    WPP_SF_qSq(*((_QWORD *)WPP_GLOBAL_Control + 22), *(wchar_t **)(*((_QWORD *)this + 4) + 24LL), *((_QWORD *)this + 3));
  if ( *((_DWORD *)this + 33) )
    CContextHandler::RemoveContext(v2, this);
  std::_Tree<std::_Tmap_traits<unsigned long,R<CRRCursor>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,R<CRRCursor>>>,0>>::erase(
    (char *)this + 400,
    &v3,
    **((_QWORD **)this + 51),
    *((_QWORD *)this + 51));
  free(*((void **)this + 51));
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  std::_Tree<std::_Tmap_traits<unsigned long,CEndReceiveCtx *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CEndReceiveCtx *>>,0>>::erase(
    (char *)this + 256,
    &v3,
    **((_QWORD **)this + 33),
    *((_QWORD *)this + 33));
  free(*((void **)this + 33));
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  CTX_OPENREMOTE_BASE::~CTX_OPENREMOTE_BASE(this);
}

```

## disassembly

```asm
0x180086508  mov     [rsp+arg_8], rbx
0x18008650d  push    rdi
0x18008650e  sub     rsp, 30h
0x180086512  mov     rdi, rcx
0x180086515  lea     rax, ??_7CRemoteReadCtx@@6B@; const CRemoteReadCtx::`vftable'
0x18008651c  mov     [rcx], rax
0x18008651f  lea     rax, WPP_GLOBAL_Control
0x180086526  mov     rcx, cs:WPP_GLOBAL_Control
0x18008652d  cmp     rcx, rax
0x180086530  jz      short loc_180086565
0x180086532  test    byte ptr [rcx+0BCh], 4
0x180086539  jz      short loc_180086565
0x18008653b  mov     r8, [rdi+20h]
0x18008653f  mov     edx, 3Ah ; ':'
0x180086544  mov     rax, [rdi+18h]
0x180086548  mov     qword ptr [rsp+38h+var_10], rax; char
0x18008654d  mov     rax, [r8+18h]
0x180086551  mov     [rsp+38h+var_18], rax; wchar_t *
0x180086556  mov     r9, rdi
0x180086559  mov     rcx, [rcx+0B0h]; LoggerHandle
0x180086560  call    WPP_SF_qSq
0x180086565  cmp     dword ptr [rdi+84h], 0
0x18008656c  jz      short loc_180086576
0x18008656e  mov     rdx, rdi; struct CRemoteReadCtx *
0x180086571  call    ?RemoveContext@CContextHandler@@QEAAJPEAVCRemoteReadCtx@@@Z; CContextHandler::RemoveContext(CRemoteReadCtx *)
0x180086576  lea     rbx, [rdi+190h]
0x18008657d  mov     r8, [rbx+8]
0x180086581  mov     r9, r8
0x180086584  mov     r8, [r8]
0x180086587  lea     rdx, [rsp+38h+arg_0]
0x18008658c  mov     rcx, rbx
0x18008658f  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$R@VCRRCursor@@@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$R@VCRRCursor@@@@@std@@@3@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z; std::_Tree<std::_Tmap_traits<ulong,R<CRRCursor>,std::less<ulong>,std::allocator<std::pair<ulong const,R<CRRCursor>>>,0>>::erase(std::_Tree<std::_Tmap_traits<ulong,R<CRRCursor>,std::less<ulong>,std::allocator<std::pair<ulong const,R<CRRCursor>>>,0>>::iterator,std::_Tree<std::_Tmap_traits<ulong,R<CRRCursor>,std::less<ulong>,std::allocator<std::pair<ulong const,R<CRRCursor>>>,0>>::iterator)
0x180086594  nop
0x180086595  mov     rcx, [rbx+8]; Block
0x180086599  call    cs:__imp_free
0x18008659f  nop
0x1800865a0  mov     qword ptr [rbx+8], 0
0x1800865a8  mov     qword ptr [rbx+10h], 0
0x1800865b0  lea     rcx, [rdi+168h]; lpCriticalSection
0x1800865b7  call    cs:__imp_DeleteCriticalSection
0x1800865bd  nop
0x1800865be  lea     rbx, [rdi+100h]
0x1800865c5  mov     r8, [rbx+8]
0x1800865c9  mov     r9, r8
0x1800865cc  mov     r8, [r8]
0x1800865cf  lea     rdx, [rsp+38h+arg_0]
0x1800865d4  mov     rcx, rbx
0x1800865d7  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAVCEndReceiveCtx@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCEndReceiveCtx@@@std@@@3@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z; std::_Tree<std::_Tmap_traits<ulong,CEndReceiveCtx *,std::less<ulong>,std::allocator<std::pair<ulong const,CEndReceiveCtx *>>,0>>::erase(std::_Tree<std::_Tmap_traits<ulong,CEndReceiveCtx *,std::less<ulong>,std::allocator<std::pair<ulong const,CEndReceiveCtx *>>,0>>::iterator,std::_Tree<std::_Tmap_traits<ulong,CEndReceiveCtx *,std::less<ulong>,std::allocator<std::pair<ulong const,CEndReceiveCtx *>>,0>>::iterator)
0x1800865dc  nop
0x1800865dd  mov     rcx, [rbx+8]; Block
0x1800865e1  call    cs:__imp_free
0x1800865e7  nop
0x1800865e8  mov     qword ptr [rbx+8], 0
0x1800865f0  mov     qword ptr [rbx+10h], 0
0x1800865f8  lea     rcx, [rdi+0D8h]; lpCriticalSection
0x1800865ff  call    cs:__imp_DeleteCriticalSection
0x180086605  nop
0x180086606  mov     rcx, rdi; this
0x180086609  mov     rbx, [rsp+38h+arg_8]
0x18008660e  add     rsp, 30h
0x180086612  pop     rdi
0x180086613  jmp     ??1CTX_OPENREMOTE_BASE@@MEAA@XZ; CTX_OPENREMOTE_BASE::~CTX_OPENREMOTE_BASE(void)
```
