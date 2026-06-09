# Microsoft::Windows::Autopilot::RegistryPolicyManager::GetStringPolicy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800280d0`
- end: `0x1800282fa`
- name: `?GetStringPolicy@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `554`
- prototype: `int __fastcall(__int64, const WCHAR *, HLOCAL *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180010764`
- `0x180016b80`
- `0x180018854`
- `0x1800280d0`
- `0x180028300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800281e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800281e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028178`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800282ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028178`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800282ad`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180028114`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002825b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180028114`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002825b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800281d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028207`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800281d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028207`

## string_xrefs

- `0x180028220`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1800282c2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

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
  const char *v13; // r9
  __int64 v14; // rdx
  HLOCAL v15; // rbp
  HLOCAL v16; // r14
  DWORD LastError; // ebx
  HLOCAL v18; // rcx
  HLOCAL pvData; // rbx
  char v20; // al
  char v21; // al
  unsigned int v22; // eax
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
      (unsigned __int64)pcbData >> 1,
      v13);
    if ( a3 == hMem )
    {
      v18 = hMem[0];
    }
    else
    {
      v15 = *a3;
      v16 = hMem[0];
      if ( *a3 )
      {
        LastError = GetLastError();
        LocalFree(v15);
        SetLastError(LastError);
      }
      *a3 = v16;
      v18 = 0;
    }
    if ( v18 )
      LocalFree(v18);
    pvData = *a3;
    if ( *a3 )
    {
      if ( *((_QWORD *)v5 + 3) > 7u )
        v5 = *(const WCHAR **)v5;
      if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
      {
        v20 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
      }
      else
      {
        v21 = RtlIsStateSeparationEnabled(v18, v14);
        `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
        v20 = v21 != 0;
        `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v20;
      }
      if ( !v20 )
        v9 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
      v22 = RegGetValueW(HKEY_LOCAL_MACHINE, v9, v5, 2u, 0, pvData, &pcbData);
      if ( v22 )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x64,
                 (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
                 (const char *)v22,
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
0x1800280d0  mov     rax, rsp
0x1800280d3  mov     [rax+8], rbx
0x1800280d7  mov     [rax+18h], rbp
0x1800280db  push    rsi
0x1800280dc  push    rdi
0x1800280dd  push    r12
0x1800280df  push    r14
0x1800280e1  push    r15
0x1800280e3  sub     rsp, 50h
0x1800280e7  cmp     qword ptr [rdx+18h], 7
0x1800280ec  mov     rsi, r8
0x1800280ef  mov     rdi, rdx
0x1800280f2  mov     dword ptr [rax+10h], 0
0x1800280f9  jbe     short loc_180028100
0x1800280fb  mov     rbx, [rdx]
0x1800280fe  jmp     short loc_180028103
0x180028100  mov     rbx, rdi
0x180028103  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18002810a  jz      short loc_180028114
0x18002810c  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180028112  jmp     short loc_180028132
0x180028114  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002811b  nop     dword ptr [rax+rax+00h]
0x180028120  test    al, al
0x180028122  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180028129  setnz   al
0x18002812c  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180028132  test    al, al
0x180028134  lea     r15, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18002813b  lea     rax, [rsp+78h+arg_8]
0x180028143  mov     rdx, r15
0x180028146  mov     [rsp+78h+pcbData], rax; pcbData
0x18002814b  lea     rbp, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180028152  cmovz   rdx, rbp; lpSubKey
0x180028156  mov     [rsp+78h+pvData], 0; pvData
0x18002815f  mov     r9d, 2; dwFlags
0x180028165  mov     [rsp+78h+pdwType], 0; int
0x18002816e  mov     r8, rbx; lpValue
0x180028171  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180028178  call    cs:__imp_RegGetValueW
0x18002817f  nop     dword ptr [rax+rax+00h]
0x180028184  mov     ecx, eax; int
0x180028186  mov     r12d, eax
0x180028189  call    ?HandleRegGetValueResult@RegistryPolicyManager@Autopilot@Windows@Microsoft@@CAJJ@Z; Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(long)
0x18002818e  test    eax, eax
0x180028190  js      loc_1800282E0
0x180028196  mov     r8d, [rsp+78h+arg_8]
0x18002819e  lea     rcx, [rsp+78h+hMem]
0x1800281a3  shr     r8, 1
0x1800281a6  xor     edx, edx
0x1800281a8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800281ad  lea     rax, [rsp+78h+hMem]
0x1800281b2  cmp     rsi, rax
0x1800281b5  jz      short loc_1800281FD
0x1800281b7  mov     rbp, [rsi]
0x1800281ba  mov     r14, [rsp+78h+hMem]
0x1800281bf  test    rbp, rbp
0x1800281c2  jz      short loc_1800281EF
0x1800281c4  call    cs:__imp_GetLastError
0x1800281cb  nop     dword ptr [rax+rax+00h]
0x1800281d0  mov     rcx, rbp; hMem
0x1800281d3  mov     ebx, eax
0x1800281d5  call    cs:__imp_LocalFree
0x1800281dc  nop     dword ptr [rax+rax+00h]
0x1800281e1  mov     ecx, ebx; dwErrCode
0x1800281e3  call    cs:__imp_SetLastError
0x1800281ea  nop     dword ptr [rax+rax+00h]
0x1800281ef  mov     [rsi], r14
0x1800281f2  lea     rbp, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800281f9  xor     ecx, ecx
0x1800281fb  jmp     short loc_180028202
0x1800281fd  mov     rcx, [rsp+78h+hMem]; hMem
0x180028202  test    rcx, rcx
0x180028205  jz      short loc_180028213
0x180028207  call    cs:__imp_LocalFree
0x18002820e  nop     dword ptr [rax+rax+00h]
0x180028213  mov     rbx, [rsi]
0x180028216  test    rbx, rbx
0x180028219  jnz     short loc_180028240
0x18002821b  mov     rcx, [rsp+78h]; this
0x180028220  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028227  mov     ebx, 8007000Eh
0x18002822c  mov     edx, 61h ; 'a'; void *
0x180028231  mov     r9d, ebx; char *
0x180028234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028239  mov     eax, ebx
0x18002823b  jmp     loc_1800282E0
0x180028240  cmp     qword ptr [rdi+18h], 7
0x180028245  jbe     short loc_18002824A
0x180028247  mov     rdi, [rdi]
0x18002824a  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180028251  jz      short loc_18002825B
0x180028253  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180028259  jmp     short loc_180028279
0x18002825b  call    cs:__imp_RtlIsStateSeparationEnabled
0x180028262  nop     dword ptr [rax+rax+00h]
0x180028267  test    al, al
0x180028269  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180028270  setnz   al
0x180028273  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180028279  test    al, al
0x18002827b  mov     r9d, 2; dwFlags
0x180028281  lea     rax, [rsp+78h+arg_8]
0x180028289  mov     r8, rdi; lpValue
0x18002828c  mov     [rsp+78h+pcbData], rax; pcbData
0x180028291  cmovz   r15, rbp
0x180028295  mov     rdx, r15; lpSubKey
0x180028298  mov     [rsp+78h+pvData], rbx; pvData
0x18002829d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800282a4  mov     [rsp+78h+pdwType], 0; unsigned int
0x1800282ad  call    cs:__imp_RegGetValueW
0x1800282b4  nop     dword ptr [rax+rax+00h]
0x1800282b9  test    eax, eax
0x1800282bb  jz      short loc_1800282D8
0x1800282bd  mov     rcx, [rsp+78h]; this
0x1800282c2  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800282c9  mov     r9d, eax; char *
0x1800282cc  mov     edx, 64h ; 'd'; void *
0x1800282d1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800282d6  jmp     short loc_1800282E0
0x1800282d8  mov     ecx, r12d; int
0x1800282db  call    ?HandleRegGetValueResult@RegistryPolicyManager@Autopilot@Windows@Microsoft@@CAJJ@Z; Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(long)
0x1800282e0  lea     r11, [rsp+78h+var_28]
0x1800282e5  mov     rbx, [r11+30h]
0x1800282e9  mov     rbp, [r11+40h]
0x1800282ed  mov     rsp, r11
0x1800282f0  pop     r15
0x1800282f2  pop     r14
0x1800282f4  pop     r12
0x1800282f6  pop     rdi
0x1800282f7  pop     rsi
0x1800282f8  retn
```
