# ComponentOnDemandp_AddToQueue(_PCA_EVENT_ETW_FROM_DM_PARAM *)

- ea: `0x1800a7078`
- end: `0x1800a7542`
- name: `?ComponentOnDemandp_AddToQueue@@YAKPEAU_PCA_EVENT_ETW_FROM_DM_PARAM@@@Z`
- size: `1226`
- prototype: `__int64 __fastcall(struct _PCA_EVENT_ETW_FROM_DM_PARAM *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029500`

## callees

- `0x180012920`
- `0x18001b320`
- `0x1800212b0`
- `0x180025cc8`
- `0x180052bf4`
- `0x18007a9cf`
- `0x1800a7078`
- `0x1800a7548`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800a74ef`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a74ef`
- `ntdll!RtlEnterCriticalSection` at `0x1800a73c4`
- `ntdll!RtlEnterCriticalSection` at `0x1800a73c4`
- `ntdll!RtlReAllocateHeap` at `0x1800a7487`
- `ntdll!RtlReAllocateHeap` at `0x1800a7487`
- `ntdll!RtlAllocateHeap` at `0x1800a70c6`
- `ntdll!RtlAllocateHeap` at `0x1800a7463`
- `ntdll!RtlAllocateHeap` at `0x1800a70c6`
- `ntdll!RtlAllocateHeap` at `0x1800a7463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a724d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a72c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a736c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a73a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a724d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a72c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a736c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a73a3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a7243`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a7243`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a7399`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a7399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a7331`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800a7362`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800a7362`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800a72b5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800a72b5`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x1800a72ec`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x1800a72ec`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800a7148`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800a7148`

## string_xrefs

