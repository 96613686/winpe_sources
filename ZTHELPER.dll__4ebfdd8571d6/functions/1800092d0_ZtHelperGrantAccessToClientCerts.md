# ZtHelperGrantAccessToClientCerts

- ea: `0x1800092d0`
- end: `0x18000941a`
- name: `ZtHelperGrantAccessToClientCerts`
- size: `330`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002550`

## callees

- `0x1800092d0`
- `0x18000c788`
- `0x18000dbcc`
- `0x18000e270`
- `0x1800120f0`
- `0x180015008`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800093e2`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800093e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800093a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800093a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009324`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009324`

## pseudocode

```c
__int64 __fastcall ZtHelperGrantAccessToClientCerts(int a1, __int64 a2)
{
  __int64 v2; // rbx
  void *v4; // rcx
  unsigned int v5; // ebx
  unsigned int ClientCertConfigLocked; // eax
  __int64 v7; // rdx
  LPVOID lpMem; // [rsp+60h] [rbp+18h] BYREF

  v2 = a1;
  v4 = 0;
  lpMem = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    WPP_SF_d(1026, 31, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, (unsigned int)v2);
    v4 = lpMem;
  }
  if ( (unsigned int)v2 <= 1 )
  {
    AcquireSRWLockShared(&g_rwZtSettingsLock);
    if ( !(unsigned int)ZtSynchronizeSettingsState(a2, (char *)&g_rgZtHelperSettingsState + 20 * v2) )
    {
      v5 = 5023;
LABEL_13:
      ReleaseSRWLockShared(&g_rwZtSettingsLock);
      goto LABEL_16;
    }
    ClientCertConfigLocked = ZtGetClientCertConfigLocked((unsigned int)v2, &lpMem);
    v5 = ClientCertConfigLocked;
    if ( ClientCertConfigLocked )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        goto LABEL_13;
      v7 = 33;
    }
    else
    {
      ClientCertConfigLocked = DnsGrantZtAccessToAllPrivateKeys(lpMem);
      v5 = ClientCertConfigLocked;
      if ( !ClientCertConfigLocked || (xmmword_18001F260 & 4) == 0 )
        goto LABEL_13;
      v7 = 34;
    }
    WPP_SF_d(1026, v7, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, ClientCertConfigLocked);
    goto LABEL_13;
  }
  v5 = 87;
  if ( (xmmword_18001F260 & 4) == 0 )
    goto LABEL_17;
  WPP_SF_d(1026, 32, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, 87);
LABEL_16:
  v4 = lpMem;
LABEL_17:
  if ( g_fVelocityZtdnsApiRefactor )
  {
    ZtFreeClientCertConfig(v4);
  }
  else
  {
    if ( !v4 )
      goto LABEL_22;
    DnsFreeZtClientCertConfig();
  }
  lpMem = 0;
LABEL_22:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 35, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800092d0  push    rbx
0x1800092d2  push    rdi
0x1800092d3  push    r14
0x1800092d5  push    r15
0x1800092d7  sub     rsp, 28h
0x1800092db  movsxd  rbx, ecx
0x1800092de  mov     rdi, rdx
0x1800092e1  xor     ecx, ecx
0x1800092e3  mov     [rsp+48h+lpMem], rcx
0x1800092e8  test    byte ptr cs:xmmword_18001F260, 4
0x1800092ef  lea     r15, WPP_c9cb64bf9be638328d158dcace113d85_Traceguids
0x1800092f6  mov     r14d, 402h
0x1800092fc  jz      short loc_180009314
0x1800092fe  lea     edx, [rcx+1Fh]
0x180009301  mov     r9d, ebx
0x180009304  mov     ecx, r14d
0x180009307  mov     r8, r15
0x18000930a  call    WPP_SF_d
0x18000930f  mov     rcx, [rsp+48h+lpMem]
0x180009314  cmp     ebx, 1
0x180009317  ja      loc_1800093A9
0x18000931d  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180009324  call    cs:__imp_AcquireSRWLockShared
0x18000932a  lea     rcx, [rbx+rbx*4]
0x18000932e  lea     rax, g_rgZtHelperSettingsState
0x180009335  lea     rdx, [rax+rcx*4]
0x180009339  mov     rcx, rdi
0x18000933c  call    ZtSynchronizeSettingsState
0x180009341  test    eax, eax
0x180009343  jnz     short loc_18000934C
0x180009345  mov     ebx, 139Fh
0x18000934a  jmp     short loc_18000939A
0x18000934c  lea     rdx, [rsp+48h+lpMem]
0x180009351  mov     ecx, ebx
0x180009353  call    ZtGetClientCertConfigLocked
0x180009358  mov     ebx, eax
0x18000935a  test    eax, eax
0x18000935c  jnz     short loc_18000937E
0x18000935e  mov     rcx, [rsp+48h+lpMem]
0x180009363  call    DnsGrantZtAccessToAllPrivateKeys
0x180009368  mov     ebx, eax
0x18000936a  test    eax, eax
0x18000936c  jz      short loc_18000939A
0x18000936e  test    byte ptr cs:xmmword_18001F260, 4
0x180009375  jz      short loc_18000939A
0x180009377  mov     edx, 22h ; '"'
0x18000937c  jmp     short loc_18000938C
0x18000937e  test    byte ptr cs:xmmword_18001F260, 4
0x180009385  jz      short loc_18000939A
0x180009387  mov     edx, 21h ; '!'
0x18000938c  mov     r9d, eax
0x18000938f  mov     r8, r15
0x180009392  mov     ecx, r14d
0x180009395  call    WPP_SF_d
0x18000939a  lea     rcx, g_rwZtSettingsLock; SRWLock
0x1800093a1  call    cs:__imp_ReleaseSRWLockShared
0x1800093a7  jmp     short loc_1800093C8
0x1800093a9  mov     ebx, 57h ; 'W'
0x1800093ae  test    byte ptr cs:xmmword_18001F260, 4
0x1800093b5  jz      short loc_1800093CD
0x1800093b7  lea     edx, [rbx-37h]
0x1800093ba  mov     ecx, r14d
0x1800093bd  mov     r9d, ebx
0x1800093c0  mov     r8, r15
0x1800093c3  call    WPP_SF_d
0x1800093c8  mov     rcx, [rsp+48h+lpMem]; lpMem
0x1800093cd  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x1800093d4  jz      short loc_1800093DD
0x1800093d6  call    ZtFreeClientCertConfig
0x1800093db  jmp     short loc_1800093E8
0x1800093dd  test    rcx, rcx
0x1800093e0  jz      short loc_1800093F1
0x1800093e2  call    cs:__imp_DnsFreeZtClientCertConfig
0x1800093e8  mov     [rsp+48h+lpMem], 0
0x1800093f1  test    byte ptr cs:xmmword_18001F260, 4
0x1800093f8  jz      short loc_18000940D
0x1800093fa  mov     edx, 23h ; '#'
0x1800093ff  mov     ecx, r14d
0x180009402  mov     r9d, ebx
0x180009405  mov     r8, r15
0x180009408  call    WPP_SF_d
0x18000940d  mov     eax, ebx
0x18000940f  add     rsp, 28h
0x180009413  pop     r15
0x180009415  pop     r14
0x180009417  pop     rdi
0x180009418  pop     rbx
0x180009419  retn
```
