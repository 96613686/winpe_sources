# SCardGetReaderIconA

- ea: `0x180025980`
- end: `0x180025b28`
- name: `SCardGetReaderIconA`
- size: `424`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002a30`
- `0x1800093e4`
- `0x18000e090`
- `0x18000e680`
- `0x180010898`
- `0x180011b0c`
- `0x1800126f0`
- `0x1800190cc`
- `0x180025980`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800259f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800259f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a28`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SCardGetReaderIconA(unsigned __int64 a1, __int64 a2, unsigned __int8 *a3, unsigned int *a4)
{
  unsigned int v8; // edi
  CHandleList *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v12; // rsi
  __int64 v13; // rbx
  const unsigned __int16 *v14; // rax
  ulong v15; // eax
  const unsigned __int16 *v16; // rax
  ulong ReaderIcon; // eax
  ulong pExceptionObject; // [rsp+28h] [rbp-90h] BYREF
  ulong v20; // [rsp+2Ch] [rbp-8Ch] BYREF
  ulong v21; // [rsp+30h] [rbp-88h] BYREF
  ulong v22; // [rsp+34h] [rbp-84h] BYREF
  ulong v23; // [rsp+38h] [rbp-80h] BYREF
  ulong v24; // [rsp+3Ch] [rbp-7Ch] BYREF
  void **v25; // [rsp+40h] [rbp-78h] BYREF
  int v26; // [rsp+48h] [rbp-70h]
  const int *v27; // [rsp+50h] [rbp-68h]
  __int64 v28; // [rsp+58h] [rbp-60h]
  int v29; // [rsp+60h] [rbp-58h]
  int v30; // [rsp+64h] [rbp-54h]
  const int *v31; // [rsp+68h] [rbp-50h]
  __int64 v32; // [rsp+70h] [rbp-48h]
  int v33; // [rsp+78h] [rbp-40h]
  int v34; // [rsp+7Ch] [rbp-3Ch]

  v8 = 0;
  try
  {
    v25 = &CTextString::`vftable';
    v27 = &CBuffer::`vftable';
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = &CBuffer::`vftable';
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v26 = 3;
    v9 = g_phlContexts;
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v9, a1);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v12 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v10);
    if ( *(_DWORD *)(v12 + 16) )
    {
      v20 = -2146435042;
      throw &v20;
    }
    v13 = *(_QWORD *)(v12 + 128);
    CTextString::operator=(&v25, a2);
    if ( v13 || !RedirectionContextIsLocal(0) )
    {
      if ( RedirectDisabled() )
      {
        v22 = -2146435043;
        throw &v22;
      }
      v16 = CTextString::Unicode((CTextString *)&v25);
      ReaderIcon = RedirectedSCardGetReaderIcon(*(struct _REDIR_LOCAL_SCARDCONTEXT **)(v12 + 128), v16, a3, a4);
      if ( ReaderIcon )
      {
        v23 = ReaderIcon;
        throw &v23;
      }
    }
    else
    {
      v14 = CTextString::Unicode((CTextString *)&v25);
      v15 = GetReaderIcon((struct CSCardUserContext *)v12, v14, a3, a4);
      if ( v15 )
      {
        v21 = v15;
        throw &v21;
      }
    }
    CTextString::~CTextString((CTextString *)&v25);
  }
  catch ( ulong v24 )
  {
    return v24;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v8;
}

```

## disassembly

```asm
0x180025980  mov     r11, rsp
0x180025983  push    rbx
0x180025984  push    rsi
0x180025985  push    rdi
0x180025986  push    r12
0x180025988  push    r13
0x18002598a  push    r14
0x18002598c  push    r15
0x18002598e  sub     rsp, 80h
0x180025995  mov     r12, r9
0x180025998  mov     r13, r8
0x18002599b  mov     r15, rdx
0x18002599e  mov     rsi, rcx
0x1800259a1  xor     ecx, ecx
0x1800259a3  mov     edi, ecx
0x1800259a5  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x1800259ac  mov     [r11-78h], rax
0x1800259b0  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800259b7  mov     [r11-68h], rax
0x1800259bb  mov     [r11-60h], rcx
0x1800259bf  mov     [rsp+0B8h+var_58], ecx
0x1800259c3  mov     [rsp+0B8h+var_54], ecx
0x1800259c7  mov     [r11-50h], rax
0x1800259cb  mov     [r11-48h], rcx
0x1800259cf  mov     [rsp+0B8h+var_40], ecx
0x1800259d3  mov     [rsp+0B8h+var_3C], ecx
0x1800259d7  mov     [rsp+0B8h+var_70], 3
0x1800259df  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x1800259e6  lea     r14, [rbx+20h]
0x1800259ea  mov     [rsp+0B8h+var_98], r14
0x1800259ef  mov     rcx, r14; lpCriticalSection
0x1800259f2  call    cs:__imp_EnterCriticalSection
0x1800259f8  nop
0x1800259f9  mov     rdx, rsi; unsigned __int64
0x1800259fc  mov     rcx, rbx; this
0x1800259ff  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180025a04  test    rax, rax
0x180025a07  jnz     short loc_180025A22
0x180025a09  mov     [rsp+0B8h+pExceptionObject], 6
0x180025a11  lea     rdx, _TI1K; pThrowInfo
0x180025a18  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180025a1d  call    _CxxThrowException_0
0x180025a22  mov     rsi, [rax]
0x180025a25  mov     rcx, r14; lpCriticalSection
0x180025a28  call    cs:__imp_LeaveCriticalSection
0x180025a2e  cmp     dword ptr [rsi+10h], 0
0x180025a32  jz      short loc_180025A4D
0x180025a34  mov     [rsp+0B8h+var_8C], 8010001Eh
0x180025a3c  lea     rdx, _TI1K; pThrowInfo
0x180025a43  lea     rcx, [rsp+0B8h+var_8C]; pExceptionObject
0x180025a48  call    _CxxThrowException_0
0x180025a4d  mov     rbx, [rsi+80h]
0x180025a54  mov     rdx, r15
0x180025a57  lea     rcx, [rsp+0B8h+var_78]
0x180025a5c  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x180025a61  test    rbx, rbx
0x180025a64  jnz     short loc_180025AA5
0x180025a66  xor     ecx, ecx; lpCriticalSection
0x180025a68  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180025a6d  test    al, al
0x180025a6f  jz      short loc_180025AA5
0x180025a71  lea     rcx, [rsp+0B8h+var_78]; this
0x180025a76  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180025a7b  mov     r9, r12; unsigned int *
0x180025a7e  mov     r8, r13; unsigned __int8 *
0x180025a81  mov     rdx, rax; unsigned __int16 *
0x180025a84  mov     rcx, rsi; struct CSCardUserContext *
0x180025a87  call    ?GetReaderIcon@@YAJPEAVCSCardUserContext@@PEBGPEAEPEAK@Z; GetReaderIcon(CSCardUserContext *,ushort const *,uchar *,ulong *)
0x180025a8c  test    eax, eax
0x180025a8e  jz      short loc_180025B00
0x180025a90  mov     [rsp+0B8h+var_88], eax
0x180025a94  lea     rdx, _TI1K; pThrowInfo
0x180025a9b  lea     rcx, [rsp+0B8h+var_88]; pExceptionObject
0x180025aa0  call    _CxxThrowException_0
0x180025aa5  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180025aaa  test    al, al
0x180025aac  jz      short loc_180025AC7
0x180025aae  mov     [rsp+0B8h+var_84], 8010001Dh
0x180025ab6  lea     rdx, _TI1K; pThrowInfo
0x180025abd  lea     rcx, [rsp+0B8h+var_84]; pExceptionObject
0x180025ac2  call    _CxxThrowException_0
0x180025ac7  lea     rcx, [rsp+0B8h+var_78]; this
0x180025acc  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180025ad1  mov     r9, r12; unsigned int *
0x180025ad4  mov     r8, r13; unsigned __int8 *
0x180025ad7  mov     rdx, rax; unsigned __int16 *
0x180025ada  mov     rcx, [rsi+80h]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x180025ae1  call    ?RedirectedSCardGetReaderIcon@@YAJ_KPEBGPEAEPEAK@Z; RedirectedSCardGetReaderIcon(unsigned __int64,ushort const *,uchar *,ulong *)
0x180025ae6  test    eax, eax
0x180025ae8  jz      short loc_180025B00
0x180025aea  mov     [rsp+0B8h+var_80], eax
0x180025aee  lea     rdx, _TI1K; pThrowInfo
0x180025af5  lea     rcx, [rsp+0B8h+var_80]; pExceptionObject
0x180025afa  call    _CxxThrowException_0
0x180025b00  lea     rcx, [rsp+0B8h+var_78]; this
0x180025b05  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180025b0a  nop
0x180025b0b  jmp     short loc_180025B13
0x180025b0d  jmp     short $+2
0x180025b0f  mov     edi, dword ptr [rsp+0B8h+var_98]
0x180025b13  mov     eax, edi
0x180025b15  add     rsp, 80h
0x180025b1c  pop     r15
0x180025b1e  pop     r14
0x180025b20  pop     r13
0x180025b22  pop     r12
0x180025b24  pop     rdi
0x180025b25  pop     rsi
0x180025b26  pop     rbx
0x180025b27  retn
```
