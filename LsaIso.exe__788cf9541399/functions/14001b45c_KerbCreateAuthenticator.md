# KerbCreateAuthenticator

- ea: `0x14001b45c`
- end: `0x14001b769`
- name: `KerbCreateAuthenticator`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x140016ac0`

## callees

- `0x140006720`
- `0x140011964`
- `0x14001a778`
- `0x14001a968`
- `0x14001a9a4`
- `0x14001aa00`
- `0x14001ab60`
- `0x14001b264`
- `0x14001b378`
- `0x14001b45c`
- `0x14001b834`
- `0x14001ea54`
- `0x14001f1d4`
- `0x140038cd2`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001b55f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001b55f`
- `MSASN1!ASN1intx_free` at `0x14001b723`
- `MSASN1!ASN1intx_free` at `0x14001b723`
- `MSASN1!ASN1intx_setuint32` at `0x14001b5c0`
- `MSASN1!ASN1intx_setuint32` at `0x14001b5c0`

## pseudocode

```c
__int64 __fastcall KerbCreateAuthenticator(
        __int64 a1,
        unsigned int a2,
        union _LARGE_INTEGER *a3,
        struct _KERB_INTERNAL_NAME *a4,
        __int64 a5,
        struct _FILETIME *a6,
        __int64 a7,
        __int64 a8,
        __int128 *a9,
        __int64 a10,
        __int64 a11)
{
  void *v13; // rsi
  __int64 v14; // rbx
  unsigned int v15; // edi
  __int16 v16; // r8
  int v17; // eax
  int v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // xmm1_8
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  void *v23; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  struct _KERB_INTERNAL_NAME *v28; // [rsp+60h] [rbp-A0h]
  __int128 v29; // [rsp+68h] [rbp-98h]
  _WORD v30[2]; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+84h] [rbp-7Ch]
  _BYTE v32[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v33[16]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  unsigned __int32 v36; // [rsp+B8h] [rbp-48h]
  _BYTE v37[20]; // [rsp+BCh] [rbp-44h] BYREF
  int v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+D4h] [rbp-2Ch]
  int v40; // [rsp+D8h] [rbp-28h]
  int v41; // [rsp+DCh] [rbp-24h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  _BYTE v43[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]

  v24 = a2;
  v26 = a11;
  v28 = a4;
  memset_0(v30, 0, 0x80u);
  v13 = 0;
  v22 = 0;
  v23 = 0;
  SystemTimeAsFileTime = 0;
  KerberosCryptoPolicy::FromKerberosKey(&v27, a1);
  v14 = v27;
  if ( v27 )
  {
    *(_QWORD *)(v26 + 24) = 0;
    memset_0(v30, 0, 0x80u);
    v31 = 5;
    v15 = KerbConvertUnicodeStringToRealm(v32, a5);
    if ( !v15 )
    {
      v15 = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v33, v28);
      if ( !v15 )
      {
        if ( a6 )
          SystemTimeAsFileTime = a6[1];
        else
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        KerbConvertLargeIntToGeneralizedTime(v37, 0, &SystemTimeAsFileTime);
        v36 = _InterlockedIncrement(&LastuSec) % 0xF4240u;
        if ( a3 )
          KerbConvertGeneralizedTimeToLargeInt(a3);
        v30[0] |= 0x20u;
        ASN1intx_setuint32(v43, v24);
        if ( v44 )
        {
          v16 = v30[0];
          if ( a7 )
          {
            v17 = *(_DWORD *)(a7 + 12);
            v18 = *(_DWORD *)(a7 + 16);
            v16 = v30[0] | 0x40;
            v19 = *(_QWORD *)(a7 + 24);
            v29 = 0;
            v38 = v17;
            v39 = 0;
            v41 = 0;
            v30[0] |= 0x40u;
            v40 = v18;
            v42 = v19;
          }
          if ( a8 )
          {
            v16 |= 0x10u;
            v45 = a8;
            v30[0] = v16;
          }
          if ( a9 )
          {
            v20 = *((_QWORD *)a9 + 2);
            v34 = *a9;
            v30[0] = v16 | 0x80;
            v35 = v20;
          }
          v15 = KerbPackData(v30, 52, &v22, &v23);
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v15);
            v13 = v23;
          }
          else
          {
            v13 = v23;
            v15 = KerberosCryptoPolicy::Encrypt(v14, v26, v22, v23);
            if ( v15 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v15);
          }
        }
        else
        {
          v15 = 60;
        }
      }
    }
    KerbFreePrincipalName(v33);
    KerbFreeRealm(v32);
    if ( v44 )
      ASN1intx_free(v43);
    if ( v13 )
      SafeAllocaFreeToHeap(v13);
  }
  else
  {
    v15 = 60;
  }
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v27);
  return v15;
}

```

