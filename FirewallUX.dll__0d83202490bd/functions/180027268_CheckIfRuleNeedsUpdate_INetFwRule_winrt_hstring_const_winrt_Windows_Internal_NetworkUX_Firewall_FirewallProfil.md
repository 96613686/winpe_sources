# CheckIfRuleNeedsUpdate(INetFwRule *,winrt::hstring const &,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,bool,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,bool *,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes *,winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes *)

- ea: `0x180027268`
- end: `0x180027491`
- name: `?CheckIfRuleNeedsUpdate@@YAJPEAUINetFwRule@@AEBUhstring@winrt@@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@3@_N22PEA_NPEAW4456783@5@Z`
- size: `553`
- prototype: `__int64 __fastcall(__int64, __int64, int, char, int, int, _BYTE *, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180026784`

## callees

- `0x180009544`
- `0x18000b5f0`
- `0x180022944`
- `0x180027268`
- `0x18002913c`
- `0x18002d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800272e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180027478`
- `OLEAUT32!__imp_SysFreeString` at `0x1800272e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180027478`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002730c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002730c`

## string_xrefs

- `0x1800272ce`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`
- `0x180027403`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CheckIfRuleNeedsUpdate(
        __int64 a1,
        __int64 a2,
        int a3,
        char a4,
        int a5,
        int a6,
        _BYTE *a7,
        _DWORD *a8,
        int *a9)
{
  _DWORD *v13; // r13
  _BYTE *v14; // r14
  int v15; // ebx
  __int64 v16; // rdx
  const WCHAR *v18; // rdx
  unsigned int v19; // r8d
  int v20; // ebx
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rdx
  BSTR bstrString; // [rsp+20h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]
  int v27; // [rsp+80h] [rbp+48h] BYREF

  v13 = a8;
  *a8 = 0;
  *a9 = 0;
  v14 = a7;
  *a7 = 0;
  bstrString = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a1 + 88LL))(a1, &bstrString);
  if ( v15 < 0 )
  {
    v16 = 301;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v15,
      (int)bstrString);
    if ( bstrString )
      SysFreeString(bstrString);
    return (unsigned int)v15;
  }
  if ( *(_QWORD *)a2 )
    v18 = *(const WCHAR **)(*(_QWORD *)a2 + 16LL);
  else
    v18 = &szFile;
  if ( !lstrcmpiW(bstrString, v18) )
  {
    LODWORD(a7) = 0;
    LODWORD(a8) = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)a1 + 328LL))(a1, &a7);
    if ( v15 < 0 )
    {
      v16 = 311;
      goto LABEL_3;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)a1 + 296LL))(a1, &a8);
    if ( v15 < 0 )
    {
      v16 = 312;
      goto LABEL_3;
    }
    v20 = a5;
    if ( !(_DWORD)a7 && (_DWORD)a8 != a5 )
    {
      v21 = 317;
LABEL_17:
      wil::details::in1diag3::Log_Hr(retaddr, (void *)v21, v19, (const char *)0x8000FFFFLL, (int)bstrString);
      goto LABEL_38;
    }
    if ( !a4 )
    {
      if ( !(_DWORD)a7 )
      {
        *v14 = 1;
        goto LABEL_38;
      }
      v21 = 325;
      goto LABEL_17;
    }
    if ( (_DWORD)a7 == 1 )
    {
      if ( (a3 & (unsigned int)a8) == 0 )
        goto LABEL_38;
    }
    else
    {
      if ( (_DWORD)a7 )
      {
        v21 = 335;
        goto LABEL_17;
      }
      if ( (a3 & a5) == 0 )
        goto LABEL_38;
    }
    v25[0] = 0;
    v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))a1)(
            a1,
            &GUID_9c27c8da_189b_4dde_89f7_8b39a316782c,
            v25);
    if ( v22 >= 0 )
    {
      v27 = 0;
      v22 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v25[0] + 344LL))(v25[0], &v27);
      if ( v22 >= 0 )
      {
        if ( !v27 || (_DWORD)a7 != 1 )
        {
          *v14 = 1;
          *v13 = a3;
          *a9 = a6 & ~v20;
        }
        goto LABEL_36;
      }
      v23 = 361;
    }
    else
    {
      v23 = 355;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)v22,
      (int)bstrString);
