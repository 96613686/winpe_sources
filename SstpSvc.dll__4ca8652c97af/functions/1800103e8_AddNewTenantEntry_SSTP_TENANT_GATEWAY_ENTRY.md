# AddNewTenantEntry(_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x1800103e8`
- end: `0x18001060f`
- name: `?AddNewTenantEntry@@YAKPEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(struct _SSTP_TENANT_GATEWAY_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800138c0`

## callees

- `0x180007c34`
- `0x18000827c`
- `0x180008360`
- `0x18000f77c`
- `0x18000fbb0`
- `0x18000fd1c`
- `0x1800103e8`
- `0x1800124fc`
- `0x180012560`
- `0x180013000`
- `0x18001bab0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800104bf`
- `msvcrt!_wcsicmp` at `0x1800104bf`

## string_xrefs

- `0x1800104e4`: `SstpSvcCreateUpdateTenantGatewayMapping: Duplicate Gateway name %ws`
- `0x180010565`: `SstpSvcCreateUpdateTenantGatewayMapping: Invalid Gateway name %ws`

## pseudocode

```c
__int64 __fastcall AddNewTenantEntry(struct _SSTP_TENANT_GATEWAY_ENTRY *a1)
{
  unsigned int v2; // r13d
  unsigned int i; // r15d
  __int64 v4; // r12
  __int64 j; // rsi
  unsigned __int64 v6; // rbx
  bool v7; // zf
  const wchar_t *v8; // rdx
  __int64 v9; // rax
  struct TenantGatewayMap *Instance; // [rsp+20h] [rbp-E0h]
  __int128 v12; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h]
  _QWORD v14[5]; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v12 = 0;
  v13 = 0;
  v2 = 0;
  Instance = TenantGatewayMap::GetInstance();
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  for ( i = 0; i < *((_DWORD *)a1 + 4); ++i )
  {
    v4 = 510LL * i;
    v2 = CheckGatewayName((PCWSTR)(v4 + *((_QWORD *)a1 + 3)));
    if ( v2 )
    {
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v15,
          L"SstpSvcCreateUpdateTenantGatewayMapping: Invalid Gateway name %ws",
          v4 + *((_QWORD *)a1 + 3));
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v15);
      }
    }
    else
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        v6 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v12 + 1) - v12) >> 3);
        v7 = (unsigned int)j == v6;
        if ( (unsigned int)j >= v6 )
          break;
        v8 = (const wchar_t *)(v12 + 40 * j);
        if ( *((_QWORD *)v8 + 3) >= 8u )
          v8 = *(const wchar_t **)v8;
        if ( !_wcsicmp((const wchar_t *)(v4 + *((_QWORD *)a1 + 3)), v8) )
        {
          if ( (byte_18002D803 & 0x10) != 0 )
          {
            LOWORD(v15) = 0;
            FormatRRASErrorString(
              &v15,
              L"SstpSvcCreateUpdateTenantGatewayMapping: Duplicate Gateway name %ws",
              v4 + *((_QWORD *)a1 + 3));
            if ( (byte_18002D803 & 0x10) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v15);
          }
          v7 = (unsigned int)j == v6;
          break;
        }
      }
      if ( v7 )
      {
        std::wstring::wstring((__int64)v14, v4 + *((_QWORD *)a1 + 3));
        std::vector<std::wstring>::push_back(&v12, v14);
        std::wstring::_Tidy(v14, 1, 0);
      }
    }
  }
  std::wstring::wstring((__int64)v14, *((_QWORD *)a1 + 1));
  v9 = std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](
         (char *)Instance + 8,
         v14);
  std::vector<std::wstring>::operator=(v9, &v12);
  std::wstring::_Tidy(v14, 1, 0);
  std::vector<std::wstring>::_Tidy((__int64)&v12);
  return v2;
}

```

## disassembly

