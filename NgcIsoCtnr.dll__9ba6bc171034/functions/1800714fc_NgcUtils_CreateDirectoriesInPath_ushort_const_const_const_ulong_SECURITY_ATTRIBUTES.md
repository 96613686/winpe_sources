# NgcUtils::CreateDirectoriesInPath(ushort const * const * const,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800714fc`
- end: `0x18007161d`
- name: `?CreateDirectoriesInPath@NgcUtils@@YAJQEBQEBGKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *const *const, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180049284`

## callees

- `0x180002654`
- `0x180007670`
- `0x180011c9c`
- `0x18001cbe8`
- `0x1800712f4`
- `0x1800713cc`
- `0x1800714fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800715af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800715af`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180071590`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180071590`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::CreateDirectoriesInPath(
        NgcUtils *this,
        const unsigned __int16 *const *const a2,
        __int64 a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  unsigned int v5; // edi
  __m128i si128; // xmm6
  unsigned int v7; // ebx
  NgcUtils *v8; // rax
  const unsigned __int16 *v9; // rdx
  int v10; // eax
  const WCHAR *v11; // rax
  signed int LastError; // eax
  int v13; // r8d
  int v14; // r9d
  unsigned int v16; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v17[2]; // [rsp+38h] [rbp-40h] BYREF

  v5 = 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v17[0] = 0;
    v17[1] = si128;
    LOWORD(v17[0]) = 0;
    v7 = NgcUtils::ComposePath(this, v5, v17);
    if ( (v7 & 0x80000000) != 0 )
      break;
    v8 = (NgcUtils *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    v10 = NgcUtils::CheckForDirectory(v8, v9);
    v7 = v10;
    if ( v10 < 0 )
    {
      if ( (unsigned int)(v10 + 2147024894) > 1 )
        break;
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      if ( !CreateDirectoryW(v11, 0) )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( *(_DWORD *)g_logProvider > 2u )
        {
          v16 = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            g_logProvider,
            (unsigned int)&byte_1800B3A9F,
            v13,
            v14,
            (__int64)&v16);
        }
        break;
      }
      v7 = 0;
    }
    std::wstring::_Tidy_deallocate(v17);
    if ( ++v5 > 2 )
      return v7;
  }
  std::wstring::_Tidy_deallocate(v17);
  return v7;
}

```

## disassembly

```asm
0x1800714fc  mov     [rsp+arg_8], rbx
0x180071501  mov     [rsp+arg_10], rsi
0x180071506  push    rdi
0x180071507  sub     rsp, 70h
0x18007150b  movaps  [rsp+78h+var_18], xmm6
0x180071510  mov     rax, cs:__security_cookie
0x180071517  xor     rax, rsp
0x18007151a  mov     [rsp+78h+var_20], rax
0x18007151f  mov     rsi, rcx
0x180071522  mov     edi, 1
0x180071527  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007152f  xorps   xmm0, xmm0
0x180071532  movups  [rsp+78h+var_40], xmm0
0x180071537  movdqu  [rsp+78h+var_30], xmm6
0x18007153d  xor     eax, eax
0x18007153f  mov     word ptr [rsp+78h+var_40], ax
0x180071544  lea     r8, [rsp+78h+var_40]
0x180071549  mov     edx, edi
0x18007154b  mov     rcx, rsi
0x18007154e  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x180071553  mov     ebx, eax
0x180071555  test    eax, eax
0x180071557  js      loc_1800715ED
0x18007155d  lea     rcx, [rsp+78h+var_40]
0x180071562  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180071567  mov     rcx, rax; this
0x18007156a  call    ?CheckForDirectory@NgcUtils@@YAJPEBG@Z; NgcUtils::CheckForDirectory(ushort const *)
0x18007156f  mov     ebx, eax
0x180071571  test    eax, eax
0x180071573  js      short loc_180071577
0x180071575  jmp     short loc_18007159C
0x180071577  add     eax, 7FF8FFFEh
0x18007157c  cmp     eax, 1
0x18007157f  ja      short loc_1800715ED
0x180071581  lea     rcx, [rsp+78h+var_40]
0x180071586  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007158b  mov     rcx, rax; lpPathName
0x18007158e  xor     edx, edx; lpSecurityAttributes
0x180071590  call    cs:__imp_CreateDirectoryW
0x180071596  test    eax, eax
0x180071598  jz      short loc_1800715AF
0x18007159a  xor     ebx, ebx
0x18007159c  lea     rcx, [rsp+78h+var_40]
0x1800715a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800715a6  inc     edi
0x1800715a8  cmp     edi, 2
0x1800715ab  jbe     short loc_18007152F
0x1800715ad  jmp     short loc_1800715F7
0x1800715af  call    cs:__imp_GetLastError
0x1800715b5  mov     ebx, eax
0x1800715b7  test    eax, eax
0x1800715b9  jle     short loc_1800715C4
0x1800715bb  movzx   ebx, ax
0x1800715be  or      ebx, 80070000h
0x1800715c4  mov     rcx, cs:g_logProvider
0x1800715cb  mov     eax, [rcx]
0x1800715cd  cmp     eax, 2
0x1800715d0  jbe     short loc_1800715ED
0x1800715d2  mov     [rsp+78h+var_48], ebx
0x1800715d6  lea     rax, [rsp+78h+var_48]
0x1800715db  mov     [rsp+78h+var_58], rax
0x1800715e0  lea     rdx, byte_1800B3A9F
0x1800715e7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800715ec  nop
0x1800715ed  lea     rcx, [rsp+78h+var_40]
0x1800715f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800715f7  mov     eax, ebx
0x1800715f9  mov     rcx, [rsp+78h+var_20]
0x1800715fe  xor     rcx, rsp; StackCookie
0x180071601  call    __security_check_cookie
0x180071606  lea     r11, [rsp+78h+var_8]
0x18007160b  mov     rbx, [r11+18h]
0x18007160f  mov     rsi, [r11+20h]
0x180071613  movaps  xmm6, [rsp+78h+var_18]
0x180071618  mov     rsp, r11
0x18007161b  pop     rdi
0x18007161c  retn
```
