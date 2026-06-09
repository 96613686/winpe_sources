# SCardRemoveReaderFromGroupW

- ea: `0x180028790`
- end: `0x180028984`
- name: `SCardRemoveReaderFromGroupW`
- size: `500`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR szReaderName, LPCWSTR szGroupName)`
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
- `0x180028790`
- `0x18002b2d8`
- `0x18002b734`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028838`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002886e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002886e`

## pseudocode

```c
LONG __stdcall SCardRemoveReaderFromGroupW(SCARDCONTEXT hContext, LPCWSTR szReaderName, LPCWSTR szGroupName)
{
  LONG v6; // edi
  CHandleList *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v10; // rbx
  __int64 v11; // rsi
  int v12; // r14d
  const unsigned __int16 *v13; // rbx
  const unsigned __int16 *v14; // rax
  ulong pExceptionObject; // [rsp+34h] [rbp-C4h] BYREF
  ulong v17; // [rsp+38h] [rbp-C0h] BYREF
  ulong v18; // [rsp+3Ch] [rbp-BCh] BYREF
  void **v19; // [rsp+50h] [rbp-A8h] BYREF
  int v20; // [rsp+58h] [rbp-A0h]
  const int *v21; // [rsp+60h] [rbp-98h]
  __int64 v22; // [rsp+68h] [rbp-90h]
  int v23; // [rsp+70h] [rbp-88h]
  int v24; // [rsp+74h] [rbp-84h]
  const int *v25; // [rsp+78h] [rbp-80h]
  __int64 v26; // [rsp+80h] [rbp-78h]
  int v27; // [rsp+88h] [rbp-70h]
  int v28; // [rsp+8Ch] [rbp-6Ch]
  void **v29; // [rsp+90h] [rbp-68h] BYREF
  int v30; // [rsp+98h] [rbp-60h]
  const int *v31; // [rsp+A0h] [rbp-58h]
  __int64 v32; // [rsp+A8h] [rbp-50h]
  int v33; // [rsp+B0h] [rbp-48h]
  int v34; // [rsp+B4h] [rbp-44h]
  const int *v35; // [rsp+B8h] [rbp-40h]
  __int64 v36; // [rsp+C0h] [rbp-38h]
  int v37; // [rsp+C8h] [rbp-30h]
  int v38; // [rsp+CCh] [rbp-2Ch]

  v6 = 0;
  v29 = &CTextString::`vftable';
  v31 = &CBuffer::`vftable';
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = &CBuffer::`vftable';
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v30 = 3;
  v19 = &CTextString::`vftable';
  v21 = &CBuffer::`vftable';
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = &CBuffer::`vftable';
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v20 = 3;
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
      v17 = -2146435042;
      throw &v17;
    }
    v11 = *(_QWORD *)(v10 + 128);
    if ( v11 )
      goto LABEL_11;
    v12 = *(_DWORD *)(v10 + 28);
  }
  else
  {
    v12 = 2;
    v11 = 0;
  }
  if ( RedirectionContextIsLocal(0) )
  {
    CTextString::operator=(&v29, szReaderName);
    CTextString::operator=(&v19, szGroupName);
    v13 = CTextString::Unicode((CTextString *)&v19);
    v14 = CTextString::Unicode((CTextString *)&v29);
    RemoveReaderFromGroup(v12, v14, v13);
    goto LABEL_14;
  }
LABEL_11:
  if ( RedirectDisabled() )
  {
    v18 = -2146435043;
    throw &v18;
  }
  v6 = I_ContextAndTwoStringCallWithLongReturn(
         v11,
         (const unsigned __int8 *)szReaderName,
         (const unsigned __int8 *)szGroupName,
         1,
         0x9007Cu);
LABEL_14:
  CTextString::~CTextString((CTextString *)&v19);
  CTextString::~CTextString((CTextString *)&v29);
  return v6;
}

