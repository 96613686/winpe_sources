# COMMAND_PROCESSOR::GetMatchingSchema(INativeConfigurationElement *,ushort const *,ushort const *,MULTISZ *)

- ea: `0x180008f00`
- end: `0x1800093f3`
- name: `?GetMatchingSchema@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEBG1PEAVMULTISZ@@@Z`
- size: `1267`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, struct INativeConfigurationElement *, const unsigned __int16 *, const unsigned __int16 *, struct MULTISZ *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008f00`
- `0x180009aac`

## callees

- `0x180001fb0`
- `0x1800024e0`
- `0x180002640`
- `0x180002e90`
- `0x180008f00`
- `0x18000a91c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000908a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000908a`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::GetMatchingSchema(
        COMMAND_PROCESSOR *this,
        struct INativeConfigurationElement *a2,
        const unsigned __int8 *a3,
        const unsigned __int16 *a4,
        struct MULTISZ *a5)
{
  const unsigned __int8 *v5; // rdi
  COMMAND_PROCESSOR *v7; // rsi
  unsigned int v9; // r14d
  int MatchingSchema; // ebx
  int v11; // eax
  COMMAND_PROCESSOR *v12; // rcx
  signed int LastError; // eax
  __int64 i; // rsi
  const unsigned __int16 *v15; // rdx
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  struct INativeConfigurationElement *v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-B8h] BYREF
  COMMAND_PROCESSOR *v21; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  __int16 v26; // [rsp+8Ch] [rbp-74h]
  int v27; // [rsp+90h] [rbp-70h]
  int v28; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v29[191]; // [rsp+A8h] [rbp-58h]
  int v30; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 *v31[191]; // [rsp+6A8h] [rbp+5A8h]
  __int16 v32; // [rsp+CA0h] [rbp+BA0h] BYREF
  _BYTE v33[510]; // [rsp+CA2h] [rbp+BA2h] BYREF

  v5 = a3;
  v22 = (const unsigned __int16 *)a3;
  v7 = this;
  v21 = this;
  v20 = 64;
  memset_0(v33, 0, sizeof(v33));
  v9 = 0;
  v25 = 512;
  v26 = 256;
  v24 = (unsigned __int16 *)&v32;
  v27 = 0;
  v32 = 0;
  v18 = 0;
  v19 = 0;
  if ( a2 && a4 && v5 && a5 )
  {
    MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, int *, unsigned int *))(*(_QWORD *)a2 + 96LL))(
                       a2,
                       &v28,
                       &v20);
    if ( MatchingSchema >= 0 )
    {
      while ( v9 < v20 )
      {
        MatchingSchema = STRU::Copy((STRU *)v23, v5);
        if ( MatchingSchema < 0 )
          break;
        if ( v27 )
        {
          MatchingSchema = STRU::Append((STRU *)v23, L".");
          if ( MatchingSchema < 0 )
            break;
        }
        v11 = (int)v29[3 * v9];
        if ( v11 )
        {
          if ( v11 == 1 )
          {
            MatchingSchema = STRU::Append((STRU *)v23, v29[3 * v9]);
            if ( MatchingSchema < 0 )
              break;
            MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)a2 + 32LL))(
                               a2,
                               v29[3 * v9],
                               &v18);
            if ( MatchingSchema < 0 )
              break;
            MatchingSchema = COMMAND_PROCESSOR::GetMatchingSchema(v7, v18, v24, a4, a5);
            if ( MatchingSchema < 0 )
              break;
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
          }
          else if ( v11 == 2 )
          {
            v17 = 64;
            MatchingSchema = STRU::Append((STRU *)v23, L"[");
            if ( MatchingSchema < 0 )
              break;
            MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a2 + 40LL))(
                               a2,
                               &v19);
            if ( MatchingSchema < 0 )
              break;
            MatchingSchema = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)v19 + 48LL))(
                               v19,
                               v29[3 * v9],
                               &v18);
            if ( MatchingSchema < 0 )
              break;
            MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, int *, int *))(*(_QWORD *)v18 + 96LL))(
                               v18,
                               &v30,
                               &v17);
            if ( MatchingSchema < 0 )
              break;
            for ( i = 0; (unsigned int)i < v17 && !LODWORD(v31[3 * i]); i = (unsigned int)(i + 1) )
            {
              if ( (BYTE4(v31[3 * i + 1]) & 6) != 0 )
              {
                if ( (_DWORD)i )
                {
                  MatchingSchema = STRU::Append((STRU *)v23, L",");
                  if ( MatchingSchema < 0 )
                    goto LABEL_62;
                }
                MatchingSchema = STRU::Append((STRU *)v23, v31[3 * i]);
                if ( MatchingSchema < 0 )
                  goto LABEL_62;
                MatchingSchema = STRU::Append((STRU *)v23, L"='");
                if ( MatchingSchema < 0 )
                  goto LABEL_62;
                switch ( LODWORD(v31[3 * i + 1]) )
                {
                  case 1:
                    v15 = L"string";
                    break;
                  case 2:
                    v15 = L"int";
                    break;
                  case 3:
                    v15 = L"int64";
                    break;
                  case 4:
                    v15 = L"true/false";
                    break;
                  case 5:
                    v15 = L"flags";
                    break;
                  case 6:
                    v15 = L"enum";
                    break;
                  case 7:
                    v15 = L"timespan";
                    break;
                  case 9:
                    v15 = L"uint";
                    break;
                  default:
                    v15 = LODWORD(v31[3 * i + 1]) == 10 ? L"uint64" : L"unknown";
                    break;
                }
                MatchingSchema = STRU::Append((STRU *)v23, v15);
                if ( MatchingSchema < 0 )
                  goto LABEL_62;
                MatchingSchema = STRU::Append((STRU *)v23, L"'");
                if ( MatchingSchema < 0 )
                  goto LABEL_62;
              }
            }
            MatchingSchema = STRU::Append((STRU *)v23, L"]");
            if ( MatchingSchema < 0 )
              break;
            v7 = v21;
            MatchingSchema = COMMAND_PROCESSOR::GetMatchingSchema(v21, v18, v24, a4, a5);
            if ( MatchingSchema < 0 )
              break;
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            v19 = 0;
          }
        }
        else
        {
          MatchingSchema = STRU::Append((STRU *)v23, v29[3 * v9]);
          if ( MatchingSchema < 0 )
            break;
          v17 = 0;
          MatchingSchema = COMMAND_PROCESSOR::IsWildcardMatch(v12, v24, a4, &v17);
          if ( MatchingSchema < 0 )
            break;
          if ( v17 && !(unsigned int)MULTISZ::Append(a5, v24) )
          {
            LastError = GetLastError();
            MatchingSchema = LastError;
            if ( LastError > 0 )
              MatchingSchema = (unsigned __int16)LastError | 0x80070000;
            break;
          }
        }
        v5 = (const unsigned __int8 *)v22;
        ++v9;
      }
    }
  }
  else
  {
    MatchingSchema = -2147024809;
  }
LABEL_62:
  if ( v18 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v23);
  return (unsigned int)MatchingSchema;
}

```

