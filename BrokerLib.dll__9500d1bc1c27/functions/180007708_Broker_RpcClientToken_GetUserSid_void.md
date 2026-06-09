# Broker::RpcClientToken::GetUserSid(void)

- ea: `0x180007708`
- end: `0x180007a06`
- name: `?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007350`

## callees

- `0x180004be0`
- `0x180004e38`
- `0x180006cec`
- `0x180007708`
- `0x180008340`
- `0x180009e94`
- `0x1800139f8`
- `0x180014a40`
- `0x1800164f6`
- `0x1800165b6`
- `0x1800165c2`
- `0x1800165da`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800077ee`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800077ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007782`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800077d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007782`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800077d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000778c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000778c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Broker::RpcClientToken::GetUserSid(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  char *v5; // rdi
  signed __int64 v6; // r15
  __int64 v7; // rbx
  __int64 LengthSid; // r9
  __int64 v9; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 v13; // r14
  DWORD LastError; // eax
  char *v15; // rax
  size_t v16; // rbx
  LPVOID TokenInformation[2]; // [rsp+38h] [rbp-39h] BYREF
  char *v18; // [rsp+48h] [rbp-29h]
  int v19; // [rsp+50h] [rbp-21h]
  void **v20; // [rsp+58h] [rbp-19h] BYREF
  __int128 v21; // [rsp+60h] [rbp-11h] BYREF
  int v22; // [rsp+70h] [rbp-1h]
  DWORD v23; // [rsp+78h] [rbp+7h]
  void **pExceptionObject; // [rsp+80h] [rbp+Fh] BYREF
  __int128 v25; // [rsp+88h] [rbp+17h] BYREF
  int v26; // [rsp+98h] [rbp+27h]
  DWORD v27; // [rsp+A0h] [rbp+2Fh]
  DWORD TokenInformationLength; // [rsp+D8h] [rbp+67h] BYREF
  _QWORD *v29; // [rsp+E0h] [rbp+6Fh]

  v29 = a2;
  *(_OWORD *)TokenInformation = 0;
  v18 = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v19 = 1;
  TokenInformationLength = 0;
  if ( GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, 0, 0, &TokenInformationLength) )
    goto LABEL_6;
  if ( GetLastError() != 122 )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&pExceptionObject);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v27);
    std::exception::exception((std::exception *)&v20, (const struct std::exception *)&pExceptionObject);
    v22 = v26;
    v20 = &Broker::Win32Error::`vftable';
    v23 = v27;
    throw (Broker::Win32Error *)&v20;
  }
  v4 = TokenInformationLength;
  v5 = (char *)TokenInformation[0];
  v6 = (char *)TokenInformation[1] - (char *)TokenInformation[0];
  if ( (LPVOID)TokenInformationLength > (LPVOID)((char *)TokenInformation[1] - (char *)TokenInformation[0]) )
  {
    v11 = v18 - (char *)TokenInformation[0];
    if ( TokenInformationLength > (unsigned __int64)(v18 - (char *)TokenInformation[0]) )
    {
      v12 = v11 >> 1;
      v13 = 0x7FFFFFFFFFFFFFFFLL;
      if ( v11 <= 0x7FFFFFFFFFFFFFFFLL - (v11 >> 1) )
      {
        v13 = v12 + v11;
        if ( v12 + v11 < TokenInformationLength )
          v13 = TokenInformationLength;
      }
      v5 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v13);
      memset_0(&v5[v6], 0, v4 - v6);
      memmove_0(v5, TokenInformation[0], (char *)TokenInformation[1] - (char *)TokenInformation[0]);
      if ( TokenInformation[0] )
        std::_Deallocate<16>(TokenInformation[0], v18 - (char *)TokenInformation[0]);
      TokenInformation[0] = v5;
      TokenInformation[1] = &v5[v4];
      v18 = &v5[v13];
      goto LABEL_5;
    }
    v16 = TokenInformationLength - v6;
    memset_0(TokenInformation[1], 0, v16);
    v15 = (char *)TokenInformation[1] + v16;
    v5 = (char *)TokenInformation[0];
  }
  else
  {
    if ( (LPVOID)TokenInformationLength >= (LPVOID)((char *)TokenInformation[1] - (char *)TokenInformation[0]) )
      goto LABEL_5;
    v15 = (char *)TokenInformation[0] + TokenInformationLength;
  }
  TokenInformation[1] = v15;
