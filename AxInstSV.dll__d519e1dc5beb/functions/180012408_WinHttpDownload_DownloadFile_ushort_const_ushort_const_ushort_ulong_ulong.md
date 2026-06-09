# WinHttpDownload::DownloadFile(ushort const *,ushort const *,ushort *,ulong,ulong)

- ea: `0x180012408`
- end: `0x1800128dc`
- name: `?DownloadFile@WinHttpDownload@@QEAAJPEBG0PEAGKK@Z`
- size: `1236`
- prototype: `__int64 __fastcall(WinHttpDownload *__hidden this, const unsigned __int16 *Src, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006518`

## callees

- `0x180005060`
- `0x1800050ec`
- `0x18000725c`
- `0x180012244`
- `0x180012408`
- `0x180012c24`
- `0x180012f9c`
- `0x1800130d4`
- `0x1800131a4`
- `0x18001431c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012525`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012525`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012510`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012510`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001245a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001245a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001264b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001278c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001264b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001278c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800128be`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800128be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001259d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001259d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001289c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001289c`
- `WINHTTP!WinHttpReceiveResponse` at `0x180012782`
- `WINHTTP!WinHttpReceiveResponse` at `0x180012782`
- `WINHTTP!WinHttpSendRequest` at `0x1800126e2`
- `WINHTTP!WinHttpSendRequest` at `0x1800126e2`
- `WINHTTP!WinHttpSetOption` at `0x180012641`
- `WINHTTP!WinHttpSetOption` at `0x180012697`
- `WINHTTP!WinHttpSetOption` at `0x180012641`
- `WINHTTP!WinHttpSetOption` at `0x180012697`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800127d4`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800127d4`

## pseudocode

```c
__int64 __fastcall WinHttpDownload::DownloadFile(
        WinHttpDownload *this,
        const unsigned __int16 *Src,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        DWORD a5,
        unsigned int a6)
{
  LPCWSTR *v6; // rsi
  __int64 v7; // r12
  __int64 v12; // rax
  size_t v13; // r14
  WCHAR *v14; // rax
  signed int LastError; // eax
  signed int appended; // ebx
  const wchar_t **v17; // r14
  int v18; // eax
  wchar_t *v19; // rax
  unsigned int v20; // r9d
  HANDLE FileW; // rax
  signed int v22; // eax
  void *v23; // rcx
  signed int v24; // eax
  unsigned __int16 *v25; // r9
  unsigned __int8 v26; // r8
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // r14d
  unsigned int v30; // r15d
  int v31; // r14d
  int v32; // r14d
  int Proxy; // eax
  signed int v34; // eax
  void *v35; // rcx
  signed int v36; // eax
  unsigned int v37; // eax
  void *v38; // rcx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-78h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-78h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-70h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-70h]
  DWORD dwBufferLength[22]; // [rsp+40h] [rbp-58h] BYREF
  int Buffer; // [rsp+A8h] [rbp+10h] BYREF

  v6 = (LPCWSTR *)((char *)this + 16);
  v7 = -1;
  a5 = 0;
  dwBufferLength[0] = 0;
  Buffer = 0;
  if ( Src )
  {
    v12 = -1;
    do
      ++v12;
    while ( Src[v12] );
    v13 = v12;
    v14 = (WCHAR *)LocalAlloc(0, 2 * v12 + 2);
    *v6 = v14;
    if ( !v14 )
    {
      LastError = GetLastError();
      appended = LastError;
      if ( LastError > 0 )
        appended = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_46;
    }
    memcpy_0(v14, Src, v13 * 2);
    (*v6)[v13] = 0;
  }
  v17 = (const wchar_t **)((char *)this + 40);
  v18 = Utils::CrackURL(
          *v6,
          (unsigned __int16 **)this + 4,
          (unsigned __int16 **)this + 6,
          (unsigned __int16 **)this + 5,
          (unsigned __int16 *)this + 12,
          (int *)this + 7);
  appended = v18;
  if ( v18 < 0 )
  {
    dwFlagsAndAttributes[0] = v18;
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      2u,
      2u,
      L"Failed to Crack URL , URL %s, error %x",
      *v6,
      *(_QWORD *)dwFlagsAndAttributes);
    goto LABEL_66;
  }
  if ( !*v17 )
  {
    appended = -2147024809;
    goto LABEL_66;
  }
  v19 = wcsrchr(*v17, 0x2Eu);
  if ( v19 && !(unsigned int)_o__wcsicmp(v19, L".exe") )
  {
    appended = -2147024809;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, 2u, L"Exe are not supported, FileName %s", *v17);
    goto LABEL_66;
  }
  appended = Utils::AppendPath(a3, *v17, a4, v20);
  if ( appended < 0 )
    goto LABEL_66;
  FileW = CreateFileW(a4, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
  *((_QWORD *)this + 10) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v22 = GetLastError();
    appended = v22;
    if ( v22 > 0 )
      appended = (unsigned __int16)v22 | 0x80070000;
    dwFlagsAndAttributesa[0] = appended;
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      2u,
      2u,
      L"Failed to Creat File , FileName %s, error %x",
      a4,
      *(_QWORD *)dwFlagsAndAttributesa);
    goto LABEL_46;
  }
  *((_DWORD *)this + 32) = a6;
  appended = WinHttpDownload::CreateHTTPSession(this, 1);
  if ( appended < 0 )
    goto LABEL_66;
  if ( *((_DWORD *)this + 28) )
  {
    appended = WinHttpDownload::SetProxy(this, (WinHttpDownload *)((char *)this + 88));
    if ( appended < 0 )
      goto LABEL_66;
  }
  v23 = (void *)*((_QWORD *)this + 9);
  Buffer = 2;
  if ( !WinHttpSetOption(v23, 0x4Du, &Buffer, 4u) )
  {
    v24 = GetLastError();
    appended = v24;
    if ( v24 > 0 )
      appended = (unsigned __int16)v24 | 0x80070000;
    v25 = L"WinHttpSetOption Failed Error %x";
    v26 = 3;
    goto LABEL_27;
  }
  if ( *((_DWORD *)this + 7) == 2 && !WinHttpSetOption(*((HINTERNET *)this + 9), 0x2Fu, 0, 0) )
  {
    v27 = GetLastError();
    appended = v27;
    if ( v27 > 0 )
      appended = (unsigned __int16)v27 | 0x80070000;
    v25 = L"WinHttpSetOption Failed Error %x";
LABEL_33:
    v26 = 2;
LABEL_27:
    dwCreationDisposition[0] = appended;
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 2u, v26, v25, *(_QWORD *)dwCreationDisposition);
    goto LABEL_46;
  }
  while ( !WinHttpSendRequest(*((HINTERNET *)this + 9), 0, 0, 0, 0, 0, 0) )
  {
    v28 = GetLastError();
    v29 = v28;
    if ( v28 > 0 )
      v30 = (unsigned __int16)v28 | 0x80070000;
    else
      v30 = v28;
    dwCreationDisposition[0] = v30;
    appended = v30;
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      2u,
      2u,
      L"WinHttpSendRequest Failed Error %x",
      *(_QWORD *)dwCreationDisposition);
    if ( !*((_DWORD *)this + 28) )
      goto LABEL_46;
    v31 = v29 - 12002;
    if ( v31 )
    {
      v32 = v31 - 5;
      if ( v32 )
      {
        if ( (unsigned int)(v32 - 22) > 1 )
          goto LABEL_46;
      }
    }
    Proxy = WinHttpDownload::SetNextProxy(this);
    appended = Proxy;
    if ( Proxy == 1 )
    {
      appended = v30;
      goto LABEL_46;
    }
    if ( Proxy < 0 )
      goto LABEL_66;
  }
  if ( !WinHttpReceiveResponse(*((HINTERNET *)this + 9), 0) )
  {
    v34 = GetLastError();
    appended = v34;
    if ( v34 > 0 )
      appended = (unsigned __int16)v34 | 0x80070000;
    v25 = L"WinHttpReceiveResponse Failed Error %x";
    goto LABEL_33;
  }
  v35 = (void *)*((_QWORD *)this + 9);
  dwBufferLength[0] = 4;
  if ( !WinHttpQueryHeaders(v35, 0x20000013u, 0, &a5, dwBufferLength, 0) )
  {
    v36 = GetLastError();
    appended = v36;
    if ( v36 > 0 )
      appended = (unsigned __int16)v36 | 0x80070000;
LABEL_46:
    if ( appended >= 0 )
      return (unsigned int)appended;
    goto LABEL_66;
  }
  v37 = a5;
  if ( a5 == 401 || a5 == 407 )
  {
    dwCreationDispositiona[0] = a5;
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      2u,
      3u,
      L"Connection Status code is %x. Will retry connection",
      *(_QWORD *)dwCreationDispositiona);
    if ( appended < 0 )
      goto LABEL_66;
    if ( (int)WinHttpDownload::RetrySecureRequest(this, &a5) < 0 )
    {
      appended = -2147012881;
      goto LABEL_66;
    }
    v37 = a5;
  }
  else if ( appended < 0 )
  {
    goto LABEL_66;
  }
  if ( v37 == 200 )
  {
    appended = WinHttpDownload::SaveToFile(this, *((void **)this + 10));
    goto LABEL_46;
  }
  dwCreationDispositiona[0] = v37;
  AxISEvents::DebugMsg(
    (AxISEvents *)&qword_180021AD8,
    2u,
    2u,
    L"Failed to download HTTP Status code %x",
    *(_QWORD *)dwCreationDispositiona);
  appended = -2147467259;
