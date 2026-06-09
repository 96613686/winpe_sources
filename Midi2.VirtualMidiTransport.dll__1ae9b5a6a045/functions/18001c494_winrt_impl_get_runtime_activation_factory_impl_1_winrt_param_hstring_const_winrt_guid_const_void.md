# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001c494`
- end: `0x18001c820`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001c3bc`

## callees

- `0x1800034d0`
- `0x1800038f0`
- `0x180003914`
- `0x180004688`
- `0x180004778`
- `0x180004790`
- `0x18000479c`
- `0x1800047d5`
- `0x1800047f9`
- `0x180004805`
- `0x18000bf6c`
- `0x18000cad0`
- `0x18000cb48`
- `0x180011a4c`
- `0x180012090`
- `0x18001a798`
- `0x18001c494`
- `0x180021010`

## string_xrefs

- `0x18001c505`: `combase.dll`
- `0x18001c770`: `DllGetActivationFactory`

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
0x18001c494  push    rbp
0x18001c496  push    rbx
0x18001c497  push    rsi
0x18001c498  push    rdi
0x18001c499  push    r12
0x18001c49b  push    r13
0x18001c49d  push    r14
0x18001c49f  push    r15
0x18001c4a1  mov     rbp, rsp
0x18001c4a4  sub     rsp, 78h
0x18001c4a8  mov     rax, cs:__security_cookie
0x18001c4af  xor     rax, rsp
0x18001c4b2  mov     [rbp+var_10], rax
0x18001c4b6  mov     r14, r9
0x18001c4b9  mov     [rbp+var_38], r9
0x18001c4bd  mov     rdi, r8
0x18001c4c0  mov     r12, rdx
0x18001c4c3  mov     [rbp+var_40], rdx
0x18001c4c7  mov     rsi, rcx
0x18001c4ca  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001c4d1  xor     r13d, r13d
0x18001c4d4  mov     r8, r9
0x18001c4d7  mov     rdx, rdi
0x18001c4da  mov     rcx, [r12]
0x18001c4de  test    rax, rax
0x18001c4e1  jz      short loc_18001C4EF
0x18001c4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4e8  mov     [rsi], eax
0x18001c4ea  jmp     loc_18001C7FA
0x18001c4ef  call    RoGetActivationFactory_0
0x18001c4f4  mov     ebx, eax
0x18001c4f6  cmp     eax, 800401F0h
0x18001c4fb  jnz     short loc_18001C54A
0x18001c4fd  xor     edx, edx; hFile
0x18001c4ff  mov     r8d, 1000h; dwFlags
0x18001c505  lea     rcx, aCombaseDll; "combase.dll"
0x18001c50c  call    LoadLibraryExW_0
0x18001c511  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x18001c518  mov     rcx, rax; hModule
0x18001c51b  call    WINRT_IMPL_GetProcAddress
0x18001c520  test    rax, rax
0x18001c523  jnz     short loc_18001C52C
0x18001c525  mov     [rsi], ebx
0x18001c527  jmp     loc_18001C7FA
0x18001c52c  mov     [rbp+var_48], r13
0x18001c530  lea     rcx, [rbp+var_48]
0x18001c534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c539  mov     r8, r14
0x18001c53c  mov     rdx, rdi
0x18001c53f  mov     rcx, [r12]
0x18001c543  call    RoGetActivationFactory_0
0x18001c548  mov     ebx, eax
0x18001c54a  test    ebx, ebx
0x18001c54c  jnz     short loc_18001C556
0x18001c54e  mov     [rsi], r13d
0x18001c551  jmp     loc_18001C7FA
0x18001c556  mov     [rbp+pperrinfo], r13
0x18001c55a  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001c55e  xor     ecx, ecx; dwReserved
0x18001c560  call    GetErrorInfo_0
0x18001c565  xorps   xmm0, xmm0
0x18001c568  movups  xmmword ptr [rbp+Src], xmm0
0x18001c56c  mov     [rbp+var_20], r13
0x18001c570  mov     [rbp+var_18], r13
0x18001c574  mov     rax, [r12]
0x18001c578  test    rax, rax
0x18001c57b  jz      short loc_18001C587
0x18001c57d  mov     rdx, [rax+10h]
0x18001c581  mov     r8d, [rax+4]
0x18001c585  jmp     short loc_18001C591
0x18001c587  lea     rdx, S2
0x18001c58e  mov     r8, r13
0x18001c591  lea     rcx, [rbp+Src]
0x18001c595  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c59a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001c59e  mov     rax, [rbp+var_20]
0x18001c5a2  lea     r14, [rbp+Src]
0x18001c5a6  cmp     [rbp+var_18], 7
0x18001c5ab  cmova   r14, [rbp+Src]
0x18001c5b0  test    rax, rax
0x18001c5b3  jz      loc_18001C7D5
0x18001c5b9  dec     rax
0x18001c5bc  cmp     rax, r15
0x18001c5bf  cmovnb  rax, r15
0x18001c5c3  inc     rax
0x18001c5c6  lea     rdi, [r14+rax*2]
0x18001c5ca  mov     r8d, 2Eh ; '.'
0x18001c5d0  mov     rdx, rdi
0x18001c5d3  mov     rcx, r14
0x18001c5d6  call    __std_find_last_trivial_2
0x18001c5db  cmp     rax, rdi
0x18001c5de  jz      loc_18001C7D5
0x18001c5e4  sub     rax, r14
0x18001c5e7  sar     rax, 1
0x18001c5ea  cmp     rax, r15
0x18001c5ed  jz      loc_18001C7D5
0x18001c5f3  mov     rdx, rax
0x18001c5f6  lea     rcx, [rbp+Src]; Src
0x18001c5fa  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c5ff  mov     rdi, [rbp+var_20]
0x18001c603  mov     r15, [rbp+var_18]
0x18001c607  mov     rax, r15
0x18001c60a  sub     rax, rdi
0x18001c60d  cmp     rax, 4
0x18001c611  jb      short loc_18001C641
0x18001c613  lea     rdx, [rdi+4]
0x18001c617  mov     [rbp+var_20], rdx
0x18001c61b  lea     rcx, [rbp+Src]
0x18001c61f  cmp     r15, 7
0x18001c623  cmova   rcx, [rbp+Src]
0x18001c628  mov     rax, qword ptr cs:aDll; ".dll"
0x18001c62f  mov     [rcx+rdi*2], rax
0x18001c633  mov     [rcx+rdx*2], r13w
0x18001c638  mov     r14, [rbp+Src]
0x18001c63c  jmp     loc_18001C732
0x18001c641  mov     r8, 7FFFFFFFFFFFFFFEh
0x18001c64b  mov     rax, r8
0x18001c64e  sub     rax, rdi
0x18001c651  cmp     rax, 4
0x18001c655  jb      loc_18001C81A
0x18001c65b  lea     r13, [rdi+4]
0x18001c65f  mov     rcx, r13
0x18001c662  or      rcx, 7
0x18001c666  cmp     rcx, r8
0x18001c669  jbe     short loc_18001C670
0x18001c66b  mov     rcx, r8
0x18001c66e  jmp     short loc_18001C68C
0x18001c670  mov     rdx, r15
0x18001c673  shr     rdx, 1
0x18001c676  mov     rax, r8
0x18001c679  sub     rax, rdx
0x18001c67c  cmp     r15, rax
0x18001c67f  ja      short loc_18001C66B
0x18001c681  lea     rax, [rdx+r15]
0x18001c685  cmp     rcx, rax
0x18001c688  cmovb   rcx, rax
0x18001c68c  mov     [rbp+var_48], rcx
0x18001c690  lea     rdx, [rbp+var_48]
0x18001c694  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18001c699  mov     r14, rax
0x18001c69c  mov     [rbp+var_20], r13
0x18001c6a0  mov     rcx, [rbp+var_48]
0x18001c6a4  mov     [rbp+var_18], rcx
0x18001c6a8  lea     r12, [rdi+rdi]
0x18001c6ac  mov     r8, r12; Size
0x18001c6af  mov     rcx, rax; void *
0x18001c6b2  cmp     r15, 7
0x18001c6b6  jbe     short loc_18001C70C
0x18001c6b8  mov     rdi, [rbp+Src]
0x18001c6bc  mov     rdx, rdi; Src
0x18001c6bf  call    memcpy_0
0x18001c6c4  mov     rax, qword ptr cs:aDll; ".dll"
0x18001c6cb  mov     [r12+r14], rax
0x18001c6cf  xor     eax, eax
0x18001c6d1  mov     [r14+r13*2], ax
0x18001c6d6  lea     rdx, ds:2[r15*2]
0x18001c6de  cmp     rdx, 1000h
0x18001c6e5  jb      short loc_18001C702
0x18001c6e7  mov     rcx, [rdi-8]
0x18001c6eb  sub     rdi, rcx
0x18001c6ee  sub     rdi, 8
0x18001c6f2  cmp     rdi, 1Fh
0x18001c6f6  ja      loc_18001C7BA
0x18001c6fc  add     rdx, 27h ; '''
0x18001c700  jmp     short loc_18001C705
0x18001c702  mov     rcx, rdi; Block
0x18001c705  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c70a  jmp     short loc_18001C727
0x18001c70c  lea     rdx, [rbp+Src]; Src
0x18001c710  call    memcpy_0
0x18001c715  mov     rax, qword ptr cs:aDll; ".dll"
0x18001c71c  mov     [r12+r14], rax
0x18001c720  xor     eax, eax
0x18001c722  mov     [r14+r13*2], ax
0x18001c727  xor     r13d, r13d
0x18001c72a  mov     r12, [rbp+var_40]
0x18001c72e  mov     [rbp+Src], r14
0x18001c732  lea     rcx, [rbp+Src]
0x18001c736  cmp     [rbp+var_18], 7
0x18001c73b  cmova   rcx, r14; lpLibFileName
0x18001c73f  xor     edx, edx; hFile
0x18001c741  mov     r8d, 1000h; dwFlags
0x18001c747  call    LoadLibraryExW_0
0x18001c74c  mov     rdi, rax
0x18001c74f  mov     rdx, [rbp+var_20]
0x18001c753  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001c757  lea     rcx, [rbp+Src]; Src
0x18001c75b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c760  test    rdi, rdi
0x18001c763  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18001c76a  jz      loc_18001C59E
0x18001c770  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18001c777  mov     rcx, rdi; hModule
0x18001c77a  call    WINRT_IMPL_GetProcAddress
0x18001c77f  test    rax, rax
0x18001c782  jnz     short loc_18001C794
0x18001c784  mov     rcx, rdi; hLibModule
0x18001c787  call    WINRT_IMPL_FreeLibrary
0x18001c78c  or      r15, r15
0x18001c78f  jmp     loc_18001C59E
0x18001c794  mov     [rbp+var_50], r13
0x18001c798  lea     rdx, [rbp+var_50]
0x18001c79c  mov     rcx, [r12]
0x18001c7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7a5  test    eax, eax
0x18001c7a7  jz      short loc_18001C7C1
0x18001c7a9  cmp     [rbp+var_50], r13
0x18001c7ad  jz      short loc_18001C784
0x18001c7af  lea     rcx, [rbp+var_50]
0x18001c7b3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c7b8  jmp     short loc_18001C784
0x18001c7ba  mov     ecx, 5
0x18001c7bf  int     29h; Win8: RtlFailFast(ecx)
0x18001c7c1  mov     rax, [rbp+var_50]
0x18001c7c5  mov     [rbp+var_50], r13
0x18001c7c9  mov     rcx, [rbp+var_38]
0x18001c7cd  mov     [rcx], rax
0x18001c7d0  mov     [rsi], r13d
0x18001c7d3  jmp     short loc_18001C7E2
0x18001c7d5  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001c7d9  xor     ecx, ecx; dwReserved
0x18001c7db  call    SetErrorInfo_0
0x18001c7e0  mov     [rsi], ebx
0x18001c7e2  lea     rcx, [rbp+Src]
0x18001c7e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c7eb  cmp     [rbp+pperrinfo], r13
0x18001c7ef  jz      short loc_18001C7FA
0x18001c7f1  lea     rcx, [rbp+pperrinfo]
0x18001c7f5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c7fa  mov     rax, rsi
0x18001c7fd  mov     rcx, [rbp+var_10]
0x18001c801  xor     rcx, rsp; StackCookie
0x18001c804  call    __security_check_cookie
0x18001c809  add     rsp, 78h
0x18001c80d  pop     r15
0x18001c80f  pop     r14
0x18001c811  pop     r13
0x18001c813  pop     r12
0x18001c815  pop     rdi
0x18001c816  pop     rsi
0x18001c817  pop     rbx
0x18001c818  pop     rbp
0x18001c819  retn
0x18001c81a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
