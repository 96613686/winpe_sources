# __ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,bool &)

- ea: `0x18001c54c`
- end: `0x18001c794`
- name: `?__ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z`
- size: `584`
- prototype: `__int64 __fastcall(wchar_t *String2, ULONG SessionId)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001b6bc`
- `0x18001b9d4`
- `0x18001bcd4`
- `0x18001bfcc`
- `0x18001c3fc`

## callees

- `0x1800062ac`
- `0x180008830`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18001c54c`
- `0x18001f420`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18001c6cb`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18001c6cb`
- `ADVAPI32!CheckTokenMembership` at `0x18001c5dd`
- `ADVAPI32!CheckTokenMembership` at `0x18001c5dd`
- `KERNEL32!GetLastError` at `0x18001c720`
- `KERNEL32!GetLastError` at `0x18001c755`
- `KERNEL32!GetLastError` at `0x18001c720`
- `KERNEL32!GetLastError` at `0x18001c755`

## pseudocode

```c
__int64 __fastcall __ImpersonateUser(wchar_t *String2, __int64 SessionId, _BYTE *a3)
{
  bool v3; // zf
  ULONG v5; // ebx
  unsigned int v7; // ebx
  BOOL v8; // eax
  __int64 v9; // r9
  wchar_t *v10; // rcx
  int UserTokenFromSid; // eax
  signed int LastError; // eax
  signed int v13; // eax
  BOOL IsMember; // [rsp+30h] [rbp-30h] BYREF
  HANDLE hToken; // [rsp+38h] [rbp-28h] BYREF
  _DWORD SidToCheck[4]; // [rsp+40h] [rbp-20h] BYREF

  v3 = *((_QWORD *)String2 + 2) == 0;
  v5 = SessionId;
  IsMember = 0;
  hToken = 0;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids);
    v7 = -2147024809;
  }
  else
  {
    SidToCheck[0] = 257;
    SidToCheck[1] = 83886080;
    SidToCheck[2] = 18;
    v8 = CheckTokenMembership(0, SidToCheck, &IsMember);
    if ( v8 )
      v8 = IsMember;
    else
      IsMember = 0;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        if ( *((_QWORD *)String2 + 3) < 8u )
          LODWORD(v9) = (_DWORD)String2;
        else
          v9 = *(_QWORD *)String2;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
          v9,
          v5);
      }
      if ( *((_QWORD *)String2 + 3) < 8u )
        v10 = String2;
      else
        v10 = *(wchar_t **)String2;
      UserTokenFromSid = GetUserTokenFromSid(v10, v5, &hToken);
      v7 = UserTokenFromSid;
      if ( UserTokenFromSid >= 0 )
      {
        if ( ImpersonateLoggedOnUser(hToken) )
        {
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids);
          *a3 = 1;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
              (unsigned int)LastError);
          }
          v13 = GetLastError();
          v7 = v13;
          if ( v13 > 0 )
            v7 = (unsigned __int16)v13 | 0x80070000;
        }
      }
      else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids,
          (unsigned int)UserTokenFromSid);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids);
      v7 = -2147467259;
    }
  }
  LOBYTE(SessionId) = 1;
  std::wstring::_Tidy(String2, SessionId, 0);
  return v7;
}

