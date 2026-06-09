# MFProfileInternalParseConcurrencyReferenceGuid(ushort const *,ushort const *,int,IMFCameraProfileValidation *,_GUID *,ushort *,int,ushort const * *)

- ea: `0x18006a228`
- end: `0x18006a4b6`
- name: `?MFProfileInternalParseConcurrencyReferenceGuid@@YAJPEBG0HPEAUIMFCameraProfileValidation@@PEAU_GUID@@PEAGHPEAPEBG@Z`
- size: `654`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, int, struct IMFCameraProfileValidation *, struct _GUID *, unsigned __int16 *, int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006abc0`

## callees

- `0x180005fa0`
- `0x18002f81c`
- `0x180067d90`
- `0x18006a228`
- `0x18006d7f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006a34d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18006a34d`

## pseudocode

```c
__int64 __fastcall MFProfileInternalParseConcurrencyReferenceGuid(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        struct IMFCameraProfileValidation *a4,
        LPCLSID pclsid,
        unsigned __int16 *lpsz,
        int a7,
        const unsigned __int16 **a8)
{
  struct IMFCameraProfileValidation *v9; // rbx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // r14
  int i; // eax
  __int64 v16; // r13
  __int64 v17; // r8

  v9 = a4;
  if ( a8 )
  {
    *a8 = 0;
    if ( !pclsid )
    {
      v11 = -2147467261;
      v12 = -2147467261;
      if ( !g_wppLevels )
        return v12;
      v13 = 27;
      goto LABEL_4;
    }
    *pclsid = GUID_00000000_0000_0000_0000_000000000000;
    if ( !a2 )
    {
      v11 = -2147024809;
      v12 = -2147024809;
      if ( !g_wppLevels )
        return v12;
      v13 = 28;
      goto LABEL_4;
    }
    if ( !lpsz )
    {
      v11 = -2147024809;
      v12 = -2147024809;
      if ( !g_wppLevels )
        return v12;
      v13 = 29;
      goto LABEL_4;
    }
    v14 = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= a3 )
        goto LABEL_28;
      v16 = i;
      if ( !a2[i] )
        goto LABEL_28;
      if ( a2[i] == 59 )
        break;
    }
    StringCchCopyNW(lpsz, 0x104u, a2, i);
    v12 = CLSIDFromString(lpsz, pclsid);
    if ( (v12 & 0x80000000) == 0 )
    {
      v14 = &a2[v16 + 1];
      if ( (unsigned __int8)byte_18008D62F >= 0x10u )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          32,
          (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
          (_DWORD)a1,
          (__int64)lpsz);
      MFTraceValidation(a4, 4, 0, "profile %S, found concurrency refguid (%S).", a1, lpsz);
      if ( v14 && *v14 )
        goto LABEL_33;
      v9 = a4;
    }
    else
    {
      if ( byte_18008D62F )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          31,
          (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
          (_DWORD)a1,
          (__int64)lpsz);
      v17 = v12;
      v9 = a4;
      MFTraceValidation(
        a4,
        4,
        v17,
        "profile %S, failed to convert concurrency refguid (%S), setting to GUID_NULL.",
        a1,
        lpsz);
      *pclsid = GUID_00000000_0000_0000_0000_000000000000;
    }
LABEL_28:
    if ( byte_18008D62F )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        33,
        (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
        (_DWORD)a1,
        (__int64)a2);
    v11 = MFTraceValidation(v9, 4, 2147944010LL, "profile %S, concurrency information is malformed (%S).", a1, a2);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        return v12;
      v13 = 34;
      goto LABEL_4;
    }
LABEL_33:
    *a8 = v14;
    return v12;
  }
  v11 = -2147467261;
  v12 = -2147467261;
  if ( g_wppLevels )
  {
    v13 = 26;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, 0, v11);
  }
  return v12;
}

