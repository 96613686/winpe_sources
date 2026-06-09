# DockedSystem::ChangeProcessPriority(unsigned __int64,int,int)

- ea: `0x180024530`
- end: `0x1800246b6`
- name: `?ChangeProcessPriority@DockedSystem@@UEAAJ_KHH@Z`
- size: `390`
- prototype: `int(DockedSystem *__hidden this, unsigned __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180007660`
- `0x1800183d4`
- `0x1800183f4`
- `0x180024530`
- `0x1800255f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180024593`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180024593`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x1800245ea`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18002462c`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x1800245ea`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18002462c`
- `ntdll!NtSetInformationProcess` at `0x18002466b`
- `ntdll!NtSetInformationProcess` at `0x18002466b`

## string_xrefs

- `0x180024569`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x1800245a2`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x1800245f9`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x18002463b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x18002467d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`

## pseudocode

```c
int __fastcall DockedSystem::ChangeProcessPriority(DockedSystem *this, void *a2, int a3, int a4)
{
  const char *v7; // r9
  int result; // eax
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  NTSTATUS v12; // eax
  int ProcessInformation; // [rsp+20h] [rbp-28h] BYREF
  int v14; // [rsp+24h] [rbp-24h] BYREF
  int v15; // [rsp+28h] [rbp-20h] BYREF
  __int64 v16; // [rsp+2Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 )
  {
    if ( SetPriorityClass(a2, a3 != 0 ? 0x4000 : 32) )
    {
      v16 = 0;
      v15 = 1;
      if ( a4 )
        v16 = 0x100000001LL;
      if ( (unsigned int)SetProcessInformation(a2, 4, &v15) )
      {
        v14 = a3 != 0 ? 1 : 5;
        if ( (unsigned int)SetProcessInformation(a2, 0, &v14) )
        {
          ProcessInformation = a3 == 0 ? 2 : 0;
          v12 = NtSetInformationProcess(a2, ProcessIoPriority, &ProcessInformation, 4u);
          if ( v12 >= 0 )
            result = 0;
          else
            result = wil::details::in1diag3::Return_NtStatus(
                       retaddr,
                       (void *)0x197,
                       (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\"
                                     "dockedsystem.cpp",
                       (const char *)(unsigned int)v12,
                       ProcessInformation);
        }
        else
        {
          result = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)0x192,
                     (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                     v11);
        }
      }
      else
      {
        result = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x18B,
                   (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                   v10);
      }
    }
    else
    {
      result = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x181,
                 (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                 v9);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80070057LL,
      ProcessInformation);
    result = -2147024809;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      ProcessInformation = wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x19B,
                             (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\"
                                           "dll\\dockedsystem.cpp",
                             v7);
      result = ProcessInformation;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180024530  mov     [rsp+arg_0], rbx
0x180024535  mov     [rsp+arg_10], rsi
0x18002453a  push    rdi
0x18002453b  sub     rsp, 40h
0x18002453f  mov     rax, cs:__security_cookie
0x180024546  xor     rax, rsp
0x180024549  mov     [rsp+48h+var_10], rax
0x18002454e  mov     esi, r9d
0x180024551  mov     edi, r8d
0x180024554  mov     rbx, rdx
0x180024557  test    rdx, rdx
0x18002455a  jnz     short loc_180024581
0x18002455c  mov     rcx, [rsp+48h]; this
0x180024561  mov     ebx, 80070057h
0x180024566  mov     r9d, ebx; char *
0x180024569  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024570  mov     edx, 17Dh; void *
0x180024575  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002457a  mov     eax, ebx
0x18002457c  jmp     loc_180024698
0x180024581  mov     eax, edi
0x180024583  neg     eax
0x180024585  sbb     edx, edx
0x180024587  and     edx, 3FE0h
0x18002458d  add     edx, 20h ; ' '; dwPriorityClass
0x180024590  mov     rcx, rbx; hProcess
0x180024593  call    cs:__imp_SetPriorityClass
0x180024599  test    eax, eax
0x18002459b  jnz     short loc_1800245B8
0x18002459d  mov     rcx, [rsp+48h]; this
0x1800245a2  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800245a9  mov     edx, 181h; void *
0x1800245ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800245b3  jmp     loc_180024698
0x1800245b8  mov     [rsp+48h+var_1C], 0
0x1800245c1  mov     eax, 1
0x1800245c6  mov     [rsp+48h+var_20], eax
0x1800245ca  test    esi, esi
0x1800245cc  jz      short loc_1800245D6
0x1800245ce  mov     dword ptr [rsp+48h+var_1C], eax
0x1800245d2  mov     dword ptr [rsp+48h+var_1C+4], eax
0x1800245d6  mov     r9d, 0Ch
0x1800245dc  lea     r8, [rsp+48h+var_20]
0x1800245e1  lea     esi, [r9-8]
0x1800245e5  mov     edx, esi
0x1800245e7  mov     rcx, rbx
0x1800245ea  call    cs:__imp_SetProcessInformation
0x1800245f0  test    eax, eax
0x1800245f2  jnz     short loc_18002460F
0x1800245f4  mov     rcx, [rsp+48h]; this
0x1800245f9  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024600  mov     edx, 18Bh; void *
0x180024605  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002460a  jmp     loc_180024698
0x18002460f  mov     eax, edi
0x180024611  neg     eax
0x180024613  sbb     ecx, ecx
0x180024615  and     ecx, 0FFFFFFFCh
0x180024618  add     ecx, 5
0x18002461b  mov     [rsp+48h+var_24], ecx
0x18002461f  mov     r9d, esi
0x180024622  lea     r8, [rsp+48h+var_24]
0x180024627  xor     edx, edx
0x180024629  mov     rcx, rbx
0x18002462c  call    cs:__imp_SetProcessInformation
0x180024632  test    eax, eax
0x180024634  jnz     short loc_18002464E
0x180024636  mov     rcx, [rsp+48h]; this
0x18002463b  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024642  mov     edx, 192h; void *
0x180024647  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002464c  jmp     short loc_180024698
0x18002464e  neg     edi
0x180024650  sbb     eax, eax
0x180024652  not     eax
0x180024654  and     eax, 2
0x180024657  mov     [rsp+48h+ProcessInformation], eax; int
0x18002465b  mov     r9d, esi; ProcessInformationLength
0x18002465e  lea     r8, [rsp+48h+ProcessInformation]; ProcessInformation
0x180024663  mov     edx, 21h ; '!'; ProcessInformationClass
0x180024668  mov     rcx, rbx; ProcessHandle
0x18002466b  call    cs:__imp_NtSetInformationProcess
0x180024671  test    eax, eax
0x180024673  jns     short loc_180024690
0x180024675  mov     rcx, [rsp+48h]; this
0x18002467a  mov     r9d, eax; char *
0x18002467d  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024684  mov     edx, 197h; void *
0x180024689  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002468e  jmp     short loc_180024698
0x180024690  xor     eax, eax
0x180024692  jmp     short loc_180024698
0x180024694  mov     eax, [rsp+48h+ProcessInformation]
0x180024698  mov     rcx, [rsp+48h+var_10]
0x18002469d  xor     rcx, rsp; StackCookie
0x1800246a0  call    __security_check_cookie
0x1800246a5  mov     rbx, [rsp+48h+arg_0]
0x1800246aa  mov     rsi, [rsp+48h+arg_10]
0x1800246af  add     rsp, 40h
0x1800246b3  pop     rdi
0x1800246b4  retn
```
