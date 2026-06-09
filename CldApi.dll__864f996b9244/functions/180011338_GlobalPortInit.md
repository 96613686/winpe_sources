# GlobalPortInit

- ea: `0x180011338`
- end: `0x18001150e`
- name: `GlobalPortInit`
- size: `470`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002630`
- `0x180002c80`
- `0x180002d20`
- `0x180004ac0`
- `0x180005710`
- `0x180006060`
- `0x1800073b0`
- `0x1800079c0`
- `0x180007cf0`
- `0x18000f330`

## callees

- `0x180011338`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011462`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001136c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001136c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800114fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800114fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800114da`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1800113c7`
- `FLTLIB!FilterConnectCommunicationPort` at `0x180011437`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1800113c7`
- `FLTLIB!FilterConnectCommunicationPort` at `0x180011437`

## pseudocode

```c
__int64 __fastcall GlobalPortInit(char a1)
{
  int v1; // ebx
  int v3; // edi
  char v4; // bp
  signed int LastError; // eax
  __int64 Context; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  Context = 0;
  v3 = a1 != 0 ? 4 : 2;
  if ( (dword_180028BE8 & v3) == 0 )
  {
    EnterCriticalSection(&_G);
    v4 = dword_180028BE8;
    if ( (dword_180028BE8 & v3) != 0 )
    {
LABEL_24:
      LeaveCriticalSection(&_G);
      return (unsigned int)v1;
    }
    if ( (dword_180028BE8 & 2) == 0 )
    {
      Context = 0x163706C43LL;
      v1 = FilterConnectCommunicationPort(L"\\CLDMSGPORT", 0, &Context, 8u, 0, &hPort);
      if ( v1 < 0 )
      {
        if ( !a1 )
        {
LABEL_20:
          if ( (v4 & 2) == 0 )
          {
            if ( hPort != (HANDLE)-1LL )
            {
              CloseHandle(hPort);
              hPort = (HANDLE)-1LL;
            }
            dword_180028BE8 &= ~2u;
          }
          goto LABEL_24;
        }
LABEL_17:
        if ( (v4 & 4) == 0 && *(&hPort + 1) != (HANDLE)-1LL )
        {
          CloseHandle(*(&hPort + 1));
          *(&hPort + 1) = (HANDLE)-1LL;
        }
        goto LABEL_20;
      }
      dword_180028BE8 |= 2u;
    }
    if ( !a1 || (dword_180028BE8 & 4) != 0 )
      goto LABEL_24;
    Context = 0x263706C43LL;
    v1 = FilterConnectCommunicationPort(L"\\CLDMSGPORT", 0, &Context, 8u, 0, &hPort + 1);
    if ( v1 >= 0 )
    {
      qword_180028C08 = (__int64)CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SyncMessageThread, 0, 0, 0);
      if ( qword_180028C08 )
      {
        v1 = 0;
      }
      else
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v1 >= 0 )
      {
        dword_180028BE8 |= 4u;
        goto LABEL_24;
      }
    }
    goto LABEL_17;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180011338  push    rbx
