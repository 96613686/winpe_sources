# CDsmDevice::_DsmNotificationThread(void)

- ea: `0x18000c3b0`
- end: `0x18000ca04`
- name: `?_DsmNotificationThread@CDsmDevice@@AEAAKXZ`
- size: `1620`
- prototype: `__int64 __fastcall(CDsmDevice *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ca10`

## callees

- `0x1800017c0`
- `0x180002570`
- `0x1800092c0`
- `0x180009d20`
- `0x18000c3b0`
- `0x18000cb30`
- `0x18000cd1c`
- `0x18000cd60`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c95f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c95f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000c4a0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000c849`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000c4a0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000c849`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c682`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c9a1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c682`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c9a1`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000c8fd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000c8fd`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000c444`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000c444`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000c59d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000c59d`

## pseudocode

```c
__int64 __fastcall CDsmDevice::_DsmNotificationThread(CDsmDevice *this)
{
  int v2; // ebx
  int v3; // r13d
  bool v4; // r12
  _QWORD *v5; // r15
  DWORD v6; // eax
  RPC_STATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  signed int v10; // ebx
  int v11; // r15d
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v15; // [rsp+44h] [rbp-124h]
  double *v16; // [rsp+50h] [rbp-118h]
  int Reply; // [rsp+58h] [rbp-110h] BYREF
  int v18; // [rsp+5Ch] [rbp-10Ch] BYREF
  __int64 v19; // [rsp+60h] [rbp-108h]
  double *v20; // [rsp+68h] [rbp-100h]
  CDsmDevice *v21; // [rsp+70h] [rbp-F8h]
  _QWORD *v22; // [rsp+78h] [rbp-F0h]
  _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-E8h] BYREF
  __int128 v24; // [rsp+F0h] [rbp-78h] BYREF
  __int128 v25; // [rsp+100h] [rbp-68h]

  v21 = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids);
  v24 = 0;
  v25 = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  if ( RpcAsyncInitializeHandle(&pAsync, 0x70u) )
  {
    v2 = -2147467259;
  }
  else
  {
    pAsync.NotificationType = RpcNotificationTypeEvent;
    pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)*((_QWORD *)this + 10);
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&stru_1800117E0,
      2u,
      0,
      &pAsync,
      DsmRpcNotify_v1_0_c_ifspec,
      *((_QWORD *)this + 13),
      &v24);
    v2 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids, 0);
  }
  v3 = 0;
  v4 = 0;
  v15 = 0;
  v19 = 0;
  v5 = (_QWORD *)((char *)this + 40);
  v16 = (double *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v20 = (double *)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  v22 = (_QWORD *)((char *)this + 56);
  *((_QWORD *)this + 7) = 0x3FF0000000000000LL;
  if ( v2 >= 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids);
  }
  while ( v2 >= 0 )
  {
    v6 = WaitForMultipleObjects(2u, (const HANDLE *)this + 9, 0, 0x32u);
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids);
        Reply = 0;
        v7 = RpcAsyncCompleteCall(&pAsync, &Reply);
        if ( v7 )
        {
          if ( v7 > 0 )
            v10 = (unsigned __int16)v7 | 0x80070000;
          else
            v10 = v7;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              &WPP_78fa114223f63f16ae43484342ae4301_Traceguids,
              (unsigned int)v7);
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 3) + 32LL))(
            *((_QWORD *)this + 3),
            *((_QWORD *)this + 4),
            2);
        }
        else
        {
          v10 = 0;
          if ( (_DWORD)v24 == 3 )
          {
            v11 = HIDWORD(v24);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v9, HIDWORD(v24));
            if ( (double)v11 > *v16 )
              *v16 = (double)v11;
            CDsmDevice::_ReportSetupProgress(this, v4);
          }
          else if ( (_DWORD)v24 == 4 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, DWORD2(v24), v25);
            v15 = DWORD2(v24);
            v19 = v25;
            if ( v3 )
            {
              v4 = 1;
            }
            else
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 32LL))(
                *((_QWORD *)this + 3),
                *((_QWORD *)this + 4),
                DWORD2(v24),
                v25);
              if ( v15 == 1 )
              {
                v3 = 1;
                *v5 = 0;
                *v20 = 0.0;
                *v22 = 0x3FF0000000000000LL;
              }
            }
          }
        }
        if ( v10 < 0 )
          break;
        Ndr64AsyncClientCall(
          (MIDL_STUBLESS_PROXY_INFO *)&stru_1800117E0,
          2u,
          0,
          &pAsync,
          DsmRpcNotify_v1_0_c_ifspec,
          *((_QWORD *)this + 13),
          &v24);
        v2 = 0;
        v5 = (_QWORD *)((char *)this + 40);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids, 0);
      }
      else if ( v6 == 258 )
      {
        if ( v3 == 1 )
        {
          CDsmDevice::_ReportSetupProgress(this, v4);
          if ( v4 && *v20 >= 100.0 )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 3) + 32LL))(
              *((_QWORD *)this + 3),
              *((_QWORD *)this + 4),
              v15,
              v19);
            v4 = 0;
            v3 = 0;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids, v6);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids);
      v12 = RpcAsyncCancelCall(&pAsync, 0);
      v13 = v12;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids, v12);
      if ( !v13 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids);
        WaitForSingleObject(*((HANDLE *)this + 10), 0xFFFFFFFF);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids);
        v18 = 0;
        RpcAsyncCompleteCall(&pAsync, &v18);
      }
      v2 = -2147467260;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_78fa114223f63f16ae43484342ae4301_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000c3b0  mov     rax, rsp
