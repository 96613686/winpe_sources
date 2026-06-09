# StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1801052a8`
- end: `0x180105515`
- name: `?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEB_W11111111@Z`
- size: `621`
- prototype: `__int64 __fastcall(StateRepository::Globals::PartitionSettings *this, struct Common::RegistryKey *, wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801056f0`

## callees

- `0x1800038f0`
- `0x1800eabf4`
- `0x180104754`
- `0x180104d04`
- `0x180104ec4`
- `0x1801052a8`

## string_xrefs

- `0x180105301`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180105332`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1801054a5`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::Load(
        StateRepository::Globals::PartitionSettings *this,
        struct Common::RegistryKey *a2,
        wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        const wchar_t *a8,
        const wchar_t *a9,
        const wchar_t *a10,
        wchar_t *a11)
{
  void *v11; // rdi
  int Setting; // eax
  void *v16; // rbx
  unsigned int v17; // r15d
  int v18; // eax
  void *v19; // r15
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rdx
  int v24; // eax
  unsigned int v25; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v26; // [rsp+24h] [rbp-1Ch] BYREF
  unsigned int v27; // [rsp+28h] [rbp-18h] BYREF
  unsigned int v28; // [rsp+2Ch] [rbp-14h] BYREF
  unsigned int v29[4]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *Block; // [rsp+70h] [rbp+30h] BYREF

  v11 = 0;
  if ( *(_QWORD *)this )
    goto LABEL_11;
  Block = 0;
  Setting = StateRepository::Globals::GetSetting(a2, a3, a11, &Block);
  v16 = Block;
  v17 = Setting;
  if ( Setting >= 0 )
  {
    Block = 0;
    v18 = StateRepository::Globals::ExpandMacros((__int64)v16, &Block);
    v17 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v18,
        v25);
      operator delete(Block);
      goto LABEL_6;
    }
    v19 = Block;
    if ( Block || (v19 = v16, v16 = 0, v19) )
    {
      operator delete(0);
      v11 = v19;
    }
    operator delete(0);
    operator delete(v16);
LABEL_11:
    LODWORD(Block) = 0;
    v20 = StateRepository::Globals::GetSetting((HKEY *)a2, a4, (const wchar_t *)0x20000, &Block);
    v21 = v20;
    if ( v20 >= 0 )
    {
      v20 = StateRepository::Globals::GetSetting((HKEY *)a2, a5, (const wchar_t *)0x20000, v29);
      v21 = v20;
      if ( v20 >= 0 )
      {
        v25 = 0;
        v20 = StateRepository::Globals::GetSetting((HKEY *)a2, a6, (const wchar_t *)0x100000, &v25);
        v21 = v20;
        if ( v20 >= 0 )
        {
          v26 = 0;
          v20 = StateRepository::Globals::GetSetting((HKEY *)a2, a7, 0, &v26);
          v21 = v20;
          if ( v20 >= 0 )
          {
            v27 = 0;
            v20 = StateRepository::Globals::GetSetting((HKEY *)a2, a8, 0, &v27);
            v21 = v20;
            if ( v20 >= 0 )
            {
              v28 = 0;
              v20 = StateRepository::Globals::GetSetting((HKEY *)a2, a9, 0, &v28);
              v21 = v20;
              if ( v20 >= 0 )
              {
                v29[0] = 0;
                v20 = StateRepository::Globals::GetSetting((HKEY *)a2, a10, 0, v29);
                v21 = v20;
                if ( v20 >= 0 )
                {
                  if ( v11 )
                    *(_QWORD *)this = v11;
                  v24 = (int)Block;
                  v17 = 0;
                  *((_DWORD *)this + 2) = (_DWORD)Block;
                  *((_DWORD *)this + 3) = v24;
                  *((_DWORD *)this + 4) = v25;
                  *((_DWORD *)this + 5) = v26;
                  *((_DWORD *)this + 6) = v27;
                  *((_DWORD *)this + 7) = v28;
                  *((_DWORD *)this + 8) = v29[0];
                  goto LABEL_29;
                }
                v22 = 325;
              }
              else
              {
                v22 = 322;
              }
            }
            else
            {
              v22 = 319;
            }
          }
          else
          {
            v22 = 316;
          }
        }
        else
        {
          v22 = 313;
        }
      }
      else
      {
        v22 = 310;
      }
    }
    else
    {
      v22 = 307;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v20,
      v25);
    operator delete(v11);
    return v21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12C,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)(unsigned int)Setting,
    v25);
LABEL_6:
  operator delete(v16);
LABEL_29:
  operator delete(0);
  return v17;
}

