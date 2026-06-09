# Broker::RpcClientToken::GetUserSid(void)

- ea: `0x18000bbc0`
- end: `0x18000bead`
- name: `?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `749`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009340`
- `0x180009740`
- `0x18000a7d0`
- `0x18000cc40`
- `0x18000ec10`

## callees

- `0x1800030e0`
- `0x18000b168`
- `0x18000bbc0`
- `0x18000beb4`
- `0x18001732c`
- `0x180019130`
- `0x180019340`
- `0x1800195e0`
- `0x18001d364`
- `0x18001d9a0`
- `0x18001d9ac`
- `0x18001e0d8`
- `0x18002244c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc2c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc74`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc74`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000bc8c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000bc8c`

## pseudocode

```c
_QWORD *__fastcall Broker::RpcClientToken::GetUserSid(__int64 a1, _QWORD *a2)
{
  size_t v4; // rsi
  char *v5; // r14
  PSID v6; // rdi
  size_t LengthSid; // r9
  _BYTE *v8; // rdx
  void *v9; // rcx
  __int64 v11; // r12
  PSID *TokenInformation; // [rsp+30h] [rbp-49h]
  char *v13; // [rsp+40h] [rbp-39h]
  _QWORD v14[3]; // [rsp+50h] [rbp-29h] BYREF
  int v15; // [rsp+68h] [rbp-11h]
  unsigned int v16; // [rsp+70h] [rbp-9h]
  _QWORD pExceptionObject[3]; // [rsp+78h] [rbp-1h] BYREF
  int v18; // [rsp+90h] [rbp+17h]
  unsigned int v19; // [rsp+98h] [rbp+1Fh]
  DWORD TokenInformationLength; // [rsp+E0h] [rbp+67h] BYREF
  _QWORD *v21; // [rsp+E8h] [rbp+6Fh]
  void *v22; // [rsp+F0h] [rbp+77h] BYREF
  unsigned __int64 v23; // [rsp+F8h] [rbp+7Fh] BYREF

  v21 = a2;
  TokenInformation = 0;
  v13 = 0;
  std::vector<_GUID>::vector<_GUID>(a2);
  TokenInformationLength = 0;
  if ( !GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, 0, 0, &TokenInformationLength) )
  {
    if ( GetLastError() != 122 )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)v14);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v16);
      std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v14);
      v18 = v15;
      pExceptionObject[0] = &Broker::Win32Error::`vftable';
      v19 = v16;
      throw (Broker::Win32Error *)pExceptionObject;
    }
    v4 = TokenInformationLength;
    v5 = 0;
    if ( TokenInformationLength )
    {
      v11 = TokenInformationLength;
      v5 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(TokenInformationLength);
      memset_0(v5, 0, v4);
      memmove_0(v5, 0, 0);
      TokenInformation = (PSID *)v5;
      v13 = &v5[v11];
    }
    if ( !GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v19);
      std::exception::exception((std::exception *)v14, (const struct std::exception *)pExceptionObject);
      v15 = v18;
      v14[0] = &Broker::Win32Error::`vftable';
      v16 = v19;
      throw (Broker::Win32Error *)v14;
    }
  }
  v6 = *TokenInformation;
  LengthSid = GetLengthSid(*TokenInformation);
  v8 = (_BYTE *)*a2;
  if ( a2[1] != *a2 )
    a2[1] = v8;
  std::vector<unsigned char>::_Insert_counted_range<unsigned char *>((__int64)a2, v8, v6, LengthSid);
  v9 = TokenInformation;
  if ( TokenInformation )
  {
    v23 = v13 - (char *)TokenInformation;
    v22 = TokenInformation;
    if ( (unsigned __int64)(v13 - (char *)TokenInformation) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v22, &v23);
      v9 = v22;
    }
    operator delete(v9);
  }
  return a2;
}

```

## disassembly

