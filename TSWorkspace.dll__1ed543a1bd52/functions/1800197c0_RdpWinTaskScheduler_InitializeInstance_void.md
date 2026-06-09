# RdpWinTaskScheduler::InitializeInstance(void)

- ea: `0x1800197c0`
- end: `0x1800199e6`
- name: `?InitializeInstance@RdpWinTaskScheduler@@UEAA?AW4_XResult32@@XZ`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18000ec94`
- `0x1800197c0`
- `0x180019fb0`
- `0x18001a008`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001993c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001993c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019986`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800198f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800198f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180019899`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180019899`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18001990b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18001990b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180019958`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180019958`

## pseudocode

```c
__int64 __fastcall RdpWinTaskScheduler::InitializeInstance(__int64 a1)
{
  unsigned int v2; // ebx
  unsigned int ActivityIdPrefix; // eax
  struct _TP_POOL *Threadpool; // rax
  DWORD LastError; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  DWORD v8; // edx
  DWORD v9; // edx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax

  v2 = (**(__int64 (__fastcall ***)(__int64))(a1 + 16))(a1 + 16);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        11,
        WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids,
        ActivityIdPrefix,
        v2,
        v2);
    }
    goto LABEL_28;
  }
  *(_DWORD *)(a1 + 56) = 3;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 116) = 1;
  *(_DWORD *)(a1 + 120) = 72;
  if ( !*(_DWORD *)(a1 + 128) )
  {
LABEL_21:
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *(_QWORD *)(a1 + 48) = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      *(_QWORD *)(a1 + 72) = ThreadpoolCleanupGroup;
      *(_QWORD *)(a1 + 80) = RdpWinTaskScheduler::staticCleanupGroupCancelCallback;
      return v2;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_27;
    }
    LastError = GetLastError();
    v6 = RdpX_GetActivityIdPrefix();
    v7 = 14;
    goto LABEL_26;
  }
  Threadpool = CreateThreadpool(0);
  *(_QWORD *)(a1 + 40) = Threadpool;
  if ( Threadpool )
  {
    v8 = *(_DWORD *)(a1 + 136);
    if ( v8 )
      SetThreadpoolThreadMaximum(Threadpool, v8);
    v9 = *(_DWORD *)(a1 + 132);
    if ( v9 && !SetThreadpoolThreadMinimum(*(PTP_POOL *)(a1 + 40), v9) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
      {
        goto LABEL_27;
      }
      LastError = GetLastError();
      v6 = RdpX_GetActivityIdPrefix();
      v7 = 13;
      goto LABEL_26;
    }
    *(_QWORD *)(a1 + 64) = *(_QWORD *)(a1 + 40);
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
  {
    goto LABEL_27;
  }
  LastError = GetLastError();
  v6 = RdpX_GetActivityIdPrefix();
  v7 = 12;
LABEL_26:
  WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 7), v7, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids, v6, LastError);
LABEL_27:
  v2 = -1;
LABEL_28:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  return v2;
}

```

## disassembly