```

## disassembly

```asm
0x1801052a8  mov     [rsp-28h+arg_8], rbx
0x1801052ad  mov     [rsp-28h+arg_10], rsi
0x1801052b2  push    rbp
0x1801052b3  push    rdi
0x1801052b4  push    r12
0x1801052b6  push    r14
0x1801052b8  push    r15
0x1801052ba  mov     rbp, rsp
0x1801052bd  sub     rsp, 40h
0x1801052c1  xor     edi, edi
0x1801052c3  mov     r12, r9
0x1801052c6  mov     rax, r8
0x1801052c9  mov     r14, rdx
0x1801052cc  mov     rsi, rcx
0x1801052cf  cmp     [rcx], rdi
0x1801052d2  jnz     loc_180105388
0x1801052d8  mov     r8, [rbp+arg_50]
0x1801052df  lea     r9, [rbp+Block]
0x1801052e3  mov     rdx, rax; unsigned __int16 *
0x1801052e6  mov     [rbp+Block], rdi
0x1801052ea  mov     rcx, r14; this
0x1801052ed  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W1AEAV?$AutoArray@_W$1??$AutoArrayDeallocate@_W@Common@@YAXPEA_W@Z@4@@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,wchar_t const *,Common::AutoArray<wchar_t,&Common::AutoArrayDeallocate<wchar_t>(wchar_t *)> &)
0x1801052f2  mov     rbx, [rbp+Block]
0x1801052f6  mov     r15d, eax
0x1801052f9  test    eax, eax
0x1801052fb  jns     short loc_180105317
0x1801052fd  mov     rcx, [rbp+28h]; this
0x180105301  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180105308  mov     r9d, eax; char *
0x18010530b  mov     edx, 12Ch; void *
0x180105310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105315  jmp     short loc_18010534F
0x180105317  lea     rdx, [rbp+Block]
0x18010531b  mov     [rbp+Block], rdi
0x18010531f  mov     rcx, rbx
0x180105322  call    ?ExpandMacros@Globals@StateRepository@@YAJPEB_WAEAV?$AutoArray@_W$1??$AutoArrayDeallocate@_W@Common@@YAXPEA_W@Z@Common@@@Z; StateRepository::Globals::ExpandMacros(wchar_t const *,Common::AutoArray<wchar_t,&Common::AutoArrayDeallocate<wchar_t>(wchar_t *)> &)
0x180105327  mov     r15d, eax
0x18010532a  test    eax, eax
0x18010532c  jns     short loc_18010535C
0x18010532e  mov     rcx, [rbp+28h]; this
0x180105332  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180105339  mov     r9d, eax; char *
0x18010533c  mov     edx, 12Eh; void *
0x180105341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105346  mov     rcx, [rbp+Block]; Block
0x18010534a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18010534f  mov     rcx, rbx; Block
0x180105352  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180105357  jmp     loc_1801054F2
0x18010535c  mov     r15, [rbp+Block]
0x180105360  test    r15, r15
0x180105363  jnz     short loc_18010536F
0x180105365  mov     r15, rbx
0x180105368  xor     ebx, ebx
0x18010536a  test    r15, r15
0x18010536d  jz      short loc_180105379
0x18010536f  xor     ecx, ecx; Block
0x180105371  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180105376  mov     rdi, r15
0x180105379  xor     ecx, ecx; Block
0x18010537b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180105380  mov     rcx, rbx; Block
0x180105383  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180105388  mov     r15d, 20000h
0x18010538e  mov     dword ptr [rbp+Block], 0
0x180105395  mov     r8d, r15d; wchar_t *
0x180105398  lea     r9, [rbp+Block]; unsigned int
0x18010539c  mov     rdx, r12; struct Common::RegistryKey *
0x18010539f  mov     rcx, r14; this
0x1801053a2  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x1801053a7  mov     ebx, eax
0x1801053a9  test    eax, eax
0x1801053ab  jns     short loc_1801053B7
0x1801053ad  mov     edx, 133h
0x1801053b2  jmp     loc_1801054A1
0x1801053b7  mov     rdx, [rbp+arg_20]; struct Common::RegistryKey *
0x1801053bb  lea     r9, [rbp+var_10]; unsigned int
0x1801053bf  mov     r8d, r15d; wchar_t *
0x1801053c2  mov     rcx, r14; this
0x1801053c5  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x1801053ca  mov     ebx, eax
0x1801053cc  test    eax, eax
0x1801053ce  jns     short loc_1801053DA
0x1801053d0  mov     edx, 136h
0x1801053d5  jmp     loc_1801054A1
0x1801053da  mov     rdx, [rbp+arg_28]; struct Common::RegistryKey *
0x1801053de  lea     r9, [rbp+var_20]; unsigned int
0x1801053e2  mov     r8d, 100000h; wchar_t *
0x1801053e8  mov     [rbp+var_20], 0
0x1801053ef  mov     rcx, r14; this
0x1801053f2  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x1801053f7  mov     ebx, eax
0x1801053f9  test    eax, eax
0x1801053fb  jns     short loc_180105407
0x1801053fd  mov     edx, 139h
0x180105402  jmp     loc_1801054A1
0x180105407  mov     rdx, [rbp+arg_30]; struct Common::RegistryKey *
0x18010540b  lea     r9, [rbp+var_1C]; unsigned int
0x18010540f  xor     r8d, r8d; wchar_t *
0x180105412  mov     [rbp+var_1C], 0
0x180105419  mov     rcx, r14; this
0x18010541c  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105421  mov     ebx, eax
0x180105423  test    eax, eax
0x180105425  jns     short loc_18010542E
0x180105427  mov     edx, 13Ch
0x18010542c  jmp     short loc_1801054A1
0x18010542e  mov     rdx, [rbp+arg_38]; struct Common::RegistryKey *
0x180105432  lea     r9, [rbp+var_18]; unsigned int
0x180105436  xor     r8d, r8d; wchar_t *
0x180105439  mov     [rbp+var_18], 0
0x180105440  mov     rcx, r14; this
0x180105443  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105448  mov     ebx, eax
0x18010544a  test    eax, eax
0x18010544c  jns     short loc_180105455
0x18010544e  mov     edx, 13Fh
0x180105453  jmp     short loc_1801054A1
0x180105455  mov     rdx, [rbp+arg_40]; struct Common::RegistryKey *
0x180105459  lea     r9, [rbp+var_14]; unsigned int
0x18010545d  xor     r8d, r8d; wchar_t *
0x180105460  mov     [rbp+var_14], 0
0x180105467  mov     rcx, r14; this
0x18010546a  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x18010546f  mov     ebx, eax
0x180105471  test    eax, eax
0x180105473  jns     short loc_18010547C
0x180105475  mov     edx, 142h
0x18010547a  jmp     short loc_1801054A1
0x18010547c  mov     rdx, [rbp+arg_48]; struct Common::RegistryKey *
0x180105480  lea     r9, [rbp+var_10]; unsigned int
0x180105484  xor     r8d, r8d; wchar_t *
0x180105487  mov     [rbp+var_10], 0
0x18010548e  mov     rcx, r14; this
0x180105491  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105496  mov     ebx, eax
0x180105498  test    eax, eax
0x18010549a  jns     short loc_1801054C0
0x18010549c  mov     edx, 145h; void *
0x1801054a1  mov     rcx, [rbp+28h]; this
0x1801054a5  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801054ac  mov     r9d, eax; char *
0x1801054af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801054b4  mov     rcx, rdi; Block
0x1801054b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801054bc  mov     eax, ebx
0x1801054be  jmp     short loc_1801054FC
0x1801054c0  test    rdi, rdi
0x1801054c3  jz      short loc_1801054C8
0x1801054c5  mov     [rsi], rdi
0x1801054c8  mov     eax, dword ptr [rbp+Block]
0x1801054cb  xor     r15d, r15d
0x1801054ce  mov     [rsi+8], eax
0x1801054d1  mov     [rsi+0Ch], eax
0x1801054d4  mov     eax, [rbp+var_20]
0x1801054d7  mov     [rsi+10h], eax
0x1801054da  mov     eax, [rbp+var_1C]
0x1801054dd  mov     [rsi+14h], eax
0x1801054e0  mov     eax, [rbp+var_18]
0x1801054e3  mov     [rsi+18h], eax
0x1801054e6  mov     eax, [rbp+var_14]
0x1801054e9  mov     [rsi+1Ch], eax
0x1801054ec  mov     eax, [rbp+var_10]
0x1801054ef  mov     [rsi+20h], eax
0x1801054f2  xor     ecx, ecx; Block
0x1801054f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801054f9  mov     eax, r15d
0x1801054fc  lea     r11, [rsp+40h+var_s0]
0x180105501  mov     rbx, [r11+38h]
0x180105505  mov     rsi, [r11+40h]
0x180105509  mov     rsp, r11
0x18010550c  pop     r15
0x18010550e  pop     r14
0x180105510  pop     r12
0x180105512  pop     rdi
0x180105513  pop     rbp
0x180105514  retn
```
