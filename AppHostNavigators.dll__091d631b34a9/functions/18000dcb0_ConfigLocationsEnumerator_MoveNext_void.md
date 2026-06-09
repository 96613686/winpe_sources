# ConfigLocationsEnumerator::MoveNext(void)

- ea: `0x18000dcb0`
- end: `0x18000de4f`
- name: `?MoveNext@ConfigLocationsEnumerator@@QEAA_NXZ`
- size: `415`
- prototype: `bool __fastcall(ConfigLocationsEnumerator *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a104`
- `0x18000cb10`

## callees

- `0x1800021a4`
- `0x180004728`
- `0x180007aac`
- `0x18000dcb0`
- `0x180012e90`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000dd33`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd33`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ConfigLocationsEnumerator::MoveNext(ConfigLocationsEnumerator *this)
{
  struct IUnknown **v2; // rsi
  unsigned int v3; // edi
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // r14d
  int v7; // eax
  const wchar_t *v8; // rax
  int v9; // eax
  struct IUnknown *v10; // rdx
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v13; // [rsp+40h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+90h] [rbp+30h] BYREF
  LONGLONG v15; // [rsp+98h] [rbp+38h] BYREF
  struct IUnknown *v16; // [rsp+A0h] [rbp+40h] BYREF

  v16 = 0;
  v15 = 0;
  v2 = (struct IUnknown **)((char *)this + 48);
  if ( *((_QWORD *)this + 6) )
    v3 = *((_DWORD *)this + 4) + 1;
  else
    v3 = 0;
  if ( v3 < *((_DWORD *)this + 4) || v3 >= *((_DWORD *)this + 5) )
  {
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
    return 0;
  }
  else
  {
    v4 = (__int64 *)*((_QWORD *)this + 1);
    v5 = *v4;
    pvarg.vt = 19;
    pvarg.lVal = v3;
    v13 = pvarg;
    v6 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IUnknown **))(v5 + 32))(v4, &v13, &v16);
    VariantClear(&pvarg);
    if ( v6 < 0 )
    {
      pExceptionObject = v6;
      throw (long *)&pExceptionObject;
    }
    v7 = ((__int64 (__fastcall *)(struct IUnknown *, LONGLONG *))v16->lpVtbl[1].QueryInterface)(v16, &v15);
    if ( v7 < 0 )
    {
      pExceptionObject = v7;
      throw (long *)&pExceptionObject;
    }
    if ( ScopedBSTR::QueryCCH((ScopedBSTR *)&v15) && *(_BYTE *)this )
    {
      v8 = L"WEBROOT/APPHOST/";
    }
    else if ( !ScopedBSTR::QueryCCH((ScopedBSTR *)&v15) || (v8 = L"APPHOST/", !*((_BYTE *)this + 1)) )
    {
      v8 = &qword_1800181B0;
    }
    *(_QWORD *)&pvarg.vt = v8;
    pvarg.llVal = v15;
    **((_WORD **)this + 4) = 0;
    *((_DWORD *)this + 10) = 0;
    v9 = STRU::AuxAppend(
           (ConfigLocationsEnumerator *)((char *)this + 24),
           (const unsigned __int16 *const *const)&pvarg,
           2u);
    if ( v9 < 0 )
    {
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    v10 = v16;
    v16 = 0;
    if ( *v2 != v10 )
      ATL::AtlComPtrAssign(v2, v10);
    *((_DWORD *)this + 4) = v3;
    ScopedBSTR::Reset((ScopedBSTR *)&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
    return 1;
  }
}

