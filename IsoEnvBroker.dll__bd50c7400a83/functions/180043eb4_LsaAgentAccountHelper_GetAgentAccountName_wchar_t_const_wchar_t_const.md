# LsaAgentAccountHelper::GetAgentAccountName(wchar_t const *,wchar_t const *)

- ea: `0x180043eb4`
- end: `0x1800440cc`
- name: `?GetAgentAccountName@LsaAgentAccountHelper@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180041b64`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18001045c`
- `0x180011e18`
- `0x180013270`
- `0x180014c04`
- `0x180043eb4`
- `0x180046bf4`
- `0x1800637fc`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180043f9b`
- `ntdll!RtlCompareUnicodeString` at `0x180043fb3`
- `ntdll!RtlCompareUnicodeString` at `0x180043f9b`
- `ntdll!RtlCompareUnicodeString` at `0x180043fb3`
- `ntdll!RtlInitUnicodeStringEx` at `0x180043f49`
- `ntdll!RtlInitUnicodeStringEx` at `0x180043f69`
- `ntdll!RtlInitUnicodeStringEx` at `0x180043f49`
- `ntdll!RtlInitUnicodeStringEx` at `0x180043f69`

## string_xrefs

- `0x180043f16`: `LsaEnumerateAgentAccounts failed: %#x`
- `0x18004407e`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x180044090`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x1800440a5`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x1800440ba`: `onecoreuap\windows\core\isoenvbroker\lib\common\LsaAgentAccountHelper.h`
- `0x18004403d`: `Did not find account name for agent %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LsaAgentAccountHelper::GetAgentAccountName(__int64 a1, __int64 a2, const WCHAR *a3, const char *a4)
{
  _DWORD *v8; // rsi
  unsigned int v9; // eax
  unsigned int v10; // edi
  int v11; // edi
  NTSTATUS inited; // eax
  NTSTATUS v13; // eax
  unsigned int v14; // edi
  __int64 v15; // r14
  __int64 v16; // r15
  _WORD *v18; // rdx
  unsigned __int64 v19; // r8
  int v20; // [rsp+20h] [rbp-58h]
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-50h] BYREF
  UNICODE_STRING String2; // [rsp+38h] [rbp-40h] BYREF
  __int128 v23; // [rsp+48h] [rbp-30h] BYREF
  __int128 v24; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  *(_QWORD *)&DestinationString.Length = a2;
  if ( !*(_BYTE *)a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x53,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      a4);
  v8 = (_DWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 24) || (v9 = LsaEnumerateAgentAccounts(*(_QWORD *)(a1 + 8), a1 + 16), (v10 = v9) == 0) )
  {
    v11 = 0;
  }
  else
  {
    Log(2u, L"LsaEnumerateAgentAccounts failed: %#x", v9);
    v11 = v10 | 0x10000000;
  }
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x55,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      (const char *)(unsigned int)v11,
      v20);
  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
  if ( inited < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      (const char *)(unsigned int)inited,
      v20);
  String2 = 0;
  v13 = RtlInitUnicodeStringEx(&String2, (PCWSTR)a4);
  if ( v13 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\LsaAgentAccountHelper.h",
      (const char *)(unsigned int)v13,
      v20);
  v14 = 0;
  if ( *v8 )
  {
    while ( 1 )
    {
      v15 = 56LL * v14;
      v16 = *(_QWORD *)(a1 + 24);
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(v15 + v16 + 8), &DestinationString, 0)
        && !RtlCompareUnicodeString((PCUNICODE_STRING)(v15 + v16 + 24), &String2, 0) )
      {
        break;
      }
      if ( ++v14 >= *v8 )
        goto LABEL_13;
    }
    v18 = *(_WORD **)(v15 + v16 + 48);
    v23 = 0;
    v24 = 0u;
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    std::wstring::_Construct<1,wchar_t const *>((char **)&v23, v18, v19);
    if ( !(_QWORD)v24 )
      Log(4u, L"Did not find account name for agent %s", a4);
    *(_OWORD *)a2 = v23;
    *(_OWORD *)(a2 + 16) = v24;
    *(_QWORD *)&v24 = 0;
    *((_QWORD *)&v24 + 1) = 7;
    LOWORD(v23) = 0;
    std::wstring::~wstring((char **)&v23);
  }
  else
  {
LABEL_13:
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)a2, &word_180096C4C, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x180043eb4  push    rbp
0x180043eb6  push    rbx
0x180043eb7  push    rsi
0x180043eb8  push    rdi
0x180043eb9  push    r12
0x180043ebb  push    r13
0x180043ebd  push    r14
0x180043ebf  push    r15
0x180043ec1  mov     rbp, rsp
0x180043ec4  sub     rsp, 78h
0x180043ec8  mov     rax, cs:__security_cookie
0x180043ecf  xor     rax, rsp
0x180043ed2  mov     [rbp+var_10], rax
0x180043ed6  mov     r12, r9
0x180043ed9  mov     r14, r8
0x180043edc  mov     rbx, rdx
0x180043edf  mov     r13, rcx
0x180043ee2  mov     qword ptr [rbp+DestinationString.Length], rdx
0x180043ee6  xor     r15d, r15d
0x180043ee9  mov     rcx, [rbp+40h]; this
0x180043eed  cmp     [r13+0], r15b
0x180043ef1  jz      loc_180044090
0x180043ef7  lea     rsi, [r13+10h]
0x180043efb  cmp     [rsi+8], r15
0x180043eff  jnz     short loc_180043F2C
0x180043f01  mov     rdx, rsi
0x180043f04  mov     rcx, [r13+8]
0x180043f08  call    LsaEnumerateAgentAccounts
0x180043f0d  mov     edi, eax
0x180043f0f  test    eax, eax
0x180043f11  jz      short loc_180043F2C
0x180043f13  mov     r8d, eax
0x180043f16  lea     rdx, aLsaenumerateag; "LsaEnumerateAgentAccounts failed: %#x"
0x180043f1d  lea     ecx, [r15+2]; unsigned __int8
0x180043f21  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180043f26  bts     edi, 1Ch
0x180043f2a  jmp     short loc_180043F2F
0x180043f2c  mov     edi, r15d
0x180043f2f  mov     rcx, [rbp+40h]; this
0x180043f33  test    edi, edi
0x180043f35  js      loc_1800440A2
0x180043f3b  xorps   xmm0, xmm0
0x180043f3e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180043f42  mov     rdx, r14; SourceString
0x180043f45  lea     rcx, [rbp+DestinationString]; DestinationString
0x180043f49  call    cs:__imp_RtlInitUnicodeStringEx
0x180043f4f  mov     rcx, [rbp+40h]; this
0x180043f53  test    eax, eax
0x180043f55  js      loc_1800440B7
0x180043f5b  xorps   xmm0, xmm0
0x180043f5e  movups  xmmword ptr [rbp+String2.Length], xmm0
0x180043f62  mov     rdx, r12; SourceString
0x180043f65  lea     rcx, [rbp+String2]; DestinationString
0x180043f69  call    cs:__imp_RtlInitUnicodeStringEx
0x180043f6f  mov     rcx, [rbp+40h]; this
0x180043f73  test    eax, eax
0x180043f75  js      loc_18004407B
0x180043f7b  mov     edi, r15d
0x180043f7e  cmp     [rsi], r15d
0x180043f81  jbe     short loc_180043FC6
0x180043f83  mov     eax, edi
0x180043f85  imul    r14, rax, 38h ; '8'
0x180043f89  mov     r15, [r13+18h]
0x180043f8d  lea     rcx, [r15+8]
0x180043f91  add     rcx, r14; String1
0x180043f94  xor     r8d, r8d; CaseInsensitive
0x180043f97  lea     rdx, [rbp+DestinationString]; String2
0x180043f9b  call    cs:__imp_RtlCompareUnicodeString
0x180043fa1  test    eax, eax
0x180043fa3  jnz     short loc_180043FBD
0x180043fa5  lea     rcx, [r15+18h]
0x180043fa9  add     rcx, r14; String1
0x180043fac  xor     r8d, r8d; CaseInsensitive
0x180043faf  lea     rdx, [rbp+String2]; String2
0x180043fb3  call    cs:__imp_RtlCompareUnicodeString
0x180043fb9  test    eax, eax
0x180043fbb  jz      short loc_180044006
0x180043fbd  inc     edi
0x180043fbf  cmp     edi, [rsi]
0x180043fc1  jb      short loc_180043F83
0x180043fc3  xor     r15d, r15d
0x180043fc6  xorps   xmm0, xmm0
0x180043fc9  movups  xmmword ptr [rbx], xmm0
0x180043fcc  mov     [rbx+10h], r15
0x180043fd0  mov     [rbx+18h], r15
0x180043fd4  xor     r8d, r8d
0x180043fd7  lea     rdx, word_180096C4C
0x180043fde  mov     rcx, rbx
0x180043fe1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180043fe6  mov     rax, rbx
0x180043fe9  mov     rcx, [rbp+var_10]
0x180043fed  xor     rcx, rsp; StackCookie
0x180043ff0  call    __security_check_cookie
0x180043ff5  add     rsp, 78h
0x180043ff9  pop     r15
0x180043ffb  pop     r14
0x180043ffd  pop     r13
0x180043fff  pop     r12
0x180044001  pop     rdi
0x180044002  pop     rsi
0x180044003  pop     rbx
0x180044004  pop     rbp
0x180044005  retn
0x180044006  mov     rdx, [r14+r15+30h]
0x18004400b  xorps   xmm0, xmm0
0x18004400e  movups  [rbp+var_30], xmm0
0x180044012  xor     edi, edi
0x180044014  mov     qword ptr [rbp+var_20], rdi
0x180044018  mov     qword ptr [rbp+var_20+8], rdi
0x18004401c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180044020  inc     r8
0x180044023  cmp     [rdx+r8*2], di
0x180044028  jnz     short loc_180044020
0x18004402a  lea     rcx, [rbp+var_30]
0x18004402e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180044033  nop
0x180044034  cmp     qword ptr [rbp+var_20], rdi
0x180044038  jnz     short loc_18004404E
0x18004403a  mov     r8, r12
0x18004403d  lea     rdx, aDidNotFindAcco; "Did not find account name for agent %s"
0x180044044  mov     ecx, 4; unsigned __int8
0x180044049  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004404e  movups  xmm0, [rbp+var_30]
0x180044052  movups  xmmword ptr [rbx], xmm0
0x180044055  movups  xmm1, [rbp+var_20]
0x180044059  movups  xmmword ptr [rbx+10h], xmm1
0x18004405d  mov     qword ptr [rbp+var_20], rdi
0x180044061  mov     qword ptr [rbp+var_20+8], 7
0x180044069  mov     word ptr [rbp+var_30], di
0x18004406d  lea     rcx, [rbp+var_30]
0x180044071  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044076  jmp     loc_180043FE6
0x18004407b  mov     r9d, eax; char *
0x18004407e  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044085  mov     edx, 5Ch ; '\'; void *
0x18004408a  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x180044090  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180044097  mov     edx, 53h ; 'S'; void *
0x18004409c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800440a2  mov     r9d, edi; char *
0x1800440a5  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800440ac  mov     edx, 55h ; 'U'; void *
0x1800440b1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800440b7  mov     r9d, eax; char *
0x1800440ba  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800440c1  mov     edx, 58h ; 'X'; void *
0x1800440c6  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
```
