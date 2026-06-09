# uus::Session::Session(ushort const *)

- ea: `0x140007ec8`
- end: `0x140008050`
- name: `??0Session@uus@@QEAA@PEBG@Z`
- size: `392`
- prototype: `uus::Session *__fastcall(uus::Session *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000a678`

## callees

- `0x140002120`
- `0x1400023b4`
- `0x1400065bc`
- `0x1400067e8`
- `0x140007188`
- `0x140007ec8`
- `0x1400087e4`
- `0x1400091b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007f70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007f70`

## pseudocode

```c
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const unsigned __int16 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  char v5; // cl
  unsigned __int64 v6; // rdx
  void *v7; // rcx
  LPVOID pv[4]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v10; // [rsp+40h] [rbp-39h] BYREF
  __int128 v11; // [rsp+50h] [rbp-29h]
  char v12; // [rsp+60h] [rbp-19h]
  _QWORD v13[4]; // [rsp+68h] [rbp-11h] BYREF
  void *v14[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+98h] [rbp+1Fh]
  _BYTE v16[32]; // [rsp+A8h] [rbp+2Fh] BYREF

  pv[0] = this;
  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  v13[0] = 32;
  v13[1] = 3;
  v13[2] = 0x140000000uLL;
  v13[3] = a2;
  *(_OWORD *)v14 = 0;
  *(_QWORD *)&v15 = 0;
  *((_QWORD *)&v15 + 1) = 7;
  LOWORD(v14[0]) = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(pv);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv[0] + v4) );
  pv[2] = pv[0];
  pv[3] = (LPVOID)v4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v16);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  uus::Utility::FindFileInArchFolder(&v10, v16);
  std::wstring::~wstring(v16);
  v5 = v12;
  if ( v12 )
  {
    if ( *((_QWORD *)&v15 + 1) > 7u )
    {
      v6 = 2LL * *((_QWORD *)&v15 + 1) + 2;
      if ( v6 < 0x1000 )
      {
        v7 = v14[0];
      }
      else
      {
        v7 = (void *)*((_QWORD *)v14[0] - 1);
        if ( (unsigned __int64)((char *)v14[0] - (char *)v7 - 8) > 0x1F )
          __fastfail(5u);
        v6 = 2LL * *((_QWORD *)&v15 + 1) + 41;
      }
      operator delete(v7, v6);
      v5 = v12;
    }
    *(_OWORD *)v14 = v10;
    v15 = v11;
    *(_QWORD *)&v11 = 0;
    *((_QWORD *)&v11 + 1) = 7;
    LOWORD(v10) = 0;
    if ( v5 )
      std::wstring::~wstring(&v10);
    v3 = uus::Utility::GetBrainSession<uus::Brain3>((char *)v14, (__int64)v13);
  }
  std::wstring::~wstring(v14);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x140007ec8  mov     [rsp-8+arg_10], rbx
0x140007ecd  mov     [rsp-8+arg_18], rdi
0x140007ed2  push    rbp
0x140007ed3  lea     rbp, [rsp-57h]
0x140007ed8  sub     rsp, 0D0h
0x140007edf  mov     rax, cs:__security_cookie
0x140007ee6  xor     rax, rsp
0x140007ee9  mov     [rbp+57h+var_8], rax
0x140007eed  mov     rdi, rcx
0x140007ef0  mov     [rbp+57h+pv], rcx
0x140007ef4  xor     ebx, ebx
0x140007ef6  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x140007efd  mov     [rcx], rax
0x140007f00  mov     [rbp+57h+var_68], 20h ; ' '
0x140007f08  mov     [rbp+57h+var_60], 3
0x140007f10  lea     rax, cs:140000000h
0x140007f17  mov     [rbp+57h+var_58], rax
0x140007f1b  mov     [rbp+57h+var_50], rdx
0x140007f1f  xorps   xmm0, xmm0
0x140007f22  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140007f26  mov     qword ptr [rbp+57h+var_38], rbx
0x140007f2a  mov     qword ptr [rbp+57h+var_38+8], 7
0x140007f32  mov     word ptr [rbp+57h+var_48], bx
0x140007f36  lea     rcx, [rbp+57h+pv]
0x140007f3a  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x140007f3f  nop
0x140007f40  mov     rcx, [rbp+57h+pv]
0x140007f44  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007f48  inc     rax
0x140007f4b  cmp     [rcx+rax*2], bx
0x140007f4f  jnz     short loc_140007F48
0x140007f51  mov     [rbp+57h+var_A0], rcx
0x140007f55  mov     [rbp+57h+var_98], rax
0x140007f59  lea     rdx, [rbp+57h+var_A0]
0x140007f5d  lea     rcx, [rbp+57h+var_28]; void *
0x140007f61  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x140007f66  nop
0x140007f67  mov     rcx, [rbp+57h+pv]; pv
0x140007f6b  test    rcx, rcx
0x140007f6e  jz      short loc_140007F77
0x140007f70  call    cs:__imp_CoTaskMemFree
0x140007f76  nop
0x140007f77  lea     rdx, [rbp+57h+var_28]
0x140007f7b  lea     rcx, [rbp+57h+var_90]
0x140007f7f  call    ?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)
0x140007f84  nop
0x140007f85  lea     rcx, [rbp+57h+var_28]
0x140007f89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007f8e  mov     cl, [rbp+57h+var_70]
0x140007f91  test    cl, cl
0x140007f93  jnz     short loc_140007F9A
0x140007f95  jmp     loc_14000801F
0x140007f9a  mov     rdx, qword ptr [rbp+57h+var_38+8]
0x140007f9e  cmp     rdx, 7
0x140007fa2  jbe     short loc_140007FE2
0x140007fa4  mov     rax, [rbp+57h+var_48]
0x140007fa8  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x140007fb0  cmp     rdx, 1000h
0x140007fb7  jb      short loc_140007FD7
0x140007fb9  mov     rcx, [rax-8]
0x140007fbd  sub     rax, rcx
0x140007fc0  sub     rax, 8
0x140007fc4  cmp     rax, 1Fh
0x140007fc8  ja      short loc_140007FD0
0x140007fca  add     rdx, 27h ; '''
0x140007fce  jmp     short loc_140007FDA
0x140007fd0  mov     ecx, 5
0x140007fd5  int     29h; Win8: RtlFailFast(ecx)
0x140007fd7  mov     rcx, rax; void *
0x140007fda  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007fdf  mov     cl, [rbp+57h+var_70]
0x140007fe2  movups  xmm0, [rbp+57h+var_90]
0x140007fe6  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140007fea  movups  xmm1, [rbp+57h+var_80]
0x140007fee  movups  [rbp+57h+var_38], xmm1
0x140007ff2  mov     qword ptr [rbp+57h+var_80], rbx
0x140007ff6  mov     qword ptr [rbp+57h+var_80+8], 7
0x140007ffe  mov     word ptr [rbp+57h+var_90], bx
0x140008002  test    cl, cl
0x140008004  jz      short loc_14000800F
0x140008006  lea     rcx, [rbp+57h+var_90]
0x14000800a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000800f  lea     rdx, [rbp+57h+var_68]
0x140008013  lea     rcx, [rbp+57h+var_48]
0x140008017  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x14000801c  mov     rbx, rax
0x14000801f  lea     rcx, [rbp+57h+var_48]
0x140008023  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140008028  mov     [rdi+8], rbx
0x14000802c  mov     rax, rdi
0x14000802f  mov     rcx, [rbp+57h+var_8]
0x140008033  xor     rcx, rsp; StackCookie
0x140008036  call    __security_check_cookie
0x14000803b  lea     r11, [rsp+0D0h+var_s0]
0x140008043  mov     rbx, [r11+20h]
0x140008047  mov     rdi, [r11+28h]
0x14000804b  mov     rsp, r11
0x14000804e  pop     rbp
0x14000804f  retn
```
