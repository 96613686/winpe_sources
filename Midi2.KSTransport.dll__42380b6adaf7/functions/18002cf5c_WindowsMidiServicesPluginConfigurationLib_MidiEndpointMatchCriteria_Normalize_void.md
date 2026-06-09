# WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(void)

- ea: `0x18002cf5c`
- end: `0x18002d628`
- name: `?Normalize@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAAXXZ`
- size: `1740`
- prototype: `void __fastcall(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x180018e84`
- `0x18002c4a4`
- `0x18002cccc`

## callees

- `0x180004000`
- `0x180004410`
- `0x1800051e6`
- `0x180005254`
- `0x18000526c`
- `0x1800052fc`
- `0x180005374`
- `0x18000c250`
- `0x18000f304`
- `0x180011240`
- `0x180014fc4`
- `0x180018778`
- `0x18001fde0`
- `0x18002beb0`
- `0x18002cf5c`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d107`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d325`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d334`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5d0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5df`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5ee`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5fd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d60c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d61b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d107`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d325`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d334`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5d0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5df`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5ee`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d5fd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d60c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d61b`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002d00a`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18002d18c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002d080`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002d1fe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002d080`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002d1fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *this)
{
  __int64 *v2; // rax
  __int64 v3; // rcx
  const wchar_t *v4; // r12
  const wchar_t *v5; // rdx
  __int64 v6; // r8
  winrt::impl *v7; // rcx
  void **v8; // rax
  void **v9; // rdx
  void **v10; // rsi
  unsigned int v11; // edi
  void **v12; // r15
  void **v13; // rbx
  void **v14; // rbx
  struct winrt::impl::shared_hstring_header *v15; // rsi
  struct winrt::impl::shared_hstring_header *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  size_t v19; // r8
  void *v20; // rcx
  void *v21; // rbx
  int v22; // eax
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  int v25; // eax
  HANDLE v26; // rax
  __int64 *v27; // rax
  __int64 v28; // rcx
  const wchar_t *v29; // rdx
  __int64 v30; // r8
  winrt::impl *v31; // rcx
  void **v32; // rax
  void **v33; // rdx
  void **v34; // r15
  unsigned int v35; // ebx
  void **v36; // r13
  void **v37; // rsi
  void **v38; // rsi
  struct winrt::impl::shared_hstring_header *v39; // r15
  struct winrt::impl::shared_hstring_header *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r9
  size_t v43; // r8
  void *v44; // rcx
  void *v45; // rbx
  int v46; // eax
  HANDLE v47; // rax
  char *v48; // r15
  void *v49; // rbx
  int v50; // eax
  HANDLE v51; // rax
  __int64 v52; // r8
  unsigned __int64 v53; // rcx
  __int128 *v54; // r8
  unsigned __int64 v55; // rdx
  __int128 *v56; // rsi
  __int128 *v57; // r10
  unsigned __int64 v58; // r11
  __int64 v59; // rax
  char *v60; // rbx
  __int64 v61; // rax
  unsigned __int64 v62; // r9
  __int64 v63; // rdx
  __int64 v64; // r8
  __int128 *v65; // rax
  __int128 *v66; // rax
  __int64 v67; // rax
  void *v68; // rbx
  int v69; // eax
  HANDLE v70; // rax
  __int64 v71; // rax
  void *v72; // rbx
  int v73; // eax
  HANDLE v74; // rax
  __int64 v75; // rax
  void *v76; // rbx
  int v77; // eax
  HANDLE v78; // rax
  __int64 v79; // rax
  void *v80; // rbx
  int v81; // eax
  HANDLE v82; // rax
  __int64 v83; // rax
  void *v84; // rbx
  int v85; // eax
  HANDLE v86; // rax
  __int64 v87; // rax
  void *v88; // rbx
  int v89; // edi
  HANDLE v90; // rax
  LPVOID lpMem[2]; // [rsp+20h] [rbp-A9h] BYREF
  LPVOID v92; // [rsp+30h] [rbp-99h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-91h] BYREF
  winrt::impl *v94[2]; // [rsp+48h] [rbp-81h]
  void *v95[2]; // [rsp+58h] [rbp-71h] BYREF
  winrt::impl *v96[2]; // [rsp+68h] [rbp-61h]
  __int128 v97; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int64 v98; // [rsp+88h] [rbp-41h]
  unsigned __int64 v99; // [rsp+90h] [rbp-39h]
  __int128 v100; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int64 v101; // [rsp+A8h] [rbp-21h]
  unsigned __int64 v102; // [rsp+B0h] [rbp-19h]
  __int128 v103; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v104; // [rsp+C8h] [rbp-1h]

  v2 = (__int64 *)WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, this);
  *(_OWORD *)Src = 0;
  *(_OWORD *)v94 = 0;
  v3 = *v2;
  v4 = &S1;
  if ( *v2 )
  {
    v5 = *(const wchar_t **)(v3 + 16);
    v6 = *(unsigned int *)(v3 + 4);
  }
  else
  {
    v5 = &S1;
    v6 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(Src, v5, v6);
  v7 = v94[1];
  v8 = (void **)Src[0];
  if ( v94[1] <= (winrt::impl *)7 )
  {
    v10 = Src;
    v9 = Src;
  }
  else
  {
    v9 = (void **)Src[0];
    v10 = (void **)Src[0];
  }
  v11 = (unsigned int)v94[0];
  v12 = (void **)((char *)v9 + 2 * (__int64)v94[0]);
  v13 = Src;
  if ( v94[1] > (winrt::impl *)7 )
    v13 = (void **)Src[0];
  if ( v13 != v12 )
  {
    do
    {
      *(_WORD *)v10 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*(unsigned __int16 *)v13);
      v10 = (void **)((char *)v10 + 2);
      v13 = (void **)((char *)v13 + 2);
    }
    while ( v13 != v12 );
    v7 = v94[1];
    v11 = (unsigned int)v94[0];
    v8 = (void **)Src[0];
  }
  v14 = Src;
  if ( (unsigned __int64)v7 > 7 )
    v14 = v8;
  if ( !v11 )
  {
    v15 = 0;
    goto LABEL_22;
  }
  v16 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v11, (unsigned int)v9);
  v15 = v16;
  v19 = 2LL * v11;
  if ( v19 )
  {
    v20 = (char *)v16 + 28;
    if ( v16 != (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      if ( v14 )
      {
        memcpy_0(v20, v14, v19);
        goto LABEL_22;
      }
      memset_0(v20, 0, v19);
    }
    *(_DWORD *)_o__errno(v20, v17, v19, v18) = 22;
    invalid_parameter_noinfo();
  }
LABEL_22:
  v92 = v15;
  std::wstring::~wstring(Src);
  v21 = lpMem[0];
  if ( lpMem[0] )
  {
    v22 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v22 )
    {
      if ( v22 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v21);
    }
  }
  winrt::hstring::operator=(this, &v92);
  v24 = v92;
  if ( v92 )
  {
    v25 = _InterlockedDecrement((volatile signed __int32 *)v92 + 6);
    if ( v25 )
    {
      if ( v25 < 0 )
        goto LABEL_72;
    }
    else
    {
      v26 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v26, 0, v24);
    }
  }
  v27 = (__int64 *)WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 8);
  *(_OWORD *)v95 = 0;
  *(_OWORD *)v96 = 0;
  v28 = *v27;
  if ( *v27 )
  {
    v29 = *(const wchar_t **)(v28 + 16);
    v30 = *(unsigned int *)(v28 + 4);
  }
  else
  {
    v29 = &S1;
    v30 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(v95, v29, v30);
  v31 = v96[1];
  v32 = (void **)v95[0];
  if ( v96[1] <= (winrt::impl *)7 )
  {
    v34 = v95;
    v33 = v95;
  }
  else
  {
    v33 = (void **)v95[0];
    v34 = (void **)v95[0];
  }
  v35 = (unsigned int)v96[0];
  v36 = (void **)((char *)v33 + 2 * (__int64)v96[0]);
  v37 = v95;
  if ( v96[1] > (winrt::impl *)7 )
    v37 = (void **)v95[0];
  if ( v37 != v36 )
  {
    do
    {
      *(_WORD *)v34 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v37);
      v34 = (void **)((char *)v34 + 2);
      v37 = (void **)((char *)v37 + 2);
    }
    while ( v37 != v36 );
    v31 = v96[1];
    v35 = (unsigned int)v96[0];
    v32 = (void **)v95[0];
  }
  v38 = v95;
  if ( (unsigned __int64)v31 > 7 )
    v38 = v32;
  if ( v35 )
  {
    v40 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v35, (unsigned int)v33);
    v39 = v40;
    v43 = 2LL * v35;
    if ( v43 )
    {
      v44 = (char *)v40 + 28;
      if ( v40 != (struct winrt::impl::shared_hstring_header *)-28LL )
      {
        if ( v38 )
        {
          memcpy_0(v44, v38, v43);
          goto LABEL_52;
        }
        memset_0(v44, 0, v43);
      }
      *(_DWORD *)_o__errno(v44, v41, v43, v42) = 22;
      invalid_parameter_noinfo();
    }
  }
  else
  {
    v39 = 0;
  }
