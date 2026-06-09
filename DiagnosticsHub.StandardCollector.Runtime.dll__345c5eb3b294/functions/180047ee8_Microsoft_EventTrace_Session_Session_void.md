# Microsoft::EventTrace::Session::Session(void)

- ea: `0x180047ee8`
- end: `0x180048072`
- name: `??0Session@EventTrace@Microsoft@@QEAA@XZ`
- size: `394`
- prototype: `__int64 __fastcall(Microsoft::EventTrace::Session *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180048e20`
- `0x180048f78`
- `0x1800494f4`
- `0x180049924`

## callees

- `0x180047ee8`
- `0x180048a24`
- `0x180049b50`
- `0x18004a078`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180047f59`
- `KERNEL32!GetCurrentProcess` at `0x180047f59`
- `KERNEL32!CloseHandle` at `0x180047fd3`
- `KERNEL32!CloseHandle` at `0x18004803e`
- `KERNEL32!CloseHandle` at `0x180047fd3`
- `KERNEL32!CloseHandle` at `0x18004803e`
- `USERENV!UnloadUserProfile` at `0x180047fbc`
- `USERENV!UnloadUserProfile` at `0x180048027`
- `USERENV!UnloadUserProfile` at `0x180047fbc`
- `USERENV!UnloadUserProfile` at `0x180048027`
- `ADVAPI32!OpenProcessToken` at `0x180047f6b`
- `ADVAPI32!OpenProcessToken` at `0x180047f6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::EventTrace::Session *__fastcall Microsoft::EventTrace::Session::Session(
        Microsoft::EventTrace::Session *this)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *v3; // rdx
  struct ATL::CTokenPrivileges *v4; // r8
  bool *v5; // r9
  HANDLE v6; // rdx
  HANDLE v7; // rcx
  HANDLE TokenHandle; // [rsp+28h] [rbp-38h] BYREF
  void **hToken; // [rsp+30h] [rbp-30h] BYREF
  HANDLE hToken_8[2]; // [rsp+38h] [rbp-28h]
  void *hProfile_8; // [rsp+48h] [rbp-18h]

  *(_QWORD *)this = &Microsoft::EventTrace::Session::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( byte_180077180 )
    return this;
  hToken = &ATL::CAccessToken::`vftable';
  *(_OWORD *)hToken_8 = 0;
  hProfile_8 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    hToken = &ATL::CAccessToken::`vftable';
    v6 = hToken_8[1];
    v7 = hToken_8[0];
LABEL_13:
    if ( v6 )
    {
      if ( v7 )
      {
        UnloadUserProfile(v7, v6);
        v7 = hToken_8[0];
      }
      hToken_8[1] = 0;
    }
    if ( v7 )
    {
      CloseHandle(v7);
      hToken_8[0] = 0;
    }
    operator delete(hProfile_8);
    LODWORD(TokenHandle) = -2147024891;
    throw (long *)&TokenHandle;
  }
  ((void (__fastcall *)(void ***))hToken[1])(&hToken);
  hToken_8[0] = TokenHandle;
  byte_180077180 = ATL::CAccessToken::EnablePrivilege((HANDLE *)&hToken, v3, v4, v5);
  hToken = &ATL::CAccessToken::`vftable';
  v6 = hToken_8[1];
  v7 = hToken_8[0];
  if ( !byte_180077180 )
    goto LABEL_13;
  if ( hToken_8[1] )
  {
    if ( hToken_8[0] )
    {
      UnloadUserProfile(hToken_8[0], hToken_8[1]);
      v7 = hToken_8[0];
    }
    hToken_8[1] = 0;
  }
  if ( v7 )
  {
    CloseHandle(v7);
    hToken_8[0] = 0;
  }
  operator delete(hProfile_8);
  return this;
}

```

## disassembly

