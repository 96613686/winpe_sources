# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180015efc`
- end: `0x180016288`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800152f8`

## callees

- `0x180003d50`
- `0x180004180`
- `0x1800041a4`
- `0x180004ff4`
- `0x1800050fc`
- `0x180005114`
- `0x18000512c`
- `0x1800051e5`
- `0x180005209`
- `0x180005215`
- `0x18000b740`
- `0x18000df04`
- `0x18000e178`
- `0x18001393c`
- `0x18001455c`
- `0x180014974`
- `0x180015efc`
- `0x180032010`

## string_xrefs

- `0x180015f6d`: `combase.dll`
- `0x1800161d8`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v6; // r12
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const wchar_t *v12; // rdx
  void **v13; // r14
  char *v14; // rdi
  __int64 last_trivial_2; // rax
  __int64 v16; // rdi
  unsigned __int64 v17; // r15
  void **v18; // rcx
  char *v19; // r14
  __int64 v20; // r13
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r12
  size_t v24; // r8
  _BYTE *v25; // rdi
  _BYTE *v26; // rcx
  void **v27; // rcx
  HMODULE v28; // rdi
  FARPROC v29; // rax
  __int64 v30; // rax
  IErrorInfo *pperrinfo; // [rsp+20h] [rbp-58h] BYREF
  __int64 v33; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v34; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-40h]
  _QWORD *v36; // [rsp+40h] [rbp-38h]
  void *Src[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v38; // [rsp+58h] [rbp-20h]
  unsigned __int64 v39; // [rsp+60h] [rbp-18h]

  v36 = a4;
  v6 = a2;
  v35 = a2;
  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
    ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
    if ( ActivationFactory_0 == -2147221008 )
    {
      Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
      ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
      if ( !ProcAddress )
      {
        *a1 = ActivationFactory_0;
        return a1;
      }
      v34 = 0;
      ((void (__fastcall *)(unsigned __int64 *))ProcAddress)(&v34);
      ActivationFactory_0 = RoGetActivationFactory_0(*v6, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      *(_OWORD *)Src = 0;
      v38 = 0;
      v39 = 0;
      if ( *v6 )
        v12 = *(const wchar_t **)(*v6 + 16LL);
      else
        v12 = &S2;
      std::wstring::_Construct<1,unsigned short const *>(Src, v12);
      while ( 1 )
      {
        v13 = Src;
        if ( v39 > 7 )
          v13 = (void **)Src[0];
        if ( !v38 )
          break;
        v14 = (char *)v13 + 2 * v38;
        last_trivial_2 = _std_find_last_trivial_2(v13, v14, 46);
        if ( (char *)last_trivial_2 == v14 || (last_trivial_2 - (__int64)v13) >> 1 == -1 )
          break;
        std::wstring::resize(Src);
        v16 = v38;
        v17 = v39;
        if ( v39 - v38 < 4 )
        {
          if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v38) < 4 )
            std::_Xlen_string();
          v20 = v38 + 4;
          v21 = (v38 + 4) | 7;
          if ( v21 > 0x7FFFFFFFFFFFFFFELL || (v22 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFELL - (v39 >> 1)) )
          {
            v21 = 0x7FFFFFFFFFFFFFFELL;
          }
          else if ( v21 < v22 + v39 )
          {
            v21 = v22 + v39;
          }
          v34 = v21;
          v19 = (char *)std::wstring::_Allocate_for_capacity<0>(v21, &v34);
          v38 = v16 + 4;
          v39 = v34;
          v23 = 2 * v16;
          v24 = 2 * v16;
          if ( v17 <= 7 )
          {
            memcpy_0(v19, Src, v24);
            *(_QWORD *)&v19[v23] = *(_QWORD *)L".dll";
            *(_WORD *)&v19[2 * v20] = 0;
          }
          else
          {
            v25 = Src[0];
            memcpy_0(v19, Src[0], v24);
            *(_QWORD *)&v19[v23] = *(_QWORD *)L".dll";
            *(_WORD *)&v19[2 * v20] = 0;
            if ( 2 * v17 + 2 < 0x1000 )
            {
              v26 = v25;
            }
            else
            {
              v26 = (_BYTE *)*((_QWORD *)v25 - 1);
              if ( (unsigned __int64)(v25 - v26 - 8) > 0x1F )
                __fastfail(5u);
            }
            operator delete(v26);
          }
          v6 = v35;
          Src[0] = v19;
        }
        else
        {
          v38 += 4;
          v18 = Src;
          if ( v39 > 7 )
            v18 = (void **)Src[0];
          *(void **)((char *)v18 + 2 * v16) = *(void **)L".dll";
          *((_WORD *)v18 + v16 + 4) = 0;
          v19 = (char *)Src[0];
        }
        v27 = Src;
        if ( v39 > 7 )
          v27 = (void **)v19;
        v28 = LoadLibraryExW_0((LPCWSTR)v27, 0, 0x1000u);
        std::wstring::resize(Src);
        if ( v28 )
        {
          v29 = WINRT_IMPL_GetProcAddress(v28, "DllGetActivationFactory");
          if ( v29 )
          {
            v33 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v29)(*v6, &v33) )
            {
              v30 = v33;
              v33 = 0;
              *v36 = v30;
              *a1 = 0;
              goto LABEL_47;
            }
            if ( v33 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v33);
          }
          WINRT_IMPL_FreeLibrary(v28);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_47:
      std::wstring::~wstring(Src);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180015efc  push    rbp
0x180015efe  push    rbx
0x180015eff  push    rsi
0x180015f00  push    rdi
0x180015f01  push    r12
0x180015f03  push    r13
0x180015f05  push    r14
0x180015f07  push    r15
0x180015f09  mov     rbp, rsp
0x180015f0c  sub     rsp, 78h
0x180015f10  mov     rax, cs:__security_cookie
0x180015f17  xor     rax, rsp
0x180015f1a  mov     [rbp+var_10], rax
0x180015f1e  mov     r14, r9
0x180015f21  mov     [rbp+var_38], r9
0x180015f25  mov     rdi, r8
0x180015f28  mov     r12, rdx
0x180015f2b  mov     [rbp+var_40], rdx
0x180015f2f  mov     rsi, rcx
0x180015f32  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180015f39  xor     r13d, r13d
0x180015f3c  mov     r8, r9
0x180015f3f  mov     rdx, rdi
0x180015f42  mov     rcx, [r12]
0x180015f46  test    rax, rax
0x180015f49  jz      short loc_180015F57
0x180015f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f50  mov     [rsi], eax
0x180015f52  jmp     loc_180016262
0x180015f57  call    RoGetActivationFactory_0
0x180015f5c  mov     ebx, eax
0x180015f5e  cmp     eax, 800401F0h
0x180015f63  jnz     short loc_180015FB2
0x180015f65  xor     edx, edx; hFile
0x180015f67  mov     r8d, 1000h; dwFlags
0x180015f6d  lea     rcx, aCombaseDll; "combase.dll"
0x180015f74  call    LoadLibraryExW_0
0x180015f79  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180015f80  mov     rcx, rax; hModule
0x180015f83  call    WINRT_IMPL_GetProcAddress
0x180015f88  test    rax, rax
0x180015f8b  jnz     short loc_180015F94
0x180015f8d  mov     [rsi], ebx
0x180015f8f  jmp     loc_180016262
0x180015f94  mov     [rbp+var_48], r13
0x180015f98  lea     rcx, [rbp+var_48]
0x180015f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fa1  mov     r8, r14
0x180015fa4  mov     rdx, rdi
0x180015fa7  mov     rcx, [r12]
0x180015fab  call    RoGetActivationFactory_0
0x180015fb0  mov     ebx, eax
0x180015fb2  test    ebx, ebx
0x180015fb4  jnz     short loc_180015FBE
0x180015fb6  mov     [rsi], r13d
0x180015fb9  jmp     loc_180016262
0x180015fbe  mov     [rbp+pperrinfo], r13
0x180015fc2  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180015fc6  xor     ecx, ecx; dwReserved
0x180015fc8  call    GetErrorInfo_0
0x180015fcd  xorps   xmm0, xmm0
0x180015fd0  movups  xmmword ptr [rbp+Src], xmm0
0x180015fd4  mov     [rbp+var_20], r13
0x180015fd8  mov     [rbp+var_18], r13
0x180015fdc  mov     rax, [r12]
0x180015fe0  test    rax, rax
0x180015fe3  jz      short loc_180015FEF
0x180015fe5  mov     rdx, [rax+10h]
0x180015fe9  mov     r8d, [rax+4]
0x180015fed  jmp     short loc_180015FF9
0x180015fef  lea     rdx, S2
0x180015ff6  mov     r8, r13
0x180015ff9  lea     rcx, [rbp+Src]
0x180015ffd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016002  or      r15, 0FFFFFFFFFFFFFFFFh
0x180016006  mov     rax, [rbp+var_20]
0x18001600a  lea     r14, [rbp+Src]
0x18001600e  cmp     [rbp+var_18], 7
0x180016013  cmova   r14, [rbp+Src]
0x180016018  test    rax, rax
0x18001601b  jz      loc_18001623D
0x180016021  dec     rax
0x180016024  cmp     rax, r15
0x180016027  cmovnb  rax, r15
0x18001602b  inc     rax
0x18001602e  lea     rdi, [r14+rax*2]
0x180016032  mov     r8d, 2Eh ; '.'
0x180016038  mov     rdx, rdi
0x18001603b  mov     rcx, r14
0x18001603e  call    __std_find_last_trivial_2
0x180016043  cmp     rax, rdi
0x180016046  jz      loc_18001623D
0x18001604c  sub     rax, r14
0x18001604f  sar     rax, 1
0x180016052  cmp     rax, r15
0x180016055  jz      loc_18001623D
0x18001605b  mov     rdx, rax
0x18001605e  lea     rcx, [rbp+Src]; Src
0x180016062  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180016067  mov     rdi, [rbp+var_20]
0x18001606b  mov     r15, [rbp+var_18]
0x18001606f  mov     rax, r15
0x180016072  sub     rax, rdi
0x180016075  cmp     rax, 4
0x180016079  jb      short loc_1800160A9
0x18001607b  lea     rdx, [rdi+4]
0x18001607f  mov     [rbp+var_20], rdx
0x180016083  lea     rcx, [rbp+Src]
0x180016087  cmp     r15, 7
0x18001608b  cmova   rcx, [rbp+Src]
0x180016090  mov     rax, qword ptr cs:aDll; ".dll"
0x180016097  mov     [rcx+rdi*2], rax
0x18001609b  mov     [rcx+rdx*2], r13w
0x1800160a0  mov     r14, [rbp+Src]
0x1800160a4  jmp     loc_18001619A
0x1800160a9  mov     r8, 7FFFFFFFFFFFFFFEh
0x1800160b3  mov     rax, r8
0x1800160b6  sub     rax, rdi
0x1800160b9  cmp     rax, 4
0x1800160bd  jb      loc_180016282
0x1800160c3  lea     r13, [rdi+4]
0x1800160c7  mov     rcx, r13
0x1800160ca  or      rcx, 7
0x1800160ce  cmp     rcx, r8
0x1800160d1  jbe     short loc_1800160D8
0x1800160d3  mov     rcx, r8
0x1800160d6  jmp     short loc_1800160F4
0x1800160d8  mov     rdx, r15
0x1800160db  shr     rdx, 1
0x1800160de  mov     rax, r8
0x1800160e1  sub     rax, rdx
0x1800160e4  cmp     r15, rax
0x1800160e7  ja      short loc_1800160D3
0x1800160e9  lea     rax, [rdx+r15]
0x1800160ed  cmp     rcx, rax
0x1800160f0  cmovb   rcx, rax
0x1800160f4  mov     [rbp+var_48], rcx
0x1800160f8  lea     rdx, [rbp+var_48]
0x1800160fc  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180016101  mov     r14, rax
0x180016104  mov     [rbp+var_20], r13
0x180016108  mov     rcx, [rbp+var_48]
0x18001610c  mov     [rbp+var_18], rcx
0x180016110  lea     r12, [rdi+rdi]
0x180016114  mov     r8, r12; Size
0x180016117  mov     rcx, rax; void *
0x18001611a  cmp     r15, 7
0x18001611e  jbe     short loc_180016174
0x180016120  mov     rdi, [rbp+Src]
0x180016124  mov     rdx, rdi; Src
0x180016127  call    memcpy_0
0x18001612c  mov     rax, qword ptr cs:aDll; ".dll"
0x180016133  mov     [r12+r14], rax
0x180016137  xor     eax, eax
0x180016139  mov     [r14+r13*2], ax
0x18001613e  lea     rdx, ds:2[r15*2]
0x180016146  cmp     rdx, 1000h
0x18001614d  jb      short loc_18001616A
0x18001614f  mov     rcx, [rdi-8]
0x180016153  sub     rdi, rcx
0x180016156  sub     rdi, 8
0x18001615a  cmp     rdi, 1Fh
0x18001615e  ja      loc_180016222
0x180016164  add     rdx, 27h ; '''
0x180016168  jmp     short loc_18001616D
0x18001616a  mov     rcx, rdi; Block
0x18001616d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016172  jmp     short loc_18001618F
0x180016174  lea     rdx, [rbp+Src]; Src
0x180016178  call    memcpy_0
0x18001617d  mov     rax, qword ptr cs:aDll; ".dll"
0x180016184  mov     [r12+r14], rax
0x180016188  xor     eax, eax
0x18001618a  mov     [r14+r13*2], ax
0x18001618f  xor     r13d, r13d
0x180016192  mov     r12, [rbp+var_40]
0x180016196  mov     [rbp+Src], r14
0x18001619a  lea     rcx, [rbp+Src]
0x18001619e  cmp     [rbp+var_18], 7
0x1800161a3  cmova   rcx, r14; lpLibFileName
0x1800161a7  xor     edx, edx; hFile
0x1800161a9  mov     r8d, 1000h; dwFlags
0x1800161af  call    LoadLibraryExW_0
0x1800161b4  mov     rdi, rax
0x1800161b7  mov     rdx, [rbp+var_20]
0x1800161bb  add     rdx, 0FFFFFFFFFFFFFFFCh
0x1800161bf  lea     rcx, [rbp+Src]; Src
0x1800161c3  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800161c8  test    rdi, rdi
0x1800161cb  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800161d2  jz      loc_180016006
0x1800161d8  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1800161df  mov     rcx, rdi; hModule
0x1800161e2  call    WINRT_IMPL_GetProcAddress
0x1800161e7  test    rax, rax
0x1800161ea  jnz     short loc_1800161FC
0x1800161ec  mov     rcx, rdi; hLibModule
0x1800161ef  call    WINRT_IMPL_FreeLibrary
0x1800161f4  or      r15, r15
0x1800161f7  jmp     loc_180016006
0x1800161fc  mov     [rbp+var_50], r13
0x180016200  lea     rdx, [rbp+var_50]
0x180016204  mov     rcx, [r12]
0x180016208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001620d  test    eax, eax
0x18001620f  jz      short loc_180016229
0x180016211  cmp     [rbp+var_50], r13
0x180016215  jz      short loc_1800161EC
0x180016217  lea     rcx, [rbp+var_50]
0x18001621b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016220  jmp     short loc_1800161EC
0x180016222  mov     ecx, 5
0x180016227  int     29h; Win8: RtlFailFast(ecx)
0x180016229  mov     rax, [rbp+var_50]
0x18001622d  mov     [rbp+var_50], r13
0x180016231  mov     rcx, [rbp+var_38]
0x180016235  mov     [rcx], rax
0x180016238  mov     [rsi], r13d
0x18001623b  jmp     short loc_18001624A
0x18001623d  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180016241  xor     ecx, ecx; dwReserved
0x180016243  call    SetErrorInfo_0
0x180016248  mov     [rsi], ebx
0x18001624a  lea     rcx, [rbp+Src]; void *
0x18001624e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016253  cmp     [rbp+pperrinfo], r13
0x180016257  jz      short loc_180016262
0x180016259  lea     rcx, [rbp+pperrinfo]
0x18001625d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016262  mov     rax, rsi
0x180016265  mov     rcx, [rbp+var_10]
0x180016269  xor     rcx, rsp; StackCookie
0x18001626c  call    __security_check_cookie
0x180016271  add     rsp, 78h
0x180016275  pop     r15
0x180016277  pop     r14
0x180016279  pop     r13
0x18001627b  pop     r12
0x18001627d  pop     rdi
0x18001627e  pop     rsi
0x18001627f  pop     rbx
0x180016280  pop     rbp
0x180016281  retn
0x180016282  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
