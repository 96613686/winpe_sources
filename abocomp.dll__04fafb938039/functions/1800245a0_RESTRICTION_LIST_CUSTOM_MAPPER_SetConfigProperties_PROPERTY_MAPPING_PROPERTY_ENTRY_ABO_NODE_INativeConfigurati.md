# RESTRICTION_LIST_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x1800245a0`
- end: `0x1800249fb`
- name: `?SetConfigProperties@RESTRICTION_LIST_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `1115`
- prototype: `__int64 __fastcall(RESTRICTION_LIST_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003460`
- `0x1800245a0`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180024788`
- `msvcrt!_wcsicmp` at `0x1800247a7`
- `msvcrt!_wcsicmp` at `0x180024788`
- `msvcrt!_wcsicmp` at `0x1800247a7`
- `iisutil!SplitCommaDelimitedString` at `0x18002470f`
- `iisutil!SplitCommaDelimitedString` at `0x18002470f`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002476c`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800247c6`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800247d8`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800247ed`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002476c`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800247c6`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800247d8`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800247ed`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180024723`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180024723`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800246ef`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800246ef`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800245e7`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800245e7`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800249d3`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800249d3`

## string_xrefs

- `0x18002479d`: `*.dll`

## pseudocode

```c
__int64 __fastcall RESTRICTION_LIST_CUSTOM_MAPPER::SetConfigProperties(
        RESTRICTION_LIST_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  const unsigned __int16 *v5; // r13
  int v9; // ebx
  unsigned int v10; // edx
  unsigned int i; // edi
  unsigned int v12; // r15d
  unsigned int v13; // edi
  const unsigned __int16 *j; // r12
  const unsigned __int16 *v15; // rax
  int v16; // r8d
  unsigned int v17; // esi
  int v18; // edx
  const wchar_t *v19; // rax
  const unsigned __int16 *v20; // rdi
  const unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // rax
  const wchar_t *v23; // r15
  int v24; // eax
  __int64 v25; // rax
  const unsigned __int16 *v27; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v28; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v29; // [rsp+40h] [rbp-41h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-3Dh]
  unsigned int v31; // [rsp+48h] [rbp-39h]
  _BYTE v32[56]; // [rsp+50h] [rbp-31h] BYREF

  v5 = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v32);
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v9 = -2147024809;
    goto LABEL_50;
  }
  v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 **))(*(_QWORD *)a5 + 40LL))(
         a5,
         &v28);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, unsigned int *))(*(_QWORD *)v28 + 72LL))(v28, &v29);
    if ( v9 >= 0 )
    {
      v10 = v29;
      for ( i = 0; i < v29; ++i )
      {
        v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v28 + 96LL))(
               v28,
               v10 - i - 1,
               0);
        if ( v9 < 0 )
          goto LABEL_50;
        v10 = v29;
      }
      v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, const unsigned __int16 **))(*(_QWORD *)v28 + 48LL))(
             v28,
             L"clear",
             &v27);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v28 + 88LL))(
               v28,
               v27,
               0,
               0);
        if ( v9 >= 0 )
        {
          v12 = 0;
          v30 = 0;
          v13 = 0;
          v31 = 0;
          (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v27 + 16LL))(v27);
          v27 = 0;
          for ( j = (const unsigned __int16 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16))
                                              + 3); ; j += v25 + 1 )
          {
            if ( *j == (_WORD)v5 )
            {
              v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 136LL))(
                     a5,
                     L"notListedCgisAllowed",
                     v12,
                     0);
              if ( v9 >= 0 )
                v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 136LL))(
                       a5,
                       L"notListedIsapisAllowed",
                       v13,
                       0);
              goto LABEL_50;
            }
            v9 = SplitCommaDelimitedString(j, 1, 1, (struct MULTISZ *)v32);
            if ( v9 < 0 )
              goto LABEL_50;
            v15 = MULTISZ::First((MULTISZ *)v32);
            v16 = *v15 - 48;
            if ( *v15 == 48 )
              v16 = v15[1] - (unsigned __int16)v5;
            if ( v16 )
            {
              v18 = *v15 - 49;
              if ( *v15 == 49 )
                v18 = v15[1] - (unsigned __int16)v5;
              if ( v18 )
              {
LABEL_47:
                v9 = -2147024883;
                goto LABEL_50;
              }
              v17 = 1;
            }
            else
            {
              v17 = (unsigned int)v5;
            }
            v19 = MULTISZ::Next((MULTISZ *)v32, v15);
            v20 = v19;
            if ( !v19 )
              goto LABEL_47;
            if ( !_wcsicmp(v19, L"*.exe") )
              break;
            if ( _wcsicmp(v20, L"*.dll") )
            {
              v21 = MULTISZ::Next((MULTISZ *)v32, v20);
              if ( v21 && (v22 = MULTISZ::Next((MULTISZ *)v32, v21), (v23 = v22) != 0) )
                v5 = MULTISZ::Next((MULTISZ *)v32, v22);
              else
                v23 = &word_18002E968;
              v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, const unsigned __int16 **))(*(_QWORD *)v28 + 48LL))(
                     v28,
                     L"add",
                     &v27);
              if ( v9 < 0
                || (v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v27 + 128LL))(
                           v27,
                           L"path",
                           v20,
                           0),
                    v9 < 0)
                || (v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v27 + 136LL))(
                           v27,
                           L"allowed",
                           v17,
                           0),
                    v9 < 0)
                || (v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v27 + 128LL))(
                           v27,
                           L"groupId",
                           v23,
                           0),
                    v9 < 0) )
              {
                v5 = 0;
                goto LABEL_50;
              }
              if ( v5 )
              {
                v24 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v27 + 128LL))(
                        v27,
                        L"description",
                        v5,
                        0);
                v5 = 0;
                v9 = v24;
                if ( v24 < 0 )
                  goto LABEL_50;
              }
              v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD))(*(_QWORD *)v28 + 88LL))(
                     v28,
                     v27,
                     0xFFFFFFFFLL,
                     0);
              if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147024713 )
                goto LABEL_50;
              (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v27 + 16LL))(v27);
              v12 = v30;
              v27 = v5;
              goto LABEL_40;
            }
            v12 = v30;
            v13 = v17;
            v31 = v17;
LABEL_41:
            v25 = -1;
            do
              ++v25;
            while ( j[v25] != (_WORD)v5 );
          }
          v12 = v17;
          v30 = v17;
LABEL_40:
          v13 = v31;
          goto LABEL_41;
        }
      }
    }
  }
LABEL_50:
  if ( v27 )
  {
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = v5;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = v5;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v32);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800245a0  push    rbp
0x1800245a2  push    rbx
0x1800245a3  push    rsi
0x1800245a4  push    rdi
0x1800245a5  push    r12
0x1800245a7  push    r13
0x1800245a9  push    r14
0x1800245ab  push    r15
0x1800245ad  lea     rbp, [rsp-17h]
0x1800245b2  sub     rsp, 98h
0x1800245b9  mov     rax, cs:__security_cookie
0x1800245c0  xor     rax, rsp
0x1800245c3  mov     [rbp+4Fh+var_48], rax
0x1800245c7  mov     r14, [rbp+4Fh+arg_20]
0x1800245cb  lea     rcx, [rbp+4Fh+var_80]
0x1800245cf  xor     r13d, r13d
0x1800245d2  mov     rdi, r9
0x1800245d5  mov     [rbp+4Fh+var_98], r13
0x1800245d9  mov     rsi, r8
0x1800245dc  mov     [rbp+4Fh+var_A0], r13
0x1800245e0  mov     rbx, rdx
0x1800245e3  mov     [rbp+4Fh+var_90], r13d
0x1800245e7  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800245ed  test    rbx, rbx
0x1800245f0  jz      loc_180024993
0x1800245f6  test    rsi, rsi
0x1800245f9  jz      loc_180024993
0x1800245ff  test    rdi, rdi
0x180024602  jz      loc_180024993
0x180024608  test    r14, r14
0x18002460b  jz      loc_180024993
0x180024611  mov     rax, [r14]
0x180024614  lea     rdx, [rbp+4Fh+var_98]
0x180024618  mov     rcx, r14
0x18002461b  mov     rax, [rax+28h]
0x18002461f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024624  mov     ebx, eax
0x180024626  test    eax, eax
0x180024628  js      loc_18002499D
0x18002462e  mov     rcx, [rbp+4Fh+var_98]
0x180024632  lea     rdx, [rbp+4Fh+var_90]
0x180024636  mov     rax, [rcx]
0x180024639  mov     rax, [rax+48h]
0x18002463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024642  mov     ebx, eax
0x180024644  test    eax, eax
0x180024646  js      loc_18002499D
0x18002464c  mov     edx, [rbp+4Fh+var_90]
0x18002464f  mov     edi, r13d
0x180024652  test    edx, edx
0x180024654  jz      short loc_180024680
0x180024656  mov     rcx, [rbp+4Fh+var_98]
0x18002465a  sub     edx, edi
0x18002465c  dec     edx
0x18002465e  xor     r8d, r8d
0x180024661  mov     rax, [rcx]
0x180024664  mov     rax, [rax+60h]
0x180024668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002466d  mov     ebx, eax
0x18002466f  test    eax, eax
0x180024671  js      loc_18002499D
0x180024677  mov     edx, [rbp+4Fh+var_90]
0x18002467a  inc     edi
0x18002467c  cmp     edi, edx
0x18002467e  jb      short loc_180024656
0x180024680  mov     rcx, [rbp+4Fh+var_98]
0x180024684  lea     r8, [rbp+4Fh+var_A0]
0x180024688  lea     rdx, aClear; "clear"
0x18002468f  mov     rax, [rcx]
0x180024692  mov     rax, [rax+30h]
0x180024696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002469b  mov     ebx, eax
0x18002469d  test    eax, eax
0x18002469f  js      loc_18002499D
0x1800246a5  mov     rcx, [rbp+4Fh+var_98]
0x1800246a9  xor     r9d, r9d
0x1800246ac  mov     rdx, [rbp+4Fh+var_A0]
0x1800246b0  xor     r8d, r8d
0x1800246b3  mov     rax, [rcx]
0x1800246b6  mov     rax, [rax+58h]
0x1800246ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246bf  mov     ebx, eax
0x1800246c1  test    eax, eax
0x1800246c3  js      loc_18002499D
0x1800246c9  mov     rcx, [rbp+4Fh+var_A0]
0x1800246cd  mov     r15d, r13d
0x1800246d0  mov     [rbp+4Fh+var_8C], r13d
0x1800246d4  mov     edi, r13d
0x1800246d7  mov     [rbp+4Fh+var_88], r13d
0x1800246db  mov     rax, [rcx]
0x1800246de  mov     rax, [rax+10h]
0x1800246e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246e7  lea     rcx, [rsi+10h]
0x1800246eb  mov     [rbp+4Fh+var_A0], r13
0x1800246ef  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800246f5  mov     r12, [rax+18h]
0x1800246f9  jmp     loc_180024939
0x1800246fe  mov     edi, 1
0x180024703  lea     r9, [rbp+4Fh+var_80]
0x180024707  mov     r8d, edi
0x18002470a  mov     edx, edi
0x18002470c  mov     rcx, r12
0x18002470f  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x180024715  mov     ebx, eax
0x180024717  test    eax, eax
0x180024719  js      loc_18002499D
0x18002471f  lea     rcx, [rbp+4Fh+var_80]
0x180024723  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180024729  movzx   r8d, word ptr [rax]
0x18002472d  sub     r8d, 30h ; '0'
0x180024731  jnz     short loc_18002473F
0x180024733  movzx   r8d, word ptr [rax+2]
0x180024738  movzx   edx, r13w
0x18002473c  sub     r8d, edx
0x18002473f  test    r8d, r8d
0x180024742  jnz     short loc_180024749
0x180024744  mov     esi, r13d
0x180024747  jmp     short loc_180024765
0x180024749  movzx   edx, word ptr [rax]
0x18002474c  sub     edx, 31h ; '1'
0x18002474f  jnz     short loc_18002475B
0x180024751  movzx   edx, word ptr [rax+2]
0x180024755  movzx   ecx, r13w
0x180024759  sub     edx, ecx
0x18002475b  test    edx, edx
0x18002475d  jnz     loc_18002498C
0x180024763  mov     esi, edi
0x180024765  mov     rdx, rax
0x180024768  lea     rcx, [rbp+4Fh+var_80]
0x18002476c  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x180024772  mov     rdi, rax
0x180024775  test    rax, rax
0x180024778  jz      loc_18002498C
0x18002477e  lea     rdx, aExe_0; "*.exe"
0x180024785  mov     rcx, rax; String1
0x180024788  call    cs:__imp__wcsicmp
0x18002478e  test    eax, eax
0x180024790  jnz     short loc_18002479D
0x180024792  mov     r15d, esi
0x180024795  mov     [rbp+4Fh+var_8C], esi
0x180024798  jmp     loc_180024920
0x18002479d  lea     rdx, aDll; "*.dll"
0x1800247a4  mov     rcx, rdi; String1
0x1800247a7  call    cs:__imp__wcsicmp
0x1800247ad  test    eax, eax
0x1800247af  jnz     short loc_1800247BF
0x1800247b1  mov     r15d, [rbp+4Fh+var_8C]
0x1800247b5  mov     edi, esi
0x1800247b7  mov     [rbp+4Fh+var_88], esi
0x1800247ba  jmp     loc_180024923
0x1800247bf  mov     rdx, rdi
0x1800247c2  lea     rcx, [rbp+4Fh+var_80]
0x1800247c6  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800247cc  test    rax, rax
0x1800247cf  jz      short loc_1800247F8
0x1800247d1  mov     rdx, rax
0x1800247d4  lea     rcx, [rbp+4Fh+var_80]
0x1800247d8  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800247de  mov     r15, rax
0x1800247e1  test    rax, rax
0x1800247e4  jz      short loc_1800247F8
0x1800247e6  mov     rdx, rax
0x1800247e9  lea     rcx, [rbp+4Fh+var_80]
0x1800247ed  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800247f3  mov     r13, rax
0x1800247f6  jmp     short loc_1800247FF
0x1800247f8  lea     r15, word_18002E968
0x1800247ff  mov     rcx, [rbp+4Fh+var_98]
0x180024803  lea     r8, [rbp+4Fh+var_A0]
0x180024807  lea     rdx, aAdd; "add"
0x18002480e  mov     rax, [rcx]
0x180024811  mov     rax, [rax+30h]
0x180024815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002481a  mov     ebx, eax
0x18002481c  test    eax, eax
0x18002481e  js      loc_18002499A
0x180024824  mov     rcx, [rbp+4Fh+var_A0]
0x180024828  lea     rdx, aPath; "path"
0x18002482f  xor     r9d, r9d
0x180024832  mov     r8, rdi
0x180024835  mov     rax, [rcx]
0x180024838  mov     rax, [rax+80h]
0x18002483f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024844  mov     ebx, eax
0x180024846  test    eax, eax
0x180024848  js      loc_18002499A
0x18002484e  mov     rcx, [rbp+4Fh+var_A0]
0x180024852  lea     rdx, aAllowed; "allowed"
0x180024859  xor     r9d, r9d
0x18002485c  mov     r8d, esi
0x18002485f  mov     rax, [rcx]
0x180024862  mov     rax, [rax+88h]
0x180024869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002486e  mov     ebx, eax
0x180024870  test    eax, eax
0x180024872  js      loc_18002499A
0x180024878  mov     rcx, [rbp+4Fh+var_A0]
0x18002487c  lea     rdx, aGroupid; "groupId"
0x180024883  xor     r9d, r9d
0x180024886  mov     r8, r15
0x180024889  mov     rax, [rcx]
0x18002488c  mov     rax, [rax+80h]
0x180024893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024898  mov     ebx, eax
0x18002489a  test    eax, eax
0x18002489c  js      loc_18002499A
0x1800248a2  test    r13, r13
0x1800248a5  jz      short loc_1800248D4
0x1800248a7  mov     rcx, [rbp+4Fh+var_A0]
0x1800248ab  lea     rdx, aDescription; "description"
0x1800248b2  xor     r9d, r9d
0x1800248b5  mov     r8, r13
0x1800248b8  mov     rax, [rcx]
0x1800248bb  mov     rax, [rax+80h]
0x1800248c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248c7  xor     r13d, r13d
0x1800248ca  mov     ebx, eax
0x1800248cc  test    eax, eax
0x1800248ce  js      loc_18002499D
0x1800248d4  mov     rcx, [rbp+4Fh+var_98]
0x1800248d8  xor     r9d, r9d
0x1800248db  mov     rdx, [rbp+4Fh+var_A0]
0x1800248df  or      r8d, 0FFFFFFFFh
0x1800248e3  mov     rax, [rcx]
0x1800248e6  mov     rax, [rax+58h]
0x1800248ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248ef  mov     esi, 80000000h
0x1800248f4  mov     ebx, eax
0x1800248f6  add     eax, esi
0x1800248f8  test    esi, eax
0x1800248fa  jnz     short loc_180024908
0x1800248fc  cmp     ebx, 800700B7h
0x180024902  jnz     loc_18002499D
0x180024908  mov     rcx, [rbp+4Fh+var_A0]
0x18002490c  mov     rax, [rcx]
0x18002490f  mov     rax, [rax+10h]
0x180024913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024918  mov     r15d, [rbp+4Fh+var_8C]
0x18002491c  mov     [rbp+4Fh+var_A0], r13
0x180024920  mov     edi, [rbp+4Fh+var_88]
0x180024923  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024927  inc     rax
0x18002492a  cmp     [r12+rax*2], r13w
0x18002492f  jnz     short loc_180024927
0x180024931  lea     r12, [r12+rax*2]
0x180024935  add     r12, 2
0x180024939  cmp     [r12], r13w
0x18002493e  jnz     loc_1800246FE
0x180024944  mov     rax, [r14]
0x180024947  lea     rdx, aNotlistedcgisa; "notListedCgisAllowed"
0x18002494e  xor     r9d, r9d
0x180024951  mov     r8d, r15d
0x180024954  mov     rcx, r14
0x180024957  mov     rax, [rax+88h]
0x18002495e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024963  mov     ebx, eax
0x180024965  test    eax, eax
0x180024967  js      short loc_18002499D
0x180024969  mov     rax, [r14]
0x18002496c  lea     rdx, aNotlistedisapi; "notListedIsapisAllowed"
0x180024973  xor     r9d, r9d
0x180024976  mov     r8d, edi
0x180024979  mov     rcx, r14
0x18002497c  mov     rax, [rax+88h]
0x180024983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024988  mov     ebx, eax
0x18002498a  jmp     short loc_18002499D
0x18002498c  mov     ebx, 8007000Dh
0x180024991  jmp     short loc_18002499D
0x180024993  mov     ebx, 80070057h
0x180024998  jmp     short loc_18002499D
0x18002499a  xor     r13d, r13d
0x18002499d  mov     rcx, [rbp+4Fh+var_A0]
0x1800249a1  test    rcx, rcx
0x1800249a4  jz      short loc_1800249B6
0x1800249a6  mov     rax, [rcx]
0x1800249a9  mov     rax, [rax+10h]
0x1800249ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249b2  mov     [rbp+4Fh+var_A0], r13
0x1800249b6  mov     rcx, [rbp+4Fh+var_98]
0x1800249ba  test    rcx, rcx
0x1800249bd  jz      short loc_1800249CF
0x1800249bf  mov     rax, [rcx]
0x1800249c2  mov     rax, [rax+10h]
0x1800249c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249cb  mov     [rbp+4Fh+var_98], r13
0x1800249cf  lea     rcx, [rbp+4Fh+var_80]
0x1800249d3  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800249d9  mov     eax, ebx
0x1800249db  mov     rcx, [rbp+4Fh+var_48]
0x1800249df  xor     rcx, rsp; StackCookie
0x1800249e2  call    __security_check_cookie
0x1800249e7  add     rsp, 98h
0x1800249ee  pop     r15
0x1800249f0  pop     r14
0x1800249f2  pop     r13
0x1800249f4  pop     r12
0x1800249f6  pop     rdi
0x1800249f7  pop     rsi
0x1800249f8  pop     rbx
  ... truncated ...
```
