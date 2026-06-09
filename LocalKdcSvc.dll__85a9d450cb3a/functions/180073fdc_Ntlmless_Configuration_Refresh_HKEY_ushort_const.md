# Ntlmless::Configuration::Refresh(HKEY__ *,ushort const *)

- ea: `0x180073fdc`
- end: `0x18007419b`
- name: `?Refresh@Configuration@Ntlmless@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `447`
- prototype: `__int64 __fastcall(Ntlmless::Configuration *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001ce0`

## callees

- `0x180002ad0`
- `0x1800101ec`
- `0x1800351d0`
- `0x18003ff0c`
- `0x180073fdc`
- `0x180074624`
- `0x1800746b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074049`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074049`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800740eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800740eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ntlmless::Configuration::Refresh(Ntlmless::Configuration *this, HKEY a2, const unsigned __int16 *a3)
{
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 *v7; // rsi
  __int64 v8; // rbx
  LSTATUS ValueW; // eax
  int v10; // edx
  int v11; // r8d
  signed int v12; // ecx
  char v13; // al
  int pvData; // [rsp+40h] [rbp-9h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-1h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp+7h] BYREF
  _QWORD v17[3]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+70h] [rbp+27h] BYREF

  v17[0] = &Ntlmless::g_config;
  v17[1] = &off_1800B2268;
  v17[2] = &off_1800B2278;
  hkey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Parameters",
         0,
         0x20019u,
         phkResult);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
    v7 = v17;
    do
    {
      v8 = *v7;
      pvData = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, *(LPCWSTR *)v8, 0x10u, 0, &pvData, &pcbData);
      v12 = ValueW;
      if ( ValueW > 0 )
        v12 = (unsigned __int16)ValueW | 0x80070000;
      if ( v12 < 0 || pvData == *(_DWORD *)(v8 + 8) )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SDL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)WPP_GLOBAL_Control,
            v11,
            *(_QWORD *)v8,
            v12,
            *(_DWORD *)(v8 + 8));
        }
        v13 = *(_BYTE *)(v8 + 12);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *(_QWORD *)v8, pvData);
        }
        v13 = *(_BYTE *)(v8 + 12) == 0;
      }
      *(_BYTE *)(v8 + 13) = v13;
      ++v7;
    }
    while ( v7 != &v18 );
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e373ffb564f23e745796b9a76c1df621_Traceguids, v5);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return v5;
  }
}

