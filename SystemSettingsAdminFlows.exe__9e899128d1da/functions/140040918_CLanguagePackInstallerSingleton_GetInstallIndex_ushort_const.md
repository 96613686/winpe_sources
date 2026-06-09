# CLanguagePackInstallerSingleton::_GetInstallIndex(ushort const *)

- ea: `0x140040918`
- end: `0x140040b06`
- name: `?_GetInstallIndex@CLanguagePackInstallerSingleton@@AEAAHPEBG@Z`
- size: `494`
- prototype: `__int64 __fastcall(CLanguagePackInstallerSingleton *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003f3f8`
- `0x140040304`

## callees

- `0x14000e624`
- `0x14003f000`
- `0x140040918`
- `0x140040ebc`
- `0x140041054`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400409e5`
- `KERNEL32!EnterCriticalSection` at `0x1400409e5`
- `KERNEL32!TlsGetValue` at `0x140040938`
- `KERNEL32!TlsGetValue` at `0x140040938`
- `KERNEL32!TlsSetValue` at `0x140040970`
- `KERNEL32!TlsSetValue` at `0x140040970`
- `KERNEL32!CompareStringOrdinal` at `0x140040a61`
- `KERNEL32!CompareStringOrdinal` at `0x140040a61`

## pseudocode

```c
__int64 __fastcall CLanguagePackInstallerSingleton::_GetInstallIndex(
        CLanguagePackInstallerSingleton *this,
        const unsigned __int16 *a2)
{
  _DWORD *Value; // rax
  _DWORD *v5; // rdi
  unsigned int v6; // ecx
  __int64 v7; // rcx
  unsigned int v8; // ebp
  unsigned __int64 v9; // r12
  unsigned __int64 i; // rbx
  const WCHAR *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  const WCHAR *v15; // rcx
  unsigned int v16; // edx
  __int64 v17; // rsi
  __int64 v19; // [rsp+28h] [rbp-50h]
  _QWORD TlsValue[9]; // [rsp+30h] [rbp-48h] BYREF
  DWORD v21; // [rsp+80h] [rbp+8h] BYREF
  char *v22; // [rsp+90h] [rbp+18h] BYREF

  Value = TlsGetValue(__g_tracingTlsSlot);
  v21 = -1;
  TlsValue[0] = 0;
  v5 = Value;
  if ( !Value )
  {
    v21 = __g_tracingTlsSlot;
    v5 = TlsValue;
    TlsSetValue(__g_tracingTlsSlot, TlsValue);
  }
  ++*v5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v6 = 5 * *v5;
    if ( v6 > 0x1E1 )
      v7 = 0;
    else
      v7 = 479LL - v6;
    WPP_SF_sqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
      (unsigned int)&asc_140089BC0[v7],
      (char)this,
      (__int64)a2);
  }
  v8 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v9 = *((_QWORD *)this + 19);
  v22 = (char *)this + 104;
  for ( i = 0; i < v9; ++i )
  {
    v11 = a2;
    v12 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
    v13 = *(_QWORD *)(v12 + 16);
    if ( !a2 )
      v11 = &Data;
    if ( v13 != -1 )
    {
      v15 = *(const WCHAR **)(v12 + 8);
      if ( v15 )
        goto LABEL_21;
      goto LABEL_20;
    }
    v14 = *(_QWORD *)(v12 + 8);
    if ( !v14 )
    {
      LODWORD(v13) = 0;
LABEL_20:
      v15 = &Data;
      goto LABEL_21;
    }
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(v14 + 2 * v13) );
    v15 = *(const WCHAR **)(v12 + 8);
LABEL_21:
    if ( CompareStringOrdinal(v15, v13, v11, -(a2 != 0), 0) == 2 )
    {
      v8 = i;
      break;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v16 = 5 * *v5;
    if ( v16 > 0x1E1 )
      v17 = 0;
    else
      v17 = 479LL - v16;
    LODWORD(v19) = v8;
    WPP_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
      (unsigned int)&asc_140089BC0[v17],
      (char)this,
      v19,
      TlsValue[0]);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v22);
  if ( v5 )
    --*v5;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v21);
  return v8;
}

