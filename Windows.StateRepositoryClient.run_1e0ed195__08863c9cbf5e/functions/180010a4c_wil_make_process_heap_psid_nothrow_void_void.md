# wil::make_process_heap_psid_nothrow(void *,void * *)

- ea: `0x180010a4c`
- end: `0x180010acc`
- name: `?make_process_heap_psid_nothrow@wil@@YAJPEAXPEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(wil *__hidden this, void *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800112b0`

## callees

- `0x1800075e4`
- `0x180010a4c`
- `0x180026690`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010a80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010a80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a6f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010a67`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010a67`

## string_xrefs

- `0x180010a93`: `onecore\base\appmodel\StateRepository\common\inc\SRwil.hpp`

## pseudocode

```c
__int64 __fastcall wil::make_process_heap_psid_nothrow(wil *this, _QWORD *a2, void **a3)
{
  size_t LengthSid; // rbp
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  void *v8; // rsi
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  if ( this )
  {
    LengthSid = GetLengthSid(this);
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 8u, (unsigned int)LengthSid);
    v8 = v7;
    if ( !v7 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\common\\inc\\SRwil.hpp",
        (const char *)0x8007000ELL,
        v10);
      return 2147942414LL;
    }
    memcpy_0(v7, this, LengthSid);
    *a2 = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180010a4c  push    rbx
0x180010a4e  push    rbp
0x180010a4f  push    rsi
0x180010a50  push    rdi
0x180010a51  sub     rsp, 28h
0x180010a55  mov     qword ptr [rdx], 0
0x180010a5c  mov     rdi, rdx
0x180010a5f  mov     rbx, rcx
0x180010a62  test    rcx, rcx
0x180010a65  jz      short loc_180010AC1
0x180010a67  call    cs:__imp_GetLengthSid
0x180010a6d  mov     ebp, eax
0x180010a6f  call    cs:__imp_GetProcessHeap
0x180010a75  mov     r8d, ebp; dwBytes
0x180010a78  mov     edx, 8; dwFlags
0x180010a7d  mov     rcx, rax; hHeap
0x180010a80  call    cs:__imp_HeapAlloc
0x180010a86  mov     rsi, rax
0x180010a89  test    rax, rax
0x180010a8c  jnz     short loc_180010AB0
0x180010a8e  mov     rcx, [rsp+48h]; this
0x180010a93  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\StateRepositor"...
0x180010a9a  mov     ebx, 8007000Eh
0x180010a9f  mov     edx, 0B1h; void *
0x180010aa4  mov     r9d, ebx; char *
0x180010aa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010aac  mov     eax, ebx
0x180010aae  jmp     short loc_180010AC3
0x180010ab0  mov     r8, rbp; Size
0x180010ab3  mov     rdx, rbx; Src
0x180010ab6  mov     rcx, rsi; void *
0x180010ab9  call    memcpy_0
0x180010abe  mov     [rdi], rsi
0x180010ac1  xor     eax, eax
0x180010ac3  add     rsp, 28h
0x180010ac7  pop     rdi
0x180010ac8  pop     rsi
0x180010ac9  pop     rbp
0x180010aca  pop     rbx
0x180010acb  retn
```
