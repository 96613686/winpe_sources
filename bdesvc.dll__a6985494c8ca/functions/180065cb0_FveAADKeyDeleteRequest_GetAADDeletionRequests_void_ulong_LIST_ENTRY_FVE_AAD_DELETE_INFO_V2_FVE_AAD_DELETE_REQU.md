# FveAADKeyDeleteRequest::GetAADDeletionRequests(void * *,ulong,_LIST_ENTRY *,_FVE_AAD_DELETE_INFO_V2 * *,_FVE_AAD_DELETE_REQUEST * *,ulong *)

- ea: `0x180065cb0`
- end: `0x1800663c0`
- name: `?GetAADDeletionRequests@FveAADKeyDeleteRequest@@SAJPEAPEAXKPEAU_LIST_ENTRY@@PEAPEAU_FVE_AAD_DELETE_INFO_V2@@PEAPEAU_FVE_AAD_DELETE_REQUEST@@PEAK@Z`
- size: `1808`
- prototype: `__int64 __fastcall(void **, unsigned int, struct _LIST_ENTRY *, struct _FVE_AAD_DELETE_INFO_V2 **, struct _FVE_AAD_DELETE_REQUEST **, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180065400`

## callees

- `0x180001fe8`
- `0x180002018`
- `0x180009f30`
- `0x180009f60`
- `0x180009fd0`
- `0x180025ed4`
- `0x1800284dc`
- `0x18002f160`
- `0x18002f28c`
- `0x180030ab4`
- `0x180034070`
- `0x180034d10`
- `0x180065cb0`
- `0x18006670c`
- `0x1800668c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800661ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800661d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800661ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800661d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066223`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065f99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065fcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066062`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066102`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065f99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065fcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066062`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066102`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065f81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065fb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006604a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800660ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066197`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800661bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006620f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065f81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065fb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006604a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800660ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066197`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800661bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006620f`

## string_xrefs

- `0x180066150`: `ParseRecoveryKeyDeleteInfo`

## pseudocode

```c
__int64 __fastcall FveAADKeyDeleteRequest::GetAADDeletionRequests(
        void **a1,
        unsigned int a2,
        struct _LIST_ENTRY *a3,
        struct _FVE_AAD_DELETE_INFO_V2 **a4,
        struct _FVE_AAD_DELETE_REQUEST **a5,
        unsigned int *a6)
{
  const wchar_t *v6; // r13
  void **v9; // rbx
  int v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r12
  __int64 v14; // r8
  __int64 v15; // r9
  struct _FVE_AAD_DELETE_INFO_V2 *v16; // r14
  PVOID *v17; // rcx
  unsigned int v18; // r14d
  unsigned int v19; // eax
  HANDLE v20; // rax
  struct _LIST_ENTRY *v21; // rsi
  HANDLE v22; // rax
  struct _LIST_ENTRY *v23; // rax
  unsigned int v24; // ecx
  unsigned int v25; // ebx
  struct _LIST_ENTRY *Blink; // rax
  HANDLE ProcessHeap; // rax
  struct _FVE_AAD_DELETE_INFO_V2 *v28; // rsi
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // eax
  struct _FVE_AAD_DELETE_REQUEST *v32; // rbx
  HANDLE v33; // rax
  struct _FVE_AAD_DELETE_REQUEST *v34; // rax
  unsigned int v35; // eax
  HANDLE v36; // rax
  HANDLE v37; // rax
  HANDLE v38; // rax
  __int64 v39; // r8
  __int64 v40; // r9
  bool v42; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v43[3]; // [rsp+44h] [rbp-75h] BYREF
  __int64 v44; // [rsp+50h] [rbp-69h] BYREF
  __int64 v45; // [rsp+58h] [rbp-61h] BYREF
  SIZE_T dwBytes; // [rsp+60h] [rbp-59h] BYREF
  SIZE_T v47; // [rsp+68h] [rbp-51h] BYREF
  __int64 v48; // [rsp+70h] [rbp-49h] BYREF
  __int64 v49; // [rsp+78h] [rbp-41h] BYREF
  struct _LIST_ENTRY *v50; // [rsp+80h] [rbp-39h]
  void **v51; // [rsp+88h] [rbp-31h]
  struct _FVE_AAD_DELETE_INFO_V2 **v52; // [rsp+90h] [rbp-29h]
  PSRWLOCK v53[3]; // [rsp+98h] [rbp-21h] BYREF
  struct _LIST_ENTRY v54; // [rsp+B0h] [rbp-9h] BYREF

  v6 = L"NA";
  v44 = (__int64)a5;
  v45 = (__int64)a6;
  v54 = 0;
  v52 = a4;
  v9 = a1;
  v50 = a3;
  v51 = a1;
  v47 = 0;
  dwBytes = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v53,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( !v9 && a2 )
  {
    v10 = -2147024809;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_82;
    v12 = 57;
    goto LABEL_81;
  }
  if ( !a4 || !a5 || !a6 )
  {
    v10 = -2147467261;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_82;
    v12 = 58;
LABEL_81:
    WPP_SF_d(v11[2], v12, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, (unsigned int)v10);
    goto LABEL_82;
  }
  *a4 = 0;
  v10 = 0;
  *a5 = 0;
  *a6 = 0;
  if ( !a2 )
    goto LABEL_85;
  v43[0] = 0;
  v54.Blink = &v54;
  v13 = 0;
  v54.Flink = &v54;
  while ( 1 )
  {
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_18009A3B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A3B8, 0x400000000000LL) )
      {
        v48 = 0x1000000;
        v49 = (__int64)v6;
        v43[1] = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          (int)&dword_18009A3B8,
          (int)&unk_18008E370,
          v14,
          v15,
          (__int64)&v43[1],
          (const unsigned __int16 **)&v49,
          (__int64)&v48);
      }
      v6 = L"NA";
    }
    v16 = (struct _FVE_AAD_DELETE_INFO_V2 *)v9[v13];
    v42 = 0;
    v10 = FveAADKeyDeleteRequest::VerifyRecoveryKeyDeletionFromVolume(v16, v50, &v42);
    if ( v10 >= 0 )
      break;
    v6 = L"VerifyRecoveryKeyDeletionFromVolume";
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_24;
    WPP_SF__guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
      (char *)v16 + 4,
      v10);