```

## disassembly

```asm
0x140040918  mov     [rsp+arg_8], rbx
0x14004091d  push    rbp
0x14004091e  push    rsi
0x14004091f  push    rdi
0x140040920  push    r12
0x140040922  push    r13
0x140040924  push    r14
0x140040926  push    r15
0x140040928  sub     rsp, 40h
0x14004092c  mov     r14, rcx
0x14004092f  mov     r15, rdx
0x140040932  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x140040938  call    cs:__imp_TlsGetValue
0x14004093e  xor     r13d, r13d
0x140040941  mov     [rsp+78h+arg_0], 0FFFFFFFFh
0x14004094c  mov     [rsp+78h+TlsValue], r13
0x140040951  mov     rdi, rax
0x140040954  test    rax, rax
0x140040957  jnz     short loc_140040976
0x140040959  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14004095f  lea     rdx, [rsp+78h+TlsValue]; lpTlsValue
0x140040964  mov     [rsp+78h+arg_0], ecx
0x14004096b  lea     rdi, [rsp+78h+TlsValue]
0x140040970  call    cs:__imp_TlsSetValue
0x140040976  inc     dword ptr [rdi]
0x140040978  mov     r10, cs:WPP_GLOBAL_Control
0x14004097f  lea     rax, WPP_GLOBAL_Control
0x140040986  lea     rdx, asc_140089BC0; "                                       "...
0x14004098d  mov     esi, 1DFh
0x140040992  cmp     r10, rax
0x140040995  jz      short loc_1400409DA
0x140040997  test    byte ptr [r10+1Ch], 80h
0x14004099c  jz      short loc_1400409DA
0x14004099e  mov     eax, [rdi]
0x1400409a0  lea     ecx, [rax+rax*4]
0x1400409a3  cmp     ecx, 1E1h
0x1400409a9  ja      short loc_1400409B4
0x1400409ab  mov     eax, ecx
0x1400409ad  mov     ecx, esi
0x1400409af  sub     rcx, rax
0x1400409b2  jmp     short loc_1400409B7
0x1400409b4  mov     rcx, r13
0x1400409b7  lea     r9, [rcx+rdx]
0x1400409bb  mov     [rsp+78h+var_50], r15
0x1400409c0  mov     rcx, [r10+10h]
0x1400409c4  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x1400409cb  mov     edx, 13h
0x1400409d0  mov     qword ptr [rsp+78h+bIgnoreCase], r14
0x1400409d5  call    WPP_SF_sqS
0x1400409da  lea     rbx, [r14+68h]
0x1400409de  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400409e2  mov     rcx, rbx; lpCriticalSection
0x1400409e5  call    cs:__imp_EnterCriticalSection
0x1400409eb  mov     r12, [r14+98h]
0x1400409f2  mov     [rsp+78h+arg_10], rbx
0x1400409fa  mov     rbx, r13
0x1400409fd  lea     r10, Data
0x140040a04  cmp     rbx, r12
0x140040a07  jnb     short loc_140040A73
0x140040a09  mov     rax, [r14+90h]
0x140040a10  mov     r8, r15
0x140040a13  mov     rcx, [rax+rbx*8]
0x140040a17  mov     rax, r15
0x140040a1a  neg     rax
0x140040a1d  sbb     r9d, r9d; cchCount2
0x140040a20  mov     rdx, [rcx+10h]; cchCount1
0x140040a24  test    r15, r15
0x140040a27  cmovz   r8, r10; lpString2
0x140040a2b  cmp     rdx, rbp
0x140040a2e  jnz     short loc_140040A50
0x140040a30  mov     rax, [rcx+8]
0x140040a34  test    rax, rax
0x140040a37  jz      short loc_140040A4B
0x140040a39  mov     rdx, rbp
0x140040a3c  inc     rdx
0x140040a3f  cmp     [rax+rdx*2], r13w
0x140040a44  jnz     short loc_140040A3C
0x140040a46  mov     rcx, rax
0x140040a49  jmp     short loc_140040A5C
0x140040a4b  mov     rdx, r13
0x140040a4e  jmp     short loc_140040A59
0x140040a50  mov     rcx, [rcx+8]
0x140040a54  test    rcx, rcx
0x140040a57  jnz     short loc_140040A5C
0x140040a59  mov     rcx, r10; lpString1
0x140040a5c  mov     [rsp+78h+bIgnoreCase], r13d; bIgnoreCase
0x140040a61  call    cs:__imp_CompareStringOrdinal
0x140040a67  cmp     eax, 2
0x140040a6a  jz      short loc_140040A71
0x140040a6c  inc     rbx
0x140040a6f  jmp     short loc_1400409FD
0x140040a71  mov     ebp, ebx
0x140040a73  mov     rcx, cs:WPP_GLOBAL_Control
0x140040a7a  lea     rax, WPP_GLOBAL_Control
0x140040a81  cmp     rcx, rax
0x140040a84  jz      short loc_140040ACB
0x140040a86  test    byte ptr [rcx+1Ch], 80h
0x140040a8a  jz      short loc_140040ACB
0x140040a8c  mov     eax, [rdi]
0x140040a8e  lea     edx, [rax+rax*4]
0x140040a91  cmp     edx, 1E1h
0x140040a97  ja      short loc_140040AA0
0x140040a99  mov     eax, edx
0x140040a9b  sub     rsi, rax
0x140040a9e  jmp     short loc_140040AA3
0x140040aa0  mov     rsi, r13
0x140040aa3  mov     rcx, [rcx+10h]
0x140040aa7  lea     r9, asc_140089BC0; "                                       "...
0x140040aae  add     r9, rsi
0x140040ab1  mov     dword ptr [rsp+78h+var_50], ebp
0x140040ab5  mov     edx, 14h
0x140040aba  mov     qword ptr [rsp+78h+bIgnoreCase], r14
0x140040abf  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x140040ac6  call    WPP_SF_sqd
0x140040acb  lea     rcx, [rsp+78h+arg_10]; this
0x140040ad3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x140040ad8  test    rdi, rdi
0x140040adb  jz      short loc_140040ADF
0x140040add  dec     dword ptr [rdi]
0x140040adf  lea     rcx, [rsp+78h+arg_0]
0x140040ae7  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x140040aec  mov     rbx, [rsp+78h+arg_8]
0x140040af4  mov     eax, ebp
0x140040af6  add     rsp, 40h
0x140040afa  pop     r15
0x140040afc  pop     r14
0x140040afe  pop     r13
0x140040b00  pop     r12
0x140040b02  pop     rdi
0x140040b03  pop     rsi
0x140040b04  pop     rbp
0x140040b05  retn
```
