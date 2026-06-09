# BiSrvSignalEvent

- ea: `0x18000bb10`
- end: `0x18000c2b2`
- name: `BiSrvSignalEvent`
- size: `1954`
- prototype: `__int64 __usercall@<rax>(char Args@<cl>, PSID Sid1@<rdx>, void *Source1@<r8>, __int64, __int64, int, void *Buf1)`
- caller_count: `6`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800480b0`
- `0x180065324`
- `0x180069540`
- `0x18007eab0`
- `0x18008bc30`
- `0x180093750`

## callees

- `0x1800075f8`
- `0x180008560`
- `0x18000bb10`
- `0x18000c2c0`
- `0x18000d560`
- `0x18000d7c0`
- `0x18000da50`
- `0x18001027c`
- `0x180049844`
- `0x18004df58`
- `0x180076b04`
- `0x180078e24`
- `0x180094656`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000bd01`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000bf71`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000bd01`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000bf71`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000bc97`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000bc97`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000bcee`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000bcee`
- `ntdll!RtlLookupEntryHashTable` at `0x18000bcb7`
- `ntdll!RtlLookupEntryHashTable` at `0x18000bcb7`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000bd73`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000bd73`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000bdf3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000bdf3`
- `ntdll!RtlWaitOnAddress` at `0x18000bf43`
- `ntdll!RtlWaitOnAddress` at `0x18000bf43`
- `ntdll!RtlFreeHeap` at `0x18000c2a7`
- `ntdll!RtlFreeHeap` at `0x18000c2a7`
- `ntdll!RtlEqualSid` at `0x18000bd3a`
- `ntdll!RtlEqualSid` at `0x18000c0e2`
- `ntdll!RtlEqualSid` at `0x18000bd3a`
- `ntdll!RtlEqualSid` at `0x18000c0e2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000bcd6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000bcd6`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000beef`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000beef`

## pseudocode

