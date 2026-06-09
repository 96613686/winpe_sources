# WindowsMidiServicesInternal::IsComponentPermitted(_GUID)

- ea: `0x1400252b8`
- end: `0x14002554b`
- name: `?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z`
- size: `659`
- prototype: `LSTATUS __fastcall(GUID *rguid, struct _GUID *)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140023398`
- `0x140030b10`
- `0x14003f730`
- `0x14003fd34`
- `0x140043720`

## callees

- `0x1400054c0`
- `0x1400060f8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000a6b4`
- `0x140023d54`
- `0x1400252b8`
- `0x140025554`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14002534e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14002534e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002531d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002531d`
- `WINTRUST!WinVerifyTrust` at `0x1400254d3`
- `WINTRUST!WinVerifyTrust` at `0x1400254e9`
- `WINTRUST!WinVerifyTrust` at `0x1400254d3`
- `WINTRUST!WinVerifyTrust` at `0x1400254e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall WindowsMidiServicesInternal::IsComponentPermitted(GUID *rguid, struct _GUID *a2)
{
  LSTATUS result; // eax
  int v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int64 v8; // r8
  int IsFileCatalogSigned; // ebx
  _QWORD *v10; // rdx
  wchar_t *v11; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h]
  _DWORD pWVTData[6]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h]
  int v19; // [rsp+90h] [rbp-70h]
  _QWORD *v20; // [rsp+98h] [rbp-68h]
  int v21; // [rsp+A0h] [rbp-60h]
  int v22; // [rsp+B8h] [rbp-48h]
  GUID pgActionID; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Str[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v25; // [rsp+F0h] [rbp-10h]
  _QWORD v26[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v27; // [rsp+118h] [rbp+18h]
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
      v25 = 0;
      v5 = -1;
      v6 = -1;
      do
        ++v6;
      while ( sz[v6] );
      std::wstring::_Construct<1,unsigned short const *>(Str, sz, v6);
      WindowsMidiServicesInternal::GetFileNameFromCLSID(v26, Str);
      std::wstring::~wstring(Str);
      v7 = v26;
      if ( v27 > 7 )
        v7 = (_QWORD *)v26[0];
      *(_OWORD *)Str = 0;
      v25 = 0;
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)v7 + v8) );
      std::wstring::_Construct<1,unsigned short const *>(Str, v7, v8);
      IsFileCatalogSigned = WindowsMidiServicesInternal::IsFileCatalogSigned(Str);
      std::wstring::~wstring(Str);
      if ( IsFileCatalogSigned >= 0 )
        goto LABEL_22;
      v10 = v26;
      if ( v27 > 7 )
        v10 = (_QWORD *)v26[0];
      *(_OWORD *)Str = 0;
      v25 = 0;
      do
        ++v5;
      while ( *((_WORD *)v10 + v5) );
      std::wstring::_Construct<1,unsigned short const *>(Str, v10, v5);
      pgActionID.Data1 = 11191659;
      *(_DWORD *)&pgActionID.Data2 = 298896708;
      *(_DWORD *)pgActionID.Data4 = -1073692020;
      *(_DWORD *)&pgActionID.Data4[4] = -292175281;
      v15[0] = 32;
      v16 = 0;
      v11 = Str;
      if ( *((_QWORD *)&v25 + 1) > 7u )
        v11 = *(wchar_t **)Str;
      v15[1] = v11;
      memset_0(pWVTData, 0, 0x58u);
      pWVTData[0] = 88;
      v18 = 2;
      v19 = 1;
      v21 = 1;
      v22 = 256;
      v20 = v15;
      v4 = WinVerifyTrust(0, &pgActionID, pWVTData);
      v21 = 2;
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
          (unsigned int)"avcore\\midi2\\Inc\\midi_utils.h",
          (const char *)(unsigned int)v4,
          pdwType);
      std::wstring::~wstring(v26);
    }
    else
    {
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"avcore\\midi2\\Inc\\midi_utils.h",
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
0x1400252b8  push    rbp
0x1400252ba  push    rbx
0x1400252bb  push    rsi
0x1400252bc  push    rdi
0x1400252bd  lea     rbp, [rsp-88h]
0x1400252c5  sub     rsp, 188h
0x1400252cc  mov     rax, cs:__security_cookie
0x1400252d3  xor     rax, rsp
0x1400252d6  mov     [rbp+0A0h+var_30], rax
0x1400252da  mov     rbx, rcx
0x1400252dd  xor     esi, esi
0x1400252df  mov     [rsp+1A0h+var_160], esi
0x1400252e3  mov     [rsp+1A0h+var_15C], 4
0x1400252eb  lea     rax, [rsp+1A0h+var_15C]
0x1400252f0  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1400252f5  lea     rax, [rsp+1A0h+var_160]
0x1400252fa  mov     [rsp+1A0h+pvData], rax; pvData
0x1400252ff  mov     [rsp+1A0h+pdwType], rsi; int
0x140025304  lea     r9d, [rsi+18h]; dwFlags
0x140025308  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x14002530f  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140025316  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14002531d  call    cs:__imp_RegGetValueW
0x140025323  test    eax, eax
0x140025325  jnz     short loc_140025332
0x140025327  cmp     [rsp+1A0h+var_160], 1
0x14002532c  jz      loc_140025533
0x140025332  xor     edx, edx; Val
0x140025334  lea     r8d, [rdx+4Eh]; Size
0x140025338  lea     rcx, [rbp+0A0h+sz]; void *
0x14002533c  call    memset_0
0x140025341  mov     r8d, 27h ; '''; cchMax
0x140025347  lea     rdx, [rbp+0A0h+sz]; lpsz
0x14002534b  mov     rcx, rbx; rguid
0x14002534e  call    cs:__imp_StringFromGUID2
0x140025354  test    eax, eax
0x140025356  jnz     short loc_14002537D
0x140025358  mov     rcx, [rbp+0A8h]; this
0x14002535f  mov     ebx, 80070057h
0x140025364  mov     r9d, ebx; char *
0x140025367  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\Inc\\midi_utils.h"
0x14002536e  mov     edx, 0BBh; void *
0x140025373  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025378  jmp     loc_140025531
0x14002537d  xorps   xmm0, xmm0
0x140025380  movups  xmmword ptr [rbp+0A0h+Str], xmm0
0x140025384  xorps   xmm1, xmm1
0x140025387  movdqu  [rbp+0A0h+var_B0], xmm1
0x14002538c  lea     rax, [rbp+0A0h+sz]
0x140025390  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140025394  mov     r8, rdi
0x140025397  inc     r8
0x14002539a  cmp     [rax+r8*2], si
0x14002539f  jnz     short loc_140025397
0x1400253a1  lea     rdx, [rbp+0A0h+sz]
0x1400253a5  lea     rcx, [rbp+0A0h+Str]
0x1400253a9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400253ae  nop
0x1400253af  lea     rdx, [rbp+0A0h+Str]
0x1400253b3  lea     rcx, [rbp+0A0h+var_A0]
0x1400253b7  call    ?GetFileNameFromCLSID@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; WindowsMidiServicesInternal::GetFileNameFromCLSID(std::wstring const &)
0x1400253bc  nop
0x1400253bd  lea     rcx, [rbp+0A0h+Str]; void *
0x1400253c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400253c6  lea     rdx, [rbp+0A0h+var_A0]
0x1400253ca  cmp     [rbp+0A0h+var_88], 7
0x1400253cf  cmova   rdx, [rbp+0A0h+var_A0]
0x1400253d4  xorps   xmm0, xmm0
0x1400253d7  movups  xmmword ptr [rbp+0A0h+Str], xmm0
0x1400253db  xorps   xmm1, xmm1
0x1400253de  movdqu  [rbp+0A0h+var_B0], xmm1
0x1400253e3  mov     r8, rdi
0x1400253e6  inc     r8
0x1400253e9  cmp     [rdx+r8*2], si
0x1400253ee  jnz     short loc_1400253E6
0x1400253f0  lea     rcx, [rbp+0A0h+Str]
0x1400253f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400253f9  lea     rcx, [rbp+0A0h+Str]; Str
0x1400253fd  call    ?IsFileCatalogSigned@WindowsMidiServicesInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::IsFileCatalogSigned(std::wstring const &)
0x140025402  mov     ebx, eax
0x140025404  lea     rcx, [rbp+0A0h+Str]; void *
0x140025408  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002540d  shr     ebx, 1Fh
0x140025410  test    bl, bl
0x140025412  jz      loc_140025526
0x140025418  lea     rdx, [rbp+0A0h+var_A0]
0x14002541c  cmp     [rbp+0A0h+var_88], 7
0x140025421  cmova   rdx, [rbp+0A0h+var_A0]
0x140025426  xorps   xmm0, xmm0
0x140025429  movups  xmmword ptr [rbp+0A0h+Str], xmm0
0x14002542d  xorps   xmm1, xmm1
0x140025430  movdqu  [rbp+0A0h+var_B0], xmm1
0x140025435  inc     rdi
0x140025438  cmp     [rdx+rdi*2], si
0x14002543c  jnz     short loc_140025435
0x14002543e  mov     r8, rdi
0x140025441  lea     rcx, [rbp+0A0h+Str]
0x140025445  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002544a  mov     [rbp+0A0h+pgActionID.Data1], 0AAC56Bh
0x140025451  mov     dword ptr [rbp+0A0h+pgActionID.Data2], 11D0CD44h
0x140025458  mov     dword ptr [rbp+0A0h+pgActionID.Data4], 0C000C28Ch
0x14002545f  mov     dword ptr [rbp+0A0h+pgActionID.Data4+4], 0EE95C24Fh
0x140025466  mov     [rsp+1A0h+var_158], 20h ; ' '
0x14002546f  xorps   xmm0, xmm0
0x140025472  movdqu  [rsp+1A0h+var_148], xmm0
0x140025478  lea     rax, [rbp+0A0h+Str]
0x14002547c  cmp     qword ptr [rbp+0A0h+var_B0+8], 7
0x140025481  cmova   rax, qword ptr [rbp+0A0h+Str]
0x140025486  mov     [rsp+1A0h+var_150], rax
0x14002548b  mov     ebx, 58h ; 'X'
0x140025490  mov     r8d, ebx; Size
0x140025493  xor     edx, edx; Val
0x140025495  lea     rcx, [rsp+1A0h+pWVTData]; void *
0x14002549a  call    memset_0
0x14002549f  mov     [rsp+1A0h+pWVTData], ebx
0x1400254a3  lea     edi, [rbx-56h]
0x1400254a6  mov     [rbp+0A0h+var_118], rdi
0x1400254aa  mov     [rbp+0A0h+var_110], 1
0x1400254b1  mov     [rbp+0A0h+var_100], 1
0x1400254b8  mov     [rbp+0A0h+var_E8], 100h
0x1400254bf  lea     rax, [rsp+1A0h+var_158]
0x1400254c4  mov     [rbp+0A0h+var_108], rax
0x1400254c8  lea     r8, [rsp+1A0h+pWVTData]; pWVTData
0x1400254cd  lea     rdx, [rbp+0A0h+pgActionID]; pgActionID
0x1400254d1  xor     ecx, ecx; hwnd
0x1400254d3  call    cs:__imp_WinVerifyTrust
0x1400254d9  mov     ebx, eax
0x1400254db  mov     [rbp+0A0h+var_100], edi
0x1400254de  lea     r8, [rsp+1A0h+pWVTData]; pWVTData
0x1400254e3  lea     rdx, [rbp+0A0h+pgActionID]; pgActionID
0x1400254e7  xor     ecx, ecx; hwnd
0x1400254e9  call    cs:__imp_WinVerifyTrust
0x1400254ef  test    ebx, ebx
0x1400254f1  jle     short loc_1400254FC
0x1400254f3  movzx   ebx, bx
0x1400254f6  or      ebx, 80070000h
0x1400254fc  lea     rcx, [rbp+0A0h+Str]; void *
0x140025500  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025505  test    ebx, ebx
0x140025507  jns     short loc_140025526
0x140025509  mov     rcx, [rbp+0A8h]; this
0x140025510  mov     r9d, ebx; char *
0x140025513  lea     r8, aAvcoreMidi2Inc; "avcore\\midi2\\Inc\\midi_utils.h"
0x14002551a  mov     edx, 0C4h; void *
0x14002551f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025524  jmp     short loc_140025528
0x140025526  mov     ebx, esi
0x140025528  lea     rcx, [rbp+0A0h+var_A0]; void *
0x14002552c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025531  mov     eax, ebx
0x140025533  mov     rcx, [rbp+0A0h+var_30]
0x140025537  xor     rcx, rsp; StackCookie
0x14002553a  call    __security_check_cookie
0x14002553f  add     rsp, 188h
0x140025546  pop     rdi
0x140025547  pop     rsi
0x140025548  pop     rbx
0x140025549  pop     rbp
0x14002554a  retn
```
