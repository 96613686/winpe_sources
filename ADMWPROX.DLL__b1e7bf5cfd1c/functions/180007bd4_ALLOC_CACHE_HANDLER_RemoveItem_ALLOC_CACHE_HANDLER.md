# ALLOC_CACHE_HANDLER::RemoveItem(ALLOC_CACHE_HANDLER *)

- ea: `0x180007bd4`
- end: `0x180007c24`
- name: `?RemoveItem@ALLOC_CACHE_HANDLER@@SAXPEAV1@@Z`
- size: `80`
- prototype: `void __fastcall(struct ALLOC_CACHE_HANDLER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007604`

## callees

- `0x180007bd4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007be4`
- `KERNEL32!EnterCriticalSection` at `0x180007be4`
- `KERNEL32!LeaveCriticalSection` at `0x180007c16`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::RemoveItem(struct ALLOC_CACHE_HANDLER *a1)
{
  _QWORD *v2; // rbx
  __int64 v3; // rdx
  _QWORD *v4; // rax

  EnterCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
  v2 = (_QWORD *)((char *)a1 + 208);
  v3 = *v2;
  if ( *(_QWORD **)(*v2 + 8LL) != v2 || (v4 = (_QWORD *)v2[1], (_QWORD *)*v4 != v2) )
    __fastfail(3u);
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  LeaveCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
}

```

## disassembly

```asm
0x180007bd4  push    rbx
0x180007bd6  sub     rsp, 20h
0x180007bda  mov     rbx, rcx
0x180007bdd  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007be4  call    cs:__imp_EnterCriticalSection
0x180007bea  add     rbx, 0D0h
0x180007bf1  mov     rdx, [rbx]
0x180007bf4  cmp     [rdx+8], rbx
0x180007bf8  jnz     short loc_180007C1D
0x180007bfa  mov     rax, [rbx+8]
0x180007bfe  cmp     [rax], rbx
0x180007c01  jnz     short loc_180007C1D
0x180007c03  mov     [rax], rdx
0x180007c06  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ALLOC_CACHE_HANDLER::sm_csItems
0x180007c0d  mov     [rdx+8], rax
0x180007c11  add     rsp, 20h
0x180007c15  pop     rbx
0x180007c16  jmp     cs:__imp_LeaveCriticalSection
0x180007c1d  mov     ecx, 3
0x180007c22  int     29h; Win8: RtlFailFast(ecx)
```
