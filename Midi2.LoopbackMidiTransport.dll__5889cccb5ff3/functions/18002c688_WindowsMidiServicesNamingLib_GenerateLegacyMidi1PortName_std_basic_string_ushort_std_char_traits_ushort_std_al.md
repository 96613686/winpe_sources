# WindowsMidiServicesNamingLib::GenerateLegacyMidi1PortName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,uchar)

- ea: `0x18002c688`
- end: `0x18002c916`
- name: `?GenerateLegacyMidi1PortName@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@E@Z`
- size: `654`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18002cab8`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000e178`
- `0x18000f0a4`
- `0x18000feb0`
- `0x1800134cc`
- `0x180022554`
- `0x18002a414`
- `0x18002abe4`
- `0x18002c688`
- `0x18002fda4`

## pseudocode

```c
_OWORD *__fastcall WindowsMidiServicesNamingLib::GenerateLegacyMidi1PortName(
        _OWORD *Src,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5)
{
  void *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rdx
  void *v12; // rax
  _QWORD *v13; // rax
  bool v14; // cc
  void *v15; // rax
  __int64 v16; // rax
  __int128 *v17; // rax
  const char *v18; // rcx
  char *v19; // r8
  __int128 *p_Srca; // rdx
  _QWORD *v21; // rax
  __int128 *v22; // rax
  __int128 v23; // xmm1
  __int128 v25; // [rsp+28h] [rbp-79h] BYREF
  __int128 v26; // [rsp+38h] [rbp-69h]
  __int128 Srca; // [rsp+48h] [rbp-59h] BYREF
  __int128 v28; // [rsp+58h] [rbp-49h]
  _OWORD v29[2]; // [rsp+70h] [rbp-31h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-11h] BYREF

  v25 = 0;
  *(_QWORD *)&v26 = 0;
  *((_QWORD *)&v26 + 1) = 7;
  LOWORD(v25) = 0;
  v9 = (void *)std::wstring::wstring(v30, a2);
  v10 = *(_QWORD *)(WindowsMidiServicesInternal::TrimmedWStringCopy(&Srca, v9) + 16);
  std::wstring::~wstring(&Srca);
  v11 = a2;
  if ( !v10 )
    v11 = a3;
  v12 = (void *)std::wstring::wstring(v30, v11);
  v13 = (_QWORD *)WindowsMidiServicesInternal::TrimmedWStringCopy(v29, v12);
  v14 = v13[3] <= 7u;
  v28 = 0;
  Srca = 0;
  if ( !v14 )
    v13 = (_QWORD *)*v13;
  std::wstring::_Construct<1,unsigned short const *>(&Srca, v13);
  std::wstring::operator=(&v25, &Srca);
  std::wstring::~wstring(&Srca);
  std::wstring::~wstring(v29);
  v15 = (void *)std::wstring::wstring(v30, &v25);
  v16 = WindowsMidiServicesInternal::TrimmedWStringCopy(&Srca, v15);
  std::wstring::operator=(&v25, v16);
  std::wstring::~wstring(&Srca);
  if ( !a5 )
    goto LABEL_20;
  if ( a4 )
  {
    if ( a4 == 1 )
    {
      v22 = &v25;
      if ( *((_QWORD *)&v26 + 1) > 7u )
        v22 = (__int128 *)v25;
      *(_QWORD *)&v29[0] = v22;
      *((_QWORD *)&v29[0] + 1) = v26;
      winrt::to_string(v30, v29);
      v18 = "MIDIOUT{} ({})";
      *((_QWORD *)&v29[0] + 1) = 14;
      goto LABEL_10;
    }
LABEL_20:
    v23 = v26;
    *Src = v25;
    LOWORD(v25) = 0;
    *((_QWORD *)&v26 + 1) = 7;
    *(_QWORD *)&v26 = 0;
    Src[1] = v23;
    goto LABEL_21;
  }
  v17 = &v25;
  if ( *((_QWORD *)&v26 + 1) > 7u )
    v17 = (__int128 *)v25;
  *(_QWORD *)&v29[0] = v17;
  *((_QWORD *)&v29[0] + 1) = v26;
  winrt::to_string(v30, v29);
  v18 = "MIDIIN{} ({})";
  *((_QWORD *)&v29[0] + 1) = 13;
LABEL_10:
  *(_QWORD *)&v29[0] = v18;
  std::format<int,std::string>(&Srca);
  std::string::~string(v30);
  if ( *((_QWORD *)&v28 + 1) > 0xFu )
  {
    p_Srca = (__int128 *)Srca;
    v19 = (char *)(Srca + v28);
  }
  else
  {
    v19 = (char *)&Srca + v28;
    p_Srca = &Srca;
  }
  v21 = (_QWORD *)std::wstring::wstring(v30, p_Srca, v19);
  memset(v29, 0, sizeof(v29));
  if ( v21[3] > 7u )
    v21 = (_QWORD *)*v21;
  std::wstring::_Construct<1,unsigned short const *>(v29, v21);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v29);
  std::wstring::~wstring(v30);
  std::string::~string(&Srca);
LABEL_21:
  std::wstring::~wstring(&v25);
  return Src;
}

```

