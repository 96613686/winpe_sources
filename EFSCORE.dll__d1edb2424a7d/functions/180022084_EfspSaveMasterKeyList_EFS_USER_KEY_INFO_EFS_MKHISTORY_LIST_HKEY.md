# EfspSaveMasterKeyList(_EFS_USER_KEY_INFO *,_EFS_MKHISTORY_LIST *,HKEY__ *)

- ea: `0x180022084`
- end: `0x1800226e5`
- name: `?EfspSaveMasterKeyList@@YAKPEAU_EFS_USER_KEY_INFO@@PEAU_EFS_MKHISTORY_LIST@@PEAUHKEY__@@@Z`
- size: `1633`
- prototype: `unsigned int __fastcall(struct _EFS_USER_KEY_INFO *, struct _EFS_MKHISTORY_LIST *, HKEY)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022bf4`

## callees

- `0x180004f86`
- `0x1800102f0`
- `0x180010bf0`
- `0x180020894`
- `0x180020cd0`
- `0x180021f8c`
- `0x180022084`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800223a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800223cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800223a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800223cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800224aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800224aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800220ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800220ef`
- `bcrypt!BCryptGenRandom` at `0x180022252`
- `bcrypt!BCryptGenRandom` at `0x180022252`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180022372`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180022372`
- `ntdll!NtCreateRegistryTransaction` at `0x180022316`
- `ntdll!NtCreateRegistryTransaction` at `0x180022316`
- `ntdll!NtCommitRegistryTransaction` at `0x1800223e5`
- `ntdll!NtCommitRegistryTransaction` at `0x1800223e5`

## pseudocode

```c
__int64 __fastcall EfspSaveMasterKeyList(struct _EFS_USER_KEY_INFO *a1, struct _EFS_MKHISTORY_LIST **a2, HKEY a3)
{
  HKEY v5; // rdi
  __int64 v6; // rcx
  unsigned int v7; // r14d
  struct _EFS_MKHISTORY_LIST *v8; // rsi
  bool v9; // zf
  const void **v10; // r12
  int v11; // eax
  SIZE_T v12; // r15
  _DWORD *v13; // rax
  __int64 v14; // rcx
  _DWORD *v15; // rdi
  char *v16; // rbx
  size_t v17; // r8
  char *v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rcx
  NTSTATUS v21; // eax
  unsigned int v22; // r9d
  unsigned int v23; // eax
  int v24; // ecx
  BYTE *v25; // r12
  unsigned int MasterKeyElementIVRegValueName; // ebx
  int v27; // eax
  LSTATUS v28; // eax
  int v29; // eax
  unsigned int v30; // eax
  char v31; // di
  int v32; // r8d
  int v33; // eax
  int v35; // r8d
  char v36; // si
  int v37; // eax
  _BYTE *i; // rax
  int v39; // r8d
  char dwOptions; // [rsp+20h] [rbp-89h]
  char dwOptionsa; // [rsp+20h] [rbp-89h]
  HANDLE hObject; // [rsp+60h] [rbp-49h] BYREF
  BYTE *lpData; // [rsp+68h] [rbp-41h] BYREF
  LPCWSTR lpValueName; // [rsp+70h] [rbp-39h] BYREF
  LPCWSTR *v45; // [rsp+78h] [rbp-31h]
  struct _EFS_MKHISTORY_LIST *v46; // [rsp+80h] [rbp-29h]
  UCHAR pbBuffer[16]; // [rsp+88h] [rbp-21h] BYREF
  __int128 v48; // [rsp+98h] [rbp-11h] BYREF
  __int128 v49; // [rsp+A8h] [rbp-1h]
  DWORD cbData; // [rsp+110h] [rbp+67h] BYREF
  struct _EFS_MKHISTORY_LIST **v51; // [rsp+118h] [rbp+6Fh]
  HKEY hKey; // [rsp+120h] [rbp+77h]
  HKEY phkResult; // [rsp+128h] [rbp+7Fh] BYREF

  hKey = a3;
  v51 = a2;
  cbData = 0;
  phkResult = 0;
  lpData = 0;
  hObject = 0;
  lpValueName = 0;
  v48 = 0;
  v5 = a3;
  v49 = 0;
  *(_OWORD *)pbBuffer = 0;
  RegDeleteValueW(a3, L"EncryptionKeyHash");
  if ( (*((_BYTE *)a1 + 48) & 0xF0) != 0 )
  {
    if ( (*((_BYTE *)a1 + 48) & 0x20) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    v7 = 32;
  }
  else
  {
    v7 = ((*((_BYTE *)a1 + 40) & 0x40) != 0) + 1;
  }
  v8 = *a2;
  if ( *a2 != (struct _EFS_MKHISTORY_LIST *)a2 )
  {
    while ( 1 )
    {
      v9 = *((_DWORD *)v8 - 8) == 65568;
      v46 = *(struct _EFS_MKHISTORY_LIST **)v8;
      if ( v9 )
      {
        v10 = (const void **)*((_QWORD *)v8 - 1);
        if ( !v10 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v6);
        v11 = *(_DWORD *)v10 + *((_DWORD *)v8 - 7) + *((_DWORD *)v10 + 4);
        v45 = (LPCWSTR *)off_1801143F8;
      }
      else
      {
        if ( *((_DWORD *)v8 - 8) != 65538 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v6);
          v32 = 87;
          v31 = -85;
          MasterKeyElementIVRegValueName = 87;
          goto LABEL_35;
        }
        v10 = 0;
        v45 = (LPCWSTR *)&qword_1801143F0;
        v11 = *((_DWORD *)v8 - 7);
      }
      v12 = (v11 + 31) & 0xFFFFFFF0;
      v13 = wil::details::heap_allocator::allocate(v12);
      v15 = v13;
      if ( !v13 )
      {
        v31 = -79;
        MasterKeyElementIVRegValueName = 8;
        v33 = fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, v12, 8, 177);
        goto LABEL_36;
      }
      if ( *((_DWORD *)v8 - 8) == 65568 )
      {
        if ( !v10 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v14);
        *v15 = v12;
        v15[1] = *(_DWORD *)v10;
        v15[2] = *((_DWORD *)v10 + 4);
        v15[3] = *((_DWORD *)v8 - 7);
        memcpy_0(v15 + 4, v10[1], *(unsigned int *)v10);
        v16 = (char *)v15 + *(unsigned int *)v10 + 16;
        memcpy_0(v16, v10[3], *((unsigned int *)v10 + 4));
        v17 = *((unsigned int *)v8 - 7);
        v18 = &v16[*((unsigned int *)v10 + 4)];
      }
      else
      {
        if ( *((_DWORD *)v8 - 8) != 65538 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v14);
          MasterKeyElementIVRegValueName = 87;
          v39 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 87, 8, 232);
          dwOptionsa = -24;
          goto LABEL_59;
        }
        *v13 = v12;
        v18 = (char *)(v13 + 4);
        v19 = *((_DWORD *)v8 - 7);
        v15[1] = v19;
        v17 = v19;
        *((_QWORD *)v15 + 1) = v15 + 4;
      }
      memcpy_0(v18, *((const void **)v8 - 3), v17);
      if ( (unsigned int)g_cbAesBlockLen > 0x10 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v20);
        MasterKeyElementIVRegValueName = 1359;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 1359, 8, 243);
        goto LABEL_60;
      }
      v21 = BCryptGenRandom(0, pbBuffer, g_cbAesBlockLen, 2u);
      if ( v21 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 8, 252);
        v39 = 1359;
        dwOptionsa = -3;
        MasterKeyElementIVRegValueName = 1359;
