# CBaseAllocator::Commit(void)

- ea: `0x180003b90`
- end: `0x180003c35`
- name: `?Commit@CBaseAllocator@@UEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003b90`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003bc8`
- `KERNEL32!LeaveCriticalSection` at `0x180003c1d`
- `KERNEL32!LeaveCriticalSection` at `0x180003bc8`
- `KERNEL32!LeaveCriticalSection` at `0x180003c1d`
- `KERNEL32!EnterCriticalSection` at `0x180003bb9`
- `KERNEL32!EnterCriticalSection` at `0x180003bb9`

## pseudocode

```c
__int64 __fastcall CBaseAllocator::Commit(CBaseAllocator *this)
{
  _DWORD *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  bool v5; // zf
  int v6; // esi

  v1 = (_DWORD *)((char *)this - 24);
  v3 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 8) & -(__int64)(this != (CBaseAllocator *)24));
  EnterCriticalSection(v3);
  if ( *((_DWORD *)this + 25) )
  {
    LeaveCriticalSection(v3);
    return 0;
  }
  v5 = *((_DWORD *)this + 26) == 0;
  *((_DWORD *)this + 25) = 1;
  if ( !v5 )
  {
    v1[32] = 0;
LABEL_8:
    v6 = 0;
    goto LABEL_9;
  }
  v6 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v1 + 40LL))(v1);
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(CBaseAllocator *))(*(_QWORD *)this + 8LL))(this);
    goto LABEL_8;
  }
  *((_DWORD *)this + 25) = 0;
LABEL_9:
  LeaveCriticalSection(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003b90  mov     [rsp+arg_0], rbx
0x180003b95  mov     [rsp+arg_8], rsi
0x180003b9a  push    rdi
0x180003b9b  sub     rsp, 20h
0x180003b9f  lea     rsi, [rcx-18h]
0x180003ba3  mov     rbx, rcx
0x180003ba6  lea     rdx, [rcx+8]
0x180003baa  mov     rax, rsi
0x180003bad  neg     rax
0x180003bb0  sbb     rdi, rdi
0x180003bb3  and     rdi, rdx
0x180003bb6  mov     rcx, rdi; lpCriticalSection
0x180003bb9  call    cs:__imp_EnterCriticalSection
0x180003bbf  cmp     dword ptr [rbx+64h], 0
0x180003bc3  jz      short loc_180003BD2
0x180003bc5  mov     rcx, rdi; lpCriticalSection
0x180003bc8  call    cs:__imp_LeaveCriticalSection
0x180003bce  xor     eax, eax
0x180003bd0  jmp     short loc_180003C25
0x180003bd2  cmp     dword ptr [rbx+68h], 0
0x180003bd6  mov     dword ptr [rbx+64h], 1
0x180003bdd  jz      short loc_180003BEB
0x180003bdf  mov     dword ptr [rsi+80h], 0
0x180003be9  jmp     short loc_180003C18
0x180003beb  mov     rax, [rsi]
0x180003bee  mov     rcx, rsi
0x180003bf1  mov     rax, [rax+28h]
0x180003bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfa  mov     esi, eax
0x180003bfc  test    eax, eax
0x180003bfe  jns     short loc_180003C09
0x180003c00  mov     dword ptr [rbx+64h], 0
0x180003c07  jmp     short loc_180003C1A
0x180003c09  mov     rax, [rbx]
0x180003c0c  mov     rcx, rbx
0x180003c0f  mov     rax, [rax+8]
0x180003c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c18  xor     esi, esi
0x180003c1a  mov     rcx, rdi; lpCriticalSection
0x180003c1d  call    cs:__imp_LeaveCriticalSection
0x180003c23  mov     eax, esi
0x180003c25  mov     rbx, [rsp+28h+arg_0]
0x180003c2a  mov     rsi, [rsp+28h+arg_8]
0x180003c2f  add     rsp, 20h
0x180003c33  pop     rdi
0x180003c34  retn
```
