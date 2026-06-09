# IkeInsertToCredCache

- ea: `0x18008028c`
- end: `0x180080733`
- name: `IkeInsertToCredCache`
- size: `1191`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f9e4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x18001afe0`
- `0x180021404`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004d60c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`
- `0x18007c99c`
- `0x18007d168`
- `0x18007dde4`
- `0x18008028c`
- `0x180080d3c`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800805e5`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800805e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800806f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800806f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080329`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080329`

## string_xrefs

- `0x1800803db`: `Credentials not present in cache, adding`
- `0x1800802d3`: `IkeInsertToCredCache`
- `0x1800806fa`: `IkeInsertToCredCache`
- `0x180080706`: `IkeInsertToCredCache`
- `0x1800806a0`: `Credentials already present in cache, not adding`
- `0x180080552`: `Num entries in cache exceed maximum, removing entry`

## pseudocode

```c
__int64 __fastcall IkeInsertToCredCache(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r15
  __int64 CredCacheEntry; // r12
  __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r14
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  HANDLE *p_OwningThread; // rax
  LPCRITICAL_SECTION *OwningThread; // rcx
  unsigned int SpinCount; // esi
  __int64 v31; // rdi
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  int v40; // edx
  int v41; // r8d
  int v42; // r9d
  HANDLE *v43; // rax
  LPCRITICAL_SECTION *LockSemaphore; // rbx
  HANDLE *v45; // rcx
  __int64 v46; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  int TlsMmLuid; // eax
  __int64 v53; // rcx
  __int64 v54; // rax
  int v55; // r8d
  int v56; // r9d
  __int64 v58; // [rsp+28h] [rbp-71h]
  __int64 v59; // [rsp+30h] [rbp-69h] BYREF
  __int64 v60; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v61[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v62[32]; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v63; // [rsp+70h] [rbp-29h]
  __int64 v64; // [rsp+78h] [rbp-21h]
  _BYTE v65[16]; // [rsp+80h] [rbp-19h] BYREF
  const char *v66; // [rsp+90h] [rbp-9h]
  __int64 v67; // [rsp+98h] [rbp-1h]
  __int64 *v68; // [rsp+A0h] [rbp+7h]
  __int64 v69; // [rsp+A8h] [rbp+Fh]

  v60 = 0;
  v61[0] = 0;
  v59 = 0;
  TraceLogHelper("IkeInsertToCredCache", 1);
  v6 = *(_QWORD *)(*(_QWORD *)(a3 + 104) + 56LL);
  CredCacheEntry = IkeCreateCredCacheEntry(a1, *(unsigned int *)(a2 + 72), v6, a3, &v60);
  if ( !CredCacheEntry )
  {
    v8 = v60;
    ++*(_DWORD *)(v60 + 48);
    *(_QWORD *)(a3 + 112) = v8;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3488));
    CredCacheEntry = IkeGetCredCacheEntry(a1, *(unsigned int *)(a2 + 72), v6, v61);
    if ( !CredCacheEntry )
    {
      v13 = v61[0];
      if ( v61[0] )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v46 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          TlsPeerAddr = IkeGetTlsPeerAddr(v10);
          TlsMmLuid = IkeGetTlsMmLuid(v49, v48, v50, v51);
          WPP_SF_iS(v46, 81, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
        }
        if ( (unsigned int)dword_180173278 > 4 )
        {
          v59 = IkeGetTlsMmLuid(v10, v9, v11, v12);
          v63 = &v59;
          v64 = 8;
          v54 = IkeGetTlsPeerAddr(v53);
          tlgCreate1Sz_wchar_t(v65, v54);
          v67 = 49;
          v66 = "Credentials already present in cache, not adding";
          tlgWriteTransfer_EtwEventWriteTransfer(
            (unsigned int)&dword_180173278,
            (unsigned int)&byte_180154C97,
            v55,
            v56,
            5,
            (__int64)v62);
        }
        IkeLogCredCacheEntry(v8);
        _InterlockedDecrement((volatile signed __int32 *)(v13 + 48));
        goto LABEL_31;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v15 = IkeGetTlsPeerAddr(v10);
        v20 = IkeGetTlsMmLuid(v17, v16, v18, v19);
        WPP_SF_iS(v14, 79, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v20, v15);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v61[0] = IkeGetTlsMmLuid(v10, v9, v11, v12);
        v63 = v61;
        v64 = 8;
        v22 = IkeGetTlsPeerAddr(v21);
        tlgCreate1Sz_wchar_t(v65, v22);
        v67 = 41;
        v66 = "Credentials not present in cache, adding";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)&byte_180154D2F,
          v23,
          v24,
          5,
          (__int64)v62);
      }
      IkeLogCredCacheEntry(v8);
      CredCacheEntry = IkeComputeCredCacheEntrySignature(
                         *(unsigned int *)(v8 + 40),
                         *(unsigned int *)(v8 + 44),
                         *(_QWORD *)(v8 + 64),
                         &v59);
      if ( !CredCacheEntry )
      {
        *(_QWORD *)(v8 + 32) = v59;
        CredCacheEntry = WfpHashtableInsert(&gIkeExtGlobals[88].SpinCount, v8 + 16);
        if ( !CredCacheEntry )
        {
          WfpRestructureHashtable(&gIkeExtGlobals[88].SpinCount);
          p_OwningThread = &gIkeExtGlobals[88].OwningThread;
          OwningThread = (LPCRITICAL_SECTION *)gIkeExtGlobals[88].OwningThread;
          if ( OwningThread[1] != (LPCRITICAL_SECTION)&gIkeExtGlobals[88].OwningThread )
            goto LABEL_23;
          *(_QWORD *)v8 = OwningThread;
          *(_QWORD *)(v8 + 8) = p_OwningThread;
          OwningThread[1] = (LPCRITICAL_SECTION)v8;
          *p_OwningThread = (HANDLE)v8;
          ++LODWORD(gIkeExtGlobals[89].SpinCount);
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 48));
          SpinCount = gIkeExtGlobals[89].SpinCount;
          if ( SpinCount > 0xC8 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v31 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v32 = IkeGetTlsPeerAddr(OwningThread);
              v37 = IkeGetTlsMmLuid(v34, v33, v35, v36);
              LODWORD(v58) = SpinCount;
              WPP_SF_iSL(v31, 80, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v37, v32, v58);
            }
            if ( (unsigned int)dword_180173278 > 4 )
            {
              v59 = IkeGetTlsMmLuid(OwningThread, v25, v26, v27);
              v63 = &v59;
              v64 = 8;
              v39 = IkeGetTlsPeerAddr(v38);
              tlgCreate1Sz_wchar_t(v65, v39);
              v66 = "Num entries in cache exceed maximum, removing entry";
              v67 = 52;
              v40 = gIkeExtGlobals[89].SpinCount;
              v68 = &v60;
              LODWORD(v60) = v40;
              v69 = 4;
              tlgWriteTransfer_EtwEventWriteTransfer(
                (unsigned int)&dword_180173278,
                (unsigned int)byte_180154CD5,
                v41,
                v42,
                6,
                (__int64)v62);
            }
            v43 = &gIkeExtGlobals[88].OwningThread;
            LockSemaphore = (LPCRITICAL_SECTION *)gIkeExtGlobals[88].LockSemaphore;
            if ( *LockSemaphore == (LPCRITICAL_SECTION)&gIkeExtGlobals[88].OwningThread )
            {
              v45 = (HANDLE *)LockSemaphore[1];
              if ( *v45 == LockSemaphore )
              {
                gIkeExtGlobals[88].LockSemaphore = v45;
                *v45 = v43;
                IkeLogCredCacheEntry(LockSemaphore);
                RtlRemoveEntryHashTable(&gIkeExtGlobals[88].SpinCount, LockSemaphore + 2, 0);
                WfpRestructureHashtable(&gIkeExtGlobals[88].SpinCount);
                --LODWORD(gIkeExtGlobals[89].SpinCount);
                IkeDerefCacheEntry(LockSemaphore);
                goto LABEL_31;
              }
            }
