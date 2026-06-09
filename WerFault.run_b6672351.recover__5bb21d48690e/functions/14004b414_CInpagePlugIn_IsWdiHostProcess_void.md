# CInpagePlugIn::IsWdiHostProcess(void)

- ea: `0x14004b414`
- end: `0x14004b7ae`
- name: `?IsWdiHostProcess@CInpagePlugIn@@AEAAHXZ`
- size: `922`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x14004b05c`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x14000ca20`
- `0x14000cd94`
- `0x140011fec`
- `0x1400122ac`
- `0x140014a88`
- `0x140014f14`
- `0x14004b414`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004b513`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004b5f3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004b513`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004b5f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b6e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b6e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004b740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004b740`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14004b6a8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x14004b6a8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14004b567`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x14004b567`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14004b53a`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14004b53a`

## string_xrefs

- `0x14004b5d6`: `wdi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInpagePlugIn::IsWdiHostProcess(CInpagePlugIn *this)
{
  char *Toolhelp32Snapshot; // rbx
  unsigned int v3; // esi
  __int64 v4; // r8
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  CUserModeHangReport *v8; // rcx
  __int64 v9; // r8
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v11; // rax
  __int64 v12; // rdx
  void *v14[2]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  char *v17; // [rsp+48h] [rbp-B8h]
  _WORD v18[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h]
  _BYTE v20[1088]; // [rsp+70h] [rbp-90h] BYREF
  MODULEENTRY32W me; // [rsp+4B0h] [rbp+3B0h] BYREF

  v16 = v18;
  v17 = (char *)v18;
  v18[0] = 0;
  v14[0] = v15;
  v14[1] = v15;
  v15[0] = 0;
  Toolhelp32Snapshot = 0;
  v19 = 0;
  memset_0(&me, 0, sizeof(me));
  v3 = 0;
  UtilGetWindowsDirectory(&v16);
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
                          v14,
                          ((v17 - (_BYTE *)v16) >> 1) + 12)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v14, v16)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          v14,
                          L"svchost.exe",
                          11) )
  {
    if ( !(unsigned int)_o__wcsicmp((char *)this + 1088, v14[0], v4) && UtilIsSystem() )
    {
      Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(8u, *((_DWORD *)this + 10));
      if ( Toolhelp32Snapshot == (char *)-1LL || Toolhelp32Snapshot + 1 == (char *)1 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          v6 = 27;
          goto LABEL_11;
        }
      }
      else
      {
        me.dwSize = 1080;
        if ( Module32FirstW(Toolhelp32Snapshot, &me) )
        {
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v14, v16);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v14, L"wdi.dll", 7);
          while ( (unsigned int)_o__wcsicmp(me.szExePath, v14[0], v9) )
          {
            memset_0(v20, 0, 0x438u);
            p_me = &me;
            v11 = v20;
            v12 = 8;
            do
            {
              *(_OWORD *)&p_me->dwSize = *v11;
              *(_OWORD *)&p_me->ProccntUsage = v11[1];
              *(_OWORD *)&p_me->modBaseSize = v11[2];
              *(_OWORD *)p_me->szModule = v11[3];
              *(_OWORD *)&p_me->szModule[8] = v11[4];
              *(_OWORD *)&p_me->szModule[16] = v11[5];
              *(_OWORD *)&p_me->szModule[24] = v11[6];
              *(_OWORD *)&p_me->szModule[32] = v11[7];
              p_me = (MODULEENTRY32W *)((char *)p_me + 128);
              v11 += 8;
              --v12;
            }
            while ( v12 );
            *(_OWORD *)&p_me->dwSize = *v11;
            *(_OWORD *)&p_me->ProccntUsage = v11[1];
            *(_OWORD *)&p_me->modBaseSize = v11[2];
            *(_QWORD *)p_me->szModule = *((_QWORD *)v11 + 6);
            me.dwSize = 1080;
            if ( !Module32NextW(Toolhelp32Snapshot, &me) )
              goto LABEL_26;
          }
          v3 = 1;
          *((_DWORD *)this + 456) = 5;
        }
        else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          v6 = 28;
