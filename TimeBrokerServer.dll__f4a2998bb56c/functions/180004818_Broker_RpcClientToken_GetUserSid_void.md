# Broker::RpcClientToken::GetUserSid(void)

- ea: `0x180004818`
- end: `0x180004a49`
- name: `?GetUserSid@RpcClientToken@Broker@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `561`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800042e8`

## callees

- `0x180003800`
- `0x180004488`
- `0x18000461c`
- `0x180004818`
- `0x180004b70`
- `0x180011240`
- `0x18001181c`
- `0x18001396c`
- `0x180013978`
- `0x180014e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004883`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004928`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004883`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004928`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004897`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004897`

## pseudocode

```c
_QWORD *__fastcall Broker::RpcClientToken::GetUserSid(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 LengthSid; // r9
  __int64 v6; // rdx
  char *v8; // rax
  size_t v9; // rbx
  LPVOID TokenInformation[2]; // [rsp+38h] [rbp-29h] BYREF
  __int64 v11; // [rsp+48h] [rbp-19h]
  int v12; // [rsp+50h] [rbp-11h]
  _QWORD pExceptionObject[3]; // [rsp+58h] [rbp-9h] BYREF
  int v14; // [rsp+70h] [rbp+Fh]
  unsigned int v15; // [rsp+78h] [rbp+17h]
  _QWORD v16[3]; // [rsp+80h] [rbp+1Fh] BYREF
  int v17; // [rsp+98h] [rbp+37h]
  unsigned int v18; // [rsp+A0h] [rbp+3Fh]
  DWORD TokenInformationLength; // [rsp+C8h] [rbp+67h] BYREF
  _QWORD *v20; // [rsp+D0h] [rbp+6Fh]

  v20 = a2;
  *(_OWORD *)TokenInformation = 0;
  v11 = 0;
  std::vector<_GUID>::vector<_GUID>(a2);
  v12 = 1;
  TokenInformationLength = 0;
  if ( GetTokenInformation(*(HANDLE *)(a1 + 8), TokenUser, 0, 0, &TokenInformationLength) )
    goto LABEL_2;
  if ( GetLastError() != 122 )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v15);
    std::exception::exception((std::exception *)v16, (const struct std::exception *)pExceptionObject);
    v17 = v14;
    v16[0] = &Broker::Win32Error::`vftable';
    v18 = v15;
    throw (Broker::Win32Error *)v16;
  }
  if ( (LPVOID)TokenInformationLength < (LPVOID)((char *)TokenInformation[1] - (char *)TokenInformation[0]) )
  {
    v8 = (char *)TokenInformation[0] + TokenInformationLength;
LABEL_8:
    TokenInformation[1] = v8;
    goto LABEL_9;
  }
  if ( (LPVOID)TokenInformationLength > (LPVOID)((char *)TokenInformation[1] - (char *)TokenInformation[0]) )
  {
    if ( TokenInformationLength <= v11 - (unsigned __int64)TokenInformation[0] )
    {
      v9 = TokenInformationLength - (unsigned __int64)((char *)TokenInformation[1] - (char *)TokenInformation[0]);
      memset_0(TokenInformation[1], 0, v9);
      v8 = (char *)TokenInformation[1] + v9;
      goto LABEL_8;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(TokenInformation, TokenInformationLength);
  }
LABEL_9:
  if ( !GetTokenInformation(
          *(HANDLE *)(a1 + 8),
          TokenUser,
          TokenInformation[0],
          TokenInformationLength,
          &TokenInformationLength) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v16);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v18);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v16);
    v14 = v17;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v15 = v18;
    throw (Broker::Win32Error *)pExceptionObject;
  }
LABEL_2:
  v4 = *(_QWORD *)TokenInformation[0];
  LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
  v6 = *a2;
  if ( a2[1] != *a2 )
    a2[1] = v6;
  std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(a2, v6, v4, LengthSid);
  std::vector<unsigned char>::_Tidy(TokenInformation);
  return a2;
}

```

## disassembly

