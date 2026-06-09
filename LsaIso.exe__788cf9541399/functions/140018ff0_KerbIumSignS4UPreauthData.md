# KerbIumSignS4UPreauthData

- ea: `0x140018ff0`
- end: `0x14001920a`
- name: `KerbIumSignS4UPreauthData`
- size: `538`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callees

- `0x140004ca8`
- `0x14001212c`
- `0x14001431c`
- `0x14001449c`
- `0x140014f38`
- `0x140018ff0`
- `0x14001ab60`
- `0x14001b094`
- `0x14001b770`
- `0x14001ea54`
- `0x140038cd2`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001904d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14001904d`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x14001910a`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x14001910a`

## string_xrefs

- `0x14001907b`: `KerbIumSignS4UPreauthData`
- `0x1400191cf`: `KerbIumSignS4UPreauthData`

## pseudocode

```c
__int64 __fastcall KerbIumSignS4UPreauthData(
        __int64 a1,
        struct _KERB_ENCRYPTION_KEY *a2,
        int a3,
        const struct _KERB_ASN1_DATA *a4,
        int *a5,
        _DWORD *a6,
        _QWORD *a7)
{
  int v11; // ebx
  PVOID *v12; // r10
  int *v13; // rdi
  _DWORD *v14; // rsi
  _QWORD *v15; // r14
  unsigned __int8 v16; // r8
  struct KerberosCryptoPolicy *v18[2]; // [rsp+30h] [rbp-B1h] BYREF
  _BYTE v19[18]; // [rsp+40h] [rbp-A1h] BYREF
  __int128 v20; // [rsp+52h] [rbp-8Fh]
  _BYTE v21[30]; // [rsp+62h] [rbp-7Fh]
  int v22; // [rsp+80h] [rbp-61h]
  int v23; // [rsp+88h] [rbp-59h]
  __int64 v24; // [rsp+90h] [rbp-51h]
  _BYTE v25[128]; // [rsp+A0h] [rbp-41h] BYREF
  _OWORD *v26; // [rsp+130h] [rbp+4Fh] BYREF

  v26 = 0;
  *(_DWORD *)v19 = 0;
  memset_0(&v19[4], 0, 0x54u);
  KerbIumClearKey::KerbIumClearKey((KerbIumClearKey *)v25, a2);
  if ( qword_140052C40 != a1 )
  {
    Sleep(5u);
    v11 = -1073741790;
    goto LABEL_30;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbIumSignS4UPreauthData");
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( !a4 )
    {
      v11 = -1073741583;
      goto LABEL_24;
    }
    v13 = a5;
    if ( !a5 )
    {
      v11 = -1073741582;
      goto LABEL_24;
    }
    v14 = a6;
    if ( !a6 )
    {
      v11 = -1073741581;
      goto LABEL_24;
    }
    v15 = a7;
    if ( !a7 )
    {
      v11 = -1073741580;
      goto LABEL_24;
    }
    if ( (int)KerbIumClearKey::Status((KerbIumClearKey *)v25) >= 0 )
    {
      v11 = KerbClientUnpackAsn1BufferVoid(a4, 0x24u, (void **)&v26);
      if ( v11 >= 0 )
      {
        v22 = *v13;
        *(_WORD *)v19 = *(_WORD *)v26;
        *(_OWORD *)&v19[2] = *(_OWORD *)((char *)v26 + 2);
        v20 = *(_OWORD *)((char *)v26 + 18);
        *(_OWORD *)v21 = *(_OWORD *)((char *)v26 + 34);
        *(_OWORD *)&v21[14] = v26[3];
        KerberosCryptoPolicy::FromKerberosKey(v18, v25);
        v11 = v18[0] ? KerbSignS4UPreauthDataEx(v18[0], a3, v16, (struct PA_S4U_X509_USER *)v19) : -1073741670;
        utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v18);
        if ( v11 >= 0 )
        {
          *v13 = v22;
          *v15 = v24;
          *v14 = v23;
        }
      }
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_24;
    }
  }
  v11 = -1073741585;
