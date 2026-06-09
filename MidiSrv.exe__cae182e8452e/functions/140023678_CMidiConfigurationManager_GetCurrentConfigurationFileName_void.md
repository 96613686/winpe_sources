# CMidiConfigurationManager::GetCurrentConfigurationFileName(void)

- ea: `0x140023678`
- end: `0x14002389b`
- name: `?GetCurrentConfigurationFileName@CMidiConfigurationManager@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `547`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140025978`

## callees

- `0x14000183c`
- `0x140005170`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x1400229d8`
- `0x140023678`

## string_xrefs

- `0x14002372f`: `CurrentConfig`
- `0x1400236b7`: `CMidiConfigurationManager::GetCurrentConfigurationFileName`
- `0x140023700`: `Software\Microsoft\Windows MIDI Services`

## pseudocode

```c
__int64 __fastcall CMidiConfigurationManager::GetCurrentConfigurationFileName(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  const WCHAR *v7; // r8
  __int128 *p_Src; // rbx
  __int128 *v9; // rcx
  __int128 *v10; // r14
  char *v11; // rdi
  __int64 trivial_2; // rax
  __int64 result; // rax
  __int64 v15; // [rsp+40h] [rbp-A8h] BYREF
  const char *v16; // [rsp+48h] [rbp-A0h] BYREF
  __int128 Src; // [rsp+50h] [rbp-98h] BYREF
  __int128 v18; // [rsp+60h] [rbp-88h]
  __int128 v19; // [rsp+70h] [rbp-78h] BYREF
  __int64 v20; // [rsp+80h] [rbp-68h]
  unsigned __int64 v21; // [rsp+88h] [rbp-60h]
  LPCWSTR lpSubKey[2]; // [rsp+90h] [rbp-58h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-48h]

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v15 = a1;
    v16 = "CMidiConfigurationManager::GetCurrentConfigurationFileName";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v4,
      (unsigned int)&byte_140088747,
      v5,
      v6,
      (__int64)&v16,
      (__int64)&v15);
  }
  *(_OWORD *)lpSubKey = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(lpSubKey, L"Software\\Microsoft\\Windows MIDI Services", 40);
  v7 = (const WCHAR *)lpSubKey;
  if ( *((_QWORD *)&v23 + 1) > 7u )
    v7 = lpSubKey[0];
  try
  {
    wil::reg::get_value<std::wstring>(&Src, HKEY_LOCAL_MACHINE, v7, L"CurrentConfig");
    if ( (_QWORD)v18 )
    {
      v19 = 0;
      v20 = 0;
      v21 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v19, L"><:?*/\\|", 8);
      p_Src = &Src;
      if ( *((_QWORD *)&v18 + 1) > 7u )
        p_Src = (__int128 *)Src;
      while ( 1 )
      {
        v9 = &Src;
        if ( *((_QWORD *)&v18 + 1) > 7u )
          v9 = (__int128 *)Src;
        if ( p_Src >= (__int128 *)((char *)v9 + 2 * (_QWORD)v18) )
          break;
        v10 = &v19;
        if ( v21 > 7 )
          v10 = (__int128 *)v19;
        if ( v20 )
        {
          v11 = (char *)v10 + 2 * v20;
          trivial_2 = _std_find_trivial_2(v10, v11, *(unsigned __int16 *)p_Src);
          if ( (char *)trivial_2 != v11 && (trivial_2 - (__int64)v10) >> 1 != -1 )
            *(_WORD *)p_Src = 45;
        }
        p_Src = (__int128 *)((char *)p_Src + 2);
      }
      std::wstring::~wstring(&v19);
    }
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    *(_OWORD *)a2 = Src;
    *(_OWORD *)(a2 + 16) = v18;
    *(_QWORD *)&v18 = 0;
    *((_QWORD *)&v18 + 1) = 7;
    LOWORD(Src) = 0;
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(lpSubKey);
    result = a2;
  }
  catch ( ... )
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>(a2, &S2, 0);
    std::wstring::~wstring(lpSubKey);
    return a2;
  }
  return result;
}

