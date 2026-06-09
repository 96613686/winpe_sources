# CInpagePlugIn::IsWdiHostProcess(void)

- ea: `0x14004812c`
- end: `0x140048495`
- name: `?IsWdiHostProcess@CInpagePlugIn@@AEAAHXZ`
- size: `873`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x140047dbc`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x14000c8a0`
- `0x14000cb24`
- `0x14001183c`
- `0x140011ab8`
- `0x140013ff0`
- `0x140014474`
- `0x14004812c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004822b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400482f3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004822b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400482f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004829e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400483dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004829e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400483dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004842e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004842e`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x1400483a2`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x1400483a2`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x140048273`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x140048273`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14004824c`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14004824c`

## string_xrefs

- `0x1400482d6`: `wdi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInpagePlugIn::IsWdiHostProcess(CInpagePlugIn *this)
{
  char *Toolhelp32Snapshot; // rbx
  unsigned int v3; // esi
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  CUserModeHangReport *v7; // rcx
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  void *v12[2]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v13[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  char *v15; // [rsp+48h] [rbp-B8h]
  _WORD v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[1088]; // [rsp+70h] [rbp-90h] BYREF
  MODULEENTRY32W me; // [rsp+4B0h] [rbp+3B0h] BYREF

  v14 = v16;
  v15 = (char *)v16;
  v16[0] = 0;
  v12[0] = v13;
  v12[1] = v13;
  v13[0] = 0;
  Toolhelp32Snapshot = 0;
  v17 = 0;
  memset_0(&me, 0, sizeof(me));
  v3 = 0;
  UtilGetWindowsDirectory(&v14);
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
                          v12,
                          ((v15 - (_BYTE *)v14) >> 1) + 12)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          v12,
                          v14,
                          (v15 - (_BYTE *)v14) >> 1)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          v12,
                          L"svchost.exe",
                          11) )
  {
    if ( !(unsigned int)_o__wcsicmp((char *)this + 1088, v12[0]) && UtilIsSystem() )
    {
      Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(8u, *((_DWORD *)this + 10));
      if ( Toolhelp32Snapshot == (char *)-1LL || Toolhelp32Snapshot + 1 == (char *)1 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          v5 = 27;
          goto LABEL_11;
        }
      }
      else
      {
        me.dwSize = 1080;
        if ( Module32FirstW(Toolhelp32Snapshot, &me) )
        {
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
            v12,
            v14,
            (v15 - (_BYTE *)v14) >> 1);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v12, L"wdi.dll", 7);
          while ( (unsigned int)_o__wcsicmp(me.szExePath, v12[0]) )
          {
            memset_0(v18, 0, 0x438u);
            p_me = &me;
            v9 = v18;
            v10 = 8;
            do
            {
              *(_OWORD *)&p_me->dwSize = *v9;
              *(_OWORD *)&p_me->ProccntUsage = v9[1];
              *(_OWORD *)&p_me->modBaseSize = v9[2];
              *(_OWORD *)p_me->szModule = v9[3];
              *(_OWORD *)&p_me->szModule[8] = v9[4];
              *(_OWORD *)&p_me->szModule[16] = v9[5];
              *(_OWORD *)&p_me->szModule[24] = v9[6];
              *(_OWORD *)&p_me->szModule[32] = v9[7];
              p_me = (MODULEENTRY32W *)((char *)p_me + 128);
              v9 += 8;
              --v10;
            }
            while ( v10 );
            *(_OWORD *)&p_me->dwSize = *v9;
            *(_OWORD *)&p_me->ProccntUsage = v9[1];
            *(_OWORD *)&p_me->modBaseSize = v9[2];
            *(_QWORD *)p_me->szModule = *((_QWORD *)v9 + 6);
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
          v5 = 28;
LABEL_11:
          v6 = LastError;
          v7 = WPP_GLOBAL_Control;
LABEL_25:
          WPP_SF_d(*((_QWORD *)v7 + 2), v5, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids, v6);
        }
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 26;
      v6 = 2147942414LL;
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( (unsigned __int64)(Toolhelp32Snapshot + 1) > 1 )
    CloseHandle(Toolhelp32Snapshot);
  if ( v12[0] != v13 )
    operator delete(v12[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v14 != v16 )
    operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
  return v3;
}

```

## disassembly

