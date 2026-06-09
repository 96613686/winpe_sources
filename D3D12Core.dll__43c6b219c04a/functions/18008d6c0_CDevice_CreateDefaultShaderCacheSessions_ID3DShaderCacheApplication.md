# CDevice::CreateDefaultShaderCacheSessions(ID3DShaderCacheApplication *)

- ea: `0x18008d6c0`
- end: `0x18008da49`
- name: `?CreateDefaultShaderCacheSessions@CDevice@@QEAAXPEAUID3DShaderCacheApplication@@@Z`
- size: `905`
- prototype: `void __fastcall(CDevice *__hidden this, struct ID3DShaderCacheApplication *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18008d1ec`

## callees

- `0x18000d770`
- `0x1800235dc`
- `0x18007f054`
- `0x180085970`
- `0x180085cc0`
- `0x18008d6c0`
- `0x18009fd4c`
- `0x1800b6608`
- `0x1800bb480`
- `0x1800c9000`
- `0x1800e9b18`
- `0x1800ead64`
- `0x1800eb28c`
- `0x1800eb2e0`
- `0x1800f0f74`
- `0x1800f4994`
- `0x1800f5068`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d8a7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008d89a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008d913`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008d89a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008d913`

## string_xrefs

- `0x18008d8c2`: `Failed MultiByteToWideChar for PrecompiledDatabasePath.`
- `0x18008d9f3`: `Failed to Create a Shader Cache Session for registered PSDB.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CDevice::CreateDefaultShaderCacheSessions(CDevice *this, struct ID3DShaderCacheApplication *a2)
{
  _QWORD *v4; // rdi
  __int64 *v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // r14d
  __int64 v8; // rcx
  const CHAR *v9; // r8
  int v10; // eax
  int cchWideChar; // edi
  signed int LastError; // eax
  __int64 v13; // rcx
  __int64 v14; // r9
  bool v15; // sf
  WCHAR *lpWideCharStr; // rax
  const CHAR *v17; // r8
  __int64 RegisteredPrecompiledDatabasePath; // rax
  LPWSTR *v19; // rax
  _QWORD *v20; // rdi
  int ShaderCacheSessionImpl; // edx
  __int64 v22; // r9
  __int64 *v23; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v24[3]; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR v25[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  unsigned __int64 v27; // [rsp+90h] [rbp-70h]
  LPCCH lpMultiByteStr[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v31; // [rsp+C0h] [rbp-40h]
  int v32; // [rsp+D0h] [rbp-30h]
  __int128 v33; // [rsp+D4h] [rbp-2Ch]
  int v34; // [rsp+E4h] [rbp-1Ch]
  int v35; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v36; // [rsp+F4h] [rbp-Ch]
  int v37; // [rsp+FCh] [rbp-4h]
  int v38; // [rsp+100h] [rbp+0h]
  int v39; // [rsp+104h] [rbp+4h]
  unsigned int v40; // [rsp+108h] [rbp+8h]
  _BYTE v41[64]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v42[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v43[120]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v44[184]; // [rsp+1E8h] [rbp+E8h] BYREF

  if ( *((_DWORD *)this + 720) )
  {
    v30 = 1;
    v33 = 0;
    v34 = 0;
    v31 = stru_1802B6408;
    v32 = 1;
    v4 = (_QWORD *)((char *)this + 744);
    if ( (int)CDevice::CreateShaderCacheSessionImpl(
                this,
                &v30,
                0,
                1,
                0,
                0,
                &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
                (char *)this + 744) >= 0 )
    {
      CLockOwnerChild<CDevice,0>::UCAddUse(*v4 + 144LL);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
    }
  }
  if ( *((_DWORD *)this + 720) >= 2u )
  {
    CDevice::CreateDefaultShaderCacheSessions_::_12_::ScopedAsdTelemetry::ScopedAsdTelemetry(&v35, this);
    v36 = *((_QWORD *)this + 706);
    v38 = (*(__int64 (__fastcall **)(void *))(qword_180339B30 + 56LL))(&qword_180339B30);
    v37 = *((_DWORD *)this + 720);
    v39 = *((_DWORD *)this + 140);
    SShaderCacheDriverIdentity::operator=(v41, (char *)this + 6432);
    SShaderCacheApplication::operator=(v43, (char *)this + 6496);
    if ( a2 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct ID3DShaderCacheApplication *, __int64 **))(*(_QWORD *)a2 + 88LL))(a2, &v23);
      v5 = &qword_1802A0AD0;
      if ( v23 )
        v5 = v23;
      v6 = -1;
      do
        ++v6;
      while ( *((_WORD *)v5 + v6) );
      std::wstring::_Assign<unsigned short>(v42);
    }
    memset(v24, 0, sizeof(v24));
    LODWORD(v24[0]) = 2;
    v7 = 0;
    std::wstring::wstring(v25);
    v40 = 2;
    CDevice::GetPrecompiledDatabasePath(v8, lpMultiByteStr);
    if ( lpMultiByteStr[2] )
    {
      v9 = (const CHAR *)lpMultiByteStr;
      if ( v29 > 0xF )
        v9 = lpMultiByteStr[0];
      v10 = MultiByteToWideChar(0xFDE9u, 8u, v9, -1, 0, 0);
      cchWideChar = v10;
      if ( v10 )
      {
        std::wstring::resize(v25, v10);
        lpWideCharStr = (WCHAR *)v25;
        if ( v27 > 7 )
          lpWideCharStr = v25[0];
        v17 = (const CHAR *)lpMultiByteStr;
        if ( v29 > 0xF )
          v17 = lpMultiByteStr[0];
        MultiByteToWideChar(0xFDE9u, 8u, v17, -1, lpWideCharStr, cchWideChar);
        v7 = 1;
      }
      else
      {
        LastError = GetLastError();
        v15 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v15 = LastError < 0;
        }
        if ( v15 )
          CJournal::RecordJournal(
            v13,
            LastError,
            (__int64)"Failed MultiByteToWideChar for PrecompiledDatabasePath.",
            v14,
            0);
      }
    }
    if ( v26
      || a2
      && (RegisteredPrecompiledDatabasePath = CDevice::GetRegisteredPrecompiledDatabasePath(this, &v30, a2),
          std::wstring::operator=(v25, RegisteredPrecompiledDatabasePath),
          std::wstring::_Tidy_deallocate(&v30),
          v26) )
    {
      v19 = v25;
      if ( v27 > 7 )
        v19 = (LPWSTR *)v25[0];
      v20 = (_QWORD *)((char *)this + 736);
      ShaderCacheSessionImpl = CDevice::CreateShaderCacheSessionImpl(
                                 this,
                                 v24,
                                 v7,
                                 16,
                                 v19,
                                 v44,
                                 &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
                                 (char *)this + 736);
      v35 = ShaderCacheSessionImpl;
      if ( ShaderCacheSessionImpl < 0 )
      {
        v40 = (v44[0] != 0) + 3;
        CJournal::RecordJournal(
          v40,
          ShaderCacheSessionImpl,
          (__int64)"Failed to Create a Shader Cache Session for registered PSDB.",
          v22,
          0);
      }
      else
      {
        v40 = 1;
        CLockOwnerChild<CDevice,0>::UCAddUse(*v20 + 144LL);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 16LL))(*v20);
      }
    }
    std::string::_Tidy_deallocate(lpMultiByteStr);
    std::wstring::_Tidy_deallocate(v25);
    CDevice::CreateDefaultShaderCacheSessions_::_12_::ScopedAsdTelemetry::_ScopedAsdTelemetry((struct AsdTelemetryData *)&v35);
  }
}

```

