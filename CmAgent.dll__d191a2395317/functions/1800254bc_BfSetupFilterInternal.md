# BfSetupFilterInternal

- ea: `0x1800254bc`
- end: `0x180025734`
- name: `BfSetupFilterInternal`
- size: `632`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *, LPCWSTR, void *, DWORD dwOutBufferSize)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800173f4`

## callees

- `0x180024e9c`
- `0x1800254bc`
- `0x18002573c`
- `0x180025868`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002570a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800256fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002570a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800256e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800256e6`
- `FLTLIB!FilterConnectCommunicationPort` at `0x18002563e`
- `FLTLIB!FilterConnectCommunicationPort` at `0x18002563e`
- `FLTLIB!FilterSendMessage` at `0x18002566c`
- `FLTLIB!FilterSendMessage` at `0x18002566c`
- `ntdll!RtlNtStatusToDosError` at `0x180025685`
- `ntdll!RtlNtStatusToDosError` at `0x180025685`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002551c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002551c`

## pseudocode

```c
__int64 __fastcall BfSetupFilterInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        LPCWSTR a5,
        void *a6,
        DWORD dwOutBufferSize)
{
  __int16 v7; // di
  _DWORD *v8; // rsi
  void *v9; // r12
  void *v10; // r15
  void *Src; // r13
  WCHAR *v12; // r14
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdi
  int v18; // eax
  int Token; // eax
  unsigned int v20; // eax
  NTSTATUS v21; // ecx
  signed int v22; // eax
  int lpSecurityAttributes; // [rsp+20h] [rbp-60h]
  int hPort; // [rsp+28h] [rbp-58h]
  int v26; // [rsp+30h] [rbp-50h]
  void *Block; // [rsp+60h] [rbp-20h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h] BYREF
  LPVOID lpInBuffer; // [rsp+70h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-8h] BYREF
  char v31; // [rsp+C0h] [rbp+40h]
  DWORD BytesReturned; // [rsp+D0h] [rbp+50h] BYREF
  int v33; // [rsp+D4h] [rbp+54h]

  v33 = HIDWORD(a3);
  v7 = 0;
  hObject = (HANDLE)-1LL;
  dwOutBufferSize = 0;
  v8 = 0;
  lpInBuffer = 0;
  BytesReturned = 0;
  v9 = 0;
  Block = 0;
  v10 = 0;
  v28 = 0;
  Src = 0;
  v31 = 0;
  v12 = (WCHAR *)a4;
  a6 = 0;
  if ( GetFileAttributesW(a4) == -1 )
  {
    v15 = BfpParsePath(v12);
    Src = a6;
    v16 = v15;
    if ( v15 < 0 )
    {
      v12 = 0;
      goto LABEL_24;
    }
    v17 = -1;
    v31 = 1;
    do
      ++v17;
    while ( *((_WORD *)a6 + v17) );
    v12 = 0;
    v7 = 2 * v17;
  }
  if ( !v12
    || (v18 = WcAttachFilterAndGetToken(L"bindflt", v12, 1, 0, (__int64)&Block), v9 = Block, v16 = v18, v18 >= 0) )
  {
    if ( !a5
      || (Token = WcAttachFilterAndGetToken(L"bindflt", a5, 1, 0, (__int64)&v28),
          v10 = (void *)v28,
          v16 = Token,
          Token >= 0) )
    {
      v20 = BfpConstructContainerInfoMessage(
              (int)v9,
              (int)v10,
              v13,
              v14,
              lpSecurityAttributes,
              hPort,
              v26,
              v7,
              Src,
              (__int64)&dwOutBufferSize,
              (__int64)&lpInBuffer);
      v8 = lpInBuffer;
      v16 = v20;
      if ( !v20 )
      {
        *(_DWORD *)lpInBuffer = 0;
        v16 = FilterConnectCommunicationPort(L"\\BindFltPort", 0, 0, 0, 0, &hObject);
        if ( !v16 )
        {
          v16 = FilterSendMessage(hObject, v8, dwOutBufferSize, v8, dwOutBufferSize, &BytesReturned);
          if ( !v16 )
          {
            v21 = v8[2];
            if ( v21 < 0 )
            {
              v22 = RtlNtStatusToDosError(v21);
              v16 = v22;
              if ( v22 > 0 )
                v16 = (unsigned __int16)v22 | 0x80070000;
            }
          }
        }
      }
    }
  }
  if ( v9 )
    free(v9);
  if ( v10 )
    free(v10);
  if ( v8 )
    free(v8);
LABEL_24:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v31 )
  {
    free(v12);
    free(Src);
  }
  return v16;
}

