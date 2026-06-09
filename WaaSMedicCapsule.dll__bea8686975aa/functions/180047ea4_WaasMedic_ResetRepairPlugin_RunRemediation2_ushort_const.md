# WaasMedic::ResetRepairPlugin::RunRemediation2(ushort const *)

- ea: `0x180047ea4`
- end: `0x180048155`
- name: `?RunRemediation2@ResetRepairPlugin@WaasMedic@@AEAAJPEBG@Z`
- size: `689`
- prototype: `__int64 __fastcall(WaasMedic::ResetRepairPlugin *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047580`

## callees

- `0x180003bb0`
- `0x180005b30`
- `0x180007520`
- `0x180007590`
- `0x18000ab8c`
- `0x180017a64`
- `0x1800231d0`
- `0x18002543c`
- `0x18002acd8`
- `0x180047828`
- `0x180047ea4`
- `0x18004a840`
- `0x18004aa4c`

## string_xrefs

- `0x180048041`: `Failed to read content of [%s]`
- `0x180048080`: `rmdir /s /q %TARGETOSDRIVE%\Windows.old\Users`
- `0x180047ecf`: `ResetRepairPlugin: RunRemediation2 starts`
- `0x1800480a3`: `ResetRepairPlugin: Find old command in target script, update command`
- `0x1800480e7`: `Failed to update command to target file`
- `0x1800480c2`: `ResetRepairPlugin: Save new command into target cmd file`
- `0x180048104`: `ResetRepairPlugin: RunRemediation2 completes`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::ResetRepairPlugin::RunRemediation2(
        WaasMedic::ResetRepairPlugin *this,
        const unsigned __int16 *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // edi
  __int128 *v7; // r9
  __int64 v8; // rax
  __int128 *v9; // rax
  __int64 v10; // rcx
  __int128 *v11; // r8
  __int128 *v12; // rsi
  char *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int128 v17; // [rsp+48h] [rbp-61h] BYREF
  __int128 v18; // [rsp+58h] [rbp-51h]
  __int128 v19; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp-31h]
  unsigned __int64 v21; // [rsp+80h] [rbp-29h]
  __int128 v22; // [rsp+88h] [rbp-21h] BYREF
  __int128 v23; // [rsp+98h] [rbp-11h]
  _OWORD Src[2]; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v25[32]; // [rsp+C8h] [rbp+1Fh] BYREF

  LogLevelW(5u, L"ResetRepairPlugin: RunRemediation2 starts");
  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(Src[0]) = *a2;
  v3 = std::wstring::append(Src, L":\\Recovery\\OEM");
  v22 = 0;
  v23 = 0;
  v22 = *(_OWORD *)v3;
  v23 = *(_OWORD *)(v3 + 16);
  *(_QWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 24) = 7;
  *(_WORD *)v3 = 0;
  std::wstring::~wstring(Src);
  if ( (_QWORD)v23 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  v6 = 0;
  v7 = &v22;
  if ( *((_QWORD *)&v23 + 1) > 7u )
    v7 = (__int128 *)v22;
  std::wstring::wstring(v25, v4, v5, v7, v23, L"\\", 1);
  v8 = std::wstring::append(v25, (void *)L"AfterImageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd");
  v17 = 0;
  v18 = 0u;
  v17 = *(_OWORD *)v8;
  v18 = *(_OWORD *)(v8 + 16);
  *(_QWORD *)(v8 + 16) = 0;
  *(_QWORD *)(v8 + 24) = 7;
  *(_WORD *)v8 = 0;
  std::wstring::~wstring(v25);
  v9 = &v17;
  if ( *((_QWORD *)&v18 + 1) > 7u )
    v9 = (__int128 *)v17;
  *(_QWORD *)&Src[0] = v9;
  *((_QWORD *)&Src[0] + 1) = v18;
  if ( !(unsigned __int8)WaasMedic::FileExists(Src) )
    goto LABEL_20;
  v19 = 0;
  v20 = 0;
  v21 = 15;
  LOBYTE(v19) = 0;
  v6 = WaasMedic::ResetRepairPlugin::ReadFileContent(v10, &v17, &v19);
  if ( v6 < 0 )
  {
    v11 = &v17;
    if ( *((_QWORD *)&v18 + 1) > 7u )
      v11 = (__int128 *)v17;
    LogLevelW(2u, L"Failed to read content of [%s]", v11);
    goto LABEL_11;
  }
  v12 = &v19;
  if ( v21 > 0xF )
    v12 = (__int128 *)v19;
  if ( v20 < 0x2D
    || (v13 = (char *)v12 + v20,
        v14 = _std_search_1(v12, (char *)v12 + v20, "rmdir /s /q %TARGETOSDRIVE%\\Windows.old\\Users"),
        (char *)v14 == v13)
    || v14 - (_QWORD)v12 == -1
    || (LogLevelW(4u, L"ResetRepairPlugin: Find old command in target script, update command"),
        std::string::replace(&v19),
        LogLevelW(4u, L"ResetRepairPlugin: Save new command into target cmd file"),
        v6 = WaasMedic::ResetRepairPlugin::WriteToFile(v15, &v19, (__int64 *)&v17, (const WCHAR *)&v22),
        v6 >= 0) )
  {
    std::string::~string(&v19);
LABEL_20:
    LogLevelW(5u, L"ResetRepairPlugin: RunRemediation2 completes");
    goto LABEL_21;
  }
  LogLevelW(2u, L"Failed to update command to target file");
LABEL_11:
  std::string::~string(&v19);
LABEL_21:
  std::wstring::~wstring(&v17);
  std::wstring::~wstring(&v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180047ea4  mov     [rsp-8+arg_0], rbx
0x180047ea9  mov     [rsp-8+arg_10], rsi
0x180047eae  push    rbp
0x180047eaf  push    rdi
0x180047eb0  push    r14
0x180047eb2  lea     rbp, [rsp-47h]
0x180047eb7  sub     rsp, 0F0h
0x180047ebe  mov     rax, cs:__security_cookie
0x180047ec5  xor     rax, rsp
0x180047ec8  mov     [rbp+57h+var_18], rax
0x180047ecc  mov     rbx, rdx
0x180047ecf  lea     rdx, aResetrepairplu_4; "ResetRepairPlugin: RunRemediation2 star"...
0x180047ed6  mov     ecx, 5; unsigned __int8
0x180047edb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047ee0  xorps   xmm0, xmm0
0x180047ee3  movups  [rbp+57h+Src], xmm0
0x180047ee7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000001
0x180047eef  movdqu  [rbp+57h+var_48], xmm1
0x180047ef4  movzx   eax, word ptr [rbx]
0x180047ef7  mov     word ptr [rbp+57h+Src], ax
0x180047efb  xor     eax, eax
0x180047efd  mov     word ptr [rbp+57h+Src+2], ax
0x180047f01  lea     rdx, aRecoveryOem; ":\\Recovery\\OEM"
0x180047f08  lea     rcx, [rbp+57h+Src]; Src
0x180047f0c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180047f11  xorps   xmm0, xmm0
0x180047f14  movups  [rbp+57h+var_78], xmm0
0x180047f18  xorps   xmm1, xmm1
0x180047f1b  movdqu  [rbp+57h+var_68], xmm1
0x180047f20  movups  xmm0, xmmword ptr [rax]
0x180047f23  movups  [rbp+57h+var_78], xmm0
0x180047f27  movups  xmm1, xmmword ptr [rax+10h]
0x180047f2b  movups  [rbp+57h+var_68], xmm1
0x180047f2f  mov     qword ptr [rax+10h], 0
0x180047f37  mov     ebx, 7
0x180047f3c  mov     [rax+18h], rbx
0x180047f40  xor     ecx, ecx
0x180047f42  mov     [rax], cx
0x180047f45  lea     rcx, [rbp+57h+Src]; void *
0x180047f49  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047f4e  mov     rcx, qword ptr [rbp+57h+var_68]
0x180047f52  mov     rax, 7FFFFFFFFFFFFFFEh
0x180047f5c  sub     rax, rcx
0x180047f5f  cmp     rax, 1
0x180047f63  jb      loc_18004814F
0x180047f69  xor     edi, edi
0x180047f6b  lea     r9, [rbp+57h+var_78]
0x180047f6f  cmp     qword ptr [rbp+57h+var_68+8], rbx
0x180047f73  cmova   r9, qword ptr [rbp+57h+var_78]
0x180047f78  mov     [rsp+100h+var_D0], 1
0x180047f81  lea     rax, asc_18006E878; "\\"
0x180047f88  mov     [rsp+100h+var_D8], rax
0x180047f8d  mov     [rsp+100h+var_E0], rcx
0x180047f92  lea     rcx, [rbp+57h+var_38]
0x180047f96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180047f9b  nop
0x180047f9c  lea     rdx, aAfterimageappl; "AfterImageApply_BDB0C1E8-6951-46C4-AB7F"...
0x180047fa3  lea     rcx, [rbp+57h+var_38]; Src
0x180047fa7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180047fac  xorps   xmm0, xmm0
0x180047faf  movups  [rbp+57h+var_B8], xmm0
0x180047fb3  mov     qword ptr [rbp+57h+var_A8], rdi
0x180047fb7  mov     qword ptr [rbp+57h+var_A8+8], rdi
0x180047fbb  movups  xmm0, xmmword ptr [rax]
0x180047fbe  movups  [rbp+57h+var_B8], xmm0
0x180047fc2  movups  xmm1, xmmword ptr [rax+10h]
0x180047fc6  movups  [rbp+57h+var_A8], xmm1
0x180047fca  mov     [rax+10h], rdi
0x180047fce  mov     [rax+18h], rbx
0x180047fd2  xor     ecx, ecx
0x180047fd4  mov     [rax], cx
0x180047fd7  lea     rcx, [rbp+57h+var_38]; void *
0x180047fdb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047fe0  lea     rax, [rbp+57h+var_B8]
0x180047fe4  cmp     qword ptr [rbp+57h+var_A8+8], rbx
0x180047fe8  cmova   rax, qword ptr [rbp+57h+var_B8]
0x180047fed  mov     qword ptr [rbp+57h+Src], rax
0x180047ff1  mov     rax, qword ptr [rbp+57h+var_A8]
0x180047ff5  mov     qword ptr [rbp+57h+Src+8], rax
0x180047ff9  lea     rcx, [rbp+57h+Src]
0x180047ffd  call    ?FileExists@WaasMedic@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WaasMedic::FileExists(std::basic_string_view<ushort> const &)
0x180048002  test    al, al
0x180048004  jz      loc_180048104
0x18004800a  xorps   xmm0, xmm0
0x18004800d  movups  [rbp+57h+var_98], xmm0
0x180048011  mov     [rbp+57h+var_88], rdi
0x180048015  mov     [rbp+57h+var_80], 0Fh
0x18004801d  mov     byte ptr [rbp+57h+var_98], dil
0x180048021  lea     r8, [rbp+57h+var_98]
0x180048025  lea     rdx, [rbp+57h+var_B8]
0x180048029  call    ?ReadFileContent@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; WaasMedic::ResetRepairPlugin::ReadFileContent(std::wstring const &,std::string &)
0x18004802e  mov     edi, eax
0x180048030  test    eax, eax
0x180048032  jns     short loc_18004805F
0x180048034  lea     r8, [rbp+57h+var_B8]
0x180048038  cmp     qword ptr [rbp+57h+var_A8+8], rbx
0x18004803c  cmova   r8, qword ptr [rbp+57h+var_B8]
0x180048041  lea     rdx, aFailedToReadCo; "Failed to read content of [%s]"
0x180048048  lea     ecx, [rbx-5]; unsigned __int8
0x18004804b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180048050  nop
0x180048051  lea     rcx, [rbp+57h+var_98]
0x180048055  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004805a  jmp     loc_180048116
0x18004805f  mov     rax, [rbp+57h+var_88]
0x180048063  lea     rsi, [rbp+57h+var_98]
0x180048067  cmp     [rbp+57h+var_80], 0Fh
0x18004806c  cmova   rsi, qword ptr [rbp+57h+var_98]
0x180048071  mov     r9d, 2Dh ; '-'
0x180048077  cmp     rax, r9
0x18004807a  jb      short loc_1800480FB
0x18004807c  lea     rbx, [rax+rsi]
0x180048080  lea     r8, aRmdirSQTargeto; "rmdir /s /q %TARGETOSDRIVE%\\Windows.ol"...
0x180048087  mov     rdx, rbx
0x18004808a  mov     rcx, rsi
0x18004808d  call    __std_search_1
0x180048092  mov     r14, rax
0x180048095  cmp     rax, rbx
0x180048098  jz      short loc_1800480FB
0x18004809a  sub     r14, rsi
0x18004809d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800480a1  jz      short loc_1800480FB
0x1800480a3  lea     rdx, aResetrepairplu_3; "ResetRepairPlugin: Find old command in "...
0x1800480aa  mov     ebx, 4
0x1800480af  mov     ecx, ebx; unsigned __int8
0x1800480b1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800480b6  mov     rdx, r14
0x1800480b9  lea     rcx, [rbp+57h+var_98]; Src
0x1800480bd  call    ?replace@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0QEBD@Z; std::string::replace(unsigned __int64,unsigned __int64,char const * const)
0x1800480c2  lea     rdx, aResetrepairplu_11; "ResetRepairPlugin: Save new command int"...
0x1800480c9  mov     ecx, ebx; unsigned __int8
0x1800480cb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800480d0  lea     r9, [rbp+57h+var_78]
0x1800480d4  lea     r8, [rbp+57h+var_B8]
0x1800480d8  lea     rdx, [rbp+57h+var_98]
0x1800480dc  call    ?WriteToFile@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@1@Z; WaasMedic::ResetRepairPlugin::WriteToFile(std::string const &,std::wstring const &,std::wstring const &)
0x1800480e1  mov     edi, eax
0x1800480e3  test    eax, eax
0x1800480e5  jns     short loc_1800480FB
0x1800480e7  lea     rdx, aFailedToUpdate; "Failed to update command to target file"
0x1800480ee  lea     ecx, [rbx-2]; unsigned __int8
0x1800480f1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800480f6  jmp     loc_180048051
0x1800480fb  lea     rcx, [rbp+57h+var_98]
0x1800480ff  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180048104  lea     rdx, aResetrepairplu_0; "ResetRepairPlugin: RunRemediation2 comp"...
0x18004810b  mov     ecx, 5; unsigned __int8
0x180048110  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180048115  nop
0x180048116  lea     rcx, [rbp+57h+var_B8]; void *
0x18004811a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004811f  nop
0x180048120  lea     rcx, [rbp+57h+var_78]; void *
0x180048124  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048129  mov     eax, edi
0x18004812b  mov     rcx, [rbp+57h+var_18]
0x18004812f  xor     rcx, rsp; StackCookie
0x180048132  call    __security_check_cookie
0x180048137  lea     r11, [rsp+100h+var_10]
0x18004813f  mov     rbx, [r11+20h]
0x180048143  mov     rsi, [r11+30h]
0x180048147  mov     rsp, r11
0x18004814a  pop     r14
0x18004814c  pop     rdi
0x18004814d  pop     rbp
0x18004814e  retn
0x18004814f  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
