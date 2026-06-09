# CPropertyCache::getproperty(ushort *,ulong *,ulong *,_iistype * *)

- ea: `0x180010cd8`
- end: `0x180010e6d`
- name: `?getproperty@CPropertyCache@@QEAAJPEAGPEAK1PEAPEAU_iistype@@@Z`
- size: `405`
- prototype: `__int64 __usercall@<rax>(CPropertyCache *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int *@<r8>, unsigned int *@<r9>, struct _iistype **)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180002ed0`
- `0x180003050`
- `0x180005a90`
- `0x180005e40`
- `0x180010104`
- `0x1800103bc`

## callees

- `0x180010968`
- `0x180010bf8`
- `0x180010cd8`
- `0x1800110bc`
- `0x1800183ac`
- `0x18001a184`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CPropertyCache::getproperty(
        IIsSchema **this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4,
        struct _iistype **a5)
{
  struct _iistype **v5; // r15
  int Schema; // r10d
  IIsSchema *v11; // rcx
  IIsSchema *v12; // r9
  __int64 v13; // rcx
  unsigned __int8 *v15; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v17; // [rsp+88h] [rbp+48h] BYREF

  v5 = a5;
  *a4 = 0;
  v16 = 0;
  *a3 = 0;
  *v5 = 0;
  Schema = CPropertyCache::LoadSchema((CPropertyCache *)this);
  if ( Schema >= 0 )
  {
    Schema = CPropertyCache::findproperty((CPropertyCache *)this, a2, &v16);
    if ( Schema == -2147463155 )
    {
      if ( *((_DWORD *)this + 10) )
        goto LABEL_7;
      Schema = (**(__int64 (__fastcall ***)(IIsSchema *, _QWORD))this[2])(this[2], 0);
      if ( (int)(Schema + 0x80000000) >= 0 && Schema != -2147463159 )
        return (unsigned int)Schema;
      Schema = CPropertyCache::findproperty((CPropertyCache *)this, a2, &v16);
      if ( Schema == -2147463155 )
      {
LABEL_7:
        v11 = this[9];
        v15 = 0;
        LODWORD(a5) = 0;
        v17 = 0;
        Schema = IIsSchema::GetDefaultProperty(v11, a2, &v17, (unsigned int *)&a5, &v15);
        if ( Schema < 0 )
          return (unsigned int)Schema;
        Schema = CPropertyCache::unmarshallproperty((CPropertyCache *)this, a2, v15, v17, (unsigned int)a5, 0);
        if ( Schema < 0 )
          return (unsigned int)Schema;
        Schema = CPropertyCache::findproperty((CPropertyCache *)this, a2, &v16);
      }
    }
    if ( Schema >= 0 )
    {
      v12 = this[4];
      v13 = 544LL * v16;
      if ( *(_QWORD *)((char *)v12 + v13 + 536) )
      {
        *a3 = *(_DWORD *)((char *)v12 + v13 + 528);
        *a4 = *(_DWORD *)((char *)v12 + v13 + 524);
        return (unsigned int)IISTypeCopyConstruct(
                               *(struct _iistype **)((char *)v12 + v13 + 536),
                               *(_DWORD *)((char *)v12 + v13 + 524),
                               v5);
      }
      else
      {
        *a4 = 0;
        Schema = -2147463163;
        *a3 = 0;
        *v5 = 0;
      }
    }
  }
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x180010cd8  mov     [rsp-28h+arg_0], rbx
0x180010cdd  mov     [rsp-28h+arg_8], rsi
0x180010ce2  push    rbp
0x180010ce3  push    rdi
0x180010ce4  push    r12
0x180010ce6  push    r14
0x180010ce8  push    r15
0x180010cea  mov     rbp, rsp
0x180010ced  sub     rsp, 40h
0x180010cf1  mov     r15, [rbp+arg_20]
0x180010cf5  xor     r12d, r12d
0x180010cf8  mov     [r9], r12d
0x180010cfb  mov     rsi, r9
0x180010cfe  mov     r14, r8
0x180010d01  mov     [rbp+arg_10], r12d
0x180010d05  mov     rdi, rdx
0x180010d08  mov     [r8], r12d
0x180010d0b  mov     [r15], r12
0x180010d0e  mov     rbx, rcx
0x180010d11  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x180010d16  mov     r10d, eax
0x180010d19  test    eax, eax
0x180010d1b  js      loc_180010E53
0x180010d21  lea     r8, [rbp+arg_10]; unsigned int *
0x180010d25  mov     rdx, rdi; unsigned __int16 *
0x180010d28  mov     rcx, rbx; this
0x180010d2b  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180010d30  mov     r10d, eax
0x180010d33  cmp     eax, 8000500Dh
0x180010d38  jnz     loc_180010DF5
0x180010d3e  cmp     [rbx+28h], r12d
0x180010d42  jnz     short loc_180010D89
0x180010d44  mov     rcx, [rbx+10h]
0x180010d48  xor     edx, edx
0x180010d4a  mov     rax, [rcx]
0x180010d4d  mov     rax, [rax]
0x180010d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d55  mov     ecx, 80000000h
0x180010d5a  mov     r10d, eax
0x180010d5d  add     eax, ecx
0x180010d5f  test    ecx, eax
0x180010d61  jnz     short loc_180010D70
0x180010d63  cmp     r10d, 80005009h
0x180010d6a  jnz     loc_180010E53
0x180010d70  lea     r8, [rbp+arg_10]; unsigned int *
0x180010d74  mov     rdx, rdi; unsigned __int16 *
0x180010d77  mov     rcx, rbx; this
0x180010d7a  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180010d7f  mov     r10d, eax
0x180010d82  cmp     eax, 8000500Dh
0x180010d87  jnz     short loc_180010DF5
0x180010d89  mov     rcx, [rbx+48h]; this
0x180010d8d  lea     rax, [rbp+var_10]
0x180010d91  lea     r9, [rbp+arg_20]; unsigned int *
0x180010d95  mov     [rsp+40h+var_20], rax; unsigned __int8 **
0x180010d9a  lea     r8, [rbp+arg_18]; unsigned int *
0x180010d9e  mov     [rbp+var_10], r12
0x180010da2  mov     rdx, rdi; unsigned __int16 *
0x180010da5  mov     dword ptr [rbp+arg_20], r12d
0x180010da9  mov     [rbp+arg_18], r12d
0x180010dad  call    ?GetDefaultProperty@IIsSchema@@QEAAJPEBGPEAK1PEAPEAE@Z; IIsSchema::GetDefaultProperty(ushort const *,ulong *,ulong *,uchar * *)
0x180010db2  mov     r10d, eax
0x180010db5  test    eax, eax
0x180010db7  js      loc_180010E53
0x180010dbd  mov     eax, dword ptr [rbp+arg_20]
0x180010dc0  mov     rdx, rdi; unsigned __int16 *
0x180010dc3  mov     r9d, [rbp+arg_18]; unsigned int
0x180010dc7  mov     rcx, rbx; this
0x180010dca  mov     r8, [rbp+var_10]; unsigned __int8 *
0x180010dce  mov     [rsp+40h+var_18], r12d; int
0x180010dd3  mov     dword ptr [rsp+40h+var_20], eax; unsigned int
0x180010dd7  call    ?unmarshallproperty@CPropertyCache@@QEAAJPEAGPEAEKKH@Z; CPropertyCache::unmarshallproperty(ushort *,uchar *,ulong,ulong,int)
0x180010ddc  mov     r10d, eax
0x180010ddf  test    eax, eax
0x180010de1  js      short loc_180010E53
0x180010de3  lea     r8, [rbp+arg_10]; unsigned int *
0x180010de7  mov     rdx, rdi; unsigned __int16 *
0x180010dea  mov     rcx, rbx; this
0x180010ded  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180010df2  mov     r10d, eax
0x180010df5  test    r10d, r10d
0x180010df8  js      short loc_180010E53
0x180010dfa  mov     eax, [rbp+arg_10]
0x180010dfd  mov     r9, [rbx+20h]
0x180010e01  imul    rcx, rax, 220h
0x180010e08  cmp     [rcx+r9+218h], r12
0x180010e10  jz      short loc_180010E44
0x180010e12  mov     eax, [rcx+r9+210h]
0x180010e1a  mov     r8, r15; struct _iistype **
0x180010e1d  mov     [r14], eax
0x180010e20  mov     eax, [rcx+r9+20Ch]
0x180010e28  mov     [rsi], eax
0x180010e2a  mov     edx, [rcx+r9+20Ch]; unsigned int
0x180010e32  mov     rcx, [rcx+r9+218h]; struct _iistype *
0x180010e3a  call    ?IISTypeCopyConstruct@@YAJPEAU_iistype@@KPEAPEAU1@@Z; IISTypeCopyConstruct(_iistype *,ulong,_iistype * *)
0x180010e3f  mov     r10d, eax
0x180010e42  jmp     short loc_180010E53
0x180010e44  mov     [rsi], r12d
0x180010e47  mov     r10d, 80005005h
0x180010e4d  mov     [r14], r12d
0x180010e50  mov     [r15], r12
0x180010e53  mov     rbx, [rsp+40h+arg_0]
0x180010e58  mov     eax, r10d
0x180010e5b  mov     rsi, [rsp+40h+arg_8]
0x180010e60  add     rsp, 40h
0x180010e64  pop     r15
0x180010e66  pop     r14
0x180010e68  pop     r12
0x180010e6a  pop     rdi
0x180010e6b  pop     rbp
0x180010e6c  retn
```