```asm
0x180004818  mov     rax, rsp
0x18000481b  mov     [rax+18h], rbx
0x18000481f  mov     [rax+20h], rsi
0x180004823  mov     [rax+10h], rdx
0x180004827  push    rbp
0x180004828  push    rdi
0x180004829  push    r14
0x18000482b  lea     rbp, [rax-5Fh]
0x18000482f  sub     rsp, 0A0h
0x180004836  mov     rdi, rdx
0x180004839  mov     r14, rcx
0x18000483c  mov     [rbp+57h+var_68], 0
0x180004843  xorps   xmm0, xmm0
0x180004846  movdqu  xmmword ptr [rbp+57h+TokenInformation], xmm0
0x18000484b  mov     [rbp+57h+var_70], 0
0x180004853  mov     rcx, rdx
0x180004856  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000485b  mov     [rbp+57h+var_68], 1
0x180004862  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180004866  mov     r9d, dword ptr [rbp+57h+TokenInformation+8]
0x18000486a  sub     r9d, r8d; TokenInformationLength
0x18000486d  mov     [rbp+57h+TokenInformationLength], r9d
0x180004871  lea     rax, [rbp+57h+TokenInformationLength]
0x180004875  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18000487a  mov     edx, 1; TokenInformationClass
0x18000487f  mov     rcx, [r14+8]; TokenHandle
0x180004883  call    cs:__imp_GetTokenInformation
0x180004889  test    eax, eax
0x18000488b  jz      short loc_1800048DD
0x18000488d  mov     rax, [rbp+57h+TokenInformation]
0x180004891  mov     rbx, [rax]
0x180004894  mov     rcx, rbx; pSid
0x180004897  call    cs:__imp_GetLengthSid
0x18000489d  mov     r9d, eax
0x1800048a0  mov     rdx, [rdi]
0x1800048a3  cmp     [rdi+8], rdx
0x1800048a7  jz      short loc_1800048AD
0x1800048a9  mov     [rdi+8], rdx
0x1800048ad  mov     r8, rbx
0x1800048b0  mov     rcx, rdi
0x1800048b3  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x1800048b8  nop
0x1800048b9  lea     rcx, [rbp+57h+TokenInformation]
0x1800048bd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800048c2  mov     rax, rdi
0x1800048c5  lea     r11, [rsp+0B0h+var_10]
0x1800048cd  mov     rbx, [r11+30h]
0x1800048d1  mov     rsi, [r11+38h]
0x1800048d5  mov     rsp, r11
0x1800048d8  pop     r14
0x1800048da  pop     rdi
0x1800048db  pop     rbp
0x1800048dc  retn
0x1800048dd  call    cs:__imp_GetLastError
0x1800048e3  cmp     eax, 7Ah ; 'z'
0x1800048e6  jnz     loc_1800049A1
0x1800048ec  mov     ebx, [rbp+57h+TokenInformationLength]
0x1800048ef  mov     rdx, [rbp+57h+TokenInformation]
0x1800048f3  mov     rsi, [rbp+57h+TokenInformation+8]
0x1800048f7  mov     rcx, rsi
0x1800048fa  sub     rcx, rdx
0x1800048fd  cmp     rbx, rcx
0x180004900  jnb     loc_180004A0C
0x180004906  lea     rax, [rbx+rdx]
0x18000490a  mov     [rbp+57h+TokenInformation+8], rax
0x18000490e  lea     rax, [rbp+57h+TokenInformationLength]
0x180004912  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180004917  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18000491b  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000491f  mov     edx, 1; TokenInformationClass
0x180004924  mov     rcx, [r14+8]; TokenHandle
0x180004928  call    cs:__imp_GetTokenInformation
0x18000492e  test    eax, eax
0x180004930  jnz     loc_18000488D
0x180004936  lea     rcx, [rbp+57h+var_38]; this
0x18000493a  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000493f  nop
0x180004940  mov     rcx, cs:WPP_GLOBAL_Control
0x180004947  test    byte ptr [rcx+1Ch], 8
0x18000494b  jz      short loc_18000496C
0x18000494d  cmp     byte ptr [rcx+19h], 2
0x180004951  jb      short loc_18000496C
0x180004953  mov     edx, 15h
0x180004958  mov     r9d, [rbp+57h+var_18]
0x18000495c  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180004963  mov     rcx, [rcx+10h]
0x180004967  call    WPP_SF_d
0x18000496c  lea     rdx, [rbp+57h+var_38]; struct std::exception *
0x180004970  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180004974  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180004979  mov     eax, [rbp+57h+var_20]
0x18000497c  mov     [rbp+57h+var_48], eax
0x18000497f  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180004986  mov     [rbp+57h+pExceptionObject], rax
0x18000498a  mov     eax, [rbp+57h+var_18]
0x18000498d  mov     [rbp+57h+var_40], eax
0x180004990  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180004997  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000499b  call    _CxxThrowException_0
0x1800049a1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800049a5  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800049aa  nop
0x1800049ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049b2  test    byte ptr [rcx+1Ch], 8
0x1800049b6  jz      short loc_1800049D7
0x1800049b8  cmp     byte ptr [rcx+19h], 2
0x1800049bc  jb      short loc_1800049D7
0x1800049be  mov     edx, 14h
0x1800049c3  mov     r9d, [rbp+57h+var_40]
0x1800049c7  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800049ce  mov     rcx, [rcx+10h]
0x1800049d2  call    WPP_SF_d
0x1800049d7  lea     rdx, [rbp+57h+pExceptionObject]; struct std::exception *
0x1800049db  lea     rcx, [rbp+57h+var_38]; this
0x1800049df  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x1800049e4  mov     eax, [rbp+57h+var_48]
0x1800049e7  mov     [rbp+57h+var_20], eax
0x1800049ea  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800049f1  mov     [rbp+57h+var_38], rax
0x1800049f5  mov     eax, [rbp+57h+var_40]
0x1800049f8  mov     [rbp+57h+var_18], eax
0x1800049fb  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180004a02  lea     rcx, [rbp+57h+var_38]; pExceptionObject
0x180004a06  call    _CxxThrowException_0
0x180004a0c  jbe     loc_18000490E
0x180004a12  mov     rax, [rbp+57h+var_70]
0x180004a16  sub     rax, rdx
0x180004a19  cmp     rbx, rax
0x180004a1c  jbe     short loc_180004A2F
0x180004a1e  mov     rdx, rbx
0x180004a21  lea     rcx, [rbp+57h+TokenInformation]
0x180004a25  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180004a2a  jmp     loc_18000490E
0x180004a2f  sub     rbx, rcx
0x180004a32  mov     r8, rbx; Size
0x180004a35  xor     edx, edx; Val
0x180004a37  mov     rcx, rsi; void *
0x180004a3a  call    memset_0
0x180004a3f  lea     rax, [rbx+rsi]
0x180004a43  jmp     loc_18000490A
```
