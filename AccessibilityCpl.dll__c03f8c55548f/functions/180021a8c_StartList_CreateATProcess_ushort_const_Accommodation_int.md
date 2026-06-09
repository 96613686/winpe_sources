# StartList::CreateATProcess(ushort const *,Accommodation *,int)

- ea: `0x180021a8c`
- end: `0x180021d3d`
- name: `?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z`
- size: `689`
- prototype: `int(StartList *__hidden this, const unsigned __int16 *, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800241b0`

## callees

- `0x18001a6c0`
- `0x18001e984`
- `0x180021704`
- `0x180021a8c`
- `0x1800249d4`
- `0x180024b94`
- `0x1800255ac`
- `0x18002561c`
- `0x18002d220`

## import_xrefs

- `msvcrt!free` at `0x180021b49`
- `msvcrt!free` at `0x180021b8b`
- `msvcrt!free` at `0x180021b9e`
- `msvcrt!free` at `0x180021cc2`
- `msvcrt!free` at `0x180021cee`
- `msvcrt!free` at `0x180021b49`
- `msvcrt!free` at `0x180021b8b`
- `msvcrt!free` at `0x180021b9e`
- `msvcrt!free` at `0x180021cc2`
- `msvcrt!free` at `0x180021cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b73`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021b67`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021b67`
- `SHELL32!ShellExecuteW` at `0x180021c70`
- `SHELL32!ShellExecuteW` at `0x180021c70`

## string_xrefs

