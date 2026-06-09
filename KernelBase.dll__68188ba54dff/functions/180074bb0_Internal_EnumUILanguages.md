# Internal_EnumUILanguages

- ea: `0x180074bb0`
- end: `0x1800754a4`
- name: `Internal_EnumUILanguages`
- size: `2292`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004437c`
- `0x180074b90`

## callees

- `0x180037714`
- `0x18003fd00`
- `0x180073fa0`
- `0x180074a80`
- `0x180074acc`
- `0x180074bb0`
- `0x1800754b0`
- `0x180075698`
- `0x180075710`
- `0x18012d119`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800750be`
- `ntdll!RtlInitUnicodeString` at `0x180075308`
- `ntdll!RtlInitUnicodeString` at `0x1800750be`
- `ntdll!RtlInitUnicodeString` at `0x180075308`
- `ntdll!RtlNtStatusToDosError` at `0x180075238`
- `ntdll!RtlNtStatusToDosError` at `0x180075458`
- `ntdll!RtlNtStatusToDosError` at `0x180075238`
- `ntdll!RtlNtStatusToDosError` at `0x180075458`
- `ntdll!RtlpLoadUserUIByPolicy` at `0x180074db7`
- `ntdll!RtlpLoadUserUIByPolicy` at `0x180074db7`
- `ntdll!RtlpLoadMachineUIByPolicy` at `0x180074d77`
- `ntdll!RtlpLoadMachineUIByPolicy` at `0x180074d77`
- `ntdll!RtlpGetLCIDFromLangInfoNode` at `0x180074f76`
- `ntdll!RtlpGetLCIDFromLangInfoNode` at `0x180074f76`
- `ntdll!qsort` at `0x180074c71`
- `ntdll!qsort` at `0x180074c71`
- `ntdll!RtlpCreateProcessRegistryInfo` at `0x18007500d`
- `ntdll!RtlpCreateProcessRegistryInfo` at `0x18007500d`
- `ntdll!RtlLCIDToCultureName` at `0x180074e55`
- `ntdll!RtlLCIDToCultureName` at `0x1800753f4`
- `ntdll!RtlLCIDToCultureName` at `0x180074e55`
- `ntdll!RtlLCIDToCultureName` at `0x1800753f4`
- `ntdll!RtlpGetNameFromLangInfoNode` at `0x180074f54`
- `ntdll!RtlpGetNameFromLangInfoNode` at `0x180074f54`
- `ntdll!NtQueryInstallUILanguage` at `0x180074e01`
- `ntdll!NtQueryInstallUILanguage` at `0x180074e01`
- `ntdll!RtlpMuiFreeLangRegistryInfo` at `0x18007506c`
- `ntdll!RtlpMuiFreeLangRegistryInfo` at `0x18007506c`
- `ntdll!RtlpInitializeLangRegistryInfo` at `0x180074d40`
- `ntdll!RtlpInitializeLangRegistryInfo` at `0x180074d40`
- `ntdll!RtlpIsQualifiedLanguage` at `0x180074f98`
- `ntdll!RtlpIsQualifiedLanguage` at `0x180074f98`
- `ntdll!RtlCultureNameToLCID` at `0x1800750cd`
- `ntdll!RtlCultureNameToLCID` at `0x1800750cd`
- `ntdll!RtlFreeHeap` at `0x180074caa`
- `ntdll!RtlFreeHeap` at `0x180074ccf`
- `ntdll!RtlFreeHeap` at `0x180074da0`
- `ntdll!RtlFreeHeap` at `0x180074de2`
- `ntdll!RtlFreeHeap` at `0x180075208`
- `ntdll!RtlFreeHeap` at `0x1800752aa`
- `ntdll!RtlFreeHeap` at `0x1800753b8`
- `ntdll!RtlFreeHeap` at `0x180075440`
- `ntdll!RtlFreeHeap` at `0x180074caa`
- `ntdll!RtlFreeHeap` at `0x180074ccf`
- `ntdll!RtlFreeHeap` at `0x180074da0`
- `ntdll!RtlFreeHeap` at `0x180074de2`
- `ntdll!RtlFreeHeap` at `0x180075208`
- `ntdll!RtlFreeHeap` at `0x1800752aa`
- `ntdll!RtlFreeHeap` at `0x1800753b8`
- `ntdll!RtlFreeHeap` at `0x180075440`
- `ntdll!RtlAllocateHeap` at `0x180074ea8`
- `ntdll!RtlAllocateHeap` at `0x180074fd0`
- `ntdll!RtlAllocateHeap` at `0x180074ea8`
- `ntdll!RtlAllocateHeap` at `0x180074fd0`

