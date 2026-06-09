# WinHttpDownload::CreateHTTPSession(int)

- ea: `0x180012244`
- end: `0x1800123ff`
- name: `?CreateHTTPSession@WinHttpDownload@@AEAAJH@Z`
- size: `443`
- prototype: `__int64 __fastcall(WinHttpDownload *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180012408`
- `0x180012c24`

## callees

- `0x18000725c`
- `0x180012244`
- `0x1800128e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001227a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001232d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001227a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001232d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123ba`
- `WINHTTP!WinHttpOpen` at `0x18001226b`
- `WINHTTP!WinHttpOpen` at `0x18001226b`
- `WINHTTP!WinHttpOpenRequest` at `0x18001231e`
- `WINHTTP!WinHttpOpenRequest` at `0x18001231e`
- `WINHTTP!WinHttpSetOption` at `0x1800123b0`
- `WINHTTP!WinHttpSetOption` at `0x1800123b0`
- `WINHTTP!WinHttpConnect` at `0x1800122c4`
- `WINHTTP!WinHttpConnect` at `0x1800122c4`

## string_xrefs

- `0x18001225e`: `Delegated Service Installer`
- `0x18001228f`: `WinHttpOpen Failed , error %x`
- `0x180012342`: `WinHttpOpenRequest Failed , error %x`
- `0x180012380`: `Setting SSL Security Option, Flag %x`
- `0x1800123d2`: `Setting SSL Security option failed, Flag %x, error %x`

## pseudocode

```c
__int64 __fastcall WinHttpDownload::CreateHTTPSession(WinHttpDownload *this, int a2)
{
  void *v4; // rax
  signed int LastError; // eax
  unsigned int Proxy; // ebx
  unsigned __int16 *v7; // r9
  void *v8; // rax
  signed int v9; // eax
  DWORD v10; // ecx
  HINTERNET v11; // rax
  signed int v12; // eax
  DWORD *v13; // r14
  signed int v14; // eax
  DWORD dwFlags[2]; // [rsp+20h] [rbp-48h]
  DWORD dwFlagsa[2]; // [rsp+20h] [rbp-48h]
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-40h]

  v4 = WinHttpOpen(L"Delegated Service Installer", 0, 0, 0, 0);
  *((_QWORD *)this + 7) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    Proxy = LastError;
    if ( LastError > 0 )
      Proxy = (unsigned __int16)LastError | 0x80070000;
    v7 = L"WinHttpOpen Failed , error %x";
LABEL_5:
    dwFlags[0] = Proxy;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, 2u, v7, *(_QWORD *)dwFlags);
    return Proxy;
  }
  v8 = WinHttpConnect(v4, *((LPCWSTR *)this + 4), *((_WORD *)this + 12), 0);
  *((_QWORD *)this + 8) = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    Proxy = v9;
    if ( v9 > 0 )
      Proxy = (unsigned __int16)v9 | 0x80070000;
    v7 = L"WinHttpConnect Failed , error %x";
    goto LABEL_5;
  }
  v10 = 0x800000;
  if ( *((_DWORD *)this + 7) != 2 )
    v10 = 0;
  v11 = WinHttpOpenRequest(v8, 0, *((LPCWSTR *)this + 6), 0, 0, 0, v10);
  *((_QWORD *)this + 9) = v11;
  if ( !v11 )
  {
    v12 = GetLastError();
    Proxy = v12;
    if ( v12 > 0 )
      Proxy = (unsigned __int16)v12 | 0x80070000;
    v7 = L"WinHttpOpenRequest Failed , error %x";
    goto LABEL_5;
  }
  Proxy = 0;
  if ( !a2 || (Proxy = WinHttpDownload::GetProxy(this), (Proxy & 0x80000000) == 0) )
  {
    v13 = (DWORD *)((char *)this + 128);
    if ( *((_DWORD *)this + 7) != 2 )
      *v13 = 0;
    if ( *v13 )
    {
      dwFlags[0] = *v13;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        2u,
        3u,
        L"Setting SSL Security Option, Flag %x",
        *(_QWORD *)dwFlags);
      if ( !WinHttpSetOption(*((HINTERNET *)this + 9), 0x1Fu, (char *)this + 128, 4u) )
      {
        v14 = GetLastError();
        Proxy = v14;
        if ( v14 > 0 )
          Proxy = (unsigned __int16)v14 | 0x80070000;
        LODWORD(ppwszAcceptTypes) = Proxy;
        dwFlagsa[0] = *v13;
        AxISEvents::DebugMsg(
          (AxISEvents *)&qword_180021AD8,
          2u,
          2u,
          L"Setting SSL Security option failed, Flag %x, error %x",
          *(_QWORD *)dwFlagsa,
          ppwszAcceptTypes);
      }
    }
  }
  return Proxy;
}

```

## disassembly

