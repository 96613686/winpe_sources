# WctGetThreadWaitChain(WCT_ENTRY *,ulong,ulong,ulong *,_WAITCHAIN_NODE_INFO *,int *)

- ea: `0x18005e2e8`
- end: `0x18005e9ec`
- name: `?WctGetThreadWaitChain@@YAKPEAUWCT_ENTRY@@KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z`
- size: `1796`
- prototype: `unsigned int(struct WCT_ENTRY *, unsigned int, unsigned int, unsigned int *, struct _WAITCHAIN_NODE_INFO *, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180036d60`
- `0x180036f30`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x18001c650`
- `0x18001fe24`
- `0x1800376a8`
- `0x18004c9d0`
- `0x1800517cc`
- `0x18005cb10`
- `0x18005cc68`
- `0x18005d450`
- `0x18005e154`
- `0x18005e2e8`
- `0x18005f4a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e904`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e904`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005e3b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005e3b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e74d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e74d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8b9`

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
  HANDLE v8; // rax
  DWORD v9; // eax
  DWORD LastError; // ebx
  unsigned int v11; // edx
  unsigned int v12; // r13d
  int v13; // r14d
  BOOL v14; // r15d
  unsigned int v15; // edi
  struct _SYSTEM_PROCESS_INFORMATION *v16; // r10
  struct _WAITCHAIN_NODE_INFO *v17; // rsi
  _OWORD *v18; // rcx
  _OWORD *v19; // rax
  __int64 v20; // rdx
  unsigned int ThreadInfo; // eax
  DWORD *p_ThreadId; // r8
  struct WCT_ENTRY *v23; // r15
  WCT_OBJECT_STATUS ObjectStatus; // ecx
  unsigned int i; // edx
  struct _WAITCHAIN_NODE_INFO *v26; // rcx
  struct _WAITCHAIN_NODE_INFO *v27; // rsi
  _OWORD *v28; // rcx
  _OWORD *v29; // rax
  __int64 v30; // rdx
  struct _SYSTEM_PROCESS_INFORMATION *v31; // r12
  unsigned int LockInfo; // eax
  unsigned int v33; // edx
  struct _WAITCHAIN_NODE_INFO *v34; // rsi
  int v35; // eax
  int v36; // r11d
  struct _WAITCHAIN_NODE_INFO *v37; // rcx
  struct _SYSTEM_PROCESS_INFORMATION *lpMem; // [rsp+58h] [rbp-B0h]
  unsigned int v40; // [rsp+60h] [rbp-A8h]
  unsigned int v41; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v42; // [rsp+68h] [rbp-A0h]
  struct _SYSTEM_PROCESS_INFORMATION *v43; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v44[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v45; // [rsp+80h] [rbp-88h] BYREF
  HANDLE hObject[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v47; // [rsp+98h] [rbp-70h]
  HWND (*v48)(unsigned int); // [rsp+A8h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-58h] BYREF
  int v50; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v51; // [rsp+BCh] [rbp-4Ch]
  _BYTE v52[288]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v53[336]; // [rsp+1F8h] [rbp+F0h] BYREF

  v7 = *a4;
  LODWORD(v42) = *a4;
  v45 = 0;
  v41 = 0;
  memset_0(v52, 0, 0x118u);
  *(_OWORD *)hObject = 0;
  v47 = 0;
  v43 = 0;
  v51 = 0;
  v49 = 0;
  v48 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  v50 = 10;
  *a6 = 0;
  memset_0(a5, 0, 280 * v7);
  v8 = OpenThread(0x48u, 0, a3);
  tlx::unique_any<tlx::file_handle_traits>::reset(&v45, v8);
  if ( v45 == -1 || v45 == 0 )
  {
    v15 = 0;
    LastError = GetLastError();
LABEL_89:
    if ( !LastError )
    {
LABEL_90:
      if ( !v15 )
        LastError = 1444;
    }
  }
  else
  {
    v9 = WctLoadUser32(&v49, &v48);
    LastError = v9;
    if ( !v9 || v9 == 50 )
    {
      LastError = WctCreateSystemSnapshot(&v43);
      if ( !LastError )
      {
        v11 = 0;
        v40 = 0;
        v12 = 0;
        v13 = 0;
        v14 = 0;
        v44[0] = a3;
        v15 = 0;
        v16 = v43;
        lpMem = v43;
        LastError = 1223;
        while ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 5, 0, 0) != 1 )
        {
          LastError = 1223;
          if ( v15 == 16 )
          {
            v23 = a1;
            v31 = lpMem;
            goto LABEL_64;
          }
          v44[1] = v15;
          if ( v13 || v15 >= (unsigned int)v42 )
          {
            v13 = 1;
            memset_0(v53, 0, 0x118u);
            v18 = v52;
            v19 = v53;
            v20 = 2;
            do
            {
              *v18 = *v19;
              v18[1] = v19[1];
              v18[2] = v19[2];
              v18[3] = v19[3];
              v18[4] = v19[4];
              v18[5] = v19[5];
              v18[6] = v19[6];
              v18[7] = v19[7];
              v18 += 8;
              v19 += 8;
              --v20;
            }
            while ( v20 );
            *v18 = *v19;
            *((_QWORD *)v18 + 2) = *((_QWORD *)v19 + 2);
            v17 = (struct _WAITCHAIN_NODE_INFO *)v52;
            v11 = v40;
            v16 = lpMem;
          }
          else
          {
            v17 = &a5[v15];
          }
          ++v15;
          if ( v14 )
          {
            v17->ObjectType = WctThreadType;
            v17->ObjectStatus = WctStatusPidOnlyRpcss;
            v17->ThreadObject.ProcessId = v41;
            p_ThreadId = &v17->ThreadObject.ThreadId;
            v17->ThreadObject.ThreadId = 0;
          }
          else
          {
            ThreadInfo = WctGetThreadInfo(a3, v16, v17, (struct _WCT_CLIENT_HANDLE *)hObject);
            v12 = ThreadInfo;
            if ( ThreadInfo )
            {
              if ( v15 <= 2 )
                goto LABEL_66;
              v23 = a1;
              if ( ThreadInfo == 5 )
              {
                v17->ObjectType = WctThreadType;
                v17->ObjectStatus = WctStatusNoAccess;
                v17->ThreadObject.ProcessId = v41;
                v17->ThreadObject.ThreadId = a3;
                v12 = 0;
                goto LABEL_67;
              }
              v34 = a5;
              a5[v15 - 2].ObjectStatus = WctStatusAbandoned;
LABEL_68:
              v31 = lpMem;
              goto LABEL_69;
            }
            v11 = v40;
            if ( !v40 )
              v11 = v47;
            v40 = v11;
            p_ThreadId = &v17->ThreadObject.ThreadId;
          }
          v23 = a1;
          if ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 5, 0, 0) == 1 )
            break;
          ObjectStatus = v17->ObjectStatus;
          if ( ((ObjectStatus - 3) & 0xFFFFFFFD) != 0
            || (a2 & 1) == 0 && (ObjectStatus == WctStatusPidOnlyRpcss || (_DWORD)v47 != v11) )
          {
            goto LABEL_67;
          }
          if ( !v13 )
          {
            for ( i = 0; i < v44[1]; ++i )
            {
              v26 = &a5[i];
              if ( v26->ObjectType == WctThreadType && v26->ThreadObject.ThreadId == *p_ThreadId )
              {
                v35 = WctCompareNode(v26, v17);
                v34 = a5;
                v31 = lpMem;
                if ( v35 )
                  *a6 = v36;
                goto LABEL_69;
              }
            }
          }
          if ( v15 == 16 )
            goto LABEL_67;
          if ( v13 || v15 >= (unsigned int)v42 )
          {
            v13 = 1;
            memset_0(v53, 0, 0x118u);
            v28 = v52;
            v29 = v53;
            v30 = 2;
            do
            {
              *v28 = *v29;
              v28[1] = v29[1];
              v28[2] = v29[2];
              v28[3] = v29[3];
              v28[4] = v29[4];
              v28[5] = v29[5];
              v28[6] = v29[6];
              v28[7] = v29[7];
              v28 += 8;
              v29 += 8;
              --v30;
            }
            while ( v30 );
            *v28 = *v29;
            *((_QWORD *)v28 + 2) = *((_QWORD *)v29 + 2);
            v27 = (struct _WAITCHAIN_NODE_INFO *)v52;
          }
          else
          {
            v27 = &a5[v15];
          }
          ++v15;
          v31 = lpMem;
          LockInfo = WctGetLockInfo(
                       a1,
                       v40,
                       (struct _WCT_CLIENT_HANDLE *)hObject,
                       (struct _WCT_LOCK_CONTEXT *)&v50,
                       a2,
                       lpMem,
                       v48,
                       v27,
                       v44,
                       &v41);
          v12 = LockInfo;
          if ( LockInfo )
          {
            if ( LockInfo == 1223 )
              break;
LABEL_64:
            v34 = a5;
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
            if ( _InterlockedCompareExchange((volatile signed __int32 *)v23 + 5, 0, 0) == 1 )
              break;
            if ( v12 && v15 )
              v13 = (unsigned int)v42 < --v15 ? v13 : 0;
            v43 = 0;
            if ( v31 )
              HeapFree(g_hWerheap, 0, v31);
            LastError = WctCreateSystemSnapshot(&v43);
            if ( LastError )
              break;
            if ( !v13 )
              *a4 = v15;
            if ( !(unsigned int)WctCheckChain(v43, a4, v34) )
            {
              *a6 = 0;
              goto LABEL_90;
            }
            if ( v13 )
            {
              *a4 = v15;
              LastError = 234;
            }
            if ( v15 == 16 )
            {
              LastError = 565;
              break;
            }
            goto LABEL_89;
          }
          if ( v27->ObjectStatus != WctStatusOwned )
            goto LABEL_64;
          v14 = v50 == 9;
          a3 = v44[0];
          if ( !v44[0] )
          {
            v33 = v41;
            if ( v41 )
            {
              if ( v50 != 9 )
              {
                if ( v15 != 16 )
                {
                  if ( v13 || v15 >= (unsigned int)v42 )
                  {
                    v13 = 1;
                    v37 = (struct _WAITCHAIN_NODE_INFO *)v52;
                    v34 = a5;
                  }
                  else
                  {
                    v34 = a5;
                    v37 = &a5[v15];
                  }
                  ++v15;
                  v37->ObjectType = WctThreadType;
                  v37->ThreadObject.ProcessId = v33;
                  v37->ThreadObject.ThreadId = 0;
                  v37->ObjectStatus = WctStatusPidOnly;
                  v23 = a1;
                  goto LABEL_68;
                }
LABEL_66:
                v23 = a1;
LABEL_67:
                v34 = a5;
                goto LABEL_68;
              }
            }
          }
          v11 = v40;
          v16 = lpMem;
          if ( v50 != 9 )
          {
            if ( hObject[0] )
            {
              CloseHandle(hObject[0]);
              hObject[0] = 0;
            }
            v11 = v40;
            v16 = lpMem;
            if ( hObject[1] )
            {
              CloseHandle(hObject[1]);
              hObject[1] = 0;
              v11 = v40;
              v16 = lpMem;
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, LastError);
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v49);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v43);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v45);
  return LastError;
}

```

