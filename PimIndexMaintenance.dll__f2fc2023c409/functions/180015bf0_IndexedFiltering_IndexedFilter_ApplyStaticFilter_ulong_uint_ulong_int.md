# IndexedFiltering::IndexedFilter::_ApplyStaticFilter(ulong,uint *,ulong *,int *)

- ea: `0x180015bf0`
- end: `0x180015e01`
- name: `?_ApplyStaticFilter@IndexedFilter@IndexedFiltering@@AEAAJKPEAIPEAKPEAH@Z`
- size: `529`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexedFilter *this, __int64, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015374`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x18000502c`
- `0x18000d510`
- `0x1800157c0`
- `0x180015800`
- `0x180015bf0`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x180015c69`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexedfilter.cpp`
- `0x180015d0b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexedfilter.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexedFilter::_ApplyStaticFilter(
        IndexedFiltering::IndexedFilter *this,
        __int64 a2,
        unsigned int *a3,
        unsigned int *a4,
        int *a5)
{
  unsigned int v7; // r15d
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  struct IUnknown *v14; // rdx
  struct IUnknown *v15; // rdx
  int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // r8
  int v19; // eax
  struct IUnknown *v21; // [rsp+30h] [rbp-30h] BYREF
  int v22; // [rsp+38h] [rbp-28h] BYREF
  __int64 v23; // [rsp+40h] [rbp-20h] BYREF
  int v24; // [rsp+48h] [rbp-18h]

  v22 = 1;
  v23 = 0;
  v7 = a2;
  v24 = 0;
  *a5 = 0;
  if ( !*((_QWORD *)this + 17) )
  {
    v9 = 0;
    goto LABEL_16;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 10) + 32LL))(
          *((_QWORD *)this + 10),
          a2,
          &v23);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v14 = (struct IUnknown *)*((_QWORD *)this + 10);
    v21 = 0;
    if ( !v14 || (ATL::AtlComQIPtrAssign(&v21, v14, &GUID_a1284db2_4c99_4ea0_9c38_4407285744b8), (v15 = v21) == 0) )
    {
      v15 = (struct IUnknown *)*((_QWORD *)this + 11);
      if ( !v15 || (ATL::AtlComPtrAssign(&v21, v15), (v15 = v21) == 0) )
      {
        Log_AssertionEvent_2(v11, v15, 668);
        v15 = v21;
      }
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, __int64 *, int *))(**((_QWORD **)this + 17) + 24LL))(
            *((_QWORD *)this + 17),
            v15,
            &v23,
            &v22);
    v9 = v16;
    if ( v16 == -2147023728 || v16 == -2147024871 )
    {
      if ( a3 )
        *a3 = 0;
      v9 = 0;
    }
    else
    {
      if ( v16 >= 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
        if ( !v22 )
          return v9;
LABEL_16:
        *a4 = v7;
        *a5 = 1;
        if ( !*((_DWORD *)this + 43) )
          return v9;
        v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), v7);
        if ( v17 != 1 )
        {
          ++*((_DWORD *)this + 9);
          if ( a3 )
          {
            v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 5) + 56LL))(
                    *((_QWORD *)this + 5),
                    v7,
                    a3);
            v9 = v19;
            if ( v19 < 0 )
            {
              Log_HREvent_3((unsigned int)v19, 1, v18, 718);
              v17 = v9;
LABEL_23:
              v12 = 694;
              v13 = v17;
              goto LABEL_5;
            }
          }
          if ( (v17 & 0x80000000) != 0 )
          {
            Log_HREvent_3(v17, 1, v18, 722);
            v9 = v17;
            goto LABEL_23;
          }
        }
        return v17;
      }
      Log_HREvent(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexedfilter.cpp",
        681);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
    return v9;
  }
  v12 = 656;
  v13 = (unsigned int)v10;
LABEL_5:
  Log_HREvent(
    v13,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexedfilter.cpp",
    v12);
  return v9;
}

```

## disassembly

