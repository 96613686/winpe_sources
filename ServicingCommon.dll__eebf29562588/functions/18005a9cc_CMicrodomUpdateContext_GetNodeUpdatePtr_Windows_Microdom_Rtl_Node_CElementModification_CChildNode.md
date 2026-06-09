# CMicrodomUpdateContext::GetNodeUpdatePtr(Windows::Microdom::Rtl::Node,CElementModification *,CChildNode * &)

- ea: `0x18005a9cc`
- end: `0x18005abdc`
- name: `?GetNodeUpdatePtr@CMicrodomUpdateContext@@QEAAJUNode@Rtl@Microdom@Windows@@PEAVCElementModification@@AEAPEAVCChildNode@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct Node, struct CElementModification *, struct CChildNode **)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180059960`
- `0x180059bb8`
- `0x18005abe4`
- `0x18005c6f0`

## callees

- `0x18001f4ac`
- `0x18001fd10`
- `0x1800293a0`
- `0x180059f50`
- `0x18005a094`
- `0x18005a228`
- `0x18005a36c`
- `0x18005a9cc`
- `0x1800a0020`

## string_xrefs

- `0x18005aa1b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005aae5`: `onecore\base\xml\udom_modify.cpp`
- `0x18005aa32`: `CMicrodomUpdateContext::GetNodeUpdatePtr`
- `0x18005aafc`: `CMicrodomUpdateContext::GetNodeUpdatePtr`
- `0x18005aa3d`: `ulIndex < UpdateChildNodes.Size()`

## pseudocode

```c
__int64 __fastcall CMicrodomUpdateContext::GetNodeUpdatePtr(
        CMicrodomUpdateContext *this,
        struct Node a2,
        struct CElementModification *a3,
        struct CChildNode **a4)
{
  unsigned __int64 AddRef_low; // rdi
  __int64 v7; // rcx
  __int128 *v9; // rdx
  __int64 result; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int128 v13; // xmm0
  __int64 (__fastcall *v14)(__int64 *, __int128 *, _QWORD *, _QWORD *); // rax
  struct CChildNode *v15; // rcx
  bool v16; // zf
  struct CChildNode *v17; // [rsp+30h] [rbp-49h] BYREF
  int v18; // [rsp+38h] [rbp-41h] BYREF
  __int128 v19; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+50h] [rbp-29h]
  const char *v21; // [rsp+58h] [rbp-21h]
  _QWORD v22[2]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-9h] BYREF
  int v24; // [rsp+80h] [rbp+7h] BYREF
  __int128 v25; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+98h] [rbp+1Fh]
  const char *v27; // [rsp+A0h] [rbp+27h]

  AddRef_low = LODWORD(a2.lpVtbl->AddRef);
  *a4 = 0;
  v7 = *((_QWORD *)this + 5);
  v24 = 0;
  if ( AddRef_low >= (*((_QWORD *)this + 6) - v7) >> 3 )
  {
    v26 = 1341;
    *(_QWORD *)&v25 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = &v25;
    *((_QWORD *)&v25 + 1) = "CMicrodomUpdateContext::GetNodeUpdatePtr";
    v27 = "ulIndex < UpdateChildNodes.Size()";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v24,
             v9);
  }
  if ( *(_QWORD *)(v7 + 8 * AddRef_low) )
    goto LABEL_21;
  v11 = *(__int64 **)this;
  v17 = 0;
  v26 = 0;
  v25 = 0;
  v12 = *v11;
  v13 = *(_OWORD *)&a2.lpVtbl->QueryInterface;
  v22[0] = &v25;
  v23[0] = &v18;
  v14 = *(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, _QWORD *))(v12 + 152);
  v22[1] = 1;
  v23[1] = 1;
  v18 = 8200;
  v19 = v13;
  result = v14(v11, &v19, v23, v22);
  if ( (int)result < 0 )
    return result;
  switch ( WORD4(v25) )
  {
    case 1u:
      result = CMicrodomUpdateContext::CreateVirtualElement(this, &v17);
      if ( (int)result < 0 )
        return result;
      v15 = v17;
      v16 = *((_QWORD *)v17 + 5) == 0;
      break;
    case 2u:
      result = CMicrodomUpdateContext::CreateVirtualAttribute(this, &v17);
      if ( (int)result < 0 )
        return result;
      v15 = v17;
      v16 = *((_QWORD *)v17 + 4) == 0;
      break;
    case 3u:
      result = CMicrodomUpdateContext::CreateVirtualTextual(this, &v17);
      if ( (int)result < 0 )
        return result;
      v15 = v17;
      v16 = *((_QWORD *)v17 + 3) == 0;
      break;
    case 8u:
      result = CMicrodomUpdateContext::CreateVirtualComment(this, &v17);
      if ( (int)result < 0 )
        return result;
      v15 = v17;
      v16 = *((_QWORD *)v17 + 6) == 0;
      break;
    default:
      v20 = 1373;
      *(_QWORD *)&v19 = "onecore\\base\\xml\\udom_modify.cpp";
      v9 = &v19;
      *((_QWORD *)&v19 + 1) = "CMicrodomUpdateContext::GetNodeUpdatePtr";
      v21 = "false";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v24,
               v9);
  }
  if ( v16 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18005ABDBLL);
  }
  *(_QWORD *)(*((_QWORD *)this + 5) + 8 * AddRef_low) = v15;
  result = (*(__int64 (__fastcall **)(_QWORD, struct CElementModification *, _QWORD))(**((_QWORD **)v15 + 7) + 80LL))(
             *((_QWORD *)v15 + 7),
             a3,
             (unsigned int)AddRef_low);
  if ( (int)result >= 0 )
  {
LABEL_21:
    result = 0;
    *a4 = *(struct CChildNode **)(*((_QWORD *)this + 5) + 8 * AddRef_low);
  }
  return result;
}

```

