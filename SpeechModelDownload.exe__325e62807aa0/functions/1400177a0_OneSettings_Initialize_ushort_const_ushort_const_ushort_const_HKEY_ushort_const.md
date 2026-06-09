# OneSettings::Initialize(ushort const *,ushort const *,ushort const *,HKEY__ *,ushort const *)

- ea: `0x1400177a0`
- end: `0x140017c9b`
- name: `?Initialize@OneSettings@@QEAAJPEBG00PEAUHKEY__@@0@Z`
- size: `1275`
- prototype: `__int64 __fastcall(OneSettings *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013b90`

## callees

- `0x140002600`
- `0x140002624`
- `0x1400030dc`
- `0x140003564`
- `0x140007dc8`
- `0x1400138c8`
- `0x140013a2c`
- `0x1400146e4`
- `0x140014a98`
- `0x140015794`
- `0x140015b60`
- `0x1400177a0`
- `0x140017ca4`
- `0x1400180f0`
- `0x140019f94`
- `0x14001a448`
- `0x14001bba8`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400178d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017a86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017c5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400178d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017a86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017c5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400178de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017c6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400178de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017c6c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140017ae1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140017ae1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017b06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017c42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017b06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017c42`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140017b54`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140017b54`

## string_xrefs

- `0x140017bdd`: `settings-win-ppe.data.microsoft.com`
- `0x140017bf3`: `settings-win-ppe.data.microsoft.com`
- `0x140017c12`: `settings-win.data.microsoft.com`
- `0x140017c28`: `settings-win.data.microsoft.com`

## pseudocode

```c
__int64 __fastcall OneSettings::Initialize(
        OneSettings *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  char *v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rax
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rbx
  int v19; // eax
  unsigned int v20; // esi
  void *v21; // rbx
  HANDLE v22; // rax
  LSTATUS v23; // eax
  LSTATUS ValueW; // eax
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  OneSettings *v27; // rsi
  __int64 v28; // rbx
  const wchar_t *v29; // r9
  _WORD *v30; // rbx
  _WORD *v31; // rbx
  void *v32; // rbx
  HANDLE v33; // rax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v37[16]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  char v39; // [rsp+78h] [rbp-88h]
  _BYTE v40[48]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v41; // [rsp+B0h] [rbp-50h]
  __int128 v42; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v43; // [rsp+D0h] [rbp-30h]
  _BYTE v44[32]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD pvData[264]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v5 = (char *)this + 216;
  *((_BYTE *)this + 230) = 1;
  SpeechOneSettingsTelemetry::LifeTime::MyInit((OneSettings *)((char *)this + 216), a2, a3, a4);
  (**(void (__fastcall ***)(char *, _QWORD))v5)(v5, 0);
  (*(void (__fastcall **)(char *, _BYTE *))(*(_QWORD *)v5 + 112LL))(v5, v37);
  OneSettings::reset(this);
  v6 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  v41 = v6;
  if ( v6 )
  {
    *(_OWORD *)v6 = 0;
    *v6 = 0;
    v6[1] = 0;
    v8 = operator new(0x60u);
    *v8 = v8;
    v8[1] = v8;
    v8[2] = v8;
    *((_WORD *)v8 + 12) = 257;
    *v7 = v8;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 25) = v7;
  if ( !v7 )
  {
    v9 = 221;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
      (const char *)0x8007000ELL,
      dwOptions);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
    if ( v39 )
    {
      v11 = lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
    }
    return 2147942414LL;
  }
  v10 = operator new(8u, (const struct std::nothrow_t *)std::nothrow);
  if ( v10 )
    *v10 = 0;
  else
    v10 = 0;
  *((_QWORD *)this + 26) = v10;
  if ( !v10 )
  {
    v9 = 224;
    goto LABEL_11;
  }
  v42 = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v42, L"analog", 6);
  v14 = OneSettingsInternal::Common::trim<std::wstring>(v44, &v42);
  std::wstring::operator=((char *)this + 32, v14);
  std::wstring::~wstring(v44);
  std::wstring::~wstring(&v42);
  v42 = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v42, L"nasp_speechmodels", 17);
  v15 = OneSettingsInternal::Common::trim<std::wstring>(v44, &v42);
  std::wstring::operator=((char *)this + 64, v15);
  std::wstring::~wstring(v44);
  std::wstring::~wstring(&v42);
  v42 = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v42, L"SpeechModelDownload", 19);
  v16 = OneSettingsInternal::Common::trim<std::wstring>(v44, &v42);
  std::wstring::operator=((char *)this + 96, v16);
  std::wstring::~wstring(v44);
  std::wstring::~wstring(&v42);
  v42 = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v42, L"SOFTWARE\\Microsoft\\Speech_OneCore\\ModelDownload", 47);
  v17 = OneSettingsInternal::Common::trim<std::wstring>(v44, &v42);
  v18 = (const WCHAR *)((char *)this + 128);
  std::wstring::operator=((char *)this + 128, v17);
  std::wstring::~wstring(v44);
  std::wstring::~wstring(&v42);
  *((_QWORD *)this + 20) = -2147483647;
  v19 = OneSettings::InitializeMachineProperties(this);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
      (const char *)(unsigned int)v19,
      dwOptions);
