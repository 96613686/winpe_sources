# WctGetThreadWaitChain(WCT_ENTRY *,ulong,ulong,ulong *,_WAITCHAIN_NODE_INFO *,int *)

- ea: `0x18003a080`
- end: `0x18003a77b`
- name: `?WctGetThreadWaitChain@@YAKPEAUWCT_ENTRY@@KKPEAKPEAU_WAITCHAIN_NODE_INFO@@PEAH@Z`
- size: `1787`
- prototype: `unsigned int(struct WCT_ENTRY *, unsigned int, unsigned int, unsigned int *, struct _WAITCHAIN_NODE_INFO *, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003aa00`
- `0x18005f790`

## callees

- `0x180036430`
- `0x180039c64`
- `0x18003a080`
- `0x18003ac90`
- `0x18003b1f8`
- `0x18003b57c`
- `0x18003b728`
- `0x18003b748`
- `0x18005df7c`
- `0x18005e0d4`
- `0x18005e660`
- `0x18005f5fc`
- `0x18005fd50`
- `0x18006505a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003a14b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003a14b`
- `KERNEL32!LocalFree` at `0x18003a693`
- `KERNEL32!LocalFree` at `0x18003a693`
- `KERNEL32!GetLastError` at `0x18003a6f7`
- `KERNEL32!GetLastError` at `0x18003a6f7`
- `KERNEL32!CloseHandle` at `0x18003a4e5`
- `KERNEL32!CloseHandle` at `0x18003a50f`
- `KERNEL32!CloseHandle` at `0x18003a63a`
- `KERNEL32!CloseHandle` at `0x18003a651`
- `KERNEL32!CloseHandle` at `0x18003a4e5`
- `KERNEL32!CloseHandle` at `0x18003a50f`
- `KERNEL32!CloseHandle` at `0x18003a63a`
- `KERNEL32!CloseHandle` at `0x18003a651`

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
  struct _SYSTEM_PROCESS_INFORMATION *hMem; // [rsp+58h] [rbp-B0h]
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
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
        hMem = v43;
        LastError = 1223;
        while ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 5, 0, 0) != 1 )
        {
          LastError = 1223;
          if ( v15 == 16 )
          {
            v23 = a1;
            v31 = hMem;
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
            v16 = hMem;
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
              v31 = hMem;
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
                v31 = hMem;
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
          v31 = hMem;
          LockInfo = WctGetLockInfo(
                       a1,
                       v40,
                       (struct _WCT_CLIENT_HANDLE *)hObject,
                       (struct _WCT_LOCK_CONTEXT *)&v50,
                       a2,
                       hMem,
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
              LocalFree(v31);
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
          v16 = hMem;
          if ( v50 != 9 )
          {
            if ( hObject[0] )
            {
              CloseHandle(hObject[0]);
              hObject[0] = 0;
            }
            v11 = v40;
            v16 = hMem;
            if ( hObject[1] )
            {
              CloseHandle(hObject[1]);
              hObject[1] = 0;
              v11 = v40;
              v16 = hMem;
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4c32fa7a72a13340317baef891270170_Traceguids, LastError);
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v49);
  utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v43);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v45);
  return LastError;
}