LABEL_59:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v39, 8, dwOptionsa);
        goto LABEL_60;
      }
      v23 = EfspEncryptData(a1, v12, (unsigned __int8 *)v15, v22, pbBuffer, v7, &cbData, &lpData);
      v25 = lpData;
      MasterKeyElementIVRegValueName = v23;
      if ( v23 )
      {
        for ( i = v15; v12; --v12 )
          *i++ = 0;
        v36 = 16;
        v37 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, MasterKeyElementIVRegValueName, 8, 16);
        goto LABEL_52;
      }
      fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 8, 20);
      MasterKeyElementIVRegValueName = EfspGenerateMasterKeyElementIVRegValueName(
                                         *((const unsigned __int16 **)v8 - 2),
                                         (unsigned __int16 **)&lpValueName);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  MasterKeyElementIVRegValueName,
                  8,
                  20) < 0 )
        goto LABEL_54;
      v27 = NtCreateRegistryTransaction(&hObject, 2031679, 0, 0);
      if ( v27 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v27, 8, 28);
        dwOptions = 29;
LABEL_43:
        v35 = 1359;
        MasterKeyElementIVRegValueName = 1359;
LABEL_53:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v35, 8, dwOptions);
LABEL_54:
        if ( v25 )
          EfsFreeHeap(v25);