```asm
0x180047ee8  mov     [rsp-8+arg_8], rbx
0x180047eed  mov     [rsp-8+arg_10], rsi
0x180047ef2  push    rbp
0x180047ef3  mov     rbp, rsp
0x180047ef6  sub     rsp, 60h
0x180047efa  mov     rax, cs:__security_cookie
0x180047f01  xor     rax, rsp
0x180047f04  mov     [rbp+var_10], rax
0x180047f08  mov     rbx, rcx
0x180047f0b  mov     [rbp+var_40], rcx
0x180047f0f  lea     rax, ??_7Session@EventTrace@Microsoft@@6B@; const Microsoft::EventTrace::Session::`vftable'
0x180047f16  mov     [rcx], rax
0x180047f19  mov     qword ptr [rcx+8], 0
0x180047f21  mov     qword ptr [rcx+10h], 0
0x180047f29  cmp     cs:byte_180077180, 0
0x180047f30  jnz     loc_180047FF0
0x180047f36  xorps   xmm0, xmm0
0x180047f39  movups  xmmword ptr [rbp+hToken], xmm0
0x180047f3d  movups  xmmword ptr [rbp+hProfile], xmm0
0x180047f41  lea     rsi, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180047f48  mov     [rbp+hToken], rsi
0x180047f4c  movdqu  xmmword ptr [rbp+hToken+8], xmm0
0x180047f51  mov     [rbp+hProfile+8], 0
0x180047f59  call    cs:__imp_GetCurrentProcess
0x180047f5f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180047f63  mov     edx, 28h ; '('; DesiredAccess
0x180047f68  mov     rcx, rax; ProcessHandle
0x180047f6b  call    cs:__imp_OpenProcessToken
0x180047f71  test    eax, eax
0x180047f73  jz      loc_180048011
0x180047f79  mov     rax, [rbp+hToken]
0x180047f7d  lea     rcx, [rbp+hToken]
0x180047f81  mov     rax, [rax+8]
0x180047f85  call    cs:__guard_dispatch_icall_fptr
0x180047f8b  mov     rax, [rbp+TokenHandle]
0x180047f8f  mov     [rbp+hToken+8], rax
0x180047f93  lea     rcx, [rbp+hToken]; this
0x180047f97  call    ?EnablePrivilege@CAccessToken@ATL@@QEAA_NPEBGPEAVCTokenPrivileges@2@PEA_N@Z; ATL::CAccessToken::EnablePrivilege(ushort const *,ATL::CTokenPrivileges *,bool *)
0x180047f9c  mov     cs:byte_180077180, al
0x180047fa2  mov     [rbp+hToken], rsi
0x180047fa6  mov     rdx, [rbp+hProfile]; hProfile
0x180047faa  mov     rcx, [rbp+hToken+8]; hToken
0x180047fae  test    al, al
0x180047fb0  jz      short loc_18004801D
0x180047fb2  test    rdx, rdx
0x180047fb5  jz      short loc_180047FCE
0x180047fb7  test    rcx, rcx
0x180047fba  jz      short loc_180047FC6
0x180047fbc  call    cs:__imp_UnloadUserProfile
0x180047fc2  mov     rcx, [rbp+hToken+8]; hObject
0x180047fc6  mov     [rbp+hProfile], 0
0x180047fce  test    rcx, rcx
0x180047fd1  jz      short loc_180047FE1
0x180047fd3  call    cs:__imp_CloseHandle
0x180047fd9  mov     [rbp+hToken+8], 0
0x180047fe1  mov     edx, 8
0x180047fe6  mov     rcx, [rbp+hProfile+8]; Block
0x180047fea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047fef  nop
0x180047ff0  mov     rax, rbx
0x180047ff3  mov     rcx, [rbp+var_10]
0x180047ff7  xor     rcx, rsp; StackCookie
0x180047ffa  call    __security_check_cookie
0x180047fff  lea     r11, [rsp+60h+var_s0]
0x180048004  mov     rbx, [r11+18h]
0x180048008  mov     rsi, [r11+20h]
0x18004800c  mov     rsp, r11
0x18004800f  pop     rbp
0x180048010  retn
0x180048011  mov     [rbp+hToken], rsi
0x180048015  mov     rdx, [rbp+hProfile]; hProfile
0x180048019  mov     rcx, [rbp+hToken+8]; hToken
0x18004801d  test    rdx, rdx
0x180048020  jz      short loc_180048039
0x180048022  test    rcx, rcx
0x180048025  jz      short loc_180048031
0x180048027  call    cs:__imp_UnloadUserProfile
0x18004802d  mov     rcx, [rbp+hToken+8]; hObject
0x180048031  mov     [rbp+hProfile], 0
0x180048039  test    rcx, rcx
0x18004803c  jz      short loc_18004804C
0x18004803e  call    cs:__imp_CloseHandle
0x180048044  mov     [rbp+hToken+8], 0
0x18004804c  mov     edx, 8
0x180048051  mov     rcx, [rbp+hProfile+8]; Block
0x180048055  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004805a  mov     dword ptr [rbp+TokenHandle], 80070005h
0x180048061  lea     rdx, _TI1J; pThrowInfo
0x180048068  lea     rcx, [rbp+TokenHandle]; pExceptionObject
0x18004806c  call    _CxxThrowException_0
```
