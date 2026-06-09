# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003c18`
- end: `0x180003cf2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b60`

## callees

- `0x180003c18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cb4`

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
0x180003c18  push    rbx
0x180003c1a  push    rbp
0x180003c1b  push    rsi
0x180003c1c  push    rdi
0x180003c1d  push    r12
0x180003c1f  push    r13
0x180003c21  push    r14
0x180003c23  push    r15
0x180003c25  sub     rsp, 28h
0x180003c29  lea     r15, [rcx+50h]
0x180003c2d  mov     rdi, rcx
0x180003c30  cmp     rcx, r15
0x180003c33  jz      loc_180003CE1
0x180003c39  mov     rsi, [rdi]
0x180003c3c  jmp     loc_180003CC8
0x180003c41  mov     r13, rsi
0x180003c44  mov     r12, rsi
0x180003c47  mov     rsi, [rsi+8]
0x180003c4b  movzx   eax, word ptr [r13+30h]
0x180003c50  mov     rbp, [r13+28h]
0x180003c54  lea     r14, [rax+rax*4]
0x180003c58  shl     r14, 4
0x180003c5c  add     r14, rbp
0x180003c5f  jmp     short loc_180003C8D
0x180003c61  mov     rbx, [rbp+40h]
0x180003c65  call    cs:__imp_GetProcessHeap
0x180003c6b  mov     r8, rbx; lpMem
0x180003c6e  xor     edx, edx; dwFlags
0x180003c70  mov     rcx, rax; hHeap
0x180003c73  call    cs:__imp_HeapFree
0x180003c79  mov     qword ptr [rbp+40h], 0
0x180003c81  mov     qword ptr [rbp+48h], 0
0x180003c89  add     rbp, 50h ; 'P'
0x180003c8d  cmp     rbp, r14
0x180003c90  jnz     short loc_180003C61
0x180003c92  mov     rbx, [r13+28h]
0x180003c96  call    cs:__imp_GetProcessHeap
0x180003c9c  mov     r8, rbx; lpMem
0x180003c9f  xor     edx, edx; dwFlags
0x180003ca1  mov     rcx, rax; hHeap
0x180003ca4  call    cs:__imp_HeapFree
0x180003caa  xor     eax, eax
0x180003cac  mov     [r13+30h], eax
0x180003cb0  mov     [r13+28h], rax
0x180003cb4  call    cs:__imp_GetProcessHeap
0x180003cba  mov     r8, r12; lpMem
0x180003cbd  xor     edx, edx; dwFlags
0x180003cbf  mov     rcx, rax; hHeap
0x180003cc2  call    cs:__imp_HeapFree
0x180003cc8  test    rsi, rsi
0x180003ccb  jnz     loc_180003C41
0x180003cd1  mov     [rdi], rsi
0x180003cd4  add     rdi, 8
0x180003cd8  cmp     rdi, r15
0x180003cdb  jnz     loc_180003C39
0x180003ce1  add     rsp, 28h
0x180003ce5  pop     r15
0x180003ce7  pop     r14
0x180003ce9  pop     r13
0x180003ceb  pop     r12
0x180003ced  pop     rdi
0x180003cee  pop     rsi
0x180003cef  pop     rbp
0x180003cf0  pop     rbx
0x180003cf1  retn
```