LABEL_23:
            __fastfail(3u);
          }
        }
      }
    }
LABEL_31:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3488));
  }
  TraceLogHelper("IkeInsertToCredCache", 0);
  return IkeReturnError(CredCacheEntry, "IkeInsertToCredCache");
}

```

## disassembly

```asm
0x18008028c  push    rbp
0x18008028e  push    rbx
0x18008028f  push    rsi
0x180080290  push    rdi
0x180080291  push    r12
0x180080293  push    r14
0x180080295  push    r15
0x180080297  lea     rbp, [rsp-27h]
0x18008029c  sub     rsp, 0C0h
0x1800802a3  mov     rax, cs:__security_cookie
0x1800802aa  xor     rax, rsp
0x1800802ad  mov     [rbp+57h+var_40], rax
0x1800802b1  mov     r14, rdx
0x1800802b4  mov     [rbp+57h+var_B8], 0
0x1800802bc  mov     edi, ecx
0x1800802be  mov     [rbp+57h+var_B0], 0
0x1800802c6  mov     edx, 1
0x1800802cb  mov     [rbp+57h+var_C0], 0
0x1800802d3  lea     rcx, aIkeinserttocre; "IkeInsertToCredCache"
0x1800802da  mov     rbx, r8
0x1800802dd  call    TraceLogHelper
0x1800802e2  mov     rax, [rbx+68h]
0x1800802e6  mov     r9, rbx
0x1800802e9  mov     edx, [r14+48h]
0x1800802ed  mov     ecx, edi
0x1800802ef  mov     r15, [rax+38h]
0x1800802f3  lea     rax, [rbp+57h+var_B8]
0x1800802f7  mov     r8, r15
0x1800802fa  mov     [rsp+0F0h+var_D0], rax
0x1800802ff  call    IkeCreateCredCacheEntry
0x180080304  mov     r12, rax
0x180080307  test    rax, rax
0x18008030a  jnz     loc_1800806F8
0x180080310  mov     rsi, [rbp+57h+var_B8]
0x180080314  inc     dword ptr [rsi+30h]
0x180080317  mov     [rbx+70h], rsi
0x18008031b  mov     rcx, cs:gIkeExtGlobals
0x180080322  add     rcx, 0DA0h; lpCriticalSection
0x180080329  call    cs:__imp_EnterCriticalSection
0x18008032f  mov     edx, [r14+48h]
0x180080333  lea     r9, [rbp+57h+var_B0]
0x180080337  mov     r8, r15
0x18008033a  mov     ecx, edi
0x18008033c  call    IkeGetCredCacheEntry
0x180080341  mov     r12, rax
0x180080344  test    rax, rax
0x180080347  jnz     loc_1800806E4
0x18008034d  mov     r14, [rbp+57h+var_B0]
0x180080351  test    r14, r14
0x180080354  jnz     loc_18008061F
0x18008035a  mov     rdi, cs:WPP_GLOBAL_Control
0x180080361  lea     r15, WPP_GLOBAL_Control
0x180080368  cmp     rdi, r15
0x18008036b  jz      short loc_1800803A6
0x18008036d  cmp     byte ptr [rdi+19h], 4
0x180080371  jb      short loc_1800803A6
0x180080373  test    byte ptr [rdi+1Ch], 10h
0x180080377  jz      short loc_1800803A6
0x180080379  mov     rdi, [rdi+10h]
0x18008037d  call    IkeGetTlsPeerAddr
0x180080382  mov     rbx, rax
0x180080385  call    IkeGetTlsMmLuid
0x18008038a  mov     r9, rax
0x18008038d  mov     [rsp+0F0h+var_D0], rbx
0x180080392  lea     edx, [r12+4Fh]
0x180080397  mov     rcx, rdi
0x18008039a  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800803a1  call    WPP_SF_iS
0x1800803a6  mov     eax, cs:dword_180173278
0x1800803ac  cmp     eax, 4
0x1800803af  jbe     short loc_180080412
0x1800803b1  call    IkeGetTlsMmLuid
0x1800803b6  mov     [rbp+57h+var_B0], rax
0x1800803ba  lea     rax, [rbp+57h+var_B0]
0x1800803be  mov     [rbp+57h+var_80], rax
0x1800803c2  mov     [rbp+57h+var_78], 8
0x1800803ca  call    IkeGetTlsPeerAddr
0x1800803cf  mov     rdx, rax
0x1800803d2  lea     rcx, [rbp+57h+var_70]
0x1800803d6  call    _tlgCreate1Sz_wchar_t
0x1800803db  lea     rcx, aCredentialsNot; "Credentials not present in cache, addin"...
0x1800803e2  mov     [rbp+57h+var_58], 29h ; ')'
0x1800803ea  lea     rax, [rbp+57h+var_A0]
0x1800803ee  mov     [rbp+57h+var_60], rcx
0x1800803f2  mov     [rsp+0F0h+var_C8], rax
0x1800803f7  lea     rcx, dword_180173278
0x1800803fe  lea     rdx, byte_180154D2F
0x180080405  mov     dword ptr [rsp+0F0h+var_D0], 5
0x18008040d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180080412  mov     rcx, rsi
0x180080415  call    IkeLogCredCacheEntry
0x18008041a  mov     r8, [rsi+40h]
0x18008041e  lea     r9, [rbp+57h+var_C0]
0x180080422  mov     edx, [rsi+2Ch]
0x180080425  mov     ecx, [rsi+28h]
0x180080428  call    IkeComputeCredCacheEntrySignature
0x18008042d  mov     r12, rax
0x180080430  test    rax, rax
0x180080433  jnz     loc_1800806E4
0x180080439  mov     rax, [rbp+57h+var_C0]
0x18008043d  lea     rdx, [rsi+10h]
0x180080441  mov     [rsi+20h], rax
0x180080445  mov     rcx, cs:gIkeExtGlobals
0x18008044c  add     rcx, 0DE0h
0x180080453  call    WfpHashtableInsert
0x180080458  mov     r12, rax
0x18008045b  test    rax, rax
0x18008045e  jnz     loc_1800806E4
0x180080464  mov     rcx, cs:gIkeExtGlobals
0x18008046b  add     rcx, 0DE0h
0x180080472  call    WfpRestructureHashtable
0x180080477  mov     rax, cs:gIkeExtGlobals
0x18008047e  add     rax, 0DD0h
0x180080484  mov     rcx, [rax]
0x180080487  cmp     [rcx+8], rax
0x18008048b  jnz     loc_180080618
0x180080491  mov     [rsi], rcx
0x180080494  mov     [rsi+8], rax
0x180080498  mov     [rcx+8], rsi
0x18008049c  mov     [rax], rsi
0x18008049f  mov     rax, cs:gIkeExtGlobals
0x1800804a6  inc     dword ptr [rax+0E08h]
0x1800804ac  lock inc dword ptr [rsi+30h]
0x1800804b0  mov     rax, cs:gIkeExtGlobals
0x1800804b7  mov     esi, [rax+0E08h]
0x1800804bd  cmp     esi, 0C8h
0x1800804c3  jbe     loc_1800806E4
0x1800804c9  mov     rdi, cs:WPP_GLOBAL_Control
0x1800804d0  cmp     rdi, r15
0x1800804d3  jz      short loc_180080512
0x1800804d5  cmp     byte ptr [rdi+19h], 4
0x1800804d9  jb      short loc_180080512
0x1800804db  test    byte ptr [rdi+1Ch], 10h
0x1800804df  jz      short loc_180080512
0x1800804e1  mov     rdi, [rdi+10h]
0x1800804e5  call    IkeGetTlsPeerAddr
0x1800804ea  mov     rbx, rax
0x1800804ed  call    IkeGetTlsMmLuid
0x1800804f2  mov     r9, rax
0x1800804f5  mov     dword ptr [rsp+0F0h+var_C8], esi
0x1800804f9  lea     edx, [r12+50h]
0x1800804fe  mov     [rsp+0F0h+var_D0], rbx
0x180080503  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18008050a  mov     rcx, rdi
0x18008050d  call    WPP_SF_iSL
0x180080512  mov     eax, cs:dword_180173278
0x180080518  cmp     eax, 4
0x18008051b  jbe     loc_1800805A2
0x180080521  call    IkeGetTlsMmLuid
0x180080526  mov     [rbp+57h+var_C0], rax
0x18008052a  lea     rax, [rbp+57h+var_C0]
0x18008052e  mov     [rbp+57h+var_80], rax
0x180080532  mov     [rbp+57h+var_78], 8
0x18008053a  call    IkeGetTlsPeerAddr
0x18008053f  mov     rdx, rax
0x180080542  lea     rcx, [rbp+57h+var_70]
0x180080546  call    _tlgCreate1Sz_wchar_t
0x18008054b  mov     rax, cs:gIkeExtGlobals
0x180080552  lea     rcx, aNumEntriesInCa; "Num entries in cache exceed maximum, re"...
0x180080559  mov     [rbp+57h+var_60], rcx
0x18008055d  lea     rcx, dword_180173278
0x180080564  mov     [rbp+57h+var_58], 34h ; '4'
0x18008056c  mov     edx, [rax+0E08h]
0x180080572  lea     rax, [rbp+57h+var_B8]
0x180080576  mov     [rbp+57h+var_50], rax
0x18008057a  lea     rax, [rbp+57h+var_A0]
0x18008057e  mov     dword ptr [rbp+57h+var_B8], edx
0x180080581  lea     rdx, byte_180154CD5
0x180080588  mov     [rsp+0F0h+var_C8], rax
0x18008058d  mov     dword ptr [rsp+0F0h+var_D0], 6
0x180080595  mov     [rbp+57h+var_48], 4
0x18008059d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800805a2  mov     rax, cs:gIkeExtGlobals
0x1800805a9  add     rax, 0DD0h
0x1800805af  mov     rbx, [rax+8]
0x1800805b3  cmp     [rbx], rax
0x1800805b6  jnz     short loc_180080618
0x1800805b8  mov     rcx, [rbx+8]
0x1800805bc  cmp     [rcx], rbx
0x1800805bf  jnz     short loc_180080618
0x1800805c1  mov     [rax+8], rcx
0x1800805c5  mov     [rcx], rax
0x1800805c8  mov     rcx, rbx
0x1800805cb  call    IkeLogCredCacheEntry
0x1800805d0  mov     rcx, cs:gIkeExtGlobals
0x1800805d7  lea     rdx, [rbx+10h]
0x1800805db  add     rcx, 0DE0h
0x1800805e2  xor     r8d, r8d
0x1800805e5  call    cs:__imp_RtlRemoveEntryHashTable
0x1800805eb  mov     rcx, cs:gIkeExtGlobals
0x1800805f2  add     rcx, 0DE0h
0x1800805f9  call    WfpRestructureHashtable
0x1800805fe  mov     rax, cs:gIkeExtGlobals
0x180080605  mov     rcx, rbx
0x180080608  dec     dword ptr [rax+0E08h]
0x18008060e  call    IkeDerefCacheEntry
0x180080613  jmp     loc_1800806E4
0x180080618  mov     ecx, 3
0x18008061d  int     29h; Win8: RtlFailFast(ecx)
0x18008061f  mov     rdi, cs:WPP_GLOBAL_Control
0x180080626  lea     r15, WPP_GLOBAL_Control
0x18008062d  cmp     rdi, r15
0x180080630  jz      short loc_18008066B
0x180080632  cmp     byte ptr [rdi+19h], 4
0x180080636  jb      short loc_18008066B
0x180080638  test    byte ptr [rdi+1Ch], 10h
0x18008063c  jz      short loc_18008066B
0x18008063e  mov     rdi, [rdi+10h]
0x180080642  call    IkeGetTlsPeerAddr
0x180080647  mov     rbx, rax
0x18008064a  call    IkeGetTlsMmLuid
0x18008064f  mov     r9, rax
0x180080652  mov     [rsp+0F0h+var_D0], rbx
0x180080657  mov     edx, 51h ; 'Q'
0x18008065c  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180080663  mov     rcx, rdi
0x180080666  call    WPP_SF_iS
0x18008066b  mov     eax, cs:dword_180173278
0x180080671  cmp     eax, 4
0x180080674  jbe     short loc_1800806D7
0x180080676  call    IkeGetTlsMmLuid
0x18008067b  mov     [rbp+57h+var_C0], rax
0x18008067f  lea     rax, [rbp+57h+var_C0]
0x180080683  mov     [rbp+57h+var_80], rax
0x180080687  mov     [rbp+57h+var_78], 8
0x18008068f  call    IkeGetTlsPeerAddr
0x180080694  mov     rdx, rax
0x180080697  lea     rcx, [rbp+57h+var_70]
0x18008069b  call    _tlgCreate1Sz_wchar_t
0x1800806a0  lea     rcx, aCredentialsAlr; "Credentials already present in cache, n"...
0x1800806a7  mov     [rbp+57h+var_58], 31h ; '1'
0x1800806af  lea     rax, [rbp+57h+var_A0]
0x1800806b3  mov     [rbp+57h+var_60], rcx
0x1800806b7  mov     [rsp+0F0h+var_C8], rax
0x1800806bc  lea     rcx, dword_180173278
0x1800806c3  lea     rdx, byte_180154C97
0x1800806ca  mov     dword ptr [rsp+0F0h+var_D0], 5
0x1800806d2  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800806d7  mov     rcx, rsi
0x1800806da  call    IkeLogCredCacheEntry
0x1800806df  lock dec dword ptr [r14+30h]
0x1800806e4  mov     rcx, cs:gIkeExtGlobals
0x1800806eb  add     rcx, 0DA0h; lpCriticalSection
0x1800806f2  call    cs:__imp_LeaveCriticalSection
0x1800806f8  xor     edx, edx
0x1800806fa  lea     rcx, aIkeinserttocre; "IkeInsertToCredCache"
0x180080701  call    TraceLogHelper
0x180080706  lea     rdx, aIkeinserttocre; "IkeInsertToCredCache"
0x18008070d  mov     rcx, r12
0x180080710  call    IkeReturnError
0x180080715  mov     rcx, [rbp+57h+var_40]
0x180080719  xor     rcx, rsp; StackCookie
0x18008071c  call    __security_check_cookie
0x180080721  add     rsp, 0C0h
0x180080728  pop     r15
0x18008072a  pop     r14
0x18008072c  pop     r12
0x18008072e  pop     rdi
0x18008072f  pop     rsi
0x180080730  pop     rbx
0x180080731  pop     rbp
0x180080732  retn
```
