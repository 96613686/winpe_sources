# DEFAULT_LOAD_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180022190`
- end: `0x180022476`
- name: `?SetConfigProperties@DEFAULT_LOAD_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `742`
- prototype: `__int64 __fastcall(DEFAULT_LOAD_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003460`
- `0x180022190`
- `0x18002c010`

## import_xrefs

- `iisutil!SplitCommaDelimitedString` at `0x18002231c`
- `iisutil!SplitCommaDelimitedString` at `0x18002231c`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800223cf`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800223cf`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180022330`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180022330`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022309`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022309`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800221c9`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800221c9`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002244a`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18002244a`

## pseudocode

```c
__int64 __fastcall DEFAULT_LOAD_CUSTOM_MAPPER::SetConfigProperties(
        DEFAULT_LOAD_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // ebx
  unsigned int v11; // edx
  int v12; // edi
  const unsigned __int16 **Ptr; // rax
  const unsigned __int16 *i; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdi
  __int64 v18; // [rsp+30h] [rbp-21h] BYREF
  __int64 v19; // [rsp+38h] [rbp-19h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-11h] BYREF
  __int64 v21; // [rsp+48h] [rbp-9h] BYREF
  _BYTE v22[56]; // [rsp+50h] [rbp-1h] BYREF

  MULTISZ::MULTISZ((MULTISZ *)v22);
  v8 = 0;
  v19 = 0;
  v9 = 0;
  v20 = 0;
  v18 = 0;
  v21 = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a5 + 32LL))(
            a5,
            L"files",
            &v21);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 40LL))(v21, &v19);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 72LL))(v19, &v20);
        if ( v10 >= 0 )
        {
          v11 = v20;
          v12 = 0;
          if ( v20 )
          {
            while ( 1 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 96LL))(v19, v11 - v12 - 1, 0);
              if ( v10 < 0 )
                break;
              v11 = v20;
              if ( ++v12 >= v20 )
                goto LABEL_11;
            }
          }
          else
          {
LABEL_11:
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v19 + 48LL))(
                    v19,
                    L"clear",
                    &v18);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 88LL))(
                      v19,
                      v18,
                      0,
                      0);
              if ( v10 >= 0 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                v18 = 0;
                Ptr = (const unsigned __int16 **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16));
                v10 = SplitCommaDelimitedString(Ptr[3], 1, 1, (struct MULTISZ *)v22);
                if ( v10 >= 0 )
                {
                  for ( i = MULTISZ::First((MULTISZ *)v22); ; i = MULTISZ::Next((MULTISZ *)v22, v16) )
                  {
                    v16 = i;
                    if ( !i )
                      break;
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v19 + 48LL))(
                            v19,
                            L"add",
                            &v18);
                    if ( v10 < 0 )
                      break;
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v18 + 128LL))(
                            v18,
                            L"value",
                            v16,
                            0);
                    if ( v10 < 0 )
                      break;
                    v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v19 + 88LL))(
                            v19,
                            v18,
                            0xFFFFFFFFLL,
                            0);
                    v10 = v15;
                    if ( v15 < 0 )
                    {
                      if ( v15 != -2147024713 )
                        break;
                      v10 = 0;
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                    v18 = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
    v8 = v18;
    v9 = v21;
  }
  else
  {
    v10 = -2147024809;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v8 = v18;
    v21 = 0;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022190  mov     [rsp-8+arg_0], rbx
0x180022195  mov     [rsp-8+arg_8], rsi
0x18002219a  push    rbp
0x18002219b  push    rdi
0x18002219c  push    r14
0x18002219e  lea     rbp, [rsp-3Fh]
0x1800221a3  sub     rsp, 90h
0x1800221aa  mov     rax, cs:__security_cookie
0x1800221b1  xor     rax, rsp
0x1800221b4  mov     [rbp+4Fh+var_18], rax
0x1800221b8  mov     rdi, [rbp+4Fh+arg_20]
0x1800221bc  lea     rcx, [rbp+4Fh+var_50]
0x1800221c0  mov     rsi, r9
0x1800221c3  mov     r14, r8
0x1800221c6  mov     rbx, rdx
0x1800221c9  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800221cf  xor     ecx, ecx
0x1800221d1  mov     [rbp+4Fh+var_68], 0
0x1800221d9  xor     edx, edx
0x1800221db  mov     [rbp+4Fh+var_60], 0
0x1800221e2  mov     [rbp+4Fh+var_70], rcx
0x1800221e6  mov     [rbp+4Fh+var_58], rdx
0x1800221ea  test    rbx, rbx
0x1800221ed  jz      loc_1800223EB
0x1800221f3  test    r14, r14
0x1800221f6  jz      loc_1800223EB
0x1800221fc  test    rsi, rsi
0x1800221ff  jz      loc_1800223EB
0x180022205  test    rdi, rdi
0x180022208  jz      loc_1800223EB
0x18002220e  mov     rax, [rdi]
0x180022211  lea     r8, [rbp+4Fh+var_58]
0x180022215  lea     rdx, aFiles; "files"
0x18002221c  mov     rcx, rdi
0x18002221f  mov     rax, [rax+20h]
0x180022223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022228  mov     ebx, eax
0x18002222a  test    eax, eax
0x18002222c  js      loc_1800223E1
0x180022232  mov     rcx, [rbp+4Fh+var_58]
0x180022236  lea     rdx, [rbp+4Fh+var_68]
0x18002223a  mov     rax, [rcx]
0x18002223d  mov     rax, [rax+28h]
0x180022241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022246  mov     ebx, eax
0x180022248  test    eax, eax
0x18002224a  js      loc_1800223E1
0x180022250  mov     rcx, [rbp+4Fh+var_68]
0x180022254  lea     rdx, [rbp+4Fh+var_60]
0x180022258  mov     rax, [rcx]
0x18002225b  mov     rax, [rax+48h]
0x18002225f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022264  mov     ebx, eax
0x180022266  test    eax, eax
0x180022268  js      loc_1800223E1
0x18002226e  mov     edx, [rbp+4Fh+var_60]
0x180022271  xor     edi, edi
0x180022273  lea     esi, [rdi+1]
0x180022276  test    edx, edx
0x180022278  jz      short loc_1800222A4
0x18002227a  mov     rcx, [rbp+4Fh+var_68]
0x18002227e  sub     edx, edi
0x180022280  sub     edx, esi
0x180022282  xor     r8d, r8d
0x180022285  mov     rax, [rcx]
0x180022288  mov     rax, [rax+60h]
0x18002228c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022291  mov     ebx, eax
0x180022293  test    eax, eax
0x180022295  js      loc_1800223E1
0x18002229b  mov     edx, [rbp+4Fh+var_60]
0x18002229e  add     edi, esi
0x1800222a0  cmp     edi, edx
0x1800222a2  jb      short loc_18002227A
0x1800222a4  mov     rcx, [rbp+4Fh+var_68]
0x1800222a8  lea     r8, [rbp+4Fh+var_70]
0x1800222ac  lea     rdx, aClear; "clear"
0x1800222b3  mov     rax, [rcx]
0x1800222b6  mov     rax, [rax+30h]
0x1800222ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222bf  mov     ebx, eax
0x1800222c1  test    eax, eax
0x1800222c3  js      loc_1800223E1
0x1800222c9  mov     rcx, [rbp+4Fh+var_68]
0x1800222cd  xor     r9d, r9d
0x1800222d0  mov     rdx, [rbp+4Fh+var_70]
0x1800222d4  xor     r8d, r8d
0x1800222d7  mov     rax, [rcx]
0x1800222da  mov     rax, [rax+58h]
0x1800222de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222e3  mov     ebx, eax
0x1800222e5  test    eax, eax
0x1800222e7  js      loc_1800223E1
0x1800222ed  mov     rcx, [rbp+4Fh+var_70]
0x1800222f1  mov     rax, [rcx]
0x1800222f4  mov     rax, [rax+10h]
0x1800222f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222fd  lea     rcx, [r14+10h]
0x180022301  mov     [rbp+4Fh+var_70], 0
0x180022309  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002230f  lea     r9, [rbp+4Fh+var_50]
0x180022313  mov     r8d, esi
0x180022316  mov     edx, esi
0x180022318  mov     rcx, [rax+18h]
0x18002231c  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x180022322  mov     ebx, eax
0x180022324  test    eax, eax
0x180022326  js      loc_1800223E1
0x18002232c  lea     rcx, [rbp+4Fh+var_50]
0x180022330  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180022336  jmp     loc_1800223D5
0x18002233b  mov     rcx, [rbp+4Fh+var_68]
0x18002233f  lea     r8, [rbp+4Fh+var_70]
0x180022343  mov     rdx, [rcx]
0x180022346  mov     rax, [rdx+30h]
0x18002234a  lea     rdx, aAdd; "add"
0x180022351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022356  mov     ebx, eax
0x180022358  test    eax, eax
0x18002235a  js      loc_1800223E1
0x180022360  mov     rcx, [rbp+4Fh+var_70]
0x180022364  lea     rdx, aValue; "value"
0x18002236b  xor     r9d, r9d
0x18002236e  mov     r8, rdi
0x180022371  mov     rax, [rcx]
0x180022374  mov     rax, [rax+80h]
0x18002237b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022380  mov     ebx, eax
0x180022382  test    eax, eax
0x180022384  js      short loc_1800223E1
0x180022386  mov     rcx, [rbp+4Fh+var_68]
0x18002238a  xor     r9d, r9d
0x18002238d  mov     rdx, [rbp+4Fh+var_70]
0x180022391  or      r8d, 0FFFFFFFFh
0x180022395  mov     rax, [rcx]
0x180022398  mov     rax, [rax+58h]
0x18002239c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a1  mov     ebx, eax
0x1800223a3  test    eax, eax
0x1800223a5  jns     short loc_1800223B0
0x1800223a7  cmp     eax, 800700B7h
0x1800223ac  jnz     short loc_1800223E1
0x1800223ae  xor     ebx, ebx
0x1800223b0  mov     rcx, [rbp+4Fh+var_70]
0x1800223b4  mov     rax, [rcx]
0x1800223b7  mov     rax, [rax+10h]
0x1800223bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223c0  mov     rdx, rdi
0x1800223c3  mov     [rbp+4Fh+var_70], 0
0x1800223cb  lea     rcx, [rbp+4Fh+var_50]
0x1800223cf  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800223d5  mov     rdi, rax
0x1800223d8  test    rax, rax
0x1800223db  jnz     loc_18002233B
0x1800223e1  mov     rcx, [rbp+4Fh+var_70]
0x1800223e5  mov     rdx, [rbp+4Fh+var_58]
0x1800223e9  jmp     short loc_1800223F0
0x1800223eb  mov     ebx, 80070057h
0x1800223f0  test    rdx, rdx
0x1800223f3  jz      short loc_180022410
0x1800223f5  mov     rax, [rdx]
0x1800223f8  mov     rcx, rdx
0x1800223fb  mov     rax, [rax+10h]
0x1800223ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022404  mov     rcx, [rbp+4Fh+var_70]
0x180022408  mov     [rbp+4Fh+var_58], 0
0x180022410  test    rcx, rcx
0x180022413  jz      short loc_180022429
0x180022415  mov     rax, [rcx]
0x180022418  mov     rax, [rax+10h]
0x18002241c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022421  mov     [rbp+4Fh+var_70], 0
0x180022429  mov     rcx, [rbp+4Fh+var_68]
0x18002242d  test    rcx, rcx
0x180022430  jz      short loc_180022446
0x180022432  mov     rax, [rcx]
0x180022435  mov     rax, [rax+10h]
0x180022439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002243e  mov     [rbp+4Fh+var_68], 0
0x180022446  lea     rcx, [rbp+4Fh+var_50]
0x18002244a  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180022450  mov     eax, ebx
0x180022452  mov     rcx, [rbp+4Fh+var_18]
0x180022456  xor     rcx, rsp; StackCookie
0x180022459  call    __security_check_cookie
0x18002245e  lea     r11, [rsp+0A0h+var_10]
0x180022466  mov     rbx, [r11+20h]
0x18002246a  mov     rsi, [r11+28h]
0x18002246e  mov     rsp, r11
0x180022471  pop     r14
0x180022473  pop     rdi
0x180022474  pop     rbp
0x180022475  retn
```
