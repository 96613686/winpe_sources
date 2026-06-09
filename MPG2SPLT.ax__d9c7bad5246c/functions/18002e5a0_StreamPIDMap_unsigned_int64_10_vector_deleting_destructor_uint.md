# StreamPIDMap<unsigned __int64,10>::`vector deleting destructor'(uint)

- ea: `0x18002e5a0`
- end: `0x18002e617`
- name: `??_E?$StreamPIDMap@_K$09@@UEAAPEAXI@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x18002e5a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e5c5`
- `KERNEL32!DeleteCriticalSection` at `0x18002e5c5`

## pseudocode

```c
char *__fastcall StreamPIDMap<unsigned __int64,10>::`vector deleting destructor'(char *a1, char a2)
{
  __int64 **v4; // rdi
  __int64 *v5; // rcx
  __int64 v6; // rdx
  __int64 *v7; // rax

  *(_QWORD *)a1 = &TGenericMap<unsigned __int64,unsigned long,1,10,19>::`vftable';
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
    operator delete(v5, 0x338u);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1, 0x1A8u);
  return a1;
}

```

## disassembly

```asm
0x18002e5a0  mov     [rsp+arg_0], rbx
0x18002e5a5  mov     [rsp+arg_8], rsi
0x18002e5aa  push    rdi
0x18002e5ab  sub     rsp, 20h
0x18002e5af  lea     rax, ??_7?$TGenericMap@_KK$00$09$0BD@@@6B@; const TGenericMap<unsigned __int64,ulong,1,10,19>::`vftable'
0x18002e5b6  mov     rbx, rcx
0x18002e5b9  mov     [rcx], rax
0x18002e5bc  mov     esi, edx
0x18002e5be  add     rcx, 180h; lpCriticalSection
0x18002e5c5  call    cs:__imp_DeleteCriticalSection
0x18002e5cb  lea     rdi, [rbx+8]
0x18002e5cf  mov     rcx, [rdi]; void *
0x18002e5d2  cmp     rcx, rdi
0x18002e5d5  jz      short loc_18002E5F1
0x18002e5d7  mov     rdx, [rcx]
0x18002e5da  mov     rax, [rcx+8]
0x18002e5de  mov     [rax], rdx
0x18002e5e1  mov     [rdx+8], rax
0x18002e5e5  mov     edx, 338h; unsigned __int64
0x18002e5ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e5ef  jmp     short loc_18002E5CF
0x18002e5f1  test    sil, 1
0x18002e5f5  jz      short loc_18002E604
0x18002e5f7  mov     edx, 1A8h; unsigned __int64
0x18002e5fc  mov     rcx, rbx; void *
0x18002e5ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e604  mov     rsi, [rsp+28h+arg_8]
0x18002e609  mov     rax, rbx
0x18002e60c  mov     rbx, [rsp+28h+arg_0]
0x18002e611  add     rsp, 20h
0x18002e615  pop     rdi
0x18002e616  retn
```
