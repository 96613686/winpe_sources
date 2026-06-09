# PCLmWriter::NameObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x1800196c0`
- end: `0x180019922`
- name: `?Serialize@NameObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `610`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180018fb0`
- `0x180019db0`

## callees

- `0x1800015f0`
- `0x18000bffc`
- `0x180010050`
- `0x1800101cc`
- `0x180010594`
- `0x180010618`
- `0x180010718`
- `0x1800113c4`
- `0x180017770`
- `0x180018770`
- `0x1800196c0`
- `0x180019f74`
- `0x18001a140`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019863`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019859`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019859`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PCLmWriter::NameObject::Serialize(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int64 i; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // ecx
  __int64 v11; // r8
  CHAR *v12; // rdx
  unsigned __int64 j; // rax
  unsigned __int64 k; // rax
  unsigned int v15; // eax
  signed int LastError; // eax
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  std::_Ref_count_base *v20; // rcx
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-29h]
  _BYTE v22[16]; // [rsp+48h] [rbp-1h] BYREF
  unsigned __int64 v23; // [rsp+58h] [rbp+Fh]
  unsigned __int64 v24; // [rsp+60h] [rbp+17h]
  CHAR MultiByteStr[4]; // [rsp+68h] [rbp+1Fh] BYREF
  char v26; // [rsp+6Ch] [rbp+23h]
  WCHAR WideCharStr[4]; // [rsp+70h] [rbp+27h] BYREF
  __int16 v28; // [rsp+78h] [rbp+2Fh]

  std::string::string(v22);
  v5 = *(_QWORD *)(a1 + 40) + 1LL;
  v6 = v23;
  if ( v23 <= v5 && v24 != v5 )
  {
    if ( v24 >= v5 )
    {
      if ( v5 <= 0xF && (unsigned __int8)std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v22) )
        std::string::_Become_small(v22);
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(v22, v5 - v23);
      v23 = v6;
    }
  }
  LOBYTE(v4) = 47;
  std::string::push_back(v22, v4);
  for ( i = 1; i < *(_QWORD *)(a1 + 40); ++i )
  {
    v8 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 24);
    v10 = *(char *)(v8 + i);
    if ( *(_BYTE *)(v8 + i) == 35 )
    {
      v11 = 3;
      v12 = "#23";
    }
    else if ( (_BYTE)v10 == 32 )
    {
      v11 = 3;
      v12 = "#20";
    }
    else
    {
      for ( j = 0; j < 0xA; ++j )
      {
        if ( *(_BYTE *)(j + v9 + 154280) == (_BYTE)v10 )
          goto LABEL_23;
      }
      for ( k = 0; k < 6; ++k )
      {
        if ( *(_BYTE *)(k + v9 + 154292) == (_BYTE)v10 )
          goto LABEL_23;
      }
      if ( (unsigned __int8)(v10 - 33) <= 0x5Du )
      {
        LOBYTE(v9) = v10;
        std::string::push_back(v22, v9);
        continue;
      }
LABEL_23:
      *(_DWORD *)MultiByteStr = 0;
      v26 = 0;
      *(_QWORD *)WideCharStr = 0;
      v28 = 0;
      v15 = StringCchPrintfW(WideCharStr, 5u, L"#%02X", v10);
      PrintCore::ThrowIfError(
        (PrintCore *)v15,
        (int)"Unspecified.",
        "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfobjects.cpp",
        (const char *)0x10A,
        lpMultiByteStr);
      if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, 5, MultiByteStr, 5, 0, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PrintCore::ThrowIfError(
          (PrintCore *)(unsigned int)LastError,
          (int)"Unspecified.",
          "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\pdfobjects.cpp",
          (const char *)0x10D,
          lpMultiByteStr);
      }
      v11 = -1;
      do
        ++v11;
      while ( MultiByteStr[v11] );
      v12 = MultiByteStr;
    }
    std::string::_Append<char>(v22, v12, v11);
  }
  v17 = std::_String_val<std::_Simple_types<char>>::_Myptr(v22);
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(v18 + 24))(v19, v17, (unsigned int)v23);
  std::string::_Tidy_deallocate(v22);
  v20 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
}

```

