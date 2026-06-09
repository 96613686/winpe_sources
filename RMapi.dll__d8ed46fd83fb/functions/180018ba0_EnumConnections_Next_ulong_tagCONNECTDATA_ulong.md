# EnumConnections::Next(ulong,tagCONNECTDATA *,ulong *)

- ea: `0x180018ba0`
- end: `0x180018d4b`
- name: `?Next@EnumConnections@@UEAAJKPEAUtagCONNECTDATA@@PEAK@Z`
- size: `427`
- prototype: `__int64 __fastcall(EnumConnections *__hidden this, unsigned int, struct tagCONNECTDATA *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ec0`
- `0x180006b98`
- `0x18000c2a4`
- `0x1800168b8`
- `0x180018ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c1f`

## string_xrefs

- `0x180018d39`: `onecoreuap\net\mobility\radiomanagement\dll\radioconnectionpoint.cpp`

## pseudocode

```c
__int64 __fastcall EnumConnections::Next(
        EnumConnections *this,
        unsigned int a2,
        struct tagCONNECTDATA *a3,
        unsigned int *a4)
{
  __int64 v5; // rbp
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  char *v10; // rbx
  const char *v11; // r9
  DWORD **v12; // rdi
  DWORD **v13; // rbx
  __int64 v14; // r14
  unsigned int v15; // r12d
  DWORD *v16; // rsi
  __int64 v17; // rdx
  DWORD *v18; // rax
  char *v21; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = a2;
  if ( a4 )
    *a4 = 0;
  if ( a2 )
  {
    if ( a3 && (a2 == 1 || a4) )
    {
      v10 = (char *)this + 16;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v12 = (DWORD **)*((_QWORD *)this + 10);
      v21 = v10;
      v13 = (DWORD **)*((_QWORD *)this + 8);
      if ( (unsigned int)(((char *)v13 - (char *)v12) >> 4) > (unsigned int)v5 )
        v13 = &v12[2 * v5];
      v14 = ((char *)v13 - (char *)v12) >> 4;
      if ( (unsigned int)v14 > (unsigned int)v5 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xE1,
          (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioconnectionpoint.cpp",
          v11);
      v15 = 0;
      while ( v12 < v13 )
      {
        v16 = *v12;
        Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(*v12 + 2);
        v17 = v15++;
        v17 *= 2;
        (&a3->pUnk)[v17] = (IUnknown *)*((_QWORD *)v16 + 1);
        v18 = *v12;
        v12 += 2;
        *(&a3->dwCookie + 2 * v17) = *v18;
      }
      if ( a4 )
        *a4 = v15;
      *((_QWORD *)this + 10) = v13;
      v8 = (unsigned int)v14 < (unsigned int)v5;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          22,
          WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids,
          (unsigned int)v14 < (unsigned int)v5);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      v8 = -2147467261;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v9 = 20;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    v8 = -2147024809;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v9 = 19;
LABEL_25:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v9, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, v8);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180018ba0  mov     [rsp+arg_8], rbx
0x180018ba5  push    rbp
0x180018ba6  push    rsi
0x180018ba7  push    rdi
0x180018ba8  push    r12
0x180018baa  push    r13
0x180018bac  push    r14
0x180018bae  push    r15
0x180018bb0  sub     rsp, 30h
0x180018bb4  mov     [rsp+68h+var_48], r8
0x180018bb9  mov     r15, r9
0x180018bbc  mov     ebp, edx
0x180018bbe  mov     r13, rcx
0x180018bc1  test    r9, r9
0x180018bc4  jz      short loc_180018BCD
0x180018bc6  mov     dword ptr [r9], 0
0x180018bcd  test    edx, edx
0x180018bcf  jnz     short loc_180018C01
0x180018bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bd8  lea     rax, WPP_GLOBAL_Control
0x180018bdf  mov     ebx, 80070057h
0x180018be4  cmp     rcx, rax
0x180018be7  jz      loc_180018D1D
0x180018bed  test    byte ptr [rcx+1Ch], 4
0x180018bf1  jz      loc_180018D1D
0x180018bf7  mov     edx, 13h
0x180018bfc  jmp     loc_180018D0A
0x180018c01  test    r8, r8
0x180018c04  jz      loc_180018CE7
0x180018c0a  cmp     ebp, 1
0x180018c0d  jz      short loc_180018C18
0x180018c0f  test    r15, r15
0x180018c12  jz      loc_180018CE7
0x180018c18  lea     rbx, [rcx+10h]
0x180018c1c  mov     rcx, rbx; lpCriticalSection
0x180018c1f  call    cs:__imp_EnterCriticalSection
0x180018c25  mov     rdi, [r13+50h]
0x180018c29  mov     [rsp+68h+var_40], rbx
0x180018c2e  mov     rbx, [r13+40h]
0x180018c32  mov     rax, rbx
0x180018c35  sub     rax, rdi
0x180018c38  sar     rax, 4
0x180018c3c  cmp     eax, ebp
0x180018c3e  jbe     short loc_180018C4A
0x180018c40  mov     rbx, rbp
0x180018c43  shl     rbx, 4
0x180018c47  add     rbx, rdi
0x180018c4a  mov     r14, rbx
0x180018c4d  sub     r14, rdi
0x180018c50  sar     r14, 4
0x180018c54  cmp     r14d, ebp
0x180018c57  ja      loc_180018D34
0x180018c5d  xor     r12d, r12d
0x180018c60  cmp     rdi, rbx
0x180018c63  jnb     short loc_180018C96
0x180018c65  mov     rsi, [rdi]
0x180018c68  lea     rcx, [rsi+8]
0x180018c6c  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x180018c71  mov     rax, [rsi+8]
0x180018c75  mov     rsi, [rsp+68h+var_48]
0x180018c7a  mov     edx, r12d
0x180018c7d  inc     r12d
0x180018c80  add     rdx, rdx
0x180018c83  mov     [rsi+rdx*8], rax
0x180018c87  mov     rax, [rdi]
0x180018c8a  add     rdi, 10h
0x180018c8e  mov     ecx, [rax]
0x180018c90  mov     [rsi+rdx*8+8], ecx
0x180018c94  jmp     short loc_180018C60
0x180018c96  test    r15, r15
0x180018c99  jz      short loc_180018C9E
0x180018c9b  mov     [r15], r12d
0x180018c9e  mov     [r13+50h], rbx
0x180018ca2  xor     ebx, ebx
0x180018ca4  cmp     r14d, ebp
0x180018ca7  setb    bl
0x180018caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cb1  lea     rax, WPP_GLOBAL_Control
0x180018cb8  cmp     rcx, rax
0x180018cbb  jz      short loc_180018CDB
0x180018cbd  test    byte ptr [rcx+1Ch], 4
0x180018cc1  jz      short loc_180018CDB
0x180018cc3  mov     rcx, [rcx+10h]
0x180018cc7  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x180018cce  mov     edx, 16h
0x180018cd3  mov     r9d, ebx
0x180018cd6  call    WPP_SF_d
0x180018cdb  lea     rcx, [rsp+68h+var_40]
0x180018ce0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180018ce5  jmp     short loc_180018D1D
0x180018ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cee  lea     rax, WPP_GLOBAL_Control
0x180018cf5  mov     ebx, 80004003h
0x180018cfa  cmp     rcx, rax
0x180018cfd  jz      short loc_180018D1D
0x180018cff  test    byte ptr [rcx+1Ch], 4
0x180018d03  jz      short loc_180018D1D
0x180018d05  mov     edx, 14h
0x180018d0a  mov     rcx, [rcx+10h]
0x180018d0e  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x180018d15  mov     r9d, ebx
0x180018d18  call    WPP_SF_d
0x180018d1d  mov     eax, ebx
0x180018d1f  mov     rbx, [rsp+68h+arg_8]
0x180018d24  add     rsp, 30h
0x180018d28  pop     r15
0x180018d2a  pop     r14
0x180018d2c  pop     r13
0x180018d2e  pop     r12
0x180018d30  pop     rdi
0x180018d31  pop     rsi
0x180018d32  pop     rbp
0x180018d33  retn
0x180018d34  mov     rcx, [rsp+68h]; this
0x180018d39  lea     r8, aOnecoreuapNetM_1; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180018d40  mov     edx, 0E1h; void *
0x180018d45  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
