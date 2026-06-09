# CMicrodomUpdateContext::CreateVirtualComment(CChildNode * &)

- ea: `0x18005a094`
- end: `0x18005a220`
- name: `?CreateVirtualComment@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct CChildNode **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005a9cc`

## callees

- `0x18001f554`
- `0x180022eb0`
- `0x1800293a0`
- `0x180058e54`
- `0x1800590b4`
- `0x18005a094`

## string_xrefs

- `0x18005a0da`: `onecore\base\xml\udom_modify.cpp`
- `0x18005a181`: `onecore\base\xml\udom_modify.cpp`
- `0x18005a0f1`: `CMicrodomUpdateContext::CreateVirtualComment`
- `0x18005a198`: `CMicrodomUpdateContext::CreateVirtualComment`
- `0x18005a1a3`: `NewChild->Comment.Allocate()`

## pseudocode

```c
__int64 __fastcall CMicrodomUpdateContext::CreateVirtualComment(CMicrodomUpdateContext *this, struct CChildNode **a2)
{
  unsigned int v2; // ebx
  __int128 *v5; // rdx
  struct CChildNode *v6; // rdi
  char *v7; // rax
  struct CChildNode **v8; // rax
  struct CChildNode *v10; // [rsp+20h] [rbp-60h] BYREF
  __int128 v11; // [rsp+28h] [rbp-58h] BYREF
  __int64 v12; // [rsp+38h] [rbp-48h]
  const char *v13; // [rsp+40h] [rbp-40h]
  _QWORD v14[4]; // [rsp+48h] [rbp-38h] BYREF
  int v15; // [rsp+68h] [rbp-18h] BYREF

  v2 = 0;
  v15 = 0;
  v10 = 0;
  *a2 = 0;
  if ( Windows::AutoNewPtr<CChildNode>::Allocate<>(&v10) )
  {
    v6 = v10;
    v7 = (char *)operator new(0x90u);
    if ( v7 )
    {
      *(_OWORD *)(v7 + 8) = 0;
      *((_QWORD *)v7 + 3) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *(_OWORD *)(v7 + 56) = 0;
      *((_QWORD *)v7 + 9) = 0;
      *((_OWORD *)v7 + 5) = 0;
      *((_QWORD *)v7 + 12) = 0;
      *((_QWORD *)v7 + 13) = 0;
      *((_QWORD *)v7 + 14) = 0;
      *((_WORD *)v7 + 60) = 0;
      *(_QWORD *)v7 = &CCommentModification::`vftable';
      *((_OWORD *)v7 + 8) = 0;
      *((_DWORD *)v7 + 34) = -1;
      v11 = 0;
      DWORD2(v11) = -1;
    }
    if ( *((_QWORD *)v6 + 6) )
      __debugbreak();
    *((_QWORD *)v6 + 6) = v7;
    if ( v7 )
    {
      *((_QWORD *)v7 + 13) = this;
      *((_QWORD *)v7 + 14) = 0;
      *((_QWORD *)v6 + 7) = v7;
      *a2 = v6;
      *((_QWORD *)v6 + 1) = *((_QWORD *)this + 2);
      *(_QWORD *)v6 = (char *)this + 8;
      v8 = (struct CChildNode **)*((_QWORD *)this + 2);
      v10 = 0;
      *v8 = v6;
      *((_QWORD *)this + 2) = v6;
      *((_QWORD *)v6 + 2) = (char *)this + 8;
      ++*((_QWORD *)this + 4);
      goto LABEL_11;
    }
    v14[2] = 1198;
    v14[0] = "onecore\\base\\xml\\udom_modify.cpp";
    v5 = (__int128 *)v14;
    v14[1] = "CMicrodomUpdateContext::CreateVirtualComment";
    v14[3] = "NewChild->Comment.Allocate()";
  }
  else
  {
    v12 = 1197;
    *(_QWORD *)&v11 = "onecore\\base\\xml\\udom_modify.cpp";
    v5 = &v11;
    *((_QWORD *)&v11 + 1) = "CMicrodomUpdateContext::CreateVirtualComment";
    v13 = "NewChild.Allocate()";
  }
  v2 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
         &v15,
         v5);
LABEL_11:
  Windows::Auto<CChildNode *>::~Auto<CChildNode *>(&v10);
  return v2;
}

