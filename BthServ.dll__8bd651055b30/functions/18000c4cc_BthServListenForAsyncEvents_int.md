# BthServListenForAsyncEvents(int)

- ea: `0x18000c4cc`
- end: `0x18000c790`
- name: `?BthServListenForAsyncEvents@@YAHH@Z`
- size: `708`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cf7c`

## callees

- `0x18000c4cc`
- `0x1800110fc`
- `0x180011194`
- `0x18001140c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c59c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c607`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c59c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c607`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c694`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c694`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c67c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c67c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c72d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c72d`

## pseudocode

```c
__int64 __fastcall BthServListenForAsyncEvents(int a1)
{
  _BYTE *v2; // rax
  char v3; // bl
  bool v4; // dl
  bool v5; // dl
  HANDLE EventW; // rsi
  bool v7; // dl
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  bool v10; // dl
  bool v11; // r8
  bool v12; // dl
  DWORD dwCreationFlags; // [rsp+20h] [rbp-68h]
  int lpThreadId; // [rsp+28h] [rbp-60h]

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  v5 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)v2 + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5),
      dwCreationFlags,
      lpThreadId,
      107,
      (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v8 = 1;
    goto LABEL_51;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( hEvent )
    {
      hObject = CreateThread(0, 0, BthServAsyncThread, EventW, 0, (LPDWORD)&hObject + 2);
      if ( hObject )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        v8 = 1;
        v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        goto LABEL_49;
      }
      v9 = WPP_GLOBAL_Control;
      v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v10 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_48:
        v8 = 0;
LABEL_49:
        CloseHandle(EventW);
        v2 = WPP_GLOBAL_Control;
        goto LABEL_51;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v10 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_48;
    }
    WPP_RECORDER_AND_TRACE_SF_s(v9[2], v10, v11, v9[5]);
    goto LABEL_48;
  }
  v2 = WPP_GLOBAL_Control;
  v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  v8 = 0;
LABEL_51:
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || v2[25] < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v2 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5));
  return v8;
}

