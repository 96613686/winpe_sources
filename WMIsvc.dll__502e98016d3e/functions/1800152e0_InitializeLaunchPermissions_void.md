# InitializeLaunchPermissions(void)

- ea: `0x1800152e0`
- end: `0x18001554e`
- name: `?InitializeLaunchPermissions@@YAXXZ`
- size: `622`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015ff0`

## callees

- `0x1800152e0`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800154f1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800154fb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800154f1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800154fb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015393`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800153ea`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015393`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800153ea`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180015310`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180015310`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180015506`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180015506`
- `wbemcomn!?GetBinary@Registry@@QEAAHPEBGPEAPEAEPEAK@Z` at `0x18001533e`
- `wbemcomn!?GetBinary@Registry@@QEAAHPEBGPEAPEAEPEAK@Z` at `0x18001533e`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x180015409`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x180015418`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x180015409`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x180015418`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800154dc`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800154e7`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800154dc`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800154e7`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800154d1`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800154d1`
- `wbemcomn!??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z` at `0x180015458`
- `wbemcomn!??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z` at `0x180015458`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x18001546c`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x18001546c`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x18001547c`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x18001547c`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x1800154bb`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x1800154bb`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x18001548c`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x18001548c`
- `wbemcomn!?SetOwner@CNtSecurityDescriptor@@QEAAHPEAVCNtSid@@@Z` at `0x18001549b`
- `wbemcomn!?SetOwner@CNtSecurityDescriptor@@QEAAHPEAVCNtSid@@@Z` at `0x18001549b`
- `wbemcomn!?SetGroup@CNtSecurityDescriptor@@QEAAHPEAVCNtSid@@@Z` at `0x1800154aa`
- `wbemcomn!?SetGroup@CNtSecurityDescriptor@@QEAAHPEAVCNtSid@@@Z` at `0x1800154aa`
- `wbemcomn!?SetBinary@Registry@@QEAAHPEBGPEAEK@Z` at `0x180015542`
- `wbemcomn!?SetBinary@Registry@@QEAAHPEBGPEAEK@Z` at `0x180015542`
- `wbemcomn!?GetSize@CNtSecurityDescriptor@@QEAAKXZ` at `0x180015529`
- `wbemcomn!?GetSize@CNtSecurityDescriptor@@QEAAKXZ` at `0x180015529`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x18001543a`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x18001543a`
- `wbemcomn!??1CNtAce@@UEAA@XZ` at `0x1800154c6`
- `wbemcomn!??1CNtAce@@UEAA@XZ` at `0x1800154c6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001534c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001534c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void InitializeLaunchPermissions(void)
{
  PSID v0; // rbx
  PSID v1; // rdi
  unsigned int Size; // eax
  unsigned __int8 *v3; // [rsp+60h] [rbp-A0h] BYREF
  int v4; // [rsp+68h] [rbp-98h]
  unsigned int v5; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  PSID v7; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v8[8]; // [rsp+88h] [rbp-78h] BYREF
  int v9; // [rsp+90h] [rbp-70h]
  _BYTE v10[20]; // [rsp+98h] [rbp-68h] BYREF
  int v11; // [rsp+ACh] [rbp-54h]
  _BYTE v12[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v13; // [rsp+B8h] [rbp-48h]
  _BYTE v14[8]; // [rsp+C0h] [rbp-40h] BYREF
  int v15; // [rsp+C8h] [rbp-38h]
  unsigned __int8 *v16; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v17[16]; // [rsp+D8h] [rbp-28h] BYREF
  int v18; // [rsp+E8h] [rbp-18h]
  PSID v19; // [rsp+F0h] [rbp-10h]
  PSID v20; // [rsp+F8h] [rbp-8h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+100h] [rbp+0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v22; // [rsp+108h] [rbp+8h] BYREF

  Registry::Registry((Registry *)v10, L"SOFTWARE\\CLASSES\\APPID\\{8bc3f05e-d86b-11d0-a075-00c04fb68820}", 3u);
  if ( !v11 )
  {
    v16 = 0;
    v5 = 0;
    if ( Registry::GetBinary((Registry *)v10, L"LaunchPermission", &v16, &v5) )
    {
      pSid = 0;
      *(_DWORD *)pIdentifierAuthority.Value = 0;
      *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        v0 = pSid;
        v19 = pSid;
        *(_DWORD *)v22.Value = 0;
        *(_WORD *)&v22.Value[4] = 1280;
        v7 = 0;
        if ( AllocateAndInitializeSid(&v22, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v7) )
        {
          v1 = v7;
          v20 = v7;
          CNtSid::CNtSid((CNtSid *)v14, pSid);
          CNtSid::CNtSid((CNtSid *)v8, v7);
          if ( !v15 && !v9 )
          {
            CNtAcl::CNtAcl((CNtAcl *)v12, 0x80u);
            CNtAce::CNtAce((CNtAce *)v17, 1u, 0, 0, (struct CNtSid *)v14);
            if ( !v18 )
            {
              CNtAcl::AddAce((CNtAcl *)v12, (struct CNtAce *)v17);
              if ( !v13 )
              {
                CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)&v3);
                CNtSecurityDescriptor::SetDacl((CNtSecurityDescriptor *)&v3, (struct CNtAcl *)v12);
                CNtSecurityDescriptor::SetOwner((CNtSecurityDescriptor *)&v3, (struct CNtSid *)v8);
                CNtSecurityDescriptor::SetGroup((CNtSecurityDescriptor *)&v3, (struct CNtSid *)v8);
                if ( !v4 )
                {
                  Size = CNtSecurityDescriptor::GetSize((CNtSecurityDescriptor *)&v3);
                  Registry::SetBinary((Registry *)v10, L"LaunchPermission", v3, Size);
                }
                CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)&v3);
              }
            }
            CNtAce::~CNtAce(v17);
            CNtAcl::~CNtAcl((CNtAcl *)v12);
          }
          CNtSid::~CNtSid((CNtSid *)v8);
          CNtSid::~CNtSid((CNtSid *)v14);
          FreeSid(v1);
        }
        FreeSid(v0);
      }
    }
    else
    {
      CWin32DefaultArena::WbemMemFree(v16);
    }
  }
  Registry::~Registry((Registry *)v10);
}

