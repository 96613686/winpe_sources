# WaasMedic::CRemediationPluginBase::EvaluateActionLimitBlock(tagPluginActionApplicability *)

- ea: `0x18001ba20`
- end: `0x18001bbae`
- name: `?EvaluateActionLimitBlock@CRemediationPluginBase@WaasMedic@@IEAAJPEAW4tagPluginActionApplicability@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(WaasMedic::CRemediationPluginBase *__hidden this, enum tagPluginActionApplicability *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18001cae0`
- `0x18003b790`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18001ba20`
- `0x18002543c`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001ba50`
- `OLEAUT32!__imp_VariantInit` at `0x18001ba50`
- `OLEAUT32!__imp_VariantClear` at `0x18001bb83`
- `OLEAUT32!__imp_VariantClear` at `0x18001bb83`

## string_xrefs

- `0x18001bafd`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001bb1b`: `PluginRunCount`
- `0x18001bb66`: `PluginRunCount`
- `0x18001bb50`: `Plugin %s action inapplicable because of exhausted action limit.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CRemediationPluginBase::EvaluateActionLimitBlock(
        WaasMedic::CRemediationPluginBase *this,
        enum tagPluginActionApplicability *a2)
{
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, _OWORD *, _OWORD *, _DWORD *); // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // ebx
  int v9; // eax
  unsigned int Lo; // ecx
  int v12; // [rsp+20h] [rbp-49h]
  _DWORD v13[2]; // [rsp+30h] [rbp-39h] BYREF
  char v14; // [rsp+38h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-29h] BYREF
  _OWORD v16[2]; // [rsp+58h] [rbp-11h] BYREF
  _OWORD v17[2]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  VariantInit(&pvarg);
  *(_DWORD *)a2 = 0;
  v14 = 0;
  v13[0] = 0;
  v13[1] = 2;
  v4 = *((_QWORD *)this + 13);
  v5 = *(__int64 (__fastcall **)(__int64, _OWORD *, _OWORD *, _DWORD *))(*(_QWORD *)v4 + 8LL);
  memset(v17, 0, sizeof(v17));
  std::wstring::_Construct<1,unsigned short const *>(v17, L"ACTIONLIMIT", 11);
  v6 = *((_QWORD *)this + 14);
  memset(v16, 0, sizeof(v16));
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  std::wstring::_Construct<1,unsigned short const *>(v16, v6, v7);
  v8 = v5(v4, v16, v17, v13);
  std::wstring::~wstring(v16);
  std::wstring::~wstring(v17);
  if ( v8 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 12) + 16LL))(
           *((_QWORD *)this + 12),
           *((_QWORD *)this + 14),
           L"PluginRunCount",
           &pvarg);
    v8 = v9;
    if ( v9 < 0 )
    {
      LogLevelW(2u, L"Failed to retrieve %s from state provider! hr = 0x%08x", L"PluginRunCount", (unsigned int)v9);
    }
    else
    {
      Lo = 0;
      if ( pvarg.vt == 19 )
        Lo = pvarg.cyVal.Lo;
      if ( Lo >= v13[0] )
      {
        *(_DWORD *)a2 = 1;
        LogLevelW(4u, L"Plugin %s action inapplicable because of exhausted action limit.", *((_QWORD *)this + 14));
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26B,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
      (const char *)(unsigned int)v8,
      v12);
  }
  VariantClear(&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ba20  mov     [rsp-8+arg_10], rbx
0x18001ba25  push    rbp
0x18001ba26  push    rsi
0x18001ba27  push    rdi
0x18001ba28  push    r14
0x18001ba2a  push    r15
0x18001ba2c  lea     rbp, [rsp-37h]
0x18001ba31  sub     rsp, 0A0h
0x18001ba38  mov     rax, cs:__security_cookie
0x18001ba3f  xor     rax, rsp
0x18001ba42  mov     [rbp+57h+var_28], rax
0x18001ba46  mov     rsi, rdx
0x18001ba49  mov     rdi, rcx
0x18001ba4c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001ba50  call    cs:__imp_VariantInit
0x18001ba56  nop
0x18001ba57  xor     r15d, r15d
0x18001ba5a  mov     [rsi], r15d
0x18001ba5d  mov     [rbp+57h+var_88], r15b
0x18001ba61  mov     [rbp+57h+var_90], r15d
0x18001ba65  mov     [rbp+57h+var_8C], 2
0x18001ba6c  mov     rbx, [rdi+68h]
0x18001ba70  mov     rax, [rbx]
0x18001ba73  mov     r14, [rax+8]
0x18001ba77  xorps   xmm0, xmm0
0x18001ba7a  movups  [rbp+57h+var_48], xmm0
0x18001ba7e  xorps   xmm1, xmm1
0x18001ba81  movdqu  [rbp+57h+var_38], xmm1
0x18001ba86  lea     r8d, [r15+0Bh]
0x18001ba8a  lea     rdx, aActionlimit; "ACTIONLIMIT"
0x18001ba91  lea     rcx, [rbp+57h+var_48]
0x18001ba95  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001ba9a  nop
0x18001ba9b  mov     rdx, [rdi+70h]
0x18001ba9f  xorps   xmm0, xmm0
0x18001baa2  movups  [rbp+57h+var_68], xmm0
0x18001baa6  xorps   xmm1, xmm1
0x18001baa9  movdqu  [rbp+57h+var_58], xmm1
0x18001baae  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001bab2  inc     r8
0x18001bab5  cmp     [rdx+r8*2], r15w
0x18001baba  jnz     short loc_18001BAB2
0x18001babc  lea     rcx, [rbp+57h+var_68]
0x18001bac0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bac5  nop
0x18001bac6  lea     r9, [rbp+57h+var_90]
0x18001baca  lea     r8, [rbp+57h+var_48]
0x18001bace  lea     rdx, [rbp+57h+var_68]
0x18001bad2  mov     rcx, rbx
0x18001bad5  mov     rax, r14
0x18001bad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001badd  mov     ebx, eax
0x18001badf  lea     rcx, [rbp+57h+var_68]; void *
0x18001bae3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bae8  nop
0x18001bae9  lea     rcx, [rbp+57h+var_48]; void *
0x18001baed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001baf2  test    ebx, ebx
0x18001baf4  jns     short loc_18001BB10
0x18001baf6  mov     rcx, [rbp+5Fh]; this
0x18001bafa  mov     r9d, ebx; char *
0x18001bafd  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001bb04  mov     edx, 26Bh; void *
0x18001bb09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb0e  jmp     short loc_18001BB7F
0x18001bb10  mov     rcx, [rdi+60h]
0x18001bb14  mov     rax, [rcx]
0x18001bb17  lea     r9, [rbp+57h+pvarg]
0x18001bb1b  lea     r8, aPluginruncount; "PluginRunCount"
0x18001bb22  mov     rdx, [rdi+70h]
0x18001bb26  mov     rax, [rax+10h]
0x18001bb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb2f  mov     ebx, eax
0x18001bb31  test    eax, eax
0x18001bb33  js      short loc_18001BB63
0x18001bb35  mov     ecx, r15d
0x18001bb38  cmp     word ptr [rbp+57h+pvarg], 13h
0x18001bb3d  cmovz   ecx, dword ptr [rbp+57h+pvarg+8]
0x18001bb41  cmp     ecx, [rbp+57h+var_90]
0x18001bb44  jb      short loc_18001BB7F
0x18001bb46  mov     dword ptr [rsi], 1
0x18001bb4c  mov     r8, [rdi+70h]
0x18001bb50  lea     rdx, aPluginSActionI_0; "Plugin %s action inapplicable because o"...
0x18001bb57  mov     ecx, 4; unsigned __int8
0x18001bb5c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001bb61  jmp     short loc_18001BB7F
0x18001bb63  mov     r9d, eax
0x18001bb66  lea     r8, aPluginruncount; "PluginRunCount"
0x18001bb6d  lea     rdx, aFailedToRetrie; "Failed to retrieve %s from state provid"...
0x18001bb74  mov     ecx, 2; unsigned __int8
0x18001bb79  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001bb7e  nop
0x18001bb7f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001bb83  call    cs:__imp_VariantClear
0x18001bb89  mov     eax, ebx
0x18001bb8b  mov     rcx, [rbp+57h+var_28]
0x18001bb8f  xor     rcx, rsp; StackCookie
0x18001bb92  call    __security_check_cookie
0x18001bb97  mov     rbx, [rsp+0C0h+arg_10]
0x18001bb9f  add     rsp, 0A0h
0x18001bba6  pop     r15
0x18001bba8  pop     r14
0x18001bbaa  pop     rdi
0x18001bbab  pop     rsi
0x18001bbac  pop     rbp
0x18001bbad  retn
```
