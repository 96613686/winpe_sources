# SCardLocateCardsByATRW

- ea: `0x180028160`
- end: `0x1800282f2`
- name: `SCardLocateCardsByATRW`
- size: `402`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPSCARD_ATRMASK rgAtrMasks, DWORD cAtrs, LPSCARD_READERSTATEW rgReaderStates, DWORD cReaders)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180028300`

## callees

- `0x1800040d0`
- `0x18000e3d0`
- `0x1800126f0`
- `0x180024634`
- `0x180028160`
- `0x18002d290`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800281af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800281af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281e5`

## pseudocode

```c
LONG __stdcall SCardLocateCardsByATRW(
        SCARDCONTEXT hContext,
        LPSCARD_ATRMASK rgAtrMasks,
        DWORD cAtrs,
        LPSCARD_READERSTATEW rgReaderStates,
        DWORD cReaders)
{
  LONG v9; // edi
  CHandleList *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v13; // r15
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rax
  int v16; // ecx
  DWORD i; // ebx
  const unsigned __int16 *v18; // rdx
  ulong pExceptionObject; // [rsp+38h] [rbp-70h] BYREF
  ulong v21; // [rsp+3Ch] [rbp-6Ch] BYREF
  ulong v22; // [rsp+40h] [rbp-68h] BYREF
  const int *v23; // [rsp+48h] [rbp-60h] BYREF
  const unsigned __int16 *v24; // [rsp+50h] [rbp-58h]
  int v25; // [rsp+58h] [rbp-50h]
  int v26; // [rsp+5Ch] [rbp-4Ch]
  char *v27; // [rsp+68h] [rbp-40h]

  v9 = 0;
  if ( !rgReaderStates )
  {
    pExceptionObject = -2146435068;
    throw &pExceptionObject;
  }
  v10 = g_phlContexts;
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
  v27 = (char *)g_phlContexts + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
  HandlePtr = CHandleList::GetHandlePtr(v10, hContext);
  if ( !HandlePtr )
  {
    v21 = 6;
    throw &v21;
  }
  v13 = *(_QWORD *)HandlePtr;
  LeaveCriticalSection(v11);
  if ( *(_DWORD *)(v13 + 16) )
  {
    v22 = -2146435042;
    throw &v22;
  }
  v14 = *(_QWORD *)(v13 + 128);
  if ( v14 )
    return RedirectedSCardLocateCardsByATRW(v14, rgAtrMasks, cAtrs, rgReaderStates, cReaders);
  v23 = &CBuffer::`vftable';
  v15 = 0;
  v24 = 0;
  v25 = 0;
  v16 = 0;
  v26 = 0;
  for ( i = 0; i < cReaders; ++i )
  {
    MStrAdd((struct CBuffer *)&v23, rgReaderStates[(unsigned __int64)i].szReader);
    v16 = v26;
    v15 = v24;
  }
  v18 = &WideCharStr;
  if ( v16 )
    v18 = v15;
  CSCardUserContext::LocateCards((CSCardUserContext *)v13, v18, rgAtrMasks, cAtrs, rgReaderStates, cReaders);
  v23 = &CBuffer::`vftable';
  CBuffer::Clear((CBuffer *)&v23);
  return v9;
}

```

## disassembly