```asm
0x1800197c0  mov     [rsp+arg_0], rbx
0x1800197c5  push    rdi
0x1800197c6  sub     rsp, 30h
0x1800197ca  mov     rdi, rcx
0x1800197cd  add     rcx, 10h
0x1800197d1  mov     rax, [rcx]
0x1800197d4  mov     rax, [rax]
0x1800197d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197dc  mov     ebx, eax
0x1800197de  test    eax, eax
0x1800197e0  jz      short loc_18001983E
0x1800197e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197e9  lea     rax, WPP_GLOBAL_Control
0x1800197f0  cmp     rcx, rax
0x1800197f3  jz      loc_1800199B9
0x1800197f9  test    byte ptr [rcx+44h], 10h
0x1800197fd  jz      loc_1800199B9
0x180019803  cmp     byte ptr [rcx+41h], 2
0x180019807  jb      loc_1800199B9
0x18001980d  call    RdpX_GetActivityIdPrefix
0x180019812  mov     rcx, cs:WPP_GLOBAL_Control
0x180019819  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x180019820  mov     edx, 0Bh
0x180019825  mov     [rsp+38h+var_10], ebx
0x180019829  mov     r9d, eax
0x18001982c  mov     [rsp+38h+var_18], ebx
0x180019830  mov     rcx, [rcx+38h]
0x180019834  call    WPP_SF_DLD
0x180019839  jmp     loc_1800199B9
0x18001983e  mov     dword ptr [rdi+38h], 3
0x180019845  mov     qword ptr [rdi+40h], 0
0x18001984d  mov     qword ptr [rdi+48h], 0
0x180019855  mov     qword ptr [rdi+50h], 0
0x18001985d  mov     qword ptr [rdi+58h], 0
0x180019865  mov     qword ptr [rdi+60h], 0
0x18001986d  mov     qword ptr [rdi+68h], 0
0x180019875  mov     dword ptr [rdi+70h], 0
0x18001987c  mov     dword ptr [rdi+74h], 1
0x180019883  mov     dword ptr [rdi+78h], 48h ; 'H'
0x18001988a  cmp     dword ptr [rdi+80h], 0
0x180019891  jz      loc_180019958
0x180019897  xor     ecx, ecx; reserved
0x180019899  call    cs:__imp_CreateThreadpool
0x18001989f  mov     [rdi+28h], rax
0x1800198a3  test    rax, rax
0x1800198a6  jnz     short loc_1800198EA
0x1800198a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198af  lea     rax, WPP_GLOBAL_Control
0x1800198b6  cmp     rcx, rax
0x1800198b9  jz      loc_1800199B6
0x1800198bf  test    byte ptr [rcx+44h], 10h
0x1800198c3  jz      loc_1800199B6
0x1800198c9  cmp     byte ptr [rcx+41h], 2
0x1800198cd  jb      loc_1800199B6
0x1800198d3  call    cs:__imp_GetLastError
0x1800198d9  mov     ebx, eax
0x1800198db  call    RdpX_GetActivityIdPrefix
0x1800198e0  mov     edx, 0Ch
0x1800198e5  jmp     loc_180019998
0x1800198ea  mov     edx, [rdi+88h]; cthrdMost
0x1800198f0  test    edx, edx
0x1800198f2  jz      short loc_1800198FD
0x1800198f4  mov     rcx, rax; ptpp
0x1800198f7  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800198fd  mov     edx, [rdi+84h]; cthrdMic
0x180019903  test    edx, edx
0x180019905  jz      short loc_180019950
0x180019907  mov     rcx, [rdi+28h]; ptpp
0x18001990b  call    cs:__imp_SetThreadpoolThreadMinimum
0x180019911  test    eax, eax
0x180019913  jnz     short loc_180019950
0x180019915  mov     rcx, cs:WPP_GLOBAL_Control
0x18001991c  lea     rax, WPP_GLOBAL_Control
0x180019923  cmp     rcx, rax
0x180019926  jz      loc_1800199B6
0x18001992c  test    byte ptr [rcx+44h], 10h
0x180019930  jz      loc_1800199B6
0x180019936  cmp     byte ptr [rcx+41h], 2
0x18001993a  jb      short loc_1800199B6
0x18001993c  call    cs:__imp_GetLastError
0x180019942  mov     ebx, eax
0x180019944  call    RdpX_GetActivityIdPrefix
0x180019949  mov     edx, 0Dh
0x18001994e  jmp     short loc_180019998
0x180019950  mov     rax, [rdi+28h]
0x180019954  mov     [rdi+40h], rax
0x180019958  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001995e  mov     [rdi+30h], rax
0x180019962  test    rax, rax
0x180019965  jnz     short loc_1800199CA
0x180019967  mov     rcx, cs:WPP_GLOBAL_Control
0x18001996e  lea     rax, WPP_GLOBAL_Control
0x180019975  cmp     rcx, rax
0x180019978  jz      short loc_1800199B6
0x18001997a  test    byte ptr [rcx+44h], 10h
0x18001997e  jz      short loc_1800199B6
0x180019980  cmp     byte ptr [rcx+41h], 2
0x180019984  jb      short loc_1800199B6
0x180019986  call    cs:__imp_GetLastError
0x18001998c  mov     ebx, eax
0x18001998e  call    RdpX_GetActivityIdPrefix
0x180019993  mov     edx, 0Eh
0x180019998  mov     rcx, cs:WPP_GLOBAL_Control
0x18001999f  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x1800199a6  mov     r9d, eax
0x1800199a9  mov     [rsp+38h+var_18], ebx
0x1800199ad  mov     rcx, [rcx+38h]
0x1800199b1  call    WPP_SF_Dd
0x1800199b6  or      ebx, 0FFFFFFFFh
0x1800199b9  mov     rax, [rdi]
0x1800199bc  mov     rcx, rdi
0x1800199bf  mov     rax, [rax+20h]
0x1800199c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199c8  jmp     short loc_1800199D9
0x1800199ca  mov     [rdi+48h], rax
0x1800199ce  lea     rax, ?staticCleanupGroupCancelCallback@RdpWinTaskScheduler@@KAXPEAX0@Z; RdpWinTaskScheduler::staticCleanupGroupCancelCallback(void *,void *)
0x1800199d5  mov     [rdi+50h], rax
0x1800199d9  mov     eax, ebx
0x1800199db  mov     rbx, [rsp+38h+arg_0]
0x1800199e0  add     rsp, 30h
0x1800199e4  pop     rdi
0x1800199e5  retn
```
