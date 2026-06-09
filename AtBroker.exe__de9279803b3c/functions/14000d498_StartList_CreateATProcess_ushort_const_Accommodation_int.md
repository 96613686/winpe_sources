# StartList::CreateATProcess(ushort const *,Accommodation *,int)

- ea: `0x14000d498`
- end: `0x14000d772`
- name: `?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z`
- size: `730`
- prototype: `__int64 __fastcall(StartList *this, const unsigned __int16 *, struct Accommodation *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140010244`

## callees

- `0x140009aa8`
- `0x14000a7e4`
- `0x14000c220`
- `0x14000c2bc`
- `0x14000d498`
- `0x140011080`
- `0x140015b00`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000d586`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14000d586`
- `KERNEL32!GetLastError` at `0x14000d592`
- `KERNEL32!GetLastError` at `0x14000d592`
- `msvcrt!malloc` at `0x14000d562`
- `msvcrt!malloc` at `0x14000d562`
- `msvcrt!free` at `0x14000d5aa`
- `msvcrt!free` at `0x14000d5bd`
- `msvcrt!free` at `0x14000d6e1`
- `msvcrt!free` at `0x14000d70a`
- `msvcrt!free` at `0x14000d717`
- `msvcrt!free` at `0x14000d72f`
- `msvcrt!free` at `0x14000d5aa`
- `msvcrt!free` at `0x14000d5bd`
- `msvcrt!free` at `0x14000d6e1`
- `msvcrt!free` at `0x14000d70a`
- `msvcrt!free` at `0x14000d717`
- `msvcrt!free` at `0x14000d72f`
- `SHELL32!ShellExecuteW` at `0x14000d68f`
- `SHELL32!ShellExecuteW` at `0x14000d68f`

## string_xrefs

- `0x14000d5f2`: `/launchnarratorupdates`
- `0x14000d4d0`: `StartList::CreateATProcess`

## pseudocode

```c
__int64 __fastcall StartList::CreateATProcess(StartList *this, const unsigned __int16 *a2, struct Accommodation *a3)
{
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdi
  WCHAR *v9; // rbx
  size_t v10; // rcx
  WCHAR *v11; // rax
  const BYTE *v12; // r14
  DWORD v13; // eax
  signed int v14; // esi
  signed int LastError; // eax
  unsigned int v16; // edi
  char IsEnabled; // al
  const BYTE *v18; // r9
  const BYTE *v19; // rcx
  const BYTE *v20; // rdx
  const BYTE *v21; // rax
  HINSTANCE v22; // rdi
  int v23; // r8d
  char *v24; // rdi
  char *v25; // rdi
  int v27; // [rsp+40h] [rbp-258h] BYREF
  WCHAR *v28; // [rsp+48h] [rbp-250h]
  _BYTE v29[16]; // [rsp+50h] [rbp-248h] BYREF
  WCHAR Parameters[256]; // [rsp+60h] [rbp-238h] BYREF

  v27 = 0;
  _Trace::_Trace((_Trace *)v29, L"StartList::CreateATProcess", &v27);
  if ( !a2 || !*a2 )
  {
    _Trace::~_Trace((_Trace *)v29);
    return 2147942487LL;
  }
  v5 = 0x7FFFFFFF;
  v6 = a2;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = (0x7FFFFFFF - v5) & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64);
  if ( !v5 || (v8 = v7 + 260, v7 + 260 < v7) )
  {
LABEL_44:
    v16 = -2147467259;
    goto LABEL_45;
  }
  v9 = 0;
  v28 = 0;
  if ( v7 == -260 )
  {
    v10 = 0;
  }
  else
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v8 < 2 )
    {
LABEL_50:
      free(v9);
      v16 = -2147024882;
      goto LABEL_45;
    }
    v10 = 2 * v8;
  }
  v11 = (WCHAR *)malloc(v10);
  v9 = v11;
  v28 = v11;
  if ( !v11 )
    goto LABEL_50;
  v12 = (const BYTE *)*((_QWORD *)a3 + 4);
  v13 = ExpandEnvironmentStringsW(a2, v11, v8);
  v14 = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    free(v9);
    goto LABEL_45;
  }
  if ( v13 > v8 )
  {
    free(v9);
    v16 = -2147024774;
LABEL_45:
    _Trace::~_Trace((_Trace *)v29);
    return v16;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
  v18 = &Data;
  v19 = (const BYTE *)L"/launchnarratorhome";
  v20 = (const BYTE *)L"/hardwarebuttonlaunch";
  if ( IsEnabled )
  {
    v21 = (const BYTE *)L"/launchnarratorupdates";
    if ( !*((_BYTE *)a3 + 86) )
      v21 = &Data;
    if ( !*((_BYTE *)a3 + 85) )
      v19 = &Data;
    if ( !*((_BYTE *)a3 + 84) )
      v20 = &Data;
    if ( v12 )
      v18 = v12;
    StringCchPrintfW(Parameters, 0x100u, L"%s %s %s %s", v18, v20, v19, v21);
  }
  else
  {
    if ( !*((_BYTE *)a3 + 85) )
      v19 = &Data;
    if ( !*((_BYTE *)a3 + 84) )
      v20 = &Data;
    if ( v12 )
      v18 = v12;
    StringCchPrintfW(Parameters, 0x100u, L"%s %s %s", v18, v20, v19);
  }
  v22 = ShellExecuteW(0, 0, v9, Parameters, 0, 5);
  if ( (__int64)v22 <= 32 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v23, (_DWORD)v9, (char)v22);
    v24 = (char *)v22 - 2;
    if ( !v24 || (v25 = v24 - 1) == 0 || v25 == (char *)8 )
    {
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      free(v9);
      v16 = v14;
      goto LABEL_45;
    }
    free(v9);
    goto LABEL_44;
  }
  free(v9);
  _Trace::~_Trace((_Trace *)v29);
  return 0;
}

```