```

## disassembly

```asm
0x18003a080  mov     rax, rsp
0x18003a083  mov     [rax+18h], rbx
0x18003a087  mov     [rax+20h], r9
0x18003a08b  mov     [rax+10h], edx
0x18003a08e  mov     [rax+8], rcx
0x18003a092  push    rbp
0x18003a093  push    rsi
0x18003a094  push    rdi
0x18003a095  push    r12
0x18003a097  push    r13
0x18003a099  push    r14
0x18003a09b  push    r15
0x18003a09d  lea     rbp, [rax-248h]
0x18003a0a4  sub     rsp, 310h
0x18003a0ab  mov     r12d, r8d
0x18003a0ae  mov     ebx, [r9]
0x18003a0b1  mov     dword ptr [rsp+340h+var_2E0], ebx
0x18003a0b5  xor     r13d, r13d
0x18003a0b8  mov     [rsp+340h+var_2C8], r13
0x18003a0bd  mov     [rsp+340h+var_2E4], r13d
0x18003a0c2  xor     edx, edx; Val
0x18003a0c4  mov     r8d, 118h; Size
0x18003a0ca  lea     rcx, [rbp+240h+var_270]; void *
0x18003a0ce  call    memset_0
0x18003a0d3  xorps   xmm0, xmm0
0x18003a0d6  movups  xmmword ptr [rbp+240h+hObject], xmm0
0x18003a0da  movups  [rbp+240h+var_2B0], xmm0
0x18003a0de  mov     [rsp+340h+var_2D8], r13
0x18003a0e3  movdqu  [rbp+240h+var_28C], xmm0
0x18003a0e8  mov     [rbp+240h+var_298], r13
0x18003a0ec  mov     [rbp+240h+var_2A0], r13
0x18003a0f0  lea     rax, WPP_GLOBAL_Control
0x18003a0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0fe  cmp     rcx, rax
0x18003a101  jz      short loc_18003A11D
0x18003a103  test    byte ptr [rcx+1Ch], 4
0x18003a107  jz      short loc_18003A11D
0x18003a109  lea     edx, [r13+34h]
0x18003a10d  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003a114  mov     rcx, [rcx+10h]
0x18003a118  call    WPP_SF_
0x18003a11d  mov     [rbp+240h+var_290], 0Ah
0x18003a124  mov     rax, [rbp+240h+arg_28]
0x18003a12b  mov     [rax], r13d
0x18003a12e  imul    r8, rbx, 118h; Size
0x18003a135  xor     edx, edx; Val
0x18003a137  mov     rcx, [rbp+240h+arg_20]; void *
0x18003a13e  call    memset_0
0x18003a143  mov     r8d, r12d; dwThreadId
0x18003a146  xor     edx, edx; bInheritHandle
0x18003a148  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18003a14b  call    cs:__imp_OpenThread
0x18003a151  mov     rdx, rax
0x18003a154  lea     rcx, [rsp+340h+var_2C8]
0x18003a159  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003a15e  mov     rax, [rsp+340h+var_2C8]
0x18003a163  inc     rax
0x18003a166  cmp     rax, 1
0x18003a16a  jbe     loc_18003A6F4
0x18003a170  lea     rdx, [rbp+240h+var_2A0]
0x18003a174  lea     rcx, [rbp+240h+var_298]
0x18003a178  call    ?WctLoadUser32@@YAKPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6APEAUHWND__@@K@Z@Z; WctLoadUser32(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,HWND__ * (**)(ulong))
0x18003a17d  mov     ebx, eax
0x18003a17f  test    eax, eax
0x18003a181  jz      short loc_18003A18C
0x18003a183  cmp     eax, 32h ; '2'
0x18003a186  jnz     loc_18003A70D
0x18003a18c  lea     rcx, [rsp+340h+var_2D8]
0x18003a191  call    ?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z; WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)
0x18003a196  mov     ebx, eax
0x18003a198  test    eax, eax
0x18003a19a  jnz     loc_18003A70D
0x18003a1a0  xor     edx, edx
0x18003a1a2  mov     [rsp+340h+var_2E8], edx
0x18003a1a6  xor     r13d, r13d
0x18003a1a9  xor     r14d, r14d
0x18003a1ac  xor     r15d, r15d
0x18003a1af  mov     [rsp+340h+var_2D0], r12d
0x18003a1b4  xor     edi, edi
0x18003a1b6  mov     r10, [rsp+340h+var_2D8]
0x18003a1bb  mov     [rsp+340h+hMem], r10
0x18003a1c0  mov     ebx, 4C7h
0x18003a1c5  mov     r11d, 1
0x18003a1cb  xor     ecx, ecx
0x18003a1cd  xor     eax, eax
0x18003a1cf  mov     r8, [rbp+240h+arg_0]
0x18003a1d6  lock cmpxchg [r8+14h], ecx
0x18003a1dc  cmp     eax, r11d
0x18003a1df  jz      loc_18003A70D
0x18003a1e5  mov     ebx, 4C7h
0x18003a1ea  cmp     edi, 10h
0x18003a1ed  jz      loc_18003A610
0x18003a1f3  mov     [rsp+340h+var_2D0+4], edi
0x18003a1f7  test    r14d, r14d
0x18003a1fa  jnz     short loc_18003A217
0x18003a1fc  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18003a200  jnb     short loc_18003A217
0x18003a202  mov     eax, edi
0x18003a204  imul    rsi, rax, 118h
0x18003a20b  add     rsi, [rbp+240h+arg_20]
0x18003a212  jmp     loc_18003A2B1
0x18003a217  mov     r14d, r11d
0x18003a21a  xor     edx, edx; Val
0x18003a21c  mov     r8d, 118h; Size
0x18003a222  lea     rcx, [rbp+240h+var_150]; void *
0x18003a229  call    memset_0
0x18003a22e  lea     rcx, [rbp+240h+var_270]
0x18003a232  lea     rax, [rbp+240h+var_150]
0x18003a239  mov     edx, 2
0x18003a23e  movups  xmm0, xmmword ptr [rax]
0x18003a241  movups  xmmword ptr [rcx], xmm0
0x18003a244  movups  xmm1, xmmword ptr [rax+10h]
0x18003a248  movups  xmmword ptr [rcx+10h], xmm1
0x18003a24c  movups  xmm0, xmmword ptr [rax+20h]
0x18003a250  movups  xmmword ptr [rcx+20h], xmm0
0x18003a254  movups  xmm1, xmmword ptr [rax+30h]
0x18003a258  movups  xmmword ptr [rcx+30h], xmm1
0x18003a25c  movups  xmm0, xmmword ptr [rax+40h]
0x18003a260  movups  xmmword ptr [rcx+40h], xmm0
0x18003a264  movups  xmm1, xmmword ptr [rax+50h]
0x18003a268  movups  xmmword ptr [rcx+50h], xmm1
0x18003a26c  movups  xmm0, xmmword ptr [rax+60h]
0x18003a270  movups  xmmword ptr [rcx+60h], xmm0
0x18003a274  movups  xmm1, xmmword ptr [rax+70h]
0x18003a278  movups  xmmword ptr [rcx+70h], xmm1
0x18003a27c  lea     rcx, [rcx+80h]
0x18003a283  lea     rax, [rax+80h]
0x18003a28a  sub     rdx, 1
0x18003a28e  jnz     short loc_18003A23E
0x18003a290  movups  xmm0, xmmword ptr [rax]
0x18003a293  movups  xmmword ptr [rcx], xmm0
0x18003a296  mov     rax, [rax+10h]
0x18003a29a  mov     [rcx+10h], rax
0x18003a29e  lea     rsi, [rbp+240h+var_270]
0x18003a2a2  mov     edx, [rsp+340h+var_2E8]
0x18003a2a6  mov     r10, [rsp+340h+hMem]
0x18003a2ab  mov     r11d, 1
0x18003a2b1  add     edi, r11d
0x18003a2b4  test    r15d, r15d
0x18003a2b7  jnz     short loc_18003A2EE
0x18003a2b9  lea     r9, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18003a2bd  mov     r8, rsi; struct _WAITCHAIN_NODE_INFO *
0x18003a2c0  mov     rdx, r10; struct _SYSTEM_PROCESS_INFORMATION *
0x18003a2c3  mov     ecx, r12d; dwThreadId
0x18003a2c6  call    ?WctGetThreadInfo@@YAKKPEAU_SYSTEM_PROCESS_INFORMATION@@PEAU_WAITCHAIN_NODE_INFO@@PEAU_WCT_CLIENT_HANDLE@@@Z; WctGetThreadInfo(ulong,_SYSTEM_PROCESS_INFORMATION *,_WAITCHAIN_NODE_INFO *,_WCT_CLIENT_HANDLE *)
0x18003a2cb  mov     r13d, eax
0x18003a2ce  test    eax, eax
0x18003a2d0  jnz     loc_18003A52B
0x18003a2d6  mov     edx, [rsp+340h+var_2E8]
0x18003a2da  test    edx, edx
0x18003a2dc  cmovz   edx, dword ptr [rbp+240h+var_2B0]
0x18003a2e0  mov     [rsp+340h+var_2E8], edx
0x18003a2e4  lea     r8, [rsi+0Ch]
0x18003a2e8  lea     r11d, [r15+1]
0x18003a2ec  jmp     short loc_18003A30D
0x18003a2ee  mov     dword ptr [rsi], 8
0x18003a2f4  mov     dword ptr [rsi+4], 5
0x18003a2fb  mov     eax, [rsp+340h+var_2E4]
0x18003a2ff  mov     [rsi+8], eax
0x18003a302  lea     r8, [rsi+0Ch]
0x18003a306  mov     dword ptr [r8], 0
0x18003a30d  xor     ecx, ecx
0x18003a30f  xor     eax, eax
0x18003a311  mov     r15, [rbp+240h+arg_0]
0x18003a318  lock cmpxchg [r15+14h], ecx
0x18003a31e  cmp     eax, r11d
0x18003a321  jz      loc_18003A70D
0x18003a327  mov     ecx, [rsi+4]
0x18003a32a  lea     eax, [rcx-3]
0x18003a32d  test    eax, 0FFFFFFFDh
0x18003a332  jnz     loc_18003A625
0x18003a338  test    byte ptr [rbp+240h+arg_8], r11b
0x18003a33f  jnz     short loc_18003A353
0x18003a341  cmp     ecx, 5
0x18003a344  jz      loc_18003A625
0x18003a34a  cmp     dword ptr [rbp+240h+var_2B0], edx
0x18003a34d  jnz     loc_18003A625
0x18003a353  test    r14d, r14d
0x18003a356  jnz     short loc_18003A38A
0x18003a358  xor     edx, edx
0x18003a35a  mov     r9d, [rsp+340h+var_2D0+4]
0x18003a35f  cmp     edx, r9d
0x18003a362  jnb     short loc_18003A38A
0x18003a364  mov     eax, edx
0x18003a366  imul    rcx, rax, 118h
0x18003a36d  add     rcx, [rbp+240h+arg_20]; struct _WAITCHAIN_NODE_INFO *
0x18003a374  cmp     dword ptr [rcx], 8
0x18003a377  jnz     short loc_18003A385
0x18003a379  mov     eax, [r8]
0x18003a37c  cmp     [rcx+0Ch], eax
0x18003a37f  jz      loc_18003A57E
0x18003a385  add     edx, r11d
0x18003a388  jmp     short loc_18003A35F
0x18003a38a  cmp     edi, 10h
0x18003a38d  jz      loc_18003A625
0x18003a393  test    r14d, r14d
0x18003a396  jnz     short loc_18003A3B3
0x18003a398  cmp     edi, dword ptr [rsp+340h+var_2E0]
0x18003a39c  jnb     short loc_18003A3B3
0x18003a39e  mov     eax, edi
0x18003a3a0  imul    rsi, rax, 118h
0x18003a3a7  add     rsi, [rbp+240h+arg_20]
0x18003a3ae  jmp     loc_18003A43E
0x18003a3b3  mov     r14d, r11d
0x18003a3b6  xor     edx, edx; Val
0x18003a3b8  mov     r8d, 118h; Size
0x18003a3be  lea     rcx, [rbp+240h+var_150]; void *
0x18003a3c5  call    memset_0
0x18003a3ca  lea     rcx, [rbp+240h+var_270]
0x18003a3ce  lea     rax, [rbp+240h+var_150]
0x18003a3d5  mov     edx, 2
0x18003a3da  lea     r8d, [rdx+7Eh]
0x18003a3de  movups  xmm0, xmmword ptr [rax]
0x18003a3e1  movups  xmmword ptr [rcx], xmm0
0x18003a3e4  movups  xmm1, xmmword ptr [rax+10h]
0x18003a3e8  movups  xmmword ptr [rcx+10h], xmm1
0x18003a3ec  movups  xmm0, xmmword ptr [rax+20h]
0x18003a3f0  movups  xmmword ptr [rcx+20h], xmm0
0x18003a3f4  movups  xmm1, xmmword ptr [rax+30h]
0x18003a3f8  movups  xmmword ptr [rcx+30h], xmm1
0x18003a3fc  movups  xmm0, xmmword ptr [rax+40h]
0x18003a400  movups  xmmword ptr [rcx+40h], xmm0
0x18003a404  movups  xmm1, xmmword ptr [rax+50h]
0x18003a408  movups  xmmword ptr [rcx+50h], xmm1
0x18003a40c  movups  xmm0, xmmword ptr [rax+60h]
0x18003a410  movups  xmmword ptr [rcx+60h], xmm0
0x18003a414  movups  xmm1, xmmword ptr [rax+70h]
0x18003a418  movups  xmmword ptr [rcx+70h], xmm1
0x18003a41c  add     rcx, r8
0x18003a41f  add     rax, r8
0x18003a422  sub     rdx, 1
0x18003a426  jnz     short loc_18003A3DE
0x18003a428  movups  xmm0, xmmword ptr [rax]
0x18003a42b  movups  xmmword ptr [rcx], xmm0
0x18003a42e  mov     rax, [rax+10h]
0x18003a432  mov     [rcx+10h], rax
0x18003a436  lea     rsi, [rbp+240h+var_270]
0x18003a43a  lea     r11d, [rdx+1]
0x18003a43e  add     edi, r11d
0x18003a441  lea     rax, [rsp+340h+var_2E4]
0x18003a446  mov     [rsp+340h+var_2F8], rax; unsigned int *
0x18003a44b  lea     rax, [rsp+340h+var_2D0]
0x18003a450  mov     [rsp+340h+var_300], rax; unsigned int *
0x18003a455  mov     [rsp+340h+var_308], rsi; struct _WAITCHAIN_NODE_INFO *
0x18003a45a  mov     rax, [rbp+240h+var_2A0]
0x18003a45e  mov     [rsp+340h+var_310], rax; HWND (*)(unsigned int)
0x18003a463  mov     r12, [rsp+340h+hMem]
0x18003a468  mov     [rsp+340h+var_318], r12; struct _SYSTEM_PROCESS_INFORMATION *
0x18003a46d  mov     eax, [rbp+240h+arg_8]
0x18003a473  mov     [rsp+340h+var_320], eax; unsigned int
0x18003a477  lea     r9, [rbp+240h+var_290]; struct _WCT_LOCK_CONTEXT *
0x18003a47b  lea     r8, [rbp+240h+hObject]; struct _WCT_CLIENT_HANDLE *
0x18003a47f  mov     edx, [rsp+340h+var_2E8]; unsigned int
0x18003a483  mov     rcx, r15; struct WCT_ENTRY *
0x18003a486  call    ?WctGetLockInfo@@YAKPEAUWCT_ENTRY@@KPEAU_WCT_CLIENT_HANDLE@@PEAU_WCT_LOCK_CONTEXT@@KPEAU_SYSTEM_PROCESS_INFORMATION@@P6APEAUHWND__@@K@ZPEAU_WAITCHAIN_NODE_INFO@@PEAK6@Z; WctGetLockInfo(WCT_ENTRY *,ulong,_WCT_CLIENT_HANDLE *,_WCT_LOCK_CONTEXT *,ulong,_SYSTEM_PROCESS_INFORMATION *,HWND__ * (*)(ulong),_WAITCHAIN_NODE_INFO *,ulong *,ulong *)
0x18003a48b  mov     r13d, eax
0x18003a48e  test    eax, eax
0x18003a490  jnz     loc_18003A5FF
0x18003a496  cmp     dword ptr [rsi+4], 6
0x18003a49a  jnz     loc_18003A607
0x18003a4a0  xor     r15d, r15d
0x18003a4a3  cmp     [rbp+240h+var_290], 9
0x18003a4a7  lea     r11d, [rax+1]
0x18003a4ab  cmovz   r15d, r11d
0x18003a4af  mov     r12d, [rsp+340h+var_2D0]
0x18003a4b4  test    r12d, r12d
0x18003a4b7  jnz     short loc_18003A4CA
0x18003a4b9  mov     edx, [rsp+340h+var_2E4]
0x18003a4bd  test    edx, edx
0x18003a4bf  jz      short loc_18003A4CA
0x18003a4c1  test    r15d, r15d
0x18003a4c4  jz      loc_18003A5A9
0x18003a4ca  test    r15d, r15d
0x18003a4cd  mov     edx, [rsp+340h+var_2E8]
0x18003a4d1  mov     r10, [rsp+340h+hMem]
0x18003a4d6  jnz     loc_18003A1CB
0x18003a4dc  mov     rcx, [rbp+240h+hObject]; hObject
0x18003a4e0  test    rcx, rcx
0x18003a4e3  jz      short loc_18003A4F9
0x18003a4e5  call    cs:__imp_CloseHandle
0x18003a4eb  mov     [rbp+240h+hObject], 0
0x18003a4f3  mov     r11d, 1
0x18003a4f9  mov     rcx, [rbp+240h+hObject+8]; hObject
0x18003a4fd  test    rcx, rcx
0x18003a500  mov     edx, [rsp+340h+var_2E8]
0x18003a504  mov     r10, [rsp+340h+hMem]
0x18003a509  jz      loc_18003A1CB
0x18003a50f  call    cs:__imp_CloseHandle
0x18003a515  mov     [rbp+240h+hObject+8], 0
0x18003a51d  mov     edx, [rsp+340h+var_2E8]
0x18003a521  mov     r10, [rsp+340h+hMem]
0x18003a526  jmp     loc_18003A1C5
0x18003a52b  cmp     edi, 2
0x18003a52e  jbe     loc_18003A61E
0x18003a534  mov     r15, [rbp+240h+arg_0]
0x18003a53b  cmp     eax, 5
0x18003a53e  jnz     short loc_18003A560
0x18003a540  mov     dword ptr [rsi], 8
0x18003a546  mov     dword ptr [rsi+4], 1
0x18003a54d  mov     eax, [rsp+340h+var_2E4]
  ... truncated ...
```
