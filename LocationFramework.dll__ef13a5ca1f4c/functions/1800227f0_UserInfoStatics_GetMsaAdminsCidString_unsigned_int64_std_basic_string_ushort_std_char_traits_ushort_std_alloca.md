# UserInfoStatics::GetMsaAdminsCidString(unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,unsigned __int64 &)

- ea: `0x1800227f0`
- end: `0x1800229b5`
- name: `?GetMsaAdminsCidString@UserInfoStatics@@SAJ_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_K@Z`
- size: `453`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022710`
- `0x18002ebe8`

## callees

- `0x1800208b0`
- `0x180020c64`
- `0x1800227f0`
- `0x18005c458`
- `0x180084ac8`
- `0x18009cc18`
- `0x1800a98c0`
- `0x1800a98e4`
- `0x1800a9e30`
- `0x1800bd834`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022852`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022852`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002288b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002288b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228be`

## string_xrefs

- `0x18002284b`: `mdmcommon.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HMODULE __fastcall UserInfoStatics::GetMsaAdminsCidString(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rax
  HMODULE result; // rax
  HMODULE v8; // rbx
  __int64 v9; // rax
  unsigned int LastError; // edi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD, _QWORD); // rsi
  unsigned __int64 v13; // rax
  void *v14; // rax
  void *v15; // rdi
  int v16; // esi
  const char *v17; // [rsp+28h] [rbp-60h]
  __int16 v18; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+0h]

  *a3 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v18 = 0;
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2);
  std::_WChar_traits<unsigned short>::assign(v6, &v18);
  result = LoadLibraryExW(L"mdmcommon.dll", 0, 0x800u);
  v8 = result;
  v19[0] = result;
  if ( result )
  {
    ProcAddress = GetProcAddress(result, "MdmUsersAuthorizedToSeeLocationAsString");
    v12 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( !ProcAddress )
    {
      LastError = wil::details::in1diag5::Return_GetLastError(
                    retaddr,
                    (void *)0x1F,
                    (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\UserInfoStatics.h",
                    "UserInfoStatics::GetMsaAdminsCidString",
                    "pfnMdmUsersAuthorizedToSeeLocationAsString",
                    v17);
      goto LABEL_5;
    }
    v20 = 0;
    LastError = ((__int64 (__fastcall *)(__int64, _QWORD *, _QWORD, unsigned __int64 *))ProcAddress)(a1, a3, 0, &v20);
    if ( (int)(LastError + 0x80000000) >= 0 && LastError != -2147024774 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v19);
      return (HMODULE)LastError;
    }
    if ( *a3 )
    {
      v13 = 2 * v20;
      if ( !is_mul_ok(v20, 2u) )
        v13 = -1;
      v14 = operator new[](v13, (const struct std::nothrow_t *)std::nothrow);
      v15 = v14;
      v19[1] = v14;
      if ( !v14 )
      {
        LastError = -2147024882;
        goto LABEL_5;
      }
      v16 = v12(a1, a3, v14, &v20);
      if ( v16 < 0 )
      {
        operator delete(v15);
        LastError = v16;
        goto LABEL_5;
      }
      v9 = std::_WChar_traits<unsigned short>::length(v15);
      std::wstring::_Assign<unsigned short>(a2, v15, v9);
      operator delete(v15);
    }
    LastError = 0;
LABEL_5:
    FreeLibrary(v8);
    return (HMODULE)LastError;
  }
  return result;
}

```

## disassembly

