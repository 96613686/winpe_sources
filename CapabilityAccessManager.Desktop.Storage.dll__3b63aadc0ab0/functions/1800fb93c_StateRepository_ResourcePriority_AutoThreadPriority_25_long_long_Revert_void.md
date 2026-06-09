# StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert(void)

- ea: `0x1800fb93c`
- end: `0x1800fb9c9`
- name: `?Revert@?$AutoThreadPriority@$0BJ@JJ@ResourcePriority@StateRepository@@QEAAJXZ`
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
- `0x1800fb93c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb95c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb95c`
- `ntdll!NtSetInformationThread` at `0x1800fb972`
- `ntdll!NtSetInformationThread` at `0x1800fb972`

## string_xrefs

- `0x1800fb981`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x1800fb9a0`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert(char **a1)
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
    v3 = NtSetInformationThread(CurrentThread, ThreadActualBasePriority, (char *)a1 + 12, 4u);
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
0x1800fb93c  mov     [rsp+arg_0], rbx
0x1800fb941  push    rdi; int
0x1800fb942  sub     rsp, 20h
0x1800fb946  cmp     byte ptr [rcx+8], 0
0x1800fb94a  mov     rbx, rcx
0x1800fb94d  jz      short loc_1800FB9BC
0x1800fb94f  mov     rcx, [rcx]
0x1800fb952  lea     rax, [rcx-1]
0x1800fb956  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800fb95a  jbe     short loc_1800FB965
0x1800fb95c  call    cs:__imp_GetCurrentThread
0x1800fb962  mov     rcx, rax; ThreadHandle
0x1800fb965  mov     edx, 19h; ThreadInformationClass
0x1800fb96a  lea     r8, [rbx+0Ch]; ThreadInformation
0x1800fb96e  lea     r9d, [rdx-15h]; ThreadInformationLength
0x1800fb972  call    cs:__imp_NtSetInformationThread
0x1800fb978  test    eax, eax
0x1800fb97a  jns     short loc_1800FB9B8
0x1800fb97c  mov     rcx, [rsp+28h]; this
0x1800fb981  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800fb988  mov     r9d, eax; char *
0x1800fb98b  mov     edx, 8Dh; void *
0x1800fb990  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fb995  mov     edi, eax
0x1800fb997  test    eax, eax
0x1800fb999  jns     short loc_1800FB9B8
0x1800fb99b  mov     rcx, [rsp+28h]; this
0x1800fb9a0  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800fb9a7  mov     r9d, eax; char *
0x1800fb9aa  mov     edx, 68h ; 'h'; void *
0x1800fb9af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb9b4  mov     eax, edi
0x1800fb9b6  jmp     short loc_1800FB9BE
0x1800fb9b8  mov     byte ptr [rbx+8], 0
0x1800fb9bc  xor     eax, eax
0x1800fb9be  mov     rbx, [rsp+28h+arg_0]
0x1800fb9c3  add     rsp, 20h
0x1800fb9c7  pop     rdi
0x1800fb9c8  retn
```
