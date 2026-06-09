# ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::ParseCommandLine(ushort const *,long *)

- ea: `0x140004210`
- end: `0x140004450`
- name: `?ParseCommandLine@?$CAtlExeModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@QEAA_NPEBGPEAJ@Z`
- size: `576`
- prototype: `char __fastcall(__int64, const WCHAR *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006b20`

## callees

- `0x1400034dc`
- `0x1400039a4`
- `0x140004210`
- `0x140005dc8`
- `0x140005f04`
- `0x140006234`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `USER32!CharNextW` at `0x140004276`
- `USER32!CharNextW` at `0x140004284`
- `USER32!CharNextW` at `0x1400042fe`
- `USER32!CharNextW` at `0x14000430c`
- `USER32!CharNextW` at `0x140004322`
- `USER32!CharNextW` at `0x140004276`
- `USER32!CharNextW` at `0x140004284`
- `USER32!CharNextW` at `0x1400042fe`
- `USER32!CharNextW` at `0x14000430c`
- `USER32!CharNextW` at `0x140004322`

## pseudocode

```c
char __fastcall ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::ParseCommandLine(
        __int64 a1,
        const WCHAR *a2,
        int *a3)
{
  const WCHAR *v4; // rbx
  WCHAR *v5; // rax
  unsigned int v7; // edx
  ATL::CAtlComModule *v8; // rcx
  const struct _GUID *v9; // r8
  unsigned int v10; // edx
  ATL::CAtlModule *v11; // rcx
  WCHAR *v12; // rax
  const WCHAR *v13; // rax
  int updated; // eax
  const unsigned __int16 *v15; // rdx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v16; // rbx
  __int64 *i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v18; // rdi
  int v19; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v20; // rax
  int v21; // eax
  const wchar_t *v22; // [rsp+20h] [rbp-30h] BYREF
  const wchar_t *v23; // [rsp+28h] [rbp-28h]
  __int128 v24; // [rsp+30h] [rbp-20h]
  WCHAR sz[4]; // [rsp+40h] [rbp-10h] BYREF

  v4 = a2;
  *a3 = 0;
  wcscpy(sz, L"-/");
  if ( a2 )
  {
LABEL_2:
    if ( *v4 )
    {
      v5 = sz;
      while ( 1 )
      {
        if ( !*v5 )
        {
LABEL_7:
          v4 = CharNextW(v4);
          if ( v4 )
            goto LABEL_2;
          return 1;
        }
        if ( *v4 == *v5 )
          break;
        v5 = CharNextW(v5);
        if ( !v5 )
          goto LABEL_7;
      }
LABEL_19:
      v13 = CharNextW(v4);
      v4 = v13;
      if ( !v13 )
        return 1;
      if ( (unsigned int)ATL::CAtlModule::WordCmpI(v13, L"UnregServer") )
      {
        if ( (unsigned int)ATL::CAtlModule::WordCmpI(v4, L"RegServer") )
        {
          for ( ; v4; v4 = CharNextW(v4) )
          {
            if ( !*v4 )
              break;
            v12 = sz;
            do
            {
              if ( !*v12 )
                break;
              if ( *v4 == *v12 )
                goto LABEL_19;
              v12 = CharNextW(v12);
            }
            while ( v12 );
          }
          return 1;
        }
        v22 = L"APPID";
        v23 = L"{F1425A67-1545-44A2-AB59-8DF1020452D9}";
        v24 = 0;
        updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v11, v10, 1, (struct ATL::_ATL_REGMAP_ENTRY *)&v22);
        *a3 = updated;
        if ( updated < 0 )
          return 0;
        v16 = off_14001B2E0;
        for ( i = off_14001B2E8; v16 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v16 )
        {
          v18 = *v16;
          if ( *v16 )
          {
            v19 = (*((__int64 (__fastcall **)(__int64))v18 + 1))(1);
            if ( v19 < 0 )
              goto LABEL_37;
            v20 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v18 + 7))();
            v19 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v18, v20, 1);
            if ( v19 < 0 )
              goto LABEL_37;
            i = off_14001B2E8;
          }
        }
        v19 = ATL::AtlRegisterTypeLib(off_14001B2D8, v15);
        if ( v19 >= 0 )
        {
          if ( ATL::_pPerfRegFunc )
            v19 = ((__int64 (__fastcall *)(HMODULE))ATL::_pPerfRegFunc)(hInstance);
        }
      }
      else
      {
        if ( !ATL::_pPerfUnRegFunc || (v21 = ATL::_pPerfUnRegFunc(), v21 >= 0) )
          v21 = ATL::CAtlComModule::UnregisterServer(v8, v7, v9);
        *a3 = v21;
        if ( v21 < 0 )
          return 0;
        v22 = L"APPID";
        v23 = L"{F1425A67-1545-44A2-AB59-8DF1020452D9}";
        v24 = 0;
        v19 = ATL::CAtlModule::UpdateRegistryFromResourceS(v8, v7, 0, (struct ATL::_ATL_REGMAP_ENTRY *)&v22);
      }
LABEL_37:
      *a3 = v19;
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140004210  mov     [rsp-18h+arg_0], rbx
0x140004215  mov     [rsp-18h+arg_18], rsi
0x14000421a  push    rbp
0x14000421b  push    rdi
0x14000421c  push    r14
0x14000421e  mov     rbp, rsp
0x140004221  sub     rsp, 50h
0x140004225  mov     rax, cs:__security_cookie
0x14000422c  xor     rax, rsp
0x14000422f  mov     [rbp+var_8], rax
0x140004233  mov     rsi, r8
0x140004236  mov     rbx, rdx
0x140004239  xor     r14d, r14d
0x14000423c  mov     [r8], r14d
0x14000423f  mov     eax, dword ptr cs:asc_140016768; "-/"
0x140004245  mov     dword ptr [rbp+sz], eax
0x140004248  movzx   eax, word ptr cs:asc_140016768+4; ""
0x14000424f  mov     [rbp+var_C], ax
0x140004253  test    rdx, rdx
0x140004256  jz      short loc_140004292
0x140004258  cmp     [rbx], r14w
0x14000425c  jz      short loc_140004292
0x14000425e  lea     rax, [rbp+sz]
0x140004262  movzx   ecx, word ptr [rax]
0x140004265  test    cx, cx
0x140004268  jz      short loc_140004281
0x14000426a  cmp     [rbx], cx
0x14000426d  jz      loc_14000431F
0x140004273  mov     rcx, rax; lpsz
0x140004276  call    cs:__imp_CharNextW
0x14000427c  test    rax, rax
0x14000427f  jnz     short loc_140004262
0x140004281  mov     rcx, rbx; lpsz
0x140004284  call    cs:__imp_CharNextW
0x14000428a  mov     rbx, rax
0x14000428d  test    rax, rax
0x140004290  jnz     short loc_140004258
0x140004292  mov     al, 1
0x140004294  mov     rcx, [rbp+var_8]
0x140004298  xor     rcx, rsp; StackCookie
0x14000429b  call    __security_check_cookie
0x1400042a0  lea     r11, [rsp+50h+var_s0]
0x1400042a5  mov     rbx, [r11+20h]
0x1400042a9  mov     rsi, [r11+38h]
0x1400042ad  mov     rsp, r11
0x1400042b0  pop     r14
0x1400042b2  pop     rdi
0x1400042b3  pop     rbp
0x1400042b4  retn
0x1400042b5  lea     rdx, aUnregserver; "UnregServer"
0x1400042bc  mov     rcx, rbx; lpsz
0x1400042bf  call    ?WordCmpI@CAtlModule@ATL@@SAHPEBG0@Z; ATL::CAtlModule::WordCmpI(ushort const *,ushort const *)
0x1400042c4  test    eax, eax
0x1400042c6  jz      loc_1400043FC
0x1400042cc  lea     rdx, aRegserver; "RegServer"
0x1400042d3  mov     rcx, rbx; lpsz
0x1400042d6  call    ?WordCmpI@CAtlModule@ATL@@SAHPEBG0@Z; ATL::CAtlModule::WordCmpI(ushort const *,ushort const *)
0x1400042db  test    eax, eax
0x1400042dd  jz      short loc_140004335
0x1400042df  test    rbx, rbx
0x1400042e2  jz      short loc_140004292
0x1400042e4  cmp     [rbx], r14w
0x1400042e8  jz      short loc_140004292
0x1400042ea  lea     rax, [rbp+sz]
0x1400042ee  movzx   ecx, word ptr [rax]
0x1400042f1  test    cx, cx
0x1400042f4  jz      short loc_140004309
0x1400042f6  cmp     [rbx], cx
0x1400042f9  jz      short loc_14000431F
0x1400042fb  mov     rcx, rax; lpsz
0x1400042fe  call    cs:__imp_CharNextW
0x140004304  test    rax, rax
0x140004307  jnz     short loc_1400042EE
0x140004309  mov     rcx, rbx; lpsz
0x14000430c  call    cs:__imp_CharNextW
0x140004312  mov     rbx, rax
0x140004315  test    rax, rax
0x140004318  jnz     short loc_1400042E4
0x14000431a  jmp     loc_140004292
0x14000431f  mov     rcx, rbx; lpsz
0x140004322  call    cs:__imp_CharNextW
0x140004328  test    rax, rax
0x14000432b  mov     rbx, rax
0x14000432e  jnz     short loc_1400042B5
0x140004330  jmp     loc_140004292
0x140004335  lea     rax, aAppid; "APPID"
0x14000433c  mov     [rbp+var_30], rax
0x140004340  lea     rax, aF1425a67154544; "{F1425A67-1545-44A2-AB59-8DF1020452D9}"
0x140004347  mov     [rbp+var_28], rax
0x14000434b  xorps   xmm0, xmm0
0x14000434e  movdqu  [rbp+var_20], xmm0
0x140004353  lea     r9, [rbp+var_30]; struct ATL::_ATL_REGMAP_ENTRY *
0x140004357  mov     r8d, 1; int
0x14000435d  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x140004362  mov     [rsi], eax
0x140004364  test    eax, eax
0x140004366  js      loc_140004449
0x14000436c  mov     eax, r14d
0x14000436f  mov     rbx, cs:off_14001B2E0
0x140004376  mov     rcx, cs:off_14001B2E8
0x14000437d  cmp     rbx, rcx
0x140004380  jnb     short loc_1400043CE
0x140004382  mov     rdi, [rbx]
0x140004385  test    rdi, rdi
0x140004388  jz      short loc_1400043C1
0x14000438a  mov     ecx, 1
0x14000438f  mov     rax, [rdi+8]
0x140004393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004398  test    eax, eax
0x14000439a  js      short loc_1400043FA
0x14000439c  mov     rax, [rdi+38h]
0x1400043a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043a5  mov     r8d, 1; int
0x1400043ab  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1400043ae  mov     rcx, [rdi]; rguid
0x1400043b1  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1400043b6  test    eax, eax
0x1400043b8  js      short loc_1400043FA
0x1400043ba  mov     rcx, cs:off_14001B2E8
0x1400043c1  add     rbx, 8
0x1400043c5  cmp     rbx, rcx
0x1400043c8  jb      short loc_140004382
0x1400043ca  test    eax, eax
0x1400043cc  js      short loc_1400043FA
0x1400043ce  mov     rcx, cs:off_14001B2D8; HINSTANCE
0x1400043d5  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x1400043da  test    eax, eax
0x1400043dc  js      short loc_1400043FA
0x1400043de  mov     rdx, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x1400043e5  test    rdx, rdx
0x1400043e8  jz      short loc_1400043FA
0x1400043ea  mov     rcx, cs:hInstance
0x1400043f1  mov     rax, rdx
0x1400043f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043f9  nop
0x1400043fa  jmp     short loc_140004447
0x1400043fc  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x140004403  test    rax, rax
0x140004406  jz      short loc_140004411
0x140004408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000440d  test    eax, eax
0x14000440f  js      short loc_140004417
0x140004411  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x140004416  nop
0x140004417  mov     [rsi], eax
0x140004419  test    eax, eax
0x14000441b  js      short loc_140004449
0x14000441d  lea     rax, aAppid; "APPID"
0x140004424  mov     [rbp+var_30], rax
0x140004428  lea     rax, aF1425a67154544; "{F1425A67-1545-44A2-AB59-8DF1020452D9}"
0x14000442f  mov     [rbp+var_28], rax
0x140004433  xorps   xmm0, xmm0
0x140004436  movdqu  [rbp+var_20], xmm0
0x14000443b  lea     r9, [rbp+var_30]; struct ATL::_ATL_REGMAP_ENTRY *
0x14000443f  xor     r8d, r8d; int
0x140004442  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x140004447  mov     [rsi], eax
0x140004449  xor     al, al
0x14000444b  jmp     loc_140004294
```
