# Windows::Networking::UX::Internal::Profile::SetAutoConnect(bool)

- ea: `0x180075900`
- end: `0x180075bc1`
- name: `?SetAutoConnect@Profile@Internal@UX@Networking@Windows@@QEAAJ_N@Z`
- size: `705`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::Profile *__hidden this, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005d160`
- `0x1800748ac`

## callees

- `0x18000de4c`
- `0x18001d3a4`
- `0x18001d4d4`
- `0x180075900`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075b5d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075b6c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075b5d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075b6c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180075b0c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180075b0c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x18007599d`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x18007599d`
- `wlanapi!WpFreeProfile` at `0x180075b7b`
- `wlanapi!WpFreeProfile` at `0x180075b7b`
- `wlanapi!WpGenerateProfileXml` at `0x180075ac1`
- `wlanapi!WpGenerateProfileXml` at `0x180075ac1`
- `wlanapi!WpParseProfileXml` at `0x180075a23`
- `wlanapi!WpParseProfileXml` at `0x180075a23`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::Profile::SetAutoConnect(
        Windows::Networking::UX::Internal::Profile *this,
        char a2)
{
  void *v4; // rcx
  signed int Profile; // eax
  signed int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  char v11; // al
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // eax
  int ProfileXml; // eax
  signed int v16; // eax
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR pstrProfileXml; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR strProfileXml[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwFlags; // [rsp+90h] [rbp+30h] BYREF
  DWORD pdwGrantedAccess; // [rsp+A0h] [rbp+40h] BYREF
  DWORD pdwReasonCode; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_660af29b5b58392da31645ec246aada0_Traceguids);
  v4 = *(void **)this;
  pstrProfileXml = 0;
  strProfileXml[0] = 0;
  v18 = 0;
  dwFlags = 0;
  pdwGrantedAccess = 0;
  pdwReasonCode = 0;
  Profile = WlanGetProfile(
              v4,
              (const GUID *)((char *)this + 8),
              (LPCWSTR)this + 12,
              0,
              &pstrProfileXml,
              &dwFlags,
              &pdwGrantedAccess);
  v6 = Profile;
  if ( Profile > 0 )
    v6 = (unsigned __int16)Profile | 0x80070000;
  if ( v6 >= 0 )
  {
    if ( (dwFlags & 1) == 0 && ((pdwGrantedAccess & 0x70023) == 458787 || (dwFlags & 2) != 0) )
    {
      v9 = WpParseProfileXml(pstrProfileXml, &v18, 0, 0);
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 >= 0 )
      {
        if ( v18 && *(_DWORD *)(v18 + 536) == 5304833 )
        {
          v10 = *(_QWORD *)(v18 + 552);
          v11 = *(_DWORD *)(v10 + 16) == 1 && ((*(_BYTE *)(v10 + 4) & 1) == 0 || (*(_BYTE *)(v10 + 24) & 1) != 0);
          if ( v11 != a2 )
          {
            v12 = *(_DWORD *)(v10 + 24);
            v13 = v12 | 1;
            v14 = v12 & 0xFFFFFFFA;
            if ( !a2 )
              v13 = v14;
            *(_DWORD *)(v10 + 24) = v13;
            ProfileXml = WpGenerateProfileXml(v18, strProfileXml);
            v6 = ProfileXml;
            if ( ProfileXml > 0 )
              v6 = (unsigned __int16)ProfileXml | 0x80070000;
            if ( v6 >= 0 )
            {
              v16 = WlanSetProfile(
                      *(HANDLE *)this,
                      (const GUID *)((char *)this + 8),
                      dwFlags,
                      strProfileXml[0],
                      0,
                      1,
                      0,
                      &pdwReasonCode);
              v6 = v16;
              if ( v16 > 0 )
                v6 = (unsigned __int16)v16 | 0x80070000;
              if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  20,
                  WPP_660af29b5b58392da31645ec246aada0_Traceguids,
                  pdwReasonCode,
                  v6);
            }
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v8 = 19;
          goto LABEL_10;
        }
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 18;
LABEL_10:
      WPP_SF_d(v7[2], v8, WPP_660af29b5b58392da31645ec246aada0_Traceguids, (unsigned int)v6);
    }
  }
  if ( pstrProfileXml )
    WlanFreeMemory(pstrProfileXml);
  if ( strProfileXml[0] )
    WlanFreeMemory((PVOID)strProfileXml[0]);
  if ( v18 )
    WpFreeProfile(v18);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_660af29b5b58392da31645ec246aada0_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180075900  mov     [rsp-28h+arg_8], rbx
0x180075905  push    rbp
0x180075906  push    rsi
0x180075907  push    rdi
0x180075908  push    r13
0x18007590a  push    r14
0x18007590c  mov     rbp, rsp
0x18007590f  sub     rsp, 60h
0x180075913  mov     sil, dl
0x180075916  mov     rdi, rcx
0x180075919  mov     rcx, cs:WPP_GLOBAL_Control
0x180075920  lea     r13, WPP_GLOBAL_Control
0x180075927  cmp     rcx, r13
0x18007592a  jz      short loc_180075947
0x18007592c  test    byte ptr [rcx+1Ch], 40h
0x180075930  jz      short loc_180075947
0x180075932  mov     rcx, [rcx+10h]
0x180075936  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x18007593d  mov     edx, 11h
0x180075942  call    WPP_SF_
0x180075947  mov     rcx, [rdi]; hClientHandle
0x18007594a  lea     rax, [rbp+arg_10]
0x18007594e  mov     [rsp+60h+pdwGrantedAccess], rax; pdwGrantedAccess
0x180075953  lea     r8, [rdi+18h]; strProfileName
0x180075957  lea     rax, [rbp+dwFlags]
0x18007595b  mov     [rbp+var_18], 0
0x180075963  mov     [rsp+60h+pdwFlags], rax; pdwFlags
0x180075968  lea     rdx, [rdi+8]; pInterfaceGuid
0x18007596c  lea     rax, [rbp+var_18]
0x180075970  mov     [rbp+strProfileXml], 0
0x180075978  xor     r9d, r9d; pReserved
0x18007597b  mov     [rsp+60h+pstrProfileXml], rax; pstrProfileXml
0x180075980  mov     [rbp+var_20], 0
0x180075988  mov     [rbp+dwFlags], 0
0x18007598f  mov     [rbp+arg_10], 0
0x180075996  mov     [rbp+arg_18], 0
0x18007599d  call    cs:__imp_WlanGetProfile
0x1800759a3  mov     ebx, eax
0x1800759a5  test    eax, eax
0x1800759a7  jle     short loc_1800759B2
0x1800759a9  movzx   ebx, ax
0x1800759ac  or      ebx, 80070000h
0x1800759b2  test    ebx, ebx
0x1800759b4  jns     short loc_1800759ED
0x1800759b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800759bd  cmp     rcx, r13
0x1800759c0  jz      loc_180075B54
0x1800759c6  test    byte ptr [rcx+1Ch], 2
0x1800759ca  jz      loc_180075B54
0x1800759d0  mov     edx, 12h
0x1800759d5  mov     rcx, [rcx+10h]
0x1800759d9  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x1800759e0  mov     r9d, ebx
0x1800759e3  call    WPP_SF_d
0x1800759e8  jmp     loc_180075B54
0x1800759ed  test    byte ptr [rbp+dwFlags], 1
0x1800759f1  jnz     loc_180075B54
0x1800759f7  mov     eax, [rbp+arg_10]
0x1800759fa  mov     ecx, 70023h
0x1800759ff  and     eax, ecx
0x180075a01  cmp     eax, ecx
0x180075a03  setnz   cl
0x180075a06  test    byte ptr [rbp+dwFlags], 2
0x180075a0a  setz    al
0x180075a0d  test    al, cl
0x180075a0f  jnz     loc_180075B54
0x180075a15  mov     rcx, [rbp+var_18]
0x180075a19  lea     rdx, [rbp+var_20]
0x180075a1d  xor     r9d, r9d
0x180075a20  xor     r8d, r8d
0x180075a23  call    cs:__imp_WpParseProfileXml
0x180075a29  mov     ebx, eax
0x180075a2b  test    eax, eax
0x180075a2d  jle     short loc_180075A38
0x180075a2f  movzx   ebx, ax
0x180075a32  or      ebx, 80070000h
0x180075a38  test    ebx, ebx
0x180075a3a  jns     short loc_180075A60
0x180075a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180075a43  cmp     rcx, r13
0x180075a46  jz      loc_180075B54
0x180075a4c  test    byte ptr [rcx+1Ch], 2
0x180075a50  jz      loc_180075B54
0x180075a56  mov     edx, 13h
0x180075a5b  jmp     loc_1800759D5
0x180075a60  mov     rcx, [rbp+var_20]
0x180075a64  test    rcx, rcx
0x180075a67  jz      loc_180075B54
0x180075a6d  cmp     dword ptr [rcx+218h], 50F201h
0x180075a77  jnz     loc_180075B54
0x180075a7d  mov     rdx, [rcx+228h]
0x180075a84  cmp     dword ptr [rdx+10h], 1
0x180075a88  jnz     short loc_180075A9A
0x180075a8a  test    byte ptr [rdx+4], 1
0x180075a8e  jz      short loc_180075A96
0x180075a90  test    byte ptr [rdx+18h], 1
0x180075a94  jz      short loc_180075A9A
0x180075a96  mov     al, 1
0x180075a98  jmp     short loc_180075A9C
0x180075a9a  xor     al, al
0x180075a9c  cmp     al, sil
0x180075a9f  jz      loc_180075B54
0x180075aa5  mov     ecx, [rdx+18h]
0x180075aa8  mov     eax, ecx
0x180075aaa  or      ecx, 1
0x180075aad  and     eax, 0FFFFFFFAh
0x180075ab0  test    sil, sil
0x180075ab3  cmovz   ecx, eax
0x180075ab6  mov     [rdx+18h], ecx
0x180075ab9  lea     rdx, [rbp+strProfileXml]
0x180075abd  mov     rcx, [rbp+var_20]
0x180075ac1  call    cs:__imp_WpGenerateProfileXml
0x180075ac7  mov     ebx, eax
0x180075ac9  test    eax, eax
0x180075acb  jle     short loc_180075AD6
0x180075acd  movzx   ebx, ax
0x180075ad0  or      ebx, 80070000h
0x180075ad6  test    ebx, ebx
0x180075ad8  js      short loc_180075B54
0x180075ada  mov     r9, [rbp+strProfileXml]; strProfileXml
0x180075ade  lea     rax, [rbp+arg_18]
0x180075ae2  mov     r8d, [rbp+dwFlags]; dwFlags
0x180075ae6  lea     rdx, [rdi+8]; pInterfaceGuid
0x180075aea  mov     rcx, [rdi]; hClientHandle
0x180075aed  mov     [rsp+60h+pdwReasonCode], rax; pdwReasonCode
0x180075af2  mov     [rsp+60h+pdwGrantedAccess], 0; pReserved
0x180075afb  mov     dword ptr [rsp+60h+pdwFlags], 1; bOverwrite
0x180075b03  mov     [rsp+60h+pstrProfileXml], 0; strAllUserProfileSecurity
0x180075b0c  call    cs:__imp_WlanSetProfile
0x180075b12  mov     ebx, eax
0x180075b14  test    eax, eax
0x180075b16  jle     short loc_180075B21
0x180075b18  movzx   ebx, ax
0x180075b1b  or      ebx, 80070000h
0x180075b21  test    ebx, ebx
0x180075b23  jns     short loc_180075B54
0x180075b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180075b2c  cmp     rcx, r13
0x180075b2f  jz      short loc_180075B54
0x180075b31  test    byte ptr [rcx+1Ch], 2
0x180075b35  jz      short loc_180075B54
0x180075b37  mov     r9d, [rbp+arg_18]
0x180075b3b  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x180075b42  mov     rcx, [rcx+10h]
0x180075b46  mov     edx, 14h
0x180075b4b  mov     dword ptr [rsp+60h+pstrProfileXml], ebx
0x180075b4f  call    WPP_SF_Dd
0x180075b54  mov     rcx, [rbp+var_18]; pMemory
0x180075b58  test    rcx, rcx
0x180075b5b  jz      short loc_180075B63
0x180075b5d  call    cs:__imp_WlanFreeMemory
0x180075b63  mov     rcx, [rbp+strProfileXml]; pMemory
0x180075b67  test    rcx, rcx
0x180075b6a  jz      short loc_180075B72
0x180075b6c  call    cs:__imp_WlanFreeMemory
0x180075b72  mov     rcx, [rbp+var_20]
0x180075b76  test    rcx, rcx
0x180075b79  jz      short loc_180075B81
0x180075b7b  call    cs:__imp_WpFreeProfile
0x180075b81  mov     rcx, cs:WPP_GLOBAL_Control
0x180075b88  cmp     rcx, r13
0x180075b8b  jz      short loc_180075BAB
0x180075b8d  test    byte ptr [rcx+1Ch], 40h
0x180075b91  jz      short loc_180075BAB
0x180075b93  mov     rcx, [rcx+10h]
0x180075b97  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x180075b9e  mov     edx, 15h
0x180075ba3  mov     r9d, ebx
0x180075ba6  call    WPP_SF_d
0x180075bab  mov     eax, ebx
0x180075bad  mov     rbx, [rsp+60h+arg_8]
0x180075bb5  add     rsp, 60h
0x180075bb9  pop     r14
0x180075bbb  pop     r13
0x180075bbd  pop     rdi
0x180075bbe  pop     rsi
0x180075bbf  pop     rbp
0x180075bc0  retn
```