```c
__int64 __fastcall BiSrvSignalEvent(
        __int64 Args,
        PSID Sid1,
        unsigned __int8 *Source1,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        void *Buf1)
{
  unsigned __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 i; // rax
  __int64 v15; // rbx
  WCHAR *v16; // rdi
  void *v17; // rdx
  int v18; // ebp
  _QWORD *v19; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v20; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v22; // esi
  __int64 v23; // rdi
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  LONG v27; // eax
  char v28; // di
  int v29; // ecx
  void *v30; // rdx
  _QWORD *v31; // rsi
  int v32; // edx
  int v33; // r8d
  int v34; // [rsp+20h] [rbp-238h]
  int v35; // [rsp+40h] [rbp-218h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+44h] [rbp-214h] BYREF
  __int64 v37; // [rsp+48h] [rbp-210h]
  __int64 v38; // [rsp+50h] [rbp-208h]
  __int64 v39; // [rsp+58h] [rbp-200h]
  __int128 v40; // [rsp+60h] [rbp-1F8h] BYREF
  __int64 v41; // [rsp+70h] [rbp-1E8h]
  WCHAR packageFullName[128]; // [rsp+80h] [rbp-1D8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+180h] [rbp-D8h] BYREF

  v38 = a5;
  v37 = a6;
  v39 = a4;
  memset_0(packageFullName, 0, 0x182u);
  while ( 1 )
  {
    v35 = dword_1800C4340;
    if ( (unsigned int)dword_1800C4340 > 1 )
      break;
    RtlWaitOnAddress(&dword_1800C4340, &v35, 4, 0);
  }
  if ( !a6 )
  {
    if ( !a7 )
      goto LABEL_6;
    goto LABEL_28;
  }
  if ( !a7 )
  {
LABEL_28:
    v25 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return (unsigned int)-1073741811;
    v26 = 70;
LABEL_31:
    WPP_SF_d(v25[2], v26, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids, a7);
    return (unsigned int)-1073741811;
  }
  if ( a7 > 0x100000 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return (unsigned int)-1073741811;
    v26 = 71;
    goto LABEL_31;
  }
LABEL_6:
  if ( Buf1 && !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    return (unsigned int)-1073741811;
  v40 = 0;
  v41 = 0;
  v12 = Source1[15]
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
  RtlAcquireSRWLockShared(&qword_1800C4370);
  v13 = 1;
  if ( v12 )
    v13 = v12;
  for ( i = RtlLookupEntryHashTable(qword_1800C4368, v13, &v40); ; i = RtlGetNextEntryHashTable(qword_1800C4368, &v40) )
  {
    v15 = i;
    if ( !i )
      break;
    if ( RtlCompareMemory(Source1, (const void *)(i + 32), 0x10u) == 16 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 28));
      RtlReleaseSRWLockShared(&qword_1800C4370);
      if ( a4 && (*(_BYTE *)(v15 + 24) & 1) == 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
        v18 = -1073741811;
        goto LABEL_25;
      }
      if ( Args )
      {
        memset_0(packageFullName, 0, 0x182u);
        v18 = RtlStringCbPrintfExW((int)packageFullName, 256, 0, 0, 2048, (__int64)L"%s", Args);
        if ( v18 < 0 )
        {
          v31 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e10bfb2d162d3f503ddb9e0a62cc8063_Traceguids);
            v31 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          packageFamilyNameLength = 65;
          v27 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
          v28 = v27;
          if ( !v27 )
          {
            v16 = packageFullName;
            goto LABEL_16;
          }
          memset_0(packageFamilyName, 0, 0x82u);
          v31 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, v33, (unsigned int)packageFullName, v28);
            v31 = WPP_GLOBAL_Control;
          }
          v18 = -1073741823;
          memset_0(packageFullName, 0, 0x182u);
        }
        if ( (*((_BYTE *)v31 + 28) & 0x40) != 0 && *((_BYTE *)v31 + 25) >= 2u )
          WPP_SF_(v31[2], 61, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
        goto LABEL_25;
      }
      v16 = 0;
LABEL_16:
      if ( !Sid1 || (v17 = *(void **)(v15 + 168)) != 0 && RtlEqualSid(Sid1, v17) )
      {
        v18 = 0;
        if ( !v16
          || v15 != -192
          && (LOBYTE(v34) = 1, !(unsigned int)RtlCompareUnicodeStrings(v16 + 128, 65, v15 + 448, 65, v34)) )
        {
          v19 = WPP_GLOBAL_Control;
          goto LABEL_23;
        }
        v18 = -1073741823;
        v19 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
          v19 = WPP_GLOBAL_Control;
          goto LABEL_88;
        }
LABEL_23:
        if ( v18 < 0 )
          goto LABEL_88;
LABEL_24:
        BipAcquireGlobalLock(v19);
        v18 = BipSignalEventWithLockHeld((PVOID)v15, a7, (__int64)Buf1);
        BipLockWatchdogContextDisarmWatchdog(v20);
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v22 = ~(1 << dword_1800C3CB0);
        dword_1800C3CB4 = 0;
        v23 = ThreadLocalStoragePointer[(unsigned int)tls_index];
        *(_DWORD *)(v23 + 8) &= v22;
        RtlReleaseSRWLockExclusive(&BipGlobalLock);
        *(_DWORD *)(v23 + 4) &= v22;
LABEL_25:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 28), 0xFFFFFFFF) == 1 )
        {
          v29 = *(_DWORD *)(v15 + 48);
          if ( v29 == 1 )
          {
            BipEventQueueDestroy((struct _BI_LOCK *)&qword_1800C4600);
          }
          else if ( v29 == 2 )
          {
            BipWorkItemCheckQueueDestroy((struct _BI_WORK_ITEM *)v15);
          }
          else
          {
            RtlFreeHeap(BipHeap, 0, (PVOID)v15);
          }
        }
        return (unsigned int)v18;
      }
      v19 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
        v19 = WPP_GLOBAL_Control;
      }
      v18 = -1073741823;
LABEL_88:
      if ( *(_QWORD *)(v15 + 184) )
      {
        if ( !(unsigned __int8)BipIsDeviceHoloLens(v19) )
          goto LABEL_56;
        if ( !Sid1 || (v30 = *(void **)(v15 + 184)) != 0 && RtlEqualSid(Sid1, v30) )
        {
          v18 = 0;
          if ( v16 && (v15 == -192 || !(unsigned __int8)BipPackageIdIsEquivalent(v16, v15 + 192)) )
          {
            v18 = -1073741823;
            v19 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
              goto LABEL_56;
            }
          }
          else
          {
LABEL_56:
            v19 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          v19 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
            v19 = WPP_GLOBAL_Control;
          }
          v18 = -1073741823;
        }
        if ( v18 >= 0 )
          goto LABEL_24;
      }
      if ( (*((_BYTE *)v19 + 28) & 0x40) != 0 && *((_BYTE *)v19 + 25) >= 2u )
        WPP_SF_(v19[2], 62, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
      goto LABEL_25;
    }
  }
  RtlReleaseSRWLockShared(&qword_1800C4370);
  v18 = -1073741275;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18000bb10  push    rbx
0x18000bb12  push    rbp
0x18000bb13  push    rdi
0x18000bb14  push    r12
0x18000bb16  push    r13
0x18000bb18  push    r15
0x18000bb1a  sub     rsp, 228h
0x18000bb21  mov     rax, cs:__security_cookie
0x18000bb28  xor     rax, rsp
0x18000bb2b  mov     [rsp+258h+var_48], rax
0x18000bb33  mov     rax, [rsp+258h+arg_20]
0x18000bb3b  mov     rdi, r8
0x18000bb3e  mov     rbx, [rsp+258h+arg_28]
0x18000bb46  mov     r13, rdx
0x18000bb49  mov     r12, [rsp+258h+Buf1]
0x18000bb51  mov     r15, rcx
0x18000bb54  xor     edx, edx; Val
0x18000bb56  mov     [rsp+258h+var_208], rax
0x18000bb5b  mov     r8d, 182h; Size
0x18000bb61  mov     [rsp+258h+var_210], rbx
0x18000bb66  lea     rcx, [rsp+258h+packageFullName]; void *
0x18000bb6e  mov     [rsp+258h+var_200], r9
0x18000bb73  mov     rbp, r9
0x18000bb76  call    memset_0
0x18000bb7b  mov     eax, cs:dword_1800C4340
0x18000bb81  mov     [rsp+258h+var_218], eax
0x18000bb85  cmp     eax, 1
0x18000bb88  jbe     loc_18000BF2E
0x18000bb8e  mov     [rsp+258h+var_38], r14
0x18000bb96  mov     r14d, [rsp+258h+arg_30]
0x18000bb9e  test    rbx, rbx
0x18000bba1  jz      loc_18000BE47
0x18000bba7  test    r14d, r14d
0x18000bbaa  jz      loc_18000BE50
0x18000bbb0  cmp     r14d, 100000h
0x18000bbb7  ja      loc_18000C0FC
0x18000bbbd  test    r12, r12
0x18000bbc0  jnz     loc_18000BF0C
0x18000bbc6  imul    rcx, cs:qword_1800C4148, 27h ; '''
0x18000bbce  xorps   xmm0, xmm0
0x18000bbd1  movups  [rsp+258h+var_1F8], xmm0
0x18000bbd6  xor     eax, eax
0x18000bbd8  mov     [rsp+258h+arg_18], rsi
0x18000bbe0  mov     [rsp+258h+var_1E8], rax
0x18000bbe5  movzx   eax, byte ptr [rdi]
0x18000bbe8  add     rcx, rax
0x18000bbeb  movzx   eax, byte ptr [rdi+1]
0x18000bbef  imul    rdx, rcx, 27h ; '''
0x18000bbf3  add     rdx, rax
0x18000bbf6  movzx   eax, byte ptr [rdi+2]
0x18000bbfa  imul    rdx, 27h ; '''
0x18000bbfe  add     rdx, rax
0x18000bc01  movzx   eax, byte ptr [rdi+3]
0x18000bc05  imul    rdx, 27h ; '''
0x18000bc09  add     rdx, rax
0x18000bc0c  movzx   eax, byte ptr [rdi+4]
0x18000bc10  imul    rdx, 27h ; '''
0x18000bc14  add     rdx, rax
0x18000bc17  movzx   eax, byte ptr [rdi+5]
0x18000bc1b  imul    rdx, 27h ; '''
0x18000bc1f  add     rdx, rax
0x18000bc22  movzx   eax, byte ptr [rdi+6]
0x18000bc26  imul    rdx, 27h ; '''
0x18000bc2a  add     rdx, rax
0x18000bc2d  movzx   eax, byte ptr [rdi+7]
0x18000bc31  imul    rdx, 27h ; '''
0x18000bc35  add     rdx, rax
0x18000bc38  movzx   eax, byte ptr [rdi+8]
0x18000bc3c  imul    rdx, 27h ; '''
0x18000bc40  add     rdx, rax
0x18000bc43  movzx   eax, byte ptr [rdi+9]
0x18000bc47  imul    rdx, 27h ; '''
0x18000bc4b  add     rdx, rax
0x18000bc4e  movzx   eax, byte ptr [rdi+0Ah]
0x18000bc52  imul    rdx, 27h ; '''
0x18000bc56  add     rdx, rax
0x18000bc59  movzx   eax, byte ptr [rdi+0Bh]
0x18000bc5d  imul    rdx, 27h ; '''
0x18000bc61  add     rdx, rax
0x18000bc64  movzx   eax, byte ptr [rdi+0Ch]
0x18000bc68  imul    rdx, 27h ; '''
0x18000bc6c  add     rdx, rax
0x18000bc6f  movzx   eax, byte ptr [rdi+0Dh]
0x18000bc73  imul    rdx, 27h ; '''
0x18000bc77  add     rdx, rax
0x18000bc7a  movzx   eax, byte ptr [rdi+0Eh]
0x18000bc7e  imul    rcx, rdx, 27h ; '''
0x18000bc82  add     rcx, rax
0x18000bc85  movzx   eax, byte ptr [rdi+0Fh]
0x18000bc89  imul    rbx, rcx, 27h ; '''
0x18000bc8d  lea     rcx, qword_1800C4370
0x18000bc94  add     rbx, rax
0x18000bc97  call    cs:__imp_RtlAcquireSRWLockShared
0x18000bc9d  mov     rcx, cs:qword_1800C4368
0x18000bca4  lea     r8, [rsp+258h+var_1F8]
0x18000bca9  test    rbx, rbx
0x18000bcac  mov     esi, 1
0x18000bcb1  mov     edx, esi
0x18000bcb3  cmovnz  rdx, rbx
0x18000bcb7  call    cs:__imp_RtlLookupEntryHashTable
0x18000bcbd  mov     rbx, rax
0x18000bcc0  test    rax, rax
0x18000bcc3  jz      loc_18000BF6A
0x18000bcc9  lea     rdx, [rax+20h]; Source2
0x18000bccd  mov     r8d, 10h; Length
0x18000bcd3  mov     rcx, rdi; Source1
0x18000bcd6  call    cs:__imp_RtlCompareMemory
0x18000bcdc  cmp     rax, 10h
0x18000bce0  jz      short loc_18000BCF6
0x18000bce2  mov     rcx, cs:qword_1800C4368
0x18000bce9  lea     rdx, [rsp+258h+var_1F8]
0x18000bcee  call    cs:__imp_RtlGetNextEntryHashTable
0x18000bcf4  jmp     short loc_18000BCBD
0x18000bcf6  lock inc dword ptr [rbx+1Ch]
0x18000bcfa  lea     rcx, qword_1800C4370
0x18000bd01  call    cs:__imp_RtlReleaseSRWLockShared
0x18000bd07  test    rbp, rbp
0x18000bd0a  jnz     loc_18000C071
0x18000bd10  test    r15, r15
0x18000bd13  jnz     loc_18000BE82
0x18000bd19  xor     edi, edi
0x18000bd1b  lea     r15, [rbx+0C0h]
0x18000bd22  test    r13, r13
0x18000bd25  jz      short loc_18000BD48
0x18000bd27  mov     rdx, [rbx+0A8h]; Sid2
0x18000bd2e  test    rdx, rdx
0x18000bd31  jz      loc_18000C009
0x18000bd37  mov     rcx, r13; Sid1
0x18000bd3a  call    cs:__imp_RtlEqualSid
0x18000bd40  test    al, al
0x18000bd42  jz      loc_18000C009
0x18000bd48  xor     ebp, ebp
0x18000bd4a  test    rdi, rdi
0x18000bd4d  jz      short loc_18000BD81
0x18000bd4f  test    r15, r15
0x18000bd52  jz      loc_18000C1E1
0x18000bd58  mov     edx, 41h ; 'A'
0x18000bd5d  mov     byte ptr [rsp+258h+var_238], sil
0x18000bd62  mov     r9d, edx
0x18000bd65  lea     r8, [r15+100h]
0x18000bd6c  lea     rcx, [rdi+100h]
0x18000bd73  call    cs:__imp_RtlCompareUnicodeStrings
0x18000bd79  test    eax, eax
0x18000bd7b  jnz     loc_18000C1E1
0x18000bd81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd88  test    ebp, ebp
0x18000bd8a  js      loc_18000C21D
0x18000bd90  call    BipAcquireGlobalLock
0x18000bd95  mov     r9, [rsp+258h+var_210]
0x18000bd9a  mov     rcx, rbx; P
0x18000bd9d  mov     r8, [rsp+258h+var_208]
0x18000bda2  mov     rdx, [rsp+258h+var_200]
0x18000bda7  mov     [rsp+258h+var_230], r12; __int64
0x18000bdac  mov     [rsp+258h+var_238], r14d; int
0x18000bdb1  call    BipSignalEventWithLockHeld
0x18000bdb6  mov     ebp, eax
0x18000bdb8  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18000bdbd  mov     ecx, cs:dword_1800C3CB0
0x18000bdc3  mov     rax, gs:58h
0x18000bdcc  shl     esi, cl
0x18000bdce  mov     ecx, cs:_tls_index
0x18000bdd4  not     esi
0x18000bdd6  mov     cs:dword_1800C3CB4, 0
0x18000bde0  mov     rdi, [rax+rcx*8]
0x18000bde4  lea     rcx, BipGlobalLock
0x18000bdeb  mov     eax, 8
0x18000bdf0  and     [rax+rdi], esi
0x18000bdf3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000bdf9  mov     eax, 4
0x18000bdfe  and     [rax+rdi], esi
0x18000be01  mov     eax, 0FFFFFFFFh
0x18000be06  lock xadd [rbx+1Ch], eax
0x18000be0b  cmp     eax, 1
0x18000be0e  jz      loc_18000BF4E
0x18000be14  mov     rsi, [rsp+258h+arg_18]
0x18000be1c  mov     r14, [rsp+258h+var_38]
0x18000be24  mov     eax, ebp
0x18000be26  mov     rcx, [rsp+258h+var_48]
0x18000be2e  xor     rcx, rsp; StackCookie
0x18000be31  call    __security_check_cookie
0x18000be36  add     rsp, 228h
0x18000be3d  pop     r15
0x18000be3f  pop     r13
0x18000be41  pop     r12
0x18000be43  pop     rdi
0x18000be44  pop     rbp
0x18000be45  pop     rbx
0x18000be46  retn
0x18000be47  test    r14d, r14d
0x18000be4a  jz      loc_18000BBBD
0x18000be50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be57  test    byte ptr [rcx+1Ch], 40h
0x18000be5b  jz      short loc_18000BE7B
0x18000be5d  cmp     byte ptr [rcx+19h], 2
0x18000be61  jb      short loc_18000BE7B
0x18000be63  mov     edx, 46h ; 'F'
0x18000be68  mov     rcx, [rcx+10h]
0x18000be6c  lea     r8, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids
0x18000be73  mov     r9d, r14d
0x18000be76  call    WPP_SF_d
0x18000be7b  mov     ebp, 0C000000Dh
0x18000be80  jmp     short loc_18000BE1C
0x18000be82  xor     edx, edx; Val
0x18000be84  lea     rcx, [rsp+258h+packageFullName]; void *
0x18000be8c  mov     r8d, 182h; Size
0x18000be92  call    memset_0
0x18000be97  lea     rax, aS; "%s"
0x18000be9e  mov     qword ptr [rsp+258h+Args], r15; Args
0x18000bea3  mov     [rsp+258h+var_230], rax; __int64
0x18000bea8  lea     rcx, [rsp+258h+packageFullName]; int
0x18000beb0  xor     r9d, r9d; int
0x18000beb3  mov     [rsp+258h+var_238], 800h; int
0x18000bebb  xor     r8d, r8d; int
0x18000bebe  mov     edx, 100h; int
0x18000bec3  call    RtlStringCbPrintfExW
0x18000bec8  mov     ebp, eax
0x18000beca  test    eax, eax
0x18000becc  js      loc_18000C121
0x18000bed2  lea     r8, [rsp+258h+packageFamilyName]; packageFamilyName
0x18000beda  mov     [rsp+258h+packageFamilyNameLength], 41h ; 'A'
0x18000bee2  lea     rdx, [rsp+258h+packageFamilyNameLength]; packageFamilyNameLength
0x18000bee7  lea     rcx, [rsp+258h+packageFullName]; packageFullName
0x18000beef  call    cs:__imp_PackageFamilyNameFromFullName
0x18000bef5  mov     edi, eax
0x18000bef7  test    eax, eax
0x18000bef9  jnz     loc_18000C15D
0x18000beff  lea     rdi, [rsp+258h+packageFullName]
0x18000bf07  jmp     loc_18000BD1B
0x18000bf0c  mov     r8d, 10h; Size
0x18000bf12  lea     rdx, GUID_NULL; Buf2
0x18000bf19  mov     rcx, r12; Buf1
0x18000bf1c  call    memcmp_0
0x18000bf21  test    eax, eax
0x18000bf23  jnz     loc_18000BBC6
0x18000bf29  jmp     loc_18000BE7B
0x18000bf2e  xor     r9d, r9d
0x18000bf31  lea     rdx, [rsp+258h+var_218]
0x18000bf36  mov     r8d, 4
0x18000bf3c  lea     rcx, dword_1800C4340
0x18000bf43  call    cs:__imp_RtlWaitOnAddress
0x18000bf49  jmp     loc_18000BB7B
0x18000bf4e  mov     ecx, [rbx+30h]
0x18000bf51  cmp     ecx, 1
0x18000bf54  jnz     short loc_18000BFB1
0x18000bf56  mov     rdx, rbx
0x18000bf59  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x18000bf60  call    BipEventQueueDestroy
0x18000bf65  jmp     loc_18000BE14
0x18000bf6a  lea     rcx, qword_1800C4370
0x18000bf71  call    cs:__imp_RtlReleaseSRWLockShared
0x18000bf77  mov     ebp, 0C0000225h
0x18000bf7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf83  test    byte ptr [rcx+1Ch], 40h
0x18000bf87  jz      loc_18000BE14
0x18000bf8d  cmp     byte ptr [rcx+19h], 2
0x18000bf91  jb      loc_18000BE14
0x18000bf97  mov     rcx, [rcx+10h]
0x18000bf9b  lea     r8, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids
0x18000bfa2  mov     edx, 3Bh ; ';'
0x18000bfa7  call    WPP_SF_
0x18000bfac  jmp     loc_18000BE14
0x18000bfb1  sub     ecx, 2
0x18000bfb4  jnz     loc_18000C298
0x18000bfba  mov     rcx, rbx; struct _BI_WORK_ITEM *
0x18000bfbd  call    BipWorkItemCheckQueueDestroy
0x18000bfc2  jmp     loc_18000BE14
0x18000bfc7  test    byte ptr [rsi+1Ch], 40h
0x18000bfcb  jz      loc_18000BE01
0x18000bfd1  cmp     byte ptr [rsi+19h], 2
0x18000bfd5  jb      loc_18000BE01
0x18000bfdb  mov     rcx, [rsi+10h]
0x18000bfdf  lea     r8, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids
0x18000bfe6  mov     edx, 3Dh ; '='
0x18000bfeb  call    WPP_SF_
0x18000bff0  jmp     loc_18000BE01
0x18000bff5  cmp     byte ptr [rcx+19h], 2
0x18000bff9  jnb     loc_18000C1C0
0x18000bfff  mov     ebp, 0C0000001h
0x18000c004  jmp     loc_18000C21D
0x18000c009  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c010  test    byte ptr [rcx+1Ch], 40h
0x18000c014  jz      short loc_18000BFFF
0x18000c016  jmp     short loc_18000BFF5
0x18000c018  test    r15, r15
0x18000c01b  jz      loc_18000C25E
0x18000c021  mov     rdx, r15
0x18000c024  mov     rcx, rdi
0x18000c027  call    BipPackageIdIsEquivalent
0x18000c02c  test    al, al
0x18000c02e  jz      loc_18000C25E
0x18000c034  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c03b  test    ebp, ebp
0x18000c03d  jns     loc_18000BD90
0x18000c043  test    byte ptr [rcx+1Ch], 40h
0x18000c047  jz      loc_18000BE01
0x18000c04d  cmp     byte ptr [rcx+19h], 2
0x18000c051  jb      loc_18000BE01
0x18000c057  mov     rcx, [rcx+10h]
0x18000c05b  lea     r8, WPP_7356033c0bb43066cc7d8f8866379e89_Traceguids
0x18000c062  mov     edx, 3Eh ; '>'
  ... truncated ...
```
