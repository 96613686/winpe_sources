# DCompTreeHost::ContainerVisualsEnabled(void)

- ea: `0x180104190`
- end: `0x18010447e`
- name: `?ContainerVisualsEnabled@DCompTreeHost@@SA_NXZ`
- size: `750`
- prototype: `bool __fastcall()`
- caller_count: `25`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a710`
- `0x180101ca0`
- `0x180104f34`
- `0x1801148a4`
- `0x18013d014`
- `0x1801975f0`
- `0x18019ec08`
- `0x1801f6638`
- `0x1801f6700`
- `0x1801f675c`
- `0x1801f6a20`
- `0x1801f6ae0`
- `0x1801f6bac`
- `0x18021b4c0`
- `0x1802223d0`
- `0x180256320`
- `0x180276128`
- `0x18027751c`
- `0x180278344`
- `0x1803e75d8`
- `0x1803e7844`
- `0x1803e86fc`
- `0x1804dc730`
- `0x1805f5070`
- `0x1805f62cc`

## callees

- `0x180070c4c`
- `0x180104190`
- `0x180153724`
- `0x1801b8d78`
- `0x18076e59c`
- `0x18076e7fc`
- `0x18076e864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180104344`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010440a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180104344`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010440a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180104310`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801043d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180104310`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801043d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104419`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1801042c3`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1801042c3`

## pseudocode

```c
bool __fastcall DCompTreeHost::ContainerVisualsEnabled()
{
  bool result; // al
  bool v1; // bp
  RuntimeFeatureBehavior::RuntimeEnabledFeatureDetector *Ptr; // rsi
  char v3; // di
  char v4; // di
  char v5; // bl
  char v6; // bl
  __int64 v7; // rdx
  char v8; // cl
  int v9; // eax
  char v10; // cl
  int v11; // eax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  if ( s_containerVisualsEnabledInitialized )
    return s_containerVisualsEnabled;
  v1 = !CQuirksMode2::m_quirksDisabledForProcess
    && !CQuirksMode2::IsXamlPresenterAssociated()
    && (unsigned int)QuirkIsEnabled(131195, v7) != 0;
  if ( _TSS0_50 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 40LL) )
  {
    Init_thread_header(&_TSS0_50);
    if ( _TSS0_50 == -1 )
    {
      RuntimeFeatureBehavior::GetRuntimeEnabledFeatureDetector(&runtimeEnabledFeatureDetector_31);
      atexit(DCompTreeHost::ContainerVisualsEnabled_::_5_::_dynamic_atexit_destructor_for__runtimeEnabledFeatureDetector__);
      Init_thread_footer(&_TSS0_50);
    }
  }
  Ptr = runtimeEnabledFeatureDetector_31._Ptr;
  v3 = (char)runtimeEnabledFeatureDetector_31._Ptr->m_runtimeFeatureStates[21];
  if ( (v3 & 4) != 0 )
  {
    v4 = v3 & 1;
  }
  else if ( (v3 & 8) != 0 )
  {
    v4 = (v3 & 2) != 0;
  }
  else
  {
    Data = 0;
    hKey = 0;
    v4 = 1;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(
              hKey,
              RuntimeFeatureBehavior::s_runtimeFeatureData[21].FeatureName,
              0,
              0,
              (LPBYTE)&Data,
              &cbData) )
        v4 = Data != 0;
      RegCloseKey(hKey);
    }
    v8 = *(_BYTE *)&Ptr->m_runtimeFeatureStates[21] ^ (*(_BYTE *)&Ptr->m_runtimeFeatureStates[21] ^ (2 * v4)) & 2;
    *(_BYTE *)&Ptr->m_runtimeFeatureStates[21] = v8;
    v9 = Data;
    *(_BYTE *)&Ptr->m_runtimeFeatureStates[21] = v8 | 0x18;
    Ptr->m_runtimeFeatureStates[21].CacheDwordData = v9;
    Ptr = runtimeEnabledFeatureDetector_31._Ptr;
  }
  v5 = (char)Ptr->m_runtimeFeatureStates[22];
  if ( (v5 & 4) != 0 )
  {
    v6 = v5 & 1;
  }
  else if ( (v5 & 8) != 0 )
  {
    v6 = (v5 & 2) != 0;
  }
  else
  {
    Data = 0;
    hKey = 0;
    v6 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\XAML", 0, 0x20019u, &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(
              hKey,
              RuntimeFeatureBehavior::s_runtimeFeatureData[22].FeatureName,
              0,
              0,
              (LPBYTE)&Data,
              &cbData) )
        v6 = Data != 0;
      RegCloseKey(hKey);
    }
    v10 = *(_BYTE *)&Ptr->m_runtimeFeatureStates[22] ^ (*(_BYTE *)&Ptr->m_runtimeFeatureStates[22] ^ (2 * v6)) & 2;
    *(_BYTE *)&Ptr->m_runtimeFeatureStates[22] = v10;
    v11 = Data;
    *(_BYTE *)&Ptr->m_runtimeFeatureStates[22] = v10 | 0x18;
    Ptr->m_runtimeFeatureStates[22].CacheDwordData = v11;
  }
  result = DCompTreeHost::SpriteVisualsEnabled();
  if ( !v1 && v4 || v6 || result )
    result = 1;
  s_containerVisualsEnabled = result;
  s_containerVisualsEnabledInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x180104190  sub     rsp, 58h
