# UbpmHardeningListInsert

- ea: `0x18000ec90`
- end: `0x18000f27b`
- name: `UbpmHardeningListInsert`
- size: `1515`
- prototype: `__int64 __usercall@<rax>(wchar_t *String2@<rcx>, __int64, char, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012b70`

## callees

- `0x18000ec90`
- `0x18000fbf0`
- `0x1800150c0`
- `0x18001af64`
- `0x18001d1d8`
- `0x18002719c`
- `0x18003f074`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000efc6`
- `msvcrt!_wcsicmp` at `0x18000efc6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ed0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ed0b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000ed7e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f002`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000ed7e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f002`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18000ef49`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18000ef84`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18000ef49`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18000ef84`
- `ntdll!RtlInitUnicodeString` at `0x18000ef2e`
- `ntdll!RtlInitUnicodeString` at `0x18000ef2e`
- `ntdll!RtlNtStatusToDosError` at `0x18000f1da`
- `ntdll!RtlNtStatusToDosError` at `0x18000f1da`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ee19`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ee19`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000eea2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f174`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000eea2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1fe`

## pseudocode

```c
__int64 __fastcall UbpmHardeningListInsert(
        wchar_t *String2,
        const WCHAR *a2,
        __int64 a3,
        void *a4,
        struct _LIST_ENTRY *a5,
        char a6,
        char a7)
{
  DWORD v7; // ebx
  unsigned int v9; // ebp
  struct _LIST_ENTRY *v11; // r13
  DWORD v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 LengthSid; // r15
  __int64 v17; // rbx
  unsigned int v19; // ebx
  struct _LIST_ENTRY *v20; // rax
  char v21; // bp
  unsigned __int64 v22; // r8
  struct _LIST_ENTRY *Flink; // r9
  __int64 v24; // rcx
  wchar_t *v25; // rdx
  struct _LIST_ENTRY *v26; // rcx
  DWORD CurrentThreadId; // eax
  struct _LIST_ENTRY *v28; // rbx
  struct _LIST_ENTRY *v29; // rdi
  unsigned __int8 i; // si
  struct _LIST_ENTRY *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  void *v36; // rax
  void *v37; // rsi
  NTSTATUS v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  PSID v42; // r8
  struct _LIST_ENTRY *v43; // rdx
  struct _LIST_ENTRY *v44; // rax
  ULONG LastError; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  ULONG v49; // ebp
  SIZE_T Size; // [rsp+30h] [rbp-58h] BYREF
  PSID pSourceSid; // [rsp+38h] [rbp-50h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v54; // [rsp+A0h] [rbp+18h]

  v54 = a3;
  v7 = 0;
  v9 = a3;
  pSourceSid = 0;
  v11 = 0;
  if ( !a4 || !a5 && !a6 )
    goto LABEL_30;
  if ( !UbpmUtilsSidSupportsHardening(a4) || !String2 )
  {
    v7 = 87;
    goto LABEL_30;
  }
  v12 = 0;
  LengthSid = GetLengthSid(a4);
  v17 = -1;
  while ( String2[++v17] != 0 )
    ;
  if ( a6 == 1 )
  {
    LODWORD(Size) = 0;
    DestinationString = 0;
    if ( v9 - 80 > 0x1F )
    {
      v7 = 87;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, String2);
      if ( (unsigned int)RtlCreateVirtualAccountSid(&DestinationString, v9, 0, &Size) == -1073741789 )
      {
        v36 = UbpmAlloc((unsigned int)Size);
        v37 = v36;
        if ( v36 )
        {
          v38 = RtlCreateVirtualAccountSid(&DestinationString, v9, v36, &Size);
          if ( v38 >= 0 )
          {
            v12 = Size;
            pSourceSid = v37;
            UBPM_MIDL_user_free(0, v39, v40, v41);
            goto LABEL_9;
          }
          LastError = RtlNtStatusToDosError(v38);
        }
        else
        {
          LastError = GetLastError();
        }
        v49 = LastError;
        UBPM_MIDL_user_free(v37, v46, v47, v48);
        if ( !v49 )
        {
          v9 = v54;
          goto LABEL_9;
        }
        v7 = v49;
LABEL_58:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            (_DWORD)String2,
            v49);
        goto LABEL_30;
      }
      v7 = 13;
    }
    LOBYTE(v49) = v7;
    UBPM_MIDL_user_free(0, v13, v14, v15);
    goto LABEL_58;
  }
LABEL_9:
  v19 = 2 * v17 + 2;
  v20 = (struct _LIST_ENTRY *)UbpmAlloc(v12 + v19 + (_DWORD)LengthSid + 64);
  v11 = v20;
  if ( v20 )
  {
    HIDWORD(v20[3].Blink) = v9;
    v20[1].Blink = v20 + 4;
    v20[1].Flink = (struct _LIST_ENTRY *)((char *)v20 + LengthSid + v12 + 64);
    if ( CopySid(LengthSid, &v20[4], a4) )
    {
      if ( a6 == 1 )
      {
        v42 = pSourceSid;
        v43 = (struct _LIST_ENTRY *)((char *)v11[1].Blink + LengthSid);
        v11[3].Flink = v43;
        if ( !CopySid(v12, v43, v42) )
        {
          v7 = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
              (_DWORD)String2,
              v7);
          goto LABEL_30;
        }
      }
      v21 = 0;
      v22 = (unsigned __int64)v19 >> 1;
      if ( v22 )
      {
        Flink = v11[1].Flink;
        v24 = 2147483646;
        v25 = String2;
        do
        {
          if ( !v24 )
            break;
          if ( !*v25 )
            break;
          LOWORD(Flink->Flink) = *v25++;
          Flink = (struct _LIST_ENTRY *)((char *)Flink + 2);
          --v24;
          --v22;
        }
        while ( v22 );
        v26 = (struct _LIST_ENTRY *)((char *)Flink - 2);
        if ( v22 )
          v26 = Flink;
        LOWORD(v26->Flink) = 0;
      }
      v11->Blink = v11;
      v11->Flink = v11;
      v11[2].Flink = a5;
      LOBYTE(v11[2].Blink) = a6;
      LODWORD(v11[3].Blink) = -1;
      RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
      CurrentThreadId = GetCurrentThreadId();
      v28 = g_leTaskHostHardeningListHead.Flink;
      v29 = &g_leTaskHostHardeningListHead;
      dword_180050018 = CurrentThreadId;
      for ( i = 0; i < 2u; ++i )
      {
        while ( v28 != v29 )
        {
          if ( !_wcsicmp((const wchar_t *)v28[1].Flink, String2) )
          {
            dword_180050018 = 0;
            RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
            v7 = 183;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                62,
                (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                (_DWORD)String2,
                183);
            goto LABEL_30;
          }
          v28 = v28->Flink;
          if ( v54 == HIDWORD(v11[3].Blink) )
            v21 = 1;
        }
        v28 = g_leNonHostHardeningListHead.Flink;
        v29 = &g_leNonHostHardeningListHead;
      }
      if ( a7 )
      {
        v44 = off_18004F140[0];
        if ( off_18004F140[0]->Flink == &g_leTaskHostHardeningListHead )
        {
          v11->Flink = &g_leTaskHostHardeningListHead;
          v11->Blink = v44;
          v44->Flink = v11;
          off_18004F140[0] = v11;
          goto LABEL_25;
        }
      }
      else
      {
        v31 = off_18004F160[0];
        if ( off_18004F160[0]->Flink == &g_leNonHostHardeningListHead )
        {
          v11->Flink = &g_leNonHostHardeningListHead;
          v11->Blink = v31;
          v31->Flink = v11;
          off_18004F160[0] = v11;
LABEL_25:
          dword_180050018 = 0;
          RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
          if ( a6 )
          {
            if ( !v21 )
              UbpmUpdateConsumerSidCache(a2);
            UbpmUpdateConsumerSidCache(a2);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_Sid(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, a3, (_DWORD)String2, (char)a5, a6);
          v7 = 0;
          v11 = 0;
          goto LABEL_30;
        }
      }
      __fastfail(3u);
    }
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
        (_DWORD)String2,
        v7);
  }
  else
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
        (_DWORD)String2,
        v7);
  }
LABEL_30:
  UBPM_MIDL_user_free(v11, a2, a3, a4);
  UBPM_MIDL_user_free(pSourceSid, v32, v33, v34);
  return v7;
}

```

