# SecurityContext::GetSecurityInfo(_DAB_SID_INFO * *,void * *,ulong *,_SID_AND_ATTRIBUTES * *)

- ea: `0x180003840`
- end: `0x180003c0a`
- name: `?GetSecurityInfo@SecurityContext@@QEAAJPEAPEAU_DAB_SID_INFO@@PEAPEAXPEAKPEAPEAU_SID_AND_ATTRIBUTES@@@Z`
- size: `970`
- prototype: `__int64 __fastcall(SecurityContext *__hidden this, struct _DAB_SID_INFO **, void **, unsigned int *, struct _SID_AND_ATTRIBUTES **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003100`
- `0x18001a7d8`
- `0x18001aba0`

## callees

- `0x1800020dc`
- `0x180003840`
- `0x180010094`
- `0x180010208`
- `0x18001022b`
- `0x18001025c`
- `0x180020c02`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003b6b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003b74`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003bbd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003b6b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003b74`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003bbd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003b89`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003bd1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003b89`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000397b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000397b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800038c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180003971`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180003aa9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800038c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180003971`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180003aa9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000392f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003994`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003ab7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000392f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003994`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003ab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000393e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003aeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000393e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003aeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b5c`
- `ntdll!RtlCopySid` at `0x1800039c1`
- `ntdll!RtlCopySid` at `0x180003ae1`
- `ntdll!RtlCopySid` at `0x1800039c1`
- `ntdll!RtlCopySid` at `0x180003ae1`

## string_xrefs

- `0x1800038ca`: `ConvertStringSidToSid failed`

## pseudocode

```c
__int64 __fastcall SecurityContext::GetSecurityInfo(
        SecurityContext *this,
        struct _DAB_SID_INFO **a2,
        void **a3,
        unsigned int *a4,
        struct _SID_AND_ATTRIBUTES **a5)
{
  void **v5; // rax
  signed int v10; // ebx
  _OWORD *v11; // rdi
  struct _SID_AND_ATTRIBUTES *v12; // r12
  void *v13; // r13
  const WCHAR **v14; // rcx
  const WCHAR *v15; // rcx
  _OWORD *v16; // rax
  void *v17; // rax
  PSID v18; // rcx
  LPCWSTR **v19; // rcx
  LPCWSTR *v20; // rcx
  signed int LastError; // eax
  void *v22; // rax
  __int64 v23; // rax
  struct _SID_AND_ATTRIBUTES **v24; // r15
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  struct _SID_AND_ATTRIBUTES *v28; // rax
  unsigned int v29; // r15d
  __int64 v30; // rdx
  const WCHAR *v31; // rcx
  void *v32; // rax
  __int64 v33; // rax
  unsigned int v34; // edi
  PSID v35; // rcx
  PSID pSid; // [rsp+20h] [rbp-58h] BYREF
  PSID Sid; // [rsp+28h] [rbp-50h] BYREF
  void *v38; // [rsp+30h] [rbp-48h]
  __int64 v39; // [rsp+38h] [rbp-40h]
  struct _SID_AND_ATTRIBUTES pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  const char *DestinationSidLength; // [rsp+A0h] [rbp+28h] BYREF
  void **v42; // [rsp+B0h] [rbp+38h]

