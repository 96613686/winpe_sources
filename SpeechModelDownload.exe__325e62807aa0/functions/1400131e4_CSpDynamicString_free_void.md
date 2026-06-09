# CSpDynamicString::_free(void)

- ea: `0x1400131e4`
- end: `0x14001328a`
- name: `?_free@CSpDynamicString@@AEAAXXZ`
- size: `166`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `11`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b2ec`
- `0x14000b7f0`
- `0x14000bd5c`
- `0x14000f920`
- `0x14001c650`
- `0x14001c670`
- `0x14001c690`
- `0x14001c6b0`
- `0x14001c6d0`
- `0x14001c6f0`
- `0x14001c710`

## callees

- `0x1400131e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400131fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400131fd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x14001320b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x14001320b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013272`

## pseudocode

```c
void __fastcall CSpDynamicString::_free(LPVOID *this)
{
  const void *v1; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v4; // rax
  SIZE_T v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  _WORD *v8; // rdi
  __int64 i; // rcx

  v1 = *this;
  if ( *this )
  {
    ProcessHeap = GetProcessHeap();
    v4 = HeapSize(ProcessHeap, 0, v1);
    if ( v4 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v5 = v4 >> 1;
      v6 = v5 - 1;
      if ( v5 - 1 >= 8 )
      {
        v8 = *this;
        if ( *this > this || (v7 = 0, v6 = 8, v8 + 7 < (_WORD *)this) )
        {
          for ( i = 8; i; --i )
            *v8++ = -8531;
          goto LABEL_13;
        }
        goto LABEL_8;
      }
      if ( v5 != 1 )
      {
        v7 = 0;
        do
LABEL_8:
          *((_WORD *)*this + v7++) = -8531;
        while ( v7 < v6 );
      }
    }
LABEL_13:
    CoTaskMemFree(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x1400131e4  mov     [rsp+arg_0], rbx
0x1400131e9  push    rdi
0x1400131ea  sub     rsp, 20h
0x1400131ee  mov     rdi, [rcx]
0x1400131f1  mov     rbx, rcx
0x1400131f4  test    rdi, rdi
0x1400131f7  jz      loc_14001327F
0x1400131fd  call    cs:__imp_GetProcessHeap
0x140013203  mov     r8, rdi; lpMem
0x140013206  xor     edx, edx; dwFlags
0x140013208  mov     rcx, rax; hHeap
0x14001320b  call    cs:__imp_HeapSize
0x140013211  lea     rdx, [rax-3]
0x140013215  cmp     rdx, 0FFFFFFFFFFFFFFFBh
0x140013219  ja      short loc_14001326F
0x14001321b  shr     rax, 1
0x14001321e  mov     r9d, 8
0x140013224  lea     rdx, [rax-1]
0x140013228  cmp     rdx, r9
0x14001322b  jnb     short loc_140013236
0x14001322d  test    rdx, rdx
0x140013230  jz      short loc_14001326F
0x140013232  xor     ecx, ecx
0x140013234  jmp     short loc_14001324C
0x140013236  mov     rdi, [rbx]
0x140013239  cmp     rdi, rbx
0x14001323c  ja      short loc_14001325F
0x14001323e  xor     ecx, ecx
0x140013240  lea     rax, [rdi+0Eh]
0x140013244  mov     rdx, r9
0x140013247  cmp     rax, rbx
0x14001324a  jb      short loc_14001325F
0x14001324c  mov     rax, [rbx]
0x14001324f  mov     word ptr [rax+rcx*2], 0DEADh
0x140013255  inc     rcx
0x140013258  cmp     rcx, rdx
0x14001325b  jb      short loc_14001324C
0x14001325d  jmp     short loc_14001326F
0x14001325f  mov     r8d, 0DEADh
0x140013265  mov     rcx, r9
0x140013268  movzx   eax, r8w
0x14001326c  rep stosw
0x14001326f  mov     rcx, [rbx]; pv
0x140013272  call    cs:__imp_CoTaskMemFree
0x140013278  mov     qword ptr [rbx], 0
0x14001327f  mov     rbx, [rsp+28h+arg_0]
0x140013284  add     rsp, 20h
0x140013288  pop     rdi
0x140013289  retn
```
