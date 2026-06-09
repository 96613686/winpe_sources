# CDownloadManager::OnRequestComplete(_DM_CONTEXT *,ulong,void *,ulong)

- ea: `0x18005c2c8`
- end: `0x18005c71b`
- name: `?OnRequestComplete@CDownloadManager@@IEAAXPEAU_DM_CONTEXT@@KPEAXK@Z`
- size: `1107`
- prototype: `void __fastcall(CDownloadManager *__hidden this, struct _DM_CONTEXT *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005f290`

## callees

- `0x18000b1d8`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18000ece0`
- `0x18005c2c8`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c33c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c3fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c4c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c652`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c33c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c3fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c4c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c652`

## string_xrefs

- `0x18005c49e`: `Dispatch async call HttpReadDataSuccess failed`

## pseudocode

```c
void __fastcall CDownloadManager::OnRequestComplete(
        CDownloadManager *this,
        struct _DM_CONTEXT *a2,
        int a3,
        _DWORD *a4,
        unsigned int a5)
{
  DWORD v8; // ebx
  unsigned int v9; // eax
  int v10; // ebx
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  DWORD v14; // ebx
  unsigned int v15; // eax
  DWORD v16; // ebx
  unsigned int v17; // eax
  DWORD v18; // ebx
  unsigned int v19; // eax
  DWORD CurrentThreadId; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v22; // [rsp+28h] [rbp-40h]

  switch ( a3 )
  {
    case 0x4000:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        CurrentThreadId = GetCurrentThreadId();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
          CurrentThreadActivityIdPrefix,
          CurrentThreadId);
      }
      std::wstring::assign((char *)a2 + 200, a4);
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, struct _DM_CONTEXT *, int))(**((_QWORD **)this + 17)
                                                                                                 + 144LL))(
              *((_QWORD *)this + 17),
              (char *)this + 112,
              0,
              0,
              a2,
              1);
      if ( v10 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 68;
        v13 = "Dispatch async call HttpRedirectPending failed";
        goto LABEL_51;
      }
      break;
    case 0x20000:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v18 = GetCurrentThreadId();
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v19, v18);
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, struct _DM_CONTEXT *, int))(**((_QWORD **)this + 17)
                                                                                                 + 144LL))(
              *((_QWORD *)this + 17),
              (char *)this + 64,
              0,
              0,
              a2,
              1);
      if ( v10 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 62;
        v13 = "Dispatch async call HttpReceiveResponseSuccess failed";
        goto LABEL_51;
      }
      break;
    case 0x40000:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v16 = GetCurrentThreadId();
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v17, v16);
      }
      *((_DWORD *)a2 + 32) = *a4;
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, struct _DM_CONTEXT *, int))(**((_QWORD **)this + 17)
                                                                                                 + 144LL))(
              *((_QWORD *)this + 17),
              (char *)this + 72,
              0,
              0,
              a2,
              1);
      if ( v10 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 64;
        v13 = "Dispatch async call HttpQueryDataSuccess failed";
        goto LABEL_51;
      }
      break;
    case 0x80000:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v14 = GetCurrentThreadId();
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v15, v14);
      }
      *((_DWORD *)a2 + 36) = a5;
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, struct _DM_CONTEXT *, int))(**((_QWORD **)this + 17)
                                                                                                 + 144LL))(
              *((_QWORD *)this + 17),
              (char *)this + 80,
              0,
              0,
              a2,
              1);
      if ( v10 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 66;
        v13 = "Dispatch async call HttpReadDataSuccess failed";
        goto LABEL_51;
      }
      break;
    case 0x400000:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v8 = GetCurrentThreadId();
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v9, v8);
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, struct _DM_CONTEXT *, int))(**((_QWORD **)this + 17)
                                                                                                 + 144LL))(
              *((_QWORD *)this + 17),
              (char *)this + 56,
              0,
              0,
              a2,
              1);
      if ( v10 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 60;
        v13 = "Dispatch async call HttpSendRequestSuccess failed";
LABEL_51:
        LODWORD(v22) = v10;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
          v11,
          (__int64)v13,
          v22);
      }
      break;
  }
}

