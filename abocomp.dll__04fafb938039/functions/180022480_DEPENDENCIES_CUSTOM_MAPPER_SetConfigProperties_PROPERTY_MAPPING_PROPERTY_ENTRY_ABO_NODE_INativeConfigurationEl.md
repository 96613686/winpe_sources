# DEPENDENCIES_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180022480`
- end: `0x18002294e`
- name: `?SetConfigProperties@DEPENDENCIES_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `1230`
- prototype: `__int64 __fastcall(DEPENDENCIES_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180022480`
- `0x18002c010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800225ea`
- `msvcrt!wcschr` at `0x180022639`
- `msvcrt!wcschr` at `0x1800225ea`
- `msvcrt!wcschr` at `0x180022639`
- `msvcrt!iswspace` at `0x180022629`
- `msvcrt!iswspace` at `0x180022629`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002265f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002265f`
- `iisutil!SplitCommaDelimitedString` at `0x180022728`
- `iisutil!SplitCommaDelimitedString` at `0x180022728`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180022809`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180022809`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002275d`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002275d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800225d3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800225d3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800224f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002251f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800224f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002251f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002291d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022927`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002291d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022927`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800226a9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800226e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800226a9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800226e6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002260c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180022657`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002260c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180022657`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002252a`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002252a`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180022913`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180022913`

## pseudocode

```c
__int64 __fastcall DEPENDENCIES_CUSTOM_MAPPER::SetConfigProperties(
        DEPENDENCIES_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v8; // ebx
  unsigned int v9; // edx
  int v10; // edi
  const wchar_t *i; // rdi
  wchar_t *v12; // rax
  wchar_t *v13; // rsi
  wint_t *j; // rbx
  wchar_t *v15; // rax
  wchar_t *v16; // rsi
  int v17; // eax
  __int64 (__fastcall *v18)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  __int64 (__fastcall *v20)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *v21; // rax
  const unsigned __int16 *k; // rax
  const unsigned __int16 *v23; // rsi
  int v24; // eax
  __int64 v25; // rax
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v33[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[56]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v35[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v36[256]; // [rsp+300h] [rbp+200h] BYREF

  v27 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  memset_0(v35, 0, sizeof(v35));
  STRU::STRU((STRU *)v34, v35, 0x100u);
  memset_0(v36, 0, sizeof(v36));
  STRU::STRU((STRU *)v33, v36, 0x100u);
  MULTISZ::MULTISZ((MULTISZ *)v32);
  if ( a2 && a3 && a4 && a5 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v30);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v30 + 72LL))(v30, &v28);
      if ( v8 >= 0 )
      {
        v9 = v28;
        v10 = 0;
        if ( v28 )
        {
          while ( 1 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 96LL))(v30, v9 - v10 - 1, 0);
            if ( v8 < 0 )
              break;
            v9 = v28;
            if ( ++v10 >= v28 )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          for ( i = (const wchar_t *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
                *i;
                i += v25 + 1 )
          {
            v12 = wcschr(i, 0x3Bu);
            v13 = v12;
            if ( !v12 )
            {
              v8 = -2147024883;
              break;
            }
            v8 = STRU::Copy((STRU *)v34, i, v12 - i);
            if ( v8 < 0 )
              break;
            for ( j = v13 + 1; iswspace(*j); ++j )
              ;
            v15 = wcschr(j, 0x2Cu);
            v16 = v15;
            v17 = v15 ? STRU::Copy((STRU *)v33, j, v15 - j) : STRU::Copy((STRU *)v33, j);
            v8 = v17;
            if ( v17 < 0 )
              break;
            v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v30 + 48LL))(
                   v30,
                   L"application",
                   &v27);
            if ( v8 < 0 )
              break;
            v18 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v27 + 128LL);
            Str = STRU::QueryStr((STRU *)v34);
            v8 = v18(v27, L"name", Str, 0);
            if ( v8 < 0 )
              break;
            v20 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v27 + 128LL);
            v21 = STRU::QueryStr((STRU *)v33);
            v8 = v20(v27, L"groupId", v21, 0);
            if ( v8 < 0 )
              break;
            if ( v16 )
            {
              v8 = SplitCommaDelimitedString(v16 + 1, 1, 1, (struct MULTISZ *)v32);
              if ( v8 < 0 )
                break;
              v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 40LL))(v27, &v31);
              if ( v8 < 0 )
                break;
              for ( k = MULTISZ::First((MULTISZ *)v32); ; k = MULTISZ::Next((MULTISZ *)v32, v23) )
              {
                v23 = k;
                if ( !k )
                  break;
                v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v31 + 48LL))(
                       v31,
                       L"add",
                       &v29);
                if ( v8 < 0 )
                  goto LABEL_44;
                v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v29 + 128LL))(
                       v29,
                       L"groupId",
                       v23,
                       0);
                if ( v8 < 0 )
                  goto LABEL_44;
                v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v31 + 56LL))(
                       v31,
                       v29,
                       0xFFFFFFFFLL,
                       0);
                if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147024713 )
                  goto LABEL_44;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                v29 = 0;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              v31 = 0;
            }
            v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v30 + 88LL))(
                    v30,
                    v27,
                    0xFFFFFFFFLL,
                    0);
            v8 = v24;
            if ( v24 < 0 )
            {
              if ( v24 != -2147024713 )
                break;
              v8 = 0;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            v25 = -1;
            v27 = 0;
            do
              ++v25;
            while ( i[v25] );
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_44:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v32);
  STRU::~STRU((STRU *)v33);
  STRU::~STRU((STRU *)v34);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022480  push    rbp
