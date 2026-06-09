# StateRepository::ResourcePriority::AutoThreadPriority<22,_IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Get(_IO_PRIORITY_HINT &)

- ea: `0x180106518`
- end: `0x1801065b4`
- name: `?Get@?$AutoThreadPriority@$0BG@W4_IO_PRIORITY_HINT@@U_FILE_IO_PRIORITY_HINT_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJAEAW4_IO_PRIORITY_HINT@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(HANDLE *, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800fc9e8`
- `0x180103210`
- `0x180106704`

## callees

- `0x1800eabf4`
- `0x1800fb7f0`
- `0x180106518`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010653a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010653a`
- `ntdll!NtQueryInformationThread` at `0x18010655b`
- `ntdll!NtQueryInformationThread` at `0x18010655b`

## string_xrefs

- `0x18010656a`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x180106589`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<22,enum _IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Get(
        HANDLE *a1,
        _DWORD *a2)
{
  char *CurrentThread; // rcx
  NTSTATUS v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  int ReturnLengtha; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int ThreadInformation; // [rsp+40h] [rbp+8h] BYREF

  CurrentThread = (char *)*a1;
  ThreadInformation = 0;
  if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    CurrentThread = (char *)GetCurrentThread();
  v4 = NtQueryInformationThread(CurrentThread, ThreadIoPriority, &ThreadInformation, 4u, 0);
  if ( v4 >= 0
    || (v5 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x7E,
               (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
               (const char *)(unsigned int)v4,
               ReturnLength),
        v6 = v5,
        v5 >= 0) )
  {
    *a2 = ThreadInformation;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
      (const char *)(unsigned int)v5,
      ReturnLengtha);
    return v6;
  }
}

```

## disassembly

```asm
0x180106518  mov     [rsp+arg_8], rbx
0x18010651d  push    rdi
0x18010651e  sub     rsp, 30h
0x180106522  mov     rcx, [rcx]
0x180106525  mov     rdi, rdx
0x180106528  mov     [rsp+38h+ThreadInformation], 0
0x180106530  lea     rax, [rcx-1]
0x180106534  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106538  jbe     short loc_180106543
0x18010653a  call    cs:__imp_GetCurrentThread
0x180106540  mov     rcx, rax; ThreadHandle
0x180106543  mov     r9d, 4; ThreadInformationLength
0x180106549  mov     qword ptr [rsp+38h+ReturnLength], 0; int
0x180106552  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180106557  lea     edx, [r9+12h]; ThreadInformationClass
0x18010655b  call    cs:__imp_NtQueryInformationThread
0x180106561  test    eax, eax
0x180106563  jns     short loc_1801065A1
0x180106565  mov     rcx, [rsp+38h]; this
0x18010656a  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x180106571  mov     r9d, eax; char *
0x180106574  mov     edx, 7Eh ; '~'; void *
0x180106579  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18010657e  mov     ebx, eax
0x180106580  test    eax, eax
0x180106582  jns     short loc_1801065A1
0x180106584  mov     rcx, [rsp+38h]; this
0x180106589  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x180106590  mov     r9d, eax; char *
0x180106593  mov     edx, 30h ; '0'; void *
0x180106598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010659d  mov     eax, ebx
0x18010659f  jmp     short loc_1801065A9
0x1801065a1  mov     eax, [rsp+38h+ThreadInformation]
0x1801065a5  mov     [rdi], eax
0x1801065a7  xor     eax, eax
0x1801065a9  mov     rbx, [rsp+38h+arg_8]
0x1801065ae  add     rsp, 30h
0x1801065b2  pop     rdi
0x1801065b3  retn
```
