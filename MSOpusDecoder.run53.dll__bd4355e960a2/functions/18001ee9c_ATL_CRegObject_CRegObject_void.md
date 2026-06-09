# ATL::CRegObject::~CRegObject(void)

- ea: `0x18001ee9c`
- end: `0x18001ef38`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f080`
- `0x180021f9c`
- `0x1800222c4`

## callees

- `0x18001ee9c`
- `0x1800201a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eefd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ef13`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eefd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ef13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eebf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eebf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eee7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eee7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eed4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eed4`

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
0x18001ee9c  mov     [rsp+arg_0], rbx
0x18001eea1  mov     [rsp+arg_8], rsi
0x18001eea6  push    rdi
0x18001eea7  sub     rsp, 20h
0x18001eeab  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001eeb2  mov     rbx, rcx
0x18001eeb5  lea     rsi, [rcx+20h]
0x18001eeb9  mov     [rcx], rax
0x18001eebc  mov     rcx, rsi; lpCriticalSection
0x18001eebf  call    cs:__imp_EnterCriticalSection
0x18001eec5  lea     rdi, [rbx+8]
0x18001eec9  mov     rcx, rdi; this
0x18001eecc  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18001eed1  mov     rcx, rsi; lpCriticalSection
0x18001eed4  call    cs:__imp_LeaveCriticalSection
0x18001eeda  cmp     byte ptr [rsi+28h], 0
0x18001eede  jz      short loc_18001EEED
0x18001eee0  mov     rcx, rsi; lpCriticalSection
0x18001eee3  mov     byte ptr [rsi+28h], 0
0x18001eee7  call    cs:__imp_DeleteCriticalSection
0x18001eeed  mov     rcx, rdi; this
0x18001eef0  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18001eef5  mov     rcx, [rdi]; Block
0x18001eef8  test    rcx, rcx
0x18001eefb  jz      short loc_18001EF0A
0x18001eefd  call    cs:__imp_free
0x18001ef03  mov     qword ptr [rdi], 0
0x18001ef0a  mov     rcx, [rbx+10h]; Block
0x18001ef0e  test    rcx, rcx
0x18001ef11  jz      short loc_18001EF21
0x18001ef13  call    cs:__imp_free
0x18001ef19  mov     qword ptr [rbx+10h], 0
0x18001ef21  mov     rsi, [rsp+28h+arg_8]
0x18001ef26  mov     dword ptr [rbx+18h], 0
0x18001ef2d  mov     rbx, [rsp+28h+arg_0]
0x18001ef32  add     rsp, 20h
0x18001ef36  pop     rdi
0x18001ef37  retn
```
