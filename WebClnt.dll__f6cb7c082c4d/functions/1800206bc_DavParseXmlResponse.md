# DavParseXmlResponse

- ea: `0x1800206bc`
- end: `0x180020974`
- name: `DavParseXmlResponse`
- size: `696`
- prototype: `__int64 __fastcall(HINTERNET hRequest, _QWORD *hMem, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000d9e4`
- `0x18001c6e8`
- `0x180020c1c`

## callees

- `0x18000b7dc`
- `0x1800206bc`
- `0x1800283fc`
- `0x180028440`
- `0x180028584`
- `0x180028680`
- `0x18002cf62`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002072e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002081f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002072e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002081f`
- `KERNEL32!LocalFree` at `0x180020868`
- `KERNEL32!LocalFree` at `0x180020868`
- `KERNEL32!LocalAlloc` at `0x180020720`
- `KERNEL32!LocalAlloc` at `0x180020720`
- `WINHTTP!WinHttpReadData` at `0x180020770`
- `WINHTTP!WinHttpReadData` at `0x180020811`
- `WINHTTP!WinHttpReadData` at `0x180020770`
- `WINHTTP!WinHttpReadData` at `0x180020811`

## pseudocode

```c
__int64 __fastcall DavParseXmlResponse(HINTERNET hRequest, _QWORD *hMem, __int64 a3)
{
  HLOCAL v5; // rax
  void *v6; // r15
  DWORD LastError; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // r14d
  BOOL i; // eax
  _QWORD *v13; // rcx
  __int64 v14; // r9
  unsigned int v15; // r12d
  unsigned int v16; // eax
  __int64 v18; // rbx
  _QWORD *v19; // r14
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // [rsp+30h] [rbp-89h] BYREF
  __int64 v24; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v25[208]; // [rsp+40h] [rbp-79h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+134h] [rbp+7Bh]
  int v29; // [rsp+138h] [rbp+7Fh] BYREF

  v28 = HIDWORD(a3);
  dwNumberOfBytesRead = 0;
  v29 = 0;
  v24 = 0;
  v23 = 0;
  memset_0(v25, 0, 0xA0u);
  v5 = LocalAlloc(0x40u, 0x1000u);
  v6 = v5;
  if ( v5 )
  {
    v11 = 0;
    for ( i = WinHttpReadData(hRequest, v5, 0x1000u, &dwNumberOfBytesRead);
          ;
          i = WinHttpReadData(hRequest, v6, 0x1000u, &dwNumberOfBytesRead) )
    {
      if ( !i )
      {
        LastError = GetLastError();
        v8 = LastError;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 63;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids,
          dwNumberOfBytesRead);
        v13 = WPP_GLOBAL_Control;
      }
      v11 += dwNumberOfBytesRead;
      v14 = *(unsigned int *)&DavFileAttributesLimitInBytes;
      if ( v11 > *(_DWORD *)&DavFileAttributesLimitInBytes )
        break;
      v15 = dwNumberOfBytesRead == 0;
      v16 = DavPushData((__int64)v6, &v24, (LPVOID *)&v23, dwNumberOfBytesRead, v15);
      v8 = v16;
      if ( v16 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v22 = 66;
          v14 = v16;
          goto LABEL_38;
        }
        goto LABEL_18;
      }
      if ( v15 )
      {
        v18 = v23;
        if ( v23 )
        {
          v19 = v25;
          if ( hMem )
            v19 = hMem;
          memset_0(v19, 0, 0xA0u);
          v20 = v24;
          v19[9] = v19 + 8;
          v19[8] = v19 + 8;
          v21 = DavParseData((__int64)v19, v20, v18, &v29);
          v8 = v21;
          if ( v21 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v21);
            DavFinalizeFileAttributesList((char *)v19, 0);
            goto LABEL_18;
          }
          if ( !hMem )
            DavFinalizeFileAttributesList((char *)v19, 0);
        }
        v8 = 0;
        goto LABEL_18;
      }
    }
    v8 = 58;
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v22 = 65;
LABEL_38:
      WPP_SF_d(v13[2], v22, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v14);
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 62;
LABEL_17:
      WPP_SF_d(v9[2], v10, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, LastError);
    }
  }
