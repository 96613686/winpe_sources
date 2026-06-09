# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180005314`
- end: `0x180005554`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `576`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `14`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180005208`
- `0x180005274`
- `0x18000529c`
- `0x1800052c4`
- `0x1800052ec`
- `0x18000555c`
- `0x180005584`
- `0x1800055ac`
- `0x1800055d4`
- `0x1800055fc`
- `0x180005624`
- `0x18000564c`
- `0x180005674`
- `0x18000f214`

## callees

- `0x180002e64`
- `0x180002eb8`
- `0x180002ef1`
- `0x180002f09`
- `0x180002f69`
- `0x180005314`
- `0x18000efbc`
- `0x18000f09c`
- `0x18000f544`
- `0x18000fbf8`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000554d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000554d`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800054a0`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800054a0`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  BSTR *v7; // rbx
  BSTR v8; // r14
  BSTR v9; // r15
  BSTR v10; // rdi
  void (__fastcall *v11)(BSTR, __int64); // r14
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // r14d
  BSTR v15; // r15
  OLECHAR *v16; // rbx
  unsigned int v17; // edx
  int v18; // eax
  HANDLE ProcessHeap; // rax
  BSTR pbstr; // [rsp+20h] [rbp-10h] BYREF
  BSTR v22; // [rsp+28h] [rbp-8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v7 = (BSTR *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  if ( pperrinfo )
  {
    pbstr = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &pbstr);
    v8 = pbstr;
    v22 = pbstr;
  }
  else
  {
    v22 = 0;
    v8 = 0;
  }
  if ( v7 == &v22 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
    *v7 = v8;
    v9 = v8;
  }
  if ( v9 )
  {
    v10 = *v7;
    v11 = *(void (__fastcall **)(BSTR, __int64))(*(_QWORD *)*v7 + 32LL);
    if ( *(_QWORD *)a1 )
    {
      WINRT_IMPL_SysFreeString(*(BSTR *)a1);
      *(_QWORD *)a1 = 0;
    }
    v11(v10, a1);
    v12 = (void (__fastcall ***)(_QWORD, __int64 *, BSTR *))*v7;
    if ( *v7 )
    {
      pbstr = 0;
      (**v12)(v12, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &pbstr);
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pbstr);
      }
    }
  }
  else
  {
    pbstr = 0;
    if ( pperrinfo )
    {
      ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr);
      v13 = 0;
      if ( pbstr )
      {
        v14 = SysStringLen_0(pbstr);
        v15 = pbstr;
        v16 = &pbstr[v14 - 1];
        if ( v14 )
        {
          while ( (unsigned int)_o_iswspace(*v16) )
          {
            --v16;
            if ( !--v14 )
              goto LABEL_21;
          }
          v13 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v14, v17);
          memcpy_s((void *const)(v13 + 7), 2LL * v14, v15, 2LL * v14);
        }
        else
        {
LABEL_21:
          v13 = 0;
        }
      }
    }
    else
    {
      v13 = 0;
    }
    winrt::hresult_error::originate(a1, a2, v13, a4);
    if ( v13 )
    {
      v18 = _InterlockedDecrement(v13 + 6);
      if ( v18 )
      {
        if ( v18 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v13);
      }
    }
    if ( pbstr )
      WINRT_IMPL_SysFreeString(pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180005314  mov     [rsp-28h+arg_8], rbx
0x180005319  mov     [rsp-28h+arg_10], rsi
0x18000531e  push    rbp
0x18000531f  push    rdi
0x180005320  push    r12
0x180005322  push    r14
0x180005324  push    r15
0x180005326  mov     rbp, rsp
0x180005329  sub     rsp, 30h
0x18000532d  mov     r12, r9
0x180005330  mov     edi, edx
0x180005332  mov     rsi, rcx
0x180005335  mov     qword ptr [rcx], 0
0x18000533c  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180005343  mov     [rcx+0Ch], edx
0x180005346  lea     rbx, [rcx+10h]
0x18000534a  mov     qword ptr [rbx], 0
0x180005351  mov     [rbp+pperrinfo], 0
0x180005359  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000535d  xor     ecx, ecx; dwReserved
0x18000535f  call    GetErrorInfo_0
0x180005364  mov     rcx, [rbp+pperrinfo]
0x180005368  test    rcx, rcx
0x18000536b  jnz     short loc_180005376
0x18000536d  mov     [rbp+var_8], rcx
0x180005371  xor     r14d, r14d
0x180005374  jmp     short loc_18000539C
0x180005376  mov     [rbp+pbstr], 0
0x18000537e  mov     rax, [rcx]
0x180005381  lea     r8, [rbp+pbstr]
0x180005385  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x18000538c  mov     rax, [rax]
0x18000538f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005394  mov     r14, [rbp+pbstr]
0x180005398  mov     [rbp+var_8], r14
0x18000539c  lea     rax, [rbp+var_8]
0x1800053a0  cmp     rbx, rax
0x1800053a3  jz      short loc_1800053BB
0x1800053a5  cmp     qword ptr [rbx], 0
0x1800053a9  jz      short loc_1800053B3
0x1800053ab  mov     rcx, rbx
0x1800053ae  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800053b3  mov     [rbx], r14
0x1800053b6  mov     r15, r14
0x1800053b9  jmp     short loc_1800053CC
0x1800053bb  mov     r15, [rbx]
0x1800053be  test    r14, r14
0x1800053c1  jz      short loc_1800053CC
0x1800053c3  lea     rcx, [rbp+var_8]
0x1800053c7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800053cc  test    r15, r15
0x1800053cf  jz      loc_180005458
0x1800053d5  mov     rdi, [rbx]
0x1800053d8  mov     rax, [rdi]
0x1800053db  mov     r14, [rax+20h]
0x1800053df  mov     rcx, [rsi]; bstrString
0x1800053e2  test    rcx, rcx
0x1800053e5  jz      short loc_1800053F3
0x1800053e7  call    WINRT_IMPL_SysFreeString
0x1800053ec  mov     qword ptr [rsi], 0
0x1800053f3  mov     rdx, rsi
0x1800053f6  mov     rcx, rdi
0x1800053f9  mov     rax, r14
0x1800053fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005401  mov     rcx, [rbx]
0x180005404  test    rcx, rcx
0x180005407  jz      loc_18000551F
0x18000540d  mov     [rbp+pbstr], 0
0x180005415  mov     rax, [rcx]
0x180005418  lea     r8, [rbp+pbstr]
0x18000541c  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x180005423  mov     rax, [rax]
0x180005426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000542b  mov     rcx, [rbp+pbstr]
0x18000542f  mov     [rbp+pbstr], rcx
0x180005433  test    rcx, rcx
0x180005436  jz      loc_18000551F
0x18000543c  mov     rax, [rcx]
0x18000543f  xor     edx, edx
0x180005441  mov     rax, [rax+28h]
0x180005445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000544a  lea     rcx, [rbp+pbstr]
0x18000544e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005453  jmp     loc_18000551F
0x180005458  mov     [rbp+pbstr], 0
0x180005460  mov     rcx, [rbp+pperrinfo]
0x180005464  test    rcx, rcx
0x180005467  jz      short loc_1800054DA
0x180005469  mov     rax, [rcx]
0x18000546c  lea     rdx, [rbp+pbstr]
0x180005470  mov     rax, [rax+28h]
0x180005474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005479  xor     ebx, ebx
0x18000547b  mov     rcx, [rbp+pbstr]; pbstr
0x18000547f  test    rcx, rcx
0x180005482  jz      short loc_1800054DC
0x180005484  call    SysStringLen_0
0x180005489  mov     r14d, eax
0x18000548c  mov     r15, [rbp+pbstr]
0x180005490  mov     ebx, eax
0x180005492  dec     rbx
0x180005495  lea     rbx, [r15+rbx*2]
0x180005499  test    eax, eax
0x18000549b  jz      short loc_1800054B4
0x18000549d  movzx   ecx, word ptr [rbx]
0x1800054a0  call    cs:__imp__o_iswspace
0x1800054a6  test    eax, eax
0x1800054a8  jz      short loc_1800054B8
0x1800054aa  sub     rbx, 2
0x1800054ae  add     r14d, 0FFFFFFFFh
0x1800054b2  jnz     short loc_18000549D
0x1800054b4  xor     ebx, ebx
0x1800054b6  jmp     short loc_1800054DC
0x1800054b8  mov     ecx, r14d; this
0x1800054bb  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800054c0  mov     rbx, rax
0x1800054c3  mov     edx, r14d
0x1800054c6  add     rdx, rdx; DestinationSize
0x1800054c9  lea     rcx, [rax+1Ch]; Destination
0x1800054cd  mov     r9, rdx; SourceSize
0x1800054d0  mov     r8, r15; Source
0x1800054d3  call    memcpy_s
0x1800054d8  jmp     short loc_1800054B6
0x1800054da  xor     ebx, ebx
0x1800054dc  mov     r9, r12
0x1800054df  mov     r8, rbx
0x1800054e2  mov     edx, edi
0x1800054e4  mov     rcx, rsi
0x1800054e7  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x1800054ec  test    rbx, rbx
0x1800054ef  jz      short loc_180005511
0x1800054f1  or      eax, 0FFFFFFFFh
0x1800054f4  lock xadd [rbx+18h], eax
0x1800054f9  sub     eax, 1
0x1800054fc  jnz     short loc_180005549
0x1800054fe  nop
0x1800054ff  call    WINRT_IMPL_GetProcessHeap
0x180005504  mov     rcx, rax; hHeap
0x180005507  mov     r8, rbx; lpMem
0x18000550a  xor     edx, edx; dwFlags
0x18000550c  call    WINRT_IMPL_HeapFree
0x180005511  mov     rcx, [rbp+pbstr]; bstrString
0x180005515  test    rcx, rcx
0x180005518  jz      short loc_18000551F
0x18000551a  call    WINRT_IMPL_SysFreeString
0x18000551f  cmp     [rbp+pperrinfo], 0
0x180005524  jz      short loc_18000552F
0x180005526  lea     rcx, [rbp+pperrinfo]
0x18000552a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000552f  mov     rax, rsi
0x180005532  mov     rbx, [rsp+30h+arg_8]
0x180005537  mov     rsi, [rsp+30h+arg_10]
0x18000553c  add     rsp, 30h
0x180005540  pop     r15
0x180005542  pop     r14
0x180005544  pop     r12
0x180005546  pop     rdi
0x180005547  pop     rbp
0x180005548  retn
0x180005549  test    eax, eax
0x18000554b  jns     short loc_180005511
0x18000554d  call    cs:__imp_abort
```