```asm
0x1800227f0  mov     [rsp+arg_18], rbx
0x1800227f5  push    rbp
0x1800227f6  push    rsi
0x1800227f7  push    rdi
0x1800227f8  push    r14
0x1800227fa  push    r15
0x1800227fc  sub     rsp, 60h
0x180022800  mov     rax, cs:__security_cookie
0x180022807  xor     rax, rsp
0x18002280a  mov     [rsp+88h+var_38], rax
0x18002280f  mov     r14, r8
0x180022812  mov     r15, rdx
0x180022815  mov     rbp, rcx
0x180022818  mov     qword ptr [r8], 0
0x18002281f  mov     qword ptr [rdx+10h], 0
0x180022827  xor     eax, eax
0x180022829  mov     [rsp+88h+var_58], ax
0x18002282e  mov     rcx, rdx
0x180022831  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022836  mov     rcx, rax
0x180022839  lea     rdx, [rsp+88h+var_58]
0x18002283e  call    ?assign@?$_WChar_traits@G@std@@SAXAEAGAEBG@Z; std::_WChar_traits<ushort>::assign(ushort &,ushort const &)
0x180022843  xor     edx, edx; hFile
0x180022845  mov     r8d, 800h; dwFlags
0x18002284b  lea     rcx, aMdmcommonDll; "mdmcommon.dll"
0x180022852  call    cs:__imp_LoadLibraryExW
0x180022858  mov     rbx, rax
0x18002285b  mov     [rsp+88h+var_50], rax
0x180022860  test    rax, rax
0x180022863  jnz     short loc_1800228B4
0x180022865  jmp     short loc_180022893
0x180022867  mov     rcx, rdi
0x18002286a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002286f  mov     r8, rax
0x180022872  mov     rdx, rdi
0x180022875  mov     rcx, r15
0x180022878  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002287d  nop
0x18002287e  mov     rcx, rdi; Block
0x180022881  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180022886  xor     edi, edi
0x180022888  mov     rcx, rbx; hLibModule
0x18002288b  call    cs:__imp_FreeLibrary
0x180022891  mov     eax, edi
0x180022893  mov     rcx, [rsp+88h+var_38]
0x180022898  xor     rcx, rsp; StackCookie
0x18002289b  call    __security_check_cookie
0x1800228a0  mov     rbx, [rsp+88h+arg_18]
0x1800228a8  add     rsp, 60h
0x1800228ac  pop     r15
0x1800228ae  pop     r14
0x1800228b0  pop     rdi
0x1800228b1  pop     rsi
0x1800228b2  pop     rbp
0x1800228b3  retn
0x1800228b4  lea     rdx, aMdmusersauthor; "MdmUsersAuthorizedToSeeLocationAsString"
0x1800228bb  mov     rcx, rbx; hModule
0x1800228be  call    cs:__imp_GetProcAddress
0x1800228c4  mov     rsi, rax
0x1800228c7  test    rax, rax
0x1800228ca  jz      loc_180022981
0x1800228d0  mov     [rsp+88h+var_40], 0
0x1800228d9  lea     r9, [rsp+88h+var_40]
0x1800228de  xor     r8d, r8d
0x1800228e1  mov     rdx, r14
0x1800228e4  mov     rcx, rbp
0x1800228e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228ec  mov     edi, eax
0x1800228ee  mov     eax, 80000000h
0x1800228f3  lea     ecx, [rdi+rax]
0x1800228f6  test    eax, ecx
0x1800228f8  jz      short loc_18002296A
0x1800228fa  cmp     qword ptr [r14], 0
0x1800228fe  jz      short loc_180022886
0x180022900  mov     eax, 2
0x180022905  mul     [rsp+88h+var_40]
0x18002290a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022911  cmovb   rax, rcx
0x180022915  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002291c  mov     rcx, rax; unsigned __int64
0x18002291f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022924  mov     rdi, rax
0x180022927  mov     [rsp+88h+var_48], rax
0x18002292c  test    rax, rax
0x18002292f  jz      short loc_180022960
0x180022931  lea     r9, [rsp+88h+var_40]
0x180022936  mov     r8, rax
0x180022939  mov     rdx, r14
0x18002293c  mov     rcx, rbp
0x18002293f  mov     rax, rsi
0x180022942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022947  mov     esi, eax
0x180022949  test    eax, eax
0x18002294b  jns     loc_180022867
0x180022951  mov     rcx, rdi; Block
0x180022954  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180022959  mov     edi, esi
0x18002295b  jmp     loc_180022888
0x180022960  mov     edi, 8007000Eh
0x180022965  jmp     loc_180022888
0x18002296a  cmp     edi, 8007007Ah
0x180022970  jz      short loc_1800228FA
0x180022972  lea     rcx, [rsp+88h+var_50]
0x180022977  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002297c  jmp     loc_180022891
0x180022981  mov     rcx, [rsp+88h]; this
0x180022989  lea     rax, aPfnmdmusersaut; "pfnMdmUsersAuthorizedToSeeLocationAsStr"...
0x180022990  mov     [rsp+88h+var_68], rax; char *
0x180022995  lea     r9, aUserinfostatic; "UserInfoStatics::GetMsaAdminsCidString"
0x18002299c  lea     r8, aOnecoreuapDriv_97; "onecoreuap\\drivers\\MobilePC\\Location"...
0x1800229a3  mov     edx, 1Fh; void *
0x1800229a8  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x1800229ad  mov     edi, eax
0x1800229af  jmp     loc_180022888
```