```

## disassembly

```asm
0x18000c4cc  push    rbx
0x18000c4ce  push    rbp
0x18000c4cf  push    rsi
0x18000c4d0  push    rdi
0x18000c4d1  push    r14
0x18000c4d3  push    r15
0x18000c4d5  sub     rsp, 58h
0x18000c4d9  mov     edi, ecx
0x18000c4db  mov     rax, cs:WPP_GLOBAL_Control
0x18000c4e2  lea     rbp, WPP_GLOBAL_Control
0x18000c4e9  mov     ebx, 1
0x18000c4ee  cmp     rax, rbp
0x18000c4f1  jz      short loc_18000C4FD
0x18000c4f3  cmp     byte ptr [rax+19h], 5
0x18000c4f7  jb      short loc_18000C4FD
0x18000c4f9  mov     dl, bl
0x18000c4fb  jmp     short loc_18000C4FF
0x18000c4fd  xor     dl, dl
0x18000c4ff  lea     r14, WPP_RECORDER_INITIALIZED
0x18000c506  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c50d  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000c514  setnz   r8b
0x18000c518  test    dl, dl
0x18000c51a  jnz     short loc_18000C521
0x18000c51c  test    r8b, r8b
0x18000c51f  jz      short loc_18000C541
0x18000c521  mov     r9, [rax+28h]
0x18000c525  mov     rcx, [rax+10h]
0x18000c529  mov     [rsp+88h+var_50], r15
0x18000c52e  mov     [rsp+88h+var_58], 6Ah ; 'j'
0x18000c535  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c53a  mov     rax, cs:WPP_GLOBAL_Control
0x18000c541  cmp     rax, rbp
0x18000c544  jz      short loc_18000C550
0x18000c546  cmp     byte ptr [rax+19h], 4
0x18000c54a  jb      short loc_18000C550
0x18000c54c  mov     dl, bl
0x18000c54e  jmp     short loc_18000C552
0x18000c550  xor     dl, dl
0x18000c552  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c559  setnz   r8b
0x18000c55d  test    dl, dl
0x18000c55f  jnz     short loc_18000C566
0x18000c561  test    r8b, r8b
0x18000c564  jz      short loc_18000C58A
0x18000c566  mov     r9, [rax+28h]
0x18000c56a  mov     rcx, [rax+10h]
0x18000c56e  mov     dword ptr [rsp+88h+var_40], edi
0x18000c572  mov     [rsp+88h+var_50], r15
0x18000c577  mov     [rsp+88h+var_58], 6Bh ; 'k'
0x18000c57e  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000c583  mov     rax, cs:WPP_GLOBAL_Control
0x18000c58a  test    edi, edi
0x18000c58c  jz      loc_18000C73C
0x18000c592  xor     r9d, r9d; lpName
0x18000c595  xor     r8d, r8d; bInitialState
0x18000c598  xor     edx, edx; bManualReset
0x18000c59a  xor     ecx, ecx; lpEventAttributes
0x18000c59c  call    cs:__imp_CreateEventW
0x18000c5a2  mov     rsi, rax
0x18000c5a5  test    rax, rax
0x18000c5a8  jnz     short loc_18000C5FD
0x18000c5aa  mov     rax, cs:WPP_GLOBAL_Control
0x18000c5b1  cmp     rax, rbp
0x18000c5b4  jz      short loc_18000C5C0
0x18000c5b6  cmp     byte ptr [rax+19h], 3
0x18000c5ba  jb      short loc_18000C5C0
0x18000c5bc  mov     dl, bl
0x18000c5be  jmp     short loc_18000C5C2
0x18000c5c0  xor     dl, dl
0x18000c5c2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c5c9  setnz   r8b
0x18000c5cd  test    dl, dl
0x18000c5cf  jnz     short loc_18000C5D6
0x18000c5d1  test    r8b, r8b
0x18000c5d4  jz      short loc_18000C5F6
0x18000c5d6  mov     r9, [rax+28h]
0x18000c5da  mov     rcx, [rax+10h]
0x18000c5de  mov     [rsp+88h+var_50], r15
0x18000c5e3  mov     [rsp+88h+var_58], 6Ch ; 'l'
0x18000c5ea  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c5ef  mov     rax, cs:WPP_GLOBAL_Control
0x18000c5f6  xor     edi, edi
0x18000c5f8  jmp     loc_18000C73E
0x18000c5fd  xor     r9d, r9d; lpName
0x18000c600  xor     r8d, r8d; bInitialState
0x18000c603  mov     edx, ebx; bManualReset
0x18000c605  xor     ecx, ecx; lpEventAttributes
0x18000c607  call    cs:__imp_CreateEventW
0x18000c60d  mov     cs:hEvent, rax
0x18000c614  test    rax, rax
0x18000c617  jnz     short loc_18000C65A
0x18000c619  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c620  cmp     rcx, rbp
0x18000c623  jz      short loc_18000C62F
0x18000c625  cmp     byte ptr [rcx+19h], 3
0x18000c629  jb      short loc_18000C62F
0x18000c62b  mov     dl, bl
0x18000c62d  jmp     short loc_18000C631
0x18000c62f  xor     dl, dl
0x18000c631  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c638  setnz   r8b
0x18000c63c  test    dl, dl
0x18000c63e  jnz     short loc_18000C649
0x18000c640  test    r8b, r8b
0x18000c643  jz      loc_18000C728
0x18000c649  mov     [rsp+88h+var_50], r15
0x18000c64e  mov     [rsp+88h+var_58], 6Dh ; 'm'
0x18000c655  jmp     loc_18000C71B
0x18000c65a  lea     rax, hObject+8
0x18000c661  mov     r9, rsi; lpParameter
0x18000c664  mov     [rsp+88h+lpThreadId], rax; lpThreadId
0x18000c669  lea     r8, ?BthServAsyncThread@@YAKPEAX@Z; lpStartAddress
0x18000c670  xor     edx, edx; dwStackSize
0x18000c672  mov     [rsp+88h+dwCreationFlags], 0; dwCreationFlags
0x18000c67a  xor     ecx, ecx; lpThreadAttributes
0x18000c67c  call    cs:__imp_CreateThread
0x18000c682  mov     qword ptr cs:hObject, rax
0x18000c689  test    rax, rax
0x18000c68c  jz      short loc_18000C6E3
0x18000c68e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c691  mov     rcx, rsi; hHandle
0x18000c694  call    cs:__imp_WaitForSingleObject
0x18000c69a  mov     edi, ebx
0x18000c69c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6a3  cmp     rcx, rbp
0x18000c6a6  jz      short loc_18000C6B2
0x18000c6a8  cmp     byte ptr [rcx+19h], 3
0x18000c6ac  jb      short loc_18000C6B2
0x18000c6ae  mov     dl, bl
0x18000c6b0  jmp     short loc_18000C6B4
0x18000c6b2  xor     dl, dl
0x18000c6b4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c6bb  setnz   r8b
0x18000c6bf  test    dl, dl
0x18000c6c1  jnz     short loc_18000C6C8
0x18000c6c3  test    r8b, r8b
0x18000c6c6  jz      short loc_18000C72A
0x18000c6c8  mov     r9, [rcx+28h]
0x18000c6cc  mov     rcx, [rcx+10h]
0x18000c6d0  mov     [rsp+88h+var_50], r15
0x18000c6d5  mov     [rsp+88h+var_58], 6Eh ; 'n'
0x18000c6dc  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c6e1  jmp     short loc_18000C72A
0x18000c6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6ea  cmp     rcx, rbp
0x18000c6ed  jz      short loc_18000C6F9
0x18000c6ef  cmp     byte ptr [rcx+19h], 3
0x18000c6f3  jb      short loc_18000C6F9
0x18000c6f5  mov     dl, bl
0x18000c6f7  jmp     short loc_18000C6FB
0x18000c6f9  xor     dl, dl
0x18000c6fb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c702  setnz   r8b
0x18000c706  test    dl, dl
0x18000c708  jnz     short loc_18000C70F
0x18000c70a  test    r8b, r8b
0x18000c70d  jz      short loc_18000C728
0x18000c70f  mov     [rsp+88h+var_50], r15
0x18000c714  mov     [rsp+88h+var_58], 6Fh ; 'o'
0x18000c71b  mov     r9, [rcx+28h]
0x18000c71f  mov     rcx, [rcx+10h]
0x18000c723  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c728  xor     edi, edi
0x18000c72a  mov     rcx, rsi; hObject
0x18000c72d  call    cs:__imp_CloseHandle
0x18000c733  mov     rax, cs:WPP_GLOBAL_Control
0x18000c73a  jmp     short loc_18000C73E
0x18000c73c  mov     edi, ebx
0x18000c73e  cmp     rax, rbp
0x18000c741  jz      short loc_18000C749
0x18000c743  cmp     byte ptr [rax+19h], 5
0x18000c747  jnb     short loc_18000C74B
0x18000c749  xor     bl, bl
0x18000c74b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c752  setnz   r8b
0x18000c756  test    bl, bl
0x18000c758  jnz     short loc_18000C75F
0x18000c75a  test    r8b, r8b
0x18000c75d  jz      short loc_18000C781
0x18000c75f  mov     r9, [rax+28h]
0x18000c763  mov     dl, bl
0x18000c765  mov     ecx, edi
0x18000c767  mov     [rsp+88h+var_40], rcx
0x18000c76c  mov     rcx, [rax+10h]
0x18000c770  mov     [rsp+88h+var_50], r15
0x18000c775  mov     [rsp+88h+var_58], 70h ; 'p'
0x18000c77c  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000c781  mov     eax, edi
0x18000c783  add     rsp, 58h
0x18000c787  pop     r15
0x18000c789  pop     r14
0x18000c78b  pop     rdi
0x18000c78c  pop     rsi
0x18000c78d  pop     rbp
0x18000c78e  pop     rbx
0x18000c78f  retn
```
