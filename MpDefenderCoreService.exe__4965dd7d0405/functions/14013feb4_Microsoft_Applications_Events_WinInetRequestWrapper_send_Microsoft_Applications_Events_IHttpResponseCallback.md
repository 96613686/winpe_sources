# Microsoft::Applications::Events::WinInetRequestWrapper::send(Microsoft::Applications::Events::IHttpResponseCallback *)

- ea: `0x14013feb4`
- end: `0x1401405a0`
- name: `?send@WinInetRequestWrapper@Events@Applications@Microsoft@@QEAAXPEAVIHttpResponseCallback@234@@Z`
- size: `1772`
- prototype: `void __fastcall(Microsoft::Applications::Events::WinInetRequestWrapper *__hidden this, struct Microsoft::Applications::Events::IHttpResponseCallback *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14013f020`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14001d848`
- `0x14003a0f4`
- `0x14003a5c0`
- `0x14007dbcc`
- `0x14007e14c`
- `0x14007e938`
- `0x14007f974`
- `0x14008040c`
- `0x140084a18`
- `0x1400858b4`
- `0x1400931ac`
- `0x1400933d8`
- `0x14009b9d0`
- `0x1400ff188`
- `0x14013f9f4`
- `0x14013feb4`
- `0x1401405a0`
- `0x140166250`
- `0x140166990`

## import_xrefs

- `WININET!InternetConnectA` at `0x140140182`
- `WININET!InternetConnectA` at `0x140140182`
- `WININET!InternetSetStatusCallbackW` at `0x140140285`
- `WININET!InternetSetStatusCallbackW` at `0x140140285`
- `WININET!InternetCrackUrlA` at `0x140140100`
- `WININET!InternetCrackUrlA` at `0x140140100`
- `WININET!HttpOpenRequestA` at `0x140140212`
- `WININET!HttpOpenRequestA` at `0x140140212`
- `WININET!HttpAddRequestHeadersA` at `0x14014039b`
- `WININET!HttpAddRequestHeadersA` at `0x14014039b`
- `WININET!HttpSendRequestW` at `0x14014047a`
- `WININET!HttpSendRequestW` at `0x14014047a`
- `KERNEL32!GetLastError` at `0x14014010a`
- `KERNEL32!GetLastError` at `0x140140194`
- `KERNEL32!GetLastError` at `0x140140221`
- `KERNEL32!GetLastError` at `0x1401403b5`
- `KERNEL32!GetLastError` at `0x140140482`
- `KERNEL32!GetLastError` at `0x14014049c`
- `KERNEL32!GetLastError` at `0x14014010a`
- `KERNEL32!GetLastError` at `0x140140194`
- `KERNEL32!GetLastError` at `0x140140221`
- `KERNEL32!GetLastError` at `0x1401403b5`
- `KERNEL32!GetLastError` at `0x140140482`
- `KERNEL32!GetLastError` at `0x14014049c`

## string_xrefs

- `0x140140230`: `HttpOpenRequest() failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::Applications::Events::WinInetRequestWrapper::send(
        Microsoft::Applications::Events::WinInetRequestWrapper *this,
        struct Microsoft::Applications::Events::IHttpResponseCallback *a2)
{
  __int64 v4; // rdi
  const CHAR *v5; // r12
  _OWORD *v6; // rsi
  __int64 v7; // r13
  __int64 v8; // rbx
  __int64 inserted; // r15
  char v10; // cl
  __int64 *v11; // rax
  const CHAR *v12; // rax
  CHAR *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  const CHAR *v16; // rcx
  DWORD LastError; // eax
  const char *v18; // rcx
  void *v19; // rcx
  DWORD v20; // eax
  DWORD dwFlags; // r8d
  const CHAR *v22; // rdx
  void *v23; // rax
  DWORD v24; // eax
  _QWORD *v25; // rsi
  _QWORD *v26; // rbx
  _QWORD *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rdx
  __int64 v31; // rax
  __int64 **v32; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  _DWORD *v35; // rax
  DWORD v36; // ebx
  const CHAR *v37; // rdx
  BOOL v38; // ebx
  DWORD v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  BOOL v42; // ebx
  DWORD v43; // eax
  DWORD v44; // eax
  __int64 v45; // rcx
  DWORD_PTR dwContext_8[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPCSTR lpszHeaders_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v48; // [rsp+80h] [rbp-88h]
  __int64 v49; // [rsp+88h] [rbp-80h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v51[30]; // [rsp+108h] [rbp+0h] BYREF
  LPCSTR lpszAcceptTypes[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  CHAR szServerName[256]; // [rsp+208h] [rbp+100h] BYREF
  CHAR szObjectName[1024]; // [rsp+308h] [rbp+200h] BYREF

  v4 = *(_QWORD *)this + 16LL;
  v49 = v4;
  if ( Mtx_lock((_Mtx_t)v4) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v4 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  *((_QWORD *)this + 5) = a2;
  v5 = (const CHAR *)(*(_QWORD *)this + 96LL);
  v6 = (_OWORD *)((char *)this + 8);
  v7 = *(_QWORD *)v5;
  v8 = *(_QWORD *)(*(_QWORD *)v5 + 8LL);
  *(_OWORD *)dwContext_8 = (unsigned __int64)v8;
  inserted = v7;
  while ( !*(_BYTE *)(v8 + 25) )
  {
    dwContext_8[0] = v8;
    v10 = std::operator<<char>((_QWORD *)(v8 + 32), (_QWORD *)this + 1);
    if ( v10 )
    {
      LODWORD(dwContext_8[1]) = 0;
    }
    else
    {
      LODWORD(dwContext_8[1]) = 1;
      inserted = v8;
    }
    v11 = (__int64 *)(v8 + 16);
    if ( !v10 )
      v11 = (__int64 *)v8;
    v8 = *v11;
  }
  if ( *(_BYTE *)(inserted + 25) || (unsigned __int8)std::operator<<char>((_QWORD *)this + 1, (_QWORD *)(inserted + 32)) )
  {
    if ( *((_QWORD *)v5 + 1) == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    lpszHeaders_8[0] = v5;
    v12 = (const CHAR *)operator new(0x48u);
    v13 = (CHAR *)v12;
    lpszHeaders_8[1] = v12;
    *((_OWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 7) = 0;
    if ( *((_QWORD *)this + 4) > 0xFu )
      v6 = *(_OWORD **)v6;
    std::string::_Construct<2,char const *>((__int64)(v12 + 32), v6, *((_QWORD *)this + 3));
    *((_QWORD *)v13 + 8) = 0;
    *(_QWORD *)v13 = v7;
    *((_QWORD *)v13 + 1) = v7;
    *((_QWORD *)v13 + 2) = v7;
    *((_WORD *)v13 + 12) = 0;
    *(_OWORD *)lpszHeaders_8 = *(_OWORD *)dwContext_8;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum Microsoft::Applications::Events::EventLatency const,Microsoft::Applications::Events::RecordStats>>>::_Insert_node(
                 v5,
                 lpszHeaders_8,
                 v13);
  }
  *(_QWORD *)(inserted + 64) = this;
  v14 = *((_QWORD *)this + 5);
  if ( *((_BYTE *)this + 1130) )
  {
LABEL_18:
    if ( v14 )
      goto LABEL_41;
    goto LABEL_42;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 16LL))(v14, 2, *((_QWORD *)this + 7), 0);
  memset(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  memset(szServerName, 0, sizeof(szServerName));
  UrlComponents.lpszHostName = szServerName;
  UrlComponents.dwHostNameLength = 256;
  memset(szObjectName, 0, sizeof(szObjectName));
  UrlComponents.lpszUrlPath = szObjectName;
  UrlComponents.dwUrlPathLength = 1024;
  v15 = *((_QWORD *)this + 8);
  v16 = (const CHAR *)(v15 + 72);
  if ( *(_QWORD *)(v15 + 96) > 0xFu )
    v16 = *(const CHAR **)v16;
  if ( !InternetCrackUrlA(v16, *(_DWORD *)(v15 + 88), 0, &UrlComponents) )
  {
    LastError = GetLastError();
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
    {
      v18 = (const char *)(*((_QWORD *)this + 8) + 72LL);
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 96LL) > 0xFu )
        v18 = *(const char **)v18;
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        2,
        "MATSDK",
        "InternetCrackUrl() failed: dwError=%d url=%s",
        LastError,
        v18);
    }
    v14 = *((_QWORD *)this + 5);
    goto LABEL_18;
  }
  v19 = InternetConnectA(
          *(HINTERNET *)(*(_QWORD *)this + 8LL),
          szServerName,
          UrlComponents.nPort,
          0,
          0,
          3u,
          0,
          (DWORD_PTR)this);
  *((_QWORD *)this + 6) = v19;
  if ( !v19 )
  {
    v20 = GetLastError();
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        2,
        "MATSDK",
        "InternetConnect() failed: %d",
        v20);
    goto LABEL_40;
  }
  lpszAcceptTypes[0] = "*/*";
  lpszAcceptTypes[1] = 0;
  dwFlags = -2075393280;
  if ( UrlComponents.nScheme == INTERNET_SCHEME_HTTPS )
    dwFlags = -2067004672;
  v22 = (const CHAR *)(*((_QWORD *)this + 8) + 40LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 8) + 64LL) > 0xFu )
    v22 = *(const CHAR **)v22;
  v23 = HttpOpenRequestA(v19, v22, szObjectName, 0, 0, lpszAcceptTypes, dwFlags, (DWORD_PTR)this);
  *((_QWORD *)this + 7) = v23;
  if ( !v23 )
  {
    v24 = GetLastError();
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        2,
        "MATSDK",
        "HttpOpenRequest() failed: %d",
        v24);
