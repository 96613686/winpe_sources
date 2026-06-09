# TpmProvider::~TpmProvider(void)

- ea: `0x18004ef44`
- end: `0x18004f001`
- name: `??1TpmProvider@@UEAA@XZ`
- size: `189`
- prototype: `void __fastcall(TpmProvider *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180081b00`
- `0x180081b50`

## callees

- `0x18004ef44`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004efdf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004efdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004efbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004efbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef92`

## pseudocode

```c
void __fastcall TpmProvider::~TpmProvider(TpmProvider *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  *(_QWORD *)this = &TpmProvider::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    LeaveCriticalSection(v2);
  EnterCriticalSection(&g_TbsLock);
  if ( !--g_TbsRefCount && g_fpTpmClose )
    g_fpTpmClose();
  LeaveCriticalSection(&g_TbsLock);
  *(_QWORD *)this = &TpmObject::`vftable';
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    DeleteCriticalSection(v2);
  *(_QWORD *)this = &ObjectWithProperties::`vftable';
}

```

## disassembly

```asm
0x18004ef44  mov     [rsp+arg_8], rbx
0x18004ef49  push    rdi
0x18004ef4a  sub     rsp, 20h
0x18004ef4e  mov     rbx, rcx
0x18004ef51  lea     rax, ??_7TpmProvider@@6B@; const TpmProvider::`vftable'
0x18004ef58  mov     [rcx], rax
0x18004ef5b  lea     rdi, [rcx+10h]
0x18004ef5f  mov     eax, [rcx+0Ch]
0x18004ef62  test    al, 1
0x18004ef64  jnz     short loc_18004EF75
0x18004ef66  mov     rcx, rdi; lpCriticalSection
0x18004ef69  call    cs:__imp_EnterCriticalSection
0x18004ef70  nop     dword ptr [rax+rax+00h]
0x18004ef75  mov     eax, [rbx+0Ch]
0x18004ef78  test    al, 1
0x18004ef7a  jnz     short loc_18004EF8B
0x18004ef7c  mov     rcx, rdi; lpCriticalSection
0x18004ef7f  call    cs:__imp_LeaveCriticalSection
0x18004ef86  nop     dword ptr [rax+rax+00h]
0x18004ef8b  lea     rcx, ?g_TbsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004ef92  call    cs:__imp_EnterCriticalSection
0x18004ef99  nop     dword ptr [rax+rax+00h]
0x18004ef9e  add     cs:?g_TbsRefCount@@3KA, 0FFFFFFFFh; ulong g_TbsRefCount
0x18004efa5  jnz     short loc_18004EFB8
0x18004efa7  mov     rax, cs:?g_fpTpmClose@@3P6AIXZEA; uint (*g_fpTpmClose)(void)
0x18004efae  test    rax, rax
0x18004efb1  jz      short loc_18004EFB8
0x18004efb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efb8  lea     rcx, ?g_TbsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004efbf  call    cs:__imp_LeaveCriticalSection
0x18004efc6  nop     dword ptr [rax+rax+00h]
0x18004efcb  lea     rax, ??_7TpmObject@@6B@; const TpmObject::`vftable'
0x18004efd2  mov     [rbx], rax
0x18004efd5  mov     eax, [rbx+0Ch]
0x18004efd8  test    al, 1
0x18004efda  jnz     short loc_18004EFEB
0x18004efdc  mov     rcx, rdi; lpCriticalSection
0x18004efdf  call    cs:__imp_DeleteCriticalSection
0x18004efe6  nop     dword ptr [rax+rax+00h]
0x18004efeb  lea     rax, ??_7ObjectWithProperties@@6B@; const ObjectWithProperties::`vftable'
0x18004eff2  mov     [rbx], rax
0x18004eff5  mov     rbx, [rsp+28h+arg_8]
0x18004effa  add     rsp, 20h
0x18004effe  pop     rdi
0x18004efff  retn
```