LABEL_52:
  v92 = v39;
  std::wstring::~wstring(v95);
  v45 = lpMem[0];
  if ( lpMem[0] )
  {
    v46 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v46 )
    {
      if ( v46 < 0 )
        abort();
    }
    else
    {
      v47 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v47, 0, v45);
    }
  }
  v48 = (char *)this + 8;
  winrt::hstring::operator=((char *)this + 8, &v92);
  v49 = v92;
  if ( v92 )
  {
    v50 = _InterlockedDecrement((volatile signed __int32 *)v92 + 6);
    if ( !v50 )
    {
      v51 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v51, 0, v49);
      goto LABEL_58;
    }
    if ( v50 < 0 )
LABEL_72:
      abort();
  }
LABEL_58:
  if ( *(_QWORD *)v48 )
    v4 = *(const wchar_t **)(*(_QWORD *)v48 + 16LL);
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v52 = -1;
  do
    ++v52;
  while ( v4[v52] );
  std::wstring::_Construct<1,unsigned short const *>(&v97, v4, v52);
  v100 = 0;
  v101 = 0;
  v102 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v100, L"SWD\\MIDISRV\\", 12);
  v53 = v101;
  v54 = &v100;
  if ( v102 > 7 )
    v54 = (__int128 *)v100;
  v55 = v98;
  v56 = &v97;
  v57 = (__int128 *)v97;
  v58 = v99;
  if ( v99 > 7 )
    v56 = (__int128 *)v97;
  if ( v101 > v98 )
  {
    v59 = -1;
    goto LABEL_76;
  }
  if ( v101 )
  {
    v60 = (char *)v56 + 2 * v98;
    v61 = _std_search_2(v56, v60, v54, v101);
    if ( (char *)v61 == v60 )
      goto LABEL_85;
    v59 = (v61 - (__int64)v56) >> 1;
    v58 = v99;
    v55 = v98;
    v57 = (__int128 *)v97;
    v53 = v101;
LABEL_76:
    if ( v59 == -1 )
      goto LABEL_85;
    goto LABEL_77;
  }
  v59 = 0;
