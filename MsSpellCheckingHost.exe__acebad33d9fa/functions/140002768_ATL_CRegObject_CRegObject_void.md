# ATL::CRegObject::~CRegObject(void)

- ea: `0x140002768`
- end: `0x140002804`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002850`
- `0x140005f04`

## callees

- `0x140002768`
- `0x140003bb0`

## import_xrefs

- `msvcrt!free` at `0x1400027c9`
- `msvcrt!free` at `0x1400027df`
- `msvcrt!free` at `0x1400027c9`
- `msvcrt!free` at `0x1400027df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400027a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400027a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000278b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000278b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400027b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400027b3`

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
0x140002768  mov     [rsp+arg_0], rbx
0x14000276d  mov     [rsp+arg_8], rsi
0x140002772  push    rdi
0x140002773  sub     rsp, 20h
0x140002777  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000277e  mov     rbx, rcx
0x140002781  lea     rsi, [rcx+20h]
0x140002785  mov     [rcx], rax
0x140002788  mov     rcx, rsi; lpCriticalSection
0x14000278b  call    cs:__imp_EnterCriticalSection
0x140002791  lea     rdi, [rbx+8]
0x140002795  mov     rcx, rdi; this
0x140002798  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000279d  mov     rcx, rsi; lpCriticalSection
0x1400027a0  call    cs:__imp_LeaveCriticalSection
0x1400027a6  cmp     byte ptr [rsi+28h], 0
0x1400027aa  jz      short loc_1400027B9
0x1400027ac  mov     rcx, rsi; lpCriticalSection
0x1400027af  mov     byte ptr [rsi+28h], 0
0x1400027b3  call    cs:__imp_DeleteCriticalSection
0x1400027b9  mov     rcx, rdi; this
0x1400027bc  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1400027c1  mov     rcx, [rdi]; Block
0x1400027c4  test    rcx, rcx
0x1400027c7  jz      short loc_1400027D6
0x1400027c9  call    cs:__imp_free
0x1400027cf  mov     qword ptr [rdi], 0
0x1400027d6  mov     rcx, [rbx+10h]; Block
0x1400027da  test    rcx, rcx
0x1400027dd  jz      short loc_1400027ED
0x1400027df  call    cs:__imp_free
0x1400027e5  mov     qword ptr [rbx+10h], 0
0x1400027ed  mov     rsi, [rsp+28h+arg_8]
0x1400027f2  mov     dword ptr [rbx+18h], 0
0x1400027f9  mov     rbx, [rsp+28h+arg_0]
0x1400027fe  add     rsp, 20h
0x140002802  pop     rdi
0x140002803  retn
```
