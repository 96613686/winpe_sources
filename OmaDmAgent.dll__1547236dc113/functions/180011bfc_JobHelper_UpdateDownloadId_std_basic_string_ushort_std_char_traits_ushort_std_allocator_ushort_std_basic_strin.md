# JobHelper::UpdateDownloadId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_GUID)

- ea: `0x180011bfc`
- end: `0x180011e4d`
- name: `?UpdateDownloadId@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0U_GUID@@@Z`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180014680`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x180009a14`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000a4f4`
- `0x18000bae8`
- `0x18000f7d4`
- `0x18000fdf8`
- `0x180011bfc`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011cb0`
- `KERNEL32!EnterCriticalSection` at `0x180011cb0`
- `KERNEL32!LeaveCriticalSection` at `0x180011dd6`
- `KERNEL32!LeaveCriticalSection` at `0x180011dd6`
- `RPCRT4!UuidToStringW` at `0x180011d5b`
- `RPCRT4!UuidToStringW` at `0x180011d5b`
- `RPCRT4!RpcStringFreeW` at `0x180011ded`
- `RPCRT4!RpcStringFreeW` at `0x180011ded`

## string_xrefs

- `0x180011d84`: `BITSId`
- `0x180011dbc`: `BITSId`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JobHelper::UpdateDownloadId(__int64 a1, _QWORD *a2, __int64 *a3, const UUID *a4)
{
  LSTATUS Key; // eax
  int JobDependencyRegPath; // ebx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r9
  const unsigned __int16 *v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-79h] BYREF
  HKEY v22; // [rsp+38h] [rbp-71h] BYREF
  HKEY phkResult[3]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v24[32]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v25[32]; // [rsp+78h] [rbp-31h] BYREF
  _QWORD *v26; // [rsp+98h] [rbp-11h]
  __int64 *v27; // [rsp+A0h] [rbp-9h]
  unsigned __int16 *v28[4]; // [rsp+A8h] [rbp-1h] BYREF

  v26 = a2;
  v27 = a3;
  std::wstring::wstring(v28, &dword_180022F6C);
  StringUuid = 0;
  phkResult[0] = 0;
  v22 = 0;
  Key = CurrentUserRegKeyHelper::GetKey(phkResult, &v22);
  JobDependencyRegPath = Key;
  if ( Key >= 0 )
  {
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    EnterCriticalSection(v10);
    phkResult[1] = (HKEY)v24;
    v11 = std::wstring::wstring(v24, a3);
    v12 = std::wstring::wstring(v25, a2);
    JobDependencyRegPath = JobHelper::GetJobDependencyRegPath(v12, v11, v28);
    if ( JobDependencyRegPath >= 0 )
    {
      if ( UuidToStringW(a4, &StringUuid) )
      {
        JobDependencyRegPath = -2147467259;
      }
      else
      {
        v15 = (const unsigned __int16 *)v28;
        if ( v28[3] >= (unsigned __int16 *)8 )
          v15 = v28[0];
        v16 = WriteRegSZValue(v22, v15, L"BITSId", (const BYTE *)StringUuid);
        JobDependencyRegPath = v16;
        if ( v16 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            112,
            (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
            (unsigned int)L"BITSId",
            v16);
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( (unsigned __int64)a3[3] < 8 )
        v13 = (__int64)a3;
      else
        v13 = *a3;
      if ( a2[3] < 8u )
        LODWORD(v14) = (_DWORD)a2;
      else
        v14 = *a2;
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v14,
        v13,
        JobDependencyRegPath);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  }
  LeaveCriticalSection(v10);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)phkResult);
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(v28, v17, 0);
  LOBYTE(v18) = 1;
  std::wstring::_Tidy(a2, v18, 0);
  LOBYTE(v19) = 1;
  std::wstring::_Tidy(a3, v19, 0);
  return (unsigned int)JobDependencyRegPath;
}

