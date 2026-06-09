# CPropertyCache::updateproperty(ushort *,ulong,ulong,_iistype *,int)

- ea: `0x1800111b4`
- end: `0x1800112db`
- name: `?updateproperty@CPropertyCache@@QEAAJPEAGKKPEAU_iistype@@H@Z`
- size: `295`
- prototype: `__int64 __usercall@<rax>(CPropertyCache *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _iistype *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800110bc`

## callees

- `0x180010968`
- `0x180010bf8`
- `0x1800111b4`
- `0x1800183ac`
- `0x1800184ac`
- `0x180019f14`

## pseudocode

```c
__int64 __fastcall CPropertyCache::updateproperty(
        IIsSchema **this,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        struct _iistype *a5,
        int a6)
{
  int Schema; // r10d
  IIsSchema *v11; // rdi
  __int64 v12; // rbx
  char *v13; // rsi
  struct _iistype *v14; // rcx
  unsigned int v16; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v17; // [rsp+24h] [rbp-44h] BYREF
  struct _iistype *v18; // [rsp+28h] [rbp-40h] BYREF

  v16 = 0;
  v17 = 0;
  v18 = 0;
  Schema = CPropertyCache::LoadSchema((CPropertyCache *)this);
  if ( Schema >= 0 )
  {
    Schema = CPropertyCache::findproperty((CPropertyCache *)this, a2, &v16);
    if ( Schema >= 0 )
    {
      v11 = this[4];
      v12 = 544LL * v16;
      v13 = (char *)v11 + v12;
      if ( a6 || (unsigned int)(*((_DWORD *)v13 + 130) - 1) > 1 )
      {
        v14 = *(struct _iistype **)((char *)v11 + v12 + 536);
        if ( v14 )
        {
          IISTypeFreeIISObjects(v14, *(_DWORD *)((char *)v11 + v12 + 524));
          *(_QWORD *)((char *)v11 + v12 + 536) = 0;
        }
        *(_DWORD *)((char *)v11 + v12 + 528) = a3;
        *(_DWORD *)((char *)v11 + v12 + 524) = a4;
        IIsSchema::ConvertPropName_To_ID(this[9], a2, &v17);
        *(_DWORD *)((char *)v11 + v12 + 532) = v17;
        Schema = IISTypeCopyConstruct(a5, a4, &v18);
        if ( Schema >= 0 )
        {
          *(_QWORD *)((char *)v11 + v12 + 536) = v18;
          *((_DWORD *)v13 + 130) = 0;
        }
      }
      else
      {
        return 0;
      }
    }
  }
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x1800111b4  push    rbx
0x1800111b6  push    rbp
0x1800111b7  push    rsi
0x1800111b8  push    rdi
0x1800111b9  push    r12
0x1800111bb  push    r14
0x1800111bd  push    r15
0x1800111bf  sub     rsp, 30h
0x1800111c3  mov     r15d, r9d
0x1800111c6  mov     [rsp+68h+var_48], 0
0x1800111ce  mov     r12d, r8d
0x1800111d1  mov     [rsp+68h+var_44], 0
0x1800111d9  mov     r14, rdx
0x1800111dc  mov     [rsp+68h+var_40], 0
0x1800111e5  mov     rbp, rcx
0x1800111e8  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x1800111ed  mov     r10d, eax
0x1800111f0  test    eax, eax
0x1800111f2  js      loc_1800112C9
0x1800111f8  lea     r8, [rsp+68h+var_48]; unsigned int *
0x1800111fd  mov     rdx, r14; unsigned __int16 *
0x180011200  mov     rcx, rbp; this
0x180011203  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x180011208  mov     r10d, eax
0x18001120b  test    eax, eax
0x18001120d  js      loc_1800112C9
0x180011213  mov     eax, [rsp+68h+var_48]
0x180011217  mov     rdi, [rbp+20h]
0x18001121b  imul    rbx, rax, 220h
0x180011222  cmp     [rsp+68h+arg_28], 0
0x18001122a  lea     rsi, [rbx+rdi]
0x18001122e  jnz     short loc_180011245
0x180011230  mov     eax, [rsi+208h]
0x180011236  dec     eax
0x180011238  cmp     eax, 1
0x18001123b  ja      short loc_180011245
0x18001123d  xor     r10d, r10d
0x180011240  jmp     loc_1800112C9
0x180011245  mov     rcx, [rbx+rdi+218h]; struct _iistype *
0x18001124d  test    rcx, rcx
0x180011250  jz      short loc_18001126A
0x180011252  mov     edx, [rbx+rdi+20Ch]; unsigned int
0x180011259  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x18001125e  mov     qword ptr [rbx+rdi+218h], 0
0x18001126a  mov     [rbx+rdi+210h], r12d
0x180011272  lea     r8, [rsp+68h+var_44]; unsigned int *
0x180011277  mov     [rbx+rdi+20Ch], r15d
0x18001127f  mov     rdx, r14; unsigned __int16 *
0x180011282  mov     rcx, [rbp+48h]; this
0x180011286  call    ?ConvertPropName_To_ID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::ConvertPropName_To_ID(ushort const *,ulong *)
0x18001128b  mov     eax, [rsp+68h+var_44]
0x18001128f  lea     r8, [rsp+68h+var_40]; struct _iistype **
0x180011294  mov     rcx, [rsp+68h+arg_20]; struct _iistype *
0x18001129c  mov     edx, r15d; unsigned int
0x18001129f  mov     [rbx+rdi+214h], eax
0x1800112a6  call    ?IISTypeCopyConstruct@@YAJPEAU_iistype@@KPEAPEAU1@@Z; IISTypeCopyConstruct(_iistype *,ulong,_iistype * *)
0x1800112ab  mov     r10d, eax
0x1800112ae  test    eax, eax
0x1800112b0  js      short loc_1800112C9
0x1800112b2  mov     rax, [rsp+68h+var_40]
0x1800112b7  mov     [rbx+rdi+218h], rax
0x1800112bf  mov     dword ptr [rsi+208h], 0
0x1800112c9  mov     eax, r10d
0x1800112cc  add     rsp, 30h
0x1800112d0  pop     r15
0x1800112d2  pop     r14
0x1800112d4  pop     r12
0x1800112d6  pop     rdi
0x1800112d7  pop     rsi
0x1800112d8  pop     rbp
0x1800112d9  pop     rbx
0x1800112da  retn
```
