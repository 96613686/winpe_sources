# File::Verify(ConfigSettings const &)

- ea: `0x1800c9400`
- end: `0x1800c962b`
- name: `?Verify@File@@QEAA?AW4FileVerifyStatus@@AEBVConfigSettings@@@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18001f378`

## callees

- `0x18001036c`
- `0x1800295dc`
- `0x1800c5fb0`
- `0x1800c623c`
- `0x1800c7f00`
- `0x1800c90d4`
- `0x1800c9400`
- `0x1800c98e4`
- `0x1800c99cc`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c94c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c94c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c94a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c94a0`

## string_xrefs

- `0x1800c95e7`: `FilePathHash invalid(%ls)`
- `0x1800c94ee`: `CreateFileW(%ls) failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall File::Verify(File *a1, const struct ConfigSettings *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rax
  HANDLE FileW; // rax
  DWORD LastError; // edi
  __int64 v9; // rax
  unsigned int v10; // edi
  __int64 Usn; // rax
  __int64 v12; // rcx
  char v13; // si
  __int64 v14; // rax
  __int64 v15; // rax
  HANDLE hDevice; // [rsp+70h] [rbp+8h] BYREF

  hDevice = (HANDLE)-1LL;
  v4 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 8LL))(a1);
  v5 = std::wstring::find(v4, 124);
  if ( v5 == -1
    || (unsigned __int64)(*(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 8LL))(a1) + 16) - v5) < 0xE )
  {
    v15 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 8LL))(a1);
    if ( *(_QWORD *)(v15 + 24) > 7u )
      v15 = *(_QWORD *)v15;
    AslLogCallPrintf(3, "File::Verify", 2283, "FilePathHash invalid(%ls)", (const wchar_t *)v15);
    goto LABEL_23;
  }
  v6 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 24LL))(a1);
  if ( *(_QWORD *)(v6 + 24) > 7u )
    v6 = *(_QWORD *)v6;
  FileW = CreateFileW((LPCWSTR)v6, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hDevice,
    FileW);
  if ( (((unsigned __int64)hDevice + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v9 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 24LL))(a1);
    if ( *(_QWORD *)(v9 + 24) > 7u )
      v9 = *(_QWORD *)v9;
    AslLogCallPrintf(3, "File::Verify", 2294, "CreateFileW(%ls) failed [%d]", (const wchar_t *)v9, LastError);
LABEL_23:
    File::RemoveFileFromCache(a1, a2);
    v10 = 2;
    goto LABEL_24;
  }
  v10 = 0;
  Usn = File::QueryUsn(hDevice, 0);
  v12 = *((_QWORD *)a1 + 99);
  if ( Usn == v12 )
  {
    v13 = 0;
  }
  else
  {
    v13 = 1;
    if ( v12 )
    {
      v14 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 24LL))(a1);
      if ( *(_QWORD *)(v14 + 24) > 7u )
        v14 = *(_QWORD *)v14;
      AslLogCallPrintf(3, "File::Verify", 2315, "File changed, updating %ls", (const wchar_t *)v14);
      File::SetFileAttributesW(a1, 0x4002150Du, 0);
      v10 = 1;
    }
    else
    {
      *((_QWORD *)a1 + 99) = Usn;
    }
  }
  if ( !*(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 16LL))(a1) + 16) )
  {
    File::SetFileAttributesW(a1, 0x4002150Du, 0);
    v10 = 3;
LABEL_19:
    File::SaveFileToCache(a1, a2);
    goto LABEL_24;
  }
  if ( v13 )
    goto LABEL_19;
LABEL_24:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
  return v10;
}

