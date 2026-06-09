# SCardForgetReaderGroupW

- ea: `0x1800274a0`
- end: `0x18002761e`
- name: `SCardForgetReaderGroupW`
- size: `382`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR szGroupName)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800093e4`
- `0x18000e090`
- `0x18000e680`
- `0x180010898`
- `0x1800126f0`
- `0x180012d80`
- `0x1800274a0`
- `0x18002ad8c`
- `0x18002b490`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027510`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027510`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027546`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LONG __stdcall SCardForgetReaderGroupW(SCARDCONTEXT hContext, LPCWSTR szGroupName)
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
  LONG v16; // [rsp+30h] [rbp-68h] BYREF
  void **v17; // [rsp+40h] [rbp-58h] BYREF
  int v18; // [rsp+48h] [rbp-50h]
  const int *v19; // [rsp+50h] [rbp-48h]
  __int64 v20; // [rsp+58h] [rbp-40h]
  int v21; // [rsp+60h] [rbp-38h]
  int v22; // [rsp+64h] [rbp-34h]
  const int *v23; // [rsp+68h] [rbp-30h]
  __int64 v24; // [rsp+70h] [rbp-28h]
  int v25; // [rsp+78h] [rbp-20h]
  int v26; // [rsp+7Ch] [rbp-1Ch]

  v4 = 0;
  try
  {
    v17 = &CTextString::`vftable';
    v19 = &CBuffer::`vftable';
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = &CBuffer::`vftable';
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v18 = 3;
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
        goto LABEL_12;
      v10 = *(_DWORD *)(v8 + 28);
    }
    else
    {
      v10 = 2;
      v9 = 0;
    }
    if ( RedirectionContextIsLocal(0) )
    {
      CTextString::operator=(&v17, szGroupName);
      v11 = CTextString::Unicode((CTextString *)&v17);
      ForgetReaderGroup(v10, v11);
LABEL_15:
      CTextString::~CTextString((CTextString *)&v17);
      return v4;
    }
LABEL_12:
    if ( RedirectDisabled() )
    {
      v15 = -2146435043;
      throw &v15;
    }
    v4 = I_ContextAndStringCallWithLongReturn(v9, (const unsigned __int8 *)szGroupName, 1, 0x9005Cu);
    goto LABEL_15;
  }
  catch ( ulong v16 )
  {
    return v16;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v4;
}

```

## disassembly

```asm
0x1800274a0  mov     r11, rsp
0x1800274a3  mov     [r11+8], rbx
0x1800274a7  mov     [r11+10h], rsi
0x1800274ab  push    rdi
0x1800274ac  push    r14
0x1800274ae  push    r15
0x1800274b0  sub     rsp, 80h
0x1800274b7  mov     r15, rdx
0x1800274ba  mov     rsi, rcx
0x1800274bd  xor     edi, edi
0x1800274bf  lea     rax, ??_7CTextString@@6B@; const CTextString::`vftable'
0x1800274c6  mov     [r11-58h], rax
0x1800274ca  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800274d1  mov     [r11-48h], rax
0x1800274d5  mov     [r11-40h], rdi
0x1800274d9  mov     [rsp+98h+var_38], edi
0x1800274dd  mov     [rsp+98h+var_34], edi
0x1800274e1  mov     [r11-30h], rax
0x1800274e5  mov     [r11-28h], rdi
0x1800274e9  mov     [rsp+98h+var_20], edi
0x1800274ed  mov     [rsp+98h+var_1C], edi
0x1800274f1  mov     [rsp+98h+var_50], 3
0x1800274f9  test    rcx, rcx
0x1800274fc  jz      short loc_18002757C
0x1800274fe  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180027505  lea     r14, [rbx+20h]
0x180027509  mov     [r11+18h], r14
0x18002750d  mov     rcx, r14; lpCriticalSection
0x180027510  call    cs:__imp_EnterCriticalSection
0x180027516  nop
0x180027517  mov     rdx, rsi; unsigned __int64
0x18002751a  mov     rcx, rbx; this
0x18002751d  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180027522  test    rax, rax
0x180027525  jnz     short loc_180027540
0x180027527  mov     [rsp+98h+pExceptionObject], 6
0x18002752f  lea     rdx, _TI1K; pThrowInfo
0x180027536  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002753b  call    _CxxThrowException_0
0x180027540  mov     rbx, [rax]
0x180027543  mov     rcx, r14; lpCriticalSection
0x180027546  call    cs:__imp_LeaveCriticalSection
0x18002754c  cmp     dword ptr [rbx+10h], 0
0x180027550  jz      short loc_18002756B
0x180027552  mov     [rsp+98h+var_70], 8010001Eh
0x18002755a  lea     rdx, _TI1K; pThrowInfo
0x180027561  lea     rcx, [rsp+98h+var_70]; pExceptionObject
0x180027566  call    _CxxThrowException_0
0x18002756b  mov     rsi, [rbx+80h]
0x180027572  test    rsi, rsi
0x180027575  jnz     short loc_1800275B1
0x180027577  mov     ebx, [rbx+1Ch]
0x18002757a  jmp     short loc_180027583
0x18002757c  mov     ebx, 2
0x180027581  xor     esi, esi
0x180027583  xor     ecx, ecx; lpCriticalSection
0x180027585  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x18002758a  test    al, al
0x18002758c  jz      short loc_1800275B1
0x18002758e  mov     rdx, r15
0x180027591  lea     rcx, [rsp+98h+var_58]
0x180027596  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18002759b  lea     rcx, [rsp+98h+var_58]; this
0x1800275a0  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800275a5  mov     rdx, rax; unsigned __int16 *
0x1800275a8  mov     ecx, ebx; unsigned int
0x1800275aa  call    ?ForgetReaderGroup@@YAXKPEBG@Z; ForgetReaderGroup(ulong,ushort const *)
0x1800275af  jmp     short loc_1800275F0
0x1800275b1  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x1800275b6  test    al, al
0x1800275b8  jz      short loc_1800275D3
0x1800275ba  mov     [rsp+98h+var_6C], 8010001Dh
0x1800275c2  lea     rdx, _TI1K; pThrowInfo
0x1800275c9  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x1800275ce  call    _CxxThrowException_0
0x1800275d3  mov     r9d, 9005Ch; unsigned int
0x1800275d9  mov     r8d, 1; int
0x1800275df  mov     rdx, r15; unsigned __int8 *
0x1800275e2  mov     rcx, rsi; unsigned __int64
0x1800275e5  call    ?I_ContextAndStringCallWithLongReturn@@YAJ_KPEBEHK@Z; I_ContextAndStringCallWithLongReturn(unsigned __int64,uchar const *,int,ulong)
0x1800275ea  mov     edi, eax
0x1800275ec  mov     [rsp+98h+var_78], eax
0x1800275f0  lea     rcx, [rsp+98h+var_58]; this
0x1800275f5  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x1800275fa  nop
0x1800275fb  jmp     short loc_180027603
0x1800275fd  jmp     short $+2
0x1800275ff  mov     edi, [rsp+98h+var_78]
0x180027603  mov     eax, edi
0x180027605  lea     r11, [rsp+98h+var_18]
0x18002760d  mov     rbx, [r11+20h]
0x180027611  mov     rsi, [r11+28h]
0x180027615  mov     rsp, r11
0x180027618  pop     r15
0x18002761a  pop     r14
0x18002761c  pop     rdi
0x18002761d  retn
```
