# InitRrasRootEnum

- ea: `0x1800073d8`
- end: `0x18000764c`
- name: `InitRrasRootEnum`
- size: `628`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006214`

## callees

- `0x1800073d8`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007477`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007477`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800075a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800075a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007503`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007607`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007607`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000758c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000758c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x1800074ca`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x1800074ca`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800074af`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800074af`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180007540`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180007540`

## pseudocode

```c
__int64 __fastcall InitRrasRootEnum(_QWORD *a1)
{
  signed int LastError; // eax
  signed int v3; // ebx
  HANDLE v4; // rax
  DWORD v6; // eax
  signed int v7; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rax
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v14; // [rsp+78h] [rbp-88h]
  int v15; // [rsp+98h] [rbp-68h]
  const wchar_t *v16; // [rsp+A0h] [rbp-60h]
  WCHAR Buffer[200]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&v13, 0, 0x48u);
  *(_OWORD *)hObject = 0;
  *(_OWORD *)lpMem = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  pdnDevInst = 0;
  v14 = L"{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}";
  g_RrasRootEnum = 0;
  v16 = L"Microsoft RRAS Root Enumerator";
  v13 = 72;
  v15 = 2;
  hObject[0] = CreateEventW(0, 0, 0, 0);
  if ( !hObject[0] )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
    if ( v3 >= 0 )
      goto LABEL_8;
    goto LABEL_6;
  }
  if ( CM_Locate_DevNodeW(&pdnDevInst, 0, 0) || CM_Get_Device_IDW(pdnDevInst, Buffer, 0xC8u, 0) )
  {
    v3 = -2147467259;
    goto LABEL_6;
  }
  v3 = SwDeviceCreate(L"MSRRAS", Buffer, &v13, 0, 0, &RrasSwDeviceCreateCallback, hObject, &g_RrasRootEnum);
  if ( v3 < 0 )
  {
LABEL_6:
    if ( g_RrasRootEnum )
    {
      SwDeviceClose();
      g_RrasRootEnum = 0;
    }
    goto LABEL_8;
  }
  v6 = WaitForSingleObject(hObject[0], 0x7530u);
  if ( v6 )
  {
    if ( v6 == 258 )
    {
      v3 = -2147023436;
      goto LABEL_6;
    }
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_6;
  }
  if ( SLODWORD(lpMem[0]) < 0 )
  {
    v3 = (signed int)lpMem[0];
    goto LABEL_22;
  }
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v9 )
  {
    v3 = -2147024882;
    goto LABEL_6;
  }
  v9[1] = g_RrasRootEnum;
  *v9 = lpMem[1];
  lpMem[1] = 0;
  if ( a1 )
    *a1 = v9;
LABEL_8:
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( lpMem[1] )
  {
    v4 = GetProcessHeap();
    HeapFree(v4, 0, lpMem[1]);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800073d8  mov     [rsp-8+arg_8], rbx
0x1800073dd  mov     [rsp-8+arg_10], rdi
0x1800073e2  push    rbp
0x1800073e3  lea     rbp, [rsp-160h]
0x1800073eb  sub     rsp, 260h
0x1800073f2  mov     rax, cs:__security_cookie
0x1800073f9  xor     rax, rsp
0x1800073fc  mov     [rbp+160h+var_10], rax
0x180007403  mov     rdi, rcx
0x180007406  mov     ebx, 48h ; 'H'
0x18000740b  mov     r8d, ebx; Size
0x18000740e  lea     rcx, [rsp+260h+var_1F0]; void *
0x180007413  xor     edx, edx; Val
0x180007415  call    memset_0
0x18000741a  xorps   xmm0, xmm0
0x18000741d  lea     rcx, [rbp+160h+Buffer]; void *
0x180007421  xor     edx, edx; Val
0x180007423  mov     r8d, 190h; Size
0x180007429  movups  xmmword ptr [rsp+260h+hObject], xmm0
0x18000742e  movups  xmmword ptr [rsp+260h+lpMem], xmm0
0x180007433  call    memset_0
0x180007438  lea     rax, a5e259276Bc7e40; "{5e259276-bc7e-40e3-b93b-8f89b5f3abc0}"
0x18000743f  mov     [rsp+260h+pdnDevInst], 0
0x180007447  mov     [rsp+260h+var_1E8], rax
0x18000744c  xor     r9d, r9d; lpName
0x18000744f  lea     rax, aMicrosoftRrasR; "Microsoft RRAS Root Enumerator"
0x180007456  mov     cs:g_RrasRootEnum, 0
0x180007461  xor     r8d, r8d; bInitialState
0x180007464  mov     [rbp+160h+var_1C0], rax
0x180007468  xor     edx, edx; bManualReset
0x18000746a  mov     [rsp+260h+var_1F0], ebx
0x18000746e  xor     ecx, ecx; lpEventAttributes
0x180007470  mov     [rbp+160h+var_1C8], 2
0x180007477  call    cs:__imp_CreateEventW
0x18000747d  mov     [rsp+260h+hObject], rax
0x180007482  test    rax, rax
0x180007485  jnz     short loc_1800074A5
0x180007487  call    cs:__imp_GetLastError
0x18000748d  mov     ebx, eax
0x18000748f  test    eax, eax
0x180007491  jle     loc_1800075DE
0x180007497  movzx   ebx, ax
0x18000749a  or      ebx, 80070000h
0x1800074a0  jmp     loc_1800075DE
0x1800074a5  xor     r8d, r8d; ulFlags
0x1800074a8  lea     rcx, [rsp+260h+pdnDevInst]; pdnDevInst
0x1800074ad  xor     edx, edx; pDeviceID
0x1800074af  call    cs:__imp_CM_Locate_DevNodeW
0x1800074b5  test    eax, eax
0x1800074b7  jz      short loc_18000752F
0x1800074b9  mov     ebx, 80004005h
0x1800074be  mov     rcx, cs:g_RrasRootEnum
0x1800074c5  test    rcx, rcx
0x1800074c8  jz      short loc_1800074DB
0x1800074ca  call    cs:__imp_SwDeviceClose
0x1800074d0  mov     cs:g_RrasRootEnum, 0
0x1800074db  mov     rcx, [rsp+260h+hObject]; hObject
0x1800074e0  test    rcx, rcx
0x1800074e3  jz      short loc_1800074EB
0x1800074e5  call    cs:__imp_CloseHandle
0x1800074eb  cmp     [rsp+260h+lpMem+8], 0
0x1800074f1  jz      short loc_180007509
0x1800074f3  call    cs:__imp_GetProcessHeap
0x1800074f9  mov     r8, [rsp+260h+lpMem+8]; lpMem
0x1800074fe  xor     edx, edx; dwFlags
0x180007500  mov     rcx, rax; hHeap
0x180007503  call    cs:__imp_HeapFree
0x180007509  mov     eax, ebx
0x18000750b  mov     rcx, [rbp+160h+var_10]
0x180007512  xor     rcx, rsp; StackCookie
0x180007515  call    __security_check_cookie
0x18000751a  lea     r11, [rsp+260h+var_s0]
0x180007522  mov     rbx, [r11+18h]
0x180007526  mov     rdi, [r11+20h]
0x18000752a  mov     rsp, r11
0x18000752d  pop     rbp
0x18000752e  retn
0x18000752f  mov     ecx, [rsp+260h+pdnDevInst]; dnDevInst
0x180007533  lea     rdx, [rbp+160h+Buffer]; Buffer
0x180007537  xor     r9d, r9d; ulFlags
0x18000753a  mov     r8d, 0C8h; BufferLen
0x180007540  call    cs:__imp_CM_Get_Device_IDW
0x180007546  test    eax, eax
0x180007548  jnz     loc_1800074B9
0x18000754e  lea     rax, g_RrasRootEnum
0x180007555  xor     r9d, r9d
0x180007558  mov     [rsp+260h+var_228], rax
0x18000755d  lea     r8, [rsp+260h+var_1F0]
0x180007562  lea     rax, [rsp+260h+hObject]
0x180007567  mov     [rsp+260h+var_230], rax
0x18000756c  lea     rdx, [rbp+160h+Buffer]
0x180007570  lea     rax, RrasSwDeviceCreateCallback
0x180007577  mov     [rsp+260h+var_238], rax
0x18000757c  lea     rcx, aMsrras; "MSRRAS"
0x180007583  mov     [rsp+260h+var_240], 0
0x18000758c  call    cs:__imp_SwDeviceCreate
0x180007592  mov     ebx, eax
0x180007594  test    eax, eax
0x180007596  js      loc_1800074BE
0x18000759c  mov     rcx, [rsp+260h+hObject]; hHandle
0x1800075a1  mov     edx, 7530h; dwMilliseconds
0x1800075a6  call    cs:__imp_WaitForSingleObject
0x1800075ac  test    eax, eax
0x1800075ae  jz      short loc_1800075D4
0x1800075b0  cmp     eax, 102h
0x1800075b5  jz      short loc_1800075EB
0x1800075b7  call    cs:__imp_GetLastError
0x1800075bd  mov     ebx, eax
0x1800075bf  test    eax, eax
0x1800075c1  jle     short loc_1800075CC
0x1800075c3  movzx   ebx, ax
0x1800075c6  or      ebx, 80070000h
0x1800075cc  test    ebx, ebx
0x1800075ce  js      loc_1800074BE
0x1800075d4  mov     eax, dword ptr [rsp+260h+lpMem]
0x1800075d8  test    eax, eax
0x1800075da  jns     short loc_1800075F5
0x1800075dc  mov     ebx, eax
0x1800075de  test    ebx, ebx
0x1800075e0  js      loc_1800074BE
0x1800075e6  jmp     loc_1800074DB
0x1800075eb  mov     ebx, 800705B4h
0x1800075f0  jmp     loc_1800074BE
0x1800075f5  call    cs:__imp_GetProcessHeap
0x1800075fb  mov     edx, 8; dwFlags
0x180007600  mov     rcx, rax; hHeap
0x180007603  lea     r8d, [rdx+8]; dwBytes
0x180007607  call    cs:__imp_HeapAlloc
0x18000760d  mov     rcx, rax
0x180007610  test    rax, rax
0x180007613  jnz     short loc_18000761F
0x180007615  mov     ebx, 8007000Eh
0x18000761a  jmp     loc_1800074BE
0x18000761f  mov     rax, cs:g_RrasRootEnum
0x180007626  mov     [rcx+8], rax
0x18000762a  mov     rax, [rsp+260h+lpMem+8]
0x18000762f  mov     [rcx], rax
0x180007632  mov     [rsp+260h+lpMem+8], 0
0x18000763b  test    rdi, rdi
0x18000763e  jz      loc_1800074DB
0x180007644  mov     [rdi], rcx
0x180007647  jmp     loc_1800074DB
```
