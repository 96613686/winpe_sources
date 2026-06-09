# R_ZtHelperPromoteConfig

- ea: `0x180002650`
- end: `0x18000272b`
- name: `R_ZtHelperPromoteConfig`
- size: `219`
- prototype: `__int64 __fastcall(__int64, struct _DNS_ZT_SETTINGS_STATE *, enum _DNS_ZT_PROMOTE_RESULT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002650`
- `0x1800044e4`
- `0x18000f1cc`
- `0x180015008`
- `0x180015094`

## pseudocode

```c
__int64 __fastcall R_ZtHelperPromoteConfig(
        __int64 a1,
        struct _DNS_ZT_SETTINGS_STATE *a2,
        enum _DNS_ZT_PROMOTE_RESULT *a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r9

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 27, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids, a2);
  if ( !a2 )
  {
    v5 = 87;
    goto LABEL_16;
  }
  if ( g_fVelocityZtdns )
  {
    v6 = Rpc_DnsRegistryAccessCheck(0x20019u);
    v5 = v6;
    if ( v6 )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        return v5;
      v7 = 29;
    }
    else
    {
      v6 = ZtHelperPromoteConfig(a2, a3);
      v5 = v6;
      if ( !v6 )
        goto LABEL_16;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v5;
      v7 = 30;
    }
    v8 = v6;
  }
  else
  {
    v5 = 50;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v5;
    v7 = 28;
    v8 = 50;
  }
  WPP_SF_d(1026, v7, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids, v8);
LABEL_16:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 31, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180002650  push    rbx
0x180002652  push    rsi
0x180002653  push    rdi
0x180002654  push    r14
0x180002656  push    r15
0x180002658  sub     rsp, 20h
0x18000265c  mov     rsi, r8
0x18000265f  mov     rdi, rdx
0x180002662  test    byte ptr cs:xmmword_18001F260, 4
0x180002669  lea     r15, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids
0x180002670  mov     r14d, 402h
0x180002676  jz      short loc_18000268B
0x180002678  mov     edx, 1Bh
0x18000267d  mov     ecx, r14d
0x180002680  mov     r9, rdi
0x180002683  mov     r8, r15
0x180002686  call    WPP_SF_q
0x18000268b  test    rdi, rdi
0x18000268e  jnz     short loc_180002695
0x180002690  lea     ebx, [rdi+57h]
0x180002693  jmp     short loc_180002701
0x180002695  cmp     cs:g_fVelocityZtdns, 0
0x18000269c  jz      short loc_1800026E2
0x18000269e  mov     ecx, 20019h; DesiredAccess
0x1800026a3  call    Rpc_DnsRegistryAccessCheck
0x1800026a8  mov     ebx, eax
0x1800026aa  test    eax, eax
0x1800026ac  jnz     short loc_1800026D2
0x1800026ae  mov     rdx, rsi; enum _DNS_ZT_PROMOTE_RESULT *
0x1800026b1  mov     rcx, rdi; struct _DNS_ZT_SETTINGS_STATE *
0x1800026b4  call    ?ZtHelperPromoteConfig@@YAJPEAU_DNS_ZT_SETTINGS_STATE@@PEAW4_DNS_ZT_PROMOTE_RESULT@@@Z; ZtHelperPromoteConfig(_DNS_ZT_SETTINGS_STATE *,_DNS_ZT_PROMOTE_RESULT *)
0x1800026b9  mov     ebx, eax
0x1800026bb  test    eax, eax
0x1800026bd  jz      short loc_180002701
0x1800026bf  test    byte ptr cs:xmmword_18001F260, 4
0x1800026c6  jz      short loc_18000271D
0x1800026c8  mov     edx, 1Eh
0x1800026cd  mov     r9d, eax
0x1800026d0  jmp     short loc_1800026F6
0x1800026d2  test    byte ptr cs:xmmword_18001F260, 4
0x1800026d9  jz      short loc_18000271D
0x1800026db  mov     edx, 1Dh
0x1800026e0  jmp     short loc_1800026CD
0x1800026e2  mov     ebx, 32h ; '2'
0x1800026e7  test    byte ptr cs:xmmword_18001F260, 4
0x1800026ee  jz      short loc_18000271D
0x1800026f0  lea     edx, [rbx-16h]
0x1800026f3  mov     r9d, ebx
0x1800026f6  mov     r8, r15
0x1800026f9  mov     ecx, r14d
0x1800026fc  call    WPP_SF_d
0x180002701  test    byte ptr cs:xmmword_18001F260, 4
0x180002708  jz      short loc_18000271D
0x18000270a  mov     edx, 1Fh
0x18000270f  mov     ecx, r14d
0x180002712  mov     r9d, ebx
0x180002715  mov     r8, r15
0x180002718  call    WPP_SF_d
0x18000271d  mov     eax, ebx
0x18000271f  add     rsp, 20h
0x180002723  pop     r15
0x180002725  pop     r14
0x180002727  pop     rdi
0x180002728  pop     rsi
0x180002729  pop     rbx
0x18000272a  retn
```
