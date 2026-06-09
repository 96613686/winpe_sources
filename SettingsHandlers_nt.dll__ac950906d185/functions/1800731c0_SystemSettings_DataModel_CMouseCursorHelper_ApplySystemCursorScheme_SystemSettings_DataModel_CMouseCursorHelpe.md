# SystemSettings::DataModel::CMouseCursorHelper::_ApplySystemCursorScheme(SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme const *)

- ea: `0x1800731c0`
- end: `0x1800734c7`
- name: `?_ApplySystemCursorScheme@CMouseCursorHelper@DataModel@SystemSettings@@AEAAJPEBUSMouseCursorScheme@123@@Z`
- size: `775`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CMouseCursorHelper *__hidden this, const struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180072f08`

## callees

- `0x18000c940`
- `0x1800109b0`
- `0x18002e1f4`
- `0x1800731c0`
- `0x1800740f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073376`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073402`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007344b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073376`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073402`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007344b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073330`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073330`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073219`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073219`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800732cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800732cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073482`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073482`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007325a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073298`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007325a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073298`
- `USER32!SystemParametersInfoW` at `0x180073463`
- `USER32!SystemParametersInfoW` at `0x180073463`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CMouseCursorHelper::_ApplySystemCursorScheme(
        SystemSettings::DataModel::CMouseCursorHelper *this,
        const struct SystemSettings::DataModel::CMouseCursorHelper::SMouseCursorScheme *a2)
{
  LSTATUS Value; // ebx
  HKEY *v4; // rax
  HKEY *v5; // rax
  const WCHAR *v6; // rdx
  BYTE *v7; // rax
  BYTE *v8; // r14
  const BYTE *v9; // rcx
  __int64 v10; // rax
  char v11; // r12
  const BYTE *v12; // rsi
  unsigned __int64 i; // r15
  char *v14; // rdi
  int v15; // eax
  const BYTE *v16; // rax
  bool v17; // cc
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  SystemSettings::DataModel::CMouseCursorHelper *cbData; // [rsp+A0h] [rbp+40h] BYREF
  int Data; // [rsp+B0h] [rbp+50h] BYREF
  HKEY v22; // [rsp+B8h] [rbp+58h] BYREF

  cbData = this;
  v22 = 0;
  Value = RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", 0, 0, 0, 0x20006u, 0, &v22, 0);
  if ( Value )
  {
    v17 = Value < 0;
    goto LABEL_31;
  }
  Data = 0;
  hKey[0] = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Cursors\\Schemes",
         0,
         0x20019u,
         v4) )
  {
    Data = 1;
    v5 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
    Value = RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors\\Schemes", 0, 0x20019u, v5);
    if ( Value )
      goto LABEL_28;
  }
  else
  {
    Data = 2;
  }
  v6 = (const WCHAR *)*((_QWORD *)a2 + 2);
  LODWORD(cbData) = 0;
  Value = RegQueryValueExW(hKey[0], v6, 0, 0, 0, (LPDWORD)&cbData);
  if ( !Value )
  {
    LODWORD(cbData) = (_DWORD)cbData + 2;
    v7 = (BYTE *)operator new[]((unsigned int)cbData, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      *(_WORD *)v7 = 0;
      Value = RegGetValueW(hKey[0], 0, *((LPCWSTR *)a2 + 2), 0x30000004u, 0, v7, (LPDWORD)&cbData);
      if ( !Value )
      {
        v9 = (const BYTE *)*((_QWORD *)a2 + 2);
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&v9[2 * v10] );
        Value = RegSetValueExW(v22, 0, 0, 1u, v9, 2 * v10 + 2);
        if ( !Value )
        {
          v11 = 0;
          v12 = v8;
          for ( i = 0; i < 0x11; ++i )
          {
            v14 = (char *)v12;
            if ( v12 && !v11 )
            {
              while ( *(_WORD *)v14 != 44 )
              {
                if ( !*(_WORD *)v14 )
                {
                  v11 = 1;
                  goto LABEL_21;
                }
                v14 += 2;
                if ( !v14 )
                  goto LABEL_21;
              }
              *(_WORD *)v14 = 0;
            }
LABEL_21:
            v15 = dword_18039D548;
            if ( !_bittest(&v15, i) )
              RegSetValueExW(v22, (&off_1802BC810)[2 * i], 0, 2u, v12, 2 * ((v14 - (char *)v12) >> 1) + 2);
            v16 = (const BYTE *)(v14 + 2);
            if ( v11 )
              v16 = v12;
            v12 = v16;
          }
          RegSetValueExW(v22, L"Scheme Source", 0, 4u, (const BYTE *)&Data, 4u);
          SystemParametersInfoW(0x57u, 0, 0, 2u);
          qword_18039D528 = a2;
        }
      }
      operator delete(v8);
    }
    else
    {
      Value = 8;
    }
  }
