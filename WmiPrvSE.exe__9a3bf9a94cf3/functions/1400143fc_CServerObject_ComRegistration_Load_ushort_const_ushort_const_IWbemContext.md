# CServerObject_ComRegistration::Load(ushort const *,ushort const *,IWbemContext *)

- ea: `0x1400143fc`
- end: `0x1400145d1`
- name: `?Load@CServerObject_ComRegistration@@QEAAJPEBG0PEAUIWbemContext@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(CServerObject_ComRegistration *__hidden this, OLECHAR *psz, OLECHAR *, struct IWbemContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140015130`

## callees

- `0x1400143fc`
- `0x140014860`
- `0x140014f2c`
- `0x140014fa4`
- `0x140015074`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001450c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001450c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400144cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400144cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014531`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014531`
- `OLEAUT32!__imp_SysAllocString` at `0x140014560`
- `OLEAUT32!__imp_SysAllocString` at `0x14001457d`
- `OLEAUT32!__imp_SysAllocString` at `0x140014560`
- `OLEAUT32!__imp_SysAllocString` at `0x14001457d`
- `OLEAUT32!__imp_SysFreeString` at `0x14001453b`
- `OLEAUT32!__imp_SysFreeString` at `0x140014592`
- `OLEAUT32!__imp_SysFreeString` at `0x1400145a5`
- `OLEAUT32!__imp_SysFreeString` at `0x14001453b`
- `OLEAUT32!__imp_SysFreeString` at `0x140014592`
- `OLEAUT32!__imp_SysFreeString` at `0x1400145a5`

## string_xrefs

- `0x140014454`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CServerObject_ComRegistration::Load(
        CServerObject_ComRegistration *this,
        OLECHAR *psz,
        OLECHAR *a3,
        struct IWbemContext *a4)
{
  OLECHAR *v6; // rcx
  OLECHAR *v9; // rcx
  int AppId; // edi
  int ServerTypes; // eax
  bool v12; // zf
  int v13; // r9d
  BSTR v15; // rax
  BSTR v16; // rax
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  v6 = (OLECHAR *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    SysFreeString(v6);
    *((_QWORD *)this + 4) = 0;
  }
  if ( psz )
  {
    v15 = SysAllocString(psz);
    *((_QWORD *)this + 4) = v15;
    if ( !v15 )
      return 2147749894LL;
  }
  v9 = (OLECHAR *)*((_QWORD *)this + 6);
  if ( v9 )
  {
    SysFreeString(v9);
    *((_QWORD *)this + 6) = 0;
  }
  if ( a3 )
  {
    v16 = SysAllocString(a3);
    *((_QWORD *)this + 6) = v16;
    if ( !v16 )
      return 2147749894LL;
  }
  lpSubKey = 0;
  AppId = WmiHelper::ConcatenateStrings(2u, (BSTR *)&lpSubKey, L"CLSID\\", psz);
  if ( AppId >= 0 )
  {
    CServerObject_ComRegistration::CalculateBitness(this, lpSubKey, a4);
    ServerTypes = CServerObject_ComRegistration::Load_ServerTypes(this, lpSubKey);
    v12 = *((_DWORD *)this + 404) == 32;
    AppId = ServerTypes;
    v13 = 512;
    hKey = 0;
    if ( !v12 )
      v13 = 256;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, v13 | 0x20019, &hKey) )
    {
      Type = 1;
      cbData = 520;
      RegQueryValueExW(hKey, CServerObject_ComRegistration::s_Strings_Reg_Null, 0, &Type, (LPBYTE)this + 1096, &cbData);
      AppId = CServerObject_ComRegistration::Load_AppId(this, hKey);
      if ( AppId >= 0 && *((_DWORD *)this + 4) != 1 && *((_DWORD *)this + 5) != 1 )
      {
        *((_DWORD *)this + 6) = 1;
        *((_QWORD *)this + 1) = 2;
      }
      RegCloseKey(hKey);
    }
    SysFreeString((BSTR)lpSubKey);
    if ( AppId >= 0 )
      *((_DWORD *)this + 7) = 1;
  }
  return (unsigned int)AppId;
}