```

## disassembly

```asm
0x1800152e0  push    rbp
0x1800152e2  push    rbx
0x1800152e3  push    rsi
0x1800152e4  push    rdi
0x1800152e5  lea     rbp, [rsp-28h]
0x1800152ea  sub     rsp, 128h
0x1800152f1  mov     rax, cs:__security_cookie
0x1800152f8  xor     rax, rsp
0x1800152fb  mov     [rbp+40h+var_30], rax
0x1800152ff  mov     r8d, 3
0x180015305  lea     rdx, aSoftwareClasse; "SOFTWARE\\CLASSES\\APPID\\{8bc3f05e-d86"...
0x18001530c  lea     rcx, [rbp+40h+var_A8]
0x180015310  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180015316  nop
0x180015317  xor     esi, esi
0x180015319  cmp     [rbp+40h+var_94], esi
0x18001531c  jnz     loc_180015502
0x180015322  mov     [rbp+40h+var_70], rsi
0x180015326  mov     [rsp+140h+var_D0], esi
0x18001532a  lea     r9, [rsp+140h+var_D0]
0x18001532f  lea     r8, [rbp+40h+var_70]
0x180015333  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x18001533a  lea     rcx, [rbp+40h+var_A8]
0x18001533e  call    cs:__imp_?GetBinary@Registry@@QEAAHPEBGPEAPEAEPEAK@Z; Registry::GetBinary(ushort const *,uchar * *,ulong *)
0x180015344  test    eax, eax
0x180015346  jnz     short loc_180015357
0x180015348  mov     rcx, [rbp+40h+var_70]
0x18001534c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180015352  jmp     loc_180015502
0x180015357  mov     [rsp+140h+var_C8], rsi
0x18001535c  mov     dword ptr [rbp+40h+pIdentifierAuthority.Value], esi
0x18001535f  mov     word ptr [rbp+40h+pIdentifierAuthority.Value+4], 100h
0x180015365  lea     rax, [rsp+140h+var_C8]
0x18001536a  mov     [rsp+140h+pSid], rax; pSid
0x18001536f  mov     [rsp+140h+nSubAuthority7], esi; nSubAuthority7
0x180015373  mov     [rsp+140h+nSubAuthority6], esi; nSubAuthority6
0x180015377  mov     [rsp+140h+nSubAuthority5], esi; nSubAuthority5
0x18001537b  mov     [rsp+140h+nSubAuthority4], esi; nSubAuthority4
0x18001537f  mov     [rsp+140h+nSubAuthority3], esi; nSubAuthority3
0x180015383  mov     [rsp+140h+nSubAuthority2], esi; nSubAuthority2
0x180015387  xor     r9d, r9d; nSubAuthority1
0x18001538a  xor     r8d, r8d; nSubAuthority0
0x18001538d  mov     dl, 1; nSubAuthorityCount
0x18001538f  lea     rcx, [rbp+40h+pIdentifierAuthority]; pIdentifierAuthority
0x180015393  call    cs:__imp_AllocateAndInitializeSid
0x180015399  test    eax, eax
0x18001539b  jz      loc_180015502
0x1800153a1  mov     rbx, [rsp+140h+var_C8]
0x1800153a6  mov     [rbp+40h+var_50], rbx
0x1800153aa  mov     dword ptr [rbp+40h+var_38.Value], esi
0x1800153ad  mov     word ptr [rbp+40h+var_38.Value+4], 500h
0x1800153b3  mov     [rbp+40h+var_C0], rsi
0x1800153b7  lea     rax, [rbp+40h+var_C0]
0x1800153bb  mov     [rsp+140h+pSid], rax; pSid
0x1800153c0  mov     [rsp+140h+nSubAuthority7], esi; nSubAuthority7
0x1800153c4  mov     [rsp+140h+nSubAuthority6], esi; nSubAuthority6
0x1800153c8  mov     [rsp+140h+nSubAuthority5], esi; nSubAuthority5
0x1800153cc  mov     [rsp+140h+nSubAuthority4], esi; nSubAuthority4
0x1800153d0  mov     [rsp+140h+nSubAuthority3], esi; nSubAuthority3
0x1800153d4  mov     [rsp+140h+nSubAuthority2], esi; nSubAuthority2
0x1800153d8  mov     r9d, 220h; nSubAuthority1
0x1800153de  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800153e4  mov     dl, 2; nSubAuthorityCount
0x1800153e6  lea     rcx, [rbp+40h+var_38]; pIdentifierAuthority
0x1800153ea  call    cs:__imp_AllocateAndInitializeSid
0x1800153f0  test    eax, eax
0x1800153f2  jz      loc_1800154F8
0x1800153f8  mov     rdi, [rbp+40h+var_C0]
0x1800153fc  mov     [rbp+40h+var_48], rdi
0x180015400  mov     rdx, [rsp+140h+var_C8]
0x180015405  lea     rcx, [rbp+40h+var_80]
0x180015409  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18001540f  nop
0x180015410  mov     rdx, [rbp+40h+var_C0]
0x180015414  lea     rcx, [rbp+40h+var_B8]
0x180015418  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18001541e  nop
0x18001541f  cmp     [rbp+40h+var_78], esi
0x180015422  jnz     loc_1800154D8
0x180015428  cmp     [rbp+40h+var_B0], esi
0x18001542b  jnz     loc_1800154D8
0x180015431  mov     edx, 80h
0x180015436  lea     rcx, [rbp+40h+var_90]
0x18001543a  call    cs:__imp_??0CNtAcl@@QEAA@K@Z; CNtAcl::CNtAcl(ulong)
0x180015440  nop
0x180015441  lea     rax, [rbp+40h+var_80]
0x180015445  mov     qword ptr [rsp+140h+nSubAuthority2], rax
0x18001544a  xor     r9d, r9d
0x18001544d  xor     r8d, r8d
0x180015450  lea     edx, [r9+1]
0x180015454  lea     rcx, [rbp+40h+var_68]
0x180015458  call    cs:__imp_??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z; CNtAce::CNtAce(ulong,ulong,ulong,CNtSid &)
0x18001545e  nop
0x18001545f  cmp     [rbp+40h+var_58], esi
0x180015462  jnz     short loc_1800154C2
0x180015464  lea     rdx, [rbp+40h+var_68]
0x180015468  lea     rcx, [rbp+40h+var_90]
0x18001546c  call    cs:__imp_?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z; CNtAcl::AddAce(CNtAce *)
0x180015472  cmp     [rbp+40h+var_88], esi
0x180015475  jnz     short loc_1800154C2
0x180015477  lea     rcx, [rsp+140h+var_E0]
0x18001547c  call    cs:__imp_??0CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::CNtSecurityDescriptor(void)
0x180015482  nop
0x180015483  lea     rdx, [rbp+40h+var_90]
0x180015487  lea     rcx, [rsp+140h+var_E0]
0x18001548c  call    cs:__imp_?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x180015492  lea     rdx, [rbp+40h+var_B8]
0x180015496  lea     rcx, [rsp+140h+var_E0]
0x18001549b  call    cs:__imp_?SetOwner@CNtSecurityDescriptor@@QEAAHPEAVCNtSid@@@Z; CNtSecurityDescriptor::SetOwner(CNtSid *)
0x1800154a1  lea     rdx, [rbp+40h+var_B8]
0x1800154a5  lea     rcx, [rsp+140h+var_E0]
0x1800154aa  call    cs:__imp_?SetGroup@CNtSecurityDescriptor@@QEAAHPEAVCNtSid@@@Z; CNtSecurityDescriptor::SetGroup(CNtSid *)
0x1800154b0  cmp     [rsp+140h+var_D8], esi
0x1800154b4  jz      short loc_180015524
0x1800154b6  lea     rcx, [rsp+140h+var_E0]
0x1800154bb  call    cs:__imp_??1CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::~CNtSecurityDescriptor(void)
0x1800154c1  nop
0x1800154c2  lea     rcx, [rbp+40h+var_68]
0x1800154c6  call    cs:__imp_??1CNtAce@@UEAA@XZ; CNtAce::~CNtAce(void)
0x1800154cc  nop
0x1800154cd  lea     rcx, [rbp+40h+var_90]
0x1800154d1  call    cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x1800154d7  nop
0x1800154d8  lea     rcx, [rbp+40h+var_B8]
0x1800154dc  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x1800154e2  nop
0x1800154e3  lea     rcx, [rbp+40h+var_80]
0x1800154e7  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x1800154ed  nop
0x1800154ee  mov     rcx, rdi; pSid
0x1800154f1  call    cs:__imp_FreeSid
0x1800154f7  nop
0x1800154f8  mov     rcx, rbx; pSid
0x1800154fb  call    cs:__imp_FreeSid
0x180015501  nop
0x180015502  lea     rcx, [rbp+40h+var_A8]
0x180015506  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18001550c  mov     rcx, [rbp+40h+var_30]
0x180015510  xor     rcx, rsp; StackCookie
0x180015513  call    __security_check_cookie
0x180015518  add     rsp, 128h
0x18001551f  pop     rdi
0x180015520  pop     rsi
0x180015521  pop     rbx
0x180015522  pop     rbp
0x180015523  retn
0x180015524  lea     rcx, [rsp+140h+var_E0]
0x180015529  call    cs:__imp_?GetSize@CNtSecurityDescriptor@@QEAAKXZ; CNtSecurityDescriptor::GetSize(void)
0x18001552f  mov     r9d, eax
0x180015532  mov     r8, [rsp+140h+var_E0]
0x180015537  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x18001553e  lea     rcx, [rbp+40h+var_A8]
0x180015542  call    cs:__imp_?SetBinary@Registry@@QEAAHPEBGPEAEK@Z; Registry::SetBinary(ushort const *,uchar *,ulong)
0x180015548  jmp     loc_1800154B6
```
