# StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::_Set(_THREAD_POWER_THROTTLING_STATE &)

- ea: `0x1800a2ff8`
- end: `0x1800a304f`
- name: `?_Set@?$AutoThreadPriority@$0DB@_NU_THREAD_POWER_THROTTLING_STATE@@@ResourcePriority@StateRepository@@IEAAJAEAU_THREAD_POWER_THROTTLING_STATE@@@Z`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800a2ea4`

## callees

- `0x18007bbb4`
- `0x1800a2ff8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a300e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a300e`
- `ntdll!NtSetInformationThread` at `0x1800a3024`
- `ntdll!NtSetInformationThread` at `0x1800a3024`

## string_xrefs

- `0x1800a3033`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::_Set(
        HANDLE *a1,
        void *a2)
{
  char *CurrentThread; // rcx
  NTSTATUS v4; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  CurrentThread = (char *)*a1;
  if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    CurrentThread = (char *)GetCurrentThread();
  v4 = NtSetInformationThread(CurrentThread, ThreadHideFromDebugger|0x20, a2, 0xCu);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
      (const char *)(unsigned int)v4,
      v6);
  return 0;
}

```

## disassembly

```asm
0x1800a2ff8  push    rbx; int
0x1800a2ffa  sub     rsp, 20h
0x1800a2ffe  mov     rcx, [rcx]
0x1800a3001  mov     rbx, rdx
0x1800a3004  lea     rax, [rcx-1]
0x1800a3008  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a300c  jbe     short loc_1800A3017
0x1800a300e  call    cs:__imp_GetCurrentThread
0x1800a3014  mov     rcx, rax; ThreadHandle
0x1800a3017  mov     r9d, 0Ch; ThreadInformationLength
0x1800a301d  mov     r8, rbx; ThreadInformation
0x1800a3020  lea     edx, [r9+25h]; ThreadInformationClass
0x1800a3024  call    cs:__imp_NtSetInformationThread
0x1800a302a  test    eax, eax
0x1800a302c  jns     short loc_1800A3047
0x1800a302e  mov     rcx, [rsp+28h]; this
0x1800a3033  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800a303a  mov     r9d, eax; char *
0x1800a303d  mov     edx, 89h; void *
0x1800a3042  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800a3047  xor     eax, eax
0x1800a3049  add     rsp, 20h
0x1800a304d  pop     rbx
0x1800a304e  retn
```
