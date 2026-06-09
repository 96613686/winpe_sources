# CDumpCollection::_SnapAllThreads(void)

- ea: `0x14000fb3c`
- end: `0x14000fd62`
- name: `?_SnapAllThreads@CDumpCollection@@AEAAJXZ`
- size: `550`
- prototype: `__int64 __fastcall(CDumpCollection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e8c4`

## callees

- `0x1400023d0`
- `0x1400073fc`
- `0x140007cd4`
- `0x14000e598`
- `0x14000e640`
- `0x14000fb3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fbd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fcdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fbd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fcdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fd35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fd35`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14000fb8f`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x14000fb8f`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14000fbcb`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x14000fbcb`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14000fc50`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x14000fc50`

## pseudocode

```c
__int64 __fastcall CDumpCollection::_SnapAllThreads(CDumpCollection *this)
{
  _QWORD *v2; // rsi
  HANDLE Toolhelp32Snapshot; // rax
  void *v4; // rbx
  unsigned __int64 v5; // r14
  signed int v6; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD *v10; // rcx
  signed int v11; // eax
  signed int LastError; // eax
  _DWORD v14[10]; // [rsp+20h] [rbp-50h] BYREF
  THREADENTRY32 te; // [rsp+48h] [rbp-28h] BYREF

  if ( !*((_DWORD *)this + 278) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = (_QWORD *)((char *)this + 2400);
  if ( *((_QWORD *)this + 300) != *((_QWORD *)this + 301) )
    return 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(4u, *((_DWORD *)this + 278));
  v4 = Toolhelp32Snapshot;
  v5 = (unsigned __int64)Toolhelp32Snapshot + 1;
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 <= 1 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v9 = 77;
    goto LABEL_31;
  }
  memset(&v14[2], 0, 28);
  *(_OWORD *)&te.dwSize = *(_OWORD *)&v14[2];
  te.dwSize = 28;
  *(_OWORD *)&te.th32OwnerProcessID = 0;
  if ( Thread32First(Toolhelp32Snapshot, &te) )
  {
    do
    {
      if ( te.th32OwnerProcessID == *((_DWORD *)this + 278) )
      {
        v10 = (DWORD *)*((_QWORD *)this + 301);
        v14[0] = te.th32ThreadID;
        if ( v10 == *((DWORD **)this + 302) )
        {
          if ( !(unsigned __int8)utl::vector<CDumpCollection::ThreadInfoNode,utl::allocator<CDumpCollection::ThreadInfoNode>>::_PushBackOne2<CDumpCollection::ThreadInfoNode>(
                                   (char *)this + 2400,
                                   v14) )
          {
            v7 = -2147024882;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
            goto LABEL_33;
          }
        }
        else
        {
          *v10 = te.th32ThreadID;
          *((_QWORD *)this + 301) += 4LL;
        }
      }
    }
    while ( Thread32Next(v4, &te) );
    if ( GetLastError() == 18 )
    {
      v7 = 0;
      goto LABEL_35;
    }
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 80;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 78;
LABEL_31:
    WPP_SF_d(v8[2], v9, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v7);
  }
LABEL_32:
  if ( (v7 & 0x80000000) != 0 )
LABEL_33:
    v2[1] = *v2;
  if ( v5 > 1 )
LABEL_35:
    CloseHandle(v4);
  return v7;
}

```

## disassembly

