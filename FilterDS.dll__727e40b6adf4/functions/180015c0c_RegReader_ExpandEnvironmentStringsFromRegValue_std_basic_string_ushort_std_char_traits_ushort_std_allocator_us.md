# RegReader::ExpandEnvironmentStringsFromRegValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180015c0c`
- end: `0x180015ddc`
- name: `?ExpandEnvironmentStringsFromRegValue@RegReader@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `464`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800127b8`
- `0x180013d40`

## callees

- `0x18000a450`
- `0x18000cef4`
- `0x180015c0c`
- `0x180015de4`
- `0x18001637c`
- `0x180021822`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180015c5f`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180015c5f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015d63`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180015d63`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180015cac`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180015cac`

## pseudocode

```c
void __fastcall RegReader::ExpandEnvironmentStringsFromRegValue(_QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rsi
  UserHelpers::UserCache *Current; // rax
  _QWORD *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  __int64 v9; // r8
  const WCHAR *v10; // rcx
  __int64 v11; // rdi
  int v12; // [rsp+20h] [rbp-E0h]
  __int64 *v13; // [rsp+28h] [rbp-D8h]
  volatile signed __int32 *v14; // [rsp+30h] [rbp-D0h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v1 = a1;
  v2 = a1 + 2;
  if ( a1[2] )
  {
    memset_0(Dst, 0, 0x208u);
    if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
    {
      Current = UserHelpers::UserCache::GetCurrent();
      UserHelpers::UserCache::GetUserTokenHandle(Current);
      if ( v1[3] < 8u )
        v4 = v1;
      else
        v4 = (_QWORD *)*v1;
      if ( v13 )
        v5 = *v13;
      else
        v5 = 0;
      v6 = ExpandEnvStringForUser(v5, v4, Dst, 260);
      if ( v6 >= 0 )
      {
        if ( Dst[0] )
        {
          v9 = -1;
          do
            ++v9;
          while ( Dst[v9] );
        }
        std::wstring::assign(v1, Dst);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(retaddr, v7, v8, (const char *)(unsigned int)v6, v12);
        if ( v1[3] >= 8u )
          v1 = (_QWORD *)*v1;
        *v2 = 0;
        *(_WORD *)v1 = 0;
      }
      if ( v14 && !_InterlockedDecrement(v14 + 2) )
      {
        (**(void (__fastcall ***)())v14)();
        if ( !_InterlockedDecrement(v14 + 3) )
          (*(void (__fastcall **)())(*(_QWORD *)v14 + 8LL))();
      }
    }
    else
    {
      if ( v1[3] < 8u )
        v10 = (const WCHAR *)v1;
      else
        v10 = (const WCHAR *)*v1;
      if ( ExpandEnvironmentStringsW(v10, Dst, 0x104u) - 1 > 0x103 )
      {
        if ( v1[3] >= 8u )
          v1 = (_QWORD *)*v1;
        *v2 = 0;
        *(_WORD *)v1 = 0;
      }
      else
      {
        if ( Dst[0] )
        {
          v11 = -1;
          do
            ++v11;
          while ( Dst[v11] );
        }
        std::wstring::assign(v1, Dst);
      }
    }
  }
}