LABEL_23:
    v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
    v18 = v43[0];
LABEL_25:
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= a2 )
    {
      if ( v18 )
      {
        v19 = ULongLongMult(v18, 0x240u, &dwBytes);
        v10 = v19;
        if ( !v19 )
          goto LABEL_43;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, v19);
        if ( v10 >= 0 )
        {
LABEL_43:
          ProcessHeap = GetProcessHeap();
          v28 = (struct _FVE_AAD_DELETE_INFO_V2 *)HeapAlloc(ProcessHeap, 8u, dwBytes);
          if ( v28 )
          {
            v31 = ULongLongMult(v18, 0x14u, &v47);
            v10 = v31;
            if ( !v31 )
              goto LABEL_52;
            v32 = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, v31);
            if ( v10 >= 0 )
            {
LABEL_52:
              v33 = GetProcessHeap();
              v34 = (struct _FVE_AAD_DELETE_REQUEST *)HeapAlloc(v33, 8u, v47);
              v32 = v34;
              if ( v34 )
              {
                v6 = L"ParseRecoveryKeyDeleteInfo";
                v35 = FveAADKeyDeleteRequest::ParseRecoveryKeyDeleteInfo(&v54, v28, v34, v18);
                v10 = v35;
                if ( !v35 )
                  goto LABEL_64;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    68,
                    WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
                    v35);
                if ( v10 >= 0 )
                {
LABEL_64:
                  *v52 = v28;
                  *(_QWORD *)v44 = v32;
                  *(_DWORD *)v45 = v18;
                  goto LABEL_76;
                }
              }
              else
              {
                v10 = -2147024882;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    67,
                    WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
                    2147942414LL);
              }
            }
            v36 = GetProcessHeap();
            HeapFree(v36, 0, v28);
            if ( v32 )
            {
              v37 = GetProcessHeap();
              HeapFree(v37, 0, v32);
            }
          }
          else
          {
            v10 = -2147024882;
            v29 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v30 = 65;
LABEL_72:
              WPP_SF_d(v29[2], v30, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids, 2147942414LL);
              goto LABEL_76;
            }
          }
        }
      }
      else if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
      {
        WPP_SF_(v17[2], 63, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
      }
      goto LABEL_76;
    }
  }
  if ( !v42 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_24;
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids);
    goto LABEL_23;
  }
  v20 = GetProcessHeap();
  v21 = (struct _LIST_ENTRY *)HeapAlloc(v20, 8u, 0x20u);
  if ( !v21 )
  {
    v10 = -2147024882;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v30 = 61;
      goto LABEL_72;
    }
    goto LABEL_76;
  }
  v22 = GetProcessHeap();
  v23 = (struct _LIST_ENTRY *)HeapAlloc(v22, 8u, 0x240u);
  v21[1].Flink = v23;
  if ( v23 )
  {
    v24 = 576;
    if ( *(_DWORD *)v16 != 2 )
      v24 = 556;
    v25 = v24;
    memcpy_0(v23, v16, v24);
    LODWORD(v21[1].Blink) = v25;
    Blink = v54.Blink;
    if ( v54.Blink->Flink != &v54 )
      __fastfail(3u);
    v9 = v51;
    v18 = v43[0] + 1;
    v21->Flink = &v54;
    v21->Blink = Blink;
    Blink->Flink = v21;
    v17 = (PVOID *)WPP_GLOBAL_Control;
    v54.Blink = v21;
    v43[0] = v18;
    goto LABEL_25;
  }
  v38 = GetProcessHeap();
  HeapFree(v38, 0, v21);
  v10 = -2147024882;
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v30 = 62;
    goto LABEL_72;
  }
