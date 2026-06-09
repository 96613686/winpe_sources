# StartList::GetSessionTransitValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x14000ddb0`
- end: `0x14000df80`
- name: `?GetSessionTransitValue@StartList@@AEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `464`
- prototype: `unsigned int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010960`

## callees

- `0x140007708`
- `0x14000cb50`
- `0x14000d118`
- `0x14000ddb0`
- `0x1400111c0`
- `0x140015ac2`
- `0x140015b00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000de29`
- `ADVAPI32!RegOpenKeyExW` at `0x14000de29`
- `ADVAPI32!RegCloseKey` at `0x14000df5b`
- `ADVAPI32!RegCloseKey` at `0x14000df5b`

## string_xrefs

- `0x14000ded9`: `SecureConfiguration`
- `0x14000de1b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\SessionTransit`
- `0x14000de65`: `Configuration`

## pseudocode

```c
unsigned int __fastcall StartList::GetSessionTransitValue(__int64 a1, __int64 a2)
{
  HKEY v3; // rsi
  unsigned int result; // eax
  __int64 v5; // r8
  unsigned int StringValue; // eax
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v13[3]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v14[1024]; // [rsp+50h] [rbp-B0h] BYREF

  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &Data);
  v3 = 0;
  memset(v13, 0, sizeof(v13));
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, StartList::m_sessionTransitKeyString, 0, 0x20019u, &hKey);
  if ( result )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_19;
    v11 = 47;
LABEL_18:
    result = WPP_SF_d(v10[2], v11, v5, result);
    goto LABEL_19;
  }
  v3 = hKey;
  v13[0] = hKey;
  memset_0(v14, 0, sizeof(v14));
  LODWORD(hKey) = 1024;
  StringValue = ATL::CRegKey::QueryStringValue(
                  (ATL::CRegKey *)v13,
                  StartList::_configuration,
                  v14,
                  (unsigned int *)&hKey);
  v8 = -1;
  if ( StringValue )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v7, StringValue);
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v14[v9] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v14, v9);
  }
  LODWORD(hKey) = 1024;
  result = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v13, L"SecureConfiguration", v14, (unsigned int *)&hKey);
  if ( result )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_19;
    v11 = 49;
    goto LABEL_18;
  }
  do
    ++v8;
  while ( v14[v8] );
  result = ATL::CSimpleStringT<unsigned short,0>::Append(a2, v14, (unsigned int)v8);
LABEL_19:
  if ( v3 )
    return RegCloseKey(v3);
  return result;
}

