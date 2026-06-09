# InitializeServerEvents(void)

- ea: `0x140059f9c`
- end: `0x14005a25c`
- name: `?InitializeServerEvents@@YAKXZ`
- size: `704`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14004ae64`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x140036e08`
- `0x140051f44`
- `0x140059f9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005a022`
- `KERNEL32!GetLastError` at `0x14005a089`
- `KERNEL32!GetLastError` at `0x14005a10b`
- `KERNEL32!GetLastError` at `0x14005a147`
- `KERNEL32!GetLastError` at `0x14005a1b7`
- `KERNEL32!GetLastError` at `0x14005a221`
- `KERNEL32!GetLastError` at `0x14005a022`
- `KERNEL32!GetLastError` at `0x14005a089`
- `KERNEL32!GetLastError` at `0x14005a10b`
- `KERNEL32!GetLastError` at `0x14005a147`
- `KERNEL32!GetLastError` at `0x14005a1b7`
- `KERNEL32!GetLastError` at `0x14005a221`
- `KERNEL32!CloseHandle` at `0x14005a18f`
- `KERNEL32!CloseHandle` at `0x14005a1f9`
- `KERNEL32!CloseHandle` at `0x14005a18f`
- `KERNEL32!CloseHandle` at `0x14005a1f9`
- `KERNEL32!CreateIoCompletionPort` at `0x14005a00a`
- `KERNEL32!CreateIoCompletionPort` at `0x14005a071`
- `KERNEL32!CreateIoCompletionPort` at `0x14005a00a`
- `KERNEL32!CreateIoCompletionPort` at `0x14005a071`

## pseudocode

```c
__int64 InitializeServerEvents(void)
{
  DWORD LastError; // ebx
  CMapDeviceId *v1; // rcx
  __int64 v2; // rdx
  unsigned int v4; // edx
  struct _SECURITY_ATTRIBUTES *v5; // rcx
  __int64 v6; // rbx
  void *v7; // rax
  DWORD v8; // edi
  void *v9; // rsi
  DWORD v10; // eax
  __int64 v11; // rbx
  HANDLE v12; // rcx
  DWORD v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-68h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-58h]
  __int128 v16; // [rsp+40h] [rbp-48h]
  unsigned int v17; // [rsp+90h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  v17 = 0;
  *(_OWORD *)hObject = 0;
  v16 = 0;
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
    v7 = CreateThreadAndRefCount(v5, v4, (unsigned int (*)(void *))FaxSendEventThread, 0, v14, &v17);
    hObject[v6] = v7;
    if ( !v7 )
      break;
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 4 )
    {
      v8 = 0;
      v9 = CreateThreadAndRefCount(v5, v4, (unsigned int (*)(void *))FaxDispatchEventThread, 0, v14, &v17);
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
  v8 = GetLastError();
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
LABEL_29:
  v11 = 0;
  do
  {
    v12 = hObject[v11];
    if ( v12
      && !CloseHandle(v12)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      WPP_SF_lll(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids,
        (unsigned int)v11,
        hObject[v11],
        v13);
    }
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < 4 );
  if ( v9
    && !CloseHandle(v9)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  return v8;
}

```

## disassembly