```

## disassembly

```asm
0x18000dcb0  push    rbp
0x18000dcb2  push    rbx
0x18000dcb3  push    rsi
0x18000dcb4  push    rdi
0x18000dcb5  push    r14
0x18000dcb7  mov     rbp, rsp
0x18000dcba  sub     rsp, 60h
0x18000dcbe  mov     rbx, rcx
0x18000dcc1  mov     [rbp+arg_10], 0
0x18000dcc9  mov     [rbp+arg_8], 0
0x18000dcd1  lea     rsi, [rcx+30h]
0x18000dcd5  cmp     qword ptr [rsi], 0
0x18000dcd9  jnz     short loc_18000DCDF
0x18000dcdb  xor     edi, edi
0x18000dcdd  jmp     short loc_18000DCE4
0x18000dcdf  mov     edi, [rcx+10h]
0x18000dce2  inc     edi
0x18000dce4  cmp     edi, [rcx+10h]
0x18000dce7  jb      loc_18000DE2F
0x18000dced  cmp     edi, [rcx+14h]
0x18000dcf0  jnb     loc_18000DE2F
0x18000dcf6  mov     rcx, [rcx+8]
0x18000dcfa  mov     rax, [rcx]
0x18000dcfd  mov     edx, 13h
0x18000dd02  mov     word ptr [rbp+pvarg], dx
0x18000dd06  mov     dword ptr [rbp+pvarg+8], edi
0x18000dd09  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000dd0d  movaps  [rbp+var_20], xmm0
0x18000dd11  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000dd16  movsd   [rbp+var_10], xmm1
0x18000dd1b  lea     r8, [rbp+arg_10]
0x18000dd1f  lea     rdx, [rbp+var_20]
0x18000dd23  mov     rax, [rax+20h]
0x18000dd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd2c  mov     r14d, eax
0x18000dd2f  lea     rcx, [rbp+pvarg]; pvarg
0x18000dd33  call    cs:__imp_VariantClear
0x18000dd39  test    r14d, r14d
0x18000dd3c  jns     short loc_18000DD53
0x18000dd3e  mov     [rbp+pExceptionObject], r14d
0x18000dd42  lea     rdx, _TI1J; pThrowInfo
0x18000dd49  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000dd4d  call    _CxxThrowException_0
0x18000dd53  mov     rcx, [rbp+arg_10]
0x18000dd57  mov     rax, [rcx]
0x18000dd5a  lea     rdx, [rbp+arg_8]
0x18000dd5e  mov     rax, [rax+18h]
0x18000dd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd67  test    eax, eax
0x18000dd69  jns     short loc_18000DD7F
0x18000dd6b  mov     [rbp+pExceptionObject], eax
0x18000dd6e  lea     rdx, _TI1J; pThrowInfo
0x18000dd75  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000dd79  call    _CxxThrowException_0
0x18000dd7f  lea     rcx, [rbp+arg_8]; this
0x18000dd83  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x18000dd88  test    eax, eax
0x18000dd8a  jz      short loc_18000DD9A
0x18000dd8c  cmp     byte ptr [rbx], 0
0x18000dd8f  jz      short loc_18000DD9A
0x18000dd91  lea     rax, aWebrootApphost; "WEBROOT/APPHOST/"
0x18000dd98  jmp     short loc_18000DDBB
0x18000dd9a  lea     rcx, [rbp+arg_8]; this
0x18000dd9e  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x18000dda3  test    eax, eax
0x18000dda5  jz      short loc_18000DDB4
0x18000dda7  cmp     byte ptr [rbx+1], 0
0x18000ddab  lea     rax, aApphost_0; "APPHOST/"
0x18000ddb2  jnz     short loc_18000DDBB
0x18000ddb4  lea     rax, qword_1800181B0
0x18000ddbb  mov     qword ptr [rbp+pvarg], rax
0x18000ddbf  mov     rax, [rbp+arg_8]
0x18000ddc3  mov     qword ptr [rbp+pvarg+8], rax
0x18000ddc7  lea     rcx, [rbx+18h]; this
0x18000ddcb  mov     rdx, [rcx+8]
0x18000ddcf  xor     eax, eax
0x18000ddd1  mov     [rdx], ax
0x18000ddd4  mov     [rcx+10h], eax
0x18000ddd7  lea     r8d, [rax+2]; unsigned __int64
0x18000dddb  lea     rdx, [rbp+pvarg]; unsigned __int16 **
0x18000dddf  call    ?AuxAppend@STRU@@AEAAJQEBQEBG_K@Z; STRU::AuxAppend(ushort const * const * const,unsigned __int64)
0x18000dde4  test    eax, eax
0x18000dde6  jns     short loc_18000DDFC
0x18000dde8  mov     [rbp+pExceptionObject], eax
0x18000ddeb  lea     rdx, _TI1J; pThrowInfo
0x18000ddf2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ddf6  call    _CxxThrowException_0
0x18000ddfc  mov     rdx, [rbp+arg_10]; struct IUnknown *
0x18000de00  mov     [rbp+arg_10], 0
0x18000de08  cmp     [rsi], rdx
0x18000de0b  jz      short loc_18000DE15
0x18000de0d  mov     rcx, rsi; struct IUnknown **
0x18000de10  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000de15  mov     [rbx+10h], edi
0x18000de18  lea     rcx, [rbp+arg_8]; this
0x18000de1c  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000de21  nop
0x18000de22  lea     rcx, [rbp+arg_10]
0x18000de26  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000de2b  mov     al, 1
0x18000de2d  jmp     short loc_18000DE44
0x18000de2f  lea     rcx, [rbp+arg_8]; this
0x18000de33  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000de38  nop
0x18000de39  lea     rcx, [rbp+arg_10]
0x18000de3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000de42  xor     al, al
0x18000de44  add     rsp, 60h
0x18000de48  pop     r14
0x18000de4a  pop     rdi
0x18000de4b  pop     rsi
0x18000de4c  pop     rbx
0x18000de4d  pop     rbp
0x18000de4e  retn
```
