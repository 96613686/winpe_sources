# FilterManager::GetReplaceByType(std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>> const &,ushort *,ushort const *,ushort const *,ulong,int *,ushort * *)

- ea: `0x18000dd08`
- end: `0x18000e006`
- name: `?GetReplaceByType@FilterManager@@IEAAXAEBV?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@PEAGPEBG2KPEAHPEAPEAG@Z`
- size: `766`
- prototype: `void __fastcall(__int64, FilterAgent ****, const wchar_t *, char *, __int64, unsigned int, int *, BSTR *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180009890`
- `0x18000a000`
- `0x18000e010`

## callees

- `0x18000cef4`
- `0x18000dd08`
- `0x18000ef78`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000de16`
- `msvcrt!_wcsicmp` at `0x18000de16`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000de2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000df27`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dfd9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000de2d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000df27`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dfd9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dfbc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dfbc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de42`
- `OLEAUT32!__imp_SysFreeString` at `0x18000df96`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de42`
- `OLEAUT32!__imp_SysFreeString` at `0x18000df96`

## pseudocode

```c
void __fastcall FilterManager::GetReplaceByType(
        __int64 a1,
        FilterAgent ****a2,
        const wchar_t *a3,
        char *a4,
        __int64 a5,
        unsigned int a6,
        int *a7,
        BSTR *a8)
{
  const wchar_t *v8; // r14
  FilterAgent ****v9; // rsi
  char v10; // r13
  unsigned __int64 v11; // r8
  FilterAgent **i; // rbx
  FilterAgent *v13; // rsi
  const unsigned __int16 *v14; // r15
  OLECHAR *v15; // rdi
  const wchar_t *v16; // rcx
  _BYTE *v17; // rcx
  int v18; // r14d
  __int64 v19; // r8
  int CharArea; // eax
  int v21; // ecx
  char v22; // al
  unsigned __int64 v23; // r8
  OLECHAR **v24; // rcx
  const OLECHAR *v25; // rcx
  BSTR v26; // rax
  int v27; // [rsp+40h] [rbp-79h] BYREF
  OLECHAR *v28; // [rsp+48h] [rbp-71h] BYREF
  const wchar_t *v29; // [rsp+50h] [rbp-69h]
  __int64 v30; // [rsp+58h] [rbp-61h]
  OLECHAR *v31; // [rsp+60h] [rbp-59h]
  FilterAgent ****v32; // [rsp+68h] [rbp-51h]
  BSTR *v33; // [rsp+70h] [rbp-49h]
  OLECHAR *psz[2]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v35; // [rsp+88h] [rbp-31h]
  unsigned __int64 v36; // [rsp+90h] [rbp-29h]
  wchar_t *String1[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-11h]
  unsigned __int64 v39; // [rsp+B0h] [rbp-9h]

  v8 = a3;
  v29 = a3;
  v9 = a2;
  v32 = a2;
  v30 = a5;
  v33 = a8;
  *a7 = 0;
  *a8 = 0;
  v10 = 0;
  v36 = 7;
  v35 = 0;
  LOWORD(psz[0]) = 0;
  if ( *(_WORD *)a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&a4[2 * v11] );
  }
  else
  {
    v11 = 0;
  }
  std::wstring::assign(psz, a4, v11);
  for ( i = **v9; ; ++i )
  {
    if ( i == (*v9)[1] )
    {
      if ( v10 )
        goto LABEL_50;
      goto LABEL_54;
    }
    v13 = *i;
    if ( !*((_BYTE *)*i + 1) || !*(_BYTE *)v13 )
      goto LABEL_21;
    v14 = (const unsigned __int16 *)psz;
    if ( v36 >= 8 )
      v14 = psz[0];
    v15 = 0;
    v31 = 0;
    v27 = 0;
    v39 = 7;
    v38 = 0;
    LOWORD(String1[0]) = 0;
    (*(void (__fastcall **)(_QWORD *, wchar_t **))(**((_QWORD **)v13 + 2) + 16LL))(*((_QWORD **)v13 + 2), String1);
    if ( !v38 )
      break;
    v16 = (const wchar_t *)String1;
    if ( v39 >= 8 )
      v16 = String1[0];
    if ( !_wcsicmp(v16, v8) )
      break;
    if ( v39 >= 8 )
      operator delete(String1[0]);
LABEL_17:
    *a7 = 0;
LABEL_18:
    if ( v15 )
      SysFreeString(v15);
    v8 = v29;
LABEL_21:
    v9 = v32;
  }
  v17 = (_BYTE *)*((_QWORD *)v13 + 2);
  if ( ((v17[12] - 1) & 0xFD) != 0 )
  {
    v18 = 1;
    if ( v17[12] == 2 )
    {
      LODWORD(v28) = 0;
      (*(void (__fastcall **)(_BYTE *, OLECHAR **))(*(_QWORD *)v17 + 56LL))(v17, &v28);
      v19 = -1;
      do
        ++v19;
      while ( v14[v19] );
      CharArea = FilterAgent::GetCharArea(v13, v14, v19);
      if ( (~(_DWORD)v28 & CharArea) != 0 )
      {
        v21 = 1;
        v27 = 1;
        v18 = 0;
      }
      else
      {
        v21 = 0;
        v27 = 0;
      }
      goto LABEL_34;
    }
LABEL_33:
    v21 = v27;
    goto LABEL_34;
  }
  v28 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD *, const unsigned __int16 *, __int64, _QWORD, int *, OLECHAR **))(**((_QWORD **)v13 + 1) + 48LL))(
          *((_QWORD **)v13 + 1),
          v14,
          v30,
          a6,
          &v27,
          &v28);
  if ( v18 )
    goto LABEL_33;
  v21 = v27;
  if ( !v27 )
    v15 = v28;
  v31 = v15;
