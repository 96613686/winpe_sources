# PROPERTY_BAG::CopyAllToBuffer(ulong,ulong *,ulong,uchar *,ulong *)

- ea: `0x18000fab8`
- end: `0x18000fc48`
- name: `?CopyAllToBuffer@PROPERTY_BAG@@QEAAJKPEAKKPEAE0@Z`
- size: `400`
- prototype: `__int64 __fastcall(PROPERTY_BAG *__hidden this, unsigned int, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bf00`
- `0x18000d7a0`

## callees

- `0x180003402`
- `0x18000fab8`
- `0x18001013c`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000faf8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fb77`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fb89`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fb99`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fba9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbb9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbd2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbe5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbf1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fc0d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000faf8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fb77`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fb89`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fb99`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fba9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbb9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbd2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbe5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fbf1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fc0d`

## pseudocode

```c
__int64 __fastcall PROPERTY_BAG::CopyAllToBuffer(
        PROPERTY_BAG *this,
        char a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  unsigned int v6; // edi
  __int64 v7; // rbp
  __int64 v11; // rbx
  unsigned int v12; // ebp
  unsigned int v13; // r14d
  __int64 v14; // r13
  int v15; // ebp
  BUFFER *v16; // r15
  __int64 v17; // rbx
  unsigned int *Ptr; // rbx
  const void **v19; // rax
  char v21; // [rsp+68h] [rbp+10h]

  v21 = a2;
  v6 = 28 * *((_DWORD *)this + 4);
  v7 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    do
    {
      v11 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7);
      PROPERTY_ENTRY::ReadProperty((PROPERTY_ENTRY *)v11);
      v7 = (unsigned int)(v7 + 1);
      v6 = (*((_DWORD *)BUFFER::QueryPtr((BUFFER *)(v11 + 16)) + 4) + 7 + v6) & 0xFFFFFFF8;
    }
    while ( (unsigned int)v7 < *((_DWORD *)this + 4) );
    a2 = v21;
  }
  if ( a6 )
    *a6 = v6;
  if ( a3 )
    *a3 = *((_DWORD *)this + 4);
  if ( a4 >= v6 )
  {
    v13 = 28 * *((_DWORD *)this + 4);
    v12 = 0;
    v14 = 0;
    if ( *((_DWORD *)this + 4) )
    {
      v15 = a2 & 0x20;
      do
      {
        v16 = (BUFFER *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8 * v14) + 16LL);
        v17 = 28LL * (unsigned int)v14;
        *(_DWORD *)&a5[v17] = *(_DWORD *)BUFFER::QueryPtr(v16);
        *(_DWORD *)&a5[v17 + 4] = *((_DWORD *)BUFFER::QueryPtr(v16) + 1);
        *(_DWORD *)&a5[v17 + 8] = *((_DWORD *)BUFFER::QueryPtr(v16) + 2);
        *(_DWORD *)&a5[v17 + 12] = *((_DWORD *)BUFFER::QueryPtr(v16) + 3);
        *(_DWORD *)&a5[v17 + 16] = *((_DWORD *)BUFFER::QueryPtr(v16) + 4);
        *(_DWORD *)&a5[v17 + 20] = v13;
        if ( v15 )
          *(_DWORD *)&a5[v17 + 4] |= *((_DWORD *)BUFFER::QueryPtr(v16) + 1) & 0x20;
        Ptr = (unsigned int *)BUFFER::QueryPtr(v16);
        v19 = (const void **)BUFFER::QueryPtr(v16);
        memcpy_0(&a5[v13], v19[3], Ptr[4]);
        v14 = (unsigned int)(v14 + 1);
        v13 = (*((_DWORD *)BUFFER::QueryPtr(v16) + 4) + 7 + v13) & 0xFFFFFFF8;
      }
      while ( (unsigned int)v14 < *((_DWORD *)this + 4) );
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024774;
  }
  return v12;
}

