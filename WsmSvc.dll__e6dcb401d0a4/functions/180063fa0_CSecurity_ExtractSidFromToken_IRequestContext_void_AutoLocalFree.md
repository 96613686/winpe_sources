# CSecurity::ExtractSidFromToken(IRequestContext *,void *,AutoLocalFree &)

- ea: `0x180063fa0`
- end: `0x18006423c`
- name: `?ExtractSidFromToken@CSecurity@@SAHPEAVIRequestContext@@PEAXAEAVAutoLocalFree@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(struct IRequestContext *, HANDLE TokenHandle, struct AutoLocalFree *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b9c0`
- `0x1800646b0`
- `0x180089544`
- `0x18009a418`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18004a900`
- `0x180063fa0`
- `0x180064250`
- `0x180112380`
- `0x1801123a8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006403a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006412d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800641d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006403a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006412d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800641d0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180064182`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180064182`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064030`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064123`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064030`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064123`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800640da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800640da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800641c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800641c6`

## string_xrefs

- `0x1800640bd`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecurity::ExtractSidFromToken(struct IRequestContext *a1, HANDLE TokenHandle, void **a3)
{
  DWORD LastError; // r14d
  unsigned int v8; // esi
  CHeap *v9; // rcx
  DWORD v10; // eax
  DWORD v11; // edi
  SIZE_T v12; // rdi
  CHeap *v13; // rcx
  void **v14; // rdi
  void *Handle; // rax
  DWORD v16; // eax
  DWORD v17; // edi
  __int64 v18; // rdx
  void *v19; // rdi
  DWORD v20; // eax
  DWORD v21; // edi
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  void **v23; // [rsp+78h] [rbp+20h] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 1079, L"1079", 0x54Fu, 0);
    return 0;
  }
  if ( !TokenHandle )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\sec.cpp", 1080, L"1080", 0x54Fu, a1);
    return 0;
  }
  AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(a3);
  *a3 = 0;
  LastError = 0;
  TokenInformationLength = 0;
  v8 = 1;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v10);
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v11);
      return 0;
    }
  }
  v12 = TokenInformationLength;
  if ( CHeap::GetHandle(v9) )
  {
    Handle = CHeap::GetHandle(v13);
    v14 = (void **)HeapAlloc(Handle, 0, v12);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    v14 = 0;
  }
  v23 = v14;
  if ( !v14 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 24LL))(a1);
LABEL_17:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v23);
    return 0;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v14, TokenInformationLength, &TokenInformationLength) )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v16);
    v18 = v17;
LABEL_23:
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 72LL))(a1, v18);
    goto LABEL_17;
  }
  v19 = *v14;
  if ( !IsValidSid(v19) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
    v18 = LastError;
    goto LABEL_23;
  }
  if ( !ConvertSidToStringSidW(v19, (LPWSTR *)a3) )
  {
    v20 = GetLastError();
    v21 = v20;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids, v20);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v21);
    v8 = 0;
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v23);
  return v8;
}

```

## disassembly

