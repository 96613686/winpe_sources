# CScanner::CVertexPool::CopyVertex(CScanner::CVertex const *,CScanner::CVertex * &)

- ea: `0x10043f5e0`
- end: `0x10043f679`
- name: `?CopyVertex@CVertexPool@CScanner@@QEAAJPEBVCVertex@2@AEAPEAV32@@Z`
- size: `153`
- prototype: `__int64 __fastcall(CScanner::CVertexPool *__hidden this, const struct CScanner::CVertex *, struct CScanner::CVertex **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100440c50`

## callees

- `0x10043f5e0`
- `0x1004436b0`

## pseudocode

```c
__int64 __fastcall CScanner::CVertexPool::CopyVertex(
        CScanner::CVertexPool *this,
        const struct CScanner::CVertex *a2,
        struct CScanner::CVertex **a3)
{
  __int64 result; // rax
  struct CScanner::CVertex *v6; // rcx

  if ( *((int *)this + 8) >= 65534 )
  {
    *a3 = 0;
    return 2147500037LL;
  }
  else
  {
    result = SQL_Memblock<CScanner::CVertex>::Allocate((char *)this + 8, a3);
    if ( (int)result >= 0 )
    {
      _mm_lfence();
      v6 = *a3;
      *(_OWORD *)v6 = *(_OWORD *)a2;
      *((_OWORD *)v6 + 1) = *((_OWORD *)a2 + 1);
      *((_OWORD *)v6 + 2) = *((_OWORD *)a2 + 2);
      *((_OWORD *)v6 + 3) = *((_OWORD *)a2 + 3);
      *((_OWORD *)v6 + 4) = *((_OWORD *)a2 + 4);
      *((_OWORD *)v6 + 5) = *((_OWORD *)a2 + 5);
      *((_OWORD *)v6 + 6) = *((_OWORD *)a2 + 6);
      *((_QWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 3) = 0;
      *((_QWORD *)v6 + 9) = 0;
      return (unsigned int)result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10043f5e0  mov     [rsp+arg_0], rbx
0x10043f5e5  push    rdi
0x10043f5e6  sub     rsp, 20h
0x10043f5ea  cmp     dword ptr [rcx+20h], 0FFFEh
0x10043f5f1  mov     rbx, r8
0x10043f5f4  mov     rdi, rdx
0x10043f5f7  jge     short loc_10043F664
0x10043f5f9  add     rcx, 8
0x10043f5fd  mov     rdx, rbx
0x10043f600  call    ?Allocate@?$SQL_Memblock@VCVertex@CScanner@@@@QEAAJPEAPEAVCVertex@CScanner@@@Z; SQL_Memblock<CScanner::CVertex>::Allocate(CScanner::CVertex * *)
0x10043f605  mov     r9d, eax
0x10043f608  test    eax, eax
0x10043f60a  js      short loc_10043F66E
0x10043f60c  lfence
0x10043f60f  movups  xmm0, xmmword ptr [rdi]
0x10043f612  mov     rcx, [rbx]
0x10043f615  xor     eax, eax
0x10043f617  movups  xmmword ptr [rcx], xmm0
0x10043f61a  movups  xmm1, xmmword ptr [rdi+10h]
0x10043f61e  movups  xmmword ptr [rcx+10h], xmm1
0x10043f622  movups  xmm0, xmmword ptr [rdi+20h]
0x10043f626  movups  xmmword ptr [rcx+20h], xmm0
0x10043f62a  movups  xmm1, xmmword ptr [rdi+30h]
0x10043f62e  movups  xmmword ptr [rcx+30h], xmm1
0x10043f632  movups  xmm0, xmmword ptr [rdi+40h]
0x10043f636  movups  xmmword ptr [rcx+40h], xmm0
0x10043f63a  movups  xmm1, xmmword ptr [rdi+50h]
0x10043f63e  movups  xmmword ptr [rcx+50h], xmm1
0x10043f642  movups  xmm0, xmmword ptr [rdi+60h]
0x10043f646  movups  xmmword ptr [rcx+60h], xmm0
0x10043f64a  mov     [rcx+20h], rax
0x10043f64e  mov     [rcx+18h], rax
0x10043f652  mov     [rcx+48h], rax
0x10043f656  mov     eax, r9d
0x10043f659  mov     rbx, [rsp+28h+arg_0]
0x10043f65e  add     rsp, 20h
0x10043f662  pop     rdi
0x10043f663  retn
0x10043f664  xor     eax, eax
0x10043f666  mov     [r8], rax
0x10043f669  mov     eax, 80004005h
0x10043f66e  mov     rbx, [rsp+28h+arg_0]
0x10043f673  add     rsp, 20h
0x10043f677  pop     rdi
0x10043f678  retn
```