```

## disassembly

```asm
0x1400143fc  mov     [rsp-18h+arg_10], rbx
0x140014401  mov     [rsp-18h+arg_18], rsi
0x140014406  push    rbp
0x140014407  push    rdi
0x140014408  push    r14
0x14001440a  mov     rbp, rsp
0x14001440d  sub     rsp, 40h
0x140014411  mov     rbx, rcx
0x140014414  mov     r14, r9
0x140014417  mov     rcx, [rcx+20h]; bstrString
0x14001441b  mov     rsi, r8
0x14001441e  mov     rdi, rdx
0x140014421  test    rcx, rcx
0x140014424  jnz     loc_140014592
0x14001442a  test    rdi, rdi
0x14001442d  jnz     loc_14001455D
0x140014433  mov     rcx, [rbx+30h]; bstrString
0x140014437  test    rcx, rcx
0x14001443a  jnz     loc_1400145A5
0x140014440  test    rsi, rsi
0x140014443  jnz     loc_14001457A
0x140014449  mov     r9, rdi
0x14001444c  mov     [rbp+lpSubKey], 0
0x140014454  lea     r8, aClsid; "CLSID\\"
0x14001445b  mov     ecx, 2
0x140014460  lea     rdx, [rbp+lpSubKey]
0x140014464  call    ?ConcatenateStrings@WmiHelper@@SA?AW4WmiStatusCode@@KPEAPEAGZZ; WmiHelper::ConcatenateStrings(ulong,ushort * *,...)
0x140014469  mov     edi, eax
0x14001446b  test    eax, eax
0x14001446d  js      loc_140014548
0x140014473  mov     rdx, [rbp+lpSubKey]; unsigned __int16 *
0x140014477  mov     r8, r14; struct IWbemContext *
0x14001447a  mov     rcx, rbx; this
0x14001447d  call    ?CalculateBitness@CServerObject_ComRegistration@@QEAAJPEBGPEAUIWbemContext@@@Z; CServerObject_ComRegistration::CalculateBitness(ushort const *,IWbemContext *)
0x140014482  mov     rdx, [rbp+lpSubKey]; unsigned __int16 *
0x140014486  mov     rcx, rbx; this
0x140014489  call    ?Load_ServerTypes@CServerObject_ComRegistration@@AEAAJPEBG@Z; CServerObject_ComRegistration::Load_ServerTypes(ushort const *)
0x14001448e  cmp     dword ptr [rbx+650h], 20h ; ' '
0x140014495  mov     edi, eax
0x140014497  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x14001449b  mov     eax, 100h
0x1400144a0  mov     r9d, 200h
0x1400144a6  mov     [rbp+hKey], 0
0x1400144ae  cmovnz  r9d, eax
0x1400144b2  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1400144b9  lea     rax, [rbp+hKey]
0x1400144bd  or      r9d, 20019h; samDesired
0x1400144c4  xor     r8d, r8d; ulOptions
0x1400144c7  mov     [rsp+40h+phkResult], rax; phkResult
0x1400144cc  call    cs:__imp_RegOpenKeyExW
0x1400144d2  mov     esi, 1
0x1400144d7  test    eax, eax
0x1400144d9  jnz     short loc_140014537
0x1400144db  mov     rdx, cs:?s_Strings_Reg_Null@CServerObject_ComRegistration@@1PEBGEB; lpValueName
0x1400144e2  lea     rcx, [rbp+cbData]
0x1400144e6  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x1400144eb  lea     rax, [rbx+448h]
0x1400144f2  mov     rcx, [rbp+hKey]; hKey
0x1400144f6  lea     r9, [rbp+Type]; lpType
0x1400144fa  xor     r8d, r8d; lpReserved
0x1400144fd  mov     [rbp+Type], esi
0x140014500  mov     [rbp+cbData], 208h
0x140014507  mov     [rsp+40h+phkResult], rax; lpData
0x14001450c  call    cs:__imp_RegQueryValueExW
0x140014512  mov     rdx, [rbp+hKey]; HKEY
0x140014516  mov     rcx, rbx; this
0x140014519  call    ?Load_AppId@CServerObject_ComRegistration@@AEAAJPEAUHKEY__@@@Z; CServerObject_ComRegistration::Load_AppId(HKEY__ *)
0x14001451e  mov     edi, eax
0x140014520  test    eax, eax
0x140014522  js      short loc_14001452D
0x140014524  cmp     [rbx+10h], esi
0x140014527  jnz     loc_1400145B8
0x14001452d  mov     rcx, [rbp+hKey]; hKey
0x140014531  call    cs:__imp_RegCloseKey
0x140014537  mov     rcx, [rbp+lpSubKey]; bstrString
0x14001453b  call    cs:__imp_SysFreeString
0x140014541  test    edi, edi
0x140014543  js      short loc_140014548
0x140014545  mov     [rbx+1Ch], esi
0x140014548  mov     eax, edi
0x14001454a  mov     rbx, [rsp+40h+arg_10]
0x14001454f  mov     rsi, [rsp+40h+arg_18]
0x140014554  add     rsp, 40h
0x140014558  pop     r14
0x14001455a  pop     rdi
0x14001455b  pop     rbp
0x14001455c  retn
0x14001455d  mov     rcx, rdi; psz
0x140014560  call    cs:__imp_SysAllocString
0x140014566  mov     [rbx+20h], rax
0x14001456a  test    rax, rax
0x14001456d  jnz     loc_140014433
0x140014573  mov     eax, 80041006h
0x140014578  jmp     short loc_14001454A
0x14001457a  mov     rcx, rsi; psz
0x14001457d  call    cs:__imp_SysAllocString
0x140014583  mov     [rbx+30h], rax
0x140014587  test    rax, rax
0x14001458a  jnz     loc_140014449
0x140014590  jmp     short loc_140014573
0x140014592  call    cs:__imp_SysFreeString
0x140014598  mov     qword ptr [rbx+20h], 0
0x1400145a0  jmp     loc_14001442A
0x1400145a5  call    cs:__imp_SysFreeString
0x1400145ab  mov     qword ptr [rbx+30h], 0
0x1400145b3  jmp     loc_140014440
0x1400145b8  cmp     [rbx+14h], esi
0x1400145bb  jz      loc_14001452D
0x1400145c1  mov     [rbx+18h], esi
0x1400145c4  mov     qword ptr [rbx+8], 2
0x1400145cc  jmp     loc_14001452D
```