  v42 = a3;
  v5 = a3;
  pSid = 0;
  if ( !*((_BYTE *)this + 16) )
    return 2147500037LL;
  v10 = -2147024882;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( a2 )
  {
    v14 = *(const WCHAR ***)this;
    if ( v14 )
    {
      v15 = *v14;
      Sid = 0;
      if ( !ConvertStringSidToSidW(v15, &Sid) )
      {
        DestinationSidLength = "ConvertStringSidToSid failed";
        exception::exception((exception *)&pExceptionObject, &DestinationSidLength);
        throw (exception *)&pExceptionObject;
      }
      v16 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v16;
      if ( !v16 || (*v16 = 0, v17 = (void *)CopySID(Sid), (*((_QWORD *)v11 + 1) = v17) == 0) )
      {
        LocalFree(Sid);
        goto LABEL_44;
      }
      *(_DWORD *)v11 = GetLengthSid(v17);
      v18 = Sid;
      *a2 = (struct _DAB_SID_INFO *)v11;
      LocalFree(v18);
      v5 = v42;
    }
    else
    {
      *a2 = 0;
    }
  }
  if ( v5 )
  {
    v19 = (LPCWSTR **)*((_QWORD *)this + 1);
    if ( v19 && (v20 = *v19) != 0 )
    {
      if ( !ConvertStringSidToSidW(*v20, &pSid) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          goto LABEL_39;
        goto LABEL_40;
      }
      LODWORD(DestinationSidLength) = GetLengthSid(pSid);
      v22 = operator new[]((unsigned int)DestinationSidLength, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v22;
      if ( !v22 )
        goto LABEL_44;
      RtlCopySid((ULONG)DestinationSidLength, v22, pSid);
      LocalFree(pSid);
      pSid = 0;
      *v42 = v13;
    }
    else
    {
      *v5 = 0;
    }
  }
  if ( a4 )
  {
    v23 = *((_QWORD *)this + 1);
    if ( v23 )
      *a4 = *(_DWORD *)(v23 + 16);
    else
      *a4 = 0;
  }
  v24 = a5;
  if ( !a5 )
    return 0;
  v25 = *((_QWORD *)this + 1);
  if ( !v25 || (v26 = *(unsigned int *)(v25 + 16), !(_DWORD)v26) || !*(_QWORD *)(v25 + 8) )
  {
    *a5 = 0;
    return 0;
  }
  v27 = 16 * v26;
  if ( !is_mul_ok(v26, 0x10u) )
    v27 = -1;
  v28 = (struct _SID_AND_ATTRIBUTES *)operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v28;
  if ( !v28 )
    goto LABEL_45;
  memset_0(v28, 0, 16LL * *(unsigned int *)(*((_QWORD *)this + 1) + 16LL));
  v29 = 0;
  v30 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL);
  v39 = v30;
  while ( 1 )
  {
    if ( v29 >= *(_DWORD *)(*((_QWORD *)this + 1) + 16LL) )
    {
      *a5 = v12;
      return 0;
    }
    if ( *(_QWORD *)v30 )
      break;
LABEL_37:
    ++v29;
  }
  v31 = **(const WCHAR ***)v30;
  *(_QWORD *)&pExceptionObject.Attributes = *(unsigned int *)(v30 + 8);
  if ( ConvertStringSidToSidW(v31, &pSid) )
  {
    LODWORD(DestinationSidLength) = GetLengthSid(pSid);
    v32 = operator new[]((unsigned int)DestinationSidLength, (const struct std::nothrow_t *)&std::nothrow);
    v38 = v32;
    if ( !v32 )
      goto LABEL_44;
    RtlCopySid((ULONG)DestinationSidLength, v32, pSid);
    LocalFree(pSid);
    v30 = v39;
    pExceptionObject.Sid = v38;
    pSid = 0;
    v12[v29] = pExceptionObject;
    goto LABEL_37;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError <= 0 )
    goto LABEL_40;
LABEL_39:
  v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_40:
  if ( v10 < 0 )
  {
LABEL_44:
    v24 = a5;
LABEL_45:
    if ( pSid )
      LocalFree(pSid);
    if ( v11 )
    {
      operator delete(*((void **)v11 + 1));
      operator delete(v11);
      *a2 = 0;
    }
    if ( v13 )
    {
      operator delete[](v13);
      *v42 = 0;
    }
    if ( v12 )
    {
      v33 = *((_QWORD *)this + 1);
      if ( v33 )
      {
        v34 = 0;
        if ( *(_DWORD *)(v33 + 16) )
        {
          do
          {
            v35 = v12[v34].Sid;
            if ( v35 )
              operator delete(v35);
            ++v34;
          }
          while ( v34 < *(_DWORD *)(*((_QWORD *)this + 1) + 16LL) );
        }
      }
      operator delete[](v12);
      *v24 = 0;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003840  mov     [rsp-20h+arg_10], r8
0x180003845  push    rbp
0x180003846  push    rsi
0x180003847  push    r14
0x180003849  push    r15
0x18000384b  mov     rbp, rsp
0x18000384e  sub     rsp, 78h
0x180003852  mov     rax, r8
0x180003855  mov     r15, r9
0x180003858  xor     r8d, r8d
0x18000385b  mov     r14, rdx
0x18000385e  mov     rsi, rcx
0x180003861  mov     [rbp+pSid], r8
0x180003865  cmp     [rcx+10h], r8b
0x180003869  jnz     short loc_18000387B
0x18000386b  mov     eax, 80004005h
0x180003870  add     rsp, 78h
0x180003874  pop     r15
0x180003876  pop     r14
0x180003878  pop     rsi
0x180003879  pop     rbp
0x18000387a  retn
0x18000387b  mov     [rsp+78h+arg_8], rbx
0x180003883  mov     ebx, 8007000Eh
0x180003888  mov     [rsp+78h+var_8], rdi
0x18000388d  mov     rdi, r8
0x180003890  mov     [rsp+78h+var_10], r12
0x180003895  mov     r12, r8
0x180003898  mov     [rsp+78h+var_18], r13
0x18000389d  mov     r13, r8
0x1800038a0  test    r14, r14
0x1800038a3  jz      loc_180003950
0x1800038a9  mov     rcx, [rcx]
0x1800038ac  test    rcx, rcx
0x1800038af  jz      loc_18000394D
0x1800038b5  mov     rcx, [rcx]; StringSid
0x1800038b8  lea     rdx, [rbp+Sid]; Sid
0x1800038bc  mov     [rbp+Sid], r8
0x1800038c0  call    cs:__imp_ConvertStringSidToSidW
0x1800038c6  test    eax, eax
0x1800038c8  jnz     short loc_1800038F3
0x1800038ca  lea     rax, aConvertstrings; "ConvertStringSidToSid failed"
0x1800038d1  lea     rdx, [rbp+DestinationSidLength]; char **
0x1800038d5  mov     [rbp+DestinationSidLength], rax
0x1800038d9  lea     rcx, [rbp+pExceptionObject]; this
0x1800038dd  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x1800038e2  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800038e9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800038ed  call    _CxxThrowException_0
0x1800038f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800038fa  mov     ecx, 10h; unsigned __int64
0x1800038ff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003904  mov     rdi, rax
0x180003907  test    rax, rax
0x18000390a  jz      loc_180003B45
0x180003910  xorps   xmm0, xmm0
0x180003913  movups  xmmword ptr [rax], xmm0
0x180003916  mov     rcx, [rbp+Sid]; SourceSid
0x18000391a  call    CopySID
0x18000391f  mov     [rdi+8], rax
0x180003923  test    rax, rax
0x180003926  jz      loc_180003B45
0x18000392c  mov     rcx, rax; pSid
0x18000392f  call    cs:__imp_GetLengthSid
0x180003935  mov     [rdi], eax
0x180003937  mov     rcx, [rbp+Sid]; hMem
0x18000393b  mov     [r14], rdi
0x18000393e  call    cs:__imp_LocalFree
0x180003944  mov     rax, [rbp+arg_10]
0x180003948  xor     r8d, r8d
0x18000394b  jmp     short loc_180003950
0x18000394d  mov     [rdx], r8
0x180003950  test    rax, rax
0x180003953  jz      loc_1800039E4
0x180003959  mov     rcx, [rsi+8]
0x18000395d  test    rcx, rcx
0x180003960  jz      short loc_1800039E1
0x180003962  mov     rcx, [rcx]
0x180003965  test    rcx, rcx
0x180003968  jz      short loc_1800039E1
0x18000396a  mov     rcx, [rcx]; StringSid
0x18000396d  lea     rdx, [rbp+pSid]; Sid
0x180003971  call    cs:__imp_ConvertStringSidToSidW
0x180003977  test    eax, eax
0x180003979  jnz     short loc_180003990
0x18000397b  call    cs:__imp_GetLastError
0x180003981  mov     ebx, eax
0x180003983  test    eax, eax
0x180003985  jg      loc_180003B27
0x18000398b  jmp     loc_180003B30
0x180003990  mov     rcx, [rbp+pSid]; pSid
0x180003994  call    cs:__imp_GetLengthSid
0x18000399a  mov     ecx, eax; unsigned __int64
0x18000399c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800039a3  mov     dword ptr [rbp+DestinationSidLength], eax
0x1800039a6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800039ab  mov     r13, rax
0x1800039ae  test    rax, rax
0x1800039b1  jz      loc_180003B4F
0x1800039b7  mov     r8, [rbp+pSid]; SourceSid
0x1800039bb  mov     rdx, rax; DestinationSid
0x1800039be  mov     ecx, dword ptr [rbp+DestinationSidLength]; DestinationSidLength
0x1800039c1  call    cs:__imp_RtlCopySid
0x1800039c7  mov     rcx, [rbp+pSid]; hMem
0x1800039cb  call    cs:__imp_LocalFree
0x1800039d1  mov     rax, [rbp+arg_10]
0x1800039d5  xor     r8d, r8d
0x1800039d8  mov     [rbp+pSid], r8
0x1800039dc  mov     [rax], r13
0x1800039df  jmp     short loc_1800039E4
0x1800039e1  mov     [rax], r8
0x1800039e4  test    r15, r15
0x1800039e7  jz      short loc_1800039FD
0x1800039e9  mov     rax, [rsi+8]
0x1800039ed  test    rax, rax
0x1800039f0  jz      short loc_1800039FA
0x1800039f2  mov     eax, [rax+10h]
0x1800039f5  mov     [r15], eax
0x1800039f8  jmp     short loc_1800039FD
0x1800039fa  mov     [r15], r8d
0x1800039fd  mov     r15, [rbp+arg_20]
0x180003a01  test    r15, r15
0x180003a04  jz      loc_180003BE3
0x180003a0a  mov     rax, [rsi+8]
0x180003a0e  test    rax, rax
0x180003a11  jz      loc_180003BE0
0x180003a17  mov     ecx, [rax+10h]
0x180003a1a  test    ecx, ecx
0x180003a1c  jz      loc_180003BE0
0x180003a22  cmp     [rax+8], r12
0x180003a26  jz      loc_180003BE0
0x180003a2c  mov     eax, 10h
0x180003a31  mul     rcx
0x180003a34  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003a3b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003a42  cmovb   rax, rcx
0x180003a46  mov     rcx, rax; unsigned __int64
0x180003a49  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003a4e  mov     r12, rax
0x180003a51  test    rax, rax
0x180003a54  jz      loc_180003B53
0x180003a5a  mov     rcx, [rsi+8]
0x180003a5e  xor     edx, edx; Val
0x180003a60  mov     r8d, [rcx+10h]
0x180003a64  mov     rcx, rax; void *
0x180003a67  shl     r8, 4; Size
0x180003a6b  call    memset_0
0x180003a70  mov     rcx, [rsi+8]
0x180003a74  xor     r8d, r8d
0x180003a77  mov     r15d, r8d
0x180003a7a  mov     rdx, [rcx+8]
0x180003a7e  mov     [rbp+var_40], rdx
0x180003a82  mov     rax, [rsi+8]
0x180003a86  cmp     r15d, [rax+10h]
0x180003a8a  jnb     loc_180003B39
0x180003a90  mov     rcx, [rdx]
0x180003a93  test    rcx, rcx
0x180003a96  jz      short loc_180003B13
0x180003a98  mov     eax, [rdx+8]
0x180003a9b  lea     rdx, [rbp+pSid]; Sid
0x180003a9f  mov     rcx, [rcx]; StringSid
0x180003aa2  mov     dword ptr [rbp+pExceptionObject+0Ch], r8d
0x180003aa6  mov     [rbp+pExceptionObject.Attributes], eax
0x180003aa9  call    cs:__imp_ConvertStringSidToSidW
0x180003aaf  test    eax, eax
0x180003ab1  jz      short loc_180003B1B
0x180003ab3  mov     rcx, [rbp+pSid]; pSid
0x180003ab7  call    cs:__imp_GetLengthSid
0x180003abd  mov     ecx, eax; unsigned __int64
0x180003abf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003ac6  mov     dword ptr [rbp+DestinationSidLength], eax
0x180003ac9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003ace  mov     [rbp+var_48], rax
0x180003ad2  test    rax, rax
0x180003ad5  jz      short loc_180003B4F
0x180003ad7  mov     r8, [rbp+pSid]; SourceSid
0x180003adb  mov     rdx, rax; DestinationSid
0x180003ade  mov     ecx, dword ptr [rbp+DestinationSidLength]; DestinationSidLength
0x180003ae1  call    cs:__imp_RtlCopySid
0x180003ae7  mov     rcx, [rbp+pSid]; hMem
0x180003aeb  call    cs:__imp_LocalFree
0x180003af1  mov     rax, [rbp+var_48]
0x180003af5  xor     r8d, r8d
0x180003af8  mov     rdx, [rbp+var_40]
0x180003afc  mov     [rbp+pExceptionObject.Sid], rax
0x180003b00  movups  xmm0, xmmword ptr [rbp+pExceptionObject.Sid]
0x180003b04  mov     eax, r15d
0x180003b07  add     rax, rax
0x180003b0a  mov     [rbp+pSid], r8
0x180003b0e  movups  xmmword ptr [r12+rax*8], xmm0
0x180003b13  inc     r15d
0x180003b16  jmp     loc_180003A82
0x180003b1b  call    cs:__imp_GetLastError
0x180003b21  mov     ebx, eax
0x180003b23  test    eax, eax
0x180003b25  jle     short loc_180003B30
0x180003b27  movzx   ebx, ax
0x180003b2a  or      ebx, 80070000h
0x180003b30  test    ebx, ebx
0x180003b32  js      short loc_180003B4F
0x180003b34  jmp     loc_180003BE6
0x180003b39  mov     rax, [rbp+arg_20]
0x180003b3d  mov     [rax], r12
0x180003b40  jmp     loc_180003BE3
0x180003b45  mov     rcx, [rbp+Sid]; hMem
0x180003b49  call    cs:__imp_LocalFree
0x180003b4f  mov     r15, [rbp+arg_20]
0x180003b53  mov     rcx, [rbp+pSid]; hMem
0x180003b57  test    rcx, rcx
0x180003b5a  jz      short loc_180003B62
0x180003b5c  call    cs:__imp_LocalFree
0x180003b62  test    rdi, rdi
0x180003b65  jz      short loc_180003B81
0x180003b67  mov     rcx, [rdi+8]
0x180003b6b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003b71  mov     rcx, rdi
0x180003b74  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003b7a  mov     qword ptr [r14], 0
0x180003b81  test    r13, r13
0x180003b84  jz      short loc_180003B9A
0x180003b86  mov     rcx, r13
0x180003b89  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003b8f  mov     rax, [rbp+arg_10]
0x180003b93  mov     qword ptr [rax], 0
0x180003b9a  test    r12, r12
0x180003b9d  jz      short loc_180003BE6
0x180003b9f  mov     rax, [rsi+8]
0x180003ba3  test    rax, rax
0x180003ba6  jz      short loc_180003BCE
0x180003ba8  xor     edi, edi
0x180003baa  cmp     [rax+10h], edi
0x180003bad  jbe     short loc_180003BCE
0x180003baf  mov     eax, edi
0x180003bb1  add     rax, rax
0x180003bb4  mov     rcx, [r12+rax*8]
0x180003bb8  test    rcx, rcx
0x180003bbb  jz      short loc_180003BC3
0x180003bbd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003bc3  mov     rax, [rsi+8]
0x180003bc7  inc     edi
0x180003bc9  cmp     edi, [rax+10h]
0x180003bcc  jb      short loc_180003BAF
0x180003bce  mov     rcx, r12
0x180003bd1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003bd7  mov     qword ptr [r15], 0
0x180003bde  jmp     short loc_180003BE6
0x180003be0  mov     [r15], r8
0x180003be3  mov     ebx, r8d
0x180003be6  mov     r12, [rsp+78h+var_10]
0x180003beb  mov     eax, ebx
0x180003bed  mov     rbx, [rsp+78h+arg_8]
0x180003bf5  mov     rdi, [rsp+78h+var_8]
0x180003bfa  mov     r13, [rsp+78h+var_18]
0x180003bff  add     rsp, 78h
0x180003c03  pop     r15
0x180003c05  pop     r14
0x180003c07  pop     rsi
0x180003c08  pop     rbp
0x180003c09  retn
```
