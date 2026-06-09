# WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(void)

- ea: `0x18004dbac`
- end: `0x18004e278`
- name: `?Normalize@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAAXXZ`
- size: `1740`
- prototype: `void __fastcall(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *__hidden this)`
- caller_count: `4`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x180024c84`
- `0x180039c00`
- `0x18004d0f4`
- `0x18004d91c`

## callees

- `0x180004af0`
- `0x180005020`
- `0x180005e16`
- `0x180005e84`
- `0x180005e9c`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000d430`
- `0x180013118`
- `0x180014f84`
- `0x18001a124`
- `0x18001b370`
- `0x180022f64`
- `0x18004c140`
- `0x18004dbac`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004dcd0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004de4e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004dcd0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004de4e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004dd57`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004df75`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004df84`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e220`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e22f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e23e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e24d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e25c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e26b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004dd57`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004df75`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004df84`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e220`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e22f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e23e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e24d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e25c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004e26b`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18004dc5a`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18004dddc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *this)
{
  const wchar_t *v2; // r12
  winrt::impl *v3; // rcx
  void **v4; // rax
  void **v5; // rdx
  void **v6; // rsi
  unsigned int v7; // edi
  void **v8; // r15
  void **v9; // rbx
  void **v10; // rbx
  struct winrt::impl::shared_hstring_header *v11; // rsi
  struct winrt::impl::shared_hstring_header *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r9
  size_t v15; // r8
  void *v16; // rcx
  void *v17; // rbx
  int v18; // eax
  HANDLE ProcessHeap; // rax
  void *v20; // rbx
  int v21; // eax
  HANDLE v22; // rax
  winrt::impl *v23; // rcx
  void **v24; // rax
  void **v25; // rdx
  void **v26; // r15
  unsigned int v27; // ebx
  void **v28; // r13
  void **v29; // rsi
  void **v30; // rsi
  struct winrt::impl::shared_hstring_header *v31; // r15
  struct winrt::impl::shared_hstring_header *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r9
  size_t v35; // r8
  void *v36; // rcx
  void *v37; // rbx
  int v38; // eax
  HANDLE v39; // rax
  char *v40; // r15
  void *v41; // rbx
  int v42; // eax
  HANDLE v43; // rax
  __int64 v44; // r8
  unsigned __int64 v45; // rcx
  __int128 *v46; // r8
  unsigned __int64 v47; // rdx
  __int128 *v48; // rsi
  __int64 v49; // rax
  char *v50; // rbx
  __int64 v51; // rax
  __int128 *v52; // rax
  __int64 v53; // rax
  void *v54; // rbx
  int v55; // eax
  HANDLE v56; // rax
  __int64 v57; // rax
  void *v58; // rbx
  int v59; // eax
  HANDLE v60; // rax
  __int64 v61; // rax
  void *v62; // rbx
  int v63; // eax
  HANDLE v64; // rax
  __int64 v65; // rax
  void *v66; // rbx
  int v67; // eax
  HANDLE v68; // rax
  __int64 v69; // rax
  void *v70; // rbx
  int v71; // eax
  HANDLE v72; // rax
  __int64 v73; // rax
  void *v74; // rbx
  int v75; // edi
  HANDLE v76; // rax
  LPVOID lpMem[2]; // [rsp+20h] [rbp-A9h] BYREF
  LPVOID v78; // [rsp+30h] [rbp-99h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-91h] BYREF
  winrt::impl *v80[2]; // [rsp+48h] [rbp-81h]
  void *v81[2]; // [rsp+58h] [rbp-71h] BYREF
  winrt::impl *v82[2]; // [rsp+68h] [rbp-61h]
  __int128 v83; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int64 v84; // [rsp+88h] [rbp-41h]
  unsigned __int64 v85; // [rsp+90h] [rbp-39h]
  __int128 v86; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int64 v87; // [rsp+A8h] [rbp-21h]
  unsigned __int64 v88; // [rsp+B0h] [rbp-19h]
  __int128 v89; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v90; // [rsp+C8h] [rbp-1h]

  WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, this);
  *(_OWORD *)Src = 0;
  *(_OWORD *)v80 = 0;
  v2 = &S1;
  std::wstring::_Construct<1,unsigned short const *>(Src);
  v3 = v80[1];
  v4 = (void **)Src[0];
  if ( v80[1] <= (winrt::impl *)7 )
  {
    v6 = Src;
    v5 = Src;
  }
  else
  {
    v5 = (void **)Src[0];
    v6 = (void **)Src[0];
  }
  v7 = (unsigned int)v80[0];
  v8 = (void **)((char *)v5 + 2 * (__int64)v80[0]);
  v9 = Src;
  if ( v80[1] > (winrt::impl *)7 )
    v9 = (void **)Src[0];
  if ( v9 != v8 )
  {
    do
    {
      *(_WORD *)v6 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*(unsigned __int16 *)v9);
      v6 = (void **)((char *)v6 + 2);
      v9 = (void **)((char *)v9 + 2);
    }
    while ( v9 != v8 );
    v3 = v80[1];
    v7 = (unsigned int)v80[0];
    v4 = (void **)Src[0];
  }
  v10 = Src;
  if ( (unsigned __int64)v3 > 7 )
    v10 = v4;
  if ( !v7 )
  {
    v11 = 0;
    goto LABEL_19;
  }
  v12 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v7, (unsigned int)v5);
  v11 = v12;
  v15 = 2LL * v7;
  if ( v15 )
  {
    v16 = (char *)v12 + 28;
    if ( v12 != (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      if ( v10 )
      {
        memcpy_0(v16, v10, v15);
        goto LABEL_19;
      }
      memset_0(v16, 0, v15);
    }
    *(_DWORD *)_o__errno(v16, v13, v15, v14) = 22;
    invalid_parameter_noinfo();
  }
LABEL_19:
  v78 = v11;
  std::wstring::~wstring(Src);
  v17 = lpMem[0];
  if ( lpMem[0] )
  {
    v18 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v17);
    }
  }
  winrt::hstring::operator=(this, &v78);
  v20 = v78;
  if ( v78 )
  {
    v21 = _InterlockedDecrement((volatile signed __int32 *)v78 + 6);
    if ( v21 )
    {
      if ( v21 < 0 )
        goto LABEL_66;
    }
    else
    {
      v22 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v22, 0, v20);
    }
  }
  WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 8);
  *(_OWORD *)v81 = 0;
  *(_OWORD *)v82 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v81);
  v23 = v82[1];
  v24 = (void **)v81[0];
  if ( v82[1] <= (winrt::impl *)7 )
  {
    v26 = v81;
    v25 = v81;
  }
  else
  {
    v25 = (void **)v81[0];
    v26 = (void **)v81[0];
  }
  v27 = (unsigned int)v82[0];
  v28 = (void **)((char *)v25 + 2 * (__int64)v82[0]);
  v29 = v81;
  if ( v82[1] > (winrt::impl *)7 )
    v29 = (void **)v81[0];
  if ( v29 != v28 )
  {
    do
    {
      *(_WORD *)v26 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v29);
      v26 = (void **)((char *)v26 + 2);
      v29 = (void **)((char *)v29 + 2);
    }
    while ( v29 != v28 );
    v23 = v82[1];
    v27 = (unsigned int)v82[0];
    v24 = (void **)v81[0];
  }
  v30 = v81;
  if ( (unsigned __int64)v23 > 7 )
    v30 = v24;
  if ( v27 )
  {
    v32 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v27, (unsigned int)v25);
    v31 = v32;
    v35 = 2LL * v27;
    if ( v35 )
    {
      v36 = (char *)v32 + 28;
      if ( v32 != (struct winrt::impl::shared_hstring_header *)-28LL )
      {
        if ( v30 )
        {
          memcpy_0(v36, v30, v35);
          goto LABEL_46;
        }
        memset_0(v36, 0, v35);
      }
      *(_DWORD *)_o__errno(v36, v33, v35, v34) = 22;
      invalid_parameter_noinfo();
    }
  }
  else
  {
    v31 = 0;
  }
