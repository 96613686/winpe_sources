# SCardListReadersWithDeviceInstanceIdA

- ea: `0x1800262f0`
- end: `0x180026639`
- name: `SCardListReadersWithDeviceInstanceIdA`
- size: `841`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x1800040d0`
- `0x1800093e4`
- `0x180009480`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000e090`
- `0x18000e3d0`
- `0x18000e470`
- `0x18000e680`
- `0x180010898`
- `0x180011b0c`
- `0x1800126f0`
- `0x18001a538`
- `0x1800262f0`
- `0x18002a02c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800264f3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800264f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026349`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026349`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002637f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002637f`

## string_xrefs

- `0x180026474`: `SCard$AllReaders`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SCardListReadersWithDeviceInstanceIdA(unsigned __int64 a1, __int64 a2, char *a3, unsigned int *a4)
{
  unsigned int *v4; // r12
  __int64 v5; // r13
  CHandleList *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v10; // rsi
  unsigned int v11; // r14d
  unsigned __int16 *v12; // r15
  unsigned __int16 *v13; // rcx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // rax
  const WCHAR *v17; // rcx
  unsigned int v19; // [rsp+20h] [rbp-108h]
  ulong pExceptionObject; // [rsp+24h] [rbp-104h] BYREF
  ulong v21; // [rsp+28h] [rbp-100h] BYREF
  ulong v22; // [rsp+2Ch] [rbp-FCh] BYREF
  ulong v23; // [rsp+30h] [rbp-F8h] BYREF
  ulong v24; // [rsp+34h] [rbp-F4h] BYREF
  ulong v25; // [rsp+38h] [rbp-F0h] BYREF
  ulong v26; // [rsp+3Ch] [rbp-ECh] BYREF
  const unsigned __int16 *v27; // [rsp+40h] [rbp-E8h]
  const int *v28; // [rsp+48h] [rbp-E0h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-D8h]
  int v30; // [rsp+58h] [rbp-D0h]
  int v31; // [rsp+5Ch] [rbp-CCh]
  __int64 v32; // [rsp+60h] [rbp-C8h]
  const int *v33; // [rsp+68h] [rbp-C0h] BYREF
  const WCHAR *v34; // [rsp+70h] [rbp-B8h]
  int v35; // [rsp+78h] [rbp-B0h]
  int v36; // [rsp+7Ch] [rbp-ACh]
  const int *v37; // [rsp+80h] [rbp-A8h] BYREF
  unsigned __int16 *v38; // [rsp+88h] [rbp-A0h]
  int v39; // [rsp+90h] [rbp-98h]
  int v40; // [rsp+94h] [rbp-94h]
  ulong v41; // [rsp+98h] [rbp-90h] BYREF
  void **v42; // [rsp+A0h] [rbp-88h] BYREF
  int v43; // [rsp+A8h] [rbp-80h]
  const int *v44; // [rsp+B0h] [rbp-78h]
  __int64 v45; // [rsp+B8h] [rbp-70h]
  int v46; // [rsp+C0h] [rbp-68h]
  int v47; // [rsp+C4h] [rbp-64h]
  const int *v48; // [rsp+C8h] [rbp-60h]
  __int64 v49; // [rsp+D0h] [rbp-58h]
  int v50; // [rsp+D8h] [rbp-50h]
  int v51; // [rsp+DCh] [rbp-4Ch]
  char *v52; // [rsp+E0h] [rbp-48h]

  v4 = a4;
  v5 = a2;
  v19 = 0;
  try
  {
    v32 = 0;
    if ( !a4 || !a2 )
    {
      v26 = -2146435068;
      throw &v26;
    }
    v7 = g_phlContexts;
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v52 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v7, a1);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v10 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v8);
    v32 = v10;
    if ( *(_DWORD *)(v10 + 16) )
    {
      v21 = -2146435042;
      throw &v21;
    }
    if ( *(_QWORD *)(v10 + 128) || (v11 = *(_DWORD *)(v10 + 28), !RedirectionContextIsLocal(0)) )
    {
      if ( RedirectDisabled() )
      {
        v24 = -2146435043;
        throw &v24;
      }
      v25 = -2146435049;
      throw &v25;
    }
    v37 = &CBuffer::`vftable';
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v33 = &CBuffer::`vftable';
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v28 = &CBuffer::`vftable';
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v42 = &CTextString::`vftable';
    v44 = &CBuffer::`vftable';
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = &CBuffer::`vftable';
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v43 = 3;
    v27 = 0;
    ListReaders(v11, L"SCard$AllReaders", (struct CBuffer *)&v37);
    v12 = (unsigned __int16 *)&WideCharStr;
    v13 = (unsigned __int16 *)&WideCharStr;
    if ( v40 )
      v13 = v38;
    for ( i = FirstString(v13); ; i = NextString(v15) )
    {
      v27 = i;
      v15 = i;
      if ( !i )
        break;
      try
      {
        CSCardUserContext::GetReaderDeviceInstanceId((CSCardUserContext *)v10, i, (struct CBuffer *)&v33);
        CTextString::operator=(&v42, v5);
        v16 = CTextString::Unicode((CTextString *)&v42);
        if ( v36 )
          v17 = v34;
        else
          v17 = &WideCharStr;
        if ( !(unsigned int)_o__wcsicmp(v17, v16) )
          MStrAdd((struct CBuffer *)&v28, v15);
      }
      catch ( ulong v22 )
      {
        if ( v22 != -2146435063 && v22 != -2146435049 )
          throw;
        v12 = (unsigned __int16 *)&WideCharStr;
        v4 = a4;
        v5 = a2;
        v10 = v32;
        v15 = v27;
        continue;
      }
    }
    if ( v31 )
      v12 = v29;
    if ( !MStringCount(v12) )
    {
      v23 = -2146435026;
      throw &v23;
    }
    PlaceMultiResult((struct CSCardUserContext *)v10, (struct CBuffer *)&v28, a3, v4);
    CTextString::~CTextString((CTextString *)&v42);
    v28 = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)&v28);
    v33 = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)&v33);
    v37 = &CBuffer::`vftable';
    CBuffer::Clear((CBuffer *)&v37);
  }
  catch ( ulong v41 )
  {
    return v41;
  }
  catch ( ... )
  {
    return (unsigned int)-2146435068;
  }
  return v19;
}

```

