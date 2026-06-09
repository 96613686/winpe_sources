# wil::details::shared_buffer::create(void const *,unsigned __int64)

- ea: `0x18001f23c`
- end: `0x18001f31f`
- name: `?create@shared_buffer@details@wil@@QEAA_NPEBX_K@Z`
- size: `227`
- prototype: `bool(wil::details::shared_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f568`
- `0x18001f8f0`

## callees

- `0x18001f23c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001f2c7`
- `msvcrt!memcpy_s` at `0x18001f2c7`
- `KERNEL32!HeapAlloc` at `0x18001f2a4`
- `KERNEL32!HeapAlloc` at `0x18001f2a4`
- `KERNEL32!GetProcessHeap` at `0x18001f276`
- `KERNEL32!GetProcessHeap` at `0x18001f295`
- `KERNEL32!GetProcessHeap` at `0x18001f2e1`
- `KERNEL32!GetProcessHeap` at `0x18001f276`
- `KERNEL32!GetProcessHeap` at `0x18001f295`
- `KERNEL32!GetProcessHeap` at `0x18001f2e1`
- `KERNEL32!HeapFree` at `0x18001f284`
- `KERNEL32!HeapFree` at `0x18001f2ef`
- `KERNEL32!HeapFree` at `0x18001f284`
- `KERNEL32!HeapFree` at `0x18001f2ef`

## pseudocode

```c
bool __fastcall wil::details::shared_buffer::create(LPVOID *this, const void *a2, rsize_t a3)
{
  volatile signed __int32 *v6; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  volatile signed __int32 *v9; // rax
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( !a3 )
  {
    v6 = (volatile signed __int32 *)*this;
    if ( v6 )
    {
      if ( !_InterlockedDecrement(v6) )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, *this);
      }
      *this = 0;
      this[1] = 0;
    }
LABEL_14:
    LOBYTE(v9) = 1;
    return (char)v9;
  }
  v8 = GetProcessHeap();
  v9 = (volatile signed __int32 *)HeapAlloc(v8, 0, a3 + 4);
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    if ( a2 )
      memcpy_s((void *const)(v9 + 1), a3, a2, a3);
    if ( *this )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)*this) )
      {
        v11 = GetProcessHeap();
        HeapFree(v11, 0, *this);
      }
      *this = 0;
      this[1] = 0;
    }
    *this = (LPVOID)v10;
    this[1] = (LPVOID)a3;
    _InterlockedIncrement(v10);
    goto LABEL_14;
  }
  return (char)v9;
}

```

## disassembly

```asm
0x18001f23c  mov     [rsp+arg_0], rbx
0x18001f241  mov     [rsp+arg_8], rbp
0x18001f246  mov     [rsp+arg_10], rsi
0x18001f24b  push    rdi
0x18001f24c  sub     rsp, 20h
0x18001f250  mov     rsi, r8
0x18001f253  mov     rbp, rdx
0x18001f256  mov     rdi, rcx
0x18001f259  test    r8, r8
0x18001f25c  jnz     short loc_18001F295
0x18001f25e  mov     rcx, [rcx]
0x18001f261  test    rcx, rcx
0x18001f264  jz      loc_18001F308
0x18001f26a  or      eax, 0FFFFFFFFh
0x18001f26d  lock xadd [rcx], eax
0x18001f271  sub     eax, 1
0x18001f274  jnz     short loc_18001F28A
0x18001f276  call    cs:__imp_GetProcessHeap
0x18001f27c  mov     r8, [rdi]; lpMem
0x18001f27f  xor     edx, edx; dwFlags
0x18001f281  mov     rcx, rax; hHeap
0x18001f284  call    cs:__imp_HeapFree
0x18001f28a  and     qword ptr [rdi], 0
0x18001f28e  and     qword ptr [rdi+8], 0
0x18001f293  jmp     short loc_18001F308
0x18001f295  call    cs:__imp_GetProcessHeap
0x18001f29b  lea     r8, [rsi+4]; dwBytes
0x18001f29f  xor     edx, edx; dwFlags
0x18001f2a1  mov     rcx, rax; hHeap
0x18001f2a4  call    cs:__imp_HeapAlloc
0x18001f2aa  mov     rbx, rax
0x18001f2ad  test    rax, rax
0x18001f2b0  jz      short loc_18001F30A
0x18001f2b2  and     dword ptr [rax], 0
0x18001f2b5  test    rbp, rbp
0x18001f2b8  jz      short loc_18001F2CD
0x18001f2ba  lea     rcx, [rax+4]; Destination
0x18001f2be  mov     r9, rsi; SourceSize
0x18001f2c1  mov     r8, rbp; Source
0x18001f2c4  mov     rdx, rsi; DestinationSize
0x18001f2c7  call    cs:__imp_memcpy_s
0x18001f2cd  mov     rcx, [rdi]
0x18001f2d0  test    rcx, rcx
0x18001f2d3  jz      short loc_18001F2FE
0x18001f2d5  or      eax, 0FFFFFFFFh
0x18001f2d8  lock xadd [rcx], eax
0x18001f2dc  sub     eax, 1
0x18001f2df  jnz     short loc_18001F2F5
0x18001f2e1  call    cs:__imp_GetProcessHeap
0x18001f2e7  mov     r8, [rdi]; lpMem
0x18001f2ea  xor     edx, edx; dwFlags
0x18001f2ec  mov     rcx, rax; hHeap
0x18001f2ef  call    cs:__imp_HeapFree
0x18001f2f5  and     qword ptr [rdi], 0
0x18001f2f9  and     qword ptr [rdi+8], 0
0x18001f2fe  mov     [rdi], rbx
0x18001f301  mov     [rdi+8], rsi
0x18001f305  lock inc dword ptr [rbx]
0x18001f308  mov     al, 1
0x18001f30a  mov     rbx, [rsp+28h+arg_0]
0x18001f30f  mov     rbp, [rsp+28h+arg_8]
0x18001f314  mov     rsi, [rsp+28h+arg_10]
0x18001f319  add     rsp, 20h
0x18001f31d  pop     rdi
0x18001f31e  retn
```