```asm
0x14000fb3c  mov     [rsp-18h+arg_8], rbx
0x14000fb41  mov     [rsp-18h+arg_10], rsi
0x14000fb46  push    rbp
0x14000fb47  push    rdi
0x14000fb48  push    r14
0x14000fb4a  mov     rbp, rsp
0x14000fb4d  sub     rsp, 70h
0x14000fb51  mov     rax, cs:__security_cookie
0x14000fb58  xor     rax, rsp
0x14000fb5b  mov     [rbp+var_8], rax
0x14000fb5f  cmp     dword ptr [rcx+458h], 0
0x14000fb66  mov     rdi, rcx
0x14000fb69  jnz     short loc_14000FB70
0x14000fb6b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000fb70  lea     rsi, [rdi+960h]
0x14000fb77  mov     rax, [rsi+8]
0x14000fb7b  cmp     [rsi], rax
0x14000fb7e  jnz     loc_14000FD3F
0x14000fb84  mov     edx, [rdi+458h]; th32ProcessID
0x14000fb8a  mov     ecx, 4; dwFlags
0x14000fb8f  call    cs:__imp_CreateToolhelp32Snapshot
0x14000fb95  mov     rbx, rax
0x14000fb98  lea     r14, [rax+1]
0x14000fb9c  cmp     r14, 1
0x14000fba0  jbe     loc_14000FCDB
0x14000fba6  xorps   xmm1, xmm1
0x14000fba9  lea     rdx, [rbp+te]; lpte
0x14000fbad  movups  xmmword ptr [rbp+var_48], xmm1
0x14000fbb1  mov     rcx, rax; hSnapshot
0x14000fbb4  movups  xmmword ptr [rbp+var_48+0Ch], xmm1
0x14000fbb8  movups  xmm0, xmmword ptr [rbp+var_48]
0x14000fbbc  movups  xmmword ptr [rbp+te.dwSize], xmm0
0x14000fbc0  mov     [rbp+te.dwSize], 1Ch
0x14000fbc7  movups  xmmword ptr [rbp+te.th32OwnerProcessID], xmm1
0x14000fbcb  call    cs:__imp_Thread32First
0x14000fbd1  test    eax, eax
0x14000fbd3  jnz     short loc_14000FC15
0x14000fbd5  call    cs:__imp_GetLastError
0x14000fbdb  mov     edi, eax
0x14000fbdd  test    eax, eax
0x14000fbdf  jle     short loc_14000FBEA
0x14000fbe1  movzx   edi, ax
0x14000fbe4  or      edi, 80070000h
0x14000fbea  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbf1  lea     rax, WPP_GLOBAL_Control
0x14000fbf8  cmp     rcx, rax
0x14000fbfb  jz      loc_14000FD21
0x14000fc01  test    byte ptr [rcx+1Ch], 1
0x14000fc05  jz      loc_14000FD21
0x14000fc0b  mov     edx, 4Eh ; 'N'
0x14000fc10  jmp     loc_14000FD0E
0x14000fc15  mov     eax, [rdi+458h]
0x14000fc1b  cmp     [rbp+te.th32OwnerProcessID], eax
0x14000fc1e  jnz     short loc_14000FC49
0x14000fc20  mov     rcx, [rsi+8]
0x14000fc24  mov     eax, [rbp+te.th32ThreadID]
0x14000fc27  mov     [rbp+var_50], eax
0x14000fc2a  cmp     rcx, [rsi+10h]
0x14000fc2e  jz      short loc_14000FC39
0x14000fc30  mov     [rcx], eax
0x14000fc32  add     qword ptr [rsi+8], 4
0x14000fc37  jmp     short loc_14000FC49
0x14000fc39  lea     rdx, [rbp+var_50]
0x14000fc3d  mov     rcx, rsi
0x14000fc40  call    ??$_PushBackOne2@UThreadInfoNode@CDumpCollection@@@?$vector@UThreadInfoNode@CDumpCollection@@V?$allocator@UThreadInfoNode@CDumpCollection@@@utl@@@utl@@AEAA_N$$QEAUThreadInfoNode@CDumpCollection@@@Z; utl::vector<CDumpCollection::ThreadInfoNode,utl::allocator<CDumpCollection::ThreadInfoNode>>::_PushBackOne2<CDumpCollection::ThreadInfoNode>(CDumpCollection::ThreadInfoNode &&)
0x14000fc45  test    al, al
0x14000fc47  jz      short loc_14000FCA2
0x14000fc49  lea     rdx, [rbp+te]; lpte
0x14000fc4d  mov     rcx, rbx; hSnapshot
0x14000fc50  call    cs:__imp_Thread32Next
0x14000fc56  test    eax, eax
0x14000fc58  jnz     short loc_14000FC15
0x14000fc5a  call    cs:__imp_GetLastError
0x14000fc60  cmp     eax, 12h
0x14000fc63  jz      short loc_14000FCD7
0x14000fc65  call    cs:__imp_GetLastError
0x14000fc6b  mov     edi, eax
0x14000fc6d  test    eax, eax
0x14000fc6f  jle     short loc_14000FC7A
0x14000fc71  movzx   edi, ax
0x14000fc74  or      edi, 80070000h
0x14000fc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc81  lea     rax, WPP_GLOBAL_Control
0x14000fc88  cmp     rcx, rax
0x14000fc8b  jz      loc_14000FD21
0x14000fc91  test    byte ptr [rcx+1Ch], 1
0x14000fc95  jz      loc_14000FD21
0x14000fc9b  mov     edx, 50h ; 'P'
0x14000fca0  jmp     short loc_14000FD0E
0x14000fca2  mov     edi, 8007000Eh
0x14000fca7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fcae  lea     rax, WPP_GLOBAL_Control
0x14000fcb5  cmp     rcx, rax
0x14000fcb8  jz      short loc_14000FD25
0x14000fcba  test    byte ptr [rcx+1Ch], 1
0x14000fcbe  jz      short loc_14000FD25
0x14000fcc0  mov     rcx, [rcx+10h]
0x14000fcc4  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000fccb  mov     edx, 4Fh ; 'O'
0x14000fcd0  call    WPP_SF_
0x14000fcd5  jmp     short loc_14000FD25
0x14000fcd7  xor     edi, edi
0x14000fcd9  jmp     short loc_14000FD32
0x14000fcdb  call    cs:__imp_GetLastError
0x14000fce1  mov     edi, eax
0x14000fce3  test    eax, eax
0x14000fce5  jle     short loc_14000FCF0
0x14000fce7  movzx   edi, ax
0x14000fcea  or      edi, 80070000h
0x14000fcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fcf7  lea     rax, WPP_GLOBAL_Control
0x14000fcfe  cmp     rcx, rax
0x14000fd01  jz      short loc_14000FD21
0x14000fd03  test    byte ptr [rcx+1Ch], 1
0x14000fd07  jz      short loc_14000FD21
0x14000fd09  mov     edx, 4Dh ; 'M'
0x14000fd0e  mov     rcx, [rcx+10h]
0x14000fd12  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x14000fd19  mov     r9d, edi
0x14000fd1c  call    WPP_SF_d
0x14000fd21  test    edi, edi
0x14000fd23  jns     short loc_14000FD2C
0x14000fd25  mov     rcx, [rsi]
0x14000fd28  mov     [rsi+8], rcx
0x14000fd2c  cmp     r14, 1
0x14000fd30  jbe     short loc_14000FD3B
0x14000fd32  mov     rcx, rbx; hObject
0x14000fd35  call    cs:__imp_CloseHandle
0x14000fd3b  mov     eax, edi
0x14000fd3d  jmp     short loc_14000FD41
0x14000fd3f  xor     eax, eax
0x14000fd41  mov     rcx, [rbp+var_8]
0x14000fd45  xor     rcx, rsp; StackCookie
0x14000fd48  call    __security_check_cookie
0x14000fd4d  lea     r11, [rsp+70h+var_s0]
0x14000fd52  mov     rbx, [r11+28h]
0x14000fd56  mov     rsi, [r11+30h]
0x14000fd5a  mov     rsp, r11
0x14000fd5d  pop     r14
0x14000fd5f  pop     rdi
0x14000fd60  pop     rbp
0x14000fd61  retn
```
