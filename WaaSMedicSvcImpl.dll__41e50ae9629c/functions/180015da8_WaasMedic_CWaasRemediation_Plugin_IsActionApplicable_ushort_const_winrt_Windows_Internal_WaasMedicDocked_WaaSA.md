# WaasMedic::CWaasRemediation::Plugin_IsActionApplicable(ushort const *,winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)

- ea: `0x180015da8`
- end: `0x1800160a6`
- name: `?Plugin_IsActionApplicable@CWaasRemediation@WaasMedic@@AEAAJPEBGW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180011fdc`

## callees

- `0x1800050a0`
- `0x180008d8d`
- `0x180008d99`
- `0x180009cd0`
- `0x18000f134`
- `0x18001039c`
- `0x180015da8`
- `0x18001dc50`
- `0x18002e56c`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fd4`

## string_xrefs

- `0x180015e0c`: `Plugin_IsActionApplicable`
- `0x180015e33`: `Plugin_IsActionApplicable`
- `0x180015ecf`: `Plugin_IsActionApplicable`
- `0x180015ee7`: `Plugin_IsActionApplicable`
- `0x180015fc7`: `Plugin_IsActionApplicable`
- `0x180016004`: `Version of Plugin_IsActionApplicable found: %d`
- `0x180015fec`: `Unable to load any version of Plugin_IsActionApplicable 0x%08x`
- `0x18001605c`: `Fallback to version 1 of Plugin_IsActionApplicable`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::CWaasRemediation::Plugin_IsActionApplicable(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        __int64 a5)
{
  __int64 v7; // rbx
  int v8; // edi
  unsigned int v10; // r14d
  __m128i si128; // xmm6
  bool v12; // cc
  unsigned __int64 *v13; // rsi
  int v14; // edi
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r15
  __int64 v18; // rbx
  size_t v19; // rbx
  __int64 v20; // rax
  FARPROC ProcAddress; // rbx
  signed int LastError; // eax
  unsigned int v23; // ebx
  __int64 v24; // r8
  int v25; // [rsp+28h] [rbp-B1h]
  _QWORD v28[3]; // [rsp+48h] [rbp-91h] BYREF
  __int128 v29; // [rsp+60h] [rbp-79h]
  _OWORD v30[2]; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v31[32]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v32[32]; // [rsp+B0h] [rbp-29h] BYREF

  v7 = a1;
  v8 = 0;
  if ( !*(_QWORD *)(a1 + 64) )
    return 2147654730LL;
  v10 = 3;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v12 = 0;
  do
  {
    if ( v12 )
    {
      v30[0] = 0;
      v30[1] = si128;
      LOWORD(v30[0]) = 0;
      v13 = (unsigned __int64 *)v30;
      v14 = v8 | 2;
    }
    else
    {
      v13 = (unsigned __int64 *)std::to_wstring(v31, v10);
      v14 = v8 | 1;
    }
    v15 = v13[2];
    v16 = v13[3];
    if ( v16 - v15 < 0x19 )
    {
      v13 = (unsigned __int64 *)std::wstring::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,unsigned short const *,unsigned __int64>(
                                  v13,
                                  v25,
                                  25);
    }
    else
    {
      v13[2] = v15 + 25;
      if ( v16 <= 7 )
        v17 = (unsigned __int64)v13;
      else
        v17 = *v13;
      if ( (unsigned __int64)L"" <= v17 || (unsigned __int64)L"Plugin_IsActionApplicable" > v17 + 2 * v15 )
      {
        v18 = 25;
      }
      else if ( v17 > (unsigned __int64)L"Plugin_IsActionApplicable" )
      {
        v18 = (__int64)(v17 - (_QWORD)L"Plugin_IsActionApplicable") >> 1;
      }
      else
      {
        v18 = 0;
      }
      memmove_0((void *)(v17 + 50), (const void *)v17, 2 * v15 + 2);
      v19 = 2 * v18;
      memcpy_0((void *)v17, L"Plugin_IsActionApplicable", v19);
      memcpy_0((void *)(v19 + v17), &aPluginIsaction[v19 / 2 + 25], 50 - v19);
      v7 = a1;
    }
    *(_OWORD *)&v28[1] = 0;
    v29 = 0;
    *(_OWORD *)&v28[1] = *(_OWORD *)v13;
    v29 = *((_OWORD *)v13 + 1);
    v13[2] = 0;
    v13[3] = 7;
    *(_WORD *)v13 = 0;
    v8 = v14 | 4;
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      std::wstring::~wstring(v30);
    }
    if ( (v8 & 1) != 0 )
    {
      v8 &= ~1u;
      std::wstring::~wstring(v31);
    }
    v20 = WaasMedic::ws2s(v32, &v28[1]);
    if ( *(_QWORD *)(v20 + 24) > 0xFu )
      v20 = *(_QWORD *)v20;
    ProcAddress = GetProcAddress(*(HMODULE *)(v7 + 64), (LPCSTR)v20);
    std::string::~string(v32);
    if ( ProcAddress )
    {
      LogLevelW(5u, L"Version of Plugin_IsActionApplicable found: %d", v10);
      std::wstring::~wstring(&v28[1]);
      LogLevelW(4u, L"Checking if %s is applicable", a2);
      if ( v10 < 2 )
      {
        LogLevelW(4u, L"Fallback to version 1 of Plugin_IsActionApplicable");
        return ((__int64 (__fastcall *)(__int64, _QWORD, __int64))ProcAddress)(a2, a3, a5);
      }
      else
      {
        LOBYTE(v24) = a4;
        return ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64))ProcAddress)(a2, a3, v24, a5);
      }
    }
    --v10;
    std::wstring::~wstring(&v28[1]);
    v12 = v10 <= 1;
    v7 = a1;
  }
  while ( (int)v10 >= 1 );
  LastError = GetLastError();
  v23 = LastError;
  if ( LastError > 0 )
    v23 = (unsigned __int16)LastError | 0x80070000;
  LogLevelW(2u, L"Unable to load any version of Plugin_IsActionApplicable 0x%08x", v23);
  return v23;
}

```