LABEL_60:
        EfsFreeHeap(v15);
        goto LABEL_37;
      }
      v28 = RegCreateKeyTransactedW(hKey, *v45, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0, hObject, 0);
      MasterKeyElementIVRegValueName = v28;
      if ( v28 )
      {
        v36 = 44;
        goto LABEL_45;
      }
      v28 = RegSetValueExW(phkResult, lpValueName, 0, 3u, pbBuffer, g_cbAesBlockLen);
      MasterKeyElementIVRegValueName = v28;
      if ( v28 )
      {
        v36 = 54;
        goto LABEL_45;
      }
      v28 = RegSetValueExW(phkResult, *((LPCWSTR *)v8 - 2), 0, 3u, v25, cbData);
      MasterKeyElementIVRegValueName = v28;
      if ( v28 )
      {
        v36 = 64;
LABEL_45:
        v37 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v28, 8, v36);
LABEL_52:
        v35 = v37;
        dwOptions = v36;
        goto LABEL_53;
      }
      v29 = NtCommitRegistryTransaction(hObject, 0);
      if ( v29 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v29, 8, 70);
        dwOptions = 71;
        goto LABEL_43;
      }
      v8 = v46;
      EfsFreeHeap(v15);
      EfsFreeHeap(v25);
      lpData = 0;
      RegCloseKey(phkResult);
      phkResult = 0;
      if ( v8 == (struct _EFS_MKHISTORY_LIST *)v51 )
      {
        v5 = hKey;
        break;
      }
    }
  }
  *((_QWORD *)&v48 + 1) = *((_QWORD *)a1 + 1);
  LODWORD(v49) = *((_DWORD *)a1 + 1);
  LODWORD(v48) = v7;
  if ( v7 == 32 )
    *((_QWORD *)&v49 + 1) = (char *)a1 + 104;
  v30 = EfspSaveMasterKeyHistoryConfiguration(v5, (struct _EFS_MKHISTORY_CONFIGURATION *)&v48);
  MasterKeyElementIVRegValueName = v30;
  if ( v30 )
  {
    v31 = 100;
    v32 = v30;
LABEL_35:
    v33 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v32, 8, v31);
LABEL_36:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v33, 8, v31);
  }
LABEL_37:
  if ( phkResult )
    RegCloseKey(phkResult);
  EfsFreeHeap((LPVOID)lpValueName);
  if ( hObject )
    CloseHandle(hObject);
  return MasterKeyElementIVRegValueName;
}

