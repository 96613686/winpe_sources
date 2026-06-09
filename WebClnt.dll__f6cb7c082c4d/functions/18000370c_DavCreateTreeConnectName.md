# DavCreateTreeConnectName

- ea: `0x18000370c`
- end: `0x180003a95`
- name: `DavCreateTreeConnectName`
- size: `905`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, ULONG, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006d20`

## callees

- `0x18000370c`
- `0x180005568`
- `0x18000b43c`
- `0x18000b564`
- `0x18000b7dc`
- `0x18002cfa0`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x180003808`
- `ntdll!RtlIntegerToUnicodeString` at `0x180003808`
- `ntdll!RtlInitUnicodeString` at `0x1800037e3`
- `ntdll!RtlInitUnicodeString` at `0x1800037e3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003a18`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180003a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003968`
- `KERNEL32!LocalAlloc` at `0x18000393a`
- `KERNEL32!LocalAlloc` at `0x18000393a`

## pseudocode

```c
__int64 __fastcall DavCreateTreeConnectName(__int64 a1, const wchar_t *a2, ULONG a3, struct _UNICODE_STRING *a4)
{
  __int64 v4; // r14
  __int64 v7; // rdi
  unsigned int LogonId; // esi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 v12; // dx
  __int64 v13; // rcx
  unsigned int v14; // ecx
  USHORT v15; // cx
  unsigned __int64 v16; // rcx
  __int16 v17; // di
  __int64 v18; // rdx
  int v19; // ecx
  int Length; // eax
  SIZE_T v21; // rdx
  wchar_t *v22; // rax
  __int64 v23; // rbx
  DWORD LastError; // eax
  size_t MaximumLength; // rdx
  wchar_t *Buffer; // rcx
  size_t v28; // rdx
  wchar_t *v29; // rcx
  struct _LUID DestinationLuid; // [rsp+30h] [rbp-39h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-31h] BYREF
  wchar_t pszDest[8]; // [rsp+48h] [rbp-21h] BYREF
  __int128 v33; // [rsp+58h] [rbp-11h]
  int v34; // [rsp+68h] [rbp-1h]

  v4 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  v34 = 0;
  DestinationString = 0;
  *(_OWORD *)pszDest = 0;
  v33 = 0;
  if ( g_LUIDDeviceMapsEnabled == 1 )
  {
    DestinationLuid = 0;
    LogonId = DavImpersonateAndGetLogonId(&DestinationLuid);
    if ( LogonId )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LogonId;
      v11 = 189;
      goto LABEL_43;
    }
    StringCbPrintfW(pszDest, 0x24u, L"%08x%08x", (unsigned int)DestinationLuid.HighPart, DestinationLuid.LowPart);
    HIWORD(v34) = 0;
    RtlInitUnicodeString(&DestinationString, pszDest);
  }
  else
  {
    DestinationString.MaximumLength = 36;
    DestinationString.Buffer = pszDest;
    RtlIntegerToUnicodeString(a3, 0xAu, &DestinationString);
  }
  LogonId = 87;
  if ( !a4 )
    return LogonId;
  v12 = 50;
  a4->MaximumLength = 50;
  if ( a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    v14 = 2 * v13;
    if ( v14 > 0xFFFF || v14 + 50 > 0xFFFF )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LogonId;
      v11 = 190;
LABEL_43:
      WPP_SF_d(v10[2], v11, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LogonId);
      return LogonId;
    }
    v15 = v14 + 50;
    a4->MaximumLength = v15;
    v12 = v15;
  }
  v16 = 2LL * (unsigned int)v7;
  if ( v16 > 0xFFFF || v16 + v12 > 0xFFFF )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LogonId;
    v11 = 191;
    goto LABEL_43;
  }
  v17 = 2 * v7;
  v18 = (unsigned __int16)(v12 + v17);
  a4->MaximumLength = v18;
  if ( (unsigned __int64)(v18 + 2) > 0xFFFF )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LogonId;
    v11 = 192;
    goto LABEL_43;
  }
  v19 = (unsigned __int16)(v18 + 2);
  Length = DestinationString.Length;
  a4->MaximumLength = v19;
  if ( (unsigned int)(Length + v19) > 0xFFFF )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LogonId;
    v11 = 193;
    goto LABEL_43;
  }
  v21 = (unsigned __int16)(DestinationString.Length + v18 + 2);
  a4->MaximumLength = v21;
  v22 = (wchar_t *)LocalAlloc(0x40u, v21);
  a4->Buffer = v22;
  if ( v22 )
  {
    wmemcpy(v22, L"\\Device\\WebDavRedirector", 24);
    a4->Length = 48;
    if ( a2 )
    {
      StringCbCatW(a4->Buffer, a4->MaximumLength, L"\\");
      MaximumLength = a4->MaximumLength;
      Buffer = a4->Buffer;
      a4->Length += 2;
      StringCbCatW(Buffer, MaximumLength, L";");
      v28 = a4->MaximumLength;
      v29 = a4->Buffer;
      a4->Length += 2;
      StringCbCatW(v29, v28, a2);
      do
        ++v4;
      while ( a2[v4] );
      a4->Length += 2 * v4;
      RtlAppendUnicodeStringToString(a4, &DestinationString);
    }
    StringCbCatW(a4->Buffer, a4->MaximumLength, (STRSAFE_LPCWSTR)(a1 + 2));
    a4->Length += v17 - 2;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v23, 194, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
    }
    return 8;
  }
}

