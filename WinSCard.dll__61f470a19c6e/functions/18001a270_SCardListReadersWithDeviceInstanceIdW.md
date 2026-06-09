# SCardListReadersWithDeviceInstanceIdW

- ea: `0x18001a270`
- end: `0x18001a52f`
- name: `SCardListReadersWithDeviceInstanceIdW`
- size: `703`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180003430`
- `0x1800040d0`
- `0x1800093e4`
- `0x180009480`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000e3d0`
- `0x180010898`
- `0x1800126f0`
- `0x18001a270`
- `0x18001a538`
- `0x18002a02c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001a3fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001a3fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a2c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a2c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a2ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a2ff`

## string_xrefs

- `0x18001a39d`: `SCard$AllReaders`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SCardListReadersWithDeviceInstanceIdW(
        unsigned __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int *v4; // r13
  __int64 v5; // r12
  CHandleList *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v10; // rbx
  unsigned int v11; // esi
  unsigned __int16 *v12; // r14
  unsigned __int16 *v13; // rcx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v15; // rsi
  const WCHAR *v16; // rcx
  unsigned int v18; // [rsp+20h] [rbp-C8h]
  ulong pExceptionObject; // [rsp+24h] [rbp-C4h] BYREF
  ulong v20; // [rsp+28h] [rbp-C0h] BYREF
  ulong v21; // [rsp+2Ch] [rbp-BCh] BYREF
  ulong v22; // [rsp+30h] [rbp-B8h] BYREF
  ulong v23; // [rsp+34h] [rbp-B4h] BYREF
  ulong v24; // [rsp+38h] [rbp-B0h] BYREF
  ulong v25; // [rsp+3Ch] [rbp-ACh] BYREF
  const unsigned __int16 *v26; // [rsp+40h] [rbp-A8h]
  const int *v27; // [rsp+48h] [rbp-A0h] BYREF
  unsigned __int16 *v28; // [rsp+50h] [rbp-98h]
  int v29; // [rsp+58h] [rbp-90h]
  int v30; // [rsp+5Ch] [rbp-8Ch]
  __int64 v31; // [rsp+60h] [rbp-88h]
  const int *v32; // [rsp+68h] [rbp-80h] BYREF
  const WCHAR *v33; // [rsp+70h] [rbp-78h]
  int v34; // [rsp+78h] [rbp-70h]
  int v35; // [rsp+7Ch] [rbp-6Ch]
  const int *v36; // [rsp+80h] [rbp-68h] BYREF
  unsigned __int16 *v37; // [rsp+88h] [rbp-60h]
  int v38; // [rsp+90h] [rbp-58h]
  int v39; // [rsp+94h] [rbp-54h]
  ulong v40; // [rsp+98h] [rbp-50h] BYREF
  char *v41; // [rsp+A0h] [rbp-48h]

  v4 = a4;
  v5 = a2;
  v18 = 0;
  try
  {
    v31 = 0;
    if ( !a4 || !a2 )
    {
      v25 = -2146435068;
      throw &v25;
    }
    v7 = g_phlContexts;
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v41 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v7, a1);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v10 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v8);
    v31 = v10;
    if ( *(_DWORD *)(v10 + 16) )
    {
      v20 = -2146435042;
      throw &v20;
    }
    if ( *(_QWORD *)(v10 + 128) || (v11 = *(_DWORD *)(v10 + 28), !RedirectionContextIsLocal(0)) )
    {
      if ( RedirectDisabled() )
      {
        v23 = -2146435043;
        throw &v23;
      }
      v24 = -2146435049;
      throw &v24;
    }
    v36 = &CBuffer::`vftable';
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v32 = &CBuffer::`vftable';
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v27 = &CBuffer::`vftable';
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v26 = 0;
    ListReaders(v11, L"SCard$AllReaders", (struct CBuffer *)&v36);
    v12 = (unsigned __int16 *)&WideCharStr;
    v13 = (unsigned __int16 *)&WideCharStr;
    if ( v39 )
      v13 = v37;
    for ( i = FirstString(v13); ; i = NextString(v15) )
    {
      v26 = i;
      v15 = i;
      if ( !i )
        break;
      try
      {
        CSCardUserContext::GetReaderDeviceInstanceId((CSCardUserContext *)v10, i, (struct CBuffer *)&v32);
        if ( v35 )
          v16 = v33;
        else
          v16 = &WideCharStr;
        if ( !(unsigned int)_o__wcsicmp(v16, v5) )
          MStrAdd((struct CBuffer *)&v27, v15);
      }
      catch ( ulong v21 )
      {
        if ( v21 != -2146435063 && v21 != -2146435049 )
          throw;
        v12 = (unsigned __int16 *)&WideCharStr;
        v4 = a4;
        v5 = a2;
        v10 = v31;
        v15 = v26;
        continue;
      }
    }
    if ( v30 )
      v12 = v28;
    if ( !MStringCount(v12) )
    {
      v22 = -2146435026;
      throw &v22;
    }
    PlaceMultiResult((struct CSCardUserContext *)v10, (struct CBuffer *)&v27, a3, v4);
    v27 = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)&v27);
    v32 = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)&v32);
    v36 = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)&v36);
  }
  catch ( ulong v40 )
  {
    return v40;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v18;
}

```

