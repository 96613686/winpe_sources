# WindowsMidiServicesInternal::IsComponentPermitted(_GUID)

- ea: `0x180044458`
- end: `0x1800446eb`
- name: `?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(GUID *rguid, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180043eb4`
- `0x1800456dc`

## callees

- `0x180005020`
- `0x180005e9c`
- `0x18000b394`
- `0x18000d430`
- `0x180013118`
- `0x180043d40`
- `0x180044458`
- `0x1800446f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800444ee`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800444ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800444bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800444bd`
- `WINTRUST!WinVerifyTrust` at `0x180044673`
- `WINTRUST!WinVerifyTrust` at `0x180044689`
- `WINTRUST!WinVerifyTrust` at `0x180044673`
- `WINTRUST!WinVerifyTrust` at `0x180044689`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall WindowsMidiServicesInternal::IsComponentPermitted(GUID *rguid, struct _GUID *a2)
{
  LSTATUS result; // eax
  int v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r8
  _QWORD *v8; // rdx
  __int64 v9; // r8
  int IsFileCatalogSigned; // ebx
  _QWORD *v11; // rdx
  wchar_t *v12; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h]
  _DWORD pWVTData[6]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+90h] [rbp-70h]
  _QWORD *v21; // [rsp+98h] [rbp-68h]
  int v22; // [rsp+A0h] [rbp-60h]
  int v23; // [rsp+B8h] [rbp-48h]
  GUID pgActionID; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Str[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v26; // [rsp+F0h] [rbp-10h]
  _QWORD v27[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v28; // [rsp+118h] [rbp+18h]
  OLECHAR sz[40]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  pvData = 0;
  pcbData = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModelUnlock",
             L"AllowDevelopmentWithoutDevLicense",
             0x18u,
             0,
             &pvData,
             &pcbData);
  if ( result || pvData != 1 )
  {
    memset_0(sz, 0, 0x4Eu);
    if ( StringFromGUID2(rguid, sz, 39) )
    {
      *(_OWORD *)Str = 0;
      v26 = 0;
      v5 = -1;
      v6 = -1;
      do
        ++v6;
      while ( sz[v6] );
      std::wstring::_Construct<1,unsigned short const *>(Str);
      WindowsMidiServicesInternal::GetFileNameFromCLSID((__int64)v27, Str, v7);
      std::wstring::~wstring(Str);
      v8 = v27;
      if ( v28 > 7 )
        v8 = (_QWORD *)v27[0];
      *(_OWORD *)Str = 0;
      v26 = 0;
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)v8 + v9) );
      std::wstring::_Construct<1,unsigned short const *>(Str);
      IsFileCatalogSigned = WindowsMidiServicesInternal::IsFileCatalogSigned(Str);
      std::wstring::~wstring(Str);
      if ( IsFileCatalogSigned >= 0 )
        goto LABEL_22;
      v11 = v27;
      if ( v28 > 7 )
        v11 = (_QWORD *)v27[0];
      *(_OWORD *)Str = 0;
      v26 = 0;
      do
        ++v5;
      while ( *((_WORD *)v11 + v5) );
      std::wstring::_Construct<1,unsigned short const *>(Str);
      pgActionID.Data1 = 11191659;
      *(_DWORD *)&pgActionID.Data2 = 298896708;
      *(_DWORD *)pgActionID.Data4 = -1073692020;
      *(_DWORD *)&pgActionID.Data4[4] = -292175281;
      v16[0] = 32;
      v17 = 0;
      v12 = Str;
      if ( *((_QWORD *)&v26 + 1) > 7u )
        v12 = *(wchar_t **)Str;
      v16[1] = v12;
      memset_0(pWVTData, 0, 0x58u);
      pWVTData[0] = 88;
      v19 = 2;
      v20 = 1;
      v22 = 1;
      v23 = 256;
      v21 = v16;
      v4 = WinVerifyTrust(0, &pgActionID, pWVTData);
      v22 = 2;
      WinVerifyTrust(0, &pgActionID, pWVTData);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      std::wstring::~wstring(Str);
      if ( v4 >= 0 )
LABEL_22:
        v4 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"avcore\\midi2\\inc\\midi_utils.h",
          (const char *)(unsigned int)v4,
          pdwType);
      std::wstring::~wstring(v27);
    }
    else
    {
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"avcore\\midi2\\inc\\midi_utils.h",
        (const char *)0x80070057LL,
        pdwType);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180044458  push    rbp
0x18004445a  push    rbx
0x18004445b  push    rsi
0x18004445c  push    rdi
0x18004445d  lea     rbp, [rsp-88h]
0x180044465  sub     rsp, 188h
0x18004446c  mov     rax, cs:__security_cookie
0x180044473  xor     rax, rsp
0x180044476  mov     [rbp+0A0h+var_30], rax
0x18004447a  mov     rbx, rcx
0x18004447d  xor     esi, esi
0x18004447f  mov     [rsp+1A0h+var_160], esi
0x180044483  mov     [rsp+1A0h+var_15C], 4
0x18004448b  lea     rax, [rsp+1A0h+var_15C]
0x180044490  mov     [rsp+1A0h+pcbData], rax; pcbData
0x180044495  lea     rax, [rsp+1A0h+var_160]
0x18004449a  mov     [rsp+1A0h+pvData], rax; pvData
0x18004449f  mov     [rsp+1A0h+pdwType], rsi; int
0x1800444a4  lea     r9d, [rsi+18h]; dwFlags
0x1800444a8  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800444af  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800444b6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800444bd  call    cs:__imp_RegGetValueW
0x1800444c3  test    eax, eax
0x1800444c5  jnz     short loc_1800444D2
0x1800444c7  cmp     [rsp+1A0h+var_160], 1
0x1800444cc  jz      loc_1800446D3
0x1800444d2  xor     edx, edx; Val
0x1800444d4  lea     r8d, [rdx+4Eh]; Size
0x1800444d8  lea     rcx, [rbp+0A0h+sz]; void *
0x1800444dc  call    memset_0
0x1800444e1  mov     r8d, 27h ; '''; cchMax
0x1800444e7  lea     rdx, [rbp+0A0h+sz]; lpsz
0x1800444eb  mov     rcx, rbx; rguid
0x1800444ee  call    cs:__imp_StringFromGUID2
0x1800444f4  test    eax, eax
0x1800444f6  jnz     short loc_18004451D
0x1800444f8  mov     rcx, [rbp+0A8h]; this
0x1800444ff  mov     ebx, 80070057h
0x180044504  mov     r9d, ebx; char *
0x180044507  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\midi_utils.h"
0x18004450e  mov     edx, 0BBh; void *
0x180044513  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044518  jmp     loc_1800446D1
0x18004451d  xorps   xmm0, xmm0
0x180044520  movups  xmmword ptr [rbp+0A0h+Str], xmm0
0x180044524  xorps   xmm1, xmm1
0x180044527  movdqu  [rbp+0A0h+var_B0], xmm1
0x18004452c  lea     rax, [rbp+0A0h+sz]
0x180044530  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180044534  mov     r8, rdi
0x180044537  inc     r8
0x18004453a  cmp     [rax+r8*2], si
0x18004453f  jnz     short loc_180044537
0x180044541  lea     rdx, [rbp+0A0h+sz]
0x180044545  lea     rcx, [rbp+0A0h+Str]
0x180044549  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004454e  nop
0x18004454f  lea     rdx, [rbp+0A0h+Str]
0x180044553  lea     rcx, [rbp+0A0h+var_A0]
0x180044557  call    ?GetFileNameFromCLSID@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; WindowsMidiServicesInternal::GetFileNameFromCLSID(std::wstring const &)
0x18004455c  nop
0x18004455d  lea     rcx, [rbp+0A0h+Str]; void *
0x180044561  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044566  lea     rdx, [rbp+0A0h+var_A0]
0x18004456a  cmp     [rbp+0A0h+var_88], 7
0x18004456f  cmova   rdx, [rbp+0A0h+var_A0]
0x180044574  xorps   xmm0, xmm0
0x180044577  movups  xmmword ptr [rbp+0A0h+Str], xmm0
0x18004457b  xorps   xmm1, xmm1
0x18004457e  movdqu  [rbp+0A0h+var_B0], xmm1
0x180044583  mov     r8, rdi
0x180044586  inc     r8
0x180044589  cmp     [rdx+r8*2], si
0x18004458e  jnz     short loc_180044586
0x180044590  lea     rcx, [rbp+0A0h+Str]
0x180044594  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180044599  lea     rcx, [rbp+0A0h+Str]; Str
0x18004459d  call    ?IsFileCatalogSigned@WindowsMidiServicesInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::IsFileCatalogSigned(std::wstring const &)
0x1800445a2  mov     ebx, eax
0x1800445a4  lea     rcx, [rbp+0A0h+Str]; void *
0x1800445a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800445ad  shr     ebx, 1Fh
0x1800445b0  test    bl, bl
0x1800445b2  jz      loc_1800446C6
0x1800445b8  lea     rdx, [rbp+0A0h+var_A0]
0x1800445bc  cmp     [rbp+0A0h+var_88], 7
0x1800445c1  cmova   rdx, [rbp+0A0h+var_A0]
0x1800445c6  xorps   xmm0, xmm0
0x1800445c9  movups  xmmword ptr [rbp+0A0h+Str], xmm0
0x1800445cd  xorps   xmm1, xmm1
0x1800445d0  movdqu  [rbp+0A0h+var_B0], xmm1
0x1800445d5  inc     rdi
0x1800445d8  cmp     [rdx+rdi*2], si
0x1800445dc  jnz     short loc_1800445D5
0x1800445de  mov     r8, rdi
0x1800445e1  lea     rcx, [rbp+0A0h+Str]
0x1800445e5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800445ea  mov     [rbp+0A0h+pgActionID.Data1], 0AAC56Bh
0x1800445f1  mov     dword ptr [rbp+0A0h+pgActionID.Data2], 11D0CD44h
0x1800445f8  mov     dword ptr [rbp+0A0h+pgActionID.Data4], 0C000C28Ch
0x1800445ff  mov     dword ptr [rbp+0A0h+pgActionID.Data4+4], 0EE95C24Fh
0x180044606  mov     [rsp+1A0h+var_158], 20h ; ' '
0x18004460f  xorps   xmm0, xmm0
0x180044612  movdqu  [rsp+1A0h+var_148], xmm0
0x180044618  lea     rax, [rbp+0A0h+Str]
0x18004461c  cmp     qword ptr [rbp+0A0h+var_B0+8], 7
0x180044621  cmova   rax, qword ptr [rbp+0A0h+Str]
0x180044626  mov     [rsp+1A0h+var_150], rax
0x18004462b  mov     ebx, 58h ; 'X'
0x180044630  mov     r8d, ebx; Size
0x180044633  xor     edx, edx; Val
0x180044635  lea     rcx, [rsp+1A0h+pWVTData]; void *
0x18004463a  call    memset_0
0x18004463f  mov     [rsp+1A0h+pWVTData], ebx
0x180044643  lea     edi, [rbx-56h]
0x180044646  mov     [rbp+0A0h+var_118], rdi
0x18004464a  mov     [rbp+0A0h+var_110], 1
0x180044651  mov     [rbp+0A0h+var_100], 1
0x180044658  mov     [rbp+0A0h+var_E8], 100h
0x18004465f  lea     rax, [rsp+1A0h+var_158]
0x180044664  mov     [rbp+0A0h+var_108], rax
0x180044668  lea     r8, [rsp+1A0h+pWVTData]; pWVTData
0x18004466d  lea     rdx, [rbp+0A0h+pgActionID]; pgActionID
0x180044671  xor     ecx, ecx; hwnd
0x180044673  call    cs:__imp_WinVerifyTrust
0x180044679  mov     ebx, eax
0x18004467b  mov     [rbp+0A0h+var_100], edi
0x18004467e  lea     r8, [rsp+1A0h+pWVTData]; pWVTData
0x180044683  lea     rdx, [rbp+0A0h+pgActionID]; pgActionID
0x180044687  xor     ecx, ecx; hwnd
0x180044689  call    cs:__imp_WinVerifyTrust
0x18004468f  test    ebx, ebx
0x180044691  jle     short loc_18004469C
0x180044693  movzx   ebx, bx
0x180044696  or      ebx, 80070000h
0x18004469c  lea     rcx, [rbp+0A0h+Str]; void *
0x1800446a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800446a5  test    ebx, ebx
0x1800446a7  jns     short loc_1800446C6
0x1800446a9  mov     rcx, [rbp+0A8h]; this
0x1800446b0  mov     r9d, ebx; char *
0x1800446b3  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\inc\\midi_utils.h"
0x1800446ba  mov     edx, 0C4h; void *
0x1800446bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800446c4  jmp     short loc_1800446C8
0x1800446c6  mov     ebx, esi
0x1800446c8  lea     rcx, [rbp+0A0h+var_A0]; void *
0x1800446cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800446d1  mov     eax, ebx
0x1800446d3  mov     rcx, [rbp+0A0h+var_30]
0x1800446d7  xor     rcx, rsp; StackCookie
0x1800446da  call    __security_check_cookie
0x1800446df  add     rsp, 188h
0x1800446e6  pop     rdi
0x1800446e7  pop     rsi
0x1800446e8  pop     rbx
0x1800446e9  pop     rbp
0x1800446ea  retn
```
