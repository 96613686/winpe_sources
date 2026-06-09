# DockedSystem::ChangeThreadPriority(unsigned __int64,int,int)

- ea: `0x1800246c0`
- end: `0x180024843`
- name: `?ChangeThreadPriority@DockedSystem@@UEAAJ_KHH@Z`
- size: `387`
- prototype: `int(DockedSystem *__hidden this, unsigned __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180007660`
- `0x1800183d4`
- `0x1800183f4`
- `0x1800246c0`
- `0x1800255f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002471d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002471d`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x180024772`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x1800247b9`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x180024772`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x1800247b9`
- `ntdll!NtSetInformationThread` at `0x1800247f8`
- `ntdll!NtSetInformationThread` at `0x1800247f8`

## string_xrefs

- `0x1800246f9`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x18002472c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024781`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x1800247c8`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x18002480a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`

## pseudocode

```c
int __fastcall DockedSystem::ChangeThreadPriority(DockedSystem *this, void *a2, int a3, int a4)
{
  const char *v7; // r9
  int result; // eax
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  NTSTATUS v12; // eax
  int ThreadInformation; // [rsp+20h] [rbp-28h] BYREF
  int v14; // [rsp+24h] [rbp-24h] BYREF
  int v15; // [rsp+28h] [rbp-20h] BYREF
  __int64 v16; // [rsp+2Ch] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 )
  {
    if ( SetThreadPriority(a2, a3 != 0 ? 0xFFFFFFFE : 0) )
    {
      v16 = 0;
      v15 = 1;
      if ( a4 )
        v16 = 0x100000001LL;
      if ( (unsigned int)SetThreadInformation(a2, 3, &v15) )
      {
        v14 = a3 != 0 ? 1 : 5;
        if ( (unsigned int)SetThreadInformation(a2, 0, &v14) )
        {
          ThreadInformation = a3 == 0 ? 2 : 0;
          v12 = NtSetInformationThread(a2, ThreadIoPriority, &ThreadInformation, 4u);
          if ( v12 >= 0 )
            result = 0;
          else
            result = wil::details::in1diag3::Return_NtStatus(
                       retaddr,
                       (void *)0x1BA,
                       (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\"
                                     "dockedsystem.cpp",
                       (const char *)(unsigned int)v12,
                       ThreadInformation);
        }
        else
        {
          result = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)0x1B5,
                     (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                     v11);
        }
      }
      else
      {
        result = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x1AE,
                   (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                   v10);
      }
    }
    else
    {
      result = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x1A4,
                 (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                 v9);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80070057LL,
      ThreadInformation);
    result = -2147024809;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      ThreadInformation = wil::details::in1diag3::Return_CaughtException(
                            retaddr,
                            (void *)0x1BE,
                            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\"
                                          "dll\\dockedsystem.cpp",
                            v7);
      result = ThreadInformation;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1800246c0  mov     [rsp+arg_0], rbx
0x1800246c5  mov     [rsp+arg_10], rsi
0x1800246ca  push    rdi
0x1800246cb  sub     rsp, 40h
0x1800246cf  mov     rax, cs:__security_cookie
0x1800246d6  xor     rax, rsp
0x1800246d9  mov     [rsp+48h+var_10], rax
0x1800246de  mov     esi, r9d
0x1800246e1  mov     edi, r8d
0x1800246e4  mov     rbx, rdx
0x1800246e7  test    rdx, rdx
0x1800246ea  jnz     short loc_180024711
0x1800246ec  mov     rcx, [rsp+48h]; this
0x1800246f1  mov     ebx, 80070057h
0x1800246f6  mov     r9d, ebx; char *
0x1800246f9  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024700  mov     edx, 1A0h; void *
0x180024705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002470a  mov     eax, ebx
0x18002470c  jmp     loc_180024825
0x180024711  mov     eax, edi
0x180024713  neg     eax
0x180024715  sbb     edx, edx
0x180024717  and     edx, 0FFFFFFFEh; nPriority
0x18002471a  mov     rcx, rbx; hThread
0x18002471d  call    cs:__imp_SetThreadPriority
0x180024723  test    eax, eax
0x180024725  jnz     short loc_180024742
0x180024727  mov     rcx, [rsp+48h]; this
0x18002472c  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024733  mov     edx, 1A4h; void *
0x180024738  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002473d  jmp     loc_180024825
0x180024742  mov     [rsp+48h+var_1C], 0
0x18002474b  mov     eax, 1
0x180024750  mov     [rsp+48h+var_20], eax
0x180024754  test    esi, esi
0x180024756  jz      short loc_180024760
0x180024758  mov     dword ptr [rsp+48h+var_1C], eax
0x18002475c  mov     dword ptr [rsp+48h+var_1C+4], eax
0x180024760  mov     r9d, 0Ch
0x180024766  lea     r8, [rsp+48h+var_20]
0x18002476b  lea     edx, [r9-9]
0x18002476f  mov     rcx, rbx
0x180024772  call    cs:__imp_SetThreadInformation
0x180024778  test    eax, eax
0x18002477a  jnz     short loc_180024797
0x18002477c  mov     rcx, [rsp+48h]; this
0x180024781  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024788  mov     edx, 1AEh; void *
0x18002478d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024792  jmp     loc_180024825
0x180024797  mov     eax, edi
0x180024799  neg     eax
0x18002479b  sbb     ecx, ecx
0x18002479d  and     ecx, 0FFFFFFFCh
0x1800247a0  add     ecx, 5
0x1800247a3  mov     [rsp+48h+var_24], ecx
0x1800247a7  mov     esi, 4
0x1800247ac  mov     r9d, esi
0x1800247af  lea     r8, [rsp+48h+var_24]
0x1800247b4  xor     edx, edx
0x1800247b6  mov     rcx, rbx
0x1800247b9  call    cs:__imp_SetThreadInformation
0x1800247bf  test    eax, eax
0x1800247c1  jnz     short loc_1800247DB
0x1800247c3  mov     rcx, [rsp+48h]; this
0x1800247c8  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800247cf  mov     edx, 1B5h; void *
0x1800247d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800247d9  jmp     short loc_180024825
0x1800247db  neg     edi
0x1800247dd  sbb     eax, eax
0x1800247df  not     eax
0x1800247e1  and     eax, 2
0x1800247e4  mov     [rsp+48h+ThreadInformation], eax; int
0x1800247e8  mov     r9d, esi; ThreadInformationLength
0x1800247eb  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x1800247f0  mov     edx, 16h; ThreadInformationClass
0x1800247f5  mov     rcx, rbx; ThreadHandle
0x1800247f8  call    cs:__imp_NtSetInformationThread
0x1800247fe  test    eax, eax
0x180024800  jns     short loc_18002481D
0x180024802  mov     rcx, [rsp+48h]; this
0x180024807  mov     r9d, eax; char *
0x18002480a  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024811  mov     edx, 1BAh; void *
0x180024816  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002481b  jmp     short loc_180024825
0x18002481d  xor     eax, eax
0x18002481f  jmp     short loc_180024825
0x180024821  mov     eax, [rsp+48h+ThreadInformation]
0x180024825  mov     rcx, [rsp+48h+var_10]
0x18002482a  xor     rcx, rsp; StackCookie
0x18002482d  call    __security_check_cookie
0x180024832  mov     rbx, [rsp+48h+arg_0]
0x180024837  mov     rsi, [rsp+48h+arg_10]
0x18002483c  add     rsp, 40h
0x180024840  pop     rdi
0x180024841  retn
```
