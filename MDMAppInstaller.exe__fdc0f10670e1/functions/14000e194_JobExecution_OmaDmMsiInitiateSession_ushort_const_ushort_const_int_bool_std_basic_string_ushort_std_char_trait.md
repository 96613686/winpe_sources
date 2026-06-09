# JobExecution::OmaDmMsiInitiateSession(ushort const *,ushort const *,int,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000e194`
- end: `0x14000e4d0`
- name: `?OmaDmMsiInitiateSession@JobExecution@@CAJPEBG0H_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `828`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, char, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000cd78`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x1400074d4`
- `0x14000775c`
- `0x14000e194`
- `0x140011c90`
- `0x140011d58`
- `0x140012878`
- `0x140012c94`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000e480`
- `KERNEL32!LocalFree` at `0x14000e480`
- `msvcrt!swprintf_s` at `0x14000e243`
- `msvcrt!swprintf_s` at `0x14000e243`
- `DeclaredConfiguration!DMOrchestratorUpdateDocStatus` at `0x14000e3fb`
- `DeclaredConfiguration!DMOrchestratorUpdateDocStatus` at `0x14000e3fb`
- `omadmapi!__imp_OmaDmInitiateSessionEx` at `0x14000e42c`
- `omadmapi!__imp_OmaDmInitiateSessionEx` at `0x14000e42c`

## string_xrefs

- `0x14000e3f1`: `DCWin32AppInstallUniqueId`
- `0x14000e1de`: `Reversed-Domain-Name:com.microsoft.mdm.win32csp_install`
- `0x14000e2eb`: `Attempting to initiate OMADM session: ServerAccount ID = %1, locURI=%2`

## pseudocode

