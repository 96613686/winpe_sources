# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180020624`
- end: `0x1800206ae`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800235fc`

## callees

- `0x180020624`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180020655`
- `KERNEL32!GetProcessHeap` at `0x18002067d`
- `KERNEL32!GetProcessHeap` at `0x180020655`
- `KERNEL32!GetProcessHeap` at `0x18002067d`
- `KERNEL32!HeapFree` at `0x180020663`
- `KERNEL32!HeapFree` at `0x18002068c`
- `KERNEL32!HeapFree` at `0x180020663`
- `KERNEL32!HeapFree` at `0x18002068c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax

  v1 = *((_QWORD *)this + 3);
  v3 = v1 + 88LL * *((unsigned __int16 *)this + 16);
  if ( v1 != v3 )
  {
    v4 = v1 + 72;
    do
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, *(LPVOID *)v4);
      *(_QWORD *)v4 = 0;
      *(_QWORD *)(v4 + 8) = 0;
      v4 += 88;
    }
    while ( v4 - 72 != v3 );
  }
  v6 = GetProcessHeap();
  HeapFree(v6, 0, *((LPVOID *)this + 3));
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180020624  mov     [rsp+arg_0], rbx
0x180020629  mov     [rsp+arg_8], rbp
0x18002062e  mov     [rsp+arg_10], rsi
0x180020633  push    rdi
0x180020634  sub     rsp, 20h
0x180020638  mov     rdi, [rcx+18h]
0x18002063c  xor     ebp, ebp
0x18002063e  movzx   eax, word ptr [rcx+20h]
0x180020642  mov     rbx, rcx
0x180020645  imul    rsi, rax, 58h ; 'X'
0x180020649  add     rsi, rdi
0x18002064c  cmp     rdi, rsi
0x18002064f  jz      short loc_18002067D
0x180020651  add     rdi, 48h ; 'H'
0x180020655  call    cs:__imp_GetProcessHeap
0x18002065b  mov     r8, [rdi]; lpMem
0x18002065e  xor     edx, edx; dwFlags
0x180020660  mov     rcx, rax; hHeap
0x180020663  call    cs:__imp_HeapFree
0x180020669  mov     [rdi], rbp
0x18002066c  mov     [rdi+8], rbp
0x180020670  lea     rdi, [rdi+58h]
0x180020674  lea     rax, [rdi-48h]
0x180020678  cmp     rax, rsi
0x18002067b  jnz     short loc_180020655
0x18002067d  call    cs:__imp_GetProcessHeap
0x180020683  mov     r8, [rbx+18h]; lpMem
0x180020687  xor     edx, edx; dwFlags
0x180020689  mov     rcx, rax; hHeap
0x18002068c  call    cs:__imp_HeapFree
0x180020692  mov     rsi, [rsp+28h+arg_10]
0x180020697  mov     [rbx+20h], ebp
0x18002069a  mov     [rbx+18h], rbp
0x18002069e  mov     rbx, [rsp+28h+arg_0]
0x1800206a3  mov     rbp, [rsp+28h+arg_8]
0x1800206a8  add     rsp, 20h
0x1800206ac  pop     rdi
0x1800206ad  retn
```