```

## disassembly

```asm
0x18001c54c  push    rbp
0x18001c54e  push    rbx
0x18001c54f  push    rsi
0x18001c550  push    rdi
0x18001c551  push    r14
0x18001c553  mov     rbp, rsp
0x18001c556  sub     rsp, 60h
0x18001c55a  mov     rax, cs:__security_cookie
0x18001c561  xor     rax, rsp
0x18001c564  mov     [rbp+var_10], rax
0x18001c568  cmp     qword ptr [rcx+10h], 0
0x18001c56d  mov     r14, r8
0x18001c570  mov     ebx, edx
0x18001c572  mov     [rbp+IsMember], 0
0x18001c579  mov     rsi, rcx
0x18001c57c  mov     [rbp+hToken], 0
0x18001c584  jnz     short loc_18001C5BE
0x18001c586  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c58d  lea     rdi, WPP_GLOBAL_Control
0x18001c594  cmp     rcx, rdi
0x18001c597  jz      short loc_18001C5B4
0x18001c599  test    byte ptr [rcx+1Ch], 4
0x18001c59d  jz      short loc_18001C5B4
0x18001c59f  mov     rcx, [rcx+10h]
0x18001c5a3  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c5aa  mov     edx, 0Bh
0x18001c5af  call    WPP_SF_
0x18001c5b4  mov     ebx, 80070057h
0x18001c5b9  jmp     loc_18001C76D
0x18001c5be  lea     r8, [rbp+IsMember]; IsMember
0x18001c5c2  mov     [rbp+SidToCheck], 101h
0x18001c5c9  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18001c5cd  mov     [rbp+var_1C], 5000000h
0x18001c5d4  xor     ecx, ecx; TokenHandle
0x18001c5d6  mov     [rbp+var_18], 12h
0x18001c5dd  call    cs:__imp_CheckTokenMembership
0x18001c5e4  nop     dword ptr [rax+rax+00h]
0x18001c5e9  test    eax, eax
0x18001c5eb  jnz     short loc_18001C5F2
0x18001c5ed  mov     [rbp+IsMember], eax
0x18001c5f0  jmp     short loc_18001C5F5
0x18001c5f2  mov     eax, [rbp+IsMember]
0x18001c5f5  test    eax, eax
0x18001c5f7  jnz     short loc_18001C62F
0x18001c5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c600  lea     rdi, WPP_GLOBAL_Control
0x18001c607  cmp     rcx, rdi
0x18001c60a  jz      short loc_18001C625
0x18001c60c  test    byte ptr [rcx+1Ch], 4
0x18001c610  jz      short loc_18001C625
0x18001c612  mov     rcx, [rcx+10h]
0x18001c616  lea     edx, [rax+0Dh]
0x18001c619  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c620  call    WPP_SF_
0x18001c625  mov     ebx, 80004005h
0x18001c62a  jmp     loc_18001C76D
0x18001c62f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c636  lea     rdi, WPP_GLOBAL_Control
0x18001c63d  cmp     rcx, rdi
0x18001c640  jz      short loc_18001C670
0x18001c642  test    byte ptr [rcx+1Ch], 1
0x18001c646  jz      short loc_18001C670
0x18001c648  cmp     qword ptr [rsi+18h], 8
0x18001c64d  jb      short loc_18001C654
0x18001c64f  mov     r9, [rsi]
0x18001c652  jmp     short loc_18001C657
0x18001c654  mov     r9, rsi
0x18001c657  mov     rcx, [rcx+10h]
0x18001c65b  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c662  mov     edx, 0Eh
0x18001c667  mov     [rsp+60h+var_40], ebx
0x18001c66b  call    WPP_SF_Sd
0x18001c670  cmp     qword ptr [rsi+18h], 8
0x18001c675  jb      short loc_18001C67C
0x18001c677  mov     rcx, [rsi]
0x18001c67a  jmp     short loc_18001C67F
0x18001c67c  mov     rcx, rsi; String2
0x18001c67f  lea     r8, [rbp+hToken]; void **
0x18001c683  mov     edx, ebx; SessionId
0x18001c685  call    ?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z; GetUserTokenFromSid(ushort const *,ulong,void * *)
0x18001c68a  mov     ebx, eax
0x18001c68c  test    eax, eax
0x18001c68e  jns     short loc_18001C6C7
0x18001c690  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c697  cmp     rcx, rdi
0x18001c69a  jz      loc_18001C76D
0x18001c6a0  test    byte ptr [rcx+1Ch], 4
0x18001c6a4  jz      loc_18001C76D
0x18001c6aa  mov     rcx, [rcx+10h]
0x18001c6ae  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c6b5  mov     edx, 0Fh
0x18001c6ba  mov     r9d, eax
0x18001c6bd  call    WPP_SF_d
0x18001c6c2  jmp     loc_18001C76D
0x18001c6c7  mov     rcx, [rbp+hToken]; hToken
0x18001c6cb  call    cs:__imp_ImpersonateLoggedOnUser
0x18001c6d2  nop     dword ptr [rax+rax+00h]
0x18001c6d7  test    eax, eax
0x18001c6d9  jz      short loc_18001C708
0x18001c6db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6e2  cmp     rcx, rdi
0x18001c6e5  jz      short loc_18001C702
0x18001c6e7  test    byte ptr [rcx+1Ch], 1
0x18001c6eb  jz      short loc_18001C702
0x18001c6ed  mov     rcx, [rcx+10h]
0x18001c6f1  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c6f8  mov     edx, 10h
0x18001c6fd  call    WPP_SF_
0x18001c702  mov     byte ptr [r14], 1
0x18001c706  jmp     short loc_18001C76D
0x18001c708  mov     rax, cs:WPP_GLOBAL_Control
0x18001c70f  mov     r14d, 80070000h
0x18001c715  cmp     rax, rdi
0x18001c718  jz      short loc_18001C755
0x18001c71a  test    byte ptr [rax+1Ch], 4
0x18001c71e  jz      short loc_18001C755
0x18001c720  call    cs:__imp_GetLastError
0x18001c727  nop     dword ptr [rax+rax+00h]
0x18001c72c  test    eax, eax
0x18001c72e  jle     short loc_18001C736
0x18001c730  movzx   eax, ax
0x18001c733  or      eax, r14d
0x18001c736  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c73d  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001c744  mov     edx, 11h
0x18001c749  mov     r9d, eax
0x18001c74c  mov     rcx, [rcx+10h]
0x18001c750  call    WPP_SF_d
0x18001c755  call    cs:__imp_GetLastError
0x18001c75c  nop     dword ptr [rax+rax+00h]
0x18001c761  mov     ebx, eax
0x18001c763  test    eax, eax
0x18001c765  jle     short loc_18001C76D
0x18001c767  movzx   ebx, ax
0x18001c76a  or      ebx, r14d
0x18001c76d  xor     r8d, r8d
0x18001c770  mov     dl, 1
0x18001c772  mov     rcx, rsi
0x18001c775  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c77a  mov     eax, ebx
0x18001c77c  mov     rcx, [rbp+var_10]
0x18001c780  xor     rcx, rsp; StackCookie
0x18001c783  call    __security_check_cookie
0x18001c788  add     rsp, 60h
0x18001c78c  pop     r14
0x18001c78e  pop     rdi
0x18001c78f  pop     rsi
0x18001c790  pop     rbx
0x18001c791  pop     rbp
0x18001c792  retn
```