```asm
0x180028160  push    rbx
0x180028162  push    rsi
0x180028163  push    rdi
0x180028164  push    r12
0x180028166  push    r13
0x180028168  push    r14
0x18002816a  push    r15
0x18002816c  sub     rsp, 70h
0x180028170  mov     rsi, r9
0x180028173  mov     r12d, r8d
0x180028176  mov     r13, rdx
0x180028179  mov     r15, rcx
0x18002817c  xor     edi, edi
0x18002817e  test    r9, r9
0x180028181  jnz     short loc_18002819C
0x180028183  mov     [rsp+0A8h+pExceptionObject], 80100004h
0x18002818b  lea     rdx, _TI1K; pThrowInfo
0x180028192  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180028197  call    _CxxThrowException_0
0x18002819c  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x1800281a3  lea     r14, [rbx+20h]
0x1800281a7  mov     [rsp+0A8h+var_40], r14
0x1800281ac  mov     rcx, r14; lpCriticalSection
0x1800281af  call    cs:__imp_EnterCriticalSection
0x1800281b5  nop
0x1800281b6  mov     rdx, r15; unsigned __int64
0x1800281b9  mov     rcx, rbx; this
0x1800281bc  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x1800281c1  test    rax, rax
0x1800281c4  jnz     short loc_1800281DF
0x1800281c6  mov     [rsp+0A8h+var_6C], 6
0x1800281ce  lea     rdx, _TI1K; pThrowInfo
0x1800281d5  lea     rcx, [rsp+0A8h+var_6C]; pExceptionObject
0x1800281da  call    _CxxThrowException_0
0x1800281df  mov     r15, [rax]
0x1800281e2  mov     rcx, r14; lpCriticalSection
0x1800281e5  call    cs:__imp_LeaveCriticalSection
0x1800281eb  xor     r8d, r8d
0x1800281ee  cmp     [r15+10h], r8d
0x1800281f2  jz      short loc_18002820D
0x1800281f4  mov     [rsp+0A8h+var_68], 8010001Eh
0x1800281fc  lea     rdx, _TI1K; pThrowInfo
0x180028203  lea     rcx, [rsp+0A8h+var_68]; pExceptionObject
0x180028208  call    _CxxThrowException_0
0x18002820d  mov     rcx, [r15+80h]; unsigned __int64
0x180028214  test    rcx, rcx
0x180028217  jz      short loc_18002823D
0x180028219  mov     eax, [rsp+0A8h+cReaders]
0x180028220  mov     dword ptr [rsp+0A8h+var_88], eax; unsigned int
0x180028224  mov     r9, rsi; struct SCARD_READERSTATEW *
0x180028227  mov     r8d, r12d; unsigned int
0x18002822a  mov     rdx, r13; struct _SCARD_ATRMASK *
0x18002822d  call    ?RedirectedSCardLocateCardsByATRW@@YAJ_KPEAU_SCARD_ATRMASK@@KPEAUSCARD_READERSTATEW@@K@Z; RedirectedSCardLocateCardsByATRW(unsigned __int64,_SCARD_ATRMASK *,ulong,SCARD_READERSTATEW *,ulong)
0x180028232  mov     edi, eax
0x180028234  mov     [rsp+0A8h+var_78], eax
0x180028238  jmp     loc_1800282D8
0x18002823d  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180028244  mov     [rsp+0A8h+var_60], rax
0x180028249  mov     rax, r8
0x18002824c  mov     [rsp+0A8h+var_58], rax
0x180028251  mov     [rsp+0A8h+var_50], r8d
0x180028256  mov     ecx, r8d
0x180028259  mov     [rsp+0A8h+var_4C], ecx
0x18002825d  mov     [rsp+0A8h+var_74], r8d
0x180028262  mov     ebx, r8d
0x180028265  mov     [rsp+0A8h+var_74], ebx
0x180028269  mov     r14d, [rsp+0A8h+cReaders]
0x180028271  cmp     ebx, r14d
0x180028274  jnb     short loc_18002829B
0x180028276  mov     edx, ebx
0x180028278  shl     rdx, 6
0x18002827c  mov     rdx, [rdx+rsi]; unsigned __int16 *
0x180028280  lea     rcx, [rsp+0A8h+var_60]; struct CBuffer *
0x180028285  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18002828a  inc     ebx
0x18002828c  mov     [rsp+0A8h+var_74], ebx
0x180028290  mov     ecx, [rsp+0A8h+var_4C]
0x180028294  mov     rax, [rsp+0A8h+var_58]
0x180028299  jmp     short loc_180028271
0x18002829b  lea     rdx, WideCharStr
0x1800282a2  test    ecx, ecx
0x1800282a4  cmovnz  rdx, rax; unsigned __int16 *
0x1800282a8  mov     [rsp+0A8h+var_80], r14d; unsigned int
0x1800282ad  mov     [rsp+0A8h+var_88], rsi; struct SCARD_READERSTATEW *
0x1800282b2  mov     r9d, r12d; unsigned int
0x1800282b5  mov     r8, r13; struct _SCARD_ATRMASK *
0x1800282b8  mov     rcx, r15; this
0x1800282bb  call    ?LocateCards@CSCardUserContext@@QEAAXPEBGPEAU_SCARD_ATRMASK@@KPEAUSCARD_READERSTATEW@@K@Z; CSCardUserContext::LocateCards(ushort const *,_SCARD_ATRMASK *,ulong,SCARD_READERSTATEW *,ulong)
0x1800282c0  nop
0x1800282c1  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800282c8  mov     [rsp+0A8h+var_60], rax
0x1800282cd  lea     rcx, [rsp+0A8h+var_60]; this
0x1800282d2  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800282d7  nop
0x1800282d8  jmp     short loc_1800282E0
0x1800282da  jmp     short $+2
0x1800282dc  mov     edi, [rsp+0A8h+var_78]
0x1800282e0  mov     eax, edi
0x1800282e2  add     rsp, 70h
0x1800282e6  pop     r15
0x1800282e8  pop     r14
0x1800282ea  pop     r13
0x1800282ec  pop     r12
0x1800282ee  pop     rdi
0x1800282ef  pop     rsi
0x1800282f0  pop     rbx
0x1800282f1  retn
```
