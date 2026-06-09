# StaticFilterParameter::GetDictionaryFullPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013d40`
- end: `0x180014050`
- name: `?GetDictionaryFullPath@StaticFilterParameter@@UEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a450`
- `0x18000cde4`
- `0x18000cef4`
- `0x180013d40`
- `0x18001442c`
- `0x180015c0c`
- `0x18001600c`
- `0x180016124`
- `0x180021822`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180013db2`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180013db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013ee6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014022`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013ee6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014022`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StaticFilterParameter::GetDictionaryFullPath(_QWORD *a1, _QWORD *a2)
{
  _WORD *v4; // rcx
  UserHelpers::UserCache *Current; // rax
  const unsigned __int16 *v6; // r8
  int v7; // r14d
  volatile signed __int32 *v8; // rdi
  DWORD v10; // r9d
  const unsigned __int16 *v11; // r8
  int v12; // esi
  volatile signed __int32 *v13; // rdi
  __int64 v14; // r8
  volatile signed __int32 *v15; // rdi
  const unsigned __int16 *v16; // r8
  int v17; // ebx
  DWORD v18; // r9d
  const unsigned __int16 *v19; // r8
  __int64 v20; // rbx
  HKEY hKey; // [rsp+20h] [rbp-E0h] BYREF
  HKEY *v22; // [rsp+28h] [rbp-D8h]
  volatile signed __int32 *v23; // [rsp+30h] [rbp-D0h]
  unsigned __int16 Src[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( a2[3] < 8u )
    v4 = a2;
  else
    v4 = (_WORD *)*a2;
  a2[2] = 0;
  *v4 = 0;
  if ( !a1[16] )
  {
    std::wstring::assign(a2);
    return 0;
  }
  hKey = 0;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    Current = UserHelpers::UserCache::GetCurrent();
    UserHelpers::UserCache::GetHKCU(Current);
    if ( v22 && *v22 )
    {
      v6 = (const unsigned __int16 *)(a1 + 14);
      if ( a1[17] >= 8u )
        v6 = *(const unsigned __int16 **)v6;
      v7 = RegReader::Open((RegReader *)&hKey, *v22, v6);
      if ( v7 < 0 )
      {
        v8 = v23;
        if ( v23 )
        {
          if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
            if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
          }
        }
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)v7;
      }
      memset_0(Src, 0, 0x208u);
      v11 = (const unsigned __int16 *)(a1 + 18);
      if ( a1[21] >= 8u )
        v11 = *(const unsigned __int16 **)v11;
      v12 = RegReader::QueryStringValue(&hKey, (BYTE *)Src, v11, v10);
      if ( v12 < 0 )
      {
        v13 = v23;
        if ( v23 )
        {
          if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          }
        }
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)v12;
      }
      if ( Src[0] )
      {
        v14 = -1;
        do
          ++v14;
        while ( Src[v14] );
      }
      std::wstring::assign(a2, Src);
      RegReader::ExpandEnvironmentStringsFromRegValue(a2);
    }
    v15 = v23;
    if ( v23 )
    {
      if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
LABEL_51:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v16 = (const unsigned __int16 *)(a1 + 14);
  if ( a1[17] >= 8u )
    v16 = *(const unsigned __int16 **)v16;
  v17 = RegReader::Open((RegReader *)&hKey, HKEY_CURRENT_USER, v16);
  if ( v17 >= 0 )
  {
    memset_0(Src, 0, 0x208u);
    v19 = (const unsigned __int16 *)(a1 + 18);
    if ( a1[21] >= 8u )
      v19 = *(const unsigned __int16 **)v19;
    v17 = RegReader::QueryStringValue(&hKey, (BYTE *)Src, v19, v18);
    if ( v17 >= 0 )
    {
      if ( Src[0] )
      {
        v20 = -1;
        do
          ++v20;
        while ( Src[v20] );
      }
      std::wstring::assign(a2, Src);
      RegReader::ExpandEnvironmentStringsFromRegValue(a2);
      goto LABEL_51;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180013d40  mov     [rsp-8+arg_10], rbx
0x180013d45  push    rbp
0x180013d46  push    rsi
0x180013d47  push    rdi
0x180013d48  push    r14
0x180013d4a  push    r15
0x180013d4c  lea     rbp, [rsp-160h]
0x180013d54  sub     rsp, 260h
0x180013d5b  mov     rax, cs:__security_cookie
0x180013d62  xor     rax, rsp
0x180013d65  mov     [rbp+180h+var_30], rax
0x180013d6c  mov     rdi, rdx
0x180013d6f  mov     rsi, rcx
0x180013d72  xor     r15d, r15d
0x180013d75  cmp     qword ptr [rdx+18h], 8
0x180013d7a  jb      short loc_180013D81
0x180013d7c  mov     rcx, [rdx]
0x180013d7f  jmp     short loc_180013D84
0x180013d81  mov     rcx, rdi
0x180013d84  mov     [rdx+10h], r15
0x180013d88  mov     [rcx], r15w
0x180013d8c  cmp     [rsi+80h], r15
0x180013d93  jnz     short loc_180013DAD
0x180013d95  lea     rdx, [rsi+50h]
0x180013d99  or      r9, 0FFFFFFFFFFFFFFFFh
0x180013d9d  xor     r8d, r8d
0x180013da0  mov     rcx, rdi; void *
0x180013da3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180013da8  jmp     loc_180014028
0x180013dad  mov     [rsp+280h+hKey], r15
0x180013db2  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180013db8  test    al, al
0x180013dba  jz      loc_180013F6B
0x180013dc0  call    ?GetCurrent@UserCache@UserHelpers@@SAAEAV12@XZ; UserHelpers::UserCache::GetCurrent(void)
0x180013dc5  lea     rdx, [rsp+280h+var_258]
0x180013dca  mov     rcx, rax
0x180013dcd  call    ?GetHKCU@UserCache@UserHelpers@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; UserHelpers::UserCache::GetHKCU(void)
0x180013dd2  nop
0x180013dd3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013dd7  mov     rax, [rsp+280h+var_258]
0x180013ddc  test    rax, rax
0x180013ddf  jz      loc_180013F28
0x180013de5  mov     rdx, [rax]; HKEY
0x180013de8  test    rdx, rdx
0x180013deb  jz      loc_180013F28
0x180013df1  lea     r8, [rsi+70h]
0x180013df5  cmp     qword ptr [r8+18h], 8
0x180013dfa  jb      short loc_180013DFF
0x180013dfc  mov     r8, [r8]; unsigned __int16 *
0x180013dff  lea     rcx, [rsp+280h+hKey]; this
0x180013e04  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x180013e09  mov     r14d, eax
0x180013e0c  test    eax, eax
0x180013e0e  jns     short loc_180013E66
0x180013e10  mov     rdi, [rsp+280h+var_250]
0x180013e15  test    rdi, rdi
0x180013e18  jz      short loc_180013E4E
0x180013e1a  mov     ecx, ebx
0x180013e1c  lock xadd [rdi+8], ecx
0x180013e21  add     ecx, ebx
0x180013e23  jnz     short loc_180013E4E
0x180013e25  mov     rax, [rdi]
0x180013e28  mov     rcx, rdi
0x180013e2b  mov     rax, [rax]
0x180013e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e33  mov     eax, ebx
0x180013e35  lock xadd [rdi+0Ch], eax
0x180013e3a  add     eax, ebx
0x180013e3c  jnz     short loc_180013E4E
0x180013e3e  mov     rax, [rdi]
0x180013e41  mov     rcx, rdi
0x180013e44  mov     rax, [rax+8]
0x180013e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e4d  nop
0x180013e4e  mov     rcx, [rsp+280h+hKey]; hKey
0x180013e53  test    rcx, rcx
0x180013e56  jz      short loc_180013E5E
0x180013e58  call    cs:__imp_RegCloseKey
0x180013e5e  mov     eax, r14d
0x180013e61  jmp     loc_18001402A
0x180013e66  xor     edx, edx; Val
0x180013e68  mov     r8d, 208h; Size
0x180013e6e  lea     rcx, [rsp+280h+Src]; void *
0x180013e73  call    memset_0
0x180013e78  lea     r8, [rsi+90h]
0x180013e7f  cmp     qword ptr [r8+18h], 8
0x180013e84  jb      short loc_180013E89
0x180013e86  mov     r8, [r8]; unsigned __int16 *
0x180013e89  lea     rdx, [rsp+280h+Src]; unsigned __int16 *
0x180013e8e  lea     rcx, [rsp+280h+hKey]; this
0x180013e93  call    ?QueryStringValue@RegReader@@QEAAJPEAGPEBGK@Z; RegReader::QueryStringValue(ushort *,ushort const *,ulong)
0x180013e98  mov     esi, eax
0x180013e9a  test    eax, eax
0x180013e9c  jns     short loc_180013EF3
0x180013e9e  mov     rdi, [rsp+280h+var_250]
0x180013ea3  test    rdi, rdi
0x180013ea6  jz      short loc_180013EDC
0x180013ea8  mov     ecx, ebx
0x180013eaa  lock xadd [rdi+8], ecx
0x180013eaf  add     ecx, ebx
0x180013eb1  jnz     short loc_180013EDC
0x180013eb3  mov     rax, [rdi]
0x180013eb6  mov     rcx, rdi
0x180013eb9  mov     rax, [rax]
0x180013ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ec1  mov     eax, ebx
0x180013ec3  lock xadd [rdi+0Ch], eax
0x180013ec8  add     eax, ebx
0x180013eca  jnz     short loc_180013EDC
0x180013ecc  mov     rax, [rdi]
0x180013ecf  mov     rcx, rdi
0x180013ed2  mov     rax, [rax+8]
0x180013ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013edb  nop
0x180013edc  mov     rcx, [rsp+280h+hKey]; hKey
0x180013ee1  test    rcx, rcx
0x180013ee4  jz      short loc_180013EEC
0x180013ee6  call    cs:__imp_RegCloseKey
0x180013eec  mov     eax, esi
0x180013eee  jmp     loc_18001402A
0x180013ef3  cmp     [rsp+280h+Src], r15w
0x180013ef9  jnz     short loc_180013F00
0x180013efb  mov     r8, r15
0x180013efe  jmp     short loc_180013F12
0x180013f00  lea     rax, [rsp+280h+Src]
0x180013f05  mov     r8, rbx
0x180013f08  inc     r8
0x180013f0b  cmp     [rax+r8*2], r15w
0x180013f10  jnz     short loc_180013F08
0x180013f12  lea     rdx, [rsp+280h+Src]; Src
0x180013f17  mov     rcx, rdi; void *
0x180013f1a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180013f1f  mov     rcx, rdi; void *
0x180013f22  call    ?ExpandEnvironmentStringsFromRegValue@RegReader@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReader::ExpandEnvironmentStringsFromRegValue(std::wstring &)
0x180013f27  nop
0x180013f28  mov     rdi, [rsp+280h+var_250]
0x180013f2d  test    rdi, rdi
0x180013f30  jz      short loc_180013F66
0x180013f32  mov     eax, ebx
0x180013f34  lock xadd [rdi+8], eax
0x180013f39  add     eax, ebx
0x180013f3b  jnz     short loc_180013F66
0x180013f3d  mov     rax, [rdi]
0x180013f40  mov     rcx, rdi
0x180013f43  mov     rax, [rax]
0x180013f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f4b  mov     eax, ebx
0x180013f4d  lock xadd [rdi+0Ch], eax
0x180013f52  add     eax, ebx
0x180013f54  jnz     short loc_180013F66
0x180013f56  mov     rax, [rdi]
0x180013f59  mov     rcx, rdi
0x180013f5c  mov     rax, [rax+8]
0x180013f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f65  nop
0x180013f66  jmp     loc_180014018
0x180013f6b  lea     r8, [rsi+70h]
0x180013f6f  cmp     qword ptr [r8+18h], 8
0x180013f74  jb      short loc_180013F79
0x180013f76  mov     r8, [r8]; unsigned __int16 *
0x180013f79  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x180013f80  lea     rcx, [rsp+280h+hKey]; this
0x180013f85  call    ?Open@RegReader@@QEAAJPEAUHKEY__@@PEBG@Z; RegReader::Open(HKEY__ *,ushort const *)
0x180013f8a  mov     ebx, eax
0x180013f8c  test    eax, eax
0x180013f8e  jns     short loc_180013FA7
0x180013f90  mov     rcx, [rsp+280h+hKey]; hKey
0x180013f95  test    rcx, rcx
0x180013f98  jz      short loc_180013FA0
0x180013f9a  call    cs:__imp_RegCloseKey
0x180013fa0  mov     eax, ebx
0x180013fa2  jmp     loc_18001402A
0x180013fa7  xor     edx, edx; Val
0x180013fa9  mov     r8d, 208h; Size
0x180013faf  lea     rcx, [rsp+280h+Src]; void *
0x180013fb4  call    memset_0
0x180013fb9  lea     r8, [rsi+90h]
0x180013fc0  cmp     qword ptr [r8+18h], 8
0x180013fc5  jb      short loc_180013FCA
0x180013fc7  mov     r8, [r8]; unsigned __int16 *
0x180013fca  lea     rdx, [rsp+280h+Src]; unsigned __int16 *
0x180013fcf  lea     rcx, [rsp+280h+hKey]; this
0x180013fd4  call    ?QueryStringValue@RegReader@@QEAAJPEAGPEBGK@Z; RegReader::QueryStringValue(ushort *,ushort const *,ulong)
0x180013fd9  mov     ebx, eax
0x180013fdb  test    eax, eax
0x180013fdd  js      short loc_180013F90
0x180013fdf  cmp     [rsp+280h+Src], r15w
0x180013fe5  jnz     short loc_180013FEC
0x180013fe7  mov     rbx, r15
0x180013fea  jmp     short loc_180013FFF
0x180013fec  lea     rax, [rsp+280h+Src]
0x180013ff1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013ff5  inc     rbx
0x180013ff8  cmp     [rax+rbx*2], r15w
0x180013ffd  jnz     short loc_180013FF5
0x180013fff  mov     r8, rbx
0x180014002  lea     rdx, [rsp+280h+Src]; Src
0x180014007  mov     rcx, rdi; void *
0x18001400a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001400f  mov     rcx, rdi; void *
0x180014012  call    ?ExpandEnvironmentStringsFromRegValue@RegReader@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReader::ExpandEnvironmentStringsFromRegValue(std::wstring &)
0x180014017  nop
0x180014018  mov     rcx, [rsp+280h+hKey]; hKey
0x18001401d  test    rcx, rcx
0x180014020  jz      short loc_180014028
0x180014022  call    cs:__imp_RegCloseKey
0x180014028  xor     eax, eax
0x18001402a  mov     rcx, [rbp+180h+var_30]
0x180014031  xor     rcx, rsp; StackCookie
0x180014034  call    __security_check_cookie
0x180014039  mov     rbx, [rsp+280h+arg_10]
0x180014041  add     rsp, 260h
0x180014048  pop     r15
0x18001404a  pop     r14
0x18001404c  pop     rdi
0x18001404d  pop     rsi
0x18001404e  pop     rbp
0x18001404f  retn
```