## disassembly

```asm
0x1800262f0  mov     rax, rsp
0x1800262f3  mov     [rax+20h], r9
0x1800262f7  mov     [rax+18h], r8
0x1800262fb  mov     [rax+10h], rdx
0x1800262ff  push    rbx
0x180026300  push    rsi
0x180026301  push    rdi
0x180026302  push    r12
0x180026304  push    r13
0x180026306  push    r14
0x180026308  push    r15
0x18002630a  sub     rsp, 0F0h
0x180026311  mov     r12, r9
0x180026314  mov     r13, rdx
0x180026317  mov     rsi, rcx
0x18002631a  xor     edi, edi
0x18002631c  mov     [rsp+128h+var_108], edi
0x180026320  mov     [rsp+128h+var_C8], rdi
0x180026325  test    r9, r9
0x180026328  jz      loc_180026606
0x18002632e  test    rdx, rdx
0x180026331  jz      loc_180026606
0x180026337  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18002633e  lea     r14, [rbx+20h]
0x180026342  mov     [rax-48h], r14
0x180026346  mov     rcx, r14; lpCriticalSection
0x180026349  call    cs:__imp_EnterCriticalSection
0x18002634f  nop
0x180026350  mov     rdx, rsi; unsigned __int64
0x180026353  mov     rcx, rbx; this
0x180026356  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x18002635b  test    rax, rax
0x18002635e  jnz     short loc_180026379
0x180026360  mov     [rsp+128h+pExceptionObject], 6
0x180026368  lea     rdx, _TI1K; pThrowInfo
0x18002636f  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180026374  call    _CxxThrowException_0
0x180026379  mov     rsi, [rax]
0x18002637c  mov     rcx, r14; lpCriticalSection
0x18002637f  call    cs:__imp_LeaveCriticalSection
0x180026385  mov     [rsp+128h+var_C8], rsi
0x18002638a  cmp     [rsi+10h], edi
0x18002638d  jz      short loc_1800263A8
0x18002638f  mov     [rsp+128h+var_100], 8010001Eh
0x180026397  lea     rdx, _TI1K; pThrowInfo
0x18002639e  lea     rcx, [rsp+128h+var_100]; pExceptionObject
0x1800263a3  call    _CxxThrowException_0
0x1800263a8  cmp     [rsi+80h], rdi
0x1800263af  jnz     loc_1800265D2
0x1800263b5  mov     r14d, [rsi+1Ch]
0x1800263b9  xor     ecx, ecx; lpCriticalSection
0x1800263bb  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x1800263c0  test    al, al
0x1800263c2  jz      loc_1800265D2
0x1800263c8  lea     rbx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800263cf  mov     [rsp+128h+var_A8], rbx
0x1800263d7  mov     [rsp+128h+var_A0], rdi
0x1800263df  mov     [rsp+128h+var_98], edi
0x1800263e6  mov     [rsp+128h+var_94], edi
0x1800263ed  mov     [rsp+128h+var_C0], rbx
0x1800263f2  mov     [rsp+128h+var_B8], rdi
0x1800263f7  mov     [rsp+128h+var_B0], edi
0x1800263fb  mov     [rsp+128h+var_AC], edi
0x1800263ff  mov     [rsp+128h+var_E0], rbx
0x180026404  mov     [rsp+128h+var_D8], rdi
0x180026409  mov     [rsp+128h+var_D0], edi
0x18002640d  mov     [rsp+128h+var_CC], edi
0x180026411  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180026418  mov     [rsp+128h+var_88], rax
0x180026420  mov     [rsp+128h+var_78], rbx
0x180026428  mov     [rsp+128h+var_70], rdi
0x180026430  mov     [rsp+128h+var_68], edi
0x180026437  mov     [rsp+128h+var_64], edi
0x18002643e  mov     [rsp+128h+var_60], rbx
0x180026446  mov     [rsp+128h+var_58], rdi
0x18002644e  mov     [rsp+128h+var_50], edi
0x180026455  mov     [rsp+128h+var_4C], edi
0x18002645c  mov     [rsp+128h+var_80], 3
0x180026467  mov     [rsp+128h+var_E8], rdi
0x18002646c  lea     r8, [rsp+128h+var_A8]; struct CBuffer *
0x180026474  lea     rdx, aScardAllreader; "SCard$AllReaders"
0x18002647b  mov     ecx, r14d; unsigned int
0x18002647e  call    ?ListReaders@@YAXKPEBGAEAVCBuffer@@@Z; ListReaders(ulong,ushort const *,CBuffer &)
0x180026483  lea     r15, WideCharStr
0x18002648a  mov     rcx, r15
0x18002648d  cmp     [rsp+128h+var_94], edi
0x180026494  cmova   rcx, [rsp+128h+var_A0]; unsigned __int16 *
0x18002649d  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x1800264a2  mov     [rsp+128h+var_E8], rax
0x1800264a7  mov     r14, rax
0x1800264aa  test    rax, rax
0x1800264ad  jz      loc_180026544
0x1800264b3  lea     r8, [rsp+128h+var_C0]; struct CBuffer *
0x1800264b8  mov     rdx, rax; unsigned __int16 *
0x1800264bb  mov     rcx, rsi; this
0x1800264be  call    ?GetReaderDeviceInstanceId@CSCardUserContext@@QEAAJPEBGAEAVCBuffer@@@Z; CSCardUserContext::GetReaderDeviceInstanceId(ushort const *,CBuffer &)
0x1800264c3  mov     rdx, r13
0x1800264c6  lea     rcx, [rsp+128h+var_88]
0x1800264ce  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x1800264d3  lea     rcx, [rsp+128h+var_88]; this
0x1800264db  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800264e0  cmp     [rsp+128h+var_AC], edi
0x1800264e4  ja      short loc_1800264EB
0x1800264e6  mov     rcx, r15
0x1800264e9  jmp     short loc_1800264F0
0x1800264eb  mov     rcx, [rsp+128h+var_B8]
0x1800264f0  mov     rdx, rax
0x1800264f3  call    cs:__imp__o__wcsicmp
0x1800264f9  test    eax, eax
0x1800264fb  jnz     short loc_18002650B
0x1800264fd  mov     rdx, r14; unsigned __int16 *
0x180026500  lea     rcx, [rsp+128h+var_E0]; struct CBuffer *
0x180026505  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18002650a  nop
0x18002650b  jmp     short loc_180026537
0x18002650d  xor     edi, edi
0x18002650f  lea     rbx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180026516  lea     r15, WideCharStr
0x18002651d  mov     r12, [rsp+128h+arg_18]
0x180026525  mov     r13, [rsp+128h+arg_8]
0x18002652d  mov     rsi, [rsp+128h+var_C8]
0x180026532  mov     r14, [rsp+128h+var_E8]
0x180026537  mov     rcx, r14; unsigned __int16 *
0x18002653a  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18002653f  jmp     loc_1800264A2
0x180026544  cmp     [rsp+128h+var_CC], edi
0x180026548  cmova   r15, [rsp+128h+var_D8]
0x18002654e  mov     rcx, r15; unsigned __int16 *
0x180026551  call    ?MStringCount@@YAKPEBG@Z; MStringCount(ushort const *)
0x180026556  test    eax, eax
0x180026558  jnz     short loc_180026573
0x18002655a  mov     [rsp+128h+var_F8], 8010002Eh
0x180026562  lea     rdx, _TI1K; pThrowInfo
0x180026569  lea     rcx, [rsp+128h+var_F8]; pExceptionObject
0x18002656e  call    _CxxThrowException_0
0x180026573  mov     r9, r12; unsigned int *
0x180026576  mov     r8, [rsp+128h+arg_10]; char *
0x18002657e  lea     rdx, [rsp+128h+var_E0]; struct CBuffer *
0x180026583  mov     rcx, rsi; this
0x180026586  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEADPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,char *,ulong *)
0x18002658b  nop
0x18002658c  lea     rcx, [rsp+128h+var_88]; this
0x180026594  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180026599  nop
0x18002659a  mov     [rsp+128h+var_E0], rbx
0x18002659f  lea     rcx, [rsp+128h+var_E0]; this
0x1800265a4  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800265a9  nop
0x1800265aa  mov     [rsp+128h+var_C0], rbx
0x1800265af  lea     rcx, [rsp+128h+var_C0]; this
0x1800265b4  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800265b9  nop
0x1800265ba  mov     [rsp+128h+var_A8], rbx
0x1800265c2  lea     rcx, [rsp+128h+var_A8]; this
0x1800265ca  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800265cf  nop
0x1800265d0  jmp     short loc_180026622
0x1800265d2  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x1800265d7  lea     rdx, _TI1K; pThrowInfo
0x1800265de  test    al, al
0x1800265e0  jz      short loc_1800265F4
0x1800265e2  mov     [rsp+128h+var_F4], 8010001Dh
0x1800265ea  lea     rcx, [rsp+128h+var_F4]; pExceptionObject
0x1800265ef  call    _CxxThrowException_0
0x1800265f4  mov     [rsp+128h+var_F0], 80100017h
0x1800265fc  lea     rcx, [rsp+128h+var_F0]; pExceptionObject
0x180026601  call    _CxxThrowException_0
0x180026606  mov     [rsp+128h+var_EC], 80100004h
0x18002660e  lea     rdx, _TI1K; pThrowInfo
0x180026615  lea     rcx, [rsp+128h+var_EC]; pExceptionObject
0x18002661a  call    _CxxThrowException_0
0x180026620  jmp     short $+2
0x180026622  mov     eax, [rsp+128h+var_108]
0x180026626  add     rsp, 0F0h
0x18002662d  pop     r15
0x18002662f  pop     r14
0x180026631  pop     r13
0x180026633  pop     r12
0x180026635  pop     rdi
0x180026636  pop     rsi
0x180026637  pop     rbx
0x180026638  retn
```
