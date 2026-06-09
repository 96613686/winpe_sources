# LogGetAsExtendedAudit(_UNICODE_STRING *,_UNICODE_STRING *,void *,_UNICODE_STRING *,void *,ulong *,long *,ulong *,ulong *,sockaddr *,_KDC_PKI_AUDIT_INFO *,KERB_TICKET *,KERB_ENCRYPTED_KDC_REPLY *,KERB_KDC_REQUEST_BODY *,_UNICODE_STRING *,KERB_EXT_ERROR *,ulong *,ulong *,_KERB_ENCRYPTION_KEY *,utl::optional<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> const &,uchar *,ulong *,PacRequestType *,ulong *,long *,_USER_INTERNAL6_INFORMATION *,_CERT_CONTEXT const *)

- ea: `0x18000cc5c`
- end: `0x18000d426`
- name: `?LogGetAsExtendedAudit@@YAXPEAU_UNICODE_STRING@@0PEAX01PEAKPEAJ22PEAUsockaddr@@PEAU_KDC_PKI_AUDIT_INFO@@PEAUKERB_TICKET@@PEAUKERB_ENCRYPTED_KDC_REPLY@@PEAUKERB_KDC_REQUEST_BODY@@0PEAUKERB_EXT_ERROR@@22PEAU_KERB_ENCRYPTION_KEY@@AEBV?$optional@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@PEAE2PEAW4PacRequestType@@23PEAU_USER_INTERNAL6_INFORMATION@@PEBU_CERT_CONTEXT@@@Z`
- size: `1994`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, __int64, struct sockaddr *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016148`
- `0x18001e930`

## callees

- `0x180002ad0`
- `0x18000a878`
- `0x18000a8d8`
- `0x18000abe4`
- `0x18000b474`
- `0x18000cc5c`
- `0x18000e874`
- `0x18000e9e8`
- `0x18000ec30`
- `0x180063144`
- `0x18007d4b0`
- `0x18007d714`
- `0x18007dc20`
- `0x18007e35c`
- `0x18007f1a4`
- `0x180080280`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000cf52`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000cf6c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000cf52`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000cf6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall LogGetAsExtendedAudit(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        void *a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8,
        int *a9,
        struct sockaddr *a10,
        const struct _UNICODE_STRING *a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        struct _UNICODE_STRING *a15,
        const unsigned __int16 *a16,
        const unsigned __int16 *a17,
        const unsigned __int16 *a18,
        const unsigned __int16 *a19,
        __int64 *a20,
        unsigned __int8 *a21,
        _DWORD *a22,
        int *a23,
        const WCHAR *a24,
        __int64 *a25,
        __int64 a26,
        __int64 a27)
{
  _DWORD *result; // rax
  __int64 v28; // rdx
  int v29; // edi
  __int64 *v30; // rax
  const WCHAR *Buffer; // r10
  __int64 v32; // r11
  __int64 *v33; // r9
  __int64 *v34; // rax
  int v35; // r15d
  __int64 v36; // r8
  __int64 v37; // rax
  const unsigned __int16 *v38; // r8
  __int64 *v39; // r9
  const WCHAR *v40; // r10
  const struct _UNICODE_STRING *v41; // r11
  const unsigned __int16 *v42; // r13
  const struct _UNICODE_STRING *v43; // r11
  const unsigned __int16 *v44; // r12
  const struct _UNICODE_STRING *v45; // r11
  unsigned __int8 *v46; // rsi
  unsigned int v47; // r14d
  int v48; // ebx
  unsigned int v49; // eax
  __int64 v50; // r8
  int v51; // r9d
  char v52; // r10
  char v53; // r11
  int v54; // [rsp+170h] [rbp-80h]
  unsigned int v55; // [rsp+174h] [rbp-7Ch] BYREF
  int v56; // [rsp+178h] [rbp-78h]
  int v57; // [rsp+17Ch] [rbp-74h]
  int v58; // [rsp+180h] [rbp-70h]
  int v59; // [rsp+184h] [rbp-6Ch]
  int v60; // [rsp+188h] [rbp-68h]
  int v61; // [rsp+18Ch] [rbp-64h] BYREF
  int v62; // [rsp+190h] [rbp-60h] BYREF
  int v63; // [rsp+194h] [rbp-5Ch] BYREF
  unsigned int v64; // [rsp+198h] [rbp-58h]
  const WCHAR *v65; // [rsp+1A0h] [rbp-50h]
  __int64 *v66; // [rsp+1A8h] [rbp-48h]
  _DWORD *v67; // [rsp+1B0h] [rbp-40h]
  int *v68; // [rsp+1B8h] [rbp-38h]
  const struct _UNICODE_STRING *v69; // [rsp+1C0h] [rbp-30h]
  __int64 *v70; // [rsp+1C8h] [rbp-28h]
  PSID v71; // [rsp+1D0h] [rbp-20h]
  PSID pSid; // [rsp+1D8h] [rbp-18h]
  const unsigned __int16 *v73; // [rsp+1E0h] [rbp-10h]
  const unsigned __int16 *v74; // [rsp+1E8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+1F0h] [rbp+0h]
  const unsigned __int16 *v76; // [rsp+1F8h] [rbp+8h]
  struct _UNICODE_STRING *v77; // [rsp+200h] [rbp+10h]
  const WCHAR *v78; // [rsp+208h] [rbp+18h]
  unsigned __int8 *v79; // [rsp+210h] [rbp+20h] BYREF
  __int64 v80; // [rsp+218h] [rbp+28h]
  const WCHAR *v81; // [rsp+220h] [rbp+30h]
  __int64 v82; // [rsp+228h] [rbp+38h] BYREF
  __int64 v83; // [rsp+230h] [rbp+40h] BYREF
  struct _UNICODE_STRING v84; // [rsp+238h] [rbp+48h] BYREF
  struct _UNICODE_STRING v85; // [rsp+248h] [rbp+58h] BYREF
  struct _UNICODE_STRING v86; // [rsp+258h] [rbp+68h] BYREF
  struct _UNICODE_STRING v87; // [rsp+268h] [rbp+78h] BYREF
  struct _UNICODE_STRING v88; // [rsp+278h] [rbp+88h] BYREF
  struct _UNICODE_STRING v89; // [rsp+288h] [rbp+98h] BYREF
  _OWORD v90[2]; // [rsp+298h] [rbp+A8h] BYREF
  __int64 v91; // [rsp+2B8h] [rbp+C8h]
  int *v92; // [rsp+2C0h] [rbp+D0h]
  __int64 v93; // [rsp+2C8h] [rbp+D8h]
  __int64 v94; // [rsp+2D0h] [rbp+E0h]
  struct _UNICODE_STRING *v95; // [rsp+2D8h] [rbp+E8h]
  struct _UNICODE_STRING *v96; // [rsp+2E0h] [rbp+F0h]
  struct _UNICODE_STRING *v97; // [rsp+2E8h] [rbp+F8h]
  const unsigned __int16 *v98; // [rsp+2F0h] [rbp+100h]
  __int64 v99; // [rsp+2F8h] [rbp+108h]
  const unsigned __int16 *v100; // [rsp+300h] [rbp+110h]
  struct _UNICODE_STRING *v101; // [rsp+308h] [rbp+118h]
  struct _UNICODE_STRING *v102; // [rsp+310h] [rbp+120h]
  struct _UNICODE_STRING *v103; // [rsp+318h] [rbp+128h]
  struct _UNICODE_STRING *v104; // [rsp+320h] [rbp+130h]
  struct _UNICODE_STRING *v105; // [rsp+328h] [rbp+138h]
  struct _UNICODE_STRING *v106; // [rsp+330h] [rbp+140h]
  char v107; // [rsp+338h] [rbp+148h]
  void *v108[4]; // [rsp+340h] [rbp+150h] BYREF
  __int128 v109; // [rsp+360h] [rbp+170h] BYREF

  v95 = a4;
  pSid = a3;
  v96 = a2;
  v97 = a1;
  v76 = a16;
  v71 = a5;
  result = a6;
  v94 = a7;
  v93 = a8;
  v92 = a9;
  v69 = a11;
  v77 = a15;
  v75 = a17;
  v74 = a18;
  v73 = a19;
  v70 = a20;
  v67 = a22;
  v68 = a23;
  v65 = a24;
  v66 = a25;
  if ( (byte_1800B2901 & 1) != 0 )
  {
    memset(v90, 0, sizeof(v90));
    LOBYTE(v90[0]) = 0;
    v91 = 0;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v84 = 0;
    v88 = 0;
    v89 = 0;
    v101 = &v85;
    v102 = &v86;
    v103 = &v87;
    v104 = &v84;
    v105 = &v88;
    v106 = &v89;
    v107 = 1;
    v63 = 0;
    v62 = 0;
    if ( a6 )
      v54 = *a6;
    else
      LOBYTE(v54) = 0;
    if ( a14 )
    {
      if ( !a6 )
        LOBYTE(v54) = KerbConvertFlagsToUlong((const struct tagASN1bitstring_t *)(a14 + 8));
      if ( (*(_BYTE *)a14 & 0x40) != 0 )
        KerbConvertPrincipalNameToString(&v85, &v63, a14 + 48);
      v28 = KerberosCryptoPolicy::EtypeListToCommaSeparatedString((__int64)v108, *(__int64 ***)(a14 + 112));
      if ( (_BYTE)v91 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
          v90,
          v28);
      }
      else
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          v90,
          v28);
        LOBYTE(v91) = 1;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v108);
      KerbConvertRealmToUnicodeString(&v86, a14 + 40);
      if ( *(char *)a14 < 0 )
        KerbConvertPrincipalNameToString(&v87, &v62, a14 + 24);
    }
    v64 = 0;
    v61 = 0;
    if ( a12 )
    {
      v64 = *(_DWORD *)(a12 + 48);
      KdcHashTicketEncryptedPart(*(unsigned __int8 **)(a12 + 56), v64, &v89);
      KerbConvertPrincipalNameToString(&v84, &v61, a12 + 16);
      KerbConvertRealmToUnicodeString(&v88, a12 + 8);
    }
    LOBYTE(v29) = 0;
    v83 = 0;
    v82 = 0;
    if ( a13 )
    {
      v83 = KerbConvertGeneralizedTimeToFileTime(a13 + 94);
      v82 = KerbConvertGeneralizedTimeToFileTime(a13 + 108);
    }
    if ( !pSid || !IsValidSid(pSid) )
      pSid = 0;
    if ( !v71 || !IsValidSid(v71) )
      v71 = 0;
    v55 = 0;
    v79 = 0;
    GetClientAddressBuffer(a10, &v55, &v79);
    v30 = (__int64 *)(a26 + 752);
    if ( !a26 )
      v30 = qword_1800A1980;
    v109 = *(_OWORD *)v30;
    v56 = 0;
    v80 = 0;
    if ( a27 && (unsigned int)(*(_DWORD *)(a27 + 16) - 1) <= 0x1FFE && *(_QWORD *)(a27 + 8) )
    {
      v56 = *(_DWORD *)(a27 + 16);
      v80 = *(_QWORD *)(a27 + 8);
    }
    if ( (byte_1800B2901 & 1) != 0 )
    {
      if ( a21 )
        v57 = *a21;
      else
        v57 = 0;
      v78 = &Class;
      if ( *((_BYTE *)v70 + 32) )
        v81 = (const WCHAR *)*v70;
      else
        v81 = &Class;
      if ( v66 )
        v58 = *(_DWORD *)v66;
      else
        v58 = 0;
      if ( v65 )
        v59 = *(_DWORD *)v65;
      else
        v59 = 0;
      if ( v69 )
      {
        Buffer = SafeGetBuffer(v69 + 3);
        v33 = (__int64 *)(v32 + 72);
        v34 = (__int64 *)(v32 + 64);
      }
      else
      {
        Buffer = &Class;
        v34 = &qword_1800A1990;
        v33 = &qword_1800A1990;
      }
      v66 = v33;
      v70 = v34;
      v65 = Buffer;
      if ( v68 )
        v60 = *v68;
      else
        v60 = 0;
      if ( v67 )
        LODWORD(v67) = *v67;
      else
        LODWORD(v67) = 0;
      if ( v73 )
        LODWORD(v68) = *((_DWORD *)v73 + 3);
      else
        LODWORD(v68) = 0;
      if ( v74 )
        LODWORD(v69) = *(_DWORD *)v74;
      else
        LODWORD(v69) = 0;
      if ( v75 )
        v35 = *(_DWORD *)v75;
      else
        LOBYTE(v35) = 0;
      v75 = SafeGetBuffer(&v88);
      v74 = SafeGetBuffer(&v84);
      v73 = SafeGetBuffer(&v86);
      v100 = SafeGetBuffer(&v87);
      v98 = SafeGetBuffer(&v85);
      v37 = v36;
      if ( (_BYTE)v91 )
        v37 = *(_QWORD *)&v90[0];
      v99 = v37;
      if ( v76 )
        v29 = *(_DWORD *)v76;
      v77 = (struct _UNICODE_STRING *)SafeGetBuffer(v77);
      v76 = SafeGetBuffer(&v89);
      if ( v41 )
      {
        v42 = SafeGetBuffer(v41 + 2);
        v44 = SafeGetBuffer(v43 + 1);
        v78 = SafeGetBuffer(v45);
      }
      else
      {
        v65 = v40;
        v66 = v39;
        v42 = v38;
        v44 = v38;
      }
      v46 = v79;
      v47 = v55;
      if ( v92 )
        v48 = *v92;
      else
        LOBYTE(v48) = 0;
      SafeGetBuffer(v95);
      SafeGetBuffer(v96);
      v49 = (unsigned int)SafeGetBuffer(v97);
      McTemplateU0zzkzkqqqqqbr9zzzzzqqmmzzqzqzzqzqqqqqmmzqqztqbr41j_EtwEventWriteTransfer(
        (unsigned int)&S_Microsoft_Windows_Kerberos_Key_Distribution_Center_Context,
        (unsigned int)KdcGetAsExtendedAudit,
        v49,
        v51,
        (__int64)pSid,
        v50,
        (__int64)v71,
        v54,
        v52,
        v53,
        v48,
        v47,
        (__int64)v46,
        (__int64)v78,
        (__int64)v44,
        (__int64)v42,
        (__int64)v76,
        (__int64)v77,
        v29,
        v64,
        (__int64)&v83,
        (__int64)&v82,
        v99,
        (__int64)v98,
        v63,
        (__int64)v100,
        v62,
        (__int64)v73,
        (__int64)v74,
        v61,
        (__int64)v75,
        v35,
        (char)v69,
        (char)v68,
        (char)v67,
        v60,
        (__int64)v70,
        (__int64)v66,
        (__int64)v65,
        v59,
        v58,
        (__int64)v81,
        v57,
        v56,
        v80,
        (__int64)&v109);
    }
    KerbFreeString(&v85);
    KerbFreeString(&v86);
    KerbFreeString(&v87);
    KerbFreeString(&v84);
    KerbFreeString(&v88);
    KerbFreeString(&v89);
    return (_DWORD *)utl::_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>::~_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(v90);
  }
  return result;
}

```

