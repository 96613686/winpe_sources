# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000fb70`
- end: `0x18000fc57`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `231`
- prototype: `bool __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fc60`
- `0x180013910`

## callees

- `0x18000fb70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000fbb1`
- `KERNEL32!HeapFree` at `0x18000fc27`
- `KERNEL32!HeapFree` at `0x18000fbb1`
- `KERNEL32!HeapFree` at `0x18000fc27`
- `KERNEL32!GetProcessHeap` at `0x18000fba3`
- `KERNEL32!GetProcessHeap` at `0x18000fbdd`
- `KERNEL32!GetProcessHeap` at `0x18000fc19`
- `KERNEL32!GetProcessHeap` at `0x18000fba3`
- `KERNEL32!GetProcessHeap` at `0x18000fbdd`
- `KERNEL32!GetProcessHeap` at `0x18000fc19`
- `KERNEL32!HeapAlloc` at `0x18000fbec`
- `KERNEL32!HeapAlloc` at `0x18000fbec`

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
0x18000fb70  mov     [rsp+arg_8], rbx
0x18000fb75  mov     [rsp+arg_10], rbp
0x18000fb7a  push    rdi
0x18000fb7b  sub     rsp, 20h
0x18000fb7f  mov     rbp, rdx
0x18000fb82  mov     rdi, rcx
0x18000fb85  test    rdx, rdx
0x18000fb88  jnz     short loc_18000FBD8
0x18000fb8a  mov     rcx, [rcx]
0x18000fb8d  test    rcx, rcx
0x18000fb90  jz      short loc_18000FBC6
0x18000fb92  mov     eax, 0FFFFFFFFh
0x18000fb97  lock xadd [rcx], eax
0x18000fb9b  cmp     eax, 1
0x18000fb9e  jnz     short loc_18000FBB7
0x18000fba0  mov     rbx, [rdi]
0x18000fba3  call    cs:__imp_GetProcessHeap
0x18000fba9  mov     r8, rbx; lpMem
0x18000fbac  xor     edx, edx; dwFlags
0x18000fbae  mov     rcx, rax; hHeap
0x18000fbb1  call    cs:__imp_HeapFree
0x18000fbb7  mov     qword ptr [rdi], 0
0x18000fbbe  mov     qword ptr [rdi+8], 0
0x18000fbc6  mov     al, 1
0x18000fbc8  mov     rbx, [rsp+28h+arg_8]
0x18000fbcd  mov     rbp, [rsp+28h+arg_10]
0x18000fbd2  add     rsp, 20h
0x18000fbd6  pop     rdi
0x18000fbd7  retn
0x18000fbd8  mov     [rsp+28h+arg_0], r14
0x18000fbdd  call    cs:__imp_GetProcessHeap
0x18000fbe3  lea     r8, [rbp+4]; dwBytes
0x18000fbe7  xor     edx, edx; dwFlags
0x18000fbe9  mov     rcx, rax; hHeap
0x18000fbec  call    cs:__imp_HeapAlloc
0x18000fbf2  mov     r14, rax
0x18000fbf5  test    rax, rax
0x18000fbf8  jz      short loc_18000FC42
0x18000fbfa  mov     dword ptr [rax], 0
0x18000fc00  mov     rcx, [rdi]
0x18000fc03  test    rcx, rcx
0x18000fc06  jz      short loc_18000FC35
0x18000fc08  mov     eax, 0FFFFFFFFh
0x18000fc0d  lock xadd [rcx], eax
0x18000fc11  cmp     eax, 1
0x18000fc14  jnz     short loc_18000FC2D
0x18000fc16  mov     rbx, [rdi]
0x18000fc19  call    cs:__imp_GetProcessHeap
0x18000fc1f  mov     r8, rbx; lpMem
0x18000fc22  xor     edx, edx; dwFlags
0x18000fc24  mov     rcx, rax; hHeap
0x18000fc27  call    cs:__imp_HeapFree
0x18000fc2d  mov     qword ptr [rdi+8], 0
0x18000fc35  mov     [rdi], r14
0x18000fc38  mov     [rdi+8], rbp
0x18000fc3c  lock inc dword ptr [r14]
0x18000fc40  mov     al, 1
0x18000fc42  mov     r14, [rsp+28h+arg_0]
0x18000fc47  mov     rbx, [rsp+28h+arg_8]
0x18000fc4c  mov     rbp, [rsp+28h+arg_10]
0x18000fc51  add     rsp, 20h
0x18000fc55  pop     rdi
0x18000fc56  retn
```
