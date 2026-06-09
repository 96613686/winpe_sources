# CDownloadManager::RequestSafeShutdown(void)

- ea: `0x18005d3c0`
- end: `0x18005d66d`
- name: `?RequestSafeShutdown@CDownloadManager@@IEAAJXZ`
- size: `685`
- prototype: `__int64 __fastcall(CDownloadManager *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800592c0`
- `0x18005bac0`
- `0x18005d018`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18005d3c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d456`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d456`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d562`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d52e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d52e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5e6`
- `WINHTTP!WinHttpCloseHandle` at `0x18005d4cf`
- `WINHTTP!WinHttpCloseHandle` at `0x18005d4cf`

## pseudocode

```c
signed int __fastcall CDownloadManager::RequestSafeShutdown(CDownloadManager *this)
{
  __int64 v1; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int result; // eax
  DWORD LastError; // ebx
  unsigned int v6; // eax
  signed int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  void *v11; // rcx
  DWORD v12; // eax
  unsigned int v13; // eax
  signed int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rcx

  v1 = *((_QWORD *)this + 258);
  if ( !v1 || !*(_QWORD *)(v1 + 40) )
    goto LABEL_42;
  if ( *(_QWORD *)(v1 + 120) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        150,
        &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    result = -2147418113;
    goto LABEL_43;
  }
  *(_QWORD *)(*((_QWORD *)this + 258) + 120LL) = CreateEventW(0, 1, 0, 0);
  if ( !*(_QWORD *)(*((_QWORD *)this + 258) + 120LL)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v6, LastError);
  }
  if ( !WinHttpCloseHandle(*(HINTERNET *)(*((_QWORD *)this + 258) + 40LL)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 152;
LABEL_21:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v9, v8);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v11 = *(void **)(*((_QWORD *)this + 258) + 120LL);
  if ( !v11 )
  {
LABEL_42:
    result = 0;
    goto LABEL_43;
  }
  v12 = WaitForSingleObject(v11, 0x7530u);
  if ( v12 != 258 )
  {
    if ( v12 == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        v8 = v14;
        if ( v14 > 0 )
          v8 = (unsigned __int16)v14 | 0x80070000;
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 154;
        goto LABEL_21;
      }
LABEL_22:
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      goto LABEL_43;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v15);
    }
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      153,
      &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
      v13,
      -2147024638);
  }
  result = -2147024638;
LABEL_43:
  v16 = *((_QWORD *)this + 258);
  if ( v16 )
    *(_QWORD *)(v16 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x18005d3c0  mov     [rsp+arg_0], rbx
0x18005d3c5  mov     [rsp+arg_8], rdi
0x18005d3ca  push    r15
0x18005d3cc  sub     rsp, 30h
0x18005d3d0  mov     rax, [rcx+810h]
0x18005d3d7  mov     r15, rcx
0x18005d3da  test    rax, rax
0x18005d3dd  jz      loc_18005D646
0x18005d3e3  cmp     qword ptr [rax+28h], 0
0x18005d3e8  jz      loc_18005D646
0x18005d3ee  cmp     qword ptr [rax+78h], 0
0x18005d3f3  jz      short loc_18005D44A
0x18005d3f5  mov     rax, cs:WPP_GLOBAL_Control
0x18005d3fc  lea     rdi, WPP_GLOBAL_Control
0x18005d403  cmp     rax, rdi
0x18005d406  jz      short loc_18005D440
0x18005d408  test    byte ptr [rax+1Ch], 8
0x18005d40c  jz      short loc_18005D440
0x18005d40e  cmp     byte ptr [rax+19h], 2
0x18005d412  jb      short loc_18005D440
0x18005d414  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d419  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d420  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d427  mov     edx, 96h
0x18005d42c  mov     [rsp+38h+var_18], 8000FFFFh
0x18005d434  mov     r9d, eax
0x18005d437  mov     rcx, [rcx+10h]
0x18005d43b  call    WPP_SF_Dd
0x18005d440  mov     eax, 8000FFFFh
0x18005d445  jmp     loc_18005D648
0x18005d44a  xor     r9d, r9d; lpName
0x18005d44d  xor     r8d, r8d; bInitialState
0x18005d450  xor     ecx, ecx; lpEventAttributes
0x18005d452  lea     edx, [r9+1]; bManualReset
0x18005d456  call    cs:__imp_CreateEventW
0x18005d45c  mov     rcx, [r15+810h]
0x18005d463  lea     rdi, WPP_GLOBAL_Control
0x18005d46a  mov     [rcx+78h], rax
0x18005d46e  mov     rax, [r15+810h]
0x18005d475  cmp     qword ptr [rax+78h], 0
0x18005d47a  jnz     short loc_18005D4C4
0x18005d47c  mov     rax, cs:WPP_GLOBAL_Control
0x18005d483  cmp     rax, rdi
0x18005d486  jz      short loc_18005D4C4
0x18005d488  test    byte ptr [rax+1Ch], 1
0x18005d48c  jz      short loc_18005D4C4
0x18005d48e  cmp     byte ptr [rax+19h], 2
0x18005d492  jb      short loc_18005D4C4
0x18005d494  call    cs:__imp_GetLastError
0x18005d49a  mov     ebx, eax
0x18005d49c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d4a8  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d4af  mov     edx, 97h
0x18005d4b4  mov     [rsp+38h+var_18], ebx
0x18005d4b8  mov     r9d, eax
0x18005d4bb  mov     rcx, [rcx+10h]
0x18005d4bf  call    WPP_SF_Dd
0x18005d4c4  mov     rcx, [r15+810h]
0x18005d4cb  mov     rcx, [rcx+28h]; hInternet
0x18005d4cf  call    cs:__imp_WinHttpCloseHandle
0x18005d4d5  test    eax, eax
0x18005d4d7  jnz     short loc_18005D549
0x18005d4d9  mov     rax, cs:WPP_GLOBAL_Control
0x18005d4e0  cmp     rax, rdi
0x18005d4e3  jz      short loc_18005D52E
0x18005d4e5  test    byte ptr [rax+1Ch], 8
0x18005d4e9  jz      short loc_18005D52E
0x18005d4eb  cmp     byte ptr [rax+19h], 2
0x18005d4ef  jb      short loc_18005D52E
0x18005d4f1  call    cs:__imp_GetLastError
0x18005d4f7  mov     ebx, eax
0x18005d4f9  test    eax, eax
0x18005d4fb  jle     short loc_18005D506
0x18005d4fd  movzx   ebx, ax
0x18005d500  or      ebx, 80070000h
0x18005d506  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d50b  mov     edx, 98h
0x18005d510  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d517  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d51e  mov     r9d, eax
0x18005d521  mov     [rsp+38h+var_18], ebx
0x18005d525  mov     rcx, [rcx+10h]
0x18005d529  call    WPP_SF_Dd
0x18005d52e  call    cs:__imp_GetLastError
0x18005d534  test    eax, eax
0x18005d536  jle     loc_18005D648
0x18005d53c  movzx   eax, ax
0x18005d53f  or      eax, 80070000h
0x18005d544  jmp     loc_18005D648
0x18005d549  mov     rax, [r15+810h]
0x18005d550  mov     rcx, [rax+78h]; hHandle
0x18005d554  test    rcx, rcx
0x18005d557  jz      loc_18005D646
0x18005d55d  mov     edx, 7530h; dwMilliseconds
0x18005d562  call    cs:__imp_WaitForSingleObject
0x18005d568  cmp     eax, 102h
0x18005d56d  jnz     short loc_18005D5BD
0x18005d56f  mov     rax, cs:WPP_GLOBAL_Control
0x18005d576  cmp     rax, rdi
0x18005d579  jz      short loc_18005D5B3
0x18005d57b  test    byte ptr [rax+1Ch], 8
0x18005d57f  jz      short loc_18005D5B3
0x18005d581  cmp     byte ptr [rax+19h], 2
0x18005d585  jb      short loc_18005D5B3
0x18005d587  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d593  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d59a  mov     edx, 99h
0x18005d59f  mov     [rsp+38h+var_18], 80070102h
0x18005d5a7  mov     r9d, eax
0x18005d5aa  mov     rcx, [rcx+10h]
0x18005d5ae  call    WPP_SF_Dd
0x18005d5b3  mov     eax, 80070102h
0x18005d5b8  jmp     loc_18005D648
0x18005d5bd  cmp     eax, 0FFFFFFFFh
0x18005d5c0  jnz     short loc_18005D60A
0x18005d5c2  mov     rax, cs:WPP_GLOBAL_Control
0x18005d5c9  cmp     rax, rdi
0x18005d5cc  jz      loc_18005D52E
0x18005d5d2  test    byte ptr [rax+1Ch], 8
0x18005d5d6  jz      loc_18005D52E
0x18005d5dc  cmp     byte ptr [rax+19h], 2
0x18005d5e0  jb      loc_18005D52E
0x18005d5e6  call    cs:__imp_GetLastError
0x18005d5ec  mov     ebx, eax
0x18005d5ee  test    eax, eax
0x18005d5f0  jle     short loc_18005D5FB
0x18005d5f2  movzx   ebx, ax
0x18005d5f5  or      ebx, 80070000h
0x18005d5fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d600  mov     edx, 9Ah
0x18005d605  jmp     loc_18005D510
0x18005d60a  mov     rax, cs:WPP_GLOBAL_Control
0x18005d611  cmp     rax, rdi
0x18005d614  jz      short loc_18005D646
0x18005d616  test    byte ptr [rax+1Ch], 1
0x18005d61a  jz      short loc_18005D646
0x18005d61c  cmp     byte ptr [rax+19h], 4
0x18005d620  jb      short loc_18005D646
0x18005d622  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d627  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d62e  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d635  mov     edx, 9Bh
0x18005d63a  mov     r9d, eax
0x18005d63d  mov     rcx, [rcx+10h]
0x18005d641  call    WPP_SF_D
0x18005d646  xor     eax, eax
0x18005d648  mov     rcx, [r15+810h]
0x18005d64f  test    rcx, rcx
0x18005d652  jz      short loc_18005D65C
0x18005d654  mov     qword ptr [rcx+28h], 0
0x18005d65c  mov     rbx, [rsp+38h+arg_0]
0x18005d661  mov     rdi, [rsp+38h+arg_8]
0x18005d666  add     rsp, 30h
0x18005d66a  pop     r15
0x18005d66c  retn
```
