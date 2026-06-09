# CSpDynamicString::_free(void)

- ea: `0x14001af50`
- end: `0x14001aff6`
- name: `?_free@CSpDynamicString@@AEAAXXZ`
- size: `166`
- prototype: `void __fastcall(CSpDynamicString *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019e28`
- `0x14001a8d0`
- `0x14001f188`
- `0x14001f240`

## callees

- `0x14001af50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001afde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001afde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001af69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001af69`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x14001af77`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x14001af77`

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
0x14001af50  mov     [rsp+arg_0], rbx
0x14001af55  push    rdi
0x14001af56  sub     rsp, 20h
0x14001af5a  mov     rdi, [rcx]
0x14001af5d  mov     rbx, rcx
0x14001af60  test    rdi, rdi
0x14001af63  jz      loc_14001AFEB
0x14001af69  call    cs:__imp_GetProcessHeap
0x14001af6f  mov     r8, rdi; lpMem
0x14001af72  xor     edx, edx; dwFlags
0x14001af74  mov     rcx, rax; hHeap
0x14001af77  call    cs:__imp_HeapSize
0x14001af7d  lea     rdx, [rax-3]
0x14001af81  cmp     rdx, 0FFFFFFFFFFFFFFFBh
0x14001af85  ja      short loc_14001AFDB
0x14001af87  shr     rax, 1
0x14001af8a  mov     r9d, 8
0x14001af90  lea     rdx, [rax-1]
0x14001af94  cmp     rdx, r9
0x14001af97  jnb     short loc_14001AFA2
0x14001af99  test    rdx, rdx
0x14001af9c  jz      short loc_14001AFDB
0x14001af9e  xor     ecx, ecx
0x14001afa0  jmp     short loc_14001AFB8
0x14001afa2  mov     rdi, [rbx]
0x14001afa5  cmp     rdi, rbx
0x14001afa8  ja      short loc_14001AFCB
0x14001afaa  xor     ecx, ecx
0x14001afac  lea     rax, [rdi+0Eh]
0x14001afb0  mov     rdx, r9
0x14001afb3  cmp     rax, rbx
0x14001afb6  jb      short loc_14001AFCB
0x14001afb8  mov     rax, [rbx]
0x14001afbb  mov     word ptr [rax+rcx*2], 0DEADh
0x14001afc1  inc     rcx
0x14001afc4  cmp     rcx, rdx
0x14001afc7  jb      short loc_14001AFB8
0x14001afc9  jmp     short loc_14001AFDB
0x14001afcb  mov     r8d, 0DEADh
0x14001afd1  mov     rcx, r9
0x14001afd4  movzx   eax, r8w
0x14001afd8  rep stosw
0x14001afdb  mov     rcx, [rbx]; pv
0x14001afde  call    cs:__imp_CoTaskMemFree
0x14001afe4  mov     qword ptr [rbx], 0
0x14001afeb  mov     rbx, [rsp+28h+arg_0]
0x14001aff0  add     rsp, 20h
0x14001aff4  pop     rdi
0x14001aff5  retn
```
