# StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180023ccc`
- end: `0x180023f39`
- name: `?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEBG11111111@Z`
- size: `621`
- prototype: `int(StateRepository::Globals::PartitionSettings *__hidden this, struct Common::RegistryKey *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002473c`
- `0x180024870`
- `0x1800249a4`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x1800232c8`
- `0x18002393c`
- `0x180023ac4`
- `0x180023ccc`

## string_xrefs

- `0x180023d25`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023d56`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180023ec9`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::Load(
        StateRepository::Globals::PartitionSettings *this,
        struct Common::RegistryKey *a2,
        unsigned __int16 *a3,
        struct Common::RegistryKey *a4,
        struct Common::RegistryKey *a5,
        struct Common::RegistryKey *a6,
        struct Common::RegistryKey *a7,
        struct Common::RegistryKey *a8,
        struct Common::RegistryKey *a9,
        struct Common::RegistryKey *a10,
        unsigned __int16 *a11)
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
  unsigned int *v25; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v26; // [rsp+28h] [rbp-18h] BYREF
  unsigned int v27; // [rsp+2Ch] [rbp-14h] BYREF
  unsigned int v28[4]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *Block; // [rsp+70h] [rbp+30h] BYREF

  v11 = 0;
  if ( *(_QWORD *)this )
    goto LABEL_11;
  Block = 0;
  Setting = StateRepository::Globals::GetSetting(a2, a3, a11);
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
        (int)v25);
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
    v20 = StateRepository::Globals::GetSetting(a2, a4, (const unsigned __int16 *)0x20000, (unsigned int)&Block, v25);
    v21 = v20;
    if ( v20 >= 0 )
    {
      v20 = StateRepository::Globals::GetSetting(a2, a5, (const unsigned __int16 *)0x20000, (unsigned int)v28, v25);
      v21 = v20;
      if ( v20 >= 0 )
      {
        LODWORD(v25) = 0;
        v20 = StateRepository::Globals::GetSetting(a2, a6, (const unsigned __int16 *)0x100000, (unsigned int)&v25, v25);
        v21 = v20;
        if ( v20 >= 0 )
        {
          v20 = StateRepository::Globals::GetSetting(
                  a2,
                  a7,
                  0,
                  (unsigned int)&v25 + 4,
                  (unsigned int *)(unsigned int)v25);
          v21 = v20;
          if ( v20 >= 0 )
          {
            v26 = 0;
            v20 = StateRepository::Globals::GetSetting(a2, a8, 0, (unsigned int)&v26, v25);
            v21 = v20;
            if ( v20 >= 0 )
            {
              v27 = 0;
              v20 = StateRepository::Globals::GetSetting(a2, a9, 0, (unsigned int)&v27, v25);
              v21 = v20;
              if ( v20 >= 0 )
              {
                v28[0] = 0;
                v20 = StateRepository::Globals::GetSetting(a2, a10, 0, (unsigned int)v28, v25);
                v21 = v20;
                if ( v20 >= 0 )
                {
                  if ( v11 )
                    *(_QWORD *)this = v11;
                  v24 = (int)Block;
                  v17 = 0;
                  *((_DWORD *)this + 2) = (_DWORD)Block;
                  *((_DWORD *)this + 3) = v24;
                  *((_QWORD *)this + 2) = v25;
                  *((_DWORD *)this + 6) = v26;
                  *((_DWORD *)this + 7) = v27;
                  *((_DWORD *)this + 8) = v28[0];
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
      (int)v25);
    operator delete(v11);
    return v21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12C,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)(unsigned int)Setting,
    (int)v25);
LABEL_6:
  operator delete(v16);
LABEL_29:
  operator delete(0);
  return v17;
}

```

## disassembly