LABEL_76:
  FveClearAsyncRequestList(&v54);
  if ( v10 < 0 )
  {
LABEL_82:
    if ( (unsigned int)dword_18009A3B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A3B8, 0x400000000000LL) )
    {
      v45 = 0x1000000;
      v44 = (__int64)v6;
      v43[1] = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        (int)&dword_18009A3B8,
        (int)&dword_18008E284,
        v39,
        v40,
        (__int64)&v43[1],
        (const unsigned __int16 **)&v44,
        (__int64)&v45);
    }
  }
LABEL_85:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids,
      (unsigned int)v10);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar(v53);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180065cb0  mov     [rsp-8+arg_8], rbx
0x180065cb5  push    rbp
0x180065cb6  push    rsi
0x180065cb7  push    rdi
0x180065cb8  push    r12
0x180065cba  push    r13
0x180065cbc  push    r14
0x180065cbe  push    r15
0x180065cc0  lea     rbp, [rsp-17h]
0x180065cc5  sub     rsp, 0D0h
0x180065ccc  mov     rax, cs:__security_cookie
0x180065cd3  xor     rax, rsp
0x180065cd6  mov     [rbp+47h+var_40], rax
0x180065cda  mov     rsi, [rbp+47h+arg_20]
0x180065cde  lea     r13, aNa; "NA"
0x180065ce5  mov     r14, [rbp+47h+arg_28]
0x180065ce9  xorps   xmm0, xmm0
0x180065cec  mov     [rbp+47h+var_B0], rsi
0x180065cf0  mov     rdi, r9
0x180065cf3  mov     [rbp+47h+var_A8], r14
0x180065cf7  mov     r15d, edx
0x180065cfa  movups  xmmword ptr [rbp+47h+var_50.Flink], xmm0
0x180065cfe  mov     [rbp+47h+var_70], r9
0x180065d02  mov     rbx, rcx
0x180065d05  mov     [rbp+47h+var_80], r8
0x180065d09  mov     [rbp+47h+var_78], rcx
0x180065d0d  mov     [rbp+47h+var_98], 0
0x180065d15  mov     [rbp+47h+dwBytes], 0
0x180065d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180065d24  lea     r12, WPP_GLOBAL_Control
0x180065d2b  cmp     rcx, r12
0x180065d2e  jz      short loc_180065D4B
0x180065d30  test    byte ptr [rcx+1Ch], 20h
0x180065d34  jz      short loc_180065D4B
0x180065d36  mov     rcx, [rcx+10h]
0x180065d3a  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x180065d41  mov     edx, 38h ; '8'
0x180065d46  call    WPP_SF_
0x180065d4b  lea     r9, ?g_bitLockerKeyRollProviderRefCount@@3JC; volatile int *
0x180065d52  lea     r8, ?g_bitLockerKeyRollProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x180065d59  lea     rdx, g_hBitLockerKeyRollProvider; struct _tlgProvider_t **
0x180065d60  lea     rcx, [rbp+47h+var_68]; this
0x180065d64  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z; TelemetryProviderRegistrar::TelemetryProviderRegistrar(_tlgProvider_t const * const *,_RTL_SRWLOCK *,long volatile *)
0x180065d69  test    rbx, rbx
0x180065d6c  jnz     short loc_180065D9A
0x180065d6e  test    r15d, r15d
0x180065d71  jz      short loc_180065D9A
0x180065d73  mov     edi, 80070057h
0x180065d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180065d7f  cmp     rcx, r12
0x180065d82  jz      loc_180066301
0x180065d88  test    byte ptr [rcx+1Ch], 40h
0x180065d8c  jz      loc_180066301
0x180065d92  lea     edx, [rbx+39h]
0x180065d95  jmp     loc_1800662EE
0x180065d9a  test    rdi, rdi
0x180065d9d  jz      loc_1800662D2
0x180065da3  test    rsi, rsi
0x180065da6  jz      loc_1800662D2
0x180065dac  test    r14, r14
0x180065daf  jz      loc_1800662D2
0x180065db5  mov     qword ptr [rdi], 0
0x180065dbc  xor     edi, edi
0x180065dbe  mov     qword ptr [rsi], 0
0x180065dc5  mov     dword ptr [r14], 0
0x180065dcc  test    r15d, r15d
0x180065dcf  jz      loc_180066363
0x180065dd5  lea     rax, [rbp+47h+var_50]
0x180065dd9  mov     [rbp+47h+var_BC], edi
0x180065ddc  mov     [rbp+47h+var_50.Blink], rax
0x180065de0  xor     r12d, r12d
0x180065de3  lea     rax, [rbp+47h+var_50]
0x180065de7  mov     [rbp+47h+var_50.Flink], rax
0x180065deb  test    r15d, r15d
0x180065dee  jz      loc_180066291
0x180065df4  test    edi, edi
0x180065df6  jns     short loc_180065E61
0x180065df8  mov     eax, cs:dword_18009A3B8
0x180065dfe  cmp     eax, 5
0x180065e01  jbe     short loc_180065E5A
0x180065e03  mov     rdx, 400000000000h
0x180065e0d  lea     rcx, dword_18009A3B8
0x180065e14  call    _tlgKeywordOn
0x180065e19  test    al, al
0x180065e1b  jz      short loc_180065E5A
0x180065e1d  lea     rax, [rbp+47h+var_90]
0x180065e21  mov     [rbp+47h+var_90], 1000000h
0x180065e29  mov     [rsp+100h+var_D0], rax; __int64
0x180065e2e  lea     rdx, unk_18008E370
0x180065e35  lea     rax, [rbp+47h+var_88]
0x180065e39  mov     [rbp+47h+var_88], r13
0x180065e3d  mov     [rsp+100h+var_D8], rax; __int64
0x180065e42  lea     rcx, dword_18009A3B8; int
0x180065e49  lea     rax, [rbp+47h+var_BC+4]
0x180065e4d  mov     [rbp+47h+var_BC+4], edi
0x180065e50  mov     [rsp+100h+var_E0], rax; __int64
0x180065e55  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180065e5a  lea     r13, aNa; "NA"
0x180065e61  mov     r14, [rbx+r12*8]
0x180065e65  lea     r8, [rbp+47h+var_C0]; bool *
0x180065e69  mov     rdx, [rbp+47h+var_80]; struct _LIST_ENTRY *
0x180065e6d  mov     rcx, r14; struct _FVE_AAD_DELETE_INFO_V2 *
0x180065e70  mov     [rbp+47h+var_C0], 0
0x180065e74  call    ?VerifyRecoveryKeyDeletionFromVolume@FveAADKeyDeleteRequest@@SAJPEAU_FVE_AAD_DELETE_INFO_V2@@PEAU_LIST_ENTRY@@PEA_N@Z; FveAADKeyDeleteRequest::VerifyRecoveryKeyDeletionFromVolume(_FVE_AAD_DELETE_INFO_V2 *,_LIST_ENTRY *,bool *)
0x180065e79  mov     edi, eax
0x180065e7b  test    eax, eax
0x180065e7d  jns     loc_180065F3C
0x180065e83  lea     r13, aVerifyrecovery; "VerifyRecoveryKeyDeletionFromVolume"
0x180065e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e91  lea     rax, WPP_GLOBAL_Control
0x180065e98  cmp     rcx, rax
0x180065e9b  jz      short loc_180065EC7
0x180065e9d  test    byte ptr [rcx+1Ch], 2
0x180065ea1  jz      short loc_180065EC7
0x180065ea3  mov     rcx, [rcx+10h]
0x180065ea7  lea     r9, [r14+4]
0x180065eab  mov     edx, 3Bh ; ';'
0x180065eb0  mov     dword ptr [rsp+100h+var_E0], edi
0x180065eb4  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x180065ebb  call    WPP_SF__guid_d
0x180065ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180065ec7  mov     r14d, [rbp+47h+var_BC]
0x180065ecb  inc     r12d
0x180065ece  cmp     r12d, r15d
0x180065ed1  jb      loc_180065DF4
0x180065ed7  test    r14d, r14d
0x180065eda  jz      loc_180066298
0x180065ee0  lea     r8, [rbp+47h+dwBytes]; unsigned __int64 *
0x180065ee4  mov     ecx, r14d; unsigned __int64
0x180065ee7  mov     edx, 240h; unsigned __int64
0x180065eec  mov     ebx, r14d
0x180065eef  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180065ef4  mov     edi, eax
0x180065ef6  test    eax, eax
0x180065ef8  jz      loc_180066043
0x180065efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180065f05  lea     r12, WPP_GLOBAL_Control
0x180065f0c  cmp     rcx, r12
0x180065f0f  jz      short loc_180065F2F
0x180065f11  test    byte ptr [rcx+1Ch], 40h
0x180065f15  jz      short loc_180065F2F
0x180065f17  mov     rcx, [rcx+10h]
0x180065f1b  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x180065f22  mov     edx, 40h ; '@'
0x180065f27  mov     r9d, eax
0x180065f2a  call    WPP_SF_d
0x180065f2f  test    edi, edi
0x180065f31  js      loc_1800662BF
0x180065f37  jmp     loc_18006604A
0x180065f3c  cmp     [rbp+47h+var_C0], 0
0x180065f40  jnz     short loc_180065F81
0x180065f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180065f49  lea     rax, WPP_GLOBAL_Control
0x180065f50  cmp     rcx, rax
0x180065f53  jz      loc_180065EC7
0x180065f59  test    byte ptr [rcx+1Ch], 8
0x180065f5d  jz      loc_180065EC7
0x180065f63  mov     rcx, [rcx+10h]
0x180065f67  lea     r9, [r14+4]
0x180065f6b  mov     edx, 3Ch ; '<'
0x180065f70  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x180065f77  call    WPP_SF__guid_
0x180065f7c  jmp     loc_180065EC0
0x180065f81  call    cs:__imp_GetProcessHeap
0x180065f88  nop     dword ptr [rax+rax+00h]
0x180065f8d  mov     edx, 8; dwFlags
0x180065f92  mov     rcx, rax; hHeap
0x180065f95  lea     r8d, [rdx+18h]; dwBytes
0x180065f99  call    cs:__imp_HeapAlloc
0x180065fa0  nop     dword ptr [rax+rax+00h]
0x180065fa5  mov     rsi, rax
0x180065fa8  test    rax, rax
0x180065fab  jz      loc_180066258
0x180065fb1  call    cs:__imp_GetProcessHeap
0x180065fb8  nop     dword ptr [rax+rax+00h]
0x180065fbd  mov     ebx, 240h
0x180065fc2  mov     edx, 8; dwFlags
0x180065fc7  mov     rcx, rax; hHeap
0x180065fca  mov     r8d, ebx; dwBytes
0x180065fcd  call    cs:__imp_HeapAlloc
0x180065fd4  nop     dword ptr [rax+rax+00h]
0x180065fd9  mov     [rsi+10h], rax
0x180065fdd  test    rax, rax
0x180065fe0  jz      loc_18006620F
0x180065fe6  cmp     dword ptr [r14], 2
0x180065fea  lea     edx, [rbx-14h]
0x180065fed  mov     ecx, ebx
0x180065fef  cmovnz  ecx, edx
0x180065ff2  mov     rdx, r14; Src
0x180065ff5  mov     ebx, ecx
0x180065ff7  mov     r8d, ecx; Size
0x180065ffa  mov     rcx, rax; void *
0x180065ffd  call    memcpy_0
0x180066002  mov     [rsi+18h], ebx
0x180066005  lea     rcx, [rbp+47h+var_50]
0x180066009  mov     rax, [rbp+47h+var_50.Blink]
0x18006600d  cmp     [rax], rcx
0x180066010  jnz     loc_180066208
0x180066016  mov     r14d, [rbp+47h+var_BC]
0x18006601a  lea     rcx, [rbp+47h+var_50]
0x18006601e  mov     rbx, [rbp+47h+var_78]
0x180066022  inc     r14d
0x180066025  mov     [rsi], rcx
0x180066028  mov     [rsi+8], rax
0x18006602c  mov     [rax], rsi
0x18006602f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066036  mov     [rbp+47h+var_50.Blink], rsi
0x18006603a  mov     [rbp+47h+var_BC], r14d
0x18006603e  jmp     loc_180065ECB
0x180066043  lea     r12, WPP_GLOBAL_Control
0x18006604a  call    cs:__imp_GetProcessHeap
0x180066051  nop     dword ptr [rax+rax+00h]
0x180066056  mov     r8, [rbp+47h+dwBytes]; dwBytes
0x18006605a  mov     edx, 8; dwFlags
0x18006605f  mov     rcx, rax; hHeap
0x180066062  call    cs:__imp_HeapAlloc
0x180066069  nop     dword ptr [rax+rax+00h]
0x18006606e  mov     rsi, rax
0x180066071  test    rax, rax
0x180066074  jnz     short loc_1800660A1
0x180066076  mov     r9d, 8007000Eh
0x18006607c  mov     edi, r9d
0x18006607f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066086  cmp     rcx, r12
0x180066089  jz      loc_1800662BF
0x18006608f  test    byte ptr [rcx+1Ch], 40h
0x180066093  jz      loc_1800662BF
0x180066099  lea     edx, [rax+41h]
0x18006609c  jmp     loc_18006627F
0x1800660a1  lea     r8, [rbp+47h+var_98]; unsigned __int64 *
0x1800660a5  mov     edx, 14h; unsigned __int64
0x1800660aa  mov     rcx, rbx; unsigned __int64
0x1800660ad  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800660b2  mov     edi, eax
0x1800660b4  test    eax, eax
0x1800660b6  jz      short loc_1800660EA
0x1800660b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660bf  xor     ebx, ebx
0x1800660c1  cmp     rcx, r12
0x1800660c4  jz      short loc_1800660E2
0x1800660c6  test    byte ptr [rcx+1Ch], 40h
0x1800660ca  jz      short loc_1800660E2
0x1800660cc  mov     rcx, [rcx+10h]
0x1800660d0  lea     edx, [rbx+42h]
0x1800660d3  mov     r9d, eax
0x1800660d6  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x1800660dd  call    WPP_SF_d
0x1800660e2  test    edi, edi
0x1800660e4  js      loc_180066197
0x1800660ea  call    cs:__imp_GetProcessHeap
0x1800660f1  nop     dword ptr [rax+rax+00h]
0x1800660f6  mov     r8, [rbp+47h+var_98]; dwBytes
0x1800660fa  mov     edx, 8; dwFlags
0x1800660ff  mov     rcx, rax; hHeap
0x180066102  call    cs:__imp_HeapAlloc
0x180066109  nop     dword ptr [rax+rax+00h]
0x18006610e  mov     rbx, rax
0x180066111  test    rax, rax
0x180066114  jnz     short loc_180066146
0x180066116  mov     r9d, 8007000Eh
0x18006611c  mov     edi, r9d
0x18006611f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066126  cmp     rcx, r12
0x180066129  jz      short loc_180066197
0x18006612b  test    byte ptr [rcx+1Ch], 40h
0x18006612f  jz      short loc_180066197
0x180066131  mov     rcx, [rcx+10h]
0x180066135  lea     edx, [rax+43h]
0x180066138  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x18006613f  call    WPP_SF_d
0x180066144  jmp     short loc_180066197
0x180066146  mov     r9d, r14d; unsigned int
0x180066149  lea     rcx, [rbp+47h+var_50]; struct _LIST_ENTRY *
0x18006614d  mov     r8, rbx; struct _FVE_AAD_DELETE_REQUEST *
0x180066150  lea     r13, aParserecoveryk; "ParseRecoveryKeyDeleteInfo"
0x180066157  mov     rdx, rsi; struct _FVE_AAD_DELETE_INFO_V2 *
0x18006615a  call    ?ParseRecoveryKeyDeleteInfo@FveAADKeyDeleteRequest@@SAJPEAU_LIST_ENTRY@@PEAU_FVE_AAD_DELETE_INFO_V2@@PEAU_FVE_AAD_DELETE_REQUEST@@K@Z; FveAADKeyDeleteRequest::ParseRecoveryKeyDeleteInfo(_LIST_ENTRY *,_FVE_AAD_DELETE_INFO_V2 *,_FVE_AAD_DELETE_REQUEST *,ulong)
0x18006615f  mov     edi, eax
0x180066161  test    eax, eax
0x180066163  jz      loc_1800661EE
0x180066169  mov     rcx, cs:WPP_GLOBAL_Control
0x180066170  cmp     rcx, r12
0x180066173  jz      short loc_180066193
0x180066175  test    byte ptr [rcx+1Ch], 40h
0x180066179  jz      short loc_180066193
0x18006617b  mov     rcx, [rcx+10h]
0x18006617f  lea     r8, WPP_7709ce7c93e736bfd9c8ec2a012a7f7b_Traceguids
0x180066186  mov     edx, 44h ; 'D'
0x18006618b  mov     r9d, eax
0x18006618e  call    WPP_SF_d
0x180066193  test    edi, edi
0x180066195  jns     short loc_1800661EE
0x180066197  call    cs:__imp_GetProcessHeap
0x18006619e  nop     dword ptr [rax+rax+00h]
0x1800661a3  mov     r8, rsi; lpMem
0x1800661a6  xor     edx, edx; dwFlags
0x1800661a8  mov     rcx, rax; hHeap
0x1800661ab  call    cs:__imp_HeapFree
0x1800661b2  nop     dword ptr [rax+rax+00h]
0x1800661b7  test    rbx, rbx
  ... truncated ...
```
