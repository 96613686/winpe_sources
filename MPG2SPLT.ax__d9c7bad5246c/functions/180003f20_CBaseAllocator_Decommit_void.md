# CBaseAllocator::Decommit(void)

- ea: `0x180003f20`
- end: `0x180003fe5`
- name: `?Decommit@CBaseAllocator@@UEAAJXZ`
- size: `197`
- prototype: `__int64 __fastcall(CBaseAllocator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000315c`

## callees

- `0x180003f20`
- `0x180034010`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180003faa`
- `KERNEL32!ReleaseSemaphore` at `0x180003faa`
- `KERNEL32!LeaveCriticalSection` at `0x180003f61`
- `KERNEL32!LeaveCriticalSection` at `0x180003fba`
- `KERNEL32!LeaveCriticalSection` at `0x180003f61`
- `KERNEL32!LeaveCriticalSection` at `0x180003fba`
- `KERNEL32!EnterCriticalSection` at `0x180003f49`
- `KERNEL32!EnterCriticalSection` at `0x180003f49`

## pseudocode

```c
__int64 __fastcall CBaseAllocator::Decommit(CBaseAllocator *this)
{
  char *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  _DWORD *v4; // rdx
  int v5; // eax
  int v6; // esi
  __int64 v7; // rax
  LONG v8; // edx

  v1 = (char *)this - 24;
  v3 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 8) & -(__int64)(this != (CBaseAllocator *)24));
  EnterCriticalSection(v3);
  v4 = (_DWORD *)((char *)this + 104);
  if ( __PAIR64__(*((_DWORD *)this + 26), *((_DWORD *)v1 + 31)) )
  {
    v5 = *((_DWORD *)this + 20);
    *((_DWORD *)this + 25) = 0;
    if ( *((_DWORD *)this + 14) >= v5 )
    {
      v7 = *(_QWORD *)v1;
      *v4 = 0;
      (*(void (__fastcall **)(char *))(v7 + 32))(v1);
      v6 = 1;
    }
    else
    {
      v6 = 0;
      *v4 = 1;
    }
    v8 = *((_DWORD *)this + 18);
    if ( v8 )
    {
      ReleaseSemaphore(*((HANDLE *)this + 8), v8, 0);
      *((_DWORD *)this + 18) = 0;
    }
    LeaveCriticalSection(v3);
    if ( v6 )
      (*(void (__fastcall **)(CBaseAllocator *))(*(_QWORD *)this + 16LL))(this);
  }
  else
  {
    LeaveCriticalSection(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180003f20  mov     [rsp+arg_0], rbx
0x180003f25  mov     [rsp+arg_8], rsi
0x180003f2a  push    rdi
0x180003f2b  sub     rsp, 20h
0x180003f2f  lea     rsi, [rcx-18h]
0x180003f33  mov     rbx, rcx
0x180003f36  lea     rdx, [rcx+8]
0x180003f3a  mov     rax, rsi
0x180003f3d  neg     rax
0x180003f40  sbb     rdi, rdi
0x180003f43  and     rdi, rdx
0x180003f46  mov     rcx, rdi; lpCriticalSection
0x180003f49  call    cs:__imp_EnterCriticalSection
0x180003f4f  cmp     dword ptr [rsi+7Ch], 0
0x180003f53  lea     rdx, [rbx+68h]
0x180003f57  jnz     short loc_180003F69
0x180003f59  cmp     dword ptr [rdx], 0
0x180003f5c  jnz     short loc_180003F69
0x180003f5e  mov     rcx, rdi; lpCriticalSection
0x180003f61  call    cs:__imp_LeaveCriticalSection
0x180003f67  jmp     short loc_180003FD3
0x180003f69  mov     eax, [rbx+50h]
0x180003f6c  mov     dword ptr [rbx+64h], 0
0x180003f73  cmp     [rbx+38h], eax
0x180003f76  jge     short loc_180003F82
0x180003f78  xor     esi, esi
0x180003f7a  mov     dword ptr [rdx], 1
0x180003f80  jmp     short loc_180003F9C
0x180003f82  mov     rax, [rsi]
0x180003f85  mov     rcx, rsi
0x180003f88  mov     dword ptr [rdx], 0
0x180003f8e  mov     rax, [rax+20h]
0x180003f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f97  mov     esi, 1
0x180003f9c  mov     edx, [rbx+48h]; lReleaseCount
0x180003f9f  test    edx, edx
0x180003fa1  jz      short loc_180003FB7
0x180003fa3  mov     rcx, [rbx+40h]; hSemaphore
0x180003fa7  xor     r8d, r8d; lpPreviousCount
0x180003faa  call    cs:__imp_ReleaseSemaphore
0x180003fb0  mov     dword ptr [rbx+48h], 0
0x180003fb7  mov     rcx, rdi; lpCriticalSection
0x180003fba  call    cs:__imp_LeaveCriticalSection
0x180003fc0  test    esi, esi
0x180003fc2  jz      short loc_180003FD3
0x180003fc4  mov     rax, [rbx]
0x180003fc7  mov     rcx, rbx
0x180003fca  mov     rax, [rax+10h]
0x180003fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd3  mov     rbx, [rsp+28h+arg_0]
0x180003fd8  xor     eax, eax
0x180003fda  mov     rsi, [rsp+28h+arg_8]
0x180003fdf  add     rsp, 20h
0x180003fe3  pop     rdi
0x180003fe4  retn
```