```

## disassembly

```asm
0x14000ddb0  push    rbp
0x14000ddb2  push    rbx
0x14000ddb3  push    rsi
0x14000ddb4  push    rdi
0x14000ddb5  push    r14
0x14000ddb7  push    r15
0x14000ddb9  lea     rbp, [rsp-768h]
0x14000ddc1  sub     rsp, 868h
0x14000ddc8  mov     rax, cs:__security_cookie
0x14000ddcf  xor     rax, rsp
0x14000ddd2  mov     [rbp+790h+var_40], rax
0x14000ddd9  mov     r14, rdx
0x14000dddc  xor     r8d, r8d
0x14000dddf  lea     rdx, Data
0x14000dde6  mov     rcx, r14
0x14000dde9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000ddee  xor     r15d, r15d
0x14000ddf1  mov     esi, r15d
0x14000ddf4  mov     [rsp+890h+var_858], r15
0x14000ddf9  mov     [rsp+890h+var_850], r15
0x14000ddfe  mov     [rsp+890h+var_848], r15
0x14000de03  mov     [rsp+890h+hKey], r15
0x14000de08  lea     rax, [rsp+890h+hKey]
0x14000de0d  mov     [rsp+890h+phkResult], rax; phkResult
0x14000de12  mov     r9d, 20019h; samDesired
0x14000de18  xor     r8d, r8d; ulOptions
0x14000de1b  lea     rdx, ?m_sessionTransitKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000de22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000de29  call    cs:__imp_RegOpenKeyExW
0x14000de2f  test    eax, eax
0x14000de31  jnz     loc_14000DF28
0x14000de37  mov     rsi, [rsp+890h+hKey]
0x14000de3c  mov     [rsp+890h+var_858], rsi
0x14000de41  xor     edx, edx; Val
0x14000de43  mov     r8d, 800h; Size
0x14000de49  lea     rcx, [rsp+890h+var_840]; void *
0x14000de4e  call    memset_0
0x14000de53  mov     dword ptr [rsp+890h+hKey], 400h
0x14000de5b  lea     r9, [rsp+890h+hKey]; unsigned int *
0x14000de60  lea     r8, [rsp+890h+var_840]; unsigned __int16 *
0x14000de65  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x14000de6c  lea     rcx, [rsp+890h+var_858]; this
0x14000de71  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000de76  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000de7a  lea     rdi, WPP_GLOBAL_Control
0x14000de81  test    eax, eax
0x14000de83  jz      short loc_14000DEA8
0x14000de85  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de8c  cmp     rcx, rdi
0x14000de8f  jz      short loc_14000DEC7
0x14000de91  test    byte ptr [rcx+1Ch], 8
0x14000de95  jz      short loc_14000DEC7
0x14000de97  lea     edx, [rbx+31h]
0x14000de9a  mov     r9d, eax
0x14000de9d  mov     rcx, [rcx+10h]
0x14000dea1  call    WPP_SF_d
0x14000dea6  jmp     short loc_14000DEC7
0x14000dea8  lea     rax, [rsp+890h+var_840]
0x14000dead  mov     r8, rbx
0x14000deb0  inc     r8
0x14000deb3  cmp     [rax+r8*2], r15w
0x14000deb8  jnz     short loc_14000DEB0
0x14000deba  lea     rdx, [rsp+890h+var_840]
0x14000debf  mov     rcx, r14
0x14000dec2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000dec7  mov     dword ptr [rsp+890h+hKey], 400h
0x14000decf  lea     r9, [rsp+890h+hKey]; unsigned int *
0x14000ded4  lea     r8, [rsp+890h+var_840]; unsigned __int16 *
0x14000ded9  lea     rdx, ?c_secureConfiguration@StartList@@0QBGB; "SecureConfiguration"
0x14000dee0  lea     rcx, [rsp+890h+var_858]; this
0x14000dee5  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000deea  test    eax, eax
0x14000deec  jz      short loc_14000DF07
0x14000deee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000def5  cmp     rcx, rdi
0x14000def8  jz      short loc_14000DF53
0x14000defa  test    byte ptr [rcx+1Ch], 8
0x14000defe  jz      short loc_14000DF53
0x14000df00  mov     edx, 31h ; '1'
0x14000df05  jmp     short loc_14000DF46
0x14000df07  lea     rax, [rsp+890h+var_840]
0x14000df0c  inc     rbx
0x14000df0f  cmp     [rax+rbx*2], r15w
0x14000df14  jnz     short loc_14000DF0C
0x14000df16  mov     r8d, ebx
0x14000df19  lea     rdx, [rsp+890h+var_840]
0x14000df1e  mov     rcx, r14
0x14000df21  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000df26  jmp     short loc_14000DF53
0x14000df28  lea     rdi, WPP_GLOBAL_Control
0x14000df2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df36  cmp     rcx, rdi
0x14000df39  jz      short loc_14000DF53
0x14000df3b  test    byte ptr [rcx+1Ch], 8
0x14000df3f  jz      short loc_14000DF53
0x14000df41  mov     edx, 2Fh ; '/'
0x14000df46  mov     r9d, eax
0x14000df49  mov     rcx, [rcx+10h]
0x14000df4d  call    WPP_SF_d
0x14000df52  nop
0x14000df53  test    rsi, rsi
0x14000df56  jz      short loc_14000DF61
0x14000df58  mov     rcx, rsi; hKey
0x14000df5b  call    cs:__imp_RegCloseKey
0x14000df61  mov     rcx, [rbp+790h+var_40]
0x14000df68  xor     rcx, rsp; StackCookie
0x14000df6b  call    __security_check_cookie
0x14000df70  add     rsp, 868h
0x14000df77  pop     r15
0x14000df79  pop     r14
0x14000df7b  pop     rdi
0x14000df7c  pop     rsi
0x14000df7d  pop     rbx
0x14000df7e  pop     rbp
0x14000df7f  retn
```
