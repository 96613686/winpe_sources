# NgcUtils::DoesFileExist(ushort const *,bool *)

- ea: `0x18005971c`
- end: `0x1800597af`
- name: `?DoesFileExist@NgcUtils@@YAJPEBGPEA_N@Z`
- size: `147`
- prototype: `__int64 __fastcall(const WCHAR *this, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023e64`

## callees

- `0x180019040`
- `0x180022e68`
- `0x18005971c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059769`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005974d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005974d`

## string_xrefs

- `0x180059782`: `onecore\ds\security\ngc\utils\common\lib\fileutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::DoesFileExist(const WCHAR *this, unsigned __int16 *a2, bool *a3)
{
  const char *v4; // r9
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE FileW; // [rsp+58h] [rbp+10h] BYREF

  *(_BYTE *)a2 = 0;
  FileW = CreateFileW(this, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    *(_BYTE *)a2 = 1;
    goto LABEL_5;
  }
  if ( GetLastError() - 2 <= 1 )
  {
LABEL_5:
    LastError = 0;
    goto LABEL_6;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x43,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\fileutils.cpp",
                v4);
LABEL_6:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
  return LastError;
}

```

## disassembly

```asm
0x18005971c  push    rbx
0x18005971e  sub     rsp, 40h
0x180059722  xor     r9d, r9d; lpSecurityAttributes
0x180059725  mov     byte ptr [rdx], 0
0x180059728  mov     rbx, rdx
0x18005972b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180059734  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005973c  mov     edx, 80000000h; dwDesiredAccess
0x180059741  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180059749  lea     r8d, [r9+1]; dwShareMode
0x18005974d  call    cs:__imp_CreateFileW
0x180059754  nop     dword ptr [rax+rax+00h]
0x180059759  mov     [rsp+48h+arg_8], rax
0x18005975e  inc     rax
0x180059761  test    rax, 0FFFFFFFFFFFFFFFEh
0x180059767  jnz     short loc_180059797
0x180059769  call    cs:__imp_GetLastError
0x180059770  nop     dword ptr [rax+rax+00h]
0x180059775  add     eax, 0FFFFFFFEh
0x180059778  cmp     eax, 1
0x18005977b  jbe     short loc_18005979A
0x18005977d  mov     rcx, [rsp+48h]; this
0x180059782  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180059789  mov     edx, 43h ; 'C'; void *
0x18005978e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180059793  mov     ebx, eax
0x180059795  jmp     short loc_18005979C
0x180059797  mov     byte ptr [rbx], 1
0x18005979a  xor     ebx, ebx
0x18005979c  lea     rcx, [rsp+48h+arg_8]
0x1800597a1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800597a6  mov     eax, ebx
0x1800597a8  add     rsp, 40h
0x1800597ac  pop     rbx
0x1800597ad  retn
```
