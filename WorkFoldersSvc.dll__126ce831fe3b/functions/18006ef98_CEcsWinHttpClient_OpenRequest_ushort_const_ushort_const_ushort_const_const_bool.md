# CEcsWinHttpClient::OpenRequest(ushort const *,ushort const *,ushort const * const *,bool)

- ea: `0x18006ef98`
- end: `0x18006f2c2`
- name: `?OpenRequest@CEcsWinHttpClient@@AEAAXPEBG0PEBQEBG_N@Z`
- size: `810`
- prototype: `void __usercall(CEcsWinHttpClient *__hidden this@<rcx>, LPCWSTR pwszUrl@<rdx>, LPCWSTR pwszVerb@<r8>, const unsigned __int16 *const *@<r9>, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006c498`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x180015150`
- `0x180047d84`
- `0x18006d770`
- `0x18006e22c`
- `0x18006e8f8`
- `0x18006ef98`
- `0x180070c74`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f14c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f14c`
- `WINHTTP!WinHttpOpenRequest` at `0x18006f0fb`
- `WINHTTP!WinHttpOpenRequest` at `0x18006f0fb`
- `WINHTTP!WinHttpSetTimeouts` at `0x18006f24f`
- `WINHTTP!WinHttpSetTimeouts` at `0x18006f24f`
- `WINHTTP!WinHttpSetOption` at `0x18006f17d`
- `WINHTTP!WinHttpSetOption` at `0x18006f1e5`
- `WINHTTP!WinHttpSetOption` at `0x18006f17d`
- `WINHTTP!WinHttpSetOption` at `0x18006f1e5`

## string_xrefs

