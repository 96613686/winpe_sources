# Microsoft::Windows::Autopilot::RegistryPolicyManager::GetStringPolicy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800270e0`
- end: `0x1800272d9`
- name: `?GetStringPolicy@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `505`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800105f4`
- `0x1800166dc`
- `0x1800182f4`
- `0x1800270e0`
- `0x1800272e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800271db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800271db`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027182`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027293`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027182`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027293`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027124`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027247`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027124`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027247`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271f9`

## string_xrefs

- `0x18002720c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1800272a2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

## pseudocode

```c
int __fastcall Microsoft::Windows::Autopilot::RegistryPolicyManager::GetStringPolicy(
        __int64 a1,
        const WCHAR *a2,
        HLOCAL *a3)
{
  bool v3; // cc
  const WCHAR *v5; // rdi
  const WCHAR *v6; // rbx
  char v7; // al
  char IsStateSeparationEnabled; // al
  const WCHAR *v9; // r15
  const WCHAR *v10; // rdx
  LSTATUS ValueW; // r12d
  int result; // eax
  __int64 v13; // rdx
  HLOCAL v14; // rbp
  HLOCAL v15; // r14
  DWORD LastError; // ebx
  HLOCAL v17; // rcx
  HLOCAL pvData; // rbx
  char v19; // al
  char v20; // al
  unsigned int v21; // eax
  int pdwType; // [rsp+20h] [rbp-58h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-58h]
  HLOCAL hMem[2]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD pcbData; // [rsp+88h] [rbp+10h] BYREF

  v3 = *((_QWORD *)a2 + 3) <= 7u;
  v5 = a2;
  pcbData = 0;
  if ( v3 )
    v6 = a2;
  else
    v6 = *(const WCHAR **)a2;
  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v7 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    v7 = IsStateSeparationEnabled != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v7;
  }
  v9 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  v10 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  if ( !v7 )
    v10 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v10, v6, 2u, 0, 0, &pcbData);
  result = Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(ValueW);
  if ( result >= 0 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      hMem,
      0,
      (unsigned __int64)pcbData >> 1);
    if ( a3 == hMem )
    {
      v17 = hMem[0];
    }
    else
    {
      v14 = *a3;
      v15 = hMem[0];
      if ( *a3 )
      {
        LastError = GetLastError();
        LocalFree(v14);
        SetLastError(LastError);
      }
      *a3 = v15;
      v17 = 0;
    }
    if ( v17 )
      LocalFree(v17);
    pvData = *a3;
    if ( *a3 )
    {
      if ( *((_QWORD *)v5 + 3) > 7u )
        v5 = *(const WCHAR **)v5;
      if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
      {
        v19 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
      }
      else
      {
        v20 = RtlIsStateSeparationEnabled(v17, v13);
        `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
        v19 = v20 != 0;
        `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v19;
      }
      if ( !v19 )
        v9 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
      v21 = RegGetValueW(HKEY_LOCAL_MACHINE, v9, v5, 2u, 0, pvData, &pcbData);
      if ( v21 )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x64,
                 (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
                 (const char *)v21,
                 pdwTypea);
      else
        return Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(ValueW);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
        (const char *)0x8007000ELL,
        pdwType);
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800270e0  mov     rax, rsp
0x1800270e3  mov     [rax+8], rbx
0x1800270e7  mov     [rax+18h], rbp
0x1800270eb  push    rsi
0x1800270ec  push    rdi
0x1800270ed  push    r12
0x1800270ef  push    r14
0x1800270f1  push    r15
0x1800270f3  sub     rsp, 50h
0x1800270f7  cmp     qword ptr [rdx+18h], 7
0x1800270fc  mov     rsi, r8
0x1800270ff  mov     rdi, rdx
0x180027102  mov     dword ptr [rax+10h], 0
0x180027109  jbe     short loc_180027110
0x18002710b  mov     rbx, [rdx]
0x18002710e  jmp     short loc_180027113
0x180027110  mov     rbx, rdi
0x180027113  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18002711a  jz      short loc_180027124
0x18002711c  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180027122  jmp     short loc_18002713C
0x180027124  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002712a  test    al, al
0x18002712c  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180027133  setnz   al
0x180027136  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18002713c  test    al, al
0x18002713e  lea     r15, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180027145  lea     rax, [rsp+78h+arg_8]
0x18002714d  mov     rdx, r15
0x180027150  mov     [rsp+78h+pcbData], rax; pcbData
0x180027155  lea     rbp, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x18002715c  cmovz   rdx, rbp; lpSubKey
0x180027160  mov     [rsp+78h+pvData], 0; pvData
0x180027169  mov     r9d, 2; dwFlags
0x18002716f  mov     [rsp+78h+pdwType], 0; int
0x180027178  mov     r8, rbx; lpValue
0x18002717b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180027182  call    cs:__imp_RegGetValueW
0x180027188  mov     ecx, eax; int
0x18002718a  mov     r12d, eax
0x18002718d  call    ?HandleRegGetValueResult@RegistryPolicyManager@Autopilot@Windows@Microsoft@@CAJJ@Z; Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(long)
0x180027192  test    eax, eax
0x180027194  js      loc_1800272C0
0x18002719a  mov     r8d, [rsp+78h+arg_8]
0x1800271a2  lea     rcx, [rsp+78h+hMem]
0x1800271a7  shr     r8, 1
0x1800271aa  xor     edx, edx
0x1800271ac  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800271b1  lea     rax, [rsp+78h+hMem]
0x1800271b6  cmp     rsi, rax
0x1800271b9  jz      short loc_1800271EF
0x1800271bb  mov     rbp, [rsi]
0x1800271be  mov     r14, [rsp+78h+hMem]
0x1800271c3  test    rbp, rbp
0x1800271c6  jz      short loc_1800271E1
0x1800271c8  call    cs:__imp_GetLastError
0x1800271ce  mov     rcx, rbp; hMem
0x1800271d1  mov     ebx, eax
0x1800271d3  call    cs:__imp_LocalFree
0x1800271d9  mov     ecx, ebx; dwErrCode
0x1800271db  call    cs:__imp_SetLastError
0x1800271e1  mov     [rsi], r14
0x1800271e4  lea     rbp, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800271eb  xor     ecx, ecx
0x1800271ed  jmp     short loc_1800271F4
0x1800271ef  mov     rcx, [rsp+78h+hMem]; hMem
0x1800271f4  test    rcx, rcx
0x1800271f7  jz      short loc_1800271FF
0x1800271f9  call    cs:__imp_LocalFree
0x1800271ff  mov     rbx, [rsi]
0x180027202  test    rbx, rbx
0x180027205  jnz     short loc_18002722C
0x180027207  mov     rcx, [rsp+78h]; this
0x18002720c  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027213  mov     ebx, 8007000Eh
0x180027218  mov     edx, 61h ; 'a'; void *
0x18002721d  mov     r9d, ebx; char *
0x180027220  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027225  mov     eax, ebx
0x180027227  jmp     loc_1800272C0
0x18002722c  cmp     qword ptr [rdi+18h], 7
0x180027231  jbe     short loc_180027236
0x180027233  mov     rdi, [rdi]
0x180027236  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18002723d  jz      short loc_180027247
0x18002723f  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180027245  jmp     short loc_18002725F
0x180027247  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002724d  test    al, al
0x18002724f  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180027256  setnz   al
0x180027259  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18002725f  test    al, al
0x180027261  mov     r9d, 2; dwFlags
0x180027267  lea     rax, [rsp+78h+arg_8]
0x18002726f  mov     r8, rdi; lpValue
0x180027272  mov     [rsp+78h+pcbData], rax; pcbData
0x180027277  cmovz   r15, rbp
0x18002727b  mov     rdx, r15; lpSubKey
0x18002727e  mov     [rsp+78h+pvData], rbx; pvData
0x180027283  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002728a  mov     [rsp+78h+pdwType], 0; unsigned int
0x180027293  call    cs:__imp_RegGetValueW
0x180027299  test    eax, eax
0x18002729b  jz      short loc_1800272B8
0x18002729d  mov     rcx, [rsp+78h]; this
0x1800272a2  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800272a9  mov     r9d, eax; char *
0x1800272ac  mov     edx, 64h ; 'd'; void *
0x1800272b1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800272b6  jmp     short loc_1800272C0
0x1800272b8  mov     ecx, r12d; int
0x1800272bb  call    ?HandleRegGetValueResult@RegistryPolicyManager@Autopilot@Windows@Microsoft@@CAJJ@Z; Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(long)
0x1800272c0  lea     r11, [rsp+78h+var_28]
0x1800272c5  mov     rbx, [r11+30h]
0x1800272c9  mov     rbp, [r11+40h]
0x1800272cd  mov     rsp, r11
0x1800272d0  pop     r15
0x1800272d2  pop     r14
0x1800272d4  pop     r12
0x1800272d6  pop     rdi
0x1800272d7  pop     rsi
0x1800272d8  retn
```