LABEL_36:
    if ( v25[0] )
      winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(v25);
  }
LABEL_38:
  if ( bstrString )
    SysFreeString(bstrString);
  return 0;
}

```

## disassembly

```asm
0x180027268  push    rbp
0x18002726a  push    rbx
0x18002726b  push    rsi
0x18002726c  push    rdi
0x18002726d  push    r12
0x18002726f  push    r13
0x180027271  push    r14
0x180027273  push    r15
0x180027275  mov     rbp, rsp
0x180027278  sub     rsp, 38h
0x18002727c  mov     r12b, r9b
0x18002727f  mov     esi, r8d
0x180027282  mov     r15, rdx
0x180027285  mov     rdi, rcx
0x180027288  xor     ecx, ecx
0x18002728a  mov     r13, [rbp+arg_38]
0x180027291  mov     [r13+0], ecx
0x180027295  mov     rax, [rbp+arg_40]
0x18002729c  mov     [rax], ecx
0x18002729e  mov     r14, [rbp+arg_30]
0x1800272a2  mov     [r14], cl
0x1800272a5  mov     [rbp+bstrString], rcx
0x1800272a9  mov     rax, [rdi]
0x1800272ac  lea     rdx, [rbp+bstrString]
0x1800272b0  mov     rcx, rdi
0x1800272b3  mov     rax, [rax+58h]
0x1800272b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272bc  mov     ebx, eax
0x1800272be  test    eax, eax
0x1800272c0  jns     short loc_1800272F0
0x1800272c2  mov     edx, 12Dh; void *
0x1800272c7  mov     rcx, [rbp+40h]; this
0x1800272cb  mov     r9d, ebx; char *
0x1800272ce  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x1800272d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800272da  mov     rcx, [rbp+bstrString]; bstrString
0x1800272de  test    rcx, rcx
0x1800272e1  jz      short loc_1800272E9
0x1800272e3  call    cs:__imp_SysFreeString
0x1800272e9  mov     eax, ebx
0x1800272eb  jmp     loc_180027480
0x1800272f0  mov     rax, [r15]
0x1800272f3  xor     r15d, r15d
0x1800272f6  test    rax, rax
0x1800272f9  jz      short loc_180027301
0x1800272fb  mov     rdx, [rax+10h]
0x1800272ff  jmp     short loc_180027308
0x180027301  lea     rdx, szFile; lpString2
0x180027308  mov     rcx, [rbp+bstrString]; lpString1
0x18002730c  call    cs:__imp_lstrcmpiW
0x180027312  test    eax, eax
0x180027314  jnz     loc_18002746F
0x18002731a  mov     dword ptr [rbp+arg_30], r15d
0x18002731e  mov     dword ptr [rbp+arg_38], r15d
0x180027325  mov     rax, [rdi]
0x180027328  lea     rdx, [rbp+arg_30]
0x18002732c  mov     rcx, rdi
0x18002732f  mov     rax, [rax+148h]
0x180027336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002733b  mov     ebx, eax
0x18002733d  test    eax, eax
0x18002733f  jns     short loc_18002734B
0x180027341  mov     edx, 137h
0x180027346  jmp     loc_1800272C7
0x18002734b  mov     rax, [rdi]
0x18002734e  lea     rdx, [rbp+arg_38]
0x180027355  mov     rcx, rdi
0x180027358  mov     rax, [rax+128h]
0x18002735f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027364  mov     ebx, eax
0x180027366  test    eax, eax
0x180027368  jns     short loc_180027374
0x18002736a  mov     edx, 138h
0x18002736f  jmp     loc_1800272C7
0x180027374  mov     ebx, [rbp+arg_20]
0x180027377  mov     eax, dword ptr [rbp+arg_30]
0x18002737a  test    eax, eax
0x18002737c  jnz     short loc_18002739F
0x18002737e  cmp     dword ptr [rbp+arg_38], ebx
0x180027384  jz      short loc_18002739F
0x180027386  mov     edx, 13Dh; void *
0x18002738b  mov     rcx, [rbp+40h]; this
0x18002738f  mov     r9d, 8000FFFFh; char *
0x180027395  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002739a  jmp     loc_18002746F
0x18002739f  test    r12b, r12b
0x1800273a2  jnz     short loc_1800273B8
0x1800273a4  test    eax, eax
0x1800273a6  jz      short loc_1800273AF
0x1800273a8  mov     edx, 145h
0x1800273ad  jmp     short loc_18002738B
0x1800273af  mov     byte ptr [r14], 1
0x1800273b3  jmp     loc_18002746F
0x1800273b8  cmp     eax, 1
0x1800273bb  jz      short loc_1800273D1
0x1800273bd  test    eax, eax
0x1800273bf  jz      short loc_1800273C8
0x1800273c1  mov     edx, 14Fh
0x1800273c6  jmp     short loc_18002738B
0x1800273c8  test    ebx, esi
0x1800273ca  jnz     short loc_1800273DD
0x1800273cc  jmp     loc_18002746F
0x1800273d1  test    dword ptr [rbp+arg_38], esi
0x1800273d7  jz      loc_18002746F
0x1800273dd  mov     [rbp+var_10], r15
0x1800273e1  mov     rax, [rdi]
0x1800273e4  lea     r8, [rbp+var_10]
0x1800273e8  lea     rdx, _GUID_9c27c8da_189b_4dde_89f7_8b39a316782c
0x1800273ef  mov     rcx, rdi
0x1800273f2  mov     rax, [rax]
0x1800273f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273fa  test    eax, eax
0x1800273fc  jns     short loc_180027418
0x1800273fe  mov     edx, 163h; void *
0x180027403  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x18002740a  mov     r9d, eax; char *
0x18002740d  mov     rcx, [rbp+40h]; this
0x180027411  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027416  jmp     short loc_180027460
0x180027418  mov     [rbp+arg_0], r15d
0x18002741c  mov     rcx, [rbp+var_10]
0x180027420  mov     rax, [rcx]
0x180027423  lea     rdx, [rbp+arg_0]
0x180027427  mov     rax, [rax+158h]
0x18002742e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027433  test    eax, eax
0x180027435  jns     short loc_18002743E
0x180027437  mov     edx, 169h
0x18002743c  jmp     short loc_180027403
0x18002743e  cmp     [rbp+arg_0], r15d
0x180027442  jz      short loc_18002744A
0x180027444  cmp     dword ptr [rbp+arg_30], 1
0x180027448  jz      short loc_180027460
0x18002744a  mov     byte ptr [r14], 1
0x18002744e  mov     [r13+0], esi
0x180027452  not     ebx
0x180027454  and     ebx, [rbp+arg_28]
0x180027457  mov     rax, [rbp+arg_40]
0x18002745e  mov     [rax], ebx
0x180027460  cmp     [rbp+var_10], r15
0x180027464  jz      short loc_18002746F
0x180027466  lea     rcx, [rbp+var_10]
0x18002746a  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x18002746f  mov     rcx, [rbp+bstrString]; bstrString
0x180027473  test    rcx, rcx
0x180027476  jz      short loc_18002747E
0x180027478  call    cs:__imp_SysFreeString
0x18002747e  xor     eax, eax
0x180027480  add     rsp, 38h
0x180027484  pop     r15
0x180027486  pop     r14
0x180027488  pop     r13
0x18002748a  pop     r12
0x18002748c  pop     rdi
0x18002748d  pop     rsi
0x18002748e  pop     rbx
0x18002748f  pop     rbp
0x180027490  retn
```
