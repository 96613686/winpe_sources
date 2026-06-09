# ConfigLocationsEnumerator::Reset(ushort const *,IAppHostAdminManager *)

- ea: `0x18000de58`
- end: `0x18000e03c`
- name: `?Reset@ConfigLocationsEnumerator@@QEAAXPEBGPEAUIAppHostAdminManager@@@Z`
- size: `484`
- prototype: `void(ConfigLocationsEnumerator *__hidden this, const unsigned __int16 *, struct IAppHostAdminManager *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a104`
- `0x18000cb10`

## callees

- `0x1800021a4`
- `0x180007aac`
- `0x18000de58`
- `0x180012df4`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ConfigLocationsEnumerator::Reset(struct IUnknown **this, OLECHAR *a2, struct IAppHostAdminManager *a3)
{
  struct IUnknown **v6; // rdi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  struct IUnknown *v13; // rdx
  __int64 v14; // [rsp+20h] [rbp-20h] BYREF
  __int64 v15; // [rsp+28h] [rbp-18h] BYREF
  __int64 v16[2]; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF
  int pExceptionObject; // [rsp+78h] [rbp+38h] BYREF
  struct IUnknown *v19; // [rsp+88h] [rbp+48h] BYREF

  *(_WORD *)this = 0;
  v6 = this + 1;
  if ( this[1] )
    ATL::AtlComPtrAssign(this + 1, 0);
  this[2] = 0;
  LOWORD(this[4]->lpVtbl) = 0;
  *((_DWORD *)this + 10) = 0;
  if ( this[6] )
    ATL::AtlComPtrAssign(this + 6, 0);
  v19 = 0;
  v17 = 0;
  if ( a2 && *a2 )
  {
    v16[0] = 0;
    v7 = ((__int64 (__fastcall *)(struct IAppHostAdminManager *, __int64 *))a3->lpVtbl->get_ConfigManager)(a3, v16);
    if ( v7 < 0 )
    {
      pExceptionObject = v7;
      throw (long *)&pExceptionObject;
    }
    v15 = 0;
    v8 = ScopedBSTR::CopyString((ScopedBSTR *)&v15, a2);
    if ( v8 < 0 )
    {
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
    v14 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16[0] + 24LL))(v16[0], v15, &v14);
    if ( v9 <= -2147024895 || (unsigned int)(v9 + 2147024892) <= 0x7FF8FFFB )
    {
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    if ( v14 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v14 + 40LL))(v14, &v19);
      if ( v10 < 0 )
      {
        pExceptionObject = v10;
        throw (long *)&pExceptionObject;
      }
      v11 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v19->lpVtbl[1].QueryInterface)(v19, &v17);
      if ( v11 < 0 )
      {
        pExceptionObject = v11;
        throw (long *)&pExceptionObject;
      }
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      if ( v12 == 7 )
        *(_BYTE *)this = 1;
      v13 = v19;
      v19 = 0;
      if ( *v6 != v13 )
        ATL::AtlComPtrAssign(v6, v13);
      *((_DWORD *)this + 5) = v17;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
}

