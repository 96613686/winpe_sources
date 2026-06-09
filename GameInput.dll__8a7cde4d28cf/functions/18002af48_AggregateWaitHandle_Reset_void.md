# AggregateWaitHandle::Reset(void)

- ea: `0x18002af48`
- end: `0x18002afdf`
- name: `?Reset@AggregateWaitHandle@@QEAAXXZ`
- size: `151`
- prototype: `void __fastcall(AggregateWaitHandle *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180024cc4`
- `0x180029ea0`
- `0x180029f90`

## callees

- `0x18000c11c`
- `0x18002af48`

## import_xrefs

- `ntdll!NtCancelWaitCompletionPacket` at `0x18002af6c`
- `ntdll!NtCancelWaitCompletionPacket` at `0x18002af6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002af7c`

## pseudocode

```c
void __fastcall AggregateWaitHandle::Reset(AggregateWaitHandle *this, const struct std::nothrow_t *a2)
{
  char *v2; // rdi
  char *i; // rbx
  char *v5; // rax
  __int64 v6; // rcx

  v2 = (char *)this + 24;
  for ( i = (char *)*((_QWORD *)this + 3); i != v2; i = *(char **)i )
  {
    LOBYTE(a2) = 1;
    NtCancelWaitCompletionPacket(*((_QWORD *)i + 3), a2);
    CloseHandle(*((HANDLE *)i + 3));
  }
  while ( 1 )
  {
    v5 = *(char **)v2;
    v6 = **(_QWORD **)v2;
    if ( *(char **)(*(_QWORD *)v2 + 8LL) != v2 || *(char **)(v6 + 8) != v5 )
      __fastfail(3u);
    *(_QWORD *)v2 = v6;
    *(_QWORD *)(v6 + 8) = v2;
    if ( v5 == v2 )
      break;
    operator delete(v5, a2);
    --*((_DWORD *)v2 + 4);
  }
  operator delete(*((PVOID *)this + 2), a2);
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x18002af48  mov     [rsp+arg_0], rbx
0x18002af4d  mov     [rsp+arg_8], rsi
0x18002af52  push    rdi
0x18002af53  sub     rsp, 20h
0x18002af57  lea     rdi, [rcx+18h]
0x18002af5b  mov     rsi, rcx
0x18002af5e  mov     rbx, [rdi]
0x18002af61  cmp     rbx, rdi
0x18002af64  jz      short loc_18002AFAA
0x18002af66  mov     rcx, [rbx+18h]
0x18002af6a  mov     dl, 1
0x18002af6c  call    cs:__imp_NtCancelWaitCompletionPacket
0x18002af73  nop     dword ptr [rax+rax+00h]
0x18002af78  mov     rcx, [rbx+18h]; hObject
0x18002af7c  call    cs:__imp_CloseHandle
0x18002af83  nop     dword ptr [rax+rax+00h]
0x18002af88  mov     rbx, [rbx]
0x18002af8b  jmp     short loc_18002AF61
0x18002af8d  cmp     [rcx+8], rax
0x18002af91  jnz     short loc_18002AFB6
0x18002af93  mov     [rdi], rcx
0x18002af96  mov     [rcx+8], rdi
0x18002af9a  cmp     rax, rdi
0x18002af9d  jz      short loc_18002AFBD
0x18002af9f  mov     rcx, rax; P
0x18002afa2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002afa7  dec     dword ptr [rdi+10h]
0x18002afaa  mov     rax, [rdi]
0x18002afad  mov     rcx, [rax]
0x18002afb0  cmp     [rax+8], rdi
0x18002afb4  jz      short loc_18002AF8D
0x18002afb6  mov     ecx, 3
0x18002afbb  int     29h; Win8: RtlFailFast(ecx)
0x18002afbd  mov     rcx, [rsi+10h]; P
0x18002afc1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002afc6  mov     rbx, [rsp+28h+arg_0]
0x18002afcb  mov     qword ptr [rsi+10h], 0
0x18002afd3  mov     rsi, [rsp+28h+arg_8]
0x18002afd8  add     rsp, 20h
0x18002afdc  pop     rdi
0x18002afdd  retn
```