```asm
0x140059f9c  push    rbx
0x140059f9e  push    rbp
0x140059f9f  push    rsi
0x140059fa0  push    rdi
0x140059fa1  push    r13
0x140059fa3  push    r15
0x140059fa5  sub     rsp, 58h
0x140059fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140059fb0  lea     r15, WPP_GLOBAL_Control
0x140059fb7  lea     r13, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140059fbe  cmp     rcx, r15
0x140059fc1  jz      short loc_140059FE0
0x140059fc3  test    byte ptr [rcx+1Ch], 4
0x140059fc7  jz      short loc_140059FE0
0x140059fc9  cmp     byte ptr [rcx+19h], 5
0x140059fcd  jb      short loc_140059FE0
0x140059fcf  mov     rcx, [rcx+10h]
0x140059fd3  mov     edx, 58h ; 'X'
0x140059fd8  mov     r8, r13
0x140059fdb  call    WPP_SF_
0x140059fe0  xorps   xmm0, xmm0
0x140059fe3  mov     [rsp+88h+arg_0], 0
0x140059fee  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140059ff2  mov     r9d, 2; NumberOfConcurrentThreads
0x140059ff8  mov     rcx, rbx; FileHandle
0x140059ffb  xor     r8d, r8d; CompletionKey
0x140059ffe  xor     edx, edx; ExistingCompletionPort
0x14005a000  movups  xmmword ptr [rsp+88h+hObject], xmm0
0x14005a005  movups  [rsp+88h+var_48], xmm0
0x14005a00a  call    cs:__imp_CreateIoCompletionPort
0x14005a011  nop     dword ptr [rax+rax+00h]
0x14005a016  mov     cs:?g_hSendEventsCompPort@@3PEAXEA, rax; void * g_hSendEventsCompPort
0x14005a01d  test    rax, rax
0x14005a020  jnz     short loc_14005A063
0x14005a022  call    cs:__imp_GetLastError
0x14005a029  nop     dword ptr [rax+rax+00h]
0x14005a02e  mov     ebx, eax
0x14005a030  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a037  cmp     rcx, r15
0x14005a03a  jz      short loc_14005A05C
0x14005a03c  test    byte ptr [rcx+1Ch], 4
0x14005a040  jz      short loc_14005A05C
0x14005a042  cmp     byte ptr [rcx+19h], 2
0x14005a046  jb      short loc_14005A05C
0x14005a048  mov     edx, 59h ; 'Y'
0x14005a04d  mov     rcx, [rcx+10h]
0x14005a051  mov     r9d, ebx
0x14005a054  mov     r8, r13
0x14005a057  call    WPP_SF_d
0x14005a05c  mov     eax, ebx
0x14005a05e  jmp     loc_14005A24E
0x14005a063  mov     r9d, 1; NumberOfConcurrentThreads
0x14005a069  xor     r8d, r8d; CompletionKey
0x14005a06c  xor     edx, edx; ExistingCompletionPort
0x14005a06e  mov     rcx, rbx; FileHandle
0x14005a071  call    cs:__imp_CreateIoCompletionPort
0x14005a078  nop     dword ptr [rax+rax+00h]
0x14005a07d  mov     cs:?g_hDispatchEventsCompPort@@3PEAXEA, rax; void * g_hDispatchEventsCompPort
0x14005a084  test    rax, rax
0x14005a087  jnz     short loc_14005A0B6
0x14005a089  call    cs:__imp_GetLastError
0x14005a090  nop     dword ptr [rax+rax+00h]
0x14005a095  mov     ebx, eax
0x14005a097  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a09e  cmp     rcx, r15
0x14005a0a1  jz      short loc_14005A05C
0x14005a0a3  test    byte ptr [rcx+1Ch], 4
0x14005a0a7  jz      short loc_14005A05C
0x14005a0a9  cmp     byte ptr [rcx+19h], 2
0x14005a0ad  jb      short loc_14005A05C
0x14005a0af  mov     edx, 5Ah ; 'Z'
0x14005a0b4  jmp     short loc_14005A04D
0x14005a0b6  xor     ebx, ebx
0x14005a0b8  lea     rax, [rsp+88h+arg_0]
0x14005a0c0  xor     r9d, r9d; void *
0x14005a0c3  lea     r8, ?FaxSendEventThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x14005a0ca  mov     [rsp+88h+var_60], rax; unsigned int *
0x14005a0cf  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14005a0d4  mov     [rsp+rbx*8+88h+hObject], rax
0x14005a0d9  test    rax, rax
0x14005a0dc  jz      short loc_14005A145
0x14005a0de  inc     ebx
0x14005a0e0  cmp     ebx, 4
0x14005a0e3  jb      short loc_14005A0B8
0x14005a0e5  lea     rax, [rsp+88h+arg_0]
0x14005a0ed  xor     r9d, r9d; void *
0x14005a0f0  lea     r8, ?FaxDispatchEventThread@@YAKPEAX@Z; unsigned int (*)(void *)
0x14005a0f7  mov     [rsp+88h+var_60], rax; unsigned int *
0x14005a0fc  xor     edi, edi
0x14005a0fe  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14005a103  mov     rsi, rax
0x14005a106  test    rax, rax
0x14005a109  jnz     short loc_14005A183
0x14005a10b  call    cs:__imp_GetLastError
0x14005a112  nop     dword ptr [rax+rax+00h]
0x14005a117  mov     edi, eax
0x14005a119  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a120  cmp     rcx, r15
0x14005a123  jz      short loc_14005A183
0x14005a125  test    byte ptr [rcx+1Ch], 4
0x14005a129  jz      short loc_14005A183
0x14005a12b  cmp     byte ptr [rcx+19h], 2
0x14005a12f  jb      short loc_14005A183
0x14005a131  mov     rcx, [rcx+10h]
0x14005a135  lea     edx, [rsi+5Ch]
0x14005a138  mov     r9d, eax
0x14005a13b  mov     r8, r13
0x14005a13e  call    WPP_SF_d
0x14005a143  jmp     short loc_14005A183
0x14005a145  xor     esi, esi
0x14005a147  call    cs:__imp_GetLastError
0x14005a14e  nop     dword ptr [rax+rax+00h]
0x14005a153  mov     edi, eax
0x14005a155  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a15c  cmp     rcx, r15
0x14005a15f  jz      short loc_14005A183
0x14005a161  test    byte ptr [rcx+1Ch], 4
0x14005a165  jz      short loc_14005A183
0x14005a167  cmp     byte ptr [rcx+19h], 2
0x14005a16b  jb      short loc_14005A183
0x14005a16d  mov     rcx, [rcx+10h]
0x14005a171  lea     edx, [rsi+5Bh]
0x14005a174  mov     r9d, ebx
0x14005a177  mov     [rsp+88h+var_68], eax
0x14005a17b  mov     r8, r13
0x14005a17e  call    WPP_SF_dd
0x14005a183  xor     ebx, ebx
0x14005a185  mov     rcx, [rsp+rbx*8+88h+hObject]; hObject
0x14005a18a  test    rcx, rcx
0x14005a18d  jz      short loc_14005A1EA
0x14005a18f  call    cs:__imp_CloseHandle
0x14005a196  nop     dword ptr [rax+rax+00h]
0x14005a19b  test    eax, eax
0x14005a19d  jnz     short loc_14005A1EA
0x14005a19f  mov     rax, cs:WPP_GLOBAL_Control
0x14005a1a6  cmp     rax, r15
0x14005a1a9  jz      short loc_14005A1EA
0x14005a1ab  test    byte ptr [rax+1Ch], 4
0x14005a1af  jz      short loc_14005A1EA
0x14005a1b1  cmp     byte ptr [rax+19h], 2
0x14005a1b5  jb      short loc_14005A1EA
0x14005a1b7  call    cs:__imp_GetLastError
0x14005a1be  nop     dword ptr [rax+rax+00h]
0x14005a1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a1ca  mov     edx, 5Dh ; ']'
0x14005a1cf  mov     dword ptr [rsp+88h+var_60], eax
0x14005a1d3  mov     r9d, ebx
0x14005a1d6  mov     eax, dword ptr [rsp+rbx*8+88h+hObject]
0x14005a1da  mov     r8, r13
0x14005a1dd  mov     [rsp+88h+var_68], eax
0x14005a1e1  mov     rcx, [rcx+10h]
0x14005a1e5  call    WPP_SF_lll
0x14005a1ea  inc     ebx
0x14005a1ec  cmp     ebx, 4
0x14005a1ef  jb      short loc_14005A185
0x14005a1f1  test    rsi, rsi
0x14005a1f4  jz      short loc_14005A24C
0x14005a1f6  mov     rcx, rsi; hObject
0x14005a1f9  call    cs:__imp_CloseHandle
0x14005a200  nop     dword ptr [rax+rax+00h]
0x14005a205  test    eax, eax
0x14005a207  jnz     short loc_14005A24C
0x14005a209  mov     rax, cs:WPP_GLOBAL_Control
0x14005a210  cmp     rax, r15
0x14005a213  jz      short loc_14005A24C
0x14005a215  test    byte ptr [rax+1Ch], 4
0x14005a219  jz      short loc_14005A24C
0x14005a21b  cmp     byte ptr [rax+19h], 2
0x14005a21f  jb      short loc_14005A24C
0x14005a221  call    cs:__imp_GetLastError
0x14005a228  nop     dword ptr [rax+rax+00h]
0x14005a22d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a234  mov     r9d, esi
0x14005a237  mov     edx, 5Eh ; '^'
0x14005a23c  mov     [rsp+88h+var_68], eax
0x14005a240  mov     r8, r13
0x14005a243  mov     rcx, [rcx+10h]
0x14005a247  call    WPP_SF_dd
0x14005a24c  mov     eax, edi
0x14005a24e  add     rsp, 58h
0x14005a252  pop     r15
0x14005a254  pop     r13
0x14005a256  pop     rdi
0x14005a257  pop     rsi
0x14005a258  pop     rbp
0x14005a259  pop     rbx
0x14005a25a  retn
```