## disassembly

```asm
0x180015da8  mov     rax, rsp
0x180015dab  push    rbp
0x180015dac  push    rbx
0x180015dad  push    rsi
0x180015dae  push    rdi
0x180015daf  push    r12
0x180015db1  push    r13
0x180015db3  push    r14
0x180015db5  push    r15
0x180015db7  lea     rbp, [rax-57h]
0x180015dbb  sub     rsp, 0E8h
0x180015dc2  movaps  xmmword ptr [rax-58h], xmm6
0x180015dc6  mov     rax, cs:__security_cookie
0x180015dcd  xor     rax, rsp
0x180015dd0  mov     qword ptr [rbp+4Fh+var_58], rax
0x180015dd4  mov     byte ptr [rsp+120h+var_F0], r9b
0x180015dd9  mov     r13d, r8d
0x180015ddc  mov     r12, rdx
0x180015ddf  mov     rbx, rcx
0x180015de2  mov     [rsp+120h+var_E8], rcx
0x180015de7  mov     rax, [rbp+4Fh+arg_20]
0x180015deb  mov     qword ptr [rsp+120h+var_E0], rax
0x180015df0  xor     edi, edi
0x180015df2  mov     dword ptr [rsp+120h+var_F0+4], edi
0x180015df6  cmp     [rcx+40h], rdi
0x180015dfa  jnz     short loc_180015E06
0x180015dfc  mov     eax, 80029C4Ah
0x180015e01  jmp     loc_18001607E
0x180015e06  mov     r14d, 3
0x180015e0c  lea     rdx, aPluginIsaction; "Plugin_IsActionApplicable"
0x180015e13  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180015e1b  cmp     r14d, 1
0x180015e1f  jbe     short loc_180015E3C
0x180015e21  mov     edx, r14d
0x180015e24  lea     rcx, [rbp+4Fh+var_98]
0x180015e28  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180015e2d  mov     rsi, rax
0x180015e30  or      edi, 1
0x180015e33  lea     rdx, aPluginIsaction; "Plugin_IsActionApplicable"
0x180015e3a  jmp     short loc_180015E55
0x180015e3c  xorps   xmm0, xmm0
0x180015e3f  movups  [rbp+4Fh+var_B8], xmm0
0x180015e43  movdqu  [rbp+4Fh+var_A8], xmm6
0x180015e48  xor     eax, eax
0x180015e4a  mov     word ptr [rbp+4Fh+var_B8], ax
0x180015e4e  lea     rsi, [rbp+4Fh+var_B8]
0x180015e52  or      edi, 2
0x180015e55  mov     dword ptr [rsp+120h+var_F0+4], edi
0x180015e59  mov     r8, [rsi+10h]
0x180015e5d  mov     rcx, [rsi+18h]
0x180015e61  mov     rax, rcx
0x180015e64  sub     rax, r8
0x180015e67  cmp     rax, 19h
0x180015e6b  jb      loc_180015F05
0x180015e71  lea     rax, [r8+19h]
0x180015e75  mov     [rsi+10h], rax
0x180015e79  cmp     rcx, 7
0x180015e7d  jbe     short loc_180015E84
0x180015e7f  mov     r15, [rsi]
0x180015e82  jmp     short loc_180015E87
0x180015e84  mov     r15, rsi
0x180015e87  lea     rax, aPluginIsaction+32h; ""
0x180015e8e  cmp     rax, r15
0x180015e91  jbe     short loc_180015EB0
0x180015e93  lea     rax, [r15+r8*2]
0x180015e97  cmp     rdx, rax
0x180015e9a  ja      short loc_180015EB0
0x180015e9c  cmp     r15, rdx
0x180015e9f  ja      short loc_180015EA5
0x180015ea1  xor     ebx, ebx
0x180015ea3  jmp     short loc_180015EB5
0x180015ea5  mov     rbx, r15
0x180015ea8  sub     rbx, rdx
0x180015eab  sar     rbx, 1
0x180015eae  jmp     short loc_180015EB5
0x180015eb0  mov     ebx, 19h
0x180015eb5  lea     r8, ds:2[r8*2]; Size
0x180015ebd  lea     rcx, [r15+32h]; void *
0x180015ec1  mov     rdx, r15; Src
0x180015ec4  call    memmove_0
0x180015ec9  add     rbx, rbx
0x180015ecc  mov     r8, rbx; Size
0x180015ecf  lea     rdx, aPluginIsaction; "Plugin_IsActionApplicable"
0x180015ed6  mov     rcx, r15; void *
0x180015ed9  call    memcpy_0
0x180015ede  mov     r8d, 32h ; '2'
0x180015ee4  sub     r8, rbx; Size
0x180015ee7  lea     rdx, aPluginIsaction; "Plugin_IsActionApplicable"
0x180015eee  add     rdx, 32h ; '2'
0x180015ef2  add     rdx, rbx; Src
0x180015ef5  lea     rcx, [rbx+r15]; void *
0x180015ef9  call    memcpy_0
0x180015efe  mov     rbx, [rsp+120h+var_E8]
0x180015f03  jmp     short loc_180015F1E
0x180015f05  mov     [rsp+120h+var_F8], 19h; __int64
0x180015f0e  mov     edx, 19h
0x180015f13  mov     rcx, rsi; Src
0x180015f16  call    ??$_Reallocate_grow_by@V_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c5c7986eab02a925bb28d3483355880c_@@_KPEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c5c7986eab02a925bb28d3483355880c_,unsigned __int64,ushort const *,unsigned __int64)
0x180015f1b  mov     rsi, rax
0x180015f1e  xorps   xmm0, xmm0
0x180015f21  movups  xmmword ptr [rsp+120h+var_E0+8], xmm0
0x180015f26  xorps   xmm1, xmm1
0x180015f29  movdqu  [rbp+4Fh+var_C8], xmm1
0x180015f2e  movups  xmm0, xmmword ptr [rsi]
0x180015f31  movups  xmmword ptr [rsp+120h+var_E0+8], xmm0
0x180015f36  movups  xmm1, xmmword ptr [rsi+10h]
0x180015f3a  movups  [rbp+4Fh+var_C8], xmm1
0x180015f3e  mov     qword ptr [rsi+10h], 0
0x180015f46  mov     qword ptr [rsi+18h], 7
0x180015f4e  xor     eax, eax
0x180015f50  mov     [rsi], ax
0x180015f53  or      edi, 4
0x180015f56  test    dil, 2
0x180015f5a  jz      short loc_180015F69
0x180015f5c  and     edi, 0FFFFFFFDh
0x180015f5f  lea     rcx, [rbp+4Fh+var_B8]; void *
0x180015f63  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015f68  nop
0x180015f69  test    dil, 1
0x180015f6d  jz      short loc_180015F7B
0x180015f6f  and     edi, 0FFFFFFFEh
0x180015f72  lea     rcx, [rbp+4Fh+var_98]; void *
0x180015f76  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015f7b  lea     rdx, [rsp+120h+var_E0+8]
0x180015f80  lea     rcx, [rbp+4Fh+var_78]
0x180015f84  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x180015f89  cmp     qword ptr [rax+18h], 0Fh
0x180015f8e  jbe     short loc_180015F93
0x180015f90  mov     rax, [rax]
0x180015f93  mov     rdx, rax; lpProcName
0x180015f96  mov     rcx, [rbx+40h]; hModule
0x180015f9a  call    cs:__imp_GetProcAddress
0x180015fa0  mov     rbx, rax
0x180015fa3  lea     rcx, [rbp+4Fh+var_78]
0x180015fa7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015fac  test    rbx, rbx
0x180015faf  jnz     short loc_180016001
0x180015fb1  dec     r14d
0x180015fb4  lea     rcx, [rsp+120h+var_E0+8]; void *
0x180015fb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015fbe  cmp     r14d, 1
0x180015fc2  mov     rbx, [rsp+120h+var_E8]
0x180015fc7  lea     rdx, aPluginIsaction; "Plugin_IsActionApplicable"
0x180015fce  jge     loc_180015E1F
0x180015fd4  call    cs:__imp_GetLastError
0x180015fda  mov     ebx, eax
0x180015fdc  test    eax, eax
0x180015fde  jle     short loc_180015FE9
0x180015fe0  movzx   ebx, ax
0x180015fe3  or      ebx, 80070000h
0x180015fe9  mov     r8d, ebx
0x180015fec  lea     rdx, aUnableToLoadAn; "Unable to load any version of Plugin_Is"...
0x180015ff3  mov     ecx, 2; unsigned __int8
0x180015ff8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180015ffd  mov     eax, ebx
0x180015fff  jmp     short loc_18001607E
0x180016001  mov     r8d, r14d
0x180016004  lea     rdx, aVersionOfPlugi; "Version of Plugin_IsActionApplicable fo"...
0x18001600b  mov     ecx, 5; unsigned __int8
0x180016010  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180016015  nop
0x180016016  lea     rcx, [rsp+120h+var_E0+8]; void *
0x18001601b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016020  mov     r8, r12
0x180016023  lea     rdx, aCheckingIfSIsA; "Checking if %s is applicable"
0x18001602a  mov     ecx, 4; unsigned __int8
0x18001602f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180016034  cmp     r14d, 2
0x180016038  jb      short loc_180016054
0x18001603a  mov     r9, qword ptr [rsp+120h+var_E0]
0x18001603f  mov     r8b, byte ptr [rsp+120h+var_F0]
0x180016044  mov     edx, r13d
0x180016047  mov     rcx, r12
0x18001604a  mov     rax, rbx
0x18001604d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016052  jmp     short loc_18001607E
0x180016054  xor     eax, eax
0x180016056  cmp     r14d, 1
0x18001605a  jnz     short loc_18001607E
0x18001605c  lea     rdx, aFallbackToVers; "Fallback to version 1 of Plugin_IsActio"...
0x180016063  lea     ecx, [rax+4]; unsigned __int8
0x180016066  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001606b  mov     r8, qword ptr [rsp+120h+var_E0]
0x180016070  mov     edx, r13d
0x180016073  mov     rcx, r12
0x180016076  mov     rax, rbx
0x180016079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001607e  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x180016082  xor     rcx, rsp; StackCookie
0x180016085  call    __security_check_cookie
0x18001608a  movaps  xmm6, [rsp+120h+var_58+8]
0x180016092  add     rsp, 0E8h
0x180016099  pop     r15
0x18001609b  pop     r14
0x18001609d  pop     r13
0x18001609f  pop     r12
0x1800160a1  pop     rdi
0x1800160a2  pop     rsi
0x1800160a3  pop     rbx
0x1800160a4  pop     rbp
0x1800160a5  retn
```
