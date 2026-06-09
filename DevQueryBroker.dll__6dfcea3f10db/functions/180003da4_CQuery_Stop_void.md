# CQuery::Stop(void)

- ea: `0x180003da4`
- end: `0x180003e48`
- name: `?Stop@CQuery@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000314c`
- `0x1800031f4`
- `0x180003330`
- `0x180004400`
- `0x180004440`

## callees

- `0x1800039a0`
- `0x180003da4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dd7`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180003dbf`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180003dbf`

## pseudocode

```c
void __fastcall CQuery::Stop(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  _QWORD *p_Type; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v4; // rax

  if ( this[1].LockSemaphore )
  {
    DevCloseObjectQuery();
    this[1].LockSemaphore = 0;
  }
  EnterCriticalSection(this + 4);
  LODWORD(this[5].DebugInfo) = 1;
  v2 = this + 3;
  while ( 1 )
  {
    p_Type = &v2->DebugInfo->Type;
    if ( (struct _RTL_CRITICAL_SECTION *)v2->DebugInfo == v2 )
      break;
    if ( (struct _RTL_CRITICAL_SECTION *)p_Type[1] != v2
      || (v4 = (struct _RTL_CRITICAL_SECTION_DEBUG *)*p_Type, *(_QWORD **)(*p_Type + 8LL) != p_Type) )
    {
      __fastfail(3u);
    }
    v2->DebugInfo = v4;
    v4->CriticalSection = v2;
    CQuery::FreeQueryEvent((struct _QUERY_EVENT *)(p_Type - 2));
  }
  HIDWORD(this[5].DebugInfo) = 0;
  LeaveCriticalSection(this + 4);
  LODWORD(this[3].OwningThread) = 0;
}

```

## disassembly

```asm
0x180003da4  mov     [rsp+arg_0], rbx
0x180003da9  mov     [rsp+arg_8], rsi
0x180003dae  push    rdi
0x180003daf  sub     rsp, 20h
0x180003db3  mov     rbx, rcx
0x180003db6  mov     rcx, [rcx+40h]
0x180003dba  test    rcx, rcx
0x180003dbd  jz      short loc_180003DCD
0x180003dbf  call    cs:__imp_DevCloseObjectQuery
0x180003dc5  mov     qword ptr [rbx+40h], 0
0x180003dcd  lea     rsi, [rbx+0A0h]
0x180003dd4  mov     rcx, rsi; lpCriticalSection
0x180003dd7  call    cs:__imp_EnterCriticalSection
0x180003ddd  mov     dword ptr [rbx+0C8h], 1
0x180003de7  lea     rdi, [rbx+78h]
0x180003deb  mov     rcx, [rdi]
0x180003dee  cmp     rcx, rdi
0x180003df1  jz      short loc_180003E1B
0x180003df3  cmp     [rcx+8], rdi
0x180003df7  jnz     short loc_180003E14
0x180003df9  mov     rax, [rcx]
0x180003dfc  cmp     [rax+8], rcx
0x180003e00  jnz     short loc_180003E14
0x180003e02  mov     [rdi], rax
0x180003e05  add     rcx, 0FFFFFFFFFFFFFFF0h; Block
0x180003e09  mov     [rax+8], rdi
0x180003e0d  call    ?FreeQueryEvent@CQuery@@SAXPEAU_QUERY_EVENT@@@Z; CQuery::FreeQueryEvent(_QUERY_EVENT *)
0x180003e12  jmp     short loc_180003DEB
0x180003e14  mov     ecx, 3
0x180003e19  int     29h; Win8: RtlFailFast(ecx)
0x180003e1b  mov     rcx, rsi; lpCriticalSection
0x180003e1e  mov     dword ptr [rbx+0CCh], 0
0x180003e28  call    cs:__imp_LeaveCriticalSection
0x180003e2e  mov     rsi, [rsp+28h+arg_8]
0x180003e33  mov     dword ptr [rbx+88h], 0
0x180003e3d  mov     rbx, [rsp+28h+arg_0]
0x180003e42  add     rsp, 20h
0x180003e46  pop     rdi
0x180003e47  retn
```
