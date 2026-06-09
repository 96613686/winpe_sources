# AtlAxCreateControlLic

- ea: `0x180011ce0`
- end: `0x180011e2e`
- name: `AtlAxCreateControlLic`
- size: `334`
- prototype: `__int64 __usercall@<rax>(OLECHAR *psz@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ab80`
- `0x18000af30`

## callees

- `0x180003858`
- `0x18000c580`
- `0x180011ce0`
- `0x180011e34`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011dc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180011dc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d90`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AtlAxCreateControlLic(OLECHAR *psz, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // edi
  void (__fastcall ***v12)(_QWORD, GUID *, _QWORD *); // rcx
  void (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-28h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v16[3]; // [rsp+60h] [rbp-18h] BYREF

  AtlAxWinInit();
  v14 = 0;
  v16[0] = 0;
  v11 = ATL::CComCreator<ATL::CComPolyObject<ATL::CAxHostWindow>>::CreateInstance(v10, v9, &v14);
  if ( v11 >= 0 )
  {
    v15 = 0;
    (**v14)(v14, &GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e, &v15);
    if ( psz )
    {
      psz = SysAllocString(psz);
      if ( !psz )
        ATL::AtlThrowImpl(-2147024882);
    }
    v11 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, _QWORD *, GUID *, _QWORD, __int64))(*(_QWORD *)v15 + 80LL))(
            v15,
            psz,
            a2,
            a3,
            v16,
            &GUID_NULL,
            0,
            a5);
    SysFreeString(psz);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( a4 )
  {
    if ( v11 >= 0 )
    {
      *a4 = v14;
      v12 = 0;
      v14 = 0;
      goto LABEL_12;
    }
    *a4 = 0;
  }
  v12 = v14;
LABEL_12:
  if ( v16[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16[0] + 16LL))(v16[0]);
    v12 = v14;
  }
  if ( v12 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v12)[2])(v12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180011ce0  push    rbp
0x180011ce2  push    rbx
0x180011ce3  push    rsi
0x180011ce4  push    rdi
0x180011ce5  push    r14
0x180011ce7  push    r15
0x180011ce9  mov     rbp, rsp
0x180011cec  sub     rsp, 78h
0x180011cf0  mov     rsi, r9
0x180011cf3  mov     r14, r8
0x180011cf6  mov     r15, rdx
0x180011cf9  mov     rbx, rcx
0x180011cfc  call    AtlAxWinInit
0x180011d01  mov     [rbp+var_28], 0
0x180011d09  mov     [rbp+var_18], 0
0x180011d11  lea     r8, [rbp+var_28]
0x180011d15  call    ?CreateInstance@?$CComCreator@V?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComPolyObject<ATL::CAxHostWindow>>::CreateInstance(void *,_GUID const &,void * *)
0x180011d1a  mov     edi, eax
0x180011d1c  test    eax, eax
0x180011d1e  js      loc_180011DAD
0x180011d24  mov     [rbp+var_20], 0
0x180011d2c  mov     rcx, [rbp+var_28]
0x180011d30  mov     rax, [rcx]
0x180011d33  lea     r8, [rbp+var_20]
0x180011d37  lea     rdx, _GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e
0x180011d3e  mov     rax, [rax]
0x180011d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d46  test    rbx, rbx
0x180011d49  jnz     short loc_180011DC5
0x180011d4b  mov     rcx, [rbp+var_20]
0x180011d4f  mov     rax, [rcx]
0x180011d52  mov     rdx, [rbp+arg_20]
0x180011d56  mov     [rsp+78h+var_40], rdx
0x180011d5b  mov     [rsp+78h+var_48], 0
0x180011d64  lea     rdx, GUID_NULL
0x180011d6b  mov     [rsp+78h+var_50], rdx
0x180011d70  lea     rdx, [rbp+var_18]
0x180011d74  mov     [rsp+78h+var_58], rdx
0x180011d79  mov     r9, r14
0x180011d7c  mov     r8, r15
0x180011d7f  mov     rdx, rbx
0x180011d82  mov     rax, [rax+50h]
0x180011d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d8b  mov     edi, eax
0x180011d8d  mov     rcx, rbx; bstrString
0x180011d90  call    cs:__imp_SysFreeString
0x180011d96  nop
0x180011d97  mov     rcx, [rbp+var_20]
0x180011d9b  test    rcx, rcx
0x180011d9e  jz      short loc_180011DAD
0x180011da0  mov     rax, [rcx]
0x180011da3  mov     rax, [rax+10h]
0x180011da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dac  nop
0x180011dad  test    rsi, rsi
0x180011db0  jz      short loc_180011DE2
0x180011db2  test    edi, edi
0x180011db4  js      short loc_180011DDB
0x180011db6  mov     rax, [rbp+var_28]
0x180011dba  mov     [rsi], rax
0x180011dbd  xor     ecx, ecx
0x180011dbf  mov     [rbp+var_28], rcx
0x180011dc3  jmp     short loc_180011DE6
0x180011dc5  mov     rcx, rbx; psz
0x180011dc8  call    cs:__imp_SysAllocString
0x180011dce  mov     rbx, rax
0x180011dd1  test    rax, rax
0x180011dd4  jz      short loc_180011E23
0x180011dd6  jmp     loc_180011D4B
0x180011ddb  mov     qword ptr [rsi], 0
0x180011de2  mov     rcx, [rbp+var_28]
0x180011de6  mov     rdx, [rbp+var_18]
0x180011dea  test    rdx, rdx
0x180011ded  jz      short loc_180011E02
0x180011def  mov     rax, [rdx]
0x180011df2  mov     rcx, rdx
0x180011df5  mov     rax, [rax+10h]
0x180011df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dfe  mov     rcx, [rbp+var_28]
0x180011e02  test    rcx, rcx
0x180011e05  jz      short loc_180011E14
0x180011e07  mov     rax, [rcx]
0x180011e0a  mov     rax, [rax+10h]
0x180011e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e13  nop
0x180011e14  mov     eax, edi
0x180011e16  add     rsp, 78h
0x180011e1a  pop     r15
0x180011e1c  pop     r14
0x180011e1e  pop     rdi
0x180011e1f  pop     rsi
0x180011e20  pop     rbx
0x180011e21  pop     rbp
0x180011e22  retn
0x180011e23  mov     ecx, 8007000Eh; int
0x180011e28  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