- `0x180021bd3`: `/launchnarratorupdates`
- `0x180021ad1`: `StartList::CreateATProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateATProcess(StartList *this, const unsigned __int16 *a2, struct Accommodation *a3)
{
  const WCHAR *v5; // r15
  char *v6; // rsi
  int v7; // edi
  void *v8; // rbx
  DWORD v9; // eax
  signed int LastError; // eax
  char IsEnabled; // al
  const WCHAR *v12; // r9
  const wchar_t *v13; // rcx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rax
  HINSTANCE v16; // rsi
  int v17; // r8d
  char *v18; // rsi
  char *v19; // rsi
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Parameters[256]; // [rsp+60h] [rbp-A0h] BYREF

  v22 = 0;
  _Trace::_Trace((_Trace *)v23, L"StartList::CreateATProcess", &v22);
  if ( a2 && *a2 )
  {
    v5 = (const WCHAR *)*((_QWORD *)a3 + 4);
    Block = 0;
    if ( (int)StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)&Block) < 0 )
      goto LABEL_39;
    v6 = (char *)Block + 260;
    if ( (char *)Block + 260 < Block )
      goto LABEL_39;
    Block = 0;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v6) )
    {
      free(Block);
      v7 = -2147024882;
LABEL_40:
      _Trace::~_Trace((_Trace *)v23);
      return (unsigned int)v7;
    }
    v8 = Block;
    v9 = ExpandEnvironmentStringsW(a2, (LPWSTR)Block, (DWORD)v6);
    v7 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError <= 0 )
      {
LABEL_11:
        free(v8);
        goto LABEL_40;
      }
      v7 = (unsigned __int16)LastError;
LABEL_10:
      v7 |= 0x80070000;
      goto LABEL_11;
    }
    if ( v9 > (unsigned __int64)v6 )
    {
      free(v8);
      v7 = -2147024774;
      goto LABEL_40;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
    v12 = &Data;
    v13 = L"/launchnarratorhome";
    v14 = L"/hardwarebuttonlaunch";
    if ( IsEnabled )
    {
      v15 = L"/launchnarratorupdates";
      if ( !*((_BYTE *)a3 + 86) )
        v15 = &Data;
      if ( !*((_BYTE *)a3 + 85) )
        v13 = &Data;
      if ( !*((_BYTE *)a3 + 84) )
        v14 = &Data;
      if ( v5 )
        v12 = v5;
      StringCchPrintfW(Parameters, 0x100u, L"%s %s %s %s", v12, v14, v13, v15);
    }
    else
    {
      if ( !*((_BYTE *)a3 + 85) )
        v13 = &Data;
      if ( !*((_BYTE *)a3 + 84) )
        v14 = &Data;
      if ( v5 )
        v12 = v5;
      StringCchPrintfW(Parameters, 0x100u, L"%s %s %s", v12, v14, v13);
    }
    v16 = ShellExecuteW(0, 0, (LPCWSTR)v8, Parameters, 0, 5);
    if ( (__int64)v16 <= 32 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v17, (_DWORD)v8, (char)v16);
      v18 = (char *)v16 - 2;
      if ( !v18 || (v19 = v18 - 1) == 0 || v19 == (char *)8 )
      {
        if ( v7 <= 0 )
          goto LABEL_11;
        v7 = (unsigned __int16)v7;
        goto LABEL_10;
      }
      free(v8);
LABEL_39:
      v7 = -2147467259;
      goto LABEL_40;
    }
    free(v8);
    _Trace::~_Trace((_Trace *)v23);
    return 0;
  }
  else
  {
    _Trace::~_Trace((_Trace *)v23);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180021a8c  mov     [rsp-8+arg_0], rbx
0x180021a91  mov     [rsp-8+arg_18], rsi
0x180021a96  push    rbp
0x180021a97  push    rdi
0x180021a98  push    r12
0x180021a9a  push    r14
0x180021a9c  push    r15
0x180021a9e  lea     rbp, [rsp-170h]
0x180021aa6  sub     rsp, 270h
0x180021aad  mov     rax, cs:__security_cookie
0x180021ab4  xor     rax, rsp
0x180021ab7  mov     [rbp+190h+var_30], rax
0x180021abe  mov     r14, r8
0x180021ac1  mov     rdi, rdx
0x180021ac4  xor     r12d, r12d
0x180021ac7  mov     [rsp+290h+var_248], r12d
0x180021acc  lea     r8, [rsp+290h+var_248]; int *
0x180021ad1  lea     rdx, aStartlistCreat; "StartList::CreateATProcess"
0x180021ad8  lea     rcx, [rsp+290h+var_240]; this
0x180021add  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x180021ae2  nop
0x180021ae3  test    rdi, rdi
0x180021ae6  jz      loc_180021D03
0x180021aec  cmp     [rdi], r12w
0x180021af0  jz      loc_180021D03
0x180021af6  mov     r15, [r14+20h]
0x180021afa  mov     [rsp+290h+Block], r12
0x180021aff  lea     r8, [rsp+290h+Block]; unsigned __int64 *
0x180021b04  mov     edx, 7FFFFFFFh; unsigned __int64
0x180021b09  mov     rcx, rdi; unsigned __int16 *
0x180021b0c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180021b11  test    eax, eax
0x180021b13  js      loc_180021CC8
0x180021b19  mov     rax, [rsp+290h+Block]
0x180021b1e  lea     rsi, [rax+104h]
0x180021b25  cmp     rsi, rax
0x180021b28  jb      loc_180021CC8
0x180021b2e  mov     [rsp+290h+Block], r12
0x180021b33  mov     rdx, rsi
0x180021b36  lea     rcx, [rsp+290h+Block]
0x180021b3b  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180021b40  test    al, al
0x180021b42  jnz     short loc_180021B59
0x180021b44  mov     rcx, [rsp+290h+Block]; Block
0x180021b49  call    cs:__imp_free
0x180021b4f  mov     edi, 8007000Eh
0x180021b54  jmp     loc_180021CCD
0x180021b59  mov     r8d, esi; nSize
0x180021b5c  mov     rbx, [rsp+290h+Block]
0x180021b61  mov     rdx, rbx; lpDst
0x180021b64  mov     rcx, rdi; lpSrc
0x180021b67  call    cs:__imp_ExpandEnvironmentStringsW
0x180021b6d  mov     edi, eax
0x180021b6f  test    eax, eax
0x180021b71  jnz     short loc_180021B96
0x180021b73  call    cs:__imp_GetLastError
0x180021b79  mov     edi, eax
0x180021b7b  test    eax, eax
0x180021b7d  jle     short loc_180021B88
0x180021b7f  movzx   edi, ax
0x180021b82  or      edi, 80070000h
0x180021b88  mov     rcx, rbx; Block
0x180021b8b  call    cs:__imp_free
0x180021b91  jmp     loc_180021CCD
0x180021b96  cmp     rdi, rsi
0x180021b99  jbe     short loc_180021BAE
0x180021b9b  mov     rcx, rbx; Block
0x180021b9e  call    cs:__imp_free
0x180021ba4  mov     edi, 8007007Ah
0x180021ba9  jmp     loc_180021CCD
0x180021bae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x180021bb5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x180021bba  lea     r9, Data
0x180021bc1  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x180021bc8  lea     rdx, aHardwarebutton_0; "/hardwarebuttonlaunch"
0x180021bcf  test    al, al
0x180021bd1  jz      short loc_180021C20
0x180021bd3  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x180021bda  cmp     [r14+56h], r12b
0x180021bde  cmovz   rax, r9
0x180021be2  cmp     [r14+55h], r12b
0x180021be6  cmovz   rcx, r9
0x180021bea  cmp     [r14+54h], r12b
0x180021bee  cmovz   rdx, r9
0x180021bf2  test    r15, r15
0x180021bf5  cmovnz  r9, r15
0x180021bf9  mov     [rsp+290h+var_260], rax
0x180021bfe  mov     qword ptr [rsp+290h+nShowCmd], rcx
0x180021c03  mov     [rsp+290h+lpDirectory], rdx
0x180021c08  lea     r8, aSSSS; "%s %s %s %s"
0x180021c0f  mov     edx, 100h; unsigned __int64
0x180021c14  lea     rcx, [rsp+290h+Parameters]; unsigned __int16 *
0x180021c19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021c1e  jmp     short loc_180021C57
0x180021c20  cmp     [r14+55h], r12b
0x180021c24  cmovz   rcx, r9
0x180021c28  cmp     [r14+54h], r12b
0x180021c2c  cmovz   rdx, r9
0x180021c30  test    r15, r15
0x180021c33  cmovnz  r9, r15
0x180021c37  mov     qword ptr [rsp+290h+nShowCmd], rcx
0x180021c3c  mov     [rsp+290h+lpDirectory], rdx
0x180021c41  lea     r8, aSSS; "%s %s %s"
0x180021c48  mov     edx, 100h; unsigned __int64
0x180021c4d  lea     rcx, [rsp+290h+Parameters]; unsigned __int16 *
0x180021c52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021c57  mov     [rsp+290h+nShowCmd], 5; nShowCmd
0x180021c5f  mov     [rsp+290h+lpDirectory], r12; lpDirectory
0x180021c64  lea     r9, [rsp+290h+Parameters]; lpParameters
0x180021c69  mov     r8, rbx; lpFile
0x180021c6c  xor     edx, edx; lpOperation
0x180021c6e  xor     ecx, ecx; hwnd
0x180021c70  call    cs:__imp_ShellExecuteW
0x180021c76  mov     rsi, rax
0x180021c79  cmp     rax, 20h ; ' '
0x180021c7d  jg      short loc_180021CEB
0x180021c7f  lea     rax, WPP_GLOBAL_Control
0x180021c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c8d  cmp     rcx, rax
0x180021c90  jz      short loc_180021CAD
0x180021c92  test    byte ptr [rcx+1Ch], 8
0x180021c96  jz      short loc_180021CAD
0x180021c98  mov     edx, 1Eh
0x180021c9d  mov     dword ptr [rsp+290h+lpDirectory], esi
0x180021ca1  mov     r9, rbx
0x180021ca4  mov     rcx, [rcx+10h]
0x180021ca8  call    WPP_SF_Sd
0x180021cad  sub     rsi, 2
0x180021cb1  jz      short loc_180021CDB
0x180021cb3  sub     rsi, 1
0x180021cb7  jz      short loc_180021CDB
0x180021cb9  cmp     rsi, 8
0x180021cbd  jz      short loc_180021CDB
0x180021cbf  mov     rcx, rbx; Block
0x180021cc2  call    cs:__imp_free
0x180021cc8  mov     edi, 80004005h
0x180021ccd  lea     rcx, [rsp+290h+var_240]; this
0x180021cd2  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x180021cd7  mov     eax, edi
0x180021cd9  jmp     short loc_180021D12
0x180021cdb  test    edi, edi
0x180021cdd  jle     loc_180021B88
0x180021ce3  movzx   edi, di
0x180021ce6  jmp     loc_180021B82
0x180021ceb  mov     rcx, rbx; Block
0x180021cee  call    cs:__imp_free
0x180021cf4  nop
0x180021cf5  lea     rcx, [rsp+290h+var_240]; this
0x180021cfa  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x180021cff  xor     eax, eax
0x180021d01  jmp     short loc_180021D12
0x180021d03  lea     rcx, [rsp+290h+var_240]; this
0x180021d08  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x180021d0d  mov     eax, 80070057h
0x180021d12  mov     rcx, [rbp+190h+var_30]
0x180021d19  xor     rcx, rsp; StackCookie
0x180021d1c  call    __security_check_cookie
0x180021d21  lea     r11, [rsp+290h+var_20]
0x180021d29  mov     rbx, [r11+30h]
0x180021d2d  mov     rsi, [r11+48h]
0x180021d31  mov     rsp, r11
0x180021d34  pop     r15
0x180021d36  pop     r14
0x180021d38  pop     r12
0x180021d3a  pop     rdi
0x180021d3b  pop     rbp
0x180021d3c  retn
```
