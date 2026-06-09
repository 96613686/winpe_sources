# CPropertyCache::putproperty(ushort *,ulong,ulong,ulong,_iistype *)

- ea: `0x180010ecc`
- end: `0x180011013`
- name: `?putproperty@CPropertyCache@@QEAAJPEAGKKKPEAU_iistype@@@Z`
- size: `327`
- prototype: `__int64 __usercall@<rax>(CPropertyCache *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, struct _iistype *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1800032a0`
- `0x1800035a0`
- `0x180006f60`
- `0x180007300`
- `0x1800103bc`

## callees

- `0x180010968`
- `0x180010bf8`
- `0x180010ecc`
- `0x1800183ac`
- `0x1800184ac`
- `0x180019f14`

## pseudocode

```c
__int64 __fastcall CPropertyCache::putproperty(
        IIsSchema **this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        struct _iistype *a6)
{
  int Schema; // esi
  IIsSchema *v11; // rdi
  __int64 v12; // rbx
  struct _iistype *v13; // rcx
  char *v14; // r14
  int v15; // ebp
  unsigned int v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v19; // [rsp+24h] [rbp-54h] BYREF
  struct _iistype *v20; // [rsp+28h] [rbp-50h] BYREF

  v19 = 0;
  v18 = 0;
  v20 = 0;
  Schema = CPropertyCache::LoadSchema((CPropertyCache *)this);
  if ( Schema >= 0 )
  {
    Schema = CPropertyCache::findproperty((CPropertyCache *)this, a2, &v19);
    if ( Schema >= 0 )
    {
      v11 = this[4];
      v12 = 544LL * v19;
      v13 = *(struct _iistype **)((char *)v11 + v12 + 536);
      v14 = (char *)v11 + v12;
      if ( v13 )
      {
        IISTypeFreeIISObjects(v13, *((_DWORD *)v14 + 131));
        *(_QWORD *)((char *)v11 + v12 + 536) = 0;
      }
      IIsSchema::ConvertPropName_To_ID(this[9], a2, &v18);
      v15 = a3 - 1;
      if ( v15 )
      {
        if ( v15 == 1 )
        {
          *(_DWORD *)((char *)v11 + v12 + 532) = v18;
          *(_DWORD *)((char *)v11 + v12 + 528) = a4;
          *((_DWORD *)v14 + 131) = 0;
          *(_QWORD *)((char *)v11 + v12 + 536) = 0;
          *(_DWORD *)((char *)v11 + v12 + 520) = 2;
        }
      }
      else
      {
        v16 = v18;
        *((_DWORD *)v14 + 131) = a5;
        *(_DWORD *)((char *)v11 + v12 + 532) = v16;
        *(_DWORD *)((char *)v11 + v12 + 528) = a4;
        Schema = IISTypeCopyConstruct(a6, a5, &v20);
        if ( Schema >= 0 )
        {
          *(_QWORD *)((char *)v11 + v12 + 536) = v20;
          *(_DWORD *)((char *)v11 + v12 + 520) = 1;
        }
      }
    }
  }
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x180010ecc  push    rbx
0x180010ece  push    rbp
0x180010ecf  push    rsi
0x180010ed0  push    rdi
0x180010ed1  push    r12
0x180010ed3  push    r13
0x180010ed5  push    r14
0x180010ed7  push    r15
0x180010ed9  sub     rsp, 38h
0x180010edd  xor     ebx, ebx
0x180010edf  mov     r12d, r9d
0x180010ee2  mov     [rsp+78h+var_54], ebx
0x180010ee6  mov     ebp, r8d
0x180010ee9  mov     [rsp+78h+var_58], ebx
0x180010eed  mov     r13, rdx
0x180010ef0  mov     [rsp+78h+var_50], rbx
0x180010ef5  mov     r15, rcx
0x180010ef8  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x180010efd  mov     esi, eax
0x180010eff  test    eax, eax
0x180010f01  js      loc_180011000
0x180010f07  lea     r8, [rsp+78h+var_54]; unsigned int *
0x180010f0c  mov     rdx, r13; unsigned __int16 *
0x180010f0f  mov     rcx, r15; this
0x180010f12  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180010f17  mov     esi, eax
0x180010f19  test    eax, eax
0x180010f1b  js      loc_180011000
0x180010f21  mov     rdi, [r15+20h]
0x180010f25  mov     eax, [rsp+78h+var_54]
0x180010f29  imul    rbx, rax, 220h
0x180010f30  mov     rcx, [rbx+rdi+218h]; struct _iistype *
0x180010f38  lea     r14, [rbx+rdi]
0x180010f3c  test    rcx, rcx
0x180010f3f  jz      short loc_180010F59
0x180010f41  mov     edx, [r14+20Ch]; unsigned int
0x180010f48  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x180010f4d  mov     qword ptr [rbx+rdi+218h], 0
0x180010f59  mov     rcx, [r15+48h]; this
0x180010f5d  lea     r8, [rsp+78h+var_58]; unsigned int *
0x180010f62  mov     rdx, r13; unsigned __int16 *
0x180010f65  call    ?ConvertPropName_To_ID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::ConvertPropName_To_ID(ushort const *,ulong *)
0x180010f6a  sub     ebp, 1
0x180010f6d  jz      short loc_180010FAF
0x180010f6f  cmp     ebp, 1
0x180010f72  jnz     loc_180011000
0x180010f78  mov     eax, [rsp+78h+var_58]
0x180010f7c  mov     [rbx+rdi+214h], eax
0x180010f83  mov     [rbx+rdi+210h], r12d
0x180010f8b  mov     dword ptr [r14+20Ch], 0
0x180010f96  mov     qword ptr [rbx+rdi+218h], 0
0x180010fa2  mov     dword ptr [rbx+rdi+208h], 2
0x180010fad  jmp     short loc_180011000
0x180010faf  mov     edx, [rsp+78h+arg_20]; unsigned int
0x180010fb6  lea     r8, [rsp+78h+var_50]; struct _iistype **
0x180010fbb  mov     eax, [rsp+78h+var_58]
0x180010fbf  mov     rcx, [rsp+78h+arg_28]; struct _iistype *
0x180010fc7  mov     [r14+20Ch], edx
0x180010fce  mov     [rbx+rdi+214h], eax
0x180010fd5  mov     [rbx+rdi+210h], r12d
0x180010fdd  call    ?IISTypeCopyConstruct@@YAJPEAU_iistype@@KPEAPEAU1@@Z; IISTypeCopyConstruct(_iistype *,ulong,_iistype * *)
0x180010fe2  mov     esi, eax
0x180010fe4  test    eax, eax
0x180010fe6  js      short loc_180011000
0x180010fe8  mov     rax, [rsp+78h+var_50]
0x180010fed  mov     [rbx+rdi+218h], rax
0x180010ff5  mov     dword ptr [rbx+rdi+208h], 1
0x180011000  mov     eax, esi
0x180011002  add     rsp, 38h
0x180011006  pop     r15
0x180011008  pop     r14
0x18001100a  pop     r13
0x18001100c  pop     r12
0x18001100e  pop     rdi
0x18001100f  pop     rsi
0x180011010  pop     rbp
0x180011011  pop     rbx
0x180011012  retn
```
