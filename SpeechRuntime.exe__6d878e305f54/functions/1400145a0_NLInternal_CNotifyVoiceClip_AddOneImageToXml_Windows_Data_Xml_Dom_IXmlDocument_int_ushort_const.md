# NLInternal::CNotifyVoiceClip::AddOneImageToXml(Windows::Data::Xml::Dom::IXmlDocument *,int,ushort const *)

- ea: `0x1400145a0`
- end: `0x1400146c4`
- name: `?AddOneImageToXml@CNotifyVoiceClip@NLInternal@@CAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@HPEBG@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct Windows::Data::Xml::Dom::IXmlDocument *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014440`

## callees

- `0x140002d30`
- `0x140003848`
- `0x14000e010`
- `0x14000e030`
- `0x1400145a0`
- `0x140017d74`
- `0x14002f370`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x140014656`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x140014656`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400145f2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400145f2`

## pseudocode

```c
__int64 __fastcall NLInternal::CNotifyVoiceClip::AddOneImageToXml(
        struct Windows::Data::Xml::Dom::IXmlDocument *a1,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  const char *v6; // r9
  const unsigned __int16 *v8; // rdx
  HRESULT v9; // ebx
  const unsigned __int16 *v10; // r9
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-12A8h]
  DWORD pcchUrl[4]; // [rsp+30h] [rbp-1298h] BYREF
  WCHAR Dst; // [rsp+40h] [rbp-1288h] BYREF
  _BYTE v15[526]; // [rsp+42h] [rbp-1286h] BYREF
  WCHAR pszUrl; // [rsp+250h] [rbp-1078h] BYREF
  _BYTE v17[4174]; // [rsp+252h] [rbp-1076h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+12C8h] [rbp+0h]

  Dst = 0;
  memset_0(v15, 0, 0x206u);
  if ( !ExpandEnvironmentStringsW(a3, &Dst, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF9,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
             v6);
  pszUrl = 0;
  memset_0(v17, 0, 0x1046u);
  pcchUrl[0] = 2084;
  v9 = UrlCreateFromPathW(&Dst, &pszUrl, pcchUrl, 0);
  if ( v9 < 0 )
  {
    v11 = 252;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
      (const char *)(unsigned int)v9,
      v12);
    return (unsigned int)v9;
  }
  v9 = NLInternal::CNotifyVoiceClip::SetXmlElementAttribute(a1, v8, a2, v10, &pszUrl);
  if ( v9 < 0 )
  {
    v11 = 253;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1400145a0  push    rbx
0x1400145a2  push    rsi
0x1400145a3  push    rdi
0x1400145a4  mov     eax, 12B0h
0x1400145a9  call    _alloca_probe
0x1400145ae  sub     rsp, rax
0x1400145b1  mov     rax, cs:__security_cookie
0x1400145b8  xor     rax, rsp
0x1400145bb  mov     [rsp+12C8h+var_28], rax
0x1400145c3  mov     rbx, r8
0x1400145c6  mov     esi, edx
0x1400145c8  mov     rdi, rcx
0x1400145cb  xor     eax, eax
0x1400145cd  xor     edx, edx; Val
0x1400145cf  mov     [rsp+12C8h+Dst], ax
0x1400145d4  mov     r8d, 206h; Size
0x1400145da  lea     rcx, [rsp+12C8h+var_1286]; void *
0x1400145df  call    memset_0
0x1400145e4  mov     r8d, 104h; nSize
0x1400145ea  lea     rdx, [rsp+12C8h+Dst]; lpDst
0x1400145ef  mov     rcx, rbx; lpSrc
0x1400145f2  call    cs:__imp_ExpandEnvironmentStringsW
0x1400145f8  test    eax, eax
0x1400145fa  jnz     short loc_14001461A
0x1400145fc  mov     rcx, [rsp+12C8h]; this
0x140014604  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001460b  mov     edx, 0F9h; void *
0x140014610  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140014615  jmp     loc_1400146A9
0x14001461a  xor     eax, eax
0x14001461c  lea     rcx, [rsp+12C8h+var_1076]; void *
0x140014624  xor     edx, edx; Val
0x140014626  mov     [rsp+12C8h+pszUrl], ax
0x14001462e  mov     r8d, 1046h; Size
0x140014634  call    memset_0
0x140014639  xor     r9d, r9d; dwFlags
0x14001463c  mov     [rsp+12C8h+pcchUrl], 824h
0x140014644  lea     r8, [rsp+12C8h+pcchUrl]; pcchUrl
0x140014649  lea     rdx, [rsp+12C8h+pszUrl]; pszUrl
0x140014651  lea     rcx, [rsp+12C8h+Dst]; pszPath
0x140014656  call    cs:__imp_UrlCreateFromPathW
0x14001465c  mov     ebx, eax
0x14001465e  test    eax, eax
0x140014660  jns     short loc_140014682
0x140014662  mov     edx, 0FCh; void *
0x140014667  mov     rcx, [rsp+12C8h]; this
0x14001466f  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140014676  mov     r9d, ebx; char *
0x140014679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001467e  mov     eax, ebx
0x140014680  jmp     short loc_1400146A9
0x140014682  lea     rax, [rsp+12C8h+pszUrl]
0x14001468a  mov     r8d, esi; unsigned int
0x14001468d  mov     rcx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x140014690  mov     qword ptr [rsp+12C8h+var_12A8], rax; unsigned __int16 *
0x140014695  call    ?SetXmlElementAttribute@CNotifyVoiceClip@NLInternal@@CAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBGI11@Z; NLInternal::CNotifyVoiceClip::SetXmlElementAttribute(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,uint,ushort const *,ushort const *)
0x14001469a  mov     ebx, eax
0x14001469c  test    eax, eax
0x14001469e  jns     short loc_1400146A7
0x1400146a0  mov     edx, 0FDh
0x1400146a5  jmp     short loc_140014667
0x1400146a7  xor     eax, eax
0x1400146a9  mov     rcx, [rsp+12C8h+var_28]
0x1400146b1  xor     rcx, rsp; StackCookie
0x1400146b4  call    __security_check_cookie
0x1400146b9  add     rsp, 12B0h
0x1400146c0  pop     rdi
0x1400146c1  pop     rsi
0x1400146c2  pop     rbx
0x1400146c3  retn
```
