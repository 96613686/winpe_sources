# KerbBuildPkinitReplyKeyCommon(long (*)(void *,ushort const *,_BCryptBufferDesc *,uchar *,ulong,ulong *,ulong),void *,ulong,ulong,uchar *,ulong,uchar *,_KERB_ENCRYPTION_KEY *)

- ea: `0x14001bfa8`
- end: `0x14001c18c`
- name: `?KerbBuildPkinitReplyKeyCommon@@YAJP6AJPEAXPEBGPEAU_BCryptBufferDesc@@PEAEKPEAKK@Z0KK3K3PEAU_KERB_ENCRYPTION_KEY@@@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(int (*)(void *, const unsigned __int16 *, struct _BCryptBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int8 *, unsigned int, unsigned __int8 *, struct _KERB_ENCRYPTION_KEY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001d728`

## callees

- `0x140011964`
- `0x14001aa94`
- `0x14001aaf0`
- `0x14001ab60`
- `0x14001bf88`
- `0x14001bfa8`
- `0x14001cd38`
- `0x14001e8dc`
- `0x14001eaf4`
- `0x14003a010`

## pseudocode

```c
__int64 __fastcall KerbBuildPkinitReplyKeyCommon(
        int (*a1)(void *, const unsigned __int16 *, struct _BCryptBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int),
        void *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        struct _KERB_ENCRYPTION_KEY *a8)
{
  KerberosCryptoPolicy *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rsi
  unsigned int v15; // edi
  __int64 v16; // r14
  unsigned __int8 *v17; // rbx
  __int64 v18; // rax
  size_t Size; // [rsp+30h] [rbp-51h]
  unsigned __int8 *v21; // [rsp+40h] [rbp-41h] BYREF
  KerberosCryptoPolicy *v22; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-31h] BYREF
  __int64 v24; // [rsp+60h] [rbp-21h] BYREF
  __int64 v25; // [rsp+68h] [rbp-19h]
  int v26; // [rsp+70h] [rbp-11h]

  KerberosCryptoPolicy::Create(&v22);
  v12 = v22;
  if ( !v22 )
    goto LABEL_6;
  *((_BYTE *)v22 + 8) = 1;
  v13 = KerberosCryptoPolicy::OpenEncryptionAlgorithm(v12, a3, 0x100000003LL);
  v14 = v13;
  if ( !v13 )
  {
    v15 = 14;
    goto LABEL_18;
  }
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 112LL))(v13);
  utl::make_unique<unsigned char [0],0>(&v21, v16);
  v17 = v21;
  if ( !v21 )
  {
LABEL_5:
    utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(&v21);
LABEL_6:
    v15 = 60;
    goto LABEL_18;
  }
  LODWORD(Size) = v16;
  v15 = KerbDerivePkinitReplySeed(a1, a2, a4, a5, a6, a7, Size, v21);
  if ( !v15 )
  {
    v18 = *(_QWORD *)v14;
    v23[0] = v16;
    v23[1] = v17;
    (*(void (__fastcall **)(__int64, __int64 *, _QWORD *))(v18 + 128))(v14, &v24, v23);
    if ( v26 >= 0 )
    {
      *((_DWORD *)a8 + 3) = a3;
      *((_DWORD *)a8 + 2) = 1;
      *(_QWORD *)a8 = 0;
      *((_DWORD *)a8 + 4) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 120LL))(v14);
      *((_QWORD *)a8 + 3) = v25;
      v25 = 0;
      v24 = 0;
      v26 = -1073741823;
      Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v24);
      utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(&v21);
      v15 = 0;
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids,
        (unsigned int)v26);
    Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v24);
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids, v15);
  utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(&v21);
LABEL_18:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v22);
  return v15;
}

```

## disassembly

