# CWorkspaceFtaAppRegistration::UnRegisterCapabilitiesKey(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800526f0`
- end: `0x180052aef`
- name: `?UnRegisterCapabilitiesKey@CWorkspaceFtaAppRegistration@@IEAAJPEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1023`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052af8`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x180020bf0`
- `0x18003b07c`
- `0x1800526f0`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800527c2`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800527c2`
- `ADVAPI32!RegGetValueW` at `0x1800528cb`
- `ADVAPI32!RegGetValueW` at `0x1800528cb`
- `ADVAPI32!RegCloseKey` at `0x180052ab3`
- `ADVAPI32!RegCloseKey` at `0x180052ab3`
- `ADVAPI32!RegDeleteValueW` at `0x180052a56`
- `ADVAPI32!RegDeleteValueW` at `0x180052a56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkspaceFtaAppRegistration::UnRegisterCapabilitiesKey(__int64 a1, void *hTransaction, void *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int ValueW; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // edi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rsi
  const WCHAR *v13; // rax
  __int64 v14; // rbx
  unsigned int v15; // eax
  const WCHAR *v16; // rax
  HKEY hkey; // [rsp+40h] [rbp-258h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-250h] BYREF
  __int64 v20; // [rsp+50h] [rbp-248h]
  void *v21; // [rsp+58h] [rbp-240h]
  _BYTE pvData[528]; // [rsp+60h] [rbp-238h] BYREF

  v20 = -2;
  v21 = a3;
  hkey = 0;
  pcbData = 520;
  if ( hTransaction == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024809);
    }
    ValueW = -2147024809;
    goto LABEL_60;
  }
  ValueW = RegOpenKeyTransactedW(
             HKEY_CURRENT_USER,
             L"Software\\RegisteredApplications",
             0,
             0x2001Fu,
             &hkey,
             hTransaction,
             0);
  if ( ValueW == 2 )
  {
    ValueW = 1;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_60;
    }
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 40;
    goto LABEL_12;
  }
  if ( ValueW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( ValueW > 0 )
        v9 = (unsigned __int16)ValueW | 0x80070000;
      else
        v9 = ValueW;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 41;
LABEL_21:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v10, v9);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v12 = a1 + 80;
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  ValueW = RegGetValueW(hkey, 0, v13, 2u, 0, pvData, &pcbData);
  switch ( ValueW )
  {
    case 2:
      ValueW = 1;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_60;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 42;
      goto LABEL_12;
    case 234:
      ValueW = 1;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_60;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 43;
      goto LABEL_12;
    case 0:
      if ( !(unsigned int)std::wstring::compare(a3, pvData) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            (unsigned int)WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
            v15,
            v14);
        }
        v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
        ValueW = RegDeleteValueW(hkey, v16);
        if ( !ValueW )
        {
          ValueW = 0;
          goto LABEL_60;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_22;
        }
        if ( ValueW > 0 )
          v9 = (unsigned __int16)ValueW | 0x80070000;
        else
          v9 = ValueW;
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 47;
        goto LABEL_21;
      }
      ValueW = 1;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_60;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 45;
LABEL_12:
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v7);
      goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( ValueW > 0 )
      v9 = (unsigned __int16)ValueW | 0x80070000;
    else
      v9 = ValueW;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 44;
    goto LABEL_21;
  }
LABEL_22:
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_60:
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  std::wstring::~wstring(a3);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800526f0  mov     rax, rsp
0x1800526f3  push    rbp
0x1800526f4  push    rsi
0x1800526f5  push    rdi
0x1800526f6  sub     rsp, 280h
0x1800526fd  mov     [rsp+298h+var_248], 0FFFFFFFFFFFFFFFEh
0x180052706  mov     [rax+20h], rbx
0x18005270a  mov     rax, cs:__security_cookie
0x180052711  xor     rax, rsp
0x180052714  mov     [rsp+298h+var_28], rax
0x18005271c  mov     rbp, r8
0x18005271f  mov     rsi, rcx
0x180052722  mov     [rsp+298h+var_240], r8
0x180052727  mov     [rsp+298h+hkey], 0
0x180052730  mov     [rsp+298h+pcbData], 208h
0x180052738  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18005273c  jnz     short loc_180052793
0x18005273e  lea     rdi, WPP_GLOBAL_Control
0x180052745  mov     rax, cs:WPP_GLOBAL_Control
0x18005274c  cmp     rax, rdi
0x18005274f  jz      short loc_180052789
0x180052751  test    byte ptr [rax+1Ch], 8
0x180052755  jz      short loc_180052789
0x180052757  cmp     byte ptr [rax+19h], 2
0x18005275b  jb      short loc_180052789
0x18005275d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052762  mov     edx, 27h ; '''
0x180052767  mov     dword ptr [rsp+298h+phkResult], 80070057h
0x18005276f  mov     r9d, eax
0x180052772  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052779  mov     rcx, cs:WPP_GLOBAL_Control
0x180052780  mov     rcx, [rcx+10h]
0x180052784  call    WPP_SF_Dd
0x180052789  mov     ebx, 80070057h
0x18005278e  jmp     loc_180052AA9
0x180052793  mov     [rsp+298h+pExtendedParemeter], 0; pExtendedParemeter
0x18005279c  mov     [rsp+298h+hTransaction], rdx; hTransaction
0x1800527a1  lea     rax, [rsp+298h+hkey]
0x1800527a6  mov     [rsp+298h+phkResult], rax; phkResult
0x1800527ab  mov     r9d, 2001Fh; samDesired
0x1800527b1  xor     r8d, r8d; ulOptions
0x1800527b4  lea     rdx, aSoftwareRegist; "Software\\RegisteredApplications"
0x1800527bb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800527c2  call    cs:__imp_RegOpenKeyTransactedW
0x1800527c8  mov     ebx, eax
0x1800527ca  cmp     eax, 2
0x1800527cd  jnz     short loc_180052823
0x1800527cf  lea     ebx, [rax-1]
0x1800527d2  lea     rdi, WPP_GLOBAL_Control
0x1800527d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800527e0  cmp     rax, rdi
0x1800527e3  jz      loc_180052AA9
0x1800527e9  test    [rax+1Ch], bl
0x1800527ec  jz      loc_180052AA9
0x1800527f2  cmp     byte ptr [rax+19h], 4
0x1800527f6  jb      loc_180052AA9
0x1800527fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052801  lea     edx, [rbx+27h]
0x180052804  mov     r9d, eax
0x180052807  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x18005280e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052815  mov     rcx, [rcx+10h]
0x180052819  call    WPP_SF_D
0x18005281e  jmp     loc_180052AA9
0x180052823  test    ebx, ebx
0x180052825  jz      short loc_180052892
0x180052827  lea     rdi, WPP_GLOBAL_Control
0x18005282e  mov     esi, 80070000h
0x180052833  mov     rax, cs:WPP_GLOBAL_Control
0x18005283a  cmp     rax, rdi
0x18005283d  jz      short loc_180052880
0x18005283f  test    byte ptr [rax+1Ch], 8
0x180052843  jz      short loc_180052880
0x180052845  cmp     byte ptr [rax+19h], 2
0x180052849  jb      short loc_180052880
0x18005284b  test    ebx, ebx
0x18005284d  jg      short loc_180052853
0x18005284f  mov     edi, ebx
0x180052851  jmp     short loc_180052858
0x180052853  movzx   edi, bx
0x180052856  or      edi, esi
0x180052858  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005285d  mov     edx, 29h ; ')'
0x180052862  mov     dword ptr [rsp+298h+phkResult], edi
0x180052866  mov     r9d, eax
0x180052869  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052870  mov     rcx, cs:WPP_GLOBAL_Control
0x180052877  mov     rcx, [rcx+10h]
0x18005287b  call    WPP_SF_Dd
0x180052880  test    ebx, ebx
0x180052882  jle     loc_180052AA9
0x180052888  movzx   ebx, bx
0x18005288b  or      ebx, esi
0x18005288d  jmp     loc_180052AA9
0x180052892  add     rsi, 50h ; 'P'
0x180052896  mov     rcx, rsi
0x180052899  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005289e  lea     rcx, [rsp+298h+pcbData]
0x1800528a3  mov     [rsp+298h+pExtendedParemeter], rcx; pcbData
0x1800528a8  lea     rcx, [rsp+298h+pvData]
0x1800528ad  mov     [rsp+298h+hTransaction], rcx; pvData
0x1800528b2  mov     [rsp+298h+phkResult], 0; pdwType
0x1800528bb  mov     r9d, 2; dwFlags
0x1800528c1  mov     r8, rax; lpValue
0x1800528c4  xor     edx, edx; lpSubKey
0x1800528c6  mov     rcx, [rsp+298h+hkey]; hkey
0x1800528cb  call    cs:__imp_RegGetValueW
0x1800528d1  mov     ebx, eax
0x1800528d3  cmp     eax, 2
0x1800528d6  jnz     short loc_180052912
0x1800528d8  lea     ebx, [rax-1]
0x1800528db  lea     rdi, WPP_GLOBAL_Control
0x1800528e2  mov     rax, cs:WPP_GLOBAL_Control
0x1800528e9  cmp     rax, rdi
0x1800528ec  jz      loc_180052AA9
0x1800528f2  test    [rax+1Ch], bl
0x1800528f5  jz      loc_180052AA9
0x1800528fb  cmp     byte ptr [rax+19h], 4
0x1800528ff  jb      loc_180052AA9
0x180052905  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005290a  lea     edx, [rbx+29h]
0x18005290d  jmp     loc_180052804
0x180052912  cmp     ebx, 0EAh
0x180052918  jnz     short loc_180052956
0x18005291a  mov     ebx, 1
0x18005291f  lea     rdi, WPP_GLOBAL_Control
0x180052926  mov     rax, cs:WPP_GLOBAL_Control
0x18005292d  cmp     rax, rdi
0x180052930  jz      loc_180052AA9
0x180052936  test    [rax+1Ch], bl
0x180052939  jz      loc_180052AA9
0x18005293f  cmp     byte ptr [rax+19h], 4
0x180052943  jb      loc_180052AA9
0x180052949  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005294e  lea     edx, [rbx+2Ah]
0x180052951  jmp     loc_180052804
0x180052956  test    ebx, ebx
0x180052958  jz      short loc_1800529A6
0x18005295a  lea     rdi, WPP_GLOBAL_Control
0x180052961  mov     esi, 80070000h
0x180052966  mov     rax, cs:WPP_GLOBAL_Control
0x18005296d  cmp     rax, rdi
0x180052970  jz      loc_180052880
0x180052976  test    byte ptr [rax+1Ch], 8
0x18005297a  jz      loc_180052880
0x180052980  cmp     byte ptr [rax+19h], 2
0x180052984  jb      loc_180052880
0x18005298a  test    ebx, ebx
0x18005298c  jg      short loc_180052992
0x18005298e  mov     edi, ebx
0x180052990  jmp     short loc_180052997
0x180052992  movzx   edi, bx
0x180052995  or      edi, esi
0x180052997  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005299c  mov     edx, 2Ch ; ','
0x1800529a1  jmp     loc_180052862
0x1800529a6  lea     rdx, [rsp+298h+pvData]
0x1800529ab  mov     rcx, rbp
0x1800529ae  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHPEBG@Z; std::wstring::compare(ushort const *)
0x1800529b3  test    eax, eax
0x1800529b5  jz      short loc_1800529F3
0x1800529b7  mov     ebx, 1
0x1800529bc  lea     rdi, WPP_GLOBAL_Control
0x1800529c3  mov     rax, cs:WPP_GLOBAL_Control
0x1800529ca  cmp     rax, rdi
0x1800529cd  jz      loc_180052AA9
0x1800529d3  test    [rax+1Ch], bl
0x1800529d6  jz      loc_180052AA9
0x1800529dc  cmp     byte ptr [rax+19h], 4
0x1800529e0  jb      loc_180052AA9
0x1800529e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800529eb  lea     edx, [rbx+2Ch]
0x1800529ee  jmp     loc_180052804
0x1800529f3  lea     rdi, WPP_GLOBAL_Control
0x1800529fa  mov     rax, cs:WPP_GLOBAL_Control
0x180052a01  cmp     rax, rdi
0x180052a04  jz      short loc_180052A46
0x180052a06  test    byte ptr [rax+1Ch], 1
0x180052a0a  jz      short loc_180052A46
0x180052a0c  cmp     byte ptr [rax+19h], 4
0x180052a10  jb      short loc_180052A46
0x180052a12  mov     rcx, rsi
0x180052a15  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052a1a  mov     rbx, rax
0x180052a1d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052a22  mov     edx, 2Eh ; '.'
0x180052a27  mov     [rsp+298h+phkResult], rbx
0x180052a2c  mov     r9d, eax
0x180052a2f  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180052a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a3d  mov     rcx, [rcx+10h]
0x180052a41  call    WPP_SF_DS
0x180052a46  mov     rcx, rsi
0x180052a49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052a4e  mov     rdx, rax; lpValueName
0x180052a51  mov     rcx, [rsp+298h+hkey]; hKey
0x180052a56  call    cs:__imp_RegDeleteValueW
0x180052a5c  mov     ebx, eax
0x180052a5e  test    eax, eax
0x180052a60  jz      short loc_180052AA7
0x180052a62  mov     esi, 80070000h
0x180052a67  mov     rax, cs:WPP_GLOBAL_Control
0x180052a6e  cmp     rax, rdi
0x180052a71  jz      loc_180052880
0x180052a77  test    byte ptr [rax+1Ch], 8
0x180052a7b  jz      loc_180052880
0x180052a81  cmp     byte ptr [rax+19h], 2
0x180052a85  jb      loc_180052880
0x180052a8b  test    ebx, ebx
0x180052a8d  jg      short loc_180052A93
0x180052a8f  mov     edi, ebx
0x180052a91  jmp     short loc_180052A98
0x180052a93  movzx   edi, bx
0x180052a96  or      edi, esi
0x180052a98  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180052a9d  mov     edx, 2Fh ; '/'
0x180052aa2  jmp     loc_180052862
0x180052aa7  xor     ebx, ebx
0x180052aa9  mov     rcx, [rsp+298h+hkey]; hKey
0x180052aae  test    rcx, rcx
0x180052ab1  jz      short loc_180052AC2
0x180052ab3  call    cs:__imp_RegCloseKey
0x180052ab9  mov     [rsp+298h+hkey], 0
0x180052ac2  mov     rcx, rbp; void *
0x180052ac5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052aca  mov     eax, ebx
0x180052acc  mov     rcx, [rsp+298h+var_28]
0x180052ad4  xor     rcx, rsp; StackCookie
0x180052ad7  call    __security_check_cookie
0x180052adc  mov     rbx, [rsp+298h+arg_18]
0x180052ae4  add     rsp, 280h
0x180052aeb  pop     rdi
0x180052aec  pop     rsi
0x180052aed  pop     rbp
0x180052aee  retn
```