## disassembly

```asm
0x180008f00  push    rbp
0x180008f02  push    rbx
0x180008f03  push    rsi
0x180008f04  push    rdi
0x180008f05  push    r12
0x180008f07  push    r13
0x180008f09  push    r14
0x180008f0b  push    r15
0x180008f0d  lea     rbp, [rsp-0DB8h]
0x180008f15  sub     rsp, 0EB8h
0x180008f1c  mov     rax, cs:__security_cookie
0x180008f23  xor     rax, rsp
0x180008f26  mov     [rbp+0DF0h+var_50], rax
0x180008f2d  mov     r13, [rbp+0DF0h+arg_20]
0x180008f34  mov     rdi, r8
0x180008f37  mov     [rsp+0EF0h+var_E98], r8
0x180008f3c  mov     r15, rdx
0x180008f3f  mov     rsi, rcx
0x180008f42  mov     [rsp+0EF0h+var_EA0], rcx
0x180008f47  xor     edx, edx; Val
0x180008f49  mov     [rsp+0EF0h+var_EA8], 40h ; '@'
0x180008f51  mov     r8d, 1FEh; Size
0x180008f57  lea     rcx, [rbp+0DF0h+var_24E]; void *
0x180008f5e  mov     r12, r9
0x180008f61  call    memset_0
0x180008f66  xor     r14d, r14d
0x180008f69  mov     [rbp+0DF0h+var_E68], 200h
0x180008f70  mov     [rbp+0DF0h+var_E64], 100h
0x180008f76  lea     rax, [rbp+0DF0h+var_250]
0x180008f7d  mov     [rbp+0DF0h+var_E70], rax
0x180008f81  mov     [rbp+0DF0h+var_E60], r14d
0x180008f85  mov     [rbp+0DF0h+var_250], r14w
0x180008f8d  mov     [rsp+0EF0h+var_EB8], r14
0x180008f92  mov     [rsp+0EF0h+var_EB0], r14
0x180008f97  test    r15, r15
0x180008f9a  jz      loc_180009381
0x180008fa0  test    r12, r12
0x180008fa3  jz      loc_180009381
0x180008fa9  test    rdi, rdi
0x180008fac  jz      loc_180009381
0x180008fb2  test    r13, r13
0x180008fb5  jz      loc_180009381
0x180008fbb  mov     rax, [r15]
0x180008fbe  lea     r8, [rsp+0EF0h+var_EA8]
0x180008fc3  lea     rdx, [rbp+0DF0h+var_E50]
0x180008fc7  mov     rcx, r15
0x180008fca  mov     rax, [rax+60h]
0x180008fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd3  mov     ebx, eax
0x180008fd5  test    eax, eax
0x180008fd7  js      loc_180009386
0x180008fdd  cmp     r14d, [rsp+0EF0h+var_EA8]
0x180008fe2  jnb     loc_180009386
0x180008fe8  mov     rdx, rdi; unsigned __int16 *
0x180008feb  lea     rcx, [rsp+0EF0h+var_E90]; this
0x180008ff0  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180008ff5  mov     ebx, eax
0x180008ff7  test    eax, eax
0x180008ff9  js      loc_180009386
0x180008fff  cmp     [rbp+0DF0h+var_E60], 0
0x180009003  jz      short loc_180009020
0x180009005  lea     rdx, asc_180039808; "."
0x18000900c  lea     rcx, [rsp+0EF0h+var_E90]; this
0x180009011  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009016  mov     ebx, eax
0x180009018  test    eax, eax
0x18000901a  js      loc_180009386
0x180009020  mov     eax, r14d
0x180009023  lea     rdi, [rax+rax*2]
0x180009027  mov     eax, [rbp+rdi*8+0DF0h+var_E50]
0x18000902b  test    eax, eax
0x18000902d  jnz     short loc_1800090A8
0x18000902f  mov     rdx, [rbp+rdi*8+0DF0h+var_E48]; unsigned __int16 *
0x180009034  lea     rcx, [rsp+0EF0h+var_E90]; this
0x180009039  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000903e  mov     ebx, eax
0x180009040  test    eax, eax
0x180009042  js      loc_180009386
0x180009048  mov     rdx, [rbp+0DF0h+var_E70]; unsigned __int16 *
0x18000904c  lea     r9, [rsp+0EF0h+var_EC0]; int *
0x180009051  mov     r8, r12; unsigned __int16 *
0x180009054  mov     [rsp+0EF0h+var_EC0], 0
0x18000905c  call    ?IsWildcardMatch@COMMAND_PROCESSOR@@AEAAJPEBG0PEAH@Z; COMMAND_PROCESSOR::IsWildcardMatch(ushort const *,ushort const *,int *)
0x180009061  mov     ebx, eax
0x180009063  test    eax, eax
0x180009065  js      loc_180009386
0x18000906b  cmp     [rsp+0EF0h+var_EC0], 0
0x180009070  jz      loc_180009374
0x180009076  mov     rdx, [rbp+0DF0h+var_E70]; unsigned __int16 *
0x18000907a  mov     rcx, r13; this
0x18000907d  call    ?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180009082  test    eax, eax
0x180009084  jnz     loc_180009374
0x18000908a  call    cs:__imp_GetLastError
0x180009090  mov     ebx, eax
0x180009092  test    eax, eax
0x180009094  jle     loc_180009386
0x18000909a  movzx   ebx, ax
0x18000909d  or      ebx, 80070000h
0x1800090a3  jmp     loc_180009386
0x1800090a8  cmp     eax, 1
0x1800090ab  jnz     short loc_18000912B
0x1800090ad  mov     rdx, [rbp+rdi*8+0DF0h+var_E48]; unsigned __int16 *
0x1800090b2  lea     rcx, [rsp+0EF0h+var_E90]; this
0x1800090b7  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800090bc  mov     ebx, eax
0x1800090be  test    eax, eax
0x1800090c0  js      loc_180009386
0x1800090c6  mov     rax, [r15]
0x1800090c9  lea     r8, [rsp+0EF0h+var_EB8]
0x1800090ce  mov     rdx, [rbp+rdi*8+0DF0h+var_E48]
0x1800090d3  mov     rcx, r15
0x1800090d6  mov     rax, [rax+20h]
0x1800090da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090df  mov     ebx, eax
0x1800090e1  test    eax, eax
0x1800090e3  js      loc_180009386
0x1800090e9  mov     r8, [rbp+0DF0h+var_E70]; unsigned __int16 *
0x1800090ed  mov     r9, r12; unsigned __int16 *
0x1800090f0  mov     rdx, [rsp+0EF0h+var_EB8]; struct INativeConfigurationElement *
0x1800090f5  mov     rcx, rsi; this
0x1800090f8  mov     [rsp+0EF0h+var_ED0], r13; struct MULTISZ *
0x1800090fd  call    ?GetMatchingSchema@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEBG1PEAVMULTISZ@@@Z; COMMAND_PROCESSOR::GetMatchingSchema(INativeConfigurationElement *,ushort const *,ushort const *,MULTISZ *)
0x180009102  mov     ebx, eax
0x180009104  test    eax, eax
0x180009106  js      loc_180009386
0x18000910c  mov     rcx, [rsp+0EF0h+var_EB8]
0x180009111  mov     rax, [rcx]
0x180009114  mov     rax, [rax+10h]
0x180009118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000911d  mov     [rsp+0EF0h+var_EB8], 0
0x180009126  jmp     loc_180009374
0x18000912b  cmp     eax, 2
0x18000912e  jnz     loc_180009374
0x180009134  lea     rdx, asc_180039918; "["
0x18000913b  mov     [rsp+0EF0h+var_EC0], 40h ; '@'
0x180009143  lea     rcx, [rsp+0EF0h+var_E90]; this
0x180009148  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000914d  mov     ebx, eax
0x18000914f  test    eax, eax
0x180009151  js      loc_180009386
0x180009157  mov     rax, [r15]
0x18000915a  lea     rdx, [rsp+0EF0h+var_EB0]
0x18000915f  mov     rcx, r15
0x180009162  mov     rax, [rax+28h]
0x180009166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916b  mov     ebx, eax
0x18000916d  test    eax, eax
0x18000916f  js      loc_180009386
0x180009175  mov     rcx, [rsp+0EF0h+var_EB0]
0x18000917a  lea     r8, [rsp+0EF0h+var_EB8]
0x18000917f  mov     rdx, [rbp+rdi*8+0DF0h+var_E48]
0x180009184  mov     rax, [rcx]
0x180009187  mov     rax, [rax+30h]
0x18000918b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009190  mov     ebx, eax
0x180009192  test    eax, eax
0x180009194  js      loc_180009386
0x18000919a  mov     rcx, [rsp+0EF0h+var_EB8]
0x18000919f  lea     r8, [rsp+0EF0h+var_EC0]
0x1800091a4  lea     rdx, [rbp+0DF0h+var_850]
0x1800091ab  mov     rax, [rcx]
0x1800091ae  mov     rax, [rax+60h]
0x1800091b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b7  mov     ebx, eax
0x1800091b9  test    eax, eax
0x1800091bb  js      loc_180009386
0x1800091c1  xor     esi, esi
0x1800091c3  cmp     esi, [rsp+0EF0h+var_EC0]
0x1800091c7  jnb     loc_180009305
0x1800091cd  lea     rdi, [rsi+rsi*2]
0x1800091d1  cmp     [rbp+rdi*8+0DF0h+var_850], 0
0x1800091d9  jnz     loc_180009305
0x1800091df  test    [rbp+rdi*8+0DF0h+var_83C], 6
0x1800091e7  jz      loc_1800092FE
0x1800091ed  test    esi, esi
0x1800091ef  jz      short loc_18000920C
0x1800091f1  lea     rdx, asc_18003991C; ","
0x1800091f8  lea     rcx, [rsp+0EF0h+var_E90]; this
0x1800091fd  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009202  mov     ebx, eax
0x180009204  test    eax, eax
0x180009206  js      loc_180009386
0x18000920c  mov     rdx, [rbp+rdi*8+0DF0h+var_848]; unsigned __int16 *
0x180009214  lea     rcx, [rsp+0EF0h+var_E90]; this
0x180009219  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000921e  mov     ebx, eax
0x180009220  test    eax, eax
0x180009222  js      loc_180009386
0x180009228  lea     rdx, asc_180039920; "='"
0x18000922f  lea     rcx, [rsp+0EF0h+var_E90]; this
0x180009234  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009239  mov     ebx, eax
0x18000923b  test    eax, eax
0x18000923d  js      loc_180009386
0x180009243  mov     ecx, [rbp+rdi*8+0DF0h+var_840]
0x18000924a  sub     ecx, 1
0x18000924d  jz      short loc_1800092C8
0x18000924f  sub     ecx, 1
0x180009252  jz      short loc_1800092BF
0x180009254  sub     ecx, 1
0x180009257  jz      short loc_1800092B6
0x180009259  sub     ecx, 1
0x18000925c  jz      short loc_1800092AD
0x18000925e  sub     ecx, 1
0x180009261  jz      short loc_1800092A4
0x180009263  sub     ecx, 1
0x180009266  jz      short loc_18000929B
0x180009268  sub     ecx, 1
0x18000926b  jz      short loc_180009292
0x18000926d  sub     ecx, 2
0x180009270  jz      short loc_180009289
0x180009272  cmp     ecx, 1
0x180009275  jz      short loc_180009280
0x180009277  lea     rdx, aUnknown; "unknown"
0x18000927e  jmp     short loc_1800092CF
0x180009280  lea     rdx, aUint64; "uint64"
0x180009287  jmp     short loc_1800092CF
0x180009289  lea     rdx, aUint; "uint"
0x180009290  jmp     short loc_1800092CF
0x180009292  lea     rdx, aTimespan; "timespan"
0x180009299  jmp     short loc_1800092CF
0x18000929b  lea     rdx, aEnum; "enum"
0x1800092a2  jmp     short loc_1800092CF
0x1800092a4  lea     rdx, aFlags; "flags"
0x1800092ab  jmp     short loc_1800092CF
0x1800092ad  lea     rdx, aTrueFalse_0; "true/false"
0x1800092b4  jmp     short loc_1800092CF
0x1800092b6  lea     rdx, aInt64; "int64"
0x1800092bd  jmp     short loc_1800092CF
0x1800092bf  lea     rdx, aInt; "int"
0x1800092c6  jmp     short loc_1800092CF
0x1800092c8  lea     rdx, aString; "string"
0x1800092cf  lea     rcx, [rsp+0EF0h+var_E90]; this
0x1800092d4  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800092d9  mov     ebx, eax
0x1800092db  test    eax, eax
0x1800092dd  js      loc_180009386
0x1800092e3  lea     rdx, asc_1800399D0; "'"
0x1800092ea  lea     rcx, [rsp+0EF0h+var_E90]; this
0x1800092ef  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800092f4  mov     ebx, eax
0x1800092f6  test    eax, eax
0x1800092f8  js      loc_180009386
0x1800092fe  inc     esi
0x180009300  jmp     loc_1800091C3
0x180009305  lea     rdx, asc_1800399D4; "]"
0x18000930c  lea     rcx, [rsp+0EF0h+var_E90]; this
0x180009311  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009316  mov     ebx, eax
0x180009318  test    eax, eax
0x18000931a  js      short loc_180009386
0x18000931c  mov     rsi, [rsp+0EF0h+var_EA0]
0x180009321  mov     r9, r12; unsigned __int16 *
0x180009324  mov     r8, [rbp+0DF0h+var_E70]; unsigned __int16 *
0x180009328  mov     rcx, rsi; this
0x18000932b  mov     rdx, [rsp+0EF0h+var_EB8]; struct INativeConfigurationElement *
0x180009330  mov     [rsp+0EF0h+var_ED0], r13; struct MULTISZ *
0x180009335  call    ?GetMatchingSchema@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEBG1PEAVMULTISZ@@@Z; COMMAND_PROCESSOR::GetMatchingSchema(INativeConfigurationElement *,ushort const *,ushort const *,MULTISZ *)
0x18000933a  mov     ebx, eax
0x18000933c  test    eax, eax
0x18000933e  js      short loc_180009386
0x180009340  mov     rcx, [rsp+0EF0h+var_EB8]
0x180009345  mov     rax, [rcx]
0x180009348  mov     rax, [rax+10h]
0x18000934c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009351  mov     rcx, [rsp+0EF0h+var_EB0]
0x180009356  mov     [rsp+0EF0h+var_EB8], 0
0x18000935f  mov     rax, [rcx]
0x180009362  mov     rax, [rax+10h]
0x180009366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000936b  mov     [rsp+0EF0h+var_EB0], 0
0x180009374  mov     rdi, [rsp+0EF0h+var_E98]
0x180009379  inc     r14d
0x18000937c  jmp     loc_180008FDD
0x180009381  mov     ebx, 80070057h
0x180009386  mov     rcx, [rsp+0EF0h+var_EB8]
0x18000938b  test    rcx, rcx
0x18000938e  jz      short loc_1800093A5
0x180009390  mov     rax, [rcx]
0x180009393  mov     rax, [rax+10h]
0x180009397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000939c  mov     [rsp+0EF0h+var_EB8], 0
0x1800093a5  mov     rcx, [rsp+0EF0h+var_EB0]
0x1800093aa  test    rcx, rcx
0x1800093ad  jz      short loc_1800093C4
0x1800093af  mov     rax, [rcx]
0x1800093b2  mov     rax, [rax+10h]
0x1800093b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093bb  mov     [rsp+0EF0h+var_EB0], 0
0x1800093c4  lea     rcx, [rsp+0EF0h+var_E90]; this
0x1800093c9  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800093ce  mov     eax, ebx
0x1800093d0  mov     rcx, [rbp+0DF0h+var_50]
0x1800093d7  xor     rcx, rsp; StackCookie
0x1800093da  call    __security_check_cookie
0x1800093df  add     rsp, 0EB8h
0x1800093e6  pop     r15
0x1800093e8  pop     r14
0x1800093ea  pop     r13
  ... truncated ...
```
