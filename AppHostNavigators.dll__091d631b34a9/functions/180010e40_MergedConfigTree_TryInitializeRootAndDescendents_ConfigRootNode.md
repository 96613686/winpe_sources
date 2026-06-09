# MergedConfigTree::TryInitializeRootAndDescendents(ConfigRootNode *)

- ea: `0x180010e40`
- end: `0x18001105c`
- name: `?TryInitializeRootAndDescendents@MergedConfigTree@@UEAA_NPEAVConfigRootNode@@@Z`
- size: `540`
- prototype: `bool __fastcall(MergedConfigTree *__hidden this, struct ConfigRootNode *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021a4`
- `0x1800021e0`
- `0x180010d64`
- `0x180010e40`
- `0x180012e40`
- `0x180012e90`
- `0x180012ea8`
- `0x180012f3c`
- `0x1800130a0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall MergedConfigTree::TryInitializeRootAndDescendents(MergedConfigTree *this, struct ConfigRootNode *a2)
{
  ScopedBSTR *v4; // rsi
  unsigned int CCH; // eax
  int v6; // eax
  UINT i; // edi
  OLECHAR *v8; // rdx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  bool v16; // bl
  int pExceptionObject; // [rsp+30h] [rbp-50h] BYREF
  __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  struct IAppHostSectionGroup *v20; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h] BYREF
  __int16 v23; // [rsp+58h] [rbp-28h] BYREF
  char v24; // [rsp+5Ah] [rbp-26h]
  int v25; // [rsp+5Ch] [rbp-24h]
  __int16 *v26; // [rsp+60h] [rbp-20h]
  int v27; // [rsp+68h] [rbp-18h]

  v4 = (MergedConfigTree *)((char *)this + 136);
  CCH = ScopedBSTR::QueryCCH((MergedConfigTree *)((char *)this + 136));
  if ( CCH )
  {
    v22 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL) + 48LL))(
           *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
           &v22);
    if ( v6 < 0 )
    {
      pExceptionObject = v6;
      throw (long *)&pExceptionObject;
    }
    v24 = 0;
    v25 = 2;
    v26 = &v23;
    v27 = 0;
    v23 = 0;
    for ( i = 0; i <= ScopedBSTR::QueryCCH(v4); ++i )
    {
      v8 = *(OLECHAR **)v4;
      if ( *(_WORD *)(*(_QWORD *)v4 + 2LL * i) == 47 || !v8[i] )
      {
        v19 = 0;
        v9 = ScopedBSTR::CopyStringCCH((ScopedBSTR *)&v19, v8, i);
        if ( v9 < 0 )
        {
          pExceptionObject = v9;
          throw (long *)&pExceptionObject;
        }
        v21 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 24LL))(v22, v19, &v21);
        if ( v10 < 0 )
        {
          pExceptionObject = v10;
          throw (long *)&pExceptionObject;
        }
        if ( v21 )
        {
          v20 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, struct IAppHostSectionGroup **))(*(_QWORD *)v21 + 80LL))(v21, &v20);
          if ( v11 < 0 )
          {
            pExceptionObject = v11;
            throw (long *)&pExceptionObject;
          }
          if ( v20 )
          {
            *v26 = 0;
            v27 = 0;
            v12 = ScopedBSTR::QueryCCH(v4);
            v13 = ScopedBSTR::QueryCCH((ScopedBSTR *)&v19);
            MergedConfigTree::InitializeSectionGroupNodeChildren(this, a2, (struct STRU *)&v23, v20, v13 == v12);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
        ScopedBSTR::Reset((ScopedBSTR *)&v19);
      }
    }
    v14 = *((_QWORD *)a2 + 4);
    if ( v14 )
      v15 = *(_DWORD *)(*(_QWORD *)(v14 + 48) - 32LL) + 1;
    else
      v15 = 0;
    v16 = v15 != 0;
    BUFFER::~BUFFER((BUFFER *)&v23);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    LOBYTE(CCH) = v16;
  }
  return CCH;
}

```

## disassembly