## disassembly

```asm
0x1800196c0  mov     [rsp-8+arg_10], rbx
0x1800196c5  mov     [rsp-8+arg_18], rsi
0x1800196ca  push    rbp
0x1800196cb  push    rdi
0x1800196cc  push    r14
0x1800196ce  lea     rbp, [rsp-47h]
0x1800196d3  sub     rsp, 90h
0x1800196da  mov     rax, cs:__security_cookie
0x1800196e1  xor     rax, rsp
0x1800196e4  mov     [rbp+57h+var_20], rax
0x1800196e8  mov     rsi, rdx
0x1800196eb  mov     rdi, rcx
0x1800196ee  mov     [rbp+57h+var_60], rdx
0x1800196f2  lea     rcx, [rbp+57h+var_58]
0x1800196f6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800196fb  nop
0x1800196fc  mov     rax, [rdi+28h]
0x180019700  inc     rax
0x180019703  mov     rbx, [rbp+57h+var_48]
0x180019707  cmp     rbx, rax
0x18001970a  ja      short loc_180019745
0x18001970c  cmp     [rbp+57h+var_40], rax
0x180019710  jz      short loc_180019745
0x180019712  jnb     short loc_180019729
0x180019714  sub     rax, rbx
0x180019717  mov     rdx, rax
0x18001971a  lea     rcx, [rbp+57h+var_58]
0x18001971e  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x180019723  mov     [rbp+57h+var_48], rbx
0x180019727  jmp     short loc_180019745
0x180019729  cmp     rax, 0Fh
0x18001972d  ja      short loc_180019745
0x18001972f  lea     rcx, [rbp+57h+var_58]
0x180019733  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x180019738  test    al, al
0x18001973a  jz      short loc_180019745
0x18001973c  lea     rcx, [rbp+57h+var_58]
0x180019740  call    ?_Become_small@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Become_small(void)
0x180019745  mov     dl, 2Fh ; '/'
0x180019747  lea     rcx, [rbp+57h+var_58]
0x18001974b  call    ?push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z; std::string::push_back(char)
0x180019750  mov     ebx, 1
0x180019755  cmp     [rdi+28h], rbx
0x180019759  jbe     loc_1800198C3
0x18001975f  lea     rdx, cs:180000000h
0x180019766  lea     rcx, [rdi+18h]
0x18001976a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001976f  movsx   ecx, byte ptr [rax+rbx]
0x180019773  cmp     cl, 23h ; '#'
0x180019776  jnz     short loc_18001978A
0x180019778  mov     r8d, 3
0x18001977e  lea     rdx, a23; "#23"
0x180019785  jmp     loc_1800198A6
0x18001978a  cmp     cl, 20h ; ' '
0x18001978d  jnz     short loc_1800197A1
0x18001978f  mov     r8d, 3
0x180019795  lea     rdx, a20; "#20"
0x18001979c  jmp     loc_1800198A6
0x1800197a1  xor     eax, eax
0x1800197a3  cmp     rax, 0Ah
0x1800197a7  jnb     short loc_1800197B7
0x1800197a9  cmp     [rax+rdx+25AA8h], cl
0x1800197b0  jz      short loc_1800197E4
0x1800197b2  inc     rax
0x1800197b5  jmp     short loc_1800197A3
0x1800197b7  xor     eax, eax
0x1800197b9  cmp     rax, 6
0x1800197bd  jnb     short loc_1800197CD
0x1800197bf  cmp     [rax+rdx+25AB4h], cl
0x1800197c6  jz      short loc_1800197E4
0x1800197c8  inc     rax
0x1800197cb  jmp     short loc_1800197B9
0x1800197cd  lea     eax, [rcx-21h]
0x1800197d0  cmp     al, 5Dh ; ']'
0x1800197d2  ja      short loc_1800197E4
0x1800197d4  mov     dl, cl
0x1800197d6  lea     rcx, [rbp+57h+var_58]
0x1800197da  call    ?push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z; std::string::push_back(char)
0x1800197df  jmp     loc_1800198AF
0x1800197e4  xor     eax, eax
0x1800197e6  mov     dword ptr [rbp+57h+MultiByteStr], eax
0x1800197e9  mov     [rbp+57h+var_34], al
0x1800197ec  mov     qword ptr [rbp+57h+WideCharStr], rax
0x1800197f0  mov     [rbp+57h+var_28], ax
0x1800197f4  mov     r9d, ecx
0x1800197f7  lea     r8, a02x; "#%02X"
0x1800197fe  lea     edx, [rax+5]; unsigned __int64
0x180019801  lea     rcx, [rbp+57h+WideCharStr]; unsigned __int16 *
0x180019805  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001980a  mov     r9d, 10Ah; char *
0x180019810  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x180019817  lea     rdx, aUnspecified; "Unspecified."
0x18001981e  mov     ecx, eax; this
0x180019820  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180019825  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001982e  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x180019837  mov     [rsp+0A0h+cbMultiByte], 5; cbMultiByte
0x18001983f  lea     rax, [rbp+57h+MultiByteStr]
0x180019843  mov     [rsp+0A0h+lpMultiByteStr], rax; unsigned int
0x180019848  mov     r9d, 5; cchWideChar
0x18001984e  lea     r8, [rbp+57h+WideCharStr]; lpWideCharStr
0x180019852  xor     edx, edx; dwFlags
0x180019854  mov     ecx, 0FDE9h; CodePage
0x180019859  call    cs:__imp_WideCharToMultiByte
0x18001985f  test    eax, eax
0x180019861  jnz     short loc_180019890
0x180019863  call    cs:__imp_GetLastError
0x180019869  test    eax, eax
0x18001986b  jle     short loc_180019875
0x18001986d  movzx   eax, ax
0x180019870  or      eax, 80070000h
0x180019875  mov     r9d, 10Dh; char *
0x18001987b  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x180019882  lea     rdx, aUnspecified; "Unspecified."
0x180019889  mov     ecx, eax; this
0x18001988b  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180019890  lea     rax, [rbp+57h+MultiByteStr]
0x180019894  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019898  inc     r8
0x18001989b  cmp     byte ptr [rax+r8], 0
0x1800198a0  jnz     short loc_180019898
0x1800198a2  lea     rdx, [rbp+57h+MultiByteStr]
0x1800198a6  lea     rcx, [rbp+57h+var_58]
0x1800198aa  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800198af  inc     rbx
0x1800198b2  cmp     rbx, [rdi+28h]
0x1800198b6  lea     rdx, cs:180000000h
0x1800198bd  jb      loc_180019766
0x1800198c3  mov     r9, [rsi]
0x1800198c6  mov     r8, [r9]
0x1800198c9  lea     rcx, [rbp+57h+var_58]
0x1800198cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800198d2  mov     rdx, rax
0x1800198d5  mov     rax, [r8+18h]
0x1800198d9  mov     r8d, dword ptr [rbp+57h+var_48]
0x1800198dd  mov     rcx, r9
0x1800198e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198e5  nop
0x1800198e6  lea     rcx, [rbp+57h+var_58]
0x1800198ea  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800198ef  nop
0x1800198f0  mov     rcx, [rsi+8]; this
0x1800198f4  test    rcx, rcx
0x1800198f7  jz      short loc_1800198FE
0x1800198f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800198fe  mov     rcx, [rbp+57h+var_20]
0x180019902  xor     rcx, rsp; StackCookie
0x180019905  call    __security_check_cookie
0x18001990a  lea     r11, [rsp+0A0h+var_10]
0x180019912  mov     rbx, [r11+30h]
0x180019916  mov     rsi, [r11+38h]
0x18001991a  mov     rsp, r11
0x18001991d  pop     r14
0x18001991f  pop     rdi
0x180019920  pop     rbp
0x180019921  retn
```