## disassembly

```asm
0x18001a270  mov     rax, rsp
0x18001a273  mov     [rax+20h], r9
0x18001a277  mov     [rax+18h], r8
0x18001a27b  mov     [rax+10h], rdx
0x18001a27f  push    rbx
0x18001a280  push    rsi
0x18001a281  push    rdi
0x18001a282  push    r12
0x18001a284  push    r13
0x18001a286  push    r14
0x18001a288  push    r15
0x18001a28a  sub     rsp, 0B0h
0x18001a291  mov     r13, r9
0x18001a294  mov     r12, rdx
0x18001a297  mov     r14, rcx
0x18001a29a  xor     edi, edi
0x18001a29c  mov     [rsp+0E8h+var_C8], edi
0x18001a2a0  mov     [rsp+0E8h+var_88], rdi
0x18001a2a5  test    r9, r9
0x18001a2a8  jz      loc_18001A4FC
0x18001a2ae  test    rdx, rdx
0x18001a2b1  jz      loc_18001A4FC
0x18001a2b7  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18001a2be  lea     rsi, [rbx+20h]
0x18001a2c2  mov     [rax-48h], rsi
0x18001a2c6  mov     rcx, rsi; lpCriticalSection
0x18001a2c9  call    cs:__imp_EnterCriticalSection
0x18001a2cf  nop
0x18001a2d0  mov     rdx, r14; unsigned __int64
0x18001a2d3  mov     rcx, rbx; this
0x18001a2d6  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x18001a2db  test    rax, rax
0x18001a2de  jnz     short loc_18001A2F9
0x18001a2e0  mov     [rsp+0E8h+pExceptionObject], 6
0x18001a2e8  lea     rdx, _TI1K; pThrowInfo
0x18001a2ef  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18001a2f4  call    _CxxThrowException_0
0x18001a2f9  mov     rbx, [rax]
0x18001a2fc  mov     rcx, rsi; lpCriticalSection
0x18001a2ff  call    cs:__imp_LeaveCriticalSection
0x18001a305  mov     [rsp+0E8h+var_88], rbx
0x18001a30a  cmp     [rbx+10h], edi
0x18001a30d  jz      short loc_18001A328
0x18001a30f  mov     [rsp+0E8h+var_C0], 8010001Eh
0x18001a317  lea     rdx, _TI1K; pThrowInfo
0x18001a31e  lea     rcx, [rsp+0E8h+var_C0]; pExceptionObject
0x18001a323  call    _CxxThrowException_0
0x18001a328  cmp     [rbx+80h], rdi
0x18001a32f  jnz     loc_18001A4C8
0x18001a335  mov     esi, [rbx+1Ch]
0x18001a338  xor     ecx, ecx; lpCriticalSection
0x18001a33a  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x18001a33f  test    al, al
0x18001a341  jz      loc_18001A4C8
0x18001a347  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001a34e  mov     [rsp+0E8h+var_68], r15
0x18001a356  mov     [rsp+0E8h+var_60], rdi
0x18001a35e  mov     [rsp+0E8h+var_58], edi
0x18001a365  mov     [rsp+0E8h+var_54], edi
0x18001a36c  mov     [rsp+0E8h+var_80], r15
0x18001a371  mov     [rsp+0E8h+var_78], rdi
0x18001a376  mov     [rsp+0E8h+var_70], edi
0x18001a37a  mov     [rsp+0E8h+var_6C], edi
0x18001a37e  mov     [rsp+0E8h+var_A0], r15
0x18001a383  mov     [rsp+0E8h+var_98], rdi
0x18001a388  mov     [rsp+0E8h+var_90], edi
0x18001a38c  mov     [rsp+0E8h+var_8C], edi
0x18001a390  mov     [rsp+0E8h+var_A8], rdi
0x18001a395  lea     r8, [rsp+0E8h+var_68]; struct CBuffer *
0x18001a39d  lea     rdx, aScardAllreader; "SCard$AllReaders"
0x18001a3a4  mov     ecx, esi; unsigned int
0x18001a3a6  call    ?ListReaders@@YAXKPEBGAEAVCBuffer@@@Z; ListReaders(ulong,ushort const *,CBuffer &)
0x18001a3ab  lea     r14, WideCharStr
0x18001a3b2  mov     rcx, r14
0x18001a3b5  cmp     [rsp+0E8h+var_54], edi
0x18001a3bc  cmova   rcx, [rsp+0E8h+var_60]; unsigned __int16 *
0x18001a3c5  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18001a3ca  mov     [rsp+0E8h+var_A8], rax
0x18001a3cf  mov     rsi, rax
0x18001a3d2  test    rax, rax
0x18001a3d5  jz      short loc_18001A448
0x18001a3d7  lea     r8, [rsp+0E8h+var_80]; struct CBuffer *
0x18001a3dc  mov     rdx, rax; unsigned __int16 *
0x18001a3df  mov     rcx, rbx; this
0x18001a3e2  call    ?GetReaderDeviceInstanceId@CSCardUserContext@@QEAAJPEBGAEAVCBuffer@@@Z; CSCardUserContext::GetReaderDeviceInstanceId(ushort const *,CBuffer &)
0x18001a3e7  cmp     [rsp+0E8h+var_6C], edi
0x18001a3eb  ja      short loc_18001A3F2
0x18001a3ed  mov     rcx, r14
0x18001a3f0  jmp     short loc_18001A3F7
0x18001a3f2  mov     rcx, [rsp+0E8h+var_78]
0x18001a3f7  mov     rdx, r12
0x18001a3fa  call    cs:__imp__o__wcsicmp
0x18001a400  test    eax, eax
0x18001a402  jnz     short loc_18001A412
0x18001a404  mov     rdx, rsi; unsigned __int16 *
0x18001a407  lea     rcx, [rsp+0E8h+var_A0]; struct CBuffer *
0x18001a40c  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18001a411  nop
0x18001a412  jmp     short loc_18001A43E
0x18001a414  xor     edi, edi
0x18001a416  lea     r15, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001a41d  lea     r14, WideCharStr
0x18001a424  mov     r13, [rsp+0E8h+arg_18]
0x18001a42c  mov     r12, [rsp+0E8h+arg_8]
0x18001a434  mov     rbx, [rsp+0E8h+var_88]
0x18001a439  mov     rsi, [rsp+0E8h+var_A8]
0x18001a43e  mov     rcx, rsi; unsigned __int16 *
0x18001a441  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18001a446  jmp     short loc_18001A3CA
0x18001a448  cmp     [rsp+0E8h+var_8C], edi
0x18001a44c  cmova   r14, [rsp+0E8h+var_98]
0x18001a452  mov     rcx, r14; unsigned __int16 *
0x18001a455  call    ?MStringCount@@YAKPEBG@Z; MStringCount(ushort const *)
0x18001a45a  test    eax, eax
0x18001a45c  jnz     short loc_18001A477
0x18001a45e  mov     [rsp+0E8h+var_B8], 8010002Eh
0x18001a466  lea     rdx, _TI1K; pThrowInfo
0x18001a46d  lea     rcx, [rsp+0E8h+var_B8]; pExceptionObject
0x18001a472  call    _CxxThrowException_0
0x18001a477  mov     r9, r13; unsigned int *
0x18001a47a  mov     r8, [rsp+0E8h+arg_10]; unsigned __int16 *
0x18001a482  lea     rdx, [rsp+0E8h+var_A0]; struct CBuffer *
0x18001a487  mov     rcx, rbx; this
0x18001a48a  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAGPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,ushort *,ulong *)
0x18001a48f  nop
0x18001a490  mov     [rsp+0E8h+var_A0], r15
0x18001a495  lea     rcx, [rsp+0E8h+var_A0]; this
0x18001a49a  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18001a49f  nop
0x18001a4a0  mov     [rsp+0E8h+var_80], r15
0x18001a4a5  lea     rcx, [rsp+0E8h+var_80]; this
0x18001a4aa  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18001a4af  nop
0x18001a4b0  mov     [rsp+0E8h+var_68], r15
0x18001a4b8  lea     rcx, [rsp+0E8h+var_68]; this
0x18001a4c0  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18001a4c5  nop
0x18001a4c6  jmp     short loc_18001A518
0x18001a4c8  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x18001a4cd  lea     rdx, _TI1K; pThrowInfo
0x18001a4d4  test    al, al
0x18001a4d6  jz      short loc_18001A4EA
0x18001a4d8  mov     [rsp+0E8h+var_B4], 8010001Dh
0x18001a4e0  lea     rcx, [rsp+0E8h+var_B4]; pExceptionObject
0x18001a4e5  call    _CxxThrowException_0
0x18001a4ea  mov     [rsp+0E8h+var_B0], 80100017h
0x18001a4f2  lea     rcx, [rsp+0E8h+var_B0]; pExceptionObject
0x18001a4f7  call    _CxxThrowException_0
0x18001a4fc  mov     [rsp+0E8h+var_AC], 80100004h
0x18001a504  lea     rdx, _TI1K; pThrowInfo
0x18001a50b  lea     rcx, [rsp+0E8h+var_AC]; pExceptionObject
0x18001a510  call    _CxxThrowException_0
0x18001a516  jmp     short $+2
0x18001a518  mov     eax, [rsp+0E8h+var_C8]
0x18001a51c  add     rsp, 0B0h
0x18001a523  pop     r15
0x18001a525  pop     r14
0x18001a527  pop     r13
0x18001a529  pop     r12
0x18001a52b  pop     rdi
0x18001a52c  pop     rsi
0x18001a52d  pop     rbx
0x18001a52e  retn
```
