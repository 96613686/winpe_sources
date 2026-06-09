# RemoveAndDestroyClientInfo(RPC_CLIENT_INFO *)

- ea: `0x180012f50`
- end: `0x180013177`
- name: `?RemoveAndDestroyClientInfo@@YAXPEAURPC_CLIENT_INFO@@@Z`
- size: `551`
- prototype: `void __fastcall(struct RPC_CLIENT_INFO *lpMem)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180012d50`
- `0x1800aa39c`

## callees

- `0x180011bb0`
- `0x180011c20`
- `0x180012f50`
- `0x1800131b4`
- `0x180019434`
- `0x180031470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012faf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012faf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013054`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013054`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001305a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001305a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012fda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ff3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001306d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012fda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012ff3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001306d`
- `RPCRT4!RpcAsyncAbortCall` at `0x180013124`
- `RPCRT4!RpcAsyncAbortCall` at `0x180013124`

## string_xrefs

- `0x18001308f`: `RemoveAndDestroyClientInfo`
- `0x1800130d1`: `RemoveAndDestroyClientInfo`

## pseudocode

```c
void __fastcall RemoveAndDestroyClientInfo(struct RPC_CLIENT_INFO ***lpMem)
{
  struct RPC_CLIENT_INFO **v2; // rdx
  struct RPC_CLIENT_INFO **v3; // rax
  struct RPC_CLIENT_INFO **v4; // rdi
  struct RPC_CLIENT_INFO *v5; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  unsigned int v8; // eax
  struct _RPC_ASYNC_STATE *v9; // rcx
  HANDLE v10; // rax

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      11,
      WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      "RemoveAndDestroyClientInfo");
  }
  EnterCriticalSection(&stru_18013F4A0);
  v2 = *lpMem;
  if ( (*lpMem)[1] != (struct RPC_CLIENT_INFO *)lpMem || (v3 = lpMem[1], *v3 != (struct RPC_CLIENT_INFO *)lpMem) )
    __fastfail(3u);
  *v3 = (struct RPC_CLIENT_INFO *)v2;
  v2[1] = (struct RPC_CLIENT_INFO *)v3;
  --dword_18013F448;
  LeaveCriticalSection(&stru_18013F4A0);
  v4 = lpMem[9];
  if ( v4 )
  {
    v5 = v4[4];
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap )
        HeapFree(ProcessHeap, 0, v5);
    }
    v7 = GetProcessHeap();
    if ( v7 )
      HeapFree(v7, 0, v4);
  }
  v8 = *((_DWORD *)lpMem + 538);
  lpMem[9] = 0;
  while ( v8 != *((_DWORD *)lpMem + 539) )
  {
    NotificationEngine::FreeNotification((struct _WCM_NOTIFICATION_DATA *)lpMem[v8 + 13]);
    lpMem[*((unsigned int *)lpMem + 538) + 13] = 0;
    v8 = (unsigned __int8)(*((_DWORD *)lpMem + 538) + 1);
    *((_DWORD *)lpMem + 538) = (unsigned __int8)v8;
  }
  v9 = (struct _RPC_ASYNC_STATE *)lpMem[10];
  if ( v9 )
  {
    if ( RpcAsyncAbortCall(v9, 0x4D4u)
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_59cb1c30c417333f98d499625c161da5_Traceguids);
    }
    lpMem[10] = 0;
    lpMem[11] = 0;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, lpMem);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 3));
  v10 = GetProcessHeap();
  if ( v10 )
    HeapFree(v10, 0, lpMem);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_sL(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      14,
      (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      (unsigned int)"RemoveAndDestroyClientInfo",
      0);
  }
}

```

## disassembly