LABEL_11:
          v7 = LastError;
          v8 = WPP_GLOBAL_Control;
LABEL_25:
          WPP_SF_d(*((_QWORD *)v8 + 2), v6, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids, v7);
        }
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 26;
      v7 = 2147942414LL;
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( (unsigned __int64)(Toolhelp32Snapshot + 1) > 1 )
    CloseHandle(Toolhelp32Snapshot);
  if ( v14[0] != v15 )
    operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v16 != v18 )
    operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  return v3;
}

```

## disassembly

```asm
0x14004b414  mov     [rsp-8+arg_8], rbx
0x14004b419  mov     [rsp-8+arg_10], rsi
0x14004b41e  push    rbp
0x14004b41f  push    rdi
0x14004b420  push    r15
0x14004b422  lea     rbp, [rsp-800h]
0x14004b42a  sub     rsp, 900h
0x14004b431  mov     rax, cs:__security_cookie
0x14004b438  xor     rax, rsp
0x14004b43b  mov     [rbp+810h+var_20], rax
0x14004b442  mov     rdi, rcx
0x14004b445  lea     rax, [rsp+910h+var_8C0]
0x14004b44a  mov     [rsp+910h+var_8D0], rax
0x14004b44f  lea     rax, [rsp+910h+var_8C0]
0x14004b454  mov     [rsp+910h+var_8C8], rax
0x14004b459  xor     eax, eax
0x14004b45b  mov     [rsp+910h+var_8C0], ax
0x14004b460  lea     rax, [rsp+910h+var_8E0]
0x14004b465  mov     [rsp+910h+var_8F0], rax
0x14004b46a  lea     rax, [rsp+910h+var_8E0]
0x14004b46f  mov     [rsp+910h+var_8E8], rax
0x14004b474  xor     eax, eax
0x14004b476  mov     [rsp+910h+var_8E0], ax
0x14004b47b  xor     ebx, ebx
0x14004b47d  mov     [rsp+910h+var_8B0], rbx
0x14004b482  mov     r15d, 438h
0x14004b488  mov     r8d, r15d; Size
0x14004b48b  xor     edx, edx; Val
0x14004b48d  lea     rcx, [rbp+810h+me]; void *
0x14004b494  call    memset_0
0x14004b499  xor     esi, esi
0x14004b49b  lea     rcx, [rsp+910h+var_8D0]
0x14004b4a0  call    ?UtilGetWindowsDirectory@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetWindowsDirectory(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14004b4a5  mov     rdx, [rsp+910h+var_8C8]
0x14004b4aa  sub     rdx, [rsp+910h+var_8D0]
0x14004b4af  sar     rdx, 1
0x14004b4b2  add     rdx, 0Ch
0x14004b4b6  lea     rcx, [rsp+910h+var_8F0]
0x14004b4bb  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x14004b4c0  test    al, al
0x14004b4c2  jz      loc_14004B6FE
0x14004b4c8  mov     r8, [rsp+910h+var_8C8]
0x14004b4cd  mov     rdx, [rsp+910h+var_8D0]
0x14004b4d2  sub     r8, rdx
0x14004b4d5  sar     r8, 1
0x14004b4d8  lea     rcx, [rsp+910h+var_8F0]
0x14004b4dd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004b4e2  test    al, al
0x14004b4e4  jz      loc_14004B6FE
0x14004b4ea  lea     r8d, [rbx+0Bh]
0x14004b4ee  lea     rdx, aSvchostExe; "svchost.exe"
0x14004b4f5  lea     rcx, [rsp+910h+var_8F0]
0x14004b4fa  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14004b4ff  test    al, al
0x14004b501  jz      loc_14004B6FE
0x14004b507  lea     rcx, [rdi+440h]
0x14004b50e  mov     rdx, [rsp+910h+var_8F0]
0x14004b513  call    cs:__imp__o__wcsicmp
0x14004b51a  nop     dword ptr [rax+rax+00h]
0x14004b51f  test    eax, eax
0x14004b521  jnz     loc_14004B733
0x14004b527  call    ?UtilIsSystem@@YA_NXZ; UtilIsSystem(void)
0x14004b52c  test    al, al
0x14004b52e  jz      loc_14004B733
0x14004b534  mov     edx, [rdi+28h]; th32ProcessID
0x14004b537  lea     ecx, [rbx+8]; dwFlags
0x14004b53a  call    cs:__imp_CreateToolhelp32Snapshot
0x14004b541  nop     dword ptr [rax+rax+00h]
0x14004b546  mov     rbx, rax
0x14004b549  inc     rax
0x14004b54c  cmp     rax, 1
0x14004b550  jbe     loc_14004B6CF
0x14004b556  mov     [rbp+810h+me.dwSize], r15d
0x14004b55d  lea     rdx, [rbp+810h+me]; lpme
0x14004b564  mov     rcx, rbx; hSnapshot
0x14004b567  call    cs:__imp_Module32FirstW
0x14004b56e  nop     dword ptr [rax+rax+00h]
0x14004b573  test    eax, eax
0x14004b575  jnz     short loc_14004B5B6
0x14004b577  lea     rax, WPP_GLOBAL_Control
0x14004b57e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b585  cmp     rcx, rax
0x14004b588  jz      loc_14004B733
0x14004b58e  test    byte ptr [rcx+1Ch], 1
0x14004b592  jz      loc_14004B733
0x14004b598  call    cs:__imp_GetLastError
0x14004b59f  nop     dword ptr [rax+rax+00h]
0x14004b5a4  lea     edx, [rsi+1Ch]
0x14004b5a7  mov     r9d, eax
0x14004b5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b5b1  jmp     loc_14004B722
0x14004b5b6  mov     r8, [rsp+910h+var_8C8]
0x14004b5bb  mov     rdx, [rsp+910h+var_8D0]
0x14004b5c0  sub     r8, rdx
0x14004b5c3  sar     r8, 1
0x14004b5c6  lea     rcx, [rsp+910h+var_8F0]
0x14004b5cb  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004b5d0  mov     r8d, 7
0x14004b5d6  lea     rdx, aWdiDll; "wdi.dll"
0x14004b5dd  lea     rcx, [rsp+910h+var_8F0]
0x14004b5e2  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14004b5e7  mov     rdx, [rsp+910h+var_8F0]
0x14004b5ec  lea     rcx, [rbp+810h+me.szExePath]
0x14004b5f3  call    cs:__imp__o__wcsicmp
0x14004b5fa  nop     dword ptr [rax+rax+00h]
0x14004b5ff  test    eax, eax
0x14004b601  jz      loc_14004B6BE
0x14004b607  mov     r8, r15; Size
0x14004b60a  xor     edx, edx; Val
0x14004b60c  lea     rcx, [rsp+910h+var_8A0]; void *
0x14004b611  call    memset_0
0x14004b616  lea     rcx, [rbp+810h+me]
0x14004b61d  lea     rax, [rsp+910h+var_8A0]
0x14004b622  mov     edx, 8
0x14004b627  movups  xmm0, xmmword ptr [rax]
0x14004b62a  movups  xmmword ptr [rcx], xmm0
0x14004b62d  movups  xmm1, xmmword ptr [rax+10h]
0x14004b631  movups  xmmword ptr [rcx+10h], xmm1
0x14004b635  movups  xmm0, xmmword ptr [rax+20h]
0x14004b639  movups  xmmword ptr [rcx+20h], xmm0
0x14004b63d  movups  xmm1, xmmword ptr [rax+30h]
0x14004b641  movups  xmmword ptr [rcx+30h], xmm1
0x14004b645  movups  xmm0, xmmword ptr [rax+40h]
0x14004b649  movups  xmmword ptr [rcx+40h], xmm0
0x14004b64d  movups  xmm1, xmmword ptr [rax+50h]
0x14004b651  movups  xmmword ptr [rcx+50h], xmm1
0x14004b655  movups  xmm0, xmmword ptr [rax+60h]
0x14004b659  movups  xmmword ptr [rcx+60h], xmm0
0x14004b65d  movups  xmm1, xmmword ptr [rax+70h]
0x14004b661  movups  xmmword ptr [rcx+70h], xmm1
0x14004b665  lea     rcx, [rcx+80h]
0x14004b66c  lea     rax, [rax+80h]
0x14004b673  sub     rdx, 1
0x14004b677  jnz     short loc_14004B627
0x14004b679  movups  xmm0, xmmword ptr [rax]
0x14004b67c  movups  xmmword ptr [rcx], xmm0
0x14004b67f  movups  xmm1, xmmword ptr [rax+10h]
0x14004b683  movups  xmmword ptr [rcx+10h], xmm1
0x14004b687  movups  xmm0, xmmword ptr [rax+20h]
0x14004b68b  movups  xmmword ptr [rcx+20h], xmm0
0x14004b68f  mov     rax, [rax+30h]
0x14004b693  mov     [rcx+30h], rax
0x14004b697  mov     [rbp+810h+me.dwSize], r15d
0x14004b69e  lea     rdx, [rbp+810h+me]; lpme
0x14004b6a5  mov     rcx, rbx; hSnapshot
0x14004b6a8  call    cs:__imp_Module32NextW
0x14004b6af  nop     dword ptr [rax+rax+00h]
0x14004b6b4  test    eax, eax
0x14004b6b6  jnz     loc_14004B5E7
0x14004b6bc  jmp     short loc_14004B733
0x14004b6be  mov     esi, 1
0x14004b6c3  mov     dword ptr [rdi+720h], 5
0x14004b6cd  jmp     short loc_14004B733
0x14004b6cf  lea     rax, WPP_GLOBAL_Control
0x14004b6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b6dd  cmp     rcx, rax
0x14004b6e0  jz      short loc_14004B733
0x14004b6e2  test    byte ptr [rcx+1Ch], 1
0x14004b6e6  jz      short loc_14004B733
0x14004b6e8  call    cs:__imp_GetLastError
0x14004b6ef  nop     dword ptr [rax+rax+00h]
0x14004b6f4  mov     edx, 1Bh
0x14004b6f9  jmp     loc_14004B5A7
0x14004b6fe  lea     rax, WPP_GLOBAL_Control
0x14004b705  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b70c  cmp     rcx, rax
0x14004b70f  jz      short loc_14004B733
0x14004b711  test    byte ptr [rcx+1Ch], 1
0x14004b715  jz      short loc_14004B733
0x14004b717  mov     edx, 1Ah
0x14004b71c  mov     r9d, 8007000Eh
0x14004b722  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x14004b729  mov     rcx, [rcx+10h]
0x14004b72d  call    WPP_SF_d
0x14004b732  nop
0x14004b733  lea     rax, [rbx+1]
0x14004b737  cmp     rax, 1
0x14004b73b  jbe     short loc_14004B74D
0x14004b73d  mov     rcx, rbx; hObject
0x14004b740  call    cs:__imp_CloseHandle
0x14004b747  nop     dword ptr [rax+rax+00h]
0x14004b74c  nop
0x14004b74d  lea     rax, [rsp+910h+var_8E0]
0x14004b752  mov     rcx, [rsp+910h+var_8F0]; void *
0x14004b757  cmp     rcx, rax
0x14004b75a  jz      short loc_14004B769
0x14004b75c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004b763  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004b768  nop
0x14004b769  lea     rax, [rsp+910h+var_8C0]
0x14004b76e  mov     rcx, [rsp+910h+var_8D0]; void *
0x14004b773  cmp     rcx, rax
0x14004b776  jz      short loc_14004B784
0x14004b778  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004b77f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004b784  mov     eax, esi
0x14004b786  mov     rcx, [rbp+810h+var_20]
0x14004b78d  xor     rcx, rsp; StackCookie
0x14004b790  call    __security_check_cookie
0x14004b795  lea     r11, [rsp+910h+var_10]
0x14004b79d  mov     rbx, [r11+28h]
0x14004b7a1  mov     rsi, [r11+30h]
0x14004b7a5  mov     rsp, r11
0x14004b7a8  pop     r15
0x14004b7aa  pop     rdi
0x14004b7ab  pop     rbp
0x14004b7ac  retn
```