LABEL_16:
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
    if ( v39 )
    {
      v21 = lpMem;
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v21);
    }
    return v20;
  }
  hKey = 0;
  if ( *((_QWORD *)this + 19) > 7u )
    v18 = *(const WCHAR **)v18;
  v23 = RegCreateKeyExW(*((HKEY *)this + 20), v18, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v20 = v23;
  if ( v23 )
  {
    if ( v23 > 0 )
      v20 = (unsigned __int16)v23 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_16;
  }
  memset_0(pvData, 0, 0x208u);
  pcbData = 520;
  ValueW = RegGetValueW(hKey, 0, L"Endpoint", 2u, 0, pvData, &pcbData);
  *((_DWORD *)this + 176) = 1;
  if ( !ValueW )
  {
    v26 = -1;
    do
      ++v26;
    while ( pvData[v26] );
    if ( v26 )
    {
      if ( v26 <= *((_QWORD *)this + 3) )
      {
        if ( *((_QWORD *)this + 3) <= 7u )
          v27 = this;
        else
          v27 = *(OneSettings **)this;
        *((_QWORD *)this + 2) = v26;
        v28 = 2 * v26;
        memmove_0(v27, pvData, 2 * v26);
        *(_WORD *)((char *)v27 + v28) = 0;
        goto LABEL_44;
      }
      v29 = pvData;
      goto LABEL_43;
    }
  }
  if ( !(unsigned int)OneSettings::UsePreProductionEndpoint(this) )
  {
    v26 = 31;
    if ( *((_QWORD *)this + 3) >= 0x1Fu )
    {
      v31 = *(_WORD **)this;
      *((_QWORD *)this + 2) = 31;
      memmove_0(v31, L"settings-win.data.microsoft.com", 0x3Eu);
      v31[31] = 0;
      goto LABEL_44;
    }
    v29 = L"settings-win.data.microsoft.com";
LABEL_43:
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(this, v26, v25, v29);
    goto LABEL_44;
  }
  v26 = 35;
  if ( *((_QWORD *)this + 3) < 0x23u )
  {
    v29 = L"settings-win-ppe.data.microsoft.com";
    goto LABEL_43;
  }
  v30 = *(_WORD **)this;
  *((_QWORD *)this + 2) = 35;
  memmove_0(v30, L"settings-win-ppe.data.microsoft.com", 0x46u);
  v30[35] = 0;
LABEL_44:
  if ( hKey )
    RegCloseKey(hKey);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
  if ( v39 )
  {
    v32 = lpMem;
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v32);
  }
  return 0;
}