```asm
0x180012f50  push    rbx
0x180012f52  push    rsi
0x180012f53  push    rdi
0x180012f54  push    r15
0x180012f56  sub     rsp, 38h
0x180012f5a  mov     rbx, rcx
0x180012f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f64  lea     r15, WPP_GLOBAL_Control
0x180012f6b  cmp     rcx, r15
0x180012f6e  jnz     loc_1800130B9
0x180012f74  lea     rcx, stru_18013F4A0; lpCriticalSection
0x180012f7b  call    cs:__imp_EnterCriticalSection
0x180012f81  mov     rdx, [rbx]
0x180012f84  cmp     [rdx+8], rbx
0x180012f88  jnz     loc_180013170
0x180012f8e  mov     rax, [rbx+8]
0x180012f92  cmp     [rax], rbx
0x180012f95  jnz     loc_180013170
0x180012f9b  mov     [rax], rdx
0x180012f9e  lea     rcx, stru_18013F4A0; lpCriticalSection
0x180012fa5  mov     [rdx+8], rax
0x180012fa9  dec     cs:dword_18013F448
0x180012faf  call    cs:__imp_LeaveCriticalSection
0x180012fb5  mov     rdi, [rbx+48h]
0x180012fb9  test    rdi, rdi
0x180012fbc  jz      short loc_180012FF9
0x180012fbe  mov     rsi, [rdi+20h]
0x180012fc2  test    rsi, rsi
0x180012fc5  jz      short loc_180012FE0
0x180012fc7  call    cs:__imp_GetProcessHeap
0x180012fcd  test    rax, rax
0x180012fd0  jz      short loc_180012FE0
0x180012fd2  mov     r8, rsi; lpMem
0x180012fd5  xor     edx, edx; dwFlags
0x180012fd7  mov     rcx, rax; hHeap
0x180012fda  call    cs:__imp_HeapFree
0x180012fe0  call    cs:__imp_GetProcessHeap
0x180012fe6  test    rax, rax
0x180012fe9  jz      short loc_180012FF9
0x180012feb  mov     r8, rdi; lpMem
0x180012fee  xor     edx, edx; dwFlags
0x180012ff0  mov     rcx, rax; hHeap
0x180012ff3  call    cs:__imp_HeapFree
0x180012ff9  mov     eax, [rbx+868h]
0x180012fff  mov     qword ptr [rbx+48h], 0
0x180013007  cmp     eax, [rbx+86Ch]
0x18001300d  jnz     loc_1800130EE
0x180013013  mov     rcx, [rbx+50h]; pAsync
0x180013017  test    rcx, rcx
0x18001301a  jnz     loc_18001311F
0x180013020  mov     rcx, cs:WPP_GLOBAL_Control
0x180013027  cmp     rcx, r15
0x18001302a  jz      short loc_180013050
0x18001302c  cmp     byte ptr [rcx+19h], 5
0x180013030  jb      short loc_180013050
0x180013032  test    byte ptr [rcx+1Ch], 1
0x180013036  jz      short loc_180013050
0x180013038  mov     rcx, [rcx+10h]
0x18001303c  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x180013043  mov     edx, 0Dh
0x180013048  mov     r9, rbx
0x18001304b  call    WPP_SF_q
0x180013050  lea     rcx, [rbx+18h]; lpCriticalSection
0x180013054  call    cs:__imp_DeleteCriticalSection
0x18001305a  call    cs:__imp_GetProcessHeap
0x180013060  test    rax, rax
0x180013063  jz      short loc_180013073
0x180013065  mov     r8, rbx; lpMem
0x180013068  xor     edx, edx; dwFlags
0x18001306a  mov     rcx, rax; hHeap
0x18001306d  call    cs:__imp_HeapFree
0x180013073  mov     rcx, cs:WPP_GLOBAL_Control
0x18001307a  cmp     rcx, r15
0x18001307d  jz      short loc_1800130AF
0x18001307f  cmp     byte ptr [rcx+19h], 5
0x180013083  jb      short loc_1800130AF
0x180013085  test    byte ptr [rcx+1Ch], 1
0x180013089  jz      short loc_1800130AF
0x18001308b  mov     rcx, [rcx+10h]
0x18001308f  lea     r9, aRemoveanddestr; "RemoveAndDestroyClientInfo"
0x180013096  mov     edx, 0Eh
0x18001309b  mov     [rsp+58h+var_38], 0
0x1800130a3  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800130aa  call    WPP_SF_sL
0x1800130af  add     rsp, 38h
0x1800130b3  pop     r15
0x1800130b5  pop     rdi
0x1800130b6  pop     rsi
0x1800130b7  pop     rbx
0x1800130b8  retn
0x1800130b9  cmp     byte ptr [rcx+19h], 5
0x1800130bd  jb      loc_180012F74
0x1800130c3  test    byte ptr [rcx+1Ch], 1
0x1800130c7  jz      loc_180012F74
0x1800130cd  mov     rcx, [rcx+10h]
0x1800130d1  lea     r9, aRemoveanddestr; "RemoveAndDestroyClientInfo"
0x1800130d8  mov     edx, 0Bh
0x1800130dd  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800130e4  call    WPP_SF_s
0x1800130e9  jmp     loc_180012F74
0x1800130ee  mov     ecx, eax
0x1800130f0  mov     rcx, [rbx+rcx*8+68h]; lpMem
0x1800130f5  call    ?FreeNotification@NotificationEngine@@SAXPEAU_WCM_NOTIFICATION_DATA@@@Z; NotificationEngine::FreeNotification(_WCM_NOTIFICATION_DATA *)
0x1800130fa  mov     eax, [rbx+868h]
0x180013100  mov     qword ptr [rbx+rax*8+68h], 0
0x180013109  mov     eax, [rbx+868h]
0x18001310f  inc     eax
0x180013111  movzx   eax, al
0x180013114  mov     [rbx+868h], eax
0x18001311a  jmp     loc_180013007
0x18001311f  mov     edx, 4D4h; ExceptionCode
0x180013124  call    cs:__imp_RpcAsyncAbortCall
0x18001312a  test    eax, eax
0x18001312c  jz      short loc_18001315B
0x18001312e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013135  cmp     rcx, r15
0x180013138  jz      short loc_18001315B
0x18001313a  cmp     byte ptr [rcx+19h], 1
0x18001313e  jb      short loc_18001315B
0x180013140  test    byte ptr [rcx+1Ch], 1
0x180013144  jz      short loc_18001315B
0x180013146  mov     rcx, [rcx+10h]
0x18001314a  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x180013151  mov     edx, 0Ch
0x180013156  call    WPP_SF_
0x18001315b  mov     qword ptr [rbx+50h], 0
0x180013163  mov     qword ptr [rbx+58h], 0
0x18001316b  jmp     loc_180013020
0x180013170  mov     ecx, 3
0x180013175  int     29h; Win8: RtlFailFast(ecx)
```