```

## disassembly

```asm
0x18005a094  mov     [rsp-18h+arg_10], rbx
0x18005a099  mov     [rsp-18h+arg_18], rsi
0x18005a09e  push    rbp
0x18005a09f  push    rdi
0x18005a0a0  push    r14
0x18005a0a2  mov     rbp, rsp
0x18005a0a5  sub     rsp, 80h
0x18005a0ac  mov     rax, cs:__security_cookie
0x18005a0b3  xor     rax, rsp
0x18005a0b6  mov     [rbp+var_10], rax
0x18005a0ba  xor     ebx, ebx
0x18005a0bc  mov     r14, rcx
0x18005a0bf  lea     rcx, [rbp+var_60]
0x18005a0c3  mov     [rbp+var_18], ebx
0x18005a0c6  mov     [rbp+var_60], rbx
0x18005a0ca  mov     rsi, rdx
0x18005a0cd  mov     [rdx], rbx
0x18005a0d0  call    ??$Allocate@$$V@?$AutoNewPtr@VCChildNode@@@Windows@@QEAAPEAVCChildNode@@XZ; Windows::AutoNewPtr<CChildNode>::Allocate<>(void)
0x18005a0d5  test    rax, rax
0x18005a0d8  jnz     short loc_18005A10C
0x18005a0da  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005a0e1  mov     [rbp+var_48], 4ADh
0x18005a0e9  mov     qword ptr [rbp+var_58], rax
0x18005a0ed  lea     rdx, [rbp+var_58]
0x18005a0f1  lea     rax, aCmicrodomupdat; "CMicrodomUpdateContext::CreateVirtualCo"...
0x18005a0f8  mov     qword ptr [rbp+var_58+8], rax
0x18005a0fc  lea     rax, aNewchildAlloca; "NewChild.Allocate()"
0x18005a103  mov     [rbp+var_40], rax
0x18005a107  jmp     loc_18005A1AE
0x18005a10c  mov     rdi, [rbp+var_60]
0x18005a110  mov     ecx, 90h; Size
0x18005a115  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a11a  test    rax, rax
0x18005a11d  jz      short loc_18005A171
0x18005a11f  xor     ecx, ecx
0x18005a121  xorps   xmm0, xmm0
0x18005a124  movups  xmmword ptr [rax+8], xmm0
0x18005a128  mov     [rax+18h], rcx
0x18005a12c  movups  xmmword ptr [rax+20h], xmm0
0x18005a130  mov     [rax+30h], rcx
0x18005a134  movups  xmmword ptr [rax+38h], xmm0
0x18005a138  mov     [rax+48h], rcx
0x18005a13c  movups  xmmword ptr [rax+50h], xmm0
0x18005a140  mov     [rax+60h], rcx
0x18005a144  mov     [rax+68h], rcx
0x18005a148  mov     [rax+70h], rcx
0x18005a14c  mov     [rax+78h], cx
0x18005a150  lea     rcx, ??_7CCommentModification@@6B@; const CCommentModification::`vftable'
0x18005a157  mov     [rax], rcx
0x18005a15a  or      ecx, 0FFFFFFFFh
0x18005a15d  movups  xmmword ptr [rax+80h], xmm0
0x18005a164  mov     [rax+88h], ecx
0x18005a16a  movups  [rbp+var_58], xmm0
0x18005a16e  mov     dword ptr [rbp+var_58+8], ecx
0x18005a171  cmp     [rdi+30h], rbx
0x18005a175  jz      short loc_18005A178
0x18005a177  int     3; Trap to Debugger
0x18005a178  mov     [rdi+30h], rax
0x18005a17c  test    rax, rax
0x18005a17f  jnz     short loc_18005A1BB
0x18005a181  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005a188  mov     [rbp+var_28], 4AEh
0x18005a190  mov     [rbp+var_38], rax
0x18005a194  lea     rdx, [rbp+var_38]
0x18005a198  lea     rax, aCmicrodomupdat; "CMicrodomUpdateContext::CreateVirtualCo"...
0x18005a19f  mov     [rbp+var_30], rax
0x18005a1a3  lea     rax, aNewchildCommen; "NewChild->Comment.Allocate()"
0x18005a1aa  mov     [rbp+var_20], rax
0x18005a1ae  lea     rcx, [rbp+var_18]
0x18005a1b2  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005a1b7  mov     ebx, eax
0x18005a1b9  jmp     short loc_18005A1F0
0x18005a1bb  mov     [rax+68h], r14
0x18005a1bf  lea     rcx, [r14+8]
0x18005a1c3  mov     [rax+70h], rbx
0x18005a1c7  mov     [rdi+38h], rax
0x18005a1cb  mov     [rsi], rdi
0x18005a1ce  mov     rax, [rcx+8]
0x18005a1d2  mov     [rdi+8], rax
0x18005a1d6  mov     [rdi], rcx
0x18005a1d9  mov     rax, [rcx+8]
0x18005a1dd  mov     [rbp+var_60], rbx
0x18005a1e1  mov     [rax], rdi
0x18005a1e4  mov     [rcx+8], rdi
0x18005a1e8  mov     [rdi+10h], rcx
0x18005a1ec  inc     qword ptr [rcx+18h]
0x18005a1f0  lea     rcx, [rbp+var_60]
0x18005a1f4  call    ??1?$Auto@PEAVCChildNode@@@Windows@@QEAA@XZ; Windows::Auto<CChildNode *>::~Auto<CChildNode *>(void)
0x18005a1f9  mov     eax, ebx
0x18005a1fb  mov     rcx, [rbp+var_10]
0x18005a1ff  xor     rcx, rsp; StackCookie
0x18005a202  call    __security_check_cookie
0x18005a207  lea     r11, [rsp+80h+var_s0]
0x18005a20f  mov     rbx, [r11+30h]
0x18005a213  mov     rsi, [r11+38h]
0x18005a217  mov     rsp, r11
0x18005a21a  pop     r14
0x18005a21c  pop     rdi
0x18005a21d  pop     rbp
0x18005a21e  retn
```