```

## disassembly

```asm
0x180015c0c  mov     [rsp-8+arg_8], rbx
0x180015c11  mov     [rsp-8+arg_10], rsi
0x180015c16  push    rbp
0x180015c17  push    rdi
0x180015c18  push    r14
0x180015c1a  lea     rbp, [rsp-160h]
0x180015c22  sub     rsp, 260h
0x180015c29  mov     rax, cs:__security_cookie
0x180015c30  xor     rax, rsp
0x180015c33  mov     [rbp+170h+var_20], rax
0x180015c3a  mov     rbx, rcx
0x180015c3d  xor     r14d, r14d
0x180015c40  lea     rsi, [rcx+10h]
0x180015c44  cmp     [rsi], r14
0x180015c47  jz      loc_180015DB5
0x180015c4d  xor     edx, edx; Val
0x180015c4f  mov     r8d, 208h; Size
0x180015c55  lea     rcx, [rsp+270h+Dst]; void *
0x180015c5a  call    memset_0
0x180015c5f  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180015c65  test    al, al
0x180015c67  jz      loc_180015D49
0x180015c6d  call    ?GetCurrent@UserCache@UserHelpers@@SAAEAV12@XZ; UserHelpers::UserCache::GetCurrent(void)
0x180015c72  lea     rdx, [rsp+270h+var_248]
0x180015c77  mov     rcx, rax; this
0x180015c7a  call    ?GetUserTokenHandle@UserCache@UserHelpers@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; UserHelpers::UserCache::GetUserTokenHandle(void)
0x180015c7f  nop
0x180015c80  cmp     qword ptr [rbx+18h], 8
0x180015c85  jb      short loc_180015C8C
0x180015c87  mov     rdx, [rbx]
0x180015c8a  jmp     short loc_180015C8F
0x180015c8c  mov     rdx, rbx
0x180015c8f  mov     rax, [rsp+270h+var_248]
0x180015c94  test    rax, rax
0x180015c97  jz      short loc_180015C9E
0x180015c99  mov     rcx, [rax]
0x180015c9c  jmp     short loc_180015CA1
0x180015c9e  mov     rcx, r14
0x180015ca1  mov     r9d, 104h
0x180015ca7  lea     r8, [rsp+270h+Dst]
0x180015cac  call    cs:__imp_ExpandEnvStringForUser
0x180015cb2  mov     rcx, [rbp+178h]; this
0x180015cb9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015cbd  test    eax, eax
0x180015cbf  jns     short loc_180015CDC
0x180015cc1  mov     r9d, eax; char *
0x180015cc4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015cc9  cmp     qword ptr [rbx+18h], 8
0x180015cce  jb      short loc_180015CD3
0x180015cd0  mov     rbx, [rbx]
0x180015cd3  mov     [rsi], r14
0x180015cd6  mov     [rbx], r14w
0x180015cda  jmp     short loc_180015D09
0x180015cdc  cmp     [rsp+270h+Dst], r14w
0x180015ce2  jnz     short loc_180015CE9
0x180015ce4  mov     r8, r14
0x180015ce7  jmp     short loc_180015CFB
0x180015ce9  lea     rax, [rsp+270h+Dst]
0x180015cee  mov     r8, rdi
0x180015cf1  inc     r8
0x180015cf4  cmp     [rax+r8*2], r14w
0x180015cf9  jnz     short loc_180015CF1
0x180015cfb  lea     rdx, [rsp+270h+Dst]; Src
0x180015d00  mov     rcx, rbx; void *
0x180015d03  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180015d08  nop
0x180015d09  mov     rbx, [rsp+270h+var_240]
0x180015d0e  test    rbx, rbx
0x180015d11  jz      short loc_180015D47
0x180015d13  mov     eax, edi
0x180015d15  lock xadd [rbx+8], eax
0x180015d1a  add     eax, edi
0x180015d1c  jnz     short loc_180015D47
0x180015d1e  mov     rax, [rbx]
0x180015d21  mov     rcx, rbx
0x180015d24  mov     rax, [rax]
0x180015d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d2c  mov     eax, edi
0x180015d2e  lock xadd [rbx+0Ch], eax
0x180015d33  add     eax, edi
0x180015d35  jnz     short loc_180015D47
0x180015d37  mov     rax, [rbx]
0x180015d3a  mov     rcx, rbx
0x180015d3d  mov     rax, [rax+8]
0x180015d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d46  nop
0x180015d47  jmp     short loc_180015DB5
0x180015d49  cmp     qword ptr [rbx+18h], 8
0x180015d4e  jb      short loc_180015D55
0x180015d50  mov     rcx, [rbx]
0x180015d53  jmp     short loc_180015D58
0x180015d55  mov     rcx, rbx; lpSrc
0x180015d58  mov     r8d, 104h; nSize
0x180015d5e  lea     rdx, [rsp+270h+Dst]; lpDst
0x180015d63  call    cs:__imp_ExpandEnvironmentStringsW
0x180015d69  dec     eax
0x180015d6b  cmp     eax, 103h
0x180015d70  ja      short loc_180015DA4
0x180015d72  cmp     [rsp+270h+Dst], r14w
0x180015d78  jnz     short loc_180015D7F
0x180015d7a  mov     rdi, r14
0x180015d7d  jmp     short loc_180015D92
0x180015d7f  lea     rax, [rsp+270h+Dst]
0x180015d84  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015d88  inc     rdi
0x180015d8b  cmp     [rax+rdi*2], r14w
0x180015d90  jnz     short loc_180015D88
0x180015d92  mov     r8, rdi
0x180015d95  lea     rdx, [rsp+270h+Dst]; Src
0x180015d9a  mov     rcx, rbx; void *
0x180015d9d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180015da2  jmp     short loc_180015DB5
0x180015da4  cmp     qword ptr [rbx+18h], 8
0x180015da9  jb      short loc_180015DAE
0x180015dab  mov     rbx, [rbx]
0x180015dae  mov     [rsi], r14
0x180015db1  mov     [rbx], r14w
0x180015db5  mov     rcx, [rbp+170h+var_20]
0x180015dbc  xor     rcx, rsp; StackCookie
0x180015dbf  call    __security_check_cookie
0x180015dc4  lea     r11, [rsp+270h+var_10]
0x180015dcc  mov     rbx, [r11+28h]
0x180015dd0  mov     rsi, [r11+30h]
0x180015dd4  mov     rsp, r11
0x180015dd7  pop     r14
0x180015dd9  pop     rdi
0x180015dda  pop     rbp
0x180015ddb  retn
```
