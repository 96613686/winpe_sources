# CIISSchemaEnum::Create(CIISSchemaEnum * *,IIsSchema *,CCredentials &,ushort *,ushort *)

- ea: `0x18000ce28`
- end: `0x18000cf75`
- name: `?Create@CIISSchemaEnum@@SAJPEAPEAV1@PEAVIIsSchema@@AEAVCCredentials@@PEAG3@Z`
- size: `333`
- prototype: `static int(struct CIISSchemaEnum **, struct IIsSchema *, struct CCredentials *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008fb0`

## callees

- `0x1800010b0`
- `0x18000ce28`
- `0x18000d380`
- `0x180014d2c`
- `0x1800195b8`
- `0x18001984c`
- `0x18001bb28`
- `0x18001beb8`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ce56`
- `OLEAUT32!__imp_VariantInit` at `0x18000ce56`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf62`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf62`

## pseudocode

```c
__int64 __fastcall CIISSchemaEnum::Create(
        struct ObjectTypeList ***a1,
        struct IIsSchema *a2,
        struct CCredentials *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  CIISEnumVariant *v9; // rax
  struct ObjectTypeList **v10; // rbx
  int v11; // edi
  VARIANTARG pvarg; // [rsp+20h] [rbp-68h] BYREF
  struct tagVARIANT v14; // [rsp+40h] [rbp-48h] BYREF

  *a1 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v9 = (CIISEnumVariant *)operator new(0x58u);
  v10 = (struct ObjectTypeList **)v9;
  if ( v9 )
  {
    CIISEnumVariant::CIISEnumVariant(v9);
    v10[2] = 0;
    *v10 = (struct ObjectTypeList *)&CIISSchemaEnum::`vftable';
    v10[3] = 0;
    v10[4] = 0;
    CCredentials::Initialize((CCredentials *)(v10 + 5), 0, 0, 0);
    *((_DWORD *)v10 + 16) = 0;
    v10[10] = a2;
    CCredentials::operator=((CCredentials *)(v10 + 5), a3);
    *((_DWORD *)v10 + 16) = 0;
    StrMap::Sort(a2);
    *((_DWORD *)v10 + 17) = 0;
    StrMap::Sort((struct IIsSchema *)((char *)a2 + 32));
    *((_DWORD *)v10 + 18) = 0;
    v11 = ADsAllocString(a4, v10 + 4);
    if ( v11 < 0
      || (v11 = ADsAllocString(a5, v10 + 3), v11 < 0)
      || (v14 = pvarg, v11 = ObjectTypeList::CreateObjectTypeList(&v14, v10 + 2), v11 < 0) )
    {
      (*((void (__fastcall **)(struct ObjectTypeList **, __int64))*v10 + 7))(v10, 1);
    }
    else
    {
      *a1 = v10;
    }
  }
  else
  {
    v11 = -2147024882;
  }
  VariantClear(&pvarg);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000ce28  push    rbx
0x18000ce2a  push    rbp
0x18000ce2b  push    rsi
0x18000ce2c  push    rdi
0x18000ce2d  push    r14
0x18000ce2f  sub     rsp, 60h
0x18000ce33  xor     eax, eax
0x18000ce35  mov     rsi, rcx
0x18000ce38  mov     [rcx], rax
0x18000ce3b  xorps   xmm0, xmm0
0x18000ce3e  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18000ce43  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x18000ce48  mov     rbp, r9
0x18000ce4b  mov     r14, r8
0x18000ce4e  mov     rdi, rdx
0x18000ce51  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x18000ce56  call    cs:__imp_VariantInit
0x18000ce5c  mov     ecx, 58h ; 'X'; Size
0x18000ce61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ce66  mov     rbx, rax
0x18000ce69  test    rax, rax
0x18000ce6c  jz      loc_18000CF58
0x18000ce72  mov     rcx, rax; this
0x18000ce75  call    ??0CIISEnumVariant@@QEAA@XZ; CIISEnumVariant::CIISEnumVariant(void)
0x18000ce7a  lea     rax, ??_7CIISSchemaEnum@@6B@; const CIISSchemaEnum::`vftable'
0x18000ce81  mov     qword ptr [rbx+10h], 0
0x18000ce89  lea     rcx, [rbx+28h]; this
0x18000ce8d  mov     [rbx], rax
0x18000ce90  xor     r9d, r9d; unsigned int
0x18000ce93  mov     qword ptr [rbx+18h], 0
0x18000ce9b  xor     r8d, r8d; unsigned __int16 *
0x18000ce9e  mov     qword ptr [rbx+20h], 0
0x18000cea6  xor     edx, edx; unsigned __int16 *
0x18000cea8  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x18000cead  mov     dword ptr [rbx+40h], 0
0x18000ceb4  lea     rcx, [rbx+28h]; this
0x18000ceb8  mov     rdx, r14; struct CCredentials *
0x18000cebb  mov     [rbx+50h], rdi
0x18000cebf  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x18000cec4  mov     rcx, rdi; this
0x18000cec7  mov     dword ptr [rbx+40h], 0
0x18000cece  call    ?Sort@StrMap@@IEBAXXZ; StrMap::Sort(void)
0x18000ced3  lea     rcx, [rdi+20h]; this
0x18000ced7  mov     dword ptr [rbx+44h], 0
0x18000cede  call    ?Sort@StrMap@@IEBAXXZ; StrMap::Sort(void)
0x18000cee3  lea     rdx, [rbx+20h]
0x18000cee7  mov     dword ptr [rbx+48h], 0
0x18000ceee  mov     rcx, rbp
0x18000cef1  call    ADsAllocString
0x18000cef6  mov     edi, eax
0x18000cef8  test    eax, eax
0x18000cefa  js      short loc_18000CF42
0x18000cefc  mov     rcx, [rsp+88h+arg_20]
0x18000cf04  lea     rdx, [rbx+18h]
0x18000cf08  call    ADsAllocString
0x18000cf0d  mov     edi, eax
0x18000cf0f  test    eax, eax
0x18000cf11  js      short loc_18000CF42
0x18000cf13  movups  xmm0, xmmword ptr [rsp+88h+pvarg]
0x18000cf18  lea     rdx, [rbx+10h]; struct ObjectTypeList **
0x18000cf1c  movsd   xmm1, qword ptr [rsp+88h+pvarg+10h]
0x18000cf22  lea     rcx, [rsp+88h+var_48]; struct tagVARIANT
0x18000cf27  movaps  xmmword ptr [rsp+88h+var_48], xmm0
0x18000cf2c  movsd   qword ptr [rsp+88h+var_48+10h], xmm1
0x18000cf32  call    ?CreateObjectTypeList@ObjectTypeList@@SAJUtagVARIANT@@PEAPEAV1@@Z; ObjectTypeList::CreateObjectTypeList(tagVARIANT,ObjectTypeList * *)
0x18000cf37  mov     edi, eax
0x18000cf39  test    eax, eax
0x18000cf3b  js      short loc_18000CF42
0x18000cf3d  mov     [rsi], rbx
0x18000cf40  jmp     short loc_18000CF5D
0x18000cf42  mov     rax, [rbx]
0x18000cf45  mov     edx, 1
0x18000cf4a  mov     rcx, rbx
0x18000cf4d  mov     rax, [rax+38h]
0x18000cf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf56  jmp     short loc_18000CF5D
0x18000cf58  mov     edi, 8007000Eh
0x18000cf5d  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18000cf62  call    cs:__imp_VariantClear
0x18000cf68  mov     eax, edi
0x18000cf6a  add     rsp, 60h
0x18000cf6e  pop     r14
0x18000cf70  pop     rdi
0x18000cf71  pop     rsi
0x18000cf72  pop     rbp
0x18000cf73  pop     rbx
0x18000cf74  retn
```