LABEL_28:
  RegCloseKey(v22);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  v17 = Value <= 0;
  if ( !Value )
    return 0;
LABEL_31:
  if ( !v17 )
    return (unsigned __int16)Value | 0x80070000;
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1800731c0  mov     r11, rsp
0x1800731c3  mov     [r11+10h], rbx
0x1800731c7  mov     [r11+8], rcx
0x1800731cb  push    rbp
0x1800731cc  push    rsi
0x1800731cd  push    rdi
0x1800731ce  push    r12
0x1800731d0  push    r13
0x1800731d2  push    r14
0x1800731d4  push    r15
0x1800731d6  mov     rbp, rsp
0x1800731d9  sub     rsp, 60h
0x1800731dd  xor     edi, edi
0x1800731df  lea     rax, [rbp+arg_18]
0x1800731e3  mov     [r11-58h], rdi
0x1800731e7  mov     r13, rdx
0x1800731ea  mov     [r11-60h], rax
0x1800731ee  lea     rdx, aControlPanelCu; "Control Panel\\Cursors"
0x1800731f5  mov     [r11-68h], rdi
0x1800731f9  mov     rsi, 0FFFFFFFF80000001h
0x180073200  mov     [rsp+60h+samDesired], 20006h; samDesired
0x180073208  xor     r9d, r9d; lpClass
0x18007320b  xor     r8d, r8d; Reserved
0x18007320e  mov     [rsp+60h+dwOptions], edi; dwOptions
0x180073212  mov     rcx, rsi; hKey
0x180073215  mov     [rbp+arg_18], rdi
0x180073219  call    cs:__imp_RegCreateKeyExW
0x180073220  nop     dword ptr [rax+rax+00h]
0x180073225  mov     ebx, eax
0x180073227  test    eax, eax
0x180073229  jnz     loc_18007349F
0x18007322f  lea     rcx, [rbp+hKey]
0x180073233  mov     [rbp+Data], edi
0x180073236  mov     [rbp+hKey], rdi
0x18007323a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18007323f  mov     ebx, 20019h
0x180073244  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x180073249  mov     r9d, ebx; samDesired
0x18007324c  lea     rdx, aSoftwareMicros_104; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180073253  xor     r8d, r8d; ulOptions
0x180073256  lea     rcx, [rsi+1]; hKey
0x18007325a  call    cs:__imp_RegOpenKeyExW
0x180073261  nop     dword ptr [rax+rax+00h]
0x180073266  test    eax, eax
0x180073268  jnz     short loc_180073273
0x18007326a  mov     [rbp+Data], 2
0x180073271  jmp     short loc_1800732AE
0x180073273  lea     rcx, [rbp+hKey]
0x180073277  mov     [rbp+Data], 1
0x18007327e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180073283  mov     r9d, ebx; samDesired
0x180073286  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x18007328b  xor     r8d, r8d; ulOptions
0x18007328e  lea     rdx, aControlPanelCu_0; "Control Panel\\Cursors\\Schemes"
0x180073295  mov     rcx, rsi; hKey
0x180073298  call    cs:__imp_RegOpenKeyExW
0x18007329f  nop     dword ptr [rax+rax+00h]
0x1800732a4  mov     ebx, eax
0x1800732a6  test    eax, eax
0x1800732a8  jnz     loc_18007347E
0x1800732ae  mov     rdx, [r13+10h]; lpValueName
0x1800732b2  lea     rax, [rbp+cbData]
0x1800732b6  mov     rcx, [rbp+hKey]; hKey
0x1800732ba  xor     r9d, r9d; lpType
0x1800732bd  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x1800732c2  xor     r8d, r8d; lpReserved
0x1800732c5  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x1800732ca  mov     dword ptr [rbp+cbData], edi
0x1800732cd  call    cs:__imp_RegQueryValueExW
0x1800732d4  nop     dword ptr [rax+rax+00h]
0x1800732d9  mov     ebx, eax
0x1800732db  test    eax, eax
0x1800732dd  jnz     loc_18007347E
0x1800732e3  mov     eax, dword ptr [rbp+cbData]
0x1800732e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800732ed  add     eax, 2
0x1800732f0  mov     ecx, eax; unsigned __int64
0x1800732f2  mov     dword ptr [rbp+cbData], eax
0x1800732f5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800732fa  mov     r14, rax
0x1800732fd  test    rax, rax
0x180073300  jnz     short loc_18007330A
0x180073302  lea     ebx, [rax+8]
0x180073305  jmp     loc_18007347E
0x18007330a  mov     [rax], di
0x18007330d  mov     r9d, 30000004h; dwFlags
0x180073313  mov     r8, [r13+10h]; lpValue
0x180073317  lea     rax, [rbp+cbData]
0x18007331b  mov     rcx, [rbp+hKey]; hkey
0x18007331f  xor     edx, edx; lpSubKey
0x180073321  mov     [rsp+60h+pcbData], rax; pcbData
0x180073326  mov     qword ptr [rsp+60h+samDesired], r14; pvData
0x18007332b  mov     qword ptr [rsp+60h+dwOptions], rdi; pdwType
0x180073330  call    cs:__imp_RegGetValueW
0x180073337  nop     dword ptr [rax+rax+00h]
0x18007333c  mov     ebx, eax
0x18007333e  test    eax, eax
0x180073340  jnz     loc_180073476
0x180073346  mov     rcx, [r13+10h]
0x18007334a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007334e  inc     rax
0x180073351  cmp     [rcx+rax*2], di
0x180073355  jnz     short loc_18007334E
0x180073357  lea     eax, ds:2[rax*2]
0x18007335e  mov     r9d, 1; dwType
0x180073364  mov     [rsp+60h+samDesired], eax; cbData
0x180073368  xor     r8d, r8d; Reserved
0x18007336b  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x180073370  xor     edx, edx; lpValueName
0x180073372  mov     rcx, [rbp+arg_18]; hKey
0x180073376  call    cs:__imp_RegSetValueExW
0x18007337d  nop     dword ptr [rax+rax+00h]
0x180073382  mov     ebx, eax
0x180073384  test    eax, eax
0x180073386  jnz     loc_180073476
0x18007338c  mov     r12b, dil
0x18007338f  mov     rsi, r14
0x180073392  mov     r15, rdi
0x180073395  mov     rdi, rsi
0x180073398  test    rsi, rsi
0x18007339b  jz      short loc_1800733BF
0x18007339d  xor     eax, eax
0x18007339f  test    r12b, r12b
0x1800733a2  jnz     short loc_1800733BF
0x1800733a4  cmp     word ptr [rdi], 2Ch ; ','
0x1800733a8  jz      short loc_1800733BC
0x1800733aa  cmp     [rdi], ax
0x1800733ad  jz      short loc_1800733B7
0x1800733af  add     rdi, 2
0x1800733b3  jnz     short loc_1800733A4
0x1800733b5  jmp     short loc_1800733BF
0x1800733b7  mov     r12b, 1
0x1800733ba  jmp     short loc_1800733BF
0x1800733bc  mov     [rdi], ax
0x1800733bf  mov     eax, cs:dword_18039D548
0x1800733c5  bt      eax, r15d
0x1800733c9  jb      short loc_18007340E
0x1800733cb  lea     rcx, off_1802BC810; "Arrow"
0x1800733d2  mov     rax, rdi
0x1800733d5  sub     rax, rsi
0x1800733d8  mov     rdx, r15
0x1800733db  sar     rax, 1
0x1800733de  add     rdx, rdx
0x1800733e1  mov     r9d, 2; dwType
0x1800733e7  xor     r8d, r8d; Reserved
0x1800733ea  mov     rdx, [rcx+rdx*8]; lpValueName
0x1800733ee  lea     eax, ds:2[rax*2]
0x1800733f5  mov     rcx, [rbp+arg_18]; hKey
0x1800733f9  mov     [rsp+60h+samDesired], eax; cbData
0x1800733fd  mov     qword ptr [rsp+60h+dwOptions], rsi; lpData
0x180073402  call    cs:__imp_RegSetValueExW
0x180073409  nop     dword ptr [rax+rax+00h]
0x18007340e  lea     rax, [rdi+2]
0x180073412  inc     r15
0x180073415  xor     edi, edi
0x180073417  test    r12b, r12b
0x18007341a  cmovnz  rax, rsi
0x18007341e  mov     rsi, rax
0x180073421  cmp     r15, 11h
0x180073425  jb      loc_180073395
0x18007342b  mov     rcx, [rbp+arg_18]; hKey
0x18007342f  lea     r9d, [rdi+4]; dwType
0x180073433  lea     rax, [rbp+Data]
0x180073437  mov     [rsp+60h+samDesired], r9d; cbData
0x18007343c  xor     r8d, r8d; Reserved
0x18007343f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180073444  lea     rdx, aSchemeSource; "Scheme Source"
0x18007344b  call    cs:__imp_RegSetValueExW
0x180073452  nop     dword ptr [rax+rax+00h]
0x180073457  lea     r9d, [rdi+2]; fWinIni
0x18007345b  xor     r8d, r8d; pvParam
0x18007345e  xor     edx, edx; uiParam
0x180073460  lea     ecx, [rdi+57h]; uiAction
0x180073463  call    cs:__imp_SystemParametersInfoW
0x18007346a  nop     dword ptr [rax+rax+00h]
0x18007346f  mov     cs:qword_18039D528, r13
0x180073476  mov     rcx, r14; Block
0x180073479  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007347e  mov     rcx, [rbp+arg_18]; hKey
0x180073482  call    cs:__imp_RegCloseKey
0x180073489  nop     dword ptr [rax+rax+00h]
0x18007348e  lea     rcx, [rbp+hKey]
0x180073492  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180073497  test    ebx, ebx
0x180073499  jnz     short loc_1800734A1
0x18007349b  mov     ebx, edi
0x18007349d  jmp     short loc_1800734AC
0x18007349f  test    ebx, ebx
0x1800734a1  jle     short loc_1800734AC
0x1800734a3  movzx   ebx, bx
0x1800734a6  or      ebx, 80070000h
0x1800734ac  mov     eax, ebx
0x1800734ae  mov     rbx, [rsp+60h+arg_8]
0x1800734b6  add     rsp, 60h
0x1800734ba  pop     r15
0x1800734bc  pop     r14
0x1800734be  pop     r13
0x1800734c0  pop     r12
0x1800734c2  pop     rdi
0x1800734c3  pop     rsi
0x1800734c4  pop     rbp
0x1800734c5  retn
```
