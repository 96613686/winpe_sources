# ObjectTypeList::CreateObjectTypeList(tagVARIANT,ObjectTypeList * *)

- ea: `0x180014d2c`
- end: `0x180014df9`
- name: `?CreateObjectTypeList@ObjectTypeList@@SAJUtagVARIANT@@PEAPEAV1@@Z`
- size: `205`
- prototype: `__int64 __fastcall(struct tagVARIANT *__struct_ptr, struct ObjectTypeList **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002710`
- `0x18000ce28`

## callees

- `0x1800010b0`
- `0x1800026e8`
- `0x180014a74`
- `0x180014b3c`
- `0x180014d2c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180014db4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180014db4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180014dcc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180014dcc`

## pseudocode

```c
__int64 __fastcall ObjectTypeList::CreateObjectTypeList(struct tagVARIANT *a1, struct ObjectTypeList **a2)
{
  int UBound; // edi
  unsigned int *v5; // rax
  unsigned int *v6; // rbx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v8; // rdx
  struct _filters *v9; // rcx
  unsigned int v10; // edx
  __int64 result; // rax
  struct tagVARIANT v12; // [rsp+20h] [rbp-48h] BYREF

  UBound = -2147024882;
  v5 = (unsigned int *)operator new(0x18u);
  v6 = v5;
  if ( v5 )
  {
    pRecInfo = a1->pRecInfo;
    *(_OWORD *)&v12.vt = *(_OWORD *)&a1->vt;
    v12.pRecInfo = pRecInfo;
    *(_QWORD *)v5 = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    if ( (int)BuildObjectArray(&v12, (struct tagSAFEARRAY **)v5, v5 + 5) >= 0
      || (UBound = BuildDefaultObjectArray(v9, v8, (struct tagSAFEARRAY **)v6, v6 + 5), UBound >= 0) )
    {
      UBound = SafeArrayGetUBound(*(SAFEARRAY **)v6, 1u, (LONG *)v6 + 4);
      if ( UBound >= 0 )
      {
        UBound = SafeArrayGetLBound(*(SAFEARRAY **)v6, 1u, (LONG *)v6 + 3);
        if ( UBound >= 0 )
        {
          v6[2] = v6[3];
          result = 0;
          *a2 = (struct ObjectTypeList *)v6;
          return result;
        }
      }
    }
    ObjectTypeList::`scalar deleting destructor'((ObjectTypeList *)v6, v10);
  }
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180014d2c  push    rbx
0x180014d2e  push    rsi
0x180014d2f  push    rdi
0x180014d30  push    r14
0x180014d32  sub     rsp, 48h
0x180014d36  mov     rsi, rcx
0x180014d39  mov     r14, rdx
0x180014d3c  mov     ecx, 18h; Size
0x180014d41  mov     edi, 8007000Eh
0x180014d46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d4b  mov     rbx, rax
0x180014d4e  test    rax, rax
0x180014d51  jz      loc_180014DED
0x180014d57  movaps  xmm0, xmmword ptr [rsi]
0x180014d5a  lea     r8, [rax+14h]; unsigned int *
0x180014d5e  movsd   xmm1, qword ptr [rsi+10h]
0x180014d63  lea     rcx, [rsp+68h+var_48]; struct tagVARIANT
0x180014d68  mov     rdx, rax; struct tagSAFEARRAY **
0x180014d6b  movaps  xmmword ptr [rsp+68h+var_48], xmm0
0x180014d70  movsd   qword ptr [rsp+68h+var_48+10h], xmm1
0x180014d76  mov     qword ptr [rax], 0
0x180014d7d  mov     qword ptr [rax+8], 0
0x180014d85  mov     qword ptr [rax+10h], 0
0x180014d8d  call    ?BuildObjectArray@@YAJUtagVARIANT@@PEAPEAUtagSAFEARRAY@@PEAK@Z; BuildObjectArray(tagVARIANT,tagSAFEARRAY * *,ulong *)
0x180014d92  test    eax, eax
0x180014d94  jns     short loc_180014DA8
0x180014d96  lea     r9, [rbx+14h]; unsigned int *
0x180014d9a  mov     r8, rbx; struct tagSAFEARRAY **
0x180014d9d  call    ?BuildDefaultObjectArray@@YAJPEAU_filters@@KPEAPEAUtagSAFEARRAY@@PEAK@Z; BuildDefaultObjectArray(_filters *,ulong,tagSAFEARRAY * *,ulong *)
0x180014da2  mov     edi, eax
0x180014da4  test    eax, eax
0x180014da6  js      short loc_180014DE5
0x180014da8  mov     rcx, [rbx]; psa
0x180014dab  lea     r8, [rbx+10h]; plUbound
0x180014daf  mov     edx, 1; nDim
0x180014db4  call    cs:__imp_SafeArrayGetUBound
0x180014dba  mov     edi, eax
0x180014dbc  test    eax, eax
0x180014dbe  js      short loc_180014DE5
0x180014dc0  mov     rcx, [rbx]; psa
0x180014dc3  lea     r8, [rbx+0Ch]; plLbound
0x180014dc7  mov     edx, 1; nDim
0x180014dcc  call    cs:__imp_SafeArrayGetLBound
0x180014dd2  mov     edi, eax
0x180014dd4  test    eax, eax
0x180014dd6  js      short loc_180014DE5
0x180014dd8  mov     eax, [rbx+0Ch]
0x180014ddb  mov     [rbx+8], eax
0x180014dde  xor     eax, eax
0x180014de0  mov     [r14], rbx
0x180014de3  jmp     short loc_180014DEF
0x180014de5  mov     rcx, rbx; this
0x180014de8  call    ??_GObjectTypeList@@QEAAPEAXI@Z; ObjectTypeList::`scalar deleting destructor'(uint)
0x180014ded  mov     eax, edi
0x180014def  add     rsp, 48h
0x180014df3  pop     r14
0x180014df5  pop     rdi
0x180014df6  pop     rsi
0x180014df7  pop     rbx
0x180014df8  retn
```
