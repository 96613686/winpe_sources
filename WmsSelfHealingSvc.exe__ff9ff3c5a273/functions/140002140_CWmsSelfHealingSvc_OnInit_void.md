# CWmsSelfHealingSvc::OnInit(void)

- ea: `0x140002140`
- end: `0x1400022fa`
- name: `?OnInit@CWmsSelfHealingSvc@@UEAAHXZ`
- size: `442`
- prototype: `_BOOL8 __fastcall(CWmsSelfHealingSvc *this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002140`
- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1400021fc`
- `KERNEL32!CreateThread` at `0x1400021fc`
- `KERNEL32!IsDebuggerPresent` at `0x14000226d`
- `KERNEL32!IsDebuggerPresent` at `0x14000226d`
- `KERNEL32!GetLastError` at `0x14000217c`
- `KERNEL32!GetLastError` at `0x1400021bf`
- `KERNEL32!GetLastError` at `0x140002212`
- `KERNEL32!GetLastError` at `0x14000217c`
- `KERNEL32!GetLastError` at `0x1400021bf`
- `KERNEL32!GetLastError` at `0x140002212`
- `KERNEL32!CreateEventW` at `0x14000216a`
- `KERNEL32!CreateEventW` at `0x1400021ad`
- `KERNEL32!CreateEventW` at `0x14000216a`
- `KERNEL32!CreateEventW` at `0x1400021ad`

## string_xrefs

- `0x1400021d4`: `m_hThreadProcKillEvent != 0`
- `0x140002227`: `m_hThreadProc`

## pseudocode

```c
_BOOL8 __fastcall CWmsSelfHealingSvc::OnInit(CWmsSelfHealingSvc *this)
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

  DEBUGMSG(L"CWmsSelfHealingSvc::OnInit\n");
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 106) = EventW;
  if ( EventW )
  {
    v7 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 111) = v7;
    if ( v7 )
    {
      v4 = 0;
      Thread = CreateThread(0, 0, CWmsSelfHealingSvc::s_ThreadProc, this, 0, 0);
      *((_QWORD *)this + 110) = Thread;
      if ( Thread )
        goto LABEL_18;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v5 = L"m_hThreadProc";
      v6 = 101;
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      v5 = L"m_hThreadProcKillEvent != 0";
      v6 = 98;
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = L"m_hExitEvent != 0";
    v6 = 95;
  }
  if ( v4 >= 0 )
    v4 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
    v6,
    L"CWmsSelfHealingSvc::OnInit",
    L"CBRAEx",
    v5,
    v4);
  if ( IsDebuggerPresent() )
  {
    v14 = v4;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      v6,
      L"CWmsSelfHealingSvc::OnInit",
      L"CBRAEx",
      v5,
      v14);
  }
  else
  {
    v13 = v4;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      v6,
      L"CWmsSelfHealingSvc::OnInit",
      L"CBRAEx",
      v5,
      v13);
  }
LABEL_18:
  v11 = L"TRUE";
  if ( v4 < 0 )
    v11 = L"FALSE";
  DEBUGMSG(L"CWmsSelfHealingSvc::OnInit returning %s\n", v11);
  return v4 >= 0;
}

