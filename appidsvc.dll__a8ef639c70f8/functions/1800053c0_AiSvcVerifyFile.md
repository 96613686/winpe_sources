# AiSvcVerifyFile

- ea: `0x1800053c0`
- end: `0x1800057fc`
- name: `AiSvcVerifyFile`
- size: `1084`
- prototype: `__int64 __fastcall(void *, _DWORD *, _QWORD *, _DWORD *, PVOID *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x18000b500`

## callees

- `0x1800049a8`
- `0x1800053c0`
- `0x180005804`
- `0x1800058c4`
- `0x18000880c`
- `0x180008ad4`
- `0x180008c14`
- `0x18000c0e0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005583`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800054e6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000550d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800054e6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000550d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800054a1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800057b2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800054a1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800057b2`
- `ntdll!RtlFreeHeap` at `0x1800054bd`
- `ntdll!RtlFreeHeap` at `0x180005752`
- `ntdll!RtlFreeHeap` at `0x18000576a`
- `ntdll!RtlFreeHeap` at `0x180005788`
- `ntdll!RtlFreeHeap` at `0x1800057a6`
- `ntdll!RtlFreeHeap` at `0x1800054bd`
- `ntdll!RtlFreeHeap` at `0x180005752`
- `ntdll!RtlFreeHeap` at `0x18000576a`
- `ntdll!RtlFreeHeap` at `0x180005788`
- `ntdll!RtlFreeHeap` at `0x1800057a6`
- `ntdll!EtwEventWriteTransfer` at `0x1800056fe`
- `ntdll!EtwEventWriteTransfer` at `0x1800056fe`
- `ntdll!RtlInitUnicodeString` at `0x180005526`
- `ntdll!RtlInitUnicodeString` at `0x180005526`

## pseudocode

```c
__int64 __fastcall AiSvcVerifyFile(
        void *a1,
        _DWORD *a2,
        _QWORD *a3,
        _DWORD *a4,
        PVOID *a5,
        _QWORD *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  DWORD FinalPathNameByHandleW; // esi
  WCHAR *v10; // rdi
  DWORD v11; // ebx
  char v12; // r15
  DWORD v13; // r14d
  WCHAR *v14; // rax
  int v15; // r8d
  int v16; // r9d
  int v17; // edx
  unsigned int TrustedPublisherName; // ebx
  int v19; // r8d
  void (__fastcall *v20)(__int64 *, const wchar_t *, _QWORD); // rax
  const wchar_t *v21; // rdx
  __int64 *v22; // rcx
  DWORD LastError; // eax
  PVOID v24; // rax
  _QWORD *v25; // rcx
  int v26; // eax
  int v27; // edx
  int v28; // r8d
  __int16 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v31; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD *v32; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID v36[2]; // [rsp+80h] [rbp-80h] BYREF
  PVOID v37[2]; // [rsp+90h] [rbp-70h]
  __int128 v38; // [rsp+A0h] [rbp-60h]
  _QWORD *v39; // [rsp+B0h] [rbp-50h]
  _DWORD *v40; // [rsp+B8h] [rbp-48h]
  PVOID *v41; // [rsp+C0h] [rbp-40h]
  _DWORD *v42; // [rsp+C8h] [rbp-38h]
  _QWORD *v43; // [rsp+D0h] [rbp-30h]
  GUID ActivityId; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v45[3]; // [rsp+F0h] [rbp-10h] BYREF
  int Length; // [rsp+108h] [rbp+8h]
  int v47; // [rsp+10Ch] [rbp+Ch]
  __int16 *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  __int64 v50; // [rsp+120h] [rbp+20h]
  int v51; // [rsp+128h] [rbp+28h]
  int v52; // [rsp+12Ch] [rbp+2Ch]
  _QWORD **v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+138h] [rbp+38h]

  v41 = a5;
  FinalPathNameByHandleW = 260;
  v43 = a6;
  v10 = 0;
  v32 = a7;
  v42 = a4;
  v39 = a3;
  v40 = a2;
  P[0] = 0;
  P[1] = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v34 = 0u;
  *(_OWORD *)v36 = 0;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  ActivityId = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_3e8fbce33354377c6a2bfec1a49552c9_Traceguids,
      "AiSvcVerifyFile");
  v11 = 8;
  v12 = 0;
  EventActivityIdControl(5u, &ActivityId);
  while ( 1 )
  {
    v13 = FinalPathNameByHandleW + 1;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    v14 = (WCHAR *)AiAlloc(2LL * (FinalPathNameByHandleW + 1));
    v10 = v14;
    if ( !v14 )
    {
      TrustedPublisherName = -1073741801;
      goto LABEL_23;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, v14, v13, v11);
    if ( !FinalPathNameByHandleW )
    {
      if ( v12 )
        break;
      v11 |= 1u;
      v12 = 1;
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, v10, v13, v11);
      if ( !FinalPathNameByHandleW )
        break;
    }
    if ( FinalPathNameByHandleW < v13 )
    {
      RtlInitUnicodeString(&DestinationString, v10);
      *a8 = 0;
      TrustedPublisherName = AiGetTrustedPublisherName((int)a1, (int)v10, v15, v16, (__int64)v36, (PUNICODE_STRING)P);
      *v32 = *((_QWORD *)&v38 + 1);
      if ( (TrustedPublisherName & 0x80000000) != 0 )
      {
        v20 = (void (__fastcall *)(__int64 *, const wchar_t *, _QWORD))g_AiLogFunctionCallErrorEvent;
        if ( !g_AiLogFunctionCallErrorEvent )
          goto LABEL_23;
        v21 = L"24";
        v22 = &qword_18000EDE0;
        goto LABEL_17;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_ZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v19, (unsigned int)&DestinationString, (__int64)P);
      v24 = v36[1];
      v25 = v39;
      v34 = *(_OWORD *)P;
      *a8 = _mm_srli_si128(*(__m128i *)P, 8).m128i_u64[0];
      *v25 = v24;
      LODWORD(v24) = v36[0];
      P[1] = 0;
      *(_OWORD *)v36 = 0;
      *v40 = (_DWORD)v24;
      *v41 = v37[1];
      LODWORD(v24) = v37[0];
      *(_OWORD *)v37 = 0;
      *v42 = (_DWORD)v24;
      *v43 = v38;
      goto LABEL_23;
    }
  }
  LastError = GetLastError();
  TrustedPublisherName = LastError;
  if ( LastError )
    TrustedPublisherName = (unsigned __int16)LastError | 0x80070000;
  v20 = (void (__fastcall *)(__int64 *, const wchar_t *, _QWORD))g_AiLogFunctionCallErrorEvent;
  if ( g_AiLogFunctionCallErrorEvent )
  {
    v21 = L"24";
    v22 = &qword_18000EE00;
LABEL_17:
    v20(v22, v21, TrustedPublisherName);
  }