0x18001133a  push    rbp
0x18001133b  push    rsi
0x18001133c  push    rdi
0x18001133d  sub     rsp, 38h
0x180011341  xor     ebx, ebx
0x180011343  mov     al, cl
0x180011345  neg     al
0x180011347  mov     [rsp+58h+Context], rbx
0x18001134c  mov     eax, cs:dword_180028BE8
0x180011352  mov     sil, cl
0x180011355  sbb     edi, edi
0x180011357  and     edi, 2
0x18001135a  add     edi, 2
0x18001135d  test    edi, eax
0x18001135f  jnz     loc_180011503
0x180011365  lea     rcx, __G; lpCriticalSection
0x18001136c  call    cs:__imp_EnterCriticalSection
0x180011372  mov     ebp, cs:dword_180028BE8
0x180011378  mov     eax, cs:dword_180028BE8
0x18001137e  test    edi, eax
0x180011380  jnz     loc_1800114F6
0x180011386  mov     eax, cs:dword_180028BE8
0x18001138c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011390  test    al, 2
0x180011392  jnz     short loc_1800113E6
0x180011394  lea     rax, hPort
0x18001139b  mov     dword ptr [rsp+58h+Context], 63706C43h
0x1800113a3  mov     [rsp+58h+hPort], rax; hPort
0x1800113a8  lea     r9d, [rbx+8]; wSizeOfContext
0x1800113ac  lea     r8, [rsp+58h+Context]; lpContext
0x1800113b1  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800113b6  xor     edx, edx; dwOptions
0x1800113b8  mov     dword ptr [rsp+58h+Context+4], 1
0x1800113c0  lea     rcx, PortName; "\\CLDMSGPORT"
0x1800113c7  call    cs:__imp_FilterConnectCommunicationPort
0x1800113cd  mov     ebx, eax
0x1800113cf  test    eax, eax
0x1800113d1  js      loc_1800114A4
0x1800113d7  mov     ecx, cs:dword_180028BE8
0x1800113dd  or      ecx, 2
0x1800113e0  mov     cs:dword_180028BE8, ecx
0x1800113e6  test    sil, sil
0x1800113e9  jz      loc_1800114A0
0x1800113ef  mov     edx, cs:dword_180028BE8
0x1800113f5  test    dl, 4
0x1800113f8  jnz     loc_1800114A0
0x1800113fe  lea     rax, hPort+8
0x180011405  mov     dword ptr [rsp+58h+Context], 63706C43h
0x18001140d  mov     [rsp+58h+hPort], rax; hPort
0x180011412  lea     r8, [rsp+58h+Context]; lpContext
0x180011417  mov     r9d, 8; wSizeOfContext
0x18001141d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180011426  xor     edx, edx; dwOptions
0x180011428  mov     dword ptr [rsp+58h+Context+4], 2
0x180011430  lea     rcx, PortName; "\\CLDMSGPORT"
0x180011437  call    cs:__imp_FilterConnectCommunicationPort
0x18001143d  mov     ebx, eax
0x18001143f  test    eax, eax
0x180011441  js      short loc_1800114A9
0x180011443  mov     [rsp+58h+hPort], 0; lpThreadId
0x18001144c  lea     r8, SyncMessageThread; lpStartAddress
0x180011453  xor     r9d, r9d; lpParameter
0x180011456  mov     dword ptr [rsp+58h+lpSecurityAttributes], 0; dwCreationFlags
0x18001145e  xor     edx, edx; dwStackSize
0x180011460  xor     ecx, ecx; lpThreadAttributes
0x180011462  call    cs:__imp_CreateThread
0x180011468  mov     cs:qword_180028C08, rax
0x18001146f  test    rax, rax
0x180011472  jz      short loc_180011478
0x180011474  xor     ebx, ebx
0x180011476  jmp     short loc_18001148D
0x180011478  call    cs:__imp_GetLastError
0x18001147e  mov     ebx, eax
0x180011480  test    eax, eax
0x180011482  jle     short loc_18001148D
0x180011484  movzx   ebx, ax
0x180011487  or      ebx, 80070000h
0x18001148d  test    ebx, ebx
0x18001148f  js      short loc_1800114A9
0x180011491  mov     eax, cs:dword_180028BE8
0x180011497  or      eax, 4
0x18001149a  mov     cs:dword_180028BE8, eax
0x1800114a0  test    ebx, ebx
0x1800114a2  jns     short loc_1800114F6
0x1800114a4  test    sil, sil
0x1800114a7  jz      short loc_1800114C8
0x1800114a9  test    bpl, 4
0x1800114ad  jnz     short loc_1800114C8
0x1800114af  mov     rcx, qword ptr cs:hPort+8; hObject
0x1800114b6  cmp     rcx, rdi
0x1800114b9  jz      short loc_1800114C8
0x1800114bb  call    cs:__imp_CloseHandle
0x1800114c1  mov     qword ptr cs:hPort+8, rdi
0x1800114c8  test    bpl, 2
0x1800114cc  jnz     short loc_1800114F6
0x1800114ce  mov     rcx, qword ptr cs:hPort; hObject
0x1800114d5  cmp     rcx, rdi
0x1800114d8  jz      short loc_1800114E7
0x1800114da  call    cs:__imp_CloseHandle
0x1800114e0  mov     qword ptr cs:hPort, rdi
0x1800114e7  mov     eax, cs:dword_180028BE8
0x1800114ed  and     eax, 0FFFFFFFDh
0x1800114f0  mov     cs:dword_180028BE8, eax
0x1800114f6  lea     rcx, __G; lpCriticalSection
0x1800114fd  call    cs:__imp_LeaveCriticalSection
0x180011503  mov     eax, ebx
0x180011505  add     rsp, 38h
0x180011509  pop     rdi
0x18001150a  pop     rsi
0x18001150b  pop     rbp
0x18001150c  pop     rbx
0x18001150d  retn
```