```

## disassembly

```asm
0x140023678  push    rbx
0x14002367a  push    rsi
0x14002367b  push    rdi
0x14002367c  push    r14
0x14002367e  sub     rsp, 0C8h
0x140023685  mov     rax, cs:__security_cookie
0x14002368c  xor     rax, rsp
0x14002368f  mov     [rsp+0E8h+var_38], rax
0x140023697  mov     rsi, rdx
0x14002369a  mov     rbx, rcx
0x14002369d  mov     [rsp+0E8h+var_B8], rdx
0x1400236a2  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400236a7  mov     rcx, [rax+8]
0x1400236ab  mov     eax, [rcx]
0x1400236ad  cmp     eax, 4
0x1400236b0  jbe     short loc_1400236E3
0x1400236b2  mov     [rsp+0E8h+var_A8], rbx
0x1400236b7  lea     rax, aCmidiconfigura_8; "CMidiConfigurationManager::GetCurrentCo"...
0x1400236be  mov     [rsp+0E8h+var_A0], rax
0x1400236c3  lea     rax, [rsp+0E8h+var_A8]
0x1400236c8  mov     [rsp+0E8h+var_C0], rax
0x1400236cd  lea     rax, [rsp+0E8h+var_A0]
0x1400236d2  mov     [rsp+0E8h+var_C8], rax
0x1400236d7  lea     rdx, byte_140088747
0x1400236de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1400236e3  xorps   xmm0, xmm0
0x1400236e6  movups  xmmword ptr [rsp+0E8h+lpSubKey], xmm0
0x1400236ee  xorps   xmm1, xmm1
0x1400236f1  movdqu  [rsp+0E8h+var_48], xmm1
0x1400236fa  mov     r8d, 28h ; '('
0x140023700  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows MIDI Servi"...
0x140023707  lea     rcx, [rsp+0E8h+lpSubKey]
0x14002370f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140023714  nop
0x140023715  lea     r8, [rsp+0E8h+lpSubKey]
0x14002371d  cmp     qword ptr [rsp+0E8h+var_48+8], 7
0x140023726  cmova   r8, [rsp+0E8h+lpSubKey]; lpSubKey
0x14002372f  lea     r9, aCurrentconfig; "CurrentConfig"
0x140023736  mov     rdx, 0FFFFFFFF80000002h; hkey
0x14002373d  lea     rcx, [rsp+0E8h+Src]; Src
0x140023742  call    ??$get_value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1@Z; wil::reg::get_value<std::wstring>(HKEY__ *,ushort const *,ushort const *)
0x140023747  nop
0x140023748  cmp     qword ptr [rsp+0E8h+var_88], 0
0x14002374e  jz      loc_140023815
0x140023754  xorps   xmm0, xmm0
0x140023757  movups  [rsp+0E8h+var_78], xmm0
0x14002375c  mov     [rsp+0E8h+var_68], 0
0x140023768  mov     [rsp+0E8h+var_60], 0
0x140023774  mov     r8d, 8
0x14002377a  lea     rdx, asc_14007D3E0; "><:?*/\\|"
0x140023781  lea     rcx, [rsp+0E8h+var_78]
0x140023786  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002378b  lea     rbx, [rsp+0E8h+Src]
0x140023790  cmp     qword ptr [rsp+0E8h+var_88+8], 7
0x140023796  cmova   rbx, qword ptr [rsp+0E8h+Src]
0x14002379c  lea     rcx, [rsp+0E8h+Src]
0x1400237a1  cmp     qword ptr [rsp+0E8h+var_88+8], 7
0x1400237a7  cmova   rcx, qword ptr [rsp+0E8h+Src]
0x1400237ad  mov     rax, qword ptr [rsp+0E8h+var_88]
0x1400237b2  lea     rdx, [rcx+rax*2]
0x1400237b6  cmp     rbx, rdx
0x1400237b9  jnb     short loc_14002380B
0x1400237bb  mov     rax, [rsp+0E8h+var_68]
0x1400237c3  lea     r14, [rsp+0E8h+var_78]
0x1400237c8  cmp     [rsp+0E8h+var_60], 7
0x1400237d1  cmova   r14, qword ptr [rsp+0E8h+var_78]
0x1400237d7  test    rax, rax
0x1400237da  jz      short loc_140023805
0x1400237dc  lea     rdi, [r14+rax*2]
0x1400237e0  movzx   r8d, word ptr [rbx]
0x1400237e4  mov     rdx, rdi
0x1400237e7  mov     rcx, r14
0x1400237ea  call    __std_find_trivial_2
0x1400237ef  cmp     rax, rdi
0x1400237f2  jz      short loc_140023805
0x1400237f4  sub     rax, r14
0x1400237f7  sar     rax, 1
0x1400237fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400237fe  jz      short loc_140023805
0x140023800  mov     word ptr [rbx], 2Dh ; '-'
0x140023805  add     rbx, 2
0x140023809  jmp     short loc_14002379C
0x14002380b  lea     rcx, [rsp+0E8h+var_78]; void *
0x140023810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023815  mov     qword ptr [rsi+10h], 0
0x14002381d  mov     qword ptr [rsi+18h], 0
0x140023825  movups  xmm0, [rsp+0E8h+Src]
0x14002382a  movups  xmmword ptr [rsi], xmm0
0x14002382d  movups  xmm1, [rsp+0E8h+var_88]
0x140023832  movups  xmmword ptr [rsi+10h], xmm1
0x140023836  mov     qword ptr [rsp+0E8h+var_88], 0
0x14002383f  mov     qword ptr [rsp+0E8h+var_88+8], 7
0x140023848  xor     ecx, ecx
0x14002384a  mov     word ptr [rsp+0E8h+Src], cx
0x14002384f  lea     rcx, [rsp+0E8h+Src]; void *
0x140023854  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023859  nop
0x14002385a  lea     rcx, [rsp+0E8h+lpSubKey]; void *
0x140023862  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023867  mov     rax, rsi
0x14002386a  jmp     short loc_14002387E
0x14002386c  lea     rcx, [rsp+0E8h+lpSubKey]; void *
0x140023874  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023879  mov     rax, [rsp+0E8h+var_B8]
0x14002387e  mov     rcx, [rsp+0E8h+var_38]
0x140023886  xor     rcx, rsp; StackCookie
0x140023889  call    __security_check_cookie
0x14002388e  add     rsp, 0C8h
0x140023895  pop     r14
0x140023897  pop     rdi
0x140023898  pop     rsi
0x140023899  pop     rbx
0x14002389a  retn
```
