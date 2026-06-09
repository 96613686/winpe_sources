# ZtHelperInitConfig(_ZTDNS_SETTINGS_TYPE,HKEY__ *)

- ea: `0x1800039e4`
- end: `0x180003cb0`
- name: `?ZtHelperInitConfig@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAUHKEY__@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000376c`

## callees

- `0x1800014b0`
- `0x180003674`
- `0x1800039e4`
- `0x18000f8f0`
- `0x18001011c`
- `0x1800101e8`
- `0x180015008`
- `0x1800152b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003a63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003a63`

## string_xrefs

- `0x180003b63`: `ZtdnsServiceNameRefreshTimeout`

## pseudocode

```c
__int64 __fastcall ZtHelperInitConfig(unsigned int a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int Bool; // ebx
  unsigned int DwordValue; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  _OWORD v9[3]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+60h] [rbp-9h]
  __int128 v11; // [rsp+70h] [rbp+7h]
  __int128 v12; // [rsp+80h] [rbp+17h] BYREF
  __int128 v13; // [rsp+90h] [rbp+27h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+37h] BYREF

  v2 = (int)a1;
  v11 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_dq(1026, 19, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, a1, a2);
  if ( !a2 )
  {
    Bool = 87;
    goto LABEL_27;
  }
  if ( (unsigned int)v2 <= 1 )
  {
    AcquireSRWLockExclusive(&g_rwZtSettingsLock);
    Bool = ReadEnableZtdnsConfig(a2, &v12);
    if ( Bool )
      goto LABEL_24;
    Bool = ZtRegReadBool(a2, L"ZtdnsAuditMode", (char *)&v12 + 4);
    if ( Bool )
      goto LABEL_24;
    Bool = ZtRegReadBool(a2, L"ZtdnsBlockLocalIps", (char *)&v12 + 8);
    if ( Bool )
      goto LABEL_24;
    Bool = ZtRegReadBool(a2, L"ZtdnsAllowHostsFile", (char *)&v12 + 12);
    if ( Bool )
      goto LABEL_24;
    Bool = ZtRegReadBool(a2, L"ZtdnsAllowIcsDhcpServer", &v13);
    if ( Bool )
      goto LABEL_24;
    Bool = ZtRegReadBool(a2, L"ZtdnsEnableForwarder", (char *)&v13 + 4);
    if ( Bool )
      goto LABEL_24;
    DwordValue = privateRegReadDwordValue(a2, L"ZtdnsUnicastLifetime", (char *)&v13 + 8);
    if ( DwordValue != 2 )
      Bool = DwordValue;
    if ( Bool )
      goto LABEL_24;
    v6 = privateRegReadDwordValue(a2, L"ZtdnsMaxRecordAge", (char *)&v13 + 12);
    Bool = v6;
    if ( v6 == 2 )
    {
      HIDWORD(v13) = 86400;
    }
    else if ( v6 )
    {
      goto LABEL_24;
    }
    v7 = privateRegReadDwordValue(a2, L"ZtdnsServiceNameRefreshTimeout", &v14);
    Bool = v7;
    if ( v7 == 2 )
    {
      LODWORD(v14) = 1800;
LABEL_21:
      LODWORD(v11) = 1;
      *((_QWORD *)&v11 + 1) = 511;
      DWORD1(v12) = DWORD1(v12) != 0;
      DWORD2(v12) = DWORD2(v12) != 0;
      HIDWORD(v12) = HIDWORD(v12) != 0;
      LODWORD(v13) = v13 != 0;
      DWORD1(v13) = DWORD1(v13) != 0;
      if ( (xmmword_18001F260 & 4) != 0 )
        WPP_SF_d(1026, 21, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, (unsigned int)g_rgfZtConfigInitialized[v2]);
      v9[0] = v11;
      v9[1] = v12;
      v9[2] = v13;
      v10 = v14;
      ZtUpdateConfig(v9, &g_rgfZtConfigInitialized[v2], &g_rgZtConfig[7 * v2], 0);
      Bool = 0;
      goto LABEL_24;
    }
    if ( !v7 )
      goto LABEL_21;
LABEL_24:
    ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
    goto LABEL_27;
  }
  Bool = 87;
  if ( (xmmword_18001F260 & 4) == 0 )
    return Bool;
  WPP_SF_d(1026, 20, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, 87);
LABEL_27:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 22, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, Bool);
  return Bool;
}

```

## disassembly

