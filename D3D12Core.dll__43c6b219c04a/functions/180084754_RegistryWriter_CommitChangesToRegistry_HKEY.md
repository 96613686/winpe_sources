# RegistryWriter::CommitChangesToRegistry(HKEY__ *)

- ea: `0x180084754`
- end: `0x1800847c8`
- name: `?CommitChangesToRegistry@RegistryWriter@@QEAAJPEAUHKEY__@@@Z`
- size: `116`
- prototype: `int(RegistryWriter *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b6d10`
- `0x18012bd30`

## callees

- `0x180084754`
- `0x180085d84`
- `0x18012cc4c`
- `0x18012cca8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180084764`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180084764`
- `ntdll!NtCommitTransaction` at `0x180084797`
- `ntdll!NtCommitTransaction` at `0x180084797`

## pseudocode

```c
__int64 __fastcall RegistryWriter::CommitChangesToRegistry(RegistryWriter *this, HKEY a2)
{
  LSTATUS v3; // eax
  __int64 v4; // rdx
  int v5; // ebx
  int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = RegFlushKey(a2);
  v5 = v3;
  if ( v3 )
  {
    RegistryError(v3);
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    return (unsigned int)v5;
  }
  else
  {
    if ( (unsigned __int64)(*(_QWORD *)this - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LOBYTE(v4) = 1;
      v7 = NtCommitTransaction(*(_QWORD *)this, v4);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(retaddr, v8, v9, (const char *)(unsigned int)v7, v10);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&long NtClose(void *)>>::reset(
        this,
        -1);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180084754  mov     [rsp+arg_0], rbx
0x180084759  push    rdi; int
0x18008475a  sub     rsp, 20h
0x18008475e  mov     rdi, rcx
0x180084761  mov     rcx, rdx; hKey
0x180084764  call    cs:__imp_RegFlushKey
0x18008476a  mov     ebx, eax
0x18008476c  test    eax, eax
0x18008476e  jz      short loc_180084788
0x180084770  mov     ecx, eax; int
0x180084772  call    ?RegistryError@@YAXJ@Z; RegistryError(long)
0x180084777  test    ebx, ebx
0x180084779  jle     short loc_180084784
0x18008477b  movzx   ebx, bx
0x18008477e  or      ebx, 80070000h
0x180084784  mov     eax, ebx
0x180084786  jmp     short loc_1800847BD
0x180084788  mov     rcx, [rdi]
0x18008478b  lea     rax, [rcx-1]
0x18008478f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180084793  ja      short loc_1800847BB
0x180084795  mov     dl, 1
0x180084797  call    cs:__imp_NtCommitTransaction
0x18008479d  test    eax, eax
0x18008479f  jns     short loc_1800847AF
0x1800847a1  mov     rcx, [rsp+28h]; this
0x1800847a6  mov     r9d, eax; char *
0x1800847a9  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800847af  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800847b3  mov     rcx, rdi
0x1800847b6  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AJPEAX@Z$1?NtClose@@YAJ0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&NtClose(void *)>>::reset(void *)
0x1800847bb  xor     eax, eax
0x1800847bd  mov     rbx, [rsp+28h+arg_0]
0x1800847c2  add     rsp, 20h
0x1800847c6  pop     rdi
0x1800847c7  retn
```
