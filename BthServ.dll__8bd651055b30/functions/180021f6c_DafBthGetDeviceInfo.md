# DafBthGetDeviceInfo

- ea: `0x180021f6c`
- end: `0x180022266`
- name: `DafBthGetDeviceInfo`
- size: `762`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002103c`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180021ac8`
- `0x180021b88`
- `0x180021f6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180022028`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180022028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002217f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002217f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800220f0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800220f0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800220c4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800220c4`

## pseudocode

```c
__int64 __fastcall DafBthGetDeviceInfo(HANDLE hFile, __int64 a2, int a3, _OWORD *a4)
{
  signed int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int LastError; // eax
  signed int v13; // eax
  __int64 v14; // rcx
  char *v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  int v26; // eax
  bool v27; // cf
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-B8h] BYREF
  int OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  char v35; // [rsp+88h] [rbp-78h] BYREF

  OutBuffer = 0;
  memset_0(&v32, 0, 0x354u);
  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
  v32 = 3;
  v33 = a2;
  v34 = 1;
  OutBuffer = a3;
  Overlapped.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Overlapped.hEvent )
  {
    v9 = 0;
    if ( DeviceIoControl(hFile, 0x411058u, &OutBuffer, 0x18u, &OutBuffer, 0x358u, &BytesReturned, &Overlapped) )
      goto LABEL_25;
    LastError = GetLastError();
    if ( LastError == 997 )
    {
      if ( GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
        goto LABEL_25;
      v13 = GetLastError();
      v9 = v13;
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v11 = 23;
        goto LABEL_10;
      }
    }
    else
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v11 = 24;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 22;
LABEL_10:
      WPP_SF_sd(v10[2], v11, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
LABEL_25:
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( Overlapped.hEvent )
  {
    CloseHandle(Overlapped.hEvent);
    v10 = WPP_GLOBAL_Control;
    Overlapped.hEvent = 0;
  }
  if ( v9 )
  {
    v26 = 0;
    v27 = *((_BYTE *)v10 + 25) < 2u;
  }
  else
  {
    v14 = 6;
    v15 = &v35;
    do
    {
      v16 = *((_OWORD *)v15 + 1);
      *a4 = *(_OWORD *)v15;
      v17 = *((_OWORD *)v15 + 2);
      a4[1] = v16;
      v18 = *((_OWORD *)v15 + 3);
      a4[2] = v17;
      v19 = *((_OWORD *)v15 + 4);
      a4[3] = v18;
      v20 = *((_OWORD *)v15 + 5);
      a4[4] = v19;
      v21 = *((_OWORD *)v15 + 6);
      a4[5] = v20;
      v22 = *((_OWORD *)v15 + 7);
      v15 += 128;
      a4[6] = v21;
      a4[7] = v22;
      a4 += 8;
      --v14;
    }
    while ( v14 );
    v23 = *((_OWORD *)v15 + 1);
    *a4 = *(_OWORD *)v15;
    v24 = *((_OWORD *)v15 + 2);
    a4[1] = v23;
    v25 = *((_OWORD *)v15 + 3);
    v26 = 0;
    a4[2] = v24;
    a4[3] = v25;
    v10 = WPP_GLOBAL_Control;
    v27 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  }
  if ( v10 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v26) = !v27;
    if ( v26 )
      WPP_SF_sd(v10[2], 25, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x180021f6c  push    rbp
0x180021f6e  push    rbx
0x180021f6f  push    rsi
0x180021f70  push    rdi
0x180021f71  push    r12
0x180021f73  push    r14
0x180021f75  lea     rbp, [rsp-2E8h]
0x180021f7d  sub     rsp, 3E8h
0x180021f84  mov     rax, cs:__security_cookie
0x180021f8b  xor     rax, rsp
0x180021f8e  mov     [rbp+310h+var_40], rax
0x180021f95  mov     r14d, r8d
0x180021f98  mov     [rsp+410h+OutBuffer], 0
0x180021fa0  mov     rbx, rdx
0x180021fa3  mov     rsi, rcx
0x180021fa6  xor     edx, edx; Val
0x180021fa8  lea     rcx, [rsp+410h+var_39C]; void *
0x180021fad  mov     r8d, 354h; Size
0x180021fb3  mov     rdi, r9
0x180021fb6  call    memset_0
0x180021fbb  xorps   xmm0, xmm0
0x180021fbe  mov     [rsp+410h+BytesReturned], 0
0x180021fc6  movups  xmmword ptr [rsp+410h+Overlapped.Internal], xmm0
0x180021fcb  movups  xmmword ptr [rsp+410h+Overlapped.10h], xmm0
0x180021fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fd7  lea     rax, WPP_GLOBAL_Control
0x180021fde  lea     r12, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids
0x180021fe5  cmp     rcx, rax
0x180021fe8  jz      short loc_180022001
0x180021fea  cmp     byte ptr [rcx+19h], 5
0x180021fee  jb      short loc_180022001
0x180021ff0  mov     rcx, [rcx+10h]
0x180021ff4  mov     edx, 15h
0x180021ff9  mov     r8, r12
0x180021ffc  call    WPP_SF_s
0x180022001  xor     edx, edx; lpName
0x180022003  mov     [rsp+410h+var_39C], 3
0x18002200b  xor     ecx, ecx; lpEventAttributes
0x18002200d  mov     [rsp+410h+var_398], rbx
0x180022012  mov     r9d, 1F0003h; dwDesiredAccess
0x180022018  mov     [rbp+310h+var_390], 1
0x18002201f  mov     [rsp+410h+OutBuffer], r14d
0x180022024  lea     r8d, [rdx+1]; dwFlags
0x180022028  call    cs:__imp_CreateEventExW
0x18002202e  mov     [rsp+410h+Overlapped.hEvent], rax
0x180022033  test    rax, rax
0x180022036  jnz     short loc_180022088
0x180022038  call    cs:__imp_GetLastError
0x18002203e  mov     ebx, eax
0x180022040  test    eax, eax
0x180022042  jle     short loc_18002204D
0x180022044  movzx   ebx, ax
0x180022047  or      ebx, 80070000h
0x18002204d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022054  lea     rsi, WPP_GLOBAL_Control
0x18002205b  cmp     rcx, rsi
0x18002205e  jz      loc_180022172
0x180022064  cmp     byte ptr [rcx+19h], 2
0x180022068  jb      loc_180022172
0x18002206e  mov     edx, 16h
0x180022073  mov     rcx, [rcx+10h]
0x180022077  mov     r8, r12
0x18002207a  mov     dword ptr [rsp+410h+lpOutBuffer], ebx
0x18002207e  call    WPP_SF_sd
0x180022083  jmp     loc_18002216B
0x180022088  lea     rax, [rsp+410h+Overlapped]
0x18002208d  xor     ebx, ebx
0x18002208f  mov     [rsp+410h+lpOverlapped], rax; lpOverlapped
0x180022094  lea     r8, [rsp+410h+OutBuffer]; lpInBuffer
0x180022099  lea     rax, [rsp+410h+BytesReturned]
0x18002209e  mov     edx, 411058h; dwIoControlCode
0x1800220a3  mov     [rsp+410h+lpBytesReturned], rax; lpBytesReturned
0x1800220a8  mov     rcx, rsi; hDevice
0x1800220ab  lea     rax, [rsp+410h+OutBuffer]
0x1800220b0  mov     [rsp+410h+nOutBufferSize], 358h; nOutBufferSize
0x1800220b8  lea     r14d, [rbx+18h]
0x1800220bc  mov     [rsp+410h+lpOutBuffer], rax; lpOutBuffer
0x1800220c1  mov     r9d, r14d; nInBufferSize
0x1800220c4  call    cs:__imp_DeviceIoControl
0x1800220ca  test    eax, eax
0x1800220cc  jnz     loc_180022164
0x1800220d2  call    cs:__imp_GetLastError
0x1800220d8  cmp     eax, 3E5h
0x1800220dd  jnz     short loc_180022132
0x1800220df  lea     r9d, [rbx+1]; bWait
0x1800220e3  mov     rcx, rsi; hFile
0x1800220e6  lea     r8, [rsp+410h+BytesReturned]; lpNumberOfBytesTransferred
0x1800220eb  lea     rdx, [rsp+410h+Overlapped]; lpOverlapped
0x1800220f0  call    cs:__imp_GetOverlappedResult
0x1800220f6  test    eax, eax
0x1800220f8  jnz     short loc_180022164
0x1800220fa  call    cs:__imp_GetLastError
0x180022100  mov     ebx, eax
0x180022102  test    eax, eax
0x180022104  jle     short loc_18002210F
0x180022106  movzx   ebx, ax
0x180022109  or      ebx, 80070000h
0x18002210f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022116  lea     rsi, WPP_GLOBAL_Control
0x18002211d  cmp     rcx, rsi
0x180022120  jz      short loc_180022172
0x180022122  cmp     byte ptr [rcx+19h], 3
0x180022126  jb      short loc_180022172
0x180022128  mov     edx, 17h
0x18002212d  jmp     loc_180022073
0x180022132  test    eax, eax
0x180022134  jg      short loc_18002213A
0x180022136  mov     ebx, eax
0x180022138  jmp     short loc_180022143
0x18002213a  movzx   ebx, ax
0x18002213d  or      ebx, 80070000h
0x180022143  mov     rcx, cs:WPP_GLOBAL_Control
0x18002214a  lea     rsi, WPP_GLOBAL_Control
0x180022151  cmp     rcx, rsi
0x180022154  jz      short loc_180022172
0x180022156  cmp     byte ptr [rcx+19h], 3
0x18002215a  jb      short loc_180022172
0x18002215c  mov     edx, r14d
0x18002215f  jmp     loc_180022073
0x180022164  lea     rsi, WPP_GLOBAL_Control
0x18002216b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022172  mov     rax, [rsp+410h+Overlapped.hEvent]
0x180022177  test    rax, rax
0x18002217a  jz      short loc_180022195
0x18002217c  mov     rcx, rax; hObject
0x18002217f  call    cs:__imp_CloseHandle
0x180022185  mov     rcx, cs:WPP_GLOBAL_Control
0x18002218c  mov     [rsp+410h+Overlapped.hEvent], 0
0x180022195  test    ebx, ebx
0x180022197  jnz     loc_18002221E
0x18002219d  lea     ecx, [rbx+6]
0x1800221a0  lea     edx, [rcx+7Ah]
0x1800221a3  lea     rax, [rbp+310h+var_388]
0x1800221a7  movups  xmm0, xmmword ptr [rax]
0x1800221aa  movups  xmm1, xmmword ptr [rax+10h]
0x1800221ae  movups  xmmword ptr [rdi], xmm0
0x1800221b1  movups  xmm0, xmmword ptr [rax+20h]
0x1800221b5  movups  xmmword ptr [rdi+10h], xmm1
0x1800221b9  movups  xmm1, xmmword ptr [rax+30h]
0x1800221bd  movups  xmmword ptr [rdi+20h], xmm0
0x1800221c1  movups  xmm0, xmmword ptr [rax+40h]
0x1800221c5  movups  xmmword ptr [rdi+30h], xmm1
0x1800221c9  movups  xmm1, xmmword ptr [rax+50h]
0x1800221cd  movups  xmmword ptr [rdi+40h], xmm0
0x1800221d1  movups  xmm0, xmmword ptr [rax+60h]
0x1800221d5  movups  xmmword ptr [rdi+50h], xmm1
0x1800221d9  movups  xmm1, xmmword ptr [rax+70h]
0x1800221dd  add     rax, rdx
0x1800221e0  movups  xmmword ptr [rdi+60h], xmm0
0x1800221e4  movups  xmmword ptr [rdi+70h], xmm1
0x1800221e8  add     rdi, rdx
0x1800221eb  sub     rcx, 1
0x1800221ef  jnz     short loc_1800221A7
0x1800221f1  movups  xmm0, xmmword ptr [rax]
0x1800221f4  movups  xmm1, xmmword ptr [rax+10h]
0x1800221f8  movups  xmmword ptr [rdi], xmm0
0x1800221fb  movups  xmm0, xmmword ptr [rax+20h]
0x1800221ff  movups  xmmword ptr [rdi+10h], xmm1
0x180022203  movups  xmm1, xmmword ptr [rax+30h]
0x180022207  xor     eax, eax
0x180022209  movups  xmmword ptr [rdi+20h], xmm0
0x18002220d  movups  xmmword ptr [rdi+30h], xmm1
0x180022211  mov     rcx, cs:WPP_GLOBAL_Control
0x180022218  cmp     byte ptr [rcx+19h], 5
0x18002221c  jmp     short loc_180022224
0x18002221e  xor     eax, eax
0x180022220  cmp     byte ptr [rcx+19h], 2
0x180022224  setnb   al
0x180022227  cmp     rcx, rsi
0x18002222a  jz      short loc_180022245
0x18002222c  test    eax, eax
0x18002222e  jz      short loc_180022245
0x180022230  mov     rcx, [rcx+10h]
0x180022234  mov     edx, 19h
0x180022239  mov     r8, r12
0x18002223c  mov     dword ptr [rsp+410h+lpOutBuffer], ebx
0x180022240  call    WPP_SF_sd
0x180022245  mov     eax, ebx
0x180022247  mov     rcx, [rbp+310h+var_40]
0x18002224e  xor     rcx, rsp; StackCookie
0x180022251  call    __security_check_cookie
0x180022256  add     rsp, 3E8h
0x18002225d  pop     r14
0x18002225f  pop     r12
0x180022261  pop     rdi
0x180022262  pop     rsi
0x180022263  pop     rbx
0x180022264  pop     rbp
0x180022265  retn
```