```

## disassembly

```asm
0x140002140  push    rbx
0x140002142  push    rbp
0x140002143  push    rsi
0x140002144  push    rdi
0x140002145  push    r14
0x140002147  push    r15
0x140002149  sub     rsp, 48h
0x14000214d  mov     rdi, rcx
0x140002150  lea     rcx, aCwmsselfhealin_28; "CWmsSelfHealingSvc::OnInit\n"
0x140002157  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000215c  xor     r9d, r9d; lpName
0x14000215f  xor     r8d, r8d; bInitialState
0x140002162  xor     ecx, ecx; lpEventAttributes
0x140002164  lea     ebx, [r9+1]
0x140002168  mov     edx, ebx; bManualReset
0x14000216a  call    cs:__imp_CreateEventW
0x140002170  mov     [rdi+350h], rax
0x140002177  test    rax, rax
0x14000217a  jnz     short loc_1400021A3
0x14000217c  call    cs:__imp_GetLastError
0x140002182  mov     ebx, eax
0x140002184  test    eax, eax
0x140002186  jle     short loc_140002191
0x140002188  movzx   ebx, ax
0x14000218b  or      ebx, 80070000h
0x140002191  lea     r15, aMHexitevent0; "m_hExitEvent != 0"
0x140002198  mov     r14d, 5Fh ; '_'
0x14000219e  jmp     loc_140002234
0x1400021a3  xor     r9d, r9d; lpName
0x1400021a6  xor     r8d, r8d; bInitialState
0x1400021a9  mov     edx, ebx; bManualReset
0x1400021ab  xor     ecx, ecx; lpEventAttributes
0x1400021ad  call    cs:__imp_CreateEventW
0x1400021b3  mov     [rdi+378h], rax
0x1400021ba  test    rax, rax
0x1400021bd  jnz     short loc_1400021E3
0x1400021bf  call    cs:__imp_GetLastError
0x1400021c5  mov     ebx, eax
0x1400021c7  test    eax, eax
0x1400021c9  jle     short loc_1400021D4
0x1400021cb  movzx   ebx, ax
0x1400021ce  or      ebx, 80070000h
0x1400021d4  lea     r15, aMHthreadprocki_0; "m_hThreadProcKillEvent != 0"
0x1400021db  mov     r14d, 62h ; 'b'
0x1400021e1  jmp     short loc_140002234
0x1400021e3  xor     ebx, ebx
0x1400021e5  lea     r8, ?s_ThreadProc@CWmsSelfHealingSvc@@CAKPEAX@Z; lpStartAddress
0x1400021ec  mov     [rsp+78h+lpThreadId], rbx; lpThreadId
0x1400021f1  mov     r9, rdi; lpParameter
0x1400021f4  xor     edx, edx; dwStackSize
0x1400021f6  mov     [rsp+78h+dwCreationFlags], ebx; dwCreationFlags
0x1400021fa  xor     ecx, ecx; lpThreadAttributes
0x1400021fc  call    cs:__imp_CreateThread
0x140002202  mov     [rdi+370h], rax
0x140002209  test    rax, rax
0x14000220c  jnz     loc_1400022C6
0x140002212  call    cs:__imp_GetLastError
0x140002218  mov     ebx, eax
0x14000221a  test    eax, eax
0x14000221c  jle     short loc_140002227
0x14000221e  movzx   ebx, ax
0x140002221  or      ebx, 80070000h
0x140002227  lea     r15, aMHthreadproc; "m_hThreadProc"
0x14000222e  mov     r14d, 65h ; 'e'
0x140002234  mov     eax, 80004005h
0x140002239  lea     rbp, aCbraex; "CBRAEx"
0x140002240  test    ebx, ebx
0x140002242  lea     rsi, aCwmsselfhealin_27; "CWmsSelfHealingSvc::OnInit"
0x140002249  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002250  mov     r9, rbp; unsigned __int16 *
0x140002253  cmovns  ebx, eax
0x140002256  mov     r8, rsi; unsigned __int16 *
0x140002259  mov     dword ptr [rsp+78h+lpThreadId], ebx; int
0x14000225d  mov     edx, r14d; unsigned int
0x140002260  mov     rcx, rdi; unsigned __int16 *
0x140002263  mov     qword ptr [rsp+78h+dwCreationFlags], r15; unsigned __int16 *
0x140002268  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000226d  call    cs:__imp_IsDebuggerPresent
0x140002273  test    eax, eax
0x140002275  jz      short loc_1400022A3
0x140002277  mov     [rsp+78h+var_40], ebx
0x14000227b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140002282  mov     [rsp+78h+var_48], r15
0x140002287  mov     r9d, r14d
0x14000228a  mov     [rsp+78h+lpThreadId], rbp
0x14000228f  mov     r8, rdi
0x140002292  mov     ecx, 2; unsigned __int8
0x140002297  mov     qword ptr [rsp+78h+dwCreationFlags], rsi
0x14000229c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400022a1  jmp     short loc_1400022C6
0x1400022a3  mov     dword ptr [rsp+78h+var_48], ebx
0x1400022a7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400022ae  mov     [rsp+78h+lpThreadId], r15
0x1400022b3  mov     r9, rsi
0x1400022b6  mov     r8d, r14d
0x1400022b9  mov     qword ptr [rsp+78h+dwCreationFlags], rbp
0x1400022be  mov     rdx, rdi
0x1400022c1  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400022c6  lea     rax, aFalse; "FALSE"
0x1400022cd  test    ebx, ebx
0x1400022cf  lea     rdx, aTrue; "TRUE"
0x1400022d6  cmovs   rdx, rax
0x1400022da  lea     rcx, aCwmsselfhealin_0; "CWmsSelfHealingSvc::OnInit returning %s"...
0x1400022e1  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400022e6  not     ebx
0x1400022e8  shr     ebx, 1Fh
0x1400022eb  mov     eax, ebx
0x1400022ed  add     rsp, 48h
0x1400022f1  pop     r15
0x1400022f3  pop     r14
0x1400022f5  pop     rdi
0x1400022f6  pop     rsi
0x1400022f7  pop     rbp
0x1400022f8  pop     rbx
0x1400022f9  retn
```
