# UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::BinarySearch(int,int,UnBCL::SmartPtr<UnBCL::String>,UnBCL::IComparer<UnBCL::SmartPtr<UnBCL::String>> *)

- ea: `0x18000e760`
- end: `0x18000e9d0`
- name: `?BinarySearch@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@AEAAHHHV?$SmartPtr@VString@UnBCL@@@2@PEAU?$IComparer@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64 (__fastcall ***)(_QWORD, __int64, __int64))`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000e9e0`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000e760`
- `0x18000ed8c`
- `0x180036010`

## import_xrefs

- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e7f4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e828`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e849`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e87d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e89e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e7f4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e828`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e849`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e87d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x18000e89e`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000e996`
- `unbcl!??0ArgumentException@UnBCL@@QEAA@PEBG@Z` at `0x18000e996`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000e93a`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000e93a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000e91d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000e979`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000e91d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000e979`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e8bd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e8c7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e8fe`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e90e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e8bd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e8c7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e8fe`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000e90e`

## string_xrefs

- `0x18000e94e`: `int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)`
- `0x18000e9aa`: `int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)`

## pseudocode

```c
__int64 __fastcall UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::BinarySearch(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 (__fastcall ***a5)(_QWORD, __int64, __int64))
{
  int (__fastcall ***v8)(_QWORD); // rcx
  signed int v9; // esi
  int v10; // r12d
  unsigned int v11; // r15d
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(_QWORD, __int64, __int64); // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  UnBCL::ArgumentOutOfRangeException *v21; // rax
  UnBCL::Exception *v22; // rbx
  UnBCL::ArgumentException *v23; // rax
  UnBCL::Exception *v24; // rbx
  UnBCL::InvalidOperationException *v25; // rbx
  UnBCL::String *v26; // rax
  const struct UnBCL::String *v27; // rdi
  UnBCL::InvalidOperationException *v28; // rax
  UnBCL::Exception *v29; // rbx
  _BYTE v30[16]; // [rsp+28h] [rbp-C0h] BYREF
  int v31; // [rsp+38h] [rbp-B0h]
  UnBCL::Exception *v32; // [rsp+40h] [rbp-A8h] BYREF
  UnBCL::Exception *v33; // [rsp+48h] [rbp-A0h] BYREF
  UnBCL::Exception *v34; // [rsp+50h] [rbp-98h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+58h] [rbp-90h] BYREF
  UnBCL::ArgumentException *v36; // [rsp+60h] [rbp-88h]
  UnBCL::String *v37; // [rsp+68h] [rbp-80h]
  _BYTE *v38; // [rsp+70h] [rbp-78h]
  struct UnBCL::Exception *v39; // [rsp+78h] [rbp-70h] BYREF
  _BYTE v40[16]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v41[16]; // [rsp+90h] [rbp-58h] BYREF
  _BYTE v42[16]; // [rsp+A0h] [rbp-48h] BYREF
  _BYTE v43[16]; // [rsp+B0h] [rbp-38h] BYREF

  if ( a3 < 0 )
  {
    v21 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v22 = v21;
    if ( v21 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(
        v21,
        L"negative index or count to ArrayList#BinarySearch");
      *(_QWORD *)v22 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v22 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v22,
                         "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int"
                         ",class UnBCL::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class"
                         " UnBCL::String> > *)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  v8 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
  if ( (**v8)(v8) < a3 )
  {
    v23 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v24 = v23;
    v36 = v23;
    if ( v23 )
    {
      UnBCL::ArgumentException::ArgumentException(
        v23,
        L"index and count do not denote a valid range of elements in ArrayList#BinarySearch");
      *(_QWORD *)v24 = &UnBCL::ArgumentException::`local vftable';
    }
    else
    {
      v24 = 0;
    }
    v32 = AddStackTraceToException<SetupCleanupTaskException>(
            v24,
            "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBCL:"
            ":SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)");
    throw (UnBCL::ArgumentException **)&v32;
  }
  v9 = 0;
  v10 = a3 - 1;
  while ( v9 <= v10 )
  {
    v11 = (v10 + v9) / 2;
    v12 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, v11);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v30, v13);
    try
    {
      if ( a5 )
      {
        v14 = **a5;
        v36 = (UnBCL::ArgumentException *)v40;
        v15 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v40, v30);
        v38 = v41;
        v16 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v41, a4);
        v17 = v14(a5, v16, v15);
      }
      else
      {
        v37 = (UnBCL::String *)v42;
        v18 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v42, v30);
        v19 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v43, a4);
        v17 = UnBCL::MP::ObjectSmartPtrCompare<UnBCL::SmartPtr<UnBCL::String>>::Compare(v19, v18);
      }
      v31 = v17;
    }
    catch ( UnBCL::Exception *v39 )
    {
      v25 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      if ( v25 )
      {
        v26 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v27 = v26;
        v37 = v26;
        if ( v26 )
        {
          UnBCL::String::String(v26, L"Compare failed -- bad comparison routines?");
          *(_QWORD *)v27 = &UnBCL::String::`local vftable';
        }
        else
        {
          v27 = 0;
        }
        UnBCL::InvalidOperationException::InvalidOperationException(v25, v27, v39);
        *(_QWORD *)v25 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v25 = 0;
      }
      v33 = AddStackTraceToException<SetupCleanupTaskException>(
              v25,
              "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBC"
              "L::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)");
      throw (UnBCL::InvalidOperationException **)&v33;
    }
    catch ( ... )
    {
      v28 = (UnBCL::InvalidOperationException *)UnBCL::Object::operator new(0x38u);
      v29 = v28;
      if ( v28 )
      {
        UnBCL::InvalidOperationException::InvalidOperationException(v28, L"sort failed -- bad comparison routines?");
        *(_QWORD *)v29 = &UnBCL::InvalidOperationException::`local vftable';
      }
      else
      {
        v29 = 0;
      }
      v34 = AddStackTraceToException<SetupCleanupTaskException>(
              v29,
              "int __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::BinarySearch(int,int,class UnBC"
              "L::SmartPtr<class UnBCL::String>,struct UnBCL::IComparer<class UnBCL::SmartPtr<class UnBCL::String> > *)");
      throw (UnBCL::InvalidOperationException **)&v34;
    }
    if ( !v17 )
    {
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v30);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a4);
      return v11;
    }
    if ( v17 >= 0 )
      v9 = v11 + 1;
    else
      v10 = v11 - 1;
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v30);
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a4);
  return (unsigned int)~v9;
}