```

## disassembly

```asm
0x18000fab8  mov     [rsp+arg_0], rbx
0x18000fabd  mov     [rsp+arg_8], edx
0x18000fac1  push    rbp
0x18000fac2  push    rsi
0x18000fac3  push    rdi
0x18000fac4  push    r12
0x18000fac6  push    r13
0x18000fac8  push    r14
0x18000faca  push    r15
0x18000facc  sub     rsp, 20h
0x18000fad0  imul    edi, [rcx+10h], 1Ch
0x18000fad4  xor     ebp, ebp
0x18000fad6  mov     r15d, r9d
0x18000fad9  mov     r14, r8
0x18000fadc  mov     rsi, rcx
0x18000fadf  cmp     [rcx+10h], ebp
0x18000fae2  jbe     short loc_18000FB14
0x18000fae4  mov     rax, [rsi+8]
0x18000fae8  mov     rbx, [rax+rbp*8]
0x18000faec  mov     rcx, rbx; this
0x18000faef  call    ?ReadProperty@PROPERTY_ENTRY@@QEAAJXZ; PROPERTY_ENTRY::ReadProperty(void)
0x18000faf4  lea     rcx, [rbx+10h]
0x18000faf8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fafe  inc     ebp
0x18000fb00  mov     ecx, [rax+10h]
0x18000fb03  add     ecx, 7
0x18000fb06  add     edi, ecx
0x18000fb08  and     edi, 0FFFFFFF8h
0x18000fb0b  cmp     ebp, [rsi+10h]
0x18000fb0e  jb      short loc_18000FAE4
0x18000fb10  mov     edx, [rsp+58h+arg_8]
0x18000fb14  mov     rax, [rsp+58h+arg_28]
0x18000fb1c  test    rax, rax
0x18000fb1f  jz      short loc_18000FB23
0x18000fb21  mov     [rax], edi
0x18000fb23  test    r14, r14
0x18000fb26  jz      short loc_18000FB2E
0x18000fb28  mov     eax, [rsi+10h]
0x18000fb2b  mov     [r14], eax
0x18000fb2e  cmp     r15d, edi
0x18000fb31  jnb     short loc_18000FB3D
0x18000fb33  mov     ebp, 8007007Ah
0x18000fb38  jmp     loc_18000FC31
0x18000fb3d  imul    r14d, [rsi+10h], 1Ch
0x18000fb42  xor     ebp, ebp
0x18000fb44  mov     rdi, [rsp+58h+arg_20]
0x18000fb4c  xor     r13d, r13d
0x18000fb4f  mov     [rsp+58h+arg_18], ebp
0x18000fb53  cmp     [rsi+10h], ebp
0x18000fb56  jbe     loc_18000FC31
0x18000fb5c  and     edx, 20h
0x18000fb5f  mov     [rsp+58h+arg_8], edx
0x18000fb63  mov     ebp, edx
0x18000fb65  mov     rax, [rsi+8]
0x18000fb69  mov     ebx, r13d
0x18000fb6c  mov     r15, [rax+r13*8]
0x18000fb70  add     r15, 10h
0x18000fb74  mov     rcx, r15
0x18000fb77  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fb7d  imul    rbx, 1Ch
0x18000fb81  mov     eax, [rax]
0x18000fb83  mov     rcx, r15
0x18000fb86  mov     [rbx+rdi], eax
0x18000fb89  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fb8f  mov     rcx, r15
0x18000fb92  mov     eax, [rax+4]
0x18000fb95  mov     [rbx+rdi+4], eax
0x18000fb99  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fb9f  mov     ecx, [rax+8]
0x18000fba2  mov     [rbx+rdi+8], ecx
0x18000fba6  mov     rcx, r15
0x18000fba9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fbaf  mov     ecx, [rax+0Ch]
0x18000fbb2  mov     [rbx+rdi+0Ch], ecx
0x18000fbb6  mov     rcx, r15
0x18000fbb9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fbbf  mov     ecx, [rax+10h]
0x18000fbc2  mov     [rbx+rdi+10h], ecx
0x18000fbc6  mov     [rbx+rdi+14h], r14d
0x18000fbcb  test    ebp, ebp
0x18000fbcd  jz      short loc_18000FBE2
0x18000fbcf  mov     rcx, r15
0x18000fbd2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fbd8  mov     ecx, [rax+4]
0x18000fbdb  and     ecx, 20h
0x18000fbde  or      [rbx+rdi+4], ecx
0x18000fbe2  mov     rcx, r15
0x18000fbe5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fbeb  mov     rcx, r15
0x18000fbee  mov     rbx, rax
0x18000fbf1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fbf7  mov     r8d, [rbx+10h]; Size
0x18000fbfb  mov     ecx, r14d
0x18000fbfe  add     rcx, rdi; void *
0x18000fc01  mov     rdx, [rax+18h]; Src
0x18000fc05  call    memcpy_0
0x18000fc0a  mov     rcx, r15
0x18000fc0d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fc13  inc     r13d
0x18000fc16  mov     ecx, [rax+10h]
0x18000fc19  add     ecx, 7
0x18000fc1c  add     r14d, ecx
0x18000fc1f  and     r14d, 0FFFFFFF8h
0x18000fc23  cmp     r13d, [rsi+10h]
0x18000fc27  jb      loc_18000FB65
0x18000fc2d  mov     ebp, [rsp+58h+arg_18]
0x18000fc31  mov     rbx, [rsp+58h+arg_0]
0x18000fc36  mov     eax, ebp
0x18000fc38  add     rsp, 20h
0x18000fc3c  pop     r15
0x18000fc3e  pop     r14
0x18000fc40  pop     r13
0x18000fc42  pop     r12
0x18000fc44  pop     rdi
0x18000fc45  pop     rsi
0x18000fc46  pop     rbp
0x18000fc47  retn
```
