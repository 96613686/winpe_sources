# FAX_StartCopyMessageFromServer

- ea: `0x140021e70`
- end: `0x14002245a`
- name: `FAX_StartCopyMessageFromServer`
- size: `1514`
- prototype: `__int64 __fastcall(void *, struct _LIST_ENTRY *, unsigned int, struct _HANDLE_ENTRY **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140010828`
- `0x1400135d0`
- `0x140021e70`
- `0x14002de70`
- `0x1400399f0`
- `0x1400479a4`
- `0x140047d20`
- `0x140048284`
- `0x14006998c`
- `0x14006e124`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140021fa1`
- `KERNEL32!GetLastError` at `0x1400222b5`
- `KERNEL32!GetLastError` at `0x140022329`
- `KERNEL32!GetLastError` at `0x1400223e8`
- `KERNEL32!GetLastError` at `0x140021fa1`
- `KERNEL32!GetLastError` at `0x1400222b5`
- `KERNEL32!GetLastError` at `0x140022329`
- `KERNEL32!GetLastError` at `0x1400223e8`
- `KERNEL32!CloseHandle` at `0x1400223d8`
- `KERNEL32!CloseHandle` at `0x1400223d8`
- `KERNEL32!EnterCriticalSection` at `0x140022005`
- `KERNEL32!EnterCriticalSection` at `0x14002239d`
- `KERNEL32!EnterCriticalSection` at `0x140022005`
- `KERNEL32!EnterCriticalSection` at `0x14002239d`
- `KERNEL32!LeaveCriticalSection` at `0x140022036`
- `KERNEL32!LeaveCriticalSection` at `0x14002209f`
- `KERNEL32!LeaveCriticalSection` at `0x14002210a`
- `KERNEL32!LeaveCriticalSection` at `0x14002215e`
- `KERNEL32!LeaveCriticalSection` at `0x1400223c3`
- `KERNEL32!LeaveCriticalSection` at `0x140022036`
- `KERNEL32!LeaveCriticalSection` at `0x14002209f`
- `KERNEL32!LeaveCriticalSection` at `0x14002210a`
- `KERNEL32!LeaveCriticalSection` at `0x14002215e`
- `KERNEL32!LeaveCriticalSection` at `0x1400223c3`

## pseudocode

```c
__int64 __fastcall FAX_StartCopyMessageFromServer(
        void *a1,
        struct _LIST_ENTRY *a2,
        unsigned int a3,
        struct _HANDLE_ENTRY **a4)
{
  struct _LIST_ENTRY *i; // rsi
  CMapDeviceId *v9; // rcx
  __int64 result; // rax
  unsigned int v11; // edi
  void *ClientUserSID; // r15
  DWORD v13; // eax
  unsigned int PreviewFile; // ebx
  __int64 v15; // r14
  WCHAR *Blink; // rcx
  WCHAR *v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  WCHAR *v20; // rcx
  unsigned int v21; // edi
  unsigned int v22; // eax
  void *File; // rax
  DWORD LastError; // eax
  struct _HANDLE_ENTRY *NewCopyHandle; // rax
  DWORD v26; // eax
  DWORD v27; // eax
  unsigned int v28; // [rsp+40h] [rbp-278h] BYREF
  int v29[3]; // [rsp+44h] [rbp-274h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-268h] BYREF

