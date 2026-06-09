# CIISSchema::Create(ushort *,ushort *,IDispatch * *)

- ea: `0x180008340`
- end: `0x1800084a2`
- name: `?Create@CIISSchema@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `354`
- prototype: `int(CIISSchema *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180008340`
- `0x180009a44`
- `0x180009d90`
- `0x18001b5ac`
- `0x18001bc54`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000840c`
- `msvcrt!_wcsicmp` at `0x180008449`
- `msvcrt!_wcsicmp` at `0x18000840c`
- `msvcrt!_wcsicmp` at `0x180008449`

## pseudocode

```c
__int64 __fastcall CIISSchema::Create(
        IIsSchema **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IDispatch **a4)
{
  IIsSchema *v8; // rcx
  unsigned int i; // ecx
  int v10; // edx
  __int64 v11; // r8
  unsigned int v13; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !(unsigned int)IIsSchema::ValidateClassName(this[6], a3) )
    return 2147504142LL;
  v8 = this[6];
  v13 = 0;
  if ( !(unsigned int)IIsSchema::PropNameWToId(v8, a3, &v13) )
    return 2147504142LL;
  for ( i = 0; ; ++i )
  {
    v10 = a3[i];
    if ( (unsigned __int16)(v10 - 48) <= 0x2Fu )
    {
      v11 = 0x87FFFFFE03FFLL;
      if ( _bittest64(&v11, (unsigned int)(v10 - 48)) )
        continue;
    }
    if ( (unsigned __int16)(v10 - 97) > 0x19u )
      break;
  }
  if ( (_WORD)v10 || i >= 0x100 || (unsigned __int16)(*a3 - 48) <= 9u )
    return 2147504136LL;
  if ( !_wcsicmp(a2, L"Class") )
    return CIISClass::CreateClass(
             (const unsigned __int16 *)*(this - 6),
             a3,
             (struct CCredentials *)(this + 7),
             2u,
             &IID_IUnknown,
             (void **)a4);
  if ( _wcsicmp(a2, L"Property") )
    return 2147504136LL;
  else
    return CIISProperty::CreateProperty(
             (const unsigned __int16 *)*(this - 6),
             a3,
             (struct CCredentials *)(this + 7),
             2u,
             &IID_IUnknown,
             (void **)a4);
}

```

## disassembly

```asm
0x180008340  mov     [rsp+arg_0], rbx
0x180008345  mov     [rsp+arg_10], rbp
0x18000834a  push    rsi
0x18000834b  push    rdi
0x18000834c  push    r14
0x18000834e  sub     rsp, 30h
0x180008352  xor     r14d, r14d
0x180008355  mov     rsi, r9
0x180008358  mov     rbx, r8
0x18000835b  mov     rbp, rdx
0x18000835e  mov     rdi, rcx
0x180008361  test    rdx, rdx
0x180008364  jz      loc_18000848A
0x18000836a  test    rbx, rbx
0x18000836d  jz      loc_18000848A
0x180008373  test    r9, r9
0x180008376  jz      loc_18000848A
0x18000837c  mov     [r9], r14
0x18000837f  mov     rdx, rbx; unsigned __int16 *
0x180008382  mov     rcx, [rcx+30h]; this
0x180008386  call    ?ValidateClassName@IIsSchema@@QEAAJPEBG@Z; IIsSchema::ValidateClassName(ushort const *)
0x18000838b  test    eax, eax
0x18000838d  jz      loc_180008483
0x180008393  mov     rcx, [rdi+30h]; this
0x180008397  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x18000839c  mov     rdx, rbx; unsigned __int16 *
0x18000839f  mov     [rsp+48h+arg_8], r14d
0x1800083a4  call    ?PropNameWToId@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::PropNameWToId(ushort const *,ulong *)
0x1800083a9  test    eax, eax
0x1800083ab  jz      loc_180008483
0x1800083b1  mov     ecx, r14d
0x1800083b4  mov     eax, ecx
0x1800083b6  movzx   edx, word ptr [rbx+rax*2]
0x1800083ba  lea     eax, [rdx-30h]
0x1800083bd  cmp     ax, 2Fh ; '/'
0x1800083c1  ja      short loc_1800083D3
0x1800083c3  mov     r8, 87FFFFFE03FFh
0x1800083cd  bt      r8, rax
0x1800083d1  jb      short loc_1800083DC
0x1800083d3  lea     eax, [rdx-61h]
0x1800083d6  cmp     ax, 19h
0x1800083da  ja      short loc_1800083E0
0x1800083dc  inc     ecx
0x1800083de  jmp     short loc_1800083B4
0x1800083e0  test    dx, dx
0x1800083e3  jnz     loc_18000847C
0x1800083e9  cmp     ecx, 100h
0x1800083ef  jnb     loc_18000847C
0x1800083f5  movzx   eax, word ptr [rbx]
0x1800083f8  sub     ax, 30h ; '0'
0x1800083fc  cmp     ax, 9
0x180008400  jbe     short loc_18000847C
0x180008402  lea     rdx, aClass_0; "Class"
0x180008409  mov     rcx, rbp; String1
0x18000840c  call    cs:__imp__wcsicmp
0x180008412  test    eax, eax
0x180008414  jnz     short loc_18000843F
0x180008416  mov     rcx, [rdi-30h]; unsigned __int16 *
0x18000841a  lea     rax, IID_IUnknown
0x180008421  lea     r8, [rdi+38h]; struct CCredentials *
0x180008425  mov     [rsp+48h+var_20], rsi; void **
0x18000842a  mov     r9d, 2; unsigned int
0x180008430  mov     [rsp+48h+var_28], rax; struct _GUID *
0x180008435  mov     rdx, rbx; unsigned __int16 *
0x180008438  call    ?CreateClass@CIISClass@@SAJPEBG0AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z; CIISClass::CreateClass(ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)
0x18000843d  jmp     short loc_18000848F
0x18000843f  lea     rdx, aProperty; "Property"
0x180008446  mov     rcx, rbp; String1
0x180008449  call    cs:__imp__wcsicmp
0x18000844f  test    eax, eax
0x180008451  jnz     short loc_18000847C
0x180008453  mov     rcx, [rdi-30h]; unsigned __int16 *
0x180008457  lea     rax, IID_IUnknown
0x18000845e  lea     r8, [rdi+38h]; struct CCredentials *
0x180008462  mov     [rsp+48h+var_20], rsi; void **
0x180008467  mov     r9d, 2; unsigned int
0x18000846d  mov     [rsp+48h+var_28], rax; struct _GUID *
0x180008472  mov     rdx, rbx; unsigned __int16 *
0x180008475  call    ?CreateProperty@CIISProperty@@SAJPEBG0AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z; CIISProperty::CreateProperty(ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)
0x18000847a  jmp     short loc_18000848F
0x18000847c  mov     eax, 80005008h
0x180008481  jmp     short loc_18000848F
0x180008483  mov     eax, 8000500Eh
0x180008488  jmp     short loc_18000848F
0x18000848a  mov     eax, 80004003h
0x18000848f  mov     rbx, [rsp+48h+arg_0]
0x180008494  mov     rbp, [rsp+48h+arg_10]
0x180008499  add     rsp, 30h
0x18000849d  pop     r14
0x18000849f  pop     rdi
0x1800084a0  pop     rsi
0x1800084a1  retn
```