```asm
0x180023ccc  mov     [rsp-28h+arg_8], rbx
0x180023cd1  mov     [rsp-28h+arg_10], rsi
0x180023cd6  push    rbp
0x180023cd7  push    rdi
0x180023cd8  push    r12
0x180023cda  push    r14
0x180023cdc  push    r15
0x180023cde  mov     rbp, rsp
0x180023ce1  sub     rsp, 40h
0x180023ce5  xor     edi, edi
0x180023ce7  mov     r12, r9
0x180023cea  mov     rax, r8
0x180023ced  mov     r14, rdx
0x180023cf0  mov     rsi, rcx
0x180023cf3  cmp     [rcx], rdi
0x180023cf6  jnz     loc_180023DAC
0x180023cfc  mov     r8, [rbp+arg_50]; unsigned __int16 *
0x180023d03  lea     r9, [rbp+Block]
0x180023d07  mov     rdx, rax; unsigned __int16 *
0x180023d0a  mov     [rbp+Block], rdi
0x180023d0e  mov     rcx, r14; this
0x180023d11  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG1AEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@4@@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x180023d16  mov     rbx, [rbp+Block]
0x180023d1a  mov     r15d, eax
0x180023d1d  test    eax, eax
0x180023d1f  jns     short loc_180023D3B
0x180023d21  mov     rcx, [rbp+28h]; this
0x180023d25  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023d2c  mov     r9d, eax; char *
0x180023d2f  mov     edx, 12Ch; void *
0x180023d34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d39  jmp     short loc_180023D73
0x180023d3b  lea     rdx, [rbp+Block]
0x180023d3f  mov     [rbp+Block], rdi
0x180023d43  mov     rcx, rbx
0x180023d46  call    ?ExpandMacros@Globals@StateRepository@@YAJPEBGAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; StateRepository::Globals::ExpandMacros(ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x180023d4b  mov     r15d, eax
0x180023d4e  test    eax, eax
0x180023d50  jns     short loc_180023D80
0x180023d52  mov     rcx, [rbp+28h]; this
0x180023d56  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023d5d  mov     r9d, eax; char *
0x180023d60  mov     edx, 12Eh; void *
0x180023d65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d6a  mov     rcx, [rbp+Block]; Block
0x180023d6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023d73  mov     rcx, rbx; Block
0x180023d76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023d7b  jmp     loc_180023F16
0x180023d80  mov     r15, [rbp+Block]
0x180023d84  test    r15, r15
0x180023d87  jnz     short loc_180023D93
0x180023d89  mov     r15, rbx
0x180023d8c  xor     ebx, ebx
0x180023d8e  test    r15, r15
0x180023d91  jz      short loc_180023D9D
0x180023d93  xor     ecx, ecx; Block
0x180023d95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023d9a  mov     rdi, r15
0x180023d9d  xor     ecx, ecx; Block
0x180023d9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023da4  mov     rcx, rbx; Block
0x180023da7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023dac  mov     r15d, 20000h
0x180023db2  mov     dword ptr [rbp+Block], 0
0x180023db9  mov     r8d, r15d; unsigned __int16 *
0x180023dbc  lea     r9, [rbp+Block]; unsigned int
0x180023dc0  mov     rdx, r12; struct Common::RegistryKey *
0x180023dc3  mov     rcx, r14; this
0x180023dc6  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180023dcb  mov     ebx, eax
0x180023dcd  test    eax, eax
0x180023dcf  jns     short loc_180023DDB
0x180023dd1  mov     edx, 133h
0x180023dd6  jmp     loc_180023EC5
0x180023ddb  mov     rdx, [rbp+arg_20]; struct Common::RegistryKey *
0x180023ddf  lea     r9, [rbp+var_10]; unsigned int
0x180023de3  mov     r8d, r15d; unsigned __int16 *
0x180023de6  mov     rcx, r14; this
0x180023de9  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180023dee  mov     ebx, eax
0x180023df0  test    eax, eax
0x180023df2  jns     short loc_180023DFE
0x180023df4  mov     edx, 136h
0x180023df9  jmp     loc_180023EC5
0x180023dfe  mov     rdx, [rbp+arg_28]; struct Common::RegistryKey *
0x180023e02  lea     r9, [rbp+var_20]; unsigned int
0x180023e06  mov     r8d, 100000h; unsigned __int16 *
0x180023e0c  mov     [rbp+var_20], 0
0x180023e13  mov     rcx, r14; this
0x180023e16  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180023e1b  mov     ebx, eax
0x180023e1d  test    eax, eax
0x180023e1f  jns     short loc_180023E2B
0x180023e21  mov     edx, 139h
0x180023e26  jmp     loc_180023EC5
0x180023e2b  mov     rdx, [rbp+arg_30]; struct Common::RegistryKey *
0x180023e2f  lea     r9, [rbp+var_1C]; unsigned int
0x180023e33  xor     r8d, r8d; unsigned __int16 *
0x180023e36  mov     [rbp+var_1C], 0
0x180023e3d  mov     rcx, r14; this
0x180023e40  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180023e45  mov     ebx, eax
0x180023e47  test    eax, eax
0x180023e49  jns     short loc_180023E52
0x180023e4b  mov     edx, 13Ch
0x180023e50  jmp     short loc_180023EC5
0x180023e52  mov     rdx, [rbp+arg_38]; struct Common::RegistryKey *
0x180023e56  lea     r9, [rbp+var_18]; unsigned int
0x180023e5a  xor     r8d, r8d; unsigned __int16 *
0x180023e5d  mov     [rbp+var_18], 0
0x180023e64  mov     rcx, r14; this
0x180023e67  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180023e6c  mov     ebx, eax
0x180023e6e  test    eax, eax
0x180023e70  jns     short loc_180023E79
0x180023e72  mov     edx, 13Fh
0x180023e77  jmp     short loc_180023EC5
0x180023e79  mov     rdx, [rbp+arg_40]; struct Common::RegistryKey *
0x180023e7d  lea     r9, [rbp+var_14]; unsigned int
0x180023e81  xor     r8d, r8d; unsigned __int16 *
0x180023e84  mov     [rbp+var_14], 0
0x180023e8b  mov     rcx, r14; this
0x180023e8e  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180023e93  mov     ebx, eax
0x180023e95  test    eax, eax
0x180023e97  jns     short loc_180023EA0
0x180023e99  mov     edx, 142h
0x180023e9e  jmp     short loc_180023EC5
0x180023ea0  mov     rdx, [rbp+arg_48]; struct Common::RegistryKey *
0x180023ea4  lea     r9, [rbp+var_10]; unsigned int
0x180023ea8  xor     r8d, r8d; unsigned __int16 *
0x180023eab  mov     [rbp+var_10], 0
0x180023eb2  mov     rcx, r14; this
0x180023eb5  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180023eba  mov     ebx, eax
0x180023ebc  test    eax, eax
0x180023ebe  jns     short loc_180023EE4
0x180023ec0  mov     edx, 145h; void *
0x180023ec5  mov     rcx, [rbp+28h]; this
0x180023ec9  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023ed0  mov     r9d, eax; char *
0x180023ed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ed8  mov     rcx, rdi; Block
0x180023edb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023ee0  mov     eax, ebx
0x180023ee2  jmp     short loc_180023F20
0x180023ee4  test    rdi, rdi
0x180023ee7  jz      short loc_180023EEC
0x180023ee9  mov     [rsi], rdi
0x180023eec  mov     eax, dword ptr [rbp+Block]
0x180023eef  xor     r15d, r15d
0x180023ef2  mov     [rsi+8], eax
0x180023ef5  mov     [rsi+0Ch], eax
0x180023ef8  mov     eax, [rbp+var_20]
0x180023efb  mov     [rsi+10h], eax
0x180023efe  mov     eax, [rbp+var_1C]
0x180023f01  mov     [rsi+14h], eax
0x180023f04  mov     eax, [rbp+var_18]
0x180023f07  mov     [rsi+18h], eax
0x180023f0a  mov     eax, [rbp+var_14]
0x180023f0d  mov     [rsi+1Ch], eax
0x180023f10  mov     eax, [rbp+var_10]
0x180023f13  mov     [rsi+20h], eax
0x180023f16  xor     ecx, ecx; Block
0x180023f18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023f1d  mov     eax, r15d
0x180023f20  lea     r11, [rsp+40h+var_s0]
0x180023f25  mov     rbx, [r11+38h]
0x180023f29  mov     rsi, [r11+40h]
0x180023f2d  mov     rsp, r11
0x180023f30  pop     r15
0x180023f32  pop     r14
0x180023f34  pop     r12
0x180023f36  pop     rdi
0x180023f37  pop     rbp
0x180023f38  retn
```
