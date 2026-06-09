# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1400037dc`
- end: `0x1400038b6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003724`

## callees

- `0x1400037dc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140003829`
- `KERNEL32!GetProcessHeap` at `0x14000385a`
- `KERNEL32!GetProcessHeap` at `0x140003878`
- `KERNEL32!GetProcessHeap` at `0x140003829`
- `KERNEL32!GetProcessHeap` at `0x14000385a`
- `KERNEL32!GetProcessHeap` at `0x140003878`
- `KERNEL32!HeapFree` at `0x140003837`
- `KERNEL32!HeapFree` at `0x140003868`
- `KERNEL32!HeapFree` at `0x140003886`
- `KERNEL32!HeapFree` at `0x140003837`
- `KERNEL32!HeapFree` at `0x140003868`
- `KERNEL32!HeapFree` at `0x140003886`

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
0x1400037dc  push    rbx
0x1400037de  push    rbp
0x1400037df  push    rsi
0x1400037e0  push    rdi
0x1400037e1  push    r12
0x1400037e3  push    r13
0x1400037e5  push    r14
0x1400037e7  push    r15
0x1400037e9  sub     rsp, 28h
0x1400037ed  lea     r15, [rcx+50h]
0x1400037f1  mov     rdi, rcx
0x1400037f4  cmp     rcx, r15
0x1400037f7  jz      loc_1400038A5
0x1400037fd  mov     rsi, [rdi]
0x140003800  jmp     loc_14000388C
0x140003805  mov     r13, rsi
0x140003808  mov     r12, rsi
0x14000380b  mov     rsi, [rsi+8]
0x14000380f  movzx   eax, word ptr [r13+30h]
0x140003814  mov     rbp, [r13+28h]
0x140003818  lea     r14, [rax+rax*4]
0x14000381c  shl     r14, 4
0x140003820  add     r14, rbp
0x140003823  jmp     short loc_140003851
0x140003825  mov     rbx, [rbp+40h]
0x140003829  call    cs:__imp_GetProcessHeap
0x14000382f  mov     r8, rbx; lpMem
0x140003832  xor     edx, edx; dwFlags
0x140003834  mov     rcx, rax; hHeap
0x140003837  call    cs:__imp_HeapFree
0x14000383d  mov     qword ptr [rbp+40h], 0
0x140003845  mov     qword ptr [rbp+48h], 0
0x14000384d  add     rbp, 50h ; 'P'
0x140003851  cmp     rbp, r14
0x140003854  jnz     short loc_140003825
0x140003856  mov     rbx, [r13+28h]
0x14000385a  call    cs:__imp_GetProcessHeap
0x140003860  mov     r8, rbx; lpMem
0x140003863  xor     edx, edx; dwFlags
0x140003865  mov     rcx, rax; hHeap
0x140003868  call    cs:__imp_HeapFree
0x14000386e  xor     eax, eax
0x140003870  mov     [r13+30h], eax
0x140003874  mov     [r13+28h], rax
0x140003878  call    cs:__imp_GetProcessHeap
0x14000387e  mov     r8, r12; lpMem
0x140003881  xor     edx, edx; dwFlags
0x140003883  mov     rcx, rax; hHeap
0x140003886  call    cs:__imp_HeapFree
0x14000388c  test    rsi, rsi
0x14000388f  jnz     loc_140003805
0x140003895  mov     [rdi], rsi
0x140003898  add     rdi, 8
0x14000389c  cmp     rdi, r15
0x14000389f  jnz     loc_1400037FD
0x1400038a5  add     rsp, 28h
0x1400038a9  pop     r15
0x1400038ab  pop     r14
0x1400038ad  pop     r13
0x1400038af  pop     r12
0x1400038b1  pop     rdi
0x1400038b2  pop     rsi
0x1400038b3  pop     rbp
0x1400038b4  pop     rbx
0x1400038b5  retn
```
