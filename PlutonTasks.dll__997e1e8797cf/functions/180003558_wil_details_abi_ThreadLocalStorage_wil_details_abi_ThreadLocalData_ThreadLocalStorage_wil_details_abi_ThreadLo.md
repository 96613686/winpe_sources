# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003558`
- end: `0x180003632`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034a0`

## callees

- `0x180003558`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003602`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035f4`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180003558  push    rbx
0x18000355a  push    rbp
0x18000355b  push    rsi
0x18000355c  push    rdi
0x18000355d  push    r12
0x18000355f  push    r13
0x180003561  push    r14
0x180003563  push    r15
0x180003565  sub     rsp, 28h
0x180003569  lea     r15, [rcx+50h]
0x18000356d  mov     rdi, rcx
0x180003570  cmp     rcx, r15
0x180003573  jz      loc_180003621
0x180003579  mov     rsi, [rdi]
0x18000357c  jmp     loc_180003608
0x180003581  mov     r13, rsi
0x180003584  mov     r12, rsi
0x180003587  mov     rsi, [rsi+8]
0x18000358b  movzx   eax, word ptr [r13+30h]
0x180003590  mov     rbp, [r13+28h]
0x180003594  lea     r14, [rax+rax*4]
0x180003598  shl     r14, 4
0x18000359c  add     r14, rbp
0x18000359f  jmp     short loc_1800035CD
0x1800035a1  mov     rbx, [rbp+40h]
0x1800035a5  call    cs:__imp_GetProcessHeap
0x1800035ab  mov     r8, rbx; lpMem
0x1800035ae  xor     edx, edx; dwFlags
0x1800035b0  mov     rcx, rax; hHeap
0x1800035b3  call    cs:__imp_HeapFree
0x1800035b9  mov     qword ptr [rbp+40h], 0
0x1800035c1  mov     qword ptr [rbp+48h], 0
0x1800035c9  add     rbp, 50h ; 'P'
0x1800035cd  cmp     rbp, r14
0x1800035d0  jnz     short loc_1800035A1
0x1800035d2  mov     rbx, [r13+28h]
0x1800035d6  call    cs:__imp_GetProcessHeap
0x1800035dc  mov     r8, rbx; lpMem
0x1800035df  xor     edx, edx; dwFlags
0x1800035e1  mov     rcx, rax; hHeap
0x1800035e4  call    cs:__imp_HeapFree
0x1800035ea  xor     eax, eax
0x1800035ec  mov     [r13+30h], eax
0x1800035f0  mov     [r13+28h], rax
0x1800035f4  call    cs:__imp_GetProcessHeap
0x1800035fa  mov     r8, r12; lpMem
0x1800035fd  xor     edx, edx; dwFlags
0x1800035ff  mov     rcx, rax; hHeap
0x180003602  call    cs:__imp_HeapFree
0x180003608  test    rsi, rsi
0x18000360b  jnz     loc_180003581
0x180003611  mov     [rdi], rsi
0x180003614  add     rdi, 8
0x180003618  cmp     rdi, r15
0x18000361b  jnz     loc_180003579
0x180003621  add     rsp, 28h
0x180003625  pop     r15
0x180003627  pop     r14
0x180003629  pop     r13
0x18000362b  pop     r12
0x18000362d  pop     rdi
0x18000362e  pop     rsi
0x18000362f  pop     rbp
0x180003630  pop     rbx
0x180003631  retn
```
