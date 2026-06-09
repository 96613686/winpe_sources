# Windows::Compat::Appraiser::SetupAppraiser::ExecuteWicaThread(Windows::Compat::Appraiser::WicaRun &)

- ea: `0x180039208`
- end: `0x1800393d0`
- name: `?ExecuteWicaThread@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEAUWicaRun@234@@Z`
- size: `456`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct Windows::Compat::Appraiser::WicaRun *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180044094`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x180039208`
- `0x1800a5d88`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x1800392eb`
- `KERNEL32!ResetEvent` at `0x1800392eb`
- `KERNEL32!CreateThread` at `0x180039251`
- `KERNEL32!CreateThread` at `0x180039251`
- `KERNEL32!WaitForMultipleObjects` at `0x1800392d4`
- `KERNEL32!WaitForMultipleObjects` at `0x1800392d4`
- `KERNEL32!TerminateThread` at `0x1800392f9`
- `KERNEL32!TerminateThread` at `0x1800392f9`
- `KERNEL32!GetLastError` at `0x18003925f`
- `KERNEL32!GetLastError` at `0x18003927a`
- `KERNEL32!GetLastError` at `0x180039310`
- `KERNEL32!GetLastError` at `0x180039318`
- `KERNEL32!GetLastError` at `0x180039348`
- `KERNEL32!GetLastError` at `0x18003925f`
- `KERNEL32!GetLastError` at `0x18003927a`
- `KERNEL32!GetLastError` at `0x180039310`
- `KERNEL32!GetLastError` at `0x180039318`
- `KERNEL32!GetLastError` at `0x180039348`

## string_xrefs

- `0x18003929e`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800393b6`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800392a5`: `Windows::Compat::Appraiser::SetupAppraiser::ExecuteWicaThread`
- `0x1800393aa`: `Windows::Compat::Appraiser::SetupAppraiser::ExecuteWicaThread`
- `0x180039289`: `Failed to create thread: [%d].`
- `0x18003932e`: `Could not terminate run thread: [%d].`
- `0x18003934e`: `Could not terminate run thread: [%d].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::ExecuteWicaThread(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::WicaRun *a2)
{
  HANDLE v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  char v6; // dl
  DWORD v7; // edi
  signed int v8; // eax
  char *v10; // [rsp+20h] [rbp-68h]
  const char *v11; // [rsp+28h] [rbp-60h]
  char *v12; // [rsp+30h] [rbp-58h]
  struct Windows::Compat::Appraiser::WicaRun *v13; // [rsp+40h] [rbp-48h] BYREF
  int v14; // [rsp+48h] [rbp-40h]
  int v15; // [rsp+4Ch] [rbp-3Ch]
  __int128 Handles; // [rsp+50h] [rbp-38h] BYREF

  v13 = a2;
  v15 = 0;
  v14 = -2147467259;
  Handles = 0;
  v3 = CreateThread(0, 0, Windows::Compat::Appraiser::SetupAppraiser::RunWicaThreadProc, &v13, 0, 0);
  if ( !v3 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
      v5 = -2147467259;
    LODWORD(v12) = GetLastError();
    v6 = -61;
    v11 = "Failed to create thread: [%d].";
    goto LABEL_7;
  }
  *(_QWORD *)&Handles = *((_QWORD *)this + 6);
  *((_QWORD *)&Handles + 1) = v3;
  if ( WaitForMultipleObjects(2u, (const HANDLE *)&Handles, 0, 0xFFFFFFFF) )
  {
    v5 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v12) = v14;
      v11 = "WicaRun failed: [0x%x].";
      v6 = -40;
LABEL_7:
      LODWORD(v10) = v5;
LABEL_8:
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v6,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::ExecuteWicaThread",
        v10,
        (int)v11,
        v12);
      return v5;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xD8u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::ExecuteWicaThread",
        "WicaRun failed: [0x%x].",
        v14);
    return 0;
  }
  else
  {
    v5 = -2144337869;
    ResetEvent(*((HANDLE *)this + 6));
    if ( !TerminateThread(v3, 0x4C7u) )
    {
      if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
      {
        v7 = GetLastError();
        v8 = GetLastError();
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        LODWORD(v12) = v7;
        v11 = "Could not terminate run thread: [%d].";
        v6 = -44;
        LODWORD(v10) = v8;
        goto LABEL_8;
      }
      LODWORD(v12) = GetLastError();
      Windows::Compat::Appraiser::WriteLog(
        0,
        212,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::ExecuteWicaThread",
        0,
        (int)"Could not terminate run thread: [%d].",
        v12);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180039208  mov     rax, rsp
0x18003920b  push    rbx
0x18003920c  push    rsi
0x18003920d  push    rdi
0x18003920e  push    r14
0x180039210  sub     rsp, 68h
0x180039214  mov     rsi, rcx
0x180039217  mov     [rax-48h], rdx
0x18003921b  xorps   xmm0, xmm0
0x18003921e  mov     qword ptr [rax-60h], 0
0x180039226  mov     r14d, 80004005h
0x18003922c  mov     dword ptr [rax-3Ch], 0
0x180039233  xor     edx, edx; dwStackSize
0x180039235  mov     [rax-40h], r14d
0x180039239  xor     ecx, ecx; lpThreadAttributes
0x18003923b  mov     dword ptr [rax-68h], 0
0x180039242  lea     r9, [rax-48h]; lpParameter
0x180039246  lea     r8, ?RunWicaThreadProc@SetupAppraiser@Appraiser@Compat@Windows@@CAKPEAX@Z; lpStartAddress
0x18003924d  movups  xmmword ptr [rax-38h], xmm0
0x180039251  call    cs:__imp_CreateThread
0x180039257  mov     rdi, rax
0x18003925a  test    rax, rax
0x18003925d  jnz     short loc_1800392B6
0x18003925f  call    cs:__imp_GetLastError
0x180039265  mov     ebx, eax
0x180039267  test    eax, eax
0x180039269  jle     short loc_180039274
0x18003926b  movzx   ebx, ax
0x18003926e  or      ebx, 80070000h
0x180039274  test    ebx, ebx
0x180039276  cmovns  ebx, r14d
0x18003927a  call    cs:__imp_GetLastError
0x180039280  mov     dword ptr [rsp+88h+var_58], eax; char *
0x180039284  mov     edx, 0C3h; bool
0x180039289  lea     rax, aFailedToCreate_13; "Failed to create thread: [%d]."
0x180039290  mov     qword ptr [rsp+88h+var_60], rax; int
0x180039295  mov     dword ptr [rsp+88h+var_68], ebx; char *
0x180039299  mov     ecx, 1; this
0x18003929e  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800392a5  lea     r9, aWindowsCompatA_151; "Windows::Compat::Appraiser::SetupApprai"...
0x1800392ac  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800392b1  jmp     loc_1800393C4
0x1800392b6  mov     rax, [rsi+30h]
0x1800392ba  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1800392bf  xor     r8d, r8d; bWaitAll
0x1800392c2  mov     [rsp+88h+Handles], rax
0x1800392c7  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800392cb  mov     [rsp+88h+var_30], rdi
0x1800392d0  lea     ecx, [r8+2]; nCount
0x1800392d4  call    cs:__imp_WaitForMultipleObjects
0x1800392da  test    eax, eax
0x1800392dc  jnz     loc_180039373
0x1800392e2  mov     rcx, [rsi+30h]; hEvent
0x1800392e6  mov     ebx, 80300033h
0x1800392eb  call    cs:__imp_ResetEvent
0x1800392f1  mov     edx, 4C7h; dwExitCode
0x1800392f6  mov     rcx, rdi; hThread
0x1800392f9  call    cs:__imp_TerminateThread
0x1800392ff  test    eax, eax
0x180039301  jnz     loc_1800393C4
0x180039307  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x18003930c  test    al, al
0x18003930e  jz      short loc_180039348
0x180039310  call    cs:__imp_GetLastError
0x180039316  mov     edi, eax
0x180039318  call    cs:__imp_GetLastError
0x18003931e  test    eax, eax
0x180039320  jle     short loc_18003932A
0x180039322  movzx   eax, ax
0x180039325  or      eax, 80070000h
0x18003932a  mov     dword ptr [rsp+88h+var_58], edi
0x18003932e  lea     rcx, aCouldNotTermin; "Could not terminate run thread: [%d]."
0x180039335  mov     qword ptr [rsp+88h+var_60], rcx
0x18003933a  mov     edx, 0D4h
0x18003933f  mov     dword ptr [rsp+88h+var_68], eax
0x180039343  jmp     loc_180039299
0x180039348  call    cs:__imp_GetLastError
0x18003934e  lea     rcx, aCouldNotTermin; "Could not terminate run thread: [%d]."
0x180039355  mov     dword ptr [rsp+88h+var_58], eax
0x180039359  mov     qword ptr [rsp+88h+var_60], rcx
0x18003935e  mov     edx, 0D4h
0x180039363  mov     [rsp+88h+var_68], 0
0x18003936c  xor     ecx, ecx
0x18003936e  jmp     loc_18003929E
0x180039373  mov     ebx, [rsp+88h+var_40]
0x180039377  test    ebx, ebx
0x180039379  jns     short loc_180039395
0x18003937b  lea     r9, aWicarunFailed0; "WicaRun failed: [0x%x]."
0x180039382  mov     dword ptr [rsp+88h+var_58], ebx
0x180039386  mov     qword ptr [rsp+88h+var_60], r9
0x18003938b  mov     edx, 0D8h
0x180039390  jmp     loc_180039295
0x180039395  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003939b  test    al, 1
0x18003939d  jz      short loc_1800393C2
0x18003939f  lea     r9, aWicarunFailed0; "WicaRun failed: [0x%x]."
0x1800393a6  mov     dword ptr [rsp+88h+var_68], ebx
0x1800393aa  lea     r8, aWindowsCompatA_151; "Windows::Compat::Appraiser::SetupApprai"...
0x1800393b1  mov     ecx, 0D8h; unsigned int
0x1800393b6  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800393bd  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800393c2  xor     ebx, ebx
0x1800393c4  mov     eax, ebx
0x1800393c6  add     rsp, 68h
0x1800393ca  pop     r14
0x1800393cc  pop     rdi
0x1800393cd  pop     rsi
0x1800393ce  pop     rbx
0x1800393cf  retn
```