LABEL_46:
  v78 = v31;
  std::wstring::~wstring(v81);
  v37 = lpMem[0];
  if ( lpMem[0] )
  {
    v38 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v38 )
    {
      if ( v38 < 0 )
        abort();
    }
    else
    {
      v39 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v39, 0, v37);
    }
  }
  v40 = (char *)this + 8;
  winrt::hstring::operator=((char *)this + 8, &v78);
  v41 = v78;
  if ( v78 )
  {
    v42 = _InterlockedDecrement((volatile signed __int32 *)v78 + 6);
    if ( !v42 )
    {
      v43 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v43, 0, v41);
      goto LABEL_52;
    }
    if ( v42 < 0 )
LABEL_66:
      abort();
  }
LABEL_52:
  if ( *(_QWORD *)v40 )
    v2 = *(const wchar_t **)(*(_QWORD *)v40 + 16LL);
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v44 = -1;
  do
    ++v44;
  while ( v2[v44] );
  std::wstring::_Construct<1,unsigned short const *>(&v83);
  v86 = 0;
  v87 = 0;
  v88 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v86);
  v45 = v87;
  v46 = &v86;
  if ( v88 > 7 )
    v46 = (__int128 *)v86;
  v47 = v84;
  v48 = &v83;
  if ( v85 > 7 )
    v48 = (__int128 *)v83;
  if ( v87 > v84 )
  {
    v49 = -1;
    goto LABEL_70;
  }
  if ( v87 )
  {
    v50 = (char *)v48 + 2 * v84;
    v51 = _std_search_2(v48, v50, v46, v87);
    if ( (char *)v51 == v50 )
      goto LABEL_75;
    v49 = (v51 - (__int64)v48) >> 1;
    v47 = v84;
    v45 = v87;
LABEL_70:
    if ( v49 == -1 )
      goto LABEL_75;
    goto LABEL_71;
  }
  v49 = 0;