```

## disassembly

```asm
0x18005c2c8  push    rbx
0x18005c2ca  push    rbp
0x18005c2cb  push    rsi
0x18005c2cc  push    rdi
0x18005c2cd  push    r14
0x18005c2cf  sub     rsp, 40h
0x18005c2d3  mov     r14, r9
0x18005c2d6  mov     rbp, rdx
0x18005c2d9  mov     rsi, rcx
0x18005c2dc  cmp     r8d, 4000h
0x18005c2e3  jz      loc_18005C633
0x18005c2e9  cmp     r8d, 20000h
0x18005c2f0  jz      loc_18005C573
0x18005c2f6  cmp     r8d, 40000h
0x18005c2fd  jz      loc_18005C4AA
0x18005c303  cmp     r8d, 80000h
0x18005c30a  jz      loc_18005C3DD
0x18005c310  cmp     r8d, 400000h
0x18005c317  jnz     loc_18005C710
0x18005c31d  mov     rax, cs:WPP_GLOBAL_Control
0x18005c324  lea     rdi, WPP_GLOBAL_Control
0x18005c32b  cmp     rax, rdi
0x18005c32e  jz      short loc_18005C36C
0x18005c330  test    byte ptr [rax+1Ch], 1
0x18005c334  jz      short loc_18005C36C
0x18005c336  cmp     byte ptr [rax+19h], 4
0x18005c33a  jb      short loc_18005C36C
0x18005c33c  call    cs:__imp_GetCurrentThreadId
0x18005c342  mov     ebx, eax
0x18005c344  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c349  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c350  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005c357  mov     edx, 3Bh ; ';'
0x18005c35c  mov     dword ptr [rsp+68h+var_48], ebx
0x18005c360  mov     r9d, eax
0x18005c363  mov     rcx, [rcx+10h]
0x18005c367  call    WPP_SF_Dd
0x18005c36c  mov     rcx, [rsi+88h]
0x18005c373  lea     rdx, [rsi+38h]
0x18005c377  mov     dword ptr [rsp+68h+var_40], 1
0x18005c37f  xor     r9d, r9d
0x18005c382  xor     r8d, r8d
0x18005c385  mov     [rsp+68h+var_48], rbp
0x18005c38a  mov     rax, [rcx]
0x18005c38d  mov     rax, [rax+90h]
0x18005c394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c399  mov     ebx, eax
0x18005c39b  test    eax, eax
0x18005c39d  jns     loc_18005C710
0x18005c3a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3aa  cmp     rcx, rdi
0x18005c3ad  jz      loc_18005C710
0x18005c3b3  test    byte ptr [rcx+1Ch], 8
0x18005c3b7  jz      loc_18005C710
0x18005c3bd  cmp     byte ptr [rcx+19h], 2
0x18005c3c1  jb      loc_18005C710
0x18005c3c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c3cc  mov     edx, 3Ch ; '<'
0x18005c3d1  lea     rcx, aDispatchAsyncC_4; "Dispatch async call HttpSendRequestSucc"...
0x18005c3d8  jmp     loc_18005C6ED
0x18005c3dd  mov     rax, cs:WPP_GLOBAL_Control
0x18005c3e4  lea     rdi, WPP_GLOBAL_Control
0x18005c3eb  cmp     rax, rdi
0x18005c3ee  jz      short loc_18005C42C
0x18005c3f0  test    byte ptr [rax+1Ch], 1
0x18005c3f4  jz      short loc_18005C42C
0x18005c3f6  cmp     byte ptr [rax+19h], 4
0x18005c3fa  jb      short loc_18005C42C
0x18005c3fc  call    cs:__imp_GetCurrentThreadId
0x18005c402  mov     ebx, eax
0x18005c404  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c409  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c410  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005c417  mov     edx, 41h ; 'A'
0x18005c41c  mov     dword ptr [rsp+68h+var_48], ebx
0x18005c420  mov     r9d, eax
0x18005c423  mov     rcx, [rcx+10h]
0x18005c427  call    WPP_SF_Dd
0x18005c42c  mov     eax, [rsp+68h+arg_20]
0x18005c433  lea     rdx, [rsi+50h]
0x18005c437  mov     [rbp+90h], eax
0x18005c43d  xor     r9d, r9d
0x18005c440  mov     rcx, [rsi+88h]
0x18005c447  xor     r8d, r8d
0x18005c44a  mov     dword ptr [rsp+68h+var_40], 1
0x18005c452  mov     [rsp+68h+var_48], rbp
0x18005c457  mov     rax, [rcx]
0x18005c45a  mov     rax, [rax+90h]
0x18005c461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c466  mov     ebx, eax
0x18005c468  test    eax, eax
0x18005c46a  jns     loc_18005C710
0x18005c470  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c477  cmp     rcx, rdi
0x18005c47a  jz      loc_18005C710
0x18005c480  test    byte ptr [rcx+1Ch], 8
0x18005c484  jz      loc_18005C710
0x18005c48a  cmp     byte ptr [rcx+19h], 2
0x18005c48e  jb      loc_18005C710
0x18005c494  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c499  mov     edx, 42h ; 'B'
0x18005c49e  lea     rcx, aDispatchAsyncC_3; "Dispatch async call HttpReadDataSuccess"...
0x18005c4a5  jmp     loc_18005C6ED
0x18005c4aa  mov     rax, cs:WPP_GLOBAL_Control
0x18005c4b1  lea     rdi, WPP_GLOBAL_Control
0x18005c4b8  cmp     rax, rdi
0x18005c4bb  jz      short loc_18005C4F9
0x18005c4bd  test    byte ptr [rax+1Ch], 1
0x18005c4c1  jz      short loc_18005C4F9
0x18005c4c3  cmp     byte ptr [rax+19h], 4
0x18005c4c7  jb      short loc_18005C4F9
0x18005c4c9  call    cs:__imp_GetCurrentThreadId
0x18005c4cf  mov     ebx, eax
0x18005c4d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4dd  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005c4e4  mov     edx, 3Fh ; '?'
0x18005c4e9  mov     dword ptr [rsp+68h+var_48], ebx
0x18005c4ed  mov     r9d, eax
0x18005c4f0  mov     rcx, [rcx+10h]
0x18005c4f4  call    WPP_SF_Dd
0x18005c4f9  mov     eax, [r14]
0x18005c4fc  lea     rdx, [rsi+48h]
0x18005c500  mov     [rbp+80h], eax
0x18005c506  xor     r9d, r9d
0x18005c509  mov     rcx, [rsi+88h]
0x18005c510  xor     r8d, r8d
0x18005c513  mov     dword ptr [rsp+68h+var_40], 1
0x18005c51b  mov     [rsp+68h+var_48], rbp
0x18005c520  mov     rax, [rcx]
0x18005c523  mov     rax, [rax+90h]
0x18005c52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c52f  mov     ebx, eax
0x18005c531  test    eax, eax
0x18005c533  jns     loc_18005C710
0x18005c539  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c540  cmp     rcx, rdi
0x18005c543  jz      loc_18005C710
0x18005c549  test    byte ptr [rcx+1Ch], 8
0x18005c54d  jz      loc_18005C710
0x18005c553  cmp     byte ptr [rcx+19h], 2
0x18005c557  jb      loc_18005C710
0x18005c55d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c562  mov     edx, 40h ; '@'
0x18005c567  lea     rcx, aDispatchAsyncC_5; "Dispatch async call HttpQueryDataSucces"...
0x18005c56e  jmp     loc_18005C6ED
0x18005c573  mov     rax, cs:WPP_GLOBAL_Control
0x18005c57a  lea     rdi, WPP_GLOBAL_Control
0x18005c581  cmp     rax, rdi
0x18005c584  jz      short loc_18005C5C2
0x18005c586  test    byte ptr [rax+1Ch], 1
0x18005c58a  jz      short loc_18005C5C2
0x18005c58c  cmp     byte ptr [rax+19h], 4
0x18005c590  jb      short loc_18005C5C2
0x18005c592  call    cs:__imp_GetCurrentThreadId
0x18005c598  mov     ebx, eax
0x18005c59a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c59f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c5a6  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005c5ad  mov     edx, 3Dh ; '='
0x18005c5b2  mov     dword ptr [rsp+68h+var_48], ebx
0x18005c5b6  mov     r9d, eax
0x18005c5b9  mov     rcx, [rcx+10h]
0x18005c5bd  call    WPP_SF_Dd
0x18005c5c2  mov     rcx, [rsi+88h]
0x18005c5c9  lea     rdx, [rsi+40h]
0x18005c5cd  mov     dword ptr [rsp+68h+var_40], 1
0x18005c5d5  xor     r9d, r9d
0x18005c5d8  xor     r8d, r8d
0x18005c5db  mov     [rsp+68h+var_48], rbp
0x18005c5e0  mov     rax, [rcx]
0x18005c5e3  mov     rax, [rax+90h]
0x18005c5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c5ef  mov     ebx, eax
0x18005c5f1  test    eax, eax
0x18005c5f3  jns     loc_18005C710
0x18005c5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c600  cmp     rcx, rdi
0x18005c603  jz      loc_18005C710
0x18005c609  test    byte ptr [rcx+1Ch], 8
0x18005c60d  jz      loc_18005C710
0x18005c613  cmp     byte ptr [rcx+19h], 2
0x18005c617  jb      loc_18005C710
0x18005c61d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c622  mov     edx, 3Eh ; '>'
0x18005c627  lea     rcx, aDispatchAsyncC_0; "Dispatch async call HttpReceiveResponse"...
0x18005c62e  jmp     loc_18005C6ED
0x18005c633  mov     rax, cs:WPP_GLOBAL_Control
0x18005c63a  lea     rdi, WPP_GLOBAL_Control
0x18005c641  cmp     rax, rdi
0x18005c644  jz      short loc_18005C682
0x18005c646  test    byte ptr [rax+1Ch], 1
0x18005c64a  jz      short loc_18005C682
0x18005c64c  cmp     byte ptr [rax+19h], 4
0x18005c650  jb      short loc_18005C682
0x18005c652  call    cs:__imp_GetCurrentThreadId
0x18005c658  mov     ebx, eax
0x18005c65a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c65f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c666  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005c66d  mov     edx, 43h ; 'C'
0x18005c672  mov     dword ptr [rsp+68h+var_48], ebx
0x18005c676  mov     r9d, eax
0x18005c679  mov     rcx, [rcx+10h]
0x18005c67d  call    WPP_SF_Dd
0x18005c682  lea     rcx, [rbp+0C8h]
0x18005c689  mov     rdx, r14
0x18005c68c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18005c691  mov     rcx, [rsi+88h]
0x18005c698  lea     rdx, [rsi+70h]
0x18005c69c  mov     dword ptr [rsp+68h+var_40], 1
0x18005c6a4  xor     r9d, r9d
0x18005c6a7  xor     r8d, r8d
0x18005c6aa  mov     [rsp+68h+var_48], rbp
0x18005c6af  mov     rax, [rcx]
0x18005c6b2  mov     rax, [rax+90h]
0x18005c6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c6be  mov     ebx, eax
0x18005c6c0  test    eax, eax
0x18005c6c2  jns     short loc_18005C710
0x18005c6c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c6cb  cmp     rcx, rdi
0x18005c6ce  jz      short loc_18005C710
0x18005c6d0  test    byte ptr [rcx+1Ch], 8
0x18005c6d4  jz      short loc_18005C710
0x18005c6d6  cmp     byte ptr [rcx+19h], 2
0x18005c6da  jb      short loc_18005C710
0x18005c6dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005c6e1  mov     edx, 44h ; 'D'
0x18005c6e6  lea     rcx, aDispatchAsyncC; "Dispatch async call HttpRedirectPending"...
0x18005c6ed  mov     dword ptr [rsp+68h+var_40], ebx
0x18005c6f1  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005c6f8  mov     [rsp+68h+var_48], rcx
0x18005c6fd  mov     r9d, eax
0x18005c700  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c707  mov     rcx, [rcx+10h]
0x18005c70b  call    WPP_SF_DsD
0x18005c710  add     rsp, 40h
0x18005c714  pop     r14
0x18005c716  pop     rdi
0x18005c717  pop     rsi
0x18005c718  pop     rbp
0x18005c719  pop     rbx
0x18005c71a  retn
```
