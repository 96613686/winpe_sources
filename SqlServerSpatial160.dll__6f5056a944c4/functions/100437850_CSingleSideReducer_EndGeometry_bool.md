# CSingleSideReducer::EndGeometry(bool)

- ea: `0x100437850`
- end: `0x1004378c4`
- name: `?EndGeometry@CSingleSideReducer@@UEAAJ_N@Z`
- size: `116`
- prototype: `__int64 __fastcall(CSingleSideReducer *__hidden this, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x100437850`
- `0x100438550`
- `0x100438d90`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::EndGeometry(CSingleSideReducer *this, unsigned __int8 a2)
{
  __int64 result; // rax
  double v5; // [rsp+30h] [rbp+8h] BYREF

  result = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 72LL))((char *)this + 48);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    *((double *)this + 14) = COERCE_DOUBLE(*((_QWORD *)this + 1) & _xmm) * *((double *)this + 7);
    result = CSingleSideReducer::Reduce(this, &v5);
    _mm_lfence();
    if ( (int)result >= 0 )
    {
      result = CSingleSideReducer::ProcessReducedShapes(this);
      _mm_lfence();
      if ( (int)result >= 0 )
        return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 72LL))(*((_QWORD *)this + 5), a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x100437850  mov     [rsp+arg_8], rbx
0x100437855  push    rdi
0x100437856  sub     rsp, 20h
0x10043785a  mov     rax, [rcx+30h]
0x10043785e  mov     rbx, rcx
0x100437861  add     rcx, 30h ; '0'
0x100437865  movzx   edi, dl
0x100437868  call    qword ptr [rax+48h]
0x10043786b  lfence
0x10043786e  test    eax, eax
0x100437870  js      short loc_1004378B9
0x100437872  movsd   xmm0, qword ptr [rbx+8]
0x100437877  lea     rdx, [rsp+28h+arg_0]; double *
0x10043787c  andps   xmm0, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100437883  mov     rcx, rbx; this
0x100437886  mulsd   xmm0, qword ptr [rbx+38h]
0x10043788b  movsd   qword ptr [rbx+70h], xmm0
0x100437890  call    ?Reduce@CSingleSideReducer@@AEAAJAEAN@Z; CSingleSideReducer::Reduce(double &)
0x100437895  lfence
0x100437898  test    eax, eax
0x10043789a  js      short loc_1004378B9
0x10043789c  mov     rcx, rbx; this
0x10043789f  call    ?ProcessReducedShapes@CSingleSideReducer@@AEAAJXZ; CSingleSideReducer::ProcessReducedShapes(void)
0x1004378a4  lfence
0x1004378a7  test    eax, eax
0x1004378a9  js      short loc_1004378B9
0x1004378ab  mov     rcx, [rbx+28h]
0x1004378af  movzx   edx, dil
0x1004378b3  mov     rax, [rcx]
0x1004378b6  call    qword ptr [rax+48h]
0x1004378b9  mov     rbx, [rsp+28h+arg_8]
0x1004378be  add     rsp, 20h
0x1004378c2  pop     rdi
0x1004378c3  retn
```