```

## disassembly

```asm
0x1800c9400  push    rbx
0x1800c9402  push    rsi
0x1800c9403  push    rdi
0x1800c9404  push    r14
0x1800c9406  sub     rsp, 48h
0x1800c940a  mov     r14, rdx
0x1800c940d  mov     rbx, rcx
0x1800c9410  mov     [rsp+68h+hDevice], 0FFFFFFFFFFFFFFFFh
0x1800c9419  mov     rax, [rcx]
0x1800c941c  mov     rax, [rax+8]
0x1800c9420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9425  mov     edx, 7Ch ; '|'
0x1800c942a  mov     rcx, rax
0x1800c942d  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x1800c9432  mov     rdi, rax
0x1800c9435  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c9439  jz      loc_1800C95C9
0x1800c943f  mov     rcx, [rbx]
0x1800c9442  mov     rax, [rcx+8]
0x1800c9446  mov     rcx, rbx
0x1800c9449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c944e  mov     rcx, [rax+10h]
0x1800c9452  sub     rcx, rdi
0x1800c9455  cmp     rcx, 0Eh
0x1800c9459  jb      loc_1800C95C9
0x1800c945f  mov     rax, [rbx]
0x1800c9462  mov     rcx, rbx
0x1800c9465  mov     rax, [rax+18h]
0x1800c9469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c946e  cmp     qword ptr [rax+18h], 7
0x1800c9473  jbe     short loc_1800C9478
0x1800c9475  mov     rax, [rax]
0x1800c9478  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800c9481  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c9489  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c9491  xor     r9d, r9d; lpSecurityAttributes
0x1800c9494  mov     edx, 80000000h; dwDesiredAccess
0x1800c9499  lea     r8d, [r9+7]; dwShareMode
0x1800c949d  mov     rcx, rax; lpFileName
0x1800c94a0  call    cs:__imp_CreateFileW
0x1800c94a6  mov     rdx, rax
0x1800c94a9  lea     rcx, [rsp+68h+hDevice]
0x1800c94ae  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c94b3  mov     rcx, [rsp+68h+hDevice]; hDevice
0x1800c94b8  lea     rax, [rcx+1]
0x1800c94bc  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800c94c2  jnz     short loc_1800C9511
0x1800c94c4  call    cs:__imp_GetLastError
0x1800c94ca  mov     edi, eax
0x1800c94cc  mov     rcx, [rbx]
0x1800c94cf  mov     rax, [rcx+18h]
0x1800c94d3  mov     rcx, rbx
0x1800c94d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c94db  cmp     qword ptr [rax+18h], 7
0x1800c94e0  jbe     short loc_1800C94E5
0x1800c94e2  mov     rax, [rax]
0x1800c94e5  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x1800c94e9  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800c94ee  lea     r9, aCreatefilewLsF; "CreateFileW(%ls) failed [%d]"
0x1800c94f5  mov     r8d, 8F6h
0x1800c94fb  lea     rdx, aFileVerify; "File::Verify"
0x1800c9502  mov     ecx, 3
0x1800c9507  call    AslLogCallPrintf
0x1800c950c  jmp     loc_1800C9605
0x1800c9511  xor     edi, edi
0x1800c9513  xor     edx, edx; lpFileName
0x1800c9515  call    ?QueryUsn@File@@SA_JPEAXPEBG@Z; File::QueryUsn(void *,ushort const *)
0x1800c951a  mov     rcx, [rbx+318h]
0x1800c9521  cmp     rax, rcx
0x1800c9524  jz      short loc_1800C9587
0x1800c9526  lea     esi, [rdi+1]
0x1800c9529  test    rcx, rcx
0x1800c952c  jnz     short loc_1800C9537
0x1800c952e  mov     [rbx+318h], rax
0x1800c9535  jmp     short loc_1800C958A
0x1800c9537  mov     rax, [rbx]
0x1800c953a  mov     rcx, rbx
0x1800c953d  mov     rax, [rax+18h]
0x1800c9541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9546  cmp     qword ptr [rax+18h], 7
0x1800c954b  jbe     short loc_1800C9550
0x1800c954d  mov     rax, [rax]
0x1800c9550  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800c9555  lea     r9, aFileChangedUpd; "File changed, updating %ls"
0x1800c955c  mov     r8d, 90Bh
0x1800c9562  lea     rdx, aFileVerify; "File::Verify"
0x1800c9569  mov     ecx, 3
0x1800c956e  call    AslLogCallPrintf
0x1800c9573  xor     r8d, r8d; bool
0x1800c9576  mov     edx, 4002150Dh; unsigned __int64
0x1800c957b  mov     rcx, rbx; this
0x1800c957e  call    ?SetFileAttributesW@File@@QEAAX_K_N@Z; File::SetFileAttributesW(unsigned __int64,bool)
0x1800c9583  mov     edi, esi
0x1800c9585  jmp     short loc_1800C958A
0x1800c9587  xor     sil, sil
0x1800c958a  mov     rax, [rbx]
0x1800c958d  mov     rcx, rbx
0x1800c9590  mov     rax, [rax+10h]
0x1800c9594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9599  cmp     qword ptr [rax+10h], 0
0x1800c959e  jnz     short loc_1800C95B7
0x1800c95a0  xor     r8d, r8d; bool
0x1800c95a3  mov     edx, 4002150Dh; unsigned __int64
0x1800c95a8  mov     rcx, rbx; this
0x1800c95ab  call    ?SetFileAttributesW@File@@QEAAX_K_N@Z; File::SetFileAttributesW(unsigned __int64,bool)
0x1800c95b0  mov     edi, 3
0x1800c95b5  jmp     short loc_1800C95BC
0x1800c95b7  test    sil, sil
0x1800c95ba  jz      short loc_1800C9615
0x1800c95bc  mov     rdx, r14; struct ConfigSettings *
0x1800c95bf  mov     rcx, rbx; this
0x1800c95c2  call    ?SaveFileToCache@File@@QEAAXAEBVConfigSettings@@@Z; File::SaveFileToCache(ConfigSettings const &)
0x1800c95c7  jmp     short loc_1800C9615
0x1800c95c9  mov     rax, [rbx]
0x1800c95cc  mov     rcx, rbx
0x1800c95cf  mov     rax, [rax+8]
0x1800c95d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c95d8  cmp     qword ptr [rax+18h], 7
0x1800c95dd  jbe     short loc_1800C95E2
0x1800c95df  mov     rax, [rax]
0x1800c95e2  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800c95e7  lea     r9, aFilepathhashIn; "FilePathHash invalid(%ls)"
0x1800c95ee  mov     r8d, 8EBh
0x1800c95f4  lea     rdx, aFileVerify; "File::Verify"
0x1800c95fb  mov     ecx, 3
0x1800c9600  call    AslLogCallPrintf
0x1800c9605  mov     rdx, r14; struct ConfigSettings *
0x1800c9608  mov     rcx, rbx; this
0x1800c960b  call    ?RemoveFileFromCache@File@@QEAAXAEBVConfigSettings@@@Z; File::RemoveFileFromCache(ConfigSettings const &)
0x1800c9610  mov     edi, 2
0x1800c9615  lea     rcx, [rsp+68h+hDevice]
0x1800c961a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c961f  mov     eax, edi
0x1800c9621  add     rsp, 48h
0x1800c9625  pop     r14
0x1800c9627  pop     rdi
0x1800c9628  pop     rsi
0x1800c9629  pop     rbx
0x1800c962a  retn
```