## disassembly

```asm
0x18008d6c0  mov     [rsp-8+arg_10], rbx
0x18008d6c5  mov     [rsp-8+arg_18], rsi
0x18008d6ca  push    rbp
0x18008d6cb  push    rdi
0x18008d6cc  push    r12
0x18008d6ce  push    r14
0x18008d6d0  push    r15
0x18008d6d2  lea     rbp, [rsp-1B0h]
0x18008d6da  sub     rsp, 2B0h
0x18008d6e1  mov     rax, cs:__security_cookie
0x18008d6e8  xor     rax, rsp
0x18008d6eb  mov     [rbp+1D0h+var_30], rax
0x18008d6f2  mov     rsi, rdx
0x18008d6f5  mov     rbx, rcx
0x18008d6f8  mov     r12d, 1
0x18008d6fe  lea     rax, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x18008d705  xor     r15d, r15d
0x18008d708  cmp     [rcx+0B40h], r15d
0x18008d70f  jbe     short loc_18008D77D
0x18008d711  mov     [rbp+1D0h+var_218], r12
0x18008d715  xorps   xmm0, xmm0
0x18008d718  movdqu  [rbp+1D0h+var_1FC], xmm0
0x18008d71d  mov     [rbp+1D0h+var_1EC], r15d
0x18008d721  movups  xmm0, xmmword ptr cs:stru_1802B6408.Data1
0x18008d728  movdqu  [rbp+1D0h+var_210], xmm0
0x18008d72d  mov     [rbp+1D0h+var_200], r12d
0x18008d731  lea     rdi, [rcx+2E8h]
0x18008d738  mov     [rsp+2D0h+var_298], rdi
0x18008d73d  mov     [rsp+2D0h+var_2A0], rax
0x18008d742  mov     qword ptr [rsp+2D0h+cchWideChar], r15
0x18008d747  mov     [rsp+2D0h+lpWideCharStr], r15
0x18008d74c  mov     r9d, r12d
0x18008d74f  xor     r8d, r8d
0x18008d752  lea     rdx, [rbp+1D0h+var_218]
0x18008d756  call    ?CreateShaderCacheSessionImpl@CDevice@@QEAAJPEBUD3D12_SHADER_CACHE_SESSION_DESC1@@W4D3D12INT_SHADER_CACHE_FLAGS@@W4D3D12_SHADER_CACHE_KIND_FLAGS@@PEBGPEAUD3D12ShaderCacheProperties@@AEBU_GUID@@PEAPEAX@Z; CDevice::CreateShaderCacheSessionImpl(D3D12_SHADER_CACHE_SESSION_DESC1 const *,D3D12INT_SHADER_CACHE_FLAGS,D3D12_SHADER_CACHE_KIND_FLAGS,ushort const *,D3D12ShaderCacheProperties *,_GUID const &,void * *)
0x18008d75b  test    eax, eax
0x18008d75d  js      short loc_18008D77D
0x18008d75f  mov     rcx, [rdi]
0x18008d762  add     rcx, 90h
0x18008d769  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18008d76e  mov     rcx, [rdi]
0x18008d771  mov     rax, [rcx]
0x18008d774  mov     rax, [rax+10h]
0x18008d778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d77d  mov     edi, 2
0x18008d782  cmp     [rbx+0B40h], edi
0x18008d788  jb      loc_18008DA1E
0x18008d78e  mov     rdx, rbx
0x18008d791  lea     rcx, [rbp+1D0h+var_1E0]
0x18008d795  call    _CDevice__CreateDefaultShaderCacheSessions____12___ScopedAsdTelemetry__ScopedAsdTelemetry
0x18008d79a  nop
0x18008d79b  mov     rax, [rbx+1610h]
0x18008d7a2  mov     [rbp+1D0h+var_1DC], rax
0x18008d7a6  mov     rax, cs:qword_180339B30
0x18008d7ad  lea     rcx, qword_180339B30
0x18008d7b4  mov     rax, [rax+38h]
0x18008d7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d7bd  mov     [rbp+1D0h+var_1D0], eax
0x18008d7c0  mov     eax, [rbx+0B40h]
0x18008d7c6  mov     [rbp+1D0h+var_1D4], eax
0x18008d7c9  mov     eax, [rbx+230h]
0x18008d7cf  mov     [rbp+1D0h+var_1CC], eax
0x18008d7d2  lea     rdx, [rbx+1920h]
0x18008d7d9  lea     rcx, [rbp+1D0h+var_1C0]
0x18008d7dd  call    ??4SShaderCacheDriverIdentity@@QEAAAEAU0@AEBU0@@Z; SShaderCacheDriverIdentity::operator=(SShaderCacheDriverIdentity const &)
0x18008d7e2  lea     rdx, [rbx+1960h]
0x18008d7e9  lea     rcx, [rbp+1D0h+var_160]
0x18008d7ed  call    ??4SShaderCacheApplication@@QEAAAEAU0@AEBU0@@Z; SShaderCacheApplication::operator=(SShaderCacheApplication const &)
0x18008d7f2  test    rsi, rsi
0x18008d7f5  jz      short loc_18008D83A
0x18008d7f7  mov     [rsp+2D0h+var_290], r15
0x18008d7fc  mov     rax, [rsi]
0x18008d7ff  lea     rdx, [rsp+2D0h+var_290]
0x18008d804  mov     rcx, rsi
0x18008d807  mov     rax, [rax+58h]
0x18008d80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d810  lea     rdx, qword_1802A0AD0
0x18008d817  mov     rax, [rsp+2D0h+var_290]
0x18008d81c  test    rax, rax
0x18008d81f  cmovnz  rdx, rax
0x18008d823  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008d827  inc     r8
0x18008d82a  cmp     [rdx+r8*2], r15w
0x18008d82f  jnz     short loc_18008D827
0x18008d831  lea     rcx, [rbp+1D0h+var_180]
0x18008d835  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008d83a  xorps   xmm0, xmm0
0x18008d83d  movups  [rsp+2D0h+var_288], xmm0
0x18008d842  movups  [rsp+2D0h+var_278], xmm0
0x18008d847  movups  [rsp+2D0h+var_268], xmm0
0x18008d84c  mov     dword ptr [rsp+2D0h+var_288], edi
0x18008d850  mov     r14d, r15d
0x18008d853  lea     rcx, [rsp+2D0h+var_258]; void *
0x18008d858  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d85d  nop
0x18008d85e  mov     [rbp+1D0h+var_1C8], edi
0x18008d861  lea     rdx, [rbp+1D0h+lpMultiByteStr]
0x18008d865  call    ?GetPrecompiledDatabasePath@CDevice@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CDevice::GetPrecompiledDatabasePath(void)
0x18008d86a  nop
0x18008d86b  cmp     [rbp+1D0h+var_228], r15
0x18008d86f  jz      loc_18008D91C
0x18008d875  lea     r8, [rbp+1D0h+lpMultiByteStr]
0x18008d879  cmp     [rbp+1D0h+var_220], 0Fh
0x18008d87e  cmova   r8, [rbp+1D0h+lpMultiByteStr]; lpMultiByteStr
0x18008d883  mov     [rsp+2D0h+cchWideChar], r15d; cchWideChar
0x18008d888  mov     [rsp+2D0h+lpWideCharStr], r15; lpWideCharStr
0x18008d88d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18008d891  lea     edx, [r9+9]; dwFlags
0x18008d895  mov     ecx, 0FDE9h; CodePage
0x18008d89a  call    cs:__imp_MultiByteToWideChar
0x18008d8a0  movsxd  rdi, eax
0x18008d8a3  test    eax, eax
0x18008d8a5  jnz     short loc_18008D8D2
0x18008d8a7  call    cs:__imp_GetLastError
0x18008d8ad  test    eax, eax
0x18008d8af  jle     short loc_18008D8BB
0x18008d8b1  movzx   eax, ax
0x18008d8b4  or      eax, 80070000h
0x18008d8b9  test    eax, eax
0x18008d8bb  jns     short loc_18008D91C
0x18008d8bd  mov     dword ptr [rsp+2D0h+lpWideCharStr], r15d
0x18008d8c2  lea     r8, aFailedMultibyt; "Failed MultiByteToWideChar for Precompi"...
0x18008d8c9  mov     edx, eax
0x18008d8cb  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18008d8d0  jmp     short loc_18008D91C
0x18008d8d2  mov     rdx, rdi
0x18008d8d5  lea     rcx, [rsp+2D0h+var_258]
0x18008d8da  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18008d8df  lea     rax, [rsp+2D0h+var_258]
0x18008d8e4  cmp     [rbp+1D0h+var_240], 7
0x18008d8e9  cmova   rax, [rsp+2D0h+var_258]
0x18008d8ef  lea     r8, [rbp+1D0h+lpMultiByteStr]
0x18008d8f3  cmp     [rbp+1D0h+var_220], 0Fh
0x18008d8f8  cmova   r8, [rbp+1D0h+lpMultiByteStr]; lpMultiByteStr
0x18008d8fd  mov     [rsp+2D0h+cchWideChar], edi; cchWideChar
0x18008d901  mov     [rsp+2D0h+lpWideCharStr], rax; lpWideCharStr
0x18008d906  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18008d90a  lea     edx, [r9+9]; dwFlags
0x18008d90e  mov     ecx, 0FDE9h; CodePage
0x18008d913  call    cs:__imp_MultiByteToWideChar
0x18008d919  mov     r14d, r12d
0x18008d91c  mov     rax, [rbp+1D0h+var_248]
0x18008d920  test    rax, rax
0x18008d923  jnz     short loc_18008D960
0x18008d925  test    rsi, rsi
0x18008d928  jz      loc_18008DA00
0x18008d92e  mov     r8, rsi
0x18008d931  lea     rdx, [rbp+1D0h+var_218]
0x18008d935  mov     rcx, rbx
0x18008d938  call    ?GetRegisteredPrecompiledDatabasePath@CDevice@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUID3DShaderCacheApplication@@PEBG@Z; CDevice::GetRegisteredPrecompiledDatabasePath(ID3DShaderCacheApplication *,ushort const *)
0x18008d93d  mov     rdx, rax
0x18008d940  lea     rcx, [rsp+2D0h+var_258]
0x18008d945  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008d94a  lea     rcx, [rbp+1D0h+var_218]
0x18008d94e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d953  mov     rax, [rbp+1D0h+var_248]
0x18008d957  test    rax, rax
0x18008d95a  jz      loc_18008DA00
0x18008d960  lea     rax, [rsp+2D0h+var_258]
0x18008d965  cmp     [rbp+1D0h+var_240], 7
0x18008d96a  cmova   rax, [rsp+2D0h+var_258]
0x18008d970  lea     rdi, [rbx+2E0h]
0x18008d977  mov     [rsp+2D0h+var_298], rdi
0x18008d97c  lea     rcx, _GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae
0x18008d983  mov     [rsp+2D0h+var_2A0], rcx
0x18008d988  lea     rcx, [rbp+1D0h+var_E8]
0x18008d98f  mov     qword ptr [rsp+2D0h+cchWideChar], rcx
0x18008d994  mov     [rsp+2D0h+lpWideCharStr], rax
0x18008d999  mov     r9d, 10h
0x18008d99f  mov     r8d, r14d
0x18008d9a2  lea     rdx, [rsp+2D0h+var_288]
0x18008d9a7  mov     rcx, rbx
0x18008d9aa  call    ?CreateShaderCacheSessionImpl@CDevice@@QEAAJPEBUD3D12_SHADER_CACHE_SESSION_DESC1@@W4D3D12INT_SHADER_CACHE_FLAGS@@W4D3D12_SHADER_CACHE_KIND_FLAGS@@PEBGPEAUD3D12ShaderCacheProperties@@AEBU_GUID@@PEAPEAX@Z; CDevice::CreateShaderCacheSessionImpl(D3D12_SHADER_CACHE_SESSION_DESC1 const *,D3D12INT_SHADER_CACHE_FLAGS,D3D12_SHADER_CACHE_KIND_FLAGS,ushort const *,D3D12ShaderCacheProperties *,_GUID const &,void * *)
0x18008d9af  mov     edx, eax
0x18008d9b1  mov     [rbp+1D0h+var_1E0], eax
0x18008d9b4  test    eax, eax
0x18008d9b6  js      short loc_18008D9DC
0x18008d9b8  mov     [rbp+1D0h+var_1C8], r12d
0x18008d9bc  mov     rcx, [rdi]
0x18008d9bf  add     rcx, 90h
0x18008d9c6  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18008d9cb  mov     rcx, [rdi]
0x18008d9ce  mov     rax, [rcx]
0x18008d9d1  mov     rax, [rax+10h]
0x18008d9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d9da  jmp     short loc_18008DA00
0x18008d9dc  mov     al, [rbp+1D0h+var_E8]
0x18008d9e2  neg     al
0x18008d9e4  sbb     ecx, ecx
0x18008d9e6  neg     ecx
0x18008d9e8  add     ecx, 3
0x18008d9eb  mov     [rbp+1D0h+var_1C8], ecx
0x18008d9ee  mov     dword ptr [rsp+2D0h+lpWideCharStr], r15d
0x18008d9f3  lea     r8, aFailedToCreate; "Failed to Create a Shader Cache Session"...
0x18008d9fa  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18008d9ff  nop
0x18008da00  lea     rcx, [rbp+1D0h+lpMultiByteStr]
0x18008da04  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18008da09  nop
0x18008da0a  lea     rcx, [rsp+2D0h+var_258]
0x18008da0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008da14  nop
0x18008da15  lea     rcx, [rbp+1D0h+var_1E0]; struct AsdTelemetryData *
0x18008da19  call    _CDevice__CreateDefaultShaderCacheSessions____12___ScopedAsdTelemetry___ScopedAsdTelemetry
0x18008da1e  mov     rcx, [rbp+1D0h+var_30]
0x18008da25  xor     rcx, rsp; StackCookie
0x18008da28  call    __security_check_cookie
0x18008da2d  lea     r11, [rsp+2D0h+var_20]
0x18008da35  mov     rbx, [r11+40h]
0x18008da39  mov     rsi, [r11+48h]
0x18008da3d  mov     rsp, r11
0x18008da40  pop     r15
0x18008da42  pop     r14
0x18008da44  pop     r12
0x18008da46  pop     rdi
0x18008da47  pop     rbp
0x18008da48  retn
```
