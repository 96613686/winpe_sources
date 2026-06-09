# CAVICmpStream::CS::Write(long,long,void *,long,ulong,long *,long *)

- ea: `0x18000e970`
- end: `0x18000ea5f`
- name: `?Write@CS@CAVICmpStream@@UEAAJJJPEAXJKPEAJ1@Z`
- size: `239`
- prototype: `int(CAVICmpStream::CS *__hidden this, int, int, void *, int, unsigned int, int *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000d86c`
- `0x18000e970`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::CS::Write(
        CAVICmpStream::CS *this,
        int a2,
        int a3,
        void *a4,
        int a5,
        unsigned int a6,
        int *a7,
        int *a8)
{
  __int64 v8; // rbx
  bool v11; // zf
  unsigned int v13; // r8d
  __int64 result; // rax

  v8 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)(v8 + 264) || a2 < *(_DWORD *)(v8 + 76) + *(_DWORD *)(v8 + 80) || a3 > 1 )
    return 2147762277LL;
  v11 = *(_DWORD *)(v8 + 52) == 541215044;
  *(_DWORD *)(v8 + 272) = a2;
  if ( v11 )
  {
    v13 = a6 | 0x10;
  }
  else
  {
    result = CAVICmpStream::ICCrunch((CAVICmpStream *)v8, *(struct tagBITMAPINFOHEADER **)(v8 + 336), a4);
    if ( (_DWORD)result )
      return result;
    v13 = 0;
    a4 = *(void **)(v8 + 296);
    a5 = *(_DWORD *)(*(_QWORD *)(v8 + 288) + 20LL);
    if ( *(_DWORD *)(v8 + 380) == a2 )
      v13 = 16;
  }
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, int, unsigned int, int *, int *))(**(_QWORD **)(v8 + 256) + 72LL))(
           *(_QWORD *)(v8 + 256),
           (unsigned int)a2,
           (unsigned int)a3,
           a4,
           a5,
           v13,
           a7,
           a8);
}

```

## disassembly

```asm
0x18000e970  mov     [rsp+arg_0], rbx
0x18000e975  mov     [rsp+arg_8], rsi
0x18000e97a  push    rdi
0x18000e97b  sub     rsp, 50h
0x18000e97f  mov     rbx, [rcx+8]
0x18000e983  mov     esi, r8d
0x18000e986  mov     edi, edx
0x18000e988  cmp     qword ptr [rbx+108h], 0
0x18000e990  jnz     loc_18000EA4A
0x18000e996  mov     eax, [rbx+50h]
0x18000e999  add     eax, [rbx+4Ch]
0x18000e99c  cmp     edx, eax
0x18000e99e  jl      loc_18000EA4A
0x18000e9a4  cmp     r8d, 1
0x18000e9a8  jg      loc_18000EA4A
0x18000e9ae  cmp     dword ptr [rbx+34h], 20424944h
0x18000e9b5  mov     [rbx+110h], edx
0x18000e9bb  jnz     short loc_18000E9D3
0x18000e9bd  mov     r8d, [rsp+58h+arg_28]
0x18000e9c5  mov     r10d, [rsp+58h+arg_20]
0x18000e9cd  or      r8d, 10h
0x18000e9d1  jmp     short loc_18000EA0C
0x18000e9d3  mov     rdx, [rbx+150h]; struct tagBITMAPINFOHEADER *
0x18000e9da  mov     r8, r9; void *
0x18000e9dd  mov     rcx, rbx; this
0x18000e9e0  call    ?ICCrunch@CAVICmpStream@@QEAAJPEAUtagBITMAPINFOHEADER@@PEAX@Z; CAVICmpStream::ICCrunch(tagBITMAPINFOHEADER *,void *)
0x18000e9e5  test    eax, eax
0x18000e9e7  jnz     short loc_18000EA4F
0x18000e9e9  mov     rax, [rbx+120h]
0x18000e9f0  xor     r8d, r8d
0x18000e9f3  cmp     [rbx+17Ch], edi
0x18000e9f9  mov     r9, [rbx+128h]
0x18000ea00  mov     r10d, [rax+14h]
0x18000ea04  lea     eax, [r8+10h]
0x18000ea08  cmovz   r8d, eax
0x18000ea0c  mov     rcx, [rbx+100h]
0x18000ea13  mov     rdx, [rsp+58h+arg_38]
0x18000ea1b  mov     [rsp+58h+var_20], rdx
0x18000ea20  mov     rdx, [rsp+58h+arg_30]
0x18000ea28  mov     rax, [rcx]
0x18000ea2b  mov     [rsp+58h+var_28], rdx
0x18000ea30  mov     edx, edi
0x18000ea32  mov     [rsp+58h+var_30], r8d
0x18000ea37  mov     r8d, esi
0x18000ea3a  mov     [rsp+58h+var_38], r10d
0x18000ea3f  mov     rax, [rax+48h]
0x18000ea43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea48  jmp     short loc_18000EA4F
0x18000ea4a  mov     eax, 80044065h
0x18000ea4f  mov     rbx, [rsp+58h+arg_0]
0x18000ea54  mov     rsi, [rsp+58h+arg_8]
0x18000ea59  add     rsp, 50h
0x18000ea5d  pop     rdi
0x18000ea5e  retn
```
