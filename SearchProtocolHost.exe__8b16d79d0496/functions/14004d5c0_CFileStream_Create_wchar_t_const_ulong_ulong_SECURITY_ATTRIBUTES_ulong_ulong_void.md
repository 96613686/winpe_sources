# CFileStream::Create(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x14004d5c0`
- end: `0x14004d673`
- name: `?Create@CFileStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(CFileStream *this, const wchar_t *, DWORD, DWORD, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400104c8`
- `0x14002801c`
- `0x140037ca8`
- `0x14004d5c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004d61c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004d61c`

## string_xrefs

- `0x14004d642`: `onecoreuap\base\appmodel\search\common\pkmutill\filestream.cxx`

## pseudocode

```c
__int64 __fastcall CFileStream::Create(
        CFileStream *this,
        const wchar_t *a2,
        DWORD a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  HANDLE FileW; // rax
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_DWORD *)this + 48) = a3;
  if ( !a2 )
    return 2147500035LL;
  FileW = CreateFileW(a2, a3, a4, lpSecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, hTemplateFile);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 24,
    FileW);
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x47,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\filestream.cxx",
             v12);
  CLMString::operator=((char *)this + 32, a2);
  return 0;
}

```

## disassembly

```asm
0x14004d5c0  mov     [rsp+arg_0], rbx
0x14004d5c5  mov     [rsp+arg_8], rsi
0x14004d5ca  push    rdi
0x14004d5cb  sub     rsp, 40h
0x14004d5cf  mov     [rcx+0C0h], r8d
0x14004d5d6  mov     r11d, r9d
0x14004d5d9  mov     r10d, r8d
0x14004d5dc  mov     rdi, rdx
0x14004d5df  mov     rsi, rcx
0x14004d5e2  test    rdx, rdx
0x14004d5e5  jnz     short loc_14004D5EE
0x14004d5e7  mov     eax, 80004003h
0x14004d5ec  jmp     short loc_14004D663
0x14004d5ee  mov     rax, [rsp+48h+arg_38]
0x14004d5f6  mov     r8d, r11d; dwShareMode
0x14004d5f9  mov     r9, [rsp+48h+lpSecurityAttributes]; lpSecurityAttributes
0x14004d5fe  mov     edx, r10d; dwDesiredAccess
0x14004d601  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x14004d606  mov     rcx, rdi; lpFileName
0x14004d609  mov     eax, [rsp+48h+arg_30]
0x14004d610  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14004d614  mov     eax, [rsp+48h+arg_28]
0x14004d618  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x14004d61c  call    cs:__imp_CreateFileW
0x14004d622  mov     rdx, rax
0x14004d625  lea     rcx, [rsi+18h]
0x14004d629  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004d62e  mov     rax, [rsi+18h]
0x14004d632  inc     rax
0x14004d635  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004d63b  jnz     short loc_14004D655
0x14004d63d  mov     rcx, [rsp+48h]; this
0x14004d642  lea     r8, aOnecoreuapBase_60; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004d649  mov     edx, 47h ; 'G'; void *
0x14004d64e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14004d653  jmp     short loc_14004D663
0x14004d655  lea     rcx, [rsi+20h]
0x14004d659  mov     rdx, rdi
0x14004d65c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004d661  xor     eax, eax
0x14004d663  mov     rbx, [rsp+48h+arg_0]
0x14004d668  mov     rsi, [rsp+48h+arg_8]
0x14004d66d  add     rsp, 40h
0x14004d671  pop     rdi
0x14004d672  retn
```
