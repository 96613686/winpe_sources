# MFCheckProcessCapabilities

- ea: `0x180056220`
- end: `0x18005657e`
- name: `MFCheckProcessCapabilities`
- size: `862`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a100`

## callees

- `0x180005fa0`
- `0x18000c94c`
- `0x180015e80`
- `0x1800441c4`
- `0x180044b1c`
- `0x180044b28`
- `0x180050bc8`
- `0x180050d7c`
- `0x1800512a8`
- `0x180051850`
- `0x180056220`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800563e7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800563e7`
- `ntdll!RtlCapabilityCheck` at `0x180056429`
- `ntdll!RtlCapabilityCheck` at `0x180056429`
- `ntdll!RtlInitUnicodeString` at `0x180056419`
- `ntdll!RtlInitUnicodeString` at `0x180056419`

## pseudocode

```c
__int64 __fastcall MFCheckProcessCapabilities(void *a1, const unsigned __int16 *a2, unsigned int a3, _DWORD *a4)
{
  unsigned int v4; // r12d
  unsigned __int64 v5; // rsi
  _DWORD *v6; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // r14
  int v13; // eax
  __int64 v14; // rdx
  char v15; // si
  int TokenCapabilities; // eax
  bool v17; // al
  int v18; // r14d
  const char *v19; // rax
  void *Block; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-48h]
  PSID pSid1; // [rsp+40h] [rbp-40h] BYREF
  char v24; // [rsp+48h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  void *v26; // [rsp+60h] [rbp-20h]
  unsigned int v27; // [rsp+68h] [rbp-18h]
  __int64 v28; // [rsp+6Ch] [rbp-14h]
  char v30; // [rsp+D0h] [rbp+50h] BYREF

  v4 = 0;
  v5 = a3;
  v26 = 0;
  v6 = 0;
  v28 = 0;
  v27 = 0;
  Block = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      54,
      (unsigned int)&WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
      (_DWORD)a1,
      (__int64)a2);
  if ( !(_DWORD)v5 || !a2 )
  {
    v9 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_50;
    v10 = 55;
    goto LABEL_49;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_50;
    v10 = 56;
LABEL_49:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v9);
    goto LABEL_50;
  }
  *a4 = 0;
  v11 = (unsigned __int16 *)operator new[](saturated_mul(v5, 2u));
  v22 = v11;
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_50;
    v10 = 57;
    goto LABEL_49;
  }
  v13 = StringCchCopyW(v11, v5, a2);
  v9 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_46;
    v14 = 58;
    goto LABEL_14;
  }
  v13 = ProcessCapabilityList(v12);
  v9 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_46;
    v14 = 59;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v13);
    goto LABEL_46;
  }
  v15 = 1;
  while ( 1 )
  {
    if ( v4 >= v27 )
      goto LABEL_39;
    pSid1 = 0;
    v24 = 0;
    if ( IsStringSid(*((LPCWSTR *)v26 + v4), &pSid1) )
      break;
    v30 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v26 + v4));
    if ( (int)RtlCapabilityCheck(0, &DestinationString, &v30) < 0 )
    {
      v15 = 0;
      KnownSid::Cleanup((KnownSid *)&pSid1);
LABEL_39:
      *a4 = v15 != 0;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v19 = "enabled";
        if ( !v15 )
          v19 = "disabled";
        WPP_SF_qSs(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)a2, (__int64)v19);
      }
      goto LABEL_43;
    }
    v17 = v30 != 0;
LABEL_31:
    v15 &= v17;
    if ( !v15 )
    {
      KnownSid::Cleanup((KnownSid *)&pSid1);
      v15 = 0;
      goto LABEL_39;
    }
    KnownSid::Cleanup((KnownSid *)&pSid1);
    ++v4;
  }
  if ( v6 )
  {
LABEL_24:
    v17 = 0;
    v18 = 0;
    if ( *v6 )
    {
      while ( !EqualSid(pSid1, *(PSID *)&v6[4 * v18 + 2]) )
      {
        v17 = 0;
        if ( (unsigned int)++v18 >= *v6 )
          goto LABEL_31;
      }
      v17 = 1;
    }
    goto LABEL_31;
  }
  TokenCapabilities = GetTokenCapabilities(a1, (struct _TOKEN_GROUPS **)&Block);
  v9 = TokenCapabilities;
  if ( TokenCapabilities >= 0 )
  {
    v6 = Block;
    if ( !Block )
    {
      *a4 = 1;
      KnownSid::Cleanup((KnownSid *)&pSid1);
      goto LABEL_45;
    }
    goto LABEL_24;
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
      0,
      TokenCapabilities);
  KnownSid::Cleanup((KnownSid *)&pSid1);
  v6 = Block;
LABEL_43:
  if ( v6 )
    operator delete(v6);
LABEL_45:
  v12 = v22;
LABEL_46:
  operator delete(v12);
LABEL_50:
  operator delete(v26);
  return v9;
}

```