```

## disassembly

```asm
0x180022084  mov     [rsp-8+hKey], r8
0x180022089  mov     [rsp-8+arg_8], rdx
0x18002208e  push    rbp
0x18002208f  push    rbx
0x180022090  push    rsi
0x180022091  push    rdi
0x180022092  push    r12
0x180022094  push    r13
0x180022096  push    r14
0x180022098  push    r15
0x18002209a  lea     rbp, [rsp-1Fh]
0x18002209f  sub     rsp, 0C8h
0x1800220a6  xorps   xmm0, xmm0
0x1800220a9  mov     [rbp+57h+cbData], 0
0x1800220b0  mov     rbx, rdx
0x1800220b3  mov     [rbp+57h+arg_18], 0
0x1800220bb  mov     r13, rcx
0x1800220be  mov     [rbp+57h+lpData], 0
0x1800220c6  lea     rdx, String2; "EncryptionKeyHash"
0x1800220cd  mov     [rbp+57h+hObject], 0
0x1800220d5  mov     rcx, r8; hKey
0x1800220d8  mov     [rbp+57h+lpValueName], 0
0x1800220e0  movups  [rbp+57h+var_68], xmm0
0x1800220e4  mov     rdi, r8
0x1800220e7  movups  [rbp+57h+var_58], xmm0
0x1800220eb  movups  xmmword ptr [rbp+57h+pbBuffer], xmm0
0x1800220ef  call    cs:__imp_RegDeleteValueW
0x1800220f5  test    byte ptr [r13+30h], 0F0h
0x1800220fa  jz      short loc_180022110
0x1800220fc  test    byte ptr [r13+30h], 20h
0x180022101  jnz     short loc_180022108
0x180022103  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "EFS_TEST_FLAG(pEfsKeyInfo->dwKeyType, EFS_KEY_TYPE_ECC_CACHED_KEY)")
0x180022108  mov     r14d, 20h ; ' '
0x18002210e  jmp     short loc_180022121
0x180022110  mov     al, [r13+28h]
0x180022114  and     al, 40h
0x180022116  neg     al
0x180022118  sbb     r14d, r14d
0x18002211b  neg     r14d
0x18002211e  inc     r14d
0x180022121  mov     rsi, [rbx]
0x180022124  mov     r15d, 8
0x18002212a  cmp     rsi, rbx
0x18002212d  jz      loc_18002242F
0x180022133  cmp     dword ptr [rsi-20h], 10020h
0x18002213a  mov     rax, [rsi]
0x18002213d  mov     [rbp+57h+var_80], rax
0x180022141  jnz     short loc_18002216A
0x180022143  mov     r12, [rsi-8]
0x180022147  test    r12, r12
0x18002214a  jnz     short loc_180022151
0x18002214c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pcSecondaryKeyInfo != NULL")
0x180022151  mov     eax, [r12+10h]
0x180022156  lea     rbx, off_1801143F8; "ECC"
0x18002215d  add     eax, [rsi-1Ch]
0x180022160  add     eax, [r12]
0x180022164  mov     [rbp+57h+var_88], rbx
0x180022168  jmp     short loc_180022188
0x18002216a  cmp     dword ptr [rsi-20h], 10002h
0x180022171  jnz     loc_1800226CD
0x180022177  lea     rax, qword_1801143F0
0x18002217e  xor     r12d, r12d
0x180022181  mov     [rbp+57h+var_88], rax
0x180022185  mov     eax, [rsi-1Ch]
0x180022188  add     eax, 1Fh
0x18002218b  and     eax, 0FFFFFFF0h
0x18002218e  mov     ecx, eax; unsigned __int64
0x180022190  mov     r15d, eax
0x180022193  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180022198  mov     rdi, rax
0x18002219b  test    rax, rax
0x18002219e  jz      loc_18002269A
0x1800221a4  cmp     dword ptr [rsi-20h], 10020h
0x1800221ab  jnz     short loc_18002220B
0x1800221ad  test    r12, r12
0x1800221b0  jnz     short loc_1800221B7
0x1800221b2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pcSecondaryKeyInfo != NULL")
0x1800221b7  mov     [rdi], r15d
0x1800221ba  lea     rbx, [rdi+10h]
0x1800221be  mov     eax, [r12]
0x1800221c2  mov     rcx, rbx; void *
0x1800221c5  mov     [rdi+4], eax
0x1800221c8  mov     eax, [r12+10h]
0x1800221cd  mov     [rdi+8], eax
0x1800221d0  mov     eax, [rsi-1Ch]
0x1800221d3  mov     [rdi+0Ch], eax
0x1800221d6  mov     r8d, [r12]; Size
0x1800221da  mov     rdx, [r12+8]; Src
0x1800221df  call    memcpy_0
0x1800221e4  mov     eax, [r12]
0x1800221e8  mov     r8d, [r12+10h]; Size
0x1800221ed  add     rbx, rax
0x1800221f0  mov     rdx, [r12+18h]; Src
0x1800221f5  mov     rcx, rbx; void *
0x1800221f8  call    memcpy_0
0x1800221fd  mov     ecx, [r12+10h]
0x180022202  mov     r8d, [rsi-1Ch]
0x180022206  add     rcx, rbx
0x180022209  jmp     short loc_18002222C
0x18002220b  cmp     dword ptr [rsi-20h], 10002h
0x180022212  jnz     loc_18002263F
0x180022218  mov     [rax], r15d
0x18002221b  lea     rcx, [rdi+10h]; void *
0x18002221f  mov     eax, [rsi-1Ch]
0x180022222  mov     [rdi+4], eax
0x180022225  mov     r8d, eax; Size
0x180022228  mov     [rdi+8], rcx
0x18002222c  mov     rdx, [rsi-18h]; Src
0x180022230  call    memcpy_0
0x180022235  mov     r8d, cs:?g_cbAesBlockLen@@3KA; cbBuffer
0x18002223c  cmp     r8d, 10h
0x180022240  ja      loc_180022621
0x180022246  mov     r9d, 2; dwFlags
0x18002224c  lea     rdx, [rbp+57h+pbBuffer]; pbBuffer
0x180022250  xor     ecx, ecx; hAlgorithm
0x180022252  call    cs:__imp_BCryptGenRandom
0x180022258  test    eax, eax
0x18002225a  jnz     loc_1800225E7
0x180022260  lea     rax, [rbp+57h+lpData]
0x180022264  mov     r8, rdi; unsigned __int8 *
0x180022267  mov     [rsp+100h+phkResult], rax; unsigned __int8 **
0x18002226c  mov     edx, r15d; unsigned int
0x18002226f  lea     rax, [rbp+57h+cbData]
0x180022273  mov     rcx, r13; struct _EFS_USER_KEY_INFO *
0x180022276  mov     [rsp+100h+lpSecurityAttributes], rax; unsigned int *
0x18002227b  lea     rax, [rbp+57h+pbBuffer]
0x18002227f  mov     [rsp+100h+samDesired], r14d; unsigned int
0x180022284  mov     qword ptr [rsp+100h+dwOptions], rax; Src
0x180022289  call    ?EfspEncryptData@@YAKPEAU_EFS_USER_KEY_INFO@@KPEAEK1KPEAKPEAPEAE@Z; EfspEncryptData(_EFS_USER_KEY_INFO *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar * *)
0x18002228e  mov     r12, [rbp+57h+lpData]
0x180022292  mov     ebx, eax
0x180022294  test    eax, eax
0x180022296  jnz     loc_180022578
0x18002229c  lea     r15d, [rax+8]
0x1800222a0  mov     [rsp+100h+dwOptions], 914h
0x1800222a8  mov     r9d, r15d
0x1800222ab  lea     r8, sourceString
0x1800222b2  lea     rdx, EFS_TRACE_START_EVENT
0x1800222b9  call    fnEfsLogTrace1Strings
0x1800222be  mov     rcx, [rsi-10h]; unsigned __int16 *
0x1800222c2  lea     rdx, [rbp+57h+lpValueName]; unsigned __int16 **
0x1800222c6  call    ?EfspGenerateMasterKeyElementIVRegValueName@@YAKPEBGPEAPEAG@Z; EfspGenerateMasterKeyElementIVRegValueName(ushort const *,ushort * *)
0x1800222cb  mov     rcx, cs:g_hPublisher
0x1800222d2  lea     r9, sourceString
0x1800222d9  mov     dword ptr [rsp+100h+lpSecurityAttributes], 914h
0x1800222e1  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800222e8  mov     [rsp+100h+samDesired], r15d
0x1800222ed  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800222f4  mov     [rsp+100h+dwOptions], eax
0x1800222f8  mov     ebx, eax
0x1800222fa  call    fnEfsLogTrace1String1Dword
0x1800222ff  test    eax, eax
0x180022301  js      loc_1800225D1
0x180022307  xor     r9d, r9d
0x18002230a  lea     rcx, [rbp+57h+hObject]
0x18002230e  xor     r8d, r8d
0x180022311  mov     edx, 1F003Fh
0x180022316  call    cs:__imp_NtCreateRegistryTransaction
0x18002231c  test    eax, eax
0x18002231e  jnz     loc_18002254D
0x180022324  mov     rax, [rbp+57h+hObject]
0x180022328  xor     r9d, r9d; lpClass
0x18002232b  mov     rdx, [rbp+57h+var_88]
0x18002232f  xor     r8d, r8d; Reserved
0x180022332  mov     rcx, [rbp+57h+hKey]; hKey
0x180022336  mov     [rsp+100h+pExtendedParemeter], 0; pExtendedParemeter
0x18002233f  mov     [rsp+100h+hTransaction], rax; hTransaction
0x180022344  lea     rax, [rbp+57h+arg_18]
0x180022348  mov     rdx, [rdx]; lpSubKey
0x18002234b  mov     [rsp+100h+lpdwDisposition], 0; lpdwDisposition
0x180022354  mov     [rsp+100h+phkResult], rax; phkResult
0x180022359  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180022362  mov     [rsp+100h+samDesired], 2001Fh; samDesired
0x18002236a  mov     [rsp+100h+dwOptions], 0; dwOptions
0x180022372  call    cs:__imp_RegCreateKeyTransactedW
0x180022378  mov     ebx, eax
0x18002237a  test    eax, eax
0x18002237c  jnz     loc_180022546
0x180022382  mov     eax, cs:?g_cbAesBlockLen@@3KA; ulong g_cbAesBlockLen
0x180022388  lea     r9d, [r15-5]; dwType
0x18002238c  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x180022390  xor     r8d, r8d; Reserved
0x180022393  mov     rcx, [rbp+57h+arg_18]; hKey
0x180022397  mov     [rsp+100h+samDesired], eax; cbData
0x18002239b  lea     rax, [rbp+57h+pbBuffer]
0x18002239f  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x1800223a4  call    cs:__imp_RegSetValueExW
0x1800223aa  mov     ebx, eax
0x1800223ac  test    eax, eax
0x1800223ae  jnz     loc_18002253F
0x1800223b4  mov     eax, [rbp+57h+cbData]
0x1800223b7  lea     r9d, [r15-5]; dwType
0x1800223bb  mov     rdx, [rsi-10h]; lpValueName
0x1800223bf  xor     r8d, r8d; Reserved
0x1800223c2  mov     rcx, [rbp+57h+arg_18]; hKey
0x1800223c6  mov     [rsp+100h+samDesired], eax; cbData
0x1800223ca  mov     qword ptr [rsp+100h+dwOptions], r12; lpData
0x1800223cf  call    cs:__imp_RegSetValueExW
0x1800223d5  mov     ebx, eax
0x1800223d7  test    eax, eax
0x1800223d9  jnz     loc_180022518
0x1800223df  mov     rcx, [rbp+57h+hObject]
0x1800223e3  xor     edx, edx
0x1800223e5  call    cs:__imp_NtCommitRegistryTransaction
0x1800223eb  test    eax, eax
0x1800223ed  jnz     loc_1800224DE
0x1800223f3  mov     rsi, [rbp+57h+var_80]
0x1800223f7  mov     rcx, rdi; lpMem
0x1800223fa  call    EfsFreeHeap
0x1800223ff  mov     rcx, r12; lpMem
0x180022402  call    EfsFreeHeap
0x180022407  mov     rcx, [rbp+57h+arg_18]; hKey
0x18002240b  mov     [rbp+57h+lpData], 0
0x180022413  call    cs:__imp_RegCloseKey
0x180022419  mov     [rbp+57h+arg_18], 0
0x180022421  cmp     rsi, [rbp+57h+arg_8]
0x180022425  jnz     loc_180022133
0x18002242b  mov     rdi, [rbp+57h+hKey]
0x18002242f  mov     rax, [r13+8]
0x180022433  mov     qword ptr [rbp+57h+var_68+8], rax
0x180022437  mov     eax, [r13+4]
0x18002243b  mov     dword ptr [rbp+57h+var_58], eax
0x18002243e  mov     dword ptr [rbp+57h+var_68], r14d
0x180022442  cmp     r14d, 20h ; ' '
0x180022446  jnz     short loc_180022450
0x180022448  lea     rax, [r13+68h]
0x18002244c  mov     qword ptr [rbp+57h+var_58+8], rax
0x180022450  lea     rdx, [rbp+57h+var_68]; struct _EFS_MKHISTORY_CONFIGURATION *
0x180022454  mov     rcx, rdi; hKey
0x180022457  call    ?EfspSaveMasterKeyHistoryConfiguration@@YAKPEAUHKEY__@@PEAU_EFS_MKHISTORY_CONFIGURATION@@@Z; EfspSaveMasterKeyHistoryConfiguration(HKEY__ *,_EFS_MKHISTORY_CONFIGURATION *)
0x18002245c  mov     ebx, eax
0x18002245e  test    eax, eax
0x180022460  jz      short loc_1800224A1
0x180022462  mov     edi, 964h
0x180022467  mov     r8d, eax
0x18002246a  mov     rcx, cs:g_hPublisher
0x180022471  lea     rdx, EFS_API_ERROR
0x180022478  mov     r9d, r15d
0x18002247b  mov     [rsp+100h+dwOptions], edi
0x18002247f  call    fnEfsLogTrace1
0x180022484  mov     r9d, r15d
0x180022487  mov     rcx, cs:g_hPublisher
0x18002248e  lea     rdx, EFS_TRACE_ERROR
0x180022495  mov     r8d, eax
0x180022498  mov     [rsp+100h+dwOptions], edi
0x18002249c  call    fnEfsLogTrace1
0x1800224a1  mov     rcx, [rbp+57h+arg_18]; hKey
0x1800224a5  test    rcx, rcx
0x1800224a8  jz      short loc_1800224B0
0x1800224aa  call    cs:__imp_RegCloseKey
0x1800224b0  mov     rcx, [rbp+57h+lpValueName]; lpMem
0x1800224b4  call    EfsFreeHeap
0x1800224b9  mov     rcx, [rbp+57h+hObject]; hObject
0x1800224bd  test    rcx, rcx
0x1800224c0  jz      short loc_1800224C8
0x1800224c2  call    cs:__imp_CloseHandle
0x1800224c8  mov     eax, ebx
0x1800224ca  add     rsp, 0C8h
0x1800224d1  pop     r15
0x1800224d3  pop     r14
0x1800224d5  pop     r13
0x1800224d7  pop     r12
0x1800224d9  pop     rdi
0x1800224da  pop     rsi
0x1800224db  pop     rbx
0x1800224dc  pop     rbp
0x1800224dd  retn
0x1800224de  mov     rcx, cs:g_hPublisher
0x1800224e5  lea     rdx, EFS_API_ERROR
0x1800224ec  mov     r9d, r15d
0x1800224ef  mov     [rsp+100h+dwOptions], 946h
0x1800224f7  mov     r8d, eax
0x1800224fa  call    fnEfsLogTrace1
0x1800224ff  mov     [rsp+100h+dwOptions], 947h
0x180022507  mov     r8d, 54Fh
0x18002250d  mov     r9d, r15d
0x180022510  mov     ebx, r8d
0x180022513  jmp     loc_1800225BE
0x180022518  mov     esi, 940h
0x18002251d  mov     rcx, cs:g_hPublisher
0x180022524  lea     rdx, EFS_API_ERROR
0x18002252b  mov     r9d, r15d
0x18002252e  mov     [rsp+100h+dwOptions], esi
0x180022532  mov     r8d, eax
0x180022535  call    fnEfsLogTrace1
0x18002253a  mov     r9d, r15d
0x18002253d  jmp     short loc_1800225B7
0x18002253f  mov     esi, 936h
0x180022544  jmp     short loc_18002251D
0x180022546  mov     esi, 92Ch
0x18002254b  jmp     short loc_18002251D
0x18002254d  mov     rcx, cs:g_hPublisher
0x180022554  lea     rdx, EFS_API_ERROR
0x18002255b  mov     r9d, r15d
0x18002255e  mov     [rsp+100h+dwOptions], 91Ch
0x180022566  mov     r8d, eax
0x180022569  call    fnEfsLogTrace1
0x18002256e  mov     [rsp+100h+dwOptions], 91Dh
0x180022576  jmp     short loc_180022507
0x180022578  mov     rax, rdi
  ... truncated ...
```
