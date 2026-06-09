# TGenericMap<unsigned __int64,ulong,0,5,19>::`vector deleting destructor'(uint)

- ea: `0x18002e520`
- end: `0x18002e597`
- name: `??_E?$TGenericMap@_KK$0A@$04$0BD@@@UEAAPEAXI@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x18002e520`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e545`
- `KERNEL32!DeleteCriticalSection` at `0x18002e545`

## pseudocode

```c
char *__fastcall TGenericMap<unsigned __int64,unsigned long,0,5,19>::`vector deleting destructor'(char *a1, char a2)
{
  __int64 **v4; // rdi
  __int64 *v5; // rcx
  __int64 v6; // rdx
  __int64 *v7; // rax

  *(_QWORD *)a1 = &TGenericMap<unsigned __int64,unsigned long,0,5,19>::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
  v4 = (__int64 **)(a1 + 8);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == (__int64 *)v4 )
      break;
    v6 = *v5;
    v7 = (__int64 *)v5[1];
    *v7 = *v5;
    *(_QWORD *)(v6 + 8) = v7;
    operator delete(v5, 0x1A8u);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1, 0x1A8u);
  return a1;
}

```

## disassembly

```asm
0x18002e520  mov     [rsp+arg_0], rbx
0x18002e525  mov     [rsp+arg_8], rsi
0x18002e52a  push    rdi
0x18002e52b  sub     rsp, 20h
0x18002e52f  lea     rax, ??_7?$TGenericMap@_KK$0A@$04$0BD@@@6B@; const TGenericMap<unsigned __int64,ulong,0,5,19>::`vftable'
0x18002e536  mov     rbx, rcx
0x18002e539  mov     [rcx], rax
0x18002e53c  mov     esi, edx
0x18002e53e  add     rcx, 180h; lpCriticalSection
0x18002e545  call    cs:__imp_DeleteCriticalSection
0x18002e54b  lea     rdi, [rbx+8]
0x18002e54f  mov     rcx, [rdi]; void *
0x18002e552  cmp     rcx, rdi
0x18002e555  jz      short loc_18002E571
0x18002e557  mov     rdx, [rcx]
0x18002e55a  mov     rax, [rcx+8]
0x18002e55e  mov     [rax], rdx
0x18002e561  mov     [rdx+8], rax
0x18002e565  mov     edx, 1A8h; unsigned __int64
0x18002e56a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e56f  jmp     short loc_18002E54F
0x18002e571  test    sil, 1
0x18002e575  jz      short loc_18002E584
0x18002e577  mov     edx, 1A8h; unsigned __int64
0x18002e57c  mov     rcx, rbx; void *
0x18002e57f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e584  mov     rsi, [rsp+28h+arg_8]
0x18002e589  mov     rax, rbx
0x18002e58c  mov     rbx, [rsp+28h+arg_0]
0x18002e591  add     rsp, 20h
0x18002e595  pop     rdi
0x18002e596  retn
```
