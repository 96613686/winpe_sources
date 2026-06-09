# WctGetThreadWaitChain(WCT_ENTRY *,ulong,ulong,ulong *,_WAITCHAIN_NODE_INFO *,int *)

- ea: `0x18003e878`
- end: `0x18003ef9f`
- name: `?WctGetThreadWaitChain@@YAKPEAUWCT_ENTRY@@KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z`
- size: `1831`
- prototype: `unsigned int(struct WCT_ENTRY *, unsigned int, unsigned int, unsigned int *, struct _WAITCHAIN_NODE_INFO *, int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003efb0`
- `0x18006c000`

## callees

- `0x18003a670`
- `0x18003df70`
- `0x18003e878`
- `0x18003faec`
- `0x18003fb18`
- `0x18003fcdc`
- `0x18003fd04`
- `0x18006a6d8`
- `0x18006a830`
- `0x18006ae08`
- `0x18006be58`
- `0x18006c63c`
- `0x18007205a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003e943`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003e943`
- `KERNEL32!LocalFree` at `0x18003eea7`
- `KERNEL32!LocalFree` at `0x18003eea7`
- `KERNEL32!GetLastError` at `0x18003ef11`
- `KERNEL32!GetLastError` at `0x18003ef11`
- `KERNEL32!CloseHandle` at `0x18003ece1`
- `KERNEL32!CloseHandle` at `0x18003ed11`
- `KERNEL32!CloseHandle` at `0x18003ee42`
- `KERNEL32!CloseHandle` at `0x18003ee5f`
- `KERNEL32!CloseHandle` at `0x18003ece1`
- `KERNEL32!CloseHandle` at `0x18003ed11`
- `KERNEL32!CloseHandle` at `0x18003ee42`
- `KERNEL32!CloseHandle` at `0x18003ee5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WctGetThreadWaitChain(
        struct WCT_ENTRY *a1,
        char a2,
        DWORD a3,
        unsigned int *a4,
        struct _WAITCHAIN_NODE_INFO *a5,
        int *a6)
{
  __int64 v7; // rbx
  HANDLE v8; // rdi
  __int64 v9; // rcx
  DWORD v10; // eax
  DWORD LastError; // ebx
  unsigned int v12; // edx
  unsigned int v13; // r13d
  int v14; // r14d
  BOOL v15; // r15d
  unsigned int v16; // edi
  struct _SYSTEM_PROCESS_INFORMATION *v17; // r10
  struct _WAITCHAIN_NODE_INFO *v18; // rsi
  _OWORD *v19; // rcx
  _OWORD *v20; // rax
  __int64 v21; // rdx
  unsigned int ThreadInfo; // eax
  DWORD *p_ThreadId; // r8
  struct WCT_ENTRY *v24; // r15
  WCT_OBJECT_STATUS ObjectStatus; // ecx
  unsigned int i; // edx
  struct _WAITCHAIN_NODE_INFO *v27; // rcx
  struct _WAITCHAIN_NODE_INFO *v28; // rsi
  _OWORD *v29; // rcx
  _OWORD *v30; // rax
  __int64 v31; // rdx
  struct _SYSTEM_PROCESS_INFORMATION *v32; // r12
  unsigned int LockInfo; // eax
  unsigned int v34; // edx
  struct _WAITCHAIN_NODE_INFO *v35; // rsi
  int v36; // eax
  int v37; // r11d
  struct _WAITCHAIN_NODE_INFO *v38; // rcx
  __int64 v39; // rcx
  struct _SYSTEM_PROCESS_INFORMATION *hMem; // [rsp+58h] [rbp-B0h]
  unsigned int v42; // [rsp+60h] [rbp-A8h]
  unsigned int v43; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v44; // [rsp+68h] [rbp-A0h]
  HANDLE v45; // [rsp+70h] [rbp-98h]
  struct _SYSTEM_PROCESS_INFORMATION *v46; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v47; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v48; // [rsp+84h] [rbp-84h]
  HANDLE hObject[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v50; // [rsp+98h] [rbp-70h]
  HWND (*v51)(unsigned int); // [rsp+A8h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-58h] BYREF
  int v53; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v54; // [rsp+BCh] [rbp-4Ch]
  _BYTE v55[288]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v56[336]; // [rsp+1F8h] [rbp+F0h] BYREF

  v7 = *a4;
  LODWORD(v44) = *a4;
  v45 = 0;
  v43 = 0;
  memset_0(v55, 0, 0x118u);
  *(_OWORD *)hObject = 0;
  v50 = 0;
  v46 = 0;
  v54 = 0;
  v52 = 0;
  v51 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  v53 = 10;
  *a6 = 0;
  memset_0(a5, 0, 280 * v7);
  v8 = OpenThread(0x48u, 0, a3);
  v45 = v8;
  tlx::file_handle_traits::operator()(v9, 0);
  if ( (unsigned __int64)v8 + 1 <= 1 )
  {
    v16 = 0;
    LastError = GetLastError();
LABEL_89:
    if ( !LastError )
    {
LABEL_90:
      if ( !v16 )
        LastError = 1444;
    }
LABEL_92:
    v8 = v45;
  }
  else
  {
    v10 = WctLoadUser32(&v52, &v51);
    LastError = v10;
    if ( !v10 || v10 == 50 )
    {
      LastError = WctCreateSystemSnapshot(&v46);
      if ( !LastError )
      {
        v12 = 0;
        v42 = 0;
        v13 = 0;
        v14 = 0;
        v15 = 0;
        v47 = a3;
        v16 = 0;
        v17 = v46;
        hMem = v46;
        LastError = 1223;
        while ( 1 )
        {
          if ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 5, 0, 0) == 1 )
            goto LABEL_92;
          LastError = 1223;
          if ( v16 == 16 )
          {
            v24 = a1;
            v32 = hMem;
            goto LABEL_64;
          }
          v48 = v16;
          if ( v14 || v16 >= (unsigned int)v44 )
          {
            v14 = 1;
            memset_0(v56, 0, 0x118u);
            v19 = v55;
            v20 = v56;
            v21 = 2;
            do
            {
              *v19 = *v20;
              v19[1] = v20[1];
              v19[2] = v20[2];
              v19[3] = v20[3];
              v19[4] = v20[4];
              v19[5] = v20[5];
              v19[6] = v20[6];
              v19[7] = v20[7];
              v19 += 8;
              v20 += 8;
              --v21;
            }
            while ( v21 );
            *v19 = *v20;
            *((_QWORD *)v19 + 2) = *((_QWORD *)v20 + 2);
            v18 = (struct _WAITCHAIN_NODE_INFO *)v55;
            v12 = v42;
            v17 = hMem;
          }
          else
          {
            v18 = &a5[v16];
          }
          ++v16;
          if ( v15 )
          {
            v18->ObjectType = WctThreadType;
            v18->ObjectStatus = WctStatusPidOnlyRpcss;
            v18->ThreadObject.ProcessId = v43;
            p_ThreadId = &v18->ThreadObject.ThreadId;
            v18->ThreadObject.ThreadId = 0;
          }
          else
          {
            ThreadInfo = WctGetThreadInfo(a3, v17, v18, (struct _WCT_CLIENT_HANDLE *)hObject);
            v13 = ThreadInfo;
            if ( ThreadInfo )
            {
              if ( v16 <= 2 )
                goto LABEL_66;
              v24 = a1;
              if ( ThreadInfo == 5 )
              {
                v18->ObjectType = WctThreadType;
                v18->ObjectStatus = WctStatusNoAccess;
                v18->ThreadObject.ProcessId = v43;
                v18->ThreadObject.ThreadId = a3;
                v13 = 0;
                goto LABEL_67;
              }
              v35 = a5;
              a5[v16 - 2].ObjectStatus = WctStatusAbandoned;
LABEL_68:
              v32 = hMem;
              goto LABEL_69;
            }
            v12 = v42;
            if ( !v42 )
              v12 = v50;
            v42 = v12;
            p_ThreadId = &v18->ThreadObject.ThreadId;
          }
          v24 = a1;
          if ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 5, 0, 0) == 1 )
            goto LABEL_92;
          ObjectStatus = v18->ObjectStatus;
          if ( ((ObjectStatus - 3) & 0xFFFFFFFD) != 0
            || (a2 & 1) == 0 && (ObjectStatus == WctStatusPidOnlyRpcss || (_DWORD)v50 != v12) )
          {
            goto LABEL_67;
          }
          if ( !v14 )
          {
            for ( i = 0; i < v48; ++i )
            {
              v27 = &a5[i];
              if ( v27->ObjectType == WctThreadType && v27->ThreadObject.ThreadId == *p_ThreadId )
              {
                v36 = WctCompareNode(v27, v18);
                v35 = a5;
                v32 = hMem;
                if ( v36 )
                  *a6 = v37;
                goto LABEL_69;
              }
            }
          }
          if ( v16 == 16 )
            goto LABEL_67;
          if ( v14 || v16 >= (unsigned int)v44 )
          {
            v14 = 1;
            memset_0(v56, 0, 0x118u);
            v29 = v55;
            v30 = v56;
            v31 = 2;
            do
            {
              *v29 = *v30;
              v29[1] = v30[1];
              v29[2] = v30[2];
              v29[3] = v30[3];
              v29[4] = v30[4];
              v29[5] = v30[5];
              v29[6] = v30[6];
              v29[7] = v30[7];
              v29 += 8;
              v30 += 8;
              --v31;
            }
            while ( v31 );
            *v29 = *v30;
            *((_QWORD *)v29 + 2) = *((_QWORD *)v30 + 2);
            v28 = (struct _WAITCHAIN_NODE_INFO *)v55;
          }
          else
          {
            v28 = &a5[v16];
          }
          ++v16;
          v32 = hMem;
          LockInfo = WctGetLockInfo(
                       a1,
                       v42,
                       (struct _WCT_CLIENT_HANDLE *)hObject,
                       (struct _WCT_LOCK_CONTEXT *)&v53,
                       a2,
                       hMem,
                       v51,
                       v28,
                       &v47,
                       &v43);
          v13 = LockInfo;
          if ( LockInfo )
          {
            if ( LockInfo == 1223 )
              goto LABEL_92;
LABEL_64:
            v35 = a5;
LABEL_69:
            if ( hObject[0] )
            {
              CloseHandle(hObject[0]);
              hObject[0] = 0;
            }
            if ( hObject[1] )
            {
              CloseHandle(hObject[1]);
              hObject[1] = 0;
            }
            if ( _InterlockedCompareExchange((volatile signed __int32 *)v24 + 5, 0, 0) == 1 )
              goto LABEL_92;
            if ( v13 && v16 )
              v14 = (unsigned int)v44 < --v16 ? v14 : 0;
            v46 = 0;
            if ( v32 )
              LocalFree(v32);
            LastError = WctCreateSystemSnapshot(&v46);
            if ( LastError )
              goto LABEL_92;
            if ( !v14 )
              *a4 = v16;
            if ( !(unsigned int)WctCheckChain(v46, a4, v35) )
            {
              *a6 = 0;
              goto LABEL_90;
            }
            if ( v14 )
            {
              *a4 = v16;
              LastError = 234;
            }
            if ( v16 == 16 )
            {
              LastError = 565;
              goto LABEL_92;
            }
            goto LABEL_89;
          }
          if ( v28->ObjectStatus != WctStatusOwned )
            goto LABEL_64;
          v15 = v53 == 9;
          a3 = v47;
          if ( !v47 )
          {
            v34 = v43;
            if ( v43 )
            {
              if ( v53 != 9 )
              {
                if ( v16 != 16 )
                {
                  if ( v14 || v16 >= (unsigned int)v44 )
                  {
                    v14 = 1;
                    v38 = (struct _WAITCHAIN_NODE_INFO *)v55;
                    v35 = a5;
                  }
                  else
                  {
                    v35 = a5;
                    v38 = &a5[v16];
                  }
                  ++v16;
                  v38->ObjectType = WctThreadType;
                  v38->ThreadObject.ProcessId = v34;
                  v38->ThreadObject.ThreadId = 0;
                  v38->ObjectStatus = WctStatusPidOnly;
                  v24 = a1;
                  goto LABEL_68;
                }
LABEL_66:
                v24 = a1;
LABEL_67:
                v35 = a5;
                goto LABEL_68;
              }
            }
          }
          v12 = v42;
          v17 = hMem;
          if ( v53 != 9 )
          {
            if ( hObject[0] )
            {
              CloseHandle(hObject[0]);
              hObject[0] = 0;
            }
            v12 = v42;
            v17 = hMem;
            if ( hObject[1] )
            {
              CloseHandle(hObject[1]);
              hObject[1] = 0;
              v12 = v42;
              v17 = hMem;
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, LastError);
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v52);
  utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v46);
  tlx::file_handle_traits::operator()(v39, v8);
  return LastError;
}

