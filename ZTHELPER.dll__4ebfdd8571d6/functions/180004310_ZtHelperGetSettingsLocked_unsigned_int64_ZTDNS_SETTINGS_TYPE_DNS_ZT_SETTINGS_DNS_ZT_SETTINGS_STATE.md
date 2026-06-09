# ZtHelperGetSettingsLocked(unsigned __int64,_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS * *,_DNS_ZT_SETTINGS_STATE *)

- ea: `0x180004310`
- end: `0x1800044de`
- name: `?ZtHelperGetSettingsLocked@@YAJ_KW4_ZTDNS_SETTINGS_TYPE@@PEAPEAU_DNS_ZT_SETTINGS@@PEAU_DNS_ZT_SETTINGS_STATE@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(char, int, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004238`
- `0x1800044e4`
- `0x1800049b0`

## callees

- `0x180004310`
- `0x18000fde8`
- `0x180010908`
- `0x180011858`
- `0x180011ca4`
- `0x1800120f0`
- `0x180012564`
- `0x180015008`
- `0x180015398`

## import_xrefs

- `DNSAPI!DnsFreeZtSettings` at `0x1800044c9`
- `DNSAPI!DnsFreeZtSettings` at `0x1800044c9`

## pseudocode

```c
__int64 __fastcall ZtHelperGetSettingsLocked(char a1, int a2, _QWORD *a3, __int64 a4)
{
  __int64 v5; // rsi
  _DWORD *v8; // rdi
  _DWORD *v9; // rax
  unsigned int ConfigLocked; // ebx
  __int64 v11; // rax

  v5 = a2;
  v8 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qq(1026, 32, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, a3, a4);
  if ( !a3 )
    goto LABEL_26;
  *a3 = 0;
  if ( (unsigned int)v5 > 1 )
  {
    ConfigLocked = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_29;
    WPP_SF_d(1026, 33, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, 87);
    goto LABEL_27;
  }
  v9 = (_DWORD *)Dns_Allocate(72);
  v8 = v9;
  if ( !v9 )
    goto LABEL_26;
  ConfigLocked = 0;
  *v9 = 1;
  if ( (a1 & 1) != 0 )
  {
    v11 = Dns_Allocate(56);
    *((_QWORD *)v8 + 2) = v11;
    if ( v11 )
    {
      ConfigLocked = ZtGetConfigLocked((unsigned int)v5, (unsigned int)g_rgfZtConfigInitialized[v5], v11);
      if ( ConfigLocked )
        goto LABEL_27;
      *((_QWORD *)v8 + 1) |= 1uLL;
      goto LABEL_10;
    }
LABEL_26:
    ConfigLocked = 87;
    goto LABEL_27;
  }
LABEL_10:
  if ( (a1 & 2) != 0 )
  {
    ConfigLocked = ZtGetTrustedServersLocked((unsigned int)v5, v8 + 8, v8 + 6);
    if ( ConfigLocked )
      goto LABEL_27;
    *((_QWORD *)v8 + 1) |= 2uLL;
  }
  if ( (a1 & 4) != 0 )
  {
    ConfigLocked = ZtGetRulesLocked((unsigned int)v5, v8 + 12, v8 + 10);
    if ( ConfigLocked )
      goto LABEL_27;
    *((_QWORD *)v8 + 1) |= 4uLL;
  }
  if ( (a1 & 8) != 0 )
  {
    ConfigLocked = ZtGetClientCertConfigLocked((unsigned int)v5, v8 + 14);
    if ( ConfigLocked )
      goto LABEL_27;
    *((_QWORD *)v8 + 1) |= 8uLL;
  }
  if ( (a1 & 0x10) == 0 )
    goto LABEL_22;
  ConfigLocked = ZtGetTrustedCaLocked((unsigned int)v5, v8 + 16);
  if ( !ConfigLocked )
  {
    *((_QWORD *)v8 + 1) |= 0x10uLL;
LABEL_22:
    *a3 = v8;
    v8 = 0;
    if ( a4 )
    {
      *(_OWORD *)a4 = *(__int128 *)((char *)&g_rgZtHelperSettingsState + 20 * v5);
      *(_DWORD *)(a4 + 16) = dword_18001F360[5 * v5];
    }
  }
LABEL_27:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 34, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, ConfigLocked);
LABEL_29:
  if ( v8 )
    DnsFreeZtSettings(v8);
  return ConfigLocked;
}

```

## disassembly