0x180104194  cmp     cs:s_containerVisualsEnabledInitialized, 0
0x18010419b  jz      short loc_1801041A9
0x18010419d  movzx   eax, cs:s_containerVisualsEnabled
0x1801041a4  add     rsp, 58h
0x1801041a8  retn
0x1801041a9  cmp     cs:?m_quirksDisabledForProcess@CQuirksMode2@@0_NA, 0; bool CQuirksMode2::m_quirksDisabledForProcess
0x1801041b0  mov     [rsp+58h+var_8], rbx
0x1801041b5  mov     [rsp+58h+var_10], rbp
0x1801041ba  mov     [rsp+58h+var_18], rsi
0x1801041bf  mov     [rsp+58h+var_20], rdi
0x1801041c4  jz      loc_1801042B1
0x1801041ca  xor     bpl, bpl
0x1801041cd  mov     ecx, cs:_tls_index
0x1801041d3  mov     rax, gs:58h
0x1801041dc  mov     edx, 28h ; '('
0x1801041e1  mov     rax, [rax+rcx*8]
0x1801041e5  mov     eax, [rdx+rax]
0x1801041e8  cmp     cs:$TSS0_50, eax
0x1801041ee  jle     short loc_180104229
0x1801041f0  lea     rcx, $TSS0_50; pOnce
0x1801041f7  call    _Init_thread_header
0x1801041fc  cmp     cs:$TSS0_50, 0FFFFFFFFh
0x180104203  jnz     short loc_180104229
0x180104205  lea     rcx, runtimeEnabledFeatureDetector_31; result
0x18010420c  call    ?GetRuntimeEnabledFeatureDetector@RuntimeFeatureBehavior@@YA?AV?$shared_ptr@VRuntimeEnabledFeatureDetector@RuntimeFeatureBehavior@@@std@@XZ; RuntimeFeatureBehavior::GetRuntimeEnabledFeatureDetector(void)
0x180104211  lea     rcx, _DCompTreeHost__ContainerVisualsEnabled____5____dynamic_atexit_destructor_for__runtimeEnabledFeatureDetector__; function
0x180104218  call    atexit
0x18010421d  lea     rcx, $TSS0_50; pOnce
0x180104224  call    _Init_thread_footer
0x180104229  mov     rsi, cs:runtimeEnabledFeatureDetector_31._Ptr
0x180104230  movzx   edi, byte ptr [rsi+0A8h]
0x180104237  test    dil, 4
0x18010423b  jnz     loc_180104455
0x180104241  test    dil, 8
0x180104245  jz      loc_1801042D4
0x18010424b  shr     dil, 1
0x18010424e  and     dil, 1
0x180104252  movzx   ebx, byte ptr [rsi+0B0h]
0x180104259  test    bl, 4
0x18010425c  jnz     loc_18010445E
0x180104262  test    bl, 8
0x180104265  jz      loc_180104396
0x18010426b  shr     bl, 1
0x18010426d  and     bl, 1
0x180104270  call    ?SpriteVisualsEnabled@DCompTreeHost@@SA_NXZ; DCompTreeHost::SpriteVisualsEnabled(void)
0x180104275  mov     rsi, [rsp+58h+var_18]
0x18010427a  test    bpl, bpl
0x18010427d  mov     rbp, [rsp+58h+var_10]
0x180104282  jnz     short loc_1801042A7
0x180104284  test    dil, dil
0x180104287  jz      short loc_1801042A7
0x180104289  mov     al, 1
0x18010428b  mov     rdi, [rsp+58h+var_20]
0x180104290  mov     rbx, [rsp+58h+var_8]
0x180104295  mov     cs:s_containerVisualsEnabled, al
0x18010429b  mov     cs:s_containerVisualsEnabledInitialized, 1
0x1801042a2  add     rsp, 58h
0x1801042a6  retn
0x1801042a7  test    bl, bl
0x1801042a9  jnz     short loc_180104289
0x1801042ab  test    al, al
0x1801042ad  jnz     short loc_180104289
0x1801042af  jmp     short loc_18010428B
0x1801042b1  call    ?IsXamlPresenterAssociated@CQuirksMode2@@SA_NXZ; CQuirksMode2::IsXamlPresenterAssociated(void)
0x1801042b6  test    al, al
0x1801042b8  jnz     loc_1801041CA
0x1801042be  mov     ecx, 2007Bh
0x1801042c3  call    cs:__imp_QuirkIsEnabled
0x1801042c9  test    eax, eax
0x1801042cb  setnz   bpl
0x1801042cf  jmp     loc_1801041CD
0x1801042d4  mov     rbx, cs:?s_runtimeFeatureData@RuntimeFeatureBehavior@@3QBURuntimeEnabledFeatureData@1@B.FeatureName+1F8h; RuntimeFeatureBehavior::RuntimeEnabledFeatureData const near * const RuntimeFeatureBehavior::s_runtimeFeatureData ...
0x1801042db  lea     rax, [rsp+58h+hKey]
0x1801042e0  mov     r9d, 20019h; samDesired
0x1801042e6  mov     [rsp+58h+phkResult], rax; phkResult
0x1801042eb  xor     r8d, r8d; ulOptions
0x1801042ee  mov     [rsp+58h+Data], 0
0x1801042f6  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\XAML"
0x1801042fd  mov     [rsp+58h+hKey], 0
0x180104306  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18010430d  mov     dil, 1
0x180104310  call    cs:__imp_RegOpenKeyExW
0x180104316  test    eax, eax
0x180104318  jnz     short loc_18010435D
0x18010431a  mov     rcx, [rsp+58h+hKey]; hKey
0x18010431f  lea     rax, [rsp+58h+cbData]
0x180104324  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180104329  xor     r9d, r9d; lpType
0x18010432c  lea     rax, [rsp+58h+Data]
0x180104331  mov     [rsp+58h+cbData], 4
0x180104339  xor     r8d, r8d; lpReserved
0x18010433c  mov     [rsp+58h+phkResult], rax; lpData
0x180104341  mov     rdx, rbx; lpValueName
0x180104344  call    cs:__imp_RegQueryValueExW
0x18010434a  test    eax, eax
0x18010434c  jz      loc_180104466
0x180104352  mov     rcx, [rsp+58h+hKey]; hKey
0x180104357  call    cs:__imp_RegCloseKey
0x18010435d  movzx   eax, byte ptr [rsi+0A8h]
0x180104364  movzx   ecx, dil
0x180104368  add     cl, cl
0x18010436a  xor     cl, al
0x18010436c  and     cl, 2
0x18010436f  xor     cl, al
0x180104371  mov     [rsi+0A8h], cl
0x180104377  or      cl, 18h
0x18010437a  mov     eax, [rsp+58h+Data]
0x18010437e  mov     [rsi+0A8h], cl
0x180104384  mov     [rsi+0ACh], eax
0x18010438a  mov     rsi, cs:runtimeEnabledFeatureDetector_31._Ptr
0x180104391  jmp     loc_180104252
0x180104396  lea     rax, [rsp+58h+hKey]
0x18010439b  mov     [rsp+58h+var_28], r14
0x1801043a0  mov     r14, cs:?s_runtimeFeatureData@RuntimeFeatureBehavior@@3QBURuntimeEnabledFeatureData@1@B.FeatureName+210h; RuntimeFeatureBehavior::RuntimeEnabledFeatureData const near * const RuntimeFeatureBehavior::s_runtimeFeatureData ...
0x1801043a7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\XAML"
0x1801043ae  mov     r9d, 20019h; samDesired
0x1801043b4  mov     [rsp+58h+phkResult], rax; phkResult
0x1801043b9  xor     r8d, r8d; ulOptions
0x1801043bc  mov     [rsp+58h+Data], 0
0x1801043c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801043cb  mov     [rsp+58h+hKey], 0
0x1801043d4  xor     bl, bl
0x1801043d6  call    cs:__imp_RegOpenKeyExW
0x1801043dc  test    eax, eax
0x1801043de  jnz     short loc_18010441F
0x1801043e0  mov     rcx, [rsp+58h+hKey]; hKey
0x1801043e5  lea     rax, [rsp+58h+cbData]
0x1801043ea  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1801043ef  xor     r9d, r9d; lpType
0x1801043f2  lea     rax, [rsp+58h+Data]
0x1801043f7  mov     [rsp+58h+cbData], 4
0x1801043ff  xor     r8d, r8d; lpReserved
0x180104402  mov     [rsp+58h+phkResult], rax; lpData
0x180104407  mov     rdx, r14; lpValueName
0x18010440a  call    cs:__imp_RegQueryValueExW
0x180104410  test    eax, eax
0x180104412  jz      short loc_180104474
0x180104414  mov     rcx, [rsp+58h+hKey]; hKey
0x180104419  call    cs:__imp_RegCloseKey
0x18010441f  movzx   eax, byte ptr [rsi+0B0h]
0x180104426  movzx   ecx, bl
0x180104429  mov     r14, [rsp+58h+var_28]
0x18010442e  add     cl, cl
0x180104430  xor     cl, al
0x180104432  and     cl, 2
0x180104435  xor     cl, al
0x180104437  mov     [rsi+0B0h], cl
0x18010443d  or      cl, 18h
0x180104440  mov     eax, [rsp+58h+Data]
0x180104444  mov     [rsi+0B0h], cl
0x18010444a  mov     [rsi+0B4h], eax
0x180104450  jmp     loc_180104270
0x180104455  and     dil, 1
0x180104459  jmp     loc_180104252
0x18010445e  and     bl, 1
0x180104461  jmp     loc_180104270
0x180104466  cmp     [rsp+58h+Data], 0
0x18010446b  setnz   dil
0x18010446f  jmp     loc_180104352
0x180104474  cmp     [rsp+58h+Data], 0
0x180104479  setnz   bl
0x18010447c  jmp     short loc_180104414
```