LABEL_77:
  v62 = v53 + v59;
  v103 = 0;
  v104 = 0;
  if ( v55 < v53 + v59 )
    std::_String_val<std::_Simple_types<char>>::_Xran(v53, v55, v54);
  v63 = v55 - v62;
  v64 = -1;
  if ( v63 != -1 )
    v64 = v63;
  v65 = &v97;
  if ( v58 > 7 )
    v65 = v57;
  std::wstring::_Construct<1,unsigned short const *>(&v103, (char *)v65 + 2 * v62, v64);
  v66 = &v103;
  if ( *((_QWORD *)&v104 + 1) > 7u )
    v66 = (__int128 *)v103;
  lpMem[0] = v66;
  lpMem[1] = (LPVOID)v104;
  winrt::hstring::operator=((char *)this + 8, lpMem);
  std::wstring::~wstring(&v103);
LABEL_85:
  v67 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 24);
  winrt::hstring::operator=((char *)this + 24, v67);
  v68 = lpMem[0];
  if ( lpMem[0] )
  {
    v69 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v69 )
    {
      if ( v69 < 0 )
        abort();
    }
    else
    {
      v70 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v70, 0, v68);
    }
  }
  v71 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 32);
  winrt::hstring::operator=((char *)this + 32, v71);
  v72 = lpMem[0];
  if ( lpMem[0] )
  {
    v73 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v73 )
    {
      if ( v73 < 0 )
        abort();
    }
    else
    {
      v74 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v74, 0, v72);
    }
  }
  v75 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 40);
  winrt::hstring::operator=((char *)this + 40, v75);
  v76 = lpMem[0];
  if ( lpMem[0] )
  {
    v77 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v77 )
    {
      if ( v77 < 0 )
        abort();
    }
    else
    {
      v78 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v78, 0, v76);
    }
  }
  v79 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 48);
  winrt::hstring::operator=((char *)this + 48, v79);
  v80 = lpMem[0];
  if ( lpMem[0] )
  {
    v81 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v81 )
    {
      if ( v81 < 0 )
        abort();
    }
    else
    {
      v82 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v82, 0, v80);
    }
  }
  v83 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 64);
  winrt::hstring::operator=((char *)this + 64, v83);
  v84 = lpMem[0];
  if ( lpMem[0] )
  {
    v85 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v85 )
    {
      if ( v85 < 0 )
        abort();
    }
    else
    {
      v86 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v86, 0, v84);
    }
  }
  v87 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 72);
  winrt::hstring::operator=((char *)this + 72, v87);
  v88 = lpMem[0];
  if ( lpMem[0] )
  {
    v89 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v89 )
    {
      if ( v89 < 0 )
        abort();
    }
    else
    {
      v90 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v90, 0, v88);
    }
  }
  std::wstring::~wstring(&v100);
  std::wstring::~wstring(&v97);
}

