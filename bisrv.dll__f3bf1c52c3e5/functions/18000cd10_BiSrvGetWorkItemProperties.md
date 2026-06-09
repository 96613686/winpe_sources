# BiSrvGetWorkItemProperties

- ea: `0x18000cd10`
- end: `0x18000d505`
- name: `BiSrvGetWorkItemProperties`
- size: `2037`
- prototype: `__int64 __usercall@<rax>(char Args@<cl>, PSID Sid1@<rdx>, void *Source1@<r8>, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c7c0`

## callees

- `0x180005670`
- `0x18000cd10`
- `0x18000d50c`
- `0x18000d560`
- `0x18000d7c0`
- `0x18000da30`
- `0x1800121b0`
- `0x1800271a0`
- `0x18004df58`
- `0x18006a8d4`
- `0x18006d364`
- `0x180076b04`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000cf11`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d270`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000cf11`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d270`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000ce7b`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000ce7b`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000ced8`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000ced8`
- `ntdll!RtlLookupEntryHashTable` at `0x18000ce9e`
- `ntdll!RtlLookupEntryHashTable` at `0x18000ce9e`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000cffb`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000cffb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d133`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d133`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d187`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d1b5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d187`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d1b5`
- `ntdll!RtlWakeAddressAll` at `0x18000d43c`
- `ntdll!RtlWakeAddressAll` at `0x18000d43c`
- `ntdll!RtlEqualSid` at `0x18000cfbf`
- `ntdll!RtlEqualSid` at `0x18000cfbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d139`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d139`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d2c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d2c4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000cebd`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000cebd`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000cf84`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000cf84`

## pseudocode

```c
__int64 __fastcall BiSrvGetWorkItemProperties(
        char Args,
        PSID Sid1,
        unsigned __int8 *Source1,
        __int64 a4,
        int a5,
        _QWORD *a6,
        int *a7,
        _QWORD *a8,
        GUID *a9,
        _DWORD *a10,
        __int64 a11,
        __int64 a12)
{
  unsigned __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 i; // rax
  __int64 v18; // rbx
  _QWORD *v19; // r13
  void *v20; // r15
  void *v21; // r12
  int v22; // ebp
  LONG v23; // eax
  __int64 v24; // rcx
  char v25; // di
  __int64 v26; // rdi
  void *v27; // rdx
  __int64 v28; // r8
  int v29; // edi
  _QWORD *v30; // rcx
  int v31; // edi
  _QWORD *v32; // r8
  unsigned int v33; // r14d
  _DWORD *v34; // rdx
  int v35; // ecx
  void *v36; // rax
  GUID *v37; // rax
  GUID v38; // xmm0
  int v39; // edi
  __int64 v40; // r14
  DWORD CurrentThreadId; // eax
  int v42; // eax
  int v43; // edi
  int v44; // esi
  void *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rdx
  _QWORD *v51; // rsi
  int v52; // edx
  int v53; // r8d
  int v54; // [rsp+20h] [rbp-258h]
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp-238h] BYREF
  _QWORD *v56; // [rsp+48h] [rbp-230h]
  __int64 v57; // [rsp+50h] [rbp-228h]
  __int64 v58; // [rsp+58h] [rbp-220h]
  _QWORD *v59; // [rsp+60h] [rbp-218h]
  int *v60; // [rsp+68h] [rbp-210h]
  _QWORD *v61; // [rsp+70h] [rbp-208h]
  _DWORD *v62; // [rsp+78h] [rbp-200h]
  GUID *v63; // [rsp+80h] [rbp-1F8h]
  __int128 v64; // [rsp+88h] [rbp-1F0h] BYREF
  __int64 v65; // [rsp+98h] [rbp-1E0h]
  WCHAR packageFullName[128]; // [rsp+A0h] [rbp-1D8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+1A0h] [rbp-D8h] BYREF

  v59 = a6;
  v60 = a7;
  v61 = a8;
  v63 = a9;
  v62 = a10;
  v58 = a11;
  v57 = a12;
  memset_0(packageFullName, 0, 0x182u);
  v64 = 0;
  v65 = 0;
  v15 = Source1[15]
      + 39
      * (Source1[14]
       + 39
       * (Source1[13]
        + 39
        * (Source1[12]
         + 39
         * (Source1[11]
          + 39
          * (Source1[10]
           + 39
           * (Source1[9]
            + 39
            * (Source1[8]
             + 39
             * (Source1[7]
              + 39
              * (Source1[6]
               + 39
               * (Source1[5]
                + 39
                * (Source1[4]
                 + 39 * (Source1[3] + 39 * (Source1[2] + 39 * (Source1[1] + 39 * (*Source1 + 39 * qword_1800C4148)))))))))))))));
  RtlAcquireSRWLockShared(&qword_1800C4390);
  v16 = 1;
  if ( v15 )
    v16 = v15;
  for ( i = RtlLookupEntryHashTable(qword_1800C4388, v16, &v64); ; i = RtlGetNextEntryHashTable(qword_1800C4388, &v64) )
  {
    v18 = i;
    if ( !i )
    {
      RtlReleaseSRWLockShared(&qword_1800C4390);
      return 3221226021LL;
    }
    if ( RtlCompareMemory(Source1, (const void *)(i + 32), 0x10u) == 16 )
      break;
  }
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v56 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v18 + 28));
  RtlReleaseSRWLockShared(&qword_1800C4390);
  memset_0(packageFullName, 0, 0x182u);
  v22 = RtlStringCbPrintfExW((int)packageFullName, 256, 0, 0, 2048, (__int64)L"%s", Args);
  if ( v22 < 0 )
  {
    v51 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e10bfb2d162d3f503ddb9e0a62cc8063_Traceguids);
      v51 = WPP_GLOBAL_Control;
    }
    goto LABEL_77;
  }
  packageFamilyNameLength = 65;
  v23 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
  v25 = v23;
  if ( v23 )
  {
    memset_0(packageFamilyName, 0, 0x82u);
    v51 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v52, v53, (unsigned int)packageFullName, v25);
      v51 = WPP_GLOBAL_Control;
    }
    v22 = -1073741823;
    memset_0(packageFullName, 0, 0x182u);
