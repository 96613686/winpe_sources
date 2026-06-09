# ATL::CComCreator<ATL::CComAggObject<CIdentityStore>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e9fc`
- end: `0x18000eaff`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCIdentityStore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005fb0`

## callees

- `0x180006230`
- `0x180006260`
- `0x18000e9fc`
- `0x18000f088`
- `0x1800106f8`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CIdentityStore>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  void *v8; // rax
  __int64 v9; // rbx
  int v10; // ecx
  int v11; // eax
  __int64 v12; // [rsp+20h] [rbp-28h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0xA8u);
    if ( v8 )
      v9 = ATL::CComAggObject<CIdentityStore>::CComAggObject<CIdentityStore>((__int64)v8, a1);
    else
      v9 = 0;
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 56));
    if ( v10 >= 0 )
      *(_BYTE *)(v9 + 96) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
    {
      *(_QWORD *)(v9 + 160) = 0;
      v11 = CIdentityProviderReg::Initialize((CIdentityProviderReg *)(v9 + 112));
    }
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18000e9fc  mov     [rsp+arg_0], rbx
0x18000ea01  mov     [rsp+arg_10], r8
0x18000ea06  mov     [rsp+arg_8], rdx
0x18000ea0b  push    rsi
0x18000ea0c  push    rdi
0x18000ea0d  push    r14
0x18000ea0f  sub     rsp, 30h
0x18000ea13  mov     rsi, r8
0x18000ea16  mov     r14, rdx
0x18000ea19  mov     rbx, rcx
0x18000ea1c  test    r8, r8
0x18000ea1f  jnz     short loc_18000EA2B
0x18000ea21  mov     eax, 80004003h
0x18000ea26  jmp     loc_18000EAF1
0x18000ea2b  mov     qword ptr [r8], 0
0x18000ea32  mov     edi, 8007000Eh
0x18000ea37  mov     [rsp+48h+arg_18], edi
0x18000ea3b  mov     [rsp+48h+var_28], 0
0x18000ea44  mov     ecx, 0A8h; Size
0x18000ea49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ea4e  test    rax, rax
0x18000ea51  jz      short loc_18000EA63
0x18000ea53  mov     rdx, rbx
0x18000ea56  mov     rcx, rax
0x18000ea59  call    ??0?$CComAggObject@VCIdentityStore@@@ATL@@QEAA@PEAX@Z; ATL::CComAggObject<CIdentityStore>::CComAggObject<CIdentityStore>(void *)
0x18000ea5e  mov     rbx, rax
0x18000ea61  jmp     short loc_18000EA65
0x18000ea63  xor     ebx, ebx
0x18000ea65  mov     [rsp+48h+var_28], rbx
0x18000ea6a  jmp     short loc_18000EA7F
0x18000ea6c  mov     rsi, [rsp+48h+arg_10]
0x18000ea71  mov     r14, [rsp+48h+arg_8]
0x18000ea76  mov     edi, [rsp+48h+arg_18]
0x18000ea7a  mov     rbx, [rsp+48h+var_28]
0x18000ea7f  test    rbx, rbx
0x18000ea82  jz      short loc_18000EAEF
0x18000ea84  lea     rcx, [rbx+38h]; this
0x18000ea88  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ea8d  mov     ecx, eax
0x18000ea8f  test    eax, eax
0x18000ea91  js      short loc_18000EA97
0x18000ea93  mov     byte ptr [rbx+60h], 1
0x18000ea97  xor     eax, eax
0x18000ea99  test    ecx, ecx
0x18000ea9b  cmovs   eax, ecx
0x18000ea9e  test    eax, eax
0x18000eaa0  js      short loc_18000EAB6
0x18000eaa2  mov     qword ptr [rbx+0A0h], 0
0x18000eaad  lea     rcx, [rbx+70h]; this
0x18000eab1  call    ?Initialize@CIdentityProviderReg@@QEAAJXZ; CIdentityProviderReg::Initialize(void)
0x18000eab6  xor     edi, edi
0x18000eab8  test    eax, eax
0x18000eaba  cmovs   edi, eax
0x18000eabd  test    edi, edi
0x18000eabf  jnz     short loc_18000EADB
0x18000eac1  mov     rax, [rbx]
0x18000eac4  mov     r8, rsi
0x18000eac7  mov     rdx, r14
0x18000eaca  mov     rcx, rbx
0x18000eacd  mov     rax, [rax]
0x18000ead0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ead5  mov     edi, eax
0x18000ead7  test    eax, eax
0x18000ead9  jz      short loc_18000EAEF
0x18000eadb  mov     r8, [rbx]
0x18000eade  mov     edx, 1
0x18000eae3  mov     rcx, rbx
0x18000eae6  mov     rax, [r8+18h]
0x18000eaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaef  mov     eax, edi
0x18000eaf1  mov     rbx, [rsp+48h+arg_0]
0x18000eaf6  add     rsp, 30h
0x18000eafa  pop     r14
0x18000eafc  pop     rdi
0x18000eafd  pop     rsi
0x18000eafe  retn
```