## pseudocode

```c
__int64 __fastcall Internal_EnumUILanguages(__int64 (__fastcall *a1)(PVOID, __int64), int a2, __int64 a3, int a4)
{
  unsigned int v4; // r15d
  int v5; // r14d
  int v9; // edi
  ULONG v10; // ecx
  unsigned int v12; // r12d
  _QWORD *v13; // r14
  unsigned int j; // edi
  void *v15; // r8
  unsigned int v16; // r12d
  int v17; // ecx
  unsigned int v18; // ebx
  NTSTATUS v19; // eax
  int v20; // eax
  LANGID SystemDefaultUILanguage; // cx
  int v22; // edi
  WCHAR *v23; // rcx
  bool v24; // zf
  PVOID Heap; // rsi
  unsigned int i; // r14d
  __int64 v27; // r12
  _WORD *v28; // r12
  __int64 v29; // r8
  PVOID v30; // rax
  WCHAR *v31; // r14
  int v32; // eax
  unsigned __int16 v33; // ax
  __int64 v34; // rdx
  unsigned int v35; // eax
  UINT CodePageFromLocale; // eax
  PVOID v37; // rdi
  int v38; // r14d
  PWSTR v39; // r14
  UINT v40; // eax
  WCHAR *v41; // rdx
  __int64 v42; // rdx
  PVOID v43; // rsi
  int v44; // r14d
  __int64 v45; // rdx
  WCHAR *Buffer; // rcx
  int v47; // eax
  UINT v48; // eax
  PVOID v49; // r14
  ULONG v50; // eax
  LANGID LanguageId; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v54; // [rsp+68h] [rbp-98h] BYREF
  PVOID v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+94h] [rbp-6Ch]
  __int128 v60; // [rsp+98h] [rbp-68h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-58h]
  WCHAR WideCharStr[264]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v63[176]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v64[176]; // [rsp+370h] [rbp+270h] BYREF

  v4 = 0;
  v58 = a4;
  v61 = a3;
  LanguageId = 0;
  v54 = 0;
  v5 = a4;
  v56 = 0;
  v53 = 0;
  DestinationString = 0;
  v60 = 0;
  if ( !a1 )
  {
    v10 = 87;
    goto LABEL_7;
  }
  if ( (a2 & 0xFFFFFF03) != 0
    || (v9 = a2 & 0xC, v9 == 12)
    || (a2 & 0x10) != 0 && ((a2 & 0x20) != 0 || (a2 & 0x40) != 0)
    || (a2 & 0x60) == 0x60 )
  {
    v10 = 1004;
LABEL_7:
    SetLastError_0(v10);
    return 0;
  }
  if ( !gpSysLocHashN )
    SetupSystemLocaleHashNode(0);
  v17 = a2 | 4;
  if ( v9 )
    v17 = a2;
  v18 = v17 | 0x20;
  if ( (v17 & 0x70) != 0 )
    v18 = v17;
  if ( (v18 & 0x80u) == 0 )
    v19 = RtlpCreateProcessRegistryInfo(&v53);
  else
    v19 = RtlpInitializeLangRegistryInfo(&v53);
  if ( v19 < 0 )
  {
    v10 = RtlNtStatusToDosError(v19);
    goto LABEL_7;
  }
  v16 = 1;
  v59 = 1;
  if ( (v18 & 0x40) != 0 )
  {
    P = 0;
    v20 = RtlpLoadMachineUIByPolicy(0, v53, &P);
    if ( P )
    {
      if ( !v20 )
        goto LABEL_75;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      P = 0;
    }
    if ( (unsigned int)RtlpLoadUserUIByPolicy(0, v53, &P) )
    {
LABEL_30:
      if ( P )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      if ( (_BYTE)v4 == 1 )
        goto LABEL_14;
      v4 = 0;
      goto LABEL_34;
    }
    if ( !P )
    {
LABEL_34:
      v18 |= 0x20u;
      goto LABEL_35;
    }
LABEL_75:
    LOBYTE(v4) = 1;
    v34 = 28LL * *(__int16 *)(*((_QWORD *)P + 3) + 4LL);
    v35 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v53 + 24) + 16LL) + v34 + 4);
    LanguageId = v35;
    if ( !(_WORD)v35 )
      goto LABEL_30;
    if ( (v18 & 4) != 0 )
    {
      if ( (_WORD)v35 == 5120 )
      {
        LOWORD(v35) = 4096;
        LanguageId = 4096;
      }
      if ( (unsigned int)NlsConvertIntegerToString((unsigned __int16)v35, 16, 4, (unsigned int)WideCharStr, 260) )
        goto LABEL_30;
      if ( !v5 )
      {
        v55 = 0;
        CodePageFromLocale = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
        if ( !CodePageFromLocale || !(unsigned int)NlsEnumUnicodeToAnsi(CodePageFromLocale, WideCharStr) )
          return v16;
        v37 = v55;
        v38 = a1(v55, a3);
        if ( v37 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
        if ( v38 != 1 )
          return v16;
        v5 = v58;
        goto LABEL_30;
      }
      Buffer = WideCharStr;
    }
    else
    {
      if ( (_WORD)v35 == 4096 )
      {
        v45 = *(__int16 *)(*(_QWORD *)(*(_QWORD *)(v53 + 24) + 16LL) + v34 + 6);
        if ( (__int16)v45 <= 0 )
          goto LABEL_30;
        RtlInitUnicodeString(
          &DestinationString,
          (PCWSTR)(*(_QWORD *)(*(_QWORD *)(v53 + 32) + 24LL)
                 + 2LL * *(__int16 *)(*(_QWORD *)(*(_QWORD *)(v53 + 32) + 16LL) + 2 * v45)));
      }
      else
      {
        DestinationString.Buffer = (PWSTR)v63;
        DestinationString.MaximumLength = 170;
        if ( !(unsigned __int8)RtlLCIDToCultureName(v35, &DestinationString) )
          goto LABEL_30;
      }
      if ( !v5 )
      {
        v47 = NlsDispatchAnsiEnumProc(*(unsigned int *)gpSysLocHashN, a1, v18, DestinationString.Buffer, 0, 0, 0, a3, 4);
LABEL_103:
        if ( v47 != 1 )
          return v16;
        goto LABEL_30;
      }
      Buffer = DestinationString.Buffer;
    }
    v47 = a1(Buffer, a3);
    goto LABEL_103;
  }
LABEL_35:
  if ( (NtQueryInstallUILanguage(&LanguageId) & 0xC0000000) == 0xC0000000 )
  {
    SystemDefaultUILanguage = GetSystemDefaultUILanguage();
    LanguageId = SystemDefaultUILanguage;
  }
  else
  {
    SystemDefaultUILanguage = LanguageId;
  }
  if ( ((SystemDefaultUILanguage - 4096) & 0xFBFF) != 0 )
  {
    v22 = v18 & 4;
    if ( (v18 & 4) != 0 )
    {
      if ( !(unsigned int)NlsConvertIntegerToString(SystemDefaultUILanguage, 16, 4, (unsigned int)WideCharStr, 260) )
      {
        if ( v5 )
        {
          v23 = WideCharStr;
          goto LABEL_42;
        }
        v55 = 0;
        v40 = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
        if ( !v40 )
          return v16;
        v41 = WideCharStr;
LABEL_91:
        if ( !(unsigned int)NlsEnumUnicodeToAnsi(v40, v41) )
          return v16;
        v42 = a3;
        v43 = v55;
        v44 = a1(v55, v42);
        if ( v43 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v43);
        v24 = v44 == 1;
        goto LABEL_43;
      }
    }
    else
    {
      DestinationString.Buffer = (PWSTR)v63;
      DestinationString.MaximumLength = 170;
      if ( (unsigned __int8)RtlLCIDToCultureName(SystemDefaultUILanguage, &DestinationString) )
      {
        if ( v5 )
        {
          v23 = DestinationString.Buffer;
LABEL_42:
          v24 = (unsigned int)a1(v23, a3) == 1;
LABEL_43:
          if ( !v24 )
            return v16;
          goto LABEL_44;
        }
        v39 = DestinationString.Buffer;
        v55 = 0;
        v40 = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
        if ( !v40 )
          return v16;
        v41 = v39;
        goto LABEL_91;
      }
    }
  }
  else
  {
    v22 = v18 & 4;
  }
  WideCharStr[0] = 0;
LABEL_44:
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8LL * *(unsigned __int16 *)(*(_QWORD *)(v53 + 24) + 6LL));
  if ( !Heap )
  {
    v50 = RtlNtStatusToDosError(-1073741801);
    SetLastError_0(v50);
    v16 = 0;
    goto LABEL_14;
  }
  for ( i = 0; ; ++i )
  {
    v27 = *(_QWORD *)(v53 + 24);
    if ( i >= *(unsigned __int16 *)(v27 + 6) )
    {
      qsort(Heap, v4, 8u, QsortStringcompareFunc);
      v12 = 0;
      if ( !v4 )
        goto LABEL_9;
      while ( 1 )
      {
        v31 = (WCHAR *)*((_QWORD *)Heap + v12);
        if ( v22 )
        {
          RtlInitUnicodeString(&DestinationString, *((PCWSTR *)Heap + v12));
          if ( !(unsigned __int8)RtlCultureNameToLCID(&DestinationString, &v56) )
            goto LABEL_67;
          v33 = v56;
          if ( v56 == 5120 )
          {
            v33 = 4096;
            v56 = 4096;
          }
          if ( (unsigned int)NlsConvertIntegerToString(v33, 16, 4, (unsigned int)WideCharStr, 260) )
            goto LABEL_67;
          v31 = WideCharStr;
        }
        if ( v58 )
        {
          v32 = a1(v31, v61);
        }
        else
        {
          v55 = 0;
          v48 = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
          if ( !v48 || !(unsigned int)NlsEnumUnicodeToAnsi(v48, v31) )
          {
LABEL_68:
            v13 = Heap;
            j = 0;
            goto LABEL_10;
          }
          v49 = v55;
          v32 = a1(v55, v61);
          LODWORD(P) = v32;
          if ( v49 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49);
            v32 = (int)P;
          }
        }
        if ( v32 != 1 )
          goto LABEL_9;
LABEL_67:
        if ( ++v12 >= v4 )
          goto LABEL_68;
      }
    }
    memset_0(v64, 0, 0xAAu);
    v28 = (_WORD *)(28LL * i + *(_QWORD *)(v27 + 16));
    LODWORD(P) = v18 & 0x10;
    *((_QWORD *)&v60 + 1) = v64;
    WORD1(v60) = 170;
    if ( (((_DWORD)P != 0 ? 34848 : 2080) & (unsigned __int16)*v28) != 0
      && (*v28 & 0x1000) == 0
      && (RtlpGetNameFromLangInfoNode(v53, v28, &v60) & 0xC0000000) != 0xC0000000
      && (RtlpGetLCIDFromLangInfoNode(v53, v28, &v54) & 0xC0000000) != 0xC0000000 )
    {
      LOBYTE(v29) = (_DWORD)P == 0;
      if ( (RtlpIsQualifiedLanguage(v53, v28, v29) & 0xC0000000) != 0xC0000000 && LanguageId != v54 )
        break;
    }
LABEL_55:
    ;
  }
  v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)v60 + 2LL);
  *((_QWORD *)Heap + v4) = v30;
  if ( v30 )
  {
    if ( (int)RtlStringCbCopyW(v30, (unsigned __int16)v60 + 2LL, *((_QWORD *)&v60 + 1)) < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)Heap + v4));
      *((_QWORD *)Heap + v4) = 0;
    }
    else
    {
      ++v4;
    }
    goto LABEL_55;
  }
  SetLastError_0(8u);
  v59 = 0;
LABEL_9:
  v13 = Heap;
  for ( j = 0; j < v4; ++j )
  {
LABEL_10:
    v15 = (void *)v13[j];
    if ( v15 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      v13[j] = 0;
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  v16 = v59;
LABEL_14:
  if ( (v18 & 0x80u) != 0 && v53 )
    RtlpMuiFreeLangRegistryInfo();
  return v16;
}

```

