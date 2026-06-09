# Pal::NetworkRequestInternalWinHttpService::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader,std::allocator<Pal::HttpHeader>>> const &)

- ea: `0x180033200`
- end: `0x18003343e`
- name: `?sendRequestAsUser@NetworkRequestInternalWinHttpService@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000b4b8`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000fe68`
- `0x180013da8`
- `0x18002c30c`
- `0x18002ea20`
- `0x18002f3e8`
- `0x180030904`
- `0x180032db0`
- `0x180033200`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ac`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003339e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003339e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Pal::NetworkRequestInternalWinHttpService::sendRequestAsUser(
        DWORD_PTR dwContext,
        __int64 a2,
        __int64 **a3)
{
  char *v6; // r15
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  std::_Ref_count_base *v11; // rcx
  __int64 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  void *v16; // rax
  signed int LastError; // eax
  __int128 *v18; // [rsp+20h] [rbp-59h] BYREF
  __int64 v19; // [rsp+28h] [rbp-51h] BYREF
  __int64 *v20; // [rsp+30h] [rbp-49h] BYREF
  DWORD_PTR dwContexta; // [rsp+38h] [rbp-41h]
  _BYTE v22[16]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v23; // [rsp+50h] [rbp-29h]
  __int128 v24; // [rsp+60h] [rbp-19h] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp-9h]

  if ( qword_18007B5A0 )
  {
    v6 = (char *)operator new(0x28u);
    v18 = (__int128 *)v6;
    *(_OWORD *)v6 = 0;
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<std::vector<Pal::HttpHeader>>::`vftable';
    std::_Construct_in_place<std::vector<Pal::HttpHeader>,>(v6 + 16);
    v20 = (__int64 *)(v6 + 16);
    dwContexta = (DWORD_PTR)v6;
    v19 = 0;
    v7 = qword_18007B5A0;
    v8 = **(__int64 (__fastcall ***)(__int64, __int64 *))qword_18007B5A0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v9 = v8(v7, &v19);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v24 = *(_OWORD *)L"Windows.GenericClient";
      v25[0] = *(_OWORD *)L"GenericClient";
      *(_OWORD *)((char *)v25 + 12) = *(_OWORD *)L"cClient";
      v18 = &v24;
      *(_BYTE *)(dwContext + 464) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19) != 0;
      v13 = *a3;
      if ( *a3 && v6 + 16 != (char *)v13 )
        std::vector<Pal::HttpHeader>::_Assign_counted_range<Pal::HttpHeader *>(v6 + 16, *v13, (v13[1] - *v13) >> 6);
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
      std::wstring::wstring((__int64)v22, v14);
      if ( v23 )
        v18 = (__int128 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
      std::vector<Pal::HttpHeader>::emplace_back<unsigned short const (&)[16],unsigned short const * &>(
        v6 + 16,
        v15,
        &v18);
      if ( v19 && (v16 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19)) != 0 )
      {
        if ( ImpersonateLoggedOnUser(v16) )
        {
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        LODWORD(v18) = LastError;
      }
      else
      {
        LODWORD(v18) = -2147023888;
      }
      v10 = Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(dwContext, a2, &v20);
      Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(&v18);
      std::wstring::_Tidy_deallocate(v22);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      v11 = (std::_Ref_count_base *)dwContexta;
      if ( !dwContexta )
        return v10;
    }
    else
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v10 = (unsigned __int16)v9;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      v11 = (std::_Ref_count_base *)v6;
    }
    std::_Ref_count_base::_Decref(v11);
    return v10;
  }
  *(_BYTE *)(dwContext + 464) = 1;
  return Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(dwContext, a2, a3);
}

```

## disassembly

```asm
0x180033200  mov     [rsp-8+arg_18], rbx
0x180033205  push    rbp
0x180033206  push    rsi
0x180033207  push    rdi
0x180033208  push    r12
0x18003320a  push    r13
0x18003320c  push    r14
0x18003320e  push    r15
0x180033210  lea     rbp, [rsp-27h]
0x180033215  sub     rsp, 0A0h
0x18003321c  mov     rax, cs:__security_cookie
0x180033223  xor     rax, rsp
0x180033226  mov     [rbp+57h+var_40], rax
0x18003322a  mov     r12, r8
0x18003322d  mov     r13, rdx
0x180033230  mov     r14, rcx
0x180033233  xor     ebx, ebx
0x180033235  cmp     cs:qword_18007B5A0, rbx
0x18003323c  jz      loc_18003340B
0x180033242  lea     ecx, [rbx+28h]; Size
0x180033245  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003324a  mov     r15, rax
0x18003324d  mov     [rbp+57h+var_B0], rax
0x180033251  xorps   xmm0, xmm0
0x180033254  movups  xmmword ptr [rax], xmm0
0x180033257  mov     dword ptr [rax+8], 1
0x18003325e  mov     dword ptr [rax+0Ch], 1
0x180033265  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<Pal::HttpHeader>>::`vftable'
0x18003326c  mov     [r15], rax
0x18003326f  lea     rsi, [r15+10h]
0x180033273  mov     rcx, rsi
0x180033276  call    ??$_Construct_in_place@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@$$V@std@@YAXAEAV?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@0@@Z; std::_Construct_in_place<std::vector<Pal::HttpHeader>,>(std::vector<Pal::HttpHeader> &)
0x18003327b  mov     [rbp+57h+var_A0], rsi
0x18003327f  mov     [rbp+57h+dwContext], r15
0x180033283  mov     [rbp+57h+var_A8], rbx
0x180033287  mov     rdi, cs:qword_18007B5A0
0x18003328e  mov     rax, [rdi]
0x180033291  mov     rbx, [rax]
0x180033294  lea     rcx, [rbp+57h+var_A8]
0x180033298  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003329d  lea     rdx, [rbp+57h+var_A8]
0x1800332a1  mov     rcx, rdi
0x1800332a4  mov     rax, rbx
0x1800332a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332ac  mov     ebx, eax
0x1800332ae  test    eax, eax
0x1800332b0  jns     short loc_1800332DA
0x1800332b2  and     eax, 1FFF0000h
0x1800332b7  cmp     eax, 70000h
0x1800332bc  jnz     short loc_1800332C1
0x1800332be  movzx   ebx, bx
0x1800332c1  lea     rcx, [rbp+57h+var_A8]
0x1800332c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800332ca  nop
0x1800332cb  mov     rcx, r15; this
0x1800332ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800332d3  mov     eax, ebx
0x1800332d5  jmp     loc_180033417
0x1800332da  movups  xmm0, xmmword ptr cs:aWindowsGeneric; "Windows.GenericClient"
0x1800332e1  movups  [rbp+57h+var_70], xmm0
0x1800332e5  movups  xmm1, xmmword ptr cs:aWindowsGeneric+10h; "GenericClient"
0x1800332ec  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x1800332f0  movups  xmm0, xmmword ptr cs:aWindowsGeneric+1Ch; "cClient"
0x1800332f7  movups  xmmword ptr [rbp+57h+var_60+0Ch], xmm0
0x1800332fb  lea     rax, [rbp+57h+var_70]
0x1800332ff  mov     [rbp+57h+var_B0], rax
0x180033303  mov     rcx, [rbp+57h+var_A8]
0x180033307  mov     rax, [rcx]
0x18003330a  mov     rax, [rax+18h]
0x18003330e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033313  test    rax, rax
0x180033316  setnz   al
0x180033319  mov     [r14+1D0h], al
0x180033320  mov     rdx, [r12]
0x180033324  test    rdx, rdx
0x180033327  jz      short loc_180033344
0x180033329  cmp     rsi, rdx
0x18003332c  jz      short loc_180033344
0x18003332e  mov     r8, [rdx+8]
0x180033332  sub     r8, [rdx]
0x180033335  sar     r8, 6
0x180033339  mov     rdx, [rdx]
0x18003333c  mov     rcx, rsi
0x18003333f  call    ??$_Assign_counted_range@PEAVHttpHeader@Pal@@@?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@AEAAXPEAVHttpHeader@Pal@@_K@Z; std::vector<Pal::HttpHeader>::_Assign_counted_range<Pal::HttpHeader *>(Pal::HttpHeader *,unsigned __int64)
0x180033344  mov     rcx, [rbp+57h+var_A8]
0x180033348  mov     rax, [rcx]
0x18003334b  mov     rax, [rax+28h]
0x18003334f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033354  mov     rdx, rax
0x180033357  lea     rcx, [rbp+57h+var_90]
0x18003335b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033360  nop
0x180033361  cmp     [rbp+57h+var_80], 0
0x180033366  jz      short loc_180033375
0x180033368  lea     rcx, [rbp+57h+var_90]
0x18003336c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033371  mov     [rbp+57h+var_B0], rax
0x180033375  lea     r8, [rbp+57h+var_B0]
0x180033379  mov     rcx, rsi
0x18003337c  call    ??$emplace_back@AEAY0BA@$$CBGAEAPEBG@?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@QEAAAEAVHttpHeader@Pal@@AEAY0BA@$$CBGAEAPEBG@Z; std::vector<Pal::HttpHeader>::emplace_back<ushort const (&)[16],ushort const * &>(ushort const (&)[16],ushort const * &)
0x180033381  mov     rcx, [rbp+57h+var_A8]
0x180033385  test    rcx, rcx
0x180033388  jz      short loc_1800333C3
0x18003338a  mov     rax, [rcx]
0x18003338d  mov     rax, [rax+18h]
0x180033391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033396  test    rax, rax
0x180033399  jz      short loc_1800333C3
0x18003339b  mov     rcx, rax; hToken
0x18003339e  call    cs:__imp_ImpersonateLoggedOnUser
0x1800333a4  test    eax, eax
0x1800333a6  jz      short loc_1800333AC
0x1800333a8  xor     eax, eax
0x1800333aa  jmp     short loc_1800333BE
0x1800333ac  call    cs:__imp_GetLastError
0x1800333b2  test    eax, eax
0x1800333b4  jle     short loc_1800333BE
0x1800333b6  movzx   eax, ax
0x1800333b9  or      eax, 80070000h
0x1800333be  mov     dword ptr [rbp+57h+var_B0], eax
0x1800333c1  jmp     short loc_1800333CA
0x1800333c3  mov     dword ptr [rbp+57h+var_B0], 800703F0h
0x1800333ca  lea     r8, [rbp+57h+var_A0]
0x1800333ce  mov     rdx, r13
0x1800333d1  mov     rcx, r14; dwContext
0x1800333d4  call    ?sendRequestAsUser@NetworkRequestInternalWinHttp@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z; Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader>> const &)
0x1800333d9  mov     ebx, eax
0x1800333db  lea     rcx, [rbp+57h+var_B0]
0x1800333df  call    ?Revert@?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAAXXZ; Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(void)
0x1800333e4  nop
0x1800333e5  lea     rcx, [rbp+57h+var_90]
0x1800333e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800333ee  nop
0x1800333ef  lea     rcx, [rbp+57h+var_A8]
0x1800333f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800333f8  nop
0x1800333f9  mov     rcx, [rbp+57h+dwContext]; dwContext
0x1800333fd  test    rcx, rcx
0x180033400  jz      loc_1800332D3
0x180033406  jmp     loc_1800332CE
0x18003340b  mov     byte ptr [rcx+1D0h], 1
0x180033412  call    ?sendRequestAsUser@NetworkRequestInternalWinHttp@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z; Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader>> const &)
0x180033417  mov     rcx, [rbp+57h+var_40]
0x18003341b  xor     rcx, rsp; StackCookie
0x18003341e  call    __security_check_cookie
0x180033423  mov     rbx, [rsp+0D0h+arg_18]
0x18003342b  add     rsp, 0A0h
0x180033432  pop     r15
0x180033434  pop     r14
0x180033436  pop     r13
0x180033438  pop     r12
0x18003343a  pop     rdi
0x18003343b  pop     rsi
0x18003343c  pop     rbp
0x18003343d  retn
```
