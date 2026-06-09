# GetDetails(_DIAGNOSTIC_BUFFER const &)

- ea: `0x180022198`
- end: `0x180022309`
- name: `?GetDetails@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_DIAGNOSTIC_BUFFER@@@Z`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800227c0`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x180020b58`
- `0x1800210f8`
- `0x18002178c`
- `0x180021a34`
- `0x180022198`
- `0x180022310`
- `0x180024030`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800222e1`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800222e1`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800222d7`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800222d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180022223`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180022223`

## string_xrefs

- `0x180022208`: `UserSharedServiceRequester`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetDetails(__int64 a1, __int64 a2)
{
  int v4; // ecx
  __int64 v5; // rax
  int v6; // ecx
  LPWSTR FileNameW; // rax
  __int64 v8; // rsi
  __int64 v9; // r8
  __int128 *Details; // rax
  __int64 v11; // r8
  __int128 v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v16[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[104]; // [rsp+D8h] [rbp-28h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v14);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v14, L"Process:");
  v4 = *(_DWORD *)(a2 + 8);
  v5 = *(_QWORD *)(a2 + 16);
  if ( !v4 )
  {
    if ( !v5 )
    {
      FileNameW = L"KernelRequester";
      goto LABEL_11;
    }
LABEL_9:
    FileNameW = PathFindFileNameW((LPCWSTR)(v5 + a2));
    goto LABEL_11;
  }
  if ( v5 )
    goto LABEL_9;
  v6 = v4 - 1;
  if ( v6 )
  {
    if ( v6 == 1 )
      FileNameW = L"UserSharedServiceRequester";
    else
      FileNameW = L"none";
  }
  else
  {
    FileNameW = L"UserProcessRequester";
  }
LABEL_11:
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v14, FileNameW);
  if ( *(_QWORD *)(a2 + 32) )
  {
    v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v14, L"-");
    Details = GetDetails(v13, a2 + *(_QWORD *)(a2 + 32), v9);
    v11 = *((_QWORD *)Details + 2);
    if ( *((_QWORD *)Details + 3) > 7u )
      Details = *(__int128 **)Details;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v8, Details, v11);
    std::wstring::_Tidy_deallocate(v13);
  }
  std::basic_stringbuf<unsigned short>::str(v15, a1);
  *(_QWORD *)&v15[*(int *)(v14 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)&v13[1] + *(int *)(v14 + 4) + 12) = *(_DWORD *)(v14 + 4) - 136;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v15);
  std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v16);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v17);
  return a1;
}

```

## disassembly

```asm
0x180022198  mov     [rsp-8+arg_10], rbx
0x18002219d  push    rbp
0x18002219e  push    rsi
0x18002219f  push    rdi
0x1800221a0  lea     rbp, [rsp-50h]
0x1800221a5  sub     rsp, 150h
0x1800221ac  mov     rax, cs:__security_cookie
0x1800221b3  xor     rax, rsp
0x1800221b6  mov     [rbp+60h+var_20], rax
0x1800221ba  mov     rbx, rdx
0x1800221bd  mov     rdi, rcx
0x1800221c0  mov     [rsp+160h+var_138], rcx
0x1800221c5  lea     rcx, [rsp+160h+var_110]
0x1800221ca  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800221cf  nop
0x1800221d0  lea     rdx, aProcess; "Process:"
0x1800221d7  lea     rcx, [rsp+160h+var_110]
0x1800221dc  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800221e1  mov     ecx, [rbx+8]
0x1800221e4  mov     rax, [rbx+10h]
0x1800221e8  test    ecx, ecx
0x1800221ea  jz      short loc_18002221A
0x1800221ec  test    rax, rax
0x1800221ef  jnz     short loc_18002221F
0x1800221f1  test    ecx, ecx
0x1800221f3  jz      short loc_18002222B
0x1800221f5  sub     ecx, 1
0x1800221f8  jz      short loc_180022211
0x1800221fa  cmp     ecx, 1
0x1800221fd  jz      short loc_180022208
0x1800221ff  lea     rax, aNone; "none"
0x180022206  jmp     short loc_180022232
0x180022208  lea     rax, aUsersharedserv; "UserSharedServiceRequester"
0x18002220f  jmp     short loc_180022232
0x180022211  lea     rax, aUserprocessreq; "UserProcessRequester"
0x180022218  jmp     short loc_180022232
0x18002221a  test    rax, rax
0x18002221d  jz      short loc_18002222B
0x18002221f  lea     rcx, [rax+rbx]; pszPath
0x180022223  call    cs:__imp_PathFindFileNameW
0x180022229  jmp     short loc_180022232
0x18002222b  lea     rax, aKernelrequeste; "KernelRequester"
0x180022232  mov     rdx, rax
0x180022235  lea     rcx, [rsp+160h+var_110]
0x18002223a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002223f  cmp     qword ptr [rbx+20h], 0
0x180022244  jz      short loc_180022290
0x180022246  lea     rdx, asc_180079CF4; "-"
0x18002224d  lea     rcx, [rsp+160h+var_110]
0x180022252  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180022257  mov     rsi, rax
0x18002225a  mov     rdx, [rbx+20h]
0x18002225e  add     rdx, rbx
0x180022261  lea     rcx, [rsp+160h+var_130]
0x180022266  call    ?GetDetails@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_REASON_BUFFER@@@Z; GetDetails(_REASON_BUFFER const *)
0x18002226b  nop
0x18002226c  mov     r8, [rax+10h]
0x180022270  cmp     qword ptr [rax+18h], 7
0x180022275  jbe     short loc_18002227A
0x180022277  mov     rax, [rax]
0x18002227a  mov     rdx, rax
0x18002227d  mov     rcx, rsi
0x180022280  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180022285  nop
0x180022286  lea     rcx, [rsp+160h+var_130]
0x18002228b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022290  mov     rdx, rdi
0x180022293  lea     rcx, [rsp+160h+var_108]
0x180022298  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002229d  nop
0x18002229e  mov     rcx, [rsp+160h+var_110]
0x1800222a3  movsxd  rdx, dword ptr [rcx+4]
0x1800222a7  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x1800222ae  mov     [rsp+rdx+160h+var_110], rax
0x1800222b3  mov     rcx, [rsp+160h+var_110]
0x1800222b8  movsxd  rdx, dword ptr [rcx+4]
0x1800222bc  lea     r8d, [rdx-88h]
0x1800222c3  mov     [rsp+rdx+160h+var_114], r8d
0x1800222c8  lea     rcx, [rsp+160h+var_108]
0x1800222cd  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x1800222d2  lea     rcx, [rsp+160h+var_100]
0x1800222d7  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x1800222dd  lea     rcx, [rbp+60h+var_88]
0x1800222e1  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800222e7  mov     rax, rdi
0x1800222ea  mov     rcx, [rbp+60h+var_20]
0x1800222ee  xor     rcx, rsp; StackCookie
0x1800222f1  call    __security_check_cookie
0x1800222f6  mov     rbx, [rsp+160h+arg_10]
0x1800222fe  add     rsp, 150h
0x180022305  pop     rdi
0x180022306  pop     rsi
0x180022307  pop     rbp
0x180022308  retn
```