## disassembly

```asm
0x18005a9cc  push    rbp
0x18005a9ce  push    rbx
0x18005a9cf  push    rsi
0x18005a9d0  push    rdi
0x18005a9d1  push    r14
0x18005a9d3  lea     rbp, [rsp-37h]
0x18005a9d8  sub     rsp, 0B0h
0x18005a9df  mov     rax, cs:__security_cookie
0x18005a9e6  xor     rax, rsp
0x18005a9e9  mov     [rbp+57h+var_28], rax
0x18005a9ed  mov     edi, [rdx+8]
0x18005a9f0  mov     rbx, rcx
0x18005a9f3  mov     qword ptr [r9], 0
0x18005a9fa  mov     rsi, r9
0x18005a9fd  mov     rcx, [rcx+28h]
0x18005aa01  mov     r14, r8
0x18005aa04  mov     [rbp+57h+var_50], 0
0x18005aa0b  mov     rax, [rbx+30h]
0x18005aa0f  sub     rax, rcx
0x18005aa12  sar     rax, 3
0x18005aa16  cmp     rdi, rax
0x18005aa19  jb      short loc_18005AA56
0x18005aa1b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005aa22  mov     [rbp+57h+var_38], 53Dh
0x18005aa2a  mov     qword ptr [rbp+57h+var_48], rax
0x18005aa2e  lea     rdx, [rbp+57h+var_48]
0x18005aa32  lea     rax, aCmicrodomupdat_3; "CMicrodomUpdateContext::GetNodeUpdatePt"...
0x18005aa39  mov     qword ptr [rbp+57h+var_48+8], rax
0x18005aa3d  lea     rax, aUlindexUpdatec; "ulIndex < UpdateChildNodes.Size()"
0x18005aa44  mov     [rbp+57h+var_30], rax
0x18005aa48  lea     rcx, [rbp+57h+var_50]
0x18005aa4c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005aa51  jmp     loc_18005ABB6
0x18005aa56  cmp     qword ptr [rcx+rdi*8], 0
0x18005aa5b  jnz     loc_18005ABA9
0x18005aa61  mov     rcx, [rbx]
0x18005aa64  lea     r8, [rbp+57h+var_48]
0x18005aa68  xor     eax, eax
0x18005aa6a  mov     [rbp+57h+var_A0], 0
0x18005aa72  xorps   xmm0, xmm0
0x18005aa75  mov     [rbp+57h+var_38], rax
0x18005aa79  movups  [rbp+57h+var_48], xmm0
0x18005aa7d  mov     rax, [rcx]
0x18005aa80  mov     r9d, 1
0x18005aa86  movaps  xmm0, xmmword ptr [rdx]
0x18005aa89  lea     rdx, [rbp+57h+var_90]
0x18005aa8d  mov     [rbp+57h+var_70], r8
0x18005aa91  lea     r8, [rbp+57h+var_98]
0x18005aa95  mov     [rbp+57h+var_60], r8
0x18005aa99  lea     r8, [rbp+57h+var_60]
0x18005aa9d  mov     rax, [rax+98h]
0x18005aaa4  mov     [rbp+57h+var_68], r9
0x18005aaa8  mov     [rbp+57h+var_58], r9
0x18005aaac  lea     r9, [rbp+57h+var_70]
0x18005aab0  mov     [rbp+57h+var_98], 2008h
0x18005aab7  movdqa  [rbp+57h+var_90], xmm0
0x18005aabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aac1  test    eax, eax
0x18005aac3  js      loc_18005ABB6
0x18005aac9  movzx   ecx, word ptr [rbp+57h+var_48+8]
0x18005aacd  sub     ecx, 1
0x18005aad0  jz      loc_18005AB6C
0x18005aad6  sub     ecx, 1
0x18005aad9  jz      short loc_18005AB51
0x18005aadb  sub     ecx, 1
0x18005aade  jz      short loc_18005AB36
0x18005aae0  cmp     ecx, 5
0x18005aae3  jz      short loc_18005AB17
0x18005aae5  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005aaec  mov     [rbp+57h+var_80], 55Dh
0x18005aaf4  mov     qword ptr [rbp+57h+var_90], rax
0x18005aaf8  lea     rdx, [rbp+57h+var_90]
0x18005aafc  lea     rax, aCmicrodomupdat_3; "CMicrodomUpdateContext::GetNodeUpdatePt"...
0x18005ab03  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005ab07  lea     rax, aFalse; "false"
0x18005ab0e  mov     [rbp+57h+var_78], rax
0x18005ab12  jmp     loc_18005AA48
0x18005ab17  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005ab1b  mov     rcx, rbx; this
0x18005ab1e  call    ?CreateVirtualComment@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualComment(CChildNode * &)
0x18005ab23  test    eax, eax
0x18005ab25  js      loc_18005ABB6
0x18005ab2b  mov     rcx, [rbp+57h+var_A0]
0x18005ab2f  cmp     qword ptr [rcx+30h], 0
0x18005ab34  jmp     short loc_18005AB85
0x18005ab36  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005ab3a  mov     rcx, rbx; this
0x18005ab3d  call    ?CreateVirtualTextual@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualTextual(CChildNode * &)
0x18005ab42  test    eax, eax
0x18005ab44  js      short loc_18005ABB6
0x18005ab46  mov     rcx, [rbp+57h+var_A0]
0x18005ab4a  cmp     qword ptr [rcx+18h], 0
0x18005ab4f  jmp     short loc_18005AB85
0x18005ab51  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005ab55  mov     rcx, rbx; this
0x18005ab58  call    ?CreateVirtualAttribute@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualAttribute(CChildNode * &)
0x18005ab5d  test    eax, eax
0x18005ab5f  js      short loc_18005ABB6
0x18005ab61  mov     rcx, [rbp+57h+var_A0]
0x18005ab65  cmp     qword ptr [rcx+20h], 0
0x18005ab6a  jmp     short loc_18005AB85
0x18005ab6c  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005ab70  mov     rcx, rbx; this
0x18005ab73  call    ?CreateVirtualElement@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualElement(CChildNode * &)
0x18005ab78  test    eax, eax
0x18005ab7a  js      short loc_18005ABB6
0x18005ab7c  mov     rcx, [rbp+57h+var_A0]
0x18005ab80  cmp     qword ptr [rcx+28h], 0
0x18005ab85  jz      short loc_18005ABD1
0x18005ab87  mov     rax, [rbx+28h]
0x18005ab8b  mov     r8d, edi
0x18005ab8e  mov     rdx, r14
0x18005ab91  mov     [rax+rdi*8], rcx
0x18005ab95  mov     rcx, [rcx+38h]
0x18005ab99  mov     rax, [rcx]
0x18005ab9c  mov     rax, [rax+50h]
0x18005aba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aba5  test    eax, eax
0x18005aba7  js      short loc_18005ABB6
0x18005aba9  mov     rax, [rbx+28h]
0x18005abad  mov     rcx, [rax+rdi*8]
0x18005abb1  xor     eax, eax
0x18005abb3  mov     [rsi], rcx
0x18005abb6  mov     rcx, [rbp+57h+var_28]
0x18005abba  xor     rcx, rsp; StackCookie
0x18005abbd  call    __security_check_cookie
0x18005abc2  add     rsp, 0B0h
0x18005abc9  pop     r14
0x18005abcb  pop     rdi
0x18005abcc  pop     rsi
0x18005abcd  pop     rbx
0x18005abce  pop     rbp
0x18005abcf  retn
0x18005abd1  mov     ecx, 0C00000E5h; int
0x18005abd6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
