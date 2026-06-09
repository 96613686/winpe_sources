# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x182d467f0`
- end: `0x182d469d2`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `482`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x182d46e30`
- `0x182d478a0`
- `0x182d47990`

## callees

- `0x182d467f0`
- `0x182d46c40`
- `0x182d46d50`
- `0x182dc4440`
- `0x1832c3a30`
- `0x1832ce3b0`

## import_xrefs

- `MSVCP140!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x182d468bc`
- `MSVCP140!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x182d468bc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4696d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4697d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4698d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4699a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4696d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4697d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4698d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d4699a`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x182d4690c`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x182d4690c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  void **v3; // rcx
  unsigned __int64 v4; // r9
  void **v5; // rdx
  void **v6; // r8
  int v7; // eax
  int v8; // eax
  void **v9; // rax
  size_t v10; // rbx
  void **v11; // rax
  size_t v12; // rax
  char v13; // bl
  void **v14; // rax
  unsigned __int64 v15; // rcx
  void **v16; // [rsp+38h] [rbp-38h] BYREF
  void *Buffer[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h]
  unsigned __int64 v19; // [rsp+58h] [rbp-18h]

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL) == -1 )
    return 0;
  v19 = 15;
  v18 = 0;
  LOBYTE(Buffer[0]) = 0;
  std::string::assign(Buffer, 8u);
LABEL_6:
  v3 = (void **)Buffer[0];
  v4 = v19;
  while ( 1 )
  {
    v5 = Buffer;
    if ( v4 >= 0x10 )
      v5 = v3;
    v6 = Buffer;
    if ( v4 >= 0x10 )
      v6 = v3;
    v7 = std::codecvt<char,char,_Mbstatet>::unshift(*(_QWORD *)(a1 + 104), a1 + 116, v6, (char *)v5 + v18, &v16);
    if ( !v7 )
    {
      *(_BYTE *)(a1 + 113) = 0;
      goto LABEL_15;
    }
    v8 = v7 - 1;
    if ( v8 )
      break;
LABEL_15:
    v9 = Buffer;
    v3 = (void **)Buffer[0];
    v4 = v19;
    if ( v19 >= 0x10 )
      v9 = (void **)Buffer[0];
    v10 = (char *)v16 - (char *)v9;
    if ( v16 != v9 )
    {
      v11 = Buffer;
      if ( v19 >= 0x10 )
        v11 = (void **)Buffer[0];
      v12 = fwrite(v11, 1u, v10, *(FILE **)(a1 + 128));
      v4 = v19;
      v3 = (void **)Buffer[0];
      if ( v10 != v12 )
        goto LABEL_25;
    }
    if ( !*(_BYTE *)(a1 + 113) )
      goto LABEL_26;
    if ( !v10 )
    {
      std::string::append(Buffer, 8, 0);
      goto LABEL_6;
    }
  }
  v4 = v19;
  v3 = (void **)Buffer[0];
  if ( v8 != 2 )
  {
LABEL_25:
    v13 = 0;
    goto LABEL_27;
  }
LABEL_26:
  v13 = 1;