LABEL_66:
  v38 = (void *)*((_QWORD *)this + 10);
  if ( v38 != (void *)-1LL )
  {
    CloseHandle(v38);
    *((_QWORD *)this + 10) = -1;
  }
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    if ( v7 )
    {
      DeleteFileW(a4);
      *a4 = 0;
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180012408  mov     rax, rsp
0x18001240b  push    rbx
0x18001240c  push    rbp
0x18001240d  push    rsi
0x18001240e  push    rdi
0x18001240f  push    r12
0x180012411  push    r13
0x180012413  push    r14
0x180012415  push    r15
0x180012417  sub     rsp, 58h
0x18001241b  xor     r15d, r15d
0x18001241e  lea     rsi, [rcx+10h]
0x180012422  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012426  mov     [rax+28h], r15d
0x18001242a  mov     [rax-58h], r15d
0x18001242e  mov     r13, r9
0x180012431  mov     [rax+10h], r15d
0x180012435  mov     rbp, r8
0x180012438  mov     rbx, rdx
0x18001243b  mov     rdi, rcx
0x18001243e  test    rdx, rdx
0x180012441  jz      short loc_18001249C
0x180012443  mov     rax, r12
0x180012446  inc     rax
0x180012449  cmp     [rdx+rax*2], r15w
0x18001244e  jnz     short loc_180012446
0x180012450  lea     r14, [rax+rax]
0x180012454  xor     ecx, ecx; uFlags
0x180012456  lea     rdx, [r14+2]; uBytes
0x18001245a  call    cs:__imp_LocalAlloc
0x180012460  mov     [rsi], rax
0x180012463  test    rax, rax
0x180012466  jnz     short loc_180012486
0x180012468  call    cs:__imp_GetLastError
0x18001246e  mov     ebx, eax
0x180012470  test    eax, eax
0x180012472  jle     loc_18001276F
0x180012478  movzx   ebx, ax
0x18001247b  or      ebx, 80070000h
0x180012481  jmp     loc_18001276F
0x180012486  mov     r8, r14; Size
0x180012489  mov     rdx, rbx; Src
0x18001248c  mov     rcx, rax; void *
0x18001248f  call    memcpy_0
0x180012494  mov     rcx, [rsi]
0x180012497  mov     [r14+rcx], r15w
0x18001249c  lea     rax, [rdi+1Ch]
0x1800124a0  lea     rcx, [rdi+18h]
0x1800124a4  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax; int *
0x1800124a9  mov     qword ptr [rsp+98h+dwCreationDisposition], rcx; unsigned __int16 *
0x1800124ae  lea     r14, [rdi+28h]
0x1800124b2  mov     rcx, [rsi]; pwszUrl
0x1800124b5  lea     r8, [rdi+30h]; unsigned __int16 **
0x1800124b9  lea     rdx, [rdi+20h]; unsigned __int16 **
0x1800124bd  mov     r9, r14; unsigned __int16 **
0x1800124c0  call    ?CrackURL@Utils@@SAJPEBGPEAPEAG11PEAGPEAH@Z; Utils::CrackURL(ushort const *,ushort * *,ushort * *,ushort * *,ushort *,int *)
0x1800124c5  mov     ebx, eax
0x1800124c7  test    eax, eax
0x1800124c9  jns     short loc_1800124F9
0x1800124cb  mov     rcx, [rsi]
0x1800124ce  lea     r9, aFailedToCrackU; "Failed to Crack URL , URL %s, error %x"
0x1800124d5  mov     esi, 2
0x1800124da  mov     [rsp+98h+dwFlagsAndAttributes], eax
0x1800124de  mov     qword ptr [rsp+98h+dwCreationDisposition], rcx
0x1800124e3  mov     r8d, esi; unsigned __int8
0x1800124e6  mov     edx, esi; unsigned int
0x1800124e8  lea     rcx, qword_180021AD8; this
0x1800124ef  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800124f4  jmp     loc_180012893
0x1800124f9  mov     rcx, [r14]; Str
0x1800124fc  test    rcx, rcx
0x1800124ff  jnz     short loc_18001250B
0x180012501  mov     ebx, 80070057h
0x180012506  jmp     loc_180012893
0x18001250b  mov     edx, 2Eh ; '.'; Ch
0x180012510  call    cs:__imp_wcsrchr
0x180012516  test    rax, rax
0x180012519  jz      short loc_18001255E
0x18001251b  lea     rdx, aExe; ".exe"
0x180012522  mov     rcx, rax
0x180012525  call    cs:__imp__o__wcsicmp
0x18001252b  test    eax, eax
0x18001252d  jnz     short loc_18001255E
0x18001252f  mov     rax, [r14]
0x180012532  lea     r9, aExeAreNotSuppo; "Exe are not supported, FileName %s"
0x180012539  mov     esi, 2
0x18001253e  mov     qword ptr [rsp+98h+dwCreationDisposition], rax
0x180012543  mov     r8d, esi; unsigned __int8
0x180012546  lea     rcx, qword_180021AD8; this
0x18001254d  mov     edx, esi; unsigned int
0x18001254f  mov     ebx, 80070057h
0x180012554  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012559  jmp     loc_180012893
0x18001255e  mov     rdx, [r14]; unsigned __int16 *
0x180012561  mov     r8, r13; unsigned __int16 *
0x180012564  mov     rcx, rbp; unsigned __int16 *
0x180012567  call    ?AppendPath@Utils@@SAJPEBG0PEAGK@Z; Utils::AppendPath(ushort const *,ushort const *,ushort *,ulong)
0x18001256c  mov     ebx, eax
0x18001256e  test    eax, eax
0x180012570  js      loc_180012893
0x180012576  mov     esi, 2
0x18001257b  mov     [rsp+98h+hTemplateFile], r15; hTemplateFile
0x180012580  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180012588  xor     r9d, r9d; lpSecurityAttributes
0x18001258b  mov     edx, 0C0000000h; dwDesiredAccess
0x180012590  mov     [rsp+98h+dwCreationDisposition], esi; dwCreationDisposition
0x180012594  mov     rcx, r13; lpFileName
0x180012597  lea     ebx, [rsi-1]
0x18001259a  mov     r8d, ebx; dwShareMode
0x18001259d  call    cs:__imp_CreateFileW
0x1800125a3  mov     [rdi+50h], rax
0x1800125a7  cmp     rax, r12
0x1800125aa  jnz     short loc_1800125E7
0x1800125ac  call    cs:__imp_GetLastError
0x1800125b2  mov     ebx, eax
0x1800125b4  test    eax, eax
0x1800125b6  jle     short loc_1800125C1
0x1800125b8  movzx   ebx, ax
0x1800125bb  or      ebx, 80070000h
0x1800125c1  mov     [rsp+98h+dwFlagsAndAttributes], ebx
0x1800125c5  lea     r9, aFailedToCreatF; "Failed to Creat File , FileName %s, err"...
0x1800125cc  mov     r8d, esi; unsigned __int8
0x1800125cf  mov     qword ptr [rsp+98h+dwCreationDisposition], r13
0x1800125d4  mov     edx, esi; unsigned int
0x1800125d6  lea     rcx, qword_180021AD8; this
0x1800125dd  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x1800125e2  jmp     loc_18001276F
0x1800125e7  mov     eax, [rsp+98h+arg_28]
0x1800125ee  mov     edx, ebx; int
0x1800125f0  mov     rcx, rdi; this
0x1800125f3  mov     [rdi+80h], eax
0x1800125f9  call    ?CreateHTTPSession@WinHttpDownload@@AEAAJH@Z; WinHttpDownload::CreateHTTPSession(int)
0x1800125fe  mov     ebx, eax
0x180012600  test    eax, eax
0x180012602  js      loc_180012893
0x180012608  cmp     [rdi+70h], r15d
0x18001260c  jz      short loc_180012624
0x18001260e  lea     rdx, [rdi+58h]; struct _WINHTTP_PROXY_INFO *
0x180012612  mov     rcx, rdi; this
0x180012615  call    ?SetProxy@WinHttpDownload@@AEAAJPEAU_WINHTTP_PROXY_INFO@@@Z; WinHttpDownload::SetProxy(_WINHTTP_PROXY_INFO *)
0x18001261a  mov     ebx, eax
0x18001261c  test    eax, eax
0x18001261e  js      loc_180012893
0x180012624  mov     rcx, [rdi+48h]; hInternet
0x180012628  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x180012630  mov     r9d, 4; dwBufferLength
0x180012636  mov     [rsp+98h+Buffer], esi
0x18001263d  lea     edx, [r9+49h]; dwOption
0x180012641  call    cs:__imp_WinHttpSetOption
0x180012647  test    eax, eax
0x180012649  jnz     short loc_180012684
0x18001264b  call    cs:__imp_GetLastError
0x180012651  mov     ebx, eax
0x180012653  test    eax, eax
0x180012655  jle     short loc_180012660
0x180012657  movzx   ebx, ax
0x18001265a  or      ebx, 80070000h
0x180012660  lea     r9, aWinhttpsetopti_0; "WinHttpSetOption Failed Error %x"
0x180012667  mov     r8d, 3; unsigned __int8
0x18001266d  mov     edx, esi; unsigned int
0x18001266f  mov     [rsp+98h+dwCreationDisposition], ebx
0x180012673  lea     rcx, qword_180021AD8; this
0x18001267a  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18001267f  jmp     loc_18001276F
0x180012684  cmp     [rdi+1Ch], esi
0x180012687  jnz     short loc_1800126C2
0x180012689  mov     rcx, [rdi+48h]; hInternet
0x18001268d  xor     r9d, r9d; dwBufferLength
0x180012690  xor     r8d, r8d; lpBuffer
0x180012693  lea     edx, [r9+2Fh]; dwOption
0x180012697  call    cs:__imp_WinHttpSetOption
0x18001269d  test    eax, eax
0x18001269f  jnz     short loc_1800126C2
0x1800126a1  call    cs:__imp_GetLastError
0x1800126a7  mov     ebx, eax
0x1800126a9  test    eax, eax
0x1800126ab  jle     short loc_1800126B6
0x1800126ad  movzx   ebx, ax
0x1800126b0  or      ebx, 80070000h
0x1800126b6  lea     r9, aWinhttpsetopti_0; "WinHttpSetOption Failed Error %x"
0x1800126bd  mov     r8d, esi
0x1800126c0  jmp     short loc_18001266D
0x1800126c2  mov     ebp, 80070000h
0x1800126c7  mov     rcx, [rdi+48h]; hRequest
0x1800126cb  xor     r9d, r9d; lpOptional
0x1800126ce  mov     [rsp+98h+hTemplateFile], r15; dwContext
0x1800126d3  xor     r8d, r8d; dwHeadersLength
0x1800126d6  mov     [rsp+98h+dwFlagsAndAttributes], r15d; dwTotalLength
0x1800126db  xor     edx, edx; lpszHeaders
0x1800126dd  mov     [rsp+98h+dwCreationDisposition], r15d; dwOptionalLength
0x1800126e2  call    cs:__imp_WinHttpSendRequest
0x1800126e8  test    eax, eax
0x1800126ea  jnz     loc_18001277C
0x1800126f0  call    cs:__imp_GetLastError
0x1800126f6  mov     r14d, eax
0x1800126f9  test    eax, eax
0x1800126fb  jg      short loc_180012702
0x1800126fd  mov     r15d, eax
0x180012700  jmp     short loc_180012709
0x180012702  movzx   r15d, r14w
0x180012706  or      r15d, ebp
0x180012709  lea     r9, aWinhttpsendreq_0; "WinHttpSendRequest Failed Error %x"
0x180012710  mov     [rsp+98h+dwCreationDisposition], r15d
0x180012715  mov     r8d, esi; unsigned __int8
0x180012718  lea     rcx, qword_180021AD8; this
0x18001271f  mov     edx, esi; unsigned int
0x180012721  mov     ebx, r15d
0x180012724  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012729  cmp     dword ptr [rdi+70h], 0
0x18001272d  jz      short loc_18001276C
0x18001272f  sub     r14d, 2EE2h
0x180012736  jz      short loc_18001274A
0x180012738  sub     r14d, 5
0x18001273c  jz      short loc_18001274A
0x18001273e  sub     r14d, 16h
0x180012742  jz      short loc_18001274A
0x180012744  cmp     r14d, 1
0x180012748  jnz     short loc_18001276C
0x18001274a  mov     rcx, rdi; this
0x18001274d  call    ?SetNextProxy@WinHttpDownload@@AEAAJXZ; WinHttpDownload::SetNextProxy(void)
0x180012752  mov     ebx, eax
0x180012754  cmp     eax, 1
0x180012757  jz      short loc_180012769
0x180012759  xor     r15d, r15d
0x18001275c  test    eax, eax
0x18001275e  jns     loc_1800126C7
0x180012764  jmp     loc_180012893
0x180012769  mov     ebx, r15d
0x18001276c  xor     r15d, r15d
0x18001276f  test    ebx, ebx
0x180012771  jns     loc_1800128C9
0x180012777  jmp     loc_180012893
0x18001277c  mov     rcx, [rdi+48h]; hRequest
0x180012780  xor     edx, edx; lpReserved
0x180012782  call    cs:__imp_WinHttpReceiveResponse
0x180012788  test    eax, eax
0x18001278a  jnz     short loc_1800127A9
0x18001278c  call    cs:__imp_GetLastError
0x180012792  mov     ebx, eax
0x180012794  test    eax, eax
0x180012796  jle     short loc_18001279D
0x180012798  movzx   ebx, ax
0x18001279b  or      ebx, ebp
0x18001279d  lea     r9, aWinhttpreceive_0; "WinHttpReceiveResponse Failed Error %x"
0x1800127a4  jmp     loc_1800126BD
0x1800127a9  mov     rcx, [rdi+48h]; hRequest
0x1800127ad  lea     rax, [rsp+98h+dwBufferLength]
0x1800127b2  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], r15; lpdwIndex
0x1800127b7  lea     r9, [rsp+98h+arg_20]; lpBuffer
0x1800127bf  xor     r8d, r8d; pwszName
0x1800127c2  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; lpdwBufferLength
0x1800127c7  mov     edx, 20000013h; dwInfoLevel
0x1800127cc  mov     [rsp+98h+dwBufferLength], 4
0x1800127d4  call    cs:__imp_WinHttpQueryHeaders
0x1800127da  test    eax, eax
0x1800127dc  jnz     short loc_1800127F4
0x1800127de  call    cs:__imp_GetLastError
0x1800127e4  mov     ebx, eax
0x1800127e6  test    eax, eax
0x1800127e8  jle     short loc_18001276F
0x1800127ea  movzx   ebx, ax
0x1800127ed  or      ebx, ebp
0x1800127ef  jmp     loc_18001276F
0x1800127f4  mov     eax, [rsp+98h+arg_20]
0x1800127fb  cmp     eax, 191h
0x180012800  jz      short loc_180012813
0x180012802  cmp     eax, 197h
0x180012807  jz      short loc_180012813
0x180012809  test    ebx, ebx
0x18001280b  js      loc_180012893
0x180012811  jmp     short loc_180012858
0x180012813  lea     r9, aConnectionStat; "Connection Status code is %x. Will retr"...
0x18001281a  mov     [rsp+98h+dwCreationDisposition], eax
0x18001281e  mov     r8d, 3; unsigned __int8
0x180012824  lea     rcx, qword_180021AD8; this
0x18001282b  mov     edx, esi; unsigned int
0x18001282d  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180012832  test    ebx, ebx
0x180012834  js      short loc_180012893
0x180012836  lea     rdx, [rsp+98h+arg_20]; unsigned int *
0x18001283e  mov     rcx, rdi; this
0x180012841  call    ?RetrySecureRequest@WinHttpDownload@@AEAAJPEAK@Z; WinHttpDownload::RetrySecureRequest(ulong *)
0x180012846  test    eax, eax
0x180012848  jns     short loc_180012851
0x18001284a  mov     ebx, 80072EEFh
0x18001284f  jmp     short loc_180012893
0x180012851  mov     eax, [rsp+98h+arg_20]
0x180012858  cmp     eax, 0C8h
0x18001285d  jnz     short loc_180012872
0x18001285f  mov     rdx, [rdi+50h]; void *
0x180012863  mov     rcx, rdi; this
0x180012866  call    ?SaveToFile@WinHttpDownload@@AEAAJPEAX@Z; WinHttpDownload::SaveToFile(void *)
0x18001286b  mov     ebx, eax
0x18001286d  jmp     loc_18001276F
0x180012872  lea     r9, aFailedToDownlo; "Failed to download HTTP Status code %x"
0x180012879  mov     [rsp+98h+dwCreationDisposition], eax
0x18001287d  mov     r8d, esi; unsigned __int8
0x180012880  lea     rcx, qword_180021AD8; this
0x180012887  mov     edx, esi; unsigned int
0x180012889  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
  ... truncated ...
```