```asm
0x18000bbc0  mov     [rsp-8+arg_8], rdx
0x18000bbc5  push    rbp
0x18000bbc6  push    rbx
0x18000bbc7  push    rsi
0x18000bbc8  push    rdi
0x18000bbc9  push    r12
0x18000bbcb  push    r14
0x18000bbcd  push    r15
0x18000bbcf  lea     rbp, [rsp-27h]
0x18000bbd4  sub     rsp, 0A0h
0x18000bbdb  mov     rbx, rdx
0x18000bbde  mov     r15, rcx
0x18000bbe1  xor     eax, eax
0x18000bbe3  mov     [rbp+57h+var_88], eax
0x18000bbe6  xorps   xmm0, xmm0
0x18000bbe9  movdqu  xmmword ptr [rbp+57h+TokenInformation], xmm0
0x18000bbee  mov     [rbp+57h+var_90], rax
0x18000bbf2  mov     rcx, rdx
0x18000bbf5  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000bbfa  mov     [rbp+57h+var_88], 1
0x18000bc01  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000bc05  mov     r9d, dword ptr [rbp+57h+TokenInformation+8]
0x18000bc09  sub     r9d, r8d; TokenInformationLength
0x18000bc0c  mov     [rbp+57h+TokenInformationLength], r9d
0x18000bc10  lea     rax, [rbp+57h+TokenInformationLength]
0x18000bc14  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18000bc19  mov     edx, 1; TokenInformationClass
0x18000bc1e  mov     rcx, [r15+8]; TokenHandle
0x18000bc22  call    cs:__imp_GetTokenInformation
0x18000bc28  test    eax, eax
0x18000bc2a  jnz     short loc_18000BC82
0x18000bc2c  call    cs:__imp_GetLastError
0x18000bc32  cmp     eax, 7Ah ; 'z'
0x18000bc35  jnz     loc_18000BD8E
0x18000bc3b  mov     esi, [rbp+57h+TokenInformationLength]
0x18000bc3e  mov     r14, [rbp+57h+TokenInformation]
0x18000bc42  mov     r12, [rbp+57h+TokenInformation+8]
0x18000bc46  mov     rdi, r12
0x18000bc49  sub     rdi, r14
0x18000bc4c  cmp     rsi, rdi
0x18000bc4f  ja      loc_18000BCED
0x18000bc55  jb      loc_18000BD81
0x18000bc5b  lea     rax, [rbp+57h+TokenInformationLength]
0x18000bc5f  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18000bc64  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18000bc68  mov     r8, r14; TokenInformation
0x18000bc6b  mov     edx, 1; TokenInformationClass
0x18000bc70  mov     rcx, [r15+8]; TokenHandle
0x18000bc74  call    cs:__imp_GetTokenInformation
0x18000bc7a  test    eax, eax
0x18000bc7c  jz      loc_18000BE27
0x18000bc82  mov     rax, [rbp+57h+TokenInformation]
0x18000bc86  mov     rdi, [rax]
0x18000bc89  mov     rcx, rdi; pSid
0x18000bc8c  call    cs:__imp_GetLengthSid
0x18000bc92  mov     r9d, eax
0x18000bc95  mov     rdx, [rbx]
0x18000bc98  cmp     [rbx+8], rdx
0x18000bc9c  jnz     loc_18000BD78
0x18000bca2  mov     r8, rdi
0x18000bca5  mov     rcx, rbx
0x18000bca8  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000bcad  nop
0x18000bcae  mov     rcx, [rbp+57h+TokenInformation]; void *
0x18000bcb2  test    rcx, rcx
0x18000bcb5  jz      short loc_18000BCD8
0x18000bcb7  mov     rdx, [rbp+57h+var_90]
0x18000bcbb  sub     rdx, rcx; unsigned __int64
0x18000bcbe  mov     [rbp+57h+arg_18], rdx
0x18000bcc2  mov     [rbp+57h+arg_10], rcx
0x18000bcc6  cmp     rdx, 1000h
0x18000bccd  jnb     loc_18000BE92
0x18000bcd3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bcd8  mov     rax, rbx
0x18000bcdb  add     rsp, 0A0h
0x18000bce2  pop     r15
0x18000bce4  pop     r14
0x18000bce6  pop     r12
0x18000bce8  pop     rdi
0x18000bce9  pop     rsi
0x18000bcea  pop     rbx
0x18000bceb  pop     rbp
0x18000bcec  retn
0x18000bced  mov     rcx, [rbp+57h+var_90]
0x18000bcf1  sub     rcx, r14
0x18000bcf4  cmp     rsi, rcx
0x18000bcf7  jbe     loc_18000BE0A
0x18000bcfd  mov     rdx, rcx
0x18000bd00  shr     rdx, 1
0x18000bd03  mov     r12, 7FFFFFFFFFFFFFFFh
0x18000bd0d  mov     rax, r12
0x18000bd10  sub     rax, rdx
0x18000bd13  cmp     rcx, rax
0x18000bd16  ja      short loc_18000BD23
0x18000bd18  lea     r12, [rdx+rcx]
0x18000bd1c  cmp     r12, rsi
0x18000bd1f  cmovb   r12, rsi
0x18000bd23  mov     rcx, r12
0x18000bd26  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000bd2b  mov     r14, rax
0x18000bd2e  mov     r8, rsi
0x18000bd31  sub     r8, rdi; Size
0x18000bd34  lea     rcx, [rdi+rax]; void *
0x18000bd38  xor     edx, edx; Val
0x18000bd3a  call    memset_0
0x18000bd3f  mov     rdx, [rbp+57h+TokenInformation]; Src
0x18000bd43  mov     r8, [rbp+57h+TokenInformation+8]
0x18000bd47  sub     r8, rdx; Size
0x18000bd4a  mov     rcx, r14; void *
0x18000bd4d  call    memmove_0
0x18000bd52  mov     rcx, [rbp+57h+TokenInformation]
0x18000bd56  test    rcx, rcx
0x18000bd59  jnz     loc_18000BDF9
0x18000bd5f  mov     [rbp+57h+TokenInformation], r14
0x18000bd63  lea     rax, [rsi+r14]
0x18000bd67  mov     [rbp+57h+TokenInformation+8], rax
0x18000bd6b  lea     rax, [r12+r14]
0x18000bd6f  mov     [rbp+57h+var_90], rax
0x18000bd73  jmp     loc_18000BC5B
0x18000bd78  mov     [rbx+8], rdx
0x18000bd7c  jmp     loc_18000BCA2
0x18000bd81  lea     rax, [rsi+r14]
0x18000bd85  mov     [rbp+57h+TokenInformation+8], rax
0x18000bd89  jmp     loc_18000BC5B
0x18000bd8e  lea     rcx, [rbp+57h+var_80]; this
0x18000bd92  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000bd97  nop
0x18000bd98  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd9f  test    byte ptr [rcx+1Ch], 8
0x18000bda3  jz      short loc_18000BDC4
0x18000bda5  cmp     byte ptr [rcx+19h], 2
0x18000bda9  jb      short loc_18000BDC4
0x18000bdab  mov     edx, 14h
0x18000bdb0  mov     r9d, [rbp+57h+var_60]
0x18000bdb4  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000bdbb  mov     rcx, [rcx+10h]
0x18000bdbf  call    WPP_SF_d
0x18000bdc4  lea     rdx, [rbp+57h+var_80]; struct std::exception *
0x18000bdc8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000bdcc  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000bdd1  mov     eax, [rbp+57h+var_68]
0x18000bdd4  mov     [rbp+57h+var_40], eax
0x18000bdd7  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000bdde  mov     [rbp+57h+pExceptionObject], rax
0x18000bde2  mov     eax, [rbp+57h+var_60]
0x18000bde5  mov     [rbp+57h+var_38], eax
0x18000bde8  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000bdef  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000bdf3  call    _CxxThrowException_0
0x18000bdf9  mov     rdx, [rbp+57h+var_90]
0x18000bdfd  sub     rdx, rcx
0x18000be00  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000be05  jmp     loc_18000BD5F
0x18000be0a  sub     rsi, rdi
0x18000be0d  mov     r8, rsi; Size
0x18000be10  xor     edx, edx; Val
0x18000be12  mov     rcx, r12; void *
0x18000be15  call    memset_0
0x18000be1a  lea     rax, [rsi+r12]
0x18000be1e  mov     r14, [rbp+57h+TokenInformation]
0x18000be22  jmp     loc_18000BD85
0x18000be27  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000be2b  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000be30  nop
0x18000be31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be38  test    byte ptr [rcx+1Ch], 8
0x18000be3c  jz      short loc_18000BE5D
0x18000be3e  cmp     byte ptr [rcx+19h], 2
0x18000be42  jb      short loc_18000BE5D
0x18000be44  mov     edx, 15h
0x18000be49  mov     r9d, [rbp+57h+var_38]
0x18000be4d  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000be54  mov     rcx, [rcx+10h]
0x18000be58  call    WPP_SF_d
0x18000be5d  lea     rdx, [rbp+57h+pExceptionObject]; struct std::exception *
0x18000be61  lea     rcx, [rbp+57h+var_80]; this
0x18000be65  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000be6a  mov     eax, [rbp+57h+var_40]
0x18000be6d  mov     [rbp+57h+var_68], eax
0x18000be70  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000be77  mov     [rbp+57h+var_80], rax
0x18000be7b  mov     eax, [rbp+57h+var_38]
0x18000be7e  mov     [rbp+57h+var_60], eax
0x18000be81  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000be88  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x18000be8c  call    _CxxThrowException_0
0x18000be92  lea     rdx, [rbp+57h+arg_18]; unsigned __int64 *
0x18000be96  lea     rcx, [rbp+57h+arg_10]; void **
0x18000be9a  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000be9f  mov     rcx, [rbp+57h+arg_10]
0x18000bea3  mov     rdx, [rbp+57h+arg_18]
0x18000bea7  jmp     loc_18000BCD3
```
