# CheckClientIdentity(void *,ulong,int *)

- ea: `0x14002233c`
- end: `0x140022566`
- name: `?CheckClientIdentity@@YAJPEAXKPEAH@Z`
- size: `554`
- prototype: `__int64 __fastcall(void *, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140022a08`

## callees

- `0x14000493c`
- `0x140005c20`
- `0x14001da70`
- `0x14002233c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14002239e`
- `KERNEL32!LocalFree` at `0x1400224e5`
- `KERNEL32!LocalFree` at `0x14002239e`
- `KERNEL32!LocalFree` at `0x1400224e5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140022459`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140022459`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1400223c7`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1400223c7`
- `ADVAPI32!CheckTokenMembership` at `0x140022475`
- `ADVAPI32!CheckTokenMembership` at `0x140022475`

## pseudocode

```c
__int64 __fastcall CheckClientIdentity(void *a1, __int64 a2, int *a3)
{
  int v4; // ebx
  unsigned __int64 v6; // rdi
  const WCHAR *v7; // rcx
  unsigned int LastFailure; // eax
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // eax
  HLOCAL hMem; // [rsp+60h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+6Ch] [rbp-14h] BYREF

  IsMember = 0;
  v4 = 0;
  hMem = 0;
  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v6 = 0;
  while ( 1 )
  {
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( (*((_BYTE *)&g_IdentityList + v6) & 0x10) == 0 )
      goto LABEL_22;
    v7 = *(const WCHAR **)((char *)&g_IdentityList + v6 + 8);
    if ( v7 )
    {
      if ( !ConvertStringSidToSidW(v7, &hMem) )
      {
        LastFailure = HrGetLastFailure();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_21aac24f1159385394c7f754eeb9837e_Traceguids,
            LastFailure);
        v4 = 0;
        goto LABEL_22;
      }
      goto LABEL_15;
    }
    if ( *(_DWORD *)((char *)&g_IdentityList + v6) != 1 )
      goto LABEL_22;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &hMem) )
      break;
LABEL_15:
    IsMember = 0;
    if ( CheckTokenMembership(0, hMem, &IsMember) )
    {
      v4 = 0;
    }
    else
    {
      v9 = HrGetLastFailure();
      v4 = v9;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, v9);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v4 < 0 )
      {
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
        {
          v11 = 13;
          v12 = (unsigned int)v4;
LABEL_34:
          WPP_SF_d(v10[2], v11, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids, v12);
          goto LABEL_24;
        }
        goto LABEL_24;
      }
    }
    if ( IsMember )
    {
      v4 = 0;
LABEL_23:
      *a3 = IsMember;
      goto LABEL_24;
    }
LABEL_22:
    v6 += 16LL;
    if ( v6 >= 0xA0 )
      goto LABEL_23;
  }
  v13 = HrGetLastFailure();
  v4 = v13;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 12;
    v12 = v13;
    goto LABEL_34;
  }