```asm
0x180015bf0  push    rbp
0x180015bf2  push    rbx
0x180015bf3  push    rsi
0x180015bf4  push    rdi
0x180015bf5  push    r12
0x180015bf7  push    r14
0x180015bf9  push    r15
0x180015bfb  mov     rbp, rsp
0x180015bfe  sub     rsp, 60h
0x180015c02  mov     rax, cs:__security_cookie
0x180015c09  xor     rax, rsp
0x180015c0c  mov     [rbp+var_10], rax
0x180015c10  mov     rdi, [rbp+arg_20]
0x180015c14  xor     eax, eax
0x180015c16  mov     r12, r9
0x180015c19  mov     [rbp+var_28], 1
0x180015c20  mov     r14, r8
0x180015c23  mov     [rbp+var_20], rax
0x180015c27  mov     r15d, edx
0x180015c2a  mov     [rbp+var_18], eax
0x180015c2d  mov     [rdi], eax
0x180015c2f  mov     rsi, rcx
0x180015c32  cmp     [rcx+88h], rax
0x180015c39  jnz     short loc_180015C42
0x180015c3b  xor     ebx, ebx
0x180015c3d  jmp     loc_180015D36
0x180015c42  mov     rcx, [rcx+50h]
0x180015c46  lea     r8, [rbp+var_20]
0x180015c4a  mov     rax, [rcx]
0x180015c4d  mov     rax, [rax+20h]
0x180015c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c56  mov     ebx, eax
0x180015c58  test    eax, eax
0x180015c5a  jns     short loc_180015C7A
0x180015c5c  mov     r9d, 290h
0x180015c62  mov     edx, 1
0x180015c67  mov     ecx, eax
0x180015c69  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180015c70  call    Log_HREvent
0x180015c75  jmp     loc_180015DE4
0x180015c7a  mov     rdx, [rsi+50h]; struct IUnknown *
0x180015c7e  mov     [rbp+var_30], 0
0x180015c86  test    rdx, rdx
0x180015c89  jz      short loc_180015CA4
0x180015c8b  lea     r8, _GUID_a1284db2_4c99_4ea0_9c38_4407285744b8; struct _GUID *
0x180015c92  lea     rcx, [rbp+var_30]; struct IUnknown **
0x180015c96  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180015c9b  mov     rdx, [rbp+var_30]
0x180015c9f  test    rdx, rdx
0x180015ca2  jnz     short loc_180015CCE
0x180015ca4  mov     rdx, [rsi+58h]; struct IUnknown *
0x180015ca8  test    rdx, rdx
0x180015cab  jz      short loc_180015CBF
0x180015cad  lea     rcx, [rbp+var_30]; struct IUnknown **
0x180015cb1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180015cb6  mov     rdx, [rbp+var_30]
0x180015cba  test    rdx, rdx
0x180015cbd  jnz     short loc_180015CCE
0x180015cbf  mov     r8d, 29Ch
0x180015cc5  call    Log_AssertionEvent_2
0x180015cca  mov     rdx, [rbp+var_30]
0x180015cce  mov     rcx, [rsi+88h]
0x180015cd5  lea     r9, [rbp+var_28]
0x180015cd9  lea     r8, [rbp+var_20]
0x180015cdd  mov     rax, [rcx]
0x180015ce0  mov     rax, [rax+18h]
0x180015ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce9  mov     ebx, eax
0x180015ceb  cmp     eax, 80070490h
0x180015cf0  jz      loc_180015DCD
0x180015cf6  cmp     eax, 80070019h
0x180015cfb  jz      loc_180015DCD
0x180015d01  test    eax, eax
0x180015d03  jns     short loc_180015D23
0x180015d05  mov     r9d, 2A9h
0x180015d0b  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180015d12  mov     edx, 1
0x180015d17  mov     ecx, eax
0x180015d19  call    Log_HREvent
0x180015d1e  jmp     loc_180015DDB
0x180015d23  lea     rcx, [rbp+var_30]
0x180015d27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015d2c  cmp     [rbp+var_28], 0
0x180015d30  jz      loc_180015DE4
0x180015d36  mov     [r12], r15d
0x180015d3a  mov     r12d, 1
0x180015d40  mov     [rdi], r12d
0x180015d43  cmp     dword ptr [rsi+0ACh], 0
0x180015d4a  jz      loc_180015DE4
0x180015d50  mov     rcx, [rsi+28h]
0x180015d54  mov     edx, r15d
0x180015d57  mov     rax, [rcx]
0x180015d5a  mov     rax, [rax+18h]
0x180015d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d63  mov     edi, eax
0x180015d65  cmp     eax, r12d
0x180015d68  jz      short loc_180015DC9
0x180015d6a  add     [rsi+24h], r12d
0x180015d6e  test    r14, r14
0x180015d71  jz      short loc_180015DA3
0x180015d73  mov     rcx, [rsi+28h]
0x180015d77  mov     r8, r14
0x180015d7a  mov     edx, r15d
0x180015d7d  mov     rax, [rcx]
0x180015d80  mov     rax, [rax+38h]
0x180015d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d89  mov     ebx, eax
0x180015d8b  test    eax, eax
0x180015d8d  jns     short loc_180015DA3
0x180015d8f  mov     r9d, 2CEh
0x180015d95  mov     edx, r12d
0x180015d98  mov     ecx, eax
0x180015d9a  call    Log_HREvent_3
0x180015d9f  mov     edi, ebx
0x180015da1  jmp     short loc_180015DB9
0x180015da3  test    edi, edi
0x180015da5  jns     short loc_180015DC9
0x180015da7  mov     r9d, 2D2h
0x180015dad  mov     edx, r12d
0x180015db0  mov     ecx, edi
0x180015db2  call    Log_HREvent_3
0x180015db7  mov     ebx, edi
0x180015db9  mov     r9d, 2B6h
0x180015dbf  mov     edx, r12d
0x180015dc2  mov     ecx, edi
0x180015dc4  jmp     loc_180015C69
0x180015dc9  mov     ebx, edi
0x180015dcb  jmp     short loc_180015DE4
0x180015dcd  test    r14, r14
0x180015dd0  jz      short loc_180015DD9
0x180015dd2  mov     dword ptr [r14], 0
0x180015dd9  xor     ebx, ebx
0x180015ddb  lea     rcx, [rbp+var_30]
0x180015ddf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015de4  mov     eax, ebx
0x180015de6  mov     rcx, [rbp+var_10]
0x180015dea  xor     rcx, rsp; StackCookie
0x180015ded  call    __security_check_cookie
0x180015df2  add     rsp, 60h
0x180015df6  pop     r15
0x180015df8  pop     r14
0x180015dfa  pop     r12
0x180015dfc  pop     rdi
0x180015dfd  pop     rsi
0x180015dfe  pop     rbx
0x180015dff  pop     rbp
0x180015e00  retn
```
