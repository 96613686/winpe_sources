# CloseFaxHandle(_HANDLE_ENTRY *)

- ea: `0x14002c70c`
- end: `0x14002c926`
- name: `?CloseFaxHandle@@YAXPEAU_HANDLE_ENTRY@@@Z`
- size: `538`
- prototype: `void __fastcall(struct _HANDLE_ENTRY *lpMem)`
- caller_count: `12`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400169a0`
- `0x140016a60`
- `0x140016ce0`
- `0x1400170d0`
- `0x140017180`
- `0x140022490`
- `0x140022630`
- `0x1400226c0`
- `0x140022770`
- `0x14002c92c`
- `0x14002cb40`
- `0x140046a7c`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14002c70c`
- `0x140037b14`
- `0x14003da1c`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002c7e3`
- `KERNEL32!GetLastError` at `0x14002c83c`
- `KERNEL32!GetLastError` at `0x14002c881`
- `KERNEL32!GetLastError` at `0x14002c7e3`
- `KERNEL32!GetLastError` at `0x14002c83c`
- `KERNEL32!GetLastError` at `0x14002c881`
- `KERNEL32!CloseHandle` at `0x14002c81a`
- `KERNEL32!CloseHandle` at `0x14002c81a`
- `KERNEL32!FindClose` at `0x14002c7b1`
- `KERNEL32!FindClose` at `0x14002c7b1`
- `KERNEL32!DeleteFileW` at `0x14002c877`
- `KERNEL32!DeleteFileW` at `0x14002c877`
- `KERNEL32!EnterCriticalSection` at `0x14002c75a`
- `KERNEL32!EnterCriticalSection` at `0x14002c8d6`
- `KERNEL32!EnterCriticalSection` at `0x14002c75a`
- `KERNEL32!EnterCriticalSection` at `0x14002c8d6`
- `KERNEL32!LeaveCriticalSection` at `0x14002c8fa`
- `KERNEL32!LeaveCriticalSection` at `0x14002c8fa`
- `KERNEL32!LeaveCriticalSection` at `0x14002c91f`

## pseudocode

```c
void __fastcall CloseFaxHandle(struct _HANDLE_ENTRY *lpMem)
{
  _QWORD *v2; // rax
  __int64 v3; // rcx
  int v4; // eax
  void *v5; // rcx
  DWORD LastError; // eax
  DWORD v7; // eax
  char v8; // al

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids);
  }
  EnterCriticalSection(&g_CsHandleTable);
  v2 = (_QWORD *)*((_QWORD *)lpMem + 1);
  v3 = *(_QWORD *)lpMem;
  *v2 = *(_QWORD *)lpMem;
  *(_QWORD *)(v3 + 8) = v2;
  v4 = *((_DWORD *)lpMem + 6);
  *(_QWORD *)lpMem = 0;
  *((_QWORD *)lpMem + 1) = 0;
  if ( !v4 )
  {
    if ( !*((_DWORD *)lpMem + 11) )
      SafeDecIdleCounter(&g_dwConnectionCount);
    goto LABEL_31;
  }
  if ( v4 == 2 )
  {
    v5 = (void *)*((_QWORD *)lpMem + 7);
    if ( v5 != (void *)-1LL
      && !FindClose(v5)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids, LastError);
    }
    goto LABEL_31;
  }
  if ( v4 != 3 )
    goto LABEL_31;
  if ( !CloseHandle(*((HANDLE *)lpMem + 7))
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids, v7);
  }
  if ( !*((_DWORD *)lpMem + 408) )
    goto LABEL_28;
  if ( *((_DWORD *)lpMem + 407) )
  {
    if ( !DeleteFileW((LPCWSTR)lpMem + 32) )
    {
      v8 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids,
          (_DWORD)lpMem + 64,
          v8);
      }
    }
LABEL_28:
    if ( *((_DWORD *)lpMem + 407) )
      goto LABEL_31;
  }
  if ( *((_QWORD *)lpMem + 205) )
  {
    EnterCriticalSection(&g_CsQueue);
    DecreaseJobRefCount(*((struct _JOB_QUEUE **)lpMem + 205), 1, 1, 1);
    LeaveCriticalSection(&g_CsQueue);
  }
LABEL_31:
  pMemFree(lpMem);
  LeaveCriticalSection(&g_CsHandleTable);
}