## disassembly

```asm
0x18005e2e8  mov     rax, rsp
0x18005e2eb  mov     [rax+18h], rbx
0x18005e2ef  mov     [rax+20h], r9
0x18005e2f3  mov     [rax+10h], edx
0x18005e2f6  mov     [rax+8], rcx
0x18005e2fa  push    rbp
0x18005e2fb  push    rsi
0x18005e2fc  push    rdi
0x18005e2fd  push    r12
0x18005e2ff  push    r13
0x18005e301  push    r14
0x18005e303  push    r15
0x18005e305  lea     rbp, [rax-248h]
0x18005e30c  sub     rsp, 310h
0x18005e313  mov     r12d, r8d
0x18005e316  mov     ebx, [r9]
0x18005e319  mov     dword ptr [rsp+340h+var_2E0], ebx
0x18005e31d  xor     r13d, r13d
0x18005e320  mov     [rsp+340h+var_2C8], r13
0x18005e325  mov     [rsp+340h+var_2E4], r13d
0x18005e32a  xor     edx, edx; Val
0x18005e32c  mov     r8d, 118h; Size
0x18005e332  lea     rcx, [rbp+240h+var_270]; void *
0x18005e336  call    memset_0
0x18005e33b  xorps   xmm0, xmm0
0x18005e33e  movups  xmmword ptr [rbp+240h+hObject], xmm0
0x18005e342  movups  [rbp+240h+var_2B0], xmm0
0x18005e346  mov     [rsp+340h+var_2D8], r13
0x18005e34b  movdqu  [rbp+240h+var_28C], xmm0
0x18005e350  mov     [rbp+240h+var_298], r13
0x18005e354  mov     [rbp+240h+var_2A0], r13
0x18005e358  lea     rax, WPP_GLOBAL_Control
0x18005e35f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e366  cmp     rcx, rax
0x18005e369  jz      short loc_18005E385
0x18005e36b  test    byte ptr [rcx+1Ch], 4
0x18005e36f  jz      short loc_18005E385
0x18005e371  lea     edx, [r13+34h]
0x18005e375  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005e37c  mov     rcx, [rcx+10h]
0x18005e380  call    WPP_SF_
0x18005e385  mov     [rbp+240h+var_290], 0Ah
0x18005e38c  mov     rax, [rbp+240h+arg_28]
0x18005e393  mov     [rax], r13d
0x18005e396  imul    r8, rbx, 118h; Size
0x18005e39d  xor     edx, edx; Val
0x18005e39f  mov     rcx, [rbp+240h+arg_20]; void *
0x18005e3a6  call    memset_0
0x18005e3ab  mov     r8d, r12d; dwThreadId
0x18005e3ae  xor     edx, edx; bInheritHandle
0x18005e3b0  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18005e3b3  call    cs:__imp_OpenThread
0x18005e3b9  mov     rdx, rax
0x18005e3bc  lea     rcx, [rsp+340h+var_2C8]
0x18005e3c1  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005e3c6  mov     rax, [rsp+340h+var_2C8]
0x18005e3cb  inc     rax
0x18005e3ce  cmp     rax, 1
0x18005e3d2  jbe     loc_18005E965
0x18005e3d8  lea     rdx, [rbp+240h+var_2A0]
0x18005e3dc  lea     rcx, [rbp+240h+var_298]
0x18005e3e0  call    ?WctLoadUser32@@YAKPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6APEAUHWND__@@K@Z@Z; WctLoadUser32(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,HWND__ * (**)(ulong))
0x18005e3e5  mov     ebx, eax
0x18005e3e7  test    eax, eax
0x18005e3e9  jz      short loc_18005E3F4
0x18005e3eb  cmp     eax, 32h ; '2'
0x18005e3ee  jnz     loc_18005E97E
0x18005e3f4  lea     rcx, [rsp+340h+var_2D8]
0x18005e3f9  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x18005e3fe  mov     ebx, eax
0x18005e400  test    eax, eax
0x18005e402  jnz     loc_18005E97E
0x18005e408  xor     edx, edx
0x18005e40a  mov     [rsp+340h+var_2E8], edx
0x18005e40e  xor     r13d, r13d
0x18005e411  xor     r14d, r14d
0x18005e414  xor     r15d, r15d
0x18005e417  mov     [rsp+340h+var_2D0], r12d
0x18005e41c  xor     edi, edi
0x18005e41e  mov     r10, [rsp+340h+var_2D8]
0x18005e423  mov     [rsp+340h+lpMem], r10
0x18005e428  mov     ebx, 4C7h
0x18005e42d  mov     r11d, 1
0x18005e433  xor     ecx, ecx
0x18005e435  xor     eax, eax
0x18005e437  mov     r8, [rbp+240h+arg_0]
0x18005e43e  lock cmpxchg [r8+14h], ecx
0x18005e444  cmp     eax, r11d
0x18005e447  jz      loc_18005E97E
0x18005e44d  mov     ebx, 4C7h
0x18005e452  cmp     edi, 10h
0x18005e455  jz      loc_18005E878
0x18005e45b  mov     [rsp+340h+var_2D0+4], edi
0x18005e45f  test    r14d, r14d
0x18005e462  jnz     short loc_18005E47F
0x18005e464  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18005e468  jnb     short loc_18005E47F
0x18005e46a  mov     eax, edi
0x18005e46c  imul    rsi, rax, 118h
0x18005e473  add     rsi, [rbp+240h+arg_20]
0x18005e47a  jmp     loc_18005E519
0x18005e47f  mov     r14d, r11d
0x18005e482  xor     edx, edx; Val
0x18005e484  mov     r8d, 118h; Size
0x18005e48a  lea     rcx, [rbp+240h+var_150]; void *
0x18005e491  call    memset_0
0x18005e496  lea     rcx, [rbp+240h+var_270]
0x18005e49a  lea     rax, [rbp+240h+var_150]
0x18005e4a1  mov     edx, 2
0x18005e4a6  movups  xmm0, xmmword ptr [rax]
0x18005e4a9  movups  xmmword ptr [rcx], xmm0
0x18005e4ac  movups  xmm1, xmmword ptr [rax+10h]
0x18005e4b0  movups  xmmword ptr [rcx+10h], xmm1
0x18005e4b4  movups  xmm0, xmmword ptr [rax+20h]
0x18005e4b8  movups  xmmword ptr [rcx+20h], xmm0
0x18005e4bc  movups  xmm1, xmmword ptr [rax+30h]
0x18005e4c0  movups  xmmword ptr [rcx+30h], xmm1
0x18005e4c4  movups  xmm0, xmmword ptr [rax+40h]
0x18005e4c8  movups  xmmword ptr [rcx+40h], xmm0
0x18005e4cc  movups  xmm1, xmmword ptr [rax+50h]
0x18005e4d0  movups  xmmword ptr [rcx+50h], xmm1
0x18005e4d4  movups  xmm0, xmmword ptr [rax+60h]
0x18005e4d8  movups  xmmword ptr [rcx+60h], xmm0
0x18005e4dc  movups  xmm1, xmmword ptr [rax+70h]
0x18005e4e0  movups  xmmword ptr [rcx+70h], xmm1
0x18005e4e4  lea     rcx, [rcx+80h]
0x18005e4eb  lea     rax, [rax+80h]
0x18005e4f2  sub     rdx, 1
0x18005e4f6  jnz     short loc_18005E4A6
0x18005e4f8  movups  xmm0, xmmword ptr [rax]
0x18005e4fb  movups  xmmword ptr [rcx], xmm0
0x18005e4fe  mov     rax, [rax+10h]
0x18005e502  mov     [rcx+10h], rax
0x18005e506  lea     rsi, [rbp+240h+var_270]
0x18005e50a  mov     edx, [rsp+340h+var_2E8]
0x18005e50e  mov     r10, [rsp+340h+lpMem]
0x18005e513  mov     r11d, 1
0x18005e519  add     edi, r11d
0x18005e51c  test    r15d, r15d
0x18005e51f  jnz     short loc_18005E556
0x18005e521  lea     r9, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18005e525  mov     r8, rsi; struct _WAITCHAIN_NODE_INFO *
0x18005e528  mov     rdx, r10; struct _SYSTEM_PROCESS_INFORMATION *
0x18005e52b  mov     ecx, r12d; dwThreadId
0x18005e52e  call    ?WctGetThreadInfo@@YAKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_WAITCHAIN_NODE_INFO@@PEAU_WCT_CLIENT_HANDLE@@@Z; WctGetThreadInfo(ulong,_SYSTEM_PROCESS_INFORMATION *,_WAITCHAIN_NODE_INFO *,_WCT_CLIENT_HANDLE *)
0x18005e533  mov     r13d, eax
0x18005e536  test    eax, eax
0x18005e538  jnz     loc_18005E793
0x18005e53e  mov     edx, [rsp+340h+var_2E8]
0x18005e542  test    edx, edx
0x18005e544  cmovz   edx, dword ptr [rbp+240h+var_2B0]
0x18005e548  mov     [rsp+340h+var_2E8], edx
0x18005e54c  lea     r8, [rsi+0Ch]
0x18005e550  lea     r11d, [r15+1]
0x18005e554  jmp     short loc_18005E575
0x18005e556  mov     dword ptr [rsi], 8
0x18005e55c  mov     dword ptr [rsi+4], 5
0x18005e563  mov     eax, [rsp+340h+var_2E4]
0x18005e567  mov     [rsi+8], eax
0x18005e56a  lea     r8, [rsi+0Ch]
0x18005e56e  mov     dword ptr [r8], 0
0x18005e575  xor     ecx, ecx
0x18005e577  xor     eax, eax
0x18005e579  mov     r15, [rbp+240h+arg_0]
0x18005e580  lock cmpxchg [r15+14h], ecx
0x18005e586  cmp     eax, r11d
0x18005e589  jz      loc_18005E97E
0x18005e58f  mov     ecx, [rsi+4]
0x18005e592  lea     eax, [rcx-3]
0x18005e595  test    eax, 0FFFFFFFDh
0x18005e59a  jnz     loc_18005E88D
0x18005e5a0  test    byte ptr [rbp+240h+arg_8], r11b
0x18005e5a7  jnz     short loc_18005E5BB
0x18005e5a9  cmp     ecx, 5
0x18005e5ac  jz      loc_18005E88D
0x18005e5b2  cmp     dword ptr [rbp+240h+var_2B0], edx
0x18005e5b5  jnz     loc_18005E88D
0x18005e5bb  test    r14d, r14d
0x18005e5be  jnz     short loc_18005E5F2
0x18005e5c0  xor     edx, edx
0x18005e5c2  mov     r9d, [rsp+340h+var_2D0+4]
0x18005e5c7  cmp     edx, r9d
0x18005e5ca  jnb     short loc_18005E5F2
0x18005e5cc  mov     eax, edx
0x18005e5ce  imul    rcx, rax, 118h
0x18005e5d5  add     rcx, [rbp+240h+arg_20]; struct _WAITCHAIN_NODE_INFO *
0x18005e5dc  cmp     dword ptr [rcx], 8
0x18005e5df  jnz     short loc_18005E5ED
0x18005e5e1  mov     eax, [r8]
0x18005e5e4  cmp     [rcx+0Ch], eax
0x18005e5e7  jz      loc_18005E7E6
0x18005e5ed  add     edx, r11d
0x18005e5f0  jmp     short loc_18005E5C7
0x18005e5f2  cmp     edi, 10h
0x18005e5f5  jz      loc_18005E88D
0x18005e5fb  test    r14d, r14d
0x18005e5fe  jnz     short loc_18005E61B
0x18005e600  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18005e604  jnb     short loc_18005E61B
0x18005e606  mov     eax, edi
0x18005e608  imul    rsi, rax, 118h
0x18005e60f  add     rsi, [rbp+240h+arg_20]
0x18005e616  jmp     loc_18005E6A6
0x18005e61b  mov     r14d, r11d
0x18005e61e  xor     edx, edx; Val
0x18005e620  mov     r8d, 118h; Size
0x18005e626  lea     rcx, [rbp+240h+var_150]; void *
0x18005e62d  call    memset_0
0x18005e632  lea     rcx, [rbp+240h+var_270]
0x18005e636  lea     rax, [rbp+240h+var_150]
0x18005e63d  mov     edx, 2
0x18005e642  lea     r8d, [rdx+7Eh]
0x18005e646  movups  xmm0, xmmword ptr [rax]
0x18005e649  movups  xmmword ptr [rcx], xmm0
0x18005e64c  movups  xmm1, xmmword ptr [rax+10h]
0x18005e650  movups  xmmword ptr [rcx+10h], xmm1
0x18005e654  movups  xmm0, xmmword ptr [rax+20h]
0x18005e658  movups  xmmword ptr [rcx+20h], xmm0
0x18005e65c  movups  xmm1, xmmword ptr [rax+30h]
0x18005e660  movups  xmmword ptr [rcx+30h], xmm1
0x18005e664  movups  xmm0, xmmword ptr [rax+40h]
0x18005e668  movups  xmmword ptr [rcx+40h], xmm0
0x18005e66c  movups  xmm1, xmmword ptr [rax+50h]
0x18005e670  movups  xmmword ptr [rcx+50h], xmm1
0x18005e674  movups  xmm0, xmmword ptr [rax+60h]
0x18005e678  movups  xmmword ptr [rcx+60h], xmm0
0x18005e67c  movups  xmm1, xmmword ptr [rax+70h]
0x18005e680  movups  xmmword ptr [rcx+70h], xmm1
0x18005e684  add     rcx, r8
0x18005e687  add     rax, r8
0x18005e68a  sub     rdx, 1
0x18005e68e  jnz     short loc_18005E646
0x18005e690  movups  xmm0, xmmword ptr [rax]
0x18005e693  movups  xmmword ptr [rcx], xmm0
0x18005e696  mov     rax, [rax+10h]
0x18005e69a  mov     [rcx+10h], rax
0x18005e69e  lea     rsi, [rbp+240h+var_270]
0x18005e6a2  lea     r11d, [rdx+1]
0x18005e6a6  add     edi, r11d
0x18005e6a9  lea     rax, [rsp+340h+var_2E4]
0x18005e6ae  mov     [rsp+340h+var_2F8], rax; unsigned int *
0x18005e6b3  lea     rax, [rsp+340h+var_2D0]
0x18005e6b8  mov     [rsp+340h+var_300], rax; unsigned int *
0x18005e6bd  mov     [rsp+340h+var_308], rsi; struct _WAITCHAIN_NODE_INFO *
0x18005e6c2  mov     rax, [rbp+240h+var_2A0]
0x18005e6c6  mov     [rsp+340h+var_310], rax; HWND (*)(unsigned int)
0x18005e6cb  mov     r12, [rsp+340h+lpMem]
0x18005e6d0  mov     [rsp+340h+var_318], r12; struct _SYSTEM_PROCESS_INFORMATION *
0x18005e6d5  mov     eax, [rbp+240h+arg_8]
0x18005e6db  mov     [rsp+340h+var_320], eax; unsigned int
0x18005e6df  lea     r9, [rbp+240h+var_290]; struct _WCT_LOCK_CONTEXT *
0x18005e6e3  lea     r8, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18005e6e7  mov     edx, [rsp+340h+var_2E8]; unsigned int
0x18005e6eb  mov     rcx, r15; struct WCT_ENTRY *
0x18005e6ee  call    ?WctGetLockInfo@@YAKPEAUWCT_ENTRY@@KPEAU_WCT_CLIENT_HANDLE@@PEAU_WCT_LOCK_CONTEXT@@KPEAU_SYSTEM_PROCESS_INFORMATION@@P6APEAUHWND__@@K@ZPEAU_WAITCHAIN_NODE_INFO@@PEAK6@Z; WctGetLockInfo(WCT_ENTRY *,ulong,_WCT_CLIENT_HANDLE *,_WCT_LOCK_CONTEXT *,ulong,_SYSTEM_PROCESS_INFORMATION *,HWND__ * (*)(ulong),_WAITCHAIN_NODE_INFO *,ulong *,ulong *)
0x18005e6f3  mov     r13d, eax
0x18005e6f6  test    eax, eax
0x18005e6f8  jnz     loc_18005E867
0x18005e6fe  cmp     dword ptr [rsi+4], 6
0x18005e702  jnz     loc_18005E86F
0x18005e708  xor     r15d, r15d
0x18005e70b  cmp     [rbp+240h+var_290], 9
0x18005e70f  lea     r11d, [rax+1]
0x18005e713  cmovz   r15d, r11d
0x18005e717  mov     r12d, [rsp+340h+var_2D0]
0x18005e71c  test    r12d, r12d
0x18005e71f  jnz     short loc_18005E732
0x18005e721  mov     edx, [rsp+340h+var_2E4]
0x18005e725  test    edx, edx
0x18005e727  jz      short loc_18005E732
0x18005e729  test    r15d, r15d
0x18005e72c  jz      loc_18005E811
0x18005e732  test    r15d, r15d
0x18005e735  mov     edx, [rsp+340h+var_2E8]
0x18005e739  mov     r10, [rsp+340h+lpMem]
0x18005e73e  jnz     loc_18005E433
0x18005e744  mov     rcx, [rbp+240h+hObject]; hObject
0x18005e748  test    rcx, rcx
0x18005e74b  jz      short loc_18005E761
0x18005e74d  call    cs:__imp_CloseHandle
0x18005e753  mov     [rbp+240h+hObject], 0
0x18005e75b  mov     r11d, 1
0x18005e761  mov     rcx, [rbp+240h+hObject+8]; hObject
0x18005e765  test    rcx, rcx
0x18005e768  mov     edx, [rsp+340h+var_2E8]
0x18005e76c  mov     r10, [rsp+340h+lpMem]
0x18005e771  jz      loc_18005E433
0x18005e777  call    cs:__imp_CloseHandle
0x18005e77d  mov     [rbp+240h+hObject+8], 0
0x18005e785  mov     edx, [rsp+340h+var_2E8]
0x18005e789  mov     r10, [rsp+340h+lpMem]
0x18005e78e  jmp     loc_18005E42D
0x18005e793  cmp     edi, 2
0x18005e796  jbe     loc_18005E886
0x18005e79c  mov     r15, [rbp+240h+arg_0]
0x18005e7a3  cmp     eax, 5
0x18005e7a6  jnz     short loc_18005E7C8
0x18005e7a8  mov     dword ptr [rsi], 8
0x18005e7ae  mov     dword ptr [rsi+4], 1
0x18005e7b5  mov     eax, [rsp+340h+var_2E4]
  ... truncated ...
```
