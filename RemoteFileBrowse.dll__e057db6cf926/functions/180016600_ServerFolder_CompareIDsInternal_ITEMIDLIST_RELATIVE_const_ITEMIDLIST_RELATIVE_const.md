# ServerFolder::CompareIDsInternal(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180016600`
- end: `0x180016720`
- name: `?CompareIDsInternal@ServerFolder@@MEAAIPEFBU_ITEMIDLIST_RELATIVE@@0@Z`
- size: `288`
- prototype: `__int64 __fastcall(ServerFolder *this, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002030`
- `0x18000591c`
- `0x180006870`
- `0x180016600`
- `0x180016d60`

## pseudocode

```c
__int64 __fastcall ServerFolder::CompareIDsInternal(
        ServerFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _ITEMIDLIST_RELATIVE *a3)
{
  int v4; // eax
  int v5; // ebx
  size_t v6; // rdi
  const wchar_t *v7; // rdx
  size_t v8; // rsi
  const wchar_t *v9; // rcx
  size_t v10; // r8
  unsigned int v11; // ebx
  wchar_t *S2[2]; // [rsp+20h] [rbp-50h] BYREF
  size_t v14; // [rsp+30h] [rbp-40h]
  unsigned __int64 v15; // [rsp+38h] [rbp-38h]
  wchar_t *S1[2]; // [rsp+40h] [rbp-30h] BYREF
  size_t N; // [rsp+50h] [rbp-20h]
  unsigned __int64 v18; // [rsp+58h] [rbp-18h]

  v4 = 1;
  if ( !a2 || (v5 = 0, !*(_WORD *)a2) )
    v5 = 1;
  if ( a3 && *(_WORD *)a3 )
    v4 = 0;
  if ( v5 || v4 )
  {
    return (unsigned int)(v5 - v4);
  }
  else
  {
    *(_OWORD *)S1 = 0;
    N = 0;
    v18 = 7;
    LOWORD(S1[0]) = 0;
    *(_OWORD *)S2 = 0;
    v14 = 0;
    v15 = 7;
    LOWORD(S2[0]) = 0;
    RfbPidlHelper<ServerFixedData>::GetStringData(a2, S1);
    RfbPidlHelper<ServerFixedData>::GetStringData(a3, S2);
    v6 = v14;
    v7 = (const wchar_t *)S2;
    if ( v15 > 7 )
      v7 = S2[0];
    v8 = N;
    v9 = (const wchar_t *)S1;
    if ( v18 > 7 )
      v9 = S1[0];
    v10 = v14;
    if ( v14 >= N )
      v10 = N;
    v11 = wmemcmp(v9, v7, v10);
    if ( !v11 )
    {
      if ( v8 >= v6 )
        v11 = v8 > v6;
      else
        v11 = -1;
    }
    std::wstring::~wstring((char **)S2);
    std::wstring::~wstring((char **)S1);
  }
  return v11;
}

```

## disassembly

```asm
0x180016600  mov     [rsp-18h+arg_0], rbx
0x180016605  mov     [rsp-18h+arg_18], rsi
0x18001660a  push    rbp
0x18001660b  push    rdi
0x18001660c  push    r14
0x18001660e  mov     rbp, rsp
0x180016611  sub     rsp, 70h
0x180016615  mov     rax, cs:__security_cookie
0x18001661c  xor     rax, rsp
0x18001661f  mov     [rbp+var_10], rax
0x180016623  mov     rdi, r8
0x180016626  mov     r8, rdx
0x180016629  mov     eax, 1
0x18001662e  xor     r14d, r14d
0x180016631  test    rdx, rdx
0x180016634  jz      short loc_18001663F
0x180016636  cmp     [rdx], r14w
0x18001663a  mov     ebx, r14d
0x18001663d  jnz     short loc_180016641
0x18001663f  mov     ebx, eax
0x180016641  test    rdi, rdi
0x180016644  jz      short loc_18001664F
0x180016646  cmp     [rdi], r14w
0x18001664a  jz      short loc_18001664F
0x18001664c  mov     eax, r14d
0x18001664f  test    ebx, ebx
0x180016651  jnz     loc_1800166FB
0x180016657  test    eax, eax
0x180016659  jnz     loc_1800166FB
0x18001665f  xorps   xmm0, xmm0
0x180016662  movups  xmmword ptr [rbp+S1], xmm0
0x180016666  mov     [rbp+N], r14
0x18001666a  lea     ebx, [rax+7]
0x18001666d  mov     [rbp+var_18], rbx
0x180016671  mov     word ptr [rbp+S1], r14w
0x180016676  movups  xmmword ptr [rbp+S2], xmm0
0x18001667a  mov     [rbp+var_40], r14
0x18001667e  mov     [rbp+var_38], rbx
0x180016682  mov     word ptr [rbp+S2], r14w
0x180016687  lea     rdx, [rbp+S1]
0x18001668b  mov     rcx, r8
0x18001668e  call    ?GetStringData@?$RfbPidlHelper@UServerFixedData@@@@SAXPEFBU_ITEMIDLIST@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbPidlHelper<ServerFixedData>::GetStringData(_ITEMIDLIST const *,std::wstring &)
0x180016693  lea     rdx, [rbp+S2]
0x180016697  mov     rcx, rdi
0x18001669a  call    ?GetStringData@?$RfbPidlHelper@UServerFixedData@@@@SAXPEFBU_ITEMIDLIST@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbPidlHelper<ServerFixedData>::GetStringData(_ITEMIDLIST const *,std::wstring &)
0x18001669f  mov     rdi, [rbp+var_40]
0x1800166a3  lea     rdx, [rbp+S2]
0x1800166a7  cmp     [rbp+var_38], rbx
0x1800166ab  cmova   rdx, [rbp+S2]; S2
0x1800166b0  mov     rsi, [rbp+N]
0x1800166b4  lea     rcx, [rbp+S1]
0x1800166b8  cmp     [rbp+var_18], rbx
0x1800166bc  cmova   rcx, [rbp+S1]; S1
0x1800166c1  mov     r8, rdi
0x1800166c4  cmp     rdi, rsi
0x1800166c7  cmovnb  r8, rsi; N
0x1800166cb  call    wmemcmp
0x1800166d0  mov     ebx, eax
0x1800166d2  test    eax, eax
0x1800166d4  jnz     short loc_1800166E6
0x1800166d6  cmp     rsi, rdi
0x1800166d9  jnb     short loc_1800166E0
0x1800166db  or      ebx, 0FFFFFFFFh
0x1800166de  jmp     short loc_1800166E6
0x1800166e0  mov     ebx, r14d
0x1800166e3  setnbe  bl
0x1800166e6  lea     rcx, [rbp+S2]
0x1800166ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800166ef  nop
0x1800166f0  lea     rcx, [rbp+S1]
0x1800166f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800166f9  jmp     short loc_1800166FD
0x1800166fb  sub     ebx, eax
0x1800166fd  mov     eax, ebx
0x1800166ff  mov     rcx, [rbp+var_10]
0x180016703  xor     rcx, rsp; StackCookie
0x180016706  call    __security_check_cookie
0x18001670b  lea     r11, [rsp+70h+var_s0]
0x180016710  mov     rbx, [r11+20h]
0x180016714  mov     rsi, [r11+38h]
0x180016718  mov     rsp, r11
0x18001671b  pop     r14
0x18001671d  pop     rdi
0x18001671e  pop     rbp
0x18001671f  retn
```