```

## disassembly

```asm
0x18000de58  mov     [rsp-28h+arg_10], rbx
0x18000de5d  push    rbp
0x18000de5e  push    rsi
0x18000de5f  push    rdi
0x18000de60  push    r14
0x18000de62  push    r15
0x18000de64  mov     rbp, rsp
0x18000de67  sub     rsp, 40h
0x18000de6b  mov     r14, r8
0x18000de6e  mov     rsi, rdx
0x18000de71  mov     rbx, rcx
0x18000de74  xor     r15d, r15d
0x18000de77  mov     [rcx], r15w
0x18000de7b  lea     rdi, [rcx+8]
0x18000de7f  cmp     [rdi], r15
0x18000de82  jz      short loc_18000DE8E
0x18000de84  xor     edx, edx; struct IUnknown *
0x18000de86  mov     rcx, rdi; struct IUnknown **
0x18000de89  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000de8e  mov     [rbx+10h], r15
0x18000de92  mov     rcx, [rbx+20h]
0x18000de96  mov     [rcx], r15w
0x18000de9a  mov     [rbx+28h], r15d
0x18000de9e  lea     rcx, [rbx+30h]; struct IUnknown **
0x18000dea2  cmp     [rcx], r15
0x18000dea5  jz      short loc_18000DEAE
0x18000dea7  xor     edx, edx; struct IUnknown *
0x18000dea9  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000deae  mov     [rbp+arg_18], r15
0x18000deb2  mov     [rbp+arg_0], r15d
0x18000deb6  test    rsi, rsi
0x18000deb9  jz      loc_18000DF80
0x18000debf  cmp     [rsi], r15w
0x18000dec3  jz      loc_18000DF80
0x18000dec9  mov     [rbp+var_10], r15
0x18000decd  mov     rax, [r14]
0x18000ded0  lea     rdx, [rbp+var_10]
0x18000ded4  mov     rcx, r14
0x18000ded7  mov     rax, [rax+30h]
0x18000dedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dee0  test    eax, eax
0x18000dee2  jns     short loc_18000DEF8
0x18000dee4  mov     [rbp+pExceptionObject], eax
0x18000dee7  lea     rdx, _TI1J; pThrowInfo
0x18000deee  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000def2  call    _CxxThrowException_0
0x18000def8  mov     [rbp+var_18], r15
0x18000defc  mov     rdx, rsi; psz
0x18000deff  lea     rcx, [rbp+var_18]; this
0x18000df03  call    ?CopyString@ScopedBSTR@@QEAAJPEBG@Z; ScopedBSTR::CopyString(ushort const *)
0x18000df08  test    eax, eax
0x18000df0a  jns     short loc_18000DF20
0x18000df0c  mov     [rbp+pExceptionObject], eax
0x18000df0f  lea     rdx, _TI1J; pThrowInfo
0x18000df16  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000df1a  call    _CxxThrowException_0
0x18000df20  mov     [rbp+var_20], r15
0x18000df24  mov     rcx, [rbp+var_10]
0x18000df28  mov     rax, [rcx]
0x18000df2b  lea     r8, [rbp+var_20]
0x18000df2f  mov     rdx, [rbp+var_18]
0x18000df33  mov     rax, [rax+18h]
0x18000df37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df3c  cmp     eax, 80070001h
0x18000df41  jle     loc_18000E028
0x18000df47  lea     ecx, [rax+7FF8FFFCh]
0x18000df4d  cmp     ecx, 7FF8FFFBh
0x18000df53  jbe     loc_18000E028
0x18000df59  mov     rcx, [rbp+var_20]
0x18000df5d  test    rcx, rcx
0x18000df60  jnz     short loc_18000DF9D
0x18000df62  lea     rcx, [rbp+var_20]
0x18000df66  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000df6b  nop
0x18000df6c  lea     rcx, [rbp+var_18]; this
0x18000df70  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000df75  nop
0x18000df76  lea     rcx, [rbp+var_10]
0x18000df7a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000df7f  nop
0x18000df80  lea     rcx, [rbp+arg_18]
0x18000df84  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000df89  mov     rbx, [rsp+40h+arg_10]
0x18000df91  add     rsp, 40h
0x18000df95  pop     r15
0x18000df97  pop     r14
0x18000df99  pop     rdi
0x18000df9a  pop     rsi
0x18000df9b  pop     rbp
0x18000df9c  retn
0x18000df9d  mov     rax, [rcx]
0x18000dfa0  lea     rdx, [rbp+arg_18]
0x18000dfa4  mov     rax, [rax+28h]
0x18000dfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfad  test    eax, eax
0x18000dfaf  jns     short loc_18000DFC5
0x18000dfb1  mov     [rbp+pExceptionObject], eax
0x18000dfb4  lea     rdx, _TI1J; pThrowInfo
0x18000dfbb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000dfbf  call    _CxxThrowException_0
0x18000dfc5  mov     rcx, [rbp+arg_18]
0x18000dfc9  mov     rax, [rcx]
0x18000dfcc  lea     rdx, [rbp+arg_0]
0x18000dfd0  mov     rax, [rax+18h]
0x18000dfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd9  test    eax, eax
0x18000dfdb  jns     short loc_18000DFF1
0x18000dfdd  mov     [rbp+pExceptionObject], eax
0x18000dfe0  lea     rdx, _TI1J; pThrowInfo
0x18000dfe7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000dfeb  call    _CxxThrowException_0
0x18000dff1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dff5  inc     rax
0x18000dff8  cmp     [rsi+rax*2], r15w
0x18000dffd  jnz     short loc_18000DFF5
0x18000dfff  cmp     rax, 7
0x18000e003  jnz     short loc_18000E008
0x18000e005  mov     byte ptr [rbx], 1
0x18000e008  mov     rdx, [rbp+arg_18]; struct IUnknown *
0x18000e00c  mov     [rbp+arg_18], r15
0x18000e010  cmp     [rdi], rdx
0x18000e013  jz      short loc_18000E01D
0x18000e015  mov     rcx, rdi; struct IUnknown **
0x18000e018  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000e01d  mov     eax, [rbp+arg_0]
0x18000e020  mov     [rbx+14h], eax
0x18000e023  jmp     loc_18000DF62
0x18000e028  mov     [rbp+pExceptionObject], eax
0x18000e02b  lea     rdx, _TI1J; pThrowInfo
0x18000e032  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000e036  call    _CxxThrowException_0
```