LABEL_71:
  v89 = 0;
  v90 = 0;
  if ( v47 < v45 + v49 )
    std::_String_val<std::_Simple_types<char>>::_Xran(v45, v47, v46);
  std::wstring::_Construct<1,unsigned short const *>(&v89);
  v52 = &v89;
  if ( *((_QWORD *)&v90 + 1) > 7u )
    v52 = (__int128 *)v89;
  lpMem[0] = v52;
  lpMem[1] = (LPVOID)v90;
  winrt::hstring::operator=((char *)this + 8, lpMem);
  std::wstring::~wstring(&v89);
LABEL_75:
  v53 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 24);
  winrt::hstring::operator=((char *)this + 24, v53);
  v54 = lpMem[0];
  if ( lpMem[0] )
  {
    v55 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v55 )
    {
      if ( v55 < 0 )
        abort();
    }
    else
    {
      v56 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v56, 0, v54);
    }
  }
  v57 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 32);
  winrt::hstring::operator=((char *)this + 32, v57);
  v58 = lpMem[0];
  if ( lpMem[0] )
  {
    v59 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v59 )
    {
      if ( v59 < 0 )
        abort();
    }
    else
    {
      v60 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v60, 0, v58);
    }
  }
  v61 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 40);
  winrt::hstring::operator=((char *)this + 40, v61);
  v62 = lpMem[0];
  if ( lpMem[0] )
  {
    v63 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v63 )
    {
      if ( v63 < 0 )
        abort();
    }
    else
    {
      v64 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v64, 0, v62);
    }
  }
  v65 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 48);
  winrt::hstring::operator=((char *)this + 48, v65);
  v66 = lpMem[0];
  if ( lpMem[0] )
  {
    v67 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v67 )
    {
      if ( v67 < 0 )
        abort();
    }
    else
    {
      v68 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v68, 0, v66);
    }
  }
  v69 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 64);
  winrt::hstring::operator=((char *)this + 64, v69);
  v70 = lpMem[0];
  if ( lpMem[0] )
  {
    v71 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v71 )
    {
      if ( v71 < 0 )
        abort();
    }
    else
    {
      v72 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v72, 0, v70);
    }
  }
  v73 = WindowsMidiServicesInternal::TrimmedHStringCopy(lpMem, (char *)this + 72);
  winrt::hstring::operator=((char *)this + 72, v73);
  v74 = lpMem[0];
  if ( lpMem[0] )
  {
    v75 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v75 )
    {
      if ( v75 < 0 )
        abort();
    }
    else
    {
      v76 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v76, 0, v74);
    }
  }
  std::wstring::~wstring(&v86);
  std::wstring::~wstring(&v83);
}

