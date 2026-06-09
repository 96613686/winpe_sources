# CSpDynamicString::_free(void)

- ea: `0x18000d6b4`
- end: `0x18000d76d`
- name: `?_free@CSpDynamicString@@AEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CSpDynamicString *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800076fc`
- `0x180007714`
- `0x180007b44`
- `0x1800082d0`
- `0x18000dc0c`
- `0x18000e2c8`
- `0x18000f270`

## callees

- `0x18000d6b4`

## import_xrefs

- `KERNEL32!HeapSize` at `0x18000d6e1`
- `KERNEL32!HeapSize` at `0x18000d6e1`
- `KERNEL32!GetProcessHeap` at `0x18000d6cd`
- `KERNEL32!GetProcessHeap` at `0x18000d6cd`
- `ole32!CoTaskMemFree` at `0x18000d74e`
- `ole32!CoTaskMemFree` at `0x18000d74e`

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
0x18000d6b4  mov     [rsp+arg_0], rbx
0x18000d6b9  push    rdi
0x18000d6ba  sub     rsp, 20h
0x18000d6be  mov     rdi, [rcx]
0x18000d6c1  mov     rbx, rcx
0x18000d6c4  test    rdi, rdi
0x18000d6c7  jz      loc_18000D761
0x18000d6cd  call    cs:__imp_GetProcessHeap
0x18000d6d4  nop     dword ptr [rax+rax+00h]
0x18000d6d9  mov     r8, rdi; lpMem
0x18000d6dc  xor     edx, edx; dwFlags
0x18000d6de  mov     rcx, rax; hHeap
0x18000d6e1  call    cs:__imp_HeapSize
0x18000d6e8  nop     dword ptr [rax+rax+00h]
0x18000d6ed  lea     rdx, [rax-3]
0x18000d6f1  cmp     rdx, 0FFFFFFFFFFFFFFFBh
0x18000d6f5  ja      short loc_18000D74B
0x18000d6f7  shr     rax, 1
0x18000d6fa  mov     r9d, 8
0x18000d700  lea     rdx, [rax-1]
0x18000d704  cmp     rdx, r9
0x18000d707  jnb     short loc_18000D712
0x18000d709  test    rdx, rdx
0x18000d70c  jz      short loc_18000D74B
0x18000d70e  xor     ecx, ecx
0x18000d710  jmp     short loc_18000D728
0x18000d712  mov     rdi, [rbx]
0x18000d715  cmp     rdi, rbx
0x18000d718  ja      short loc_18000D73B
0x18000d71a  xor     ecx, ecx
0x18000d71c  lea     rax, [rdi+0Eh]
0x18000d720  mov     rdx, r9
0x18000d723  cmp     rax, rbx
0x18000d726  jb      short loc_18000D73B
0x18000d728  mov     rax, [rbx]
0x18000d72b  mov     word ptr [rax+rcx*2], 0DEADh
0x18000d731  inc     rcx
0x18000d734  cmp     rcx, rdx
0x18000d737  jb      short loc_18000D728
0x18000d739  jmp     short loc_18000D74B
0x18000d73b  mov     r8d, 0DEADh
0x18000d741  mov     rcx, r9
0x18000d744  movzx   eax, r8w
0x18000d748  rep stosw
0x18000d74b  mov     rcx, [rbx]; pv
0x18000d74e  call    cs:__imp_CoTaskMemFree
0x18000d755  nop     dword ptr [rax+rax+00h]
0x18000d75a  mov     qword ptr [rbx], 0
0x18000d761  mov     rbx, [rsp+28h+arg_0]
0x18000d766  add     rsp, 20h
0x18000d76a  pop     rdi
0x18000d76b  retn
```