```asm
0x180010e40  mov     [rsp-28h+arg_10], rbx
0x180010e45  mov     [rsp-28h+arg_18], rsi
0x180010e4a  push    rbp
0x180010e4b  push    rdi
0x180010e4c  push    r12
0x180010e4e  push    r14
0x180010e50  push    r15
0x180010e52  mov     rbp, rsp
0x180010e55  sub     rsp, 80h
0x180010e5c  mov     rax, cs:__security_cookie
0x180010e63  xor     rax, rsp
0x180010e66  mov     [rbp+var_10], rax
0x180010e6a  mov     r15, rdx
0x180010e6d  mov     r14, rcx
0x180010e70  lea     rsi, [rcx+88h]
0x180010e77  mov     rcx, rsi; this
0x180010e7a  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x180010e7f  xor     r12d, r12d
0x180010e82  test    eax, eax
0x180010e84  jz      loc_180011034
0x180010e8a  mov     [rbp+var_30], r12
0x180010e8e  mov     rax, [r14+18h]
0x180010e92  mov     rcx, [rax+10h]
0x180010e96  mov     rax, [rcx]
0x180010e99  lea     rdx, [rbp+var_30]
0x180010e9d  mov     rax, [rax+30h]
0x180010ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea6  test    eax, eax
0x180010ea8  jns     short loc_180010EBE
0x180010eaa  mov     [rbp+pExceptionObject], eax
0x180010ead  lea     rdx, _TI1J; pThrowInfo
0x180010eb4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010eb8  call    _CxxThrowException_0
0x180010ebe  mov     [rbp+var_26], r12b
0x180010ec2  mov     [rbp+var_24], 2
0x180010ec9  lea     rax, [rbp+var_28]
0x180010ecd  mov     [rbp+var_20], rax
0x180010ed1  mov     [rbp+var_18], r12d
0x180010ed5  mov     [rbp+var_28], r12w
0x180010eda  mov     edi, r12d
0x180010edd  mov     rcx, rsi; this
0x180010ee0  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x180010ee5  cmp     edi, eax
0x180010ee7  ja      loc_180011003
0x180010eed  mov     rdx, [rsi]; strIn
0x180010ef0  mov     eax, edi
0x180010ef2  cmp     word ptr [rdx+rax*2], 2Fh ; '/'
0x180010ef7  jz      short loc_180010F04
0x180010ef9  cmp     [rdx+rax*2], r12w
0x180010efe  jnz     loc_180010FC0
0x180010f04  mov     [rbp+var_48], r12
0x180010f08  mov     r8d, edi; ui
0x180010f0b  lea     rcx, [rbp+var_48]; this
0x180010f0f  call    ?CopyStringCCH@ScopedBSTR@@QEAAJPEBGI@Z; ScopedBSTR::CopyStringCCH(ushort const *,uint)
0x180010f14  test    eax, eax
0x180010f16  js      loc_180010FEF
0x180010f1c  mov     [rbp+var_38], r12
0x180010f20  mov     rcx, [rbp+var_30]
0x180010f24  mov     rax, [rcx]
0x180010f27  lea     r8, [rbp+var_38]
0x180010f2b  mov     rdx, [rbp+var_48]
0x180010f2f  mov     rax, [rax+18h]
0x180010f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f38  test    eax, eax
0x180010f3a  js      loc_180010FDB
0x180010f40  mov     rcx, [rbp+var_38]
0x180010f44  test    rcx, rcx
0x180010f47  jz      short loc_180010FAD
0x180010f49  mov     [rbp+var_40], r12
0x180010f4d  mov     rax, [rcx]
0x180010f50  lea     rdx, [rbp+var_40]
0x180010f54  mov     rax, [rax+50h]
0x180010f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f5d  test    eax, eax
0x180010f5f  js      short loc_180010FC7
0x180010f61  cmp     [rbp+var_40], r12
0x180010f65  jz      short loc_180010FA3
0x180010f67  mov     rax, [rbp+var_20]
0x180010f6b  mov     [rax], r12w
0x180010f6f  mov     [rbp+var_18], r12d
0x180010f73  mov     rcx, rsi; this
0x180010f76  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x180010f7b  mov     ebx, eax
0x180010f7d  lea     rcx, [rbp+var_48]; this
0x180010f81  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x180010f86  cmp     eax, ebx
0x180010f88  setz    al
0x180010f8b  mov     [rsp+80h+var_60], al; pExceptionObject
0x180010f8f  mov     r9, [rbp+var_40]; struct IAppHostSectionGroup *
0x180010f93  lea     r8, [rbp+var_28]; struct STRU *
0x180010f97  mov     rdx, r15; struct SectionGroupNode *
0x180010f9a  mov     rcx, r14; this
0x180010f9d  call    ?InitializeSectionGroupNodeChildren@MergedConfigTree@@AEAAXPEAVSectionGroupNode@@AEAVSTRU@@PEAUIAppHostSectionGroup@@_N@Z; MergedConfigTree::InitializeSectionGroupNodeChildren(SectionGroupNode *,STRU &,IAppHostSectionGroup *,bool)
0x180010fa2  nop
0x180010fa3  lea     rcx, [rbp+var_40]
0x180010fa7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010fac  nop
0x180010fad  lea     rcx, [rbp+var_38]
0x180010fb1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010fb6  nop
0x180010fb7  lea     rcx, [rbp+var_48]; this
0x180010fbb  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x180010fc0  inc     edi
0x180010fc2  jmp     loc_180010EDD
0x180010fc7  mov     [rbp+pExceptionObject], eax
0x180010fca  lea     rdx, _TI1J; pThrowInfo
0x180010fd1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010fd5  call    _CxxThrowException_0
0x180010fdb  mov     [rbp+pExceptionObject], eax
0x180010fde  lea     rdx, _TI1J; pThrowInfo
0x180010fe5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010fe9  call    _CxxThrowException_0
0x180010fef  mov     [rbp+pExceptionObject], eax
0x180010ff2  lea     rdx, _TI1J; pThrowInfo
0x180010ff9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010ffd  call    _CxxThrowException_0
0x180011003  mov     rax, [r15+20h]
0x180011007  test    rax, rax
0x18001100a  jnz     short loc_180011011
0x18001100c  mov     eax, r12d
0x18001100f  jmp     short loc_18001101A
0x180011011  mov     rax, [rax+30h]
0x180011015  mov     eax, [rax-20h]
0x180011018  inc     eax
0x18001101a  test    eax, eax
0x18001101c  setnz   bl
0x18001101f  lea     rcx, [rbp+var_28]; this
0x180011023  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011028  nop
0x180011029  lea     rcx, [rbp+var_30]
0x18001102d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180011032  mov     al, bl
0x180011034  mov     rcx, [rbp+var_10]
0x180011038  xor     rcx, rsp; StackCookie
0x18001103b  call    __security_check_cookie
0x180011040  lea     r11, [rsp+80h+var_s0]
0x180011048  mov     rbx, [r11+40h]
0x18001104c  mov     rsi, [r11+48h]
0x180011050  mov     rsp, r11
0x180011053  pop     r15
0x180011055  pop     r14
0x180011057  pop     r12
0x180011059  pop     rdi
0x18001105a  pop     rbp
0x18001105b  retn
```