  i = 0;
  v28 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 508, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v9 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v9 + 2), 509, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 87;
  }
  if ( a3 > 2 )
  {
    if ( v9 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v9 + 2), 510, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a3);
    return 87;
  }
  v29[0] = 0;
  result = FaxSvcAccessCheck(0x2000000u, v29, &v28, 1);
  if ( !(_DWORD)result )
  {
    v11 = v28;
    if ( (v28 & 0xE03FF) == 0 )
      return 5;
    v28 = 0;
    if ( a3 == 2 )
    {
      ClientUserSID = GetClientUserSID();
      if ( ClientUserSID )
      {
        v15 = -1;
        EnterCriticalSection(&g_CsQueue);
        for ( i = g_QueueListHead.Flink; i != &g_QueueListHead; i = i->Flink )
        {
          if ( i[1].Flink == a2 )
          {
            if ( i )
            {
              if ( !AccessibleJob((struct _JOB_QUEUE *)i, 1, v11, ClientUserSID) )
              {
                LeaveCriticalSection(&g_CsQueue);
                PreviewFile = 7009;
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 513, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
                }
                goto LABEL_78;
              }
              PreviewFile = CreatePreviewFile((struct _JOB_QUEUE *)i);
              if ( PreviewFile )
              {
                LeaveCriticalSection(&g_CsQueue);
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    514,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    PreviewFile);
                }
                goto LABEL_78;
              }
              LeaveCriticalSection(&g_CsQueue);
              Blink = (WCHAR *)i[37].Blink;
              v17 = FileName;
              v18 = 2147483646;
              v28 = 1;
              v19 = 260;
              do
              {
                if ( !v18 )
                  break;
                if ( !*Blink )
                  break;
                *v17++ = *Blink++;
                --v18;
                --v19;
              }
              while ( v19 );
              v20 = v17 - 1;
              v21 = v19 == 0 ? 0x8007007A : 0;
              if ( v19 )
                v20 = v17;
              *v20 = 0;
              if ( !v19 )
              {
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    515,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    v21);
                }
                PreviewFile = (unsigned __int16)v21;
                if ( (v21 & 0x1FFF0000) != 0x70000 )
                  PreviewFile = v21;
                goto LABEL_78;
              }
LABEL_66:
              File = (void *)InternalSafeCreateFile(FileName, 0x80000000, 1u, 3u, 128);
              v15 = (__int64)File;
              if ( File == (void *)-1LL )
              {
                LastError = GetLastError();
                PreviewFile = LastError;
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    517,
                    (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    (unsigned int)FileName,
                    LastError);
                }
              }
              else
              {
                NewCopyHandle = CreateNewCopyHandle(a1, File, 0, 0, (struct _JOB_QUEUE *)i);
                if ( NewCopyHandle )
                {
                  *a4 = NewCopyHandle;
                }
                else
                {
                  v26 = GetLastError();
                  PreviewFile = v26;
                  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      518,
                      &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                      v26);
                  }
                }
              }
              if ( ClientUserSID )
LABEL_78:
                pMemFree(ClientUserSID);
              if ( PreviewFile )
              {
                if ( v28 )
                {
                  EnterCriticalSection(&g_CsQueue);
                  DecreaseJobRefCount((struct _JOB_QUEUE *)i, 1, 1, 1);
                  LeaveCriticalSection(&g_CsQueue);
                }
                if ( v15 != -1 )
                {
                  if ( CloseHandle((HANDLE)v15) )
                  {
                    v27 = GetLastError();
                    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        519,
                        &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                        v27);
                    }
                  }
                }
                goto LABEL_88;
              }
              goto LABEL_89;
            }
LABEL_30:
            LeaveCriticalSection(&g_CsQueue);
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 512, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
            }
            PreviewFile = 7009;
            goto LABEL_78;
          }
        }
        i = 0;
        goto LABEL_30;
      }
      v13 = GetLastError();
      PreviewFile = v13;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 511, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v13);
      }
      return PreviewFile;
    }
    v22 = FindArchivedMessageAfterAccessCheck(a3, a2, v11, 1, FileName);
    PreviewFile = v22;
    if ( !v22 )
    {
      ClientUserSID = 0;
      goto LABEL_66;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 516, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v22);
    }
LABEL_88:
    if ( PreviewFile != 8 )
    {
LABEL_89:
      if ( PreviewFile != 14 )
        return PreviewFile;
    }
    return 7001;
  }
  return result;
}