```

## disassembly

```asm
0x18006a228  mov     [rsp+arg_18], r9
0x18006a22d  push    rbx
0x18006a22e  push    rbp
0x18006a22f  push    rsi
0x18006a230  push    rdi
0x18006a231  push    r12
0x18006a233  push    r13
0x18006a235  push    r14
0x18006a237  push    r15
0x18006a239  sub     rsp, 38h
0x18006a23d  mov     r12, [rsp+78h+arg_38]
0x18006a245  mov     r15, rcx
0x18006a248  xor     ecx, ecx
0x18006a24a  mov     rbx, r9
0x18006a24d  mov     rsi, rdx
0x18006a250  test    r12, r12
0x18006a253  jnz     short loc_18006A28F
0x18006a255  mov     eax, 80004003h
0x18006a25a  mov     ebx, eax
0x18006a25c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a263  jb      loc_18006A4A3
0x18006a269  lea     edx, [rcx+1Ah]
0x18006a26c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a273  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006a27a  xor     r9d, r9d
0x18006a27d  mov     dword ptr [rsp+78h+var_58], eax
0x18006a281  mov     rcx, [rcx+10h]
0x18006a285  call    WPP_SF_qD
0x18006a28a  jmp     loc_18006A4A3
0x18006a28f  mov     rbp, [rsp+78h+pclsid]
0x18006a297  mov     [r12], rcx
0x18006a29b  test    rbp, rbp
0x18006a29e  jnz     short loc_18006A2B9
0x18006a2a0  mov     eax, 80004003h
0x18006a2a5  mov     ebx, eax
0x18006a2a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a2ae  jb      loc_18006A4A3
0x18006a2b4  lea     edx, [rbp+1Bh]
0x18006a2b7  jmp     short loc_18006A26C
0x18006a2b9  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006a2c0  movdqu  xmmword ptr [rbp+0], xmm0
0x18006a2c5  test    rsi, rsi
0x18006a2c8  jnz     short loc_18006A2E3
0x18006a2ca  mov     eax, 80070057h
0x18006a2cf  mov     ebx, eax
0x18006a2d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a2d8  jb      loc_18006A4A3
0x18006a2de  lea     edx, [rsi+1Ch]
0x18006a2e1  jmp     short loc_18006A26C
0x18006a2e3  mov     rdi, [rsp+78h+lpsz]
0x18006a2eb  test    rdi, rdi
0x18006a2ee  jnz     short loc_18006A30C
0x18006a2f0  mov     eax, 80070057h
0x18006a2f5  mov     ebx, eax
0x18006a2f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a2fe  jb      loc_18006A4A3
0x18006a304  lea     edx, [rdi+1Dh]
0x18006a307  jmp     loc_18006A26C
0x18006a30c  mov     r14, rcx
0x18006a30f  mov     eax, ecx
0x18006a311  cmp     eax, r8d
0x18006a314  jge     loc_18006A432
0x18006a31a  movsxd  r13, eax
0x18006a31d  cmp     [rdx+r13*2], cx
0x18006a322  jz      loc_18006A432
0x18006a328  cmp     word ptr [rdx+r13*2], 3Bh ; ';'
0x18006a32e  jz      short loc_18006A334
0x18006a330  inc     eax
0x18006a332  jmp     short loc_18006A311
0x18006a334  mov     r9, r13; unsigned __int64
0x18006a337  mov     r8, rsi; unsigned __int16 *
0x18006a33a  mov     edx, 104h; unsigned __int64
0x18006a33f  mov     rcx, rdi; unsigned __int16 *
0x18006a342  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18006a347  mov     rdx, rbp; pclsid
0x18006a34a  mov     rcx, rdi; lpsz
0x18006a34d  call    cs:__imp_CLSIDFromString
0x18006a353  mov     ebx, eax
0x18006a355  test    eax, eax
0x18006a357  jns     short loc_18006A3C0
0x18006a359  cmp     cs:byte_18008D62F, 1
0x18006a360  jb      short loc_18006A389
0x18006a362  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a369  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006a370  mov     edx, 1Fh
0x18006a375  mov     [rsp+78h+var_58], rdi
0x18006a37a  mov     r9, r15
0x18006a37d  mov     rcx, [rcx+128h]
0x18006a384  call    WPP_SF_SS
0x18006a389  mov     r8d, ebx
0x18006a38c  mov     [rsp+78h+var_50], rdi
0x18006a391  mov     rbx, [rsp+78h+arg_18]
0x18006a399  lea     r9, aProfileSFailed_1; "profile %S, failed to convert concurren"...
0x18006a3a0  mov     rcx, rbx
0x18006a3a3  mov     [rsp+78h+var_58], r15
0x18006a3a8  mov     edx, 4
0x18006a3ad  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x18006a3b2  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006a3b9  movdqu  xmmword ptr [rbp+0], xmm0
0x18006a3be  jmp     short loc_18006A432
0x18006a3c0  lea     r14, [rsi+2]
0x18006a3c4  lea     r14, [r14+r13*2]
0x18006a3c8  cmp     cs:byte_18008D62F, 10h
0x18006a3cf  jb      short loc_18006A3F8
0x18006a3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3d8  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006a3df  mov     edx, 20h ; ' '
0x18006a3e4  mov     [rsp+78h+var_58], rdi
0x18006a3e9  mov     r9, r15
0x18006a3ec  mov     rcx, [rcx+128h]
0x18006a3f3  call    WPP_SF_SS
0x18006a3f8  mov     rcx, [rsp+78h+arg_18]
0x18006a400  lea     r9, aProfileSFoundC; "profile %S, found concurrency refguid ("...
0x18006a407  xor     r8d, r8d
0x18006a40a  mov     [rsp+78h+var_50], rdi
0x18006a40f  mov     [rsp+78h+var_58], r15
0x18006a414  lea     edx, [r8+4]
0x18006a418  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x18006a41d  xor     ecx, ecx
0x18006a41f  test    r14, r14
0x18006a422  jz      short loc_18006A42A
0x18006a424  cmp     [r14], cx
0x18006a428  jnz     short loc_18006A49F
0x18006a42a  mov     rbx, [rsp+78h+arg_18]
0x18006a432  cmp     cs:byte_18008D62F, 1
0x18006a439  jb      short loc_18006A462
0x18006a43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a442  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006a449  mov     edx, 21h ; '!'
0x18006a44e  mov     [rsp+78h+var_58], rsi
0x18006a453  mov     r9, r15
0x18006a456  mov     rcx, [rcx+128h]
0x18006a45d  call    WPP_SF_SS
0x18006a462  mov     [rsp+78h+var_50], rsi
0x18006a467  lea     r9, aProfileSConcur; "profile %S, concurrency information is "...
0x18006a46e  mov     edx, 4
0x18006a473  mov     [rsp+78h+var_58], r15
0x18006a478  mov     r8d, 8007064Ah
0x18006a47e  mov     rcx, rbx
0x18006a481  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x18006a486  mov     ebx, eax
0x18006a488  test    eax, eax
0x18006a48a  jns     short loc_18006A49F
0x18006a48c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a493  jb      short loc_18006A4A3
0x18006a495  mov     edx, 22h ; '"'
0x18006a49a  jmp     loc_18006A26C
0x18006a49f  mov     [r12], r14
0x18006a4a3  mov     eax, ebx
0x18006a4a5  add     rsp, 38h
0x18006a4a9  pop     r15
0x18006a4ab  pop     r14
0x18006a4ad  pop     r13
0x18006a4af  pop     r12
0x18006a4b1  pop     rdi
0x18006a4b2  pop     rsi
0x18006a4b3  pop     rbp
0x18006a4b4  pop     rbx
0x18006a4b5  retn
```
