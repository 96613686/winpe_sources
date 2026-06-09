# ATL::CRegObject::~CRegObject(void)

- ea: `0x180005368`
- end: `0x180005404`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005690`
- `0x1800088fc`
- `0x180008c1c`

## callees

- `0x180005368`
- `0x18000678c`

## import_xrefs

- `msvcrt!free` at `0x1800053c9`
- `msvcrt!free` at `0x1800053df`
- `msvcrt!free` at `0x1800053c9`
- `msvcrt!free` at `0x1800053df`
- `KERNEL32!LeaveCriticalSection` at `0x1800053a0`
- `KERNEL32!LeaveCriticalSection` at `0x1800053a0`
- `KERNEL32!EnterCriticalSection` at `0x18000538b`
- `KERNEL32!EnterCriticalSection` at `0x18000538b`
- `KERNEL32!DeleteCriticalSection` at `0x1800053b3`
- `KERNEL32!DeleteCriticalSection` at `0x1800053b3`

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
0x180005368  mov     [rsp+arg_0], rbx
0x18000536d  mov     [rsp+arg_8], rsi
0x180005372  push    rdi
0x180005373  sub     rsp, 20h
0x180005377  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000537e  mov     rbx, rcx
0x180005381  lea     rsi, [rcx+20h]
0x180005385  mov     [rcx], rax
0x180005388  mov     rcx, rsi; lpCriticalSection
0x18000538b  call    cs:__imp_EnterCriticalSection
0x180005391  lea     rdi, [rbx+8]
0x180005395  mov     rcx, rdi; this
0x180005398  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000539d  mov     rcx, rsi; lpCriticalSection
0x1800053a0  call    cs:__imp_LeaveCriticalSection
0x1800053a6  cmp     byte ptr [rsi+28h], 0
0x1800053aa  jz      short loc_1800053B9
0x1800053ac  mov     rcx, rsi; lpCriticalSection
0x1800053af  mov     byte ptr [rsi+28h], 0
0x1800053b3  call    cs:__imp_DeleteCriticalSection
0x1800053b9  mov     rcx, rdi; this
0x1800053bc  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800053c1  mov     rcx, [rdi]; Block
0x1800053c4  test    rcx, rcx
0x1800053c7  jz      short loc_1800053D6
0x1800053c9  call    cs:__imp_free
0x1800053cf  mov     qword ptr [rdi], 0
0x1800053d6  mov     rcx, [rbx+10h]; Block
0x1800053da  test    rcx, rcx
0x1800053dd  jz      short loc_1800053ED
0x1800053df  call    cs:__imp_free
0x1800053e5  mov     qword ptr [rbx+10h], 0
0x1800053ed  mov     rsi, [rsp+28h+arg_8]
0x1800053f2  mov     dword ptr [rbx+18h], 0
0x1800053f9  mov     rbx, [rsp+28h+arg_0]
0x1800053fe  add     rsp, 20h
0x180005402  pop     rdi
0x180005403  retn
```