## disassembly

```asm
0x14001b45c  mov     [rsp-8+arg_0], rbx
0x14001b461  push    rbp
0x14001b462  push    rsi
0x14001b463  push    rdi
0x14001b464  push    r12
0x14001b466  push    r13
0x14001b468  push    r14
0x14001b46a  push    r15
0x14001b46c  lea     rbp, [rsp-10h]
0x14001b471  sub     rsp, 110h
0x14001b478  mov     rax, cs:__security_cookie
0x14001b47f  xor     rax, rsp
0x14001b482  mov     [rbp+40h+var_40], rax
0x14001b486  mov     rax, [rbp+40h+arg_50]
0x14001b48d  mov     r13, r8
0x14001b490  mov     rdi, [rbp+40h+arg_20]
0x14001b494  mov     rbx, rcx
0x14001b497  mov     r15, [rbp+40h+arg_28]
0x14001b49b  lea     rcx, [rbp+40h+var_C0]; void *
0x14001b49f  mov     r12, [rbp+40h+arg_38]
0x14001b4a6  mov     r8d, 80h; Size
0x14001b4ac  mov     r14, [rbp+40h+arg_40]
0x14001b4b3  mov     [rsp+140h+var_100], edx
0x14001b4b7  xor     edx, edx; Val
0x14001b4b9  mov     [rsp+140h+var_F0], rax
0x14001b4be  mov     [rsp+140h+var_E0], r9
0x14001b4c3  call    memset_0
0x14001b4c8  xor     esi, esi
0x14001b4ca  mov     [rsp+140h+var_110], 0
0x14001b4d2  mov     rdx, rbx
0x14001b4d5  mov     [rsp+140h+var_108], rsi
0x14001b4da  lea     rcx, [rsp+140h+var_E8]
0x14001b4df  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x14001b4e4  call    ?FromKerberosKey@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEAU_KERB_ENCRYPTION_KEY@@_N1W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::FromKerberosKey(_KERB_ENCRYPTION_KEY *,bool,bool,Kerb3961PolicyType)
0x14001b4e9  mov     rbx, [rsp+140h+var_E8]
0x14001b4ee  test    rbx, rbx
0x14001b4f1  jnz     short loc_14001B4FB
0x14001b4f3  lea     edi, [rsi+3Ch]
0x14001b4f6  jmp     loc_14001B736
0x14001b4fb  mov     rax, [rsp+140h+var_F0]
0x14001b500  lea     rcx, [rbp+40h+var_C0]; void *
0x14001b504  xor     edx, edx; Val
0x14001b506  mov     r8d, 80h; Size
0x14001b50c  mov     [rax+18h], rsi
0x14001b510  call    memset_0
0x14001b515  mov     rdx, rdi
0x14001b518  mov     [rbp+40h+var_BC], 5
0x14001b51f  lea     rcx, [rbp+40h+var_B8]
0x14001b523  call    KerbConvertUnicodeStringToRealm
0x14001b528  mov     edi, eax
0x14001b52a  test    eax, eax
0x14001b52c  jnz     loc_14001B706
0x14001b532  mov     rdx, [rsp+140h+var_E0]; struct _KERB_INTERNAL_NAME *
0x14001b537  lea     rcx, [rbp+40h+var_B0]; struct KERB_PRINCIPAL_NAME *
0x14001b53b  call    ?KerbConvertKdcNameToPrincipalName@@YAJPEAUKERB_PRINCIPAL_NAME@@PEAU_KERB_INTERNAL_NAME@@@Z; KerbConvertKdcNameToPrincipalName(KERB_PRINCIPAL_NAME *,_KERB_INTERNAL_NAME *)
0x14001b540  mov     edi, eax
0x14001b542  test    eax, eax
0x14001b544  jnz     loc_14001B706
0x14001b54a  test    r15, r15
0x14001b54d  jz      short loc_14001B55A
0x14001b54f  mov     rax, [r15+8]
0x14001b553  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], rax
0x14001b558  jmp     short loc_14001B565
0x14001b55a  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14001b55f  call    cs:__imp_GetSystemTimeAsFileTime
0x14001b565  lea     r8, [rsp+140h+SystemTimeAsFileTime]
0x14001b56a  xor     edx, edx
0x14001b56c  lea     rcx, [rbp+40h+var_84]
0x14001b570  call    KerbConvertLargeIntToGeneralizedTime
0x14001b575  mov     r15d, 1
0x14001b57b  mov     r8d, r15d
0x14001b57e  lock xadd cs:?LastuSec@@3JC, r8d; long volatile LastuSec
0x14001b587  add     r8d, r15d
0x14001b58a  mov     eax, 431BDE83h
0x14001b58f  mul     r8d
0x14001b592  shr     edx, 12h
0x14001b595  imul    eax, edx, 0F4240h
0x14001b59b  sub     r8d, eax
0x14001b59e  mov     [rbp+40h+var_88], r8d
0x14001b5a2  test    r13, r13
0x14001b5a5  jz      short loc_14001B5B3
0x14001b5a7  lea     rdx, [rbp+40h+var_84]
0x14001b5ab  mov     rcx, r13; Time
0x14001b5ae  call    KerbConvertGeneralizedTimeToLargeInt
0x14001b5b3  mov     edx, [rsp+140h+var_100]
0x14001b5b7  lea     rcx, [rbp+40h+var_58]
0x14001b5bb  or      [rbp+40h+var_C0], 20h
0x14001b5c0  call    cs:__imp_ASN1intx_setuint32
0x14001b5c6  cmp     [rbp+40h+var_50], rsi
0x14001b5ca  jnz     short loc_14001B5D6
0x14001b5cc  mov     edi, 3Ch ; '<'
0x14001b5d1  jmp     loc_14001B706
0x14001b5d6  mov     rdx, [rbp+40h+arg_30]
0x14001b5dd  movzx   r8d, [rbp+40h+var_C0]
0x14001b5e2  test    rdx, rdx
0x14001b5e5  jz      short loc_14001B61B
0x14001b5e7  mov     eax, [rdx+0Ch]
0x14001b5ea  xorps   xmm0, xmm0
0x14001b5ed  mov     ecx, [rdx+10h]
0x14001b5f0  or      r8w, 40h
0x14001b5f5  mov     rdx, [rdx+18h]
0x14001b5f9  movups  [rsp+140h+var_D8], xmm0
0x14001b5fe  mov     [rbp+40h+var_70], eax
0x14001b601  mov     eax, dword ptr [rsp+140h+var_D8+4]
0x14001b605  mov     [rbp+40h+var_6C], eax
0x14001b608  mov     eax, dword ptr [rsp+140h+var_D8+0Ch]
0x14001b60c  mov     [rbp+40h+var_64], eax
0x14001b60f  mov     [rbp+40h+var_C0], r8w
0x14001b614  mov     [rbp+40h+var_68], ecx
0x14001b617  mov     [rbp+40h+var_60], rdx
0x14001b61b  test    r12, r12
0x14001b61e  jz      short loc_14001B62E
0x14001b620  or      r8w, 10h
0x14001b625  mov     [rbp+40h+var_48], r12
0x14001b629  mov     [rbp+40h+var_C0], r8w
0x14001b62e  test    r14, r14
0x14001b631  jz      short loc_14001B654
0x14001b633  movups  xmm0, xmmword ptr [r14]
0x14001b637  mov     eax, 80h
0x14001b63c  movsd   xmm1, qword ptr [r14+10h]
0x14001b642  or      r8w, ax
0x14001b646  movaps  [rbp+40h+var_A0], xmm0
0x14001b64a  mov     [rbp+40h+var_C0], r8w
0x14001b64f  movsd   [rbp+40h+var_90], xmm1
0x14001b654  lea     r9, [rsp+140h+var_108]
0x14001b659  mov     edx, 34h ; '4'
0x14001b65e  lea     r8, [rsp+140h+var_110]
0x14001b663  lea     rcx, [rbp+40h+var_C0]
0x14001b667  call    KerbPackData
0x14001b66c  mov     edi, eax
0x14001b66e  test    eax, eax
0x14001b670  jz      short loc_14001B6AA
0x14001b672  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b679  lea     rax, WPP_GLOBAL_Control
0x14001b680  cmp     rcx, rax
0x14001b683  jz      short loc_14001B6A3
0x14001b685  test    [rcx+1Ch], r15b
0x14001b689  jz      short loc_14001B6A3
0x14001b68b  mov     rcx, [rcx+10h]
0x14001b68f  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x14001b696  mov     edx, 1Eh
0x14001b69b  mov     r9d, edi
0x14001b69e  call    WPP_SF_d
0x14001b6a3  mov     rsi, [rsp+140h+var_108]
0x14001b6a8  jmp     short loc_14001B706
0x14001b6aa  mov     eax, [rbp+40h+arg_48]
0x14001b6b0  mov     rcx, rbx
0x14001b6b3  mov     rsi, [rsp+140h+var_108]
0x14001b6b8  mov     r8d, [rsp+140h+var_110]
0x14001b6bd  mov     r9, rsi
0x14001b6c0  mov     rdx, [rsp+140h+var_F0]
0x14001b6c5  mov     [rsp+140h+var_118], rax
0x14001b6ca  call    ?Encrypt@KerberosCryptoPolicy@@QEAAJPEAUKERB_ENCRYPTED_DATA@@KPEAEKW4KeyUsage@Kerb3961@@@Z; KerberosCryptoPolicy::Encrypt(KERB_ENCRYPTED_DATA *,ulong,uchar *,ulong,Kerb3961::KeyUsage)
0x14001b6cf  mov     edi, eax
0x14001b6d1  test    eax, eax
0x14001b6d3  jz      short loc_14001B706
0x14001b6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6dc  lea     rax, WPP_GLOBAL_Control
0x14001b6e3  cmp     rcx, rax
0x14001b6e6  jz      short loc_14001B706
0x14001b6e8  test    [rcx+1Ch], r15b
0x14001b6ec  jz      short loc_14001B706
0x14001b6ee  mov     rcx, [rcx+10h]
0x14001b6f2  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x14001b6f9  mov     edx, 1Fh
0x14001b6fe  mov     r9d, edi
0x14001b701  call    WPP_SF_d
0x14001b706  lea     rcx, [rbp+40h+var_B0]
0x14001b70a  call    KerbFreePrincipalName
0x14001b70f  lea     rcx, [rbp+40h+var_B8]
0x14001b713  call    KerbFreeRealm
0x14001b718  cmp     [rbp+40h+var_50], 0
0x14001b71d  jz      short loc_14001B729
0x14001b71f  lea     rcx, [rbp+40h+var_58]
0x14001b723  call    cs:__imp_ASN1intx_free
0x14001b729  test    rsi, rsi
0x14001b72c  jz      short loc_14001B736
0x14001b72e  mov     rcx, rsi; void *
0x14001b731  call    SafeAllocaFreeToHeap
0x14001b736  lea     rcx, [rsp+140h+var_E8]
0x14001b73b  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x14001b740  mov     eax, edi
0x14001b742  mov     rcx, [rbp+40h+var_40]
0x14001b746  xor     rcx, rsp; StackCookie
0x14001b749  call    __security_check_cookie
0x14001b74e  mov     rbx, [rsp+140h+arg_0]
0x14001b756  add     rsp, 110h
0x14001b75d  pop     r15
0x14001b75f  pop     r14
0x14001b761  pop     r13
0x14001b763  pop     r12
0x14001b765  pop     rdi
0x14001b766  pop     rsi
0x14001b767  pop     rbp
0x14001b768  retn
```