## disassembly

```asm
0x180074bb0  mov     [rsp-8+arg_18], rbx
0x180074bb5  push    rbp
0x180074bb6  push    rsi
0x180074bb7  push    rdi
0x180074bb8  push    r12
0x180074bba  push    r13
0x180074bbc  push    r14
0x180074bbe  push    r15
0x180074bc0  lea     rbp, [rsp-330h]
0x180074bc8  sub     rsp, 430h
0x180074bcf  mov     rax, cs:__security_cookie
0x180074bd6  xor     rax, rsp
0x180074bd9  mov     [rbp+360h+var_40], rax
0x180074be0  xor     r15d, r15d
0x180074be3  mov     [rbp+360h+var_3D0], r9d
0x180074be7  mov     [rbp+360h+var_3B8], r8
0x180074beb  xorps   xmm0, xmm0
0x180074bee  mov     [rsp+460h+LanguageId], r15w
0x180074bf4  xorps   xmm1, xmm1
0x180074bf7  mov     [rsp+460h+var_3F8], r15w
0x180074bfd  mov     r14d, r9d
0x180074c00  mov     [rsp+460h+var_3E8], r15d
0x180074c05  mov     rsi, r8
0x180074c08  mov     [rsp+460h+var_400], r15
0x180074c0d  mov     ebx, edx
0x180074c0f  mov     r13, rcx
0x180074c12  movups  xmmword ptr [rbp+360h+DestinationString.Length], xmm0
0x180074c16  movups  [rbp+360h+var_3C8], xmm1
0x180074c1a  test    rcx, rcx
0x180074c1d  jz      loc_1800753C7
0x180074c23  test    edx, 0FFFFFF03h
0x180074c29  jnz     short loc_180074C4D
0x180074c2b  lea     eax, [r15+0Ch]
0x180074c2f  mov     edi, edx
0x180074c31  and     edi, eax
0x180074c33  cmp     edi, eax
0x180074c35  jz      short loc_180074C4D
0x180074c37  test    bl, 10h
0x180074c3a  jnz     loc_180075334
0x180074c40  mov     eax, ebx
0x180074c42  and     eax, 60h
0x180074c45  cmp     al, 60h ; '`'
0x180074c47  jnz     loc_180074D0E
0x180074c4d  mov     ecx, 3ECh; dwErrCode
0x180074c52  call    SetLastError_0
0x180074c57  xor     eax, eax
0x180074c59  jmp     loc_180074CE4
0x180074c5e  mov     edx, r15d; NumOfElements
0x180074c61  lea     r9, QsortStringcompareFunc; CompareFunction
0x180074c68  mov     r8d, 8; SizeOfElements
0x180074c6e  mov     rcx, rsi; Base
0x180074c71  call    cs:__imp_qsort
0x180074c77  xor     ecx, ecx
0x180074c79  mov     r12d, ecx
0x180074c7c  test    r15d, r15d
0x180074c7f  jnz     loc_180075077
0x180074c85  mov     r14, rsi
0x180074c88  mov     edi, ecx
0x180074c8a  test    r15d, r15d
0x180074c8d  jz      short loc_180074CBD
0x180074c8f  mov     r12d, edi
0x180074c92  mov     r8, [r14+r12*8]; P
0x180074c96  test    r8, r8
0x180074c99  jz      short loc_180074CB6
0x180074c9b  mov     rcx, gs:60h
0x180074ca4  xor     edx, edx; Flags
0x180074ca6  mov     rcx, [rcx+30h]; HeapHandle
0x180074caa  call    cs:__imp_RtlFreeHeap
0x180074cb0  xor     ecx, ecx
0x180074cb2  mov     [r14+r12*8], rcx
0x180074cb6  inc     edi
0x180074cb8  cmp     edi, r15d
0x180074cbb  jb      short loc_180074C8F
0x180074cbd  mov     rcx, gs:60h
0x180074cc6  mov     r8, rsi; P
0x180074cc9  xor     edx, edx; Flags
0x180074ccb  mov     rcx, [rcx+30h]; HeapHandle
0x180074ccf  call    cs:__imp_RtlFreeHeap
0x180074cd5  mov     r12d, [rbp+360h+var_3CC]
0x180074cd9  test    bl, bl
0x180074cdb  js      loc_18007505E
0x180074ce1  mov     eax, r12d
0x180074ce4  mov     rcx, [rbp+360h+var_40]
0x180074ceb  xor     rcx, rsp; StackCookie
0x180074cee  call    __security_check_cookie
0x180074cf3  mov     rbx, [rsp+460h+arg_18]
0x180074cfb  add     rsp, 430h
0x180074d02  pop     r15
0x180074d04  pop     r14
0x180074d06  pop     r13
0x180074d08  pop     r12
0x180074d0a  pop     rdi
0x180074d0b  pop     rsi
0x180074d0c  pop     rbp
0x180074d0d  retn
0x180074d0e  cmp     cs:gpSysLocHashN, r15
0x180074d15  jnz     short loc_180074D1E
0x180074d17  xor     ecx, ecx
0x180074d19  call    SetupSystemLocaleHashNode
0x180074d1e  mov     ecx, ebx
0x180074d20  or      ecx, 4
0x180074d23  test    edi, edi
0x180074d25  cmovnz  ecx, ebx
0x180074d28  mov     ebx, ecx
0x180074d2a  or      ebx, 20h
0x180074d2d  test    cl, 70h
0x180074d30  cmovnz  ebx, ecx
0x180074d33  lea     rcx, [rsp+460h+var_400]
0x180074d38  test    bl, bl
0x180074d3a  jns     loc_18007500D
0x180074d40  call    cs:__imp_RtlpInitializeLangRegistryInfo
0x180074d46  test    eax, eax
0x180074d48  js      loc_180075236
0x180074d4e  mov     r12d, 1
0x180074d54  mov     edi, 1000h
0x180074d59  mov     [rbp+360h+var_3CC], r12d
0x180074d5d  test    bl, 40h
0x180074d60  jz      loc_180074DFC
0x180074d66  mov     rdx, [rsp+460h+var_400]
0x180074d6b  lea     r8, [rsp+460h+P]
0x180074d70  xor     ecx, ecx
0x180074d72  mov     [rsp+460h+P], r15
0x180074d77  call    cs:__imp_RtlpLoadMachineUIByPolicy
0x180074d7d  cmp     [rsp+460h+P], r15
0x180074d82  jz      short loc_180074DAB
0x180074d84  test    eax, eax
0x180074d86  jz      loc_180075124
0x180074d8c  mov     rcx, gs:60h
0x180074d95  xor     edx, edx; Flags
0x180074d97  mov     r8, [rsp+460h+P]; P
0x180074d9c  mov     rcx, [rcx+30h]; HeapHandle
0x180074da0  call    cs:__imp_RtlFreeHeap
0x180074da6  mov     [rsp+460h+P], r15
0x180074dab  mov     rdx, [rsp+460h+var_400]
0x180074db0  lea     r8, [rsp+460h+P]
0x180074db5  xor     ecx, ecx
0x180074db7  call    cs:__imp_RtlpLoadUserUIByPolicy
0x180074dbd  xor     edi, edi
0x180074dbf  test    eax, eax
0x180074dc1  jz      loc_180075119
0x180074dc7  cmp     [rsp+460h+P], rdi
0x180074dcc  jz      short loc_180074DE8
0x180074dce  mov     rcx, gs:60h
0x180074dd7  xor     edx, edx; Flags
0x180074dd9  mov     r8, [rsp+460h+P]; P
0x180074dde  mov     rcx, [rcx+30h]; HeapHandle
0x180074de2  call    cs:__imp_RtlFreeHeap
0x180074de8  cmp     r15b, r12b
0x180074deb  jz      loc_180074CD9
0x180074df1  xor     r15d, r15d
0x180074df4  or      ebx, 20h
0x180074df7  mov     edi, 1000h
0x180074dfc  lea     rcx, [rsp+460h+LanguageId]; LanguageId
0x180074e01  call    cs:__imp_NtQueryInstallUILanguage
0x180074e07  mov     ecx, 0C0000000h
0x180074e0c  and     eax, ecx
0x180074e0e  cmp     eax, ecx
0x180074e10  jz      loc_18007504C
0x180074e16  movzx   ecx, [rsp+460h+LanguageId]
0x180074e1b  movzx   eax, cx
0x180074e1e  mov     edx, 0FBFFh
0x180074e23  sub     ax, di
0x180074e26  mov     edi, ebx
0x180074e28  test    dx, ax
0x180074e2b  jz      loc_1800752B8
0x180074e31  movzx   ecx, cx
0x180074e34  and     edi, 4
0x180074e37  jnz     loc_180075018
0x180074e3d  lea     rax, [rbp+360h+var_1A0]
0x180074e44  mov     [rbp+360h+DestinationString.Buffer], rax
0x180074e48  lea     rdx, [rbp+360h+DestinationString]
0x180074e4c  mov     eax, 0AAh
0x180074e51  mov     [rbp+360h+DestinationString.MaximumLength], ax
0x180074e55  call    cs:__imp_RtlLCIDToCultureName
0x180074e5b  test    al, al
0x180074e5d  jz      loc_1800752BB
0x180074e63  test    r14d, r14d
0x180074e66  jz      loc_180075245
0x180074e6c  mov     rcx, [rbp+360h+DestinationString.Buffer]
0x180074e70  mov     rdx, rsi
0x180074e73  mov     rax, r13
0x180074e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e7b  cmp     eax, r12d
0x180074e7e  jnz     loc_180074CE1
0x180074e84  mov     rax, [rsp+460h+var_400]
0x180074e89  mov     edx, 8; Flags
0x180074e8e  mov     rcx, [rax+18h]
0x180074e92  movzx   r8d, word ptr [rcx+6]
0x180074e97  mov     rcx, gs:60h
0x180074ea0  shl     r8, 3; Size
0x180074ea4  mov     rcx, [rcx+30h]; HeapHandle
0x180074ea8  call    cs:__imp_RtlAllocateHeap
0x180074eae  mov     rsi, rax
0x180074eb1  test    rax, rax
0x180074eb4  jz      loc_180075453
0x180074eba  xor     r11d, r11d
0x180074ebd  mov     r14d, r11d
0x180074ec0  mov     rax, [rsp+460h+var_400]
0x180074ec5  mov     r12, [rax+18h]
0x180074ec9  movzx   eax, word ptr [r12+6]
0x180074ecf  cmp     r14d, eax
0x180074ed2  jnb     loc_180074C5E
0x180074ed8  xor     edx, edx; Val
0x180074eda  lea     rcx, [rbp+360h+var_F0]; void *
0x180074ee1  mov     r8d, 0AAh; Size
0x180074ee7  call    memset_0
0x180074eec  mov     r12, [r12+10h]
0x180074ef1  mov     eax, r14d
0x180074ef4  imul    rcx, rax, 1Ch
0x180074ef8  mov     eax, ebx
0x180074efa  and     eax, 10h
0x180074efd  add     r12, rcx
0x180074f00  mov     dword ptr [rsp+460h+P], eax
0x180074f04  lea     rcx, [rbp+360h+var_F0]
0x180074f0b  neg     eax
0x180074f0d  mov     qword ptr [rbp+360h+var_3C8+8], rcx
0x180074f11  mov     eax, 0Ch
0x180074f16  mov     ecx, 0AAh
0x180074f1b  sbb     edx, edx
0x180074f1d  mov     word ptr [rbp+360h+var_3C8+2], cx
0x180074f21  movzx   r8d, word ptr [r12]
0x180074f26  and     edx, 8000h
0x180074f2c  add     edx, 820h
0x180074f32  test    r8d, edx
0x180074f35  setnz   dl
0x180074f38  bt      r8w, ax
0x180074f3d  setnb   al
0x180074f40  test    al, dl
0x180074f42  jz      loc_180075005
0x180074f48  mov     rcx, [rsp+460h+var_400]
0x180074f4d  lea     r8, [rbp+360h+var_3C8]
0x180074f51  mov     rdx, r12
0x180074f54  call    cs:__imp_RtlpGetNameFromLangInfoNode
0x180074f5a  mov     ecx, 0C0000000h
0x180074f5f  and     eax, ecx
0x180074f61  cmp     eax, ecx
0x180074f63  jz      loc_180075005
0x180074f69  mov     rcx, [rsp+460h+var_400]
0x180074f6e  lea     r8, [rsp+460h+var_3F8]
0x180074f73  mov     rdx, r12
0x180074f76  call    cs:__imp_RtlpGetLCIDFromLangInfoNode
0x180074f7c  mov     ecx, 0C0000000h
0x180074f81  and     eax, ecx
0x180074f83  cmp     eax, ecx
0x180074f85  jz      short loc_180075005
0x180074f87  cmp     dword ptr [rsp+460h+P], 0
0x180074f8c  mov     rdx, r12
0x180074f8f  mov     rcx, [rsp+460h+var_400]
0x180074f94  setz    r8b
0x180074f98  call    cs:__imp_RtlpIsQualifiedLanguage
0x180074f9e  mov     ecx, 0C0000000h
0x180074fa3  and     eax, ecx
0x180074fa5  cmp     eax, ecx
0x180074fa7  jz      short loc_180075005
0x180074fa9  movzx   eax, [rsp+460h+var_3F8]
0x180074fae  cmp     [rsp+460h+LanguageId], ax
0x180074fb3  jz      short loc_180075005
0x180074fb5  mov     rcx, gs:60h
0x180074fbe  mov     edx, 8; Flags
0x180074fc3  movzx   r8d, word ptr [rbp+360h+var_3C8]
0x180074fc8  add     r8, 2; Size
0x180074fcc  mov     rcx, [rcx+30h]; HeapHandle
0x180074fd0  call    cs:__imp_RtlAllocateHeap
0x180074fd6  mov     r12d, r15d
0x180074fd9  mov     [rsi+r12*8], rax
0x180074fdd  test    rax, rax
0x180074fe0  jz      loc_180075222
0x180074fe6  movzx   edx, word ptr [rbp+360h+var_3C8]
0x180074fea  mov     rcx, rax
0x180074fed  mov     r8, qword ptr [rbp+360h+var_3C8+8]
0x180074ff1  add     rdx, 2
0x180074ff5  call    RtlStringCbCopyW
0x180074ffa  test    eax, eax
0x180074ffc  js      loc_18007542D
0x180075002  inc     r15d
0x180075005  inc     r14d
0x180075008  jmp     loc_180074EC0
0x18007500d  call    cs:__imp_RtlpCreateProcessRegistryInfo
0x180075013  jmp     loc_180074D46
0x180075018  mov     edx, 10h
0x18007501d  mov     dword ptr [rsp+460h+var_440], 104h
0x180075025  lea     r9, [rbp+360h+WideCharStr]
0x180075029  lea     r8d, [rdx-0Ch]
0x18007502d  call    NlsConvertIntegerToString
0x180075032  test    eax, eax
0x180075034  jnz     loc_1800752BB
0x18007503a  test    r14d, r14d
0x18007503d  jz      loc_180075407
0x180075043  lea     rcx, [rbp+360h+WideCharStr]
0x180075047  jmp     loc_180074E70
0x18007504c  call    GetSystemDefaultUILanguage
0x180075051  movzx   ecx, ax
0x180075054  mov     [rsp+460h+LanguageId], ax
0x180075059  jmp     loc_180074E1B
0x18007505e  mov     rcx, [rsp+460h+var_400]
0x180075063  test    rcx, rcx
0x180075066  jz      loc_180074CE1
0x18007506c  call    cs:__imp_RtlpMuiFreeLangRegistryInfo
0x180075072  jmp     loc_180074CE1
0x180075077  mov     eax, r12d
  ... truncated ...
```
