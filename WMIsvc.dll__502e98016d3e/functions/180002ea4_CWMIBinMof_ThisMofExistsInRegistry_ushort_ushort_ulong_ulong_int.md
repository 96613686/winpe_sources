# CWMIBinMof::ThisMofExistsInRegistry(ushort *,ushort *,ulong,ulong,int)

- ea: `0x180002ea4`
- end: `0x1800031d6`
- name: `?ThisMofExistsInRegistry@CWMIBinMof@@QEAAHPEAG0KKH@Z`
- size: `818`
- prototype: `int(CWMIBinMof *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002478`
- `0x180017e3c`

## callees

- `0x180002ea4`
- `0x180003494`
- `0x1800034f0`
- `0x18000354c`
- `0x18000366c`
- `0x180003958`
- `0x1800039c4`
- `0x1800039f4`
- `0x180003b08`
- `0x180010100`
- `0x18001d034`
- `0x18001d377`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f17`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180002fa4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180002fa4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000312d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003140`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800031b7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000312d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003140`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800031b7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003013`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000305c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003013`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000305c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWMIBinMof::ThisMofExistsInRegistry(
        CWMIBinMof *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  unsigned int v9; // r12d
  __int64 v10; // r14
  unsigned int CurrentKeyValue; // eax
  int *v12; // rbx
  unsigned int v13; // edi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  unsigned int v16; // r15d
  wchar_t *v17; // rax
  wchar_t *v18; // rdi
  wchar_t **v19; // r8
  __int64 v20; // rcx
  int *v21; // rdx
  wchar_t *v22; // rax
  wchar_t *v23; // rcx
  wchar_t *v24; // rax
  int *v26; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+60h] [rbp-A0h] BYREF
  int *v29; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v30; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  char v34[14]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Class[261]; // [rsp+A6h] [rbp-5Ah] BYREF
  DWORD cchClass; // [rsp+2B0h] [rbp+1B0h] BYREF
  DWORD cSubKeys; // [rsp+2B4h] [rbp+1B4h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+2B8h] [rbp+1B8h] BYREF
  DWORD cbMaxClassLen; // [rsp+2BCh] [rbp+1BCh] BYREF
  DWORD cValues; // [rsp+2C0h] [rbp+1C0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+2C4h] [rbp+1C4h] BYREF
  DWORD cbMaxValueLen; // [rsp+2C8h] [rbp+1C8h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+2CCh] [rbp+1CCh] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+2D0h] [rbp+1D0h] BYREF

  v9 = 0;
  CRegistry::CRegistry((CRegistry *)&v32);
  if ( hKey )
    CRegistry::PrepareToReOpen((CRegistry *)&v32);
  v32 = -2147483646;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey) )
  {
    v10 = 260;
    cchClass = 260;
    RegQueryInfoKeyW(
      hKey,
      Class,
      &cchClass,
      0,
      &cSubKeys,
      &cbMaxSubKeyLen,
      &cbMaxClassLen,
      &cValues,
      &cbMaxValueNameLen,
      &cbMaxValueLen,
      &cbSecurityDescriptor,
      &ftLastWriteTime);
    CHString::operator=((CHString *)v34, a2);
    v29 = &dword_1800323BC;
    CurrentKeyValue = CRegistry::GetCurrentKeyValue((CRegistry *)&v32, hKey, a3, (struct CHString *)&v29);
    v12 = v29;
    if ( !CurrentKeyValue )
    {
      if ( a6 )
      {
        SafeInt<unsigned int>::MixedSizeAddition<int>(&Size, 260);
        v13 = Size;
        v14 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)Size, 2u));
        v15 = v14;
        v31 = v14;
        if ( v14 )
          memset_0(v14, 0, v13);
        SafeInt<unsigned int>::MixedSizeAddition<int>(&Size, 260);
        v16 = Size;
        v17 = (wchar_t *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)Size, 2u));
        v18 = v17;
        v30 = v17;
        if ( v17 )
          memset_0(v17, 0, v16);
        if ( v15 )
        {
          if ( v18 )
          {
            LODWORD(phkResult) = a5;
            if ( (int)StringCchPrintfW(v15, 0x104u, L"LowDateTime:%ld,HighDateTime:%ld", a4, phkResult) >= 0 )
            {
              v20 = 2147483646;
              v21 = v12;
              v22 = v18;
              do
              {
                if ( !v20 )
                  break;
                v19 = (wchar_t **)*(unsigned __int16 *)v21;
                if ( !(_WORD)v19 )
                  break;
                v21 = (int *)((char *)v21 + 2);
                *v22++ = (unsigned __int16)v19;
                --v20;
                --v10;
              }
              while ( v10 );
              v23 = v22 - 1;
              if ( v10 )
                v23 = v22;
              *v23 = 0;
              if ( v10 )
              {
                v24 = wcstok_mvcrt_legacy_two_parameter_form(v18, L"*", v19);
                if ( v24 )
                {
                  if ( !(unsigned int)wbem_wcsicmp(v24, v15) )
                    v9 = 1;
                }
              }
            }
          }
        }
        if ( v18 )
          CWin32DefaultArena::WbemMemFree(v18);
        v30 = 0;
        if ( v15 )
          CWin32DefaultArena::WbemMemFree(v15);
        v31 = 0;
      }
      else
      {
        v9 = 1;
      }
    }
    if ( v12 != &dword_1800323BC )
    {
      v26 = v12 - 3;
      if ( v12 - 3 != (int *)byte_1800323B0 && _InterlockedDecrement(v26) <= 0 )
        CWin32DefaultArena::WbemMemFree(v26);
    }
  }
  CRegistry::Close((CRegistry *)&v32);
  CRegistry::~CRegistry((CRegistry *)&v32);
  return v9;
}

```

