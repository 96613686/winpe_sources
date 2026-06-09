# SCardForgetReaderGroupA

- ea: `0x180025300`
- end: `0x18002547b`
- name: `SCardForgetReaderGroupA`
- size: `379`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCSTR szGroupName)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800093e4`
- `0x18000e090`
- `0x18000e680`
- `0x180010898`
- `0x180011b0c`
- `0x1800126f0`
- `0x180025300`
- `0x18002ad8c`
- `0x18002b490`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025370`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025370`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800253a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800253a6`

## pseudocode

```c
LONG __stdcall SCardForgetReaderGroupA(SCARDCONTEXT hContext, LPCSTR szGroupName)
{
  LONG v4; // edi
  CHandleList *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // r14
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v8; // rbx
  __int64 v9; // rsi
  int v10; // ebx
  const unsigned __int16 *v11; // rax
  ulong pExceptionObject; // [rsp+24h] [rbp-74h] BYREF
  ulong v14; // [rsp+28h] [rbp-70h] BYREF
  ulong v15; // [rsp+2Ch] [rbp-6Ch] BYREF
  void **v16; // [rsp+40h] [rbp-58h] BYREF
  int v17; // [rsp+48h] [rbp-50h]
  const int *v18; // [rsp+50h] [rbp-48h]
  __int64 v19; // [rsp+58h] [rbp-40h]
  int v20; // [rsp+60h] [rbp-38h]
  int v21; // [rsp+64h] [rbp-34h]
  const int *v22; // [rsp+68h] [rbp-30h]
  __int64 v23; // [rsp+70h] [rbp-28h]
  int v24; // [rsp+78h] [rbp-20h]
  int v25; // [rsp+7Ch] [rbp-1Ch]

  v4 = 0;
  v16 = &CTextString::`vftable';
  v18 = &CBuffer::`vftable';
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = &CBuffer::`vftable';
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v17 = 3;
  if ( hContext )
  {
    v5 = g_phlContexts;
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    HandlePtr = CHandleList::GetHandlePtr(v5, hContext);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v8 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v6);
    if ( *(_DWORD *)(v8 + 16) )
    {
      v14 = -2146435042;
      throw &v14;
    }
    v9 = *(_QWORD *)(v8 + 128);
    if ( v9 )
      goto LABEL_11;
    v10 = *(_DWORD *)(v8 + 28);
  }
  else
  {
    v10 = 2;
    v9 = 0;
  }
  if ( RedirectionContextIsLocal(0) )
  {
    CTextString::operator=(&v16, szGroupName);
    v11 = CTextString::Unicode((CTextString *)&v16);
    ForgetReaderGroup(v10, v11);
    goto LABEL_14;
  }
LABEL_11:
  if ( RedirectDisabled() )
  {
    v15 = -2146435043;
    throw &v15;
  }
  v4 = I_ContextAndStringCallWithLongReturn(v9, (const unsigned __int8 *)szGroupName, 0, 0x90058u);
LABEL_14:
  CTextString::~CTextString((CTextString *)&v16);
  return v4;
}

