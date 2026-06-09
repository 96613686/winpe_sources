# Windows::Rtl::AutoHive::LoadFromWin32PathForOfflineHive(ulong,wchar_t const * const,ulong *)

- ea: `0x18001a5b4`
- end: `0x18001a8e7`
- name: `?LoadFromWin32PathForOfflineHive@AutoHive@Rtl@Windows@@QEAAJKQEB_WPEAK@Z`
- size: `819`
- prototype: `__int64 __fastcall(Windows::Rtl::AutoHive *this, __int64, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800177f8`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x18000f82c`
- `0x18000fafc`
- `0x180010794`
- `0x18001a120`
- `0x18001a5b4`
- `0x180023fec`
- `0x1800242a8`
- `0x180024658`
- `0x180025098`
- `0x180031bf8`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::AutoHive::LoadFromWin32PathForOfflineHive(
        Windows::Rtl::AutoHive *this,
        __int64 a2,
        const wchar_t *a3,
        unsigned int *a4)
{
  int LoadedHiveKeyNameInternal; // eax
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  size_t v15; // r8
  size_t v16; // r9
  __int64 v17; // rdx
  size_t v18; // rax
  unsigned __int64 i; // rsi
  size_t v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  wchar_t *v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // rax
  __int128 v27; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *Size; // [rsp+48h] [rbp-C0h]
  size_t Size_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  void *Src; // [rsp+60h] [rbp-A8h]
  const char *v31; // [rsp+68h] [rbp-A0h]
  __int64 v32; // [rsp+70h] [rbp-98h]
  wchar_t *v33; // [rsp+78h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-88h]
  __int128 v35; // [rsp+88h] [rbp-80h] BYREF
  __int64 v36; // [rsp+98h] [rbp-70h]
  __int128 v37; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-58h]
  wchar_t v39[256]; // [rsp+B8h] [rbp-50h] BYREF

  v34 = -2;
  memset_0(v39, 0, sizeof(v39));
  v37 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  LoadedHiveKeyNameInternal = GetLoadedHiveKeyNameInternal(a3, v39);
  v7 = 0;
  if ( LoadedHiveKeyNameInternal < 0 )
    v7 = LoadedHiveKeyNameInternal | 0x10000000u;
  v8 = ConvertHResultToNtStatus(v7);
  if ( v8 >= 0 )
  {
    v27 = 0;
    Size = 0;
    Size_8[0] = 38;
    Size_8[1] = 40;
    Src = L"HKEY_LOCAL_MACHINE\\";
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( v39[v12] );
    v13 = 2 * v12;
    v14 = v13 + 2;
    v31 = (const char *)v13;
    v32 = v13 + 2;
    v33 = v39;
    v15 = 0;
    *(_QWORD *)&v27 = 0;
    v16 = 0;
    v17 = 0;
    while ( 1 )
    {
      v18 = v16 + Size_8[3 * v17];
      if ( v18 < v16 )
      {
        Size_8[0] = (size_t)"OneCore\\Internal\\Base\\inc\\rtlstringutil.h";
        Size_8[1] = (size_t)"Windows::StringUtil::Rtl::ConcatenateStringsInList";
        Src = (void *)2879;
        v31 = "BUCL::Rtl::AddInPlaceWithOverflowCheck(&MaximumLength , Sources[i].Length)";
        RtlReportErrorOrigination(Size_8, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225621LL);
        v8 = -1073741675;
        goto LABEL_34;
      }
      if ( (unsigned __int64)++v17 >= 2 )
        break;
      v16 = v18;
    }
    if ( v18 <= *((_QWORD *)&v27 + 1) )
    {
LABEL_17:
      for ( i = 0; i < 2; ++i )
      {
        v20 = Size_8[3 * i];
        memcpy_0(&Size[v15 >> 1], *(&Src + 3 * i), v20);
        v15 = v20 + v27;
        *(_QWORD *)&v27 = v20 + v27;
      }
      *(_OWORD *)Size_8 = v27;
      Src = Size;
      v8 = RtlConvertWin32RegistryPathToNtRegistryPathWithSid(v22, v21, Size_8, &v37);
      v23 = Size;
      if ( v8 >= 0 )
      {
        if ( Size )
          anonymous_namespace_::OurRtlFreeStringRoutine(Size);
        if ( a3 )
        {
          do
            ++v11;
          while ( a3[v11] );
          v24 = 2 * v11;
          v25 = v24 + 2;
        }
        else
        {
          a3 = 0;
          v24 = 0;
          v25 = 0;
        }
        *(_QWORD *)&v27 = v24;
        *((_QWORD *)&v27 + 1) = v25;
        Size = (wchar_t *)a3;
        v8 = RtlConvertWin32FilePathToNtFilePath(&v27, &v35);
        if ( v8 < 0 )
          goto LABEL_4;
        v8 = Windows::Rtl::AutoHive::Load(
               this,
               0,
               (const struct _LUNICODE_STRING *)&v37,
               (const struct _LUNICODE_STRING *)&v35);
        v9 = v36;
        if ( v8 < 0 )
          goto LABEL_5;
        if ( v36 )
        {
          anonymous_namespace_::OurRtlFreeStringRoutine(v36);
          v35 = 0;
          v36 = 0;
        }
        if ( v38 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v38);
        return 0;
      }
      goto LABEL_35;
    }
    v8 = RtlReallocateLUnicodeString(v14, v18, &v27);
    if ( v8 >= 0 )
    {
      v15 = v27;
      goto LABEL_17;
    }
LABEL_34:
    v23 = Size;
    if ( !Size )
      goto LABEL_37;
LABEL_35:
    if ( v23 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v23);
LABEL_37:
    if ( v36 )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine(v36);
      v35 = 0;
      v36 = 0;
    }
    v10 = v38;
    if ( !v38 )
      return (unsigned int)v8;
  }
  else
  {
LABEL_4:
    v9 = v36;
LABEL_5:
    if ( v9 )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine(v9);
      v35 = 0;
      v36 = 0;
    }
    v10 = v38;
  }
  if ( v10 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001a5b4  mov     rax, rsp
0x18001a5b7  push    rbp
0x18001a5b8  push    rdi
0x18001a5b9  push    r12
0x18001a5bb  push    r14
0x18001a5bd  push    r15
0x18001a5bf  lea     rbp, [rax-1E8h]
0x18001a5c6  sub     rsp, 2C0h
0x18001a5cd  mov     [rsp+2E0h+var_268], 0FFFFFFFFFFFFFFFEh
0x18001a5d6  mov     [rax+10h], rbx
0x18001a5da  mov     [rax+20h], rsi
0x18001a5de  mov     rax, cs:__security_cookie
0x18001a5e5  xor     rax, rsp
0x18001a5e8  mov     [rbp+1E0h+var_30], rax
0x18001a5ef  mov     r14, r8
0x18001a5f2  mov     r15, rcx
0x18001a5f5  xor     edx, edx; Val
0x18001a5f7  mov     r8d, 200h; Size
0x18001a5fd  lea     rcx, [rbp+1E0h+var_230]; void *
0x18001a601  call    memset_0
0x18001a606  xorps   xmm0, xmm0
0x18001a609  xor     eax, eax
0x18001a60b  movups  [rbp+1E0h+var_248], xmm0
0x18001a60f  mov     [rbp+1E0h+var_238], rax
0x18001a613  movups  [rbp+1E0h+var_260], xmm0
0x18001a617  mov     [rbp+1E0h+var_250], rax
0x18001a61b  mov     r8d, 100h; unsigned __int64
0x18001a621  lea     rdx, [rbp+1E0h+var_230]; wchar_t *
0x18001a625  mov     rcx, r14; wchar_t *
0x18001a628  call    ?GetLoadedHiveKeyNameInternal@@YAJPEB_WPEA_W_K@Z; GetLoadedHiveKeyNameInternal(wchar_t const *,wchar_t *,unsigned __int64)
0x18001a62d  mov     edx, eax
0x18001a62f  bts     edx, 1Ch
0x18001a633  xor     r12d, r12d
0x18001a636  mov     ecx, r12d
0x18001a639  test    eax, eax
0x18001a63b  cmovs   ecx, edx
0x18001a63e  call    ConvertHResultToNtStatus
0x18001a643  mov     ebx, eax
0x18001a645  test    eax, eax
0x18001a647  jns     short loc_18001A66D
0x18001a649  mov     rcx, [rbp+1E0h+var_250]
0x18001a64d  test    rcx, rcx
0x18001a650  jz      short loc_18001A664
0x18001a652  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a657  xorps   xmm0, xmm0
0x18001a65a  xor     eax, eax
0x18001a65c  movups  [rbp+1E0h+var_260], xmm0
0x18001a660  mov     [rbp+1E0h+var_250], rax
0x18001a664  mov     rcx, [rbp+1E0h+var_238]
0x18001a668  jmp     loc_18001A8B0
0x18001a66d  xorps   xmm0, xmm0
0x18001a670  xor     eax, eax
0x18001a672  movups  [rsp+2E0h+var_2B8+8], xmm0
0x18001a677  mov     [rsp+2E0h+Size], rax
0x18001a67c  mov     [rsp+2E0h+Size+8], 26h ; '&'
0x18001a685  mov     [rsp+2E0h+var_290], 28h ; '('
0x18001a68e  lea     rax, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x18001a695  mov     [rsp+2E0h+Src], rax
0x18001a69a  lea     rcx, [rbp+1E0h+var_230]
0x18001a69e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001a6a2  mov     rax, rdi
0x18001a6a5  inc     rax
0x18001a6a8  cmp     [rcx+rax*2], r12w
0x18001a6ad  jnz     short loc_18001A6A5
0x18001a6af  add     rax, rax
0x18001a6b2  lea     rcx, [rax+2]
0x18001a6b6  mov     [rsp+2E0h+var_280], rax
0x18001a6bb  mov     [rsp+2E0h+var_278], rcx
0x18001a6c0  lea     rax, [rbp+1E0h+var_230]
0x18001a6c4  mov     [rsp+2E0h+var_270], rax
0x18001a6c9  mov     r8, r12
0x18001a6cc  mov     qword ptr [rsp+2E0h+var_2B8+8], r12
0x18001a6d1  mov     r9, r12
0x18001a6d4  mov     rdx, r12
0x18001a6d7  lea     rax, [rdx+rdx*2]
0x18001a6db  mov     rax, [rsp+rax*8+2E0h+Size+8]
0x18001a6e0  add     rax, r9
0x18001a6e3  cmp     rax, r9
0x18001a6e6  jb      loc_18001A82E
0x18001a6ec  inc     rdx
0x18001a6ef  cmp     rdx, 2
0x18001a6f3  jnb     short loc_18001A6FA
0x18001a6f5  mov     r9, rax
0x18001a6f8  jmp     short loc_18001A6D7
0x18001a6fa  cmp     rax, [rsp+2E0h+var_2A8]
0x18001a6ff  jbe     short loc_18001A71D
0x18001a701  lea     r8, [rsp+2E0h+var_2B8+8]
0x18001a706  mov     rdx, rax
0x18001a709  call    RtlReallocateLUnicodeString
0x18001a70e  mov     ebx, eax
0x18001a710  test    eax, eax
0x18001a712  js      loc_18001A877
0x18001a718  mov     r8, qword ptr [rsp+2E0h+var_2B8+8]
0x18001a71d  mov     rsi, r12
0x18001a720  lea     rdx, [rsi+rsi*2]
0x18001a724  mov     rbx, [rsp+rdx*8+2E0h+Size+8]
0x18001a729  shr     r8, 1
0x18001a72c  mov     rax, [rsp+2E0h+Size]
0x18001a731  lea     rcx, [rax+r8*2]; void *
0x18001a735  mov     r8, rbx; Size
0x18001a738  mov     rdx, [rsp+rdx*8+2E0h+Src]; Src
0x18001a73d  call    memcpy_0
0x18001a742  mov     r8, qword ptr [rsp+2E0h+var_2B8+8]
0x18001a747  add     r8, rbx
0x18001a74a  mov     qword ptr [rsp+2E0h+var_2B8+8], r8
0x18001a74f  inc     rsi
0x18001a752  cmp     rsi, 2
0x18001a756  jb      short loc_18001A720
0x18001a758  movups  xmm0, [rsp+2E0h+var_2B8+8]
0x18001a75d  movups  xmmword ptr [rsp+2E0h+Size+8], xmm0
0x18001a762  movsd   xmm1, [rsp+2E0h+Size]
0x18001a768  movsd   [rsp+2E0h+Src], xmm1
0x18001a76e  lea     r9, [rbp+1E0h+var_248]
0x18001a772  lea     r8, [rsp+2E0h+Size+8]
0x18001a777  call    RtlConvertWin32RegistryPathToNtRegistryPathWithSid
0x18001a77c  mov     ebx, eax
0x18001a77e  mov     rcx, [rsp+2E0h+Size]
0x18001a783  test    eax, eax
0x18001a785  js      loc_18001A881
0x18001a78b  test    rcx, rcx
0x18001a78e  jz      short loc_18001A795
0x18001a790  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a795  test    r14, r14
0x18001a798  jz      short loc_18001A7AD
0x18001a79a  inc     rdi
0x18001a79d  cmp     [r14+rdi*2], r12w
0x18001a7a2  jnz     short loc_18001A79A
0x18001a7a4  add     rdi, rdi
0x18001a7a7  lea     rax, [rdi+2]
0x18001a7ab  jmp     short loc_18001A7B6
0x18001a7ad  mov     r14, r12
0x18001a7b0  mov     rdi, r12
0x18001a7b3  mov     rax, r12
0x18001a7b6  mov     qword ptr [rsp+2E0h+var_2B8+8], rdi
0x18001a7bb  mov     [rsp+2E0h+var_2A8], rax
0x18001a7c0  mov     [rsp+2E0h+Size], r14
0x18001a7c5  lea     rdx, [rbp+1E0h+var_260]
0x18001a7c9  lea     rcx, [rsp+2E0h+var_2B8+8]
0x18001a7ce  call    RtlConvertWin32FilePathToNtFilePath
0x18001a7d3  mov     ebx, eax
0x18001a7d5  test    eax, eax
0x18001a7d7  js      loc_18001A649
0x18001a7dd  mov     [rsp+2E0h+var_2C0], r12; unsigned int *
0x18001a7e2  lea     r9, [rbp+1E0h+var_260]; struct _LUNICODE_STRING *
0x18001a7e6  lea     r8, [rbp+1E0h+var_248]; struct _LUNICODE_STRING *
0x18001a7ea  xor     edx, edx; unsigned int
0x18001a7ec  mov     rcx, r15; this
0x18001a7ef  call    ?Load@AutoHive@Rtl@Windows@@QEAAJKAEBU_LUNICODE_STRING@@0PEAK@Z; Windows::Rtl::AutoHive::Load(ulong,_LUNICODE_STRING const &,_LUNICODE_STRING const &,ulong *)
0x18001a7f4  mov     ebx, eax
0x18001a7f6  mov     rcx, [rbp+1E0h+var_250]
0x18001a7fa  test    eax, eax
0x18001a7fc  js      loc_18001A64D
0x18001a802  test    rcx, rcx
0x18001a805  jz      short loc_18001A819
0x18001a807  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a80c  xorps   xmm0, xmm0
0x18001a80f  xor     eax, eax
0x18001a811  movups  [rbp+1E0h+var_260], xmm0
0x18001a815  mov     [rbp+1E0h+var_250], rax
0x18001a819  mov     rcx, [rbp+1E0h+var_238]
0x18001a81d  test    rcx, rcx
0x18001a820  jz      short loc_18001A827
0x18001a822  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a827  xor     eax, eax
0x18001a829  jmp     loc_18001A8BC
0x18001a82e  lea     rax, aOnecoreInterna_0; "OneCore\\Internal\\Base\\inc\\rtlstring"...
0x18001a835  mov     [rsp+2E0h+Size+8], rax
0x18001a83a  lea     rax, aWindowsStringu_3; "Windows::StringUtil::Rtl::ConcatenateSt"...
0x18001a841  mov     [rsp+2E0h+var_290], rax
0x18001a846  mov     [rsp+2E0h+Src], 0B3Fh
0x18001a84f  lea     rax, aBuclRtlAddinpl_0; "BUCL::Rtl::AddInPlaceWithOverflowCheck("...
0x18001a856  mov     [rsp+2E0h+var_280], rax
0x18001a85b  mov     r8d, 0C0000095h
0x18001a861  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a868  lea     rcx, [rsp+2E0h+Size+8]
0x18001a86d  call    RtlReportErrorOrigination
0x18001a872  mov     ebx, 0C0000095h
0x18001a877  mov     rcx, [rsp+2E0h+Size]
0x18001a87c  test    rcx, rcx
0x18001a87f  jz      short loc_18001A88C
0x18001a881  test    rcx, rcx
0x18001a884  jz      short loc_18001A88C
0x18001a886  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a88b  nop
0x18001a88c  mov     rcx, [rbp+1E0h+var_250]
0x18001a890  test    rcx, rcx
0x18001a893  jz      short loc_18001A8A7
0x18001a895  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a89a  xorps   xmm0, xmm0
0x18001a89d  xor     eax, eax
0x18001a89f  movups  [rbp+1E0h+var_260], xmm0
0x18001a8a3  mov     [rbp+1E0h+var_250], rax
0x18001a8a7  mov     rcx, [rbp+1E0h+var_238]
0x18001a8ab  test    rcx, rcx
0x18001a8ae  jz      short loc_18001A8BA
0x18001a8b0  test    rcx, rcx
0x18001a8b3  jz      short loc_18001A8BA
0x18001a8b5  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a8ba  mov     eax, ebx
0x18001a8bc  mov     rcx, [rbp+1E0h+var_30]
0x18001a8c3  xor     rcx, rsp; StackCookie
0x18001a8c6  call    __security_check_cookie
0x18001a8cb  lea     r11, [rsp+2E0h+var_20]
0x18001a8d3  mov     rbx, [r11+38h]
0x18001a8d7  mov     rsi, [r11+48h]
0x18001a8db  mov     rsp, r11
0x18001a8de  pop     r15
0x18001a8e0  pop     r14
0x18001a8e2  pop     r12
0x18001a8e4  pop     rdi
0x18001a8e5  pop     rbp
0x18001a8e6  retn
```
