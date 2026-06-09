# TraceTpmInformation(ulong,ushort *)

- ea: `0x1800341ec`
- end: `0x18003445b`
- name: `?TraceTpmInformation@@YAXKPEAG@Z`
- size: `623`
- prototype: `void __fastcall(unsigned int, LPCWSTR lpValueName)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b6e0`
- `0x180033e1c`
- `0x180033fc0`
- `0x180036ad0`

## callees

- `0x1800341ec`
- `0x180036ab4`
- `0x18004c72c`
- `0x180050a28`
- `0x180052a54`
- `0x1800537c8`
- `0x180054100`
- `0x18005d294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800343b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800343b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003424a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003424a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800342ee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003432f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800343cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800342ee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003432f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800343cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034383`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034383`

## string_xrefs

- `0x180034345`: `UpdateTimeLast`
- `0x180034366`: `UpdateTimeLast`

## pseudocode

```c
void __fastcall TraceTpmInformation(unsigned int a1, LPCWSTR lpValueName)
{
  LSTATUS v4; // eax
  bool v5; // sf
  char v6; // bl
  int v7; // eax
  int TpmRegDword; // eax
  int v9; // eax
  const WCHAR *v10; // rdx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  DWORD dwLowDateTime; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v15; // [rsp+54h] [rbp-2Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-20h] BYREF
  struct _FILETIME v18; // [rsp+68h] [rbp-18h] BYREF
  struct _FILETIME v19; // [rsp+70h] [rbp-10h] BYREF
  struct _FILETIME v20; // [rsp+B0h] [rbp+30h] BYREF
  unsigned int v21; // [rsp+B8h] [rbp+38h] BYREF

  hKey = 0;
  v4 = RegCreateKeyExW(
         HKEY_USERS,
         L"S-1-5-19\\Software\\Microsoft\\Cryptography\\TPM\\Telemetry",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( !v5 )
  {
    if ( UpdateTpmRegDword(hKey, lpValueName, a1)
      || (v20 = 0, ReadTpmRegQword(hKey, L"TraceTimeLast", &v20) == -2147024894)
      || IsDayOldFileTime(v20) )
    {
      v21 = 0;
      v6 = 1;
      v7 = ReadTpmRegDword(hKey, L"TPMStatus", &v21);
      if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 )
      {
        RegDeleteValueW(hKey, L"TPMStatus");
        v6 = 0;
      }
      v20.dwLowDateTime = 0;
      TpmRegDword = ReadTpmRegDword(hKey, L"EKCertExists", (unsigned int *)&v20);
      if ( ((TpmRegDword + 0x80000000) & 0x80000000) == 0 && TpmRegDword != -2147024894 )
      {
        RegDeleteValueW(hKey, L"EKCertExists");
        v6 = 0;
      }
      v18 = 0;
      v9 = ReadTpmRegQword(hKey, L"UpdateTimeLast", &v18);
      if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -2147024894 )
      {
        v10 = L"UpdateTimeLast";
LABEL_19:
        RegDeleteValueW(hKey, v10);
        goto LABEL_23;
      }
      if ( v6 )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( RegSetValueExW(hKey, L"TraceTimeLast", 0, 0xBu, (const BYTE *)&SystemTimeAsFileTime, 8u) < 0 )
        {
          v10 = L"TraceTimeLast";
          goto LABEL_19;
        }
        if ( (unsigned int)dword_1801091E0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801091E0, 0x400000000000LL) )
        {
          v19 = v18;
          dwLowDateTime = v20.dwLowDateTime;
          v15 = v21;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            v11,
            (unsigned int)byte_1800F6A3B,
            v12,
            v13,
            (__int64)&v15,
            (__int64)&dwLowDateTime,
            (__int64)&v19);
        }
      }
    }
  }
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800341ec  mov     r11, rsp
0x1800341ef  mov     [r11+8], rbx
0x1800341f3  push    rbp
0x1800341f4  push    rdi
0x1800341f5  push    r15
0x1800341f7  mov     rbp, rsp
0x1800341fa  sub     rsp, 80h
0x180034201  mov     qword ptr [r11-58h], 0
0x180034209  lea     rax, [rbp+hKey]
0x18003420d  mov     [r11-60h], rax
0x180034211  mov     rbx, rdx
0x180034214  mov     qword ptr [r11-68h], 0
0x18003421c  lea     rdx, SubKey; "S-1-5-19\\Software\\Microsoft\\Cryptogr"...
0x180034223  mov     edi, ecx
0x180034225  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18003422d  xor     r9d, r9d; lpClass
0x180034230  mov     [rsp+80h+dwOptions], 0; dwOptions
0x180034238  xor     r8d, r8d; Reserved
0x18003423b  mov     [rbp+hKey], 0
0x180034243  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003424a  call    cs:__imp_RegCreateKeyExW
0x180034251  nop     dword ptr [rax+rax+00h]
0x180034256  test    eax, eax
0x180034258  jle     short loc_180034264
0x18003425a  movzx   eax, ax
0x18003425d  or      eax, 80070000h
0x180034262  test    eax, eax
0x180034264  js      loc_18003443D
0x18003426a  mov     rcx, [rbp+hKey]; hKey
0x18003426e  mov     r8d, edi; unsigned int
0x180034271  mov     rdx, rbx; lpValueName
0x180034274  call    ?UpdateTpmRegDword@@YA_NPEAUHKEY__@@PEBGK@Z; UpdateTpmRegDword(HKEY__ *,ushort const *,ulong)
0x180034279  mov     edi, 80070002h
0x18003427e  test    al, al
0x180034280  jnz     short loc_1800342B3
0x180034282  mov     rcx, [rbp+hKey]; HKEY
0x180034286  lea     r8, [rbp+arg_10]; struct _FILETIME *
0x18003428a  lea     rdx, aTracetimelast; "TraceTimeLast"
0x180034291  mov     qword ptr [rbp+arg_10.dwLowDateTime], 0
0x180034299  call    ?ReadTpmRegQword@@YAJPEAUHKEY__@@PEBGPEAU_FILETIME@@@Z; ReadTpmRegQword(HKEY__ *,ushort const *,_FILETIME *)
0x18003429e  cmp     eax, edi
0x1800342a0  jz      short loc_1800342B3
0x1800342a2  mov     rcx, qword ptr [rbp+arg_10.dwLowDateTime]; struct _FILETIME
0x1800342a6  call    ?IsDayOldFileTime@@YA_NU_FILETIME@@@Z; IsDayOldFileTime(_FILETIME)
0x1800342ab  test    al, al
0x1800342ad  jz      loc_18003443D
0x1800342b3  mov     rcx, [rbp+hKey]; HKEY
0x1800342b7  lea     r8, [rbp+arg_18]; unsigned int *
0x1800342bb  lea     rdx, ValueName; "TPMStatus"
0x1800342c2  mov     [rbp+arg_18], 0
0x1800342c9  mov     bl, 1
0x1800342cb  call    ?ReadTpmRegDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; ReadTpmRegDword(HKEY__ *,ushort const *,ulong *)
0x1800342d0  mov     r15d, 80000000h
0x1800342d6  lea     ecx, [rax+r15]
0x1800342da  test    r15d, ecx
0x1800342dd  jnz     short loc_1800342FC
0x1800342df  cmp     eax, edi
0x1800342e1  jz      short loc_1800342FC
0x1800342e3  mov     rcx, [rbp+hKey]; hKey
0x1800342e7  lea     rdx, ValueName; "TPMStatus"
0x1800342ee  call    cs:__imp_RegDeleteValueW
0x1800342f5  nop     dword ptr [rax+rax+00h]
0x1800342fa  xor     bl, bl
0x1800342fc  mov     rcx, [rbp+hKey]; HKEY
0x180034300  lea     r8, [rbp+arg_10]; unsigned int *
0x180034304  lea     rdx, aEkcertexists; "EKCertExists"
0x18003430b  mov     [rbp+arg_10.dwLowDateTime], 0
0x180034312  call    ?ReadTpmRegDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; ReadTpmRegDword(HKEY__ *,ushort const *,ulong *)
0x180034317  lea     ecx, [rax+r15]
0x18003431b  test    r15d, ecx
0x18003431e  jnz     short loc_18003433D
0x180034320  cmp     eax, edi
0x180034322  jz      short loc_18003433D
0x180034324  mov     rcx, [rbp+hKey]; hKey
0x180034328  lea     rdx, aEkcertexists; "EKCertExists"
0x18003432f  call    cs:__imp_RegDeleteValueW
0x180034336  nop     dword ptr [rax+rax+00h]
0x18003433b  xor     bl, bl
0x18003433d  mov     rcx, [rbp+hKey]; HKEY
0x180034341  lea     r8, [rbp+var_18]; struct _FILETIME *
0x180034345  lea     rdx, aUpdatetimelast; "UpdateTimeLast"
0x18003434c  mov     qword ptr [rbp+var_18.dwLowDateTime], 0
0x180034354  call    ?ReadTpmRegQword@@YAJPEAUHKEY__@@PEBGPEAU_FILETIME@@@Z; ReadTpmRegQword(HKEY__ *,ushort const *,_FILETIME *)
0x180034359  lea     ecx, [rax+r15]
0x18003435d  test    r15d, ecx
0x180034360  jnz     short loc_18003436F
0x180034362  cmp     eax, edi
0x180034364  jz      short loc_18003436F
0x180034366  lea     rdx, aUpdatetimelast; "UpdateTimeLast"
0x18003436d  jmp     short loc_1800343CB
0x18003436f  test    bl, bl
0x180034371  jz      loc_18003443D
0x180034377  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003437b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180034383  call    cs:__imp_GetSystemTimeAsFileTime
0x18003438a  nop     dword ptr [rax+rax+00h]
0x18003438f  mov     rcx, [rbp+hKey]; hKey
0x180034393  lea     rax, [rbp+SystemTimeAsFileTime]
0x180034397  mov     [rsp+80h+samDesired], 8; cbData
0x18003439f  lea     rdx, aTracetimelast; "TraceTimeLast"
0x1800343a6  mov     r9d, 0Bh; dwType
0x1800343ac  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x1800343b1  xor     r8d, r8d; Reserved
0x1800343b4  call    cs:__imp_RegSetValueExW
0x1800343bb  nop     dword ptr [rax+rax+00h]
0x1800343c0  test    eax, eax
0x1800343c2  jns     short loc_1800343DD
0x1800343c4  lea     rdx, aTracetimelast; "TraceTimeLast"
0x1800343cb  mov     rcx, [rbp+hKey]; hKey
0x1800343cf  call    cs:__imp_RegDeleteValueW
0x1800343d6  nop     dword ptr [rax+rax+00h]
0x1800343db  jmp     short loc_18003443D
0x1800343dd  mov     eax, cs:dword_1801091E0
0x1800343e3  cmp     eax, 5
0x1800343e6  jbe     short loc_18003443D
0x1800343e8  mov     rdx, 400000000000h
0x1800343f2  lea     rcx, dword_1801091E0
0x1800343f9  call    _tlgKeywordOn
0x1800343fe  test    al, al
0x180034400  jz      short loc_18003443D
0x180034402  mov     rax, qword ptr [rbp+var_18.dwLowDateTime]
0x180034406  lea     rdx, byte_1800F6A3B
0x18003440d  mov     [rbp+var_10], rax
0x180034411  mov     eax, [rbp+arg_10.dwLowDateTime]
0x180034414  mov     [rbp+var_30], eax
0x180034417  mov     eax, [rbp+arg_18]
0x18003441a  mov     [rbp+var_2C], eax
0x18003441d  lea     rax, [rbp+var_10]
0x180034421  mov     [rsp+80h+var_50], rax
0x180034426  lea     rax, [rbp+var_30]
0x18003442a  mov     qword ptr [rsp+80h+samDesired], rax
0x18003442f  lea     rax, [rbp+var_2C]
0x180034433  mov     qword ptr [rsp+80h+dwOptions], rax
0x180034438  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003443d  lea     rcx, [rbp+hKey]
0x180034441  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034446  mov     rbx, [rsp+80h+arg_0]
0x18003444e  add     rsp, 80h
0x180034455  pop     r15
0x180034457  pop     rdi
0x180034458  pop     rbp
0x180034459  retn
```
