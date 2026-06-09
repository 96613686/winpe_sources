# APPLICATION_CUSTOM_PROVIDER::UpgradeToVDir(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18001b158`
- end: `0x18001b4f3`
- name: `?UpgradeToVDir@APPLICATION_CUSTOM_PROVIDER@@AEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `923`
- prototype: `int(APPLICATION_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18001ad10`

## callees

- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x1800047b0`
- `0x180006e28`
- `0x18000a4e8`
- `0x18001a36c`
- `0x18001b158`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001b2a7`
- `msvcrt!_wcsnicmp` at `0x18001b2a7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b245`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b269`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b2e8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b245`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b269`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b2e8`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18001b355`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18001b355`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b27e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b2c0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b315`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b333`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b347`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b27e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b2c0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b315`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b333`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001b347`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001b1b1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001b1d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001b202`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001b1b1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001b1d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001b202`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4af`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4b9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4af`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4b9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4c4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b237`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b25c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b28a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b298`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b2cc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b325`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b3b5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b237`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b25c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b28a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b298`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b2cc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b325`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001b3b5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001b300`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001b300`

## string_xrefs

- `0x18001b384`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall APPLICATION_CUSTOM_PROVIDER::UpgradeToVDir(
        APPLICATION_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  const unsigned __int16 *Str; // rax
  int v7; // ebx
  const unsigned __int16 *v8; // rax
  unsigned int CCH; // edi
  const wchar_t *v10; // rbx
  const wchar_t *v11; // rax
  __int64 v12; // rbx
  const unsigned __int16 *v13; // rdi
  unsigned __int16 *v14; // rbx
  unsigned int v15; // eax
  __int64 (__fastcall *v16)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *v17; // rax
  VDIR_CUSTOM_PROVIDER *v18; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v19; // rax
  CUSTOM_PROPERTY_PROVIDER *v20; // rdi
  struct INativeConfigurationElement *v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v26[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v27[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v28[256]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v29[256]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v25, v27, 0x100u);
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v26, v28, 0x100u);
  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v24, v29, 0x100u);
  v22 = 0;
  v23 = 0;
  if ( a2 && a3 )
  {
    Str = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 256LL));
    v7 = STRU::Copy((STRU *)v25, Str);
    if ( v7 >= 0 )
    {
      v8 = STRU::QueryStr((struct ABO_NODE *)((char *)a3 + 256));
      v7 = STRU::Copy((STRU *)v26, v8);
      if ( v7 >= 0 )
      {
        CCH = STRU::QueryCCH((STRU *)v25);
        v10 = STRU::QueryStr((STRU *)v26);
        v11 = STRU::QueryStr((STRU *)v25);
        if ( _wcsnicmp(v11, v10, CCH) )
        {
          v7 = -2147024846;
        }
        else
        {
          v12 = STRU::QueryCCH((STRU *)v25);
          v13 = &STRU::QueryStr((STRU *)v26)[v12];
          if ( *v13 == 47 || (v7 = STRU::Copy((STRU *)v24, L"/"), v7 >= 0) )
          {
            v7 = STRU::Append((STRU *)v24, v13);
            if ( v7 >= 0 )
            {
              if ( STRU::QueryCCH((STRU *)v24) > 1 )
              {
                v14 = STRU::QueryStr((STRU *)v24);
                if ( v14[STRU::QueryCCH((STRU *)v24) - 1] == 47 )
                {
                  v15 = STRU::QueryCCH((STRU *)v24);
                  STRU::SetLen((STRU *)v24, v15 - 1);
                }
              }
              v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 40LL))(
                     *((_QWORD *)this + 3),
                     &v23);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v23 + 48LL))(
                       v23,
                       L"virtualDirectory",
                       &v22);
                if ( v7 >= 0 )
                {
                  v16 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v22 + 128LL);
                  v17 = STRU::QueryStr((STRU *)v24);
                  v7 = v16(v22, L"path", v17, 0);
                  if ( v7 >= 0 )
                  {
                    v7 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v23 + 56LL))(
                           v23,
                           v22,
                           0xFFFFFFFFLL,
                           0);
                    if ( v7 >= 0 )
                    {
                      v18 = (VDIR_CUSTOM_PROVIDER *)operator new(0x60u);
                      if ( v18
                        && (v19 = VDIR_CUSTOM_PROVIDER::VDIR_CUSTOM_PROVIDER(
                                    v18,
                                    a3,
                                    v22,
                                    *((struct INativeConfigurationElement **)this + 3)),
                            (v20 = v19) != 0) )
                      {
                        v7 = ABO_NODE::AddProvider(a3, v19);
                        if ( v7 >= 0 )
                        {
                          v7 = ABO_NODE::MapNodeAndChildren(a3);
                          if ( v7 >= 0 )
                            *((_DWORD *)a3 + 56) = 1;
                        }
                        CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v20);
                      }
                      else
                      {
                        v7 = -2147024888;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  STRU::~STRU((STRU *)v24);
  STRU::~STRU((STRU *)v26);
  STRU::~STRU((STRU *)v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b158  mov     [rsp-8+arg_8], rbx
0x18001b15d  mov     [rsp-8+arg_18], rsi
0x18001b162  push    rbp
0x18001b163  push    rdi
0x18001b164  push    r14
0x18001b166  lea     rbp, [rsp-600h]
0x18001b16e  sub     rsp, 700h
0x18001b175  mov     rax, cs:__security_cookie
0x18001b17c  xor     rax, rsp
0x18001b17f  mov     [rbp+610h+var_20], rax
0x18001b186  mov     rsi, r8
0x18001b189  mov     rbx, rdx
0x18001b18c  mov     r14, rcx
0x18001b18f  mov     edi, 200h
0x18001b194  mov     r8d, edi; Size
0x18001b197  lea     rcx, [rbp+610h+var_620]; void *
0x18001b19b  xor     edx, edx; Val
0x18001b19d  call    memset_0
0x18001b1a2  mov     r8d, 100h
0x18001b1a8  lea     rdx, [rbp+610h+var_620]
0x18001b1ac  lea     rcx, [rsp+710h+var_698]
0x18001b1b1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001b1b7  mov     r8d, edi; Size
0x18001b1ba  lea     rcx, [rbp+610h+var_420]; void *
0x18001b1c1  xor     edx, edx; Val
0x18001b1c3  call    memset_0
0x18001b1c8  mov     r8d, 100h
0x18001b1ce  lea     rdx, [rbp+610h+var_420]
0x18001b1d5  lea     rcx, [rbp+610h+var_660]
0x18001b1d9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001b1df  mov     r8d, edi; Size
0x18001b1e2  lea     rcx, [rbp+610h+var_220]; void *
0x18001b1e9  xor     edx, edx; Val
0x18001b1eb  call    memset_0
0x18001b1f0  mov     r8d, 100h
0x18001b1f6  lea     rdx, [rbp+610h+var_220]
0x18001b1fd  lea     rcx, [rsp+710h+var_6D0]
0x18001b202  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001b208  mov     [rsp+710h+var_6E0], 0
0x18001b211  mov     [rsp+710h+var_6D8], 0
0x18001b21a  test    rbx, rbx
0x18001b21d  jz      loc_18001B467
0x18001b223  test    rsi, rsi
0x18001b226  jz      loc_18001B467
0x18001b22c  mov     rcx, [r14+10h]
0x18001b230  add     rcx, 100h
0x18001b237  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b23d  mov     rdx, rax
0x18001b240  lea     rcx, [rsp+710h+var_698]
0x18001b245  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b24b  mov     ebx, eax
0x18001b24d  test    eax, eax
0x18001b24f  js      loc_18001B46C
0x18001b255  lea     rcx, [rsi+100h]
0x18001b25c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b262  mov     rdx, rax
0x18001b265  lea     rcx, [rbp+610h+var_660]
0x18001b269  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b26f  mov     ebx, eax
0x18001b271  test    eax, eax
0x18001b273  js      loc_18001B46C
0x18001b279  lea     rcx, [rsp+710h+var_698]
0x18001b27e  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001b284  lea     rcx, [rbp+610h+var_660]
0x18001b288  mov     edi, eax
0x18001b28a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b290  lea     rcx, [rsp+710h+var_698]
0x18001b295  mov     rbx, rax
0x18001b298  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b29e  mov     r8d, edi; MaxCount
0x18001b2a1  mov     rdx, rbx; String2
0x18001b2a4  mov     rcx, rax; String1
0x18001b2a7  call    cs:__imp__wcsnicmp
0x18001b2ad  test    eax, eax
0x18001b2af  jz      short loc_18001B2BB
0x18001b2b1  mov     ebx, 80070032h
0x18001b2b6  jmp     loc_18001B46C
0x18001b2bb  lea     rcx, [rsp+710h+var_698]
0x18001b2c0  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001b2c6  lea     rcx, [rbp+610h+var_660]
0x18001b2ca  mov     ebx, eax
0x18001b2cc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b2d2  lea     rdi, [rax+rbx*2]
0x18001b2d6  cmp     word ptr [rdi], 2Fh ; '/'
0x18001b2da  jz      short loc_18001B2F8
0x18001b2dc  lea     rdx, asc_18002E8E8; "/"
0x18001b2e3  lea     rcx, [rsp+710h+var_6D0]
0x18001b2e8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b2ee  mov     ebx, eax
0x18001b2f0  test    eax, eax
0x18001b2f2  js      loc_18001B46C
0x18001b2f8  mov     rdx, rdi
0x18001b2fb  lea     rcx, [rsp+710h+var_6D0]
0x18001b300  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001b306  mov     ebx, eax
0x18001b308  test    eax, eax
0x18001b30a  js      loc_18001B46C
0x18001b310  lea     rcx, [rsp+710h+var_6D0]
0x18001b315  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001b31b  cmp     eax, 1
0x18001b31e  jbe     short loc_18001B35B
0x18001b320  lea     rcx, [rsp+710h+var_6D0]
0x18001b325  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b32b  lea     rcx, [rsp+710h+var_6D0]
0x18001b330  mov     rbx, rax
0x18001b333  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001b339  dec     eax
0x18001b33b  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x18001b340  jnz     short loc_18001B35B
0x18001b342  lea     rcx, [rsp+710h+var_6D0]
0x18001b347  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001b34d  lea     rcx, [rsp+710h+var_6D0]
0x18001b352  lea     edx, [rax-1]
0x18001b355  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001b35b  mov     rcx, [r14+18h]
0x18001b35f  lea     rdx, [rsp+710h+var_6D8]
0x18001b364  mov     rax, [rcx]
0x18001b367  mov     rax, [rax+28h]
0x18001b36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b370  mov     ebx, eax
0x18001b372  test    eax, eax
0x18001b374  js      loc_18001B46C
0x18001b37a  mov     rcx, [rsp+710h+var_6D8]
0x18001b37f  lea     r8, [rsp+710h+var_6E0]
0x18001b384  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x18001b38b  mov     rax, [rcx]
0x18001b38e  mov     rax, [rax+30h]
0x18001b392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b397  mov     ebx, eax
0x18001b399  test    eax, eax
0x18001b39b  js      loc_18001B46C
0x18001b3a1  mov     rax, [rsp+710h+var_6E0]
0x18001b3a6  mov     rcx, [rax]
0x18001b3a9  mov     rbx, [rcx+80h]
0x18001b3b0  lea     rcx, [rsp+710h+var_6D0]
0x18001b3b5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001b3bb  mov     rcx, [rsp+710h+var_6E0]
0x18001b3c0  lea     rdx, aPath; "path"
0x18001b3c7  mov     r8, rax
0x18001b3ca  xor     r9d, r9d
0x18001b3cd  mov     rax, rbx
0x18001b3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d5  mov     ebx, eax
0x18001b3d7  test    eax, eax
0x18001b3d9  js      loc_18001B46C
0x18001b3df  mov     rcx, [rsp+710h+var_6D8]
0x18001b3e4  xor     r9d, r9d
0x18001b3e7  mov     rdx, [rsp+710h+var_6E0]
0x18001b3ec  or      r8d, 0FFFFFFFFh
0x18001b3f0  mov     rax, [rcx]
0x18001b3f3  mov     rax, [rax+38h]
0x18001b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3fc  mov     ebx, eax
0x18001b3fe  test    eax, eax
0x18001b400  js      short loc_18001B46C
0x18001b402  mov     ecx, 60h ; '`'; Size
0x18001b407  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b40c  test    rax, rax
0x18001b40f  jz      short loc_18001B460
0x18001b411  mov     r9, [r14+18h]; struct INativeConfigurationElement *
0x18001b415  mov     rdx, rsi; struct ABO_NODE *
0x18001b418  mov     r8, [rsp+710h+var_6E0]; struct INativeConfigurationElement *
0x18001b41d  mov     rcx, rax; this
0x18001b420  call    ??0VDIR_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; VDIR_CUSTOM_PROVIDER::VDIR_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x18001b425  mov     rdi, rax
0x18001b428  test    rax, rax
0x18001b42b  jz      short loc_18001B460
0x18001b42d  mov     rdx, rax; struct CUSTOM_PROPERTY_PROVIDER *
0x18001b430  mov     rcx, rsi; this
0x18001b433  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x18001b438  mov     ebx, eax
0x18001b43a  test    eax, eax
0x18001b43c  js      short loc_18001B456
0x18001b43e  mov     rcx, rsi; this
0x18001b441  call    ?MapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::MapNodeAndChildren(void)
0x18001b446  mov     ebx, eax
0x18001b448  test    eax, eax
0x18001b44a  js      short loc_18001B456
0x18001b44c  mov     dword ptr [rsi+0E0h], 1
0x18001b456  mov     rcx, rdi; this
0x18001b459  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x18001b45e  jmp     short loc_18001B46C
0x18001b460  mov     ebx, 80070008h
0x18001b465  jmp     short loc_18001B46C
0x18001b467  mov     ebx, 80070057h
0x18001b46c  mov     rcx, [rsp+710h+var_6E0]
0x18001b471  test    rcx, rcx
0x18001b474  jz      short loc_18001B48B
0x18001b476  mov     rax, [rcx]
0x18001b479  mov     rax, [rax+10h]
0x18001b47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b482  mov     [rsp+710h+var_6E0], 0
0x18001b48b  mov     rcx, [rsp+710h+var_6D8]
0x18001b490  test    rcx, rcx
0x18001b493  jz      short loc_18001B4AA
0x18001b495  mov     rax, [rcx]
0x18001b498  mov     rax, [rax+10h]
0x18001b49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a1  mov     [rsp+710h+var_6D8], 0
0x18001b4aa  lea     rcx, [rsp+710h+var_6D0]
0x18001b4af  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001b4b5  lea     rcx, [rbp+610h+var_660]
0x18001b4b9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001b4bf  lea     rcx, [rsp+710h+var_698]
0x18001b4c4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001b4ca  mov     eax, ebx
0x18001b4cc  mov     rcx, [rbp+610h+var_20]
0x18001b4d3  xor     rcx, rsp; StackCookie
0x18001b4d6  call    __security_check_cookie
0x18001b4db  lea     r11, [rsp+710h+var_10]
0x18001b4e3  mov     rbx, [r11+28h]
0x18001b4e7  mov     rsi, [r11+38h]
0x18001b4eb  mov     rsp, r11
0x18001b4ee  pop     r14
0x18001b4f0  pop     rdi
0x18001b4f1  pop     rbp
0x18001b4f2  retn
```