```

## disassembly

```asm
0x18000370c  push    rbp
0x18000370e  push    rbx
0x18000370f  push    rsi
0x180003710  push    rdi
0x180003711  push    r12
0x180003713  push    r13
0x180003715  push    r14
0x180003717  push    r15
0x180003719  lea     rbp, [rsp-1Fh]
0x18000371e  sub     rsp, 88h
0x180003725  mov     rax, cs:__security_cookie
0x18000372c  xor     rax, rsp
0x18000372f  mov     [rbp+57h+var_50], rax
0x180003733  or      r14, 0FFFFFFFFFFFFFFFFh
0x180003737  mov     rbx, r9
0x18000373a  mov     r13, rcx
0x18000373d  mov     rdi, r14
0x180003740  xor     ecx, ecx
0x180003742  mov     r9d, r8d
0x180003745  mov     r15, rdx
0x180003748  inc     rdi
0x18000374b  cmp     [r13+rdi*2+0], cx
0x180003751  jnz     short loc_180003748
0x180003753  xor     eax, eax
0x180003755  xorps   xmm1, xmm1
0x180003758  xorps   xmm0, xmm0
0x18000375b  mov     [rbp+57h+var_58], eax
0x18000375e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180003762  lea     r12d, [rax+1]
0x180003766  cmp     cs:g_LUIDDeviceMapsEnabled, r12d
0x18000376d  movups  xmmword ptr [rbp+57h+pszDest], xmm1
0x180003771  movups  [rbp+57h+var_68], xmm1
0x180003775  jnz     short loc_1800037EB
0x180003777  mov     qword ptr [rbp+57h+DestinationLuid.LowPart], rcx
0x18000377b  lea     rcx, [rbp+57h+DestinationLuid]; DestinationLuid
0x18000377f  call    DavImpersonateAndGetLogonId
0x180003784  mov     esi, eax
0x180003786  test    eax, eax
0x180003788  jz      short loc_1800037B5
0x18000378a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003791  lea     rdx, WPP_GLOBAL_Control
0x180003798  cmp     rcx, rdx
0x18000379b  jz      loc_180003A73
0x1800037a1  test    [rcx+1Ch], r12b
0x1800037a5  jz      loc_180003A73
0x1800037ab  mov     edx, 0BDh
0x1800037b0  jmp     loc_180003A60
0x1800037b5  mov     eax, [rbp+57h+DestinationLuid.LowPart]
0x1800037b8  lea     r8, a08x08x; "%08x%08x"
0x1800037bf  mov     r9d, [rbp+57h+DestinationLuid.HighPart]
0x1800037c3  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800037c7  mov     edx, 24h ; '$'; cbDest
0x1800037cc  mov     [rsp+0C0h+var_A0], eax
0x1800037d0  call    StringCbPrintfW
0x1800037d5  xor     eax, eax
0x1800037d7  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1800037db  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800037df  mov     word ptr [rbp+57h+var_58+2], ax
0x1800037e3  call    cs:__imp_RtlInitUnicodeString
0x1800037e9  jmp     short loc_18000380E
0x1800037eb  mov     eax, 24h ; '$'
0x1800037f0  lea     r8, [rbp+57h+DestinationString]; String
0x1800037f4  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x1800037f8  mov     edx, 0Ah; Base
0x1800037fd  lea     rax, [rbp+57h+pszDest]
0x180003801  mov     ecx, r9d; Value
0x180003804  mov     [rbp+57h+DestinationString.Buffer], rax
0x180003808  call    cs:__imp_RtlIntegerToUnicodeString
0x18000380e  xor     eax, eax
0x180003810  mov     esi, 57h ; 'W'
0x180003815  test    rbx, rbx
0x180003818  jz      loc_180003A73
0x18000381e  lea     edx, [rsi-25h]
0x180003821  mov     r8d, 0FFFFh
0x180003827  mov     [rbx+2], dx
0x18000382b  test    r15, r15
0x18000382e  jz      short loc_180003856
0x180003830  mov     rcx, r14
0x180003833  inc     rcx
0x180003836  cmp     [r15+rcx*2], ax
0x18000383b  jnz     short loc_180003833
0x18000383d  add     ecx, ecx
0x18000383f  cmp     ecx, r8d
0x180003842  ja      short loc_1800038BA
0x180003844  lea     eax, [rcx+32h]
0x180003847  cmp     eax, r8d
0x18000384a  ja      short loc_1800038BA
0x18000384c  add     cx, dx
0x18000384f  mov     [rbx+2], cx
0x180003853  movzx   edx, cx
0x180003856  mov     ecx, edi
0x180003858  add     rcx, rcx
0x18000385b  cmp     rcx, r8
0x18000385e  ja      loc_180003A42
0x180003864  movzx   eax, dx
0x180003867  add     rax, rcx
0x18000386a  cmp     rax, r8
0x18000386d  ja      loc_180003A42
0x180003873  add     di, di
0x180003876  mov     r9d, 2
0x18000387c  lea     eax, [rdx+rdi]
0x18000387f  movzx   edx, ax
0x180003882  mov     [rbx+2], dx
0x180003886  lea     rax, [r9+rdx]
0x18000388a  cmp     rax, r8
0x18000388d  jbe     short loc_1800038E5
0x18000388f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003896  lea     rdx, WPP_GLOBAL_Control
0x18000389d  cmp     rcx, rdx
0x1800038a0  jz      loc_180003A73
0x1800038a6  test    [rcx+1Ch], r12b
0x1800038aa  jz      loc_180003A73
0x1800038b0  mov     edx, 0C0h
0x1800038b5  jmp     loc_180003A60
0x1800038ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038c1  lea     rdx, WPP_GLOBAL_Control
0x1800038c8  cmp     rcx, rdx
0x1800038cb  jz      loc_180003A73
0x1800038d1  test    [rcx+1Ch], r12b
0x1800038d5  jz      loc_180003A73
0x1800038db  mov     edx, 0BEh
0x1800038e0  jmp     loc_180003A60
0x1800038e5  lea     eax, [r9+rdx]
0x1800038e9  movzx   ecx, ax
0x1800038ec  movzx   eax, [rbp+57h+DestinationString.Length]
0x1800038f0  mov     [rbx+2], cx
0x1800038f4  add     ecx, eax
0x1800038f6  cmp     ecx, r8d
0x1800038f9  jbe     short loc_180003926
0x1800038fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003902  lea     rdx, WPP_GLOBAL_Control
0x180003909  cmp     rcx, rdx
0x18000390c  jz      loc_180003A73
0x180003912  test    [rcx+1Ch], r12b
0x180003916  jz      loc_180003A73
0x18000391c  mov     edx, 0C1h
0x180003921  jmp     loc_180003A60
0x180003926  add     dx, [rbp+57h+DestinationString.Length]
0x18000392a  mov     ecx, 40h ; '@'; uFlags
0x18000392f  add     dx, r9w
0x180003933  movzx   edx, dx; uBytes
0x180003936  mov     [rbx+2], dx
0x18000393a  call    cs:__imp_LocalAlloc
0x180003940  xor     esi, esi
0x180003942  mov     [rbx+8], rax
0x180003946  test    rax, rax
0x180003949  jnz     short loc_18000398F
0x18000394b  mov     rbx, cs:WPP_GLOBAL_Control
0x180003952  lea     rdx, WPP_GLOBAL_Control
0x180003959  cmp     rbx, rdx
0x18000395c  jz      short loc_180003985
0x18000395e  test    [rbx+1Ch], r12b
0x180003962  jz      short loc_180003985
0x180003964  mov     rbx, [rbx+10h]
0x180003968  call    cs:__imp_GetLastError
0x18000396e  mov     edx, 0C2h
0x180003973  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000397a  mov     r9d, eax
0x18000397d  mov     rcx, rbx
0x180003980  call    WPP_SF_d
0x180003985  mov     eax, 8
0x18000398a  jmp     loc_180003A75
0x18000398f  movups  xmm0, xmmword ptr cs:aDeviceWebdavre_1; "\\Device\\WebDavRedirector"
0x180003996  movups  xmmword ptr [rax], xmm0
0x180003999  movups  xmm1, xmmword ptr cs:aDeviceWebdavre_1+10h; "WebDavRedirector"
0x1800039a0  movups  xmmword ptr [rax+10h], xmm1
0x1800039a4  movups  xmm0, xmmword ptr cs:aDeviceWebdavre_1+20h; "director"
0x1800039ab  movups  xmmword ptr [rax+20h], xmm0
0x1800039af  mov     word ptr [rbx], 30h ; '0'
0x1800039b4  test    r15, r15
0x1800039b7  jz      short loc_180003A20
0x1800039b9  movzx   edx, word ptr [rbx+2]; cbDest
0x1800039bd  lea     r8, pszSrc; "\\"
0x1800039c4  mov     rcx, [rbx+8]; pszDest
0x1800039c8  call    StringCbCatW
0x1800039cd  movzx   edx, word ptr [rbx+2]; cbDest
0x1800039d1  lea     r8, asc_180031274; ";"
0x1800039d8  mov     rcx, [rbx+8]; pszDest
0x1800039dc  mov     r12d, 2
0x1800039e2  add     [rbx], r12w
0x1800039e6  call    StringCbCatW
0x1800039eb  movzx   edx, word ptr [rbx+2]; cbDest
0x1800039ef  mov     r8, r15; pszSrc
0x1800039f2  mov     rcx, [rbx+8]; pszDest
0x1800039f6  add     [rbx], r12w
0x1800039fa  call    StringCbCatW
0x1800039ff  inc     r14
0x180003a02  cmp     [r15+r14*2], si
0x180003a07  jnz     short loc_1800039FF
0x180003a09  add     r14w, r14w
0x180003a0d  lea     rdx, [rbp+57h+DestinationString]; Source
0x180003a11  add     [rbx], r14w
0x180003a15  mov     rcx, rbx; Destination
0x180003a18  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003a1e  jmp     short loc_180003A26
0x180003a20  mov     r12d, 2
0x180003a26  movzx   edx, word ptr [rbx+2]; cbDest
0x180003a2a  lea     r8, [r13+2]; pszSrc
0x180003a2e  mov     rcx, [rbx+8]; pszDest
0x180003a32  call    StringCbCatW
0x180003a37  sub     di, r12w
0x180003a3b  add     [rbx], di
0x180003a3e  xor     eax, eax
0x180003a40  jmp     short loc_180003A75
0x180003a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a49  lea     rdx, WPP_GLOBAL_Control
0x180003a50  cmp     rcx, rdx
0x180003a53  jz      short loc_180003A73
0x180003a55  test    [rcx+1Ch], r12b
0x180003a59  jz      short loc_180003A73
0x180003a5b  mov     edx, 0BFh
0x180003a60  mov     rcx, [rcx+10h]
0x180003a64  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003a6b  mov     r9d, esi
0x180003a6e  call    WPP_SF_d
0x180003a73  mov     eax, esi
0x180003a75  mov     rcx, [rbp+57h+var_50]
0x180003a79  xor     rcx, rsp; StackCookie
0x180003a7c  call    __security_check_cookie
0x180003a81  add     rsp, 88h
0x180003a88  pop     r15
0x180003a8a  pop     r14
0x180003a8c  pop     r13
0x180003a8e  pop     r12
0x180003a90  pop     rdi
0x180003a91  pop     rsi
0x180003a92  pop     rbx
0x180003a93  pop     rbp
0x180003a94  retn
```
