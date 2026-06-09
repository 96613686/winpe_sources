# SerializeToFile<_RPC_COOKIE>(void *,void (*)(void *,_RPC_COOKIE *),_GUID const *,_RPC_COOKIE *)

- ea: `0x180149220`
- end: `0x1801494bb`
- name: `??$SerializeToFile@U_RPC_COOKIE@@@@YAJPEAXP6AX0PEAU_RPC_COOKIE@@@ZPEBU_GUID@@1@Z`
- size: `667`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801c9384`

## callees

- `0x180020fc4`
- `0x1800701d0`
- `0x180149220`
- `0x1801494c4`
- `0x18014a7a0`
- `0x1801c9b24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180149394`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801493f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180149394`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801493f4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180149425`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180149425`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180149348`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180149348`
- `RPCRT4!MesHandleFree` at `0x180149474`
- `RPCRT4!MesHandleFree` at `0x180149474`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1801492ca`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1801492ca`

## pseudocode

```c
__int64 __fastcall SerializeToFile<_RPC_COOKIE>(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4)
{
  signed int v6; // ebx
  RPC_STATUS v7; // eax
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // rcx
  int LastError; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  char *v19; // [rsp+30h] [rbp-40h] BYREF
  handle_t pHandle; // [rsp+38h] [rbp-38h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-30h] BYREF
  unsigned int pEncodedSize; // [rsp+48h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-24h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v25; // [rsp+60h] [rbp-10h]

  HIDWORD(v19) = 0;
  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  NumberOfBytesWritten = 0;
  v25 = 0;
  Buffer = 0;
  if ( hFile )
  {
    if ( hFile == (HANDLE)-1LL )
    {
      v6 = -2147024809;
      HIDWORD(v19) = 81;
    }
    else if ( a4 )
    {
      v7 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v6 >= 0 )
      {
        v8 = InvokeCoder<_RPC_COOKIE>(pHandle, &RPC_COOKIE_Encode, a4);
        v6 = v8;
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        if ( v6 >= 0 )
        {
          Buffer = xmmword_180229E18;
          LODWORD(v25) = ComputeCheckSum(v9, (unsigned __int8 *)pBuffer, pEncodedSize);
          if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
          {
            LastError = WxGetLastError(v10);
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
            HIDWORD(v19) = 102;
            if ( v6 >= 0 )
              v6 = -2147418113;
          }
          else if ( WriteFile(hFile, &Buffer, 0x18u, &NumberOfBytesWritten, 0) )
          {
            if ( NumberOfBytesWritten == 24 )
            {
              if ( WriteFile(hFile, pBuffer, pEncodedSize, &NumberOfBytesWritten, 0) )
              {
                if ( SetEndOfFile(hFile) )
                {
                  if ( NumberOfBytesWritten == pEncodedSize )
                  {
                    v6 = 0;
                  }
                  else
                  {
                    v6 = -2147418113;
                    HIDWORD(v19) = 115;
                  }
                }
                else
                {
                  v17 = WxGetLastError(v16);
                  v6 = v17;
                  if ( v17 > 0 )
                    v6 = (unsigned __int16)v17 | 0x80070000;
                  HIDWORD(v19) = 112;
                  if ( v6 >= 0 )
                    v6 = -2147418113;
                }
              }
              else
              {
                v15 = WxGetLastError(v14);
                v6 = v15;
                if ( v15 > 0 )
                  v6 = (unsigned __int16)v15 | 0x80070000;
                HIDWORD(v19) = 111;
                if ( v6 >= 0 )
                  v6 = -2147418113;
              }
            }
            else
            {
              v6 = -2147418113;
              HIDWORD(v19) = 105;
            }
          }
          else
          {
            v13 = WxGetLastError(v12);
            v6 = v13;
            if ( v13 > 0 )
              v6 = (unsigned __int16)v13 | 0x80070000;
            HIDWORD(v19) = 103;
            if ( v6 >= 0 )
              v6 = -2147418113;
          }
        }
        else
        {
          HIDWORD(v19) = 90;
        }
      }
      else
      {
        HIDWORD(v19) = 89;
      }
    }
    else
    {
      v6 = -2147024809;
      HIDWORD(v19) = 84;
    }
  }
  else
  {
    v6 = -2147024809;
    HIDWORD(v19) = 80;
  }
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  if ( pBuffer )
  {
    v19 = pBuffer;
    WxHeapFree<_WX_AVL_TABLE>(&v19);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180149220  mov     [rsp-18h+arg_8], rbx
0x180149225  mov     [rsp-18h+arg_10], rsi
0x18014922a  push    rbp
0x18014922b  push    rdi
0x18014922c  push    r15
0x18014922e  mov     rbp, rsp
0x180149231  sub     rsp, 70h
0x180149235  mov     rax, cs:__security_cookie
0x18014923c  xor     rax, rsp
0x18014923f  mov     [rbp+var_8], rax
0x180149243  xor     eax, eax
0x180149245  mov     dword ptr [rbp+var_40+4], 0
0x18014924c  mov     [rbp+pBuffer], 0
0x180149254  xorps   xmm0, xmm0
0x180149257  mov     [rbp+pEncodedSize], 0
0x18014925e  mov     rsi, r9
0x180149261  mov     [rbp+pHandle], 0
0x180149269  mov     rdi, rcx
0x18014926c  mov     [rbp+NumberOfBytesWritten], 0
0x180149273  mov     [rbp+var_10], rax
0x180149277  movups  [rbp+Buffer], xmm0
0x18014927b  test    rcx, rcx
0x18014927e  jnz     short loc_180149291
0x180149280  mov     ebx, 80070057h
0x180149285  mov     dword ptr [rbp+var_40+4], 50h ; 'P'
0x18014928c  jmp     loc_18014946B
0x180149291  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180149295  jnz     short loc_1801492A8
0x180149297  mov     ebx, 80070057h
0x18014929c  mov     dword ptr [rbp+var_40+4], 51h ; 'Q'
0x1801492a3  jmp     loc_18014946B
0x1801492a8  test    rsi, rsi
0x1801492ab  jnz     short loc_1801492BE
0x1801492ad  mov     ebx, 80070057h
0x1801492b2  mov     dword ptr [rbp+var_40+4], 54h ; 'T'
0x1801492b9  jmp     loc_18014946B
0x1801492be  lea     r8, [rbp+pHandle]; pHandle
0x1801492c2  lea     rdx, [rbp+pEncodedSize]; pEncodedSize
0x1801492c6  lea     rcx, [rbp+pBuffer]; pBuffer
0x1801492ca  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x1801492d0  mov     ebx, eax
0x1801492d2  mov     r15d, 80070000h
0x1801492d8  test    eax, eax
0x1801492da  jle     short loc_1801492E2
0x1801492dc  movzx   ebx, ax
0x1801492df  or      ebx, r15d
0x1801492e2  test    ebx, ebx
0x1801492e4  jns     short loc_1801492F2
0x1801492e6  mov     dword ptr [rbp+var_40+4], 59h ; 'Y'
0x1801492ed  jmp     loc_18014946B
0x1801492f2  mov     rcx, [rbp+pHandle]
0x1801492f6  lea     rdx, RPC_COOKIE_Encode
0x1801492fd  mov     r8, rsi
0x180149300  call    ??$InvokeCoder@U_RPC_COOKIE@@@@YAJPEAXP6AX0PEAU_RPC_COOKIE@@@Z1@Z; InvokeCoder<_RPC_COOKIE>(void *,void (*)(void *,_RPC_COOKIE *),_RPC_COOKIE *)
0x180149305  mov     ebx, eax
0x180149307  test    eax, eax
0x180149309  jle     short loc_180149311
0x18014930b  movzx   ebx, ax
0x18014930e  or      ebx, r15d
0x180149311  test    ebx, ebx
0x180149313  jns     short loc_180149321
0x180149315  mov     dword ptr [rbp+var_40+4], 5Ah ; 'Z'
0x18014931c  jmp     loc_18014946B
0x180149321  movups  xmm0, cs:xmmword_180229E18
0x180149328  mov     rdx, [rbp+pBuffer]; unsigned __int8 *
0x18014932c  mov     r8d, [rbp+pEncodedSize]; unsigned int
0x180149330  movdqu  [rbp+Buffer], xmm0
0x180149335  call    ?ComputeCheckSum@@YAKKPEAEK@Z; ComputeCheckSum(ulong,uchar *,ulong)
0x18014933a  xor     r9d, r9d; dwMoveMethod
0x18014933d  mov     dword ptr [rbp+var_10], eax
0x180149340  mov     rcx, rdi; hFile
0x180149343  xor     r8d, r8d; lpDistanceToMoveHigh
0x180149346  xor     edx, edx; lDistanceToMove
0x180149348  call    cs:__imp_SetFilePointer
0x18014934e  cmp     eax, 0FFFFFFFFh
0x180149351  jnz     short loc_18014937A
0x180149353  call    WxGetLastError
0x180149358  mov     ebx, eax
0x18014935a  test    eax, eax
0x18014935c  jle     short loc_180149364
0x18014935e  movzx   ebx, ax
0x180149361  or      ebx, r15d
0x180149364  test    ebx, ebx
0x180149366  mov     dword ptr [rbp+var_40+4], 66h ; 'f'
0x18014936d  mov     eax, 8000FFFFh
0x180149372  cmovns  ebx, eax
0x180149375  jmp     loc_18014946B
0x18014937a  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18014937e  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180149387  mov     r8d, 18h; nNumberOfBytesToWrite
0x18014938d  lea     rdx, [rbp+Buffer]; lpBuffer
0x180149391  mov     rcx, rdi; hFile
0x180149394  call    cs:__imp_WriteFile
0x18014939a  test    eax, eax
0x18014939c  jnz     short loc_1801493C5
0x18014939e  call    WxGetLastError
0x1801493a3  mov     ebx, eax
0x1801493a5  test    eax, eax
0x1801493a7  jle     short loc_1801493AF
0x1801493a9  movzx   ebx, ax
0x1801493ac  or      ebx, r15d
0x1801493af  test    ebx, ebx
0x1801493b1  mov     dword ptr [rbp+var_40+4], 67h ; 'g'
0x1801493b8  mov     eax, 8000FFFFh
0x1801493bd  cmovns  ebx, eax
0x1801493c0  jmp     loc_18014946B
0x1801493c5  cmp     [rbp+NumberOfBytesWritten], 18h
0x1801493c9  jz      short loc_1801493DC
0x1801493cb  mov     ebx, 8000FFFFh
0x1801493d0  mov     dword ptr [rbp+var_40+4], 69h ; 'i'
0x1801493d7  jmp     loc_18014946B
0x1801493dc  mov     r8d, [rbp+pEncodedSize]; nNumberOfBytesToWrite
0x1801493e0  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801493e4  mov     rdx, [rbp+pBuffer]; lpBuffer
0x1801493e8  mov     rcx, rdi; hFile
0x1801493eb  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1801493f4  call    cs:__imp_WriteFile
0x1801493fa  test    eax, eax
0x1801493fc  jnz     short loc_180149422
0x1801493fe  call    WxGetLastError
0x180149403  mov     ebx, eax
0x180149405  test    eax, eax
0x180149407  jle     short loc_18014940F
0x180149409  movzx   ebx, ax
0x18014940c  or      ebx, r15d
0x18014940f  test    ebx, ebx
0x180149411  mov     dword ptr [rbp+var_40+4], 6Fh ; 'o'
0x180149418  mov     eax, 8000FFFFh
0x18014941d  cmovns  ebx, eax
0x180149420  jmp     short loc_18014946B
0x180149422  mov     rcx, rdi; hFile
0x180149425  call    cs:__imp_SetEndOfFile
0x18014942b  test    eax, eax
0x18014942d  jnz     short loc_180149453
0x18014942f  call    WxGetLastError
0x180149434  mov     ebx, eax
0x180149436  test    eax, eax
0x180149438  jle     short loc_180149440
0x18014943a  movzx   ebx, ax
0x18014943d  or      ebx, r15d
0x180149440  test    ebx, ebx
0x180149442  mov     dword ptr [rbp+var_40+4], 70h ; 'p'
0x180149449  mov     eax, 8000FFFFh
0x18014944e  cmovns  ebx, eax
0x180149451  jmp     short loc_18014946B
0x180149453  mov     eax, [rbp+pEncodedSize]
0x180149456  cmp     [rbp+NumberOfBytesWritten], eax
0x180149459  jz      short loc_180149469
0x18014945b  mov     ebx, 8000FFFFh
0x180149460  mov     dword ptr [rbp+var_40+4], 73h ; 's'
0x180149467  jmp     short loc_18014946B
0x180149469  xor     ebx, ebx
0x18014946b  mov     rcx, [rbp+pHandle]; Handle
0x18014946f  test    rcx, rcx
0x180149472  jz      short loc_180149482
0x180149474  call    cs:__imp_MesHandleFree
0x18014947a  mov     [rbp+pHandle], 0
0x180149482  mov     rax, [rbp+pBuffer]
0x180149486  test    rax, rax
0x180149489  jz      short loc_180149498
0x18014948b  lea     rcx, [rbp+var_40]
0x18014948f  mov     [rbp+var_40], rax
0x180149493  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x180149498  mov     eax, ebx
0x18014949a  mov     rcx, [rbp+var_8]
0x18014949e  xor     rcx, rsp; StackCookie
0x1801494a1  call    __security_check_cookie
0x1801494a6  lea     r11, [rsp+70h+var_s0]
0x1801494ab  mov     rbx, [r11+28h]
0x1801494af  mov     rsi, [r11+30h]
0x1801494b3  mov     rsp, r11
0x1801494b6  pop     r15
0x1801494b8  pop     rdi
0x1801494b9  pop     rbp
0x1801494ba  retn
```
