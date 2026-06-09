# uus::Session::Session(ushort const *)

- ea: `0x18000865c`
- end: `0x18000878b`
- name: `??0Session@uus@@QEAA@PEBG@Z`
- size: `303`
- prototype: `uus::Session *__fastcall(uus::Session *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000aa84`

## callees

- `0x180002200`
- `0x180006cfc`
- `0x180006f28`
- `0x180007940`
- `0x18000865c`
- `0x180008f20`
- `0x180009168`
- `0x180009b34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008709`

## pseudocode

```c
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const unsigned __int16 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // r8
  LPVOID pv[6]; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp-19h] BYREF
  char v8; // [rsp+70h] [rbp+7h]
  __int128 v9; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v10; // [rsp+88h] [rbp+1Fh]
  __int64 v11; // [rsp+90h] [rbp+27h]
  _OWORD v12[2]; // [rsp+98h] [rbp+2Fh] BYREF

  pv[0] = this;
  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  pv[1] = (LPVOID)32;
  pv[2] = (LPVOID)3;
  pv[3] = (LPVOID)0x180000000LL;
  pv[4] = (LPVOID)a2;
  v12[0] = 0;
  v12[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v12[0]) = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(pv);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv[0] + v4) );
  v9 = 0;
  v10 = 0;
  v11 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v9, pv[0]);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  uus::Utility::FindFileInArchFolder(v7, &v9);
  std::wstring::~wstring(&v9);
  if ( v8 )
  {
    std::wstring::operator=(v12, v7);
    if ( v8 )
      std::wstring::~wstring(v7);
    v3 = uus::Utility::GetBrainSession<uus::Brain3>((char *)v12);
  }
  std::wstring::~wstring(v12);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x18000865c  mov     [rsp-8+arg_10], rbx
0x180008661  mov     [rsp-8+arg_18], rdi
0x180008666  push    rbp
0x180008667  lea     rbp, [rsp-57h]
0x18000866c  sub     rsp, 0C0h
0x180008673  mov     rax, cs:__security_cookie
0x18000867a  xor     rax, rsp
0x18000867d  mov     [rbp+57h+var_8], rax
0x180008681  mov     rdi, rcx
0x180008684  mov     [rbp+57h+pv], rcx
0x180008688  xor     ebx, ebx
0x18000868a  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x180008691  mov     [rcx], rax
0x180008694  mov     [rbp+57h+var_98], 20h ; ' '
0x18000869c  mov     [rbp+57h+var_90], 3
0x1800086a4  lea     rax, cs:180000000h
0x1800086ab  mov     [rbp+57h+var_88], rax
0x1800086af  mov     [rbp+57h+var_80], rdx
0x1800086b3  xorps   xmm0, xmm0
0x1800086b6  movups  [rbp+57h+var_28], xmm0
0x1800086ba  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800086c2  movdqu  [rbp+57h+var_18], xmm1
0x1800086c7  mov     word ptr [rbp+57h+var_28], bx
0x1800086cb  lea     rcx, [rbp+57h+pv]
0x1800086cf  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x1800086d4  nop
0x1800086d5  mov     rdx, [rbp+57h+pv]
0x1800086d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800086dd  inc     r8
0x1800086e0  cmp     [rdx+r8*2], bx
0x1800086e5  jnz     short loc_1800086DD
0x1800086e7  xorps   xmm0, xmm0
0x1800086ea  movups  [rbp+57h+var_48], xmm0
0x1800086ee  mov     [rbp+57h+var_38], rbx
0x1800086f2  mov     [rbp+57h+var_30], rbx
0x1800086f6  lea     rcx, [rbp+57h+var_48]
0x1800086fa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800086ff  nop
0x180008700  mov     rcx, [rbp+57h+pv]; pv
0x180008704  test    rcx, rcx
0x180008707  jz      short loc_180008710
0x180008709  call    cs:__imp_CoTaskMemFree
0x18000870f  nop
0x180008710  lea     rdx, [rbp+57h+var_48]
0x180008714  lea     rcx, [rbp+57h+var_70]
0x180008718  call    ?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)
0x18000871d  nop
0x18000871e  lea     rcx, [rbp+57h+var_48]
0x180008722  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008727  cmp     [rbp+57h+var_50], bl
0x18000872a  jnz     short loc_18000872E
0x18000872c  jmp     short loc_18000875A
0x18000872e  lea     rdx, [rbp+57h+var_70]
0x180008732  lea     rcx, [rbp+57h+var_28]
0x180008736  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000873b  nop
0x18000873c  cmp     [rbp+57h+var_50], bl
0x18000873f  jz      short loc_18000874A
0x180008741  lea     rcx, [rbp+57h+var_70]
0x180008745  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000874a  lea     rdx, [rbp+57h+var_98]
0x18000874e  lea     rcx, [rbp+57h+var_28]
0x180008752  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x180008757  mov     rbx, rax
0x18000875a  lea     rcx, [rbp+57h+var_28]
0x18000875e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008763  mov     [rdi+8], rbx
0x180008767  mov     rax, rdi
0x18000876a  mov     rcx, [rbp+57h+var_8]
0x18000876e  xor     rcx, rsp; StackCookie
0x180008771  call    __security_check_cookie
0x180008776  lea     r11, [rsp+0C0h+var_s0]
0x18000877e  mov     rbx, [r11+20h]
0x180008782  mov     rdi, [r11+28h]
0x180008786  mov     rsp, r11
0x180008789  pop     rbp
0x18000878a  retn
```
