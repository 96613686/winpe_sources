# CWmsService::OnInit(void)

- ea: `0x140044fa0`
- end: `0x140045172`
- name: `?OnInit@CWmsService@@UEAAHXZ`
- size: `466`
- prototype: `__int64 __fastcall(CWmsService *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x140007fd0`
- `0x140044fa0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1400450fe`
- `KERNEL32!CreateThread` at `0x1400450fe`
- `KERNEL32!CreateEventW` at `0x140044fca`
- `KERNEL32!CreateEventW` at `0x1400450a6`
- `KERNEL32!CreateEventW` at `0x140044fca`
- `KERNEL32!CreateEventW` at `0x1400450a6`
- `KERNEL32!GetLastError` at `0x140044fe0`
- `KERNEL32!GetLastError` at `0x1400450b8`
- `KERNEL32!GetLastError` at `0x140045110`
- `KERNEL32!GetLastError` at `0x140044fe0`
- `KERNEL32!GetLastError` at `0x1400450b8`
- `KERNEL32!GetLastError` at `0x140045110`
- `KERNEL32!IsDebuggerPresent` at `0x14004503b`
- `KERNEL32!IsDebuggerPresent` at `0x14004503b`

## string_xrefs

- `0x140044fb0`: `CWmsService::OnInit\n`
- `0x140045010`: `CWmsService::OnInit`
- `0x140045017`: `termsrv\wms\src\devices\wmssvc\wmsservice.cpp`
- `0x1400450cd`: `m_hThreadProcKillEvent != 0`
- `0x140045125`: `m_hThreadProc`
- `0x140045152`: `CWmsService::OnInit returning %s\n`

## pseudocode

```c
_BOOL8 __fastcall CWmsService::OnInit(CWmsService *this)
{
  HANDLE EventW; // rax
  signed int v3; // eax
  signed int v4; // ebx
  const unsigned __int16 *v5; // r15
  unsigned int v6; // r14d
  HANDLE v7; // rax
  signed int v8; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  const wchar_t *v11; // rdx
  signed int v13; // [rsp+30h] [rbp-48h]
  signed int v14; // [rsp+38h] [rbp-40h]

  DEBUGMSG(L"CWmsService::OnInit\n");
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 106) = EventW;
  if ( EventW )
  {
    v7 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 148) = v7;
    if ( v7 )
    {
      Thread = CreateThread(0, 0, CWmsService::s_ThreadProc, this, 0, 0);
      *((_QWORD *)this + 147) = Thread;
      if ( Thread )
      {
        CDelayedWdpUninstallManager::s_Init();
        v4 = 0;
        goto LABEL_19;
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v5 = L"m_hThreadProc";
      v6 = 177;
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      v5 = L"m_hThreadProcKillEvent != 0";
      v6 = 174;
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = L"m_hExitEvent != 0";
    v6 = 171;
  }
  if ( v4 >= 0 )
    v4 = -2147467259;
  LOGASSERTHR(L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp", v6, L"CWmsService::OnInit", L"CBRAEx", v5, v4);
  if ( IsDebuggerPresent() )
  {
    v14 = v4;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
      v6,
      L"CWmsService::OnInit",
      L"CBRAEx",
      v5,
      v14);
  }
  else
  {
    v13 = v4;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
      v6,
      L"CWmsService::OnInit",
      L"CBRAEx",
      v5,
      v13);
  }
LABEL_19:
  v11 = L"TRUE";
  if ( v4 < 0 )
    v11 = L"FALSE";
  DEBUGMSG(L"CWmsService::OnInit returning %s\n", v11);
  return v4 >= 0;
}

```

## disassembly

