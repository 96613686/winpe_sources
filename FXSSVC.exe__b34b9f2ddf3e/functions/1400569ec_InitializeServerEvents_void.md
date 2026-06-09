# InitializeServerEvents(void)

- ea: `0x1400569ec`
- end: `0x140056c6f`
- name: `?InitializeServerEvents@@YAKXZ`
- size: `643`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400480f0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x140035158`
- `0x14004ecd4`
- `0x1400569ec`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140056a6c`
- `KERNEL32!GetLastError` at `0x140056ac7`
- `KERNEL32!GetLastError` at `0x140056b43`
- `KERNEL32!GetLastError` at `0x140056b79`
- `KERNEL32!GetLastError` at `0x140056bdd`
- `KERNEL32!GetLastError` at `0x140056c3b`
- `KERNEL32!GetLastError` at `0x140056a6c`
- `KERNEL32!GetLastError` at `0x140056ac7`
- `KERNEL32!GetLastError` at `0x140056b43`
- `KERNEL32!GetLastError` at `0x140056b79`
- `KERNEL32!GetLastError` at `0x140056bdd`
- `KERNEL32!GetLastError` at `0x140056c3b`
- `KERNEL32!CloseHandle` at `0x140056bbb`
- `KERNEL32!CloseHandle` at `0x140056c19`
- `KERNEL32!CloseHandle` at `0x140056bbb`
- `KERNEL32!CloseHandle` at `0x140056c19`
- `KERNEL32!CreateIoCompletionPort` at `0x140056a5a`
- `KERNEL32!CreateIoCompletionPort` at `0x140056ab5`
- `KERNEL32!CreateIoCompletionPort` at `0x140056a5a`
- `KERNEL32!CreateIoCompletionPort` at `0x140056ab5`

## pseudocode

```c
__int64 InitializeServerEvents(void)
{
  DWORD LastError; // ebx
  CMapDeviceId *v1; // rcx
  __int64 v2; // rdx
  __int64 v4; // rdx
  struct _SECURITY_ATTRIBUTES *v5; // rcx
  __int64 v6; // rbx
  HANDLE v7; // rax
  DWORD v8; // edi
  HANDLE v9; // rsi
  DWORD v10; // eax
  DWORD v11; // eax
  __int64 v12; // rbx
  HANDLE v13; // rcx
  DWORD v14; // eax
  DWORD v15; // eax
  unsigned int v16; // [rsp+20h] [rbp-68h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-58h]
  __int128 v18; // [rsp+40h] [rbp-48h]
  unsigned int v19; // [rsp+90h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  v19 = 0;
  *(_OWORD *)hObject = 0;
  v18 = 0;
  g_hSendEventsCompPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 2u);
  if ( !g_hSendEventsCompPort )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v2 = 89;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v1 + 2), v2, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, LastError);
    return LastError;
  }
  g_hDispatchEventsCompPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  if ( !g_hDispatchEventsCompPort )
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v2 = 90;
    goto LABEL_10;
  }
  v6 = 0;
  while ( 1 )
  {
    v7 = CreateThreadAndRefCount(v5, v4, (unsigned int (*)(void *))FaxSendEventThread, 0, v16, &v19);
    hObject[v6] = v7;
    if ( !v7 )
      break;
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 4 )
    {
      v8 = 0;
      v9 = CreateThreadAndRefCount(v5, v4, (unsigned int (*)(void *))FaxDispatchEventThread, 0, v16, &v19);
      if ( !v9 )
      {
        v10 = GetLastError();
        v8 = v10;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v10);
        }
      }
      goto LABEL_29;
    }
  }
  v9 = 0;
  v11 = GetLastError();
  v8 = v11;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids,
      (unsigned int)v6,
      v11);
  }
LABEL_29:
  v12 = 0;
  do
  {
    v13 = hObject[v12];
    if ( v13
      && !CloseHandle(v13)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = GetLastError();
      WPP_SF_lll(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids,
        (unsigned int)v12,
        hObject[v12],
        v14);
    }
    v12 = (unsigned int)(v12 + 1);
  }
  while ( (unsigned int)v12 < 4 );
  if ( v9
    && !CloseHandle(v9)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = GetLastError();
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids,
      (unsigned int)v9,
      v15);
  }
  return v8;
}

```

## disassembly