LABEL_77:
    if ( (*((_BYTE *)v51 + 28) & 0x40) != 0 && *((_BYTE *)v51 + 25) >= 2u )
      WPP_SF_(v51[2], 43, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
    goto LABEL_36;
  }
  BipAcquireGlobalLock(v24);
  if ( *(int *)(v18 + 24) < 0 )
  {
    v22 = -1073741275;
    v30 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v50 = 44;
LABEL_57:
    WPP_SF_(v30[2], v50, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
    goto LABEL_32;
  }
  v26 = *(_QWORD *)(v18 + 72);
  if ( Sid1 )
  {
    v27 = *(void **)(v26 + 168);
    if ( !v27 || !RtlEqualSid(Sid1, v27) )
    {
      v30 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
        v30 = WPP_GLOBAL_Control;
      }
      v22 = -1073741823;
      goto LABEL_54;
    }
  }
  if ( v26 == -192
    || (LOBYTE(v54) = 1,
        v28 = v26 + 448,
        v29 = 0,
        (unsigned int)RtlCompareUnicodeStrings(packageFamilyName, 65, v28, 65, v54)) )
  {
    v22 = -1073741823;
    v29 = -1073741823;
    v30 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
      v30 = WPP_GLOBAL_Control;
LABEL_54:
      if ( (*((_BYTE *)v30 + 28) & 0x40) == 0 || *((_BYTE *)v30 + 25) < 2u )
        goto LABEL_32;
      v50 = 45;
      goto LABEL_57;
    }
  }
  else
  {
    v30 = WPP_GLOBAL_Control;
  }
  v22 = v29;
  if ( v29 < 0 )
    goto LABEL_54;
  if ( *(_WORD *)(v18 + 384) )
  {
    v46 = MIDL_user_allocate(*(unsigned __int16 *)(v18 + 384));
    v20 = v46;
    if ( !v46 )
    {
      v22 = -1073741670;
      goto LABEL_32;
    }
    memcpy_0(v46, *(const void **)(v18 + 392), *(unsigned __int16 *)(v18 + 384));
    v31 = *(unsigned __int16 *)(v18 + 384) >> 1;
  }
  else
  {
    v31 = 0;
  }
  if ( (*(_DWORD *)(v18 + 24) & 0x20000000) != 0 )
  {
    if ( !(unsigned __int8)BipUtilActTypeIsDebugSupported(*(unsigned int *)(v18 + 400)) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v48, v47, v49);
    v56 = MIDL_user_allocate(8u);
    v19 = v56;
    if ( !v56 )
    {
      v22 = -1073741670;
      goto LABEL_32;
    }
    *v56 = *(_QWORD *)(v18 + 576);
  }
  v32 = (_QWORD *)v58;
  v33 = 0;
  v34 = (_DWORD *)v57;
  if ( !v58 || !v57 || (v35 = *(_DWORD *)(v18 + 400), v35 != 2) && v35 || !*(_QWORD *)(v18 + 616) )
  {
LABEL_27:
    *v59 = v20;
    *v60 = v31;
    *v61 = v19;
    *v62 = *(_DWORD *)(*(_QWORD *)(v18 + 72) + 580LL);
    v37 = *(GUID **)(v18 + 72);
    if ( v37 )
      v38 = v37[2];
    else
      v38 = GUID_NULL;
    *v63 = v38;
    if ( v32 && v34 )
    {
      *v34 = v33;
      *v32 = v21;
    }
    goto LABEL_32;
  }
  v33 = *(_DWORD *)(v18 + 608);
  if ( !v33 )
  {
    v33 = 0;
    goto LABEL_27;
  }
  v36 = MIDL_user_allocate(v33);
  v21 = v36;
  if ( v36 )
  {
    memcpy_0(v36, *(const void **)(v18 + 616), v33);
    v34 = (_DWORD *)v57;
    v32 = (_QWORD *)v58;
    v19 = v56;
    goto LABEL_27;
  }
  v22 = -1073741670;
