# CAppScriptManager::LoadSupportedAppList(void)

- ea: `0x180053320`
- end: `0x18005351e`
- name: `?LoadSupportedAppList@CAppScriptManager@@AEAAHXZ`
- size: `510`
- prototype: `__int64 __fastcall(CAppScriptManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053cf0`

## callees

- `0x1800052a0`
- `0x18000b2dc`
- `0x18005304c`
- `0x180053154`
- `0x180053240`
- `0x180053320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053364`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053364`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180053433`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180053433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800534ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053507`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800534ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053507`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800533ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800533ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800534e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800534e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800533e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800533e6`

## string_xrefs

- `0x18005335d`: `Software\Microsoft\Windows NT\CurrentVersion\Terminal Server\Compatibility\Scripts`

## pseudocode

```c
_BOOL8 __fastcall CAppScriptManager::LoadSupportedAppList(CAppScriptManager *this)
{
  LSTATUS v2; // r14d
  __int64 v3; // rdx
  unsigned __int64 v4; // rdx
  WCHAR *v5; // rsi
  DWORD i; // edi
  unsigned __int64 v7; // rdx
  CAppScript *v8; // rax
  CAppScript *v9; // rbx
  unsigned int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-8h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+B8h] [rbp+48h] BYREF
  DWORD cSubKeys; // [rsp+C0h] [rbp+50h] BYREF
  CAppScript *cchName; // [rsp+C8h] [rbp+58h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Terminal Server\\Compatibility\\Scripts",
          0,
          0x20019u,
          &hKey) )
  {
    v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v2 )
    {
LABEL_17:
      RegCloseKey(hKey);
      return v2 == 0;
    }
    v3 = cbMaxSubKeyLen + 1;
    if ( (unsigned int)v3 < cbMaxSubKeyLen )
    {
      cbMaxSubKeyLen = -1;
    }
    else
    {
      ++cbMaxSubKeyLen;
      v4 = 2 * v3;
      if ( v4 <= 0xFFFFFFFF )
      {
        v5 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v4);
        if ( v5 )
        {
          for ( i = 0; i < cSubKeys; ++i )
          {
            LODWORD(cchName) = cbMaxSubKeyLen;
            ftLastWriteTime = 0;
            v2 = RegEnumKeyExW(hKey, i, v5, (LPDWORD)&cchName, 0, 0, 0, &ftLastWriteTime);
            if ( v2 )
              break;
            v8 = (CAppScript *)DirectUI::HAllocAndZero((DirectUI *)0x20, v7);
            cchName = v8;
            v9 = v8;
            if ( !v8 )
              break;
            *(_QWORD *)v8 = 0;
            *((_QWORD *)v8 + 1) = 0;
            *((_QWORD *)v8 + 2) = 0;
            *((_QWORD *)v8 + 3) = 0;
            cchName = v8;
            if ( (unsigned int)CAppScript::Load((unsigned __int16 **)v8, hKey, v5) )
            {
              v12 = *(_QWORD *)this;
              v13 = std::_List_buy<CAppScript *>::_Buynode<CAppScript * const &>(
                      v11,
                      *(_QWORD *)this,
                      *(_QWORD *)(*(_QWORD *)this + 8LL),
                      &cchName);
              v14 = *((_QWORD *)this + 1);
              if ( v14 == 0xAAAAAAAAAAAAAA9LL )
                std::_Xlength_error("list<T> too long");
              *((_QWORD *)this + 1) = v14 + 1;
              *(_QWORD *)(v12 + 8) = v13;
              **(_QWORD **)(v13 + 8) = v13;
            }
            else
            {
              CAppScript::`scalar deleting destructor'(v9, v10);
            }
          }
          LocalFree(v5);
          goto LABEL_17;
        }
      }
    }
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180053320  push    rbp
0x180053322  push    rbx
0x180053323  push    rsi
0x180053324  push    rdi
0x180053325  push    r12
0x180053327  push    r14
0x180053329  push    r15
0x18005332b  mov     rbp, rsp
0x18005332e  sub     rsp, 70h
0x180053332  xor     r12d, r12d
0x180053335  lea     rax, [rbp+hKey]
0x180053339  mov     r15, rcx
0x18005333c  mov     [rbp+hKey], r12
0x180053340  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053347  mov     [rbp+cSubKeys], r12d
0x18005334b  mov     r9d, 20019h; samDesired
0x180053351  mov     [rbp+cbMaxSubKeyLen], r12d
0x180053355  xor     r8d, r8d; ulOptions
0x180053358  mov     [rsp+70h+phkResult], rax; phkResult
0x18005335d  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180053364  call    cs:__imp_RegOpenKeyExW
0x18005336a  test    eax, eax
0x18005336c  jnz     loc_18005350D
0x180053372  mov     rcx, [rbp+hKey]; hKey
0x180053376  lea     rax, [rbp+cbMaxSubKeyLen]
0x18005337a  mov     [rsp+70h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18005337f  xor     r9d, r9d; lpReserved
0x180053382  mov     [rsp+70h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180053387  xor     r8d, r8d; lpcchClass
0x18005338a  mov     [rsp+70h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18005338f  xor     edx, edx; lpClass
0x180053391  mov     [rsp+70h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180053396  mov     [rsp+70h+lpcValues], r12; lpcValues
0x18005339b  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800533a0  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800533a5  lea     rax, [rbp+cSubKeys]
0x1800533a9  mov     [rsp+70h+phkResult], rax; lpcSubKeys
0x1800533ae  call    cs:__imp_RegQueryInfoKeyW
0x1800533b4  mov     r14d, eax
0x1800533b7  test    eax, eax
0x1800533b9  jnz     loc_1800534EB
0x1800533bf  mov     ecx, [rbp+cbMaxSubKeyLen]
0x1800533c2  lea     edx, [rcx+1]
0x1800533c5  cmp     edx, ecx
0x1800533c7  mov     ecx, 0FFFFFFFFh
0x1800533cc  jb      loc_180053500
0x1800533d2  mov     [rbp+cbMaxSubKeyLen], edx
0x1800533d5  add     rdx, rdx
0x1800533d8  cmp     rdx, rcx
0x1800533db  ja      loc_180053503
0x1800533e1  mov     edx, edx; uBytes
0x1800533e3  lea     ecx, [rax+40h]; uFlags
0x1800533e6  call    cs:__imp_LocalAlloc
0x1800533ec  mov     rsi, rax
0x1800533ef  test    rax, rax
0x1800533f2  jz      loc_180053503
0x1800533f8  mov     edi, r12d
0x1800533fb  cmp     edi, [rbp+cSubKeys]
0x1800533fe  jnb     loc_1800534E2
0x180053404  mov     ecx, [rbp+cbMaxSubKeyLen]
0x180053407  lea     rax, [rbp+ftLastWriteTime]
0x18005340b  mov     [rsp+70h+lpcValues], rax; lpftLastWriteTime
0x180053410  lea     r9, [rbp+cchName]; lpcchName
0x180053414  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcchClass
0x180053419  mov     r8, rsi; lpName
0x18005341c  mov     dword ptr [rbp+cchName], ecx
0x18005341f  mov     edx, edi; dwIndex
0x180053421  mov     rcx, [rbp+hKey]; hKey
0x180053425  mov     [rsp+70h+lpcbMaxSubKeyLen], r12; lpClass
0x18005342a  mov     [rsp+70h+phkResult], r12; lpReserved
0x18005342f  mov     qword ptr [rbp+ftLastWriteTime.dwLowDateTime], r12
0x180053433  call    cs:__imp_RegEnumKeyExW
0x180053439  mov     r14d, eax
0x18005343c  test    eax, eax
0x18005343e  jnz     loc_1800534E2
0x180053444  lea     ecx, [rax+20h]; this
0x180053447  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18005344c  mov     [rbp+cchName], rax
0x180053450  mov     rbx, rax
0x180053453  test    rax, rax
0x180053456  jz      loc_1800534E2
0x18005345c  mov     [rax], r12
0x18005345f  mov     [rax+8], r12
0x180053463  mov     [rax+10h], r12
0x180053467  mov     [rax+18h], r12
0x18005346b  mov     [rbp+cchName], rax
0x18005346f  test    rax, rax
0x180053472  jz      short loc_1800534E2
0x180053474  mov     rdx, [rbp+hKey]; hKey
0x180053478  mov     r8, rsi; lpSubKey
0x18005347b  mov     rcx, rax; this
0x18005347e  call    ?Load@CAppScript@@QEAAHPEAUHKEY__@@PEBG@Z; CAppScript::Load(HKEY__ *,ushort const *)
0x180053483  test    eax, eax
0x180053485  jz      short loc_1800534C6
0x180053487  mov     rbx, [r15]
0x18005348a  lea     r9, [rbp+cchName]
0x18005348e  mov     rdx, rbx
0x180053491  mov     r8, [rbx+8]
0x180053495  call    ??$_Buynode@AEBQEAVCAppScript@@@?$_List_buy@PEAVCAppScript@@V?$allocator@PEAVCAppScript@@@std@@@std@@QEAAPEAU?$_List_node@PEAVCAppScript@@PEAX@1@PEAU21@0AEBQEAVCAppScript@@@Z; std::_List_buy<CAppScript *>::_Buynode<CAppScript * const &>(std::_List_node<CAppScript *,void *> *,std::_List_node<CAppScript *,void *> *,CAppScript * const &)
0x18005349a  mov     rdx, [r15+8]
0x18005349e  mov     rcx, 0AAAAAAAAAAAAAA9h
0x1800534a8  sub     rcx, rdx
0x1800534ab  cmp     rcx, 1
0x1800534af  jb      short loc_1800534D5
0x1800534b1  lea     rcx, [rdx+1]
0x1800534b5  mov     [r15+8], rcx
0x1800534b9  mov     [rbx+8], rax
0x1800534bd  mov     rcx, [rax+8]
0x1800534c1  mov     [rcx], rax
0x1800534c4  jmp     short loc_1800534CE
0x1800534c6  mov     rcx, rbx; this
0x1800534c9  call    ??_GCAppScript@@QEAAPEAXI@Z; CAppScript::`scalar deleting destructor'(uint)
0x1800534ce  inc     edi
0x1800534d0  jmp     loc_1800533FB
0x1800534d5  lea     rcx, aListTTooLong; "list<T> too long"
0x1800534dc  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800534e2  mov     rcx, rsi; hMem
0x1800534e5  call    cs:__imp_LocalFree
0x1800534eb  mov     rcx, [rbp+hKey]; hKey
0x1800534ef  call    cs:__imp_RegCloseKey
0x1800534f5  test    r14d, r14d
0x1800534f8  mov     eax, r12d
0x1800534fb  setz    al
0x1800534fe  jmp     short loc_18005350F
0x180053500  mov     [rbp+cbMaxSubKeyLen], ecx
0x180053503  mov     rcx, [rbp+hKey]; hKey
0x180053507  call    cs:__imp_RegCloseKey
0x18005350d  xor     eax, eax
0x18005350f  add     rsp, 70h
0x180053513  pop     r15
0x180053515  pop     r14
0x180053517  pop     r12
0x180053519  pop     rdi
0x18005351a  pop     rsi
0x18005351b  pop     rbx
0x18005351c  pop     rbp
0x18005351d  retn
```
