# GetNextRPCSystemWideCell(void *,tagDebugCellUnion * *,tagDebugCellID *,ulong *)

- ea: `0x180009ca4`
- end: `0x180009d17`
- name: `?GetNextRPCSystemWideCell@@YAJPEAXPEAPEAUtagDebugCellUnion@@PEAUtagDebugCellID@@PEAK@Z`
- size: `115`
- prototype: `int __fastcall(void **, struct tagDebugCellUnion **, struct tagDebugCellID *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000960c`
- `0x1800096c0`
- `0x1800097b0`

## callees

- `0x180009b54`
- `0x180009bf8`
- `0x180009ca4`
- `0x180009db0`

## pseudocode

```c
int __fastcall GetNextRPCSystemWideCell(
        void **a1,
        struct tagDebugCellUnion **a2,
        struct tagDebugCellID *a3,
        unsigned int *a4)
{
  void **v5; // rbx
  struct tagDebugCellUnion *NextDebugCellInfo; // rax
  int result; // eax

  v5 = a1 + 1;
  do
  {
    NextDebugCellInfo = GetNextDebugCellInfo(*v5, a3);
    *a2 = NextDebugCellInfo;
    if ( !NextDebugCellInfo )
    {
      CloseRPCServerDebugInfo(v5);
      result = OpenNextRPCServer(*a1, v5);
      if ( result )
      {
        *v5 = 0;
        return result;
      }
    }
  }
  while ( !*a2 );
  if ( a4 )
    *a4 = *((_DWORD *)*a1 + (unsigned int)(*(_DWORD *)*a1 - 1) + 2);
  return 0;
}

```

## disassembly

```asm
0x180009ca4  push    rbx
0x180009ca6  push    rbp
0x180009ca7  push    rsi
0x180009ca8  push    rdi
0x180009ca9  push    r14
0x180009cab  sub     rsp, 20h
0x180009caf  mov     rdi, r9
0x180009cb2  lea     rbx, [rcx+8]
0x180009cb6  mov     rbp, r8
0x180009cb9  mov     r14, rdx
0x180009cbc  mov     rsi, rcx
0x180009cbf  mov     rcx, [rbx]; void *
0x180009cc2  mov     rdx, rbp; struct tagDebugCellID *
0x180009cc5  call    ?GetNextDebugCellInfo@@YAPEAUtagDebugCellUnion@@PEAXPEAUtagDebugCellID@@@Z; GetNextDebugCellInfo(void *,tagDebugCellID *)
0x180009cca  mov     [r14], rax
0x180009ccd  test    rax, rax
0x180009cd0  jnz     short loc_180009CE9
0x180009cd2  mov     rcx, rbx; void **
0x180009cd5  call    ?CloseRPCServerDebugInfo@@YAXPEAPEAX@Z; CloseRPCServerDebugInfo(void * *)
0x180009cda  mov     rcx, [rsi]; void *
0x180009cdd  mov     rdx, rbx; void **
0x180009ce0  call    ?OpenNextRPCServer@@YAJPEAXPEAPEAX@Z; OpenNextRPCServer(void *,void * *)
0x180009ce5  test    eax, eax
0x180009ce7  jnz     short loc_180009D0E
0x180009ce9  cmp     qword ptr [r14], 0
0x180009ced  jz      short loc_180009CBF
0x180009cef  test    rdi, rdi
0x180009cf2  jz      short loc_180009D01
0x180009cf4  mov     rcx, [rsi]
0x180009cf7  mov     eax, [rcx]
0x180009cf9  dec     eax
0x180009cfb  mov     ecx, [rcx+rax*4+8]
0x180009cff  mov     [rdi], ecx
0x180009d01  xor     eax, eax
0x180009d03  add     rsp, 20h
0x180009d07  pop     r14
0x180009d09  pop     rdi
0x180009d0a  pop     rsi
0x180009d0b  pop     rbp
0x180009d0c  pop     rbx
0x180009d0d  retn
0x180009d0e  mov     qword ptr [rbx], 0
0x180009d15  jmp     short loc_180009D03
```