```asm
0x14001bfa8  push    rbp
0x14001bfaa  push    rbx
0x14001bfab  push    rsi
0x14001bfac  push    rdi
0x14001bfad  push    r12
0x14001bfaf  push    r13
0x14001bfb1  push    r14
0x14001bfb3  push    r15
0x14001bfb5  lea     rbp, [rsp-7]
0x14001bfba  sub     rsp, 88h
0x14001bfc1  mov     r13, rcx
0x14001bfc4  mov     edi, r9d
0x14001bfc7  lea     rcx, [rbp+3Fh+var_78]
0x14001bfcb  mov     r15d, r8d
0x14001bfce  mov     r12, rdx
0x14001bfd1  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x14001bfd6  mov     rcx, [rbp+3Fh+var_78]
0x14001bfda  test    rcx, rcx
0x14001bfdd  jz      short loc_14001C035
0x14001bfdf  mov     r8, 100000003h
0x14001bfe9  mov     byte ptr [rcx+8], 1
0x14001bfed  mov     edx, r15d
0x14001bff0  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x14001bff5  mov     rsi, rax
0x14001bff8  test    rax, rax
0x14001bffb  jnz     short loc_14001C005
0x14001bffd  lea     edi, [rax+0Eh]
0x14001c000  jmp     loc_14001C16D
0x14001c005  mov     rax, [rax]
0x14001c008  mov     rcx, rsi
0x14001c00b  mov     rax, [rax+70h]
0x14001c00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c014  mov     rdx, rax
0x14001c017  lea     rcx, [rbp+3Fh+var_80]
0x14001c01b  mov     r14, rax
0x14001c01e  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x14001c023  mov     rbx, [rbp+3Fh+var_80]
0x14001c027  test    rbx, rbx
0x14001c02a  jnz     short loc_14001C03F
0x14001c02c  lea     rcx, [rbp+3Fh+var_80]
0x14001c030  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)
0x14001c035  mov     edi, 3Ch ; '<'
0x14001c03a  jmp     loc_14001C16D
0x14001c03f  mov     rax, [rbp+3Fh+arg_30]
0x14001c043  mov     r8d, edi; unsigned int
0x14001c046  mov     r9, [rbp+3Fh+arg_20]; unsigned __int8 *
0x14001c04a  mov     rdx, r12; void *
0x14001c04d  mov     [rsp+0C0h+var_88], rbx; unsigned __int8 *
0x14001c052  mov     rcx, r13; int (*)(void *, const unsigned __int16 *, struct _BCryptBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)
0x14001c055  mov     dword ptr [rsp+0C0h+Size], r14d; Size
0x14001c05a  mov     [rsp+0C0h+var_98], rax; unsigned __int8 *
0x14001c05f  mov     eax, [rbp+3Fh+arg_28]
0x14001c062  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x14001c066  call    ?KerbDerivePkinitReplySeed@@YAJP6AJPEAXPEBGPEAU_BCryptBufferDesc@@PEAEKPEAKK@Z0K3K3K3@Z; KerbDerivePkinitReplySeed(long (*)(void *,ushort const *,_BCryptBufferDesc *,uchar *,ulong,ulong *,ulong),void *,ulong,uchar *,ulong,uchar *,ulong,uchar *)
0x14001c06b  xor     r12d, r12d
0x14001c06e  mov     edi, eax
0x14001c070  test    eax, eax
0x14001c072  jz      short loc_14001C0B3
0x14001c074  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c07b  lea     rax, WPP_GLOBAL_Control
0x14001c082  cmp     rcx, rax
0x14001c085  jz      short loc_14001C0A5
0x14001c087  test    byte ptr [rcx+1Ch], 1
0x14001c08b  jz      short loc_14001C0A5
0x14001c08d  mov     rcx, [rcx+10h]
0x14001c091  lea     edx, [r12+0Dh]
0x14001c096  mov     r9d, edi
0x14001c099  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x14001c0a0  call    WPP_SF_d
0x14001c0a5  lea     rcx, [rbp+3Fh+var_80]
0x14001c0a9  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)
0x14001c0ae  jmp     loc_14001C16D
0x14001c0b3  mov     rax, [rsi]
0x14001c0b6  lea     r8, [rbp+3Fh+var_70]
0x14001c0ba  lea     rdx, [rbp+3Fh+var_60]
0x14001c0be  mov     [rbp+3Fh+var_70], r14
0x14001c0c2  mov     rcx, rsi
0x14001c0c5  mov     [rbp+3Fh+var_68], rbx
0x14001c0c9  mov     rax, [rax+80h]
0x14001c0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c0d5  mov     r9d, [rbp+3Fh+var_50]
0x14001c0d9  test    r9d, r9d
0x14001c0dc  jns     short loc_14001C11A
0x14001c0de  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c0e5  lea     rax, WPP_GLOBAL_Control
0x14001c0ec  cmp     rcx, rax
0x14001c0ef  jz      short loc_14001C10C
0x14001c0f1  test    byte ptr [rcx+1Ch], 1
0x14001c0f5  jz      short loc_14001C10C
0x14001c0f7  mov     rcx, [rcx+10h]
0x14001c0fb  lea     r8, WPP_b70a4a8a1f343610d5d6878394a5537d_Traceguids
0x14001c102  mov     edx, 0Eh
0x14001c107  call    WPP_SF_d
0x14001c10c  lea     rcx, [rbp+3Fh+var_60]; this
0x14001c110  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x14001c115  jmp     loc_14001C02C
0x14001c11a  mov     rbx, [rbp+3Fh+arg_38]
0x14001c121  mov     rcx, rsi
0x14001c124  mov     [rbx+0Ch], r15d
0x14001c128  mov     dword ptr [rbx+8], 1
0x14001c12f  mov     [rbx], r12
0x14001c132  mov     rax, [rsi]
0x14001c135  mov     rax, [rax+78h]
0x14001c139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c13e  mov     [rbx+10h], eax
0x14001c141  lea     rcx, [rbp+3Fh+var_60]; this
0x14001c145  mov     rax, [rbp+3Fh+var_58]
0x14001c149  mov     [rbx+18h], rax
0x14001c14d  mov     [rbp+3Fh+var_58], r12
0x14001c151  mov     [rbp+3Fh+var_60], r12
0x14001c155  mov     [rbp+3Fh+var_50], 0C0000001h
0x14001c15c  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x14001c161  lea     rcx, [rbp+3Fh+var_80]
0x14001c165  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)
0x14001c16a  mov     edi, r12d
0x14001c16d  lea     rcx, [rbp+3Fh+var_78]
0x14001c171  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x14001c176  mov     eax, edi
0x14001c178  add     rsp, 88h
0x14001c17f  pop     r15
0x14001c181  pop     r14
0x14001c183  pop     r13
0x14001c185  pop     r12
0x14001c187  pop     rdi
0x14001c188  pop     rsi
0x14001c189  pop     rbx
0x14001c18a  pop     rbp
0x14001c18b  retn
```
