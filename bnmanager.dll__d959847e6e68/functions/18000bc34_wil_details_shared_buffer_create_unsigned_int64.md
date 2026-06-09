# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000bc34`
- end: `0x18000bcf7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a948`
- `0x18000c030`

## callees

- `0x18000bc34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bc98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bc98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bcc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bcc3`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
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
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
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
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000bc34  push    rbx
0x18000bc36  push    rbp
0x18000bc37  push    rsi
0x18000bc38  push    rdi
0x18000bc39  sub     rsp, 28h
0x18000bc3d  mov     rbp, rdx
0x18000bc40  mov     rdi, rcx
0x18000bc43  test    rdx, rdx
0x18000bc46  jnz     short loc_18000BC89
0x18000bc48  mov     rcx, [rcx]
0x18000bc4b  test    rcx, rcx
0x18000bc4e  jz      short loc_18000BC82
0x18000bc50  or      eax, 0FFFFFFFFh
0x18000bc53  lock xadd [rcx], eax
0x18000bc57  cmp     eax, 1
0x18000bc5a  jnz     short loc_18000BC73
0x18000bc5c  mov     rbx, [rdi]
0x18000bc5f  call    cs:__imp_GetProcessHeap
0x18000bc65  mov     r8, rbx; lpMem
0x18000bc68  xor     edx, edx; dwFlags
0x18000bc6a  mov     rcx, rax; hHeap
0x18000bc6d  call    cs:__imp_HeapFree
0x18000bc73  mov     qword ptr [rdi], 0
0x18000bc7a  mov     qword ptr [rdi+8], 0
0x18000bc82  mov     eax, 1
0x18000bc87  jmp     short loc_18000BCEE
0x18000bc89  call    cs:__imp_GetProcessHeap
0x18000bc8f  lea     r8, [rbp+4]; dwBytes
0x18000bc93  xor     edx, edx; dwFlags
0x18000bc95  mov     rcx, rax; hHeap
0x18000bc98  call    cs:__imp_HeapAlloc
0x18000bc9e  mov     rsi, rax
0x18000bca1  test    rax, rax
0x18000bca4  jz      short loc_18000BCEE
0x18000bca6  mov     dword ptr [rax], 0
0x18000bcac  mov     rcx, [rdi]
0x18000bcaf  test    rcx, rcx
0x18000bcb2  jz      short loc_18000BCDF
0x18000bcb4  or      eax, 0FFFFFFFFh
0x18000bcb7  lock xadd [rcx], eax
0x18000bcbb  cmp     eax, 1
0x18000bcbe  jnz     short loc_18000BCD7
0x18000bcc0  mov     rbx, [rdi]
0x18000bcc3  call    cs:__imp_GetProcessHeap
0x18000bcc9  mov     r8, rbx; lpMem
0x18000bccc  xor     edx, edx; dwFlags
0x18000bcce  mov     rcx, rax; hHeap
0x18000bcd1  call    cs:__imp_HeapFree
0x18000bcd7  mov     qword ptr [rdi+8], 0
0x18000bcdf  mov     [rdi], rsi
0x18000bce2  mov     eax, 1
0x18000bce7  mov     [rdi+8], rbp
0x18000bceb  lock add [rsi], eax
0x18000bcee  add     rsp, 28h
0x18000bcf2  pop     rdi
0x18000bcf3  pop     rsi
0x18000bcf4  pop     rbp
0x18000bcf5  pop     rbx
0x18000bcf6  retn
```