LABEL_23:
  v30 = DestinationString.Length >> 1;
  LODWORD(v32) = TrustedPublisherName;
  v45[0] = &v30;
  v45[2] = DestinationString.Buffer;
  Length = DestinationString.Length;
  v31 = (unsigned __int16)v34 >> 1;
  v48 = &v31;
  v50 = *((_QWORD *)&v34 + 1);
  v51 = (unsigned __int16)v34;
  v53 = &v32;
  v45[1] = 2;
  v47 = 0;
  v49 = 2;
  v52 = 0;
  v54 = 4;
  v26 = EtwEventWriteTransfer(AiSvcEventHandle, AppIdServiceVerifyFileCall, 0, 0, 5, v45);
  if ( v26 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_ZZDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      v28,
      (unsigned int)&DestinationString,
      (__int64)&v34,
      (char)v32,
      v26);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v36[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v36[1]);
  if ( v37[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37[1]);
  EventActivityIdControl(2u, &ActivityId);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2));
  return TrustedPublisherName;
}

```

## disassembly

```asm
0x1800053c0  push    rbp
0x1800053c2  push    rbx
0x1800053c3  push    rsi
0x1800053c4  push    rdi
0x1800053c5  push    r12
0x1800053c7  push    r13
0x1800053c9  push    r14
0x1800053cb  push    r15
0x1800053cd  lea     rbp, [rsp-58h]
0x1800053d2  sub     rsp, 158h
0x1800053d9  mov     rax, cs:__security_cookie
0x1800053e0  xor     rax, rsp
0x1800053e3  mov     [rbp+90h+var_50], rax
0x1800053e7  mov     rax, [rbp+90h+arg_20]
0x1800053ee  xor     r14d, r14d
0x1800053f1  mov     r13, [rbp+90h+arg_38]
0x1800053f8  xorps   xmm0, xmm0
0x1800053fb  mov     [rbp+90h+var_D0], rax
0x1800053ff  mov     r12, rcx
0x180005402  mov     rax, [rbp+90h+arg_28]
0x180005409  mov     esi, 104h
0x18000540e  mov     [rbp+90h+var_C0], rax
0x180005412  mov     edi, r14d
0x180005415  mov     rax, [rbp+90h+arg_30]
0x18000541c  mov     [rsp+190h+var_148], rax
0x180005421  mov     [rbp+90h+var_C8], r9
0x180005425  mov     [rbp+90h+var_E0], r8
0x180005429  mov     [rbp+90h+var_D8], rdx
0x18000542d  mov     [rsp+190h+P], r14
0x180005432  mov     [rsp+190h+P+8], r14
0x180005437  mov     qword ptr [rsp+190h+DestinationString.Length], r14
0x18000543c  mov     [rsp+190h+DestinationString.Buffer], r14
0x180005441  mov     qword ptr [rsp+190h+var_130], r14
0x180005446  mov     qword ptr [rsp+190h+var_130+8], r14
0x18000544b  movups  xmmword ptr [rbp+90h+var_110], xmm0
0x18000544f  movups  xmmword ptr [rbp+90h+var_100], xmm0
0x180005453  movups  [rbp+90h+var_F0], xmm0
0x180005457  movups  xmmword ptr [rbp+90h+ActivityId.Data1], xmm0
0x18000545b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005462  lea     rax, WPP_GLOBAL_Control
0x180005469  cmp     rcx, rax
0x18000546c  jz      short loc_180005492
0x18000546e  test    dword ptr [rcx+1Ch], 400h
0x180005475  jz      short loc_180005492
0x180005477  mov     rcx, [rcx+10h]
0x18000547b  lea     edx, [r14+0Ah]
0x18000547f  lea     r9, aAisvcverifyfil_0; "AiSvcVerifyFile"
0x180005486  lea     r8, WPP_3e8fbce33354377c6a2bfec1a49552c9_Traceguids
0x18000548d  call    WPP_SF_s
0x180005492  mov     ebx, 8
0x180005497  lea     rdx, [rbp+90h+ActivityId]; ActivityId
0x18000549b  mov     r15b, r14b
0x18000549e  lea     ecx, [rbx-3]; ControlCode
0x1800054a1  call    cs:__imp_EventActivityIdControl
0x1800054a7  mov     rcx, gs:60h
0x1800054b0  lea     r14d, [rsi+1]
0x1800054b4  mov     r8, rdi; P
0x1800054b7  xor     edx, edx; Flags
0x1800054b9  mov     rcx, [rcx+30h]; HeapHandle
0x1800054bd  call    cs:__imp_RtlFreeHeap
0x1800054c3  mov     ecx, r14d
0x1800054c6  add     rcx, rcx
0x1800054c9  call    AiAlloc
0x1800054ce  mov     rdi, rax
0x1800054d1  test    rax, rax
0x1800054d4  jz      loc_180005652
0x1800054da  mov     r9d, ebx; dwFlags
0x1800054dd  mov     r8d, r14d; cchFilePath
0x1800054e0  mov     rdx, rax; lpszFilePath
0x1800054e3  mov     rcx, r12; hFile
0x1800054e6  call    cs:__imp_GetFinalPathNameByHandleW
0x1800054ec  mov     esi, eax
0x1800054ee  test    eax, eax
0x1800054f0  jnz     short loc_180005519
0x1800054f2  test    r15b, r15b
0x1800054f5  jnz     loc_180005583
0x1800054fb  or      ebx, 1
0x1800054fe  mov     r8d, r14d; cchFilePath
0x180005501  mov     r9d, ebx; dwFlags
0x180005504  mov     rdx, rdi; lpszFilePath
0x180005507  mov     rcx, r12; hFile
0x18000550a  mov     r15b, 1
0x18000550d  call    cs:__imp_GetFinalPathNameByHandleW
0x180005513  mov     esi, eax
0x180005515  test    eax, eax
0x180005517  jz      short loc_180005583
0x180005519  cmp     esi, r14d
0x18000551c  jnb     short loc_1800054A7
0x18000551e  mov     rdx, rdi; SourceString
0x180005521  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x180005526  call    cs:__imp_RtlInitUnicodeString
0x18000552c  lea     rax, [rsp+190h+P]
0x180005531  xor     r14d, r14d
0x180005534  mov     [rsp+190h+var_168], rax; DestinationString
0x180005539  mov     rdx, rdi; int
0x18000553c  lea     rax, [rbp+90h+var_110]
0x180005540  mov     [r13+0], r14
0x180005544  mov     rcx, r12; int
0x180005547  mov     [rsp+190h+var_170], rax; __int64
0x18000554c  call    AiGetTrustedPublisherName
0x180005551  mov     rcx, qword ptr [rbp+90h+var_F0+8]
0x180005555  mov     ebx, eax
0x180005557  mov     rax, [rsp+190h+var_148]
0x18000555c  mov     [rax], rcx
0x18000555f  test    ebx, ebx
0x180005561  jns     short loc_1800055C6
0x180005563  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000556a  test    rax, rax
0x18000556d  jz      loc_18000565A
0x180005573  lea     rdx, a24; "24"
0x18000557a  lea     rcx, qword_18000EDE0
0x180005581  jmp     short loc_1800055B9
0x180005583  call    cs:__imp_GetLastError
0x180005589  xor     r14d, r14d
0x18000558c  mov     ebx, eax
0x18000558e  test    eax, eax
0x180005590  jz      short loc_18000559B
0x180005592  movzx   ebx, ax
0x180005595  or      ebx, 80070000h
0x18000559b  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x1800055a2  test    rax, rax
0x1800055a5  jz      loc_18000565A
0x1800055ab  lea     rdx, a24_0; "24"
0x1800055b2  lea     rcx, qword_18000EE00
0x1800055b9  mov     r8d, ebx
0x1800055bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c1  jmp     loc_18000565A
0x1800055c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055cd  lea     r15, WPP_GLOBAL_Control
0x1800055d4  cmp     rcx, r15
0x1800055d7  jz      short loc_1800055F7
0x1800055d9  test    byte ptr [rcx+1Ch], 80h
0x1800055dd  jz      short loc_1800055F7
0x1800055df  mov     rcx, [rcx+10h]
0x1800055e3  lea     rax, [rsp+190h+P]
0x1800055e8  lea     r9, [rsp+190h+DestinationString]
0x1800055ed  mov     [rsp+190h+var_170], rax
0x1800055f2  call    WPP_SF_ZZ
0x1800055f7  mov     rax, [rbp+90h+var_110+8]
0x1800055fb  movaps  xmm0, xmmword ptr [rsp+190h+P]
0x180005600  mov     rcx, [rbp+90h+var_E0]
0x180005604  movdqa  [rsp+190h+var_130], xmm0
0x18000560a  psrldq  xmm0, 8
0x18000560f  movq    qword ptr [r13+0], xmm0
0x180005615  xorps   xmm0, xmm0
0x180005618  mov     [rcx], rax
0x18000561b  mov     eax, dword ptr [rbp+90h+var_110]
0x18000561e  mov     rcx, [rbp+90h+var_D8]
0x180005622  mov     [rsp+190h+P+8], r14
0x180005627  movups  xmmword ptr [rbp+90h+var_110], xmm0
0x18000562b  mov     [rcx], eax
0x18000562d  mov     rax, [rbp+90h+var_100+8]
0x180005631  mov     rcx, [rbp+90h+var_D0]
0x180005635  mov     [rcx], rax
0x180005638  mov     eax, dword ptr [rbp+90h+var_100]
0x18000563b  mov     rcx, [rbp+90h+var_C8]
0x18000563f  movups  xmmword ptr [rbp+90h+var_100], xmm0
0x180005643  mov     [rcx], eax
0x180005645  mov     rcx, [rbp+90h+var_C0]
0x180005649  mov     rax, qword ptr [rbp+90h+var_F0]
0x18000564d  mov     [rcx], rax
0x180005650  jmp     short loc_180005661
0x180005652  mov     ebx, 0C0000017h
0x180005657  xor     r14d, r14d
0x18000565a  lea     r15, WPP_GLOBAL_Control
0x180005661  movzx   eax, [rsp+190h+DestinationString.Length]
0x180005666  lea     rdx, AppIdServiceVerifyFileCall
0x18000566d  mov     rcx, cs:?AiSvcEventHandle@@3_KA; unsigned __int64 AiSvcEventHandle
0x180005674  mov     esi, 2
0x180005679  shr     ax, 1
0x18000567c  xor     r9d, r9d
0x18000567f  mov     [rsp+190h+var_150], ax
0x180005684  xor     r8d, r8d
0x180005687  lea     rax, [rsp+190h+var_150]
0x18000568c  mov     dword ptr [rsp+190h+var_148], ebx
0x180005690  mov     [rbp+90h+var_A0], rax
0x180005694  mov     rax, [rsp+190h+DestinationString.Buffer]
0x180005699  mov     [rbp+90h+var_90], rax
0x18000569d  movzx   eax, [rsp+190h+DestinationString.Length]
0x1800056a2  mov     [rbp+90h+var_88], eax
0x1800056a5  movzx   eax, word ptr [rsp+190h+var_130]
0x1800056aa  shr     ax, 1
0x1800056ad  mov     [rsp+190h+var_14C], ax
0x1800056b2  lea     rax, [rsp+190h+var_14C]
0x1800056b7  mov     [rbp+90h+var_80], rax
0x1800056bb  mov     rax, qword ptr [rsp+190h+var_130+8]
0x1800056c0  mov     [rbp+90h+var_70], rax
0x1800056c4  movzx   eax, word ptr [rsp+190h+var_130]
0x1800056c9  mov     [rbp+90h+var_68], eax
0x1800056cc  lea     rax, [rsp+190h+var_148]
0x1800056d1  mov     [rbp+90h+var_60], rax
0x1800056d5  lea     rax, [rbp+90h+var_A0]
0x1800056d9  mov     [rsp+190h+var_168], rax
0x1800056de  mov     dword ptr [rsp+190h+var_170], 5
0x1800056e6  mov     [rbp+90h+var_98], rsi
0x1800056ea  mov     [rbp+90h+var_84], r14d
0x1800056ee  mov     [rbp+90h+var_78], rsi
0x1800056f2  mov     [rbp+90h+var_64], r14d
0x1800056f6  mov     [rbp+90h+var_58], 4
0x1800056fe  call    cs:__imp_EtwEventWriteTransfer
0x180005704  test    eax, eax
0x180005706  jns     short loc_18000573E
0x180005708  mov     rcx, cs:WPP_GLOBAL_Control
0x18000570f  cmp     rcx, r15
0x180005712  jz      short loc_18000573E
0x180005714  test    byte ptr [rcx+1Ch], 4
0x180005718  jz      short loc_18000573E
0x18000571a  mov     rcx, [rcx+10h]
0x18000571e  lea     r9, [rsp+190h+DestinationString]
0x180005723  mov     [rsp+190h+var_160], eax
0x180005727  mov     eax, dword ptr [rsp+190h+var_148]
0x18000572b  mov     dword ptr [rsp+190h+var_168], eax
0x18000572f  lea     rax, [rsp+190h+var_130]
0x180005734  mov     [rsp+190h+var_170], rax
0x180005739  call    WPP_SF_ZZDD
0x18000573e  mov     rcx, gs:60h
0x180005747  xor     edx, edx; Flags
0x180005749  mov     r8, [rsp+190h+P+8]; P
0x18000574e  mov     rcx, [rcx+30h]; HeapHandle
0x180005752  call    cs:__imp_RtlFreeHeap
0x180005758  mov     rcx, gs:60h
0x180005761  mov     r8, rdi; P
0x180005764  xor     edx, edx; Flags
0x180005766  mov     rcx, [rcx+30h]; HeapHandle
0x18000576a  call    cs:__imp_RtlFreeHeap
0x180005770  mov     r8, [rbp+90h+var_110+8]; P
0x180005774  test    r8, r8
0x180005777  jz      short loc_18000578E
0x180005779  mov     rcx, gs:60h
0x180005782  xor     edx, edx; Flags
0x180005784  mov     rcx, [rcx+30h]; HeapHandle
0x180005788  call    cs:__imp_RtlFreeHeap
0x18000578e  mov     r8, [rbp+90h+var_100+8]; P
0x180005792  test    r8, r8
0x180005795  jz      short loc_1800057AC
0x180005797  mov     rcx, gs:60h
0x1800057a0  xor     edx, edx; Flags
0x1800057a2  mov     rcx, [rcx+30h]; HeapHandle
0x1800057a6  call    cs:__imp_RtlFreeHeap
0x1800057ac  lea     rdx, [rbp+90h+ActivityId]; ActivityId
0x1800057b0  mov     ecx, esi; ControlCode
0x1800057b2  call    cs:__imp_EventActivityIdControl
0x1800057b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057bf  cmp     rcx, r15
0x1800057c2  jz      short loc_1800057DA
0x1800057c4  test    dword ptr [rcx+1Ch], 400h
0x1800057cb  jz      short loc_1800057DA
0x1800057cd  mov     rcx, [rcx+10h]
0x1800057d1  mov     dword ptr [rsp+190h+var_170], ebx
0x1800057d5  call    WPP_SF_sD
0x1800057da  mov     eax, ebx
0x1800057dc  mov     rcx, [rbp+90h+var_50]
0x1800057e0  xor     rcx, rsp; StackCookie
0x1800057e3  call    __security_check_cookie
0x1800057e8  add     rsp, 158h
0x1800057ef  pop     r15
0x1800057f1  pop     r14
0x1800057f3  pop     r13
0x1800057f5  pop     r12
0x1800057f7  pop     rdi
0x1800057f8  pop     rsi
0x1800057f9  pop     rbx
0x1800057fa  pop     rbp
0x1800057fb  retn
```
