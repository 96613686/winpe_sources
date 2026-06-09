# StateRepository::ResourcePriority::AutoThreadPriority<22,_IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert(void)

- ea: `0x1800fb814`
- end: `0x1800fb8a1`
- name: `?Revert@?$AutoThreadPriority@$0BG@W4_IO_PRIORITY_HINT@@U_FILE_IO_PRIORITY_HINT_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800f85a8`

## callees

- `0x1800eabf4`
- `0x1800fb7f0`
- `0x1800fb814`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb834`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb834`
- `ntdll!NtSetInformationThread` at `0x1800fb84a`
- `ntdll!NtSetInformationThread` at `0x1800fb84a`

## string_xrefs

- `0x1800fb859`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x1800fb878`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<22,enum _IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert(
        char **a1)
{
  char *CurrentThread; // rcx
  NTSTATUS v3; // eax
  int v4; // eax
  unsigned int v5; // edi
  int v7; // [rsp+20h] [rbp-8h]
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)a1 + 8) )
  {
    CurrentThread = *a1;
    if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      CurrentThread = (char *)GetCurrentThread();
    v3 = NtSetInformationThread(CurrentThread, ThreadIoPriority, (char *)a1 + 12, 4u);
    if ( v3 < 0 )
    {
      v4 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x8D,
             (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
             (const char *)(unsigned int)v3,
             v7);
      v5 = v4;
      if ( v4 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x68,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
          (const char *)(unsigned int)v4,
          v8);
        return v5;
      }
    }
    *((_BYTE *)a1 + 8) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800fb814  mov     [rsp+arg_0], rbx
0x1800fb819  push    rdi; int
0x1800fb81a  sub     rsp, 20h
0x1800fb81e  cmp     byte ptr [rcx+8], 0
0x1800fb822  mov     rbx, rcx
0x1800fb825  jz      short loc_1800FB894
0x1800fb827  mov     rcx, [rcx]
0x1800fb82a  lea     rax, [rcx-1]
0x1800fb82e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800fb832  jbe     short loc_1800FB83D
0x1800fb834  call    cs:__imp_GetCurrentThread
0x1800fb83a  mov     rcx, rax; ThreadHandle
0x1800fb83d  mov     edx, 16h; ThreadInformationClass
0x1800fb842  lea     r8, [rbx+0Ch]; ThreadInformation
0x1800fb846  lea     r9d, [rdx-12h]; ThreadInformationLength
0x1800fb84a  call    cs:__imp_NtSetInformationThread
0x1800fb850  test    eax, eax
0x1800fb852  jns     short loc_1800FB890
0x1800fb854  mov     rcx, [rsp+28h]; this
0x1800fb859  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800fb860  mov     r9d, eax; char *
0x1800fb863  mov     edx, 8Dh; void *
0x1800fb868  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fb86d  mov     edi, eax
0x1800fb86f  test    eax, eax
0x1800fb871  jns     short loc_1800FB890
0x1800fb873  mov     rcx, [rsp+28h]; this
0x1800fb878  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800fb87f  mov     r9d, eax; char *
0x1800fb882  mov     edx, 68h ; 'h'; void *
0x1800fb887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb88c  mov     eax, edi
0x1800fb88e  jmp     short loc_1800FB896
0x1800fb890  mov     byte ptr [rbx+8], 0
0x1800fb894  xor     eax, eax
0x1800fb896  mov     rbx, [rsp+28h+arg_0]
0x1800fb89b  add     rsp, 20h
0x1800fb89f  pop     rdi
0x1800fb8a0  retn
```
