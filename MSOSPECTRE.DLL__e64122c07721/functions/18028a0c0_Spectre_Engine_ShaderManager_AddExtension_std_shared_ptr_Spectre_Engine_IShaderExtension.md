# Spectre::Engine::ShaderManager::AddExtension(std::shared_ptr<Spectre::Engine::IShaderExtension>)

- ea: `0x18028a0c0`
- end: `0x18028a83e`
- name: `?AddExtension@ShaderManager@Engine@Spectre@@QEAAXV?$shared_ptr@VIShaderExtension@Engine@Spectre@@@std@@@Z`
- size: `1918`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802247c0`

## callees

- `0x180014b80`
- `0x180015770`
- `0x1800157b0`
- `0x180017670`
- `0x180029b60`
- `0x18002e6b0`
- `0x1801b51d0`
- `0x1801cc6d0`
- `0x18020e630`
- `0x18021afc0`
- `0x18021b930`
- `0x180228ea0`
- `0x180279a70`
- `0x18027ad80`
- `0x18027b210`
- `0x180288bc0`
- `0x180289e00`
- `0x18028a0c0`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f920`
- `0x1804f99e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18028a263`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18028a64f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18028a6f1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18028a263`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18028a64f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18028a6f1`

## string_xrefs

- `0x18028a785`: `ShaderManager::AddExtension() -- Extension passed to function cannot be null`
- `0x18028a7ec`: `' is already installed`
- `0x18028a7db`: `ShaderManager::AddExtension() -- Extension with name '`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Spectre::Engine::ShaderManager::AddExtension(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 *v5; // r12
  __int64 v6; // rsi
  __int64 v7; // rdi
  unsigned __int64 v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rbx
  __int64 inserted; // r15
  unsigned __int64 v12; // r13
  size_t v13; // r14
  void **i; // r8
  void **v15; // rdx
  const void *v16; // rcx
  size_t v17; // rdi
  size_t v18; // r8
  int v19; // eax
  const void *v20; // rdx
  void **v21; // rcx
  size_t v22; // rbx
  size_t v23; // r8
  int v24; // eax
  __int64 *v25; // rdi
  _QWORD *v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rdx
  volatile signed __int32 *v29; // rbx
  _QWORD *v30; // rbx
  __int64 v31; // r14
  _QWORD *v32; // rax
  __int64 v33; // rcx
  unsigned int v34; // r15d
  char *v35; // r14
  char *v36; // rbx
  __int64 v37; // rcx
  __int64 *v38; // rdi
  volatile signed __int32 *v39; // rbx
  __int64 v40; // rdi
  volatile signed __int32 *v41; // rdi
  char *v42; // rax
  void *v43; // rcx
  volatile signed __int32 *v44; // rbx
  int v45; // eax
  __int64 v46; // rax
  int v47; // ebx
  int v48; // eax
  __int64 v49; // [rsp+30h] [rbp-D0h]
  __int128 v50; // [rsp+30h] [rbp-D0h]
  __int128 v51; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v52; // [rsp+50h] [rbp-B0h]
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  int v54; // [rsp+68h] [rbp-98h]
  __int128 v55; // [rsp+80h] [rbp-80h]
  __int64 *v56; // [rsp+90h] [rbp-70h]
  __int64 *v57; // [rsp+98h] [rbp-68h]
  _BYTE v58[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-50h]
  _QWORD *v60; // [rsp+C0h] [rbp-40h]
  _BYTE pExceptionObject[64]; // [rsp+D0h] [rbp-30h] BYREF
  char v62[16]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v63; // [rsp+120h] [rbp+20h]
  char v64[40]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v65[64]; // [rsp+150h] [rbp+50h] BYREF
  void *Buf2[2]; // [rsp+190h] [rbp+90h] BYREF
  size_t Size; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v68; // [rsp+1A8h] [rbp+A8h]
  void *Block[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v70; // [rsp+1C0h] [rbp+C0h]
  Spectre::Engine::Mutex *v71[2]; // [rsp+1C8h] [rbp+C8h]

  v52 = a2;
  *(_QWORD *)&v51 = a1;
  v60 = a2;
  if ( !*a2 )
  {
    std::string::string(&v53, "ShaderManager::AddExtension() -- Extension passed to function cannot be null");
    v45 = std::string::string(v58, "..\\Source\\Engine\\ShaderManager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v45,
      436,
      (unsigned int)&v53,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  Spectre::Engine::IShaderExtension::GetName(*a2, Buf2);
  v4 = std::string::string(pExceptionObject, Buf2);
  v5 = (__int64 *)(a1 + 2184);
  v6 = *(_QWORD *)(a1 + 2184);
  std::_Tree<std::_Tmap_traits<std::string,GLTFChannelAnimations::SamplerChannelData,std::less<std::string>,std::allocator<std::pair<std::string const,GLTFChannelAnimations::SamplerChannelData>>,0>>::_Find_lower_bound<std::string>(
    a1 + 2184,
    v58,
    v4);
  v7 = v59;
  if ( *(_BYTE *)(v59 + 25) || (unsigned __int8)std::less<std::string>::operator()(a1 + 2184, v4, v59 + 32) )
    v7 = *v5;
  v8 = *(_QWORD *)(v4 + 24);
  if ( v8 >= 0x10 )
  {
    v9 = *(_QWORD **)v4;
    if ( v8 + 1 >= 0x1000 )
    {
      if ( (unsigned __int64)v9 - *(v9 - 1) - 8 > 0x1F )
        _invalid_parameter_noinfo_noreturn();
      v9 = (_QWORD *)*(v9 - 1);
    }
    operator delete(v9);
  }
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 15;
  *(_BYTE *)v4 = 0;
  if ( v7 != v6 )
  {
    v46 = std::operator+<char>(v58);
    v47 = std::operator+<char>(&v53, v46, "' is already installed");
    v48 = std::string::string(pExceptionObject, "..\\Source\\Engine\\ShaderManager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v65, v48, 440, v47, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)v65;
  }
  Spectre::Engine::IShaderExtension::OnInstall(*a2, *(_QWORD *)(a1 + 2280), a1, a1 + 2256);
  v49 = *v5;
  v10 = *(_QWORD *)(*v5 + 8);
  v53 = v10;
  v54 = 0;
  inserted = v49;
  v12 = v68;
  v13 = Size;
  for ( i = (void **)Buf2[0]; !*(_BYTE *)(v10 + 25); i = (void **)Buf2[0] )
  {
    v53 = v10;
    v15 = Buf2;
    if ( v12 >= 0x10 )
      v15 = i;
    v16 = (const void *)(v10 + 32);
    if ( *(_QWORD *)(v10 + 56) >= 0x10u )
      v16 = *(const void **)(v10 + 32);
    v17 = *(_QWORD *)(v10 + 48);
    v18 = v17;
    if ( v13 < v17 )
      v18 = v13;
    v19 = memcmp_0(v16, v15, v18);
    if ( !v19 )
    {
      if ( v17 >= v13 )
        v19 = v17 > v13;
      else
        v19 = -1;
    }
    if ( v19 >= 0 )
    {
      v54 = 1;
      inserted = v10;
      v10 = *(_QWORD *)v10;
    }
    else
    {
      v54 = 0;
      v10 = *(_QWORD *)(v10 + 16);
    }
  }
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_39;
  v20 = (const void *)(inserted + 32);
  if ( *(_QWORD *)(inserted + 56) >= 0x10u )
    v20 = *(const void **)(inserted + 32);
  v21 = Buf2;
  if ( v12 >= 0x10 )
    v21 = i;
  v22 = *(_QWORD *)(inserted + 48);
  v23 = v13;
  if ( v22 < v13 )
    v23 = *(_QWORD *)(inserted + 48);
  v24 = memcmp_0(v21, v20, v23);
  if ( !v24 )
  {
    if ( v13 >= v22 )
      v24 = v13 > v22;
    else
      v24 = -1;
  }
  if ( v24 < 0 )
  {
LABEL_39:
    if ( v5[1] == 0x333333333333333LL )
      std::_Throw_tree_length_error();
    v56 = v5;
    v25 = (__int64 *)operator new(0x50u);
    v57 = v25;
    std::string::string(v25 + 4, Buf2);
    v25[8] = 0;
    v25[9] = 0;
    *v25 = v49;
    v25[1] = v49;
    v25[2] = v49;
    *((_WORD *)v25 + 12) = 0;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>>>::_Insert_node(
                 v5,
                 &v53,
                 v25);
  }
  v26 = v52;
  v27 = *v52;
  v28 = v52[1];
  *v52 = 0;
  v26[1] = 0;
  *(_QWORD *)(inserted + 64) = v27;
  v29 = *(volatile signed __int32 **)(inserted + 72);
  *(_QWORD *)(inserted + 72) = v28;
  if ( v29 )
  {
    if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
      if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
    }
  }
  v30 = (_QWORD *)std::string::string(v64, Buf2);
  v52 = v30;
  std::_Tree<std::_Tmap_traits<std::string,GLTFChannelAnimations::SamplerChannelData,std::less<std::string>,std::allocator<std::pair<std::string const,GLTFChannelAnimations::SamplerChannelData>>,0>>::_Find_lower_bound<std::string>(
    v51 + 2152,
    v62,
    v30);
  v31 = v63;
  if ( *(_BYTE *)(v63 + 25) || (unsigned __int8)std::less<std::string>::operator()(v51 + 2152, v30, v63 + 32) )
    v31 = *(_QWORD *)(v51 + 2152);
  if ( v31 == *(_QWORD *)(v51 + 2152) )
  {
    v50 = 0;
  }
  else
  {
    v32 = (_QWORD *)std::map<std::string,std::shared_ptr<Spectre::Engine::ShaderFamily>>::operator[](v51 + 2152, v30);
    v33 = v32[1];
    if ( v33 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
      v33 = v32[1];
    }
    *(_QWORD *)&v50 = *v32;
    *((_QWORD *)&v50 + 1) = v33;
  }
  std::string::~string(v30);
  *(_OWORD *)Block = 0;
  v70 = 0;
  Spectre::Engine::Engine::SafeGetDeviceList(*(_QWORD *)(v51 + 2280), Block);
  v34 = 0;
  v35 = (char *)Block[1];
  v36 = (char *)Block[0];
  if ( ((char *)Block[1] - (char *)Block[0]) >> 4 )
  {
    v37 = 0;
    do
    {
      v55 = 0;
      v38 = (__int64 *)&v36[16 * v37];
      v39 = (volatile signed __int32 *)v38[1];
      if ( v39 )
      {
        _InterlockedIncrement(v39 + 2);
        v39 = (volatile signed __int32 *)v38[1];
      }
      v40 = *v38;
      *(_QWORD *)&v55 = v40;
      *((_QWORD *)&v55 + 1) = v39;
      *(_OWORD *)v71 = 0;
      Spectre::Engine::Lockable::GetExclusiveLock((Spectre::Utils::SharedMutex *)(v40 + 24));
      v51 = 0;
      if ( v39 )
      {
        _InterlockedIncrement(v39 + 2);
        v40 = v55;
      }
      *(_QWORD *)&v51 = v40;
      *((_QWORD *)&v51 + 1) = v39;
      Spectre::Engine::ShaderFamily::AttachDevice(v50, &v51);
      if ( LOBYTE(v71[1]) )
        Spectre::Engine::Mutex::unlock(v71[0]);
      if ( v39 )
      {
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
          if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        }
      }
      ++v34;
      v35 = (char *)Block[1];
      v36 = (char *)Block[0];
      v37 = v34;
    }
    while ( v34 < (unsigned __int64)(((char *)Block[1] - (char *)Block[0]) >> 4) );
  }
  if ( v36 )
  {
    if ( v36 != v35 )
    {
      do
      {
        v41 = (volatile signed __int32 *)*((_QWORD *)v36 + 1);
        if ( v41 )
        {
          if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
            if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
          }
        }
        v36 += 16;
      }
      while ( v36 != v35 );
      v36 = (char *)Block[0];
    }
    v42 = v36;
    if ( ((v70 - (_QWORD)v36) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      v36 = (char *)*((_QWORD *)v36 - 1);
      if ( (unsigned __int64)(v42 - v36 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v36);
    *(_OWORD *)Block = 0;
    v70 = 0;
  }
  if ( *((_QWORD *)&v50 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v50 + 1))(*((_QWORD *)&v50 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v50 + 1) + 8LL))(*((_QWORD *)&v50 + 1));
    }
  }
  if ( v68 >= 0x10 )
  {
    v43 = Buf2[0];
    if ( v68 + 1 >= 0x1000 )
    {
      v43 = (void *)*((_QWORD *)Buf2[0] - 1);
      if ( (unsigned __int64)((char *)Buf2[0] - (char *)v43 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v43);
  }
  Size = 0;
  v68 = 15;
  LOBYTE(Buf2[0]) = 0;
  v44 = (volatile signed __int32 *)v26[1];
  if ( v44 && _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
    if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
  }
}

```

## disassembly

```asm
0x18028a0c0  mov     [rsp-8+arg_10], rbx
0x18028a0c5  push    rbp
0x18028a0c6  push    rsi
0x18028a0c7  push    rdi
0x18028a0c8  push    r12
0x18028a0ca  push    r13
0x18028a0cc  push    r14
0x18028a0ce  push    r15
0x18028a0d0  lea     rbp, [rsp-0E0h]
0x18028a0d8  sub     rsp, 1E0h
0x18028a0df  mov     rax, cs:__security_cookie
0x18028a0e6  xor     rax, rsp
0x18028a0e9  mov     [rbp+110h+var_38], rax
0x18028a0f0  mov     r15, rdx
0x18028a0f3  mov     [rsp+210h+var_1C0], rdx
0x18028a0f8  mov     r14, rcx
0x18028a0fb  mov     qword ptr [rsp+210h+var_1D0], rcx
0x18028a100  mov     [rbp+110h+var_150], rdx
0x18028a104  mov     rcx, [rdx]
0x18028a107  test    rcx, rcx
0x18028a10a  jz      loc_18028A785
0x18028a110  lea     rdx, [rbp+110h+Buf2]
0x18028a117  call    ?GetName@IShaderExtension@Engine@Spectre@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Spectre::Engine::IShaderExtension::GetName(void)
0x18028a11c  nop
0x18028a11d  lea     rdx, [rbp+110h+Buf2]
0x18028a124  lea     rcx, [rbp+110h+pExceptionObject]
0x18028a128  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18028a12d  mov     rbx, rax
0x18028a130  lea     r12, [r14+888h]
0x18028a137  mov     rsi, [r12]
0x18028a13b  mov     r8, rax
0x18028a13e  lea     rdx, [rbp+110h+var_170]
0x18028a142  mov     rcx, r12
0x18028a145  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,GLTFChannelAnimations::SamplerChannelData,std::less<std::string>,std::allocator<std::pair<std::string const,GLTFChannelAnimations::SamplerChannelData>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18028a14a  mov     rdi, [rbp+110h+var_160]
0x18028a14e  cmp     byte ptr [rdi+19h], 0
0x18028a152  jnz     short loc_18028A167
0x18028a154  lea     r8, [rdi+20h]
0x18028a158  mov     rdx, rbx
0x18028a15b  mov     rcx, r12
0x18028a15e  call    ??R?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEBA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::less<std::string>::operator()(std::string const &,std::string const &)
0x18028a163  test    al, al
0x18028a165  jz      short loc_18028A16B
0x18028a167  mov     rdi, [r12]
0x18028a16b  mov     rdx, [rbx+18h]
0x18028a16f  cmp     rdx, 10h
0x18028a173  jb      short loc_18028A1A5
0x18028a175  mov     rcx, [rbx]
0x18028a178  inc     rdx
0x18028a17b  cmp     rdx, 1000h
0x18028a182  jb      short loc_18028A1A0
0x18028a184  add     rdx, 27h ; '''
0x18028a188  mov     r8, [rcx-8]
0x18028a18c  sub     rcx, r8
0x18028a18f  lea     rax, [rcx-8]
0x18028a193  cmp     rax, 1Fh
0x18028a197  ja      loc_18028A263
0x18028a19d  mov     rcx, r8; Block
0x18028a1a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18028a1a5  xor     r13d, r13d
0x18028a1a8  mov     [rbx+10h], r13
0x18028a1ac  mov     qword ptr [rbx+18h], 0Fh
0x18028a1b4  mov     [rbx], r13b
0x18028a1b7  cmp     rdi, rsi
0x18028a1ba  jnz     loc_18028A7D4
0x18028a1c0  lea     r9, [r14+8D0h]
0x18028a1c7  mov     r8, r14
0x18028a1ca  mov     rdx, [r14+8E8h]
0x18028a1d1  mov     rcx, [r15]
0x18028a1d4  call    ?OnInstall@IShaderExtension@Engine@Spectre@@QEAAXPEAV223@PEAVShaderManager@23@AEBV?$vector@W4EShaderModel@Engine@Spectre@@V?$allocator@W4EShaderModel@Engine@Spectre@@@std@@@std@@@Z; Spectre::Engine::IShaderExtension::OnInstall(Spectre::Engine::Engine *,Spectre::Engine::ShaderManager *,std::vector<Spectre::Engine::EShaderModel> const &)
0x18028a1d9  mov     rax, [r12]
0x18028a1dd  mov     qword ptr [rsp+210h+var_1E0], rax
0x18028a1e2  mov     rbx, [rax+8]
0x18028a1e6  mov     qword ptr [rsp+210h+var_1B0], rbx
0x18028a1eb  mov     dword ptr [rsp+210h+var_1B0+8], r13d
0x18028a1f0  mov     r15, rax
0x18028a1f3  mov     esi, 0FFFFFFFFh
0x18028a1f8  mov     r13, [rbp+110h+var_68]
0x18028a1ff  mov     r14, [rbp+110h+Size]
0x18028a206  mov     r8, [rbp+110h+Buf2]
0x18028a20d  cmp     byte ptr [rbx+19h], 0
0x18028a211  jnz     loc_18028A2A6
0x18028a217  nop     word ptr [rax+rax+00000000h]
0x18028a220  mov     qword ptr [rsp+210h+var_1B0], rbx
0x18028a225  lea     rdx, [rbp+110h+Buf2]
0x18028a22c  cmp     r13, 10h
0x18028a230  cmovnb  rdx, r8; Buf2
0x18028a234  lea     rcx, [rbx+20h]
0x18028a238  cmp     qword ptr [rbx+38h], 10h
0x18028a23d  jb      short loc_18028A243
0x18028a23f  mov     rcx, [rbx+20h]; Buf1
0x18028a243  mov     rdi, [rbx+30h]
0x18028a247  mov     r8, rdi
0x18028a24a  cmp     r14, rdi
0x18028a24d  cmovb   r8, r14; Size
0x18028a251  call    memcmp_0
0x18028a256  test    eax, eax
0x18028a258  jnz     short loc_18028A272
0x18028a25a  cmp     rdi, r14
0x18028a25d  jnb     short loc_18028A26A
0x18028a25f  mov     eax, esi
0x18028a261  jmp     short loc_18028A272
0x18028a263  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18028a26a  xor     eax, eax
0x18028a26c  cmp     rdi, r14
0x18028a26f  setnbe  al
0x18028a272  shr     eax, 1Fh
0x18028a275  test    al, al
0x18028a277  jz      short loc_18028A287
0x18028a279  mov     dword ptr [rsp+210h+var_1B0+8], 0
0x18028a281  mov     rbx, [rbx+10h]
0x18028a285  jmp     short loc_18028A295
0x18028a287  mov     dword ptr [rsp+210h+var_1B0+8], 1
0x18028a28f  mov     r15, rbx
0x18028a292  mov     rbx, [rbx]
0x18028a295  cmp     byte ptr [rbx+19h], 0
0x18028a299  mov     r8, [rbp+110h+Buf2]
0x18028a2a0  jz      loc_18028A220
0x18028a2a6  cmp     byte ptr [r15+19h], 0
0x18028a2ab  jnz     short loc_18028A2FE
0x18028a2ad  lea     rdx, [r15+20h]
0x18028a2b1  cmp     qword ptr [r15+38h], 10h
0x18028a2b6  jb      short loc_18028A2BC
0x18028a2b8  mov     rdx, [r15+20h]; Buf2
0x18028a2bc  lea     rcx, [rbp+110h+Buf2]
0x18028a2c3  cmp     r13, 10h
0x18028a2c7  cmovnb  rcx, r8; Buf1
0x18028a2cb  mov     rbx, [r15+30h]
0x18028a2cf  mov     r8, r14
0x18028a2d2  cmp     rbx, r14
0x18028a2d5  cmovb   r8, rbx; Size
0x18028a2d9  call    memcmp_0
0x18028a2de  xor     r13d, r13d
0x18028a2e1  test    eax, eax
0x18028a2e3  jnz     short loc_18028A2F7
0x18028a2e5  cmp     r14, rbx
0x18028a2e8  jnb     short loc_18028A2EE
0x18028a2ea  mov     eax, esi
0x18028a2ec  jmp     short loc_18028A2F7
0x18028a2ee  mov     eax, r13d
0x18028a2f1  cmp     r14, rbx
0x18028a2f4  setnbe  al
0x18028a2f7  shr     eax, 1Fh
0x18028a2fa  test    al, al
0x18028a2fc  jz      short loc_18028A378
0x18028a2fe  mov     rax, 333333333333333h
0x18028a308  cmp     [r12+8], rax
0x18028a30d  jz      loc_18028A77F
0x18028a313  mov     [rbp+110h+var_180], r12
0x18028a317  xor     r13d, r13d
0x18028a31a  mov     [rbp+110h+var_178], r13
0x18028a31e  lea     ecx, [r13+50h]; Size
0x18028a322  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18028a327  mov     rdi, rax
0x18028a32a  mov     [rbp+110h+var_178], rax
0x18028a32e  lea     rdx, [rbp+110h+Buf2]
0x18028a335  lea     rcx, [rax+20h]
0x18028a339  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18028a33e  mov     [rdi+40h], r13
0x18028a342  mov     [rdi+48h], r13
0x18028a346  mov     rax, qword ptr [rsp+210h+var_1E0]
0x18028a34b  mov     [rdi], rax
0x18028a34e  mov     [rdi+8], rax
0x18028a352  mov     [rdi+10h], rax
0x18028a356  mov     [rdi+18h], r13w
0x18028a35b  movups  xmm0, [rsp+210h+var_1B0]
0x18028a360  movaps  [rsp+210h+var_1B0], xmm0
0x18028a365  mov     r8, rdi
0x18028a368  lea     rdx, [rsp+210h+var_1B0]
0x18028a36d  mov     rcx, r12
0x18028a370  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>,void *> *>,std::_Tree_node<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>,void *> * const)
0x18028a375  mov     r15, rax
0x18028a378  mov     r12, [rsp+210h+var_1C0]
0x18028a37d  mov     rcx, [r12]
0x18028a381  mov     rdx, [r12+8]
0x18028a386  mov     [r12], r13
0x18028a38a  mov     [r12+8], r13
0x18028a38f  mov     [r15+40h], rcx
0x18028a393  mov     rbx, [r15+48h]
0x18028a397  mov     [r15+48h], rdx
0x18028a39b  test    rbx, rbx
0x18028a39e  jz      short loc_18028A3D7
0x18028a3a0  mov     eax, esi
0x18028a3a2  lock xadd [rbx+8], eax
0x18028a3a7  cmp     eax, 1
0x18028a3aa  jnz     short loc_18028A3D7
0x18028a3ac  mov     rax, [rbx]
0x18028a3af  mov     rcx, rbx
0x18028a3b2  mov     rax, [rax]
0x18028a3b5  call    cs:__guard_dispatch_icall_fptr
0x18028a3bb  mov     eax, esi
0x18028a3bd  lock xadd [rbx+0Ch], eax
0x18028a3c2  cmp     eax, 1
0x18028a3c5  jnz     short loc_18028A3D7
0x18028a3c7  mov     rax, [rbx]
0x18028a3ca  mov     rcx, rbx
0x18028a3cd  mov     rax, [rax+8]
0x18028a3d1  call    cs:__guard_dispatch_icall_fptr
0x18028a3d7  xorps   xmm0, xmm0
0x18028a3da  movups  [rsp+210h+var_1E0], xmm0
0x18028a3df  lea     rdx, [rbp+110h+Buf2]
0x18028a3e6  lea     rcx, [rbp+110h+var_E8]
0x18028a3ea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18028a3ef  mov     rbx, rax
0x18028a3f2  mov     [rsp+210h+var_1C0], rax
0x18028a3f7  mov     r15, qword ptr [rsp+210h+var_1D0]
0x18028a3fc  mov     r8, rax
0x18028a3ff  lea     rdx, [rbp+110h+var_100]
0x18028a403  lea     rcx, [r15+868h]
0x18028a40a  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,GLTFChannelAnimations::SamplerChannelData,std::less<std::string>,std::allocator<std::pair<std::string const,GLTFChannelAnimations::SamplerChannelData>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18028a40f  mov     r14, [rbp+110h+var_F0]
0x18028a413  cmp     byte ptr [r14+19h], 0
0x18028a418  jnz     short loc_18028A431
0x18028a41a  lea     r8, [r14+20h]
0x18028a41e  mov     rdx, rbx
0x18028a421  lea     rcx, [r15+868h]
0x18028a428  call    ??R?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEBA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::less<std::string>::operator()(std::string const &,std::string const &)
0x18028a42d  test    al, al
0x18028a42f  jz      short loc_18028A438
0x18028a431  mov     r14, [r15+868h]
0x18028a438  cmp     r14, [r15+868h]
0x18028a43f  jnz     short loc_18028A44C
0x18028a441  xorps   xmm0, xmm0
0x18028a444  movdqu  [rsp+210h+var_1E0], xmm0
0x18028a44a  jmp     short loc_18028A479
0x18028a44c  mov     rdx, rbx
0x18028a44f  lea     rcx, [r15+868h]
0x18028a456  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VShaderFamily@Engine@Spectre@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::shared_ptr<Spectre::Engine::ShaderFamily>>::operator[](std::string const &)
0x18028a45b  mov     rcx, [rax+8]
0x18028a45f  test    rcx, rcx
0x18028a462  jz      short loc_18028A46C
0x18028a464  lock inc dword ptr [rcx+8]
0x18028a468  mov     rcx, [rax+8]
0x18028a46c  mov     rax, [rax]
0x18028a46f  mov     qword ptr [rsp+210h+var_1E0], rax
0x18028a474  mov     qword ptr [rsp+210h+var_1E0+8], rcx
0x18028a479  mov     rcx, rbx; void *
0x18028a47c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18028a481  nop
0x18028a482  xorps   xmm0, xmm0
0x18028a485  xor     eax, eax
0x18028a487  movups  xmmword ptr [rbp+110h+Block], xmm0
0x18028a48e  mov     [rbp+110h+var_50], rax
0x18028a495  lea     rdx, [rbp+110h+Block]
0x18028a49c  mov     rcx, [r15+8E8h]
0x18028a4a3  call    ?SafeGetDeviceList@Engine@1Spectre@@QEAA?AV?$vector@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@@std@@XZ; Spectre::Engine::Engine::SafeGetDeviceList(void)
0x18028a4a8  nop
0x18028a4a9  mov     r15d, r13d
0x18028a4ac  mov     r14, [rbp+110h+Block+8]
0x18028a4b3  mov     rax, r14
0x18028a4b6  mov     rbx, [rbp+110h+Block]
0x18028a4bd  sub     rax, rbx
0x18028a4c0  sar     rax, 4
0x18028a4c4  test    rax, rax
0x18028a4c7  jz      loc_18028A5BB
0x18028a4cd  mov     rcx, r13
0x18028a4d0  xorps   xmm0, xmm0
0x18028a4d3  movups  [rbp+110h+var_190], xmm0
0x18028a4d7  add     rcx, rcx
0x18028a4da  lea     rdi, [rbx+rcx*8]
0x18028a4de  mov     rbx, [rdi+8]
0x18028a4e2  test    rbx, rbx
0x18028a4e5  jz      short loc_18028A4EF
0x18028a4e7  lock inc dword ptr [rbx+8]
0x18028a4eb  mov     rbx, [rdi+8]
0x18028a4ef  mov     rdi, [rdi]
0x18028a4f2  mov     qword ptr [rbp+110h+var_190], rdi
0x18028a4f6  mov     qword ptr [rbp+110h+var_190+8], rbx
0x18028a4fa  movups  xmmword ptr [rbp+110h+var_48], xmm0
0x18028a501  lea     rcx, [rdi+18h]; this
0x18028a505  lea     rdx, [rbp+110h+var_48]
0x18028a50c  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x18028a511  nop
0x18028a512  xorps   xmm0, xmm0
0x18028a515  movdqu  [rsp+210h+var_1D0], xmm0
0x18028a51b  test    rbx, rbx
0x18028a51e  jz      short loc_18028A528
0x18028a520  lock inc dword ptr [rbx+8]
0x18028a524  mov     rdi, qword ptr [rbp+110h+var_190]
0x18028a528  mov     qword ptr [rsp+210h+var_1D0], rdi
0x18028a52d  mov     qword ptr [rsp+210h+var_1D0+8], rbx
0x18028a532  lea     rdx, [rsp+210h+var_1D0]
0x18028a537  mov     rcx, qword ptr [rsp+210h+var_1E0]
0x18028a53c  call    ?AttachDevice@ShaderFamily@Engine@Spectre@@QEAAXV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::ShaderFamily::AttachDevice(std::shared_ptr<Spectre::Engine::RenderDevice>)
0x18028a541  nop
0x18028a542  cmp     byte ptr [rbp+110h+var_48+8], 0
0x18028a549  jz      short loc_18028A558
0x18028a54b  mov     rcx, [rbp+110h+var_48]; this
0x18028a552  call    ?unlock@Mutex@Engine@Spectre@@QEAAXXZ; Spectre::Engine::Mutex::unlock(void)
0x18028a557  nop
0x18028a558  test    rbx, rbx
0x18028a55b  jz      short loc_18028A594
0x18028a55d  mov     eax, esi
0x18028a55f  lock xadd [rbx+8], eax
0x18028a564  cmp     eax, 1
0x18028a567  jnz     short loc_18028A594
0x18028a569  mov     rax, [rbx]
0x18028a56c  mov     rcx, rbx
0x18028a56f  mov     rax, [rax]
0x18028a572  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
