# StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::Revert(void)

- ea: `0x1800fb8a8`
- end: `0x1800fb935`
- name: `?Revert@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ`
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
- `0x1800fb8a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb8c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb8c8`
- `ntdll!NtSetInformationThread` at `0x1800fb8de`
- `ntdll!NtSetInformationThread` at `0x1800fb8de`

## string_xrefs

- `0x1800fb8ed`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x1800fb90c`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::Revert(
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
    v3 = NtSetInformationThread(CurrentThread, ThreadPagePriority, (char *)a1 + 12, 4u);
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
0x1800fb8a8  mov     [rsp+arg_0], rbx
0x1800fb8ad  push    rdi; int
0x1800fb8ae  sub     rsp, 20h
0x1800fb8b2  cmp     byte ptr [rcx+8], 0
0x1800fb8b6  mov     rbx, rcx
0x1800fb8b9  jz      short loc_1800FB928
0x1800fb8bb  mov     rcx, [rcx]
0x1800fb8be  lea     rax, [rcx-1]
0x1800fb8c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800fb8c6  jbe     short loc_1800FB8D1
0x1800fb8c8  call    cs:__imp_GetCurrentThread
0x1800fb8ce  mov     rcx, rax; ThreadHandle
0x1800fb8d1  mov     edx, 18h; ThreadInformationClass
0x1800fb8d6  lea     r8, [rbx+0Ch]; ThreadInformation
0x1800fb8da  lea     r9d, [rdx-14h]; ThreadInformationLength
0x1800fb8de  call    cs:__imp_NtSetInformationThread
0x1800fb8e4  test    eax, eax
0x1800fb8e6  jns     short loc_1800FB924
0x1800fb8e8  mov     rcx, [rsp+28h]; this
0x1800fb8ed  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800fb8f4  mov     r9d, eax; char *
0x1800fb8f7  mov     edx, 8Dh; void *
0x1800fb8fc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fb901  mov     edi, eax
0x1800fb903  test    eax, eax
0x1800fb905  jns     short loc_1800FB924
0x1800fb907  mov     rcx, [rsp+28h]; this
0x1800fb90c  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800fb913  mov     r9d, eax; char *
0x1800fb916  mov     edx, 68h ; 'h'; void *
0x1800fb91b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb920  mov     eax, edi
0x1800fb922  jmp     short loc_1800FB92A
0x1800fb924  mov     byte ptr [rbx+8], 0
0x1800fb928  xor     eax, eax
0x1800fb92a  mov     rbx, [rsp+28h+arg_0]
0x1800fb92f  add     rsp, 20h
0x1800fb933  pop     rdi
0x1800fb934  retn
```