## disassembly

```asm
0x18002c688  push    rbp
0x18002c68a  push    rbx
0x18002c68b  push    rsi
0x18002c68c  push    rdi
0x18002c68d  push    r13
0x18002c68f  push    r14
0x18002c691  push    r15
0x18002c693  lea     rbp, [rsp-1Fh]
0x18002c698  sub     rsp, 0C0h
0x18002c69f  mov     rax, cs:__security_cookie
0x18002c6a6  xor     rax, rsp
0x18002c6a9  mov     [rbp+4Fh+var_40], rax
0x18002c6ad  mov     r14d, r9d
0x18002c6b0  mov     r15, r8
0x18002c6b3  mov     rsi, rdx
0x18002c6b6  mov     rdi, rcx
0x18002c6b9  xorps   xmm0, xmm0
0x18002c6bc  movups  [rbp+4Fh+var_C8], xmm0
0x18002c6c0  mov     qword ptr [rbp+4Fh+var_B8], 0
0x18002c6c8  mov     r13d, 7
0x18002c6ce  mov     qword ptr [rbp+4Fh+var_B8+8], r13
0x18002c6d2  xor     eax, eax
0x18002c6d4  mov     word ptr [rbp+4Fh+var_C8], ax
0x18002c6d8  lea     rcx, [rbp+4Fh+var_60]
0x18002c6dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c6e1  mov     rdx, rax; void *
0x18002c6e4  lea     rcx, [rbp+4Fh+Src]; Src
0x18002c6e8  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c6ed  mov     rbx, [rax+10h]
0x18002c6f1  lea     rcx, [rbp+4Fh+Src]; void *
0x18002c6f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c6fa  lea     rcx, [rbp+4Fh+var_60]
0x18002c6fe  test    rbx, rbx
0x18002c701  mov     rdx, rsi
0x18002c704  jnz     short loc_18002C709
0x18002c706  mov     rdx, r15
0x18002c709  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c70e  mov     rdx, rax; void *
0x18002c711  lea     rcx, [rbp+4Fh+var_80]; Src
0x18002c715  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c71a  mov     ebx, 1Fh
0x18002c71f  mov     r8d, ebx
0x18002c722  cmp     [rax+10h], rbx
0x18002c726  cmovb   r8, [rax+10h]
0x18002c72b  xorps   xmm1, xmm1
0x18002c72e  xorps   xmm0, xmm0
0x18002c731  cmp     [rax+18h], r13
0x18002c735  movdqu  [rbp+4Fh+var_98], xmm1
0x18002c73a  movups  [rbp+4Fh+Src], xmm0
0x18002c73e  jbe     short loc_18002C743
0x18002c740  mov     rax, [rax]
0x18002c743  mov     rdx, rax
0x18002c746  lea     rcx, [rbp+4Fh+Src]
0x18002c74a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c74f  lea     rdx, [rbp+4Fh+Src]
0x18002c753  lea     rcx, [rbp+4Fh+var_C8]
0x18002c757  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c75c  lea     rcx, [rbp+4Fh+Src]; void *
0x18002c760  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c765  lea     rcx, [rbp+4Fh+var_80]; void *
0x18002c769  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c76e  lea     rdx, [rbp+4Fh+var_C8]
0x18002c772  lea     rcx, [rbp+4Fh+var_60]
0x18002c776  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c77b  mov     rdx, rax; void *
0x18002c77e  lea     rcx, [rbp+4Fh+Src]; Src
0x18002c782  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c787  mov     rdx, rax
0x18002c78a  lea     rcx, [rbp+4Fh+var_C8]
0x18002c78e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c793  lea     rcx, [rbp+4Fh+Src]; void *
0x18002c797  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c79c  movzx   esi, [rbp+4Fh+arg_20]
0x18002c7a0  test    sil, sil
0x18002c7a3  jz      loc_18002C8CF
0x18002c7a9  test    r14d, r14d
0x18002c7ac  jnz     loc_18002C888
0x18002c7b2  lea     rax, [rbp+4Fh+var_C8]
0x18002c7b6  cmp     qword ptr [rbp+4Fh+var_B8+8], r13
0x18002c7ba  cmova   rax, qword ptr [rbp+4Fh+var_C8]
0x18002c7bf  mov     qword ptr [rbp+4Fh+var_80], rax
0x18002c7c3  mov     rax, qword ptr [rbp+4Fh+var_B8]
0x18002c7c7  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x18002c7cb  lea     rdx, [rbp+4Fh+var_80]
0x18002c7cf  lea     rcx, [rbp+4Fh+var_60]
0x18002c7d3  call    ?to_string@winrt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; winrt::to_string(std::basic_string_view<ushort>)
0x18002c7d8  lea     ecx, [rsi+1]
0x18002c7db  mov     [rsp+0F0h+var_D0], ecx
0x18002c7df  lea     rcx, aMidiin; "MIDIIN{} ({})"
0x18002c7e6  mov     qword ptr [rbp+4Fh+var_80+8], 0Dh
0x18002c7ee  mov     qword ptr [rbp+4Fh+var_80], rcx
0x18002c7f2  mov     r9, rax
0x18002c7f5  lea     r8, [rsp+0F0h+var_D0]
0x18002c7fa  lea     rdx, [rbp+4Fh+var_80]
0x18002c7fe  lea     rcx, [rbp+4Fh+Src]; Src
0x18002c802  call    ??$format@HV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@U?$basic_format_string@DHV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@$$QEAH$$QEAV10@@Z; std::format<int,std::string>(std::basic_format_string<char,int,std::string>,int &&,std::string &&)
0x18002c807  lea     rcx, [rbp+4Fh+var_60]
0x18002c80b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c810  mov     r8, qword ptr [rbp+4Fh+var_98]
0x18002c814  cmp     qword ptr [rbp+4Fh+var_98+8], 0Fh
0x18002c819  ja      short loc_18002C828
0x18002c81b  lea     rcx, [rbp+4Fh+Src]
0x18002c81f  add     r8, rcx
0x18002c822  lea     rdx, [rbp+4Fh+Src]
0x18002c826  jmp     short loc_18002C82F
0x18002c828  mov     rdx, qword ptr [rbp+4Fh+Src]
0x18002c82c  add     r8, rdx
0x18002c82f  lea     rcx, [rbp+4Fh+var_60]
0x18002c833  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<ushort> const &)
0x18002c838  xorps   xmm0, xmm0
0x18002c83b  xorps   xmm1, xmm1
0x18002c83e  movups  [rbp+4Fh+var_80], xmm0
0x18002c842  movdqu  [rbp+4Fh+var_70], xmm1
0x18002c847  cmp     [rax+10h], rbx
0x18002c84b  cmovb   rbx, [rax+10h]
0x18002c850  cmp     [rax+18h], r13
0x18002c854  jbe     short loc_18002C859
0x18002c856  mov     rax, [rax]
0x18002c859  mov     r8, rbx
0x18002c85c  mov     rdx, rax
0x18002c85f  lea     rcx, [rbp+4Fh+var_80]
0x18002c863  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c868  lea     rdx, [rbp+4Fh+var_80]; void *
0x18002c86c  mov     rcx, rdi; Src
0x18002c86f  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c874  lea     rcx, [rbp+4Fh+var_60]; void *
0x18002c878  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c87d  lea     rcx, [rbp+4Fh+Src]
0x18002c881  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c886  jmp     short loc_18002C8EC
0x18002c888  cmp     r14d, 1
0x18002c88c  jnz     short loc_18002C8CF
0x18002c88e  lea     rax, [rbp+4Fh+var_C8]
0x18002c892  cmp     qword ptr [rbp+4Fh+var_B8+8], r13
0x18002c896  cmova   rax, qword ptr [rbp+4Fh+var_C8]
0x18002c89b  mov     qword ptr [rbp+4Fh+var_80], rax
0x18002c89f  mov     rax, qword ptr [rbp+4Fh+var_B8]
0x18002c8a3  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x18002c8a7  lea     rdx, [rbp+4Fh+var_80]
0x18002c8ab  lea     rcx, [rbp+4Fh+var_60]
0x18002c8af  call    ?to_string@winrt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; winrt::to_string(std::basic_string_view<ushort>)
0x18002c8b4  lea     ecx, [rsi+1]
0x18002c8b7  mov     [rsp+0F0h+var_D0], ecx
0x18002c8bb  lea     rcx, aMidiout; "MIDIOUT{} ({})"
0x18002c8c2  mov     qword ptr [rbp+4Fh+var_80+8], 0Eh
0x18002c8ca  jmp     loc_18002C7EE
0x18002c8cf  movups  xmm0, [rbp+4Fh+var_C8]
0x18002c8d3  xor     eax, eax
0x18002c8d5  movups  xmm1, [rbp+4Fh+var_B8]
0x18002c8d9  movups  xmmword ptr [rdi], xmm0
0x18002c8dc  mov     word ptr [rbp+4Fh+var_C8], ax
0x18002c8e0  mov     qword ptr [rbp+4Fh+var_B8+8], r13
0x18002c8e4  mov     qword ptr [rbp+4Fh+var_B8], rax
0x18002c8e8  movups  xmmword ptr [rdi+10h], xmm1
0x18002c8ec  lea     rcx, [rbp+4Fh+var_C8]; void *
0x18002c8f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c8f5  mov     rax, rdi
0x18002c8f8  mov     rcx, [rbp+4Fh+var_40]
0x18002c8fc  xor     rcx, rsp; StackCookie
0x18002c8ff  call    __security_check_cookie
0x18002c904  add     rsp, 0C0h
0x18002c90b  pop     r15
0x18002c90d  pop     r14
0x18002c90f  pop     r13
0x18002c911  pop     rdi
0x18002c912  pop     rsi
0x18002c913  pop     rbx
0x18002c914  pop     rbp
0x18002c915  retn
```