LABEL_24:
  if ( v26 )
  {
    KerbFreeData(36);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 < 0 && v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_sd(
      (unsigned int)v12[2],
      42,
      (unsigned int)WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      (unsigned int)"KerbIumSignS4UPreauthData",
      v11);
LABEL_30:
  KerbIumClearKey::~KerbIumClearKey((KerbIumClearKey *)v25);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140018ff0  push    rbp
0x140018ff2  push    rbx
0x140018ff3  push    rsi
0x140018ff4  push    rdi
0x140018ff5  push    r12
0x140018ff7  push    r13
0x140018ff9  push    r14
0x140018ffb  push    r15
0x140018ffd  lea     rbp, [rsp-7]
0x140019002  sub     rsp, 0E8h
0x140019009  xor     eax, eax
0x14001900b  mov     [rbp+3Fh+arg_0], 0
0x140019013  mov     r12d, r8d
0x140019016  mov     dword ptr [rsp+120h+var_E0], eax
0x14001901a  mov     rdi, rdx
0x14001901d  mov     rbx, rcx
0x140019020  xor     edx, edx; Val
0x140019022  lea     rcx, [rsp+120h+var_E0+4]; void *
0x140019027  lea     r8d, [rax+54h]; Size
0x14001902b  mov     r15, r9
0x14001902e  call    memset_0
0x140019033  mov     rdx, rdi; struct _KERB_ENCRYPTION_KEY *
0x140019036  lea     rcx, [rbp+3Fh+var_80]; this
0x14001903a  call    ??0KerbIumClearKey@@QEAA@PEAU_KERB_ENCRYPTION_KEY@@@Z; KerbIumClearKey::KerbIumClearKey(_KERB_ENCRYPTION_KEY *)
0x14001903f  cmp     cs:qword_140052C40, rbx
0x140019046  jz      short loc_14001905D
0x140019048  mov     ecx, 5; dwMilliseconds
0x14001904d  call    cs:__imp_Sleep
0x140019053  mov     ebx, 0C0000022h
0x140019058  jmp     loc_1400191EB
0x14001905d  mov     r10, cs:WPP_GLOBAL_Control
0x140019064  lea     r13, WPP_GLOBAL_Control
0x14001906b  cmp     r10, r13
0x14001906e  jz      short loc_14001909A
0x140019070  test    byte ptr [r10+1Ch], 4
0x140019075  jz      short loc_14001909A
0x140019077  mov     rcx, [r10+10h]
0x14001907b  lea     r9, aKerbiumsigns4u; "KerbIumSignS4UPreauthData"
0x140019082  mov     edx, 29h ; ')'
0x140019087  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x14001908e  call    WPP_SF_s
0x140019093  mov     r10, cs:WPP_GLOBAL_Control
0x14001909a  test    rdi, rdi
0x14001909d  jnz     short loc_1400190A9
0x14001909f  mov     ebx, 0C00000EFh
0x1400190a4  jmp     loc_1400191A1
0x1400190a9  test    r15, r15
0x1400190ac  jnz     short loc_1400190B8
0x1400190ae  mov     ebx, 0C00000F1h
0x1400190b3  jmp     loc_1400191A1
0x1400190b8  mov     rdi, [rbp+3Fh+arg_20]
0x1400190bc  test    rdi, rdi
0x1400190bf  jnz     short loc_1400190CB
0x1400190c1  mov     ebx, 0C00000F2h
0x1400190c6  jmp     loc_1400191A1
0x1400190cb  mov     rsi, [rbp+3Fh+arg_28]
0x1400190cf  test    rsi, rsi
0x1400190d2  jnz     short loc_1400190DE
0x1400190d4  mov     ebx, 0C00000F3h
0x1400190d9  jmp     loc_1400191A1
0x1400190de  mov     r14, [rbp+3Fh+arg_30]
0x1400190e2  test    r14, r14
0x1400190e5  jnz     short loc_1400190F1
0x1400190e7  mov     ebx, 0C00000F4h
0x1400190ec  jmp     loc_1400191A1
0x1400190f1  lea     rcx, [rbp+3Fh+var_80]; this
0x1400190f5  call    ?Status@KerbIumClearKey@@QEBAJXZ; KerbIumClearKey::Status(void)
0x1400190fa  test    eax, eax
0x1400190fc  js      short loc_14001909F
0x1400190fe  lea     r8, [rbp+3Fh+arg_0]
0x140019102  mov     edx, 24h ; '$'
0x140019107  mov     rcx, r15
0x14001910a  call    cs:__imp_?KerbClientUnpackAsn1BufferVoid@@YAJAEBU_KERB_ASN1_DATA@@KPEAPEAX@Z; KerbClientUnpackAsn1BufferVoid(_KERB_ASN1_DATA const &,ulong,void * *)
0x140019110  mov     ebx, eax
0x140019112  test    eax, eax
0x140019114  js      loc_14001919A
0x14001911a  mov     rcx, [rbp+3Fh+arg_0]
0x14001911e  lea     rdx, [rbp+3Fh+var_80]
0x140019122  mov     eax, [rdi]
0x140019124  mov     [rbp+3Fh+var_A0], eax
0x140019127  movzx   eax, word ptr [rcx]
0x14001912a  mov     word ptr [rsp+120h+var_E0], ax
0x14001912f  movups  xmm0, xmmword ptr [rcx+2]
0x140019133  movups  xmmword ptr [rsp+120h+var_E0+2], xmm0
0x140019138  movups  xmm1, xmmword ptr [rcx+12h]
0x14001913c  movups  [rsp+120h+var_CE], xmm1
0x140019141  movups  xmm0, xmmword ptr [rcx+22h]
0x140019145  movups  xmmword ptr [rbp+3Fh+var_BE], xmm0
0x140019149  movups  xmm1, xmmword ptr [rcx+30h]
0x14001914d  lea     rcx, [rsp+120h+var_F0]
0x140019152  movups  xmmword ptr [rbp+3Fh+var_BE+0Eh], xmm1
0x140019156  call    ?FromKerberosKey@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEAU_KERB_ENCRYPTION_KEY@@_N1W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::FromKerberosKey(_KERB_ENCRYPTION_KEY *,bool,bool,Kerb3961PolicyType)
0x14001915b  mov     rcx, [rsp+120h+var_F0]; struct KerberosCryptoPolicy *
0x140019160  test    rcx, rcx
0x140019163  jnz     short loc_14001916C
0x140019165  mov     ebx, 0C000009Ah
0x14001916a  jmp     short loc_14001917B
0x14001916c  lea     r9, [rsp+120h+var_E0]; struct PA_S4U_X509_USER *
0x140019171  mov     edx, r12d; int
0x140019174  call    ?KerbSignS4UPreauthDataEx@@YAJPEAVKerberosCryptoPolicy@@HEPEAUPA_S4U_X509_USER@@@Z; KerbSignS4UPreauthDataEx(KerberosCryptoPolicy *,int,uchar,PA_S4U_X509_USER *)
0x140019179  mov     ebx, eax
0x14001917b  lea     rcx, [rsp+120h+var_F0]
0x140019180  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x140019185  test    ebx, ebx
0x140019187  js      short loc_14001919A
0x140019189  mov     eax, [rbp+3Fh+var_A0]
0x14001918c  mov     [rdi], eax
0x14001918e  mov     rax, [rbp+3Fh+var_90]
0x140019192  mov     [r14], rax
0x140019195  mov     eax, [rbp+3Fh+var_98]
0x140019198  mov     [rsi], eax
0x14001919a  mov     r10, cs:WPP_GLOBAL_Control
0x1400191a1  mov     rdx, [rbp+3Fh+arg_0]
0x1400191a5  test    rdx, rdx
0x1400191a8  jz      short loc_1400191BB
0x1400191aa  mov     ecx, 24h ; '$'
0x1400191af  call    KerbFreeData
0x1400191b4  mov     r10, cs:WPP_GLOBAL_Control
0x1400191bb  test    ebx, ebx
0x1400191bd  jns     short loc_1400191EB
0x1400191bf  cmp     r10, r13
0x1400191c2  jz      short loc_1400191EB
0x1400191c4  test    byte ptr [r10+1Ch], 1
0x1400191c9  jz      short loc_1400191EB
0x1400191cb  mov     rcx, [r10+10h]
0x1400191cf  lea     r9, aKerbiumsigns4u; "KerbIumSignS4UPreauthData"
0x1400191d6  mov     edx, 2Ah ; '*'
0x1400191db  mov     [rsp+120h+var_100], ebx
0x1400191df  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x1400191e6  call    WPP_SF_sd
0x1400191eb  lea     rcx, [rbp+3Fh+var_80]; this
0x1400191ef  call    ??1KerbIumClearKey@@QEAA@XZ; KerbIumClearKey::~KerbIumClearKey(void)
0x1400191f4  mov     eax, ebx
0x1400191f6  add     rsp, 0E8h
0x1400191fd  pop     r15
0x1400191ff  pop     r14
0x140019201  pop     r13
0x140019203  pop     r12
0x140019205  pop     rdi
0x140019206  pop     rsi
0x140019207  pop     rbx
0x140019208  pop     rbp
0x140019209  retn
```