```asm
0x1800103e8  push    rbp
0x1800103ea  push    rbx
0x1800103eb  push    rsi
0x1800103ec  push    rdi
0x1800103ed  push    r12
0x1800103ef  push    r13
0x1800103f1  push    r14
0x1800103f3  push    r15
0x1800103f5  lea     rbp, [rsp-788h]
0x1800103fd  sub     rsp, 888h
0x180010404  mov     rax, cs:__security_cookie
0x18001040b  xor     rax, rsp
0x18001040e  mov     [rbp+7C0h+var_50], rax
0x180010415  mov     rdi, rcx
0x180010418  xorps   xmm0, xmm0
0x18001041b  movdqu  [rsp+8C0h+var_898], xmm0
0x180010421  mov     [rsp+8C0h+var_888], 0
0x18001042a  xor     r13d, r13d
0x18001042d  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180010432  mov     [rsp+8C0h+var_8A0], rax
0x180010437  xor     eax, eax
0x180010439  mov     [rsp+8C0h+var_850], eax
0x18001043d  xor     edx, edx; Val
0x18001043f  mov     r8d, 7FCh; Size
0x180010445  lea     rcx, [rsp+8C0h+var_84C]; void *
0x18001044a  call    memset_0
0x18001044f  xor     r15d, r15d
0x180010452  cmp     r15d, [rdi+10h]
0x180010456  jnb     loc_18001059F
0x18001045c  mov     eax, r15d
0x18001045f  imul    r12, rax, 1FEh
0x180010466  mov     rcx, [rdi+18h]
0x18001046a  add     rcx, r12; pszName
0x18001046d  call    CheckGatewayName
0x180010472  mov     r13d, eax
0x180010475  test    eax, eax
0x180010477  jnz     loc_18001054E
0x18001047d  xor     esi, esi
0x18001047f  mov     r14d, esi
0x180010482  mov     rbx, qword ptr [rsp+8C0h+var_898+8]
0x180010487  mov     rcx, qword ptr [rsp+8C0h+var_898]
0x18001048c  sub     rbx, rcx
0x18001048f  sar     rbx, 3
0x180010493  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001049d  imul    rbx, rax
0x1800104a1  cmp     r14, rbx
0x1800104a4  jnb     short loc_180010519
0x1800104a6  lea     rax, [rsi+rsi*4]
0x1800104aa  lea     rdx, [rcx+rax*8]
0x1800104ae  cmp     qword ptr [rdx+18h], 8
0x1800104b3  jb      short loc_1800104B8
0x1800104b5  mov     rdx, [rdx]; String2
0x1800104b8  mov     rcx, [rdi+18h]
0x1800104bc  add     rcx, r12; String1
0x1800104bf  call    cs:__imp__wcsicmp
0x1800104c5  test    eax, eax
0x1800104c7  jz      short loc_1800104CD
0x1800104c9  inc     esi
0x1800104cb  jmp     short loc_18001047F
0x1800104cd  test    cs:byte_18002D803, 10h
0x1800104d4  jz      short loc_180010516
0x1800104d6  xor     eax, eax
0x1800104d8  mov     word ptr [rsp+8C0h+var_850], ax
0x1800104dd  mov     r8, [rdi+18h]
0x1800104e1  add     r8, r12
0x1800104e4  lea     rdx, aSstpsvccreateu_5; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x1800104eb  lea     rcx, [rsp+8C0h+var_850]
0x1800104f0  call    FormatRRASErrorString
0x1800104f5  test    cs:byte_18002D803, 10h
0x1800104fc  jz      short loc_180010516
0x1800104fe  lea     r8, [rsp+8C0h+var_850]
0x180010503  lea     rdx, RasSSTPSvcTraceInfo
0x18001050a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010511  call    McTemplateU0z_EventWriteTransfer
0x180010516  cmp     r14, rbx
0x180010519  jnz     short loc_180010597
0x18001051b  mov     rdx, [rdi+18h]
0x18001051f  add     rdx, r12
0x180010522  lea     rcx, [rsp+8C0h+var_878]
0x180010527  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001052c  nop
0x18001052d  lea     rdx, [rsp+8C0h+var_878]
0x180010532  lea     rcx, [rsp+8C0h+var_898]
0x180010537  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18001053c  nop
0x18001053d  xor     r8d, r8d
0x180010540  mov     dl, 1
0x180010542  lea     rcx, [rsp+8C0h+var_878]
0x180010547  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001054c  jmp     short loc_180010597
0x18001054e  test    cs:byte_18002D803, 8
0x180010555  jz      short loc_180010597
0x180010557  xor     eax, eax
0x180010559  mov     word ptr [rsp+8C0h+var_850], ax
0x18001055e  mov     r8, [rdi+18h]
0x180010562  add     r8, r12
0x180010565  lea     rdx, aSstpsvccreateu_3; "SstpSvcCreateUpdateTenantGatewayMapping"...
0x18001056c  lea     rcx, [rsp+8C0h+var_850]
0x180010571  call    FormatRRASErrorString
0x180010576  test    cs:byte_18002D803, 8
0x18001057d  jz      short loc_180010597
0x18001057f  lea     r8, [rsp+8C0h+var_850]
0x180010584  lea     rdx, RasSSTPSvcTraceError
0x18001058b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010592  call    McTemplateU0z_EventWriteTransfer
0x180010597  inc     r15d
0x18001059a  jmp     loc_180010452
0x18001059f  mov     rbx, [rsp+8C0h+var_8A0]
0x1800105a4  mov     rdx, [rdi+8]
0x1800105a8  lea     rcx, [rsp+8C0h+var_878]
0x1800105ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800105b2  nop
0x1800105b3  lea     rdx, [rsp+8C0h+var_878]
0x1800105b8  lea     rcx, [rbx+8]
0x1800105bc  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAAAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::operator[](std::wstring &&)
0x1800105c1  mov     rcx, rax
0x1800105c4  lea     rdx, [rsp+8C0h+var_898]
0x1800105c9  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x1800105ce  nop
0x1800105cf  xor     r8d, r8d
0x1800105d2  mov     dl, 1
0x1800105d4  lea     rcx, [rsp+8C0h+var_878]
0x1800105d9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800105de  nop
0x1800105df  lea     rcx, [rsp+8C0h+var_898]
0x1800105e4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800105e9  mov     eax, r13d
0x1800105ec  mov     rcx, [rbp+7C0h+var_50]
0x1800105f3  xor     rcx, rsp; StackCookie
0x1800105f6  call    __security_check_cookie
0x1800105fb  add     rsp, 888h
0x180010602  pop     r15
0x180010604  pop     r14
0x180010606  pop     r13
0x180010608  pop     r12
0x18001060a  pop     rdi
0x18001060b  pop     rsi
0x18001060c  pop     rbx
0x18001060d  pop     rbp
0x18001060e  retn
```