## disassembly

```asm
0x18000ec90  mov     [rsp+arg_0], rbx
0x18000ec95  mov     [rsp+arg_10], r8d
0x18000ec9a  mov     [rsp+SourceString], rdx
0x18000ec9f  push    rbp
0x18000eca0  push    rsi
0x18000eca1  push    rdi
0x18000eca2  push    r12
0x18000eca4  push    r13
0x18000eca6  push    r14
0x18000eca8  push    r15
0x18000ecaa  sub     rsp, 50h
0x18000ecae  xor     ebx, ebx
0x18000ecb0  mov     rdi, r9
0x18000ecb3  mov     [rsp+88h+arg_18], ebx
0x18000ecba  mov     ebp, r8d
0x18000ecbd  mov     [rsp+88h+pSourceSid], rbx
0x18000ecc2  mov     r12, rcx
0x18000ecc5  mov     r13d, ebx
0x18000ecc8  test    r9, r9
0x18000eccb  jz      loc_18000EF0B
0x18000ecd1  movzx   esi, [rsp+88h+arg_28]
0x18000ecd9  cmp     [rsp+88h+arg_20], rbx
0x18000ece1  jnz     short loc_18000ECEC
0x18000ece3  test    sil, sil
0x18000ece6  jz      loc_18000EF0B
0x18000ecec  mov     rcx, rdi; pSid1
0x18000ecef  call    ?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z; UbpmUtilsSidSupportsHardening(void *)
0x18000ecf4  test    al, al
0x18000ecf6  jz      loc_18000F1C7
0x18000ecfc  test    r12, r12
0x18000ecff  jz      loc_18000F1C7
0x18000ed05  mov     rcx, rdi; pSid
0x18000ed08  mov     r14d, ebx
0x18000ed0b  call    cs:__imp_GetLengthSid
0x18000ed12  nop     dword ptr [rax+rax+00h]
0x18000ed17  mov     r15d, eax
0x18000ed1a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ed21  cmp     [r12+rbx*2+2], r13w
0x18000ed27  lea     rbx, [rbx+1]
0x18000ed2b  jnz     short loc_18000ED21
0x18000ed2d  cmp     sil, 1
0x18000ed31  jz      loc_18000EF0D
0x18000ed37  lea     ecx, [r15+40h]
0x18000ed3b  lea     ebx, ds:2[rbx*2]
0x18000ed42  add     ecx, ebx
0x18000ed44  add     ecx, r14d; Size
0x18000ed47  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000ed4c  mov     r13, rax
0x18000ed4f  test    rax, rax
0x18000ed52  jz      loc_18000F0C4
0x18000ed58  lea     rdx, [rax+40h]; pDestinationSid
0x18000ed5c  mov     [r13+3Ch], ebp
0x18000ed60  mov     [rax+18h], rdx
0x18000ed64  mov     r8, rdi; pSourceSid
0x18000ed67  mov     eax, r14d
0x18000ed6a  mov     ecx, r15d; nDestinationSidLength
0x18000ed6d  add     rax, 40h ; '@'
0x18000ed71  mov     rsi, r15
0x18000ed74  add     rax, r15
0x18000ed77  add     rax, r13
0x18000ed7a  mov     [r13+10h], rax
0x18000ed7e  call    cs:__imp_CopySid
0x18000ed85  nop     dword ptr [rax+rax+00h]
0x18000ed8a  test    eax, eax
0x18000ed8c  jz      loc_18000F1FE
0x18000ed92  movzx   r15d, [rsp+88h+arg_28]
0x18000ed9b  cmp     r15b, 1
0x18000ed9f  jz      loc_18000EFEF
0x18000eda5  xor     bpl, bpl
0x18000eda8  mov     r8d, ebx
0x18000edab  shr     r8, 1
0x18000edae  jz      short loc_18000EDF2
0x18000edb0  mov     r9, [r13+10h]
0x18000edb4  mov     ecx, 7FFFFFFEh
0x18000edb9  mov     rdx, r12
0x18000edbc  nop     dword ptr [rax+00h]
0x18000edc0  test    rcx, rcx
0x18000edc3  jz      short loc_18000EDE2
0x18000edc5  movzx   eax, word ptr [rdx]
0x18000edc8  test    ax, ax
0x18000edcb  jz      short loc_18000EDE2
0x18000edcd  mov     [r9], ax
0x18000edd1  add     rdx, 2
0x18000edd5  add     r9, 2
0x18000edd9  dec     rcx
0x18000eddc  sub     r8, 1
0x18000ede0  jnz     short loc_18000EDC0
0x18000ede2  test    r8, r8
0x18000ede5  lea     rcx, [r9-2]
0x18000ede9  cmovnz  rcx, r9
0x18000eded  xor     eax, eax
0x18000edef  mov     [rcx], ax
0x18000edf2  mov     rax, [rsp+88h+arg_20]
0x18000edfa  lea     rcx, g_TaskHostContextListLock
0x18000ee01  mov     [r13+8], r13
0x18000ee05  mov     [r13+0], r13
0x18000ee09  mov     [r13+20h], rax
0x18000ee0d  mov     [r13+28h], r15b
0x18000ee11  mov     dword ptr [r13+38h], 0FFFFFFFFh
0x18000ee19  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000ee20  nop     dword ptr [rax+rax+00h]
0x18000ee25  call    cs:__imp_GetCurrentThreadId
0x18000ee2c  nop     dword ptr [rax+rax+00h]
0x18000ee31  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18000ee38  lea     rdi, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18000ee3f  mov     r14d, [rsp+88h+arg_10]
0x18000ee47  lea     rcx, ?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x18000ee4e  mov     cs:dword_180050018, eax
0x18000ee54  xor     sil, sil
0x18000ee57  cmp     sil, 2
0x18000ee5b  jb      loc_18000EFB6
0x18000ee61  cmp     [rsp+88h+arg_30], 0
0x18000ee69  jnz     loc_18000F096
0x18000ee6f  mov     rax, cs:off_18004F160
0x18000ee76  cmp     [rax], rcx
0x18000ee79  jnz     loc_18000F15C
0x18000ee7f  mov     [r13+0], rcx
0x18000ee83  mov     [r13+8], rax
0x18000ee87  mov     [rax], r13
0x18000ee8a  mov     cs:off_18004F160, r13
0x18000ee91  lea     rcx, g_TaskHostContextListLock
0x18000ee98  mov     cs:dword_180050018, 0
0x18000eea2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000eea9  nop     dword ptr [rax+rax+00h]
0x18000eeae  test    r15b, r15b
0x18000eeb1  jnz     loc_18000F06C
0x18000eeb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eebe  lea     rax, WPP_GLOBAL_Control
0x18000eec5  cmp     rcx, rax
0x18000eec8  jz      short loc_18000EED4
0x18000eeca  test    byte ptr [rcx+1Ch], 80h
0x18000eece  jnz     loc_18000F253
0x18000eed4  mov     ebx, [rsp+88h+arg_18]
0x18000eedb  xor     r13d, r13d
0x18000eede  mov     rcx, r13
0x18000eee1  call    UBPM_MIDL_user_free
0x18000eee6  mov     rcx, [rsp+88h+pSourceSid]
0x18000eeeb  call    UBPM_MIDL_user_free
0x18000eef0  mov     eax, ebx
0x18000eef2  mov     rbx, [rsp+88h+arg_0]
0x18000eefa  add     rsp, 50h
0x18000eefe  pop     r15
0x18000ef00  pop     r14
0x18000ef02  pop     r13
0x18000ef04  pop     r12
0x18000ef06  pop     rdi
0x18000ef07  pop     rsi
0x18000ef08  pop     rbp
0x18000ef09  retn
0x18000ef0b  jmp     short loc_18000EEDE
0x18000ef0d  lea     eax, [rbp-50h]
0x18000ef10  mov     dword ptr [rsp+88h+Size], r13d
0x18000ef15  xorps   xmm0, xmm0
0x18000ef18  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18000ef1d  cmp     eax, 1Fh
0x18000ef20  ja      loc_18000F1EB
0x18000ef26  mov     rdx, r12; SourceString
0x18000ef29  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18000ef2e  call    cs:__imp_RtlInitUnicodeString
0x18000ef35  nop     dword ptr [rax+rax+00h]
0x18000ef3a  lea     r9, [rsp+88h+Size]
0x18000ef3f  xor     r8d, r8d
0x18000ef42  mov     edx, ebp
0x18000ef44  lea     rcx, [rsp+88h+DestinationString]
0x18000ef49  call    cs:__imp_RtlCreateVirtualAccountSid
0x18000ef50  nop     dword ptr [rax+rax+00h]
0x18000ef55  cmp     eax, 0C0000023h
0x18000ef5a  jnz     loc_18000F1D1
0x18000ef60  mov     ecx, dword ptr [rsp+88h+Size]; Size
0x18000ef64  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000ef69  mov     rsi, rax
0x18000ef6c  test    rax, rax
0x18000ef6f  jz      loc_18000F101
0x18000ef75  lea     r9, [rsp+88h+Size]
0x18000ef7a  mov     r8, rax
0x18000ef7d  mov     edx, ebp
0x18000ef7f  lea     rcx, [rsp+88h+DestinationString]
0x18000ef84  call    cs:__imp_RtlCreateVirtualAccountSid
0x18000ef8b  nop     dword ptr [rax+rax+00h]
0x18000ef90  test    eax, eax
0x18000ef92  js      loc_18000F1D8
0x18000ef98  mov     r14d, dword ptr [rsp+88h+Size]
0x18000ef9d  xor     ecx, ecx
0x18000ef9f  mov     [rsp+88h+pSourceSid], rsi
0x18000efa4  call    UBPM_MIDL_user_free
0x18000efa9  mov     [rsp+88h+arg_18], r13d
0x18000efb1  jmp     loc_18000ED37
0x18000efb6  cmp     rbx, rdi
0x18000efb9  jz      loc_18000F053
0x18000efbf  mov     rcx, [rbx+10h]; String1
0x18000efc3  mov     rdx, r12; String2
0x18000efc6  call    cs:__imp__wcsicmp
0x18000efcd  nop     dword ptr [rax+rax+00h]
0x18000efd2  test    eax, eax
0x18000efd4  jz      loc_18000F163
0x18000efda  cmp     r14d, [r13+3Ch]
0x18000efde  mov     eax, 1
0x18000efe3  mov     rbx, [rbx]
0x18000efe6  movzx   ebp, bpl
0x18000efea  cmovz   ebp, eax
0x18000efed  jmp     short loc_18000EFB6
0x18000efef  mov     rdx, [r13+18h]
0x18000eff3  mov     ecx, r14d; nDestinationSidLength
0x18000eff6  mov     r8, [rsp+88h+pSourceSid]; pSourceSid
0x18000effb  add     rdx, rsi; pDestinationSid
0x18000effe  mov     [r13+30h], rdx
0x18000f002  call    cs:__imp_CopySid
0x18000f009  nop     dword ptr [rax+rax+00h]
0x18000f00e  test    eax, eax
0x18000f010  jnz     loc_18000EDA5
0x18000f016  call    cs:__imp_GetLastError
0x18000f01d  nop     dword ptr [rax+rax+00h]
0x18000f022  mov     ebx, eax
0x18000f024  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f02b  lea     rax, WPP_GLOBAL_Control
0x18000f032  cmp     rcx, rax
0x18000f035  jz      loc_18000EEDE
0x18000f03b  test    byte ptr [rcx+1Ch], 1
0x18000f03f  jz      loc_18000EEDE
0x18000f045  mov     edx, 3Dh ; '='
0x18000f04a  mov     dword ptr [rsp+88h+var_68], ebx
0x18000f04e  jmp     loc_18000F1AF
0x18000f053  mov     rbx, cs:?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x18000f05a  lea     rcx, ?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x18000f061  mov     rdi, rcx
0x18000f064  inc     sil
0x18000f067  jmp     loc_18000EE57
0x18000f06c  mov     rbx, [rsp+88h+SourceString]
0x18000f074  test    bpl, bpl
0x18000f077  jz      loc_18000F23B
0x18000f07d  mov     r9d, 1
0x18000f083  mov     r8d, r14d
0x18000f086  mov     rdx, r12
0x18000f089  mov     rcx, rbx; SourceString
0x18000f08c  call    UbpmUpdateConsumerSidCache
0x18000f091  jmp     loc_18000EEB7
0x18000f096  mov     rax, cs:off_18004F140
0x18000f09d  lea     rcx, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18000f0a4  cmp     [rax], rcx
0x18000f0a7  jnz     loc_18000F15C
0x18000f0ad  mov     [r13+0], rcx
0x18000f0b1  mov     [r13+8], rax
0x18000f0b5  mov     [rax], r13
0x18000f0b8  mov     cs:off_18004F140, r13
0x18000f0bf  jmp     loc_18000EE91
0x18000f0c4  call    cs:__imp_GetLastError
0x18000f0cb  nop     dword ptr [rax+rax+00h]
0x18000f0d0  mov     ebx, eax
0x18000f0d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0d9  lea     rax, WPP_GLOBAL_Control
0x18000f0e0  cmp     rcx, rax
0x18000f0e3  jz      loc_18000EEDE
0x18000f0e9  test    byte ptr [rcx+1Ch], 1
0x18000f0ed  jz      loc_18000EEDE
0x18000f0f3  mov     edx, 3Bh ; ';'
0x18000f0f8  mov     dword ptr [rsp+88h+var_68], ebx
0x18000f0fc  jmp     loc_18000F1AF
0x18000f101  call    cs:__imp_GetLastError
0x18000f108  nop     dword ptr [rax+rax+00h]
0x18000f10d  mov     ebp, eax
0x18000f10f  mov     rcx, rsi
0x18000f112  call    UBPM_MIDL_user_free
0x18000f117  mov     [rsp+88h+arg_18], ebp
0x18000f11e  test    ebp, ebp
0x18000f120  jz      short loc_18000F150
0x18000f122  mov     ebx, ebp
0x18000f124  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f12b  lea     rax, WPP_GLOBAL_Control
0x18000f132  cmp     rcx, rax
0x18000f135  jz      loc_18000EEDE
0x18000f13b  test    byte ptr [rcx+1Ch], 1
0x18000f13f  jz      loc_18000EEDE
0x18000f145  mov     edx, 3Ah ; ':'
0x18000f14a  mov     dword ptr [rsp+88h+var_68], ebp
0x18000f14e  jmp     short loc_18000F1AF
0x18000f150  mov     ebp, [rsp+88h+arg_10]
0x18000f157  jmp     loc_18000ED37
0x18000f15c  mov     ecx, 3
0x18000f161  int     29h; Win8: RtlFailFast(ecx)
0x18000f163  lea     rcx, g_TaskHostContextListLock
0x18000f16a  mov     cs:dword_180050018, 0
0x18000f174  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000f17b  nop     dword ptr [rax+rax+00h]
0x18000f180  mov     ebx, 0B7h
0x18000f185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f18c  lea     rax, WPP_GLOBAL_Control
0x18000f193  cmp     rcx, rax
0x18000f196  jz      loc_18000EEDE
0x18000f19c  test    byte ptr [rcx+1Ch], 1
0x18000f1a0  jz      loc_18000EEDE
0x18000f1a6  mov     edx, 3Eh ; '>'
0x18000f1ab  mov     dword ptr [rsp+88h+var_68], ebx
0x18000f1af  mov     rcx, [rcx+10h]
0x18000f1b3  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000f1ba  mov     r9, r12
0x18000f1bd  call    WPP_SF_Sd
0x18000f1c2  jmp     loc_18000EEDE
0x18000f1c7  mov     ebx, 57h ; 'W'
0x18000f1cc  jmp     loc_18000EEDE
0x18000f1d1  mov     ebx, 0Dh
  ... truncated ...
```