```

## disassembly

```asm
0x18004dbac  push    rbp
0x18004dbae  push    rbx
0x18004dbaf  push    rsi
0x18004dbb0  push    rdi
0x18004dbb1  push    r12
0x18004dbb3  push    r13
0x18004dbb5  push    r14
0x18004dbb7  push    r15
0x18004dbb9  lea     rbp, [rsp-1Fh]
0x18004dbbe  sub     rsp, 0E8h
0x18004dbc5  mov     rax, cs:__security_cookie
0x18004dbcc  xor     rax, rsp
0x18004dbcf  mov     [rbp+57h+var_48], rax
0x18004dbd3  mov     r14, rcx
0x18004dbd6  mov     rdx, rcx
0x18004dbd9  lea     rcx, [rsp+120h+lpMem]
0x18004dbde  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18004dbe3  nop
0x18004dbe4  xorps   xmm0, xmm0
0x18004dbe7  movups  xmmword ptr [rsp+120h+Src], xmm0
0x18004dbec  xorps   xmm1, xmm1
0x18004dbef  movdqu  xmmword ptr [rsp+120h+var_D8], xmm1
0x18004dbf5  mov     rcx, [rax]
0x18004dbf8  lea     r12, S1
0x18004dbff  test    rcx, rcx
0x18004dc02  jz      short loc_18004DC0E
0x18004dc04  mov     rdx, [rcx+10h]
0x18004dc08  mov     r8d, [rcx+4]
0x18004dc0c  jmp     short loc_18004DC14
0x18004dc0e  mov     rdx, r12
0x18004dc11  xor     r8d, r8d
0x18004dc14  lea     rcx, [rsp+120h+Src]
0x18004dc19  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004dc1e  nop
0x18004dc1f  mov     rcx, [rbp+57h+var_D8+8]
0x18004dc23  mov     rax, [rsp+120h+Src]
0x18004dc28  cmp     rcx, 7
0x18004dc2c  jbe     short loc_18004DC36
0x18004dc2e  mov     rdx, rax
0x18004dc31  mov     rsi, rax
0x18004dc34  jmp     short loc_18004DC40
0x18004dc36  lea     rsi, [rsp+120h+Src]
0x18004dc3b  lea     rdx, [rsp+120h+Src]
0x18004dc40  mov     rdi, [rsp+120h+var_D8]
0x18004dc45  lea     r15, [rdx+rdi*2]
0x18004dc49  lea     rbx, [rsp+120h+Src]
0x18004dc4e  cmova   rbx, rax
0x18004dc52  cmp     rbx, r15
0x18004dc55  jz      short loc_18004DC84
0x18004dc57  movzx   ecx, word ptr [rbx]
0x18004dc5a  mov     rax, cs:__imp__o_towlower
0x18004dc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc66  mov     [rsi], ax
0x18004dc69  lea     rsi, [rsi+2]
0x18004dc6d  add     rbx, 2
0x18004dc71  cmp     rbx, r15
0x18004dc74  jnz     short loc_18004DC57
0x18004dc76  mov     rcx, [rbp+57h+var_D8+8]
0x18004dc7a  mov     rdi, [rsp+120h+var_D8]
0x18004dc7f  mov     rax, [rsp+120h+Src]
0x18004dc84  lea     rbx, [rsp+120h+Src]
0x18004dc89  cmp     rcx, 7
0x18004dc8d  cmova   rbx, rax
0x18004dc91  mov     r15d, 16h
0x18004dc97  test    edi, edi
0x18004dc99  jnz     short loc_18004DC9F
0x18004dc9b  xor     esi, esi
0x18004dc9d  jmp     short loc_18004DCDE
0x18004dc9f  mov     ecx, edi; this
0x18004dca1  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004dca6  mov     rsi, rax
0x18004dca9  mov     r8d, edi
0x18004dcac  add     r8, r8; Size
0x18004dcaf  jz      short loc_18004DCDE
0x18004dcb1  lea     rcx, [rax+1Ch]; void *
0x18004dcb5  test    rcx, rcx
0x18004dcb8  jz      short loc_18004DCD0
0x18004dcba  test    rbx, rbx
0x18004dcbd  jz      short loc_18004DCC9
0x18004dcbf  mov     rdx, rbx; Src
0x18004dcc2  call    memcpy_0
0x18004dcc7  jmp     short loc_18004DCDE
0x18004dcc9  xor     edx, edx; Val
0x18004dccb  call    memset_0
0x18004dcd0  call    cs:__imp__o__errno
0x18004dcd6  mov     [rax], r15d
0x18004dcd9  call    _invalid_parameter_noinfo
0x18004dcde  mov     [rsp+120h+var_F0], rsi
0x18004dce3  lea     rcx, [rsp+120h+Src]; void *
0x18004dce8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004dced  nop
0x18004dcee  mov     rbx, [rsp+120h+lpMem]
0x18004dcf3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004dcf7  test    rbx, rbx
0x18004dcfa  jz      short loc_18004DD1B
0x18004dcfc  mov     eax, edi
0x18004dcfe  lock xadd [rbx+18h], eax
0x18004dd03  sub     eax, 1
0x18004dd06  jnz     short loc_18004DD53
0x18004dd08  nop
0x18004dd09  call    WINRT_IMPL_GetProcessHeap
0x18004dd0e  mov     rcx, rax; hHeap
0x18004dd11  mov     r8, rbx; lpMem
0x18004dd14  xor     edx, edx; dwFlags
0x18004dd16  call    WINRT_IMPL_HeapFree
0x18004dd1b  lea     rdx, [rsp+120h+var_F0]
0x18004dd20  mov     rcx, r14
0x18004dd23  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004dd28  mov     rbx, [rsp+120h+var_F0]
0x18004dd2d  test    rbx, rbx
0x18004dd30  jz      short loc_18004DD66
0x18004dd32  mov     eax, edi
0x18004dd34  lock xadd [rbx+18h], eax
0x18004dd39  sub     eax, 1
0x18004dd3c  jnz     short loc_18004DD5E
0x18004dd3e  nop
0x18004dd3f  call    WINRT_IMPL_GetProcessHeap
0x18004dd44  mov     rcx, rax; hHeap
0x18004dd47  mov     r8, rbx; lpMem
0x18004dd4a  xor     edx, edx; dwFlags
0x18004dd4c  call    WINRT_IMPL_HeapFree
0x18004dd51  jmp     short loc_18004DD66
0x18004dd53  test    eax, eax
0x18004dd55  jns     short loc_18004DD1B
0x18004dd57  call    cs:__imp_abort
0x18004dd5e  test    eax, eax
0x18004dd60  js      loc_18004DF84
0x18004dd66  lea     rdx, [r14+8]
0x18004dd6a  lea     rcx, [rsp+120h+lpMem]
0x18004dd6f  call    ?TrimmedHStringCopy@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@AEBU23@@Z; WindowsMidiServicesInternal::TrimmedHStringCopy(winrt::hstring const &)
0x18004dd74  nop
0x18004dd75  xorps   xmm0, xmm0
0x18004dd78  movups  xmmword ptr [rbp+57h+var_C8], xmm0
0x18004dd7c  xorps   xmm1, xmm1
0x18004dd7f  movdqu  xmmword ptr [rbp+57h+var_B8], xmm1
0x18004dd84  mov     rcx, [rax]
0x18004dd87  test    rcx, rcx
0x18004dd8a  jz      short loc_18004DD96
0x18004dd8c  mov     rdx, [rcx+10h]
0x18004dd90  mov     r8d, [rcx+4]
0x18004dd94  jmp     short loc_18004DD9C
0x18004dd96  mov     rdx, r12
0x18004dd99  xor     r8d, r8d
0x18004dd9c  lea     rcx, [rbp+57h+var_C8]
0x18004dda0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004dda5  nop
0x18004dda6  mov     rcx, [rbp+57h+var_B8+8]
0x18004ddaa  mov     rax, [rbp+57h+var_C8]
0x18004ddae  cmp     rcx, 7
0x18004ddb2  jbe     short loc_18004DDBC
0x18004ddb4  mov     rdx, rax
0x18004ddb7  mov     r15, rax
0x18004ddba  jmp     short loc_18004DDC4
0x18004ddbc  lea     r15, [rbp+57h+var_C8]
0x18004ddc0  lea     rdx, [rbp+57h+var_C8]
0x18004ddc4  mov     rbx, [rbp+57h+var_B8]
0x18004ddc8  lea     r13, [rdx+rbx*2]
0x18004ddcc  lea     rsi, [rbp+57h+var_C8]
0x18004ddd0  cmova   rsi, rax
0x18004ddd4  cmp     rsi, r13
0x18004ddd7  jz      short loc_18004DE05
0x18004ddd9  movzx   ecx, word ptr [rsi]
0x18004dddc  mov     rax, cs:__imp_towupper
0x18004dde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dde8  mov     [r15], ax
0x18004ddec  lea     r15, [r15+2]
0x18004ddf0  add     rsi, 2
0x18004ddf4  cmp     rsi, r13
0x18004ddf7  jnz     short loc_18004DDD9
0x18004ddf9  mov     rcx, [rbp+57h+var_B8+8]
0x18004ddfd  mov     rbx, [rbp+57h+var_B8]
0x18004de01  mov     rax, [rbp+57h+var_C8]
0x18004de05  lea     rsi, [rbp+57h+var_C8]
0x18004de09  cmp     rcx, 7
0x18004de0d  cmova   rsi, rax
0x18004de11  xor     r13d, r13d
0x18004de14  test    ebx, ebx
0x18004de16  jnz     short loc_18004DE1D
0x18004de18  mov     r15d, r13d
0x18004de1b  jmp     short loc_18004DE5F
0x18004de1d  mov     ecx, ebx; this
0x18004de1f  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004de24  mov     r15, rax
0x18004de27  mov     r8d, ebx
0x18004de2a  add     r8, r8; Size
0x18004de2d  jz      short loc_18004DE5F
0x18004de2f  lea     rcx, [rax+1Ch]; void *
0x18004de33  test    rcx, rcx
0x18004de36  jz      short loc_18004DE4E
0x18004de38  test    rsi, rsi
0x18004de3b  jz      short loc_18004DE47
0x18004de3d  mov     rdx, rsi; Src
0x18004de40  call    memcpy_0
0x18004de45  jmp     short loc_18004DE5F
0x18004de47  xor     edx, edx; Val
0x18004de49  call    memset_0
0x18004de4e  call    cs:__imp__o__errno
0x18004de54  mov     dword ptr [rax], 16h
0x18004de5a  call    _invalid_parameter_noinfo
0x18004de5f  mov     [rsp+120h+var_F0], r15
0x18004de64  lea     rcx, [rbp+57h+var_C8]; void *
0x18004de68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004de6d  nop
0x18004de6e  mov     rbx, [rsp+120h+lpMem]
0x18004de73  test    rbx, rbx
0x18004de76  jz      short loc_18004DE9B
0x18004de78  mov     eax, edi
0x18004de7a  lock xadd [rbx+18h], eax
0x18004de7f  sub     eax, 1
0x18004de82  jnz     loc_18004DF6D
0x18004de88  nop
0x18004de89  call    WINRT_IMPL_GetProcessHeap
0x18004de8e  mov     rcx, rax; hHeap
0x18004de91  mov     r8, rbx; lpMem
0x18004de94  xor     edx, edx; dwFlags
0x18004de96  call    WINRT_IMPL_HeapFree
0x18004de9b  lea     rdx, [rsp+120h+var_F0]
0x18004dea0  lea     r15, [r14+8]
0x18004dea4  mov     rcx, r15
0x18004dea7  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004deac  mov     rbx, [rsp+120h+var_F0]
0x18004deb1  test    rbx, rbx
0x18004deb4  jz      short loc_18004DED9
0x18004deb6  mov     eax, edi
0x18004deb8  lock xadd [rbx+18h], eax
0x18004debd  sub     eax, 1
0x18004dec0  jnz     loc_18004DF7C
0x18004dec6  nop
0x18004dec7  call    WINRT_IMPL_GetProcessHeap
0x18004decc  mov     rcx, rax; hHeap
0x18004decf  mov     r8, rbx; lpMem
0x18004ded2  xor     edx, edx; dwFlags
0x18004ded4  call    WINRT_IMPL_HeapFree
0x18004ded9  mov     rax, [r15]
0x18004dedc  test    rax, rax
0x18004dedf  jz      short loc_18004DEE5
0x18004dee1  mov     r12, [rax+10h]
0x18004dee5  xorps   xmm0, xmm0
0x18004dee8  movups  [rbp+57h+var_A8], xmm0
0x18004deec  mov     [rbp+57h+var_98], r13
0x18004def0  mov     [rbp+57h+var_90], r13
0x18004def4  mov     r8, rdi
0x18004def7  inc     r8
0x18004defa  cmp     [r12+r8*2], r13w
0x18004deff  jnz     short loc_18004DEF7
0x18004df01  mov     rdx, r12
0x18004df04  lea     rcx, [rbp+57h+var_A8]
0x18004df08  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004df0d  nop
0x18004df0e  xorps   xmm0, xmm0
0x18004df11  movups  [rbp+57h+var_88], xmm0
0x18004df15  mov     [rbp+57h+var_78], r13
0x18004df19  mov     [rbp+57h+var_70], r13
0x18004df1d  mov     r8d, 0Ch
0x18004df23  lea     rdx, aSwdMidisrv; "SWD\\MIDISRV\\"
0x18004df2a  lea     rcx, [rbp+57h+var_88]
0x18004df2e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004df33  nop
0x18004df34  mov     rcx, [rbp+57h+var_78]
0x18004df38  lea     r8, [rbp+57h+var_88]
0x18004df3c  cmp     [rbp+57h+var_70], 7
0x18004df41  cmova   r8, qword ptr [rbp+57h+var_88]
0x18004df46  mov     rdx, [rbp+57h+var_98]
0x18004df4a  lea     rsi, [rbp+57h+var_A8]
0x18004df4e  mov     r10, qword ptr [rbp+57h+var_A8]
0x18004df52  mov     r11, [rbp+57h+var_90]
0x18004df56  cmp     r11, 7
0x18004df5a  cmova   rsi, r10
0x18004df5e  cmp     rcx, rdx
0x18004df61  ja      short loc_18004DFBE
0x18004df63  test    rcx, rcx
0x18004df66  jnz     short loc_18004DF8B
0x18004df68  mov     rax, r13
0x18004df6b  jmp     short loc_18004DFC6
0x18004df6d  test    eax, eax
0x18004df6f  jns     loc_18004DE9B
0x18004df75  call    cs:__imp_abort
0x18004df7c  test    eax, eax
0x18004df7e  jns     loc_18004DED9
0x18004df84  call    cs:__imp_abort
0x18004df8b  lea     rbx, [rsi+rdx*2]
0x18004df8f  mov     r9, rcx
0x18004df92  mov     rdx, rbx
0x18004df95  mov     rcx, rsi
0x18004df98  call    __std_search_2
0x18004df9d  cmp     rax, rbx
0x18004dfa0  jz      loc_18004E03C
0x18004dfa6  sub     rax, rsi
0x18004dfa9  sar     rax, 1
0x18004dfac  mov     r11, [rbp+57h+var_90]
0x18004dfb0  mov     rdx, [rbp+57h+var_98]
0x18004dfb4  mov     r10, qword ptr [rbp+57h+var_A8]
0x18004dfb8  mov     rcx, [rbp+57h+var_78]
0x18004dfbc  jmp     short loc_18004DFC1
0x18004dfbe  mov     rax, rdi
0x18004dfc1  cmp     rax, rdi
0x18004dfc4  jz      short loc_18004E03C
0x18004dfc6  lea     r9, [rcx+rax]
0x18004dfca  xorps   xmm0, xmm0
0x18004dfcd  movups  [rbp+57h+var_68], xmm0
  ... truncated ...
```
