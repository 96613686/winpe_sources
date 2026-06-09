# LogAppDrivers_EventArpKeyCreate(_PCA_EVENT_ETW_FROM_DM_PARAM *)

- ea: `0x180032324`
- end: `0x18003263e`
- name: `?LogAppDrivers_EventArpKeyCreate@@YAKPEAU_PCA_EVENT_ETW_FROM_DM_PARAM@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(struct _PCA_EVENT_ETW_FROM_DM_PARAM *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002edd0`

## callees

- `0x18000c560`
- `0x180012920`
- `0x180032324`
- `0x18007a9cf`
- `0x1800a1fc0`
- `0x1800a5ea0`
- `0x1800a5f14`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800323d8`
- `ntdll!RtlCompareMemory` at `0x1800323d8`
- `ntdll!RtlAllocateHeap` at `0x1800324d9`
- `ntdll!RtlAllocateHeap` at `0x1800324d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003243d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003243d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032503`

## string_xrefs

- `0x180032424`: `LogAppDrivers_EventArpKeyCreate`
- `0x1800324a5`: `LogAppDrivers_EventArpKeyCreate`
- `0x1800324f4`: `LogAppDrivers_EventArpKeyCreate`
- `0x18003253e`: `LogAppDrivers_EventArpKeyCreate`
- `0x18003257f`: `LogAppDrivers_EventArpKeyCreate`
- `0x1800325c2`: `LogAppDrivers_EventArpKeyCreate`
- `0x180032601`: `LogAppDrivers_EventArpKeyCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogAppDrivers_EventArpKeyCreate(struct _PCA_EVENT_ETW_FROM_DM_PARAM *a1)
{
  struct Windows::Compat::Inventory::AppInfo2 *v2; // rsi
  __int64 v3; // rax
  unsigned __int64 v4; // r14
  _QWORD *v5; // rbx
  unsigned __int64 v6; // rcx
  unsigned __int16 *v7; // r15
  unsigned __int16 *v8; // r12
  unsigned __int64 v9; // rax
  const unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r9
  __int64 v14; // rax
  SIZE_T v15; // rbx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v17; // r14
  DWORD LastError; // ebx
  const unsigned __int16 *v19; // rcx
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // r9
  struct Windows::Compat::Inventory::AppInfo2 *AppInfo2; // rax
  int v23; // eax
  char v24; // [rsp+20h] [rbp-298h]
  unsigned __int16 v25[264]; // [rsp+60h] [rbp-258h] BYREF

  v2 = 0;
  if ( !dword_180159830 )
    return 6;
  EnterCriticalSection(&g_DriverLog);
  v3 = *((_QWORD *)a1 + 14);
  if ( *(_QWORD *)(v3 + 8) < 4u )
  {
    LastError = 160;
    v24 = -96;
    AslLogCallPrintf(1, (unsigned int)"LogAppDrivers_EventArpKeyCreate", 844, (unsigned int)"Bad ArpKey event [%d]");
  }
  else
  {
    *(_QWORD *)(v3 + 32) = 4;
    v4 = 520;
    memset_0(v25, 0, 0x208u);
    v5 = (_QWORD *)*((_QWORD *)a1 + 14);
    v6 = v5[4];
    if ( v6 >= v5[1] )
    {
LABEL_28:
      LastError = 160;
      v24 = -96;
      AslLogCallPrintf(1, (unsigned int)"LogAppDrivers_EventArpKeyCreate", 855, (unsigned int)"Bad ArpKey event [%d]");
    }
    else
    {
      v7 = (unsigned __int16 *)(v6 + v5[5]);
      v8 = v25;
      while ( 1 )
      {
        v9 = v5[1];
        if ( v6 >= v9 )
          break;
        if ( v9 - v6 >= 2 && RtlCompareMemory(&dword_1800FF0F4, v7, 2u) == 2 )
        {
          v5[4] += 2LL;
          break;
        }
        if ( v4 < 2 )
          goto LABEL_28;
        *v8++ = *v7++;
        v4 -= 2LL;
        v5[4] += 2LL;
        v6 = v5[4];
      }
      v14 = -1;
      do
        ++v14;
      while ( v25[v14] );
      v15 = 2 * v14 + 40;
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v15);
      v17 = Heap;
      if ( Heap )
      {
        if ( StringCbCopyW(Heap, v15, L"HKEY_LOCAL_MACHINE\\") >= 0 )
        {
          if ( StringCbCatW(v17, v15, v25) >= 0 )
          {
            AppInfo2 = LogAppDrivers_GetAppInfo2(v19, v17, v20, v21, v24, 0);
            v2 = AppInfo2;
            if ( AppInfo2 )
            {
              v23 = RtlStringArray::Append(
                      (RtlStringArray *)&qword_1801597C0,
                      *((const unsigned __int16 **)AppInfo2 + 1),
                      0);
              LastError = v23;
              if ( v23 )
              {
                v24 = v23;
                AslLogCallPrintf(
                  1,
                  (unsigned int)"LogAppDrivers_EventArpKeyCreate",
                  908,
                  (unsigned int)"Failed to add programId to driverlog [%d]");
              }
            }
            else
            {
              LastError = 0;
              v24 = (char)v17;
              AslLogCallPrintf(
                1,
                (unsigned int)"LogAppDrivers_EventArpKeyCreate",
                901,
                (unsigned int)"Failed to get ProgramId for [%ls]");
            }
          }
          else
          {
            LastError = 122;
            v24 = 122;
            AslLogCallPrintf(
              1,
              (unsigned int)"LogAppDrivers_EventArpKeyCreate",
              885,
              (unsigned int)"Failed to cat arp key name [%d]");
          }
        }
        else
        {
          LastError = 122;
          v24 = 122;
          AslLogCallPrintf(
            1,
            (unsigned int)"LogAppDrivers_EventArpKeyCreate",
            876,
            (unsigned int)"Failed to cat Hklm [%d]");
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"LogAppDrivers_EventArpKeyCreate",
          863,
          (unsigned int)"Failed to allocate memory for ArpKeyName");
        LastError = GetLastError();
      }
    }
  }
  LeaveCriticalSection(&g_DriverLog);
  if ( v2 )
    LogAppDrivers_GetAppInfo2(v10, 0, v11, v12, v24, v2);
  return LastError;
}

