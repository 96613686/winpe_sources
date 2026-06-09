# StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::Get(ulong &)

- ea: `0x1801065bc`
- end: `0x180106658`
- name: `?Get@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJAEAK@Z`
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
- `0x1801065bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801065de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801065de`
- `ntdll!NtQueryInformationThread` at `0x1801065ff`
- `ntdll!NtQueryInformationThread` at `0x1801065ff`

## string_xrefs

- `0x18010660e`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x18010662d`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::Get(
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
  v4 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
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
0x1801065bc  mov     [rsp+arg_8], rbx
0x1801065c1  push    rdi
0x1801065c2  sub     rsp, 30h
0x1801065c6  mov     rcx, [rcx]
0x1801065c9  mov     rdi, rdx
0x1801065cc  mov     [rsp+38h+ThreadInformation], 0
0x1801065d4  lea     rax, [rcx-1]
0x1801065d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801065dc  jbe     short loc_1801065E7
0x1801065de  call    cs:__imp_GetCurrentThread
0x1801065e4  mov     rcx, rax; ThreadHandle
0x1801065e7  mov     r9d, 4; ThreadInformationLength
0x1801065ed  mov     qword ptr [rsp+38h+ReturnLength], 0; int
0x1801065f6  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1801065fb  lea     edx, [r9+14h]; ThreadInformationClass
0x1801065ff  call    cs:__imp_NtQueryInformationThread
0x180106605  test    eax, eax
0x180106607  jns     short loc_180106645
0x180106609  mov     rcx, [rsp+38h]; this
0x18010660e  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x180106615  mov     r9d, eax; char *
0x180106618  mov     edx, 7Eh ; '~'; void *
0x18010661d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180106622  mov     ebx, eax
0x180106624  test    eax, eax
0x180106626  jns     short loc_180106645
0x180106628  mov     rcx, [rsp+38h]; this
0x18010662d  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x180106634  mov     r9d, eax; char *
0x180106637  mov     edx, 30h ; '0'; void *
0x18010663c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106641  mov     eax, ebx
0x180106643  jmp     short loc_18010664D
0x180106645  mov     eax, [rsp+38h+ThreadInformation]
0x180106649  mov     [rdi], eax
0x18010664b  xor     eax, eax
0x18010664d  mov     rbx, [rsp+38h+arg_8]
0x180106652  add     rsp, 30h
0x180106656  pop     rdi
0x180106657  retn
```