```

## disassembly

```asm
0x180025300  mov     r11, rsp
0x180025303  mov     [r11+8], rbx
0x180025307  mov     [r11+10h], rsi
0x18002530b  push    rdi
0x18002530c  push    r14
0x18002530e  push    r15
0x180025310  sub     rsp, 80h
0x180025317  mov     r15, rdx
0x18002531a  mov     rsi, rcx
0x18002531d  xor     edi, edi
0x18002531f  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180025326  mov     [r11-58h], rax
0x18002532a  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180025331  mov     [r11-48h], rax
0x180025335  mov     [r11-40h], rdi
0x180025339  mov     [rsp+98h+var_38], edi
0x18002533d  mov     [rsp+98h+var_34], edi
0x180025341  mov     [r11-30h], rax
0x180025345  mov     [r11-28h], rdi
0x180025349  mov     [rsp+98h+var_20], edi
0x18002534d  mov     [rsp+98h+var_1C], edi
0x180025351  mov     [rsp+98h+var_50], 3
0x180025359  test    rcx, rcx
0x18002535c  jz      short loc_1800253DC
0x18002535e  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180025365  lea     r14, [rbx+20h]
0x180025369  mov     [r11+18h], r14
0x18002536d  mov     rcx, r14; lpCriticalSection
0x180025370  call    cs:__imp_EnterCriticalSection
0x180025376  nop
0x180025377  mov     rdx, rsi; unsigned __int64
0x18002537a  mov     rcx, rbx; this
0x18002537d  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180025382  test    rax, rax
0x180025385  jnz     short loc_1800253A0
0x180025387  mov     [rsp+98h+pExceptionObject], 6
0x18002538f  lea     rdx, _TI1K; pThrowInfo
0x180025396  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002539b  call    _CxxThrowException_0
0x1800253a0  mov     rbx, [rax]
0x1800253a3  mov     rcx, r14; lpCriticalSection
0x1800253a6  call    cs:__imp_LeaveCriticalSection
0x1800253ac  cmp     dword ptr [rbx+10h], 0
0x1800253b0  jz      short loc_1800253CB
0x1800253b2  mov     [rsp+98h+var_70], 8010001Eh
0x1800253ba  lea     rdx, _TI1K; pThrowInfo
0x1800253c1  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x1800253c6  call    _CxxThrowException_0
0x1800253cb  mov     rsi, [rbx+80h]
0x1800253d2  test    rsi, rsi
0x1800253d5  jnz     short loc_180025411
0x1800253d7  mov     ebx, [rbx+1Ch]
0x1800253da  jmp     short loc_1800253E3
0x1800253dc  mov     ebx, 2
0x1800253e1  xor     esi, esi
0x1800253e3  xor     ecx, ecx; lpCriticalSection
0x1800253e5  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x1800253ea  test    al, al
0x1800253ec  jz      short loc_180025411
0x1800253ee  mov     rdx, r15
0x1800253f1  lea     rcx, [rsp+98h+var_58]
0x1800253f6  call    ??4CTextString@@QEAAPEBDPEBD@Z; CTextString::operator=(char const *)
0x1800253fb  lea     rcx, [rsp+98h+var_58]; this
0x180025400  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180025405  mov     rdx, rax; unsigned __int16 *
0x180025408  mov     ecx, ebx; unsigned int
0x18002540a  call    ?ForgetReaderGroup@@YAXKPEBG@Z; ForgetReaderGroup(ulong,ushort const *)
0x18002540f  jmp     short loc_18002544D
0x180025411  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180025416  test    al, al
0x180025418  jz      short loc_180025433
0x18002541a  mov     [rsp+98h+var_6C], 8010001Dh
0x180025422  lea     rdx, _TI1K; pThrowInfo
0x180025429  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x18002542e  call    _CxxThrowException_0
0x180025433  mov     r9d, 90058h; unsigned int
0x180025439  xor     r8d, r8d; int
0x18002543c  mov     rdx, r15; unsigned __int8 *
0x18002543f  mov     rcx, rsi; unsigned __int64
0x180025442  call    ?I_ContextAndStringCallWithLongReturn@@YAJ_KPEBEHK@Z; I_ContextAndStringCallWithLongReturn(unsigned __int64,uchar const *,int,ulong)
0x180025447  mov     edi, eax
0x180025449  mov     [rsp+98h+var_78], eax
0x18002544d  lea     rcx, [rsp+98h+var_58]; this
0x180025452  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180025457  nop
0x180025458  jmp     short loc_180025460
0x18002545a  jmp     short $+2
0x18002545c  mov     edi, [rsp+98h+var_78]
0x180025460  mov     eax, edi
0x180025462  lea     r11, [rsp+98h+var_18]
0x18002546a  mov     rbx, [r11+20h]
0x18002546e  mov     rsi, [r11+28h]
0x180025472  mov     rsp, r11
0x180025475  pop     r15
0x180025477  pop     r14
0x180025479  pop     rdi
0x18002547a  retn
```