```asm
0x180004310  push    rbx
0x180004312  push    rbp
0x180004313  push    rsi
0x180004314  push    rdi
0x180004315  push    r14
0x180004317  push    r15
0x180004319  sub     rsp, 38h
0x18000431d  mov     r15, r9
0x180004320  movsxd  rsi, edx
0x180004323  mov     r14, r8
0x180004326  mov     rbp, rcx
0x180004329  xor     edi, edi
0x18000432b  test    byte ptr cs:xmmword_18001F260, 4
0x180004332  jz      short loc_180004350
0x180004334  mov     [rsp+68h+var_48], r9
0x180004339  lea     edx, [rdi+20h]
0x18000433c  mov     r9, r8
0x18000433f  mov     ecx, 402h
0x180004344  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x18000434b  call    WPP_SF_qq
0x180004350  test    r14, r14
0x180004353  jz      loc_18000449A
0x180004359  mov     [r14], rdi
0x18000435c  cmp     esi, 1
0x18000435f  ja      loc_180004473
0x180004365  mov     ecx, 48h ; 'H'
0x18000436a  call    Dns_Allocate
0x18000436f  mov     rdi, rax
0x180004372  test    rax, rax
0x180004375  jz      loc_18000449A
0x18000437b  xor     ebx, ebx
0x18000437d  mov     dword ptr [rax], 1
0x180004383  test    bpl, 1
0x180004387  jz      short loc_1800043C5
0x180004389  lea     ecx, [rbx+38h]
0x18000438c  call    Dns_Allocate
0x180004391  mov     [rdi+10h], rax
0x180004395  test    rax, rax
0x180004398  jz      loc_18000449A
0x18000439e  mov     r8, rax
0x1800043a1  mov     ecx, esi
0x1800043a3  lea     rax, cs:180000000h
0x1800043aa  mov     edx, rva g_rgfZtConfigInitialized[rax+rsi*4]
0x1800043b1  call    ZtGetConfigLocked
0x1800043b6  mov     ebx, eax
0x1800043b8  test    eax, eax
0x1800043ba  jnz     loc_18000449F
0x1800043c0  or      qword ptr [rdi+8], 1
0x1800043c5  test    bpl, 2
0x1800043c9  jz      short loc_1800043E9
0x1800043cb  lea     r8, [rdi+18h]
0x1800043cf  mov     ecx, esi
0x1800043d1  lea     rdx, [rdi+20h]
0x1800043d5  call    ZtGetTrustedServersLocked
0x1800043da  mov     ebx, eax
0x1800043dc  test    eax, eax
0x1800043de  jnz     loc_18000449F
0x1800043e4  or      qword ptr [rdi+8], 2
0x1800043e9  test    bpl, 4
0x1800043ed  jz      short loc_18000440D
0x1800043ef  lea     r8, [rdi+28h]
0x1800043f3  mov     ecx, esi
0x1800043f5  lea     rdx, [rdi+30h]
0x1800043f9  call    ZtGetRulesLocked
0x1800043fe  mov     ebx, eax
0x180004400  test    eax, eax
0x180004402  jnz     loc_18000449F
0x180004408  or      qword ptr [rdi+8], 4
0x18000440d  test    bpl, 8
0x180004411  jz      short loc_180004429
0x180004413  lea     rdx, [rdi+38h]
0x180004417  mov     ecx, esi
0x180004419  call    ZtGetClientCertConfigLocked
0x18000441e  mov     ebx, eax
0x180004420  test    eax, eax
0x180004422  jnz     short loc_18000449F
0x180004424  or      qword ptr [rdi+8], 8
0x180004429  test    bpl, 10h
0x18000442d  jz      short loc_180004445
0x18000442f  lea     rdx, [rdi+40h]
0x180004433  mov     ecx, esi
0x180004435  call    ZtGetTrustedCaLocked
0x18000443a  mov     ebx, eax
0x18000443c  test    eax, eax
0x18000443e  jnz     short loc_18000449F
0x180004440  or      qword ptr [rdi+8], 10h
0x180004445  mov     [r14], rdi
0x180004448  xor     edi, edi
0x18000444a  test    r15, r15
0x18000444d  jz      short loc_18000449F
0x18000444f  lea     rax, [rsi+rsi*4]
0x180004453  lea     rcx, cs:180000000h
0x18000445a  movups  xmm0, rva g_rgZtHelperSettingsState[rcx+rax*4]
0x180004462  movups  xmmword ptr [r15], xmm0
0x180004466  mov     eax, rva dword_18001F360[rcx+rax*4]
0x18000446d  mov     [r15+10h], eax
0x180004471  jmp     short loc_18000449F
0x180004473  mov     ebx, 57h ; 'W'
0x180004478  test    byte ptr cs:xmmword_18001F260, 4
0x18000447f  jz      short loc_1800044C1
0x180004481  lea     edx, [rbx-36h]
0x180004484  mov     ecx, 402h
0x180004489  mov     r9d, ebx
0x18000448c  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180004493  call    WPP_SF_d
0x180004498  jmp     short loc_18000449F
0x18000449a  mov     ebx, 57h ; 'W'
0x18000449f  test    byte ptr cs:xmmword_18001F260, 4
0x1800044a6  jz      short loc_1800044C1
0x1800044a8  mov     edx, 22h ; '"'
0x1800044ad  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x1800044b4  mov     ecx, 402h
0x1800044b9  mov     r9d, ebx
0x1800044bc  call    WPP_SF_d
0x1800044c1  test    rdi, rdi
0x1800044c4  jz      short loc_1800044CF
0x1800044c6  mov     rcx, rdi
0x1800044c9  call    cs:__imp_DnsFreeZtSettings
0x1800044cf  mov     eax, ebx
0x1800044d1  add     rsp, 38h
0x1800044d5  pop     r15
0x1800044d7  pop     r14
0x1800044d9  pop     rdi
0x1800044da  pop     rsi
0x1800044db  pop     rbp
0x1800044dc  pop     rbx
0x1800044dd  retn
```
