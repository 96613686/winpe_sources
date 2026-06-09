# ATL::AtlModuleTerm(ATL::_ATL_MODULE *)

- ea: `0x180018ba0`
- end: `0x180018c1c`
- name: `?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z`
- size: `124`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001040`

## callees

- `0x180018ba0`
- `0x180030010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x180018c0e`
- `KERNEL32!HeapDestroy` at `0x180018c0e`
- `MSDART!MPDeleteCriticalSection` at `0x180018be2`
- `MSDART!MPDeleteCriticalSection` at `0x180018bef`
- `MSDART!MPDeleteCriticalSection` at `0x180018bfc`
- `MSDART!MPDeleteCriticalSection` at `0x180018be2`
- `MSDART!MPDeleteCriticalSection` at `0x180018bef`
- `MSDART!MPDeleteCriticalSection` at `0x180018bfc`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleTerm(struct ATL::_ATL_MODULE *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rcx

  v1 = (_QWORD *)qword_1800454E0;
  if ( qword_1800454E0 )
  {
    while ( *v1 )
    {
      v2 = v1[3];
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      v1[3] = 0;
      v1 += 6;
    }
  }
  MPDeleteCriticalSection(&qword_1800454F8);
  MPDeleteCriticalSection(&qword_180045500);
  MPDeleteCriticalSection(&qword_180045508);
  if ( hHeap )
    HeapDestroy(hHeap);
  return 0;
}

```

## disassembly

```asm
0x180018ba0  push    rbx
0x180018ba2  sub     rsp, 20h
0x180018ba6  mov     rbx, cs:qword_1800454E0
0x180018bad  test    rbx, rbx
0x180018bb0  jz      short loc_180018BDB
0x180018bb2  jmp     short loc_180018BD5
0x180018bb4  mov     rcx, [rbx+18h]
0x180018bb8  test    rcx, rcx
0x180018bbb  jz      short loc_180018BC9
0x180018bbd  mov     rax, [rcx]
0x180018bc0  mov     rax, [rax+10h]
0x180018bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bc9  mov     qword ptr [rbx+18h], 0
0x180018bd1  add     rbx, 30h ; '0'
0x180018bd5  cmp     qword ptr [rbx], 0
0x180018bd9  jnz     short loc_180018BB4
0x180018bdb  lea     rcx, qword_1800454F8
0x180018be2  call    cs:__imp_MPDeleteCriticalSection
0x180018be8  lea     rcx, qword_180045500
0x180018bef  call    cs:__imp_MPDeleteCriticalSection
0x180018bf5  lea     rcx, qword_180045508
0x180018bfc  call    cs:__imp_MPDeleteCriticalSection
0x180018c02  mov     rcx, cs:hHeap; hHeap
0x180018c09  test    rcx, rcx
0x180018c0c  jz      short loc_180018C14
0x180018c0e  call    cs:__imp_HeapDestroy
0x180018c14  xor     eax, eax
0x180018c16  add     rsp, 20h
0x180018c1a  pop     rbx
0x180018c1b  retn
```
