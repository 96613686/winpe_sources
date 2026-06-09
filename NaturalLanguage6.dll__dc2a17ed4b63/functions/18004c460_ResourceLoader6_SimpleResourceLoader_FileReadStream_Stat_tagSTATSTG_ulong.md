# ResourceLoader6::SimpleResourceLoader::FileReadStream::Stat(tagSTATSTG *,ulong)

- ea: `0x18004c460`
- end: `0x18004c56b`
- name: `?Stat@FileReadStream@SimpleResourceLoader@ResourceLoader6@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `267`
- prototype: `int(ResourceLoader6::SimpleResourceLoader::FileReadStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800162e4`
- `0x18004c460`
- `0x18009e2c2`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c4af`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004c509`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004c509`

## pseudocode

```c
int __fastcall ResourceLoader6::SimpleResourceLoader::FileReadStream::Stat(
        ResourceLoader6::SimpleResourceLoader::FileReadStream *this,
        struct tagSTATSTG *a2,
        int a3)
{
  int result; // eax
  OLECHAR *v7; // rax
  const unsigned __int16 *v8; // r8
  void *v9; // rcx
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-48h] BYREF

  if ( !a2 )
    return -2147287031;
  memset_0(a2, 0, sizeof(struct tagSTATSTG));
  if ( a3 )
    goto LABEL_9;
  v7 = (OLECHAR *)CoTaskMemAlloc(*((_QWORD *)this + 4) + 1LL);
  a2->pwcsName = v7;
  if ( !v7 )
    return -2147024882;
  v8 = (const unsigned __int16 *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) >= 8u )
    v8 = *(const unsigned __int16 **)v8;
  result = StringCchCopyW(v7, *((_QWORD *)this + 4) + 1LL, v8);
  if ( result >= 0 )
  {
LABEL_9:
    v9 = (void *)*((_QWORD *)this + 6);
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(v9, &FileInformation) )
    {
      a2->ctime = FileInformation.ftCreationTime;
      a2->atime = FileInformation.ftLastAccessTime;
      a2->mtime = FileInformation.ftLastWriteTime;
      a2->cbSize.HighPart = FileInformation.nFileSizeHigh;
      a2->cbSize.LowPart = FileInformation.nFileSizeLow;
      result = 0;
      a2->type = 2;
    }
    else
    {
      return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004c460  mov     [rsp+arg_10], rbx
0x18004c465  mov     [rsp+arg_18], rsi
0x18004c46a  push    rdi
0x18004c46b  sub     rsp, 60h
0x18004c46f  mov     rax, cs:__security_cookie
0x18004c476  xor     rax, rsp
0x18004c479  mov     [rsp+68h+var_10], rax
0x18004c47e  mov     esi, r8d
0x18004c481  mov     rbx, rdx
0x18004c484  mov     rdi, rcx
0x18004c487  test    rdx, rdx
0x18004c48a  jnz     short loc_18004C496
0x18004c48c  mov     eax, 80030009h
0x18004c491  jmp     loc_18004C54C
0x18004c496  xor     edx, edx; Val
0x18004c498  mov     rcx, rbx; void *
0x18004c49b  lea     r8d, [rdx+50h]; Size
0x18004c49f  call    memset_0
0x18004c4a4  test    esi, esi
0x18004c4a6  jnz     short loc_18004C4E8
0x18004c4a8  mov     rcx, [rdi+20h]
0x18004c4ac  inc     rcx; cb
0x18004c4af  call    cs:__imp_CoTaskMemAlloc
0x18004c4b5  mov     [rbx], rax
0x18004c4b8  test    rax, rax
0x18004c4bb  jnz     short loc_18004C4C7
0x18004c4bd  mov     eax, 8007000Eh
0x18004c4c2  jmp     loc_18004C54C
0x18004c4c7  lea     r8, [rdi+10h]
0x18004c4cb  cmp     qword ptr [r8+18h], 8
0x18004c4d0  jb      short loc_18004C4D5
0x18004c4d2  mov     r8, [r8]; unsigned __int16 *
0x18004c4d5  mov     rdx, [rdi+20h]
0x18004c4d9  mov     rcx, rax; unsigned __int16 *
0x18004c4dc  inc     rdx; unsigned __int64
0x18004c4df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004c4e4  test    eax, eax
0x18004c4e6  js      short loc_18004C54C
0x18004c4e8  mov     rcx, [rdi+30h]; hFile
0x18004c4ec  lea     rdx, [rsp+68h+FileInformation]; lpFileInformation
0x18004c4f1  xorps   xmm0, xmm0
0x18004c4f4  xor     eax, eax
0x18004c4f6  movups  xmmword ptr [rsp+68h+FileInformation.dwFileAttributes], xmm0
0x18004c4fb  mov     [rsp+68h+FileInformation.nFileIndexLow], eax
0x18004c4ff  movups  xmmword ptr [rsp+68h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18004c504  movups  xmmword ptr [rsp+68h+FileInformation.nFileSizeHigh], xmm0
0x18004c509  call    cs:__imp_GetFileInformationByHandle
0x18004c50f  test    eax, eax
0x18004c511  jnz     short loc_18004C51A
0x18004c513  mov     eax, 80004005h
0x18004c518  jmp     short loc_18004C54C
0x18004c51a  mov     rax, qword ptr [rsp+68h+FileInformation.ftCreationTime.dwLowDateTime]
0x18004c51f  mov     [rbx+20h], rax
0x18004c523  mov     rax, qword ptr [rsp+68h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x18004c528  mov     [rbx+28h], rax
0x18004c52c  mov     rax, qword ptr [rsp+68h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18004c531  mov     [rbx+18h], rax
0x18004c535  mov     eax, [rsp+68h+FileInformation.nFileSizeHigh]
0x18004c539  mov     [rbx+14h], eax
0x18004c53c  mov     eax, [rsp+68h+FileInformation.nFileSizeLow]
0x18004c540  mov     [rbx+10h], eax
0x18004c543  xor     eax, eax
0x18004c545  mov     dword ptr [rbx+8], 2
0x18004c54c  mov     rcx, [rsp+68h+var_10]
0x18004c551  xor     rcx, rsp; StackCookie
0x18004c554  call    __security_check_cookie
0x18004c559  lea     r11, [rsp+68h+var_8]
0x18004c55e  mov     rbx, [r11+20h]
0x18004c562  mov     rsi, [r11+28h]
0x18004c566  mov     rsp, r11
0x18004c569  pop     rdi
0x18004c56a  retn
```