```

## disassembly

```asm
0x18003e878  mov     rax, rsp
0x18003e87b  mov     [rax+18h], rbx
0x18003e87f  mov     [rax+20h], r9
0x18003e883  mov     [rax+10h], edx
0x18003e886  mov     [rax+8], rcx
0x18003e88a  push    rbp
0x18003e88b  push    rsi
0x18003e88c  push    rdi
0x18003e88d  push    r12
0x18003e88f  push    r13
0x18003e891  push    r14
0x18003e893  push    r15
0x18003e895  lea     rbp, [rax-248h]
0x18003e89c  sub     rsp, 310h
0x18003e8a3  mov     r12d, r8d
0x18003e8a6  mov     ebx, [r9]
0x18003e8a9  mov     dword ptr [rsp+340h+var_2E0], ebx
0x18003e8ad  xor     r13d, r13d
0x18003e8b0  mov     [rsp+340h+var_2D8], r13
0x18003e8b5  mov     [rsp+340h+var_2E4], r13d
0x18003e8ba  xor     edx, edx; Val
0x18003e8bc  mov     r8d, 118h; Size
0x18003e8c2  lea     rcx, [rbp+240h+var_270]; void *
0x18003e8c6  call    memset_0
0x18003e8cb  xorps   xmm0, xmm0
0x18003e8ce  movups  xmmword ptr [rbp+240h+hObject], xmm0
0x18003e8d2  movups  [rbp+240h+var_2B0], xmm0
0x18003e8d6  mov     [rsp+340h+var_2D0], r13
0x18003e8db  movdqu  [rbp+240h+var_28C], xmm0
0x18003e8e0  mov     [rbp+240h+var_298], r13
0x18003e8e4  mov     [rbp+240h+var_2A0], r13
0x18003e8e8  lea     rax, WPP_GLOBAL_Control
0x18003e8ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8f6  cmp     rcx, rax
0x18003e8f9  jz      short loc_18003E915
0x18003e8fb  test    byte ptr [rcx+1Ch], 4
0x18003e8ff  jz      short loc_18003E915
0x18003e901  lea     edx, [r13+34h]
0x18003e905  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003e90c  mov     rcx, [rcx+10h]
0x18003e910  call    WPP_SF_
0x18003e915  mov     [rbp+240h+var_290], 0Ah
0x18003e91c  mov     rax, [rbp+240h+arg_28]
0x18003e923  mov     [rax], r13d
0x18003e926  imul    r8, rbx, 118h; Size
0x18003e92d  xor     edx, edx; Val
0x18003e92f  mov     rcx, [rbp+240h+arg_20]; void *
0x18003e936  call    memset_0
0x18003e93b  mov     r8d, r12d; dwThreadId
0x18003e93e  xor     edx, edx; bInheritHandle
0x18003e940  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18003e943  call    cs:__imp_OpenThread
0x18003e94a  nop     dword ptr [rax+rax+00h]
0x18003e94f  mov     rdi, rax
0x18003e952  mov     [rsp+340h+var_2D8], rax
0x18003e957  xor     edx, edx
0x18003e959  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003e95e  lea     rcx, [rdi+1]
0x18003e962  cmp     rcx, 1
0x18003e966  jbe     loc_18003EF0E
0x18003e96c  lea     rdx, [rbp+240h+var_2A0]
0x18003e970  lea     rcx, [rbp+240h+var_298]
0x18003e974  call    ?WctLoadUser32@@YAKPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6APEAUHWND__@@K@Z@Z; WctLoadUser32(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,HWND__ * (**)(ulong))
0x18003e979  mov     ebx, eax
0x18003e97b  test    eax, eax
0x18003e97d  jz      short loc_18003E988
0x18003e97f  cmp     eax, 32h ; '2'
0x18003e982  jnz     loc_18003EF32
0x18003e988  lea     rcx, [rsp+340h+var_2D0]
0x18003e98d  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x18003e992  mov     ebx, eax
0x18003e994  test    eax, eax
0x18003e996  jnz     loc_18003EF32
0x18003e99c  xor     edx, edx
0x18003e99e  mov     [rsp+340h+var_2E8], edx
0x18003e9a2  xor     r13d, r13d
0x18003e9a5  xor     r14d, r14d
0x18003e9a8  xor     r15d, r15d
0x18003e9ab  mov     [rsp+340h+var_2C8], r12d
0x18003e9b0  xor     edi, edi
0x18003e9b2  mov     r10, [rsp+340h+var_2D0]
0x18003e9b7  mov     [rsp+340h+hMem], r10
0x18003e9bc  mov     ebx, 4C7h
0x18003e9c1  mov     r11d, 1
0x18003e9c7  xor     ecx, ecx
0x18003e9c9  xor     eax, eax
0x18003e9cb  mov     r8, [rbp+240h+arg_0]
0x18003e9d2  lock cmpxchg [r8+14h], ecx
0x18003e9d8  cmp     eax, r11d
0x18003e9db  jz      loc_18003EF2D
0x18003e9e1  mov     ebx, 4C7h
0x18003e9e6  cmp     edi, 10h
0x18003e9e9  jz      loc_18003EE18
0x18003e9ef  mov     [rsp+340h+var_2C4], edi
0x18003e9f3  test    r14d, r14d
0x18003e9f6  jnz     short loc_18003EA13
0x18003e9f8  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18003e9fc  jnb     short loc_18003EA13
0x18003e9fe  mov     eax, edi
0x18003ea00  imul    rsi, rax, 118h
0x18003ea07  add     rsi, [rbp+240h+arg_20]
0x18003ea0e  jmp     loc_18003EAAD
0x18003ea13  mov     r14d, r11d
0x18003ea16  xor     edx, edx; Val
0x18003ea18  mov     r8d, 118h; Size
0x18003ea1e  lea     rcx, [rbp+240h+var_150]; void *
0x18003ea25  call    memset_0
0x18003ea2a  lea     rcx, [rbp+240h+var_270]
0x18003ea2e  lea     rax, [rbp+240h+var_150]
0x18003ea35  mov     edx, 2
0x18003ea3a  movups  xmm0, xmmword ptr [rax]
0x18003ea3d  movups  xmmword ptr [rcx], xmm0
0x18003ea40  movups  xmm1, xmmword ptr [rax+10h]
0x18003ea44  movups  xmmword ptr [rcx+10h], xmm1
0x18003ea48  movups  xmm0, xmmword ptr [rax+20h]
0x18003ea4c  movups  xmmword ptr [rcx+20h], xmm0
0x18003ea50  movups  xmm1, xmmword ptr [rax+30h]
0x18003ea54  movups  xmmword ptr [rcx+30h], xmm1
0x18003ea58  movups  xmm0, xmmword ptr [rax+40h]
0x18003ea5c  movups  xmmword ptr [rcx+40h], xmm0
0x18003ea60  movups  xmm1, xmmword ptr [rax+50h]
0x18003ea64  movups  xmmword ptr [rcx+50h], xmm1
0x18003ea68  movups  xmm0, xmmword ptr [rax+60h]
0x18003ea6c  movups  xmmword ptr [rcx+60h], xmm0
0x18003ea70  movups  xmm1, xmmword ptr [rax+70h]
0x18003ea74  movups  xmmword ptr [rcx+70h], xmm1
0x18003ea78  lea     rcx, [rcx+80h]
0x18003ea7f  lea     rax, [rax+80h]
0x18003ea86  sub     rdx, 1
0x18003ea8a  jnz     short loc_18003EA3A
0x18003ea8c  movups  xmm0, xmmword ptr [rax]
0x18003ea8f  movups  xmmword ptr [rcx], xmm0
0x18003ea92  mov     rax, [rax+10h]
0x18003ea96  mov     [rcx+10h], rax
0x18003ea9a  lea     rsi, [rbp+240h+var_270]
0x18003ea9e  mov     edx, [rsp+340h+var_2E8]
0x18003eaa2  mov     r10, [rsp+340h+hMem]
0x18003eaa7  mov     r11d, 1
0x18003eaad  add     edi, r11d
0x18003eab0  test    r15d, r15d
0x18003eab3  jnz     short loc_18003EAEA
0x18003eab5  lea     r9, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18003eab9  mov     r8, rsi; struct _WAITCHAIN_NODE_INFO *
0x18003eabc  mov     rdx, r10; struct _SYSTEM_PROCESS_INFORMATION *
0x18003eabf  mov     ecx, r12d; dwThreadId
0x18003eac2  call    ?WctGetThreadInfo@@YAKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_WAITCHAIN_NODE_INFO@@PEAU_WCT_CLIENT_HANDLE@@@Z; WctGetThreadInfo(ulong,_SYSTEM_PROCESS_INFORMATION *,_WAITCHAIN_NODE_INFO *,_WCT_CLIENT_HANDLE *)
0x18003eac7  mov     r13d, eax
0x18003eaca  test    eax, eax
0x18003eacc  jnz     loc_18003ED33
0x18003ead2  mov     edx, [rsp+340h+var_2E8]
0x18003ead6  test    edx, edx
0x18003ead8  cmovz   edx, dword ptr [rbp+240h+var_2B0]
0x18003eadc  mov     [rsp+340h+var_2E8], edx
0x18003eae0  lea     r8, [rsi+0Ch]
0x18003eae4  lea     r11d, [r15+1]
0x18003eae8  jmp     short loc_18003EB09
0x18003eaea  mov     dword ptr [rsi], 8
0x18003eaf0  mov     dword ptr [rsi+4], 5
0x18003eaf7  mov     eax, [rsp+340h+var_2E4]
0x18003eafb  mov     [rsi+8], eax
0x18003eafe  lea     r8, [rsi+0Ch]
0x18003eb02  mov     dword ptr [r8], 0
0x18003eb09  xor     ecx, ecx
0x18003eb0b  xor     eax, eax
0x18003eb0d  mov     r15, [rbp+240h+arg_0]
0x18003eb14  lock cmpxchg [r15+14h], ecx
0x18003eb1a  cmp     eax, r11d
0x18003eb1d  jz      loc_18003EF2D
0x18003eb23  mov     ecx, [rsi+4]
0x18003eb26  lea     eax, [rcx-3]
0x18003eb29  test    eax, 0FFFFFFFDh
0x18003eb2e  jnz     loc_18003EE2D
0x18003eb34  test    byte ptr [rbp+240h+arg_8], r11b
0x18003eb3b  jnz     short loc_18003EB4F
0x18003eb3d  cmp     ecx, 5
0x18003eb40  jz      loc_18003EE2D
0x18003eb46  cmp     dword ptr [rbp+240h+var_2B0], edx
0x18003eb49  jnz     loc_18003EE2D
0x18003eb4f  test    r14d, r14d
0x18003eb52  jnz     short loc_18003EB86
0x18003eb54  xor     edx, edx
0x18003eb56  mov     r9d, [rsp+340h+var_2C4]
0x18003eb5b  cmp     edx, r9d
0x18003eb5e  jnb     short loc_18003EB86
0x18003eb60  mov     eax, edx
0x18003eb62  imul    rcx, rax, 118h
0x18003eb69  add     rcx, [rbp+240h+arg_20]; struct _WAITCHAIN_NODE_INFO *
0x18003eb70  cmp     dword ptr [rcx], 8
0x18003eb73  jnz     short loc_18003EB81
0x18003eb75  mov     eax, [r8]
0x18003eb78  cmp     [rcx+0Ch], eax
0x18003eb7b  jz      loc_18003ED86
0x18003eb81  add     edx, r11d
0x18003eb84  jmp     short loc_18003EB5B
0x18003eb86  cmp     edi, 10h
0x18003eb89  jz      loc_18003EE2D
0x18003eb8f  test    r14d, r14d
0x18003eb92  jnz     short loc_18003EBAF
0x18003eb94  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18003eb98  jnb     short loc_18003EBAF
0x18003eb9a  mov     eax, edi
0x18003eb9c  imul    rsi, rax, 118h
0x18003eba3  add     rsi, [rbp+240h+arg_20]
0x18003ebaa  jmp     loc_18003EC3A
0x18003ebaf  mov     r14d, r11d
0x18003ebb2  xor     edx, edx; Val
0x18003ebb4  mov     r8d, 118h; Size
0x18003ebba  lea     rcx, [rbp+240h+var_150]; void *
0x18003ebc1  call    memset_0
0x18003ebc6  lea     rcx, [rbp+240h+var_270]
0x18003ebca  lea     rax, [rbp+240h+var_150]
0x18003ebd1  mov     edx, 2
0x18003ebd6  lea     r8d, [rdx+7Eh]
0x18003ebda  movups  xmm0, xmmword ptr [rax]
0x18003ebdd  movups  xmmword ptr [rcx], xmm0
0x18003ebe0  movups  xmm1, xmmword ptr [rax+10h]
0x18003ebe4  movups  xmmword ptr [rcx+10h], xmm1
0x18003ebe8  movups  xmm0, xmmword ptr [rax+20h]
0x18003ebec  movups  xmmword ptr [rcx+20h], xmm0
0x18003ebf0  movups  xmm1, xmmword ptr [rax+30h]
0x18003ebf4  movups  xmmword ptr [rcx+30h], xmm1
0x18003ebf8  movups  xmm0, xmmword ptr [rax+40h]
0x18003ebfc  movups  xmmword ptr [rcx+40h], xmm0
0x18003ec00  movups  xmm1, xmmword ptr [rax+50h]
0x18003ec04  movups  xmmword ptr [rcx+50h], xmm1
0x18003ec08  movups  xmm0, xmmword ptr [rax+60h]
0x18003ec0c  movups  xmmword ptr [rcx+60h], xmm0
0x18003ec10  movups  xmm1, xmmword ptr [rax+70h]
0x18003ec14  movups  xmmword ptr [rcx+70h], xmm1
0x18003ec18  add     rcx, r8
0x18003ec1b  add     rax, r8
0x18003ec1e  sub     rdx, 1
0x18003ec22  jnz     short loc_18003EBDA
0x18003ec24  movups  xmm0, xmmword ptr [rax]
0x18003ec27  movups  xmmword ptr [rcx], xmm0
0x18003ec2a  mov     rax, [rax+10h]
0x18003ec2e  mov     [rcx+10h], rax
0x18003ec32  lea     rsi, [rbp+240h+var_270]
0x18003ec36  lea     r11d, [rdx+1]
0x18003ec3a  add     edi, r11d
0x18003ec3d  lea     rax, [rsp+340h+var_2E4]
0x18003ec42  mov     [rsp+340h+var_2F8], rax; unsigned int *
0x18003ec47  lea     rax, [rsp+340h+var_2C8]
0x18003ec4c  mov     [rsp+340h+var_300], rax; unsigned int *
0x18003ec51  mov     [rsp+340h+var_308], rsi; struct _WAITCHAIN_NODE_INFO *
0x18003ec56  mov     rax, [rbp+240h+var_2A0]
0x18003ec5a  mov     [rsp+340h+var_310], rax; HWND (*)(unsigned int)
0x18003ec5f  mov     r12, [rsp+340h+hMem]
0x18003ec64  mov     [rsp+340h+var_318], r12; struct _SYSTEM_PROCESS_INFORMATION *
0x18003ec69  mov     eax, [rbp+240h+arg_8]
0x18003ec6f  mov     [rsp+340h+var_320], eax; unsigned int
0x18003ec73  lea     r9, [rbp+240h+var_290]; struct _WCT_LOCK_CONTEXT *
0x18003ec77  lea     r8, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18003ec7b  mov     edx, [rsp+340h+var_2E8]; unsigned int
0x18003ec7f  mov     rcx, r15; struct WCT_ENTRY *
0x18003ec82  call    ?WctGetLockInfo@@YAKPEAUWCT_ENTRY@@KPEAU_WCT_CLIENT_HANDLE@@PEAU_WCT_LOCK_CONTEXT@@KPEAU_SYSTEM_PROCESS_INFORMATION@@P6APEAUHWND__@@K@ZPEAU_WAITCHAIN_NODE_INFO@@PEAK6@Z; WctGetLockInfo(WCT_ENTRY *,ulong,_WCT_CLIENT_HANDLE *,_WCT_LOCK_CONTEXT *,ulong,_SYSTEM_PROCESS_INFORMATION *,HWND__ * (*)(ulong),_WAITCHAIN_NODE_INFO *,ulong *,ulong *)
0x18003ec87  mov     r13d, eax
0x18003ec8a  test    eax, eax
0x18003ec8c  jnz     loc_18003EE07
0x18003ec92  cmp     dword ptr [rsi+4], 6
0x18003ec96  jnz     loc_18003EE0F
0x18003ec9c  xor     r15d, r15d
0x18003ec9f  cmp     [rbp+240h+var_290], 9
0x18003eca3  lea     r11d, [rax+1]
0x18003eca7  cmovz   r15d, r11d
0x18003ecab  mov     r12d, [rsp+340h+var_2C8]
0x18003ecb0  test    r12d, r12d
0x18003ecb3  jnz     short loc_18003ECC6
0x18003ecb5  mov     edx, [rsp+340h+var_2E4]
0x18003ecb9  test    edx, edx
0x18003ecbb  jz      short loc_18003ECC6
0x18003ecbd  test    r15d, r15d
0x18003ecc0  jz      loc_18003EDB1
0x18003ecc6  test    r15d, r15d
0x18003ecc9  mov     edx, [rsp+340h+var_2E8]
0x18003eccd  mov     r10, [rsp+340h+hMem]
0x18003ecd2  jnz     loc_18003E9C7
0x18003ecd8  mov     rcx, [rbp+240h+hObject]; hObject
0x18003ecdc  test    rcx, rcx
0x18003ecdf  jz      short loc_18003ECFB
0x18003ece1  call    cs:__imp_CloseHandle
0x18003ece8  nop     dword ptr [rax+rax+00h]
0x18003eced  mov     [rbp+240h+hObject], 0
0x18003ecf5  mov     r11d, 1
0x18003ecfb  mov     rcx, [rbp+240h+hObject+8]; hObject
0x18003ecff  test    rcx, rcx
0x18003ed02  mov     edx, [rsp+340h+var_2E8]
0x18003ed06  mov     r10, [rsp+340h+hMem]
0x18003ed0b  jz      loc_18003E9C7
0x18003ed11  call    cs:__imp_CloseHandle
0x18003ed18  nop     dword ptr [rax+rax+00h]
0x18003ed1d  mov     [rbp+240h+hObject+8], 0
0x18003ed25  mov     edx, [rsp+340h+var_2E8]
0x18003ed29  mov     r10, [rsp+340h+hMem]
0x18003ed2e  jmp     loc_18003E9C1
0x18003ed33  cmp     edi, 2
0x18003ed36  jbe     loc_18003EE26
0x18003ed3c  mov     r15, [rbp+240h+arg_0]
0x18003ed43  cmp     eax, 5
0x18003ed46  jnz     short loc_18003ED68
  ... truncated ...
```