```

## disassembly

```asm
0x18000e760  mov     [rsp+arg_0], rbx
0x18000e765  mov     [rsp+arg_8], rsi
0x18000e76a  mov     [rsp+arg_18], r9
0x18000e76f  push    rdi
0x18000e770  push    r12
0x18000e772  push    r13
0x18000e774  push    r14
0x18000e776  push    r15
0x18000e778  sub     rsp, 0C0h
0x18000e77f  mov     r14, r9
0x18000e782  mov     ebx, r8d
0x18000e785  mov     r13, rcx
0x18000e788  test    r8d, r8d
0x18000e78b  js      loc_18000E918
0x18000e791  mov     rax, [rcx+8]
0x18000e795  movsxd  rcx, dword ptr [rax+0Ch]
0x18000e799  add     rcx, 8
0x18000e79d  add     rcx, r13
0x18000e7a0  mov     rax, [rcx]
0x18000e7a3  mov     rax, [rax]
0x18000e7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ab  cmp     eax, ebx
0x18000e7ad  jl      loc_18000E974
0x18000e7b3  xor     esi, esi
0x18000e7b5  lea     r12d, [rbx-1]
0x18000e7b9  cmp     esi, r12d
0x18000e7bc  jg      loc_18000E909
0x18000e7c2  lea     eax, [r12+rsi]
0x18000e7c6  cdq
0x18000e7c7  sub     eax, edx
0x18000e7c9  sar     eax, 1
0x18000e7cb  mov     r15d, eax
0x18000e7ce  mov     rcx, [r13+8]
0x18000e7d2  movsxd  rcx, dword ptr [rcx+10h]
0x18000e7d6  add     rcx, 8
0x18000e7da  add     rcx, r13
0x18000e7dd  mov     rdx, [rcx]
0x18000e7e0  mov     rax, [rdx+18h]
0x18000e7e4  mov     edx, r15d
0x18000e7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ec  mov     rdx, rax
0x18000e7ef  lea     rcx, [rsp+0E8h+var_C0]
0x18000e7f4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000e7fa  nop
0x18000e7fb  mov     rax, [rsp+0E8h+arg_20]
0x18000e803  lea     rdx, [rsp+0E8h+var_C0]
0x18000e808  test    rax, rax
0x18000e80b  jz      short loc_18000E868
0x18000e80d  mov     rax, [rax]
0x18000e810  mov     rdi, [rax]
0x18000e813  lea     rax, [rsp+0E8h+var_68]
0x18000e81b  mov     [rsp+0E8h+var_88], rax
0x18000e820  lea     rcx, [rsp+0E8h+var_68]
0x18000e828  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000e82e  mov     rbx, rax
0x18000e831  lea     rax, [rsp+0E8h+var_58]
0x18000e839  mov     [rsp+0E8h+var_78], rax
0x18000e83e  mov     rdx, r14
0x18000e841  lea     rcx, [rsp+0E8h+var_58]
0x18000e849  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000e84f  nop
0x18000e850  mov     r8, rbx
0x18000e853  mov     rdx, rax
0x18000e856  mov     rcx, [rsp+0E8h+arg_20]
0x18000e85e  mov     rax, rdi
0x18000e861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e866  jmp     short loc_18000E8B0
0x18000e868  lea     rax, [rsp+0E8h+var_48]
0x18000e870  mov     [rsp+0E8h+var_80], rax
0x18000e875  lea     rcx, [rsp+0E8h+var_48]
0x18000e87d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000e883  mov     rbx, rax
0x18000e886  lea     rax, [rsp+0E8h+var_38]
0x18000e88e  mov     [rsp+0E8h+var_C8], rax
0x18000e893  mov     rdx, r14
0x18000e896  lea     rcx, [rsp+0E8h+var_38]
0x18000e89e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000e8a4  nop
0x18000e8a5  mov     rdx, rbx
0x18000e8a8  mov     rcx, rax
0x18000e8ab  call    ?Compare@?$ObjectSmartPtrCompare@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@MP@UnBCL@@SAHV?$SmartPtr@VString@UnBCL@@@3@0@Z; UnBCL::MP::ObjectSmartPtrCompare<UnBCL::SmartPtr<UnBCL::String>>::Compare(UnBCL::SmartPtr<UnBCL::String>,UnBCL::SmartPtr<UnBCL::String>)
0x18000e8b0  mov     [rsp+0E8h+var_B0], eax
0x18000e8b4  test    eax, eax
0x18000e8b6  jnz     short loc_18000E8ED
0x18000e8b8  lea     rcx, [rsp+0E8h+var_C0]
0x18000e8bd  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18000e8c3  nop
0x18000e8c4  mov     rcx, r14
0x18000e8c7  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18000e8cd  mov     eax, r15d
0x18000e8d0  lea     r11, [rsp+0E8h+var_28]
0x18000e8d8  mov     rbx, [r11+30h]
0x18000e8dc  mov     rsi, [r11+38h]
0x18000e8e0  mov     rsp, r11
0x18000e8e3  pop     r15
0x18000e8e5  pop     r14
0x18000e8e7  pop     r13
0x18000e8e9  pop     r12
0x18000e8eb  pop     rdi
0x18000e8ec  retn
0x18000e8ed  jns     short loc_18000E8F5
0x18000e8ef  lea     r12d, [r15-1]
0x18000e8f3  jmp     short loc_18000E8F9
0x18000e8f5  lea     esi, [r15+1]
0x18000e8f9  lea     rcx, [rsp+0E8h+var_C0]
0x18000e8fe  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18000e904  jmp     loc_18000E7B9
0x18000e909  not     esi
0x18000e90b  mov     rcx, r14
0x18000e90e  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18000e914  mov     eax, esi
0x18000e916  jmp     short loc_18000E8D0
0x18000e918  mov     ecx, 38h ; '8'
0x18000e91d  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000e923  mov     rbx, rax
0x18000e926  mov     [rsp+0E8h+var_C8], rax
0x18000e92b  test    rax, rax
0x18000e92e  jz      short loc_18000E94C
0x18000e930  lea     rdx, aNegativeIndexO; "negative index or count to ArrayList#Bi"...
0x18000e937  mov     rcx, rax
0x18000e93a  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18000e940  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18000e947  mov     [rbx], rax
0x18000e94a  jmp     short loc_18000E94E
0x18000e94c  xor     ebx, ebx
0x18000e94e  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x18000e955  mov     rcx, rbx
0x18000e958  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000e95d  mov     [rsp+0E8h+pExceptionObject], rax
0x18000e962  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18000e969  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18000e96e  call    _CxxThrowException_0
0x18000e974  mov     ecx, 38h ; '8'
0x18000e979  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000e97f  mov     rbx, rax
0x18000e982  mov     [rsp+0E8h+var_88], rax
0x18000e987  test    rax, rax
0x18000e98a  jz      short loc_18000E9A8
0x18000e98c  lea     rdx, aIndexAndCountD; "index and count do not denote a valid r"...
0x18000e993  mov     rcx, rax
0x18000e996  call    cs:__imp_??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18000e99c  lea     rax, ??_SArgumentException@UnBCL@@6B@; const UnBCL::ArgumentException::`local vftable'
0x18000e9a3  mov     [rbx], rax
0x18000e9a6  jmp     short loc_18000E9AA
0x18000e9a8  xor     ebx, ebx
0x18000e9aa  lea     rdx, aIntCdeclUnbclA_2; "int __cdecl UnBCL::ArrayList<class UnBC"...
0x18000e9b1  mov     rcx, rbx
0x18000e9b4  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000e9b9  mov     [rsp+0E8h+var_A8], rax
0x18000e9be  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18000e9c5  lea     rcx, [rsp+0E8h+var_A8]; pExceptionObject
0x18000e9ca  call    _CxxThrowException_0
```
