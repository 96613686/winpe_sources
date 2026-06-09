# PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180024260`
- end: `0x18002459a`
- name: `?SetConfigProperties@PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `826`
- prototype: `__int64 __fastcall(PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x180002990`
- `0x1800029d0`
- `0x18000341a`
- `0x180003460`
- `0x180024260`
- `0x180029af8`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800243f2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800243f2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800243db`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800243db`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800242d5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800242d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024569`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024569`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002443c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002443c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002440e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002440e`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800242af`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800242af`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180024573`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180024573`

## pseudocode

```c
__int64 __fastcall PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER::SetConfigProperties(
        PERIODIC_RESTART_SCHEDULE_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v8; // ebx
  unsigned int v9; // edx
  int v10; // edi
  const unsigned __int16 *i; // rsi
  _QWORD *v12; // rax
  _QWORD *v13; // rdi
  unsigned __int16 *Str; // rax
  int v15; // eax
  __int64 v16; // rax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v23[256]; // [rsp+C0h] [rbp-40h] BYREF

  v19 = 0;
  v18 = 0;
  v20 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v22);
  memset_0(v23, 0, sizeof(v23));
  STRU::STRU((STRU *)v21, v23, 0x100u);
  if ( a2 && a3 && a4 && a5 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v19);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 72LL))(v19, &v20);
      if ( v8 >= 0 )
      {
        v9 = v20;
        v10 = 0;
        if ( v20 )
        {
          while ( 1 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 96LL))(v19, v9 - v10 - 1, 0);
            if ( v8 < 0 )
              break;
            v9 = v20;
            if ( ++v10 >= v20 )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v19 + 48LL))(
                 v19,
                 L"clear",
                 &v18);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 88LL))(v19, v18, 0, 0);
            if ( v8 >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              v18 = 0;
              for ( i = (const unsigned __int16 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16))
                                                  + 3); *i; i += v16 + 1 )
              {
                v8 = STRU::Copy((STRU *)v21, i);
                if ( v8 < 0 )
                  break;
                v8 = STRU::Append((STRU *)v21, L":00");
                if ( v8 < 0 )
                  break;
                v12 = operator new(8u);
                v13 = v12;
                if ( !v12 )
                {
                  v8 = -2147024888;
                  break;
                }
                *v12 = 0;
                Str = STRU::QueryStr((STRU *)v21);
                v8 = TIMESPAN_PARSER::ParseFromString(v13, Str, 0, 0);
                if ( v8 < 0
                  || (v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v19 + 48LL))(
                             v19,
                             L"add",
                             &v18),
                      v8 < 0)
                  || (v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v18 + 144LL))(
                             v18,
                             L"value",
                             *v13,
                             0),
                      v8 < 0) )
                {
LABEL_27:
                  operator delete(v13);
                  break;
                }
                v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v19 + 88LL))(
                        v19,
                        v18,
                        0xFFFFFFFFLL,
                        0);
                v8 = v15;
                if ( v15 < 0 )
                {
                  if ( v15 != -2147024713 )
                    goto LABEL_27;
                  v8 = 0;
                }
                operator delete(v13);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                v16 = -1;
                v18 = 0;
                do
                  ++v16;
                while ( i[v16] );
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  STRU::~STRU((STRU *)v21);
  MULTISZ::~MULTISZ((MULTISZ *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024260  push    rbp
0x180024262  push    rbx
0x180024263  push    rsi
0x180024264  push    rdi
0x180024265  push    r14
0x180024267  push    r15
0x180024269  lea     rbp, [rsp-1D8h]
0x180024271  sub     rsp, 2D8h
0x180024278  mov     rax, cs:__security_cookie
0x18002427f  xor     rax, rsp
0x180024282  mov     [rbp+200h+var_40], rax
0x180024289  mov     rdi, [rbp+200h+arg_20]
0x180024290  lea     rcx, [rbp+200h+var_280]
0x180024294  xor     r15d, r15d
0x180024297  mov     rsi, r9
0x18002429a  mov     [rsp+300h+var_2C8], r15
0x18002429f  mov     r14, r8
0x1800242a2  mov     [rsp+300h+var_2D0], r15
0x1800242a7  mov     rbx, rdx
0x1800242aa  mov     [rsp+300h+var_2C0], r15d
0x1800242af  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800242b5  xor     edx, edx; Val
0x1800242b7  lea     rcx, [rbp+200h+var_240]; void *
0x1800242bb  mov     r8d, 200h; Size
0x1800242c1  call    memset_0
0x1800242c6  mov     r8d, 100h
0x1800242cc  lea     rdx, [rbp+200h+var_240]
0x1800242d0  lea     rcx, [rsp+300h+var_2B8]
0x1800242d5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800242db  test    rbx, rbx
0x1800242de  jz      loc_180024529
0x1800242e4  test    r14, r14
0x1800242e7  jz      loc_180024529
0x1800242ed  test    rsi, rsi
0x1800242f0  jz      loc_180024529
0x1800242f6  test    rdi, rdi
0x1800242f9  jz      loc_180024529
0x1800242ff  mov     rax, [rdi]
0x180024302  lea     rdx, [rsp+300h+var_2C8]
0x180024307  mov     rcx, rdi
0x18002430a  mov     rax, [rax+28h]
0x18002430e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024313  mov     ebx, eax
0x180024315  test    eax, eax
0x180024317  js      loc_18002452E
0x18002431d  mov     rcx, [rsp+300h+var_2C8]
0x180024322  lea     rdx, [rsp+300h+var_2C0]
0x180024327  mov     rax, [rcx]
0x18002432a  mov     rax, [rax+48h]
0x18002432e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024333  mov     ebx, eax
0x180024335  test    eax, eax
0x180024337  js      loc_18002452E
0x18002433d  mov     edx, [rsp+300h+var_2C0]
0x180024341  mov     edi, r15d
0x180024344  test    edx, edx
0x180024346  jz      short loc_180024374
0x180024348  mov     rcx, [rsp+300h+var_2C8]
0x18002434d  sub     edx, edi
0x18002434f  dec     edx
0x180024351  xor     r8d, r8d
0x180024354  mov     rax, [rcx]
0x180024357  mov     rax, [rax+60h]
0x18002435b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024360  mov     ebx, eax
0x180024362  test    eax, eax
0x180024364  js      loc_18002452E
0x18002436a  mov     edx, [rsp+300h+var_2C0]
0x18002436e  inc     edi
0x180024370  cmp     edi, edx
0x180024372  jb      short loc_180024348
0x180024374  mov     rcx, [rsp+300h+var_2C8]
0x180024379  lea     r8, [rsp+300h+var_2D0]
0x18002437e  lea     rdx, aClear; "clear"
0x180024385  mov     rax, [rcx]
0x180024388  mov     rax, [rax+30h]
0x18002438c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024391  mov     ebx, eax
0x180024393  test    eax, eax
0x180024395  js      loc_18002452E
0x18002439b  mov     rcx, [rsp+300h+var_2C8]
0x1800243a0  xor     r9d, r9d
0x1800243a3  mov     rdx, [rsp+300h+var_2D0]
0x1800243a8  xor     r8d, r8d
0x1800243ab  mov     rax, [rcx]
0x1800243ae  mov     rax, [rax+58h]
0x1800243b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243b7  mov     ebx, eax
0x1800243b9  test    eax, eax
0x1800243bb  js      loc_18002452E
0x1800243c1  mov     rcx, [rsp+300h+var_2D0]
0x1800243c6  mov     rax, [rcx]
0x1800243c9  mov     rax, [rax+10h]
0x1800243cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243d2  lea     rcx, [r14+10h]
0x1800243d6  mov     [rsp+300h+var_2D0], r15
0x1800243db  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800243e1  mov     rsi, [rax+18h]
0x1800243e5  jmp     loc_18002450C
0x1800243ea  mov     rdx, rsi
0x1800243ed  lea     rcx, [rsp+300h+var_2B8]
0x1800243f2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800243f8  mov     ebx, eax
0x1800243fa  test    eax, eax
0x1800243fc  js      loc_18002452E
0x180024402  lea     rdx, a00; ":00"
0x180024409  lea     rcx, [rsp+300h+var_2B8]
0x18002440e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180024414  mov     ebx, eax
0x180024416  test    eax, eax
0x180024418  js      loc_18002452E
0x18002441e  mov     ecx, 8; Size
0x180024423  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024428  mov     rdi, rax
0x18002442b  test    rax, rax
0x18002442e  jz      loc_180024522
0x180024434  lea     rcx, [rsp+300h+var_2B8]
0x180024439  mov     [rax], r15
0x18002443c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180024442  xor     r9d, r9d
0x180024445  xor     r8d, r8d
0x180024448  mov     rdx, rax
0x18002444b  mov     rcx, rdi
0x18002444e  call    ?ParseFromString@TIMESPAN_PARSER@@QEAAJPEBGW4TIMESPAN_FORMAT@@H@Z; TIMESPAN_PARSER::ParseFromString(ushort const *,TIMESPAN_FORMAT,int)
0x180024453  mov     ebx, eax
0x180024455  test    eax, eax
0x180024457  js      loc_180024518
0x18002445d  mov     rcx, [rsp+300h+var_2C8]
0x180024462  lea     r8, [rsp+300h+var_2D0]
0x180024467  lea     rdx, aAdd; "add"
0x18002446e  mov     rax, [rcx]
0x180024471  mov     rax, [rax+30h]
0x180024475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002447a  mov     ebx, eax
0x18002447c  test    eax, eax
0x18002447e  js      loc_180024518
0x180024484  mov     rcx, [rsp+300h+var_2D0]
0x180024489  lea     rdx, aValue; "value"
0x180024490  mov     r8, [rdi]
0x180024493  xor     r9d, r9d
0x180024496  mov     rax, [rcx]
0x180024499  mov     rax, [rax+90h]
0x1800244a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244a5  mov     ebx, eax
0x1800244a7  test    eax, eax
0x1800244a9  js      short loc_180024518
0x1800244ab  mov     rcx, [rsp+300h+var_2C8]
0x1800244b0  xor     r9d, r9d
0x1800244b3  mov     rdx, [rsp+300h+var_2D0]
0x1800244b8  or      r8d, 0FFFFFFFFh
0x1800244bc  mov     rax, [rcx]
0x1800244bf  mov     rax, [rax+58h]
0x1800244c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244c8  mov     ebx, eax
0x1800244ca  test    eax, eax
0x1800244cc  jns     short loc_1800244D8
0x1800244ce  cmp     eax, 800700B7h
0x1800244d3  jnz     short loc_180024518
0x1800244d5  mov     ebx, r15d
0x1800244d8  mov     rcx, rdi; Block
0x1800244db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800244e0  mov     rcx, [rsp+300h+var_2D0]
0x1800244e5  mov     rax, [rcx]
0x1800244e8  mov     rax, [rax+10h]
0x1800244ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800244f5  mov     [rsp+300h+var_2D0], r15
0x1800244fa  inc     rax
0x1800244fd  cmp     [rsi+rax*2], r15w
0x180024502  jnz     short loc_1800244FA
0x180024504  lea     rsi, [rsi+rax*2]
0x180024508  add     rsi, 2
0x18002450c  cmp     [rsi], r15w
0x180024510  jnz     loc_1800243EA
0x180024516  jmp     short loc_18002452E
0x180024518  mov     rcx, rdi; Block
0x18002451b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024520  jmp     short loc_18002452E
0x180024522  mov     ebx, 80070008h
0x180024527  jmp     short loc_18002452E
0x180024529  mov     ebx, 80070057h
0x18002452e  mov     rcx, [rsp+300h+var_2C8]
0x180024533  test    rcx, rcx
0x180024536  jz      short loc_180024549
0x180024538  mov     rax, [rcx]
0x18002453b  mov     rax, [rax+10h]
0x18002453f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024544  mov     [rsp+300h+var_2C8], r15
0x180024549  mov     rcx, [rsp+300h+var_2D0]
0x18002454e  test    rcx, rcx
0x180024551  jz      short loc_180024564
0x180024553  mov     rax, [rcx]
0x180024556  mov     rax, [rax+10h]
0x18002455a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002455f  mov     [rsp+300h+var_2D0], r15
0x180024564  lea     rcx, [rsp+300h+var_2B8]
0x180024569  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002456f  lea     rcx, [rbp+200h+var_280]
0x180024573  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180024579  mov     eax, ebx
0x18002457b  mov     rcx, [rbp+200h+var_40]
0x180024582  xor     rcx, rsp; StackCookie
0x180024585  call    __security_check_cookie
0x18002458a  add     rsp, 2D8h
0x180024591  pop     r15
0x180024593  pop     r14
0x180024595  pop     rdi
0x180024596  pop     rsi
0x180024597  pop     rbx
0x180024598  pop     rbp
0x180024599  retn
```