```asm
0x1400569ec  push    rbx
0x1400569ee  push    rbp
0x1400569ef  push    rsi
0x1400569f0  push    rdi
0x1400569f1  push    r13
0x1400569f3  push    r15
0x1400569f5  sub     rsp, 58h
0x1400569f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a00  lea     r15, WPP_GLOBAL_Control
0x140056a07  lea     r13, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140056a0e  cmp     rcx, r15
0x140056a11  jz      short loc_140056A30
0x140056a13  test    byte ptr [rcx+1Ch], 4
0x140056a17  jz      short loc_140056A30
0x140056a19  cmp     byte ptr [rcx+19h], 5
0x140056a1d  jb      short loc_140056A30
0x140056a1f  mov     rcx, [rcx+10h]
0x140056a23  mov     edx, 58h ; 'X'
0x140056a28  mov     r8, r13
0x140056a2b  call    WPP_SF_
0x140056a30  xorps   xmm0, xmm0
0x140056a33  mov     [rsp+88h+arg_0], 0
0x140056a3e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140056a42  mov     r9d, 2; NumberOfConcurrentThreads
0x140056a48  mov     rcx, rbx; FileHandle
0x140056a4b  xor     r8d, r8d; CompletionKey
0x140056a4e  xor     edx, edx; ExistingCompletionPort
0x140056a50  movups  xmmword ptr [rsp+88h+hObject], xmm0
0x140056a55  movups  [rsp+88h+var_48], xmm0
0x140056a5a  call    cs:__imp_CreateIoCompletionPort
0x140056a60  mov     cs:?g_hSendEventsCompPort@@3PEAXEA, rax; void * g_hSendEventsCompPort
0x140056a67  test    rax, rax
0x140056a6a  jnz     short loc_140056AA7
0x140056a6c  call    cs:__imp_GetLastError
0x140056a72  mov     ebx, eax
0x140056a74  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a7b  cmp     rcx, r15
0x140056a7e  jz      short loc_140056AA0
0x140056a80  test    byte ptr [rcx+1Ch], 4
0x140056a84  jz      short loc_140056AA0
0x140056a86  cmp     byte ptr [rcx+19h], 2
0x140056a8a  jb      short loc_140056AA0
0x140056a8c  mov     edx, 59h ; 'Y'
0x140056a91  mov     rcx, [rcx+10h]
0x140056a95  mov     r9d, ebx
0x140056a98  mov     r8, r13
0x140056a9b  call    WPP_SF_d
0x140056aa0  mov     eax, ebx
0x140056aa2  jmp     loc_140056C62
0x140056aa7  mov     r9d, 1; NumberOfConcurrentThreads
0x140056aad  xor     r8d, r8d; CompletionKey
0x140056ab0  xor     edx, edx; ExistingCompletionPort
0x140056ab2  mov     rcx, rbx; FileHandle
0x140056ab5  call    cs:__imp_CreateIoCompletionPort
0x140056abb  mov     cs:?g_hDispatchEventsCompPort@@3PEAXEA, rax; void * g_hDispatchEventsCompPort
0x140056ac2  test    rax, rax
0x140056ac5  jnz     short loc_140056AEE
0x140056ac7  call    cs:__imp_GetLastError
0x140056acd  mov     ebx, eax
0x140056acf  mov     rcx, cs:WPP_GLOBAL_Control
0x140056ad6  cmp     rcx, r15
0x140056ad9  jz      short loc_140056AA0
0x140056adb  test    byte ptr [rcx+1Ch], 4
0x140056adf  jz      short loc_140056AA0
0x140056ae1  cmp     byte ptr [rcx+19h], 2
0x140056ae5  jb      short loc_140056AA0
0x140056ae7  mov     edx, 5Ah ; 'Z'
0x140056aec  jmp     short loc_140056A91
0x140056aee  xor     ebx, ebx
0x140056af0  lea     rax, [rsp+88h+arg_0]
0x140056af8  xor     r9d, r9d; void *
0x140056afb  lea     r8, ?FaxSendEventThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x140056b02  mov     [rsp+88h+var_60], rax; unsigned int *
0x140056b07  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x140056b0c  mov     [rsp+rbx*8+88h+hObject], rax
0x140056b11  test    rax, rax
0x140056b14  jz      short loc_140056B77
0x140056b16  inc     ebx
0x140056b18  cmp     ebx, 4
0x140056b1b  jb      short loc_140056AF0
0x140056b1d  lea     rax, [rsp+88h+arg_0]
0x140056b25  xor     r9d, r9d; void *
0x140056b28  lea     r8, ?FaxDispatchEventThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x140056b2f  mov     [rsp+88h+var_60], rax; unsigned int *
0x140056b34  xor     edi, edi
0x140056b36  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x140056b3b  mov     rsi, rax
0x140056b3e  test    rax, rax
0x140056b41  jnz     short loc_140056BAF
0x140056b43  call    cs:__imp_GetLastError
0x140056b49  mov     edi, eax
0x140056b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056b52  cmp     rcx, r15
0x140056b55  jz      short loc_140056BAF
0x140056b57  test    byte ptr [rcx+1Ch], 4
0x140056b5b  jz      short loc_140056BAF
0x140056b5d  cmp     byte ptr [rcx+19h], 2
0x140056b61  jb      short loc_140056BAF
0x140056b63  mov     rcx, [rcx+10h]
0x140056b67  lea     edx, [rsi+5Ch]
0x140056b6a  mov     r9d, eax
0x140056b6d  mov     r8, r13
0x140056b70  call    WPP_SF_d
0x140056b75  jmp     short loc_140056BAF
0x140056b77  xor     esi, esi
0x140056b79  call    cs:__imp_GetLastError
0x140056b7f  mov     edi, eax
0x140056b81  mov     rcx, cs:WPP_GLOBAL_Control
0x140056b88  cmp     rcx, r15
0x140056b8b  jz      short loc_140056BAF
0x140056b8d  test    byte ptr [rcx+1Ch], 4
0x140056b91  jz      short loc_140056BAF
0x140056b93  cmp     byte ptr [rcx+19h], 2
0x140056b97  jb      short loc_140056BAF
0x140056b99  mov     rcx, [rcx+10h]
0x140056b9d  lea     edx, [rsi+5Bh]
0x140056ba0  mov     r9d, ebx
0x140056ba3  mov     [rsp+88h+var_68], eax
0x140056ba7  mov     r8, r13
0x140056baa  call    WPP_SF_dd
0x140056baf  xor     ebx, ebx
0x140056bb1  mov     rcx, [rsp+rbx*8+88h+hObject]; hObject
0x140056bb6  test    rcx, rcx
0x140056bb9  jz      short loc_140056C0A
0x140056bbb  call    cs:__imp_CloseHandle
0x140056bc1  test    eax, eax
0x140056bc3  jnz     short loc_140056C0A
0x140056bc5  mov     rax, cs:WPP_GLOBAL_Control
0x140056bcc  cmp     rax, r15
0x140056bcf  jz      short loc_140056C0A
0x140056bd1  test    byte ptr [rax+1Ch], 4
0x140056bd5  jz      short loc_140056C0A
0x140056bd7  cmp     byte ptr [rax+19h], 2
0x140056bdb  jb      short loc_140056C0A
0x140056bdd  call    cs:__imp_GetLastError
0x140056be3  mov     rcx, cs:WPP_GLOBAL_Control
0x140056bea  mov     edx, 5Dh ; ']'
0x140056bef  mov     dword ptr [rsp+88h+var_60], eax
0x140056bf3  mov     r9d, ebx
0x140056bf6  mov     eax, dword ptr [rsp+rbx*8+88h+hObject]
0x140056bfa  mov     r8, r13
0x140056bfd  mov     [rsp+88h+var_68], eax
0x140056c01  mov     rcx, [rcx+10h]
0x140056c05  call    WPP_SF_lll
0x140056c0a  inc     ebx
0x140056c0c  cmp     ebx, 4
0x140056c0f  jb      short loc_140056BB1
0x140056c11  test    rsi, rsi
0x140056c14  jz      short loc_140056C60
0x140056c16  mov     rcx, rsi; hObject
0x140056c19  call    cs:__imp_CloseHandle
0x140056c1f  test    eax, eax
0x140056c21  jnz     short loc_140056C60
0x140056c23  mov     rax, cs:WPP_GLOBAL_Control
0x140056c2a  cmp     rax, r15
0x140056c2d  jz      short loc_140056C60
0x140056c2f  test    byte ptr [rax+1Ch], 4
0x140056c33  jz      short loc_140056C60
0x140056c35  cmp     byte ptr [rax+19h], 2
0x140056c39  jb      short loc_140056C60
0x140056c3b  call    cs:__imp_GetLastError
0x140056c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c48  mov     r9d, esi
0x140056c4b  mov     edx, 5Eh ; '^'
0x140056c50  mov     [rsp+88h+var_68], eax
0x140056c54  mov     r8, r13
0x140056c57  mov     rcx, [rcx+10h]
0x140056c5b  call    WPP_SF_dd
0x140056c60  mov     eax, edi
0x140056c62  add     rsp, 58h
0x140056c66  pop     r15
0x140056c68  pop     r13
0x140056c6a  pop     rdi
0x140056c6b  pop     rsi
0x140056c6c  pop     rbp
0x140056c6d  pop     rbx
0x140056c6e  retn
```