LABEL_5:
  if ( !GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
  {
    v21 = 0;
    v22 = 1;
    v20 = &Broker::Win32Error::`vftable';
    LastError = GetLastError();
    v23 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
    pExceptionObject = &std::exception::`vftable';
    v25 = 0;
    o___std_exception_copy_0(&v21, &v25);
    v26 = v22;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v27 = v23;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
LABEL_6:
  v7 = *(_QWORD *)TokenInformation[0];
  LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
  v9 = *a2;
  if ( a2[1] != *a2 )
    a2[1] = v9;
  std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(a2, v9, v7, LengthSid);
  std::vector<unsigned char>::_Tidy(TokenInformation);
  return a2;
}

```

## disassembly

```asm
0x180007708  mov     rax, rsp
0x18000770b  mov     [rax+18h], rbx
0x18000770f  mov     [rax+20h], rsi
0x180007713  mov     [rax+10h], rdx
0x180007717  push    rbp
0x180007718  push    rdi
0x180007719  push    r13
0x18000771b  push    r14
0x18000771d  push    r15
0x18000771f  lea     rbp, [rax-5Fh]
0x180007723  sub     rsp, 0A0h
0x18000772a  mov     rsi, rdx
0x18000772d  mov     r13, rcx
0x180007730  mov     [rbp+57h+var_78], 0
0x180007737  xorps   xmm0, xmm0
0x18000773a  movdqu  xmmword ptr [rbp+57h+TokenInformation], xmm0
0x18000773f  mov     [rbp+57h+var_80], 0
0x180007747  mov     qword ptr [rdx], 0
0x18000774e  mov     qword ptr [rdx+8], 0
0x180007756  mov     qword ptr [rdx+10h], 0
0x18000775e  mov     ecx, 1
0x180007763  mov     [rbp+57h+var_78], ecx
0x180007766  mov     [rbp+57h+TokenInformationLength], 0
0x18000776d  lea     rax, [rbp+57h+TokenInformationLength]
0x180007771  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180007776  xor     r9d, r9d; TokenInformationLength
0x180007779  xor     r8d, r8d; TokenInformation
0x18000777c  mov     edx, ecx; TokenInformationClass
0x18000777e  mov     rcx, [r13+8]; TokenHandle
0x180007782  call    cs:__imp_GetTokenInformation
0x180007788  test    eax, eax
0x18000778a  jnz     short loc_1800077E4
0x18000778c  call    cs:__imp_GetLastError
0x180007792  cmp     eax, 7Ah ; 'z'
0x180007795  jnz     loc_180007932
0x18000779b  mov     ebx, [rbp+57h+TokenInformationLength]
0x18000779e  mov     rdi, [rbp+57h+TokenInformation]
0x1800077a2  mov     r14, [rbp+57h+TokenInformation+8]
0x1800077a6  mov     r15, r14
0x1800077a9  sub     r15, rdi
0x1800077ac  cmp     rbx, r15
0x1800077af  ja      loc_180007838
0x1800077b5  jb      loc_18000799D
0x1800077bb  lea     rax, [rbp+57h+TokenInformationLength]
0x1800077bf  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1800077c4  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800077c8  mov     r8, rdi; TokenInformation
0x1800077cb  mov     ebx, 1
0x1800077d0  mov     edx, ebx; TokenInformationClass
0x1800077d2  mov     rcx, [r13+8]; TokenHandle
0x1800077d6  call    cs:__imp_GetTokenInformation
0x1800077dc  test    eax, eax
0x1800077de  jz      loc_1800078C3
0x1800077e4  mov     rax, [rbp+57h+TokenInformation]
0x1800077e8  mov     rbx, [rax]
0x1800077eb  mov     rcx, rbx; pSid
0x1800077ee  call    cs:__imp_GetLengthSid
0x1800077f4  mov     r9d, eax
0x1800077f7  mov     rdx, [rsi]
0x1800077fa  cmp     [rsi+8], rdx
0x1800077fe  jnz     loc_1800079FC
0x180007804  mov     r8, rbx
0x180007807  mov     rcx, rsi
0x18000780a  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000780f  nop
0x180007810  lea     rcx, [rbp+57h+TokenInformation]
0x180007814  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007819  mov     rax, rsi
0x18000781c  lea     r11, [rsp+0C0h+var_20]
0x180007824  mov     rbx, [r11+40h]
0x180007828  mov     rsi, [r11+48h]
0x18000782c  mov     rsp, r11
0x18000782f  pop     r15
0x180007831  pop     r14
0x180007833  pop     r13
0x180007835  pop     rdi
0x180007836  pop     rbp
0x180007837  retn
0x180007838  mov     rcx, [rbp+57h+var_80]
0x18000783c  sub     rcx, rdi
0x18000783f  cmp     rbx, rcx
0x180007842  jbe     loc_1800079B4
0x180007848  mov     rdx, rcx
0x18000784b  shr     rdx, 1
0x18000784e  mov     r14, 7FFFFFFFFFFFFFFFh
0x180007858  mov     rax, r14
0x18000785b  sub     rax, rdx
0x18000785e  cmp     rcx, rax
0x180007861  ja      short loc_18000786E
0x180007863  lea     r14, [rdx+rcx]
0x180007867  cmp     r14, rbx
0x18000786a  cmovb   r14, rbx
0x18000786e  mov     rcx, r14
0x180007871  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180007876  mov     rdi, rax
0x180007879  mov     r8, rbx
0x18000787c  sub     r8, r15; Size
0x18000787f  lea     rcx, [r15+rax]; void *
0x180007883  xor     edx, edx; Val
0x180007885  call    memset_0
0x18000788a  mov     rdx, [rbp+57h+TokenInformation]; Src
0x18000788e  mov     r8, [rbp+57h+TokenInformation+8]
0x180007892  sub     r8, rdx; Size
0x180007895  mov     rcx, rdi; void *
0x180007898  call    memmove_0
0x18000789d  mov     rcx, [rbp+57h+TokenInformation]
0x1800078a1  test    rcx, rcx
0x1800078a4  jnz     loc_1800079A3
0x1800078aa  mov     [rbp+57h+TokenInformation], rdi
0x1800078ae  lea     rax, [rbx+rdi]
0x1800078b2  mov     [rbp+57h+TokenInformation+8], rax
0x1800078b6  lea     rax, [r14+rdi]
0x1800078ba  mov     [rbp+57h+var_80], rax
0x1800078be  jmp     loc_1800077BB
0x1800078c3  xorps   xmm0, xmm0
0x1800078c6  movups  [rbp+57h+var_68], xmm0
0x1800078ca  mov     [rbp+57h+var_58], ebx
0x1800078cd  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800078d4  mov     [rbp+57h+var_70], rbx
0x1800078d8  call    cs:__imp_GetLastError
0x1800078de  mov     [rbp+57h+var_50], eax
0x1800078e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078e8  test    byte ptr [rcx+1Ch], 8
0x1800078ec  jnz     loc_1800079D5
0x1800078f2  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800078f9  mov     [rbp+57h+pExceptionObject], rax
0x1800078fd  xorps   xmm0, xmm0
0x180007900  movups  [rbp+57h+var_40], xmm0
0x180007904  lea     rdx, [rbp+57h+var_40]
0x180007908  lea     rcx, [rbp+57h+var_68]
0x18000790c  call    _o___std_exception_copy_0
0x180007911  mov     eax, [rbp+57h+var_58]
0x180007914  mov     [rbp+57h+var_30], eax
0x180007917  mov     [rbp+57h+pExceptionObject], rbx
0x18000791b  mov     eax, [rbp+57h+var_50]
0x18000791e  mov     [rbp+57h+var_28], eax
0x180007921  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180007928  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000792c  call    _CxxThrowException_0
0x180007932  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180007936  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000793b  nop
0x18000793c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007943  test    byte ptr [rcx+1Ch], 8
0x180007947  jz      short loc_180007968
0x180007949  cmp     byte ptr [rcx+19h], 2
0x18000794d  jb      short loc_180007968
0x18000794f  mov     edx, 14h
0x180007954  mov     r9d, [rbp+57h+var_28]
0x180007958  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000795f  mov     rcx, [rcx+10h]
0x180007963  call    WPP_SF_d
0x180007968  lea     rdx, [rbp+57h+pExceptionObject]; struct std::exception *
0x18000796c  lea     rcx, [rbp+57h+var_70]; this
0x180007970  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180007975  mov     eax, [rbp+57h+var_30]
0x180007978  mov     [rbp+57h+var_58], eax
0x18000797b  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180007982  mov     [rbp+57h+var_70], rbx
0x180007986  mov     eax, [rbp+57h+var_28]
0x180007989  mov     [rbp+57h+var_50], eax
0x18000798c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180007993  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x180007997  call    _CxxThrowException_0
0x18000799d  lea     rax, [rbx+rdi]
0x1800079a1  jmp     short loc_1800079CC
0x1800079a3  mov     rdx, [rbp+57h+var_80]
0x1800079a7  sub     rdx, rcx
0x1800079aa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800079af  jmp     loc_1800078AA
0x1800079b4  sub     rbx, r15
0x1800079b7  mov     r8, rbx; Size
0x1800079ba  xor     edx, edx; Val
0x1800079bc  mov     rcx, r14; void *
0x1800079bf  call    memset_0
0x1800079c4  lea     rax, [rbx+r14]
0x1800079c8  mov     rdi, [rbp+57h+TokenInformation]
0x1800079cc  mov     [rbp+57h+TokenInformation+8], rax
0x1800079d0  jmp     loc_1800077BB
0x1800079d5  cmp     byte ptr [rcx+19h], 2
0x1800079d9  jb      loc_1800078F2
0x1800079df  mov     edx, 15h
0x1800079e4  mov     r9d, eax
0x1800079e7  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800079ee  mov     rcx, [rcx+10h]
0x1800079f2  call    WPP_SF_d
0x1800079f7  jmp     loc_1800078F2
0x1800079fc  mov     [rsi+8], rdx
0x180007a00  jmp     loc_180007804
```