```asm
0x140044fa0  push    rbx
0x140044fa2  push    rbp
0x140044fa3  push    rsi
0x140044fa4  push    rdi
0x140044fa5  push    r14
0x140044fa7  push    r15
0x140044fa9  sub     rsp, 48h
0x140044fad  mov     rbx, rcx
0x140044fb0  lea     rcx, aCwmsserviceOni_1; "CWmsService::OnInit\n"
0x140044fb7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140044fbc  xor     r9d, r9d; lpName
0x140044fbf  xor     r8d, r8d; bInitialState
0x140044fc2  xor     ecx, ecx; lpEventAttributes
0x140044fc4  lea     edi, [r9+1]
0x140044fc8  mov     edx, edi; bManualReset
0x140044fca  call    cs:__imp_CreateEventW
0x140044fd0  mov     [rbx+350h], rax
0x140044fd7  test    rax, rax
0x140044fda  jnz     loc_14004509C
0x140044fe0  call    cs:__imp_GetLastError
0x140044fe6  mov     ebx, eax
0x140044fe8  test    eax, eax
0x140044fea  jle     short loc_140044FF5
0x140044fec  movzx   ebx, ax
0x140044fef  or      ebx, 80070000h
0x140044ff5  lea     r15, aMHexitevent0; "m_hExitEvent != 0"
0x140044ffc  mov     r14d, 0ABh
0x140045002  mov     eax, 80004005h
0x140045007  lea     rbp, aCbraex; "CBRAEx"
0x14004500e  test    ebx, ebx
0x140045010  lea     rsi, aCwmsserviceOni; "CWmsService::OnInit"
0x140045017  lea     rdi, aTermsrvWmsSrcD_6; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004501e  mov     r9, rbp; unsigned __int16 *
0x140045021  cmovns  ebx, eax
0x140045024  mov     r8, rsi; unsigned __int16 *
0x140045027  mov     dword ptr [rsp+78h+lpThreadId], ebx; int
0x14004502b  mov     edx, r14d; unsigned int
0x14004502e  mov     rcx, rdi; unsigned __int16 *
0x140045031  mov     qword ptr [rsp+78h+dwCreationFlags], r15; unsigned __int16 *
0x140045036  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004503b  call    cs:__imp_IsDebuggerPresent
0x140045041  test    eax, eax
0x140045043  jz      short loc_140045074
0x140045045  mov     [rsp+78h+var_40], ebx
0x140045049  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140045050  mov     [rsp+78h+var_48], r15
0x140045055  mov     r9d, r14d
0x140045058  mov     [rsp+78h+lpThreadId], rbp
0x14004505d  mov     r8, rdi
0x140045060  mov     ecx, 2; unsigned __int8
0x140045065  mov     qword ptr [rsp+78h+dwCreationFlags], rsi
0x14004506a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004506f  jmp     loc_14004513E
0x140045074  mov     dword ptr [rsp+78h+var_48], ebx
0x140045078  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004507f  mov     [rsp+78h+lpThreadId], r15
0x140045084  mov     r9, rsi
0x140045087  mov     r8d, r14d
0x14004508a  mov     qword ptr [rsp+78h+dwCreationFlags], rbp
0x14004508f  mov     rdx, rdi
0x140045092  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140045097  jmp     loc_14004513E
0x14004509c  xor     r9d, r9d; lpName
0x14004509f  xor     r8d, r8d; bInitialState
0x1400450a2  mov     edx, edi; bManualReset
0x1400450a4  xor     ecx, ecx; lpEventAttributes
0x1400450a6  call    cs:__imp_CreateEventW
0x1400450ac  mov     [rbx+4A0h], rax
0x1400450b3  test    rax, rax
0x1400450b6  jnz     short loc_1400450DF
0x1400450b8  call    cs:__imp_GetLastError
0x1400450be  mov     ebx, eax
0x1400450c0  test    eax, eax
0x1400450c2  jle     short loc_1400450CD
0x1400450c4  movzx   ebx, ax
0x1400450c7  or      ebx, 80070000h
0x1400450cd  lea     r15, aMHthreadprocki_0; "m_hThreadProcKillEvent != 0"
0x1400450d4  mov     r14d, 0AEh
0x1400450da  jmp     loc_140045002
0x1400450df  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x1400450e8  lea     r8, ?s_ThreadProc@CWmsService@@CAKPEAX@Z; lpStartAddress
0x1400450ef  mov     r9, rbx; lpParameter
0x1400450f2  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1400450fa  xor     edx, edx; dwStackSize
0x1400450fc  xor     ecx, ecx; lpThreadAttributes
0x1400450fe  call    cs:__imp_CreateThread
0x140045104  mov     [rbx+498h], rax
0x14004510b  test    rax, rax
0x14004510e  jnz     short loc_140045137
0x140045110  call    cs:__imp_GetLastError
0x140045116  mov     ebx, eax
0x140045118  test    eax, eax
0x14004511a  jle     short loc_140045125
0x14004511c  movzx   ebx, ax
0x14004511f  or      ebx, 80070000h
0x140045125  lea     r15, aMHthreadproc; "m_hThreadProc"
0x14004512c  mov     r14d, 0B1h
0x140045132  jmp     loc_140045002
0x140045137  call    ?s_Init@CDelayedWdpUninstallManager@@SAJXZ; CDelayedWdpUninstallManager::s_Init(void)
0x14004513c  xor     ebx, ebx
0x14004513e  lea     rax, aFalse; "FALSE"
0x140045145  test    ebx, ebx
0x140045147  lea     rdx, aTrue; "TRUE"
0x14004514e  cmovs   rdx, rax
0x140045152  lea     rcx, aCwmsserviceOni_0; "CWmsService::OnInit returning %s\n"
0x140045159  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004515e  not     ebx
0x140045160  shr     ebx, 1Fh
0x140045163  mov     eax, ebx
0x140045165  add     rsp, 48h
0x140045169  pop     r15
0x14004516b  pop     r14
0x14004516d  pop     rdi
0x14004516e  pop     rsi
0x14004516f  pop     rbp
0x140045170  pop     rbx
0x140045171  retn
```
