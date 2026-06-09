# CMicrodomUpdateContext::GetNodeUpdatePtr(Windows::Microdom::Rtl::Node,CElementModification *,CChildNode * &)

- ea: `0x18005b96c`
- end: `0x18005bb87`
- name: `?GetNodeUpdatePtr@CMicrodomUpdateContext@@QEAAJUNode@Rtl@Microdom@Windows@@PEAVCElementModification@@AEAPEAVCChildNode@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(CMicrodomUpdateContext *__hidden this, struct Node, struct CElementModification *, struct CChildNode **)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005a8b0`
- `0x18005ab04`
- `0x18005bb90`
- `0x18005d680`

## callees

- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005aea0`
- `0x18005afe4`
- `0x18005b178`
- `0x18005b2bc`
- `0x18005b96c`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005bb30`
- `ntdll!RtlRaiseStatus` at `0x18005bb30`

## string_xrefs

- `0x18005b9bb`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ba85`: `onecore\base\xml\udom_modify.cpp`
- `0x18005b9d2`: `CMicrodomUpdateContext::GetNodeUpdatePtr`
- `0x18005ba9c`: `CMicrodomUpdateContext::GetNodeUpdatePtr`
- `0x18005b9dd`: `ulIndex < UpdateChildNodes.Size()`

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
    goto LABEL_22;
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
    RtlRaiseStatus(-1073741595);
  *(_QWORD *)(*((_QWORD *)this + 5) + 8 * AddRef_low) = v15;
  result = (*(__int64 (__fastcall **)(_QWORD, struct CElementModification *, _QWORD))(**((_QWORD **)v15 + 7) + 80LL))(
             *((_QWORD *)v15 + 7),
             a3,
             (unsigned int)AddRef_low);
  if ( (int)result >= 0 )
  {
LABEL_22:
    result = 0;
    *a4 = *(struct CChildNode **)(*((_QWORD *)this + 5) + 8 * AddRef_low);
  }
  return result;
}

```

## disassembly

