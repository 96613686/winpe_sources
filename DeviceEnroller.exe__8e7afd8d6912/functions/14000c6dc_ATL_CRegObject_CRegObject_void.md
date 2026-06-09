# ATL::CRegObject::~CRegObject(void)

- ea: `0x14000c6dc`
- end: `0x14000c778`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cfb0`
- `0x14001903c`
- `0x140019364`

## callees

- `0x14000c6dc`
- `0x14000e570`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c73d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c753`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c73d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000c753`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c6ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c6ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c714`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c714`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000c727`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000c727`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  void **v3; // rdi
  void *v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void **)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  if ( *v3 )
  {
    free(*v3);
    *v3 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x14000c6dc  mov     [rsp+arg_0], rbx
0x14000c6e1  mov     [rsp+arg_8], rsi
0x14000c6e6  push    rdi
0x14000c6e7  sub     rsp, 20h
0x14000c6eb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000c6f2  mov     rbx, rcx
0x14000c6f5  lea     rsi, [rcx+20h]
0x14000c6f9  mov     [rcx], rax
0x14000c6fc  mov     rcx, rsi; lpCriticalSection
0x14000c6ff  call    cs:__imp_EnterCriticalSection
0x14000c705  lea     rdi, [rbx+8]
0x14000c709  mov     rcx, rdi; this
0x14000c70c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000c711  mov     rcx, rsi; lpCriticalSection
0x14000c714  call    cs:__imp_LeaveCriticalSection
0x14000c71a  cmp     byte ptr [rsi+28h], 0
0x14000c71e  jz      short loc_14000C72D
0x14000c720  mov     rcx, rsi; lpCriticalSection
0x14000c723  mov     byte ptr [rsi+28h], 0
0x14000c727  call    cs:__imp_DeleteCriticalSection
0x14000c72d  mov     rcx, rdi; this
0x14000c730  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000c735  mov     rcx, [rdi]; Block
0x14000c738  test    rcx, rcx
0x14000c73b  jz      short loc_14000C74A
0x14000c73d  call    cs:__imp_free
0x14000c743  mov     qword ptr [rdi], 0
0x14000c74a  mov     rcx, [rbx+10h]; Block
0x14000c74e  test    rcx, rcx
0x14000c751  jz      short loc_14000C761
0x14000c753  call    cs:__imp_free
0x14000c759  mov     qword ptr [rbx+10h], 0
0x14000c761  mov     rsi, [rsp+28h+arg_8]
0x14000c766  mov     dword ptr [rbx+18h], 0
0x14000c76d  mov     rbx, [rsp+28h+arg_0]
0x14000c772  add     rsp, 20h
0x14000c776  pop     rdi
0x14000c777  retn
```