```

## disassembly

```asm
0x180032324  push    rbx
0x180032326  push    rsi
0x180032327  push    rdi
0x180032328  push    r12
0x18003232a  push    r14
0x18003232c  push    r15
0x18003232e  sub     rsp, 288h
0x180032335  mov     rax, cs:__security_cookie
0x18003233c  xor     rax, rsp
0x18003233f  mov     [rsp+2B8h+var_48], rax
0x180032347  mov     rbx, rcx
0x18003234a  xor     edi, edi
0x18003234c  mov     esi, edi
0x18003234e  mov     [rsp+2B8h+var_280], rdi
0x180032353  cmp     cs:dword_180159830, edi
0x180032359  jz      loc_180032488
0x18003235f  lea     rcx, ?g_DriverLog@@3U_LAP_DRIVER_LOG@@A; lpCriticalSection
0x180032366  call    cs:__imp_EnterCriticalSection
0x18003236c  mov     rax, [rbx+70h]
0x180032370  cmp     qword ptr [rax+8], 4
0x180032375  jb      loc_18003248F
0x18003237b  mov     qword ptr [rax+20h], 4
0x180032383  mov     r14d, 208h
0x180032389  mov     r8d, r14d; Size
0x18003238c  xor     edx, edx; Val
0x18003238e  lea     rcx, [rsp+2B8h+var_258]; void *
0x180032393  call    memset_0
0x180032398  mov     rbx, [rbx+70h]
0x18003239c  mov     rcx, [rbx+20h]
0x1800323a0  cmp     rcx, [rbx+8]
0x1800323a4  jnb     short loc_18003240E
0x1800323a6  mov     r15, [rbx+28h]
0x1800323aa  add     r15, rcx
0x1800323ad  lea     r12, [rsp+2B8h+var_258]
0x1800323b2  mov     rax, [rbx+8]
0x1800323b6  cmp     rcx, rax
0x1800323b9  jnb     loc_180032474
0x1800323bf  sub     rax, rcx
0x1800323c2  cmp     rax, 2
0x1800323c6  jb      short loc_1800323E8
0x1800323c8  mov     r8d, 2; Length
0x1800323ce  mov     rdx, r15; Source2
0x1800323d1  lea     rcx, dword_1800FF0F4; Source1
0x1800323d8  call    cs:__imp_RtlCompareMemory
0x1800323de  cmp     rax, 2
0x1800323e2  jz      loc_18003246F
0x1800323e8  cmp     r14, 2
0x1800323ec  jb      short loc_18003240E
0x1800323ee  movzx   eax, word ptr [r15]
0x1800323f2  mov     [r12], ax
0x1800323f7  add     r15, 2
0x1800323fb  add     r12, 2
0x1800323ff  sub     r14, 2
0x180032403  add     qword ptr [rbx+20h], 2
0x180032408  mov     rcx, [rbx+20h]
0x18003240c  jmp     short loc_1800323B2
0x18003240e  mov     ebx, 0A0h
0x180032413  mov     dword ptr [rsp+2B8h+var_298], ebx; bool
0x180032417  lea     r9, aBadArpkeyEvent; "Bad ArpKey event [%d]"
0x18003241e  mov     r8d, 357h
0x180032424  lea     rdx, aLogappdriversE; "LogAppDrivers_EventArpKeyCreate"
0x18003242b  mov     ecx, 1
0x180032430  call    AslLogCallPrintf
0x180032435  nop
0x180032436  lea     rcx, ?g_DriverLog@@3U_LAP_DRIVER_LOG@@A; lpCriticalSection
0x18003243d  call    cs:__imp_LeaveCriticalSection
0x180032443  test    rsi, rsi
0x180032446  jnz     loc_18003262D
0x18003244c  mov     eax, ebx
0x18003244e  mov     rcx, [rsp+2B8h+var_48]
0x180032456  xor     rcx, rsp; StackCookie
0x180032459  call    __security_check_cookie
0x18003245e  add     rsp, 288h
0x180032465  pop     r15
0x180032467  pop     r14
0x180032469  pop     r12
0x18003246b  pop     rdi
0x18003246c  pop     rsi
0x18003246d  pop     rbx
0x18003246e  retn
0x18003246f  add     qword ptr [rbx+20h], 2
0x180032474  lea     rcx, [rsp+2B8h+var_258]
0x180032479  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003247d  inc     rax
0x180032480  cmp     [rcx+rax*2], di
0x180032484  jnz     short loc_18003247D
0x180032486  jmp     short loc_1800324BC
0x180032488  mov     eax, 6
0x18003248d  jmp     short loc_18003244E
0x18003248f  mov     ebx, 0A0h
0x180032494  mov     dword ptr [rsp+2B8h+var_298], ebx
0x180032498  lea     r9, aBadArpkeyEvent; "Bad ArpKey event [%d]"
0x18003249f  mov     r8d, 34Ch
0x1800324a5  lea     rdx, aLogappdriversE; "LogAppDrivers_EventArpKeyCreate"
0x1800324ac  mov     ecx, 1
0x1800324b1  call    AslLogCallPrintf
0x1800324b6  nop
0x1800324b7  jmp     loc_180032436
0x1800324bc  lea     rbx, ds:28h[rax*2]
0x1800324c4  mov     rcx, gs:60h
0x1800324cd  mov     r8, rbx; Size
0x1800324d0  mov     edx, 8; Flags
0x1800324d5  mov     rcx, [rcx+30h]; HeapHandle
0x1800324d9  call    cs:__imp_RtlAllocateHeap
0x1800324df  mov     r14, rax
0x1800324e2  test    rax, rax
0x1800324e5  jnz     short loc_180032510
0x1800324e7  lea     r9, aFailedToAlloca_14; "Failed to allocate memory for ArpKeyNam"...
0x1800324ee  mov     r8d, 35Fh
0x1800324f4  lea     rdx, aLogappdriversE; "LogAppDrivers_EventArpKeyCreate"
0x1800324fb  lea     ecx, [rax+1]
0x1800324fe  call    AslLogCallPrintf
0x180032503  call    cs:__imp_GetLastError
0x180032509  mov     ebx, eax
0x18003250b  jmp     loc_180032436
0x180032510  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\"
0x180032517  mov     rdx, rbx; unsigned __int64
0x18003251a  mov     rcx, r14; unsigned __int16 *
0x18003251d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180032522  test    eax, eax
0x180032524  jns     short loc_180032553
0x180032526  mov     eax, 7Ah ; 'z'
0x18003252b  mov     ebx, eax
0x18003252d  mov     dword ptr [rsp+2B8h+var_298], eax
0x180032531  lea     r9, aFailedToCatHkl; "Failed to cat Hklm [%d]"
0x180032538  mov     r8d, 36Ch
0x18003253e  lea     rdx, aLogappdriversE; "LogAppDrivers_EventArpKeyCreate"
0x180032545  lea     ecx, [rax-79h]
0x180032548  call    AslLogCallPrintf
0x18003254d  nop
0x18003254e  jmp     loc_180032436
0x180032553  lea     r8, [rsp+2B8h+var_258]; unsigned __int16 *
0x180032558  mov     rdx, rbx; unsigned __int64
0x18003255b  mov     rcx, r14; unsigned __int16 *
0x18003255e  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180032563  test    eax, eax
0x180032565  jns     short loc_180032594
0x180032567  mov     eax, 7Ah ; 'z'
0x18003256c  mov     ebx, eax
0x18003256e  mov     dword ptr [rsp+2B8h+var_298], eax
0x180032572  lea     r9, aFailedToCatArp; "Failed to cat arp key name [%d]"
0x180032579  mov     r8d, 375h
0x18003257f  lea     rdx, aLogappdriversE; "LogAppDrivers_EventArpKeyCreate"
0x180032586  lea     ecx, [rax-79h]
0x180032589  call    AslLogCallPrintf
0x18003258e  nop
0x18003258f  jmp     loc_180032436
0x180032594  mov     [rsp+2B8h+var_290], rdi; struct Windows::Compat::Inventory::AppInfo2 *
0x180032599  mov     rdx, r14; unsigned __int16 *
0x18003259c  call    ?LogAppDrivers_GetAppInfo2@@YAPEAUAppInfo2@Inventory@Compat@Windows@@PEBG000_NPEAU1234@@Z; LogAppDrivers_GetAppInfo2(ushort const *,ushort const *,ushort const *,ushort const *,bool,Windows::Compat::Inventory::AppInfo2 *)
0x1800325a1  mov     rsi, rax
0x1800325a4  mov     [rsp+2B8h+var_280], rax
0x1800325a9  test    rax, rax
0x1800325ac  jnz     short loc_1800325D7
0x1800325ae  mov     ebx, edi
0x1800325b0  mov     qword ptr [rsp+2B8h+var_298], r14
0x1800325b5  lea     r9, aFailedToGetPro_5; "Failed to get ProgramId for [%ls]"
0x1800325bc  mov     r8d, 385h
0x1800325c2  lea     rdx, aLogappdriversE; "LogAppDrivers_EventArpKeyCreate"
0x1800325c9  lea     ecx, [rax+1]
0x1800325cc  call    AslLogCallPrintf
0x1800325d1  nop
0x1800325d2  jmp     loc_180032436
0x1800325d7  xor     r8d, r8d; unsigned __int64
0x1800325da  mov     rdx, [rax+8]; unsigned __int16 *
0x1800325de  lea     rcx, qword_1801597C0; this
0x1800325e5  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x1800325ea  mov     ebx, eax
0x1800325ec  test    eax, eax
0x1800325ee  jz      short loc_180032618
0x1800325f0  mov     dword ptr [rsp+2B8h+var_298], eax
0x1800325f4  lea     r9, aFailedToAddPro; "Failed to add programId to driverlog [%"...
0x1800325fb  mov     r8d, 38Ch
0x180032601  lea     rdx, aLogappdriversE; "LogAppDrivers_EventArpKeyCreate"
0x180032608  mov     ecx, 1
0x18003260d  call    AslLogCallPrintf
0x180032612  nop
0x180032613  jmp     loc_180032436
0x180032618  jmp     loc_180032436
0x18003261d  jmp     short $+2
0x18003261f  mov     rsi, [rsp+2B8h+var_280]
0x180032624  mov     ebx, [rsp+2B8h+var_288]
0x180032628  jmp     loc_180032436
0x18003262d  mov     [rsp+2B8h+var_290], rsi; struct Windows::Compat::Inventory::AppInfo2 *
0x180032632  xor     edx, edx; unsigned __int16 *
0x180032634  call    ?LogAppDrivers_GetAppInfo2@@YAPEAUAppInfo2@Inventory@Compat@Windows@@PEBG000_NPEAU1234@@Z; LogAppDrivers_GetAppInfo2(ushort const *,ushort const *,ushort const *,ushort const *,bool,Windows::Compat::Inventory::AppInfo2 *)
0x180032639  jmp     loc_18003244C
```