- `0x1800a73af`: `Failed to open process token [%d]`
- `0x1800a722a`: `Failed to get component name [%d]`
- `0x1800a72fe`: `Failed to read compatibility data [%d]`
- `0x1800a70e1`: `ComponentOnDemandp_AddToQueue`
- `0x1800a711d`: `ComponentOnDemandp_AddToQueue`
- `0x1800a727e`: `ComponentOnDemandp_AddToQueue`
- `0x1800a7536`: `Failed to read suspend process value [%d]`
- `0x1800a7205`: `Failed to read BinaryName [%d]`
- `0x1800a7502`: `Request,Component,%S,Binary,%S`
- `0x1800a7510`: `ComponentOnDemand`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComponentOnDemandp_AddToQueue(struct _PCA_EVENT_ETW_FROM_DM_PARAM *a1)
{
  PVOID Heap; // rdi
  unsigned int String; // ebx
  _QWORD *v4; // rdx
  DWORD v5; // r12d
  unsigned __int64 v6; // rcx
  int v7; // r8d
  const char *v8; // r9
  unsigned __int64 v10; // r8
  _QWORD *v11; // rdx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned int v14; // edx
  DWORD LastError; // eax
  const char *v16; // r9
  int v17; // r8d
  HANDLE v18; // rax
  DWORD v19; // eax
  unsigned int v20; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v22; // eax
  DWORD v23; // eax
  ULONGLONG v24; // r14
  __int64 v25; // rsi
  __int64 v26; // r9
  ULONGLONG v27; // rsi
  PVOID v28; // rax
  PVOID v29; // rbx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-E0h]
  ULONGLONG Size; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG pullResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v34[264]; // [rsp+60h] [rbp-A0h] BYREF

  v34[0] = 0;
  v32 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x240u);
  if ( !Heap )
  {
    String = 14;
    AslLogCallPrintf(1, (unsigned int)"ComponentOnDemandp_AddToQueue", 262, (unsigned int)"Out of memory");
LABEL_8:
    ComponentOnDemandp_CleanupCODRequest((struct _PCA_COMPONENT_ON_DEMAND_DATA *)Heap);
    goto LABEL_9;
  }
  v4 = (_QWORD *)*((_QWORD *)a1 + 14);
  v5 = 0;
  v6 = v4[4];
  if ( v6 > v4[1] || (v10 = v6 + 4, v6 + 4 < v6) || v10 > v4[1] )
  {
    String = 160;
  }
  else
  {
    String = 0;
    v5 = *(_DWORD *)(v6 + v4[5]);
    v4[4] = v10;
    if ( v5 )
    {
      v11 = (_QWORD *)*((_QWORD *)a1 + 14);
      v12 = v11[4];
      if ( v12 > v11[1] || v12 + 4 < v12 || v12 + 4 > v11[1] )
      {
        String = 160;
      }
      else
      {
        *((_DWORD *)Heap + 131) = *(_DWORD *)(v12 + v11[5]);
        v13 = v11[4];
        if ( v13 + 4 >= v13 )
        {
          v11[4] = v13 + 4;
          String = RtlMemoryStream::ReadString(*((RtlMemoryStream **)a1 + 14), v34, 0x104u, &dword_1800FF0F4);
          if ( String )
          {
            v7 = 295;
            v8 = "Failed to read BinaryName [%d]";
            goto LABEL_6;
          }
          String = ComponentOnDemandp_GetComponentName((unsigned __int16 *)Heap, v14, v34);
          if ( String )
          {
            v7 = 307;
            v8 = "Failed to get component name [%d]";
            goto LABEL_6;
          }
          if ( !ProcessIdToSessionId(v5, (DWORD *)Heap + 133) )
          {
            LastError = GetLastError();
            v7 = 317;
            v8 = "Failed to get session id [%d]";
            String = LastError;
            goto LABEL_6;
          }
          if ( !*((_DWORD *)Heap + 133) )
          {
            v16 = "Cannot process requests for session 0 [%d]";
            v17 = 327;
LABEL_28:
            String = 1359;
            AslLogCallPrintf(1, (unsigned int)"ComponentOnDemandp_AddToQueue", v17, (_DWORD)v16, 1359);
            goto LABEL_8;
          }
          v18 = OpenProcess(*((_DWORD *)Heap + 131) != 0 ? 3152 : 1104, 0, v5);
          *((_QWORD *)Heap + 67) = v18;
          if ( !v18 )
          {
            v19 = GetLastError();
            v7 = 351;
            v8 = "Failed to get process handle [%d]";
            String = v19;
            goto LABEL_6;
          }
          String = BaseReadAppCompatDataForProcess(v18, &v32, 0);
          if ( String )
          {
            v7 = 364;
            v8 = "Failed to read compatibility data [%d]";
            goto LABEL_6;
          }
          if ( !*(_QWORD *)(v32 + 4472) )
          {
            v16 = "Invalid request process [%d]";
            v17 = 377;
            goto LABEL_28;
          }
          v20 = *(_DWORD *)(v32 + 4472);
          CurrentProcess = GetCurrentProcess();
          if ( !DuplicateHandle(*((HANDLE *)Heap + 67), (HANDLE)v20, CurrentProcess, (LPHANDLE)Heap + 68, 0, 0, 2u) )
          {
            v22 = GetLastError();
            v7 = 395;
            v8 = "Failed to get duplicate handle [%d]";
            String = v22;
            goto LABEL_6;
          }
          if ( !OpenProcessToken(*((HANDLE *)Heap + 67), 0xBu, (PHANDLE)Heap + 69) )
          {
            v23 = GetLastError();
            v7 = 407;
            v8 = "Failed to open process token [%d]";
            String = v23;
            goto LABEL_6;
          }
          RtlEnterCriticalSection(&g_CODQueueLock);
          v24 = xmmword_180159848;
          if ( xmmword_180159848 >= *(&xmmword_180159848 + 1) )
          {
            if ( xmmword_180159848 + 1 <= *(&xmmword_180159848 + 1) )
              goto LABEL_53;
            v25 = xmmword_180159858 - 1;
            if ( (unsigned __int64)xmmword_180159858 + xmmword_180159848 < xmmword_180159848 + 1 )
              goto LABEL_53;
            Size = 0;
            if ( ULongLongMult(*(&xmmword_180159848 + 1), (ULONGLONG)*(&g_CODQueue + 1), pullResult) < 0 )
              goto LABEL_53;
            v27 = v26 & ~v25;
            if ( ULongLongMult(v27, (ULONGLONG)*(&g_CODQueue + 1), &Size) < 0 )
              goto LABEL_53;
            if ( *((_QWORD *)&xmmword_180159858 + 1) )
            {
              v29 = RtlReAllocateHeap(g_CODQueue, 0, *((PVOID *)&xmmword_180159858 + 1), Size);
            }
            else
            {
              v28 = RtlAllocateHeap(g_CODQueue, 0, Size);
              v29 = v28;
              if ( v28 )
                memset_0(v28, 0, Size);
            }
            if ( !v29 )
              goto LABEL_53;
            *((_QWORD *)&xmmword_180159858 + 1) = v29;
            *(&xmmword_180159848 + 1) = v27;
          }
          Size = 0;
          if ( ULongLongMult((ULONGLONG)*(&g_CODQueue + 1), v24, &Size) >= 0
            && *((_QWORD *)&xmmword_180159858 + 1) + Size >= *((_QWORD *)&xmmword_180159858 + 1) )
          {
            *(_QWORD *)(*((_QWORD *)&xmmword_180159858 + 1) + Size) = Heap;
            ++xmmword_180159848;
          }
LABEL_53:
          RtlLeaveCriticalSection(&g_CODQueueLock);
          PcaTracePrintf("ComponentOnDemand", 0, v5, "Request,Component,%S,Binary,%S", (const wchar_t *)Heap, v34);
          String = 0;
          goto LABEL_9;
        }
        v11[4] = -1;
        String = 534;
      }
      v7 = 284;
      v8 = "Failed to read suspend process value [%d]";
      goto LABEL_6;
    }
  }
  v7 = 273;
  v8 = "Failed to get process id [%d]";