LABEL_34:
  if ( v39 >= 8 )
  {
    operator delete(String1[0]);
    v21 = v27;
  }
  if ( v18 )
    goto LABEL_17;
  v22 = v10;
  if ( !v10 )
    v22 = 1;
  v10 = v22;
  *a7 = v21;
  if ( v21 != 1 )
  {
    if ( *v15 )
    {
      v23 = -1;
      do
        ++v23;
      while ( v15[v23] );
    }
    else
    {
      v23 = 0;
    }
    std::wstring::assign(psz, (char *)v15, v23);
    goto LABEL_18;
  }
  v24 = psz;
  if ( v36 >= 8 )
    v24 = (OLECHAR **)psz[0];
  v35 = 0;
  *(_WORD *)v24 = 0;
  if ( v15 )
    SysFreeString(v15);
LABEL_50:
  if ( *a7 == 1 )
  {
LABEL_54:
    v26 = 0;
    goto LABEL_55;
  }
  v25 = (const OLECHAR *)psz;
  if ( v36 >= 8 )
    v25 = psz[0];
  v26 = SysAllocString(v25);
LABEL_55:
  *v33 = v26;
  if ( v36 >= 8 )
    operator delete(psz[0]);
}

```

## disassembly

```asm
0x18000dd08  mov     [rsp-8+arg_0], rbx
0x18000dd0d  push    rbp
0x18000dd0e  push    rsi
0x18000dd0f  push    rdi
0x18000dd10  push    r12
0x18000dd12  push    r13
0x18000dd14  push    r14
0x18000dd16  push    r15
0x18000dd18  lea     rbp, [rsp-7]
0x18000dd1d  sub     rsp, 0C0h
0x18000dd24  mov     rax, cs:__security_cookie
0x18000dd2b  xor     rax, rsp
0x18000dd2e  mov     [rbp+37h+var_38], rax
0x18000dd32  mov     r14, r8
0x18000dd35  mov     [rbp+37h+var_A0], r8
0x18000dd39  mov     rsi, rdx
0x18000dd3c  mov     [rbp+37h+var_88], rdx
0x18000dd40  mov     rax, [rbp+37h+arg_20]
0x18000dd44  mov     [rbp+37h+var_98], rax
0x18000dd48  mov     r12, [rbp+37h+arg_30]
0x18000dd4c  mov     rdi, [rbp+37h+arg_38]
0x18000dd50  mov     [rbp+37h+var_80], rdi
0x18000dd54  xor     r15d, r15d
0x18000dd57  mov     [r12], r15d
0x18000dd5b  mov     [rdi], r15
0x18000dd5e  mov     r13b, r15b
0x18000dd61  mov     [rbp+37h+var_60], 7
0x18000dd69  mov     [rbp+37h+var_68], r15
0x18000dd6d  mov     word ptr [rbp+37h+psz], r15w
0x18000dd72  cmp     [r9], r15w
0x18000dd76  jnz     short loc_18000DD7D
0x18000dd78  mov     r8d, r15d
0x18000dd7b  jmp     short loc_18000DD8B
0x18000dd7d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000dd81  inc     r8
0x18000dd84  cmp     [r9+r8*2], r15w
0x18000dd89  jnz     short loc_18000DD81
0x18000dd8b  mov     rdx, r9; Src
0x18000dd8e  lea     rcx, [rbp+37h+psz]; void *
0x18000dd92  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000dd97  mov     rbx, [rsi]
0x18000dd9a  mov     rbx, [rbx]
0x18000dd9d  mov     rax, [rsi]
0x18000dda0  cmp     rbx, [rax+8]
0x18000dda4  jz      loc_18000DF9E
0x18000ddaa  mov     rsi, [rbx]
0x18000ddad  cmp     [rsi+1], r15b
0x18000ddb1  jz      loc_18000DE4C
0x18000ddb7  cmp     [rsi], r15b
0x18000ddba  jz      loc_18000DE4C
0x18000ddc0  lea     r15, [rbp+37h+psz]
0x18000ddc4  cmp     [rbp+37h+var_60], 8
0x18000ddc9  cmovnb  r15, [rbp+37h+psz]
0x18000ddce  xor     eax, eax
0x18000ddd0  mov     edi, eax
0x18000ddd2  mov     [rbp+37h+var_90], rax
0x18000ddd6  mov     [rbp+37h+var_B0], eax
0x18000ddd9  mov     [rbp+37h+var_40], 7
0x18000dde1  mov     [rbp+37h+var_48], rax
0x18000dde5  mov     word ptr [rbp+37h+String1], ax
0x18000dde9  mov     rcx, [rsi+10h]
0x18000dded  mov     rax, [rcx]
0x18000ddf0  lea     rdx, [rbp+37h+String1]
0x18000ddf4  mov     rax, [rax+10h]
0x18000ddf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddfd  xor     edx, edx
0x18000ddff  cmp     [rbp+37h+var_48], rdx
0x18000de03  jz      short loc_18000DE59
0x18000de05  lea     rcx, [rbp+37h+String1]
0x18000de09  cmp     [rbp+37h+var_40], 8
0x18000de0e  cmovnb  rcx, [rbp+37h+String1]; String1
0x18000de13  mov     rdx, r14; String2
0x18000de16  call    cs:__imp__wcsicmp
0x18000de1c  xor     edx, edx
0x18000de1e  test    eax, eax
0x18000de20  jz      short loc_18000DE59
0x18000de22  cmp     [rbp+37h+var_40], 8
0x18000de27  jb      short loc_18000DE33
0x18000de29  mov     rcx, [rbp+37h+String1]
0x18000de2d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000de33  xor     r15d, r15d
0x18000de36  mov     [r12], r15d
0x18000de3a  test    rdi, rdi
0x18000de3d  jz      short loc_18000DE48
0x18000de3f  mov     rcx, rdi; bstrString
0x18000de42  call    cs:__imp_SysFreeString
0x18000de48  mov     r14, [rbp+37h+var_A0]
0x18000de4c  add     rbx, 8
0x18000de50  mov     rsi, [rbp+37h+var_88]
0x18000de54  jmp     loc_18000DD9D
0x18000de59  mov     rcx, [rsi+10h]
0x18000de5d  mov     al, [rcx+0Ch]
0x18000de60  dec     al
0x18000de62  test    al, 0FDh
0x18000de64  jz      short loc_18000DEC6
0x18000de66  mov     r14d, 1
0x18000de6c  cmp     byte ptr [rcx+0Ch], 2
0x18000de70  jnz     loc_18000DF11
0x18000de76  mov     dword ptr [rbp+37h+var_A8], edx
0x18000de79  mov     rax, [rcx]
0x18000de7c  lea     rdx, [rbp+37h+var_A8]
0x18000de80  mov     rax, [rax+38h]
0x18000de84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de89  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000de8d  xor     eax, eax
0x18000de8f  inc     r8; unsigned __int64
0x18000de92  cmp     [r15+r8*2], ax
0x18000de97  jnz     short loc_18000DE8F
0x18000de99  mov     rdx, r15; unsigned __int16 *
0x18000de9c  mov     rcx, rsi; this
0x18000de9f  call    ?GetCharArea@FilterAgent@@AEBAKPEBG_K@Z; FilterAgent::GetCharArea(ushort const *,unsigned __int64)
0x18000dea4  mov     ecx, dword ptr [rbp+37h+var_A8]
0x18000dea7  not     ecx
0x18000dea9  mov     esi, r14d
0x18000deac  xor     r15d, r15d
0x18000deaf  test    eax, ecx
0x18000deb1  jz      short loc_18000DEBE
0x18000deb3  mov     ecx, r14d
0x18000deb6  mov     [rbp+37h+var_B0], ecx
0x18000deb9  mov     r14d, r15d
0x18000debc  jmp     short loc_18000DF1C
0x18000debe  mov     ecx, r15d
0x18000dec1  mov     [rbp+37h+var_B0], ecx
0x18000dec4  jmp     short loc_18000DF1C
0x18000dec6  mov     [rbp+37h+var_A8], rdx
0x18000deca  mov     rcx, [rsi+8]
0x18000dece  mov     rax, [rcx]
0x18000ded1  lea     rdx, [rbp+37h+var_A8]
0x18000ded5  mov     [rsp+0F0h+var_C8], rdx
0x18000deda  lea     rdx, [rbp+37h+var_B0]
0x18000dede  mov     [rsp+0F0h+var_D0], rdx
0x18000dee3  mov     r9d, [rbp+37h+arg_28]
0x18000dee7  mov     r8, [rbp+37h+var_98]
0x18000deeb  mov     rdx, r15
0x18000deee  mov     rax, [rax+30h]
0x18000def2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def7  mov     r14d, eax
0x18000defa  xor     r15d, r15d
0x18000defd  test    eax, eax
0x18000deff  jnz     short loc_18000DF14
0x18000df01  mov     ecx, [rbp+37h+var_B0]
0x18000df04  test    ecx, ecx
0x18000df06  cmovz   rdi, [rbp+37h+var_A8]
0x18000df0b  mov     [rbp+37h+var_90], rdi
0x18000df0f  jmp     short loc_18000DF17
0x18000df11  xor     r15d, r15d
0x18000df14  mov     ecx, [rbp+37h+var_B0]
0x18000df17  mov     esi, 1
0x18000df1c  cmp     [rbp+37h+var_40], 8
0x18000df21  jb      short loc_18000DF30
0x18000df23  mov     rcx, [rbp+37h+String1]
0x18000df27  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000df2d  mov     ecx, [rbp+37h+var_B0]
0x18000df30  test    r14d, r14d
0x18000df33  jnz     loc_18000DE36
0x18000df39  movzx   eax, r13b
0x18000df3d  test    r13b, r13b
0x18000df40  cmovz   eax, esi
0x18000df43  mov     r13b, al
0x18000df46  mov     [r12], ecx
0x18000df4a  cmp     ecx, esi
0x18000df4c  jz      short loc_18000DF78
0x18000df4e  cmp     [rdi], r15w
0x18000df52  jnz     short loc_18000DF59
0x18000df54  mov     r8, r15
0x18000df57  jmp     short loc_18000DF67
0x18000df59  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000df5d  inc     r8
0x18000df60  cmp     [rdi+r8*2], r15w
0x18000df65  jnz     short loc_18000DF5D
0x18000df67  mov     rdx, rdi; Src
0x18000df6a  lea     rcx, [rbp+37h+psz]; void *
0x18000df6e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000df73  jmp     loc_18000DE3A
0x18000df78  lea     rcx, [rbp+37h+psz]
0x18000df7c  cmp     [rbp+37h+var_60], 8
0x18000df81  cmovnb  rcx, [rbp+37h+psz]
0x18000df86  mov     [rbp+37h+var_68], r15
0x18000df8a  mov     [rcx], r15w
0x18000df8e  test    rdi, rdi
0x18000df91  jz      short loc_18000DFA8
0x18000df93  mov     rcx, rdi; bstrString
0x18000df96  call    cs:__imp_SysFreeString
0x18000df9c  jmp     short loc_18000DFA8
0x18000df9e  test    r13b, r13b
0x18000dfa1  jz      short loc_18000DFC4
0x18000dfa3  mov     esi, 1
0x18000dfa8  cmp     [r12], esi
0x18000dfac  jz      short loc_18000DFC4
0x18000dfae  lea     rcx, [rbp+37h+psz]
0x18000dfb2  cmp     [rbp+37h+var_60], 8
0x18000dfb7  cmovnb  rcx, [rbp+37h+psz]; psz
0x18000dfbc  call    cs:__imp_SysAllocString
0x18000dfc2  jmp     short loc_18000DFC7
0x18000dfc4  mov     rax, r15
0x18000dfc7  mov     rcx, [rbp+37h+var_80]
0x18000dfcb  mov     [rcx], rax
0x18000dfce  cmp     [rbp+37h+var_60], 8
0x18000dfd3  jb      short loc_18000DFDF
0x18000dfd5  mov     rcx, [rbp+37h+psz]
0x18000dfd9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dfdf  mov     rcx, [rbp+37h+var_38]
0x18000dfe3  xor     rcx, rsp; StackCookie
0x18000dfe6  call    __security_check_cookie
0x18000dfeb  mov     rbx, [rsp+0F0h+arg_0]
0x18000dff3  add     rsp, 0C0h
0x18000dffa  pop     r15
0x18000dffc  pop     r14
0x18000dffe  pop     r13
0x18000e000  pop     r12
0x18000e002  pop     rdi
0x18000e003  pop     rsi
0x18000e004  pop     rbp
0x18000e005  retn
```
