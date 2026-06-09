# WIMHashFile::~WIMHashFile(void)

- ea: `0x180001948`
- end: `0x1800019cc`
- name: `??1WIMHashFile@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(WIMHashFile *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040a8`

## callees

- `0x180001948`
- `0x180002768`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000196f`
- `KERNEL32!HeapFree` at `0x18000196f`
- `KERNEL32!GetProcessHeap` at `0x180001961`
- `KERNEL32!GetProcessHeap` at `0x180001961`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000198e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800019b4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000198e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800019b4`
- `bcrypt!BCryptDestroyHash` at `0x1800019a0`
- `bcrypt!BCryptDestroyHash` at `0x1800019a0`

## pseudocode

```c
void __fastcall WIMHashFile::~WIMHashFile(WIMHashFile *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v1 = (void *)*((_QWORD *)this + 18);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 18) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 20);
  if ( v4 )
    BCryptCloseAlgorithmProvider(v4, 0);
  v5 = (void *)*((_QWORD *)this + 22);
  if ( v5 )
    BCryptDestroyHash(v5);
  v6 = (void *)*((_QWORD *)this + 21);
  if ( v6 )
    BCryptCloseAlgorithmProvider(v6, 0);
  File::~File((HANDLE *)this);
}

```

## disassembly

```asm
0x180001948  mov     [rsp+arg_0], rbx
0x18000194d  push    rdi
0x18000194e  sub     rsp, 20h
0x180001952  mov     rdi, [rcx+90h]
0x180001959  mov     rbx, rcx
0x18000195c  test    rdi, rdi
0x18000195f  jz      short loc_180001980
0x180001961  call    cs:__imp_GetProcessHeap
0x180001967  mov     r8, rdi; lpMem
0x18000196a  xor     edx, edx; dwFlags
0x18000196c  mov     rcx, rax; hHeap
0x18000196f  call    cs:__imp_HeapFree
0x180001975  mov     qword ptr [rbx+90h], 0
0x180001980  mov     rcx, [rbx+0A0h]; hAlgorithm
0x180001987  test    rcx, rcx
0x18000198a  jz      short loc_180001994
0x18000198c  xor     edx, edx; dwFlags
0x18000198e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180001994  mov     rcx, [rbx+0B0h]; hHash
0x18000199b  test    rcx, rcx
0x18000199e  jz      short loc_1800019A6
0x1800019a0  call    cs:__imp_BCryptDestroyHash
0x1800019a6  mov     rcx, [rbx+0A8h]; hAlgorithm
0x1800019ad  test    rcx, rcx
0x1800019b0  jz      short loc_1800019BA
0x1800019b2  xor     edx, edx; dwFlags
0x1800019b4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800019ba  mov     rcx, rbx; this
0x1800019bd  mov     rbx, [rsp+28h+arg_0]
0x1800019c2  add     rsp, 20h
0x1800019c6  pop     rdi
0x1800019c7  jmp     ??1File@@QEAA@XZ; File::~File(void)
```
