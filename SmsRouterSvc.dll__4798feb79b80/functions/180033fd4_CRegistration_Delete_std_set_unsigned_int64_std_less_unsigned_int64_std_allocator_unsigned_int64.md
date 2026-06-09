# CRegistration::Delete(std::set<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>> &)

- ea: `0x180033fd4`
- end: `0x180034295`
- name: `?Delete@CRegistration@@QEAAJAEAV?$set@_KU?$less@_K@std@@V?$allocator@_K@2@@std@@@Z`
- size: `705`
- prototype: `__int64 __fastcall(CRegistration *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180011cc0`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000dd64`
- `0x180033aa0`
- `0x180033fd4`
- `0x1800351fc`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003412d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003412d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034259`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800341a8`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800341a8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800340ce`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800340ce`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003404a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003404a`

## string_xrefs

- `0x180034071`: `RegCreateKey failed Key: %S`
- `0x180034100`: `RegDeleteKey failed RegId: %S`
- `0x18003407d`: `CRegistration::Delete`
- `0x18003410c`: `CRegistration::Delete`
- `0x1800341e9`: `CRegistration::Delete`
- `0x1800341da`: `RegDeleteKeyValue failed ValueName: %S\%S`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRegistration::Delete(CRegistration *this, __int64 *a2)
{
  CRegistration *v3; // rdi
  char *v4; // r15
  LSTATUS v5; // eax
  signed int v6; // ebx
  unsigned int v7; // r8d
  HKEY v9; // rbx
  const WCHAR *v10; // rdx
  int v11; // esi
  unsigned int v12; // r8d
  _QWORD *v13; // r9
  _QWORD *v14; // r8
  _QWORD *v15; // rdx
  const WCHAR *v16; // r8
  int v17; // eax
  const wchar_t *v18; // rcx
  int v19; // [rsp+30h] [rbp-39h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-31h] BYREF
  HKEY v21; // [rsp+40h] [rbp-29h]
  __int64 v22[3]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp-9h] BYREF
  LPCWSTR lpValueName[3]; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v25; // [rsp+88h] [rbp+1Fh]

  v3 = this;
  v22[1] = (__int64)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v4 = (char *)this + 304;
  v22[2] = (__int64)this + 304;
  (**((void (__fastcall ***)(char *))this + 38))((char *)this + 304);
  v21 = 0;
  phkResult = 0;
  v5 = RegCreateKeyW(g_SmsRouterKey, L"Registration\\Ids", &phkResult);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v7 = (unsigned __int16)v5 | 0x80070000;
    else
      v7 = v5;
    LogSmsRouterError("CRegistration::Delete", 0x384u, v7, "RegCreateKey failed Key: %S", L"Registration\\Ids");
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    return (unsigned int)v6;
  }
  else
  {
    v9 = phkResult;
    v21 = phkResult;
    phkResult = 0;
    if ( *((_QWORD *)v3 + 3) <= 7u )
      v10 = (const WCHAR *)v3;
    else
      v10 = *(const WCHAR **)v3;
    v11 = RegDeleteKeyW(v9, v10);
    if ( v11 )
    {
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(CRegistration **)v3;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      else
        v12 = v11;
      LogSmsRouterError("CRegistration::Delete", 0x38Eu, v12, "RegDeleteKey failed RegId: %S", (const wchar_t *)v3);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 )
        RegCloseKey(v9);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
      return (unsigned int)v11;
    }
    else
    {
      *((_DWORD *)v3 + 56) = 0;
      v13 = (_QWORD *)((char *)v3 + 112);
      if ( *((_QWORD *)v3 + 17) > 7u )
        v13 = (_QWORD *)*v13;
      v14 = (_QWORD *)((char *)v3 + 80);
      if ( *((_QWORD *)v3 + 13) > 7u )
        v14 = (_QWORD *)*v14;
      v15 = (_QWORD *)((char *)v3 + 48);
      if ( *((_QWORD *)v3 + 9) > 7u )
        v15 = (_QWORD *)*v15;
      CRegistration::GetUniqueId(lpValueName, v15, v14, v13);
      v16 = (const WCHAR *)lpValueName;
      if ( v25 > 7 )
        v16 = lpValueName[0];
      v17 = RegDeleteKeyValueW(g_SmsRouterKey, L"Registration\\Map", v16);
      if ( v17 )
      {
        v18 = (const wchar_t *)lpValueName;
        if ( v25 > 7 )
          v18 = lpValueName[0];
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        LogSmsRouterError(
          "CRegistration::Delete",
          0x39Au,
          v17,
          "RegDeleteKeyValue failed ValueName: %S\\%S",
          L"Registration\\Map",
          v18);
      }
      while ( *((_QWORD *)v3 + 32) )
      {
        v19 = 0;
        v22[0] = *(_QWORD *)(**((_QWORD **)v3 + 31) + 32LL);
        CRegistration::AcknowledgeMessage(v3, v22[0], 0, 0, &v19);
        if ( v19 )
          std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(
            a2,
            (__int64)v23,
            v22);
      }
      std::wstring::~wstring((char **)lpValueName);
      if ( v9 )
        RegCloseKey(v9);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180033fd4  mov     [rsp-8+arg_10], rbx
0x180033fd9  push    rbp
0x180033fda  push    rsi
0x180033fdb  push    rdi
0x180033fdc  push    r12
0x180033fde  push    r15
0x180033fe0  lea     rbp, [rsp-37h]
0x180033fe5  sub     rsp, 0A0h
0x180033fec  mov     rax, cs:__security_cookie
0x180033ff3  xor     rax, rsp
0x180033ff6  mov     [rbp+57h+var_30], rax
0x180033ffa  mov     r12, rdx
0x180033ffd  mov     rdi, rcx
0x180034000  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180034007  mov     [rbp+57h+var_70], rax
0x18003400b  lea     r15, [rcx+130h]
0x180034012  mov     [rbp+57h+var_68], r15
0x180034016  mov     rax, [r15]
0x180034019  mov     rcx, r15
0x18003401c  mov     rax, [rax]
0x18003401f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034024  nop
0x180034025  mov     [rbp+57h+var_80], 0
0x18003402d  mov     [rbp+57h+phkResult], 0
0x180034035  lea     r8, [rbp+57h+phkResult]; phkResult
0x180034039  lea     rsi, aRegistrationId; "Registration\\Ids"
0x180034040  mov     rdx, rsi; lpSubKey
0x180034043  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18003404a  call    cs:__imp_RegCreateKeyW
0x180034050  mov     ebx, eax
0x180034052  test    eax, eax
0x180034054  jz      short loc_1800340AC
0x180034056  movzx   edi, bx
0x180034059  test    eax, eax
0x18003405b  jg      short loc_180034062
0x18003405d  mov     r8d, eax
0x180034060  jmp     short loc_18003406C
0x180034062  mov     r8d, edi
0x180034065  or      r8d, 80070000h; int
0x18003406c  mov     [rsp+0C0h+var_A0], rsi
0x180034071  lea     r9, aRegcreatekeyFa; "RegCreateKey failed Key: %S"
0x180034078  mov     edx, 384h; unsigned int
0x18003407d  lea     rcx, aCregistrationD_0; "CRegistration::Delete"
0x180034084  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180034089  test    ebx, ebx
0x18003408b  jle     short loc_180034095
0x18003408d  mov     ebx, edi
0x18003408f  or      ebx, 80070000h
0x180034095  mov     rdx, [r15]
0x180034098  mov     rcx, r15
0x18003409b  mov     rax, [rdx+8]
0x18003409f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340a4  nop
0x1800340a5  mov     eax, ebx
0x1800340a7  jmp     loc_180034272
0x1800340ac  mov     rbx, [rbp+57h+phkResult]
0x1800340b0  mov     [rbp+57h+var_80], rbx
0x1800340b4  mov     [rbp+57h+phkResult], 0
0x1800340bc  cmp     qword ptr [rdi+18h], 7
0x1800340c1  jbe     short loc_1800340C8
0x1800340c3  mov     rdx, [rdi]
0x1800340c6  jmp     short loc_1800340CB
0x1800340c8  mov     rdx, rdi; lpSubKey
0x1800340cb  mov     rcx, rbx; hKey
0x1800340ce  call    cs:__imp_RegDeleteKeyW
0x1800340d4  mov     esi, eax
0x1800340d6  test    eax, eax
0x1800340d8  jz      short loc_18003414B
0x1800340da  cmp     qword ptr [rdi+18h], 7
0x1800340df  jbe     short loc_1800340E4
0x1800340e1  mov     rdi, [rdi]
0x1800340e4  movzx   r12d, si
0x1800340e8  test    esi, esi
0x1800340ea  jg      short loc_1800340F1
0x1800340ec  mov     r8d, esi
0x1800340ef  jmp     short loc_1800340FB
0x1800340f1  mov     r8d, r12d
0x1800340f4  or      r8d, 80070000h; int
0x1800340fb  mov     [rsp+0C0h+var_A0], rdi
0x180034100  lea     r9, aRegdeletekeyFa; "RegDeleteKey failed RegId: %S"
0x180034107  mov     edx, 38Eh; unsigned int
0x18003410c  lea     rcx, aCregistrationD_0; "CRegistration::Delete"
0x180034113  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180034118  test    esi, esi
0x18003411a  jle     short loc_180034125
0x18003411c  mov     esi, r12d
0x18003411f  or      esi, 80070000h
0x180034125  test    rbx, rbx
0x180034128  jz      short loc_180034134
0x18003412a  mov     rcx, rbx; hKey
0x18003412d  call    cs:__imp_RegCloseKey
0x180034133  nop
0x180034134  mov     rcx, [r15]
0x180034137  mov     rax, [rcx+8]
0x18003413b  mov     rcx, r15
0x18003413e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034143  nop
0x180034144  mov     eax, esi
0x180034146  jmp     loc_180034272
0x18003414b  mov     dword ptr [rdi+0E0h], 0
0x180034155  lea     r9, [rdi+70h]
0x180034159  cmp     qword ptr [r9+18h], 7
0x18003415e  jbe     short loc_180034163
0x180034160  mov     r9, [r9]
0x180034163  lea     r8, [rdi+50h]
0x180034167  cmp     qword ptr [r8+18h], 7
0x18003416c  jbe     short loc_180034171
0x18003416e  mov     r8, [r8]
0x180034171  lea     rdx, [rdi+30h]
0x180034175  cmp     qword ptr [rdx+18h], 7
0x18003417a  jbe     short loc_18003417F
0x18003417c  mov     rdx, [rdx]
0x18003417f  lea     rcx, [rbp+57h+lpValueName]
0x180034183  call    ?GetUniqueId@CRegistration@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00@Z; CRegistration::GetUniqueId(ushort const *,ushort const *,ushort const *)
0x180034188  nop
0x180034189  lea     r8, [rbp+57h+lpValueName]
0x18003418d  cmp     [rbp+57h+var_38], 7
0x180034192  cmova   r8, [rbp+57h+lpValueName]; lpValueName
0x180034197  lea     rsi, aRegistrationMa; "Registration\\Map"
0x18003419e  mov     rdx, rsi; lpSubKey
0x1800341a1  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x1800341a8  call    cs:__imp_RegDeleteKeyValueW
0x1800341ae  test    eax, eax
0x1800341b0  jz      loc_18003423D
0x1800341b6  lea     rcx, [rbp+57h+lpValueName]
0x1800341ba  cmp     [rbp+57h+var_38], 7
0x1800341bf  cmova   rcx, [rbp+57h+lpValueName]
0x1800341c4  test    eax, eax
0x1800341c6  jle     short loc_1800341D0
0x1800341c8  movzx   eax, ax
0x1800341cb  or      eax, 80070000h
0x1800341d0  mov     [rsp+0C0h+var_98], rcx
0x1800341d5  mov     [rsp+0C0h+var_A0], rsi
0x1800341da  lea     r9, aRegdeletekeyva; "RegDeleteKeyValue failed ValueName: %S"...
0x1800341e1  mov     r8d, eax; int
0x1800341e4  mov     edx, 39Ah; unsigned int
0x1800341e9  lea     rcx, aCregistrationD_0; "CRegistration::Delete"
0x1800341f0  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800341f5  jmp     short loc_18003423D
0x1800341f7  mov     [rbp+57h+var_90], 0
0x1800341fe  mov     rax, [rdi+0F8h]
0x180034205  mov     rcx, [rax]
0x180034208  mov     rdx, [rcx+20h]; unsigned __int64
0x18003420c  mov     [rbp+57h+var_78], rdx
0x180034210  lea     rax, [rbp+57h+var_90]
0x180034214  mov     [rsp+0C0h+var_A0], rax; int *
0x180034219  xor     r9d, r9d; int
0x18003421c  xor     r8d, r8d; int
0x18003421f  mov     rcx, rdi; this
0x180034222  call    ?AcknowledgeMessage@CRegistration@@QEAAJ_KHHPEAH@Z; CRegistration::AcknowledgeMessage(unsigned __int64,int,int,int *)
0x180034227  cmp     [rbp+57h+var_90], 0
0x18003422b  jz      short loc_18003423D
0x18003422d  lea     r8, [rbp+57h+var_78]
0x180034231  lea     rdx, [rbp+57h+var_60]
0x180034235  mov     rcx, r12
0x180034238  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEAUSmsServiceCallContext@@U?$less@PEAUSmsServiceCallContext@@@std@@V?$allocator@PEAUSmsServiceCallContext@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAUSmsServiceCallContext@@@std@@@std@@@std@@_N@1@AEBQEAUSmsServiceCallContext@@@Z; std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(SmsServiceCallContext * const &)
0x18003423d  cmp     qword ptr [rdi+100h], 0
0x180034245  ja      short loc_1800341F7
0x180034247  lea     rcx, [rbp+57h+lpValueName]; void *
0x18003424b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034250  nop
0x180034251  test    rbx, rbx
0x180034254  jz      short loc_180034260
0x180034256  mov     rcx, rbx; hKey
0x180034259  call    cs:__imp_RegCloseKey
0x18003425f  nop
0x180034260  mov     rax, [r15]
0x180034263  mov     rcx, r15
0x180034266  mov     rax, [rax+8]
0x18003426a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003426f  nop
0x180034270  xor     eax, eax
0x180034272  mov     rcx, [rbp+57h+var_30]
0x180034276  xor     rcx, rsp; StackCookie
0x180034279  call    __security_check_cookie
0x18003427e  mov     rbx, [rsp+0C0h+arg_10]
0x180034286  add     rsp, 0A0h
0x18003428d  pop     r15
0x18003428f  pop     r12
0x180034291  pop     rdi
0x180034292  pop     rsi
0x180034293  pop     rbp
0x180034294  retn
```
