# HEADER_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180022c10`
- end: `0x180022f9e`
- name: `?SetConfigProperties@HEADER_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `910`
- prototype: `__int64 __fastcall(HEADER_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180022c10`
- `0x18002c010`

## import_xrefs

- `msvcrt!wcschr` at `0x180022dc8`
- `msvcrt!wcschr` at `0x180022dc8`
- `msvcrt!iswspace` at `0x180022e01`
- `msvcrt!iswspace` at `0x180022e01`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180022e13`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180022e13`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022dac`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022dac`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022c7a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ca6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022c7a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ca6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022f6d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022f77`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022f6d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022f77`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022e5d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022e9b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022e5d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022e9b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180022dea`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180022dea`

## pseudocode

```c
__int64 __fastcall HEADER_CUSTOM_MAPPER::SetConfigProperties(
        HEADER_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v8; // ebx
  unsigned int v9; // edx
  int v10; // edi
  const wchar_t *v11; // rsi
  wchar_t *v12; // rax
  wint_t *v13; // rdi
  __int64 (__fastcall *v14)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  __int64 (__fastcall *v16)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v19; // rax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v26[256]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v27[256]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v22 = 0;
  v21 = 0;
  v23 = 0;
  memset_0(v26, 0, sizeof(v26));
  STRU::STRU((STRU *)v25, v26, 0x100u);
  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v24, v27, 0x100u);
  if ( a2 && a3 && a4 && a5 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v22);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 72LL))(v22, &v23);
      if ( v8 >= 0 )
      {
        v9 = v23;
        v10 = 0;
        if ( v23 )
        {
          while ( 1 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 96LL))(v22, v9 - v10 - 1, 0);
            if ( v8 < 0 )
              break;
            v9 = v23;
            if ( ++v10 >= v23 )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v22 + 48LL))(
                 v22,
                 L"clear",
                 &v21);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 88LL))(v22, v21, 0, 0);
            if ( v8 >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              v21 = 0;
              v11 = (const wchar_t *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
              if ( *v11 )
              {
                while ( 1 )
                {
                  v12 = wcschr(v11, 0x3Au);
                  v13 = v12;
                  if ( !v12 )
                    break;
                  v8 = STRU::Copy((STRU *)v25, v11, v12 - v11);
                  if ( v8 < 0 )
                    goto LABEL_29;
                  do
                    ++v13;
                  while ( iswspace(*v13) );
                  v8 = STRU::Copy((STRU *)v24, v13);
                  if ( v8 < 0 )
                    goto LABEL_29;
                  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v22 + 48LL))(
                         v22,
                         L"add",
                         &v21);
                  if ( v8 < 0 )
                    goto LABEL_29;
                  v14 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v21 + 128LL);
                  Str = STRU::QueryStr((STRU *)v25);
                  v8 = v14(v21, L"name", Str, 0);
                  if ( v8 < 0 )
                    goto LABEL_29;
                  v16 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v21 + 128LL);
                  v17 = STRU::QueryStr((STRU *)v24);
                  v8 = v16(v21, L"value", v17, 0);
                  if ( v8 < 0 )
                    goto LABEL_29;
                  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v22 + 88LL))(
                          v22,
                          v21,
                          0xFFFFFFFFLL,
                          0);
                  v8 = v18;
                  if ( v18 < 0 )
                  {
                    if ( v18 != -2147024713 )
                      goto LABEL_29;
                    v8 = 0;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                  v19 = -1;
                  v21 = 0;
                  do
                    ++v19;
                  while ( v11[v19] );
                  v11 += v19 + 1;
                  if ( !*v11 )
                    goto LABEL_31;
                }
                v8 = -2147024883;
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
LABEL_29:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
LABEL_31:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  STRU::~STRU((STRU *)v24);
  STRU::~STRU((STRU *)v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022c10  push    rbp
0x180022c12  push    rbx
0x180022c13  push    rsi
0x180022c14  push    rdi
0x180022c15  push    r13
0x180022c17  push    r14
0x180022c19  lea     rbp, [rsp-3D8h]
0x180022c21  sub     rsp, 4D8h
0x180022c28  mov     rax, cs:__security_cookie
0x180022c2f  xor     rax, rsp
0x180022c32  mov     [rbp+400h+var_40], rax
0x180022c39  mov     rdi, [rbp+400h+arg_20]
0x180022c40  lea     rcx, [rbp+400h+var_440]; void *
0x180022c44  xor     r13d, r13d
0x180022c47  mov     rsi, r8
0x180022c4a  mov     rbx, rdx
0x180022c4d  mov     [rsp+500h+var_4C8], r13
0x180022c52  xor     edx, edx; Val
0x180022c54  mov     [rsp+500h+var_4D0], r13
0x180022c59  mov     r8d, 200h; Size
0x180022c5f  mov     [rsp+500h+var_4C0], r13d
0x180022c64  mov     r14, r9
0x180022c67  call    memset_0
0x180022c6c  mov     r8d, 100h
0x180022c72  lea     rdx, [rbp+400h+var_440]
0x180022c76  lea     rcx, [rbp+400h+var_480]
0x180022c7a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022c80  xor     edx, edx; Val
0x180022c82  lea     rcx, [rbp+400h+var_240]; void *
0x180022c89  mov     r8d, 200h; Size
0x180022c8f  call    memset_0
0x180022c94  mov     r8d, 100h
0x180022c9a  lea     rdx, [rbp+400h+var_240]
0x180022ca1  lea     rcx, [rsp+500h+var_4B8]
0x180022ca6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022cac  test    rbx, rbx
0x180022caf  jz      loc_180022F2D
0x180022cb5  test    rsi, rsi
0x180022cb8  jz      loc_180022F2D
0x180022cbe  test    r14, r14
0x180022cc1  jz      loc_180022F2D
0x180022cc7  test    rdi, rdi
0x180022cca  jz      loc_180022F2D
0x180022cd0  mov     rax, [rdi]
0x180022cd3  lea     rdx, [rsp+500h+var_4C8]
0x180022cd8  mov     rcx, rdi
0x180022cdb  mov     rax, [rax+28h]
0x180022cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ce4  mov     ebx, eax
0x180022ce6  test    eax, eax
0x180022ce8  js      loc_180022F32
0x180022cee  mov     rcx, [rsp+500h+var_4C8]
0x180022cf3  lea     rdx, [rsp+500h+var_4C0]
0x180022cf8  mov     rax, [rcx]
0x180022cfb  mov     rax, [rax+48h]
0x180022cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d04  mov     ebx, eax
0x180022d06  test    eax, eax
0x180022d08  js      loc_180022F32
0x180022d0e  mov     edx, [rsp+500h+var_4C0]
0x180022d12  mov     edi, r13d
0x180022d15  test    edx, edx
0x180022d17  jz      short loc_180022D45
0x180022d19  mov     rcx, [rsp+500h+var_4C8]
0x180022d1e  sub     edx, edi
0x180022d20  dec     edx
0x180022d22  xor     r8d, r8d
0x180022d25  mov     rax, [rcx]
0x180022d28  mov     rax, [rax+60h]
0x180022d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d31  mov     ebx, eax
0x180022d33  test    eax, eax
0x180022d35  js      loc_180022F32
0x180022d3b  mov     edx, [rsp+500h+var_4C0]
0x180022d3f  inc     edi
0x180022d41  cmp     edi, edx
0x180022d43  jb      short loc_180022D19
0x180022d45  mov     rcx, [rsp+500h+var_4C8]
0x180022d4a  lea     r8, [rsp+500h+var_4D0]
0x180022d4f  lea     rdx, aClear; "clear"
0x180022d56  mov     rax, [rcx]
0x180022d59  mov     rax, [rax+30h]
0x180022d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d62  mov     ebx, eax
0x180022d64  test    eax, eax
0x180022d66  js      loc_180022F32
0x180022d6c  mov     rcx, [rsp+500h+var_4C8]
0x180022d71  xor     r9d, r9d
0x180022d74  mov     rdx, [rsp+500h+var_4D0]
0x180022d79  xor     r8d, r8d
0x180022d7c  mov     rax, [rcx]
0x180022d7f  mov     rax, [rax+58h]
0x180022d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d88  mov     ebx, eax
0x180022d8a  test    eax, eax
0x180022d8c  js      loc_180022F32
0x180022d92  mov     rcx, [rsp+500h+var_4D0]
0x180022d97  mov     rax, [rcx]
0x180022d9a  mov     rax, [rax+10h]
0x180022d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022da3  lea     rcx, [rsi+10h]
0x180022da7  mov     [rsp+500h+var_4D0], r13
0x180022dac  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022db2  mov     rsi, [rax+18h]
0x180022db6  cmp     [rsi], r13w
0x180022dba  jz      loc_180022F32
0x180022dc0  mov     edx, 3Ah ; ':'; Ch
0x180022dc5  mov     rcx, rsi; Str
0x180022dc8  call    cs:__imp_wcschr
0x180022dce  mov     rdi, rax
0x180022dd1  test    rax, rax
0x180022dd4  jz      loc_180022F26
0x180022dda  mov     r8, rax
0x180022ddd  lea     rcx, [rbp+400h+var_480]
0x180022de1  sub     r8, rsi
0x180022de4  mov     rdx, rsi
0x180022de7  sar     r8, 1
0x180022dea  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180022df0  mov     ebx, eax
0x180022df2  test    eax, eax
0x180022df4  js      loc_180022F32
0x180022dfa  add     rdi, 2
0x180022dfe  movzx   ecx, word ptr [rdi]; C
0x180022e01  call    cs:__imp_iswspace
0x180022e07  test    eax, eax
0x180022e09  jnz     short loc_180022DFA
0x180022e0b  mov     rdx, rdi
0x180022e0e  lea     rcx, [rsp+500h+var_4B8]
0x180022e13  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180022e19  mov     ebx, eax
0x180022e1b  test    eax, eax
0x180022e1d  js      loc_180022F32
0x180022e23  mov     rcx, [rsp+500h+var_4C8]
0x180022e28  lea     r8, [rsp+500h+var_4D0]
0x180022e2d  lea     rdx, aAdd; "add"
0x180022e34  mov     rax, [rcx]
0x180022e37  mov     rax, [rax+30h]
0x180022e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e40  mov     ebx, eax
0x180022e42  test    eax, eax
0x180022e44  js      loc_180022F32
0x180022e4a  mov     rax, [rsp+500h+var_4D0]
0x180022e4f  mov     rcx, [rax]
0x180022e52  mov     rbx, [rcx+80h]
0x180022e59  lea     rcx, [rbp+400h+var_480]
0x180022e5d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180022e63  mov     rcx, [rsp+500h+var_4D0]
0x180022e68  lea     rdx, aName; "name"
0x180022e6f  mov     r8, rax
0x180022e72  xor     r9d, r9d
0x180022e75  mov     rax, rbx
0x180022e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e7d  mov     ebx, eax
0x180022e7f  test    eax, eax
0x180022e81  js      loc_180022F32
0x180022e87  mov     rax, [rsp+500h+var_4D0]
0x180022e8c  mov     rcx, [rax]
0x180022e8f  mov     rbx, [rcx+80h]
0x180022e96  lea     rcx, [rsp+500h+var_4B8]
0x180022e9b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180022ea1  mov     rcx, [rsp+500h+var_4D0]
0x180022ea6  lea     rdx, aValue; "value"
0x180022ead  mov     r8, rax
0x180022eb0  xor     r9d, r9d
0x180022eb3  mov     rax, rbx
0x180022eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ebb  mov     ebx, eax
0x180022ebd  test    eax, eax
0x180022ebf  js      short loc_180022F32
0x180022ec1  mov     rcx, [rsp+500h+var_4C8]
0x180022ec6  xor     r9d, r9d
0x180022ec9  mov     rdx, [rsp+500h+var_4D0]
0x180022ece  or      r8d, 0FFFFFFFFh
0x180022ed2  mov     rax, [rcx]
0x180022ed5  mov     rax, [rax+58h]
0x180022ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ede  mov     ebx, eax
0x180022ee0  test    eax, eax
0x180022ee2  jns     short loc_180022EEE
0x180022ee4  cmp     eax, 800700B7h
0x180022ee9  jnz     short loc_180022F32
0x180022eeb  mov     ebx, r13d
0x180022eee  mov     rcx, [rsp+500h+var_4D0]
0x180022ef3  mov     rax, [rcx]
0x180022ef6  mov     rax, [rax+10h]
0x180022efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022eff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022f03  mov     [rsp+500h+var_4D0], r13
0x180022f08  inc     rax
0x180022f0b  cmp     [rsi+rax*2], r13w
0x180022f10  jnz     short loc_180022F08
0x180022f12  lea     rsi, [rsi+rax*2]
0x180022f16  add     rsi, 2
0x180022f1a  cmp     [rsi], r13w
0x180022f1e  jnz     loc_180022DC0
0x180022f24  jmp     short loc_180022F4D
0x180022f26  mov     ebx, 8007000Dh
0x180022f2b  jmp     short loc_180022F32
0x180022f2d  mov     ebx, 80070057h
0x180022f32  mov     rcx, [rsp+500h+var_4D0]
0x180022f37  test    rcx, rcx
0x180022f3a  jz      short loc_180022F4D
0x180022f3c  mov     rax, [rcx]
0x180022f3f  mov     rax, [rax+10h]
0x180022f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f48  mov     [rsp+500h+var_4D0], r13
0x180022f4d  mov     rcx, [rsp+500h+var_4C8]
0x180022f52  test    rcx, rcx
0x180022f55  jz      short loc_180022F68
0x180022f57  mov     rax, [rcx]
0x180022f5a  mov     rax, [rax+10h]
0x180022f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f63  mov     [rsp+500h+var_4C8], r13
0x180022f68  lea     rcx, [rsp+500h+var_4B8]
0x180022f6d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022f73  lea     rcx, [rbp+400h+var_480]
0x180022f77  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022f7d  mov     eax, ebx
0x180022f7f  mov     rcx, [rbp+400h+var_40]
0x180022f86  xor     rcx, rsp; StackCookie
0x180022f89  call    __security_check_cookie
0x180022f8e  add     rsp, 4D8h
0x180022f95  pop     r14
0x180022f97  pop     r13
0x180022f99  pop     rdi
0x180022f9a  pop     rsi
0x180022f9b  pop     rbx
0x180022f9c  pop     rbp
0x180022f9d  retn
```