## disassembly

```asm
0x180056220  mov     [rsp-38h+arg_8], rbx
0x180056225  mov     [rsp-38h+arg_0], rcx
0x18005622a  push    rbp
0x18005622b  push    rsi
0x18005622c  push    rdi
0x18005622d  push    r12
0x18005622f  push    r13
0x180056231  push    r14
0x180056233  push    r15
0x180056235  mov     rbp, rsp
0x180056238  sub     rsp, 80h
0x18005623f  xor     r12d, r12d
0x180056242  mov     esi, r8d
0x180056245  mov     [rbp+var_20], r12
0x180056249  mov     edi, r12d
0x18005624c  mov     [rbp+var_14], r12
0x180056250  mov     r15, r9
0x180056253  mov     [rbp+var_18], r12d
0x180056257  mov     r13, rdx
0x18005625a  mov     [rbp+Block], r12
0x18005625e  cmp     cs:byte_18008D62D, 8
0x180056265  jb      short loc_18005628E
0x180056267  mov     r9, rcx
0x18005626a  mov     [rsp+80h+var_60], r13
0x18005626f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056276  lea     edx, [r12+36h]
0x18005627b  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180056282  mov     rcx, [rcx+0D8h]
0x180056289  call    WPP_SF_qS
0x18005628e  test    esi, esi
0x180056290  jz      loc_180056527
0x180056296  test    r13, r13
0x180056299  jz      loc_180056527
0x18005629f  test    r15, r15
0x1800562a2  jnz     short loc_1800562BF
0x1800562a4  mov     ebx, 80004003h
0x1800562a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800562b0  jb      loc_180056558
0x1800562b6  lea     edx, [r15+38h]
0x1800562ba  jmp     loc_18005653A
0x1800562bf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800562c6  mov     [r15], r12d
0x1800562c9  mov     eax, 2
0x1800562ce  mul     rsi
0x1800562d1  cmovb   rax, rcx
0x1800562d5  mov     rcx, rax; unsigned __int64
0x1800562d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800562dd  mov     [rbp+var_48], rax
0x1800562e1  mov     r14, rax
0x1800562e4  test    rax, rax
0x1800562e7  jnz     short loc_180056303
0x1800562e9  mov     ebx, 8007000Eh
0x1800562ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800562f5  jb      loc_180056558
0x1800562fb  lea     edx, [rax+39h]
0x1800562fe  jmp     loc_18005653A
0x180056303  mov     r8, r13; unsigned __int16 *
0x180056306  mov     rdx, rsi; unsigned __int64
0x180056309  mov     rcx, r14; unsigned __int16 *
0x18005630c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056311  mov     ebx, eax
0x180056313  test    eax, eax
0x180056315  jns     short loc_18005634C
0x180056317  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005631e  jb      loc_18005651D
0x180056324  mov     edx, 3Ah ; ':'
0x180056329  mov     rcx, cs:WPP_GLOBAL_Control
0x180056330  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180056337  xor     r9d, r9d
0x18005633a  mov     dword ptr [rsp+80h+var_60], eax
0x18005633e  mov     rcx, [rcx+10h]
0x180056342  call    WPP_SF_qD
0x180056347  jmp     loc_18005651D
0x18005634c  lea     r8, [rbp+var_20]
0x180056350  mov     edx, esi
0x180056352  mov     rcx, r14; unsigned __int16 *
0x180056355  call    ?ProcessCapabilityList@@YAJPEAGKAEAV?$CTEntryArray@PEBG@@@Z; ProcessCapabilityList(ushort *,ulong,CTEntryArray<ushort const *> &)
0x18005635a  mov     ebx, eax
0x18005635c  test    eax, eax
0x18005635e  jns     short loc_180056374
0x180056360  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180056367  jb      loc_18005651D
0x18005636d  mov     edx, 3Bh ; ';'
0x180056372  jmp     short loc_180056329
0x180056374  mov     sil, 1
0x180056377  cmp     r12d, [rbp+var_18]
0x18005637b  jnb     loc_1800564B6
0x180056381  mov     rcx, [rbp+var_20]
0x180056385  lea     rdx, [rbp+pSid1]; Sid
0x180056389  mov     [rbp+pSid1], 0
0x180056391  mov     [rbp+var_38], 0
0x180056395  mov     r14d, r12d
0x180056398  mov     rcx, [rcx+r14*8]; StringSid
0x18005639c  call    ?IsStringSid@@YA_NPEBGPEAUKnownSid@@@Z; IsStringSid(ushort const *,KnownSid *)
0x1800563a1  test    al, al
0x1800563a3  jz      short loc_180056402
0x1800563a5  test    rdi, rdi
0x1800563a8  jnz     short loc_1800563CE
0x1800563aa  mov     rcx, [rbp+arg_0]; void *
0x1800563ae  lea     rdx, [rbp+Block]; struct _TOKEN_GROUPS **
0x1800563b2  call    ?GetTokenCapabilities@@YAJPEAXPEAPEAU_TOKEN_GROUPS@@@Z; GetTokenCapabilities(void *,_TOKEN_GROUPS * *)
0x1800563b7  mov     ebx, eax
0x1800563b9  test    eax, eax
0x1800563bb  js      loc_180056465
0x1800563c1  mov     rdi, [rbp+Block]
0x1800563c5  test    rdi, rdi
0x1800563c8  jz      loc_180056450
0x1800563ce  xor     al, al
0x1800563d0  xor     r14d, r14d
0x1800563d3  cmp     [rdi], r14d
0x1800563d6  jbe     short loc_18005643A
0x1800563d8  mov     rcx, [rbp+pSid1]; pSid1
0x1800563dc  mov     edx, r14d
0x1800563df  add     rdx, rdx
0x1800563e2  mov     rdx, [rdi+rdx*8+8]; pSid2
0x1800563e7  call    cs:__imp_EqualSid
0x1800563ed  cmp     eax, 1
0x1800563f0  jz      short loc_1800563FE
0x1800563f2  xor     al, al
0x1800563f4  inc     r14d
0x1800563f7  cmp     r14d, [rdi]
0x1800563fa  jb      short loc_1800563D8
0x1800563fc  jmp     short loc_18005643A
0x1800563fe  mov     al, 1
0x180056400  jmp     short loc_18005643A
0x180056402  mov     rax, [rbp+var_20]
0x180056406  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005640a  xorps   xmm0, xmm0
0x18005640d  mov     [rbp+arg_10], 0
0x180056411  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180056415  mov     rdx, [rax+r14*8]; SourceString
0x180056419  call    cs:__imp_RtlInitUnicodeString
0x18005641f  lea     r8, [rbp+arg_10]
0x180056423  xor     ecx, ecx
0x180056425  lea     rdx, [rbp+DestinationString]
0x180056429  call    cs:__imp_RtlCapabilityCheck
0x18005642f  test    eax, eax
0x180056431  js      short loc_1800564AA
0x180056433  cmp     [rbp+arg_10], 0
0x180056437  setnz   al
0x18005643a  lea     rcx, [rbp+pSid1]; this
0x18005643e  and     sil, al
0x180056441  jz      short loc_1800564A0
0x180056443  call    ?Cleanup@KnownSid@@QEAAXXZ; KnownSid::Cleanup(void)
0x180056448  inc     r12d
0x18005644b  jmp     loc_180056377
0x180056450  lea     rcx, [rbp+pSid1]; this
0x180056454  mov     dword ptr [r15], 1
0x18005645b  call    ?Cleanup@KnownSid@@QEAAXXZ; KnownSid::Cleanup(void)
0x180056460  jmp     loc_180056519
0x180056465  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005646c  jb      short loc_180056491
0x18005646e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056475  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18005647c  mov     edx, 3Ch ; '<'
0x180056481  mov     dword ptr [rsp+80h+var_60], eax
0x180056485  xor     r9d, r9d
0x180056488  mov     rcx, [rcx+10h]
0x18005648c  call    WPP_SF_qD
0x180056491  lea     rcx, [rbp+pSid1]; this
0x180056495  call    ?Cleanup@KnownSid@@QEAAXXZ; KnownSid::Cleanup(void)
0x18005649a  mov     rdi, [rbp+Block]
0x18005649e  jmp     short loc_18005650C
0x1800564a0  call    ?Cleanup@KnownSid@@QEAAXXZ; KnownSid::Cleanup(void)
0x1800564a5  xor     sil, sil
0x1800564a8  jmp     short loc_1800564B6
0x1800564aa  xor     sil, sil
0x1800564ad  lea     rcx, [rbp+pSid1]; this
0x1800564b1  call    ?Cleanup@KnownSid@@QEAAXXZ; KnownSid::Cleanup(void)
0x1800564b6  xor     eax, eax
0x1800564b8  test    sil, sil
0x1800564bb  setnz   al
0x1800564be  mov     [r15], eax
0x1800564c1  cmp     cs:byte_18008D62D, 8
0x1800564c8  jb      short loc_18005650C
0x1800564ca  mov     r9, [rbp+arg_0]
0x1800564ce  lea     rcx, aDisabled_0; "disabled"
0x1800564d5  test    sil, sil
0x1800564d8  lea     rax, aEnabled; "enabled"
0x1800564df  mov     edx, 3Dh ; '='
0x1800564e4  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800564eb  cmovz   rax, rcx
0x1800564ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800564f6  mov     [rsp+80h+var_58], rax; __int64
0x1800564fb  mov     [rsp+80h+var_60], r13; __int64
0x180056500  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180056507  call    WPP_SF_qSs
0x18005650c  test    rdi, rdi
0x18005650f  jz      short loc_180056519
0x180056511  mov     rcx, rdi; Block
0x180056514  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056519  mov     r14, [rbp+var_48]
0x18005651d  mov     rcx, r14; Block
0x180056520  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056525  jmp     short loc_180056558
0x180056527  mov     ebx, 80070057h
0x18005652c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180056533  jb      short loc_180056558
0x180056535  mov     edx, 37h ; '7'
0x18005653a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056541  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180056548  xor     r9d, r9d
0x18005654b  mov     dword ptr [rsp+80h+var_60], ebx
0x18005654f  mov     rcx, [rcx+10h]
0x180056553  call    WPP_SF_qD
0x180056558  mov     rcx, [rbp+var_20]; Block
0x18005655c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056561  mov     eax, ebx
0x180056563  mov     rbx, [rsp+80h+arg_8]
0x18005656b  add     rsp, 80h
0x180056572  pop     r15
0x180056574  pop     r14
0x180056576  pop     r13
0x180056578  pop     r12
0x18005657a  pop     rdi
0x18005657b  pop     rsi
0x18005657c  pop     rbp
0x18005657d  retn
```
