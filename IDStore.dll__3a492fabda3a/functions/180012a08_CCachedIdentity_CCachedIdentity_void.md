# CCachedIdentity::~CCachedIdentity(void)

- ea: `0x180012a08`
- end: `0x180012aee`
- name: `??1CCachedIdentity@@QEAA@XZ`
- size: `230`
- prototype: `void __fastcall(CCachedIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008260`

## callees

- `0x180012a08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012ac2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012aab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012aab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ad0`

## pseudocode

```c
void __fastcall CCachedIdentity::~CCachedIdentity(CCachedIdentity *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax

  v1 = (void *)*((_QWORD *)this + 18);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 14);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
    *((_QWORD *)this + 14) = 0;
    *((_QWORD *)this + 15) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 6);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180012a08  mov     [rsp+arg_0], rbx
0x180012a0d  mov     [rsp+arg_8], rsi
0x180012a12  push    rdi
0x180012a13  sub     rsp, 20h
0x180012a17  mov     rdi, [rcx+90h]
0x180012a1e  xor     esi, esi
0x180012a20  mov     rbx, rcx
0x180012a23  test    rdi, rdi
0x180012a26  jz      short loc_180012A4A
0x180012a28  call    cs:__imp_GetProcessHeap
0x180012a2e  mov     r8, rdi; lpMem
0x180012a31  xor     edx, edx; dwFlags
0x180012a33  mov     rcx, rax; hHeap
0x180012a36  call    cs:__imp_HeapFree
0x180012a3c  mov     [rbx+90h], rsi
0x180012a43  mov     [rbx+98h], rsi
0x180012a4a  mov     rdi, [rbx+70h]
0x180012a4e  test    rdi, rdi
0x180012a51  jz      short loc_180012A6F
0x180012a53  call    cs:__imp_GetProcessHeap
0x180012a59  mov     r8, rdi; lpMem
0x180012a5c  xor     edx, edx; dwFlags
0x180012a5e  mov     rcx, rax; hHeap
0x180012a61  call    cs:__imp_HeapFree
0x180012a67  mov     [rbx+70h], rsi
0x180012a6b  mov     [rbx+78h], rsi
0x180012a6f  mov     rdi, [rbx+50h]
0x180012a73  test    rdi, rdi
0x180012a76  jz      short loc_180012A94
0x180012a78  call    cs:__imp_GetProcessHeap
0x180012a7e  mov     r8, rdi; lpMem
0x180012a81  xor     edx, edx; dwFlags
0x180012a83  mov     rcx, rax; hHeap
0x180012a86  call    cs:__imp_HeapFree
0x180012a8c  mov     [rbx+50h], rsi
0x180012a90  mov     [rbx+58h], rsi
0x180012a94  mov     rdi, [rbx+30h]
0x180012a98  test    rdi, rdi
0x180012a9b  jz      short loc_180012AB9
0x180012a9d  call    cs:__imp_GetProcessHeap
0x180012aa3  mov     r8, rdi; lpMem
0x180012aa6  xor     edx, edx; dwFlags
0x180012aa8  mov     rcx, rax; hHeap
0x180012aab  call    cs:__imp_HeapFree
0x180012ab1  mov     [rbx+30h], rsi
0x180012ab5  mov     [rbx+38h], rsi
0x180012ab9  mov     rdi, [rbx+10h]
0x180012abd  test    rdi, rdi
0x180012ac0  jz      short loc_180012ADE
0x180012ac2  call    cs:__imp_GetProcessHeap
0x180012ac8  mov     r8, rdi; lpMem
0x180012acb  xor     edx, edx; dwFlags
0x180012acd  mov     rcx, rax; hHeap
0x180012ad0  call    cs:__imp_HeapFree
0x180012ad6  mov     [rbx+10h], rsi
0x180012ada  mov     [rbx+18h], rsi
0x180012ade  mov     rbx, [rsp+28h+arg_0]
0x180012ae3  mov     rsi, [rsp+28h+arg_8]
0x180012ae8  add     rsp, 20h
0x180012aec  pop     rdi
0x180012aed  retn
```