LABEL_18:
  DavCloseContext(v24, v23);
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x1800206bc  mov     qword ptr [rsp-8+dwNumberOfBytesRead], r8
0x1800206c1  mov     [rsp-8+hRequest], rcx
0x1800206c6  push    rbp
0x1800206c7  push    rbx
0x1800206c8  push    rdi
0x1800206c9  push    r12
0x1800206cb  push    r13
0x1800206cd  push    r14
0x1800206cf  push    r15
0x1800206d1  lea     rbp, [rsp-27h]
0x1800206d6  sub     rsp, 0E0h
0x1800206dd  mov     r13, rdx
0x1800206e0  mov     [rbp+57h+dwNumberOfBytesRead], 0
0x1800206e7  mov     rbx, rcx
0x1800206ea  mov     [rbp+57h+arg_18], 0
0x1800206f1  xor     edx, edx; Val
0x1800206f3  mov     [rsp+110h+var_D8], 0
0x1800206fc  lea     rcx, [rbp+57h+var_D0]; void *
0x180020700  mov     [rsp+110h+var_E0], 0
0x180020709  mov     r8d, 0A0h; Size
0x18002070f  call    memset_0
0x180020714  mov     edi, 1000h
0x180020719  mov     ecx, 40h ; '@'; uFlags
0x18002071e  mov     edx, edi; uBytes
0x180020720  call    cs:__imp_LocalAlloc
0x180020726  mov     r15, rax
0x180020729  test    rax, rax
0x18002072c  jnz     short loc_180020760
0x18002072e  call    cs:__imp_GetLastError
0x180020734  mov     ebx, eax
0x180020736  mov     rcx, cs:WPP_GLOBAL_Control
0x18002073d  lea     rdi, WPP_GLOBAL_Control
0x180020744  cmp     rcx, rdi
0x180020747  jz      loc_180020851
0x18002074d  test    byte ptr [rcx+1Ch], 1
0x180020751  jz      loc_180020851
0x180020757  lea     edx, [r15+3Eh]
0x18002075b  jmp     loc_18002083E
0x180020760  xor     r14d, r14d
0x180020763  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180020767  mov     r8d, edi; dwNumberOfBytesToRead
0x18002076a  mov     rdx, r15; lpBuffer
0x18002076d  mov     rcx, rbx; hRequest
0x180020770  call    cs:__imp_WinHttpReadData
0x180020776  lea     rdi, WPP_GLOBAL_Control
0x18002077d  jmp     loc_180020817
0x180020782  mov     rcx, cs:WPP_GLOBAL_Control
0x180020789  cmp     rcx, rdi
0x18002078c  jz      short loc_1800207B4
0x18002078e  test    byte ptr [rcx+1Ch], 2
0x180020792  jz      short loc_1800207B4
0x180020794  mov     r9d, [rbp+57h+dwNumberOfBytesRead]
0x180020798  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18002079f  mov     rcx, [rcx+10h]
0x1800207a3  mov     edx, 40h ; '@'
0x1800207a8  call    WPP_SF_d
0x1800207ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207b4  mov     eax, [rbp+57h+dwNumberOfBytesRead]
0x1800207b7  add     r14d, eax
0x1800207ba  mov     r9d, cs:DavFileAttributesLimitInBytes
0x1800207c1  cmp     r14d, r9d
0x1800207c4  ja      loc_180020944
0x1800207ca  xor     r12d, r12d
0x1800207cd  lea     r8, [rsp+110h+var_E0]
0x1800207d2  test    eax, eax
0x1800207d4  lea     rdx, [rsp+110h+var_D8]
0x1800207d9  mov     r9d, eax
0x1800207dc  mov     rcx, r15
0x1800207df  setz    r12b
0x1800207e3  mov     [rsp+110h+var_F0], r12d
0x1800207e8  call    DavPushData
0x1800207ed  mov     ebx, eax
0x1800207ef  test    eax, eax
0x1800207f1  jnz     loc_180020920
0x1800207f7  test    r12d, r12d
0x1800207fa  jnz     loc_180020883
0x180020800  mov     rcx, [rbp+57h+hRequest]; hRequest
0x180020804  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180020808  mov     r8d, 1000h; dwNumberOfBytesToRead
0x18002080e  mov     rdx, r15; lpBuffer
0x180020811  call    cs:__imp_WinHttpReadData
0x180020817  test    eax, eax
0x180020819  jnz     loc_180020782
0x18002081f  call    cs:__imp_GetLastError
0x180020825  mov     ebx, eax
0x180020827  mov     rcx, cs:WPP_GLOBAL_Control
0x18002082e  cmp     rcx, rdi
0x180020831  jz      short loc_180020851
0x180020833  test    byte ptr [rcx+1Ch], 1
0x180020837  jz      short loc_180020851
0x180020839  mov     edx, 3Fh ; '?'
0x18002083e  mov     rcx, [rcx+10h]
0x180020842  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x180020849  mov     r9d, eax
0x18002084c  call    WPP_SF_d
0x180020851  mov     rdx, [rsp+110h+var_E0]
0x180020856  mov     rcx, [rsp+110h+var_D8]
0x18002085b  call    DavCloseContext
0x180020860  test    r15, r15
0x180020863  jz      short loc_18002086E
0x180020865  mov     rcx, r15; hMem
0x180020868  call    cs:__imp_LocalFree
0x18002086e  mov     eax, ebx
0x180020870  add     rsp, 0E0h
0x180020877  pop     r15
0x180020879  pop     r14
0x18002087b  pop     r13
0x18002087d  pop     r12
0x18002087f  pop     rdi
0x180020880  pop     rbx
0x180020881  pop     rbp
0x180020882  retn
0x180020883  mov     rbx, [rsp+110h+var_E0]
0x180020888  test    rbx, rbx
0x18002088b  jz      loc_180020919
0x180020891  test    r13, r13
0x180020894  lea     r14, [rbp+57h+var_D0]
0x180020898  mov     r8d, 0A0h; Size
0x18002089e  cmovnz  r14, r13
0x1800208a2  xor     edx, edx; Val
0x1800208a4  mov     rcx, r14; void *
0x1800208a7  call    memset_0
0x1800208ac  mov     rdx, [rsp+110h+var_D8]
0x1800208b1  lea     rax, [r14+40h]
0x1800208b5  lea     r9, [rbp+57h+arg_18]
0x1800208b9  mov     [rax+8], rax
0x1800208bd  mov     r8, rbx
0x1800208c0  mov     [rax], rax
0x1800208c3  mov     rcx, r14
0x1800208c6  call    DavParseData
0x1800208cb  mov     ebx, eax
0x1800208cd  test    eax, eax
0x1800208cf  jz      short loc_18002090A
0x1800208d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208d8  cmp     rcx, rdi
0x1800208db  jz      short loc_1800208FB
0x1800208dd  test    byte ptr [rcx+1Ch], 1
0x1800208e1  jz      short loc_1800208FB
0x1800208e3  mov     rcx, [rcx+10h]
0x1800208e7  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x1800208ee  mov     edx, 43h ; 'C'
0x1800208f3  mov     r9d, eax
0x1800208f6  call    WPP_SF_d
0x1800208fb  xor     edx, edx
0x1800208fd  mov     rcx, r14; hMem
0x180020900  call    DavFinalizeFileAttributesList
0x180020905  jmp     loc_180020851
0x18002090a  test    r13, r13
0x18002090d  jnz     short loc_180020919
0x18002090f  xor     edx, edx
0x180020911  mov     rcx, r14; hMem
0x180020914  call    DavFinalizeFileAttributesList
0x180020919  xor     ebx, ebx
0x18002091b  jmp     loc_180020851
0x180020920  mov     rcx, cs:WPP_GLOBAL_Control
0x180020927  cmp     rcx, rdi
0x18002092a  jz      loc_180020851
0x180020930  test    byte ptr [rcx+1Ch], 1
0x180020934  jz      loc_180020851
0x18002093a  mov     edx, 42h ; 'B'
0x18002093f  mov     r9d, eax
0x180020942  jmp     short loc_18002095F
0x180020944  mov     ebx, 3Ah ; ':'
0x180020949  cmp     rcx, rdi
0x18002094c  jz      loc_180020851
0x180020952  test    byte ptr [rcx+1Ch], 1
0x180020956  jz      loc_180020851
0x18002095c  lea     edx, [rbx+7]
0x18002095f  mov     rcx, [rcx+10h]
0x180020963  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18002096a  call    WPP_SF_d
0x18002096f  jmp     loc_180020851
```