LABEL_24:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002233c  mov     [rsp-18h+arg_0], rbx
0x140022341  mov     [rsp-18h+arg_8], rsi
0x140022346  mov     [rsp-18h+arg_18], rdi
0x14002234b  push    rbp
0x14002234c  push    r14
0x14002234e  push    r15
0x140022350  mov     rbp, rsp
0x140022353  sub     rsp, 80h
0x14002235a  mov     rax, cs:__security_cookie
0x140022361  xor     rax, rsp
0x140022364  mov     [rbp+var_8], rax
0x140022368  xor     r14d, r14d
0x14002236b  mov     rsi, r8
0x14002236e  mov     [rbp+IsMember], r14d
0x140022372  mov     ebx, r14d
0x140022375  mov     [rbp+hMem], r14
0x140022379  test    r8, r8
0x14002237c  jnz     short loc_140022388
0x14002237e  mov     eax, 80070057h
0x140022383  jmp     loc_1400224ED
0x140022388  mov     [r8], r14d
0x14002238b  lea     r15, WPP_GLOBAL_Control
0x140022392  mov     rdi, r14
0x140022395  mov     rcx, [rbp+hMem]; hMem
0x140022399  test    rcx, rcx
0x14002239c  jz      short loc_1400223A8
0x14002239e  call    cs:__imp_LocalFree
0x1400223a4  mov     [rbp+hMem], r14
0x1400223a8  lea     rax, ?g_IdentityList@@3PAUtagMPIDENTITY_ITEM@@A; tagMPIDENTITY_ITEM near * g_IdentityList
0x1400223af  test    byte ptr [rdi+rax], 10h
0x1400223b3  jz      loc_1400224C6
0x1400223b9  mov     rcx, [rdi+rax+8]; StringSid
0x1400223be  test    rcx, rcx
0x1400223c1  jz      short loc_14002240C
0x1400223c3  lea     rdx, [rbp+hMem]; Sid
0x1400223c7  call    cs:__imp_ConvertStringSidToSidW
0x1400223cd  test    eax, eax
0x1400223cf  jnz     loc_140022467
0x1400223d5  call    HrGetLastFailure
0x1400223da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400223e1  cmp     rcx, r15
0x1400223e4  jz      short loc_140022404
0x1400223e6  test    byte ptr [rcx+1Ch], 1
0x1400223ea  jz      short loc_140022404
0x1400223ec  mov     rcx, [rcx+10h]
0x1400223f0  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x1400223f7  mov     edx, 0Bh
0x1400223fc  mov     r9d, eax
0x1400223ff  call    WPP_SF_d
0x140022404  mov     ebx, r14d
0x140022407  jmp     loc_1400224C6
0x14002240c  cmp     dword ptr [rdi+rax], 1
0x140022410  jnz     loc_1400224C6
0x140022416  lea     rax, [rbp+hMem]
0x14002241a  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x14002241e  mov     [rsp+80h+pSid], rax; pSid
0x140022423  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x140022427  mov     [rsp+80h+nSubAuthority7], r14d; nSubAuthority7
0x14002242c  mov     r9d, 220h; nSubAuthority1
0x140022432  mov     [rsp+80h+nSubAuthority6], r14d; nSubAuthority6
0x140022437  mov     r8d, 20h ; ' '; nSubAuthority0
0x14002243d  mov     [rsp+80h+nSubAuthority5], r14d; nSubAuthority5
0x140022442  mov     dl, 2; nSubAuthorityCount
0x140022444  mov     [rsp+80h+nSubAuthority4], r14d; nSubAuthority4
0x140022449  mov     [rsp+80h+nSubAuthority3], r14d; nSubAuthority3
0x14002244e  mov     [rsp+80h+nSubAuthority2], r14d; nSubAuthority2
0x140022453  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x140022459  call    cs:__imp_AllocateAndInitializeSid
0x14002245f  test    eax, eax
0x140022461  jz      loc_140022530
0x140022467  mov     rdx, [rbp+hMem]; SidToCheck
0x14002246b  lea     r8, [rbp+IsMember]; IsMember
0x14002246f  xor     ecx, ecx; TokenHandle
0x140022471  mov     [rbp+IsMember], r14d
0x140022475  call    cs:__imp_CheckTokenMembership
0x14002247b  test    eax, eax
0x14002247d  jz      short loc_140022484
0x14002247f  mov     ebx, r14d
0x140022482  jmp     short loc_1400224C0
0x140022484  call    HrGetLastFailure
0x140022489  mov     ebx, eax
0x14002248b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022492  cmp     rcx, r15
0x140022495  jz      short loc_1400224BC
0x140022497  test    byte ptr [rcx+1Ch], 1
0x14002249b  jz      short loc_1400224BC
0x14002249d  mov     rcx, [rcx+10h]
0x1400224a1  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x1400224a8  mov     edx, 0Ah
0x1400224ad  mov     r9d, eax
0x1400224b0  call    WPP_SF_d
0x1400224b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400224bc  test    ebx, ebx
0x1400224be  js      short loc_14002251B
0x1400224c0  cmp     [rbp+IsMember], r14d
0x1400224c4  jnz     short loc_140022516
0x1400224c6  add     rdi, 10h
0x1400224ca  cmp     rdi, 0A0h
0x1400224d1  jb      loc_140022395
0x1400224d7  mov     eax, [rbp+IsMember]
0x1400224da  mov     [rsi], eax
0x1400224dc  mov     rcx, [rbp+hMem]; hMem
0x1400224e0  test    rcx, rcx
0x1400224e3  jz      short loc_1400224EB
0x1400224e5  call    cs:__imp_LocalFree
0x1400224eb  mov     eax, ebx
0x1400224ed  mov     rcx, [rbp+var_8]
0x1400224f1  xor     rcx, rsp; StackCookie
0x1400224f4  call    __security_check_cookie
0x1400224f9  lea     r11, [rsp+80h+var_s0]
0x140022501  mov     rbx, [r11+20h]
0x140022505  mov     rsi, [r11+28h]
0x140022509  mov     rdi, [r11+38h]
0x14002250d  mov     rsp, r11
0x140022510  pop     r15
0x140022512  pop     r14
0x140022514  pop     rbp
0x140022515  retn
0x140022516  mov     ebx, r14d
0x140022519  jmp     short loc_1400224D7
0x14002251b  cmp     rcx, r15
0x14002251e  jz      short loc_1400224DC
0x140022520  test    byte ptr [rcx+1Ch], 1
0x140022524  jz      short loc_1400224DC
0x140022526  mov     edx, 0Dh
0x14002252b  mov     r9d, ebx
0x14002252e  jmp     short loc_140022551
0x140022530  call    HrGetLastFailure
0x140022535  mov     ebx, eax
0x140022537  mov     rcx, cs:WPP_GLOBAL_Control
0x14002253e  cmp     rcx, r15
0x140022541  jz      short loc_1400224DC
0x140022543  test    byte ptr [rcx+1Ch], 1
0x140022547  jz      short loc_1400224DC
0x140022549  mov     edx, 0Ch
0x14002254e  mov     r9d, eax
0x140022551  mov     rcx, [rcx+10h]
0x140022555  lea     r8, WPP_21aac24f1159385394c7f754eeb9837e_Traceguids
0x14002255c  call    WPP_SF_d
0x140022561  jmp     loc_1400224DC
```
