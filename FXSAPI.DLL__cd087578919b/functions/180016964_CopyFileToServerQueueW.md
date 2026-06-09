# CopyFileToServerQueueW

- ea: `0x180016964`
- end: `0x180016ddd`
- name: `CopyFileToServerQueueW`
- size: `1145`
- prototype: `__int64 __fastcall(__int64, void *, __int64, _WORD *, DWORD NumberOfBytesRead)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a82c`
- `0x18001ad28`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180016964`
- `0x18002bab8`
- `0x18002bb58`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180016a8b`
- `RPCRT4!NdrClientCall3` at `0x180016bdd`
- `RPCRT4!NdrClientCall3` at `0x180016caf`
- `RPCRT4!NdrClientCall3` at `0x180016a8b`
- `RPCRT4!NdrClientCall3` at `0x180016bdd`
- `RPCRT4!NdrClientCall3` at `0x180016caf`
- `KERNEL32!ReadFile` at `0x180016b54`
- `KERNEL32!ReadFile` at `0x180016b54`
- `KERNEL32!SetLastError` at `0x180016d6f`
- `KERNEL32!SetLastError` at `0x180016d89`
- `KERNEL32!SetLastError` at `0x180016d6f`
- `KERNEL32!SetLastError` at `0x180016d89`
- `KERNEL32!GetLastError` at `0x180016b64`
- `KERNEL32!GetLastError` at `0x180016b64`

## pseudocode

