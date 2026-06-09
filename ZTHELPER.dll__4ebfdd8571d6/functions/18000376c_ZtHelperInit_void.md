# ZtHelperInit(void)

- ea: `0x18000376c`
- end: `0x1800039db`
- name: `?ZtHelperInit@@YAKXZ`
- size: `623`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180003150`

## callees

- `0x1800014b0`
- `0x18000376c`
- `0x1800039e4`
- `0x180003d88`
- `0x180006f9c`
- `0x18000897c`
- `0x180009420`
- `0x1800099a8`
- `0x18000ff50`
- `0x180015008`
- `0x180015114`
- `0x180015268`

## import_xrefs

- `ntdll!NtClose` at `0x1800038f8`
- `ntdll!NtClose` at `0x1800039a4`
- `ntdll!NtClose` at `0x1800038f8`
- `ntdll!NtClose` at `0x1800039a4`
- `RPCRT4!UuidCreateSequential` at `0x1800037ca`
- `RPCRT4!UuidCreateSequential` at `0x1800037ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039bb`

## pseudocode

```c
__int64 ZtHelperInit(void)
{
  RPC_STATUS v0; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  unsigned int v3; // ebx
  unsigned int v4; // edi
  unsigned int v5; // ebx
  unsigned int inited; // eax
  __int64 v7; // rdx
  HANDLE Handle; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  hKey = 0;
  Uuid = 0;
  Handle = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_(1026, 23, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids);
  v0 = UuidCreateSequential(&Uuid);
  if ( !v0 || v0 == 1824 )
  {
    if ( g_fVelocityZtdnsProbing && (unsigned int)ZtStagingExists() )
      _InterlockedIncrement(&dword_18001F364);
    v4 = 0;
    while ( 1 )
    {
      v5 = v4;
      *(__int128 *)((char *)&g_rgZtHelperSettingsState + 20 * (int)v4 + 4) = (__int128)Uuid;
      if ( v4 == 1 )
        v5 = ZtStagingExists() != 0;
      inited = ZtRegOpen(v5, v1, v2, &hKey, &Handle);
      v3 = inited;
      if ( inited )
        break;
      inited = ZtHelperInitConfig(v4, hKey);
      v3 = inited;
      if ( inited )
      {
        if ( (xmmword_18001F260 & 4) == 0 )
          goto LABEL_40;
        v7 = 26;
        goto LABEL_37;
      }
      inited = ZtHelperInitTrustedServers(v4, hKey, Handle);
      v3 = inited;
      if ( inited )
      {
        if ( (xmmword_18001F260 & 4) == 0 )
          goto LABEL_40;
        v7 = 27;
        goto LABEL_37;
      }
      inited = ZtHelperInitRules(v4, hKey, Handle);
      v3 = inited;
      if ( inited )
      {
        if ( (xmmword_18001F260 & 4) == 0 )
          goto LABEL_40;
        v7 = 28;
        goto LABEL_37;
      }
      inited = ZtHelperInitTrustedCa(v4, hKey, Handle);
      v3 = inited;
      if ( inited )
      {
        if ( (xmmword_18001F260 & 4) == 0 )
          goto LABEL_40;
        v7 = 29;
        goto LABEL_37;
      }
      inited = ZtHelperInitClientCerts(v4, hKey, Handle);
      v3 = inited;
      if ( inited )
      {
        if ( (xmmword_18001F260 & 4) == 0 )
          goto LABEL_40;
        v7 = 30;
        goto LABEL_37;
      }
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      if ( Handle )
      {
        NtClose(Handle);
        Handle = 0;
      }
      if ( ++v4 >= 2 )
        goto LABEL_38;
    }
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_40;
    v7 = 25;
LABEL_37:
    WPP_SF_d(1026, v7, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, inited);
  }
  else
  {
    v3 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_40;
    WPP_SF_Dd(1026, 24, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids);
  }
LABEL_38:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 31, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, v3);
LABEL_40:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18000376c  push    rbp
0x18000376e  push    rbx
0x18000376f  push    rdi
0x180003770  push    r12
0x180003772  push    r15
0x180003774  mov     rbp, rsp
0x180003777  sub     rsp, 60h
0x18000377b  mov     rax, cs:__security_cookie
0x180003782  xor     rax, rsp
0x180003785  mov     [rbp+var_10], rax
0x180003789  xorps   xmm0, xmm0
0x18000378c  mov     [rbp+hKey], 0
0x180003794  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180003798  mov     [rbp+Handle], 0
0x1800037a0  test    byte ptr cs:xmmword_18001F260, 4
0x1800037a7  lea     r12, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x1800037ae  mov     r15d, 402h
0x1800037b4  jz      short loc_1800037C6
0x1800037b6  mov     edx, 17h
0x1800037bb  mov     ecx, r15d
0x1800037be  mov     r8, r12
0x1800037c1  call    WPP_SF_
0x1800037c6  lea     rcx, [rbp+Uuid]; Uuid
0x1800037ca  call    cs:__imp_UuidCreateSequential
0x1800037d0  test    eax, eax
0x1800037d2  jz      short loc_180003804
0x1800037d4  cmp     eax, 720h
0x1800037d9  jz      short loc_180003804
0x1800037db  mov     ebx, 57h ; 'W'
0x1800037e0  test    byte ptr cs:xmmword_18001F260, 4
0x1800037e7  jz      loc_18000399B
0x1800037ed  lea     edx, [rbx-3Fh]
0x1800037f0  mov     dword ptr [rsp+60h+var_40], ebx
0x1800037f4  mov     ecx, r15d
0x1800037f7  mov     r8, r12
0x1800037fa  call    WPP_SF_Dd
0x1800037ff  jmp     loc_18000397F
0x180003804  cmp     cs:g_fVelocityZtdnsProbing, 0
0x18000380b  jz      short loc_18000381D
0x18000380d  call    ZtStagingExists
0x180003812  test    eax, eax
0x180003814  jz      short loc_18000381D
0x180003816  lock inc cs:dword_18001F364
0x18000381d  xor     edi, edi
0x18000381f  movsxd  rax, edi
0x180003822  mov     ebx, edi
0x180003824  movups  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180003828  lea     rcx, [rax+rax*4]
0x18000382c  lea     rax, g_rgZtHelperSettingsState
0x180003833  movdqu  xmmword ptr [rax+rcx*4+4], xmm0
0x180003839  cmp     edi, 1
0x18000383c  jnz     short loc_180003849
0x18000383e  call    ZtStagingExists
0x180003843  neg     eax
0x180003845  sbb     ecx, ecx
0x180003847  and     ebx, ecx
0x180003849  lea     rax, [rbp+Handle]
0x18000384d  mov     ecx, ebx
0x18000384f  lea     r9, [rbp+hKey]
0x180003853  mov     [rsp+60h+var_40], rax
0x180003858  call    ZtRegOpen
0x18000385d  mov     ebx, eax
0x18000385f  test    eax, eax
0x180003861  jnz     loc_180003963
0x180003867  mov     rdx, [rbp+hKey]
0x18000386b  mov     ecx, edi
0x18000386d  call    ?ZtHelperInitConfig@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAUHKEY__@@@Z; ZtHelperInitConfig(_ZTDNS_SETTINGS_TYPE,HKEY__ *)
0x180003872  mov     ebx, eax
0x180003874  test    eax, eax
0x180003876  jnz     loc_180003953
0x18000387c  mov     r8, [rbp+Handle]
0x180003880  mov     ecx, edi
0x180003882  mov     rdx, [rbp+hKey]
0x180003886  call    ZtHelperInitTrustedServers
0x18000388b  mov     ebx, eax
0x18000388d  test    eax, eax
0x18000388f  jnz     loc_180003943
0x180003895  mov     r8, [rbp+Handle]
0x180003899  mov     ecx, edi
0x18000389b  mov     rdx, [rbp+hKey]
0x18000389f  call    ZtHelperInitRules
0x1800038a4  mov     ebx, eax
0x1800038a6  test    eax, eax
0x1800038a8  jnz     loc_180003933
0x1800038ae  mov     r8, [rbp+Handle]
0x1800038b2  mov     ecx, edi
0x1800038b4  mov     rdx, [rbp+hKey]
0x1800038b8  call    ZtHelperInitTrustedCa
0x1800038bd  mov     ebx, eax
0x1800038bf  test    eax, eax
0x1800038c1  jnz     short loc_180003923
0x1800038c3  mov     r8, [rbp+Handle]
0x1800038c7  mov     ecx, edi
0x1800038c9  mov     rdx, [rbp+hKey]
0x1800038cd  call    ZtHelperInitClientCerts
0x1800038d2  mov     ebx, eax
0x1800038d4  test    eax, eax
0x1800038d6  jnz     short loc_180003913
0x1800038d8  mov     rcx, [rbp+hKey]; hKey
0x1800038dc  test    rcx, rcx
0x1800038df  jz      short loc_1800038EF
0x1800038e1  call    cs:__imp_RegCloseKey
0x1800038e7  mov     [rbp+hKey], 0
0x1800038ef  mov     rcx, [rbp+Handle]; Handle
0x1800038f3  test    rcx, rcx
0x1800038f6  jz      short loc_180003906
0x1800038f8  call    cs:__imp_NtClose
0x1800038fe  mov     [rbp+Handle], 0
0x180003906  inc     edi
0x180003908  cmp     edi, 2
0x18000390b  jb      loc_18000381F
0x180003911  jmp     short loc_18000397F
0x180003913  test    byte ptr cs:xmmword_18001F260, 4
0x18000391a  jz      short loc_18000399B
0x18000391c  mov     edx, 1Eh
0x180003921  jmp     short loc_180003971
0x180003923  test    byte ptr cs:xmmword_18001F260, 4
0x18000392a  jz      short loc_18000399B
0x18000392c  mov     edx, 1Dh
0x180003931  jmp     short loc_180003971
0x180003933  test    byte ptr cs:xmmword_18001F260, 4
0x18000393a  jz      short loc_18000399B
0x18000393c  mov     edx, 1Ch
0x180003941  jmp     short loc_180003971
0x180003943  test    byte ptr cs:xmmword_18001F260, 4
0x18000394a  jz      short loc_18000399B
0x18000394c  mov     edx, 1Bh
0x180003951  jmp     short loc_180003971
0x180003953  test    byte ptr cs:xmmword_18001F260, 4
0x18000395a  jz      short loc_18000399B
0x18000395c  mov     edx, 1Ah
0x180003961  jmp     short loc_180003971
0x180003963  test    byte ptr cs:xmmword_18001F260, 4
0x18000396a  jz      short loc_18000399B
0x18000396c  mov     edx, 19h
0x180003971  mov     r9d, eax
0x180003974  mov     r8, r12
0x180003977  mov     ecx, r15d
0x18000397a  call    WPP_SF_d
0x18000397f  test    byte ptr cs:xmmword_18001F260, 4
0x180003986  jz      short loc_18000399B
0x180003988  mov     edx, 1Fh
0x18000398d  mov     ecx, r15d
0x180003990  mov     r9d, ebx
0x180003993  mov     r8, r12
0x180003996  call    WPP_SF_d
0x18000399b  mov     rcx, [rbp+Handle]; Handle
0x18000399f  test    rcx, rcx
0x1800039a2  jz      short loc_1800039B2
0x1800039a4  call    cs:__imp_NtClose
0x1800039aa  mov     [rbp+Handle], 0
0x1800039b2  mov     rcx, [rbp+hKey]; hKey
0x1800039b6  test    rcx, rcx
0x1800039b9  jz      short loc_1800039C1
0x1800039bb  call    cs:__imp_RegCloseKey
0x1800039c1  mov     eax, ebx
0x1800039c3  mov     rcx, [rbp+var_10]
0x1800039c7  xor     rcx, rsp; StackCookie
0x1800039ca  call    __security_check_cookie
0x1800039cf  add     rsp, 60h
0x1800039d3  pop     r15
0x1800039d5  pop     r12
0x1800039d7  pop     rdi
0x1800039d8  pop     rbx
0x1800039d9  pop     rbp
0x1800039da  retn
```