```asm
0x14004812c  mov     [rsp-8+arg_8], rbx
0x140048131  mov     [rsp-8+arg_10], rsi
0x140048136  push    rbp
0x140048137  push    rdi
0x140048138  push    r15
0x14004813a  lea     rbp, [rsp-800h]
0x140048142  sub     rsp, 900h
0x140048149  mov     rax, cs:__security_cookie
0x140048150  xor     rax, rsp
0x140048153  mov     [rbp+810h+var_20], rax
0x14004815a  mov     rdi, rcx
0x14004815d  lea     rax, [rsp+910h+var_8C0]
0x140048162  mov     [rsp+910h+var_8D0], rax
0x140048167  lea     rax, [rsp+910h+var_8C0]
0x14004816c  mov     [rsp+910h+var_8C8], rax
0x140048171  xor     eax, eax
0x140048173  mov     [rsp+910h+var_8C0], ax
0x140048178  lea     rax, [rsp+910h+var_8E0]
0x14004817d  mov     [rsp+910h+var_8F0], rax
0x140048182  lea     rax, [rsp+910h+var_8E0]
0x140048187  mov     [rsp+910h+var_8E8], rax
0x14004818c  xor     eax, eax
0x14004818e  mov     [rsp+910h+var_8E0], ax
0x140048193  xor     ebx, ebx
0x140048195  mov     [rsp+910h+var_8B0], rbx
0x14004819a  mov     r15d, 438h
0x1400481a0  mov     r8d, r15d; Size
0x1400481a3  xor     edx, edx; Val
0x1400481a5  lea     rcx, [rbp+810h+me]; void *
0x1400481ac  call    memset_0
0x1400481b1  xor     esi, esi
0x1400481b3  lea     rcx, [rsp+910h+var_8D0]
0x1400481b8  call    ?UtilGetWindowsDirectory@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetWindowsDirectory(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400481bd  mov     rdx, [rsp+910h+var_8C8]
0x1400481c2  sub     rdx, [rsp+910h+var_8D0]
0x1400481c7  sar     rdx, 1
0x1400481ca  add     rdx, 0Ch
0x1400481ce  lea     rcx, [rsp+910h+var_8F0]
0x1400481d3  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x1400481d8  test    al, al
0x1400481da  jz      loc_1400483EC
0x1400481e0  mov     r8, [rsp+910h+var_8C8]
0x1400481e5  mov     rdx, [rsp+910h+var_8D0]
0x1400481ea  sub     r8, rdx
0x1400481ed  sar     r8, 1
0x1400481f0  lea     rcx, [rsp+910h+var_8F0]
0x1400481f5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400481fa  test    al, al
0x1400481fc  jz      loc_1400483EC
0x140048202  lea     r8d, [rbx+0Bh]
0x140048206  lea     rdx, aSvchostExe; "svchost.exe"
0x14004820d  lea     rcx, [rsp+910h+var_8F0]
0x140048212  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140048217  test    al, al
0x140048219  jz      loc_1400483EC
0x14004821f  lea     rcx, [rdi+440h]
0x140048226  mov     rdx, [rsp+910h+var_8F0]
0x14004822b  call    cs:__imp__o__wcsicmp
0x140048231  test    eax, eax
0x140048233  jnz     loc_140048421
0x140048239  call    ?UtilIsSystem@@YA_NXZ; UtilIsSystem(void)
0x14004823e  test    al, al
0x140048240  jz      loc_140048421
0x140048246  mov     edx, [rdi+28h]; th32ProcessID
0x140048249  lea     ecx, [rbx+8]; dwFlags
0x14004824c  call    cs:__imp_CreateToolhelp32Snapshot
0x140048252  mov     rbx, rax
0x140048255  inc     rax
0x140048258  cmp     rax, 1
0x14004825c  jbe     loc_1400483C3
0x140048262  mov     [rbp+810h+me.dwSize], r15d
0x140048269  lea     rdx, [rbp+810h+me]; lpme
0x140048270  mov     rcx, rbx; hSnapshot
0x140048273  call    cs:__imp_Module32FirstW
0x140048279  test    eax, eax
0x14004827b  jnz     short loc_1400482B6
0x14004827d  lea     rax, WPP_GLOBAL_Control
0x140048284  mov     rcx, cs:WPP_GLOBAL_Control
0x14004828b  cmp     rcx, rax
0x14004828e  jz      loc_140048421
0x140048294  test    byte ptr [rcx+1Ch], 1
0x140048298  jz      loc_140048421
0x14004829e  call    cs:__imp_GetLastError
0x1400482a4  lea     edx, [rsi+1Ch]
0x1400482a7  mov     r9d, eax
0x1400482aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400482b1  jmp     loc_140048410
0x1400482b6  mov     r8, [rsp+910h+var_8C8]
0x1400482bb  mov     rdx, [rsp+910h+var_8D0]
0x1400482c0  sub     r8, rdx
0x1400482c3  sar     r8, 1
0x1400482c6  lea     rcx, [rsp+910h+var_8F0]
0x1400482cb  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400482d0  mov     r8d, 7
0x1400482d6  lea     rdx, aWdiDll; "wdi.dll"
0x1400482dd  lea     rcx, [rsp+910h+var_8F0]
0x1400482e2  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400482e7  mov     rdx, [rsp+910h+var_8F0]
0x1400482ec  lea     rcx, [rbp+810h+me.szExePath]
0x1400482f3  call    cs:__imp__o__wcsicmp
0x1400482f9  test    eax, eax
0x1400482fb  jz      loc_1400483B2
0x140048301  mov     r8, r15; Size
0x140048304  xor     edx, edx; Val
0x140048306  lea     rcx, [rsp+910h+var_8A0]; void *
0x14004830b  call    memset_0
0x140048310  lea     rcx, [rbp+810h+me]
0x140048317  lea     rax, [rsp+910h+var_8A0]
0x14004831c  mov     edx, 8
0x140048321  movups  xmm0, xmmword ptr [rax]
0x140048324  movups  xmmword ptr [rcx], xmm0
0x140048327  movups  xmm1, xmmword ptr [rax+10h]
0x14004832b  movups  xmmword ptr [rcx+10h], xmm1
0x14004832f  movups  xmm0, xmmword ptr [rax+20h]
0x140048333  movups  xmmword ptr [rcx+20h], xmm0
0x140048337  movups  xmm1, xmmword ptr [rax+30h]
0x14004833b  movups  xmmword ptr [rcx+30h], xmm1
0x14004833f  movups  xmm0, xmmword ptr [rax+40h]
0x140048343  movups  xmmword ptr [rcx+40h], xmm0
0x140048347  movups  xmm1, xmmword ptr [rax+50h]
0x14004834b  movups  xmmword ptr [rcx+50h], xmm1
0x14004834f  movups  xmm0, xmmword ptr [rax+60h]
0x140048353  movups  xmmword ptr [rcx+60h], xmm0
0x140048357  movups  xmm1, xmmword ptr [rax+70h]
0x14004835b  movups  xmmword ptr [rcx+70h], xmm1
0x14004835f  lea     rcx, [rcx+80h]
0x140048366  lea     rax, [rax+80h]
0x14004836d  sub     rdx, 1
0x140048371  jnz     short loc_140048321
0x140048373  movups  xmm0, xmmword ptr [rax]
0x140048376  movups  xmmword ptr [rcx], xmm0
0x140048379  movups  xmm1, xmmword ptr [rax+10h]
0x14004837d  movups  xmmword ptr [rcx+10h], xmm1
0x140048381  movups  xmm0, xmmword ptr [rax+20h]
0x140048385  movups  xmmword ptr [rcx+20h], xmm0
0x140048389  mov     rax, [rax+30h]
0x14004838d  mov     [rcx+30h], rax
0x140048391  mov     [rbp+810h+me.dwSize], r15d
0x140048398  lea     rdx, [rbp+810h+me]; lpme
0x14004839f  mov     rcx, rbx; hSnapshot
0x1400483a2  call    cs:__imp_Module32NextW
0x1400483a8  test    eax, eax
0x1400483aa  jnz     loc_1400482E7
0x1400483b0  jmp     short loc_140048421
0x1400483b2  mov     esi, 1
0x1400483b7  mov     dword ptr [rdi+720h], 5
0x1400483c1  jmp     short loc_140048421
0x1400483c3  lea     rax, WPP_GLOBAL_Control
0x1400483ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400483d1  cmp     rcx, rax
0x1400483d4  jz      short loc_140048421
0x1400483d6  test    byte ptr [rcx+1Ch], 1
0x1400483da  jz      short loc_140048421
0x1400483dc  call    cs:__imp_GetLastError
0x1400483e2  mov     edx, 1Bh
0x1400483e7  jmp     loc_1400482A7
0x1400483ec  lea     rax, WPP_GLOBAL_Control
0x1400483f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400483fa  cmp     rcx, rax
0x1400483fd  jz      short loc_140048421
0x1400483ff  test    byte ptr [rcx+1Ch], 1
0x140048403  jz      short loc_140048421
0x140048405  mov     edx, 1Ah
0x14004840a  mov     r9d, 8007000Eh
0x140048410  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x140048417  mov     rcx, [rcx+10h]
0x14004841b  call    WPP_SF_d
0x140048420  nop
0x140048421  lea     rax, [rbx+1]
0x140048425  cmp     rax, 1
0x140048429  jbe     short loc_140048435
0x14004842b  mov     rcx, rbx; hObject
0x14004842e  call    cs:__imp_CloseHandle
0x140048434  nop
0x140048435  lea     rax, [rsp+910h+var_8E0]
0x14004843a  mov     rcx, [rsp+910h+var_8F0]; void *
0x14004843f  cmp     rcx, rax
0x140048442  jz      short loc_140048451
0x140048444  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004844b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140048450  nop
0x140048451  lea     rax, [rsp+910h+var_8C0]
0x140048456  mov     rcx, [rsp+910h+var_8D0]; void *
0x14004845b  cmp     rcx, rax
0x14004845e  jz      short loc_14004846C
0x140048460  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140048467  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004846c  mov     eax, esi
0x14004846e  mov     rcx, [rbp+810h+var_20]
0x140048475  xor     rcx, rsp; StackCookie
0x140048478  call    __security_check_cookie
0x14004847d  lea     r11, [rsp+910h+var_10]
0x140048485  mov     rbx, [r11+28h]
0x140048489  mov     rsi, [r11+30h]
0x14004848d  mov     rsp, r11
0x140048490  pop     r15
0x140048492  pop     rdi
0x140048493  pop     rbp
0x140048494  retn
```