LABEL_32:
  v39 = 1 << dword_1800C3CF8;
  v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_DWORD *)(v40 + 4) >= (unsigned int)(1 << dword_1800C3CF8) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipGlobals);
  RtlAcquireSRWLockExclusive(BipGlobals);
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v40 + 4) |= v39;
  dword_1800C3CFC = CurrentThreadId;
  *(_DWORD *)(v40 + 8) |= v39;
  v42 = *(_DWORD *)(v40 + 8);
  if ( *((_QWORD *)&xmmword_1800C3D00 + 1) )
  {
    *(_QWORD *)&xmmword_1800C3D00 = 0;
    BipSyncReleaseLock(BipGlobals, 1);
    RtlWakeAddressAll(&xmmword_1800C3D00);
  }
  else
  {
    v43 = ~(1 << dword_1800C3CF8);
    dword_1800C3CFC = 0;
    *(_DWORD *)(v40 + 8) = v43 & v42;
    RtlReleaseSRWLockExclusive(BipGlobals);
    *(_DWORD *)(v40 + 4) &= v43;
  }
  v44 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  *(_DWORD *)(v40 + 8) &= v44;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  *(_DWORD *)(v40 + 4) &= v44;
LABEL_36:
  BipWorkItemDereference(v18);
  if ( v22 < 0 )
  {
    if ( v20 )
      CempHeapFree(v20);
    if ( v56 )
      CempHeapFree(v56);
    if ( v21 )
      CempHeapFree(v21);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000cd10  push    rbx
0x18000cd12  push    rbp
0x18000cd13  push    rsi
0x18000cd14  push    rdi
0x18000cd15  push    r14
0x18000cd17  sub     rsp, 250h
0x18000cd1e  mov     rax, cs:__security_cookie
0x18000cd25  xor     rax, rsp
0x18000cd28  mov     [rsp+278h+var_48], rax
0x18000cd30  mov     rax, [rsp+278h+arg_28]
0x18000cd38  mov     rdi, r8
0x18000cd3b  mov     [rsp+278h+var_218], rax
0x18000cd40  mov     r14, rdx
0x18000cd43  mov     rax, [rsp+278h+arg_30]
0x18000cd4b  mov     rbp, rcx
0x18000cd4e  mov     [rsp+278h+var_210], rax
0x18000cd53  lea     rcx, [rsp+278h+packageFullName]; void *
0x18000cd5b  mov     rax, [rsp+278h+arg_38]
0x18000cd63  xor     edx, edx; Val
0x18000cd65  mov     [rsp+278h+var_208], rax
0x18000cd6a  mov     r8d, 182h; Size
0x18000cd70  mov     rax, [rsp+278h+arg_40]
0x18000cd78  mov     [rsp+278h+var_1F8], rax
0x18000cd80  mov     rax, [rsp+278h+arg_48]
0x18000cd88  mov     [rsp+278h+var_200], rax
0x18000cd8d  mov     rax, [rsp+278h+arg_50]
0x18000cd95  mov     [rsp+278h+var_220], rax
0x18000cd9a  mov     rax, [rsp+278h+arg_58]
0x18000cda2  mov     [rsp+278h+var_228], rax
0x18000cda7  call    memset_0
0x18000cdac  imul    rcx, cs:qword_1800C4148, 27h ; '''
0x18000cdb4  xorps   xmm0, xmm0
0x18000cdb7  movups  [rsp+278h+var_1F0], xmm0
0x18000cdbf  xor     eax, eax
0x18000cdc1  mov     [rsp+278h+var_1E0], rax
0x18000cdc9  movzx   eax, byte ptr [rdi]
0x18000cdcc  add     rcx, rax
0x18000cdcf  movzx   eax, byte ptr [rdi+1]
0x18000cdd3  imul    rdx, rcx, 27h ; '''
0x18000cdd7  add     rdx, rax
0x18000cdda  movzx   eax, byte ptr [rdi+2]
0x18000cdde  imul    rdx, 27h ; '''
0x18000cde2  add     rdx, rax
0x18000cde5  movzx   eax, byte ptr [rdi+3]
0x18000cde9  imul    rdx, 27h ; '''
0x18000cded  add     rdx, rax
0x18000cdf0  movzx   eax, byte ptr [rdi+4]
0x18000cdf4  imul    rdx, 27h ; '''
0x18000cdf8  add     rdx, rax
0x18000cdfb  movzx   eax, byte ptr [rdi+5]
0x18000cdff  imul    rdx, 27h ; '''
0x18000ce03  add     rdx, rax
0x18000ce06  movzx   eax, byte ptr [rdi+6]
0x18000ce0a  imul    rdx, 27h ; '''
0x18000ce0e  add     rdx, rax
0x18000ce11  movzx   eax, byte ptr [rdi+7]
0x18000ce15  imul    rdx, 27h ; '''
0x18000ce19  add     rdx, rax
0x18000ce1c  movzx   eax, byte ptr [rdi+8]
0x18000ce20  imul    rdx, 27h ; '''
0x18000ce24  add     rdx, rax
0x18000ce27  movzx   eax, byte ptr [rdi+9]
0x18000ce2b  imul    rdx, 27h ; '''
0x18000ce2f  add     rdx, rax
0x18000ce32  movzx   eax, byte ptr [rdi+0Ah]
0x18000ce36  imul    rdx, 27h ; '''
0x18000ce3a  add     rdx, rax
0x18000ce3d  movzx   eax, byte ptr [rdi+0Bh]
0x18000ce41  imul    rdx, 27h ; '''
0x18000ce45  add     rdx, rax
0x18000ce48  movzx   eax, byte ptr [rdi+0Ch]
0x18000ce4c  imul    rdx, 27h ; '''
0x18000ce50  add     rdx, rax
0x18000ce53  movzx   eax, byte ptr [rdi+0Dh]
0x18000ce57  imul    rdx, 27h ; '''
0x18000ce5b  add     rdx, rax
0x18000ce5e  movzx   eax, byte ptr [rdi+0Eh]
0x18000ce62  imul    rcx, rdx, 27h ; '''
0x18000ce66  add     rcx, rax
0x18000ce69  movzx   eax, byte ptr [rdi+0Fh]
0x18000ce6d  imul    rbx, rcx, 27h ; '''
0x18000ce71  lea     rcx, qword_1800C4390
0x18000ce78  add     rbx, rax
0x18000ce7b  call    cs:__imp_RtlAcquireSRWLockShared
0x18000ce81  mov     rcx, cs:qword_1800C4388
0x18000ce88  lea     r8, [rsp+278h+var_1F0]
0x18000ce90  mov     esi, 1
0x18000ce95  test    rbx, rbx
0x18000ce98  mov     edx, esi
0x18000ce9a  cmovnz  rdx, rbx
0x18000ce9e  call    cs:__imp_RtlLookupEntryHashTable
0x18000cea4  mov     rbx, rax
0x18000cea7  test    rax, rax
0x18000ceaa  jz      loc_18000D269
0x18000ceb0  lea     rdx, [rax+20h]; Source2
0x18000ceb4  mov     r8d, 10h; Length
0x18000ceba  mov     rcx, rdi; Source1
0x18000cebd  call    cs:__imp_RtlCompareMemory
0x18000cec3  cmp     rax, 10h
0x18000cec7  jz      short loc_18000CEE0
0x18000cec9  mov     rcx, cs:qword_1800C4388
0x18000ced0  lea     rdx, [rsp+278h+var_1F0]
0x18000ced8  call    cs:__imp_RtlGetNextEntryHashTable
0x18000cede  jmp     short loc_18000CEA4
0x18000cee0  mov     [rsp+278h+arg_18], r12
0x18000cee8  mov     [rsp+278h+var_30], r13
0x18000cef0  xor     r13d, r13d
0x18000cef3  mov     [rsp+278h+var_38], r15
0x18000cefb  xor     r15d, r15d
0x18000cefe  xor     r12d, r12d
0x18000cf01  mov     [rsp+278h+var_230], r13
0x18000cf06  lock inc dword ptr [rbx+1Ch]
0x18000cf0a  lea     rcx, qword_1800C4390
0x18000cf11  call    cs:__imp_RtlReleaseSRWLockShared
0x18000cf17  xor     edx, edx; Val
0x18000cf19  lea     rcx, [rsp+278h+packageFullName]; void *
0x18000cf21  mov     r8d, 182h; Size
0x18000cf27  call    memset_0
0x18000cf2c  lea     rax, aS; "%s"
0x18000cf33  mov     qword ptr [rsp+278h+Args], rbp; Args
0x18000cf38  mov     [rsp+278h+var_250], rax; __int64
0x18000cf3d  lea     rcx, [rsp+278h+packageFullName]; int
0x18000cf45  xor     r9d, r9d; int
0x18000cf48  mov     [rsp+278h+var_258], 800h; int
0x18000cf50  xor     r8d, r8d; int
0x18000cf53  mov     edx, 100h; int
0x18000cf58  call    RtlStringCbPrintfExW
0x18000cf5d  mov     ebp, eax
0x18000cf5f  test    eax, eax
0x18000cf61  js      loc_18000D32F
0x18000cf67  lea     r8, [rsp+278h+packageFamilyName]; packageFamilyName
0x18000cf6f  mov     [rsp+278h+packageFamilyNameLength], 41h ; 'A'
0x18000cf77  lea     rdx, [rsp+278h+packageFamilyNameLength]; packageFamilyNameLength
0x18000cf7c  lea     rcx, [rsp+278h+packageFullName]; packageFullName
0x18000cf84  call    cs:__imp_PackageFamilyNameFromFullName
0x18000cf8a  mov     edi, eax
0x18000cf8c  test    eax, eax
0x18000cf8e  jnz     loc_18000D447
0x18000cf94  call    BipAcquireGlobalLock
0x18000cf99  cmp     [rbx+18h], r12d
0x18000cf9d  jl      loc_18000D36B
0x18000cfa3  mov     rdi, [rbx+48h]
0x18000cfa7  test    r14, r14
0x18000cfaa  jz      short loc_18000CFCD
0x18000cfac  mov     rdx, [rdi+0A8h]; Sid2
0x18000cfb3  test    rdx, rdx
0x18000cfb6  jz      loc_18000D320
0x18000cfbc  mov     rcx, r14; Sid1
0x18000cfbf  call    cs:__imp_RtlEqualSid
0x18000cfc5  test    al, al
0x18000cfc7  jz      loc_18000D320
0x18000cfcd  lea     r8, [rdi+0C0h]
0x18000cfd4  test    r8, r8
0x18000cfd7  jz      loc_18000D3B6
0x18000cfdd  mov     edx, 41h ; 'A'
0x18000cfe2  mov     byte ptr [rsp+278h+var_258], sil
0x18000cfe7  mov     r9d, edx
0x18000cfea  lea     rcx, [rsp+278h+packageFamilyName]
0x18000cff2  add     r8, 100h
0x18000cff9  xor     edi, edi
0x18000cffb  call    cs:__imp_RtlCompareUnicodeStrings
0x18000d001  test    eax, eax
0x18000d003  jnz     loc_18000D3B6
0x18000d009  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d010  mov     ebp, edi
0x18000d012  test    edi, edi
0x18000d014  js      loc_18000D2F2
0x18000d01a  movzx   eax, word ptr [rbx+180h]
0x18000d021  test    ax, ax
0x18000d024  jnz     loc_18000D207
0x18000d02a  xor     edi, edi
0x18000d02c  test    dword ptr [rbx+18h], 20000000h
0x18000d033  jnz     loc_18000D280
0x18000d039  mov     r8, [rsp+278h+var_220]
0x18000d03e  xor     r14d, r14d
0x18000d041  mov     rdx, [rsp+278h+var_228]
0x18000d046  test    r8, r8
0x18000d049  jz      short loc_18000D0AD
0x18000d04b  test    rdx, rdx
0x18000d04e  jz      short loc_18000D0AD
0x18000d050  mov     ecx, [rbx+190h]
0x18000d056  cmp     ecx, 2
0x18000d059  jnz     loc_18000D40D
0x18000d05f  cmp     [rbx+268h], r12
0x18000d066  jz      short loc_18000D0AD
0x18000d068  mov     r14d, [rbx+260h]
0x18000d06f  test    r14d, r14d
0x18000d072  jz      loc_18000D240
0x18000d078  mov     ecx, r14d; size
0x18000d07b  call    MIDL_user_allocate
0x18000d080  mov     r12, rax
0x18000d083  test    rax, rax
0x18000d086  jz      loc_18000D25F
0x18000d08c  mov     rdx, [rbx+268h]; Src
0x18000d093  mov     r8d, r14d; Size
0x18000d096  mov     rcx, rax; void *
0x18000d099  call    memcpy_0
0x18000d09e  mov     rdx, [rsp+278h+var_228]
0x18000d0a3  mov     r8, [rsp+278h+var_220]
0x18000d0a8  mov     r13, [rsp+278h+var_230]
0x18000d0ad  mov     rax, [rsp+278h+var_218]
0x18000d0b2  mov     [rax], r15
0x18000d0b5  mov     rax, [rsp+278h+var_210]
0x18000d0ba  mov     [rax], edi
0x18000d0bc  mov     rax, [rsp+278h+var_208]
0x18000d0c1  mov     [rax], r13
0x18000d0c4  mov     rax, [rbx+48h]
0x18000d0c8  mov     ecx, [rax+244h]
0x18000d0ce  mov     rax, [rsp+278h+var_200]
0x18000d0d3  mov     [rax], ecx
0x18000d0d5  mov     rax, [rbx+48h]
0x18000d0d9  test    rax, rax
0x18000d0dc  jz      loc_18000D248
0x18000d0e2  movups  xmm0, xmmword ptr [rax+20h]
0x18000d0e6  mov     rax, [rsp+278h+var_1F8]
0x18000d0ee  movups  xmmword ptr [rax], xmm0
0x18000d0f1  test    r8, r8
0x18000d0f4  jz      short loc_18000D0FF
0x18000d0f6  test    rdx, rdx
0x18000d0f9  jnz     loc_18000D254
0x18000d0ff  mov     ecx, cs:dword_1800C3CF8
0x18000d105  mov     edi, esi
0x18000d107  mov     rax, gs:58h
0x18000d110  shl     edi, cl
0x18000d112  mov     ecx, cs:_tls_index
0x18000d118  mov     r13d, 4
0x18000d11e  mov     r14, [rax+rcx*8]
0x18000d122  cmp     [r14+r13], edi
0x18000d126  jnb     loc_18000D2C4
0x18000d12c  lea     rcx, BipGlobals
0x18000d133  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000d139  call    cs:__imp_GetCurrentThreadId
0x18000d13f  or      [r14+r13], edi
0x18000d143  mov     edx, 8
0x18000d148  mov     cs:dword_1800C3CFC, eax
0x18000d14e  or      [rdx+r14], edi
0x18000d152  cmp     qword ptr cs:xmmword_1800C3D00+8, 0
0x18000d15a  mov     eax, [rdx+r14]
0x18000d15e  jnz     loc_18000D41A
0x18000d164  mov     ecx, cs:dword_1800C3CF8
0x18000d16a  mov     edi, esi
0x18000d16c  shl     edi, cl
0x18000d16e  lea     rcx, BipGlobals
0x18000d175  not     edi
0x18000d177  mov     cs:dword_1800C3CFC, 0
0x18000d181  and     eax, edi
0x18000d183  mov     [rdx+r14], eax
0x18000d187  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000d18d  and     [r14+r13], edi
0x18000d191  mov     ecx, cs:dword_1800C3CB0
0x18000d197  shl     esi, cl
0x18000d199  lea     rcx, BipGlobalLock
0x18000d1a0  mov     eax, 8
0x18000d1a5  not     esi
0x18000d1a7  mov     cs:dword_1800C3CB4, 0
0x18000d1b1  and     [rax+r14], esi
0x18000d1b5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000d1bb  and     [r14+r13], esi
0x18000d1bf  mov     rcx, rbx
0x18000d1c2  call    BipWorkItemDereference
0x18000d1c7  mov     r13, [rsp+278h+var_30]
0x18000d1cf  test    ebp, ebp
0x18000d1d1  js      loc_18000D4D3
0x18000d1d7  mov     r12, [rsp+278h+arg_18]
0x18000d1df  mov     eax, ebp
0x18000d1e1  mov     r15, [rsp+278h+var_38]
0x18000d1e9  mov     rcx, [rsp+278h+var_48]
0x18000d1f1  xor     rcx, rsp; StackCookie
0x18000d1f4  call    __security_check_cookie
0x18000d1f9  add     rsp, 250h
0x18000d200  pop     r14
0x18000d202  pop     rdi
0x18000d203  pop     rsi
0x18000d204  pop     rbp
0x18000d205  pop     rbx
0x18000d206  retn
0x18000d207  mov     rcx, rax; size
0x18000d20a  call    MIDL_user_allocate
0x18000d20f  mov     r15, rax
0x18000d212  test    rax, rax
0x18000d215  jz      loc_18000D3F9
0x18000d21b  movzx   r8d, word ptr [rbx+180h]; Size
0x18000d223  mov     rcx, rax; void *
0x18000d226  mov     rdx, [rbx+188h]; Src
0x18000d22d  call    memcpy_0
0x18000d232  movzx   edi, word ptr [rbx+180h]
0x18000d239  shr     edi, 1
0x18000d23b  jmp     loc_18000D02C
0x18000d240  mov     r14d, r12d
0x18000d243  jmp     loc_18000D0AD
0x18000d248  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000d24f  jmp     loc_18000D0E6
0x18000d254  mov     [rdx], r14d
0x18000d257  mov     [r8], r12
0x18000d25a  jmp     loc_18000D0FF
0x18000d25f  mov     ebp, 0C000009Ah
0x18000d264  jmp     loc_18000D0FF
0x18000d269  lea     rcx, qword_1800C4390
0x18000d270  call    cs:__imp_RtlReleaseSRWLockShared
0x18000d276  mov     eax, 0C0000225h
  ... truncated ...
```
