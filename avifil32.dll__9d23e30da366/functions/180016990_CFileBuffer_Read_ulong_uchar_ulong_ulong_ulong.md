# CFileBuffer::Read(ulong,uchar *,ulong,ulong,ulong *)

- ea: `0x180016990`
- end: `0x180016a8e`
- name: `?Read@CFileBuffer@@QEAAHKPEAEKKPEAK@Z`
- size: `254`
- prototype: `__int64 __fastcall(CFileBuffer *this, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016a94`

## callees

- `0x1800163d4`
- `0x180016990`
- `0x180016e2c`
- `0x180016f00`
- `0x180017359`

## pseudocode

```c
__int64 __fastcall CFileBuffer::Read(
        CFileBuffer *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int v9; // ecx
  unsigned int *v10; // rdi
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // r10
  unsigned int v13; // r8d
  unsigned int v14; // ecx
  unsigned int v15; // r9d
  int v16; // esi
  __int64 result; // rax

  *((_DWORD *)this + 10) = a5;
  v9 = *((_DWORD *)this + 8);
  *a6 = 0;
  v10 = (unsigned int *)((char *)this + 28);
  v11 = a2;
  if ( a2 < v9 || a2 >= *v10 + v9 )
  {
    if ( !(unsigned int)CFileBuffer::Commit(this) || !(unsigned int)CFileBuffer::WaitComplete(this) )
      return 0;
    v12 = *((unsigned int *)this + 9);
    v13 = v11 - v11 % v12;
    *((_DWORD *)this + 8) = v13;
    v14 = a4 + v11 % v12;
    if ( v14 < 0x3000 )
      v14 = 12288;
    v15 = v14 + v12 - 1 - (v14 + v12 - 1) % v12;
    if ( v15 >= *((_DWORD *)this + 6) )
      v15 = *((_DWORD *)this + 6);
    *v10 = v15;
    if ( !CFileBuffer::ReadIntoBuffer(this, 0, v13, v15) || !(unsigned int)CFileBuffer::WaitComplete(this) )
      return 0;
  }
  v16 = v11 - *((_DWORD *)this + 8);
  if ( a4 >= *v10 - v16 )
    a4 = *v10 - v16;
  memcpy_0(a3, (const void *)(*((_QWORD *)this + 1) + v16), a4);
  result = 1;
  *a6 = a4;
  return result;
}

```

## disassembly

```asm
0x180016990  push    rbx
0x180016992  push    rbp
0x180016993  push    rsi
0x180016994  push    rdi
0x180016995  push    r14
0x180016997  push    r15
0x180016999  sub     rsp, 28h
0x18001699d  mov     r14, [rsp+58h+arg_28]
0x1800169a5  mov     rbx, rcx
0x1800169a8  mov     eax, [rsp+58h+arg_20]
0x1800169af  mov     ebp, r9d
0x1800169b2  mov     [rcx+28h], eax
0x1800169b5  mov     r15, r8
0x1800169b8  mov     ecx, [rcx+20h]
0x1800169bb  mov     dword ptr [r14], 0
0x1800169c2  lea     rdi, [rbx+1Ch]
0x1800169c6  mov     esi, edx
0x1800169c8  cmp     edx, ecx
0x1800169ca  jb      short loc_1800169D6
0x1800169cc  add     ecx, [rdi]
0x1800169ce  cmp     esi, ecx
0x1800169d0  jb      loc_180016A57
0x1800169d6  mov     rcx, rbx; this
0x1800169d9  call    ?Commit@CFileBuffer@@QEAAHXZ; CFileBuffer::Commit(void)
0x1800169de  test    eax, eax
0x1800169e0  jz      loc_180016A7F
0x1800169e6  mov     rcx, rbx; this
0x1800169e9  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x1800169ee  test    eax, eax
0x1800169f0  jz      loc_180016A7F
0x1800169f6  mov     r10d, [rbx+24h]
0x1800169fa  xor     edx, edx
0x1800169fc  mov     rax, rsi
0x1800169ff  mov     r8, rsi
0x180016a02  div     r10
0x180016a05  mov     eax, 3000h
0x180016a0a  mov     ecx, esi
0x180016a0c  sub     r8d, edx; unsigned int
0x180016a0f  lea     r9, [r10-1]
0x180016a13  sub     ecx, r8d
0x180016a16  mov     [rbx+20h], r8d
0x180016a1a  add     ecx, ebp
0x180016a1c  cmp     ecx, eax
0x180016a1e  cmovb   ecx, eax
0x180016a21  xor     edx, edx
0x180016a23  mov     eax, ecx
0x180016a25  mov     rcx, rbx; this
0x180016a28  add     r9, rax
0x180016a2b  mov     rax, r9
0x180016a2e  div     r10
0x180016a31  sub     r9d, edx
0x180016a34  cmp     r9d, [rbx+18h]
0x180016a38  cmovnb  r9d, [rbx+18h]; unsigned int
0x180016a3d  xor     edx, edx; int
0x180016a3f  mov     [rdi], r9d
0x180016a42  call    ?ReadIntoBuffer@CFileBuffer@@AEAAHHKK@Z; CFileBuffer::ReadIntoBuffer(int,ulong,ulong)
0x180016a47  test    eax, eax
0x180016a49  jz      short loc_180016A7F
0x180016a4b  mov     rcx, rbx; this
0x180016a4e  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x180016a53  test    eax, eax
0x180016a55  jz      short loc_180016A7F
0x180016a57  sub     esi, [rbx+20h]
0x180016a5a  mov     rcx, r15; void *
0x180016a5d  mov     eax, [rdi]
0x180016a5f  sub     eax, esi
0x180016a61  movsxd  rdx, esi
0x180016a64  cmp     ebp, eax
0x180016a66  cmovnb  ebp, eax
0x180016a69  add     rdx, [rbx+8]; Src
0x180016a6d  mov     r8d, ebp; Size
0x180016a70  call    memcpy_0
0x180016a75  mov     eax, 1
0x180016a7a  mov     [r14], ebp
0x180016a7d  jmp     short loc_180016A81
0x180016a7f  xor     eax, eax
0x180016a81  add     rsp, 28h
0x180016a85  pop     r15
0x180016a87  pop     r14
0x180016a89  pop     rdi
0x180016a8a  pop     rsi
0x180016a8b  pop     rbp
0x180016a8c  pop     rbx
0x180016a8d  retn
```