```

## disassembly

```asm
0x180011bfc  push    rbp
0x180011bfe  push    rbx
0x180011bff  push    rsi
0x180011c00  push    rdi
0x180011c01  push    r14
0x180011c03  push    r15
0x180011c05  lea     rbp, [rsp-2Fh]
0x180011c0a  sub     rsp, 0D8h
0x180011c11  mov     rax, cs:__security_cookie
0x180011c18  xor     rax, rsp
0x180011c1b  mov     [rbp+57h+var_38], rax
0x180011c1f  mov     r15, r9
0x180011c22  mov     rsi, r8
0x180011c25  mov     r14, rdx
0x180011c28  mov     rdi, rcx
0x180011c2b  mov     [rbp+57h+var_68], rdx
0x180011c2f  mov     [rbp+57h+var_60], r8
0x180011c33  lea     rdx, dword_180022F6C
0x180011c3a  lea     rcx, [rbp+57h+var_58]
0x180011c3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180011c43  nop
0x180011c44  mov     [rbp+57h+StringUuid], 0
0x180011c4c  mov     [rbp+57h+phkResult], 0
0x180011c54  mov     [rbp+57h+var_C8], 0
0x180011c5c  lea     rdx, [rbp+57h+var_C8]; HKEY *
0x180011c60  lea     rcx, [rbp+57h+phkResult]; phkResult
0x180011c64  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x180011c69  mov     ebx, eax
0x180011c6b  test    eax, eax
0x180011c6d  jns     short loc_180011CA9
0x180011c6f  lea     rdx, WPP_GLOBAL_Control
0x180011c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c7d  cmp     rcx, rdx
0x180011c80  jz      short loc_180011CA0
0x180011c82  test    byte ptr [rcx+1Ch], 4
0x180011c86  jz      short loc_180011CA0
0x180011c88  mov     edx, 6Eh ; 'n'
0x180011c8d  mov     r9d, eax
0x180011c90  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011c97  mov     rcx, [rcx+10h]
0x180011c9b  call    WPP_SF_d
0x180011ca0  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180011ca4  jmp     loc_180011DD3
0x180011ca9  sub     rdi, 0FFFFFFFFFFFFFF80h
0x180011cad  mov     rcx, rdi; lpCriticalSection
0x180011cb0  call    cs:__imp_EnterCriticalSection
0x180011cb7  nop     dword ptr [rax+rax+00h]
0x180011cbc  lea     rax, [rbp+57h+var_A8]
0x180011cc0  mov     [rbp+57h+var_B8], rax
0x180011cc4  mov     rdx, rsi
0x180011cc7  lea     rcx, [rbp+57h+var_A8]
0x180011ccb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011cd0  mov     rbx, rax
0x180011cd3  mov     rdx, r14
0x180011cd6  lea     rcx, [rbp+57h+var_88]
0x180011cda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011cdf  nop
0x180011ce0  lea     r8, [rbp+57h+var_58]
0x180011ce4  mov     rdx, rbx
0x180011ce7  mov     rcx, rax
0x180011cea  call    ?GetJobDependencyRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobDependencyRegPath(std::wstring,std::wstring,std::wstring &)
0x180011cef  mov     ebx, eax
0x180011cf1  test    eax, eax
0x180011cf3  jns     short loc_180011D54
0x180011cf5  lea     rdx, WPP_GLOBAL_Control
0x180011cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d03  cmp     rcx, rdx
0x180011d06  jz      loc_180011DD3
0x180011d0c  test    byte ptr [rcx+1Ch], 4
0x180011d10  jz      loc_180011DD3
0x180011d16  cmp     qword ptr [rsi+18h], 8
0x180011d1b  jb      short loc_180011D22
0x180011d1d  mov     rax, [rsi]
0x180011d20  jmp     short loc_180011D25
0x180011d22  mov     rax, rsi
0x180011d25  cmp     qword ptr [r14+18h], 8
0x180011d2a  jb      short loc_180011D31
0x180011d2c  mov     r9, [r14]
0x180011d2f  jmp     short loc_180011D34
0x180011d31  mov     r9, r14
0x180011d34  mov     edx, 6Fh ; 'o'
0x180011d39  mov     [rsp+100h+var_D8], ebx
0x180011d3d  mov     [rsp+100h+var_E0], rax
0x180011d42  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011d49  mov     rcx, [rcx+10h]
0x180011d4d  call    WPP_SF_SSD
0x180011d52  jmp     short loc_180011DD3
0x180011d54  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180011d58  mov     rcx, r15; Uuid
0x180011d5b  call    cs:__imp_UuidToStringW
0x180011d62  nop     dword ptr [rax+rax+00h]
0x180011d67  test    eax, eax
0x180011d69  jz      short loc_180011D72
0x180011d6b  mov     ebx, 80004005h
0x180011d70  jmp     short loc_180011DD3
0x180011d72  lea     rdx, [rbp+57h+var_58]
0x180011d76  cmp     [rbp+57h+var_40], 8
0x180011d7b  cmovnb  rdx, [rbp+57h+var_58]; unsigned __int16 *
0x180011d80  mov     r9, [rbp+57h+StringUuid]; unsigned __int16 *
0x180011d84  lea     r8, aBitsid; "BITSId"
0x180011d8b  mov     rcx, [rbp+57h+var_C8]; HKEY
0x180011d8f  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x180011d94  mov     ebx, eax
0x180011d96  test    eax, eax
0x180011d98  jns     short loc_180011DD3
0x180011d9a  lea     rdx, WPP_GLOBAL_Control
0x180011da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180011da8  cmp     rcx, rdx
0x180011dab  jz      short loc_180011DD3
0x180011dad  test    byte ptr [rcx+1Ch], 4
0x180011db1  jz      short loc_180011DD3
0x180011db3  mov     edx, 70h ; 'p'
0x180011db8  mov     dword ptr [rsp+100h+var_E0], eax
0x180011dbc  lea     r9, aBitsid; "BITSId"
0x180011dc3  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180011dca  mov     rcx, [rcx+10h]
0x180011dce  call    WPP_SF_Sd
0x180011dd3  mov     rcx, rdi; lpCriticalSection
0x180011dd6  call    cs:__imp_LeaveCriticalSection
0x180011ddd  nop     dword ptr [rax+rax+00h]
0x180011de2  cmp     [rbp+57h+StringUuid], 0
0x180011de7  jz      short loc_180011DFA
0x180011de9  lea     rcx, [rbp+57h+StringUuid]; String
0x180011ded  call    cs:__imp_RpcStringFreeW
0x180011df4  nop     dword ptr [rax+rax+00h]
0x180011df9  nop
0x180011dfa  lea     rcx, [rbp+57h+phkResult]; this
0x180011dfe  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x180011e03  nop
0x180011e04  xor     r8d, r8d
0x180011e07  mov     dl, 1
0x180011e09  lea     rcx, [rbp+57h+var_58]
0x180011e0d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011e12  nop
0x180011e13  xor     r8d, r8d
0x180011e16  mov     dl, 1
0x180011e18  mov     rcx, r14
0x180011e1b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011e20  nop
0x180011e21  xor     r8d, r8d
0x180011e24  mov     dl, 1
0x180011e26  mov     rcx, rsi
0x180011e29  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011e2e  mov     eax, ebx
0x180011e30  mov     rcx, [rbp+57h+var_38]
0x180011e34  xor     rcx, rsp; StackCookie
0x180011e37  call    __security_check_cookie
0x180011e3c  add     rsp, 0D8h
0x180011e43  pop     r15
0x180011e45  pop     r14
0x180011e47  pop     rdi
0x180011e48  pop     rsi
0x180011e49  pop     rbx
0x180011e4a  pop     rbp
0x180011e4b  retn
```