## disassembly

```asm
0x18000cc5c  push    rbp
0x18000cc5e  push    rbx
0x18000cc5f  push    rsi
0x18000cc60  push    rdi
0x18000cc61  push    r12
0x18000cc63  push    r13
0x18000cc65  push    r14
0x18000cc67  push    r15
0x18000cc69  lea     rbp, [rsp-198h]
0x18000cc71  sub     rsp, 388h
0x18000cc78  mov     rax, cs:__security_cookie
0x18000cc7f  xor     rax, rsp
0x18000cc82  mov     [rbp+1D0h+var_50], rax
0x18000cc89  mov     [rbp+1D0h+var_E8], r9
0x18000cc90  mov     [rbp+1D0h+pSid], r8
0x18000cc94  mov     [rbp+1D0h+var_E0], rdx
0x18000cc9b  mov     [rbp+1D0h+var_D8], rcx
0x18000cca2  mov     rax, [rbp+1D0h+arg_78]
0x18000cca9  mov     [rbp+1D0h+var_1C8], rax
0x18000ccad  mov     rbx, [rbp+1D0h+arg_68]
0x18000ccb4  mov     rcx, [rbp+1D0h+arg_20]
0x18000ccbb  mov     [rbp+1D0h+var_1F0], rcx
0x18000ccbf  mov     rax, [rbp+1D0h+arg_28]
0x18000ccc6  mov     rcx, [rbp+1D0h+arg_30]
0x18000cccd  mov     [rbp+1D0h+var_F0], rcx
0x18000ccd4  mov     rcx, [rbp+1D0h+arg_38]
0x18000ccdb  mov     [rbp+1D0h+var_F8], rcx
0x18000cce2  mov     rcx, [rbp+1D0h+arg_40]
0x18000cce9  mov     [rbp+1D0h+var_100], rcx
0x18000ccf0  mov     r13, [rbp+1D0h+arg_48]
0x18000ccf7  mov     rcx, [rbp+1D0h+arg_50]
0x18000ccfe  mov     [rbp+1D0h+var_200], rcx
0x18000cd02  mov     rdi, [rbp+1D0h+arg_58]
0x18000cd09  mov     rsi, [rbp+1D0h+arg_60]
0x18000cd10  mov     rcx, [rbp+1D0h+arg_70]
0x18000cd17  mov     [rbp+1D0h+var_1C0], rcx
0x18000cd1b  mov     rcx, [rbp+1D0h+arg_80]
0x18000cd22  mov     [rbp+1D0h+var_1D0], rcx
0x18000cd26  mov     rcx, [rbp+1D0h+arg_88]
0x18000cd2d  mov     [rbp+1D0h+var_1D8], rcx
0x18000cd31  mov     rcx, [rbp+1D0h+arg_90]
0x18000cd38  mov     [rbp+1D0h+var_1E0], rcx
0x18000cd3c  mov     rcx, [rbp+1D0h+arg_98]
0x18000cd43  mov     [rbp+1D0h+var_1F8], rcx
0x18000cd47  mov     r12, [rbp+1D0h+arg_A0]
0x18000cd4e  mov     rcx, [rbp+1D0h+arg_A8]
0x18000cd55  mov     [rbp+1D0h+var_210], rcx
0x18000cd59  mov     rcx, [rbp+1D0h+arg_B0]
0x18000cd60  mov     [rbp+1D0h+var_208], rcx
0x18000cd64  mov     rcx, [rbp+1D0h+arg_B8]
0x18000cd6b  mov     [rbp+1D0h+var_220], rcx
0x18000cd6f  mov     rcx, [rbp+1D0h+arg_C0]
0x18000cd76  mov     [rbp+1D0h+var_218], rcx
0x18000cd7a  mov     r15, [rbp+1D0h+arg_C8]
0x18000cd81  mov     r14, [rbp+1D0h+arg_D0]
0x18000cd88  test    cs:byte_1800B2901, 1
0x18000cd8f  jz      loc_18000D403
0x18000cd95  xorps   xmm0, xmm0
0x18000cd98  xor     ecx, ecx
0x18000cd9a  movups  [rbp+1D0h+var_128], xmm0
0x18000cda1  movups  [rbp+1D0h+var_118], xmm0
0x18000cda8  mov     [rbp+1D0h+var_108], rcx
0x18000cdaf  xor     edx, edx
0x18000cdb1  mov     byte ptr [rbp+1D0h+var_128], dl
0x18000cdb7  mov     byte ptr [rbp+1D0h+var_108], dl
0x18000cdbd  movups  xmmword ptr [rbp+1D0h+var_178.Length], xmm0
0x18000cdc1  xorps   xmm1, xmm1
0x18000cdc4  movups  xmmword ptr [rbp+1D0h+var_168.Length], xmm1
0x18000cdc8  movups  xmmword ptr [rbp+1D0h+var_158.Length], xmm0
0x18000cdcc  movups  xmmword ptr [rbp+1D0h+var_188.Length], xmm1
0x18000cdd0  movups  xmmword ptr [rbp+1D0h+var_148.Length], xmm0
0x18000cdd7  movups  xmmword ptr [rbp+1D0h+var_138.Length], xmm1
0x18000cdde  lea     rcx, [rbp+1D0h+var_178]
0x18000cde2  mov     [rbp+1D0h+var_B8], rcx
0x18000cde9  lea     rcx, [rbp+1D0h+var_168]
0x18000cded  mov     [rbp+1D0h+var_B0], rcx
0x18000cdf4  lea     rcx, [rbp+1D0h+var_158]
0x18000cdf8  mov     [rbp+1D0h+var_A8], rcx
0x18000cdff  lea     rcx, [rbp+1D0h+var_188]
0x18000ce03  mov     [rbp+1D0h+var_A0], rcx
0x18000ce0a  lea     rcx, [rbp+1D0h+var_148]
0x18000ce11  mov     [rbp+1D0h+var_98], rcx
0x18000ce18  lea     rcx, [rbp+1D0h+var_138]
0x18000ce1f  mov     [rbp+1D0h+var_90], rcx
0x18000ce26  mov     [rbp+1D0h+var_88], 1
0x18000ce2d  mov     [rbp+1D0h+var_22C], edx
0x18000ce30  mov     [rbp+1D0h+var_230], edx
0x18000ce33  test    rax, rax
0x18000ce36  jz      short loc_18000CE3F
0x18000ce38  mov     ecx, [rax]
0x18000ce3a  mov     [rbp+1D0h+var_250], ecx
0x18000ce3d  jmp     short loc_18000CE42
0x18000ce3f  mov     [rbp+1D0h+var_250], edx
0x18000ce42  test    rbx, rbx
0x18000ce45  jz      loc_18000CED9
0x18000ce4b  test    rax, rax
0x18000ce4e  jnz     short loc_18000CE5C
0x18000ce50  lea     rcx, [rbx+8]; struct tagASN1bitstring_t *
0x18000ce54  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x18000ce59  mov     [rbp+1D0h+var_250], eax
0x18000ce5c  test    byte ptr [rbx], 40h
0x18000ce5f  jz      short loc_18000CE72
0x18000ce61  lea     r8, [rbx+30h]
0x18000ce65  lea     rdx, [rbp+1D0h+var_22C]
0x18000ce69  lea     rcx, [rbp+1D0h+var_178]
0x18000ce6d  call    KerbConvertPrincipalNameToString
0x18000ce72  mov     rdx, [rbx+70h]
0x18000ce76  lea     rcx, [rbp+1D0h+var_80]
0x18000ce7d  call    ?EtypeListToCommaSeparatedString@KerberosCryptoPolicy@@SA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUKERB_KDC_REQUEST_BODY_encryption_type_s@@@Z; KerberosCryptoPolicy::EtypeListToCommaSeparatedString(KERB_KDC_REQUEST_BODY_encryption_type_s const *)
0x18000ce82  mov     rdx, rax
0x18000ce85  lea     rcx, [rbp+1D0h+var_128]
0x18000ce8c  cmp     byte ptr [rbp+1D0h+var_108], 0
0x18000ce93  jz      short loc_18000CE9C
0x18000ce95  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18000ce9a  jmp     short loc_18000CEA8
0x18000ce9c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18000cea1  mov     byte ptr [rbp+1D0h+var_108], 1
0x18000cea8  lea     rcx, [rbp+1D0h+var_80]
0x18000ceaf  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18000ceb4  lea     rdx, [rbx+28h]
0x18000ceb8  lea     rcx, [rbp+1D0h+var_168]
0x18000cebc  call    KerbConvertRealmToUnicodeString
0x18000cec1  test    byte ptr [rbx], 80h
0x18000cec4  jz      short loc_18000CED7
0x18000cec6  lea     r8, [rbx+18h]
0x18000ceca  lea     rdx, [rbp+1D0h+var_230]
0x18000cece  lea     rcx, [rbp+1D0h+var_158]
0x18000ced2  call    KerbConvertPrincipalNameToString
0x18000ced7  xor     edx, edx
0x18000ced9  mov     [rbp+1D0h+var_228], edx
0x18000cedc  mov     [rbp+1D0h+var_234], edx
0x18000cedf  test    rdi, rdi
0x18000cee2  jz      short loc_18000CF1D
0x18000cee4  mov     ebx, [rdi+30h]
0x18000cee7  mov     [rbp+1D0h+var_228], ebx
0x18000ceea  lea     r8, [rbp+1D0h+var_138]; struct _UNICODE_STRING *
0x18000cef1  mov     edx, ebx; unsigned int
0x18000cef3  mov     rcx, [rdi+38h]; unsigned __int8 *
0x18000cef7  call    ?KdcHashTicketEncryptedPart@@YAXPEAEKPEAU_UNICODE_STRING@@@Z; KdcHashTicketEncryptedPart(uchar *,ulong,_UNICODE_STRING *)
0x18000cefc  lea     r8, [rdi+10h]
0x18000cf00  lea     rdx, [rbp+1D0h+var_234]
0x18000cf04  lea     rcx, [rbp+1D0h+var_188]
0x18000cf08  call    KerbConvertPrincipalNameToString
0x18000cf0d  lea     rdx, [rdi+8]
0x18000cf11  lea     rcx, [rbp+1D0h+var_148]
0x18000cf18  call    KerbConvertRealmToUnicodeString
0x18000cf1d  xor     edi, edi
0x18000cf1f  mov     [rbp+1D0h+var_190], rdi
0x18000cf23  mov     [rbp+1D0h+var_198], rdi
0x18000cf27  test    rsi, rsi
0x18000cf2a  jz      short loc_18000CF46
0x18000cf2c  lea     rcx, [rsi+5Eh]
0x18000cf30  call    KerbConvertGeneralizedTimeToFileTime
0x18000cf35  mov     [rbp+1D0h+var_190], rax
0x18000cf39  lea     rcx, [rsi+6Ch]
0x18000cf3d  call    KerbConvertGeneralizedTimeToFileTime
0x18000cf42  mov     [rbp+1D0h+var_198], rax
0x18000cf46  mov     rbx, [rbp+1D0h+pSid]
0x18000cf4a  test    rbx, rbx
0x18000cf4d  jz      short loc_18000CF5C
0x18000cf4f  mov     rcx, rbx; pSid
0x18000cf52  call    cs:__imp_IsValidSid
0x18000cf58  test    eax, eax
0x18000cf5a  jnz     short loc_18000CF60
0x18000cf5c  mov     [rbp+1D0h+pSid], rdi
0x18000cf60  mov     rbx, [rbp+1D0h+var_1F0]
0x18000cf64  test    rbx, rbx
0x18000cf67  jz      short loc_18000CF76
0x18000cf69  mov     rcx, rbx; pSid
0x18000cf6c  call    cs:__imp_IsValidSid
0x18000cf72  test    eax, eax
0x18000cf74  jnz     short loc_18000CF7A
0x18000cf76  mov     [rbp+1D0h+var_1F0], rdi
0x18000cf7a  mov     [rbp+1D0h+var_24C], edi
0x18000cf7d  mov     [rbp+1D0h+var_1B0], rdi
0x18000cf81  lea     r8, [rbp+1D0h+var_1B0]; unsigned __int8 **
0x18000cf85  lea     rdx, [rbp+1D0h+var_24C]; unsigned int *
0x18000cf89  mov     rcx, r13; struct sockaddr *
0x18000cf8c  call    ?GetClientAddressBuffer@@YAXQEAUsockaddr@@AEAKAEAPEAE@Z; GetClientAddressBuffer(sockaddr * const,ulong &,uchar * &)
0x18000cf91  test    r15, r15
0x18000cf94  lea     rax, [r15+2F0h]
0x18000cf9b  jnz     short loc_18000CFA4
0x18000cf9d  lea     rax, qword_1800A1980
0x18000cfa4  movups  xmm0, xmmword ptr [rax]
0x18000cfa7  movdqu  [rbp+1D0h+var_60], xmm0
0x18000cfaf  mov     [rbp+1D0h+var_248], edi
0x18000cfb2  mov     [rbp+1D0h+var_1A8], rdi
0x18000cfb6  test    r14, r14
0x18000cfb9  jz      short loc_18000CFDA
0x18000cfbb  mov     ecx, [r14+10h]
0x18000cfbf  lea     eax, [rcx-1]
0x18000cfc2  cmp     eax, 1FFEh
0x18000cfc7  ja      short loc_18000CFDA
0x18000cfc9  cmp     [r14+8], rdi
0x18000cfcd  jz      short loc_18000CFDA
0x18000cfcf  mov     [rbp+1D0h+var_248], ecx
0x18000cfd2  mov     rax, [r14+8]
0x18000cfd6  mov     [rbp+1D0h+var_1A8], rax
0x18000cfda  test    cs:byte_1800B2901, 1
0x18000cfe1  jz      loc_18000D3BA
0x18000cfe7  test    r12, r12
0x18000cfea  jz      short loc_18000CFF6
0x18000cfec  movzx   ecx, byte ptr [r12]
0x18000cff1  mov     [rbp+1D0h+var_244], ecx
0x18000cff4  jmp     short loc_18000CFF9
0x18000cff6  mov     [rbp+1D0h+var_244], edi
0x18000cff9  lea     r8, Class
0x18000d000  mov     [rbp+1D0h+var_1B8], r8
0x18000d004  mov     rax, [rbp+1D0h+var_1F8]
0x18000d008  cmp     [rax+20h], dil
0x18000d00c  jz      short loc_18000D017
0x18000d00e  mov     rcx, [rax]
0x18000d011  mov     [rbp+1D0h+var_1A0], rcx
0x18000d015  jmp     short loc_18000D01B
0x18000d017  mov     [rbp+1D0h+var_1A0], r8
0x18000d01b  mov     rax, [rbp+1D0h+var_218]
0x18000d01f  test    rax, rax
0x18000d022  jz      short loc_18000D02B
0x18000d024  mov     ecx, [rax]
0x18000d026  mov     [rbp+1D0h+var_240], ecx
0x18000d029  jmp     short loc_18000D02E
0x18000d02b  mov     [rbp+1D0h+var_240], edi
0x18000d02e  mov     rax, [rbp+1D0h+var_220]
0x18000d032  test    rax, rax
0x18000d035  jz      short loc_18000D03E
0x18000d037  mov     eax, [rax]
0x18000d039  mov     [rbp+1D0h+var_23C], eax
0x18000d03c  jmp     short loc_18000D041
0x18000d03e  mov     [rbp+1D0h+var_23C], edi
0x18000d041  mov     r11, [rbp+1D0h+var_200]
0x18000d045  test    r11, r11
0x18000d048  jz      short loc_18000D060
0x18000d04a  lea     rcx, [r11+30h]; struct _UNICODE_STRING *
0x18000d04e  call    ?SafeGetBuffer@@YAPEBGPEBU_UNICODE_STRING@@@Z; SafeGetBuffer(_UNICODE_STRING const *)
0x18000d053  mov     r10, rax
0x18000d056  lea     r9, [r11+48h]
0x18000d05a  lea     rax, [r11+40h]
0x18000d05e  jmp     short loc_18000D06D
0x18000d060  mov     r10, r8
0x18000d063  lea     rax, qword_1800A1990
0x18000d06a  mov     r9, rax
0x18000d06d  mov     [rbp+1D0h+var_218], r9
0x18000d071  mov     [rbp+1D0h+var_1F8], rax
0x18000d075  mov     [rbp+1D0h+var_220], r10
0x18000d079  mov     rax, [rbp+1D0h+var_208]
0x18000d07d  test    rax, rax
0x18000d080  jz      short loc_18000D089
0x18000d082  mov     eax, [rax]
0x18000d084  mov     [rbp+1D0h+var_238], eax
0x18000d087  jmp     short loc_18000D08C
0x18000d089  mov     [rbp+1D0h+var_238], edi
0x18000d08c  mov     rax, [rbp+1D0h+var_210]
0x18000d090  test    rax, rax
0x18000d093  jz      short loc_18000D09C
0x18000d095  mov     eax, [rax]
0x18000d097  mov     dword ptr [rbp+1D0h+var_210], eax
0x18000d09a  jmp     short loc_18000D09F
0x18000d09c  mov     dword ptr [rbp+1D0h+var_210], edi
0x18000d09f  mov     rax, [rbp+1D0h+var_1E0]
0x18000d0a3  test    rax, rax
0x18000d0a6  jz      short loc_18000D0B0
0x18000d0a8  mov     eax, [rax+0Ch]
0x18000d0ab  mov     dword ptr [rbp+1D0h+var_208], eax
0x18000d0ae  jmp     short loc_18000D0B3
0x18000d0b0  mov     dword ptr [rbp+1D0h+var_208], edi
0x18000d0b3  mov     rax, [rbp+1D0h+var_1D8]
0x18000d0b7  test    rax, rax
0x18000d0ba  jz      short loc_18000D0C3
0x18000d0bc  mov     eax, [rax]
0x18000d0be  mov     dword ptr [rbp+1D0h+var_200], eax
0x18000d0c1  jmp     short loc_18000D0C6
0x18000d0c3  mov     dword ptr [rbp+1D0h+var_200], edi
0x18000d0c6  mov     rax, [rbp+1D0h+var_1D0]
0x18000d0ca  test    rax, rax
0x18000d0cd  jz      short loc_18000D0D4
0x18000d0cf  mov     r15d, [rax]
0x18000d0d2  jmp     short loc_18000D0D7
0x18000d0d4  mov     r15d, edi
0x18000d0d7  lea     rcx, [rbp+1D0h+var_148]; struct _UNICODE_STRING *
0x18000d0de  call    ?SafeGetBuffer@@YAPEBGPEBU_UNICODE_STRING@@@Z; SafeGetBuffer(_UNICODE_STRING const *)
0x18000d0e3  mov     [rbp+1D0h+var_1D0], rax
0x18000d0e7  lea     rcx, [rbp+1D0h+var_188]; struct _UNICODE_STRING *
0x18000d0eb  call    ?SafeGetBuffer@@YAPEBGPEBU_UNICODE_STRING@@@Z; SafeGetBuffer(_UNICODE_STRING const *)
0x18000d0f0  mov     [rbp+1D0h+var_1D8], rax
0x18000d0f4  lea     rcx, [rbp+1D0h+var_168]; struct _UNICODE_STRING *
0x18000d0f8  call    ?SafeGetBuffer@@YAPEBGPEBU_UNICODE_STRING@@@Z; SafeGetBuffer(_UNICODE_STRING const *)
0x18000d0fd  mov     [rbp+1D0h+var_1E0], rax
0x18000d101  lea     rcx, [rbp+1D0h+var_158]; struct _UNICODE_STRING *
0x18000d105  call    ?SafeGetBuffer@@YAPEBGPEBU_UNICODE_STRING@@@Z; SafeGetBuffer(_UNICODE_STRING const *)
0x18000d10a  mov     [rbp+1D0h+var_C0], rax
0x18000d111  lea     rcx, [rbp+1D0h+var_178]; struct _UNICODE_STRING *
0x18000d115  call    ?SafeGetBuffer@@YAPEBGPEBU_UNICODE_STRING@@@Z; SafeGetBuffer(_UNICODE_STRING const *)
0x18000d11a  mov     [rbp+1D0h+var_D0], rax
0x18000d121  mov     rax, r8
0x18000d124  cmp     byte ptr [rbp+1D0h+var_108], dil
0x18000d12b  cmovnz  rax, qword ptr [rbp+1D0h+var_128]
0x18000d133  mov     [rbp+1D0h+var_C8], rax
0x18000d13a  mov     rax, [rbp+1D0h+var_1C8]
0x18000d13e  test    rax, rax
0x18000d141  jz      short loc_18000D145
  ... truncated ...
```