LABEL_6:
  dwDesiredAccess[0] = String;
  AslLogCallPrintf(1, (unsigned int)"ComponentOnDemandp_AddToQueue", v7, (_DWORD)v8, *(_QWORD *)dwDesiredAccess);
  if ( String || !v5 )
    goto LABEL_8;
LABEL_9:
  if ( v32 )
    BaseFreeAppCompatDataForProcess();
  return String;
}

```

## disassembly

```asm
0x1800a7078  push    rbp
0x1800a707a  push    rbx
0x1800a707b  push    rsi
0x1800a707c  push    rdi
0x1800a707d  push    r12
0x1800a707f  push    r14
0x1800a7081  lea     rbp, [rsp-188h]
0x1800a7089  sub     rsp, 288h
0x1800a7090  mov     rax, cs:__security_cookie
0x1800a7097  xor     rax, rsp
0x1800a709a  mov     [rbp+1B0h+var_40], rax
0x1800a70a1  xor     eax, eax
0x1800a70a3  mov     rsi, rcx
0x1800a70a6  mov     [rsp+2B0h+var_250], ax
0x1800a70ab  mov     r8d, 240h; Size
0x1800a70b1  mov     [rsp+2B0h+var_268], rax
0x1800a70b6  mov     rcx, gs:60h
0x1800a70bf  lea     edx, [rax+8]; Flags
0x1800a70c2  mov     rcx, [rcx+30h]; HeapHandle
0x1800a70c6  call    cs:__imp_RtlAllocateHeap
0x1800a70cc  mov     rdi, rax
0x1800a70cf  test    rax, rax
0x1800a70d2  jnz     short loc_1800A70F5
0x1800a70d4  lea     r9, aOutOfMemory; "Out of memory"
0x1800a70db  mov     r8d, 106h
0x1800a70e1  lea     rdx, aComponentondem_7; "ComponentOnDemandp_AddToQueue"
0x1800a70e8  lea     ecx, [rax+1]
0x1800a70eb  lea     ebx, [rax+0Eh]
0x1800a70ee  call    AslLogCallPrintf
0x1800a70f3  jmp     short loc_1800A7136
0x1800a70f5  mov     rdx, [rsi+70h]
0x1800a70f9  xor     r12d, r12d
0x1800a70fc  mov     rcx, [rdx+20h]
0x1800a7100  cmp     rcx, [rdx+8]
0x1800a7104  jbe     short loc_1800A716F
0x1800a7106  mov     ebx, 0A0h
0x1800a710b  mov     r8d, 111h
0x1800a7111  lea     r9, aFailedToGetPro_0; "Failed to get process id [%d]"
0x1800a7118  mov     ecx, 1
0x1800a711d  lea     rdx, aComponentondem_7; "ComponentOnDemandp_AddToQueue"
0x1800a7124  mov     [rsp+2B0h+dwDesiredAccess], ebx
0x1800a7128  call    AslLogCallPrintf
0x1800a712d  test    ebx, ebx
0x1800a712f  jnz     short loc_1800A7136
0x1800a7131  test    r12d, r12d
0x1800a7134  jnz     short loc_1800A713E
0x1800a7136  mov     rcx, rdi; struct _PCA_COMPONENT_ON_DEMAND_DATA *
0x1800a7139  call    ?ComponentOnDemandp_CleanupCODRequest@@YAXPEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@Z; ComponentOnDemandp_CleanupCODRequest(_PCA_COMPONENT_ON_DEMAND_DATA *)
0x1800a713e  mov     rcx, [rsp+2B0h+var_268]
0x1800a7143  test    rcx, rcx
0x1800a7146  jz      short loc_1800A714E
0x1800a7148  call    cs:__imp_BaseFreeAppCompatDataForProcess
0x1800a714e  mov     eax, ebx
0x1800a7150  mov     rcx, [rbp+1B0h+var_40]
0x1800a7157  xor     rcx, rsp; StackCookie
0x1800a715a  call    __security_check_cookie
0x1800a715f  add     rsp, 288h
0x1800a7166  pop     r14
0x1800a7168  pop     r12
0x1800a716a  pop     rdi
0x1800a716b  pop     rsi
0x1800a716c  pop     rbx
0x1800a716d  pop     rbp
0x1800a716e  retn
0x1800a716f  lea     r8, [rcx+4]
0x1800a7173  cmp     r8, rcx
0x1800a7176  jb      short loc_1800A7106
0x1800a7178  cmp     r8, [rdx+8]
0x1800a717c  ja      short loc_1800A7106
0x1800a717e  mov     rax, [rdx+28h]
0x1800a7182  xor     ebx, ebx
0x1800a7184  mov     r12d, [rcx+rax]
0x1800a7188  mov     [rdx+20h], r8
0x1800a718c  test    r12d, r12d
0x1800a718f  jz      loc_1800A710B
0x1800a7195  mov     rdx, [rsi+70h]
0x1800a7199  mov     rcx, [rdx+20h]
0x1800a719d  cmp     rcx, [rdx+8]
0x1800a71a1  jbe     short loc_1800A71AD
0x1800a71a3  mov     ebx, 0A0h
0x1800a71a8  jmp     loc_1800A7530
0x1800a71ad  lea     rax, [rcx+4]
0x1800a71b1  cmp     rax, rcx
0x1800a71b4  jb      short loc_1800A71A3
0x1800a71b6  cmp     rax, [rdx+8]
0x1800a71ba  ja      short loc_1800A71A3
0x1800a71bc  mov     rax, [rdx+28h]
0x1800a71c0  mov     ecx, [rcx+rax]
0x1800a71c3  mov     [rdi+20Ch], ecx
0x1800a71c9  mov     rax, [rdx+20h]
0x1800a71cd  lea     rcx, [rax+4]
0x1800a71d1  cmp     rcx, rax
0x1800a71d4  jb      loc_1800A7523
0x1800a71da  mov     [rdx+20h], rcx
0x1800a71de  lea     r9, dword_1800FF0F4; unsigned __int16 *
0x1800a71e5  mov     rcx, [rsi+70h]; this
0x1800a71e9  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800a71ee  mov     r8d, 104h; unsigned __int64
0x1800a71f4  call    ?ReadString@RtlMemoryStream@@QEAAKPEAG_KPEBG@Z; RtlMemoryStream::ReadString(ushort *,unsigned __int64,ushort const *)
0x1800a71f9  mov     ebx, eax
0x1800a71fb  test    eax, eax
0x1800a71fd  jz      short loc_1800A7211
0x1800a71ff  mov     r8d, 127h
0x1800a7205  lea     r9, aFailedToReadBi; "Failed to read BinaryName [%d]"
0x1800a720c  jmp     loc_1800A7118
0x1800a7211  lea     r8, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800a7216  mov     rcx, rdi; unsigned __int16 *
0x1800a7219  call    ?ComponentOnDemandp_GetComponentName@@YAKPEAGK0@Z; ComponentOnDemandp_GetComponentName(ushort *,ulong,ushort *)
0x1800a721e  mov     ebx, eax
0x1800a7220  test    eax, eax
0x1800a7222  jz      short loc_1800A7236
0x1800a7224  mov     r8d, 133h
0x1800a722a  lea     r9, aFailedToGetCom; "Failed to get component name [%d]"
0x1800a7231  jmp     loc_1800A7118
0x1800a7236  lea     rbx, [rdi+214h]
0x1800a723d  mov     ecx, r12d; dwProcessId
0x1800a7240  mov     rdx, rbx; pSessionId
0x1800a7243  call    cs:__imp_ProcessIdToSessionId
0x1800a7249  test    eax, eax
0x1800a724b  jnz     short loc_1800A7267
0x1800a724d  call    cs:__imp_GetLastError
0x1800a7253  mov     r8d, 13Dh
0x1800a7259  lea     r9, aFailedToGetSes; "Failed to get session id [%d]"
0x1800a7260  mov     ebx, eax
0x1800a7262  jmp     loc_1800A7118
0x1800a7267  cmp     dword ptr [rbx], 0
0x1800a726a  jnz     short loc_1800A729A
0x1800a726c  lea     r9, aCannotProcessR; "Cannot process requests for session 0 ["...
0x1800a7273  mov     r8d, 147h
0x1800a7279  mov     eax, 54Fh
0x1800a727e  lea     rdx, aComponentondem_7; "ComponentOnDemandp_AddToQueue"
0x1800a7285  mov     ecx, 1
0x1800a728a  mov     [rsp+2B0h+dwDesiredAccess], eax
0x1800a728e  mov     ebx, eax
0x1800a7290  call    AslLogCallPrintf
0x1800a7295  jmp     loc_1800A7136
0x1800a729a  mov     eax, [rdi+20Ch]
0x1800a72a0  mov     r8d, r12d; dwProcessId
0x1800a72a3  neg     eax
0x1800a72a5  sbb     ecx, ecx
0x1800a72a7  xor     edx, edx; bInheritHandle
0x1800a72a9  and     ecx, 800h
0x1800a72af  add     ecx, 450h; dwDesiredAccess
0x1800a72b5  call    cs:__imp_OpenProcess
0x1800a72bb  mov     [rdi+218h], rax
0x1800a72c2  test    rax, rax
0x1800a72c5  jnz     short loc_1800A72E1
0x1800a72c7  call    cs:__imp_GetLastError
0x1800a72cd  mov     r8d, 15Fh
0x1800a72d3  lea     r9, aFailedToGetPro; "Failed to get process handle [%d]"
0x1800a72da  mov     ebx, eax
0x1800a72dc  jmp     loc_1800A7118
0x1800a72e1  xor     r8d, r8d
0x1800a72e4  lea     rdx, [rsp+2B0h+var_268]
0x1800a72e9  mov     rcx, rax
0x1800a72ec  call    cs:__imp_BaseReadAppCompatDataForProcess
0x1800a72f2  mov     ebx, eax
0x1800a72f4  test    eax, eax
0x1800a72f6  jz      short loc_1800A730A
0x1800a72f8  mov     r8d, 16Ch
0x1800a72fe  lea     r9, aFailedToReadCo_1; "Failed to read compatibility data [%d]"
0x1800a7305  jmp     loc_1800A7118
0x1800a730a  mov     rax, [rsp+2B0h+var_268]
0x1800a730f  cmp     qword ptr [rax+1178h], 0
0x1800a7317  jnz     short loc_1800A732B
0x1800a7319  lea     r9, aInvalidRequest; "Invalid request process [%d]"
0x1800a7320  mov     r8d, 179h
0x1800a7326  jmp     loc_1800A7279
0x1800a732b  mov     ebx, [rax+1178h]
0x1800a7331  call    cs:__imp_GetCurrentProcess
0x1800a7337  mov     rcx, [rdi+218h]; hSourceProcessHandle
0x1800a733e  lea     r9, [rdi+220h]; lpTargetHandle
0x1800a7345  mov     [rsp+2B0h+dwOptions], 2; dwOptions
0x1800a734d  mov     r8, rax; hTargetProcessHandle
0x1800a7350  mov     [rsp+2B0h+bInheritHandle], 0; bInheritHandle
0x1800a7358  mov     edx, ebx; hSourceHandle
0x1800a735a  mov     [rsp+2B0h+dwDesiredAccess], 0; dwDesiredAccess
0x1800a7362  call    cs:__imp_DuplicateHandle
0x1800a7368  test    eax, eax
0x1800a736a  jnz     short loc_1800A7386
0x1800a736c  call    cs:__imp_GetLastError
0x1800a7372  mov     r8d, 18Bh
0x1800a7378  lea     r9, aFailedToGetDup; "Failed to get duplicate handle [%d]"
0x1800a737f  mov     ebx, eax
0x1800a7381  jmp     loc_1800A7118
0x1800a7386  mov     rcx, [rdi+218h]; ProcessHandle
0x1800a738d  lea     r8, [rdi+228h]; TokenHandle
0x1800a7394  mov     edx, 0Bh; DesiredAccess
0x1800a7399  call    cs:__imp_OpenProcessToken
0x1800a739f  test    eax, eax
0x1800a73a1  jnz     short loc_1800A73BD
0x1800a73a3  call    cs:__imp_GetLastError
0x1800a73a9  mov     r8d, 197h
0x1800a73af  lea     r9, aFailedToOpenPr; "Failed to open process token [%d]"
0x1800a73b6  mov     ebx, eax
0x1800a73b8  jmp     loc_1800A7118
0x1800a73bd  lea     rcx, ?g_CODQueueLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800a73c4  call    cs:__imp_RtlEnterCriticalSection
0x1800a73ca  mov     rcx, qword ptr cs:xmmword_180159848+8; ullMultiplicand
0x1800a73d1  mov     r14, qword ptr cs:xmmword_180159848
0x1800a73d8  cmp     r14, rcx
0x1800a73db  jb      loc_1800A74A3
0x1800a73e1  lea     rdx, [r14+1]
0x1800a73e5  cmp     rdx, rcx
0x1800a73e8  jbe     loc_1800A74E8
0x1800a73ee  mov     rsi, qword ptr cs:xmmword_180159858
0x1800a73f5  dec     rsi
0x1800a73f8  lea     r9, [rsi+rdx]
0x1800a73fc  cmp     r9, rdx
0x1800a73ff  jb      loc_1800A74E8
0x1800a7405  mov     rdx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplier
0x1800a740c  lea     r8, [rsp+2B0h+pullResult]; pullResult
0x1800a7411  mov     [rsp+2B0h+Size], 0
0x1800a741a  call    ULongLongMult
0x1800a741f  test    eax, eax
0x1800a7421  js      loc_1800A74E8
0x1800a7427  mov     rdx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplier
0x1800a742e  lea     r8, [rsp+2B0h+Size]; pullResult
0x1800a7433  not     rsi
0x1800a7436  and     rsi, r9
0x1800a7439  mov     rcx, rsi; ullMultiplicand
0x1800a743c  call    ULongLongMult
0x1800a7441  test    eax, eax
0x1800a7443  js      loc_1800A74E8
0x1800a7449  mov     r8, qword ptr cs:xmmword_180159858+8; Ptr
0x1800a7450  xor     edx, edx; Flags
0x1800a7452  mov     rcx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A; Heap
0x1800a7459  test    r8, r8
0x1800a745c  jnz     short loc_1800A7482
0x1800a745e  mov     r8, [rsp+2B0h+Size]; Size
0x1800a7463  call    cs:__imp_RtlAllocateHeap
0x1800a7469  mov     rbx, rax
0x1800a746c  test    rax, rax
0x1800a746f  jz      short loc_1800A7490
0x1800a7471  mov     r8, [rsp+2B0h+Size]; Size
0x1800a7476  xor     edx, edx; Val
0x1800a7478  mov     rcx, rax; void *
0x1800a747b  call    memset_0
0x1800a7480  jmp     short loc_1800A7490
0x1800a7482  mov     r9, [rsp+2B0h+Size]; Size
0x1800a7487  call    cs:__imp_RtlReAllocateHeap
0x1800a748d  mov     rbx, rax
0x1800a7490  test    rbx, rbx
0x1800a7493  jz      short loc_1800A74E8
0x1800a7495  mov     qword ptr cs:xmmword_180159858+8, rbx
0x1800a749c  mov     qword ptr cs:xmmword_180159848+8, rsi
0x1800a74a3  mov     rcx, qword ptr cs:?g_CODQueue@@3V?$RtlArray@PEAU_PCA_COMPONENT_ON_DEMAND_DATA@@@@A+8; ullMultiplicand
0x1800a74aa  lea     r8, [rsp+2B0h+Size]; pullResult
0x1800a74af  mov     rdx, r14; ullMultiplier
0x1800a74b2  mov     [rsp+2B0h+Size], 0
0x1800a74bb  call    ULongLongMult
0x1800a74c0  test    eax, eax
0x1800a74c2  js      short loc_1800A74E8
0x1800a74c4  mov     r9, [rsp+2B0h+Size]
0x1800a74c9  add     r9, qword ptr cs:xmmword_180159858+8
0x1800a74d0  cmp     r9, qword ptr cs:xmmword_180159858+8
0x1800a74d7  jb      short loc_1800A74E8
0x1800a74d9  mov     ecx, 1
0x1800a74de  mov     [r9], rdi
0x1800a74e1  add     qword ptr cs:xmmword_180159848, rcx
0x1800a74e8  lea     rcx, ?g_CODQueueLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800a74ef  call    cs:__imp_RtlLeaveCriticalSection
0x1800a74f5  lea     rax, [rsp+2B0h+var_250]
0x1800a74fa  mov     r8d, r12d; unsigned int
0x1800a74fd  mov     qword ptr [rsp+2B0h+bInheritHandle], rax
0x1800a7502  lea     r9, aRequestCompone; "Request,Component,%S,Binary,%S"
0x1800a7509  xor     edx, edx; unsigned int
0x1800a750b  mov     qword ptr [rsp+2B0h+dwDesiredAccess], rdi
0x1800a7510  lea     rcx, aComponentondem_1; "ComponentOnDemand"
0x1800a7517  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800a751c  xor     ebx, ebx
0x1800a751e  jmp     loc_1800A713E
0x1800a7523  mov     qword ptr [rdx+20h], 0FFFFFFFFFFFFFFFFh
0x1800a752b  mov     ebx, 216h
0x1800a7530  mov     r8d, 11Ch
0x1800a7536  lea     r9, aFailedToReadSu; "Failed to read suspend process value [%"...
0x1800a753d  jmp     loc_1800A7118
```