```asm
0x180063fa0  mov     [rsp+arg_8], rbx
0x180063fa5  push    rbp
0x180063fa6  push    rsi
0x180063fa7  push    rdi
0x180063fa8  push    r14
0x180063faa  push    r15
0x180063fac  sub     rsp, 30h
0x180063fb0  mov     r15, r8
0x180063fb3  mov     rbp, rdx
0x180063fb6  mov     rbx, rcx
0x180063fb9  test    rcx, rcx
0x180063fbc  jnz     short loc_180063FE8
0x180063fbe  mov     [rsp+58h+ReturnLength], rcx; struct IRequestContext *
0x180063fc3  lea     r8, a1079; "1079"
0x180063fca  mov     edx, 437h; unsigned int
0x180063fcf  mov     r9d, 54Fh; unsigned int
0x180063fd5  lea     rcx, aOnecoreAdminWm_142; "onecore\\admin\\wmi\\wmx\\stdlib\\sec.c"...
0x180063fdc  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180063fe1  xor     eax, eax
0x180063fe3  jmp     loc_18006422B
0x180063fe8  test    rbp, rbp
0x180063feb  jnz     short loc_180064000
0x180063fed  mov     [rsp+58h+ReturnLength], rbx
0x180063ff2  lea     r8, a1080; "1080"
0x180063ff9  mov     edx, 438h
0x180063ffe  jmp     short loc_180063FCF
0x180064000  mov     rcx, r15; void *
0x180064003  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x180064008  mov     qword ptr [r15], 0
0x18006400f  xor     r14d, r14d
0x180064012  mov     [rsp+58h+TokenInformationLength], r14d
0x180064017  lea     rax, [rsp+58h+TokenInformationLength]
0x18006401c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180064021  xor     r9d, r9d; TokenInformationLength
0x180064024  xor     r8d, r8d; TokenInformation
0x180064027  lea     esi, [r14+1]
0x18006402b  mov     edx, esi; TokenInformationClass
0x18006402d  mov     rcx, rbp; TokenHandle
0x180064030  call    cs:__imp_GetTokenInformation
0x180064036  test    eax, eax
0x180064038  jnz     short loc_180064098
0x18006403a  call    cs:__imp_GetLastError
0x180064040  mov     r14d, eax
0x180064043  cmp     eax, 7Ah ; 'z'
0x180064046  jz      short loc_180064098
0x180064048  call    cs:__imp_GetLastError
0x18006404e  mov     edi, eax
0x180064050  lea     rdx, WPP_GLOBAL_Control
0x180064057  mov     rcx, cs:WPP_GLOBAL_Control
0x18006405e  cmp     rcx, rdx
0x180064061  jz      short loc_180064082
0x180064063  test    dword ptr [rcx+1Ch], 800000h
0x18006406a  jz      short loc_180064082
0x18006406c  lea     edx, [rsi+32h]
0x18006406f  mov     r9d, eax
0x180064072  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180064079  mov     rcx, [rcx+10h]
0x18006407d  call    WPP_SF_d
0x180064082  mov     rax, [rbx]
0x180064085  mov     edx, edi
0x180064087  mov     rcx, rbx
0x18006408a  mov     rax, [rax+48h]
0x18006408e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064093  jmp     loc_180063FE1
0x180064098  mov     edi, [rsp+58h+TokenInformationLength]
0x18006409c  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800640a1  test    rax, rax
0x1800640a4  jnz     short loc_1800640CD
0x1800640a6  mov     [rsp+58h+ReturnLength], rax; struct IRequestContext *
0x1800640ab  mov     r9d, 54Fh; unsigned int
0x1800640b1  lea     r8, a170; "170"
0x1800640b8  mov     edx, 0AAh; unsigned int
0x1800640bd  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x1800640c4  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800640c9  xor     edi, edi
0x1800640cb  jmp     short loc_1800640E3
0x1800640cd  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800640d2  mov     r8, rdi; dwBytes
0x1800640d5  xor     edx, edx; dwFlags
0x1800640d7  mov     rcx, rax; hHeap
0x1800640da  call    cs:__imp_HeapAlloc
0x1800640e0  mov     rdi, rax
0x1800640e3  mov     [rsp+58h+arg_18], rdi
0x1800640e8  test    rdi, rdi
0x1800640eb  jnz     short loc_18006410C
0x1800640ed  mov     rax, [rbx]
0x1800640f0  mov     rcx, rbx
0x1800640f3  mov     rax, [rax+18h]
0x1800640f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640fc  nop
0x1800640fd  lea     rcx, [rsp+58h+arg_18]
0x180064102  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180064107  jmp     loc_180063FE1
0x18006410c  lea     rax, [rsp+58h+TokenInformationLength]
0x180064111  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180064116  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18006411b  mov     r8, rdi; TokenInformation
0x18006411e  mov     edx, esi; TokenInformationClass
0x180064120  mov     rcx, rbp; TokenHandle
0x180064123  call    cs:__imp_GetTokenInformation
0x180064129  test    eax, eax
0x18006412b  jnz     short loc_18006417C
0x18006412d  call    cs:__imp_GetLastError
0x180064133  mov     edi, eax
0x180064135  lea     rdx, WPP_GLOBAL_Control
0x18006413c  mov     rcx, cs:WPP_GLOBAL_Control
0x180064143  cmp     rcx, rdx
0x180064146  jz      short loc_180064169
0x180064148  test    dword ptr [rcx+1Ch], 800000h
0x18006414f  jz      short loc_180064169
0x180064151  mov     edx, 34h ; '4'
0x180064156  mov     r9d, eax
0x180064159  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180064160  mov     rcx, [rcx+10h]
0x180064164  call    WPP_SF_d
0x180064169  mov     edx, edi
0x18006416b  mov     rax, [rbx]
0x18006416e  mov     rcx, rbx
0x180064171  mov     rax, [rax+48h]
0x180064175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006417a  jmp     short loc_1800640FD
0x18006417c  mov     rdi, [rdi]
0x18006417f  mov     rcx, rdi; pSid
0x180064182  call    cs:__imp_IsValidSid
0x180064188  test    eax, eax
0x18006418a  jnz     short loc_1800641C0
0x18006418c  lea     rdx, WPP_GLOBAL_Control
0x180064193  mov     rcx, cs:WPP_GLOBAL_Control
0x18006419a  cmp     rcx, rdx
0x18006419d  jz      short loc_1800641BB
0x18006419f  test    dword ptr [rcx+1Ch], 800000h
0x1800641a6  jz      short loc_1800641BB
0x1800641a8  lea     edx, [rax+35h]
0x1800641ab  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x1800641b2  mov     rcx, [rcx+10h]
0x1800641b6  call    WPP_SF_
0x1800641bb  mov     edx, r14d
0x1800641be  jmp     short loc_18006416B
0x1800641c0  mov     rdx, r15; StringSid
0x1800641c3  mov     rcx, rdi; Sid
0x1800641c6  call    cs:__imp_ConvertSidToStringSidW
0x1800641cc  test    eax, eax
0x1800641ce  jnz     short loc_18006421F
0x1800641d0  call    cs:__imp_GetLastError
0x1800641d6  mov     edi, eax
0x1800641d8  lea     rdx, WPP_GLOBAL_Control
0x1800641df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800641e6  cmp     rcx, rdx
0x1800641e9  jz      short loc_18006420C
0x1800641eb  test    dword ptr [rcx+1Ch], 800000h
0x1800641f2  jz      short loc_18006420C
0x1800641f4  mov     edx, 36h ; '6'
0x1800641f9  mov     r9d, eax
0x1800641fc  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x180064203  mov     rcx, [rcx+10h]
0x180064207  call    WPP_SF_d
0x18006420c  mov     rax, [rbx]
0x18006420f  mov     edx, edi
0x180064211  mov     rcx, rbx
0x180064214  mov     rax, [rax+48h]
0x180064218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006421d  xor     esi, esi
0x18006421f  lea     rcx, [rsp+58h+arg_18]
0x180064224  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180064229  mov     eax, esi
0x18006422b  mov     rbx, [rsp+58h+arg_8]
0x180064230  add     rsp, 30h
0x180064234  pop     r15
0x180064236  pop     r14
0x180064238  pop     rdi
0x180064239  pop     rsi
0x18006423a  pop     rbp
0x18006423b  retn
```