LABEL_27:
  if ( v4 >= 0x10 )
  {
    if ( v4 + 1 >= 0x1000 )
    {
      if ( ((__int64)Buffer[0] & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v14 = (void **)*(v3 - 1);
      if ( v14 >= v3 )
        _invalid_parameter_noinfo_noreturn();
      v15 = (char *)v3 - (char *)v14;
      if ( v15 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v15 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v3 = v14;
    }
    operator delete(v3);
  }
  return v13;
}

```

## disassembly

```asm
0x182d467f0  mov     rax, rsp
0x182d467f3  push    rbp
0x182d467f4  mov     rbp, rsp
0x182d467f7  sub     rsp, 70h
0x182d467fb  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x182d46803  mov     [rax+10h], rbx
0x182d46807  mov     [rax+18h], rsi
0x182d4680b  mov     [rax+20h], rdi
0x182d4680f  mov     rax, cs:__security_cookie
0x182d46816  xor     rax, rsp
0x182d46819  mov     [rbp+var_10], rax
0x182d4681d  mov     rdi, rcx
0x182d46820  cmp     qword ptr [rcx+68h], 0
0x182d46825  jz      loc_182D469AE
0x182d4682b  cmp     byte ptr [rcx+71h], 0
0x182d4682f  jz      loc_182D469AE
0x182d46835  mov     rax, [rcx]
0x182d46838  mov     rbx, [rax+18h]
0x182d4683c  mov     rcx, rbx; this
0x182d4683f  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x182d46845  or      edx, 0FFFFFFFFh
0x182d46848  mov     rcx, rdi
0x182d4684b  call    rbx
0x182d4684d  cmp     eax, 0FFFFFFFFh
0x182d46850  jnz     short loc_182D46859
0x182d46852  xor     al, al
0x182d46854  jmp     loc_182D469B0
0x182d46859  mov     [rbp+var_18], 0Fh
0x182d46861  mov     [rbp+var_20], 0
0x182d46869  mov     byte ptr [rbp+Buffer], 0
0x182d4686d  xor     r8d, r8d
0x182d46870  lea     edx, [r8+8]; Size
0x182d46874  lea     rcx, [rbp+Buffer]; void *
0x182d46878  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::assign(unsigned __int64,char)
0x182d4687d  nop
0x182d4687e  mov     rcx, [rbp+Buffer]
0x182d46882  mov     r9, [rbp+var_18]
0x182d46886  nop     word ptr [rax+rax+00000000h]
0x182d46890  lea     rdx, [rbp+Buffer]
0x182d46894  cmp     r9, 10h
0x182d46898  cmovnb  rdx, rcx
0x182d4689c  lea     r8, [rbp+Buffer]
0x182d468a0  cmovnb  r8, rcx
0x182d468a4  mov     r9, [rbp+var_20]
0x182d468a8  add     r9, rdx
0x182d468ab  lea     rax, [rbp+var_38]
0x182d468af  mov     [rsp+70h+var_50], rax
0x182d468b4  lea     rdx, [rdi+74h]
0x182d468b8  mov     rcx, [rdi+68h]
0x182d468bc  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x182d468c2  test    eax, eax
0x182d468c4  jz      short loc_182D468CD
0x182d468c6  sub     eax, 1
0x182d468c9  jnz     short loc_182D46942
0x182d468cb  jmp     short loc_182D468D1
0x182d468cd  mov     byte ptr [rdi+71h], 0
0x182d468d1  lea     rax, [rbp+Buffer]
0x182d468d5  mov     rcx, [rbp+Buffer]
0x182d468d9  mov     r9, [rbp+var_18]
0x182d468dd  cmp     r9, 10h
0x182d468e1  cmovnb  rax, rcx
0x182d468e5  mov     rbx, [rbp+var_38]
0x182d468e9  sub     rbx, rax
0x182d468ec  jz      short loc_182D4691F
0x182d468ee  lea     rax, [rbp+Buffer]
0x182d468f2  cmp     r9, 10h
0x182d468f6  cmovnb  rax, rcx
0x182d468fa  mov     r9, [rdi+80h]; Stream
0x182d46901  mov     r8, rbx; ElementCount
0x182d46904  mov     edx, 1; ElementSize
0x182d46909  mov     rcx, rax; Buffer
0x182d4690c  call    cs:__imp_fwrite
0x182d46912  mov     r9, [rbp+var_18]
0x182d46916  mov     rcx, [rbp+Buffer]
0x182d4691a  cmp     rbx, rax
0x182d4691d  jnz     short loc_182D4694F
0x182d4691f  cmp     byte ptr [rdi+71h], 0
0x182d46923  jz      short loc_182D46953
0x182d46925  test    rbx, rbx
0x182d46928  jnz     loc_182D46890
0x182d4692e  xor     r8d, r8d
0x182d46931  lea     edx, [rbx+8]
0x182d46934  lea     rcx, [rbp+Buffer]
0x182d46938  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x182d4693d  jmp     loc_182D4687E
0x182d46942  sub     eax, 2
0x182d46945  mov     r9, [rbp+var_18]
0x182d46949  mov     rcx, [rbp+Buffer]
0x182d4694d  jz      short loc_182D46953
0x182d4694f  xor     bl, bl
0x182d46951  jmp     short loc_182D46955
0x182d46953  mov     bl, 1
0x182d46955  cmp     r9, 10h
0x182d46959  jb      short loc_182D469A9
0x182d4695b  lea     rax, [r9+1]
0x182d4695f  cmp     rax, 1000h
0x182d46965  jb      short loc_182D469A4
0x182d46967  test    byte ptr [rbp+Buffer], 1Fh
0x182d4696b  jz      short loc_182D46974
0x182d4696d  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d46974  mov     rax, [rcx-8]
0x182d46978  cmp     rax, rcx
0x182d4697b  jb      short loc_182D46984
0x182d4697d  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d46984  sub     rcx, rax
0x182d46987  cmp     rcx, 8
0x182d4698b  jnb     short loc_182D46994
0x182d4698d  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d46994  cmp     rcx, 27h ; '''
0x182d46998  jbe     short loc_182D469A1
0x182d4699a  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d469a1  mov     rcx, rax; void *
0x182d469a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x182d469a9  movzx   eax, bl
0x182d469ac  jmp     short loc_182D469B0
0x182d469ae  mov     al, 1
0x182d469b0  mov     rcx, [rbp+var_10]
0x182d469b4  xor     rcx, rsp; StackCookie
0x182d469b7  call    __security_check_cookie
0x182d469bc  lea     r11, [rsp+70h+var_s0]
0x182d469c1  mov     rbx, [r11+18h]
0x182d469c5  mov     rsi, [r11+20h]
0x182d469c9  mov     rdi, [r11+28h]
0x182d469cd  mov     rsp, r11
0x182d469d0  pop     rbp
0x182d469d1  retn
```
