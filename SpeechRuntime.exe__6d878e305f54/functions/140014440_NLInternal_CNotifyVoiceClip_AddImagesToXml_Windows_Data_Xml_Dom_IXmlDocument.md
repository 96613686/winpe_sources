# NLInternal::CNotifyVoiceClip::AddImagesToXml(Windows::Data::Xml::Dom::IXmlDocument *)

- ea: `0x140014440`
- end: `0x140014598`
- name: `?AddImagesToXml@CNotifyVoiceClip@NLInternal@@CAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct Windows::Data::Xml::Dom::IXmlDocument *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017ad0`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x140014440`
- `0x1400145a0`

## string_xrefs

- `0x140014471`: `%SystemRoot%\System32\Speech_OneCore\Common\toast-hero-image.png`
- `0x1400144df`: `%SystemRoot%\System32\Speech_OneCore\Common\privacy-icon.png`

## pseudocode

```c
__int64 __fastcall NLInternal::CNotifyVoiceClip::AddImagesToXml(struct Windows::Data::Xml::Dom::IXmlDocument *a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  unsigned __int16 v5[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v6; // [rsp+30h] [rbp-D0h]
  __int128 v7; // [rsp+40h] [rbp-C0h]
  __int128 v8; // [rsp+50h] [rbp-B0h]
  __int128 v9; // [rsp+60h] [rbp-A0h]
  __int128 v10; // [rsp+70h] [rbp-90h]
  __int128 v11; // [rsp+80h] [rbp-80h]
  __int128 v12; // [rsp+90h] [rbp-70h]
  __int16 v13; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v14[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v15; // [rsp+C0h] [rbp-40h]
  __int128 v16; // [rsp+D0h] [rbp-30h]
  __int128 v17; // [rsp+E0h] [rbp-20h]
  __int128 v18; // [rsp+F0h] [rbp-10h]
  __int128 v19; // [rsp+100h] [rbp+0h]
  _OWORD v20[2]; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v6 = *(_OWORD *)L"oot%\\System32\\Speech_OneCore\\Common\\toast-hero-image.png";
  v13 = *(_WORD *)L"";
  *(_OWORD *)v5 = *(_OWORD *)L"%SystemRoot%\\System32\\Speech_OneCore\\Common\\toast-hero-image.png";
  v8 = *(_OWORD *)L"eech_OneCore\\Common\\toast-hero-image.png";
  v7 = *(_OWORD *)L"tem32\\Speech_OneCore\\Common\\toast-hero-image.png";
  v10 = *(_OWORD *)L"mon\\toast-hero-image.png";
  v9 = *(_OWORD *)L"Core\\Common\\toast-hero-image.png";
  v12 = *(_OWORD *)L"mage.png";
  v11 = *(_OWORD *)L"t-hero-image.png";
  v15 = *(_OWORD *)L"oot%\\System32\\Speech_OneCore\\Common\\privacy-icon.png";
  *(_OWORD *)v14 = *(_OWORD *)L"%SystemRoot%\\System32\\Speech_OneCore\\Common\\privacy-icon.png";
  v17 = *(_OWORD *)L"eech_OneCore\\Common\\privacy-icon.png";
  v16 = *(_OWORD *)L"tem32\\Speech_OneCore\\Common\\privacy-icon.png";
  v19 = *(_OWORD *)L"mon\\privacy-icon.png";
  v18 = *(_OWORD *)L"Core\\Common\\privacy-icon.png";
  v20[0] = *(_OWORD *)L"acy-icon.png";
  *(_OWORD *)((char *)v20 + 10) = *(_OWORD *)L"con.png";
  v2 = NLInternal::CNotifyVoiceClip::AddOneImageToXml(a1, 0, v5);
  if ( v2 < 0 )
  {
    v3 = 241;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
      (const char *)(unsigned int)v2,
      *(int *)v5);
    return (unsigned int)v2;
  }
  v2 = NLInternal::CNotifyVoiceClip::AddOneImageToXml(a1, 1u, v14);
  if ( v2 < 0 )
  {
    v3 = 242;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x140014440  mov     [rsp-8+arg_8], rbx
0x140014445  mov     [rsp-8+arg_10], rdi
0x14001444a  push    rbp
0x14001444b  lea     rbp, [rsp-40h]
0x140014450  sub     rsp, 140h
0x140014457  mov     rax, cs:__security_cookie
0x14001445e  xor     rax, rsp
0x140014461  mov     [rbp+40h+var_10], rax
0x140014465  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+10h; "oot%\\System32\\Speech_OneCore\\Common"...
0x14001446c  lea     r8, [rsp+140h+var_120]; unsigned __int16 *
0x140014471  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0; "%SystemRoot%\\System32\\Speech_OneCore"...
0x140014478  xor     edx, edx; int
0x14001447a  movzx   eax, word ptr cs:aSystemrootSyst_0+80h; ""
0x140014481  mov     rdi, rcx
0x140014484  movups  [rsp+140h+var_110], xmm1
0x140014489  mov     [rbp+40h+var_A0], ax
0x14001448d  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+30h; "eech_OneCore\\Common\\toast-hero-image."...
0x140014494  movups  xmmword ptr [rsp+140h+var_120], xmm0; int
0x140014499  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0+20h; "tem32\\Speech_OneCore\\Common\\toast-he"...
0x1400144a0  movups  [rsp+140h+var_F0], xmm1
0x1400144a5  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+50h; "mon\\toast-hero-image.png"
0x1400144ac  movups  [rsp+140h+var_100], xmm0
0x1400144b1  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0+40h; "Core\\Common\\toast-hero-image.png"
0x1400144b8  movups  [rsp+140h+var_D0], xmm1
0x1400144bd  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+70h; "mage.png"
0x1400144c4  movups  [rsp+140h+var_E0], xmm0
0x1400144c9  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0+60h; "t-hero-image.png"
0x1400144d0  movups  [rbp+40h+var_B0], xmm1
0x1400144d4  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot%\\System32\\Speech_OneCore\\Common"...
0x1400144db  movups  [rbp+40h+var_C0], xmm0
0x1400144df  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "%SystemRoot%\\System32\\Speech_OneCore"...
0x1400144e6  movaps  [rbp+40h+var_80], xmm1
0x1400144ea  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "eech_OneCore\\Common\\privacy-icon.png"
0x1400144f1  movaps  xmmword ptr [rbp+40h+var_90], xmm0
0x1400144f5  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "tem32\\Speech_OneCore\\Common\\privacy-"...
0x1400144fc  movaps  [rbp+40h+var_60], xmm1
0x140014500  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+50h; "mon\\privacy-icon.png"
0x140014507  movaps  [rbp+40h+var_70], xmm0
0x14001450b  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+40h; "Core\\Common\\privacy-icon.png"
0x140014512  movaps  [rbp+40h+var_40], xmm1
0x140014516  movups  xmm1, xmmword ptr cs:aSystemrootSyst+6Ah; "con.png"
0x14001451d  movaps  [rbp+40h+var_50], xmm0
0x140014521  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+60h; "acy-icon.png"
0x140014528  movaps  xmmword ptr [rbp+40h+var_30], xmm0
0x14001452c  movups  xmmword ptr [rbp+40h+var_30+0Ah], xmm1
0x140014530  call    ?AddOneImageToXml@CNotifyVoiceClip@NLInternal@@CAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@HPEBG@Z; NLInternal::CNotifyVoiceClip::AddOneImageToXml(Windows::Data::Xml::Dom::IXmlDocument *,int,ushort const *)
0x140014535  mov     ebx, eax
0x140014537  test    eax, eax
0x140014539  jns     short loc_140014557
0x14001453b  mov     edx, 0F1h; void *
0x140014540  mov     rcx, [rbp+48h]; this
0x140014544  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001454b  mov     r9d, ebx; char *
0x14001454e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014553  mov     eax, ebx
0x140014555  jmp     short loc_140014577
0x140014557  lea     r8, [rbp+40h+var_90]; unsigned __int16 *
0x14001455b  mov     edx, 1; int
0x140014560  mov     rcx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x140014563  call    ?AddOneImageToXml@CNotifyVoiceClip@NLInternal@@CAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@HPEBG@Z; NLInternal::CNotifyVoiceClip::AddOneImageToXml(Windows::Data::Xml::Dom::IXmlDocument *,int,ushort const *)
0x140014568  mov     ebx, eax
0x14001456a  test    eax, eax
0x14001456c  jns     short loc_140014575
0x14001456e  mov     edx, 0F2h
0x140014573  jmp     short loc_140014540
0x140014575  xor     eax, eax
0x140014577  mov     rcx, [rbp+40h+var_10]
0x14001457b  xor     rcx, rsp; StackCookie
0x14001457e  call    __security_check_cookie
0x140014583  lea     r11, [rsp+140h+var_s0]
0x14001458b  mov     rbx, [r11+18h]
0x14001458f  mov     rdi, [r11+20h]
0x140014593  mov     rsp, r11
0x140014596  pop     rbp
0x140014597  retn
```