```asm
0x18005b96c  push    rbp
0x18005b96e  push    rbx
0x18005b96f  push    rsi
0x18005b970  push    rdi
0x18005b971  push    r14
0x18005b973  lea     rbp, [rsp-37h]
0x18005b978  sub     rsp, 0B0h
0x18005b97f  mov     rax, cs:__security_cookie
0x18005b986  xor     rax, rsp
0x18005b989  mov     [rbp+57h+var_28], rax
0x18005b98d  mov     edi, [rdx+8]
0x18005b990  mov     rbx, rcx
0x18005b993  mov     qword ptr [r9], 0
0x18005b99a  mov     rsi, r9
0x18005b99d  mov     rcx, [rcx+28h]
0x18005b9a1  mov     r14, r8
0x18005b9a4  mov     [rbp+57h+var_50], 0
0x18005b9ab  mov     rax, [rbx+30h]
0x18005b9af  sub     rax, rcx
0x18005b9b2  sar     rax, 3
0x18005b9b6  cmp     rdi, rax
0x18005b9b9  jb      short loc_18005B9F6
0x18005b9bb  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005b9c2  mov     [rbp+57h+var_38], 53Dh
0x18005b9ca  mov     qword ptr [rbp+57h+var_48], rax
0x18005b9ce  lea     rdx, [rbp+57h+var_48]
0x18005b9d2  lea     rax, aCmicrodomupdat_3; "CMicrodomUpdateContext::GetNodeUpdatePt"...
0x18005b9d9  mov     qword ptr [rbp+57h+var_48+8], rax
0x18005b9dd  lea     rax, aUlindexUpdatec; "ulIndex < UpdateChildNodes.Size()"
0x18005b9e4  mov     [rbp+57h+var_30], rax
0x18005b9e8  lea     rcx, [rbp+57h+var_50]
0x18005b9ec  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005b9f1  jmp     loc_18005BB6C
0x18005b9f6  cmp     qword ptr [rcx+rdi*8], 0
0x18005b9fb  jnz     loc_18005BB5F
0x18005ba01  mov     rcx, [rbx]
0x18005ba04  lea     r8, [rbp+57h+var_48]
0x18005ba08  xor     eax, eax
0x18005ba0a  mov     [rbp+57h+var_A0], 0
0x18005ba12  xorps   xmm0, xmm0
0x18005ba15  mov     [rbp+57h+var_38], rax
0x18005ba19  movups  [rbp+57h+var_48], xmm0
0x18005ba1d  mov     rax, [rcx]
0x18005ba20  mov     r9d, 1
0x18005ba26  movaps  xmm0, xmmword ptr [rdx]
0x18005ba29  lea     rdx, [rbp+57h+var_90]
0x18005ba2d  mov     [rbp+57h+var_70], r8
0x18005ba31  lea     r8, [rbp+57h+var_98]
0x18005ba35  mov     [rbp+57h+var_60], r8
0x18005ba39  lea     r8, [rbp+57h+var_60]
0x18005ba3d  mov     rax, [rax+98h]
0x18005ba44  mov     [rbp+57h+var_68], r9
0x18005ba48  mov     [rbp+57h+var_58], r9
0x18005ba4c  lea     r9, [rbp+57h+var_70]
0x18005ba50  mov     [rbp+57h+var_98], 2008h
0x18005ba57  movdqa  [rbp+57h+var_90], xmm0
0x18005ba5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba61  test    eax, eax
0x18005ba63  js      loc_18005BB6C
0x18005ba69  movzx   ecx, word ptr [rbp+57h+var_48+8]
0x18005ba6d  sub     ecx, 1
0x18005ba70  jz      loc_18005BB10
0x18005ba76  sub     ecx, 1
0x18005ba79  jz      short loc_18005BAF5
0x18005ba7b  sub     ecx, 1
0x18005ba7e  jz      short loc_18005BAD6
0x18005ba80  cmp     ecx, 5
0x18005ba83  jz      short loc_18005BAB7
0x18005ba85  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ba8c  mov     [rbp+57h+var_80], 55Dh
0x18005ba94  mov     qword ptr [rbp+57h+var_90], rax
0x18005ba98  lea     rdx, [rbp+57h+var_90]
0x18005ba9c  lea     rax, aCmicrodomupdat_3; "CMicrodomUpdateContext::GetNodeUpdatePt"...
0x18005baa3  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005baa7  lea     rax, aFalse; "false"
0x18005baae  mov     [rbp+57h+var_78], rax
0x18005bab2  jmp     loc_18005B9E8
0x18005bab7  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005babb  mov     rcx, rbx; this
0x18005babe  call    ?CreateVirtualComment@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualComment(CChildNode * &)
0x18005bac3  test    eax, eax
0x18005bac5  js      loc_18005BB6C
0x18005bacb  mov     rcx, [rbp+57h+var_A0]
0x18005bacf  cmp     qword ptr [rcx+30h], 0
0x18005bad4  jmp     short loc_18005BB29
0x18005bad6  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005bada  mov     rcx, rbx; this
0x18005badd  call    ?CreateVirtualTextual@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualTextual(CChildNode * &)
0x18005bae2  test    eax, eax
0x18005bae4  js      loc_18005BB6C
0x18005baea  mov     rcx, [rbp+57h+var_A0]
0x18005baee  cmp     qword ptr [rcx+18h], 0
0x18005baf3  jmp     short loc_18005BB29
0x18005baf5  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005baf9  mov     rcx, rbx; this
0x18005bafc  call    ?CreateVirtualAttribute@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualAttribute(CChildNode * &)
0x18005bb01  test    eax, eax
0x18005bb03  js      short loc_18005BB6C
0x18005bb05  mov     rcx, [rbp+57h+var_A0]
0x18005bb09  cmp     qword ptr [rcx+20h], 0
0x18005bb0e  jmp     short loc_18005BB29
0x18005bb10  lea     rdx, [rbp+57h+var_A0]; struct CChildNode **
0x18005bb14  mov     rcx, rbx; this
0x18005bb17  call    ?CreateVirtualElement@CMicrodomUpdateContext@@QEAAJAEAPEAVCChildNode@@@Z; CMicrodomUpdateContext::CreateVirtualElement(CChildNode * &)
0x18005bb1c  test    eax, eax
0x18005bb1e  js      short loc_18005BB6C
0x18005bb20  mov     rcx, [rbp+57h+var_A0]
0x18005bb24  cmp     qword ptr [rcx+28h], 0
0x18005bb29  jnz     short loc_18005BB3D
0x18005bb2b  mov     ecx, 0C00000E5h; Status
0x18005bb30  call    cs:__imp_RtlRaiseStatus
0x18005bb37  nop     dword ptr [rax+rax+00h]
0x18005bb3c  int     3; Trap to Debugger
0x18005bb3d  mov     rax, [rbx+28h]
0x18005bb41  mov     r8d, edi
0x18005bb44  mov     rdx, r14
0x18005bb47  mov     [rax+rdi*8], rcx
0x18005bb4b  mov     rcx, [rcx+38h]
0x18005bb4f  mov     rax, [rcx]
0x18005bb52  mov     rax, [rax+50h]
0x18005bb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb5b  test    eax, eax
0x18005bb5d  js      short loc_18005BB6C
0x18005bb5f  mov     rax, [rbx+28h]
0x18005bb63  mov     rcx, [rax+rdi*8]
0x18005bb67  xor     eax, eax
0x18005bb69  mov     [rsi], rcx
0x18005bb6c  mov     rcx, [rbp+57h+var_28]
0x18005bb70  xor     rcx, rsp; StackCookie
0x18005bb73  call    __security_check_cookie
0x18005bb78  add     rsp, 0B0h
0x18005bb7f  pop     r14
0x18005bb81  pop     rdi
0x18005bb82  pop     rsi
0x18005bb83  pop     rbx
0x18005bb84  pop     rbp
0x18005bb85  retn
```