```asm
0x180012244  push    rbx
0x180012246  push    rbp
0x180012247  push    rsi
0x180012248  push    rdi
0x180012249  push    r14
0x18001224b  sub     rsp, 40h
0x18001224f  mov     ebp, edx
0x180012251  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180012259  mov     rsi, rcx
0x18001225c  xor     edx, edx; dwAccessType
0x18001225e  lea     rcx, pszAgentW; "Delegated Service Installer"
0x180012265  xor     r9d, r9d; pszProxyBypassW
0x180012268  xor     r8d, r8d; pszProxyW
0x18001226b  call    cs:__imp_WinHttpOpen
0x180012271  mov     [rsi+38h], rax
0x180012275  test    rax, rax
0x180012278  jnz     short loc_1800122B5
0x18001227a  call    cs:__imp_GetLastError
0x180012280  mov     ebx, eax
0x180012282  test    eax, eax
0x180012284  jle     short loc_18001228F
0x180012286  movzx   ebx, ax
0x180012289  or      ebx, 80070000h
0x18001228f  lea     r9, aWinhttpopenFai; "WinHttpOpen Failed , error %x"
0x180012296  mov     edi, 2
0x18001229b  mov     r8d, edi; unsigned __int8
0x18001229e  mov     [rsp+68h+dwFlags], ebx
0x1800122a2  mov     edx, edi; unsigned int
0x1800122a4  lea     rcx, qword_180021AD8; this
0x1800122ab  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800122b0  jmp     loc_1800123F2
0x1800122b5  movzx   r8d, word ptr [rsi+18h]; nServerPort
0x1800122ba  xor     r9d, r9d; dwReserved
0x1800122bd  mov     rdx, [rsi+20h]; pswzServerName
0x1800122c1  mov     rcx, rax; hSession
0x1800122c4  call    cs:__imp_WinHttpConnect
0x1800122ca  mov     [rsi+40h], rax
0x1800122ce  mov     r10, rax
0x1800122d1  test    rax, rax
0x1800122d4  jnz     short loc_1800122F4
0x1800122d6  call    cs:__imp_GetLastError
0x1800122dc  mov     ebx, eax
0x1800122de  test    eax, eax
0x1800122e0  jle     short loc_1800122EB
0x1800122e2  movzx   ebx, ax
0x1800122e5  or      ebx, 80070000h
0x1800122eb  lea     r9, aWinhttpconnect_0; "WinHttpConnect Failed , error %x"
0x1800122f2  jmp     short loc_180012296
0x1800122f4  mov     r8, [rsi+30h]; pwszObjectName
0x1800122f8  xor     eax, eax
0x1800122fa  mov     ecx, 800000h
0x1800122ff  lea     edi, [rax+2]
0x180012302  cmp     [rsi+1Ch], edi
0x180012305  cmovnz  ecx, eax
0x180012308  xor     r9d, r9d; pwszVersion
0x18001230b  mov     [rsp+68h+var_38], ecx; dwFlags
0x18001230f  xor     edx, edx; pwszVerb
0x180012311  mov     [rsp+68h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x180012316  mov     rcx, r10; hConnect
0x180012319  mov     qword ptr [rsp+68h+dwFlags], rax; pwszReferrer
0x18001231e  call    cs:__imp_WinHttpOpenRequest
0x180012324  mov     [rsi+48h], rax
0x180012328  test    rax, rax
0x18001232b  jnz     short loc_18001234E
0x18001232d  call    cs:__imp_GetLastError
0x180012333  mov     ebx, eax
0x180012335  test    eax, eax
0x180012337  jle     short loc_180012342
0x180012339  movzx   ebx, ax
0x18001233c  or      ebx, 80070000h
0x180012342  lea     r9, aWinhttpopenreq_0; "WinHttpOpenRequest Failed , error %x"
0x180012349  jmp     loc_18001229B
0x18001234e  xor     ebx, ebx
0x180012350  test    ebp, ebp
0x180012352  jz      short loc_180012366
0x180012354  mov     rcx, rsi; this
0x180012357  call    ?GetProxy@WinHttpDownload@@AEAAJXZ; WinHttpDownload::GetProxy(void)
0x18001235c  mov     ebx, eax
0x18001235e  test    eax, eax
0x180012360  js      loc_1800123F2
0x180012366  lea     r14, [rsi+80h]
0x18001236d  cmp     [rsi+1Ch], edi
0x180012370  jz      short loc_180012379
0x180012372  mov     dword ptr [r14], 0
0x180012379  mov     eax, [r14]
0x18001237c  test    eax, eax
0x18001237e  jz      short loc_1800123F2
0x180012380  lea     r9, aSettingSslSecu_0; "Setting SSL Security Option, Flag %x"
0x180012387  mov     [rsp+68h+dwFlags], eax
0x18001238b  mov     r8d, 3; unsigned __int8
0x180012391  lea     rcx, qword_180021AD8; this
0x180012398  mov     edx, edi; unsigned int
0x18001239a  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18001239f  mov     rcx, [rsi+48h]; hInternet
0x1800123a3  mov     r9d, 4; dwBufferLength
0x1800123a9  mov     r8, r14; lpBuffer
0x1800123ac  lea     edx, [r9+1Bh]; dwOption
0x1800123b0  call    cs:__imp_WinHttpSetOption
0x1800123b6  test    eax, eax
0x1800123b8  jnz     short loc_1800123F2
0x1800123ba  call    cs:__imp_GetLastError
0x1800123c0  mov     ebx, eax
0x1800123c2  test    eax, eax
0x1800123c4  jle     short loc_1800123CF
0x1800123c6  movzx   ebx, ax
0x1800123c9  or      ebx, 80070000h
0x1800123cf  mov     eax, [r14]
0x1800123d2  lea     r9, aSettingSslSecu; "Setting SSL Security option failed, Fla"...
0x1800123d9  mov     dword ptr [rsp+68h+ppwszAcceptTypes], ebx
0x1800123dd  lea     rcx, qword_180021AD8; this
0x1800123e4  mov     r8d, edi; unsigned __int8
0x1800123e7  mov     [rsp+68h+dwFlags], eax
0x1800123eb  mov     edx, edi; unsigned int
0x1800123ed  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800123f2  mov     eax, ebx
0x1800123f4  add     rsp, 40h
0x1800123f8  pop     r14
0x1800123fa  pop     rdi
0x1800123fb  pop     rsi
0x1800123fc  pop     rbp
0x1800123fd  pop     rbx
0x1800123fe  retn
```
