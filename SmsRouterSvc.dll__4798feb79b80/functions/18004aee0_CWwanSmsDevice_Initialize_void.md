# CWwanSmsDevice::Initialize(void)

- ea: `0x18004aee0`
- end: `0x18004b2dc`
- name: `?Initialize@CWwanSmsDevice@@UEAAJXZ`
- size: `1020`
- prototype: `__int64 __fastcall(CWwanSmsDevice *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003a60`
- `0x180004998`
- `0x1800069f0`
- `0x180006c84`
- `0x1800093d4`
- `0x18000d388`
- `0x18001446c`
- `0x1800183c8`
- `0x18001c304`
- `0x1800276a4`
- `0x18004aee0`
- `0x18004b4fc`
- `0x18004b818`
- `0x18004d1d8`
- `0x18005005c`
- `0x180061618`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004af97`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b138`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b1fa`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b262`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b27d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004af97`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b138`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b1fa`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b262`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004b27d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004af5f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004af5f`

## string_xrefs

- `0x18004af58`: `%ProgramData%\Microsoft\SmsRouter\SegmentStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWwanSmsDevice::Initialize(CWwanSmsDevice *this)
{
  const unsigned __int16 *v2; // rdx
  int DirectoryDeepNoThrow; // ebx
  _BYTE *v4; // rdx
  __int64 v6; // r8
  char *v7; // rbx
  const WCHAR *p_Src; // rdx
  int v9; // r14d
  _BYTE *v10; // rdx
  _BYTE *v11; // rdx
  _BYTE *v12; // rcx
  _BYTE *v13; // rdx
  _QWORD v14[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 Src; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v16; // [rsp+B0h] [rbp-50h]
  void **v17; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v18[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE *v19; // [rsp+100h] [rbp+0h]
  WCHAR Dst[264]; // [rsp+110h] [rbp+10h] BYREF

  v14[0] = off_180070800;
  v14[1] = this;
  v14[7] = v14;
  Windows::Sms::Common::undo_action::undo_action(&v17, v14);
  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%ProgramData%\\Microsoft\\SmsRouter\\SegmentStore", Dst, 0x104u) - 1 > 0x103 )
  {
LABEL_29:
    v17 = &Windows::Sms::Common::undo_action::`vftable';
    v12 = v19;
    if ( !v19 )
      std::_Xbad_function_call();
    goto LABEL_31;
  }
  DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)Dst, v2);
  if ( DirectoryDeepNoThrow < 0 )
  {
    v17 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v19 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v19 )
    {
      v4 = v18;
      LOBYTE(v4) = v19 != v18;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v4);
    }
    return (unsigned int)DirectoryDeepNoThrow;
  }
  Src = 0;
  v16 = 0;
  v6 = -1;
  do
    ++v6;
  while ( Dst[v6] );
  std::wstring::_Construct<1,unsigned short const *>(&Src, Dst);
  std::wstring::append(&Src, (void *)L"\\");
  StringCchPrintfW(
    Dst,
    0x104u,
    L"{%08X-%04hX-%04hX-%04hX-%04hX%04hX%04hX}.dat",
    *((unsigned int *)this + 38),
    *((unsigned __int16 *)this + 78),
    *((unsigned __int16 *)this + 79),
    HIBYTE(*((unsigned __int16 *)this + 80)) | ((unsigned __int8)*((_WORD *)this + 80) << 8),
    HIBYTE(*((unsigned __int16 *)this + 81)) | ((unsigned __int8)*((_WORD *)this + 81) << 8),
    HIBYTE(*((unsigned __int16 *)this + 82)) | ((unsigned __int8)*((_WORD *)this + 82) << 8),
    HIBYTE(*((unsigned __int16 *)this + 83)) | ((unsigned __int8)*((_WORD *)this + 83) << 8));
  std::wstring::append(&Src, Dst);
  v7 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    p_Src = (const WCHAR *)&Src;
    if ( *((_QWORD *)&v16 + 1) > 7u )
      p_Src = (const WCHAR *)Src;
    v9 = CSmsConcatenateStore::Open((HANDLE *)this + 87, p_Src);
    if ( v9 >= 0 )
    {
      *((_DWORD *)this + 6) = 1;
      if ( *((_QWORD *)this + 74) )
      {
        CWwanSmsDevice::UpdateReadMessageList(this);
        std::wstring::operator=((char *)this + 608, (char *)this + 576);
        CWwanSmsDevice::OnNewSimMessageStatus(this, 0, 2);
      }
      Windows::Sms::Common::undo_action::release((Windows::Sms::Common::undo_action *)&v17);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 32);
      CWwanSmsDevice::ProcessPendingMessages(this);
      CWwanSmsDevice::NotifyDeviceChange(this, 4);
      std::wstring::~wstring(&Src);
      v17 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v19 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v19 )
      {
        v11 = v18;
        LOBYTE(v11) = v19 != v18;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v11);
      }
      return 0;
    }
    else
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 32);
      std::wstring::~wstring(&Src);
      v17 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v19 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v19 )
      {
        v10 = v18;
        LOBYTE(v10) = v19 != v18;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v10);
      }
      return (unsigned int)v9;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 32);
  std::wstring::~wstring(&Src);
  v17 = &Windows::Sms::Common::undo_action::`vftable';
  v12 = v19;
  if ( !v19 )
  {
    std::_Xbad_function_call();
    goto LABEL_29;
  }
LABEL_31:
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v19 )
  {
    v13 = v18;
    LOBYTE(v13) = v19 != v18;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v13);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18004aee0  mov     [rsp-8+arg_8], rbx
0x18004aee5  mov     [rsp-8+arg_10], rsi
0x18004aeea  push    rbp
0x18004aeeb  push    rdi
0x18004aeec  push    r14
0x18004aeee  lea     rbp, [rsp-230h]
0x18004aef6  sub     rsp, 330h
0x18004aefd  mov     rax, cs:__security_cookie
0x18004af04  xor     rax, rsp
0x18004af07  mov     [rbp+240h+var_20], rax
0x18004af0e  mov     rsi, rcx
0x18004af11  lea     rax, off_180070800
0x18004af18  mov     [rsp+340h+var_2E0], rax
0x18004af1d  mov     [rsp+340h+var_2D8], rcx
0x18004af22  lea     rax, [rsp+340h+var_2E0]
0x18004af27  mov     [rbp+240h+var_2A8], rax
0x18004af2b  lea     rdx, [rsp+340h+var_2E0]
0x18004af30  lea     rcx, [rbp+240h+var_280]
0x18004af34  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x18004af39  nop
0x18004af3a  xor     edx, edx; Val
0x18004af3c  mov     r8d, 208h; Size
0x18004af42  lea     rcx, [rbp+240h+Dst]; void *
0x18004af46  call    memset_0
0x18004af4b  mov     r14d, 104h
0x18004af51  mov     r8d, r14d; nSize
0x18004af54  lea     rdx, [rbp+240h+Dst]; lpDst
0x18004af58  lea     rcx, aProgramdataMic_0; "%ProgramData%\\Microsoft\\SmsRouter\\Se"...
0x18004af5f  call    cs:__imp_ExpandEnvironmentStringsW
0x18004af65  dec     eax
0x18004af67  cmp     eax, 103h
0x18004af6c  ja      loc_18004B269
0x18004af72  lea     rcx, [rbp+240h+Dst]; this
0x18004af76  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18004af7b  mov     ebx, eax
0x18004af7d  xor     edi, edi
0x18004af7f  test    eax, eax
0x18004af81  jns     short loc_18004AFD1
0x18004af83  lea     rcx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18004af8a  mov     [rbp+240h+var_280], rcx
0x18004af8e  mov     rcx, [rbp+240h+var_240]
0x18004af92  test    rcx, rcx
0x18004af95  jnz     short loc_18004AF9E
0x18004af97  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18004af9d  int     3; Trap to Debugger
0x18004af9e  mov     rax, [rcx]
0x18004afa1  mov     rax, [rax+10h]
0x18004afa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afaa  mov     rcx, [rbp+240h+var_240]
0x18004afae  test    rcx, rcx
0x18004afb1  jz      short loc_18004AFCA
0x18004afb3  mov     rax, [rcx]
0x18004afb6  lea     rdx, [rbp+240h+var_278]
0x18004afba  cmp     rcx, rdx
0x18004afbd  setnz   dl
0x18004afc0  mov     rax, [rax+20h]
0x18004afc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afc9  nop
0x18004afca  mov     eax, ebx
0x18004afcc  jmp     loc_18004B2B5
0x18004afd1  xorps   xmm0, xmm0
0x18004afd4  movups  [rbp+240h+Src], xmm0
0x18004afd8  xorps   xmm1, xmm1
0x18004afdb  movdqu  [rbp+240h+var_290], xmm1
0x18004afe0  lea     rax, [rbp+240h+Dst]
0x18004afe4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004afe8  inc     r8
0x18004afeb  cmp     [rax+r8*2], di
0x18004aff0  jnz     short loc_18004AFE8
0x18004aff2  lea     rdx, [rbp+240h+Dst]
0x18004aff6  lea     rcx, [rbp+240h+Src]
0x18004affa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004afff  nop
0x18004b000  lea     rdx, StringValue; "\\"
0x18004b007  lea     rcx, [rbp+240h+Src]; Src
0x18004b00b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004b010  movzx   eax, word ptr [rsi+0A6h]
0x18004b017  movzx   ecx, word ptr [rsi+0A4h]
0x18004b01e  movzx   edx, word ptr [rsi+0A2h]
0x18004b025  movzx   r11d, word ptr [rsi+0A0h]
0x18004b02d  movzx   ebx, al
0x18004b030  shl     ebx, 8
0x18004b033  shr     eax, 8
0x18004b036  or      ebx, eax
0x18004b038  movzx   r10d, cl
0x18004b03c  shl     r10d, 8
0x18004b040  shr     ecx, 8
0x18004b043  or      r10d, ecx
0x18004b046  movzx   r9d, dl
0x18004b04a  shl     r9d, 8
0x18004b04e  shr     edx, 8
0x18004b051  or      r9d, edx
0x18004b054  movzx   r8d, r11b
0x18004b058  shl     r8d, 8
0x18004b05c  shr     r11d, 8
0x18004b060  or      r8d, r11d
0x18004b063  movzx   eax, word ptr [rsi+9Eh]
0x18004b06a  movzx   ecx, word ptr [rsi+9Ch]
0x18004b071  mov     [rsp+340h+var_2F8], ebx
0x18004b075  mov     [rsp+340h+var_300], r10d
0x18004b07a  mov     [rsp+340h+var_308], r9d
0x18004b07f  mov     [rsp+340h+var_310], r8d
0x18004b084  mov     [rsp+340h+var_318], eax
0x18004b088  mov     [rsp+340h+var_320], ecx
0x18004b08c  mov     r9d, [rsi+98h]
0x18004b093  lea     r8, a08x04hx04hx04h_0; "{%08X-%04hX-%04hX-%04hX-%04hX%04hX%04hX"...
0x18004b09a  mov     rdx, r14; unsigned __int64
0x18004b09d  lea     rcx, [rbp+240h+Dst]; unsigned __int16 *
0x18004b0a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b0a6  lea     rdx, [rbp+240h+Dst]; void *
0x18004b0aa  lea     rcx, [rbp+240h+Src]; Src
0x18004b0ae  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004b0b3  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004b0ba  mov     [rsp+340h+var_2F0], rax
0x18004b0bf  lea     rbx, [rsi+20h]
0x18004b0c3  mov     [rsp+340h+var_2E8], rbx
0x18004b0c8  mov     rax, [rbx]
0x18004b0cb  mov     rcx, rbx
0x18004b0ce  mov     rax, [rax]
0x18004b0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0d6  nop
0x18004b0d7  cmp     [rsi+18h], edi
0x18004b0da  jnz     loc_18004B234
0x18004b0e0  cmp     [rsi+1Ch], edi
0x18004b0e3  jnz     loc_18004B234
0x18004b0e9  lea     rdx, [rbp+240h+Src]
0x18004b0ed  cmp     qword ptr [rbp+240h+var_290+8], 7
0x18004b0f2  cmova   rdx, qword ptr [rbp+240h+Src]; lpFileName
0x18004b0f7  lea     rcx, [rsi+2B8h]; this
0x18004b0fe  call    ?Open@CSmsConcatenateStore@@QEAAJPEBG@Z; CSmsConcatenateStore::Open(ushort const *)
0x18004b103  mov     r14d, eax
0x18004b106  test    eax, eax
0x18004b108  jns     short loc_18004B173
0x18004b10a  mov     rcx, [rbx]
0x18004b10d  mov     rax, [rcx+8]
0x18004b111  mov     rcx, rbx
0x18004b114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b119  nop
0x18004b11a  lea     rcx, [rbp+240h+Src]; void *
0x18004b11e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b123  nop
0x18004b124  lea     rcx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18004b12b  mov     [rbp+240h+var_280], rcx
0x18004b12f  mov     rcx, [rbp+240h+var_240]
0x18004b133  test    rcx, rcx
0x18004b136  jnz     short loc_18004B13F
0x18004b138  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18004b13e  int     3; Trap to Debugger
0x18004b13f  mov     rax, [rcx]
0x18004b142  mov     rax, [rax+10h]
0x18004b146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b14b  mov     rcx, [rbp+240h+var_240]
0x18004b14f  test    rcx, rcx
0x18004b152  jz      short loc_18004B16B
0x18004b154  mov     rax, [rcx]
0x18004b157  lea     rdx, [rbp+240h+var_278]
0x18004b15b  cmp     rcx, rdx
0x18004b15e  setnz   dl
0x18004b161  mov     rax, [rax+20h]
0x18004b165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b16a  nop
0x18004b16b  mov     eax, r14d
0x18004b16e  jmp     loc_18004B2B5
0x18004b173  mov     dword ptr [rsi+18h], 1
0x18004b17a  lea     r14, [rsi+240h]
0x18004b181  cmp     [r14+10h], rdi
0x18004b185  jz      short loc_18004B1AC
0x18004b187  mov     rcx, rsi; this
0x18004b18a  call    ?UpdateReadMessageList@CWwanSmsDevice@@AEAAXXZ; CWwanSmsDevice::UpdateReadMessageList(void)
0x18004b18f  lea     rcx, [rsi+260h]
0x18004b196  mov     rdx, r14
0x18004b199  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004b19e  xor     edx, edx
0x18004b1a0  lea     r8d, [rdx+2]
0x18004b1a4  mov     rcx, rsi
0x18004b1a7  call    ?OnNewSimMessageStatus@CWwanSmsDevice@@AEAAXKW4_WWAN_SMS_FLAG@@@Z; CWwanSmsDevice::OnNewSimMessageStatus(ulong,_WWAN_SMS_FLAG)
0x18004b1ac  lea     rcx, [rbp+240h+var_280]; this
0x18004b1b0  call    ?release@undo_action@Common@Sms@Windows@@QEAAXXZ; Windows::Sms::Common::undo_action::release(void)
0x18004b1b5  nop
0x18004b1b6  mov     rax, [rbx]
0x18004b1b9  mov     rcx, rbx
0x18004b1bc  mov     rax, [rax+8]
0x18004b1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1c5  nop
0x18004b1c6  mov     rcx, rsi; this
0x18004b1c9  call    ?ProcessPendingMessages@CWwanSmsDevice@@AEAAXXZ; CWwanSmsDevice::ProcessPendingMessages(void)
0x18004b1ce  mov     edx, 4
0x18004b1d3  mov     rcx, rsi
0x18004b1d6  call    ?NotifyDeviceChange@CWwanSmsDevice@@AEAAXW4SMS_DEVICE_STATUS_CHANGE_FLAGS@@@Z; CWwanSmsDevice::NotifyDeviceChange(SMS_DEVICE_STATUS_CHANGE_FLAGS)
0x18004b1db  nop
0x18004b1dc  lea     rcx, [rbp+240h+Src]; void *
0x18004b1e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b1e5  nop
0x18004b1e6  lea     rcx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18004b1ed  mov     [rbp+240h+var_280], rcx
0x18004b1f1  mov     rcx, [rbp+240h+var_240]
0x18004b1f5  test    rcx, rcx
0x18004b1f8  jnz     short loc_18004B201
0x18004b1fa  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18004b200  int     3; Trap to Debugger
0x18004b201  mov     rax, [rcx]
0x18004b204  mov     rax, [rax+10h]
0x18004b208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b20d  mov     rcx, [rbp+240h+var_240]
0x18004b211  test    rcx, rcx
0x18004b214  jz      short loc_18004B22D
0x18004b216  mov     rax, [rcx]
0x18004b219  lea     rdx, [rbp+240h+var_278]
0x18004b21d  cmp     rcx, rdx
0x18004b220  setnz   dl
0x18004b223  mov     rax, [rax+20h]
0x18004b227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b22c  nop
0x18004b22d  xor     eax, eax
0x18004b22f  jmp     loc_18004B2B5
0x18004b234  mov     rax, [rbx]
0x18004b237  mov     rcx, rbx
0x18004b23a  mov     rax, [rax+8]
0x18004b23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b243  nop
0x18004b244  lea     rcx, [rbp+240h+Src]; void *
0x18004b248  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b24d  nop
0x18004b24e  lea     rcx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18004b255  mov     [rbp+240h+var_280], rcx
0x18004b259  mov     rcx, [rbp+240h+var_240]
0x18004b25d  test    rcx, rcx
0x18004b260  jnz     short loc_18004B284
0x18004b262  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18004b268  nop
0x18004b269  lea     rcx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18004b270  mov     [rbp+240h+var_280], rcx
0x18004b274  mov     rcx, [rbp+240h+var_240]
0x18004b278  test    rcx, rcx
0x18004b27b  jnz     short loc_18004B284
0x18004b27d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18004b283  nop
0x18004b284  mov     rax, [rcx]
0x18004b287  mov     rax, [rax+10h]
0x18004b28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b290  mov     rcx, [rbp+240h+var_240]
0x18004b294  test    rcx, rcx
0x18004b297  jz      short loc_18004B2B0
0x18004b299  lea     rdx, [rbp+240h+var_278]
0x18004b29d  cmp     rcx, rdx
0x18004b2a0  mov     rax, [rcx]
0x18004b2a3  setnz   dl
0x18004b2a6  mov     rax, [rax+20h]
0x18004b2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2af  nop
0x18004b2b0  mov     eax, 8000FFFFh
0x18004b2b5  mov     rcx, [rbp+240h+var_20]
0x18004b2bc  xor     rcx, rsp; StackCookie
0x18004b2bf  call    __security_check_cookie
0x18004b2c4  lea     r11, [rsp+340h+var_10]
0x18004b2cc  mov     rbx, [r11+28h]
0x18004b2d0  mov     rsi, [r11+30h]
0x18004b2d4  mov     rsp, r11
0x18004b2d7  pop     r14
0x18004b2d9  pop     rdi
0x18004b2da  pop     rbp
0x18004b2db  retn
```