## disassembly

```asm
0x180002ea4  mov     [rsp-8+arg_0], rbx
0x180002ea9  push    rbp
0x180002eaa  push    rsi
0x180002eab  push    rdi
0x180002eac  push    r12
0x180002eae  push    r13
0x180002eb0  push    r14
0x180002eb2  push    r15
0x180002eb4  lea     rbp, [rsp-1F0h]
0x180002ebc  sub     rsp, 2F0h
0x180002ec3  mov     rax, cs:__security_cookie
0x180002eca  xor     rax, rsp
0x180002ecd  mov     [rbp+220h+var_40], rax
0x180002ed4  mov     r13d, r9d
0x180002ed7  mov     rdi, r8
0x180002eda  mov     rbx, rdx
0x180002edd  xor     r15d, r15d
0x180002ee0  mov     r12d, r15d
0x180002ee3  lea     rcx, [rbp+220h+var_2A0]; this
0x180002ee7  call    ??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180002eec  nop
0x180002eed  cmp     [rbp+220h+hKey], r15
0x180002ef1  jnz     loc_1800031C7
0x180002ef7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002efe  mov     [rbp+220h+var_2A0], rcx
0x180002f02  lea     rax, [rbp+220h+hKey]
0x180002f06  mov     [rsp+320h+phkResult], rax; phkResult
0x180002f0b  mov     r9d, 20019h; samDesired
0x180002f11  xor     r8d, r8d; ulOptions
0x180002f14  mov     rdx, rbx; lpSubKey
0x180002f17  call    cs:__imp_RegOpenKeyExW
0x180002f1d  test    eax, eax
0x180002f1f  jnz     loc_18000315B
0x180002f25  mov     r14d, 104h
0x180002f2b  mov     [rbp+220h+cchClass], r14d
0x180002f32  lea     rax, [rbp+220h+ftLastWriteTime]
0x180002f39  mov     [rsp+320h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180002f3e  lea     rax, [rbp+220h+cbSecurityDescriptor]
0x180002f45  mov     [rsp+320h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180002f4a  lea     rax, [rbp+220h+cbMaxValueLen]
0x180002f51  mov     [rsp+320h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180002f56  lea     rax, [rbp+220h+cbMaxValueNameLen]
0x180002f5d  mov     [rsp+320h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180002f62  lea     rax, [rbp+220h+cValues]
0x180002f69  mov     [rsp+320h+lpcValues], rax; lpcValues
0x180002f6e  lea     rax, [rbp+220h+cbMaxClassLen]
0x180002f75  mov     [rsp+320h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x180002f7a  lea     rax, [rbp+220h+cbMaxSubKeyLen]
0x180002f81  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180002f86  lea     rax, [rbp+220h+cSubKeys]
0x180002f8d  mov     [rsp+320h+phkResult], rax; lpcSubKeys
0x180002f92  xor     r9d, r9d; lpReserved
0x180002f95  lea     r8, [rbp+220h+cchClass]; lpcchClass
0x180002f9c  lea     rdx, [rbp+220h+Class]; lpClass
0x180002fa0  mov     rcx, [rbp+220h+hKey]; hKey
0x180002fa4  call    cs:__imp_RegQueryInfoKeyW
0x180002faa  mov     rdx, rbx; unsigned __int16 *
0x180002fad  lea     rcx, [rbp+220h+var_288]; this
0x180002fb1  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x180002fb6  lea     rax, dword_1800323BC
0x180002fbd  mov     [rsp+320h+var_2B8], rax
0x180002fc2  lea     r9, [rsp+320h+var_2B8]; struct CHString *
0x180002fc7  mov     r8, rdi; unsigned __int16 *
0x180002fca  mov     rdx, [rbp+220h+hKey]; HKEY
0x180002fce  lea     rcx, [rbp+220h+var_2A0]; this
0x180002fd2  call    ?GetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)
0x180002fd7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002fdb  mov     rbx, [rsp+320h+var_2B8]
0x180002fe0  test    eax, eax
0x180002fe2  jnz     loc_18000314F
0x180002fe8  cmp     [rbp+220h+arg_28], r15d
0x180002fef  jz      loc_1800031BF
0x180002ff5  mov     edx, r14d
0x180002ff8  lea     rcx, [rsp+320h+Size]
0x180002ffd  call    ??$MixedSizeAddition@H@?$SafeInt@I@@CA?AV0@V0@H@Z; SafeInt<uint>::MixedSizeAddition<int>(SafeInt<uint>,int)
0x180003002  mov     edi, dword ptr [rsp+320h+Size]
0x180003006  lea     eax, [rsi+3]
0x180003009  mul     rdi
0x18000300c  cmovb   rax, rsi
0x180003010  mov     rcx, rax
0x180003013  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003019  mov     rsi, rax
0x18000301c  mov     [rsp+320h+var_2A8], rax
0x180003021  test    rax, rax
0x180003024  jz      short loc_180003034
0x180003026  mov     r8d, edi; Size
0x180003029  xor     edx, edx; Val
0x18000302b  mov     rcx, rax; void *
0x18000302e  call    memset_0
0x180003033  nop
0x180003034  mov     edx, r14d
0x180003037  lea     rcx, [rsp+320h+Size]
0x18000303c  call    ??$MixedSizeAddition@H@?$SafeInt@I@@CA?AV0@V0@H@Z; SafeInt<uint>::MixedSizeAddition<int>(SafeInt<uint>,int)
0x180003041  mov     r15d, dword ptr [rsp+320h+Size]
0x180003046  mov     eax, 2
0x18000304b  mul     r15
0x18000304e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003055  cmovb   rax, rcx
0x180003059  mov     rcx, rax
0x18000305c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003062  mov     rdi, rax
0x180003065  mov     [rsp+320h+var_2B0], rax
0x18000306a  test    rax, rax
0x18000306d  jz      short loc_18000307D
0x18000306f  mov     r8d, r15d; Size
0x180003072  xor     edx, edx; Val
0x180003074  mov     rcx, rax; void *
0x180003077  call    memset_0
0x18000307c  nop
0x18000307d  xor     r15d, r15d
0x180003080  test    rsi, rsi
0x180003083  jz      loc_180003125
0x180003089  test    rdi, rdi
0x18000308c  jz      loc_180003125
0x180003092  mov     eax, [rbp+220h+arg_20]
0x180003098  mov     dword ptr [rsp+320h+phkResult], eax
0x18000309c  mov     r9d, r13d
0x18000309f  lea     r8, aLowdatetimeLdH_0; "LowDateTime:%ld,HighDateTime:%ld"
0x1800030a6  mov     rdx, r14; unsigned __int64
0x1800030a9  mov     rcx, rsi; unsigned __int16 *
0x1800030ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800030b1  test    eax, eax
0x1800030b3  js      short loc_180003125
0x1800030b5  mov     ecx, 7FFFFFFEh
0x1800030ba  mov     rdx, rbx
0x1800030bd  mov     rax, rdi
0x1800030c0  mov     r15d, 1
0x1800030c6  xor     r13d, r13d
0x1800030c9  test    rcx, rcx
0x1800030cc  jz      short loc_1800030EC
0x1800030ce  movzx   r8d, word ptr [rdx]; Context
0x1800030d2  test    r8w, r8w
0x1800030d6  jz      short loc_1800030EC
0x1800030d8  add     rdx, 2
0x1800030dc  mov     [rax], r8w
0x1800030e0  add     rax, 2
0x1800030e4  sub     rcx, r15
0x1800030e7  sub     r14, r15
0x1800030ea  jnz     short loc_1800030C9
0x1800030ec  lea     rcx, [rax-2]
0x1800030f0  test    r14, r14
0x1800030f3  cmovnz  rcx, rax
0x1800030f7  mov     [rcx], r13w
0x1800030fb  jz      short loc_180003122
0x1800030fd  lea     rdx, Delimiter; "*"
0x180003104  mov     rcx, rdi; String
0x180003107  call    wcstok_mvcrt_legacy_two_parameter_form
0x18000310c  test    rax, rax
0x18000310f  jz      short loc_180003122
0x180003111  mov     rdx, rsi; unsigned __int16 *
0x180003114  mov     rcx, rax; unsigned __int16 *
0x180003117  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x18000311c  test    eax, eax
0x18000311e  cmovz   r12d, r15d
0x180003122  xor     r15d, r15d
0x180003125  test    rdi, rdi
0x180003128  jz      short loc_180003133
0x18000312a  mov     rcx, rdi
0x18000312d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003133  mov     [rsp+320h+var_2B0], r15
0x180003138  test    rsi, rsi
0x18000313b  jz      short loc_180003146
0x18000313d  mov     rcx, rsi
0x180003140  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003146  mov     [rsp+320h+var_2A8], r15
0x18000314b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000314f  lea     rax, dword_1800323BC
0x180003156  cmp     rbx, rax
0x180003159  jnz     short loc_18000319B
0x18000315b  lea     rcx, [rbp+220h+var_2A0]; this
0x18000315f  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x180003164  nop
0x180003165  lea     rcx, [rbp+220h+var_2A0]; this
0x180003169  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18000316e  mov     eax, r12d
0x180003171  mov     rcx, [rbp+220h+var_40]
0x180003178  xor     rcx, rsp; StackCookie
0x18000317b  call    __security_check_cookie
0x180003180  mov     rbx, [rsp+320h+arg_0]
0x180003188  add     rsp, 2F0h
0x18000318f  pop     r15
0x180003191  pop     r14
0x180003193  pop     r13
0x180003195  pop     r12
0x180003197  pop     rdi
0x180003198  pop     rsi
0x180003199  pop     rbp
0x18000319a  retn
0x18000319b  lea     rcx, [rbx-0Ch]
0x18000319f  lea     rax, byte_1800323B0
0x1800031a6  cmp     rcx, rax
0x1800031a9  jz      short loc_18000315B
0x1800031ab  mov     edx, esi
0x1800031ad  lock xadd [rcx], edx
0x1800031b1  add     edx, esi
0x1800031b3  test    edx, edx
0x1800031b5  jg      short loc_18000315B
0x1800031b7  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800031bd  jmp     short loc_18000315B
0x1800031bf  mov     r12d, 1
0x1800031c5  jmp     short loc_18000314F
0x1800031c7  lea     rcx, [rbp+220h+var_2A0]; this
0x1800031cb  call    ?PrepareToReOpen@CRegistry@@AEAAXXZ; CRegistry::PrepareToReOpen(void)
0x1800031d0  jmp     loc_180002EF7
```