```

## disassembly

```asm
0x18002cf5c  push    rbp
0x18002cf5e  push    rbx
0x18002cf5f  push    rsi
0x18002cf60  push    rdi
0x18002cf61  push    r12
0x18002cf63  push    r13
0x18002cf65  push    r14
0x18002cf67  push    r15
0x18002cf69  lea     rbp, [rsp-1Fh]
0x18002cf6e  sub     rsp, 0E8h
0x18002cf75  mov     rax, cs:__security_cookie
0x18002cf7c  xor     rax, rsp
0x18002cf7f  mov     [rbp+57h+var_48], rax
0x18002cf83  mov     r14, rcx
0x18002cf86  mov     rdx, rcx
0x18002cf89  lea     rcx, [rsp+120h+lpMem]
0x18002cf8e  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18002cf93  nop
0x18002cf94  xorps   xmm0, xmm0
0x18002cf97  movups  xmmword ptr [rsp+120h+Src], xmm0
0x18002cf9c  xorps   xmm1, xmm1
0x18002cf9f  movdqu  xmmword ptr [rsp+120h+var_D8], xmm1
0x18002cfa5  mov     rcx, [rax]
0x18002cfa8  lea     r12, S1
0x18002cfaf  test    rcx, rcx
0x18002cfb2  jz      short loc_18002CFBE
0x18002cfb4  mov     rdx, [rcx+10h]
0x18002cfb8  mov     r8d, [rcx+4]
0x18002cfbc  jmp     short loc_18002CFC4
0x18002cfbe  mov     rdx, r12
0x18002cfc1  xor     r8d, r8d
0x18002cfc4  lea     rcx, [rsp+120h+Src]
0x18002cfc9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cfce  nop
0x18002cfcf  mov     rcx, [rbp+57h+var_D8+8]
0x18002cfd3  mov     rax, [rsp+120h+Src]
0x18002cfd8  cmp     rcx, 7
0x18002cfdc  jbe     short loc_18002CFE6
0x18002cfde  mov     rdx, rax
0x18002cfe1  mov     rsi, rax
0x18002cfe4  jmp     short loc_18002CFF0
0x18002cfe6  lea     rsi, [rsp+120h+Src]
0x18002cfeb  lea     rdx, [rsp+120h+Src]
0x18002cff0  mov     rdi, [rsp+120h+var_D8]
0x18002cff5  lea     r15, [rdx+rdi*2]
0x18002cff9  lea     rbx, [rsp+120h+Src]
0x18002cffe  cmova   rbx, rax
0x18002d002  cmp     rbx, r15
0x18002d005  jz      short loc_18002D034
0x18002d007  movzx   ecx, word ptr [rbx]
0x18002d00a  mov     rax, cs:__imp__o_towlower
0x18002d011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d016  mov     [rsi], ax
0x18002d019  lea     rsi, [rsi+2]
0x18002d01d  add     rbx, 2
0x18002d021  cmp     rbx, r15
0x18002d024  jnz     short loc_18002D007
0x18002d026  mov     rcx, [rbp+57h+var_D8+8]
0x18002d02a  mov     rdi, [rsp+120h+var_D8]
0x18002d02f  mov     rax, [rsp+120h+Src]
0x18002d034  lea     rbx, [rsp+120h+Src]
0x18002d039  cmp     rcx, 7
0x18002d03d  cmova   rbx, rax
0x18002d041  mov     r15d, 16h
0x18002d047  test    edi, edi
0x18002d049  jnz     short loc_18002D04F
0x18002d04b  xor     esi, esi
0x18002d04d  jmp     short loc_18002D08E
0x18002d04f  mov     ecx, edi; this
0x18002d051  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18002d056  mov     rsi, rax
0x18002d059  mov     r8d, edi
0x18002d05c  add     r8, r8; Size
0x18002d05f  jz      short loc_18002D08E
0x18002d061  lea     rcx, [rax+1Ch]; void *
0x18002d065  test    rcx, rcx
0x18002d068  jz      short loc_18002D080
0x18002d06a  test    rbx, rbx
0x18002d06d  jz      short loc_18002D079
0x18002d06f  mov     rdx, rbx; Src
0x18002d072  call    memcpy_0
0x18002d077  jmp     short loc_18002D08E
0x18002d079  xor     edx, edx; Val
0x18002d07b  call    memset_0
0x18002d080  call    cs:__imp__o__errno
0x18002d086  mov     [rax], r15d
0x18002d089  call    _invalid_parameter_noinfo
0x18002d08e  mov     [rsp+120h+var_F0], rsi
0x18002d093  lea     rcx, [rsp+120h+Src]; void *
0x18002d098  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d09d  nop
0x18002d09e  mov     rbx, [rsp+120h+lpMem]
0x18002d0a3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002d0a7  test    rbx, rbx
0x18002d0aa  jz      short loc_18002D0CB
0x18002d0ac  mov     eax, edi
0x18002d0ae  lock xadd [rbx+18h], eax
0x18002d0b3  sub     eax, 1
0x18002d0b6  jnz     short loc_18002D103
0x18002d0b8  nop
0x18002d0b9  call    WINRT_IMPL_GetProcessHeap
0x18002d0be  mov     rcx, rax; hHeap
0x18002d0c1  mov     r8, rbx; lpMem
0x18002d0c4  xor     edx, edx; dwFlags
0x18002d0c6  call    WINRT_IMPL_HeapFree
0x18002d0cb  lea     rdx, [rsp+120h+var_F0]
0x18002d0d0  mov     rcx, r14
0x18002d0d3  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002d0d8  mov     rbx, [rsp+120h+var_F0]
0x18002d0dd  test    rbx, rbx
0x18002d0e0  jz      short loc_18002D116
0x18002d0e2  mov     eax, edi
0x18002d0e4  lock xadd [rbx+18h], eax
0x18002d0e9  sub     eax, 1
0x18002d0ec  jnz     short loc_18002D10E
0x18002d0ee  nop
0x18002d0ef  call    WINRT_IMPL_GetProcessHeap
0x18002d0f4  mov     rcx, rax; hHeap
0x18002d0f7  mov     r8, rbx; lpMem
0x18002d0fa  xor     edx, edx; dwFlags
0x18002d0fc  call    WINRT_IMPL_HeapFree
0x18002d101  jmp     short loc_18002D116
0x18002d103  test    eax, eax
0x18002d105  jns     short loc_18002D0CB
0x18002d107  call    cs:__imp_abort
0x18002d10e  test    eax, eax
0x18002d110  js      loc_18002D334
0x18002d116  lea     rdx, [r14+8]
0x18002d11a  lea     rcx, [rsp+120h+lpMem]
0x18002d11f  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18002d124  nop
0x18002d125  xorps   xmm0, xmm0
0x18002d128  movups  xmmword ptr [rbp+57h+var_C8], xmm0
0x18002d12c  xorps   xmm1, xmm1
0x18002d12f  movdqu  xmmword ptr [rbp+57h+var_B8], xmm1
0x18002d134  mov     rcx, [rax]
0x18002d137  test    rcx, rcx
0x18002d13a  jz      short loc_18002D146
0x18002d13c  mov     rdx, [rcx+10h]
0x18002d140  mov     r8d, [rcx+4]
0x18002d144  jmp     short loc_18002D14C
0x18002d146  mov     rdx, r12
0x18002d149  xor     r8d, r8d
0x18002d14c  lea     rcx, [rbp+57h+var_C8]
0x18002d150  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d155  nop
0x18002d156  mov     rcx, [rbp+57h+var_B8+8]
0x18002d15a  mov     rax, [rbp+57h+var_C8]
0x18002d15e  cmp     rcx, 7
0x18002d162  jbe     short loc_18002D16C
0x18002d164  mov     rdx, rax
0x18002d167  mov     r15, rax
0x18002d16a  jmp     short loc_18002D174
0x18002d16c  lea     r15, [rbp+57h+var_C8]
0x18002d170  lea     rdx, [rbp+57h+var_C8]
0x18002d174  mov     rbx, [rbp+57h+var_B8]
0x18002d178  lea     r13, [rdx+rbx*2]
0x18002d17c  lea     rsi, [rbp+57h+var_C8]
0x18002d180  cmova   rsi, rax
0x18002d184  cmp     rsi, r13
0x18002d187  jz      short loc_18002D1B5
0x18002d189  movzx   ecx, word ptr [rsi]
0x18002d18c  mov     rax, cs:__imp_towupper
0x18002d193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d198  mov     [r15], ax
0x18002d19c  lea     r15, [r15+2]
0x18002d1a0  add     rsi, 2
0x18002d1a4  cmp     rsi, r13
0x18002d1a7  jnz     short loc_18002D189
0x18002d1a9  mov     rcx, [rbp+57h+var_B8+8]
0x18002d1ad  mov     rbx, [rbp+57h+var_B8]
0x18002d1b1  mov     rax, [rbp+57h+var_C8]
0x18002d1b5  lea     rsi, [rbp+57h+var_C8]
0x18002d1b9  cmp     rcx, 7
0x18002d1bd  cmova   rsi, rax
0x18002d1c1  xor     r13d, r13d
0x18002d1c4  test    ebx, ebx
0x18002d1c6  jnz     short loc_18002D1CD
0x18002d1c8  mov     r15d, r13d
0x18002d1cb  jmp     short loc_18002D20F
0x18002d1cd  mov     ecx, ebx; this
0x18002d1cf  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18002d1d4  mov     r15, rax
0x18002d1d7  mov     r8d, ebx
0x18002d1da  add     r8, r8; Size
0x18002d1dd  jz      short loc_18002D20F
0x18002d1df  lea     rcx, [rax+1Ch]; void *
0x18002d1e3  test    rcx, rcx
0x18002d1e6  jz      short loc_18002D1FE
0x18002d1e8  test    rsi, rsi
0x18002d1eb  jz      short loc_18002D1F7
0x18002d1ed  mov     rdx, rsi; Src
0x18002d1f0  call    memcpy_0
0x18002d1f5  jmp     short loc_18002D20F
0x18002d1f7  xor     edx, edx; Val
0x18002d1f9  call    memset_0
0x18002d1fe  call    cs:__imp__o__errno
0x18002d204  mov     dword ptr [rax], 16h
0x18002d20a  call    _invalid_parameter_noinfo
0x18002d20f  mov     [rsp+120h+var_F0], r15
0x18002d214  lea     rcx, [rbp+57h+var_C8]; void *
0x18002d218  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d21d  nop
0x18002d21e  mov     rbx, [rsp+120h+lpMem]
0x18002d223  test    rbx, rbx
0x18002d226  jz      short loc_18002D24B
0x18002d228  mov     eax, edi
0x18002d22a  lock xadd [rbx+18h], eax
0x18002d22f  sub     eax, 1
0x18002d232  jnz     loc_18002D31D
0x18002d238  nop
0x18002d239  call    WINRT_IMPL_GetProcessHeap
0x18002d23e  mov     rcx, rax; hHeap
0x18002d241  mov     r8, rbx; lpMem
0x18002d244  xor     edx, edx; dwFlags
0x18002d246  call    WINRT_IMPL_HeapFree
0x18002d24b  lea     rdx, [rsp+120h+var_F0]
0x18002d250  lea     r15, [r14+8]
0x18002d254  mov     rcx, r15
0x18002d257  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002d25c  mov     rbx, [rsp+120h+var_F0]
0x18002d261  test    rbx, rbx
0x18002d264  jz      short loc_18002D289
0x18002d266  mov     eax, edi
0x18002d268  lock xadd [rbx+18h], eax
0x18002d26d  sub     eax, 1
0x18002d270  jnz     loc_18002D32C
0x18002d276  nop
0x18002d277  call    WINRT_IMPL_GetProcessHeap
0x18002d27c  mov     rcx, rax; hHeap
0x18002d27f  mov     r8, rbx; lpMem
0x18002d282  xor     edx, edx; dwFlags
0x18002d284  call    WINRT_IMPL_HeapFree
0x18002d289  mov     rax, [r15]
0x18002d28c  test    rax, rax
0x18002d28f  jz      short loc_18002D295
0x18002d291  mov     r12, [rax+10h]
0x18002d295  xorps   xmm0, xmm0
0x18002d298  movups  [rbp+57h+var_A8], xmm0
0x18002d29c  mov     [rbp+57h+var_98], r13
0x18002d2a0  mov     [rbp+57h+var_90], r13
0x18002d2a4  mov     r8, rdi
0x18002d2a7  inc     r8
0x18002d2aa  cmp     [r12+r8*2], r13w
0x18002d2af  jnz     short loc_18002D2A7
0x18002d2b1  mov     rdx, r12
0x18002d2b4  lea     rcx, [rbp+57h+var_A8]
0x18002d2b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d2bd  nop
0x18002d2be  xorps   xmm0, xmm0
0x18002d2c1  movups  [rbp+57h+var_88], xmm0
0x18002d2c5  mov     [rbp+57h+var_78], r13
0x18002d2c9  mov     [rbp+57h+var_70], r13
0x18002d2cd  mov     r8d, 0Ch
0x18002d2d3  lea     rdx, aSwdMidisrv; "SWD\\MIDISRV\\"
0x18002d2da  lea     rcx, [rbp+57h+var_88]
0x18002d2de  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d2e3  nop
0x18002d2e4  mov     rcx, [rbp+57h+var_78]
0x18002d2e8  lea     r8, [rbp+57h+var_88]
0x18002d2ec  cmp     [rbp+57h+var_70], 7
0x18002d2f1  cmova   r8, qword ptr [rbp+57h+var_88]
0x18002d2f6  mov     rdx, [rbp+57h+var_98]
0x18002d2fa  lea     rsi, [rbp+57h+var_A8]
0x18002d2fe  mov     r10, qword ptr [rbp+57h+var_A8]
0x18002d302  mov     r11, [rbp+57h+var_90]
0x18002d306  cmp     r11, 7
0x18002d30a  cmova   rsi, r10
0x18002d30e  cmp     rcx, rdx
0x18002d311  ja      short loc_18002D36E
0x18002d313  test    rcx, rcx
0x18002d316  jnz     short loc_18002D33B
0x18002d318  mov     rax, r13
0x18002d31b  jmp     short loc_18002D376
0x18002d31d  test    eax, eax
0x18002d31f  jns     loc_18002D24B
0x18002d325  call    cs:__imp_abort
0x18002d32c  test    eax, eax
0x18002d32e  jns     loc_18002D289
0x18002d334  call    cs:__imp_abort
0x18002d33b  lea     rbx, [rsi+rdx*2]
0x18002d33f  mov     r9, rcx
0x18002d342  mov     rdx, rbx
0x18002d345  mov     rcx, rsi
0x18002d348  call    __std_search_2
0x18002d34d  cmp     rax, rbx
0x18002d350  jz      loc_18002D3EC
0x18002d356  sub     rax, rsi
0x18002d359  sar     rax, 1
0x18002d35c  mov     r11, [rbp+57h+var_90]
0x18002d360  mov     rdx, [rbp+57h+var_98]
0x18002d364  mov     r10, qword ptr [rbp+57h+var_A8]
0x18002d368  mov     rcx, [rbp+57h+var_78]
0x18002d36c  jmp     short loc_18002D371
0x18002d36e  mov     rax, rdi
0x18002d371  cmp     rax, rdi
0x18002d374  jz      short loc_18002D3EC
0x18002d376  lea     r9, [rcx+rax]
0x18002d37a  xorps   xmm0, xmm0
0x18002d37d  movups  [rbp+57h+var_68], xmm0
  ... truncated ...
```
