# SCardListReaderGroupsW

- ea: `0x180028000`
- end: `0x180028156`
- name: `SCardListReaderGroupsW`
- size: `342`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPWSTR mszGroups, LPDWORD pcchGroups)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180003430`
- `0x1800093e4`
- `0x18000e3d0`
- `0x180010898`
- `0x1800126f0`
- `0x180028000`
- `0x18002a8ec`
- `0x18002ba08`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028049`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028049`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002807f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002807f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LONG __stdcall SCardListReaderGroupsW(SCARDCONTEXT hContext, LPWSTR mszGroups, LPDWORD pcchGroups)
{
  LONG v6; // edi
  CHandleList *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v10; // rbx
  struct _REDIR_LOCAL_SCARDCONTEXT *v11; // rsi
  unsigned int v12; // r14d
  ulong pExceptionObject; // [rsp+24h] [rbp-64h] BYREF
  ulong v15; // [rsp+28h] [rbp-60h] BYREF
  ulong v16; // [rsp+2Ch] [rbp-5Ch] BYREF
  LONG v17; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-50h] BYREF
  int v19; // [rsp+48h] [rbp-40h]
  int v20; // [rsp+4Ch] [rbp-3Ch]

  v6 = 0;
  try
  {
    v18[0] = &CBuffer::`vftable';
    v18[1] = 0;
    v19 = 0;
    v20 = 0;
    if ( hContext )
    {
      v7 = g_phlContexts;
      v8 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
      HandlePtr = CHandleList::GetHandlePtr(v7, hContext);
      if ( !HandlePtr )
      {
        pExceptionObject = 6;
        throw &pExceptionObject;
      }
      v10 = *(_QWORD *)HandlePtr;
      LeaveCriticalSection(v8);
      if ( *(_DWORD *)(v10 + 16) )
      {
        v15 = -2146435042;
        throw &v15;
      }
      v11 = *(struct _REDIR_LOCAL_SCARDCONTEXT **)(v10 + 128);
      if ( v11 )
        goto LABEL_12;
      v12 = *(_DWORD *)(v10 + 28);
    }
    else
    {
      v10 = 0;
      v11 = 0;
      v12 = 2;
    }
    if ( RedirectionContextIsLocal(0) )
    {
      ListReaderGroups(v12, (struct CBuffer *)v18);
      PlaceMultiResult((struct CSCardUserContext *)v10, (struct CBuffer *)v18, mszGroups, pcchGroups);
LABEL_15:
      v18[0] = &CBuffer::`vftable';
      CBuffer::Clear((CBuffer *)v18);
      return v6;
    }
LABEL_12:
    if ( RedirectDisabled() )
    {
      v16 = -2146435043;
      throw &v16;
    }
    v6 = I_SCardListReaderGroups(v11, (unsigned __int8 *)mszGroups, pcchGroups, 1);
    goto LABEL_15;
  }
  catch ( ulong v17 )
  {
    return v17;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v6;
}

```

## disassembly

```asm
0x180028000  mov     r11, rsp
0x180028003  push    rbx
0x180028004  push    rsi
0x180028005  push    rdi
0x180028006  push    r12
0x180028008  push    r14
0x18002800a  push    r15
0x18002800c  sub     rsp, 58h
0x180028010  mov     r15, r8
0x180028013  mov     r12, rdx
0x180028016  mov     rsi, rcx
0x180028019  xor     edi, edi
0x18002801b  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180028022  mov     [r11-50h], rax
0x180028026  mov     [r11-48h], rdi
0x18002802a  mov     [rsp+88h+var_40], edi
0x18002802e  mov     [rsp+88h+var_3C], edi
0x180028032  test    rcx, rcx
0x180028035  jz      short loc_1800280B6
0x180028037  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18002803e  lea     r14, [rbx+20h]
0x180028042  mov     [r11+20h], r14
0x180028046  mov     rcx, r14; lpCriticalSection
0x180028049  call    cs:__imp_EnterCriticalSection
0x18002804f  nop
0x180028050  mov     rdx, rsi; unsigned __int64
0x180028053  mov     rcx, rbx; this
0x180028056  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x18002805b  test    rax, rax
0x18002805e  jnz     short loc_180028079
0x180028060  mov     [rsp+88h+pExceptionObject], 6
0x180028068  lea     rdx, _TI1K; pThrowInfo
0x18002806f  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180028074  call    _CxxThrowException_0
0x180028079  mov     rbx, [rax]
0x18002807c  mov     rcx, r14; lpCriticalSection
0x18002807f  call    cs:__imp_LeaveCriticalSection
0x180028085  cmp     dword ptr [rbx+10h], 0
0x180028089  jz      short loc_1800280A4
0x18002808b  mov     [rsp+88h+var_60], 8010001Eh
0x180028093  lea     rdx, _TI1K; pThrowInfo
0x18002809a  lea     rcx, [rsp+88h+var_60]; pExceptionObject
0x18002809f  call    _CxxThrowException_0
0x1800280a4  mov     rsi, [rbx+80h]
0x1800280ab  test    rsi, rsi
0x1800280ae  jnz     short loc_1800280EB
0x1800280b0  mov     r14d, [rbx+1Ch]
0x1800280b4  jmp     short loc_1800280BE
0x1800280b6  xor     ebx, ebx
0x1800280b8  xor     esi, esi
0x1800280ba  lea     r14d, [rbx+2]
0x1800280be  xor     ecx, ecx; lpCriticalSection
0x1800280c0  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x1800280c5  test    al, al
0x1800280c7  jz      short loc_1800280EB
0x1800280c9  lea     rdx, [rsp+88h+var_50]; struct CBuffer *
0x1800280ce  mov     ecx, r14d; unsigned int
0x1800280d1  call    ?ListReaderGroups@@YAXKAEAVCBuffer@@@Z; ListReaderGroups(ulong,CBuffer &)
0x1800280d6  mov     r9, r15; unsigned int *
0x1800280d9  mov     r8, r12; unsigned __int16 *
0x1800280dc  lea     rdx, [rsp+88h+var_50]; struct CBuffer *
0x1800280e1  mov     rcx, rbx; this
0x1800280e4  call    ?PlaceMultiResult@@YAXPEAVCSCardUserContext@@AEAVCBuffer@@PEAGPEAK@Z; PlaceMultiResult(CSCardUserContext *,CBuffer &,ushort *,ulong *)
0x1800280e9  jmp     short loc_180028127
0x1800280eb  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x1800280f0  test    al, al
0x1800280f2  jz      short loc_18002810D
0x1800280f4  mov     [rsp+88h+var_5C], 8010001Dh
0x1800280fc  lea     rdx, _TI1K; pThrowInfo
0x180028103  lea     rcx, [rsp+88h+var_5C]; pExceptionObject
0x180028108  call    _CxxThrowException_0
0x18002810d  mov     r9d, 1; int
0x180028113  mov     r8, r15; unsigned int *
0x180028116  mov     rdx, r12; unsigned __int8 *
0x180028119  mov     rcx, rsi; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18002811c  call    ?I_SCardListReaderGroups@@YAJ_KPEAEPEAKH@Z; I_SCardListReaderGroups(unsigned __int64,uchar *,ulong *,int)
0x180028121  mov     edi, eax
0x180028123  mov     [rsp+88h+var_68], eax
0x180028127  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002812e  mov     [rsp+88h+var_50], rax
0x180028133  lea     rcx, [rsp+88h+var_50]; this
0x180028138  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x18002813d  nop
0x18002813e  jmp     short loc_180028146
0x180028140  jmp     short $+2
0x180028142  mov     edi, [rsp+88h+var_68]
0x180028146  mov     eax, edi
0x180028148  add     rsp, 58h
0x18002814c  pop     r15
0x18002814e  pop     r14
0x180028150  pop     r12
0x180028152  pop     rdi
0x180028153  pop     rsi
0x180028154  pop     rbx
0x180028155  retn
```