- `0x18006f01f`: `CEcsWinHttpClient::OpenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CEcsWinHttpClient::OpenRequest(
        CEcsWinHttpClient *this,
        LPCWSTR pwszUrl,
        LPCWSTR pwszVerb,
        const unsigned __int16 *const *a4,
        bool a5)
{
  _BYTE *v8; // rax
  char v9; // cl
  const unsigned __int16 *v10; // rax
  char v11; // bl
  const WCHAR *v12; // rax
  DWORD dwFlags; // r9d
  HINTERNET v14; // rax
  void *RequestHandle; // rax
  void *v16; // rax
  int v17; // ebx
  void *v18; // rax
  char pExceptionObject; // [rsp+40h] [rbp-61h] BYREF
  int pExceptionObject_4; // [rsp+44h] [rbp-5Dh] BYREF
  int Buffer; // [rsp+48h] [rbp-59h] BYREF
  int LastFailureAsHRESULT; // [rsp+50h] [rbp-51h] BYREF
  int v23; // [rsp+54h] [rbp-4Dh]
  char v24; // [rsp+58h] [rbp-49h]
  const char *v25; // [rsp+60h] [rbp-41h]
  __int64 v26; // [rsp+68h] [rbp-39h]
  HINTERNET hConnect; // [rsp+70h] [rbp-31h] BYREF
  PSRWLOCK SRWLock; // [rsp+78h] [rbp-29h] BYREF
  char v29; // [rsp+80h] [rbp-21h]
  _BYTE v30[32]; // [rsp+88h] [rbp-19h] BYREF
  _BYTE v31[32]; // [rsp+A8h] [rbp+7h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_13baba31ff4d3f580777c125170b76f8_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v8[68] & 8) == 0 || (v9 = 1, v8[65] < 6u) )
    v9 = 0;
  LastFailureAsHRESULT = 0;
  v23 = 905;
  v24 = v9;
  v25 = "CEcsWinHttpClient::OpenRequest";
  v26 = 0;
  std::wstring::wstring((__int64)v31);
  std::wstring::wstring((__int64)v30);
  LOWORD(pExceptionObject_4) = 0;
  pExceptionObject = 0;
  if ( *((_QWORD *)this + 4) )
  {
    (*(void (__fastcall **)(CEcsWinHttpClient *))(*(_QWORD *)this + 104LL))(this);
    *((_BYTE *)this + 323) = 0;
    *((_DWORD *)this + 81) = 0;
  }
  CEcsWinHttpClient::GetUrlParts(pwszUrl, (__int64)&pExceptionObject);
  hConnect = 0;
  v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
  CEcsWinHttpClient::GetConnection(this, v10, pExceptionObject_4, &hConnect);
  v11 = pExceptionObject;
  Buffer = pExceptionObject != 0 ? 8388864 : 256;
  CEcsExclusiveLock<CEcsSrwLock>::CEcsExclusiveLock<CEcsSrwLock>((__int64)&SRWLock, (RTL_SRWLOCK *)this + 1);
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
  v14 = WinHttpOpenRequest(hConnect, pwszVerb, v12, 0, 0, 0, dwFlags);
  *((_QWORD *)this + 4) = v14;
  if ( !v14 )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v23) = 943;
    pExceptionObject_4 = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject_4;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v23) = 943;
  if ( v29 )
  {
    ReleaseSRWLockExclusive(SRWLock);
    v29 = 0;
  }
  Buffer = 1;
  RequestHandle = CEcsWinHttpClient::GetRequestHandle(this);
  if ( !WinHttpSetOption(RequestHandle, 0x4Du, &Buffer, 4u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v23) = 953;
    pExceptionObject_4 = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject_4;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v23) = 953;
  if ( v11 && !a5 )
  {
    pExceptionObject_4 = 1;
    LastFailureAsHRESULT = 0;
    v16 = CEcsWinHttpClient::GetRequestHandle(this);
    if ( !WinHttpSetOption(v16, 0x4Fu, &pExceptionObject_4, 4u) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v23) = 962;
      LODWORD(hConnect) = LastFailureAsHRESULT;
      throw (long *)&hConnect;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v23) = 962;
  }
  CEcsWinHttpClient::WinhttpStatusCallbackSetup(this);
  v17 = *((_DWORD *)this + 99);
  v18 = CEcsWinHttpClient::GetRequestHandle(this);
  if ( !WinHttpSetTimeouts(v18, 60000, 60000, v17, v17) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v23) = 969;
    LODWORD(hConnect) = LastFailureAsHRESULT;
    throw (long *)&hConnect;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v23) = 969;
  std::wstring::~wstring((__int64)v30);
  std::wstring::~wstring((__int64)v31);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x18006ef98  push    rbp
0x18006ef9a  push    rbx
0x18006ef9b  push    rsi
0x18006ef9c  push    rdi
0x18006ef9d  push    r14
0x18006ef9f  lea     rbp, [rsp-2Fh]
0x18006efa4  sub     rsp, 0D0h
0x18006efab  mov     rax, cs:__security_cookie
0x18006efb2  xor     rax, rsp
0x18006efb5  mov     [rbp+4Fh+var_28], rax
0x18006efb9  mov     rsi, r8
0x18006efbc  mov     rbx, rdx
0x18006efbf  mov     rdi, rcx
0x18006efc2  lea     rcx, WPP_GLOBAL_Control
0x18006efc9  mov     rax, cs:WPP_GLOBAL_Control
0x18006efd0  cmp     rax, rcx
0x18006efd3  jz      short loc_18006EFFD
0x18006efd5  test    byte ptr [rax+44h], 8
0x18006efd9  jz      short loc_18006EFFD
0x18006efdb  cmp     byte ptr [rax+41h], 6
0x18006efdf  jb      short loc_18006EFFD
0x18006efe1  mov     edx, 1Dh
0x18006efe6  lea     r8, WPP_13baba31ff4d3f580777c125170b76f8_Traceguids
0x18006efed  mov     rcx, [rax+38h]
0x18006eff1  call    WPP_SF_
0x18006eff6  mov     rax, cs:WPP_GLOBAL_Control
0x18006effd  xor     r14d, r14d
0x18006f000  test    byte ptr [rax+44h], 8
0x18006f004  jz      short loc_18006F00E
0x18006f006  cmp     byte ptr [rax+41h], 6
0x18006f00a  mov     cl, 1
0x18006f00c  jnb     short loc_18006F011
0x18006f00e  mov     cl, r14b
0x18006f011  mov     [rbp+4Fh+var_A0], r14d
0x18006f015  mov     [rbp+4Fh+var_9C], 389h
0x18006f01c  mov     [rbp+4Fh+var_98], cl
0x18006f01f  lea     rax, aCecswinhttpcli_22; "CEcsWinHttpClient::OpenRequest"
0x18006f026  mov     [rbp+4Fh+var_90], rax
0x18006f02a  mov     [rbp+4Fh+var_88], r14
0x18006f02e  lea     rcx, [rbp+4Fh+var_48]
0x18006f032  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006f037  nop
0x18006f038  lea     rcx, [rbp+4Fh+var_68]
0x18006f03c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006f041  nop
0x18006f042  mov     word ptr [rbp+4Fh+pExceptionObject+4], r14w
0x18006f047  mov     byte ptr [rbp+4Fh+pExceptionObject], r14b
0x18006f04b  cmp     [rdi+20h], r14
0x18006f04f  jz      short loc_18006F06E
0x18006f051  mov     rax, [rdi]
0x18006f054  mov     rcx, rdi
0x18006f057  mov     rax, [rax+68h]
0x18006f05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f060  mov     [rdi+143h], r14b
0x18006f067  mov     [rdi+144h], r14d
0x18006f06e  lea     rax, [rbp+4Fh+pExceptionObject]
0x18006f072  mov     [rsp+0F0h+pwszReferrer], rax; pExceptionObject
0x18006f077  lea     r9, [rbp+4Fh+pExceptionObject+4]
0x18006f07b  lea     r8, [rbp+4Fh+var_68]
0x18006f07f  lea     rdx, [rbp+4Fh+var_48]
0x18006f083  mov     rcx, rbx; pwszUrl
0x18006f086  call    ?GetUrlParts@CEcsWinHttpClient@@SAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1PEAGPEA_N@Z; CEcsWinHttpClient::GetUrlParts(ushort const *,std::wstring &,std::wstring &,ushort *,bool *)
0x18006f08b  mov     [rbp+4Fh+hConnect], r14
0x18006f08f  lea     rcx, [rbp+4Fh+var_48]
0x18006f093  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f098  mov     rdx, rax; unsigned __int16 *
0x18006f09b  lea     r9, [rbp+4Fh+hConnect]; void **
0x18006f09f  movzx   r8d, word ptr [rbp+4Fh+pExceptionObject+4]; unsigned __int16
0x18006f0a4  mov     rcx, rdi; this
0x18006f0a7  call    ?GetConnection@CEcsWinHttpClient@@AEAAXPEBGGPEAPEAX@Z; CEcsWinHttpClient::GetConnection(ushort const *,ushort,void * *)
0x18006f0ac  mov     bl, byte ptr [rbp+4Fh+pExceptionObject]
0x18006f0af  mov     al, bl
0x18006f0b1  neg     al
0x18006f0b3  sbb     ecx, ecx
0x18006f0b5  and     ecx, 800000h
0x18006f0bb  add     ecx, 100h
0x18006f0c1  mov     [rbp+4Fh+Buffer], ecx
0x18006f0c4  lea     rdx, [rdi+8]
0x18006f0c8  lea     rcx, [rbp+4Fh+SRWLock]
0x18006f0cc  call    ??0?$CEcsExclusiveLock@VCEcsSrwLock@@@@QEAA@AEAVCEcsSrwLock@@_N@Z; CEcsExclusiveLock<CEcsSrwLock>::CEcsExclusiveLock<CEcsSrwLock>(CEcsSrwLock &,bool)
0x18006f0d1  nop
0x18006f0d2  mov     r9d, [rbp+4Fh+Buffer]
0x18006f0d6  lea     rcx, [rbp+4Fh+var_68]
0x18006f0da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f0df  mov     r8, rax; pwszObjectName
0x18006f0e2  mov     [rsp+0F0h+dwFlags], r9d; dwFlags
0x18006f0e7  mov     [rsp+0F0h+ppwszAcceptTypes], r14; ppwszAcceptTypes
0x18006f0ec  mov     [rsp+0F0h+pwszReferrer], r14; pwszReferrer
0x18006f0f1  xor     r9d, r9d; pwszVersion
0x18006f0f4  mov     rdx, rsi; pwszVerb
0x18006f0f7  mov     rcx, [rbp+4Fh+hConnect]; hConnect
0x18006f0fb  call    cs:__imp_WinHttpOpenRequest
0x18006f101  mov     [rdi+20h], rax
0x18006f105  mov     ecx, [rbp+4Fh+var_A0]
0x18006f108  mov     [rbp+4Fh+var_A0], ecx
0x18006f10b  test    rax, rax
0x18006f10e  jnz     short loc_18006F135
0x18006f110  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006f115  mov     [rbp+4Fh+var_A0], eax
0x18006f118  mov     ecx, 3AFh
0x18006f11d  mov     word ptr [rbp+4Fh+var_9C+2], cx
0x18006f121  mov     dword ptr [rbp+4Fh+pExceptionObject+4], eax
0x18006f124  lea     rdx, _TI1J; pThrowInfo
0x18006f12b  lea     rcx, [rbp+4Fh+pExceptionObject+4]; pExceptionObject
0x18006f12f  call    _CxxThrowException_0
0x18006f135  mov     [rbp+4Fh+var_A0], r14d
0x18006f139  mov     ecx, 3AFh
0x18006f13e  mov     word ptr [rbp+4Fh+var_9C], cx
0x18006f142  cmp     [rbp+4Fh+var_70], r14b
0x18006f146  jz      short loc_18006F156
0x18006f148  mov     rcx, [rbp+4Fh+SRWLock]; SRWLock
0x18006f14c  call    cs:__imp_ReleaseSRWLockExclusive
0x18006f152  mov     [rbp+4Fh+var_70], r14b
0x18006f156  mov     [rbp+4Fh+Buffer], 1
0x18006f15d  mov     eax, [rbp+4Fh+var_A0]
0x18006f160  mov     [rbp+4Fh+var_A0], eax
0x18006f163  mov     rcx, rdi; this
0x18006f166  call    ?GetRequestHandle@CEcsWinHttpClient@@AEAAPEAXXZ; CEcsWinHttpClient::GetRequestHandle(void)
0x18006f16b  mov     rcx, rax; hInternet
0x18006f16e  mov     esi, 4
0x18006f173  mov     r9d, esi; dwBufferLength
0x18006f176  lea     r8, [rbp+4Fh+Buffer]; lpBuffer
0x18006f17a  lea     edx, [rsi+49h]; dwOption
0x18006f17d  call    cs:__imp_WinHttpSetOption
0x18006f183  test    eax, eax
0x18006f185  jnz     short loc_18006F1AC
0x18006f187  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006f18c  mov     [rbp+4Fh+var_A0], eax
0x18006f18f  mov     ecx, 3B9h
0x18006f194  mov     word ptr [rbp+4Fh+var_9C+2], cx
0x18006f198  mov     dword ptr [rbp+4Fh+pExceptionObject+4], eax
0x18006f19b  lea     rdx, _TI1J; pThrowInfo
0x18006f1a2  lea     rcx, [rbp+4Fh+pExceptionObject+4]; pExceptionObject
0x18006f1a6  call    _CxxThrowException_0
0x18006f1ac  mov     [rbp+4Fh+var_A0], r14d
0x18006f1b0  mov     ecx, 3B9h
0x18006f1b5  mov     word ptr [rbp+4Fh+var_9C], cx
0x18006f1b9  test    bl, bl
0x18006f1bb  jz      short loc_18006F221
0x18006f1bd  cmp     [rbp+4Fh+arg_20], r14b
0x18006f1c1  jnz     short loc_18006F221
0x18006f1c3  mov     dword ptr [rbp+4Fh+pExceptionObject+4], 1
0x18006f1ca  mov     [rbp+4Fh+var_A0], r14d
0x18006f1ce  mov     rcx, rdi; this
0x18006f1d1  call    ?GetRequestHandle@CEcsWinHttpClient@@AEAAPEAXXZ; CEcsWinHttpClient::GetRequestHandle(void)
0x18006f1d6  mov     rcx, rax; hInternet
0x18006f1d9  mov     r9d, esi; dwBufferLength
0x18006f1dc  lea     r8, [rbp+4Fh+pExceptionObject+4]; lpBuffer
0x18006f1e0  mov     edx, 4Fh ; 'O'; dwOption
0x18006f1e5  call    cs:__imp_WinHttpSetOption
0x18006f1eb  test    eax, eax
0x18006f1ed  jnz     short loc_18006F214
0x18006f1ef  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006f1f4  mov     [rbp+4Fh+var_A0], eax
0x18006f1f7  mov     ecx, 3C2h
0x18006f1fc  mov     word ptr [rbp+4Fh+var_9C+2], cx
0x18006f200  mov     dword ptr [rbp+4Fh+hConnect], eax
0x18006f203  lea     rdx, _TI1J; pThrowInfo
0x18006f20a  lea     rcx, [rbp+4Fh+hConnect]; pExceptionObject
0x18006f20e  call    _CxxThrowException_0
0x18006f214  mov     [rbp+4Fh+var_A0], r14d
0x18006f218  mov     ecx, 3C2h
0x18006f21d  mov     word ptr [rbp+4Fh+var_9C], cx
0x18006f221  mov     rcx, rdi; this
0x18006f224  call    ?WinhttpStatusCallbackSetup@CEcsWinHttpClient@@AEAAXXZ; CEcsWinHttpClient::WinhttpStatusCallbackSetup(void)
0x18006f229  mov     eax, [rbp+4Fh+var_A0]
0x18006f22c  mov     [rbp+4Fh+var_A0], eax
0x18006f22f  mov     ebx, [rdi+18Ch]
0x18006f235  mov     rcx, rdi; this
0x18006f238  call    ?GetRequestHandle@CEcsWinHttpClient@@AEAAPEAXXZ; CEcsWinHttpClient::GetRequestHandle(void)
0x18006f23d  mov     dword ptr [rsp+0F0h+pwszReferrer], ebx; nReceiveTimeout
0x18006f241  mov     r9d, ebx; nSendTimeout
0x18006f244  mov     edx, 0EA60h; nResolveTimeout
0x18006f249  mov     r8d, edx; nConnectTimeout
0x18006f24c  mov     rcx, rax; hInternet
0x18006f24f  call    cs:__imp_WinHttpSetTimeouts
0x18006f255  test    eax, eax
0x18006f257  jnz     short loc_18006F27E
0x18006f259  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006f25e  mov     [rbp+4Fh+var_A0], eax
0x18006f261  mov     ecx, 3C9h
0x18006f266  mov     word ptr [rbp+4Fh+var_9C+2], cx
0x18006f26a  mov     dword ptr [rbp+4Fh+hConnect], eax
0x18006f26d  lea     rdx, _TI1J; pThrowInfo
0x18006f274  lea     rcx, [rbp+4Fh+hConnect]; pExceptionObject
0x18006f278  call    _CxxThrowException_0
0x18006f27e  mov     [rbp+4Fh+var_A0], r14d
0x18006f282  mov     ecx, 3C9h
0x18006f287  mov     word ptr [rbp+4Fh+var_9C], cx
0x18006f28b  lea     rcx, [rbp+4Fh+var_68]
0x18006f28f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006f294  nop
0x18006f295  lea     rcx, [rbp+4Fh+var_48]
0x18006f299  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006f29e  nop
0x18006f29f  lea     rcx, [rbp+4Fh+var_A0]; this
0x18006f2a3  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18006f2a8  mov     rcx, [rbp+4Fh+var_28]
0x18006f2ac  xor     rcx, rsp; StackCookie
0x18006f2af  call    __security_check_cookie
0x18006f2b4  add     rsp, 0D0h
0x18006f2bb  pop     r14
0x18006f2bd  pop     rdi
0x18006f2be  pop     rsi
0x18006f2bf  pop     rbx
0x18006f2c0  pop     rbp
0x18006f2c1  retn
```
