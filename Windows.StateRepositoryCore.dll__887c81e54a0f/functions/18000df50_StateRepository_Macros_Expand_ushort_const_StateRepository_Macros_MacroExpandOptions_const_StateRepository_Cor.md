# StateRepository::Macros::Expand(ushort const *,StateRepository::Macros::MacroExpandOptions const &,StateRepository::Core::Text &)

- ea: `0x18000df50`
- end: `0x18000e32e`
- name: `?Expand@Macros@StateRepository@@YAJPEBGAEBUMacroExpandOptions@12@AEAVText@Core@2@@Z`
- size: `990`
- prototype: `__int64 __fastcall(StateRepository::Macros *this, const unsigned __int16 *, const struct StateRepository::Macros::MacroExpandOptions *, struct StateRepository::Core::Text *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e340`

## callees

- `0x1800022a0`
- `0x18000940c`
- `0x18000a8d4`
- `0x18000df20`
- `0x18000df50`
- `0x18000e760`
- `0x18000e78c`
- `0x18000e954`
- `0x18000e9a0`
- `0x18000eb40`
- `0x18000f228`
- `0x18000fe28`
- `0x180011010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e01c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e0d9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e01c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e0d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e14e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e14e`

## pseudocode

```c
__int64 __fastcall StateRepository::Macros::Expand(
        StateRepository::Macros *this,
        const unsigned __int16 *a2,
        const struct StateRepository::Macros::MacroExpandOptions *a3,
        struct StateRepository::Core::Text *a4)
{
  int v4; // r14d
  const struct StateRepository::Macros::MacroExpandOptions *v5; // rdi
  wchar_t v9; // ax
  char v10; // r15
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  wchar_t *v13; // r14
  int v14; // eax
  unsigned int v15; // ebx
  const wchar_t *v16; // r14
  __int64 v17; // rdx
  wchar_t *v18; // rax
  unsigned __int64 i; // rbx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ebx
  int v23; // eax
  unsigned __int16 *v24; // rcx
  __int64 v25; // rdx
  unsigned __int16 *v26; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-60h]
  __int16 v28; // [rsp+30h] [rbp-50h]
  unsigned __int16 v29; // [rsp+34h] [rbp-4Ch]
  wchar_t v30; // [rsp+38h] [rbp-48h]
  unsigned __int16 *v31; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *v32; // [rsp+48h] [rbp-38h]
  LPCWCH lpString1[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 **v34; // [rsp+60h] [rbp-20h] BYREF
  __int64 v35; // [rsp+68h] [rbp-18h] BYREF
  char v36; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  char v38; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int16 *v39; // [rsp+D8h] [rbp+58h] BYREF

  v4 = 0;
  v5 = a3;
  if ( !this )
  {
    StateRepository::Core::Text::Reset(a3);
    return 0;
  }
  if ( *((_QWORD *)a3 + 1) )
  {
    if ( *(_QWORD *)a3 )
      goto LABEL_8;
  }
  else if ( !*(_QWORD *)a3 )
  {
    goto LABEL_8;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
LABEL_8:
  if ( *(_QWORD *)v5 )
    **(_WORD **)v5 = 0;
  v9 = a2[14];
  v28 = v9;
  if ( !v9 )
  {
    v9 = 36;
    v28 = 36;
  }
  v29 = a2[15];
  if ( !v29 )
    v29 = 40;
  v30 = a2[16];
  if ( !v30 )
    v30 = 41;
  lpString1[0] = 0;
  v10 = 0;
  lpString1[1] = 0;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)this + v11) );
  v12 = 0;
  while ( 1 )
  {
    if ( v12 >= v11 )
      goto LABEL_61;
    v39 = (unsigned __int16 *)((char *)this + 2 * v12);
    v13 = wcschr(v39, v9);
    if ( !v13 )
      goto LABEL_60;
    if ( v13 > v39 )
    {
      v14 = StateRepository::Core::Text::Append(v5, v39, v13 - v39);
      v15 = v14;
      if ( v14 < 0 )
        break;
    }
    v16 = v13 + 1;
    v12 = ((char *)v16 - (char *)this) >> 1;
    if ( *v16 == v28 )
    {
      LOWORD(v39) = v28;
      v4 = StateRepository::Core::Text::Append(v5, (const unsigned __int16 *)&v39, 1u);
      if ( v4 < 0 )
      {
        v17 = 70;
LABEL_51:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros.cpp",
          (const char *)(unsigned int)v4,
          bIgnoreCase);
        goto LABEL_52;
      }
      v10 = 1;
      ++v12;
    }
    else
    {
      if ( *v16 == v29 )
      {
        v18 = wcschr(v16, v30);
        v32 = v18;
        if ( v18 )
        {
          v14 = StateRepository::Core::Text::SetSubstring(
                  (StateRepository::Core::Text *)lpString1,
                  v16 + 1,
                  (unsigned __int64)a3,
                  ((char *)v18 - (char *)v16 - 2) >> 1);
          v15 = v14;
          if ( v14 < 0 )
          {
            v25 = 93;
          }
          else
          {
            v38 = 0;
            for ( i = 0; i < *(_QWORD *)a2; ++i )
            {
              v39 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
              a3 = *(const struct StateRepository::Macros::MacroExpandOptions **)&v39[8 * i];
              if ( a3 && CompareStringOrdinal(lpString1[0], -1, (LPCWCH)a3, -1, 1) == 2 )
              {
                v20 = *((_QWORD *)a2 + 2);
                v34 = &v31;
                v31 = 0;
                v35 = 0;
                v36 = 1;
                v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))&v39[8 * i + 4])(v20, &v35);
                v4 = 0;
                v22 = v21;
                if ( v21 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x68,
                    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros.cpp",
                    (const char *)(unsigned int)v21);
                wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>((void ***)&v34);
                if ( v22 < 0 || (v23 = StateRepository::Core::Text::Append(v5, v31), v15 = v23, v23 >= 0) )
                {
                  v24 = v31;
                  v38 = 1;
                  v10 = 1;
                  v31 = 0;
                  if ( v24 )
                  {
                    operator delete(v24);
                    goto LABEL_44;
                  }
                  goto LABEL_48;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x6B,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros.cpp",
                  (const char *)(unsigned int)v23,
                  bIgnoreCase);
                v26 = v31;
                v31 = 0;
                if ( v26 )
                  operator delete(v26);
                goto LABEL_53;
              }
            }
            v4 = 0;
LABEL_44:
            if ( v38 )
            {
LABEL_48:
              v9 = v28;
              v12 = (((char *)v32 - (char *)this) >> 1) + 1;
              continue;
            }
            v14 = StateRepository::Macros::Evaluators::BuiltIn::Expand(
                    lpString1[0],
                    v5,
                    *((_DWORD *)a2 + 6),
                    (struct StateRepository::Core::Text *)&v38);
            v15 = v14;
            if ( v14 >= 0 )
            {
              if ( v38 )
                v10 = 1;
              goto LABEL_48;
            }
            v25 = 116;
          }
          goto LABEL_58;
        }
        --v12;
LABEL_60:
        v4 = 0;
LABEL_61:
        if ( v10 )
        {
          if ( v12 < v11 )
          {
            v14 = StateRepository::Core::Text::Append(v5, (const unsigned __int16 *)this + v12, v11 - v12);
            v15 = v14;
            if ( v14 < 0 )
            {
              v25 = 137;
              goto LABEL_58;
            }
          }
        }
        else
        {
          v14 = StateRepository::Core::Text::Set(v5, (const unsigned __int16 *)this, (unsigned __int64)a3);
          v15 = v14;
          if ( v14 < 0 )
          {
            v25 = 130;
            goto LABEL_58;
          }
        }
LABEL_52:
        v15 = v4;
        goto LABEL_53;
      }
      LOWORD(v39) = v28;
      v4 = StateRepository::Core::Text::Append(v5, (const unsigned __int16 *)&v39, 1u);
      if ( v4 < 0 )
      {
        v17 = 79;
        goto LABEL_51;
      }
    }
    v9 = v28;
    v4 = 0;
  }
  v25 = 63;
LABEL_58:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros.cpp",
    (const char *)(unsigned int)v14,
    bIgnoreCase);
LABEL_53:
  StateRepository::Core::Text::Reset((StateRepository::Core::Text *)lpString1);
  return v15;
}

```

