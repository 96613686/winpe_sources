# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180002670`
- end: `0x180002757`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `231`
- prototype: `bool __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d00`
- `0x180003580`

## callees

- `0x180002670`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800026b1`
- `KERNEL32!HeapFree` at `0x180002727`
- `KERNEL32!HeapFree` at `0x1800026b1`
- `KERNEL32!HeapFree` at `0x180002727`
- `KERNEL32!HeapAlloc` at `0x1800026ec`
- `KERNEL32!HeapAlloc` at `0x1800026ec`
- `KERNEL32!GetProcessHeap` at `0x1800026a3`
- `KERNEL32!GetProcessHeap` at `0x1800026dd`
- `KERNEL32!GetProcessHeap` at `0x180002719`
- `KERNEL32!GetProcessHeap` at `0x1800026a3`
- `KERNEL32!GetProcessHeap` at `0x1800026dd`
- `KERNEL32!GetProcessHeap` at `0x180002719`

## pseudocode

```c
bool __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  volatile signed __int32 *v7; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // r14
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    v7 = (volatile signed __int32 *)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = v7;
    if ( v7 )
    {
      *v7 = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      this[1] = a2;
      _InterlockedIncrement(v9);
      LOBYTE(v7) = 1;
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    LOBYTE(v7) = 1;
  }
  return (char)v7;
}

```

## disassembly

```asm
0x180002670  mov     [rsp+arg_8], rbx
0x180002675  mov     [rsp+arg_10], rbp
0x18000267a  push    rdi
0x18000267b  sub     rsp, 20h
0x18000267f  mov     rbp, rdx
0x180002682  mov     rdi, rcx
0x180002685  test    rdx, rdx
0x180002688  jnz     short loc_1800026D8
0x18000268a  mov     rcx, [rcx]
0x18000268d  test    rcx, rcx
0x180002690  jz      short loc_1800026C6
0x180002692  mov     eax, 0FFFFFFFFh
0x180002697  lock xadd [rcx], eax
0x18000269b  cmp     eax, 1
0x18000269e  jnz     short loc_1800026B7
0x1800026a0  mov     rbx, [rdi]
0x1800026a3  call    cs:__imp_GetProcessHeap
0x1800026a9  mov     r8, rbx; lpMem
0x1800026ac  xor     edx, edx; dwFlags
0x1800026ae  mov     rcx, rax; hHeap
0x1800026b1  call    cs:__imp_HeapFree
0x1800026b7  mov     qword ptr [rdi], 0
0x1800026be  mov     qword ptr [rdi+8], 0
0x1800026c6  mov     al, 1
0x1800026c8  mov     rbx, [rsp+28h+arg_8]
0x1800026cd  mov     rbp, [rsp+28h+arg_10]
0x1800026d2  add     rsp, 20h
0x1800026d6  pop     rdi
0x1800026d7  retn
0x1800026d8  mov     [rsp+28h+arg_0], r14
0x1800026dd  call    cs:__imp_GetProcessHeap
0x1800026e3  lea     r8, [rbp+4]; dwBytes
0x1800026e7  xor     edx, edx; dwFlags
0x1800026e9  mov     rcx, rax; hHeap
0x1800026ec  call    cs:__imp_HeapAlloc
0x1800026f2  mov     r14, rax
0x1800026f5  test    rax, rax
0x1800026f8  jz      short loc_180002742
0x1800026fa  mov     dword ptr [rax], 0
0x180002700  mov     rcx, [rdi]
0x180002703  test    rcx, rcx
0x180002706  jz      short loc_180002735
0x180002708  mov     eax, 0FFFFFFFFh
0x18000270d  lock xadd [rcx], eax
0x180002711  cmp     eax, 1
0x180002714  jnz     short loc_18000272D
0x180002716  mov     rbx, [rdi]
0x180002719  call    cs:__imp_GetProcessHeap
0x18000271f  mov     r8, rbx; lpMem
0x180002722  xor     edx, edx; dwFlags
0x180002724  mov     rcx, rax; hHeap
0x180002727  call    cs:__imp_HeapFree
0x18000272d  mov     qword ptr [rdi+8], 0
0x180002735  mov     [rdi], r14
0x180002738  mov     [rdi+8], rbp
0x18000273c  lock inc dword ptr [r14]
0x180002740  mov     al, 1
0x180002742  mov     r14, [rsp+28h+arg_0]
0x180002747  mov     rbx, [rsp+28h+arg_8]
0x18000274c  mov     rbp, [rsp+28h+arg_10]
0x180002751  add     rsp, 20h
0x180002755  pop     rdi
0x180002756  retn
```