```asm
0x1800039e4  mov     [rsp-8+arg_10], rbx
0x1800039e9  push    rbp
0x1800039ea  push    rsi
0x1800039eb  push    rdi
0x1800039ec  lea     rbp, [rsp-47h]
0x1800039f1  sub     rsp, 0B0h
0x1800039f8  mov     rax, cs:__security_cookie
0x1800039ff  xor     rax, rsp
0x180003a02  mov     [rbp+57h+var_18], rax
0x180003a06  xorps   xmm0, xmm0
0x180003a09  movsxd  rsi, ecx
0x180003a0c  xor     eax, eax
0x180003a0e  mov     rdi, rdx
0x180003a11  movups  [rbp+57h+var_50], xmm0
0x180003a15  mov     [rbp+57h+var_20], rax
0x180003a19  movups  [rbp+57h+var_40], xmm0
0x180003a1d  movups  [rbp+57h+var_30], xmm0
0x180003a21  test    byte ptr cs:xmmword_18001F260, 4
0x180003a28  jz      short loc_180003A46
0x180003a2a  lea     edx, [rax+13h]
0x180003a2d  mov     [rsp+0C0h+var_A0], rdi
0x180003a32  mov     ecx, 402h
0x180003a37  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003a3e  mov     r9d, esi
0x180003a41  call    WPP_SF_dq
0x180003a46  test    rdi, rdi
0x180003a49  jnz     short loc_180003A53
0x180003a4b  lea     ebx, [rdi+57h]
0x180003a4e  jmp     loc_180003C6D
0x180003a53  cmp     esi, 1
0x180003a56  ja      loc_180003C48
0x180003a5c  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180003a63  call    cs:__imp_AcquireSRWLockExclusive
0x180003a69  lea     rdx, [rbp+57h+var_40]
0x180003a6d  mov     rcx, rdi
0x180003a70  call    ReadEnableZtdnsConfig
0x180003a75  mov     ebx, eax
0x180003a77  test    eax, eax
0x180003a79  jnz     loc_180003C39
0x180003a7f  lea     r8, [rbp+57h+var_40+4]
0x180003a83  mov     rcx, rdi
0x180003a86  lea     rdx, aZtdnsauditmode; "ZtdnsAuditMode"
0x180003a8d  call    ZtRegReadBool
0x180003a92  mov     ebx, eax
0x180003a94  test    eax, eax
0x180003a96  jnz     loc_180003C39
0x180003a9c  lea     r8, [rbp+57h+var_40+8]
0x180003aa0  mov     rcx, rdi
0x180003aa3  lea     rdx, aZtdnsblockloca; "ZtdnsBlockLocalIps"
0x180003aaa  call    ZtRegReadBool
0x180003aaf  mov     ebx, eax
0x180003ab1  test    eax, eax
0x180003ab3  jnz     loc_180003C39
0x180003ab9  lea     r8, [rbp+57h+var_40+0Ch]
0x180003abd  mov     rcx, rdi
0x180003ac0  lea     rdx, aZtdnsallowhost; "ZtdnsAllowHostsFile"
0x180003ac7  call    ZtRegReadBool
0x180003acc  mov     ebx, eax
0x180003ace  test    eax, eax
0x180003ad0  jnz     loc_180003C39
0x180003ad6  lea     r8, [rbp+57h+var_30]
0x180003ada  mov     rcx, rdi
0x180003add  lea     rdx, aZtdnsallowicsd; "ZtdnsAllowIcsDhcpServer"
0x180003ae4  call    ZtRegReadBool
0x180003ae9  mov     ebx, eax
0x180003aeb  test    eax, eax
0x180003aed  jnz     loc_180003C39
0x180003af3  lea     r8, [rbp+57h+var_30+4]
0x180003af7  mov     rcx, rdi
0x180003afa  lea     rdx, aZtdnsenablefor; "ZtdnsEnableForwarder"
0x180003b01  call    ZtRegReadBool
0x180003b06  mov     ebx, eax
0x180003b08  test    eax, eax
0x180003b0a  jnz     loc_180003C39
0x180003b10  lea     r8, [rbp+57h+var_30+8]
0x180003b14  mov     rcx, rdi
0x180003b17  lea     rdx, aZtdnsunicastli; "ZtdnsUnicastLifetime"
0x180003b1e  call    privateRegReadDwordValue
0x180003b23  cmp     eax, 2
0x180003b26  cmovnz  ebx, eax
0x180003b29  test    ebx, ebx
0x180003b2b  jnz     loc_180003C39
0x180003b31  lea     r8, [rbp+57h+var_30+0Ch]
0x180003b35  mov     rcx, rdi
0x180003b38  lea     rdx, aZtdnsmaxrecord; "ZtdnsMaxRecordAge"
0x180003b3f  call    privateRegReadDwordValue
0x180003b44  mov     ebx, eax
0x180003b46  cmp     eax, 2
0x180003b49  jnz     short loc_180003B54
0x180003b4b  mov     dword ptr [rbp+57h+var_30+0Ch], 15180h
0x180003b52  jmp     short loc_180003B5C
0x180003b54  test    eax, eax
0x180003b56  jnz     loc_180003C39
0x180003b5c  lea     r8, [rbp+57h+var_20]
0x180003b60  mov     rcx, rdi
0x180003b63  lea     rdx, aZtdnsservicena; "ZtdnsServiceNameRefreshTimeout"
0x180003b6a  call    privateRegReadDwordValue
0x180003b6f  mov     ebx, eax
0x180003b71  cmp     eax, 2
0x180003b74  jnz     short loc_180003B7F
0x180003b76  mov     dword ptr [rbp+57h+var_20], 708h
0x180003b7d  jmp     short loc_180003B87
0x180003b7f  test    eax, eax
0x180003b81  jnz     loc_180003C39
0x180003b87  xor     eax, eax
0x180003b89  mov     dword ptr [rbp+57h+var_50], 1
0x180003b90  cmp     dword ptr [rbp+57h+var_40+4], eax
0x180003b93  mov     qword ptr [rbp+57h+var_50+8], 1FFh
0x180003b9b  setnz   al
0x180003b9e  mov     dword ptr [rbp+57h+var_40+4], eax
0x180003ba1  xor     eax, eax
0x180003ba3  cmp     dword ptr [rbp+57h+var_40+8], eax
0x180003ba6  setnz   al
0x180003ba9  mov     dword ptr [rbp+57h+var_40+8], eax
0x180003bac  xor     eax, eax
0x180003bae  cmp     dword ptr [rbp+57h+var_40+0Ch], eax
0x180003bb1  setnz   al
0x180003bb4  mov     dword ptr [rbp+57h+var_40+0Ch], eax
0x180003bb7  xor     eax, eax
0x180003bb9  cmp     dword ptr [rbp+57h+var_30], eax
0x180003bbc  setnz   al
0x180003bbf  mov     dword ptr [rbp+57h+var_30], eax
0x180003bc2  xor     eax, eax
0x180003bc4  cmp     dword ptr [rbp+57h+var_30+4], eax
0x180003bc7  setnz   al
0x180003bca  mov     dword ptr [rbp+57h+var_30+4], eax
0x180003bcd  test    byte ptr cs:xmmword_18001F260, 4
0x180003bd4  lea     rbx, g_rgfZtConfigInitialized
0x180003bdb  jz      short loc_180003BF7
0x180003bdd  mov     r9d, [rbx+rsi*4]
0x180003be1  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003be8  mov     edx, 15h
0x180003bed  mov     ecx, 402h
0x180003bf2  call    WPP_SF_d
0x180003bf7  movups  xmm0, [rbp+57h+var_50]
0x180003bfb  lea     rcx, g_rgZtConfig
0x180003c02  xor     r9d, r9d
0x180003c05  movups  xmm1, [rbp+57h+var_40]
0x180003c09  lea     rdx, [rbx+rsi*4]
0x180003c0d  movaps  [rbp+57h+var_90], xmm0
0x180003c11  movups  xmm0, [rbp+57h+var_30]
0x180003c15  movaps  [rbp+57h+var_80], xmm1
0x180003c19  movsd   xmm1, [rbp+57h+var_20]
0x180003c1e  imul    r8, rsi, 38h ; '8'
0x180003c22  movaps  [rbp+57h+var_70], xmm0
0x180003c26  movsd   [rbp+57h+var_60], xmm1
0x180003c2b  add     r8, rcx
0x180003c2e  lea     rcx, [rbp+57h+var_90]
0x180003c32  call    ZtUpdateConfig
0x180003c37  xor     ebx, ebx
0x180003c39  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180003c40  call    cs:__imp_ReleaseSRWLockExclusive
0x180003c46  jmp     short loc_180003C6D
0x180003c48  mov     ebx, 57h ; 'W'
0x180003c4d  test    byte ptr cs:xmmword_18001F260, 4
0x180003c54  jz      short loc_180003C8F
0x180003c56  lea     edx, [rbx-43h]
0x180003c59  mov     ecx, 402h
0x180003c5e  mov     r9d, ebx
0x180003c61  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003c68  call    WPP_SF_d
0x180003c6d  test    byte ptr cs:xmmword_18001F260, 4
0x180003c74  jz      short loc_180003C8F
0x180003c76  mov     edx, 16h
0x180003c7b  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003c82  mov     ecx, 402h
0x180003c87  mov     r9d, ebx
0x180003c8a  call    WPP_SF_d
0x180003c8f  mov     eax, ebx
0x180003c91  mov     rcx, [rbp+57h+var_18]
0x180003c95  xor     rcx, rsp; StackCookie
0x180003c98  call    __security_check_cookie
0x180003c9d  mov     rbx, [rsp+0C0h+arg_10]
0x180003ca5  add     rsp, 0B0h
0x180003cac  pop     rdi
0x180003cad  pop     rsi
0x180003cae  pop     rbp
0x180003caf  retn
```