## disassembly

```asm
0x18000df50  mov     [rsp-38h+arg_8], rbx
0x18000df55  push    rbp
0x18000df56  push    rsi
0x18000df57  push    rdi
0x18000df58  push    r12
0x18000df5a  push    r13
0x18000df5c  push    r14
0x18000df5e  push    r15
0x18000df60  mov     rbp, rsp
0x18000df63  sub     rsp, 80h
0x18000df6a  xor     r14d, r14d
0x18000df6d  mov     rdi, r8
0x18000df70  mov     r13, rdx
0x18000df73  mov     r12, rcx
0x18000df76  test    rcx, rcx
0x18000df79  jnz     short loc_18000DF8A
0x18000df7b  mov     rcx, r8; this
0x18000df7e  call    ?Reset@Text@Core@StateRepository@@QEAAXXZ; StateRepository::Core::Text::Reset(void)
0x18000df83  xor     eax, eax
0x18000df85  jmp     loc_18000E273
0x18000df8a  cmp     [r8+8], r14
0x18000df8e  jnz     short loc_18000DF97
0x18000df90  cmp     [r8], r14
0x18000df93  jz      short loc_18000DFA1
0x18000df95  jmp     short loc_18000DF9C
0x18000df97  cmp     [r8], r14
0x18000df9a  jnz     short loc_18000DFA1
0x18000df9c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dfa1  mov     rcx, [rdi]
0x18000dfa4  test    rcx, rcx
0x18000dfa7  jz      short loc_18000DFAF
0x18000dfa9  mov     eax, r14d
0x18000dfac  mov     [rcx], ax
0x18000dfaf  movzx   eax, word ptr [r13+1Ch]
0x18000dfb4  mov     [rbp+var_50], eax
0x18000dfb7  test    ax, ax
0x18000dfba  jnz     short loc_18000DFC4
0x18000dfbc  mov     eax, 24h ; '$'
0x18000dfc1  mov     [rbp+var_50], eax
0x18000dfc4  movzx   ecx, word ptr [r13+1Eh]
0x18000dfc9  mov     [rbp+var_4C], ecx
0x18000dfcc  test    cx, cx
0x18000dfcf  jnz     short loc_18000DFD8
0x18000dfd1  mov     [rbp+var_4C], 28h ; '('
0x18000dfd8  movzx   ecx, word ptr [r13+20h]
0x18000dfdd  mov     dword ptr [rbp+var_48], ecx
0x18000dfe0  test    cx, cx
0x18000dfe3  jnz     short loc_18000DFEC
0x18000dfe5  mov     dword ptr [rbp+var_48], 29h ; ')'
0x18000dfec  mov     [rbp+lpString1], r14
0x18000dff0  mov     r15b, r14b
0x18000dff3  mov     [rbp+var_28], r14
0x18000dff7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000dffb  inc     rsi
0x18000dffe  cmp     [r12+rsi*2], r14w
0x18000e003  jnz     short loc_18000DFFB
0x18000e005  mov     rbx, r14
0x18000e008  cmp     rbx, rsi
0x18000e00b  jnb     loc_18000E2E1
0x18000e011  lea     rcx, [r12+rbx*2]; Str
0x18000e015  movzx   edx, ax; Ch
0x18000e018  mov     [rbp+arg_18], rcx
0x18000e01c  call    cs:__imp_wcschr
0x18000e022  mov     r14, rax
0x18000e025  test    rax, rax
0x18000e028  jz      loc_18000E2DE
0x18000e02e  mov     rax, [rbp+arg_18]
0x18000e032  cmp     r14, rax
0x18000e035  jbe     short loc_18000E055
0x18000e037  mov     r8, r14
0x18000e03a  mov     rdx, rax; unsigned __int16 *
0x18000e03d  sub     r8, rax
0x18000e040  mov     rcx, rdi; this
0x18000e043  sar     r8, 1; unsigned __int64
0x18000e046  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Core::Text::Append(ushort const *,unsigned __int64)
0x18000e04b  mov     ebx, eax
0x18000e04d  test    eax, eax
0x18000e04f  js      loc_18000E246
0x18000e055  mov     eax, [rbp+var_50]
0x18000e058  add     r14, 2
0x18000e05c  mov     rbx, r14
0x18000e05f  sub     rbx, r12
0x18000e062  sar     rbx, 1
0x18000e065  cmp     [r14], ax
0x18000e069  jnz     short loc_18000E0A2
0x18000e06b  mov     r8d, 1; unsigned __int64
0x18000e071  mov     word ptr [rbp+arg_18], ax
0x18000e075  lea     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000e079  mov     rcx, rdi; this
0x18000e07c  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Core::Text::Append(ushort const *,unsigned __int64)
0x18000e081  mov     r14d, eax
0x18000e084  test    eax, eax
0x18000e086  js      loc_18000E24D
0x18000e08c  mov     edx, 1
0x18000e091  mov     r15b, dl
0x18000e094  add     rbx, rdx
0x18000e097  mov     eax, [rbp+var_50]
0x18000e09a  xor     r14d, r14d
0x18000e09d  jmp     loc_18000E008
0x18000e0a2  mov     ecx, [rbp+var_4C]
0x18000e0a5  cmp     [r14], cx
0x18000e0a9  jz      short loc_18000E0D2
0x18000e0ab  mov     r8d, 1; unsigned __int64
0x18000e0b1  mov     word ptr [rbp+arg_18], ax
0x18000e0b5  lea     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000e0b9  mov     rcx, rdi; this
0x18000e0bc  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Core::Text::Append(ushort const *,unsigned __int64)
0x18000e0c1  mov     r14d, eax
0x18000e0c4  test    eax, eax
0x18000e0c6  jns     short loc_18000E097
0x18000e0c8  mov     edx, 4Fh ; 'O'
0x18000e0cd  jmp     loc_18000E252
0x18000e0d2  movzx   edx, [rbp+var_48]; Ch
0x18000e0d6  mov     rcx, r14; Str
0x18000e0d9  call    cs:__imp_wcschr
0x18000e0df  mov     [rbp+var_38], rax
0x18000e0e3  test    rax, rax
0x18000e0e6  jz      loc_18000E2DB
0x18000e0ec  mov     r9, rax
0x18000e0ef  lea     rdx, [r14+2]; unsigned __int16 *
0x18000e0f3  sub     r9, r14
0x18000e0f6  lea     rcx, [rbp+lpString1]; this
0x18000e0fa  sub     r9, 2
0x18000e0fe  sar     r9, 1; unsigned __int64
0x18000e101  call    ?SetSubstring@Text@Core@StateRepository@@QEAAJPEBG_K1@Z; StateRepository::Core::Text::SetSubstring(ushort const *,unsigned __int64,unsigned __int64)
0x18000e106  xor     r14d, r14d
0x18000e109  mov     ebx, eax
0x18000e10b  test    eax, eax
0x18000e10d  js      loc_18000E2C1
0x18000e113  mov     [rbp+arg_0], r14b
0x18000e117  mov     ebx, r14d
0x18000e11a  cmp     rbx, [r13+0]
0x18000e11e  jnb     loc_18000E1F2
0x18000e124  mov     rax, [r13+8]
0x18000e128  mov     r14, rbx
0x18000e12b  add     r14, r14
0x18000e12e  mov     [rbp+arg_18], rax
0x18000e132  mov     r8, [rax+r14*8]; lpString2
0x18000e136  test    r8, r8
0x18000e139  jz      short loc_18000E159
0x18000e13b  mov     rcx, [rbp+lpString1]; lpString1
0x18000e13f  or      r9d, 0FFFFFFFFh; cchCount2
0x18000e143  or      edx, r9d; cchCount1
0x18000e146  mov     [rsp+80h+bIgnoreCase], 1; int
0x18000e14e  call    cs:__imp_CompareStringOrdinal
0x18000e154  cmp     eax, 2
0x18000e157  jz      short loc_18000E15E
0x18000e159  inc     rbx
0x18000e15c  jmp     short loc_18000E11A
0x18000e15e  mov     rcx, [r13+10h]
0x18000e162  lea     rax, [rbp+var_40]
0x18000e166  mov     [rbp+var_20], rax
0x18000e16a  lea     rdx, [rbp+var_18]
0x18000e16e  mov     rax, [rbp+arg_18]
0x18000e172  mov     [rbp+var_40], 0
0x18000e17a  mov     [rbp+var_18], 0
0x18000e182  mov     [rbp+var_10], 1
0x18000e186  mov     rax, [rax+r14*8+8]
0x18000e18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e190  xor     r14d, r14d
0x18000e193  mov     ebx, eax
0x18000e195  test    eax, eax
0x18000e197  jns     short loc_18000E1B0
0x18000e199  mov     rcx, [rbp+38h]; this
0x18000e19d  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x18000e1a4  mov     r9d, eax; char *
0x18000e1a7  lea     edx, [r14+68h]; void *
0x18000e1ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e1b0  lea     rcx, [rbp+var_20]
0x18000e1b4  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18000e1b9  test    ebx, ebx
0x18000e1bb  js      short loc_18000E1D3
0x18000e1bd  mov     rdx, [rbp+var_40]; unsigned __int16 *
0x18000e1c1  mov     rcx, rdi; this
0x18000e1c4  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG@Z; StateRepository::Core::Text::Append(ushort const *)
0x18000e1c9  mov     ebx, eax
0x18000e1cb  test    eax, eax
0x18000e1cd  js      loc_18000E28E
0x18000e1d3  mov     rcx, [rbp+var_40]; void *
0x18000e1d7  mov     edx, 1; unsigned __int64
0x18000e1dc  mov     [rbp+arg_0], dl
0x18000e1df  mov     r15b, dl
0x18000e1e2  mov     [rbp+var_40], r14
0x18000e1e6  test    rcx, rcx
0x18000e1e9  jz      short loc_18000E231
0x18000e1eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e1f0  jmp     short loc_18000E1F5
0x18000e1f2  xor     r14d, r14d
0x18000e1f5  cmp     [rbp+arg_0], r14b
0x18000e1f9  jnz     short loc_18000E22C
0x18000e1fb  mov     r8d, [r13+18h]
0x18000e1ff  lea     r9, [rbp+arg_0]
0x18000e203  mov     rcx, [rbp+lpString1]
0x18000e207  mov     rdx, rdi
0x18000e20a  call    ?Expand@BuiltIn@Evaluators@Macros@StateRepository@@YAJPEBGAEAVText@Core@4@W4SRCacheExpandMacrosFlags@@AEA_N@Z; StateRepository::Macros::Evaluators::BuiltIn::Expand(ushort const *,StateRepository::Core::Text &,SRCacheExpandMacrosFlags,bool &)
0x18000e20f  mov     ebx, eax
0x18000e211  test    eax, eax
0x18000e213  js      loc_18000E2BA
0x18000e219  cmp     [rbp+arg_0], r14b
0x18000e21d  mov     edx, 1
0x18000e222  movzx   r15d, r15b
0x18000e226  cmovnz  r15d, edx
0x18000e22a  jmp     short loc_18000E231
0x18000e22c  mov     edx, 1
0x18000e231  mov     rbx, [rbp+var_38]
0x18000e235  mov     eax, [rbp+var_50]
0x18000e238  sub     rbx, r12
0x18000e23b  sar     rbx, 1
0x18000e23e  add     rbx, rdx
0x18000e241  jmp     loc_18000E008
0x18000e246  mov     edx, 3Fh ; '?'
0x18000e24b  jmp     short loc_18000E2C6
0x18000e24d  mov     edx, 46h ; 'F'; void *
0x18000e252  mov     rcx, [rbp+38h]; this
0x18000e256  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x18000e25d  mov     r9d, r14d; char *
0x18000e260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e265  mov     ebx, r14d
0x18000e268  lea     rcx, [rbp+lpString1]; this
0x18000e26c  call    ?Reset@Text@Core@StateRepository@@QEAAXXZ; StateRepository::Core::Text::Reset(void)
0x18000e271  mov     eax, ebx
0x18000e273  mov     rbx, [rsp+80h+arg_8]
0x18000e27b  add     rsp, 80h
0x18000e282  pop     r15
0x18000e284  pop     r14
0x18000e286  pop     r13
0x18000e288  pop     r12
0x18000e28a  pop     rdi
0x18000e28b  pop     rsi
0x18000e28c  pop     rbp
0x18000e28d  retn
0x18000e28e  mov     rcx, [rbp+38h]; this
0x18000e292  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x18000e299  mov     r9d, eax; char *
0x18000e29c  mov     edx, 6Bh ; 'k'; void *
0x18000e2a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2a6  mov     rcx, [rbp+var_40]; void *
0x18000e2aa  mov     [rbp+var_40], r14
0x18000e2ae  test    rcx, rcx
0x18000e2b1  jz      short loc_18000E268
0x18000e2b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e2b8  jmp     short loc_18000E268
0x18000e2ba  mov     edx, 74h ; 't'
0x18000e2bf  jmp     short loc_18000E2C6
0x18000e2c1  mov     edx, 5Dh ; ']'; void *
0x18000e2c6  mov     rcx, [rbp+38h]; this
0x18000e2ca  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x18000e2d1  mov     r9d, eax; char *
0x18000e2d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2d9  jmp     short loc_18000E268
0x18000e2db  dec     rbx
0x18000e2de  xor     r14d, r14d
0x18000e2e1  test    r15b, r15b
0x18000e2e4  jnz     short loc_18000E302
0x18000e2e6  mov     rdx, r12; unsigned __int16 *
0x18000e2e9  mov     rcx, rdi; this
0x18000e2ec  call    ?Set@Text@Core@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Core::Text::Set(ushort const *,unsigned __int64)
0x18000e2f1  mov     ebx, eax
0x18000e2f3  test    eax, eax
0x18000e2f5  jns     loc_18000E265
0x18000e2fb  mov     edx, 82h
0x18000e300  jmp     short loc_18000E2C6
0x18000e302  cmp     rbx, rsi
0x18000e305  jnb     loc_18000E265
0x18000e30b  sub     rsi, rbx
0x18000e30e  lea     rdx, [r12+rbx*2]; unsigned __int16 *
0x18000e312  mov     r8, rsi; unsigned __int64
0x18000e315  mov     rcx, rdi; this
0x18000e318  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Core::Text::Append(ushort const *,unsigned __int64)
0x18000e31d  mov     ebx, eax
0x18000e31f  test    eax, eax
0x18000e321  jns     loc_18000E265
0x18000e327  mov     edx, 89h
0x18000e32c  jmp     short loc_18000E2C6
```