```

## disassembly

```asm
0x180073fdc  push    rbp
0x180073fde  push    rbx
0x180073fdf  push    rsi
0x180073fe0  push    rdi
0x180073fe1  lea     rbp, [rsp-3Fh]
0x180073fe6  sub     rsp, 88h
0x180073fed  mov     rax, cs:__security_cookie
0x180073ff4  xor     rax, rsp
0x180073ff7  mov     [rbp+57h+var_30], rax
0x180073ffb  lea     rax, ?g_config@Ntlmless@@3UConfiguration@1@A; Ntlmless::Configuration Ntlmless::g_config
0x180074002  mov     [rbp+57h+var_48], rax
0x180074006  lea     rax, off_1800B2268; "LocalKdcBackout"
0x18007400d  mov     [rbp+57h+var_40], rax
0x180074011  lea     rax, off_1800B2278; "LocalKdcServerOptIn"
0x180074018  mov     [rbp+57h+var_38], rax
0x18007401c  mov     [rbp+57h+hkey], 0
0x180074024  lea     rcx, [rbp+57h+hkey]
0x180074028  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18007402d  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180074032  mov     r9d, 20019h; samDesired
0x180074038  xor     r8d, r8d; ulOptions
0x18007403b  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Lsa"...
0x180074042  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180074049  call    cs:__imp_RegOpenKeyExW
0x18007404f  mov     ebx, eax
0x180074051  test    eax, eax
0x180074053  jle     short loc_18007405E
0x180074055  movzx   ebx, ax
0x180074058  or      ebx, 80070000h
0x18007405e  test    ebx, ebx
0x180074060  jns     short loc_1800740A5
0x180074062  lea     rdi, WPP_GLOBAL_Control
0x180074069  mov     rcx, cs:WPP_GLOBAL_Control
0x180074070  cmp     rcx, rdi
0x180074073  jz      short loc_180074094
0x180074075  test    byte ptr [rcx+1Ch], 1
0x180074079  jz      short loc_180074094
0x18007407b  mov     edx, 0Ah
0x180074080  mov     r9d, ebx
0x180074083  lea     r8, WPP_e373ffb564f23e745796b9a76c1df621_Traceguids
0x18007408a  mov     rcx, [rcx+10h]
0x18007408e  call    WPP_SF_d
0x180074093  nop
0x180074094  lea     rcx, [rbp+57h+hkey]
0x180074098  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007409d  nop
0x18007409e  mov     eax, ebx
0x1800740a0  jmp     loc_180074183
0x1800740a5  lea     rsi, [rbp+57h+var_48]
0x1800740a9  lea     rdi, WPP_GLOBAL_Control
0x1800740b0  mov     rbx, [rsi]
0x1800740b3  mov     [rbp+57h+var_60], 0
0x1800740ba  mov     [rbp+57h+var_50], 4
0x1800740c1  lea     rax, [rbp+57h+var_50]
0x1800740c5  mov     [rsp+0A0h+pcbData], rax; pcbData
0x1800740ca  lea     rax, [rbp+57h+var_60]
0x1800740ce  mov     [rsp+0A0h+pvData], rax; pvData
0x1800740d3  mov     [rsp+0A0h+phkResult], 0; pdwType
0x1800740dc  mov     r9d, 10h; dwFlags
0x1800740e2  mov     r8, [rbx]; lpValue
0x1800740e5  xor     edx, edx; lpSubKey
0x1800740e7  mov     rcx, [rbp+57h+hkey]; hkey
0x1800740eb  call    cs:__imp_RegGetValueW
0x1800740f1  mov     ecx, eax
0x1800740f3  test    eax, eax
0x1800740f5  jle     short loc_180074100
0x1800740f7  movzx   ecx, ax
0x1800740fa  or      ecx, 80070000h
0x180074100  test    ecx, ecx
0x180074102  js      short loc_180074137
0x180074104  mov     eax, [rbp+57h+var_60]
0x180074107  cmp     eax, [rbx+8]
0x18007410a  jz      short loc_180074137
0x18007410c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074113  cmp     rcx, rdi
0x180074116  jz      short loc_18007412E
0x180074118  test    byte ptr [rcx+1Ch], 4
0x18007411c  jz      short loc_18007412E
0x18007411e  mov     dword ptr [rsp+0A0h+phkResult], eax
0x180074122  mov     r9, [rbx]
0x180074125  mov     rcx, [rcx+10h]
0x180074129  call    WPP_SF_SL
0x18007412e  cmp     byte ptr [rbx+0Ch], 0
0x180074132  setz    al
0x180074135  jmp     short loc_180074163
0x180074137  mov     rdx, cs:WPP_GLOBAL_Control
0x18007413e  cmp     rdx, rdi
0x180074141  jz      short loc_180074160
0x180074143  test    byte ptr [rdx+1Ch], 4
0x180074147  jz      short loc_180074160
0x180074149  mov     eax, [rbx+8]
0x18007414c  mov     dword ptr [rsp+0A0h+pvData], eax
0x180074150  mov     dword ptr [rsp+0A0h+phkResult], ecx
0x180074154  mov     r9, [rbx]
0x180074157  mov     rcx, [rdx+10h]
0x18007415b  call    WPP_SF_SDL
0x180074160  mov     al, [rbx+0Ch]
0x180074163  mov     [rbx+0Dh], al
0x180074166  add     rsi, 8
0x18007416a  lea     rax, [rbp+57h+var_30]
0x18007416e  cmp     rsi, rax
0x180074171  jnz     loc_1800740B0
0x180074177  lea     rcx, [rbp+57h+hkey]
0x18007417b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180074180  nop
0x180074181  xor     eax, eax
0x180074183  mov     rcx, [rbp+57h+var_30]
0x180074187  xor     rcx, rsp; StackCookie
0x18007418a  call    __security_check_cookie
0x18007418f  add     rsp, 88h
0x180074196  pop     rdi
0x180074197  pop     rsi
0x180074198  pop     rbx
0x180074199  pop     rbp
0x18007419a  retn
```