```

## disassembly

```asm
0x14002c70c  mov     [rsp+arg_0], rbx
0x14002c711  mov     [rsp+arg_8], rdi
0x14002c716  push    r14
0x14002c718  sub     rsp, 30h
0x14002c71c  mov     rbx, rcx
0x14002c71f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c726  lea     r14, WPP_GLOBAL_Control
0x14002c72d  cmp     rcx, r14
0x14002c730  jz      short loc_14002C753
0x14002c732  test    byte ptr [rcx+1Ch], 4
0x14002c736  jz      short loc_14002C753
0x14002c738  cmp     byte ptr [rcx+19h], 5
0x14002c73c  jb      short loc_14002C753
0x14002c73e  mov     rcx, [rcx+10h]
0x14002c742  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002c749  mov     edx, 14h
0x14002c74e  call    WPP_SF_
0x14002c753  lea     rcx, ?g_CsHandleTable@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002c75a  call    cs:__imp_EnterCriticalSection
0x14002c760  mov     rax, [rbx+8]
0x14002c764  mov     rcx, [rbx]
0x14002c767  mov     [rax], rcx
0x14002c76a  mov     [rcx+8], rax
0x14002c76e  mov     eax, [rbx+18h]
0x14002c771  mov     qword ptr [rbx], 0
0x14002c778  mov     qword ptr [rbx+8], 0
0x14002c780  test    eax, eax
0x14002c782  jnz     short loc_14002C79E
0x14002c784  cmp     [rbx+2Ch], eax
0x14002c787  jnz     loc_14002C900
0x14002c78d  lea     rcx, ?g_dwConnectionCount@@3KA; unsigned int *
0x14002c794  call    ?SafeDecIdleCounter@@YAXPEAK@Z; SafeDecIdleCounter(ulong *)
0x14002c799  jmp     loc_14002C900
0x14002c79e  cmp     eax, 2
0x14002c7a1  jnz     short loc_14002C80D
0x14002c7a3  mov     rcx, [rbx+38h]; hFindFile
0x14002c7a7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002c7ab  jz      loc_14002C900
0x14002c7b1  call    cs:__imp_FindClose
0x14002c7b7  test    eax, eax
0x14002c7b9  jnz     loc_14002C900
0x14002c7bf  mov     rax, cs:WPP_GLOBAL_Control
0x14002c7c6  cmp     rax, r14
0x14002c7c9  jz      loc_14002C900
0x14002c7cf  test    byte ptr [rax+1Ch], 4
0x14002c7d3  jz      loc_14002C900
0x14002c7d9  cmp     byte ptr [rax+19h], 2
0x14002c7dd  jb      loc_14002C900
0x14002c7e3  call    cs:__imp_GetLastError
0x14002c7e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c7f0  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002c7f7  mov     edx, 15h
0x14002c7fc  mov     r9d, eax
0x14002c7ff  mov     rcx, [rcx+10h]
0x14002c803  call    WPP_SF_d
0x14002c808  jmp     loc_14002C900
0x14002c80d  cmp     eax, 3
0x14002c810  jnz     loc_14002C900
0x14002c816  mov     rcx, [rbx+38h]; hObject
0x14002c81a  call    cs:__imp_CloseHandle
0x14002c820  test    eax, eax
0x14002c822  jnz     short loc_14002C861
0x14002c824  mov     rax, cs:WPP_GLOBAL_Control
0x14002c82b  cmp     rax, r14
0x14002c82e  jz      short loc_14002C861
0x14002c830  test    byte ptr [rax+1Ch], 4
0x14002c834  jz      short loc_14002C861
0x14002c836  cmp     byte ptr [rax+19h], 2
0x14002c83a  jb      short loc_14002C861
0x14002c83c  call    cs:__imp_GetLastError
0x14002c842  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c849  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002c850  mov     edx, 16h
0x14002c855  mov     r9d, eax
0x14002c858  mov     rcx, [rcx+10h]
0x14002c85c  call    WPP_SF_d
0x14002c861  cmp     dword ptr [rbx+660h], 0
0x14002c868  jz      short loc_14002C8BC
0x14002c86a  cmp     dword ptr [rbx+65Ch], 0
0x14002c871  jz      short loc_14002C8C5
0x14002c873  lea     rcx, [rbx+40h]; lpFileName
0x14002c877  call    cs:__imp_DeleteFileW
0x14002c87d  test    eax, eax
0x14002c87f  jnz     short loc_14002C8BC
0x14002c881  call    cs:__imp_GetLastError
0x14002c887  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c88e  cmp     rcx, r14
0x14002c891  jz      short loc_14002C8BC
0x14002c893  test    byte ptr [rcx+1Ch], 4
0x14002c897  jz      short loc_14002C8BC
0x14002c899  cmp     byte ptr [rcx+19h], 2
0x14002c89d  jb      short loc_14002C8BC
0x14002c89f  mov     rcx, [rcx+10h]
0x14002c8a3  lea     r9, [rbx+40h]
0x14002c8a7  mov     edx, 17h
0x14002c8ac  mov     [rsp+38h+var_18], eax
0x14002c8b0  lea     r8, WPP_e38c90d1bbc138e818de5cb7090417ec_Traceguids
0x14002c8b7  call    WPP_SF_Sd
0x14002c8bc  cmp     dword ptr [rbx+65Ch], 0
0x14002c8c3  jnz     short loc_14002C900
0x14002c8c5  cmp     qword ptr [rbx+668h], 0
0x14002c8cd  jz      short loc_14002C900
0x14002c8cf  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002c8d6  call    cs:__imp_EnterCriticalSection
0x14002c8dc  mov     rcx, [rbx+668h]; struct _JOB_QUEUE *
0x14002c8e3  mov     edx, 1; int
0x14002c8e8  mov     r9d, edx; int
0x14002c8eb  mov     r8d, edx; int
0x14002c8ee  call    ?DecreaseJobRefCount@@YAXPEAU_JOB_QUEUE@@HHH@Z; DecreaseJobRefCount(_JOB_QUEUE *,int,int,int)
0x14002c8f3  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002c8fa  call    cs:__imp_LeaveCriticalSection
0x14002c900  mov     rcx, rbx; lpMem
0x14002c903  call    pMemFree
0x14002c908  lea     rcx, ?g_CsHandleTable@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsHandleTable
0x14002c90f  mov     rbx, [rsp+38h+arg_0]
0x14002c914  mov     rdi, [rsp+38h+arg_8]
0x14002c919  add     rsp, 30h
0x14002c91d  pop     r14
0x14002c91f  jmp     cs:__imp_LeaveCriticalSection
```
