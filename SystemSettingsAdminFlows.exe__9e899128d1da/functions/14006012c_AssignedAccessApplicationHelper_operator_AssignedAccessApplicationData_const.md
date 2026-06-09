# AssignedAccessApplicationHelper::operator==(AssignedAccessApplicationData const &)

- ea: `0x14006012c`
- end: `0x140060272`
- name: `??8AssignedAccessApplicationHelper@@QEAA_NAEBUAssignedAccessApplicationData@@@Z`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005f1f8`
- `0x1400626f4`

## callees

- `0x140005f30`
- `0x140029eb8`
- `0x14002a2c0`
- `0x14002a3e8`
- `0x14006012c`
- `0x140060ad0`
- `0x140060b50`
- `0x14007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400601c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006021d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400601c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006021d`
- `KERNEL32!CompareStringOrdinal` at `0x140060238`
- `KERNEL32!CompareStringOrdinal` at `0x140060238`

## string_xrefs

- `0x14006017a`: `pcshell\shell\systemsettings\adminflows\assignedaccess\assignedaccesshelpers.h`

## pseudocode

```c
bool __fastcall AssignedAccessApplicationHelper::operator==(_QWORD *a1, _BYTE *a2)
{
  char v2; // bp
  int v5; // eax
  bool v6; // di
  __int64 v7; // rbx
  __int64 Arguments; // rax
  __int64 v9; // rax
  bool v10; // bl
  const WCHAR *v12; // rbx
  __int64 AppId; // rax
  const WCHAR *v14; // rcx
  bool v15; // zf
  bool v16; // bl
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = 0;
  v18 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 64LL))(*a1, &v18);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\assignedaccess\\assignedaccesshelpers.h",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  v6 = v18 == 3;
  v10 = 1;
  if ( (v18 == 3) == *a2 )
  {
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 40);
    Arguments = AssignedAccessApplicationHelper::GetArguments(a1, v19);
    v2 = 1;
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Arguments);
    if ( !(unsigned int)_o__wcsicmp(v9, v7) )
      v10 = 0;
  }
  if ( (v2 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v19);
  if ( v10 )
    return 0;
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 8);
  AppId = AssignedAccessApplicationHelper::GetAppId(a1, v19);
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(AppId);
  if ( v6 )
    v15 = (unsigned int)_o__wcsicmp(v14, v12) == 0;
  else
    v15 = CompareStringOrdinal(v14, -1, v12, -1, 1) == 2;
  v16 = v15;
  std::wstring::_Tidy_deallocate(v19);
  return v16;
}

```

## disassembly

```asm
0x14006012c  mov     [rsp+arg_10], rbx
0x140060131  mov     [rsp+arg_18], rbp
0x140060136  push    rsi
0x140060137  push    rdi
0x140060138  push    r14
0x14006013a  sub     rsp, 60h
0x14006013e  mov     rax, cs:__security_cookie
0x140060145  xor     rax, rsp
0x140060148  mov     [rsp+78h+var_20], rax
0x14006014d  xor     ebp, ebp
0x14006014f  mov     r14, rcx
0x140060152  mov     [rsp+78h+var_48], ebp
0x140060156  mov     rsi, rdx
0x140060159  mov     rcx, [rcx]
0x14006015c  lea     rdx, [rsp+78h+var_48]
0x140060161  mov     [rsp+78h+var_48], ebp
0x140060165  mov     rax, [rcx]
0x140060168  mov     rax, [rax+40h]
0x14006016c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060171  test    eax, eax
0x140060173  jns     short loc_14006018F
0x140060175  mov     rcx, [rsp+78h]; this
0x14006017a  lea     r8, aPcshellShellSy_18; "pcshell\\shell\\systemsettings\\adminfl"...
0x140060181  mov     r9d, eax; char *
0x140060184  mov     edx, 143h; void *
0x140060189  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006018f  cmp     [rsp+78h+var_48], 3
0x140060194  setz    dil
0x140060198  cmp     dil, [rsi]
0x14006019b  jnz     short loc_1400601D7
0x14006019d  lea     rcx, [rsi+28h]
0x1400601a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400601a6  mov     rcx, r14
0x1400601a9  lea     rdx, [rsp+78h+var_40]
0x1400601ae  mov     rbx, rax
0x1400601b1  call    ?GetArguments@AssignedAccessApplicationHelper@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AssignedAccessApplicationHelper::GetArguments(void)
0x1400601b6  mov     rcx, rax
0x1400601b9  mov     ebp, 1
0x1400601be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400601c3  mov     rcx, rax
0x1400601c6  mov     rdx, rbx
0x1400601c9  call    cs:__imp__o__wcsicmp
0x1400601cf  test    eax, eax
0x1400601d1  jnz     short loc_1400601D7
0x1400601d3  xor     bl, bl
0x1400601d5  jmp     short loc_1400601D9
0x1400601d7  mov     bl, 1
0x1400601d9  test    bpl, 1
0x1400601dd  jz      short loc_1400601E9
0x1400601df  lea     rcx, [rsp+78h+var_40]
0x1400601e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400601e9  test    bl, bl
0x1400601eb  jz      short loc_1400601F1
0x1400601ed  xor     al, al
0x1400601ef  jmp     short loc_140060250
0x1400601f1  lea     rcx, [rsi+8]
0x1400601f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400601fa  mov     rcx, r14
0x1400601fd  lea     rdx, [rsp+78h+var_40]
0x140060202  mov     rbx, rax
0x140060205  call    ?GetAppId@AssignedAccessApplicationHelper@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AssignedAccessApplicationHelper::GetAppId(void)
0x14006020a  mov     rcx, rax
0x14006020d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140060212  mov     rcx, rax; lpString1
0x140060215  test    dil, dil
0x140060218  jz      short loc_140060227
0x14006021a  mov     rdx, rbx
0x14006021d  call    cs:__imp__o__wcsicmp
0x140060223  test    eax, eax
0x140060225  jmp     short loc_140060241
0x140060227  or      edx, 0FFFFFFFFh; cchCount1
0x14006022a  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x140060232  mov     r9d, edx; cchCount2
0x140060235  mov     r8, rbx; lpString2
0x140060238  call    cs:__imp_CompareStringOrdinal
0x14006023e  cmp     eax, 2
0x140060241  lea     rcx, [rsp+78h+var_40]
0x140060246  setz    bl
0x140060249  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006024e  mov     al, bl
0x140060250  mov     rcx, [rsp+78h+var_20]
0x140060255  xor     rcx, rsp; StackCookie
0x140060258  call    __security_check_cookie
0x14006025d  lea     r11, [rsp+78h+var_18]
0x140060262  mov     rbx, [r11+30h]
0x140060266  mov     rbp, [r11+38h]
0x14006026a  mov     rsp, r11
0x14006026d  pop     r14
0x14006026f  pop     rdi
0x140060270  pop     rsi
0x140060271  retn
```
