# CIISNamespaceEnum::Create(CIISNamespaceEnum * *,tagVARIANT,CCredentials &)

- ea: `0x180002710`
- end: `0x1800027ce`
- name: `?Create@CIISNamespaceEnum@@SAJPEAPEAV1@UtagVARIANT@@AEAVCCredentials@@@Z`
- size: `190`
- prototype: `static int(struct CIISNamespaceEnum **, struct tagVARIANT *__struct_ptr, struct CCredentials *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002560`

## callees

- `0x1800010b0`
- `0x180002710`
- `0x18000d380`
- `0x180014d2c`
- `0x1800195b8`
- `0x18001984c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIISNamespaceEnum::Create(
        struct CIISNamespaceEnum **a1,
        struct tagVARIANT *a2,
        struct CCredentials *a3)
{
  CIISEnumVariant *v6; // rax
  CIISEnumVariant *v7; // rbx
  IRecordInfo *pRecInfo; // xmm1_8
  int v9; // edi
  struct tagVARIANT v11; // [rsp+20h] [rbp-48h] BYREF

  v6 = (CIISEnumVariant *)operator new(0x40u);
  v7 = v6;
  if ( v6 )
  {
    CIISEnumVariant::CIISEnumVariant(v6);
    *(_QWORD *)v7 = &CIISNamespaceEnum::`vftable';
    CCredentials::Initialize((CIISEnumVariant *)((char *)v7 + 32), 0, 0, 0);
    pRecInfo = a2->pRecInfo;
    *(_OWORD *)&v11.vt = *(_OWORD *)&a2->vt;
    v11.pRecInfo = pRecInfo;
    *((_QWORD *)v7 + 2) = 0;
    *((_DWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    v9 = ObjectTypeList::CreateObjectTypeList(&v11, (struct ObjectTypeList **)v7 + 2);
    if ( v9 >= 0 )
    {
      CCredentials::operator=((CIISEnumVariant *)((char *)v7 + 32), a3);
      *a1 = v7;
    }
    else
    {
      (*(void (__fastcall **)(CIISEnumVariant *, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002710  push    rbx
0x180002712  push    rsi
0x180002713  push    rdi
0x180002714  push    r14
0x180002716  sub     rsp, 48h
0x18000271a  mov     r14, rcx
0x18000271d  mov     rsi, r8
0x180002720  mov     ecx, 40h ; '@'; Size
0x180002725  mov     rdi, rdx
0x180002728  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000272d  mov     rbx, rax
0x180002730  test    rax, rax
0x180002733  jz      loc_1800027BD
0x180002739  mov     rcx, rax; this
0x18000273c  call    ??0CIISEnumVariant@@QEAA@XZ; CIISEnumVariant::CIISEnumVariant(void)
0x180002741  lea     rax, ??_7CIISNamespaceEnum@@6B@; const CIISNamespaceEnum::`vftable'
0x180002748  xor     r9d, r9d; unsigned int
0x18000274b  lea     rcx, [rbx+20h]; this
0x18000274f  mov     [rbx], rax
0x180002752  xor     r8d, r8d; unsigned __int16 *
0x180002755  xor     edx, edx; unsigned __int16 *
0x180002757  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x18000275c  movaps  xmm0, xmmword ptr [rdi]
0x18000275f  lea     rdx, [rbx+10h]; struct ObjectTypeList **
0x180002763  movsd   xmm1, qword ptr [rdi+10h]
0x180002768  lea     rcx, [rsp+68h+var_48]; struct tagVARIANT
0x18000276d  movaps  xmmword ptr [rsp+68h+var_48], xmm0
0x180002772  movsd   qword ptr [rsp+68h+var_48+10h], xmm1
0x180002778  mov     qword ptr [rbx+10h], 0
0x180002780  mov     dword ptr [rbx+18h], 0
0x180002787  mov     byte ptr [rbx+38h], 0
0x18000278b  call    ?CreateObjectTypeList@ObjectTypeList@@SAJUtagVARIANT@@PEAPEAV1@@Z; ObjectTypeList::CreateObjectTypeList(tagVARIANT,ObjectTypeList * *)
0x180002790  mov     edi, eax
0x180002792  test    eax, eax
0x180002794  jns     short loc_1800027AC
0x180002796  mov     rcx, [rbx]
0x180002799  mov     edx, 1
0x18000279e  mov     rax, [rcx+38h]
0x1800027a2  mov     rcx, rbx
0x1800027a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027aa  jmp     short loc_1800027C2
0x1800027ac  lea     rcx, [rbx+20h]; this
0x1800027b0  mov     rdx, rsi; struct CCredentials *
0x1800027b3  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x1800027b8  mov     [r14], rbx
0x1800027bb  jmp     short loc_1800027C2
0x1800027bd  mov     edi, 8007000Eh
0x1800027c2  mov     eax, edi
0x1800027c4  add     rsp, 48h
0x1800027c8  pop     r14
0x1800027ca  pop     rdi
0x1800027cb  pop     rsi
0x1800027cc  pop     rbx
0x1800027cd  retn
```