LABEL_40:
    v14 = *((_QWORD *)this + 5);
    if ( v14 )
LABEL_41:
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 16LL))(
        v14,
        3,
        *((_QWORD *)this + 7),
        0);
LABEL_42:
    Microsoft::Applications::Events::WinInetRequestWrapper::onRequestComplete(this, 0x2EF1u);
    goto LABEL_76;
  }
  InternetSetStatusCallbackW(v23, Microsoft::Applications::Events::WinInetRequestWrapper::winInetCallback);
  memset(v51, 0, 0xE8u);
  std::ostringstream::ostringstream(v51);
  v25 = *(_QWORD **)(*((_QWORD *)this + 8) + 104LL);
  v26 = (_QWORD *)*v25;
  while ( v26 != v25 )
  {
    v27 = v26 + 4;
    if ( v26[7] > 0xFu )
      v27 = (_QWORD *)*v27;
    v28 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v51, v27, v26[6]);
    v29 = std::operator<<<std::char_traits<char>>(v28, ": ");
    v30 = v26 + 8;
    if ( v26[11] > 0xFu )
      v30 = (_QWORD *)*v30;
    v31 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v29, v30, v26[10]);
    std::operator<<<std::char_traits<char>>(v31, "\r\n");
    v32 = (__int64 **)v26[2];
    if ( *((_BYTE *)v32 + 25) )
    {
      for ( i = v26[1]; !*(_BYTE *)(i + 25) && v26 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v26 = (_QWORD *)i;
      v26 = (_QWORD *)i;
    }
    else
    {
      v26 = (_QWORD *)v26[2];
      for ( j = *v32; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v26 = j;
    }
  }
  v35 = (_DWORD *)std::ostream::tellp(v51, dwContext_8);
  v36 = *v35 + v35[2];
  std::stringbuf::str(&v51[1], lpszHeaders_8);
  v37 = (const CHAR *)lpszHeaders_8;
  if ( v48 > 0xF )
    v37 = lpszHeaders_8[0];
  v38 = HttpAddRequestHeadersA(*((HINTERNET *)this + 7), v37, v36, 0xA0000000);
  std::string::_Tidy_deallocate(lpszHeaders_8);
  if ( v38 )
  {
    v41 = *((_QWORD *)this + 5);
    if ( v41 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 16LL))(v41, 6, *((_QWORD *)this + 7));
    v42 = HttpSendRequestW(
            *((HINTERNET *)this + 7),
            0,
            0,
            *(LPVOID *)(*((_QWORD *)this + 8) + 152LL),
            *(_DWORD *)(*((_QWORD *)this + 8) + 160LL) - *(_QWORD *)(*((_QWORD *)this + 8) + 152LL));
    v43 = GetLastError();
    if ( !v42 || v43 == 997 )
    {
      std::ostringstream::~ostringstream(&v51[17]);
      v51[17] = &std::ios_base::`vftable';
      std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v51[17]);
      goto LABEL_76;
    }
    v44 = GetLastError();
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        2,
        "MATSDK",
        "HttpSendRequest() failed: %d",
        v44);
    v45 = *((_QWORD *)this + 5);
    if ( v45 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v45 + 16LL))(v45, 5, *((_QWORD *)this + 7));
  }
  else
  {
    v39 = GetLastError();
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        2,
        "MATSDK",
        "HttpAddRequestHeadersA() failed: %d",
        v39);
    v40 = *((_QWORD *)this + 5);
    if ( v40 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v40 + 16LL))(
        v40,
        3,
        *((_QWORD *)this + 7),
        0);
  }
  Microsoft::Applications::Events::WinInetRequestWrapper::onRequestComplete(this, 0x2EF1u);
  std::ostringstream::~ostringstream(&v51[17]);
  v51[17] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v51[17]);
LABEL_76:
  Mtx_unlock((_Mtx_t)v4);
}

```

## disassembly

```asm
0x14013feb4  mov     rax, rsp
0x14013feb7  mov     [rax+10h], rbx
0x14013febb  mov     [rax+18h], rsi
0x14013febf  mov     [rax+20h], rdi
0x14013fec3  push    rbp
0x14013fec4  push    r12
0x14013fec6  push    r13
0x14013fec8  push    r14
0x14013feca  push    r15
0x14013fecc  lea     rbp, [rax-638h]
0x14013fed3  sub     rsp, 710h
0x14013feda  mov     rax, cs:__security_cookie
0x14013fee1  xor     rax, rsp
0x14013fee4  mov     [rbp+630h+var_30], rax
0x14013feeb  mov     rbx, rdx
0x14013feee  mov     r14, rcx
0x14013fef1  mov     rdi, [rcx]
0x14013fef4  add     rdi, 10h
0x14013fef8  mov     [rbp+630h+var_6B0], rdi
0x14013fefc  mov     rcx, rdi; _Mtx_t
0x14013feff  call    _Mtx_lock
0x14013ff04  test    eax, eax
0x14013ff06  jnz     loc_140140583
0x14013ff0c  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x14013ff13  jz      loc_14014058E
0x14013ff19  mov     [r14+28h], rbx
0x14013ff1d  mov     r12, [r14]
0x14013ff20  add     r12, 60h ; '`'
0x14013ff24  lea     rsi, [r14+8]
0x14013ff28  mov     r13, [r12]
0x14013ff2c  mov     rbx, [r13+8]
0x14013ff30  mov     [rsp+730h+dwContext+8], rbx
0x14013ff35  mov     [rsp+730h+var_6E8], 0
0x14013ff3e  mov     r15, r13
0x14013ff41  jmp     short loc_14013FF7C
0x14013ff43  mov     [rsp+730h+dwContext+8], rbx
0x14013ff48  lea     rcx, [rbx+20h]
0x14013ff4c  mov     rdx, rsi
0x14013ff4f  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0@Z; std::operator<<char>(std::string const &,std::string const &)
0x14013ff54  mov     cl, al
0x14013ff56  test    al, al
0x14013ff58  jz      short loc_14013FF64
0x14013ff5a  mov     dword ptr [rsp+730h+var_6E8], 0
0x14013ff62  jmp     short loc_14013FF6F
0x14013ff64  mov     dword ptr [rsp+730h+var_6E8], 1
0x14013ff6c  mov     r15, rbx
0x14013ff6f  lea     rax, [rbx+10h]
0x14013ff73  test    cl, cl
0x14013ff75  cmovz   rax, rbx
0x14013ff79  mov     rbx, [rax]
0x14013ff7c  cmp     byte ptr [rbx+19h], 0
0x14013ff80  jz      short loc_14013FF43
0x14013ff82  cmp     byte ptr [r15+19h], 0
0x14013ff87  jnz     short loc_14013FFA1
0x14013ff89  lea     rdx, [r15+20h]
0x14013ff8d  mov     rcx, rsi
0x14013ff90  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0@Z; std::operator<<char>(std::string const &,std::string const &)
0x14013ff95  test    al, al
0x14013ff97  jnz     short loc_14013FFA1
0x14013ff99  xor     r13d, r13d
0x14013ff9c  jmp     loc_140140040
0x14013ffa1  mov     rax, 38E38E38E38E38Eh
0x14013ffab  cmp     [r12+8], rax
0x14013ffb0  jz      loc_14014057D
0x14013ffb6  mov     [rsp+730h+lpszHeaders+8], r12
0x14013ffbb  mov     [rsp+730h+var_6C8], 0
0x14013ffc4  mov     ecx, 48h ; 'H'; Size
0x14013ffc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14013ffce  mov     rbx, rax
0x14013ffd1  mov     [rsp+730h+var_6C8], rax
0x14013ffd6  xorps   xmm0, xmm0
0x14013ffd9  movups  xmmword ptr [rax+20h], xmm0
0x14013ffdd  mov     qword ptr [rax+30h], 0
0x14013ffe5  mov     qword ptr [rax+38h], 0
0x14013ffed  mov     r8, [rsi+10h]
0x14013fff1  cmp     qword ptr [rsi+18h], 0Fh
0x14013fff6  jbe     short loc_14013FFFB
0x14013fff8  mov     rsi, [rsi]
0x14013fffb  mov     rdx, rsi
0x14013fffe  lea     rcx, [rax+20h]
0x140140002  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x140140007  mov     qword ptr [rbx+40h], 0
0x14014000f  mov     [rbx], r13
0x140140012  mov     [rbx+8], r13
0x140140016  mov     [rbx+10h], r13
0x14014001a  xor     r13d, r13d
0x14014001d  mov     [rbx+18h], r13w
0x140140022  movups  xmm0, xmmword ptr [rsp+730h+dwContext+8]
0x140140027  movdqu  xmmword ptr [rsp+730h+lpszHeaders+8], xmm0
0x14014002d  mov     r8, rbx
0x140140030  lea     rdx, [rsp+730h+lpszHeaders+8]
0x140140035  mov     rcx, r12
0x140140038  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4EventLatency@Events@Applications@Microsoft@@VRecordStats@234@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4EventLatency@Events@Applications@Microsoft@@VRecordStats@234@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4EventLatency@Events@Applications@Microsoft@@VRecordStats@234@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::Applications::Events::EventLatency const,Microsoft::Applications::Events::RecordStats>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Microsoft::Applications::Events::EventLatency const,Microsoft::Applications::Events::RecordStats>,void *> *>,std::_Tree_node<std::pair<Microsoft::Applications::Events::EventLatency const,Microsoft::Applications::Events::RecordStats>,void *> * const)
0x14014003d  mov     r15, rax
0x140140040  mov     [r15+40h], r14
0x140140044  mov     rcx, [r14+28h]
0x140140048  cmp     [r14+46Ah], r13b
0x14014004f  jz      short loc_140140064
0x140140051  test    rcx, rcx
0x140140054  jz      loc_140140269
0x14014005a  mov     edx, 3
0x14014005f  jmp     loc_140140255
0x140140064  mov     r12d, 2
0x14014006a  test    rcx, rcx
0x14014006d  jz      short loc_140140086
0x14014006f  mov     rax, [rcx]
0x140140072  xor     r9d, r9d
0x140140075  mov     r8, [r14+38h]
0x140140079  mov     edx, r12d
0x14014007c  mov     rax, [rax+10h]
0x140140080  call    cs:__guard_dispatch_icall_fptr
0x140140086  mov     ebx, 68h ; 'h'
0x14014008b  mov     r8d, ebx; Size
0x14014008e  xor     edx, edx; Val
0x140140090  lea     rcx, [rbp+630h+UrlComponents]; void *
0x140140094  call    memset
0x140140099  mov     [rbp+630h+UrlComponents.dwStructSize], ebx
0x14014009c  mov     ebx, 100h
0x1401400a1  mov     r8d, ebx; Size
0x1401400a4  xor     edx, edx; Val
0x1401400a6  lea     rcx, [rbp+630h+szServerName]; void *
0x1401400ad  call    memset
0x1401400b2  lea     rax, [rbp+630h+szServerName]
0x1401400b9  mov     [rbp+630h+UrlComponents.lpszHostName], rax
0x1401400bd  mov     [rbp+630h+UrlComponents.dwHostNameLength], ebx
0x1401400c0  mov     ebx, 400h
0x1401400c5  mov     r8d, ebx; Size
0x1401400c8  xor     edx, edx; Val
0x1401400ca  lea     rcx, [rbp+630h+szObjectName]; void *
0x1401400d1  call    memset
0x1401400d6  lea     rax, [rbp+630h+szObjectName]
0x1401400dd  mov     [rbp+630h+UrlComponents.lpszUrlPath], rax
0x1401400e1  mov     [rbp+630h+UrlComponents.dwUrlPathLength], ebx
0x1401400e4  mov     rax, [r14+40h]
0x1401400e8  lea     rcx, [rax+48h]
0x1401400ec  cmp     qword ptr [rcx+18h], 0Fh
0x1401400f1  jbe     short loc_1401400F6
0x1401400f3  mov     rcx, [rcx]; lpszUrl
0x1401400f6  lea     r9, [rbp+630h+UrlComponents]; lpUrlComponents
0x1401400fa  xor     r8d, r8d; dwFlags
0x1401400fd  mov     edx, [rax+58h]; dwUrlLength
0x140140100  call    cs:__imp_InternetCrackUrlA
0x140140106  test    eax, eax
0x140140108  jnz     short loc_140140152
0x14014010a  call    cs:__imp_GetLastError
0x140140110  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r12d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140140117  jl      short loc_140140149
0x140140119  mov     rcx, [r14+40h]
0x14014011d  add     rcx, 48h ; 'H'
0x140140121  cmp     qword ptr [rcx+18h], 0Fh
0x140140126  jbe     short loc_14014012B
0x140140128  mov     rcx, [rcx]
0x14014012b  mov     [rsp+730h+lpszPassword], rcx
0x140140130  mov     r9d, eax
0x140140133  lea     r8, aInternetcracku; "InternetCrackUrl() failed: dwError=%d u"...
0x14014013a  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140140141  mov     ecx, r12d
0x140140144  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140140149  mov     rcx, [r14+28h]
0x14014014d  jmp     loc_140140051
0x140140152  mov     rcx, [r14]
0x140140155  mov     [rsp+730h+dwContext], r14; dwContext
0x14014015a  mov     [rsp+730h+dwFlags], r13d; dwFlags
0x14014015f  mov     r15d, 3
0x140140165  mov     [rsp+730h+dwService], r15d; dwService
0x14014016a  mov     [rsp+730h+lpszPassword], r13; lpszPassword
0x14014016f  xor     r9d, r9d; lpszUserName
0x140140172  movzx   r8d, [rbp+630h+UrlComponents.nPort]; nServerPort
0x140140177  lea     rdx, [rbp+630h+szServerName]; lpszServerName
0x14014017e  mov     rcx, [rcx+8]; hInternet
0x140140182  call    cs:__imp_InternetConnectA
0x140140188  mov     rcx, rax; hConnect
0x14014018b  mov     [r14+30h], rax
0x14014018f  test    rax, rax
0x140140192  jnz     short loc_1401401B3
0x140140194  call    cs:__imp_GetLastError
0x14014019a  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r12d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x1401401a1  jl      loc_140140249
0x1401401a7  lea     r8, aInternetconnec; "InternetConnect() failed: %d"
0x1401401ae  jmp     loc_140140237
0x1401401b3  lea     rax, asc_1401A2C14; "*/*"
0x1401401ba  mov     [rbp+630h+lpszAcceptTypes], rax
0x1401401c1  mov     [rbp+630h+var_538], r13
0x1401401c8  mov     eax, 84CC0300h
0x1401401cd  mov     r8d, 844C0300h
0x1401401d3  cmp     [rbp+630h+UrlComponents.nScheme], 4
0x1401401d7  cmovz   r8d, eax
0x1401401db  mov     rdx, [r14+40h]
0x1401401df  add     rdx, 28h ; '('
0x1401401e3  cmp     qword ptr [rdx+18h], 0Fh
0x1401401e8  jbe     short loc_1401401ED
0x1401401ea  mov     rdx, [rdx]; lpszVerb
0x1401401ed  mov     [rsp+730h+dwContext], r14; dwContext
0x1401401f2  mov     [rsp+730h+dwFlags], r8d; dwFlags
0x1401401f7  lea     rax, [rbp+630h+lpszAcceptTypes]
0x1401401fe  mov     qword ptr [rsp+730h+dwService], rax; lplpszAcceptTypes
0x140140203  mov     [rsp+730h+lpszPassword], r13; lpszReferrer
0x140140208  xor     r9d, r9d; lpszVersion
0x14014020b  lea     r8, [rbp+630h+szObjectName]; lpszObjectName
0x140140212  call    cs:__imp_HttpOpenRequestA
0x140140218  mov     [r14+38h], rax
0x14014021c  test    rax, rax
0x14014021f  jnz     short loc_14014027B
0x140140221  call    cs:__imp_GetLastError
0x140140227  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, r12d; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14014022e  jl      short loc_140140249
0x140140230  lea     r8, aHttpopenreques; "HttpOpenRequest() failed: %d"
0x140140237  mov     r9d, eax
0x14014023a  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x140140241  mov     ecx, r12d
0x140140244  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140140249  mov     rcx, [r14+28h]
0x14014024d  test    rcx, rcx
0x140140250  jz      short loc_140140269
0x140140252  mov     edx, r15d
0x140140255  mov     rax, [rcx]
0x140140258  xor     r9d, r9d
0x14014025b  mov     r8, [r14+38h]
0x14014025f  mov     rax, [rax+10h]
0x140140263  call    cs:__guard_dispatch_icall_fptr
0x140140269  mov     edx, 2EF1h; unsigned int
0x14014026e  mov     rcx, r14; this
0x140140271  call    ?onRequestComplete@WinInetRequestWrapper@Events@Applications@Microsoft@@QEAAXK@Z; Microsoft::Applications::Events::WinInetRequestWrapper::onRequestComplete(ulong)
0x140140276  jmp     loc_140140545
0x14014027b  lea     rdx, ?winInetCallback@WinInetRequestWrapper@Events@Applications@Microsoft@@SAXPEAX_KK0K@Z; lpfnInternetCallback
0x140140282  mov     rcx, rax; hInternet
0x140140285  call    cs:__imp_InternetSetStatusCallbackW
0x14014028b  xor     edx, edx; Val
0x14014028d  mov     r8d, 0E8h; Size
0x140140293  lea     rcx, [rbp+630h+var_630]; void *
0x140140297  call    memset
0x14014029c  lea     rcx, [rbp+630h+var_630]
0x1401402a0  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1401402a5  nop
0x1401402a6  mov     rsi, [r14+40h]
0x1401402aa  mov     rsi, [rsi+68h]
0x1401402ae  mov     rbx, [rsi]
0x1401402b1  cmp     rbx, rsi
0x1401402b4  jz      loc_14014035C
0x1401402ba  lea     rdx, [rbx+20h]
0x1401402be  cmp     qword ptr [rbx+38h], 0Fh
0x1401402c3  jbe     short loc_1401402C8
0x1401402c5  mov     rdx, [rdx]
0x1401402c8  mov     r8, [rbx+30h]
0x1401402cc  lea     rcx, [rbp+630h+var_630]
0x1401402d0  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1401402d5  lea     rdx, asc_140194BD8; ": "
0x1401402dc  mov     rcx, rax
0x1401402df  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1401402e4  lea     rdx, [rbx+40h]
0x1401402e8  cmp     qword ptr [rbx+58h], 0Fh
0x1401402ed  jbe     short loc_1401402F2
0x1401402ef  mov     rdx, [rdx]
0x1401402f2  mov     r8, [rbx+50h]
0x1401402f6  mov     rcx, rax
0x1401402f9  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x1401402fe  lea     rdx, asc_1401A2CE4; "\r\n"
0x140140305  mov     rcx, rax
0x140140308  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x14014030d  mov     rcx, [rbx+10h]
0x140140311  cmp     [rcx+19h], r13b
0x140140315  jz      short loc_140140338
0x140140317  mov     rax, [rbx+8]
0x14014031b  jmp     short loc_14014032A
0x14014031d  cmp     rbx, [rax+10h]
0x140140321  jnz     short loc_140140330
0x140140323  mov     rbx, rax
0x140140326  mov     rax, [rax+8]
0x14014032a  cmp     [rax+19h], r13b
0x14014032e  jz      short loc_14014031D
0x140140330  mov     rbx, rax
0x140140333  jmp     loc_1401402B1
0x140140338  mov     rbx, rcx
0x14014033b  mov     rcx, [rcx]
0x14014033e  cmp     [rcx+19h], r13b
0x140140342  jnz     loc_1401402B1
0x140140348  mov     rbx, rcx
0x14014034b  mov     rax, [rcx]
0x14014034e  mov     rcx, rax
0x140140351  cmp     [rax+19h], r13b
0x140140355  jz      short loc_140140348
0x140140357  jmp     loc_1401402B1
0x14014035c  lea     rdx, [rsp+730h+dwContext+8]
0x140140361  lea     rcx, [rbp+630h+var_630]
0x140140365  call    ?tellp@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::ostream::tellp(void)
0x14014036a  mov     ebx, [rax+8]
0x14014036d  add     ebx, [rax]
0x14014036f  lea     rdx, [rsp+730h+lpszHeaders+8]
0x140140374  lea     rcx, [rbp+630h+var_628]
0x140140378  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x14014037d  lea     rdx, [rsp+730h+lpszHeaders+8]
0x140140382  cmp     [rsp+730h+var_6B8], 0Fh
0x140140388  cmova   rdx, [rsp+730h+lpszHeaders+8]; lpszHeaders
0x14014038e  mov     r9d, 0A0000000h; dwModifiers
0x140140394  mov     r8d, ebx; dwHeadersLength
0x140140397  mov     rcx, [r14+38h]; hRequest
0x14014039b  call    cs:__imp_HttpAddRequestHeadersA
0x1401403a1  mov     ebx, eax
0x1401403a3  lea     rcx, [rsp+730h+lpszHeaders+8]
0x1401403a8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
  ... truncated ...
```