```

## disassembly

```asm
0x180028790  mov     r11, rsp
0x180028793  mov     [r11+8], rbx
0x180028797  mov     [r11+10h], rsi
0x18002879b  push    rdi
0x18002879c  push    r12
0x18002879e  push    r13
0x1800287a0  push    r14
0x1800287a2  push    r15
0x1800287a4  sub     rsp, 0D0h
0x1800287ab  mov     r15, r8
0x1800287ae  mov     r12, rdx
0x1800287b1  mov     r14, rcx
0x1800287b4  xor     r13d, r13d
0x1800287b7  mov     edi, r13d
0x1800287ba  lea     rcx, ??_7CTextString@@6B@; const CTextString::`vftable'
0x1800287c1  mov     [r11-68h], rcx
0x1800287c5  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800287cc  mov     [r11-58h], rax
0x1800287d0  mov     [r11-50h], r13
0x1800287d4  mov     [r11-48h], r13d
0x1800287d8  mov     [r11-44h], r13d
0x1800287dc  mov     [r11-40h], rax
0x1800287e0  mov     [r11-38h], r13
0x1800287e4  mov     [r11-30h], r13d
0x1800287e8  mov     [r11-2Ch], r13d
0x1800287ec  lea     edx, [r13+3]
0x1800287f0  mov     [r11-60h], edx
0x1800287f4  mov     [rsp+0F8h+var_A8], rcx
0x1800287f9  mov     [rsp+0F8h+var_98], rax
0x1800287fe  mov     [rsp+0F8h+var_90], r13
0x180028803  mov     [rsp+0F8h+var_88], r13d
0x180028808  mov     [rsp+0F8h+var_84], r13d
0x18002880d  mov     [r11-80h], rax
0x180028811  mov     [r11-78h], r13
0x180028815  mov     [r11-70h], r13d
0x180028819  mov     [r11-6Ch], r13d
0x18002881d  mov     [rsp+0F8h+var_A0], edx
0x180028821  test    r14, r14
0x180028824  jz      short loc_1800288A5
0x180028826  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x18002882d  lea     rsi, [rbx+20h]
0x180028831  mov     [r11+20h], rsi
0x180028835  mov     rcx, rsi; lpCriticalSection
0x180028838  call    cs:__imp_EnterCriticalSection
0x18002883e  nop
0x18002883f  mov     rdx, r14; unsigned __int64
0x180028842  mov     rcx, rbx; this
0x180028845  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x18002884a  test    rax, rax
0x18002884d  jnz     short loc_180028868
0x18002884f  mov     [rsp+0F8h+pExceptionObject], 6
0x180028857  lea     rdx, _TI1K; pThrowInfo
0x18002885e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180028863  call    _CxxThrowException_0
0x180028868  mov     rbx, [rax]
0x18002886b  mov     rcx, rsi; lpCriticalSection
0x18002886e  call    cs:__imp_LeaveCriticalSection
0x180028874  cmp     [rbx+10h], r13d
0x180028878  jz      short loc_180028893
0x18002887a  mov     [rsp+0F8h+var_C0], 8010001Eh
0x180028882  lea     rdx, _TI1K; pThrowInfo
0x180028889  lea     rcx, [rsp+0F8h+var_C0]; pExceptionObject
0x18002888e  call    _CxxThrowException_0
0x180028893  mov     rsi, [rbx+80h]
0x18002889a  test    rsi, rsi
0x18002889d  jnz     short loc_180028900
0x18002889f  mov     r14d, [rbx+1Ch]
0x1800288a3  jmp     short loc_1800288AE
0x1800288a5  mov     r14d, 2
0x1800288ab  mov     rsi, r13
0x1800288ae  xor     ecx, ecx; lpCriticalSection
0x1800288b0  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x1800288b5  test    al, al
0x1800288b7  jz      short loc_180028900
0x1800288b9  mov     rdx, r12
0x1800288bc  lea     rcx, [rsp+0F8h+var_68]
0x1800288c4  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x1800288c9  mov     rdx, r15
0x1800288cc  lea     rcx, [rsp+0F8h+var_A8]
0x1800288d1  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x1800288d6  lea     rcx, [rsp+0F8h+var_A8]; this
0x1800288db  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800288e0  mov     rbx, rax
0x1800288e3  lea     rcx, [rsp+0F8h+var_68]; this
0x1800288eb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x1800288f0  mov     r8, rbx; unsigned __int16 *
0x1800288f3  mov     rdx, rax; unsigned __int16 *
0x1800288f6  mov     ecx, r14d; unsigned int
0x1800288f9  call    ?RemoveReaderFromGroup@@YAXKPEBG0@Z; RemoveReaderFromGroup(ulong,ushort const *,ushort const *)
0x1800288fe  jmp     short loc_180028944
0x180028900  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180028905  test    al, al
0x180028907  jz      short loc_180028922
0x180028909  mov     [rsp+0F8h+var_BC], 8010001Dh
0x180028911  lea     rdx, _TI1K; pThrowInfo
0x180028918  lea     rcx, [rsp+0F8h+var_BC]; pExceptionObject
0x18002891d  call    _CxxThrowException_0
0x180028922  mov     [rsp+0F8h+IoControlCode], 9007Ch; IoControlCode
0x18002892a  mov     r9d, 1; int
0x180028930  mov     r8, r15; unsigned __int8 *
0x180028933  mov     rdx, r12; unsigned __int8 *
0x180028936  mov     rcx, rsi; unsigned __int64
0x180028939  call    ?I_ContextAndTwoStringCallWithLongReturn@@YAJ_KPEBE1HK@Z; I_ContextAndTwoStringCallWithLongReturn(unsigned __int64,uchar const *,uchar const *,int,ulong)
0x18002893e  mov     edi, eax
0x180028940  mov     [rsp+0F8h+var_C8], eax
0x180028944  lea     rcx, [rsp+0F8h+var_A8]; this
0x180028949  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18002894e  nop
0x18002894f  lea     rcx, [rsp+0F8h+var_68]; this
0x180028957  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x18002895c  nop
0x18002895d  jmp     short loc_180028965
0x18002895f  jmp     short $+2
0x180028961  mov     edi, [rsp+0F8h+var_C8]
0x180028965  mov     eax, edi
0x180028967  lea     r11, [rsp+0F8h+var_28]
0x18002896f  mov     rbx, [r11+30h]
0x180028973  mov     rsi, [r11+38h]
0x180028977  mov     rsp, r11
0x18002897a  pop     r15
0x18002897c  pop     r14
0x18002897e  pop     r13
0x180028980  pop     r12
0x180028982  pop     rdi
0x180028983  retn
```
