# StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Get(long &)

- ea: `0x180106660`
- end: `0x1801066fc`
- name: `?Get@?$AutoThreadPriority@$0BJ@JJ@ResourcePriority@StateRepository@@QEAAJAEAJ@Z`
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
- `0x180106660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106682`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106682`
- `ntdll!NtQueryInformationThread` at `0x1801066a3`
- `ntdll!NtQueryInformationThread` at `0x1801066a3`

## string_xrefs

- `0x1801066b2`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x1801066d1`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Get(HANDLE *a1, _DWORD *a2)
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
  v4 = NtQueryInformationThread(CurrentThread, ThreadActualBasePriority, &ThreadInformation, 4u, 0);
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
0x180106660  mov     [rsp+arg_8], rbx
0x180106665  push    rdi
0x180106666  sub     rsp, 30h
0x18010666a  mov     rcx, [rcx]
0x18010666d  mov     rdi, rdx
0x180106670  mov     [rsp+38h+ThreadInformation], 0
0x180106678  lea     rax, [rcx-1]
0x18010667c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180106680  jbe     short loc_18010668B
0x180106682  call    cs:__imp_GetCurrentThread
0x180106688  mov     rcx, rax; ThreadHandle
0x18010668b  mov     r9d, 4; ThreadInformationLength
0x180106691  mov     qword ptr [rsp+38h+ReturnLength], 0; int
0x18010669a  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x18010669f  lea     edx, [r9+15h]; ThreadInformationClass
0x1801066a3  call    cs:__imp_NtQueryInformationThread
0x1801066a9  test    eax, eax
0x1801066ab  jns     short loc_1801066E9
0x1801066ad  mov     rcx, [rsp+38h]; this
0x1801066b2  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1801066b9  mov     r9d, eax; char *
0x1801066bc  mov     edx, 7Eh ; '~'; void *
0x1801066c1  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801066c6  mov     ebx, eax
0x1801066c8  test    eax, eax
0x1801066ca  jns     short loc_1801066E9
0x1801066cc  mov     rcx, [rsp+38h]; this
0x1801066d1  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1801066d8  mov     r9d, eax; char *
0x1801066db  mov     edx, 30h ; '0'; void *
0x1801066e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801066e5  mov     eax, ebx
0x1801066e7  jmp     short loc_1801066F1
0x1801066e9  mov     eax, [rsp+38h+ThreadInformation]
0x1801066ed  mov     [rdi], eax
0x1801066ef  xor     eax, eax
0x1801066f1  mov     rbx, [rsp+38h+arg_8]
0x1801066f6  add     rsp, 30h
0x1801066fa  pop     rdi
0x1801066fb  retn
```