0x180022482  push    rbx
0x180022483  push    rsi
0x180022484  push    rdi
0x180022485  push    r13
0x180022487  push    r14
0x180022489  lea     rbp, [rsp-418h]
0x180022491  sub     rsp, 518h
0x180022498  mov     rax, cs:__security_cookie
0x18002249f  xor     rax, rsp
0x1800224a2  mov     [rbp+440h+var_40], rax
0x1800224a9  mov     rdi, [rbp+440h+arg_20]
0x1800224b0  lea     rcx, [rbp+440h+var_440]; void *
0x1800224b4  xor     r13d, r13d
0x1800224b7  mov     rsi, r8
0x1800224ba  mov     rbx, rdx
0x1800224bd  mov     [rsp+540h+var_510], r13
0x1800224c2  xor     edx, edx; Val
0x1800224c4  mov     [rsp+540h+var_500], r13
0x1800224c9  mov     r8d, 200h; Size
0x1800224cf  mov     [rsp+540h+var_4F8], r13
0x1800224d4  mov     [rsp+540h+var_4F0], r13
0x1800224d9  mov     r14, r9
0x1800224dc  mov     [rsp+540h+var_508], r13d
0x1800224e1  call    memset_0
0x1800224e6  mov     r8d, 100h
0x1800224ec  lea     rdx, [rbp+440h+var_440]
0x1800224f0  lea     rcx, [rbp+440h+var_478]
0x1800224f4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800224fa  xor     edx, edx; Val
0x1800224fc  lea     rcx, [rbp+440h+var_240]; void *
0x180022503  mov     r8d, 200h; Size
0x180022509  call    memset_0
0x18002250e  mov     r8d, 100h
0x180022514  lea     rdx, [rbp+440h+var_240]
0x18002251b  lea     rcx, [rbp+440h+var_4B0]
0x18002251f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022525  lea     rcx, [rsp+540h+var_4E8]
0x18002252a  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180022530  test    rbx, rbx
0x180022533  jz      loc_18002289D
0x180022539  test    rsi, rsi
0x18002253c  jz      loc_18002289D
0x180022542  test    r14, r14
0x180022545  jz      loc_18002289D
0x18002254b  test    rdi, rdi
0x18002254e  jz      loc_18002289D
0x180022554  mov     rax, [rdi]
0x180022557  lea     rdx, [rsp+540h+var_4F8]
0x18002255c  mov     rcx, rdi
0x18002255f  mov     rax, [rax+28h]
0x180022563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022568  mov     ebx, eax
0x18002256a  test    eax, eax
0x18002256c  js      loc_1800228A2
0x180022572  mov     rcx, [rsp+540h+var_4F8]
0x180022577  lea     rdx, [rsp+540h+var_508]
0x18002257c  mov     rax, [rcx]
0x18002257f  mov     rax, [rax+48h]
0x180022583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022588  mov     ebx, eax
0x18002258a  test    eax, eax
0x18002258c  js      loc_1800228A2
0x180022592  mov     edx, [rsp+540h+var_508]
0x180022596  lea     r14d, [r13+1]
0x18002259a  mov     edi, r13d
0x18002259d  test    edx, edx
0x18002259f  jz      short loc_1800225CF
0x1800225a1  mov     rcx, [rsp+540h+var_4F8]
0x1800225a6  sub     edx, edi
0x1800225a8  sub     edx, r14d
0x1800225ab  xor     r8d, r8d
0x1800225ae  mov     rax, [rcx]
0x1800225b1  mov     rax, [rax+60h]
0x1800225b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225ba  mov     ebx, eax
0x1800225bc  test    eax, eax
0x1800225be  js      loc_1800228A2
0x1800225c4  mov     edx, [rsp+540h+var_508]
0x1800225c8  add     edi, r14d
0x1800225cb  cmp     edi, edx
0x1800225cd  jb      short loc_1800225A1
0x1800225cf  lea     rcx, [rsi+10h]
0x1800225d3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800225d9  mov     rdi, [rax+18h]
0x1800225dd  jmp     loc_18002288A
0x1800225e2  mov     edx, 3Bh ; ';'; Ch
0x1800225e7  mov     rcx, rdi; Str
0x1800225ea  call    cs:__imp_wcschr
0x1800225f0  mov     rsi, rax
0x1800225f3  test    rax, rax
0x1800225f6  jz      loc_180022896
0x1800225fc  mov     r8, rax
0x1800225ff  lea     rcx, [rbp+440h+var_478]
0x180022603  sub     r8, rdi
0x180022606  mov     rdx, rdi
0x180022609  sar     r8, 1
0x18002260c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180022612  mov     ebx, eax
0x180022614  test    eax, eax
0x180022616  js      loc_1800228A2
0x18002261c  lea     rbx, [rsi+2]
0x180022620  jmp     short loc_180022626
0x180022622  add     rbx, 2
0x180022626  movzx   ecx, word ptr [rbx]; C
0x180022629  call    cs:__imp_iswspace
0x18002262f  test    eax, eax
0x180022631  jnz     short loc_180022622
0x180022633  lea     edx, [rax+2Ch]; Ch
0x180022636  mov     rcx, rbx; Str
0x180022639  call    cs:__imp_wcschr
0x18002263f  mov     rdx, rbx
0x180022642  lea     rcx, [rbp+440h+var_4B0]
0x180022646  mov     rsi, rax
0x180022649  test    rax, rax
0x18002264c  jz      short loc_18002265F
0x18002264e  mov     r8, rax
0x180022651  sub     r8, rbx
0x180022654  sar     r8, 1
0x180022657  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002265d  jmp     short loc_180022665
0x18002265f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180022665  mov     ebx, eax
0x180022667  test    eax, eax
0x180022669  js      loc_1800228A2
0x18002266f  mov     rcx, [rsp+540h+var_4F8]
0x180022674  lea     r8, [rsp+540h+var_510]
0x180022679  lea     rdx, aApplication; "application"
0x180022680  mov     rax, [rcx]
0x180022683  mov     rax, [rax+30h]
0x180022687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002268c  mov     ebx, eax
0x18002268e  test    eax, eax
0x180022690  js      loc_1800228A2
0x180022696  mov     rax, [rsp+540h+var_510]
0x18002269b  mov     rcx, [rax]
0x18002269e  mov     rbx, [rcx+80h]
0x1800226a5  lea     rcx, [rbp+440h+var_478]
0x1800226a9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800226af  mov     rcx, [rsp+540h+var_510]
0x1800226b4  lea     rdx, aName; "name"
0x1800226bb  mov     r8, rax
0x1800226be  xor     r9d, r9d
0x1800226c1  mov     rax, rbx
0x1800226c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226c9  mov     ebx, eax
0x1800226cb  test    eax, eax
0x1800226cd  js      loc_1800228A2
0x1800226d3  mov     rax, [rsp+540h+var_510]
0x1800226d8  mov     rcx, [rax]
0x1800226db  mov     rbx, [rcx+80h]
0x1800226e2  lea     rcx, [rbp+440h+var_4B0]
0x1800226e6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800226ec  mov     rcx, [rsp+540h+var_510]
0x1800226f1  lea     rdx, aGroupid; "groupId"
0x1800226f8  mov     r8, rax
0x1800226fb  xor     r9d, r9d
0x1800226fe  mov     rax, rbx
0x180022701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022706  mov     ebx, eax
0x180022708  test    eax, eax
0x18002270a  js      loc_1800228A2
0x180022710  test    rsi, rsi
0x180022713  jz      loc_180022831
0x180022719  lea     rcx, [rsi+2]
0x18002271d  mov     r8d, r14d
0x180022720  lea     r9, [rsp+540h+var_4E8]
0x180022725  mov     edx, r14d
0x180022728  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x18002272e  mov     ebx, eax
0x180022730  test    eax, eax
0x180022732  js      loc_1800228A2
0x180022738  mov     rcx, [rsp+540h+var_510]
0x18002273d  lea     rdx, [rsp+540h+var_4F0]
0x180022742  mov     rax, [rcx]
0x180022745  mov     rax, [rax+28h]
0x180022749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002274e  mov     ebx, eax
0x180022750  test    eax, eax
0x180022752  js      loc_1800228A2
0x180022758  lea     rcx, [rsp+540h+var_4E8]
0x18002275d  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180022763  jmp     loc_18002280F
0x180022768  mov     rdx, [rcx]
0x18002276b  lea     r8, [rsp+540h+var_500]
0x180022770  mov     rax, [rdx+30h]
0x180022774  lea     rdx, aAdd; "add"
0x18002277b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022780  mov     ebx, eax
0x180022782  test    eax, eax
0x180022784  js      loc_1800228A2
0x18002278a  mov     rcx, [rsp+540h+var_500]
0x18002278f  lea     rdx, aGroupid; "groupId"
0x180022796  xor     r9d, r9d
0x180022799  mov     r8, rsi
0x18002279c  mov     rax, [rcx]
0x18002279f  mov     rax, [rax+80h]
0x1800227a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ab  mov     ebx, eax
0x1800227ad  test    eax, eax
0x1800227af  js      loc_1800228A2
0x1800227b5  mov     rcx, [rsp+540h+var_4F0]
0x1800227ba  xor     r9d, r9d
0x1800227bd  mov     rdx, [rsp+540h+var_500]
0x1800227c2  or      r8d, 0FFFFFFFFh
0x1800227c6  mov     rax, [rcx]
0x1800227c9  mov     rax, [rax+38h]
0x1800227cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227d2  mov     ecx, 80000000h
0x1800227d7  mov     ebx, eax
0x1800227d9  add     eax, ecx
0x1800227db  test    ecx, eax
0x1800227dd  jnz     short loc_1800227EB
0x1800227df  cmp     ebx, 800700B7h
0x1800227e5  jnz     loc_1800228A2
0x1800227eb  mov     rcx, [rsp+540h+var_500]
0x1800227f0  mov     rax, [rcx]
0x1800227f3  mov     rax, [rax+10h]
0x1800227f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227fc  mov     rdx, rsi
0x1800227ff  mov     [rsp+540h+var_500], r13
0x180022804  lea     rcx, [rsp+540h+var_4E8]
0x180022809  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x18002280f  mov     rcx, [rsp+540h+var_4F0]
0x180022814  mov     rsi, rax
0x180022817  test    rax, rax
0x18002281a  jnz     loc_180022768
0x180022820  mov     rax, [rcx]
0x180022823  mov     rax, [rax+10h]
0x180022827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002282c  mov     [rsp+540h+var_4F0], r13
0x180022831  mov     rcx, [rsp+540h+var_4F8]
0x180022836  xor     r9d, r9d
0x180022839  mov     rdx, [rsp+540h+var_510]
0x18002283e  or      r8d, 0FFFFFFFFh
0x180022842  mov     rax, [rcx]
0x180022845  mov     rax, [rax+58h]
0x180022849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002284e  mov     ebx, eax
0x180022850  test    eax, eax
0x180022852  jns     short loc_18002285E
0x180022854  cmp     eax, 800700B7h
0x180022859  jnz     short loc_1800228A2
0x18002285b  mov     ebx, r13d
0x18002285e  mov     rcx, [rsp+540h+var_510]
0x180022863  mov     rax, [rcx]
0x180022866  mov     rax, [rax+10h]
0x18002286a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002286f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022873  mov     [rsp+540h+var_510], r13
0x180022878  inc     rax
0x18002287b  cmp     [rdi+rax*2], r13w
0x180022880  jnz     short loc_180022878
0x180022882  lea     rdi, [rdi+rax*2]
0x180022886  add     rdi, 2
0x18002288a  cmp     [rdi], r13w
0x18002288e  jnz     loc_1800225E2
0x180022894  jmp     short loc_1800228A2
0x180022896  mov     ebx, 8007000Dh
0x18002289b  jmp     short loc_1800228A2
0x18002289d  mov     ebx, 80070057h
0x1800228a2  mov     rcx, [rsp+540h+var_500]
0x1800228a7  test    rcx, rcx
0x1800228aa  jz      short loc_1800228BD
0x1800228ac  mov     rax, [rcx]
0x1800228af  mov     rax, [rax+10h]
0x1800228b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228b8  mov     [rsp+540h+var_500], r13
0x1800228bd  mov     rcx, [rsp+540h+var_510]
0x1800228c2  test    rcx, rcx
0x1800228c5  jz      short loc_1800228D8
0x1800228c7  mov     rax, [rcx]
0x1800228ca  mov     rax, [rax+10h]
0x1800228ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228d3  mov     [rsp+540h+var_510], r13
0x1800228d8  mov     rcx, [rsp+540h+var_4F8]
0x1800228dd  test    rcx, rcx
0x1800228e0  jz      short loc_1800228F3
0x1800228e2  mov     rax, [rcx]
0x1800228e5  mov     rax, [rax+10h]
0x1800228e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228ee  mov     [rsp+540h+var_4F8], r13
0x1800228f3  mov     rcx, [rsp+540h+var_4F0]
0x1800228f8  test    rcx, rcx
0x1800228fb  jz      short loc_18002290E
0x1800228fd  mov     rax, [rcx]
0x180022900  mov     rax, [rax+10h]
0x180022904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022909  mov     [rsp+540h+var_4F0], r13
0x18002290e  lea     rcx, [rsp+540h+var_4E8]
0x180022913  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180022919  lea     rcx, [rbp+440h+var_4B0]
0x18002291d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022923  lea     rcx, [rbp+440h+var_478]
0x180022927  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002292d  mov     eax, ebx
0x18002292f  mov     rcx, [rbp+440h+var_40]
0x180022936  xor     rcx, rsp; StackCookie
0x180022939  call    __security_check_cookie
0x18002293e  add     rsp, 518h
  ... truncated ...
```
