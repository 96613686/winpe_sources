# CIISGenObject::Create(ushort *,ushort *,IDispatch * *)

- ea: `0x180005350`
- end: `0x180005493`
- name: `?Create@CIISGenObject@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `323`
- prototype: `int(CIISGenObject *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180005350`
- `0x18000549c`
- `0x180007e04`
- `0x18001bc54`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005465`
- `OLEAUT32!__imp_SysFreeString` at `0x180005473`
- `OLEAUT32!__imp_SysFreeString` at `0x180005465`
- `OLEAUT32!__imp_SysFreeString` at `0x180005473`

## pseudocode

```c
__int64 __fastcall CIISGenObject::Create(
        CIISGenObject *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IDispatch **a4)
{
  IIsSchema *v8; // rcx
  unsigned __int16 *v9; // rbx
  int v10; // edi
  int v11; // eax
  unsigned __int16 *v13; // [rsp+40h] [rbp-28h] BYREF
  void *v14; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-10h] BYREF
  int v17; // [rsp+B8h] [rbp+50h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  v8 = (IIsSchema *)*((_QWORD *)this + 17);
  v9 = 0;
  v17 = 0;
  bstrString = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  v10 = IIsSchema::ValidateClassName(v8, a2);
  if ( v10 >= 0 )
  {
    v11 = CIISGenObject::ValidateChildNode((CIISGenObject *)((char *)this - 72), a2, a3, &v17, &bstrString, &v13, &v15);
    v9 = v13;
    v10 = v11;
    if ( v11 >= 0 )
    {
      v10 = CIISGenObject::CreateGenericObject(v13, v15, a2, (CIISGenObject *)((char *)this + 104), 2u, &IID_IADs, &v14);
      if ( v10 >= 0 )
        v10 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IDispatch **))v14)(v14, &IID_IDispatch, a4);
    }
  }
  if ( v14 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v17 )
  {
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v9 )
      SysFreeString(v9);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005350  push    rbp
0x180005352  push    rbx
0x180005353  push    rsi
0x180005354  push    rdi
0x180005355  push    r12
0x180005357  push    r13
0x180005359  push    r14
0x18000535b  push    r15
0x18000535d  mov     rbp, rsp
0x180005360  sub     rsp, 68h
0x180005364  xor     eax, eax
0x180005366  mov     r15, r9
0x180005369  mov     r14, r8
0x18000536c  mov     rsi, rdx
0x18000536f  mov     r13, rcx
0x180005372  test    rdx, rdx
0x180005375  jz      loc_18000547D
0x18000537b  test    r8, r8
0x18000537e  jz      loc_18000547D
0x180005384  test    r9, r9
0x180005387  jz      loc_18000547D
0x18000538d  mov     rcx, [rcx+88h]; this
0x180005394  mov     ebx, eax
0x180005396  mov     [rbp+arg_8], eax
0x180005399  mov     [rbp+bstrString], rax
0x18000539d  mov     [rbp+var_28], rax
0x1800053a1  mov     [rbp+var_18], rax
0x1800053a5  mov     [rbp+var_20], rax
0x1800053a9  call    ?ValidateClassName@IIsSchema@@QEAAJPEBG@Z; IIsSchema::ValidateClassName(ushort const *)
0x1800053ae  mov     edi, eax
0x1800053b0  test    eax, eax
0x1800053b2  js      loc_180005441
0x1800053b8  lea     rax, [rbp+var_18]
0x1800053bc  mov     r8, r14; unsigned __int16 *
0x1800053bf  mov     [rsp+68h+var_38], rax; unsigned __int16 **
0x1800053c4  lea     r9, [rbp+arg_8]; int *
0x1800053c8  lea     rax, [rbp+var_28]
0x1800053cc  mov     rdx, rsi; unsigned __int16 *
0x1800053cf  mov     [rsp+68h+var_40], rax; unsigned __int16 **
0x1800053d4  lea     rcx, [r13-48h]; this
0x1800053d8  lea     rax, [rbp+bstrString]
0x1800053dc  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x1800053e1  call    ?ValidateChildNode@CIISGenObject@@IEAAJPEAG0PEAHPEAPEAG22@Z; CIISGenObject::ValidateChildNode(ushort *,ushort *,int *,ushort * *,ushort * *,ushort * *)
0x1800053e6  mov     rbx, [rbp+var_28]
0x1800053ea  mov     edi, eax
0x1800053ec  test    eax, eax
0x1800053ee  js      short loc_180005441
0x1800053f0  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800053f4  lea     rax, [rbp+var_20]
0x1800053f8  mov     [rsp+68h+var_38], rax; void **
0x1800053fd  lea     r9, [r13+68h]; struct CCredentials *
0x180005401  lea     rax, IID_IADs
0x180005408  mov     r8, rsi; unsigned __int16 *
0x18000540b  mov     [rsp+68h+var_40], rax; struct _GUID *
0x180005410  mov     rcx, rbx; unsigned __int16 *
0x180005413  mov     dword ptr [rsp+68h+var_48], 2; unsigned int
0x18000541b  call    ?CreateGenericObject@CIISGenObject@@SAJPEBG00AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z; CIISGenObject::CreateGenericObject(ushort const *,ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)
0x180005420  mov     edi, eax
0x180005422  test    eax, eax
0x180005424  js      short loc_180005441
0x180005426  mov     rcx, [rbp+var_20]
0x18000542a  lea     rdx, IID_IDispatch
0x180005431  mov     r8, r15
0x180005434  mov     rax, [rcx]
0x180005437  mov     rax, [rax]
0x18000543a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543f  mov     edi, eax
0x180005441  mov     rcx, [rbp+var_20]
0x180005445  test    rcx, rcx
0x180005448  jz      short loc_180005456
0x18000544a  mov     rax, [rcx]
0x18000544d  mov     rax, [rax+10h]
0x180005451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005456  cmp     [rbp+arg_8], 0
0x18000545a  jz      short loc_180005479
0x18000545c  mov     rcx, [rbp+bstrString]; bstrString
0x180005460  test    rcx, rcx
0x180005463  jz      short loc_18000546B
0x180005465  call    cs:__imp_SysFreeString
0x18000546b  test    rbx, rbx
0x18000546e  jz      short loc_180005479
0x180005470  mov     rcx, rbx; bstrString
0x180005473  call    cs:__imp_SysFreeString
0x180005479  mov     eax, edi
0x18000547b  jmp     short loc_180005482
0x18000547d  mov     eax, 80004003h
0x180005482  add     rsp, 68h
0x180005486  pop     r15
0x180005488  pop     r14
0x18000548a  pop     r13
0x18000548c  pop     r12
0x18000548e  pop     rdi
0x18000548f  pop     rsi
0x180005490  pop     rbx
0x180005491  pop     rbp
0x180005492  retn
```
