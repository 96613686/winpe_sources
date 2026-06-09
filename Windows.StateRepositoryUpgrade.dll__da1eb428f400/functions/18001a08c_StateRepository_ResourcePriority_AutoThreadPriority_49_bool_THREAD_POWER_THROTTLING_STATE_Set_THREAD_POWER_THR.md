# StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::_Set(_THREAD_POWER_THROTTLING_STATE &)

- ea: `0x18001a08c`
- end: `0x18001a0d7`
- name: `?_Set@?$AutoThreadPriority@$0DB@_NU_THREAD_POWER_THROTTLING_STATE@@@ResourcePriority@StateRepository@@IEAAJAEAU_THREAD_POWER_THROTTLING_STATE@@@Z`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019838`

## callees

- `0x180019f6c`
- `0x18001a08c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a0a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a0a2`
- `ntdll!NtSetInformationThread` at `0x18001a0b8`
- `ntdll!NtSetInformationThread` at `0x18001a0b8`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::_Set(
        HANDLE *a1,
        void *a2)
{
  char *CurrentThread; // rcx
  NTSTATUS v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  CurrentThread = (char *)*a1;
  if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    CurrentThread = (char *)GetCurrentThread();
  v4 = NtSetInformationThread(CurrentThread, ThreadHideFromDebugger|0x20, a2, 0xCu);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_NtStatus(retaddr, v5, v6, (const char *)(unsigned int)v4, v8);
  return 0;
}

```

## disassembly

```asm
0x18001a08c  push    rbx; int
0x18001a08e  sub     rsp, 20h
0x18001a092  mov     rcx, [rcx]
0x18001a095  mov     rbx, rdx
0x18001a098  lea     rax, [rcx-1]
0x18001a09c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a0a0  jbe     short loc_18001A0AB
0x18001a0a2  call    cs:__imp_GetCurrentThread
0x18001a0a8  mov     rcx, rax; ThreadHandle
0x18001a0ab  mov     r9d, 0Ch; ThreadInformationLength
0x18001a0b1  mov     r8, rbx; ThreadInformation
0x18001a0b4  lea     edx, [r9+25h]; ThreadInformationClass
0x18001a0b8  call    cs:__imp_NtSetInformationThread
0x18001a0be  test    eax, eax
0x18001a0c0  jns     short loc_18001A0CF
0x18001a0c2  mov     rcx, [rsp+28h]; this
0x18001a0c7  mov     r9d, eax; char *
0x18001a0ca  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18001a0cf  xor     eax, eax
0x18001a0d1  add     rsp, 20h
0x18001a0d5  pop     rbx
0x18001a0d6  retn
```