```

## disassembly

```asm
0x1400177a0  mov     [rsp-8+arg_8], rbx
0x1400177a5  mov     [rsp-8+arg_10], rsi
0x1400177aa  push    rbp
0x1400177ab  push    rdi
0x1400177ac  push    r14
0x1400177ae  lea     rbp, [rsp-220h]
0x1400177b6  sub     rsp, 320h
0x1400177bd  mov     rax, cs:__security_cookie
0x1400177c4  xor     rax, rsp
0x1400177c7  mov     [rbp+230h+var_20], rax
0x1400177ce  mov     rdi, rcx
0x1400177d1  xor     r14d, r14d
0x1400177d4  lea     rbx, [rcx+0D8h]
0x1400177db  mov     byte ptr [rbx+0Eh], 1
0x1400177df  mov     rcx, rbx; this
0x1400177e2  call    ?MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z; SpeechOneSettingsTelemetry::LifeTime::MyInit(ushort const *,ushort const *,ushort const *)
0x1400177e7  mov     rax, [rbx]
0x1400177ea  xor     edx, edx
0x1400177ec  mov     rcx, rbx
0x1400177ef  mov     rax, [rax]
0x1400177f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400177f7  mov     rax, [rbx]
0x1400177fa  lea     rdx, [rsp+330h+var_2D0]
0x1400177ff  mov     rcx, rbx
0x140017802  mov     rax, [rax+70h]
0x140017806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001780b  nop
0x14001780c  mov     rcx, rdi; this
0x14001780f  call    ?reset@OneSettings@@AEAAXXZ; OneSettings::reset(void)
0x140017814  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001781b  lea     ecx, [r14+10h]; unsigned __int64
0x14001781f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140017824  mov     rbx, rax
0x140017827  mov     [rbp+230h+var_280], rax
0x14001782b  test    rax, rax
0x14001782e  jz      short loc_14001785C
0x140017830  xorps   xmm0, xmm0
0x140017833  movups  xmmword ptr [rax], xmm0
0x140017836  mov     [rax], r14
0x140017839  mov     [rax+8], r14
0x14001783d  lea     ecx, [r14+60h]; Size
0x140017841  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140017846  mov     [rax], rax
0x140017849  mov     [rax+8], rax
0x14001784d  mov     [rax+10h], rax
0x140017851  mov     word ptr [rax+18h], 101h
0x140017857  mov     [rbx], rax
0x14001785a  jmp     short loc_14001785F
0x14001785c  mov     rbx, r14
0x14001785f  mov     [rdi+0C8h], rbx
0x140017866  test    rbx, rbx
0x140017869  jnz     short loc_140017872
0x14001786b  mov     edx, 0DDh
0x140017870  jmp     short loc_1400178A1
0x140017872  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017879  mov     ecx, 8; unsigned __int64
0x14001787e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140017883  test    rax, rax
0x140017886  jz      short loc_14001788D
0x140017888  mov     [rax], r14
0x14001788b  jmp     short loc_140017890
0x14001788d  mov     rax, r14
0x140017890  mov     [rdi+0D0h], rax
0x140017897  test    rax, rax
0x14001789a  jnz     short loc_1400178EE
0x14001789c  mov     edx, 0E0h; void *
0x1400178a1  mov     r9d, 8007000Eh; char *
0x1400178a7  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x1400178ae  mov     rcx, [rbp+238h]; this
0x1400178b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400178ba  nop
0x1400178bb  lea     rcx, [rbp+230h+var_2B0]; this
0x1400178bf  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1400178c4  cmp     [rsp+330h+var_2B8], r14b
0x1400178c9  jz      short loc_1400178E4
0x1400178cb  mov     rbx, [rsp+330h+lpMem]
0x1400178d0  call    cs:__imp_GetProcessHeap
0x1400178d6  mov     r8, rbx; lpMem
0x1400178d9  xor     edx, edx; dwFlags
0x1400178db  mov     rcx, rax; hHeap
0x1400178de  call    cs:__imp_HeapFree
0x1400178e4  mov     eax, 8007000Eh
0x1400178e9  jmp     loc_140017C74
0x1400178ee  xorps   xmm0, xmm0
0x1400178f1  movups  [rbp+230h+var_270], xmm0
0x1400178f5  xorps   xmm1, xmm1
0x1400178f8  movdqu  [rbp+230h+var_260], xmm1
0x1400178fd  mov     r8d, 6
0x140017903  lea     rdx, aAnalog; "analog"
0x14001790a  lea     rcx, [rbp+230h+var_270]
0x14001790e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140017913  nop
0x140017914  lea     rdx, [rbp+230h+var_270]
0x140017918  lea     rcx, [rbp+230h+var_250]
0x14001791c  call    ??$trim@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Common@OneSettingsInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; OneSettingsInternal::Common::trim<std::wstring>(std::wstring const &)
0x140017921  lea     rcx, [rdi+20h]
0x140017925  mov     rdx, rax
0x140017928  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001792d  lea     rcx, [rbp+230h+var_250]
0x140017931  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017936  nop
0x140017937  lea     rcx, [rbp+230h+var_270]
0x14001793b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017940  xorps   xmm0, xmm0
0x140017943  movups  [rbp+230h+var_270], xmm0
0x140017947  xorps   xmm1, xmm1
0x14001794a  movdqu  [rbp+230h+var_260], xmm1
0x14001794f  mov     r8d, 11h
0x140017955  lea     rdx, aNaspSpeechmode; "nasp_speechmodels"
0x14001795c  lea     rcx, [rbp+230h+var_270]
0x140017960  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140017965  nop
0x140017966  lea     rdx, [rbp+230h+var_270]
0x14001796a  lea     rcx, [rbp+230h+var_250]
0x14001796e  call    ??$trim@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Common@OneSettingsInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; OneSettingsInternal::Common::trim<std::wstring>(std::wstring const &)
0x140017973  lea     rcx, [rdi+40h]
0x140017977  mov     rdx, rax
0x14001797a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001797f  lea     rcx, [rbp+230h+var_250]
0x140017983  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017988  nop
0x140017989  lea     rcx, [rbp+230h+var_270]
0x14001798d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017992  xorps   xmm0, xmm0
0x140017995  movups  [rbp+230h+var_270], xmm0
0x140017999  xorps   xmm1, xmm1
0x14001799c  movdqu  [rbp+230h+var_260], xmm1
0x1400179a1  mov     r8d, 13h
0x1400179a7  lea     rdx, aSpeechmodeldow; "SpeechModelDownload"
0x1400179ae  lea     rcx, [rbp+230h+var_270]
0x1400179b2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400179b7  nop
0x1400179b8  lea     rdx, [rbp+230h+var_270]
0x1400179bc  lea     rcx, [rbp+230h+var_250]
0x1400179c0  call    ??$trim@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Common@OneSettingsInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; OneSettingsInternal::Common::trim<std::wstring>(std::wstring const &)
0x1400179c5  lea     rcx, [rdi+60h]
0x1400179c9  mov     rdx, rax
0x1400179cc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400179d1  lea     rcx, [rbp+230h+var_250]
0x1400179d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400179da  nop
0x1400179db  lea     rcx, [rbp+230h+var_270]
0x1400179df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400179e4  xorps   xmm0, xmm0
0x1400179e7  movups  [rbp+230h+var_270], xmm0
0x1400179eb  xorps   xmm1, xmm1
0x1400179ee  movdqu  [rbp+230h+var_260], xmm1
0x1400179f3  mov     r8d, 2Fh ; '/'
0x1400179f9  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Speech_OneCore\\Mo"...
0x140017a00  lea     rcx, [rbp+230h+var_270]
0x140017a04  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140017a09  nop
0x140017a0a  lea     rdx, [rbp+230h+var_270]
0x140017a0e  lea     rcx, [rbp+230h+var_250]
0x140017a12  call    ??$trim@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Common@OneSettingsInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; OneSettingsInternal::Common::trim<std::wstring>(std::wstring const &)
0x140017a17  lea     rbx, [rdi+80h]
0x140017a1e  mov     rdx, rax
0x140017a21  mov     rcx, rbx
0x140017a24  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140017a29  lea     rcx, [rbp+230h+var_250]
0x140017a2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017a32  nop
0x140017a33  lea     rcx, [rbp+230h+var_270]
0x140017a37  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017a3c  mov     qword ptr [rdi+0A0h], 0FFFFFFFF80000001h
0x140017a47  mov     rcx, rdi; this
0x140017a4a  call    ?InitializeMachineProperties@OneSettings@@AEAAJXZ; OneSettings::InitializeMachineProperties(void)
0x140017a4f  mov     esi, eax
0x140017a51  test    eax, eax
0x140017a53  jns     short loc_140017AA1
0x140017a55  mov     rcx, [rbp+238h]; this
0x140017a5c  mov     r9d, eax; char *
0x140017a5f  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140017a66  mov     edx, 0E8h; void *
0x140017a6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017a70  nop
0x140017a71  lea     rcx, [rbp+230h+var_2B0]; this
0x140017a75  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140017a7a  cmp     [rsp+330h+var_2B8], r14b
0x140017a7f  jz      short loc_140017A9A
0x140017a81  mov     rbx, [rsp+330h+lpMem]
0x140017a86  call    cs:__imp_GetProcessHeap
0x140017a8c  mov     r8, rbx; lpMem
0x140017a8f  xor     edx, edx; dwFlags
0x140017a91  mov     rcx, rax; hHeap
0x140017a94  call    cs:__imp_HeapFree
0x140017a9a  mov     eax, esi
0x140017a9c  jmp     loc_140017C74
0x140017aa1  mov     [rsp+330h+hKey], r14
0x140017aa6  cmp     qword ptr [rbx+18h], 7
0x140017aab  jbe     short loc_140017AB0
0x140017aad  mov     rbx, [rbx]
0x140017ab0  mov     [rsp+330h+lpdwDisposition], r14; lpdwDisposition
0x140017ab5  lea     rax, [rsp+330h+hKey]
0x140017aba  mov     [rsp+330h+phkResult], rax; phkResult
0x140017abf  mov     [rsp+330h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140017ac4  mov     [rsp+330h+samDesired], 0F003Fh; samDesired
0x140017acc  mov     [rsp+330h+dwOptions], r14d; dwOptions
0x140017ad1  xor     r9d, r9d; lpClass
0x140017ad4  xor     r8d, r8d; Reserved
0x140017ad7  mov     rdx, rbx; lpSubKey
0x140017ada  mov     rcx, [rdi+0A0h]; hKey
0x140017ae1  call    cs:__imp_RegCreateKeyExW
0x140017ae7  mov     esi, eax
0x140017ae9  test    eax, eax
0x140017aeb  jz      short loc_140017B11
0x140017aed  jle     short loc_140017AF8
0x140017aef  movzx   esi, ax
0x140017af2  or      esi, 80070000h
0x140017af8  mov     rcx, [rsp+330h+hKey]; hKey
0x140017afd  test    rcx, rcx
0x140017b00  jz      loc_140017A71
0x140017b06  call    cs:__imp_RegCloseKey
0x140017b0c  jmp     loc_140017A71
0x140017b11  mov     ebx, 208h
0x140017b16  mov     r8d, ebx; Size
0x140017b19  xor     edx, edx; Val
0x140017b1b  lea     rcx, [rbp+230h+pvData]; void *
0x140017b1f  call    memset_0
0x140017b24  mov     [rsp+330h+pcbData], ebx
0x140017b28  lea     rax, [rsp+330h+pcbData]
0x140017b2d  mov     [rsp+330h+lpSecurityAttributes], rax; pcbData
0x140017b32  lea     rax, [rbp+230h+pvData]
0x140017b36  mov     qword ptr [rsp+330h+samDesired], rax; pvData
0x140017b3b  mov     qword ptr [rsp+330h+dwOptions], r14; pdwType
0x140017b40  mov     r9d, 2; dwFlags
0x140017b46  lea     r8, aEndpoint; "Endpoint"
0x140017b4d  xor     edx, edx; lpSubKey
0x140017b4f  mov     rcx, [rsp+330h+hKey]; hkey
0x140017b54  call    cs:__imp_RegGetValueW
0x140017b5a  mov     dword ptr [rdi+2C0h], 1
0x140017b64  test    eax, eax
0x140017b66  jnz     short loc_140017BBB
0x140017b68  lea     rax, [rbp+230h+pvData]
0x140017b6c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140017b70  inc     rdx
0x140017b73  cmp     [rax+rdx*2], r14w
0x140017b78  jnz     short loc_140017B70
0x140017b7a  test    rdx, rdx
0x140017b7d  jz      short loc_140017BBB
0x140017b7f  cmp     rdx, [rdi+18h]
0x140017b83  ja      short loc_140017BB5
0x140017b85  cmp     qword ptr [rdi+18h], 7
0x140017b8a  jbe     short loc_140017B91
0x140017b8c  mov     rsi, [rdi]
0x140017b8f  jmp     short loc_140017B94
0x140017b91  mov     rsi, rdi
0x140017b94  mov     [rdi+10h], rdx
0x140017b98  lea     rbx, [rdx+rdx]
0x140017b9c  mov     r8, rbx; Size
0x140017b9f  lea     rdx, [rbp+230h+pvData]; Src
0x140017ba3  mov     rcx, rsi; void *
0x140017ba6  call    memmove_0
0x140017bab  mov     [rsi+rbx], r14w
0x140017bb0  jmp     loc_140017C38
0x140017bb5  lea     r9, [rbp+230h+pvData]
0x140017bb9  jmp     short loc_140017C2F
0x140017bbb  mov     rcx, rdi; this
0x140017bbe  call    ?UsePreProductionEndpoint@OneSettings@@AEAAHXZ; OneSettings::UsePreProductionEndpoint(void)
0x140017bc3  test    eax, eax
0x140017bc5  jz      short loc_140017BFC
0x140017bc7  mov     edx, 23h ; '#'
0x140017bcc  cmp     [rdi+18h], rdx
0x140017bd0  jb      short loc_140017BF3
0x140017bd2  mov     rbx, [rdi]
0x140017bd5  mov     [rdi+10h], rdx
0x140017bd9  lea     r8d, [rdx+23h]; Size
0x140017bdd  lea     rdx, aSettingsWinPpe; "settings-win-ppe.data.microsoft.com"
0x140017be4  mov     rcx, rbx; void *
0x140017be7  call    memmove_0
0x140017bec  mov     [rbx+46h], r14w
0x140017bf1  jmp     short loc_140017C38
0x140017bf3  lea     r9, aSettingsWinPpe; "settings-win-ppe.data.microsoft.com"
0x140017bfa  jmp     short loc_140017C2F
0x140017bfc  mov     edx, 1Fh
0x140017c01  cmp     [rdi+18h], rdx
0x140017c05  jb      short loc_140017C28
0x140017c07  mov     rbx, [rdi]
0x140017c0a  mov     [rdi+10h], rdx
0x140017c0e  lea     r8d, [rdx+1Fh]; Size
0x140017c12  lea     rdx, aSettingsWinDat; "settings-win.data.microsoft.com"
0x140017c19  mov     rcx, rbx; void *
0x140017c1c  call    memmove_0
0x140017c21  mov     [rbx+3Eh], r14w
0x140017c26  jmp     short loc_140017C38
0x140017c28  lea     r9, aSettingsWinDat; "settings-win.data.microsoft.com"
0x140017c2f  mov     rcx, rdi
0x140017c32  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140017c37  nop
0x140017c38  mov     rcx, [rsp+330h+hKey]; hKey
0x140017c3d  test    rcx, rcx
0x140017c40  jz      short loc_140017C49
0x140017c42  call    cs:__imp_RegCloseKey
0x140017c48  nop
0x140017c49  lea     rcx, [rbp+230h+var_2B0]; this
0x140017c4d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140017c52  cmp     [rsp+330h+var_2B8], r14b
0x140017c57  jz      short loc_140017C72
0x140017c59  mov     rbx, [rsp+330h+lpMem]
0x140017c5e  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