## disassembly

```asm
0x14000d498  mov     [rsp+arg_0], rbx
0x14000d49d  push    rbp
0x14000d49e  push    rsi
0x14000d49f  push    rdi
0x14000d4a0  push    r14
0x14000d4a2  push    r15
0x14000d4a4  sub     rsp, 270h
0x14000d4ab  mov     rax, cs:__security_cookie
0x14000d4b2  xor     rax, rsp
0x14000d4b5  mov     [rsp+298h+var_38], rax
0x14000d4bd  mov     rbp, r8
0x14000d4c0  mov     rsi, rdx
0x14000d4c3  xor     r15d, r15d
0x14000d4c6  mov     [rsp+298h+var_258], r15d
0x14000d4cb  lea     r8, [rsp+298h+var_258]; int *
0x14000d4d0  lea     rdx, aStartlistCreat; "StartList::CreateATProcess"
0x14000d4d7  lea     rcx, [rsp+298h+var_248]; this
0x14000d4dc  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x14000d4e1  nop
0x14000d4e2  test    rsi, rsi
0x14000d4e5  jz      loc_14000D73C
0x14000d4eb  cmp     [rsi], r15w
0x14000d4ef  jz      loc_14000D73C
0x14000d4f5  mov     r8d, 7FFFFFFFh
0x14000d4fb  mov     ecx, r8d
0x14000d4fe  mov     rax, rsi
0x14000d501  cmp     [rax], r15w
0x14000d505  jz      short loc_14000D511
0x14000d507  add     rax, 2
0x14000d50b  sub     rcx, 1
0x14000d50f  jnz     short loc_14000D501
0x14000d511  mov     rax, rcx
0x14000d514  sub     r8, rcx
0x14000d517  neg     rax
0x14000d51a  sbb     rdx, rdx
0x14000d51d  and     rdx, r8
0x14000d520  test    rcx, rcx
0x14000d523  jz      loc_14000D6E7
0x14000d529  lea     rdi, [rdx+104h]
0x14000d530  cmp     rdi, rdx
0x14000d533  jb      loc_14000D6E7
0x14000d539  mov     rbx, r15
0x14000d53c  mov     [rsp+298h+var_250], rbx
0x14000d541  test    rdi, rdi
0x14000d544  jnz     short loc_14000D54B
0x14000d546  mov     rcx, r15
0x14000d549  jmp     short loc_14000D562
0x14000d54b  xor     edx, edx
0x14000d54d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d551  div     rdi
0x14000d554  cmp     rax, 2
0x14000d558  jb      loc_14000D72C
0x14000d55e  lea     rcx, [rdi+rdi]; Size
0x14000d562  call    cs:__imp_malloc
0x14000d568  mov     rbx, rax
0x14000d56b  mov     [rsp+298h+var_250], rax
0x14000d570  test    rax, rax
0x14000d573  jz      loc_14000D72C
0x14000d579  mov     r14, [rbp+20h]
0x14000d57d  mov     r8d, edi; nSize
0x14000d580  mov     rdx, rax; lpDst
0x14000d583  mov     rcx, rsi; lpSrc
0x14000d586  call    cs:__imp_ExpandEnvironmentStringsW
0x14000d58c  mov     esi, eax
0x14000d58e  test    eax, eax
0x14000d590  jnz     short loc_14000D5B5
0x14000d592  call    cs:__imp_GetLastError
0x14000d598  mov     edi, eax
0x14000d59a  test    eax, eax
0x14000d59c  jle     short loc_14000D5A7
0x14000d59e  movzx   edi, ax
0x14000d5a1  or      edi, 80070000h
0x14000d5a7  mov     rcx, rbx; Block
0x14000d5aa  call    cs:__imp_free
0x14000d5b0  jmp     loc_14000D6EC
0x14000d5b5  cmp     rsi, rdi
0x14000d5b8  jbe     short loc_14000D5CD
0x14000d5ba  mov     rcx, rbx; Block
0x14000d5bd  call    cs:__imp_free
0x14000d5c3  mov     edi, 8007007Ah
0x14000d5c8  jmp     loc_14000D6EC
0x14000d5cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x14000d5d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x14000d5d9  lea     r9, Data
0x14000d5e0  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x14000d5e7  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x14000d5ee  test    al, al
0x14000d5f0  jz      short loc_14000D63F
0x14000d5f2  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x14000d5f9  cmp     [rbp+56h], r15b
0x14000d5fd  cmovz   rax, r9
0x14000d601  cmp     [rbp+55h], r15b
0x14000d605  cmovz   rcx, r9
0x14000d609  cmp     [rbp+54h], r15b
0x14000d60d  cmovz   rdx, r9
0x14000d611  test    r14, r14
0x14000d614  cmovnz  r9, r14
0x14000d618  mov     [rsp+298h+var_268], rax
0x14000d61d  mov     qword ptr [rsp+298h+nShowCmd], rcx
0x14000d622  mov     [rsp+298h+lpDirectory], rdx
0x14000d627  lea     r8, aSSSS; "%s %s %s %s"
0x14000d62e  mov     edx, 100h; unsigned __int64
0x14000d633  lea     rcx, [rsp+298h+Parameters]; unsigned __int16 *
0x14000d638  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d63d  jmp     short loc_14000D676
0x14000d63f  cmp     [rbp+55h], r15b
0x14000d643  cmovz   rcx, r9
0x14000d647  cmp     [rbp+54h], r15b
0x14000d64b  cmovz   rdx, r9
0x14000d64f  test    r14, r14
0x14000d652  cmovnz  r9, r14
0x14000d656  mov     qword ptr [rsp+298h+nShowCmd], rcx
0x14000d65b  mov     [rsp+298h+lpDirectory], rdx
0x14000d660  lea     r8, aSSS; "%s %s %s"
0x14000d667  mov     edx, 100h; unsigned __int64
0x14000d66c  lea     rcx, [rsp+298h+Parameters]; unsigned __int16 *
0x14000d671  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d676  mov     [rsp+298h+nShowCmd], 5; nShowCmd
0x14000d67e  mov     [rsp+298h+lpDirectory], r15; lpDirectory
0x14000d683  lea     r9, [rsp+298h+Parameters]; lpParameters
0x14000d688  mov     r8, rbx; lpFile
0x14000d68b  xor     edx, edx; lpOperation
0x14000d68d  xor     ecx, ecx; hwnd
0x14000d68f  call    cs:__imp_ShellExecuteW
0x14000d695  mov     rdi, rax
0x14000d698  cmp     rax, 20h ; ' '
0x14000d69c  jg      short loc_14000D714
0x14000d69e  lea     rax, WPP_GLOBAL_Control
0x14000d6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d6ac  cmp     rcx, rax
0x14000d6af  jz      short loc_14000D6CC
0x14000d6b1  test    byte ptr [rcx+1Ch], 8
0x14000d6b5  jz      short loc_14000D6CC
0x14000d6b7  mov     edx, 1Eh
0x14000d6bc  mov     dword ptr [rsp+298h+lpDirectory], edi
0x14000d6c0  mov     r9, rbx
0x14000d6c3  mov     rcx, [rcx+10h]
0x14000d6c7  call    WPP_SF_Sd
0x14000d6cc  sub     rdi, 2
0x14000d6d0  jz      short loc_14000D6FA
0x14000d6d2  sub     rdi, 1
0x14000d6d6  jz      short loc_14000D6FA
0x14000d6d8  cmp     rdi, 8
0x14000d6dc  jz      short loc_14000D6FA
0x14000d6de  mov     rcx, rbx; Block
0x14000d6e1  call    cs:__imp_free
0x14000d6e7  mov     edi, 80004005h
0x14000d6ec  lea     rcx, [rsp+298h+var_248]; this
0x14000d6f1  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14000d6f6  mov     eax, edi
0x14000d6f8  jmp     short loc_14000D74B
0x14000d6fa  test    esi, esi
0x14000d6fc  jle     short loc_14000D707
0x14000d6fe  movzx   esi, si
0x14000d701  or      esi, 80070000h
0x14000d707  mov     rcx, rbx; Block
0x14000d70a  call    cs:__imp_free
0x14000d710  mov     edi, esi
0x14000d712  jmp     short loc_14000D6EC
0x14000d714  mov     rcx, rbx; Block
0x14000d717  call    cs:__imp_free
0x14000d71d  nop
0x14000d71e  lea     rcx, [rsp+298h+var_248]; this
0x14000d723  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14000d728  xor     eax, eax
0x14000d72a  jmp     short loc_14000D74B
0x14000d72c  mov     rcx, rbx; Block
0x14000d72f  call    cs:__imp_free
0x14000d735  mov     edi, 8007000Eh
0x14000d73a  jmp     short loc_14000D6EC
0x14000d73c  lea     rcx, [rsp+298h+var_248]; this
0x14000d741  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14000d746  mov     eax, 80070057h
0x14000d74b  mov     rcx, [rsp+298h+var_38]
0x14000d753  xor     rcx, rsp; StackCookie
0x14000d756  call    __security_check_cookie
0x14000d75b  mov     rbx, [rsp+298h+arg_0]
0x14000d763  add     rsp, 270h
0x14000d76a  pop     r15
0x14000d76c  pop     r14
0x14000d76e  pop     rdi
0x14000d76f  pop     rsi
0x14000d770  pop     rbp
0x14000d771  retn
```
