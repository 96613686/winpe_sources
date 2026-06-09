# HTTP_REDIRECT_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180023190`
- end: `0x18002376a`
- name: `?SetConfigProperties@HTTP_REDIRECT_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `1498`
- prototype: `__int64 __fastcall(HTTP_REDIRECT_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180023190`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800235ec`
- `msvcrt!_wcsicmp` at `0x180023605`
- `msvcrt!_wcsicmp` at `0x18002361e`
- `msvcrt!_wcsicmp` at `0x18002363a`
- `msvcrt!_wcsicmp` at `0x180023656`
- `msvcrt!_wcsicmp` at `0x1800235ec`
- `msvcrt!_wcsicmp` at `0x180023605`
- `msvcrt!_wcsicmp` at `0x18002361e`
- `msvcrt!_wcsicmp` at `0x18002363a`
- `msvcrt!_wcsicmp` at `0x180023656`
- `msvcrt!wcschr` at `0x1800233f8`
- `msvcrt!wcschr` at `0x180023416`
- `msvcrt!wcschr` at `0x180023452`
- `msvcrt!wcschr` at `0x1800233f8`
- `msvcrt!wcschr` at `0x180023416`
- `msvcrt!wcschr` at `0x180023452`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023467`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180023467`
- `iisutil!SplitCommaDelimitedString` at `0x180023355`
- `iisutil!SplitCommaDelimitedString` at `0x180023355`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800235cb`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002366f`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800235cb`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x18002366f`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002336a`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002336a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023340`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023340`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002320f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023234`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002320f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023234`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002372a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023734`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002372a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180023734`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800234c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800234ff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800234c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800234ff`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180023438`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180023478`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180023438`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180023478`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800231e4`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800231e4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002373f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002373f`

## string_xrefs

- `0x180023614`: `TEMPORARY`

## pseudocode

```c
__int64 __fastcall HTTP_REDIRECT_CUSTOM_MAPPER::SetConfigProperties(
        HTTP_REDIRECT_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v8; // ebx
  unsigned int v9; // edx
  int v10; // edi
  const unsigned __int16 **Ptr; // rax
  const unsigned __int16 *v12; // rdi
  unsigned __int64 v13; // rax
  const wchar_t *v14; // rbx
  wchar_t *v15; // rax
  wchar_t *v16; // r14
  wchar_t *v17; // rbx
  wchar_t *v18; // rax
  const unsigned __int16 *v19; // rdx
  wchar_t *v20; // r14
  int v21; // eax
  __int64 (__fastcall *v22)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  __int64 (__fastcall *v24)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *v25; // rax
  const wchar_t *v26; // r8
  unsigned int v27; // r14d
  unsigned int v28; // r12d
  unsigned int v29; // r15d
  const unsigned __int16 *i; // rbx
  __int64 v32; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v34; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v35[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v36[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[56]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v38[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v39[256]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v33 = 0;
  v32 = 0;
  v34 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v35);
  memset_0(v38, 0, sizeof(v38));
  STRU::STRU((STRU *)v37, v38, 0x100u);
  memset_0(v39, 0, sizeof(v39));
  STRU::STRU((STRU *)v36, v39, 0x100u);
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v8 = -2147024809;
    goto LABEL_57;
  }
  v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v33);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 72LL))(v33, &v34);
    if ( v8 >= 0 )
    {
      v9 = v34;
      v10 = 0;
      if ( !v34 )
      {
LABEL_10:
        v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v33 + 48LL))(
               v33,
               L"clear",
               &v32);
        if ( v8 < 0 )
          goto LABEL_57;
        v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v33 + 88LL))(v33, v32, 0, 0);
        if ( v8 < 0 )
          goto LABEL_57;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        v32 = 0;
        Ptr = (const unsigned __int16 **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16));
        v8 = SplitCommaDelimitedString(Ptr[3], 1, 1, (struct MULTISZ *)v35);
        if ( v8 < 0 )
          goto LABEL_57;
        v12 = MULTISZ::First((MULTISZ *)v35);
        if ( v12 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v12[v13] );
          if ( v13 >= 2 && *v12 == 42 && v12[1] == 59 )
            v12 += 2;
          if ( *v12 )
          {
            v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, bool, _QWORD))(*(_QWORD *)a5 + 136LL))(
                   a5,
                   L"enabled",
                   *v12 != 33,
                   0);
            if ( v8 < 0 || *v12 == 33 )
              goto LABEL_57;
            if ( !wcschr(v12, 0x2Au) )
            {
              v26 = v12;
LABEL_40:
              v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)a5 + 128LL))(
                     a5,
                     L"destination",
                     v26,
                     0);
              if ( v8 >= 0 )
              {
                v27 = 302;
                v28 = 0;
                v29 = 0;
                for ( i = MULTISZ::Next((MULTISZ *)v35, v12); i; i = MULTISZ::Next((MULTISZ *)v35, i) )
                {
                  if ( _wcsicmp(i, L"CHILD_ONLY") )
                  {
                    if ( _wcsicmp(i, L"EXACT_DESTINATION") )
                    {
                      if ( _wcsicmp(i, L"TEMPORARY") )
                      {
                        if ( _wcsicmp(i, L"PERMANENT") )
                        {
                          if ( !_wcsicmp(i, L"PERMREDIRECT") )
                            v27 = 308;
                        }
                        else
                        {
                          v27 = 301;
                        }
                      }
                      else
                      {
                        v27 = 307;
                      }
                    }
                    else
                    {
                      v28 = 1;
                    }
                  }
                  else
                  {
                    v29 = 1;
                  }
                }
                v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 136LL))(
                       a5,
                       L"childOnly",
                       v29,
                       0);
                if ( v8 >= 0 )
                {
                  v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 136LL))(
                         a5,
                         L"exactDestination",
                         v28,
                         0);
                  if ( v8 >= 0 )
                    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 112LL))(
                           a5,
                           L"httpResponseStatus",
                           v27,
                           0);
                }
              }
              goto LABEL_57;
            }
            v14 = v12;
            while ( 1 )
            {
              v15 = wcschr(v14, 0x3Bu);
              v16 = v15;
              if ( !v15 )
                break;
              v8 = STRU::Copy((STRU *)v37, v14, v15 - v14);
              if ( v8 < 0 )
                goto LABEL_57;
              v17 = v16 + 1;
              v18 = wcschr(v16 + 1, 0x3Bu);
              v19 = v16 + 1;
              v20 = v18;
              v21 = v18 ? STRU::Copy((STRU *)v36, v19, v18 - v17) : STRU::Copy((STRU *)v36, v19);
              v8 = v21;
              if ( v21 < 0 )
                goto LABEL_57;
              v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v33 + 48LL))(
                     v33,
                     L"add",
                     &v32);
              if ( v8 < 0 )
                goto LABEL_57;
              v22 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v32 + 128LL);
              Str = STRU::QueryStr((STRU *)v37);
              v8 = v22(v32, L"wildcard", Str, 0);
              if ( v8 < 0 )
                goto LABEL_57;
              v24 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v32 + 128LL);
              v25 = STRU::QueryStr((STRU *)v36);
              v8 = v24(v32, L"destination", v25, 0);
              if ( v8 < 0 )
                goto LABEL_57;
              v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v33 + 88LL))(
                     v33,
                     v32,
                     0xFFFFFFFFLL,
                     0);
              if ( ((v8 + 0x80000000) & 0x80000000) == 0 && v8 != -2147024713 )
                goto LABEL_57;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
              v32 = 0;
              v14 = (const wchar_t *)((unsigned __int64)(v20 + 1) & -(__int64)(v20 != 0));
              if ( !v14 )
              {
                v26 = &word_18002E968;
                goto LABEL_40;
              }
            }
          }
        }
        v8 = -2147024883;
        goto LABEL_57;
      }
      while ( 1 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v33 + 96LL))(v33, v9 - v10 - 1, 0);
        if ( v8 < 0 )
          break;
        v9 = v34;
        if ( ++v10 >= v34 )
          goto LABEL_10;
      }
    }
  }
LABEL_57:
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  STRU::~STRU((STRU *)v36);
  STRU::~STRU((STRU *)v37);
  MULTISZ::~MULTISZ((MULTISZ *)v35);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180023190  push    rbp
0x180023192  push    rbx
0x180023193  push    rsi
0x180023194  push    rdi
0x180023195  push    r12
0x180023197  push    r13
0x180023199  push    r14
0x18002319b  push    r15
0x18002319d  lea     rbp, [rsp-408h]
0x1800231a5  sub     rsp, 508h
0x1800231ac  mov     rax, cs:__security_cookie
0x1800231b3  xor     rax, rsp
0x1800231b6  mov     [rbp+440h+var_50], rax
0x1800231bd  mov     rsi, [rbp+440h+arg_20]
0x1800231c4  lea     rcx, [rsp+540h+var_4F8]
0x1800231c9  xor     r13d, r13d
0x1800231cc  mov     rdi, r9
0x1800231cf  mov     [rsp+540h+var_508], r13
0x1800231d4  mov     r14, r8
0x1800231d7  mov     [rsp+540h+var_510], r13
0x1800231dc  mov     rbx, rdx
0x1800231df  mov     [rsp+540h+var_500], r13d
0x1800231e4  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800231ea  mov     r12d, 200h
0x1800231f0  lea     rcx, [rbp+440h+var_450]; void *
0x1800231f4  mov     r8d, r12d; Size
0x1800231f7  xor     edx, edx; Val
0x1800231f9  call    memset_0
0x1800231fe  mov     r15d, 100h
0x180023204  lea     rdx, [rbp+440h+var_450]
0x180023208  mov     r8d, r15d
0x18002320b  lea     rcx, [rbp+440h+var_488]
0x18002320f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180023215  mov     r8d, r12d; Size
0x180023218  lea     rcx, [rbp+440h+var_250]; void *
0x18002321f  xor     edx, edx; Val
0x180023221  call    memset_0
0x180023226  mov     r8d, r15d
0x180023229  lea     rdx, [rbp+440h+var_250]
0x180023230  lea     rcx, [rbp+440h+var_4C0]
0x180023234  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002323a  test    rbx, rbx
0x18002323d  jz      loc_1800236EB
0x180023243  test    r14, r14
0x180023246  jz      loc_1800236EB
0x18002324c  test    rdi, rdi
0x18002324f  jz      loc_1800236EB
0x180023255  test    rsi, rsi
0x180023258  jz      loc_1800236EB
0x18002325e  mov     rax, [rsi]
0x180023261  lea     rdx, [rsp+540h+var_508]
0x180023266  mov     rcx, rsi
0x180023269  mov     rax, [rax+28h]
0x18002326d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023272  mov     ebx, eax
0x180023274  test    eax, eax
0x180023276  js      loc_1800236F0
0x18002327c  mov     rcx, [rsp+540h+var_508]
0x180023281  lea     rdx, [rsp+540h+var_500]
0x180023286  mov     rax, [rcx]
0x180023289  mov     rax, [rax+48h]
0x18002328d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023292  mov     ebx, eax
0x180023294  test    eax, eax
0x180023296  js      loc_1800236F0
0x18002329c  mov     edx, [rsp+540h+var_500]
0x1800232a0  lea     r15d, [r13+1]
0x1800232a4  mov     edi, r13d
0x1800232a7  test    edx, edx
0x1800232a9  jz      short loc_1800232D9
0x1800232ab  mov     rcx, [rsp+540h+var_508]
0x1800232b0  sub     edx, edi
0x1800232b2  sub     edx, r15d
0x1800232b5  xor     r8d, r8d
0x1800232b8  mov     rax, [rcx]
0x1800232bb  mov     rax, [rax+60h]
0x1800232bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232c4  mov     ebx, eax
0x1800232c6  test    eax, eax
0x1800232c8  js      loc_1800236F0
0x1800232ce  mov     edx, [rsp+540h+var_500]
0x1800232d2  add     edi, r15d
0x1800232d5  cmp     edi, edx
0x1800232d7  jb      short loc_1800232AB
0x1800232d9  mov     rcx, [rsp+540h+var_508]
0x1800232de  lea     r8, [rsp+540h+var_510]
0x1800232e3  lea     rdx, aClear; "clear"
0x1800232ea  mov     rax, [rcx]
0x1800232ed  mov     rax, [rax+30h]
0x1800232f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232f6  mov     ebx, eax
0x1800232f8  test    eax, eax
0x1800232fa  js      loc_1800236F0
0x180023300  mov     rcx, [rsp+540h+var_508]
0x180023305  xor     r9d, r9d
0x180023308  mov     rdx, [rsp+540h+var_510]
0x18002330d  xor     r8d, r8d
0x180023310  mov     rax, [rcx]
0x180023313  mov     rax, [rax+58h]
0x180023317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002331c  mov     ebx, eax
0x18002331e  test    eax, eax
0x180023320  js      loc_1800236F0
0x180023326  mov     rcx, [rsp+540h+var_510]
0x18002332b  mov     rax, [rcx]
0x18002332e  mov     rax, [rax+10h]
0x180023332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023337  lea     rcx, [r14+10h]
0x18002333b  mov     [rsp+540h+var_510], r13
0x180023340  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023346  lea     r9, [rsp+540h+var_4F8]
0x18002334b  mov     r8d, r15d
0x18002334e  mov     edx, r15d
0x180023351  mov     rcx, [rax+18h]
0x180023355  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x18002335b  mov     ebx, eax
0x18002335d  test    eax, eax
0x18002335f  js      loc_1800236F0
0x180023365  lea     rcx, [rsp+540h+var_4F8]
0x18002336a  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180023370  mov     rdi, rax
0x180023373  test    rax, rax
0x180023376  jnz     short loc_180023382
0x180023378  mov     ebx, 8007000Dh
0x18002337d  jmp     loc_1800236F0
0x180023382  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023386  inc     rax
0x180023389  cmp     [rdi+rax*2], r13w
0x18002338e  jnz     short loc_180023386
0x180023390  mov     r14d, 2Ah ; '*'
0x180023396  lea     r15d, [r14+11h]
0x18002339a  cmp     rax, 2
0x18002339e  jb      short loc_1800233B1
0x1800233a0  cmp     [rdi], r14w
0x1800233a4  jnz     short loc_1800233B1
0x1800233a6  cmp     [rdi+2], r15w
0x1800233ab  jnz     short loc_1800233B1
0x1800233ad  add     rdi, 4
0x1800233b1  cmp     [rdi], r13w
0x1800233b5  jz      short loc_180023378
0x1800233b7  mov     rax, [rsi]
0x1800233ba  lea     rdx, aEnabled; "enabled"
0x1800233c1  cmp     word ptr [rdi], 21h ; '!'
0x1800233c5  mov     r8d, r13d
0x1800233c8  mov     rcx, rsi
0x1800233cb  setnz   r8b
0x1800233cf  xor     r9d, r9d
0x1800233d2  mov     rax, [rax+88h]
0x1800233d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233de  mov     ebx, eax
0x1800233e0  test    eax, eax
0x1800233e2  js      loc_1800236F0
0x1800233e8  cmp     word ptr [rdi], 21h ; '!'
0x1800233ec  jz      loc_1800236F0
0x1800233f2  mov     edx, r14d; Ch
0x1800233f5  mov     rcx, rdi; Str
0x1800233f8  call    cs:__imp_wcschr
0x1800233fe  test    rax, rax
0x180023401  jz      loc_18002358E
0x180023407  mov     rbx, rdi
0x18002340a  mov     r12d, 80000000h
0x180023410  mov     edx, r15d; Ch
0x180023413  mov     rcx, rbx; Str
0x180023416  call    cs:__imp_wcschr
0x18002341c  mov     r14, rax
0x18002341f  test    rax, rax
0x180023422  jz      loc_180023378
0x180023428  mov     r8, rax
0x18002342b  lea     rcx, [rbp+440h+var_488]
0x18002342f  sub     r8, rbx
0x180023432  mov     rdx, rbx
0x180023435  sar     r8, 1
0x180023438  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002343e  mov     ebx, eax
0x180023440  test    eax, eax
0x180023442  js      loc_1800236F0
0x180023448  lea     rbx, [r14+2]
0x18002344c  mov     edx, r15d; Ch
0x18002344f  mov     rcx, rbx; Str
0x180023452  call    cs:__imp_wcschr
0x180023458  mov     rdx, rbx
0x18002345b  lea     rcx, [rbp+440h+var_4C0]
0x18002345f  mov     r14, rax
0x180023462  test    rax, rax
0x180023465  jnz     short loc_18002346F
0x180023467  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002346d  jmp     short loc_18002347E
0x18002346f  mov     r8, r14
0x180023472  sub     r8, rbx
0x180023475  sar     r8, 1
0x180023478  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002347e  mov     ebx, eax
0x180023480  test    eax, eax
0x180023482  js      loc_1800236F0
0x180023488  mov     rcx, [rsp+540h+var_508]
0x18002348d  lea     r8, [rsp+540h+var_510]
0x180023492  lea     rdx, aAdd; "add"
0x180023499  mov     rax, [rcx]
0x18002349c  mov     rax, [rax+30h]
0x1800234a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234a5  mov     ebx, eax
0x1800234a7  test    eax, eax
0x1800234a9  js      loc_1800236F0
0x1800234af  mov     rax, [rsp+540h+var_510]
0x1800234b4  mov     rcx, [rax]
0x1800234b7  mov     rbx, [rcx+80h]
0x1800234be  lea     rcx, [rbp+440h+var_488]
0x1800234c2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800234c8  mov     rcx, [rsp+540h+var_510]
0x1800234cd  lea     rdx, aWildcard; "wildcard"
0x1800234d4  mov     r8, rax
0x1800234d7  xor     r9d, r9d
0x1800234da  mov     rax, rbx
0x1800234dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234e2  mov     ebx, eax
0x1800234e4  test    eax, eax
0x1800234e6  js      loc_1800236F0
0x1800234ec  mov     rax, [rsp+540h+var_510]
0x1800234f1  mov     rcx, [rax]
0x1800234f4  mov     rbx, [rcx+80h]
0x1800234fb  lea     rcx, [rbp+440h+var_4C0]
0x1800234ff  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180023505  mov     rcx, [rsp+540h+var_510]
0x18002350a  lea     rdx, aDestination; "destination"
0x180023511  mov     r8, rax
0x180023514  xor     r9d, r9d
0x180023517  mov     rax, rbx
0x18002351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002351f  mov     ebx, eax
0x180023521  test    eax, eax
0x180023523  js      loc_1800236F0
0x180023529  mov     rcx, [rsp+540h+var_508]
0x18002352e  xor     r9d, r9d
0x180023531  mov     rdx, [rsp+540h+var_510]
0x180023536  or      r8d, 0FFFFFFFFh
0x18002353a  mov     rax, [rcx]
0x18002353d  mov     rax, [rax+58h]
0x180023541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023546  mov     ebx, eax
0x180023548  add     eax, r12d
0x18002354b  test    r12d, eax
0x18002354e  jnz     short loc_18002355C
0x180023550  cmp     ebx, 800700B7h
0x180023556  jnz     loc_1800236F0
0x18002355c  mov     rcx, [rsp+540h+var_510]
0x180023561  mov     rax, [rcx]
0x180023564  mov     rax, [rax+10h]
0x180023568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002356d  lea     rax, [r14+2]
0x180023571  mov     [rsp+540h+var_510], r13
0x180023576  neg     r14
0x180023579  sbb     rbx, rbx
0x18002357c  and     rbx, rax
0x18002357f  jnz     loc_180023410
0x180023585  lea     r8, word_18002E968
0x18002358c  jmp     short loc_180023591
0x18002358e  mov     r8, rdi
0x180023591  mov     rax, [rsi]
0x180023594  lea     rdx, aDestination; "destination"
0x18002359b  xor     r9d, r9d
0x18002359e  mov     rcx, rsi
0x1800235a1  mov     rax, [rax+80h]
0x1800235a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235ad  mov     ebx, eax
0x1800235af  test    eax, eax
0x1800235b1  js      loc_1800236F0
0x1800235b7  mov     rdx, rdi
0x1800235ba  lea     rcx, [rsp+540h+var_4F8]
0x1800235bf  mov     r14d, 12Eh
0x1800235c5  mov     r12d, r13d
0x1800235c8  mov     r15d, r13d
0x1800235cb  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800235d1  mov     rbx, rax
0x1800235d4  test    rax, rax
0x1800235d7  jz      loc_180023681
0x1800235dd  mov     edi, 1
0x1800235e2  lea     rdx, aChildOnly_0; "CHILD_ONLY"
0x1800235e9  mov     rcx, rbx; String1
0x1800235ec  call    cs:__imp__wcsicmp
0x1800235f2  test    eax, eax
0x1800235f4  jnz     short loc_1800235FB
0x1800235f6  mov     r15d, edi
0x1800235f9  jmp     short loc_180023667
0x1800235fb  lea     rdx, aExactDestinati_0; "EXACT_DESTINATION"
0x180023602  mov     rcx, rbx; String1
0x180023605  call    cs:__imp__wcsicmp
0x18002360b  test    eax, eax
0x18002360d  jnz     short loc_180023614
0x18002360f  mov     r12d, edi
0x180023612  jmp     short loc_180023667
0x180023614  lea     rdx, aTemporary_0; "TEMPORARY"
0x18002361b  mov     rcx, rbx; String1
0x18002361e  call    cs:__imp__wcsicmp
0x180023624  test    eax, eax
0x180023626  jnz     short loc_180023630
0x180023628  mov     r14d, 133h
0x18002362e  jmp     short loc_180023667
0x180023630  lea     rdx, aPermanent; "PERMANENT"
0x180023637  mov     rcx, rbx; String1
0x18002363a  call    cs:__imp__wcsicmp
  ... truncated ...
```
