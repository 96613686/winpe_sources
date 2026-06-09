# ATL::CRegObject::~CRegObject(void)

- ea: `0x18000407c`
- end: `0x180004118`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004250`
- `0x180006bcc`
- `0x180006ef4`

## callees

- `0x18000407c`
- `0x180004e68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800040dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800040f3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800040dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800040f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040c7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800040b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800040b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000409f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000409f`

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
0x18000407c  mov     [rsp+arg_0], rbx
0x180004081  mov     [rsp+arg_8], rsi
0x180004086  push    rdi
0x180004087  sub     rsp, 20h
0x18000408b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180004092  mov     rbx, rcx
0x180004095  lea     rsi, [rcx+20h]
0x180004099  mov     [rcx], rax
0x18000409c  mov     rcx, rsi; lpCriticalSection
0x18000409f  call    cs:__imp_EnterCriticalSection
0x1800040a5  lea     rdi, [rbx+8]
0x1800040a9  mov     rcx, rdi; this
0x1800040ac  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800040b1  mov     rcx, rsi; lpCriticalSection
0x1800040b4  call    cs:__imp_LeaveCriticalSection
0x1800040ba  cmp     byte ptr [rsi+28h], 0
0x1800040be  jz      short loc_1800040CD
0x1800040c0  mov     rcx, rsi; lpCriticalSection
0x1800040c3  mov     byte ptr [rsi+28h], 0
0x1800040c7  call    cs:__imp_DeleteCriticalSection
0x1800040cd  mov     rcx, rdi; this
0x1800040d0  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800040d5  mov     rcx, [rdi]; Block
0x1800040d8  test    rcx, rcx
0x1800040db  jz      short loc_1800040EA
0x1800040dd  call    cs:__imp_free
0x1800040e3  mov     qword ptr [rdi], 0
0x1800040ea  mov     rcx, [rbx+10h]; Block
0x1800040ee  test    rcx, rcx
0x1800040f1  jz      short loc_180004101
0x1800040f3  call    cs:__imp_free
0x1800040f9  mov     qword ptr [rbx+10h], 0
0x180004101  mov     rsi, [rsp+28h+arg_8]
0x180004106  mov     dword ptr [rbx+18h], 0
0x18000410d  mov     rbx, [rsp+28h+arg_0]
0x180004112  add     rsp, 20h
0x180004116  pop     rdi
0x180004117  retn
```