0x18000c3b3  push    rbx
0x18000c3b4  push    rsi
0x18000c3b5  push    r12
0x18000c3b7  push    r13
0x18000c3b9  push    r14
0x18000c3bb  push    r15
0x18000c3bd  sub     rsp, 138h
0x18000c3c4  movaps  xmmword ptr [rax-48h], xmm6
0x18000c3c8  mov     rax, cs:__security_cookie
0x18000c3cf  xor     rax, rsp
0x18000c3d2  mov     [rsp+168h+var_58], rax
0x18000c3da  mov     r14, rcx
0x18000c3dd  mov     [rsp+168h+var_F8], rcx
0x18000c3e2  lea     rsi, WPP_GLOBAL_Control
0x18000c3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3f0  cmp     rcx, rsi
0x18000c3f3  jz      short loc_18000C410
0x18000c3f5  test    byte ptr [rcx+1Ch], 1
0x18000c3f9  jz      short loc_18000C410
0x18000c3fb  mov     edx, 10h
0x18000c400  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c407  mov     rcx, [rcx+10h]
0x18000c40b  call    WPP_SF_
0x18000c410  xorps   xmm0, xmm0
0x18000c413  movups  [rsp+168h+var_78], xmm0
0x18000c41b  movups  [rsp+168h+var_68], xmm0
0x18000c423  mov     ebx, 70h ; 'p'
0x18000c428  mov     r8d, ebx; Size
0x18000c42b  xor     edx, edx; Val
0x18000c42d  lea     rcx, [rsp+168h+pAsync]; void *
0x18000c435  call    memset_0
0x18000c43a  mov     edx, ebx; Size
0x18000c43c  lea     rcx, [rsp+168h+pAsync]; pAsync
0x18000c444  call    cs:__imp_RpcAsyncInitializeHandle
0x18000c44a  test    eax, eax
0x18000c44c  jnz     loc_18000C501
0x18000c452  mov     [rsp+168h+pAsync.NotificationType], 1
0x18000c45d  mov     rax, [r14+50h]
0x18000c461  mov     qword ptr [rsp+168h+pAsync.u], rax
0x18000c469  lea     rax, [rsp+168h+var_78]
0x18000c471  mov     [rsp+168h+var_138], rax
0x18000c476  mov     rax, [r14+68h]
0x18000c47a  mov     [rsp+168h+var_140], rax
0x18000c47f  mov     rax, cs:DsmRpcNotify_v1_0_c_ifspec
0x18000c486  mov     [rsp+168h+var_148], rax
0x18000c48b  lea     r9, [rsp+168h+pAsync]
0x18000c493  xor     r8d, r8d; pReturnValue
0x18000c496  lea     edx, [rbx-6Eh]; nProcNum
0x18000c499  lea     rcx, stru_1800117E0; pProxyInfo
0x18000c4a0  call    cs:__imp_Ndr64AsyncClientCall
0x18000c4a6  xor     eax, eax
0x18000c4a8  mov     [rsp+168h+var_120], eax
0x18000c4ac  jmp     short loc_18000C4BE
0x18000c4ae  mov     [rsp+168h+var_120], eax
0x18000c4b2  lea     rsi, WPP_GLOBAL_Control
0x18000c4b9  mov     r14, [rsp+168h+var_F8]
0x18000c4be  test    eax, eax
0x18000c4c0  jnz     short loc_18000C4C6
0x18000c4c2  xor     ebx, ebx
0x18000c4c4  jmp     short loc_18000C4D5
0x18000c4c6  jg      short loc_18000C4CC
0x18000c4c8  mov     ebx, eax
0x18000c4ca  jmp     short loc_18000C4D5
0x18000c4cc  movzx   ebx, ax
0x18000c4cf  or      ebx, 80070000h
0x18000c4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4dc  cmp     rcx, rsi
0x18000c4df  jz      short loc_18000C506
0x18000c4e1  test    byte ptr [rcx+1Ch], 1
0x18000c4e5  jz      short loc_18000C506
0x18000c4e7  mov     edx, 11h
0x18000c4ec  mov     r9d, eax
0x18000c4ef  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c4f6  mov     rcx, [rcx+10h]
0x18000c4fa  call    WPP_SF_D
0x18000c4ff  jmp     short loc_18000C506
0x18000c501  mov     ebx, 80004005h
0x18000c506  xor     r13d, r13d
0x18000c509  mov     [rsp+168h+var_11C], r13d
0x18000c50e  xor     r12b, r12b
0x18000c511  mov     [rsp+168h+var_128], r12b
0x18000c516  xor     edx, edx
0x18000c518  mov     [rsp+168h+var_124], edx
0x18000c51c  xor     r8d, r8d
0x18000c51f  mov     [rsp+168h+var_108], r8
0x18000c524  lea     r15, [r14+28h]
0x18000c528  mov     [rsp+168h+var_118], r15
0x18000c52d  mov     [r15], rdx
0x18000c530  lea     rax, [r14+30h]
0x18000c534  mov     [rsp+168h+var_100], rax
0x18000c539  mov     [rax], rdx
0x18000c53c  lea     rax, [r14+38h]
0x18000c540  mov     [rsp+168h+var_F0], rax
0x18000c545  mov     rdx, 3FF0000000000000h
0x18000c54f  mov     [rax], rdx
0x18000c552  test    ebx, ebx
0x18000c554  js      short loc_18000C57C
0x18000c556  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c55d  cmp     rcx, rsi
0x18000c560  jz      short loc_18000C57C
0x18000c562  test    byte ptr [rcx+1Ch], 1
0x18000c566  jz      short loc_18000C57C
0x18000c568  lea     edx, [r13+12h]
0x18000c56c  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c573  mov     rcx, [rcx+10h]
0x18000c577  call    WPP_SF_
0x18000c57c  movsd   xmm6, cs:__real@4059000000000000
0x18000c584  test    ebx, ebx
0x18000c586  js      loc_18000C9B1
0x18000c58c  lea     rdx, [r14+48h]; lpHandles
0x18000c590  mov     r9d, 32h ; '2'; dwMilliseconds
0x18000c596  xor     r8d, r8d; bWaitAll
0x18000c599  lea     ecx, [r9-30h]; nCount
0x18000c59d  call    cs:__imp_WaitForMultipleObjects
0x18000c5a3  mov     ecx, eax
0x18000c5a5  test    eax, eax
0x18000c5a7  jz      loc_18000C8CC
0x18000c5ad  sub     ecx, 1
0x18000c5b0  jz      loc_18000C646
0x18000c5b6  cmp     ecx, 101h
0x18000c5bc  jz      short loc_18000C5EA
0x18000c5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5c5  cmp     rcx, rsi
0x18000c5c8  jz      short loc_18000C584
0x18000c5ca  test    byte ptr [rcx+1Ch], 4
0x18000c5ce  jz      short loc_18000C584
0x18000c5d0  mov     edx, 1Ch
0x18000c5d5  mov     r9d, eax
0x18000c5d8  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c5df  mov     rcx, [rcx+10h]
0x18000c5e3  call    WPP_SF_D
0x18000c5e8  jmp     short loc_18000C584
0x18000c5ea  cmp     r13d, 1
0x18000c5ee  jnz     short loc_18000C584
0x18000c5f0  mov     dl, r12b; bool
0x18000c5f3  mov     rcx, r14; this
0x18000c5f6  call    ?_ReportSetupProgress@CDsmDevice@@AEAAJ_N@Z; CDsmDevice::_ReportSetupProgress(bool)
0x18000c5fb  test    r12b, r12b
0x18000c5fe  jz      short loc_18000C584
0x18000c600  mov     rax, [rsp+168h+var_100]
0x18000c605  movsd   xmm0, qword ptr [rax]
0x18000c609  comisd  xmm0, xmm6
0x18000c60d  jb      loc_18000C584
0x18000c613  mov     rcx, [r14+18h]
0x18000c617  mov     rax, [rcx]
0x18000c61a  mov     r9, [rsp+168h+var_108]
0x18000c61f  mov     r8d, [rsp+168h+var_124]
0x18000c624  mov     rdx, [r14+20h]
0x18000c628  mov     rax, [rax+20h]
0x18000c62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c631  xor     r12b, r12b
0x18000c634  mov     [rsp+168h+var_128], r12b
0x18000c639  xor     r13d, r13d
0x18000c63c  mov     [rsp+168h+var_11C], r13d
0x18000c641  jmp     loc_18000C584
0x18000c646  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c64d  cmp     rcx, rsi
0x18000c650  jz      short loc_18000C66D
0x18000c652  test    byte ptr [rcx+1Ch], 1
0x18000c656  jz      short loc_18000C66D
0x18000c658  mov     edx, 17h
0x18000c65d  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c664  mov     rcx, [rcx+10h]
0x18000c668  call    WPP_SF_
0x18000c66d  mov     [rsp+168h+Reply], 0
0x18000c675  lea     rdx, [rsp+168h+Reply]; Reply
0x18000c67a  lea     rcx, [rsp+168h+pAsync]; pAsync
0x18000c682  call    cs:__imp_RpcAsyncCompleteCall
0x18000c688  test    eax, eax
0x18000c68a  jnz     short loc_18000C690
0x18000c68c  xor     ebx, ebx
0x18000c68e  jmp     short loc_18000C6A7
0x18000c690  jg      short loc_18000C696
0x18000c692  mov     ebx, eax
0x18000c694  jmp     short loc_18000C69F
0x18000c696  movzx   ebx, ax
0x18000c699  or      ebx, 80070000h
0x18000c69f  test    ebx, ebx
0x18000c6a1  js      loc_18000C7C4
0x18000c6a7  mov     ecx, dword ptr [rsp+168h+var_78]
0x18000c6ae  sub     ecx, 3
0x18000c6b1  jz      loc_18000C773
0x18000c6b7  cmp     ecx, 1
0x18000c6ba  jnz     loc_18000C809
0x18000c6c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6c7  cmp     rcx, rsi
0x18000c6ca  jz      short loc_18000C6EF
0x18000c6cc  test    byte ptr [rcx+1Ch], 1
0x18000c6d0  jz      short loc_18000C6EF
0x18000c6d2  mov     rax, qword ptr [rsp+168h+var_68]
0x18000c6da  mov     dword ptr [rsp+168h+var_148], eax
0x18000c6de  mov     r9d, dword ptr [rsp+168h+var_78+8]
0x18000c6e6  mov     rcx, [rcx+10h]
0x18000c6ea  call    WPP_SF_dD
0x18000c6ef  mov     edx, dword ptr [rsp+168h+var_78+8]
0x18000c6f6  mov     [rsp+168h+var_124], edx
0x18000c6fa  mov     r8, qword ptr [rsp+168h+var_68]
0x18000c702  mov     [rsp+168h+var_108], r8
0x18000c707  test    r13d, r13d
0x18000c70a  jnz     short loc_18000C766
0x18000c70c  mov     rcx, [r14+18h]
0x18000c710  mov     rax, [rcx]
0x18000c713  mov     r9, r8
0x18000c716  mov     r8d, edx
0x18000c719  mov     rdx, [r14+20h]
0x18000c71d  mov     rax, [rax+20h]
0x18000c721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c726  cmp     [rsp+168h+var_124], 1
0x18000c72b  jnz     loc_18000C809
0x18000c731  mov     r13d, 1
0x18000c737  mov     [rsp+168h+var_11C], r13d
0x18000c73c  mov     qword ptr [r15], 0
0x18000c743  mov     rax, [rsp+168h+var_100]
0x18000c748  mov     qword ptr [rax], 0
0x18000c74f  mov     rax, [rsp+168h+var_F0]
0x18000c754  mov     rcx, 3FF0000000000000h
0x18000c75e  mov     [rax], rcx
0x18000c761  jmp     loc_18000C809
0x18000c766  mov     r12b, 1
0x18000c769  mov     [rsp+168h+var_128], r12b
0x18000c76e  jmp     loc_18000C809
0x18000c773  mov     r15d, dword ptr [rsp+168h+var_78+0Ch]
0x18000c77b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c782  cmp     rcx, rsi
0x18000c785  jz      short loc_18000C79E
0x18000c787  test    byte ptr [rcx+1Ch], 1
0x18000c78b  jz      short loc_18000C79E
0x18000c78d  mov     edx, 19h
0x18000c792  mov     r9d, r15d
0x18000c795  mov     rcx, [rcx+10h]
0x18000c799  call    WPP_SF_d
0x18000c79e  xorps   xmm0, xmm0
0x18000c7a1  cvtsi2sd xmm0, r15
0x18000c7a6  mov     r15, [rsp+168h+var_118]
0x18000c7ab  comisd  xmm0, qword ptr [r15]
0x18000c7b0  jbe     short loc_18000C7B7
0x18000c7b2  movsd   qword ptr [r15], xmm0
0x18000c7b7  mov     dl, r12b; bool
0x18000c7ba  mov     rcx, r14; this
0x18000c7bd  call    ?_ReportSetupProgress@CDsmDevice@@AEAAJ_N@Z; CDsmDevice::_ReportSetupProgress(bool)
0x18000c7c2  jmp     short loc_18000C809
0x18000c7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7cb  cmp     rcx, rsi
0x18000c7ce  jz      short loc_18000C7EE
0x18000c7d0  test    byte ptr [rcx+1Ch], 4
0x18000c7d4  jz      short loc_18000C7EE
0x18000c7d6  mov     edx, 1Ah
0x18000c7db  mov     r9d, eax
0x18000c7de  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c7e5  mov     rcx, [rcx+10h]
0x18000c7e9  call    WPP_SF_D
0x18000c7ee  mov     rcx, [r14+18h]
0x18000c7f2  mov     rax, [rcx]
0x18000c7f5  xor     r9d, r9d
0x18000c7f8  lea     r8d, [r9+2]
0x18000c7fc  mov     rdx, [r14+20h]
0x18000c800  mov     rax, [rax+20h]
0x18000c804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c809  test    ebx, ebx
0x18000c80b  js      loc_18000C9B1
0x18000c811  lea     rax, [rsp+168h+var_78]
0x18000c819  mov     [rsp+168h+var_138], rax
0x18000c81e  mov     rax, [r14+68h]
0x18000c822  mov     [rsp+168h+var_140], rax
0x18000c827  mov     rax, cs:DsmRpcNotify_v1_0_c_ifspec
0x18000c82e  mov     [rsp+168h+var_148], rax
0x18000c833  lea     r9, [rsp+168h+pAsync]
0x18000c83b  xor     r8d, r8d; pReturnValue
0x18000c83e  lea     edx, [r8+2]; nProcNum
0x18000c842  lea     rcx, stru_1800117E0; pProxyInfo
0x18000c849  call    cs:__imp_Ndr64AsyncClientCall
0x18000c84f  xor     eax, eax
0x18000c851  mov     [rsp+168h+var_120], eax
0x18000c855  jmp     short loc_18000C879
0x18000c857  mov     [rsp+168h+var_120], eax
0x18000c85b  lea     rsi, WPP_GLOBAL_Control
0x18000c862  mov     r13d, [rsp+168h+var_11C]
0x18000c867  mov     r12b, [rsp+168h+var_128]
0x18000c86c  movsd   xmm6, cs:__real@4059000000000000
0x18000c874  mov     r14, [rsp+168h+var_F8]
0x18000c879  test    eax, eax
0x18000c87b  jnz     short loc_18000C881
0x18000c87d  xor     ebx, ebx
0x18000c87f  jmp     short loc_18000C890
0x18000c881  jg      short loc_18000C887
0x18000c883  mov     ebx, eax
0x18000c885  jmp     short loc_18000C890
0x18000c887  movzx   ebx, ax
0x18000c88a  or      ebx, 80070000h
0x18000c890  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c897  cmp     rcx, rsi
0x18000c89a  mov     r15, [rsp+168h+var_118]
0x18000c89f  jz      loc_18000C584
0x18000c8a5  test    byte ptr [rcx+1Ch], 1
0x18000c8a9  jz      loc_18000C584
0x18000c8af  mov     edx, 1Bh
0x18000c8b4  mov     r9d, eax
0x18000c8b7  lea     r8, WPP_78fa114223f63f16ae43484342ae4301_Traceguids
0x18000c8be  mov     rcx, [rcx+10h]
  ... truncated ...
```