```

## disassembly

```asm
0x140021e70  push    rbx
0x140021e72  push    rbp
0x140021e73  push    rsi
0x140021e74  push    rdi
0x140021e75  push    r12
0x140021e77  push    r13
0x140021e79  push    r14
0x140021e7b  push    r15
0x140021e7d  sub     rsp, 278h
0x140021e84  mov     rax, cs:__security_cookie
0x140021e8b  xor     rax, rsp
0x140021e8e  mov     [rsp+2B8h+var_58], rax
0x140021e96  xor     esi, esi
0x140021e98  mov     r12, r9
0x140021e9b  mov     [rsp+2B8h+var_278], esi
0x140021e9f  mov     ebx, r8d
0x140021ea2  mov     rbp, rdx
0x140021ea5  mov     r13, rcx
0x140021ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x140021eaf  lea     r15, WPP_GLOBAL_Control
0x140021eb6  mov     r14b, 4
0x140021eb9  cmp     rcx, r15
0x140021ebc  jz      short loc_140021EE6
0x140021ebe  test    [rcx+1Ch], r14b
0x140021ec2  jz      short loc_140021EE6
0x140021ec4  cmp     byte ptr [rcx+19h], 5
0x140021ec8  jb      short loc_140021EE6
0x140021eca  mov     rcx, [rcx+10h]
0x140021ece  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021ed5  mov     edx, 1FCh
0x140021eda  call    WPP_SF_
0x140021edf  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ee6  test    rbp, rbp
0x140021ee9  jnz     short loc_140021F13
0x140021eeb  cmp     rcx, r15
0x140021eee  jz      short loc_140021F41
0x140021ef0  test    [rcx+1Ch], r14b
0x140021ef4  jz      short loc_140021F41
0x140021ef6  cmp     byte ptr [rcx+19h], 2
0x140021efa  jb      short loc_140021F41
0x140021efc  mov     rcx, [rcx+10h]
0x140021f00  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021f07  mov     edx, 1FDh
0x140021f0c  call    WPP_SF_
0x140021f11  jmp     short loc_140021F41
0x140021f13  cmp     ebx, 2
0x140021f16  jbe     short loc_140021F4B
0x140021f18  cmp     rcx, r15
0x140021f1b  jz      short loc_140021F41
0x140021f1d  test    [rcx+1Ch], r14b
0x140021f21  jz      short loc_140021F41
0x140021f23  cmp     byte ptr [rcx+19h], 2
0x140021f27  jb      short loc_140021F41
0x140021f29  mov     rcx, [rcx+10h]
0x140021f2d  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021f34  mov     edx, 1FEh
0x140021f39  mov     r9d, ebx
0x140021f3c  call    WPP_SF_d
0x140021f41  mov     eax, 57h ; 'W'
0x140021f46  jmp     loc_140022435
0x140021f4b  mov     r9d, 1; int
0x140021f51  mov     [rsp+2B8h+var_274], esi
0x140021f55  lea     r8, [rsp+2B8h+var_278]; unsigned int *
0x140021f5a  mov     ecx, 2000000h; unsigned int
0x140021f5f  lea     rdx, [rsp+2B8h+var_274]; int *
0x140021f64  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140021f69  test    eax, eax
0x140021f6b  jnz     loc_140022435
0x140021f71  mov     edi, [rsp+2B8h+var_278]
0x140021f75  test    edi, 0E03FFh
0x140021f7b  jnz     short loc_140021F87
0x140021f7d  mov     eax, 5
0x140021f82  jmp     loc_140022435
0x140021f87  mov     [rsp+2B8h+var_278], esi
0x140021f8b  cmp     ebx, 2
0x140021f8e  jnz     loc_14002221E
0x140021f94  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x140021f99  mov     r15, rax
0x140021f9c  test    rax, rax
0x140021f9f  jnz     short loc_140021FF7
0x140021fa1  call    cs:__imp_GetLastError
0x140021fa8  nop     dword ptr [rax+rax+00h]
0x140021fad  mov     ebx, eax
0x140021faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fb6  lea     r12, WPP_GLOBAL_Control
0x140021fbd  cmp     rcx, r12
0x140021fc0  jz      loc_140022433
0x140021fc6  test    [rcx+1Ch], r14b
0x140021fca  jz      loc_140022433
0x140021fd0  cmp     byte ptr [rcx+19h], 2
0x140021fd4  jb      loc_140022433
0x140021fda  mov     rcx, [rcx+10h]
0x140021fde  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021fe5  mov     edx, 1FFh
0x140021fea  mov     r9d, eax
0x140021fed  call    WPP_SF_d
0x140021ff2  jmp     loc_140022433
0x140021ff7  lea     rbx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsQueue
0x140021ffe  or      r14, 0FFFFFFFFFFFFFFFFh
0x140022002  mov     rcx, rbx; lpCriticalSection
0x140022005  call    cs:__imp_EnterCriticalSection
0x14002200c  nop     dword ptr [rax+rax+00h]
0x140022011  mov     rsi, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x140022018  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14002201f  jmp     short loc_14002202A
0x140022021  cmp     [rsi+10h], rbp
0x140022025  jz      short loc_140022080
0x140022027  mov     rsi, [rsi]
0x14002202a  cmp     rsi, rax
0x14002202d  jnz     short loc_140022021
0x14002202f  xor     ebp, ebp
0x140022031  mov     esi, ebp
0x140022033  mov     rcx, rbx; lpCriticalSection
0x140022036  call    cs:__imp_LeaveCriticalSection
0x14002203d  nop     dword ptr [rax+rax+00h]
0x140022042  mov     rcx, cs:WPP_GLOBAL_Control
0x140022049  lea     r12, WPP_GLOBAL_Control
0x140022050  cmp     rcx, r12
0x140022053  jz      short loc_140022076
0x140022055  test    byte ptr [rcx+1Ch], 4
0x140022059  jz      short loc_140022076
0x14002205b  cmp     byte ptr [rcx+19h], 2
0x14002205f  jb      short loc_140022076
0x140022061  mov     rcx, [rcx+10h]
0x140022065  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002206c  mov     edx, 200h
0x140022071  call    WPP_SF_
0x140022076  mov     ebx, 1B61h
0x14002207b  jmp     loc_140022380
0x140022080  xor     ebp, ebp
0x140022082  test    rsi, rsi
0x140022085  jz      short loc_140022033
0x140022087  mov     r9, r15; void *
0x14002208a  lea     edx, [rbp+1]; int
0x14002208d  mov     r8d, edi; unsigned int
0x140022090  mov     rcx, rsi; struct _JOB_QUEUE *
0x140022093  call    ?AccessibleJob@@YAHPEAU_JOB_QUEUE@@HKPEAX@Z; AccessibleJob(_JOB_QUEUE *,int,ulong,void *)
0x140022098  test    eax, eax
0x14002209a  jnz     short loc_1400220F5
0x14002209c  mov     rcx, rbx; lpCriticalSection
0x14002209f  call    cs:__imp_LeaveCriticalSection
0x1400220a6  nop     dword ptr [rax+rax+00h]
0x1400220ab  mov     ebx, 1B61h
0x1400220b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220b7  lea     r12, WPP_GLOBAL_Control
0x1400220be  cmp     rcx, r12
0x1400220c1  jz      loc_140022380
0x1400220c7  test    byte ptr [rcx+1Ch], 4
0x1400220cb  jz      loc_140022380
0x1400220d1  cmp     byte ptr [rcx+19h], 2
0x1400220d5  jb      loc_140022380
0x1400220db  mov     rcx, [rcx+10h]
0x1400220df  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400220e6  mov     edx, 201h
0x1400220eb  call    WPP_SF_
0x1400220f0  jmp     loc_140022380
0x1400220f5  mov     rcx, rsi; struct _JOB_QUEUE *
0x1400220f8  call    CreatePreviewFile
0x1400220fd  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140022104  mov     ebx, eax
0x140022106  test    eax, eax
0x140022108  jz      short loc_14002215E
0x14002210a  call    cs:__imp_LeaveCriticalSection
0x140022111  nop     dword ptr [rax+rax+00h]
0x140022116  mov     rcx, cs:WPP_GLOBAL_Control
0x14002211d  lea     r12, WPP_GLOBAL_Control
0x140022124  cmp     rcx, r12
0x140022127  jz      loc_140022380
0x14002212d  test    byte ptr [rcx+1Ch], 4
0x140022131  jz      loc_140022380
0x140022137  cmp     byte ptr [rcx+19h], 2
0x14002213b  jb      loc_140022380
0x140022141  mov     rcx, [rcx+10h]
0x140022145  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14002214c  mov     edx, 202h
0x140022151  mov     r9d, ebx
0x140022154  call    WPP_SF_d
0x140022159  jmp     loc_140022380
0x14002215e  call    cs:__imp_LeaveCriticalSection
0x140022165  nop     dword ptr [rax+rax+00h]
0x14002216a  mov     rcx, [rsi+258h]
0x140022171  lea     r8, [rsp+2B8h+FileName]
0x140022176  mov     eax, 7FFFFFFEh
0x14002217b  mov     [rsp+2B8h+var_278], 1
0x140022183  mov     edx, 104h
0x140022188  test    rax, rax
0x14002218b  jz      short loc_1400221AC
0x14002218d  movzx   r9d, word ptr [rcx]
0x140022191  test    r9w, r9w
0x140022195  jz      short loc_1400221AC
0x140022197  mov     [r8], r9w
0x14002219b  add     rcx, 2
0x14002219f  add     r8, 2
0x1400221a3  dec     rax
0x1400221a6  sub     rdx, 1
0x1400221aa  jnz     short loc_140022188
0x1400221ac  mov     rax, rdx
0x1400221af  lea     rcx, [r8-2]
0x1400221b3  neg     rax
0x1400221b6  sbb     edi, edi
0x1400221b8  not     edi
0x1400221ba  and     edi, 8007007Ah
0x1400221c0  test    rdx, rdx
0x1400221c3  cmovnz  rcx, r8
0x1400221c7  mov     [rcx], bp
0x1400221ca  jnz     loc_140022287
0x1400221d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221d7  lea     r12, WPP_GLOBAL_Control
0x1400221de  cmp     rcx, r12
0x1400221e1  jz      short loc_140022207
0x1400221e3  test    byte ptr [rcx+1Ch], 4
0x1400221e7  jz      short loc_140022207
0x1400221e9  cmp     byte ptr [rcx+19h], 2
0x1400221ed  jb      short loc_140022207
0x1400221ef  mov     rcx, [rcx+10h]
0x1400221f3  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400221fa  mov     edx, 203h
0x1400221ff  mov     r9d, edi
0x140022202  call    WPP_SF_d
0x140022207  mov     eax, edi
0x140022209  movzx   ebx, di
0x14002220c  and     eax, 1FFF0000h
0x140022211  cmp     eax, 70000h
0x140022216  cmovnz  ebx, edi
0x140022219  jmp     loc_140022380
0x14002221e  lea     rax, [rsp+2B8h+FileName]
0x140022223  mov     r9d, 1
0x140022229  mov     r8d, edi
0x14002222c  mov     qword ptr [rsp+2B8h+var_298], rax
0x140022231  mov     rdx, rbp
0x140022234  mov     ecx, ebx
0x140022236  call    FindArchivedMessageAfterAccessCheck
0x14002223b  xor     ebp, ebp
0x14002223d  mov     ebx, eax
0x14002223f  test    eax, eax
0x140022241  jz      short loc_140022284
0x140022243  mov     rcx, cs:WPP_GLOBAL_Control
0x14002224a  cmp     rcx, r15
0x14002224d  jz      loc_140022424
0x140022253  test    [rcx+1Ch], r14b
0x140022257  jz      loc_140022424
0x14002225d  cmp     byte ptr [rcx+19h], 2
0x140022261  jb      loc_140022424
0x140022267  mov     rcx, [rcx+10h]
0x14002226b  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022272  mov     edx, 204h
0x140022277  mov     r9d, eax
0x14002227a  call    WPP_SF_d
0x14002227f  jmp     loc_140022424
0x140022284  mov     r15, rbp
0x140022287  mov     [rsp+2B8h+var_290], 80h; int
0x14002228f  lea     rcx, [rsp+2B8h+FileName]; lpFileName
0x140022294  mov     edx, 80000000h; dwDesiredAccess
0x140022299  mov     [rsp+2B8h+var_298], 3; DWORD
0x1400222a1  mov     r8d, 1; dwShareMode
0x1400222a7  call    InternalSafeCreateFile
0x1400222ac  mov     r14, rax
0x1400222af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400222b3  jnz     short loc_14002230E
0x1400222b5  call    cs:__imp_GetLastError
0x1400222bc  nop     dword ptr [rax+rax+00h]
0x1400222c1  mov     ebx, eax
0x1400222c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400222ca  lea     r12, WPP_GLOBAL_Control
0x1400222d1  cmp     rcx, r12
0x1400222d4  jz      loc_14002237B
0x1400222da  test    byte ptr [rcx+1Ch], 4
0x1400222de  jz      loc_14002237B
0x1400222e4  cmp     byte ptr [rcx+19h], 2
0x1400222e8  jb      loc_14002237B
0x1400222ee  mov     rcx, [rcx+10h]
0x1400222f2  lea     r9, [rsp+2B8h+FileName]
0x1400222f7  mov     edx, 205h
0x1400222fc  mov     [rsp+2B8h+var_298], eax
0x140022300  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022307  call    WPP_SF_Sd
0x14002230c  jmp     short loc_14002237B
0x14002230e  xor     r9d, r9d; unsigned __int16 *
0x140022311  mov     qword ptr [rsp+2B8h+var_298], rsi; struct _JOB_QUEUE *
0x140022316  xor     r8d, r8d; int
0x140022319  mov     rdx, rax; void *
0x14002231c  mov     rcx, r13; void *
0x14002231f  call    ?CreateNewCopyHandle@@YAPEAU_HANDLE_ENTRY@@PEAX0HPEBGPEAU_JOB_QUEUE@@@Z; CreateNewCopyHandle(void *,void *,int,ushort const *,_JOB_QUEUE *)
0x140022324  test    rax, rax
0x140022327  jnz     short loc_140022370
0x140022329  call    cs:__imp_GetLastError
0x140022330  nop     dword ptr [rax+rax+00h]
0x140022335  mov     ebx, eax
0x140022337  mov     rcx, cs:WPP_GLOBAL_Control
0x14002233e  lea     r12, WPP_GLOBAL_Control
0x140022345  cmp     rcx, r12
0x140022348  jz      short loc_14002237B
0x14002234a  test    byte ptr [rcx+1Ch], 4
0x14002234e  jz      short loc_14002237B
0x140022350  cmp     byte ptr [rcx+19h], 2
0x140022354  jb      short loc_14002237B
0x140022356  mov     rcx, [rcx+10h]
0x14002235a  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140022361  mov     edx, 206h
0x140022366  mov     r9d, eax
  ... truncated ...
```
