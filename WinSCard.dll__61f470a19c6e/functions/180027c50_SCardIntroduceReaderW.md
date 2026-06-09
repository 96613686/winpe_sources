# SCardIntroduceReaderW

- ea: `0x180027c50`
- end: `0x180027e44`
- name: `SCardIntroduceReaderW`
- size: `500`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, LPCWSTR szReaderName, LPCWSTR szDeviceName)`
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
- `0x180027c50`
- `0x18002b0ec`
- `0x18002b734`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027cf8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027cf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027d2e`

## pseudocode

```c
LONG __stdcall SCardIntroduceReaderW(SCARDCONTEXT hContext, LPCWSTR szReaderName, LPCWSTR szDeviceName)
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
    CTextString::operator=(&v19, szDeviceName);
    v13 = CTextString::Unicode((CTextString *)&v19);
    v14 = CTextString::Unicode((CTextString *)&v29);
    IntroduceReader(v12, v14, v13);
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
         (const unsigned __int8 *)szDeviceName,
         1,
         0x90064u);
LABEL_14:
  CTextString::~CTextString((CTextString *)&v19);
  CTextString::~CTextString((CTextString *)&v29);
  return v6;
}

```

## disassembly

```asm
0x180027c50  mov     r11, rsp
0x180027c53  mov     [r11+8], rbx
0x180027c57  mov     [r11+10h], rsi
0x180027c5b  push    rdi
0x180027c5c  push    r12
0x180027c5e  push    r13
0x180027c60  push    r14
0x180027c62  push    r15
0x180027c64  sub     rsp, 0D0h
0x180027c6b  mov     r15, r8
0x180027c6e  mov     r12, rdx
0x180027c71  mov     r14, rcx
0x180027c74  xor     r13d, r13d
0x180027c77  mov     edi, r13d
0x180027c7a  lea     rcx, ??_7CTextString@@6B@; const CTextString::`vftable'
0x180027c81  mov     [r11-68h], rcx
0x180027c85  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180027c8c  mov     [r11-58h], rax
0x180027c90  mov     [r11-50h], r13
0x180027c94  mov     [r11-48h], r13d
0x180027c98  mov     [r11-44h], r13d
0x180027c9c  mov     [r11-40h], rax
0x180027ca0  mov     [r11-38h], r13
0x180027ca4  mov     [r11-30h], r13d
0x180027ca8  mov     [r11-2Ch], r13d
0x180027cac  lea     edx, [r13+3]
0x180027cb0  mov     [r11-60h], edx
0x180027cb4  mov     [rsp+0F8h+var_A8], rcx
0x180027cb9  mov     [rsp+0F8h+var_98], rax
0x180027cbe  mov     [rsp+0F8h+var_90], r13
0x180027cc3  mov     [rsp+0F8h+var_88], r13d
0x180027cc8  mov     [rsp+0F8h+var_84], r13d
0x180027ccd  mov     [r11-80h], rax
0x180027cd1  mov     [r11-78h], r13
0x180027cd5  mov     [r11-70h], r13d
0x180027cd9  mov     [r11-6Ch], r13d
0x180027cdd  mov     [rsp+0F8h+var_A0], edx
0x180027ce1  test    r14, r14
0x180027ce4  jz      short loc_180027D65
0x180027ce6  mov     rbx, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180027ced  lea     rsi, [rbx+20h]
0x180027cf1  mov     [r11+20h], rsi
0x180027cf5  mov     rcx, rsi; lpCriticalSection
0x180027cf8  call    cs:__imp_EnterCriticalSection
0x180027cfe  nop
0x180027cff  mov     rdx, r14; unsigned __int64
0x180027d02  mov     rcx, rbx; this
0x180027d05  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180027d0a  test    rax, rax
0x180027d0d  jnz     short loc_180027D28
0x180027d0f  mov     [rsp+0F8h+pExceptionObject], 6
0x180027d17  lea     rdx, _TI1K; pThrowInfo
0x180027d1e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180027d23  call    _CxxThrowException_0
0x180027d28  mov     rbx, [rax]
0x180027d2b  mov     rcx, rsi; lpCriticalSection
0x180027d2e  call    cs:__imp_LeaveCriticalSection
0x180027d34  cmp     [rbx+10h], r13d
0x180027d38  jz      short loc_180027D53
0x180027d3a  mov     [rsp+0F8h+var_C0], 8010001Eh
0x180027d42  lea     rdx, _TI1K; pThrowInfo
0x180027d49  lea     rcx, [rsp+0F8h+var_C0]; pExceptionObject
0x180027d4e  call    _CxxThrowException_0
0x180027d53  mov     rsi, [rbx+80h]
0x180027d5a  test    rsi, rsi
0x180027d5d  jnz     short loc_180027DC0
0x180027d5f  mov     r14d, [rbx+1Ch]
0x180027d63  jmp     short loc_180027D6E
0x180027d65  mov     r14d, 2
0x180027d6b  mov     rsi, r13
0x180027d6e  xor     ecx, ecx; lpCriticalSection
0x180027d70  call    ?RedirectionContextIsLocal@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextIsLocal(_REDIRECTION_CONTEXT *)
0x180027d75  test    al, al
0x180027d77  jz      short loc_180027DC0
0x180027d79  mov     rdx, r12
0x180027d7c  lea     rcx, [rsp+0F8h+var_68]
0x180027d84  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x180027d89  mov     rdx, r15
0x180027d8c  lea     rcx, [rsp+0F8h+var_A8]
0x180027d91  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x180027d96  lea     rcx, [rsp+0F8h+var_A8]; this
0x180027d9b  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180027da0  mov     rbx, rax
0x180027da3  lea     rcx, [rsp+0F8h+var_68]; this
0x180027dab  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x180027db0  mov     r8, rbx; unsigned __int16 *
0x180027db3  mov     rdx, rax; unsigned __int16 *
0x180027db6  mov     ecx, r14d; unsigned int
0x180027db9  call    ?IntroduceReader@@YAXKPEBG0@Z; IntroduceReader(ulong,ushort const *,ushort const *)
0x180027dbe  jmp     short loc_180027E04
0x180027dc0  call    ?RedirectDisabled@@YA_NXZ; RedirectDisabled(void)
0x180027dc5  test    al, al
0x180027dc7  jz      short loc_180027DE2
0x180027dc9  mov     [rsp+0F8h+var_BC], 8010001Dh
0x180027dd1  lea     rdx, _TI1K; pThrowInfo
0x180027dd8  lea     rcx, [rsp+0F8h+var_BC]; pExceptionObject
0x180027ddd  call    _CxxThrowException_0
0x180027de2  mov     [rsp+0F8h+IoControlCode], 90064h; IoControlCode
0x180027dea  mov     r9d, 1; int
0x180027df0  mov     r8, r15; unsigned __int8 *
0x180027df3  mov     rdx, r12; unsigned __int8 *
0x180027df6  mov     rcx, rsi; unsigned __int64
0x180027df9  call    ?I_ContextAndTwoStringCallWithLongReturn@@YAJ_KPEBE1HK@Z; I_ContextAndTwoStringCallWithLongReturn(unsigned __int64,uchar const *,uchar const *,int,ulong)
0x180027dfe  mov     edi, eax
0x180027e00  mov     [rsp+0F8h+var_C8], eax
0x180027e04  lea     rcx, [rsp+0F8h+var_A8]; this
0x180027e09  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180027e0e  nop
0x180027e0f  lea     rcx, [rsp+0F8h+var_68]; this
0x180027e17  call    ??1CTextString@@UEAA@XZ; CTextString::~CTextString(void)
0x180027e1c  nop
0x180027e1d  jmp     short loc_180027E25
0x180027e1f  jmp     short $+2
0x180027e21  mov     edi, [rsp+0F8h+var_C8]
0x180027e25  mov     eax, edi
0x180027e27  lea     r11, [rsp+0F8h+var_28]
0x180027e2f  mov     rbx, [r11+30h]
0x180027e33  mov     rsi, [r11+38h]
0x180027e37  mov     rsp, r11
0x180027e3a  pop     r15
0x180027e3c  pop     r14
0x180027e3e  pop     r13
0x180027e40  pop     r12
0x180027e42  pop     rdi
0x180027e43  retn
```