```c
__int64 __fastcall CopyFileToServerQueueW(__int64 a1, void *a2, __int64 a3, _WORD *a4, DWORD NumberOfBytesRead)
{
  void *v7; // r12
  DWORD Pointer; // edi
  _WORD *v9; // rdi
  __int64 i; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  DWORD LastError; // eax
  __int64 v14; // r9
  unsigned int v15; // eax
  DWORD v16; // ebx
  CLIENT_CALL_RETURN v18; // [rsp+28h] [rbp-60h]
  __int64 v19; // [rsp+90h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+98h] [rbp+10h]
  __int64 v21; // [rsp+A0h] [rbp+18h]

  v21 = a3;
  hFile = a2;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
  }
  if ( a1 && *(_DWORD *)a1 && !*(_DWORD *)(a1 + 16) )
  {
    v7 = (void *)pMemAlloc(0x4000u);
    if ( v7 )
    {
      v9 = a4;
      for ( i = 260; i; --i )
        *v9++ = 65;
      a4[259] = 0;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x44u,
                                0,
                                **(_QWORD **)(a1 + 32),
                                v21,
                                a4,
                                &v19).Pointer;
      v11 = WPP_GLOBAL_Control;
      if ( Pointer )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 16;
LABEL_32:
          v14 = Pointer;
LABEL_33:
          WPP_SF_d(v11[2], v12, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v14);
        }
      }
      else
      {
        do
        {
          NumberOfBytesRead = 0;
          if ( !ReadFile(hFile, v7, 0x4000u, &NumberOfBytesRead, 0) )
          {
            LastError = GetLastError();
            Pointer = LastError;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 17;
              v14 = LastError;
              goto LABEL_33;
            }
            goto LABEL_34;
          }
          if ( !NumberOfBytesRead )
            goto LABEL_34;
          LODWORD(v18.Pointer) = NumberOfBytesRead;
          Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x46u, 0, v19, v7, v18.Simple).Pointer;
          v11 = WPP_GLOBAL_Control;
        }
        while ( !Pointer );
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 19;
          goto LABEL_32;
        }
      }
    }
    else
    {
      Pointer = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
      }
    }
LABEL_34:
    if ( v19 )
    {
      v15 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x48u, 0, &v19).Pointer;
      v16 = v15;
      if ( v15
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v15);
      }
      if ( !Pointer )
        Pointer = v16;
    }
    if ( v7 )
      pMemFree(v7);
    if ( !Pointer )
      return 1;
    SetLastError(Pointer);
  }
  else
  {
    SetLastError(6u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016964  mov     rax, rsp
0x180016967  mov     [rax+20h], rbx
0x18001696b  mov     [rax+18h], r8
0x18001696f  mov     [rax+10h], rdx
0x180016973  push    rsi
0x180016974  push    rdi
0x180016975  push    r12
0x180016977  push    r13
0x180016979  push    r15
0x18001697b  sub     rsp, 60h
0x18001697f  mov     r13, r9
0x180016982  mov     rbx, rcx
0x180016985  xor     esi, esi
0x180016987  mov     [rax+8], rsi
0x18001698b  lea     r15, WPP_GLOBAL_Control
0x180016992  mov     rcx, cs:WPP_GLOBAL_Control
0x180016999  cmp     rcx, r15
0x18001699c  jz      short loc_1800169C0
0x18001699e  test    dword ptr [rcx+1Ch], 1000h
0x1800169a5  jz      short loc_1800169C0
0x1800169a7  cmp     byte ptr [rcx+19h], 5
0x1800169ab  jb      short loc_1800169C0
0x1800169ad  lea     edx, [rsi+0Ch]
0x1800169b0  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x1800169b7  mov     rcx, [rcx+10h]
0x1800169bb  call    WPP_SF_
0x1800169c0  test    rbx, rbx
0x1800169c3  jz      loc_180016D84
0x1800169c9  cmp     [rbx], esi
0x1800169cb  jz      loc_180016D84
0x1800169d1  cmp     [rbx+10h], esi
0x1800169d4  jnz     loc_180016D84
0x1800169da  mov     ecx, 4000h; dwBytes
0x1800169df  call    pMemAlloc
0x1800169e4  mov     r12, rax
0x1800169e7  mov     [rsp+88h+var_40], rax
0x1800169ec  test    rax, rax
0x1800169ef  jnz     short loc_180016A37
0x1800169f1  lea     edi, [rax+8]
0x1800169f4  mov     [rsp+88h+var_48], edi
0x1800169f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169ff  cmp     rcx, r15
0x180016a02  jz      loc_180016C86
0x180016a08  test    dword ptr [rcx+1Ch], 1000h
0x180016a0f  jz      loc_180016C86
0x180016a15  cmp     byte ptr [rcx+19h], 2
0x180016a19  jb      loc_180016C86
0x180016a1f  lea     edx, [rax+0Eh]
0x180016a22  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016a29  mov     rcx, [rcx+10h]
0x180016a2d  call    WPP_SF_
0x180016a32  jmp     loc_180016C86
0x180016a37  mov     eax, 41h ; 'A'
0x180016a3c  movzx   eax, ax
0x180016a3f  mov     rdi, r13
0x180016a42  mov     ecx, 104h
0x180016a47  rep stosw
0x180016a4a  mov     [r13+206h], si
0x180016a52  mov     rax, [rbx+20h]
0x180016a56  mov     [rsp+88h+var_38], rsi
0x180016a5b  lea     rcx, [rsp+88h+arg_0]
0x180016a63  mov     [rsp+88h+var_58], rcx
0x180016a68  mov     [rsp+88h+var_60], r13
0x180016a6d  mov     rcx, [rsp+88h+arg_10]
0x180016a75  mov     [rsp+88h+lpOverlapped], rcx
0x180016a7a  mov     r9, [rax]
0x180016a7d  xor     r8d, r8d; pReturnValue
0x180016a80  lea     edx, [r8+44h]; nProcNum
0x180016a84  lea     rcx, pProxyInfo; pProxyInfo
0x180016a8b  call    cs:__imp_NdrClientCall3
0x180016a92  nop     dword ptr [rax+rax+00h]
0x180016a97  mov     rdi, rax
0x180016a9a  mov     [rsp+88h+var_38], rax
0x180016a9f  mov     [rsp+88h+var_48], eax
0x180016aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aaa  jmp     short loc_180016B01
0x180016aac  mov     edi, eax
0x180016aae  mov     [rsp+88h+var_48], eax
0x180016ab2  lea     rdx, WPP_GLOBAL_Control
0x180016ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ac0  cmp     rcx, rdx
0x180016ac3  jz      short loc_180016AF3
0x180016ac5  test    dword ptr [rcx+1Ch], 1000h
0x180016acc  jz      short loc_180016AF3
0x180016ace  cmp     byte ptr [rcx+19h], 2
0x180016ad2  jb      short loc_180016AF3
0x180016ad4  mov     edx, 0Fh
0x180016ad9  mov     r9d, eax
0x180016adc  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016ae3  mov     rcx, [rcx+10h]
0x180016ae7  call    WPP_SF_d
0x180016aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180016af3  xor     esi, esi
0x180016af5  lea     r15, WPP_GLOBAL_Control
0x180016afc  mov     r12, [rsp+88h+var_40]
0x180016b01  test    edi, edi
0x180016b03  jz      short loc_180016B2F
0x180016b05  cmp     rcx, r15
0x180016b08  jz      loc_180016C86
0x180016b0e  test    dword ptr [rcx+1Ch], 1000h
0x180016b15  jz      loc_180016C86
0x180016b1b  cmp     byte ptr [rcx+19h], 2
0x180016b1f  jb      loc_180016C86
0x180016b25  mov     edx, 10h
0x180016b2a  jmp     loc_180016C73
0x180016b2f  mov     [rsp+88h+NumberOfBytesRead], esi
0x180016b36  mov     [rsp+88h+lpOverlapped], rsi; lpOverlapped
0x180016b3b  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180016b43  mov     r8d, 4000h; nNumberOfBytesToRead
0x180016b49  mov     rdx, r12; lpBuffer
0x180016b4c  mov     rcx, [rsp+88h+hFile]; hFile
0x180016b54  call    cs:__imp_ReadFile
0x180016b5b  nop     dword ptr [rax+rax+00h]
0x180016b60  test    eax, eax
0x180016b62  jnz     short loc_180016BAA
0x180016b64  call    cs:__imp_GetLastError
0x180016b6b  nop     dword ptr [rax+rax+00h]
0x180016b70  mov     edi, eax
0x180016b72  mov     [rsp+88h+var_48], eax
0x180016b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b7d  cmp     rcx, r15
0x180016b80  jz      loc_180016C86
0x180016b86  test    dword ptr [rcx+1Ch], 1000h
0x180016b8d  jz      loc_180016C86
0x180016b93  cmp     byte ptr [rcx+19h], 2
0x180016b97  jb      loc_180016C86
0x180016b9d  mov     edx, 11h
0x180016ba2  mov     r9d, eax
0x180016ba5  jmp     loc_180016C76
0x180016baa  mov     eax, [rsp+88h+NumberOfBytesRead]
0x180016bb1  test    eax, eax
0x180016bb3  jz      loc_180016C86
0x180016bb9  mov     [rsp+88h+var_38], rsi
0x180016bbe  mov     dword ptr [rsp+88h+var_60], eax
0x180016bc2  mov     [rsp+88h+lpOverlapped], r12
0x180016bc7  mov     r9, [rsp+88h+arg_0]
0x180016bcf  xor     r8d, r8d; pReturnValue
0x180016bd2  lea     edx, [r8+46h]; nProcNum
0x180016bd6  lea     rcx, pProxyInfo; pProxyInfo
0x180016bdd  call    cs:__imp_NdrClientCall3
0x180016be4  nop     dword ptr [rax+rax+00h]
0x180016be9  mov     [rsp+88h+var_38], rax
0x180016bee  mov     edi, eax
0x180016bf0  mov     [rsp+88h+var_48], eax
0x180016bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bfb  jmp     short loc_180016C52
0x180016bfd  mov     edi, eax
0x180016bff  mov     [rsp+88h+var_48], eax
0x180016c03  lea     rdx, WPP_GLOBAL_Control
0x180016c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c11  cmp     rcx, rdx
0x180016c14  jz      short loc_180016C44
0x180016c16  test    dword ptr [rcx+1Ch], 1000h
0x180016c1d  jz      short loc_180016C44
0x180016c1f  cmp     byte ptr [rcx+19h], 2
0x180016c23  jb      short loc_180016C44
0x180016c25  mov     edx, 12h
0x180016c2a  mov     r9d, eax
0x180016c2d  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016c34  mov     rcx, [rcx+10h]
0x180016c38  call    WPP_SF_d
0x180016c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c44  xor     esi, esi
0x180016c46  lea     r15, WPP_GLOBAL_Control
0x180016c4d  mov     r12, [rsp+88h+var_40]
0x180016c52  test    edi, edi
0x180016c54  jz      loc_180016B2F
0x180016c5a  cmp     rcx, r15
0x180016c5d  jz      short loc_180016C86
0x180016c5f  test    dword ptr [rcx+1Ch], 1000h
0x180016c66  jz      short loc_180016C86
0x180016c68  cmp     byte ptr [rcx+19h], 2
0x180016c6c  jb      short loc_180016C86
0x180016c6e  mov     edx, 13h
0x180016c73  mov     r9d, edi
0x180016c76  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016c7d  mov     rcx, [rcx+10h]
0x180016c81  call    WPP_SF_d
0x180016c86  cmp     [rsp+88h+arg_0], rsi
0x180016c8e  jz      loc_180016D5C
0x180016c94  mov     [rsp+88h+var_38], rsi
0x180016c99  lea     r9, [rsp+88h+arg_0]
0x180016ca1  xor     r8d, r8d; pReturnValue
0x180016ca4  lea     edx, [r8+48h]; nProcNum
0x180016ca8  lea     rcx, pProxyInfo; pProxyInfo
0x180016caf  call    cs:__imp_NdrClientCall3
0x180016cb6  nop     dword ptr [rax+rax+00h]
0x180016cbb  mov     rbx, rax
0x180016cbe  mov     [rsp+88h+var_38], rax
0x180016cc3  mov     [rsp+88h+var_44], eax
0x180016cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cce  jmp     short loc_180016D27
0x180016cd0  mov     ebx, eax
0x180016cd2  mov     [rsp+88h+var_44], eax
0x180016cd6  lea     rdx, WPP_GLOBAL_Control
0x180016cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ce4  cmp     rcx, rdx
0x180016ce7  jz      short loc_180016D17
0x180016ce9  test    dword ptr [rcx+1Ch], 1000h
0x180016cf0  jz      short loc_180016D17
0x180016cf2  cmp     byte ptr [rcx+19h], 2
0x180016cf6  jb      short loc_180016D17
0x180016cf8  mov     edx, 14h
0x180016cfd  mov     r9d, eax
0x180016d00  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016d07  mov     rcx, [rcx+10h]
0x180016d0b  call    WPP_SF_d
0x180016d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d17  lea     r15, WPP_GLOBAL_Control
0x180016d1e  mov     edi, [rsp+88h+var_48]
0x180016d22  mov     r12, [rsp+88h+var_40]
0x180016d27  test    ebx, ebx
0x180016d29  jz      short loc_180016D57
0x180016d2b  cmp     rcx, r15
0x180016d2e  jz      short loc_180016D57
0x180016d30  test    dword ptr [rcx+1Ch], 1000h
0x180016d37  jz      short loc_180016D57
0x180016d39  cmp     byte ptr [rcx+19h], 2
0x180016d3d  jb      short loc_180016D57
0x180016d3f  mov     edx, 15h
0x180016d44  mov     r9d, ebx
0x180016d47  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016d4e  mov     rcx, [rcx+10h]
0x180016d52  call    WPP_SF_d
0x180016d57  test    edi, edi
0x180016d59  cmovz   edi, ebx
0x180016d5c  test    r12, r12
0x180016d5f  jz      short loc_180016D69
0x180016d61  mov     rcx, r12; lpMem
0x180016d64  call    pMemFree
0x180016d69  test    edi, edi
0x180016d6b  jz      short loc_180016D7D
0x180016d6d  mov     ecx, edi; dwErrCode
0x180016d6f  call    cs:__imp_SetLastError
0x180016d76  nop     dword ptr [rax+rax+00h]
0x180016d7b  jmp     short loc_180016DC5
0x180016d7d  mov     eax, 1
0x180016d82  jmp     short loc_180016DC7
0x180016d84  mov     ecx, 6; dwErrCode
0x180016d89  call    cs:__imp_SetLastError
0x180016d90  nop     dword ptr [rax+rax+00h]
0x180016d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d9c  cmp     rcx, r15
0x180016d9f  jz      short loc_180016DC5
0x180016da1  test    dword ptr [rcx+1Ch], 1000h
0x180016da8  jz      short loc_180016DC5
0x180016daa  cmp     byte ptr [rcx+19h], 2
0x180016dae  jb      short loc_180016DC5
0x180016db0  mov     edx, 0Dh
0x180016db5  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x180016dbc  mov     rcx, [rcx+10h]
0x180016dc0  call    WPP_SF_
0x180016dc5  xor     eax, eax
0x180016dc7  mov     rbx, [rsp+88h+arg_18]
0x180016dcf  add     rsp, 60h
0x180016dd3  pop     r15
0x180016dd5  pop     r13
0x180016dd7  pop     r12
0x180016dd9  pop     rdi
0x180016dda  pop     rsi
0x180016ddb  retn
```