```

## disassembly

```asm
0x1800254bc  mov     rax, rsp
0x1800254bf  mov     [rax+20h], rbx
0x1800254c3  mov     [rax+18h], r8
0x1800254c7  mov     [rax+10h], rdx
0x1800254cb  mov     [rax+8], ecx
0x1800254ce  push    rbp
0x1800254cf  push    rsi
0x1800254d0  push    rdi
0x1800254d1  push    r12
0x1800254d3  push    r13
0x1800254d5  push    r14
0x1800254d7  push    r15
0x1800254d9  mov     rbp, rsp
0x1800254dc  sub     rsp, 80h
0x1800254e3  xor     edi, edi
0x1800254e5  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1800254ed  mov     rcx, r9; lpFileName
0x1800254f0  mov     [rbp+dwOutBufferSize], edi
0x1800254f3  mov     esi, edi
0x1800254f5  mov     [rbp+lpInBuffer], rdi
0x1800254f9  mov     [rbp+BytesReturned], edi
0x1800254fc  mov     r12d, edi
0x1800254ff  mov     [rbp+Block], rdi
0x180025503  mov     r15d, edi
0x180025506  mov     [rbp+var_18], rdi
0x18002550a  mov     r13d, edi
0x18002550d  mov     [rbp+arg_0], dil
0x180025511  mov     r14, r9
0x180025514  mov     [rbp+lpFileName], rdi
0x180025518  mov     [rbp+arg_28], rdi
0x18002551c  call    cs:__imp_GetFileAttributesW
0x180025523  nop     dword ptr [rax+rax+00h]
0x180025528  cmp     eax, 0FFFFFFFFh
0x18002552b  jnz     short loc_18002556E
0x18002552d  lea     r8, [rbp+arg_28]
0x180025531  mov     rcx, r14; Src
0x180025534  lea     rdx, [rbp+lpFileName]
0x180025538  call    BfpParsePath
0x18002553d  mov     r13, [rbp+arg_28]
0x180025541  mov     ebx, eax
0x180025543  test    eax, eax
0x180025545  js      short loc_180025565
0x180025547  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002554b  mov     [rbp+arg_0], 1
0x18002554f  xor     ecx, ecx
0x180025551  inc     rdi
0x180025554  cmp     [r13+rdi*2+0], cx
0x18002555a  jnz     short loc_180025551
0x18002555c  mov     r14, [rbp+lpFileName]
0x180025560  add     di, di
0x180025563  jmp     short loc_180025570
0x180025565  mov     r14, [rbp+lpFileName]
0x180025569  jmp     loc_1800256DC
0x18002556e  xor     ecx, ecx
0x180025570  test    r14, r14
0x180025573  jz      short loc_1800255A9
0x180025575  lea     rax, [rbp+Block]
0x180025579  mov     r8d, 120h
0x18002557f  mov     [rsp+80h+var_50], rax; int
0x180025584  mov     rdx, r14; lpFileName
0x180025587  mov     [rsp+80h+hPort], rcx; int
0x18002558c  lea     rcx, aBindflt; "bindflt"
0x180025593  mov     byte ptr [rsp+80h+lpSecurityAttributes], 1; int
0x180025598  call    WcAttachFilterAndGetToken
0x18002559d  mov     r12, [rbp+Block]
0x1800255a1  xor     ecx, ecx
0x1800255a3  mov     ebx, eax
0x1800255a5  test    eax, eax
0x1800255a7  js      short loc_1800255E1
0x1800255a9  mov     rdx, [rbp+arg_20]; lpFileName
0x1800255ad  test    rdx, rdx
0x1800255b0  jz      short loc_1800255E8
0x1800255b2  lea     rax, [rbp+var_18]
0x1800255b6  mov     r8d, 40h ; '@'
0x1800255bc  mov     [rsp+80h+var_50], rax; __int64
0x1800255c1  mov     [rsp+80h+hPort], rcx; __int64
0x1800255c6  lea     rcx, aBindflt; "bindflt"
0x1800255cd  mov     byte ptr [rsp+80h+lpSecurityAttributes], 1; char
0x1800255d2  call    WcAttachFilterAndGetToken
0x1800255d7  mov     r15, [rbp+var_18]
0x1800255db  mov     ebx, eax
0x1800255dd  test    eax, eax
0x1800255df  jns     short loc_1800255E8
0x1800255e1  xor     edi, edi
0x1800255e3  jmp     loc_1800256A0
0x1800255e8  lea     rax, [rbp+lpInBuffer]
0x1800255ec  mov     rdx, r15; int
0x1800255ef  mov     [rsp+80h+var_30], rax; __int64
0x1800255f4  mov     rcx, r12; int
0x1800255f7  lea     rax, [rbp+dwOutBufferSize]
0x1800255fb  mov     [rsp+80h+var_38], rax; __int64
0x180025600  mov     [rsp+80h+Src], r13; Src
0x180025605  mov     [rsp+80h+var_48], di; __int16
0x18002560a  call    BfpConstructContainerInfoMessage
0x18002560f  mov     rsi, [rbp+lpInBuffer]
0x180025613  xor     edi, edi
0x180025615  mov     ebx, eax
0x180025617  test    eax, eax
0x180025619  jnz     loc_1800256A0
0x18002561f  lea     rax, [rbp+hObject]
0x180025623  mov     [rsi], edi
0x180025625  mov     [rsp+80h+hPort], rax; hPort
0x18002562a  lea     rcx, aBindfltport; "\\BindFltPort"
0x180025631  xor     r9d, r9d; wSizeOfContext
0x180025634  mov     [rsp+80h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180025639  xor     r8d, r8d; lpContext
0x18002563c  xor     edx, edx; dwOptions
0x18002563e  call    cs:__imp_FilterConnectCommunicationPort
0x180025645  nop     dword ptr [rax+rax+00h]
0x18002564a  mov     ebx, eax
0x18002564c  test    eax, eax
0x18002564e  jnz     short loc_1800256A0
0x180025650  mov     r8d, [rbp+dwOutBufferSize]; dwInBufferSize
0x180025654  lea     rax, [rbp+BytesReturned]
0x180025658  mov     rcx, [rbp+hObject]; hPort
0x18002565c  mov     r9, rsi; lpOutBuffer
0x18002565f  mov     [rsp+80h+hPort], rax; lpBytesReturned
0x180025664  mov     rdx, rsi; lpInBuffer
0x180025667  mov     dword ptr [rsp+80h+lpSecurityAttributes], r8d; dwOutBufferSize
0x18002566c  call    cs:__imp_FilterSendMessage
0x180025673  nop     dword ptr [rax+rax+00h]
0x180025678  mov     ebx, eax
0x18002567a  test    eax, eax
0x18002567c  jnz     short loc_1800256A0
0x18002567e  mov     ecx, [rsi+8]; Status
0x180025681  test    ecx, ecx
0x180025683  jns     short loc_1800256A0
0x180025685  call    cs:__imp_RtlNtStatusToDosError
0x18002568c  nop     dword ptr [rax+rax+00h]
0x180025691  mov     ebx, eax
0x180025693  test    eax, eax
0x180025695  jle     short loc_1800256A0
0x180025697  movzx   ebx, ax
0x18002569a  or      ebx, 80070000h
0x1800256a0  test    r12, r12
0x1800256a3  jz      short loc_1800256B4
0x1800256a5  mov     rcx, r12; Block
0x1800256a8  call    cs:__imp_free
0x1800256af  nop     dword ptr [rax+rax+00h]
0x1800256b4  test    r15, r15
0x1800256b7  jz      short loc_1800256C8
0x1800256b9  mov     rcx, r15; Block
0x1800256bc  call    cs:__imp_free
0x1800256c3  nop     dword ptr [rax+rax+00h]
0x1800256c8  test    rsi, rsi
0x1800256cb  jz      short loc_1800256DC
0x1800256cd  mov     rcx, rsi; Block
0x1800256d0  call    cs:__imp_free
0x1800256d7  nop     dword ptr [rax+rax+00h]
0x1800256dc  mov     rcx, [rbp+hObject]; hObject
0x1800256e0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800256e4  jz      short loc_1800256F2
0x1800256e6  call    cs:__imp_CloseHandle
0x1800256ed  nop     dword ptr [rax+rax+00h]
0x1800256f2  cmp     [rbp+arg_0], dil
0x1800256f6  jz      short loc_180025716
0x1800256f8  mov     rcx, r14; Block
0x1800256fb  call    cs:__imp_free
0x180025702  nop     dword ptr [rax+rax+00h]
0x180025707  mov     rcx, r13; Block
0x18002570a  call    cs:__imp_free
0x180025711  nop     dword ptr [rax+rax+00h]
0x180025716  mov     eax, ebx
0x180025718  mov     rbx, [rsp+80h+arg_18]
0x180025720  add     rsp, 80h
0x180025727  pop     r15
0x180025729  pop     r14
0x18002572b  pop     r13
0x18002572d  pop     r12
0x18002572f  pop     rdi
0x180025730  pop     rsi
0x180025731  pop     rbp
0x180025732  retn
```
