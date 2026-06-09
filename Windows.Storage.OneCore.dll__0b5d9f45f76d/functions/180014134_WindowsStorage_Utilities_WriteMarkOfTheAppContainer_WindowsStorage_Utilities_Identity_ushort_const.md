# WindowsStorage::Utilities::WriteMarkOfTheAppContainer(WindowsStorage::Utilities::Identity &,ushort const *)

- ea: `0x180014134`
- end: `0x1800141ae`
- name: `?WriteMarkOfTheAppContainer@Utilities@WindowsStorage@@YAXAEAVIdentity@12@PEBG@Z`
- size: `122`
- prototype: `void __fastcall(WindowsStorage::Utilities *this, WCHAR *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800176f0`
- `0x180018440`
- `0x180018990`
- `0x180018bb0`

## callees

- `0x18000d4e0`
- `0x1800123a0`
- `0x180014134`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001416b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001416b`

## pseudocode

```c
void __fastcall WindowsStorage::Utilities::WriteMarkOfTheAppContainer(
        WindowsStorage::Utilities *this,
        WCHAR *a2,
        const unsigned __int16 *a3)
{
  HANDLE FileW; // rax
  HANDLE v5; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(a2, 0x180u, 7u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    WindowsStorage::Utilities::ModifyZoneIdentifierOnPath__lambda_95b1af8c5fd714bdb7e16334665ccd4e___(
      FileW,
      (struct _GUID *)a2);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v5);
}

```

## disassembly

```asm
0x180014134  mov     rax, rsp
0x180014137  mov     [rax+8], rbx
0x18001413b  push    rdi
0x18001413c  sub     rsp, 40h
0x180014140  mov     rbx, rdx
0x180014143  mov     rdi, rcx
0x180014146  mov     qword ptr [rax-18h], 0
0x18001414e  mov     dword ptr [rax-20h], 0
0x180014155  mov     dword ptr [rax-28h], 3
0x18001415c  xor     r9d, r9d; lpSecurityAttributes
0x18001415f  mov     edx, 180h; dwDesiredAccess
0x180014164  lea     r8d, [r9+7]; dwShareMode
0x180014168  mov     rcx, rbx; lpFileName
0x18001416b  call    cs:__imp_CreateFileW
0x180014171  mov     [rsp+48h+arg_18], rax
0x180014176  lea     rcx, [rax+1]
0x18001417a  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180014181  jz      short loc_180014199
0x180014183  mov     [rsp+48h+arg_10], rdi
0x180014188  lea     r9, [rsp+48h+arg_10]
0x18001418d  mov     rdx, rbx; struct _GUID *
0x180014190  mov     rcx, rax; hFile
0x180014193  call    WindowsStorage__Utilities__ModifyZoneIdentifierOnPath__lambda_95b1af8c5fd714bdb7e16334665ccd4e___
0x180014198  nop
0x180014199  lea     rcx, [rsp+48h+arg_18]
0x18001419e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800141a3  mov     rbx, [rsp+48h+arg_0]
0x1800141a8  add     rsp, 40h
0x1800141ac  pop     rdi
0x1800141ad  retn
```