```c
__int64 __fastcall JobExecution::OmaDmMsiInitiateSession(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        _QWORD *a5,
        _QWORD *a6)
{
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _WORD *v12; // rcx
  __int64 v13; // r8
  unsigned __int64 v14; // rsi
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rbx
  _QWORD *v18; // rax
  _QWORD *v19; // r9
  const wchar_t *v20; // rdx
  int v21; // ebx
  __int64 v22; // rax
  unsigned __int64 v23; // rcx
  __int16 v25; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD *v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h]
  _QWORD *v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+70h] [rbp-90h]
  int v32; // [rsp+74h] [rbp-8Ch]
  _QWORD *v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  _QWORD v36[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v37; // [rsp+A8h] [rbp-58h]
  _QWORD v38[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v39[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v40[4]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v41[7]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t Buffer[64]; // [rsp+180h] [rbp+80h] BYREF

  v41[0] = *(_OWORD *)L"Reversed-Domain-Name:com.microsoft.mdm.win32csp_install";
  v41[1] = *(_OWORD *)L"-Domain-Name:com.microsoft.mdm.win32csp_install";
  v41[2] = *(_OWORD *)L"Name:com.microsoft.mdm.win32csp_install";
  v41[3] = *(_OWORD *)L".microsoft.mdm.win32csp_install";
  v41[4] = *(_OWORD *)L"ft.mdm.win32csp_install";
  v41[5] = *(_OWORD *)L"in32csp_install";
  v41[6] = *(_OWORD *)L"install";
  swprintf_s(Buffer, 0x40u, L"%d", a3);
  std::wstring::wstring((__int64)v39, (__int64)Buffer);
  std::wstring::wstring((__int64)v38, (__int64)&word_14001E5B4);
  hMem = 0;
  v27[0] = 64;
  v27[1] = 1224;
  v28 = v41;
  v29 = a2;
  v10 = v39;
  if ( v39[3] >= 8u )
    v10 = (_QWORD *)v39[0];
  v30 = v10;
  v31 = 0;
  v32 = 5;
  v11 = v38;
  if ( v38[3] >= 8u )
    v11 = (_QWORD *)v38[0];
  v33 = v11;
  v34 = 200;
  v35 = 0;
  if ( a6[3] < 8u )
    v12 = a6;
  else
    v12 = (_WORD *)*a6;
  a6[2] = 0;
  *v12 = 0;
  LogInfo(L"Attempting to initiate OMADM session: ServerAccount ID = %1, locURI=%2", a1, a2);
  v37 = 7;
  v36[2] = 0;
  LOWORD(v36[0]) = 0;
  v25 = 123;
  v14 = std::wstring::find(a5, &v25, v13, 1);
  v25 = 125;
  v16 = std::wstring::find(a5, &v25, v15, 1);
  v17 = v16;
  if ( v14 == -1 || v16 == -1 || v16 <= v14 )
  {
    std::wstring::append(v36, a5, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    std::wstring::append((__int64)v36, (__int64)L"%7b");
    v18 = (_QWORD *)std::wstring::substr(a5, v40, v14 + 1, v17 - v14 - 1);
    std::wstring::append(v36, v18, 0, 0xFFFFFFFFFFFFFFFFuLL);
    std::wstring::_Tidy(v40, 1, 0);
    std::wstring::append((__int64)v36, (__int64)L"%7d");
  }
  v19 = v36;
  if ( v37 >= 8 )
    v19 = (_QWORD *)v36[0];
  v20 = L"User";
  if ( !a4 )
    v20 = L"Device";
  DMOrchestratorUpdateDocStatus(a1, v20, L"DCWin32AppInstallUniqueId", v19, a3 == 0);
  v21 = OmaDmInitiateSessionEx(a1, 1, 2, v27, 1, &hMem, 13);
  if ( v21 >= 0 && hMem )
  {
    v22 = std::char_traits<unsigned short>::length(hMem);
    std::wstring::assign(a6, v23, v22);
  }
  std::wstring::_Tidy(v36, 1, 0);
  if ( v21 < 0 )
    LogWarn(L"OmaDmInitializeSessionEx failed with Error 0x%1!x!", (unsigned int)v21);
  if ( hMem )
    LocalFree(hMem);
  std::wstring::_Tidy(v38, 1, 0);
  std::wstring::_Tidy(v39, 1, 0);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x14000e194  mov     [rsp-8+arg_18], rbx
0x14000e199  push    rbp
0x14000e19a  push    rsi
0x14000e19b  push    rdi
0x14000e19c  push    r12
0x14000e19e  push    r13
0x14000e1a0  push    r14
0x14000e1a2  push    r15
0x14000e1a4  lea     rbp, [rsp-110h]
0x14000e1ac  sub     rsp, 210h
0x14000e1b3  mov     rax, cs:__security_cookie
0x14000e1ba  xor     rax, rsp
0x14000e1bd  mov     [rbp+140h+var_40], rax
0x14000e1c4  mov     r13b, r9b
0x14000e1c7  mov     r12d, r8d
0x14000e1ca  mov     rbx, rdx
0x14000e1cd  mov     r15, rcx
0x14000e1d0  mov     rdi, [rbp+140h+arg_28]
0x14000e1d7  mov     r14, [rbp+140h+arg_20]
0x14000e1de  movaps  xmm0, xmmword ptr cs:aReversedDomain; "Reversed-Domain-Name:com.microsoft.mdm."...
0x14000e1e5  movaps  [rbp+140h+var_130], xmm0
0x14000e1e9  movaps  xmm1, xmmword ptr cs:aReversedDomain+10h; "-Domain-Name:com.microsoft.mdm.win32csp"...
0x14000e1f0  movaps  [rbp+140h+var_120], xmm1
0x14000e1f4  movaps  xmm0, xmmword ptr cs:aReversedDomain+20h; "Name:com.microsoft.mdm.win32csp_install"
0x14000e1fb  movaps  [rbp+140h+var_110], xmm0
0x14000e1ff  movaps  xmm1, xmmword ptr cs:aReversedDomain+30h; ".microsoft.mdm.win32csp_install"
0x14000e206  movaps  [rbp+140h+var_100], xmm1
0x14000e20a  movaps  xmm0, xmmword ptr cs:aReversedDomain+40h; "ft.mdm.win32csp_install"
0x14000e211  movaps  [rbp+140h+var_F0], xmm0
0x14000e215  movaps  xmm1, xmmword ptr cs:aReversedDomain+50h; "in32csp_install"
0x14000e21c  movaps  [rbp+140h+var_E0], xmm1
0x14000e220  movaps  xmm0, xmmword ptr cs:aReversedDomain+60h; "install"
0x14000e227  movaps  [rbp+140h+var_D0], xmm0
0x14000e22b  mov     r9d, r8d
0x14000e22e  lea     r8, aD; "%d"
0x14000e235  mov     esi, 40h ; '@'
0x14000e23a  mov     edx, esi; BufferCount
0x14000e23c  lea     rcx, [rbp+140h+Buffer]; Buffer
0x14000e243  call    cs:__imp_swprintf_s
0x14000e249  lea     rdx, [rbp+140h+Buffer]
0x14000e250  lea     rcx, [rbp+140h+var_170]
0x14000e254  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000e259  nop
0x14000e25a  lea     rdx, word_14001E5B4
0x14000e261  lea     rcx, [rbp+140h+var_190]
0x14000e265  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000e26a  nop
0x14000e26b  mov     [rsp+240h+hMem], 0
0x14000e274  mov     [rsp+240h+var_1F0], esi
0x14000e278  mov     [rsp+240h+var_1EC], 4C8h
0x14000e280  lea     rax, [rbp+140h+var_130]
0x14000e284  mov     [rsp+240h+var_1E8], rax
0x14000e289  mov     [rsp+240h+var_1E0], rbx
0x14000e28e  lea     rax, [rbp+140h+var_170]
0x14000e292  cmp     [rbp+140h+var_158], 8
0x14000e297  cmovnb  rax, [rbp+140h+var_170]
0x14000e29c  mov     [rsp+240h+var_1D8], rax
0x14000e2a1  xor     esi, esi
0x14000e2a3  mov     [rsp+240h+var_1D0], esi
0x14000e2a7  mov     [rsp+240h+var_1CC], 5
0x14000e2af  lea     rax, [rbp+140h+var_190]
0x14000e2b3  cmp     [rbp+140h+var_178], 8
0x14000e2b8  cmovnb  rax, [rbp+140h+var_190]
0x14000e2bd  mov     [rsp+240h+var_1C8], rax
0x14000e2c2  mov     [rbp+140h+var_1C0], 0C8h
0x14000e2c9  xor     eax, eax
0x14000e2cb  mov     [rbp+140h+var_1B8], rax
0x14000e2cf  cmp     qword ptr [rdi+18h], 8
0x14000e2d4  jb      short loc_14000E2DB
0x14000e2d6  mov     rcx, [rdi]
0x14000e2d9  jmp     short loc_14000E2DE
0x14000e2db  mov     rcx, rdi
0x14000e2de  mov     [rdi+10h], rsi
0x14000e2e2  mov     [rcx], si
0x14000e2e5  mov     r8, rbx
0x14000e2e8  mov     rdx, r15
0x14000e2eb  lea     rcx, aAttemptingToIn; "Attempting to initiate OMADM session: S"...
0x14000e2f2  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000e2f7  mov     [rbp+140h+var_198], 7
0x14000e2ff  mov     [rbp+140h+var_1A0], rsi
0x14000e303  mov     word ptr [rbp+140h+var_1B0], si
0x14000e307  mov     eax, 7Bh ; '{'
0x14000e30c  mov     [rsp+240h+var_200], ax
0x14000e311  lea     ebx, [rax-7Ah]
0x14000e314  mov     r9d, ebx
0x14000e317  lea     rdx, [rsp+240h+var_200]
0x14000e31c  mov     rcx, r14
0x14000e31f  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x14000e324  mov     rsi, rax
0x14000e327  lea     eax, [rbx+7Ch]
0x14000e32a  mov     [rsp+240h+var_200], ax
0x14000e32f  mov     r9d, ebx
0x14000e332  lea     rdx, [rsp+240h+var_200]
0x14000e337  mov     rcx, r14
0x14000e33a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x14000e33f  mov     rbx, rax
0x14000e342  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000e346  jz      short loc_14000E3AF
0x14000e348  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000e34c  jz      short loc_14000E3AF
0x14000e34e  cmp     rax, rsi
0x14000e351  jbe     short loc_14000E3AF
0x14000e353  lea     rdx, a7b; "%7b"
0x14000e35a  lea     rcx, [rbp+140h+var_1B0]
0x14000e35e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000e363  sub     rbx, rsi
0x14000e366  lea     r9, [rbx-1]
0x14000e36a  lea     r8, [rsi+1]
0x14000e36e  lea     rdx, [rbp+140h+var_150]
0x14000e372  mov     rcx, r14
0x14000e375  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x14000e37a  nop
0x14000e37b  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000e37f  xor     r8d, r8d
0x14000e382  mov     rdx, rax
0x14000e385  lea     rcx, [rbp+140h+var_1B0]
0x14000e389  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000e38e  nop
0x14000e38f  xor     r8d, r8d
0x14000e392  mov     dl, 1
0x14000e394  lea     rcx, [rbp+140h+var_150]
0x14000e398  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000e39d  lea     rdx, a7d; "%7d"
0x14000e3a4  lea     rcx, [rbp+140h+var_1B0]
0x14000e3a8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14000e3ad  jmp     short loc_14000E3C2
0x14000e3af  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000e3b3  xor     r8d, r8d
0x14000e3b6  mov     rdx, r14
0x14000e3b9  lea     rcx, [rbp+140h+var_1B0]
0x14000e3bd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000e3c2  xor     eax, eax
0x14000e3c4  test    r12d, r12d
0x14000e3c7  setz    al
0x14000e3ca  lea     r9, [rbp+140h+var_1B0]
0x14000e3ce  cmp     [rbp+140h+var_198], 8
0x14000e3d3  cmovnb  r9, [rbp+140h+var_1B0]
0x14000e3d8  lea     rcx, aDevice; "Device"
0x14000e3df  lea     rdx, aUser; "User"
0x14000e3e6  test    r13b, r13b
0x14000e3e9  cmovz   rdx, rcx
0x14000e3ed  mov     [rsp+240h+var_220], eax
0x14000e3f1  lea     r8, aDcwin32appinst; "DCWin32AppInstallUniqueId"
0x14000e3f8  mov     rcx, r15
0x14000e3fb  call    cs:__imp_DMOrchestratorUpdateDocStatus
0x14000e401  mov     [rsp+240h+var_210], 0Dh
0x14000e409  lea     rax, [rsp+240h+hMem]
0x14000e40e  mov     [rsp+240h+var_218], rax
0x14000e413  mov     [rsp+240h+var_220], 1
0x14000e41b  lea     r9, [rsp+240h+var_1F0]
0x14000e420  mov     edx, 1
0x14000e425  lea     r8d, [rdx+1]
0x14000e429  mov     rcx, r15
0x14000e42c  call    cs:__imp_OmaDmInitiateSessionEx
0x14000e432  mov     ebx, eax
0x14000e434  test    eax, eax
0x14000e436  js      short loc_14000E456
0x14000e438  mov     rcx, [rsp+240h+hMem]
0x14000e43d  test    rcx, rcx
0x14000e440  jz      short loc_14000E456
0x14000e442  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14000e447  mov     r8, rax
0x14000e44a  mov     rdx, rcx
0x14000e44d  mov     rcx, rdi
0x14000e450  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000e455  nop
0x14000e456  xor     r8d, r8d
0x14000e459  mov     dl, 1
0x14000e45b  lea     rcx, [rbp+140h+var_1B0]
0x14000e45f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000e464  test    ebx, ebx
0x14000e466  jns     short loc_14000E476
0x14000e468  mov     edx, ebx
0x14000e46a  lea     rcx, aOmadminitializ; "OmaDmInitializeSessionEx failed with Er"...
0x14000e471  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14000e476  mov     rcx, [rsp+240h+hMem]; hMem
0x14000e47b  test    rcx, rcx
0x14000e47e  jz      short loc_14000E487
0x14000e480  call    cs:__imp_LocalFree
0x14000e486  nop
0x14000e487  xor     r8d, r8d
0x14000e48a  mov     dl, 1
0x14000e48c  lea     rcx, [rbp+140h+var_190]
0x14000e490  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000e495  nop
0x14000e496  xor     r8d, r8d
0x14000e499  mov     dl, 1
0x14000e49b  lea     rcx, [rbp+140h+var_170]
0x14000e49f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000e4a4  mov     eax, ebx
0x14000e4a6  mov     rcx, [rbp+140h+var_40]
0x14000e4ad  xor     rcx, rsp; StackCookie
0x14000e4b0  call    __security_check_cookie
0x14000e4b5  mov     rbx, [rsp+240h+arg_18]
0x14000e4bd  add     rsp, 210h
0x14000e4c4  pop     r15
0x14000e4c6  pop     r14
0x14000e4c8  pop     r13
0x14000e4ca  pop     r12
0x14000e4cc  pop     rdi
0x14000e4cd  pop     rsi
0x14000e4ce  pop     rbp
0x14000e4cf  retn
```
