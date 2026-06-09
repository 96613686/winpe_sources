# UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::DeleteRange(int,int)

- ea: `0x18000fa5c`
- end: `0x18000fb08`
- name: `?DeleteRange@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@AEAAXHH@Z`
- size: `172`
- prototype: `void __fastcall(__int64, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ddf0`
- `0x18000eb54`
- `0x180012390`

## callees

- `0x18000fa5c`
- `0x1800107cc`
- `0x180036010`

## import_xrefs

- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000faab`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000fae3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000faab`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000fae3`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000faec`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000faec`

## pseudocode

```c
void __fastcall UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::DeleteRange(__int64 a1, int a2, int a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  _BYTE v12[16]; // [rsp+28h] [rbp-30h] BYREF
  _BYTE v13[32]; // [rsp+38h] [rbp-20h] BYREF

  if ( a2 <= a3 )
  {
    v4 = a2;
    do
    {
      v6 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, v4);
      v8 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v12, v7);
      if ( !(unsigned int)UnBCL::MP::SmartPtrNull<UnBCL::SmartPtr<UnBCL::String>>::IsNull(v8) )
      {
        v9 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, v4);
        v11 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v13, v10);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v11);
      }
      ++v4;
    }
    while ( (int)v4 <= a3 );
  }
}

```

## disassembly

```asm
0x18000fa5c  cmp     edx, r8d
0x18000fa5f  jg      locret_18000FB07
0x18000fa65  mov     [rsp+arg_0], rbx
0x18000fa6a  mov     [rsp+arg_8], rsi
0x18000fa6f  push    rdi
0x18000fa70  sub     rsp, 50h
0x18000fa74  mov     edi, r8d
0x18000fa77  mov     ebx, edx
0x18000fa79  mov     rsi, rcx
0x18000fa7c  lea     rax, [rsp+58h+var_30]
0x18000fa81  mov     [rsp+58h+arg_18], rax
0x18000fa86  mov     rax, [rsi+8]
0x18000fa8a  movsxd  rcx, dword ptr [rax+10h]
0x18000fa8e  add     rcx, 8
0x18000fa92  add     rcx, rsi
0x18000fa95  mov     rax, [rcx]
0x18000fa98  mov     edx, ebx
0x18000fa9a  mov     rax, [rax+18h]
0x18000fa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faa3  mov     rdx, rax
0x18000faa6  lea     rcx, [rsp+58h+var_30]
0x18000faab  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000fab1  nop
0x18000fab2  mov     rcx, rax
0x18000fab5  call    ?IsNull@?$SmartPtrNull@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@MP@UnBCL@@SAHV?$SmartPtr@VString@UnBCL@@@3@@Z; UnBCL::MP::SmartPtrNull<UnBCL::SmartPtr<UnBCL::String>>::IsNull(UnBCL::SmartPtr<UnBCL::String>)
0x18000faba  test    eax, eax
0x18000fabc  jnz     short loc_18000FAF2
0x18000fabe  mov     rax, [rsi+8]
0x18000fac2  movsxd  rcx, dword ptr [rax+10h]
0x18000fac6  add     rcx, 8
0x18000faca  add     rcx, rsi
0x18000facd  mov     rax, [rcx]
0x18000fad0  mov     edx, ebx
0x18000fad2  mov     rax, [rax+18h]
0x18000fad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fadb  mov     rdx, rax
0x18000fade  lea     rcx, [rsp+58h+var_20]
0x18000fae3  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000fae9  mov     rcx, rax
0x18000faec  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18000faf2  inc     ebx
0x18000faf4  cmp     ebx, edi
0x18000faf6  jle     short loc_18000FA7C
0x18000faf8  mov     rbx, [rsp+58h+arg_0]
0x18000fafd  mov     rsi, [rsp+58h+arg_8]
0x18000fb02  add     rsp, 50h
0x18000fb06  pop     rdi
0x18000fb07  retn
```
