# CFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x14004d9e0`
- end: `0x14004db3c`
- name: `?Stat@CFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `348`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400061f8`
- `0x140016098`
- `0x14004d9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004da7e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14004da66`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14004da66`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14004daa9`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14004daa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004dae9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004dae9`

## pseudocode

```c
signed int __fastcall CFileStream::Stat(CFileStream *this, struct tagSTATSTG *a2, char a3)
{
  signed int result; // eax
  DWORD FileSize; // eax
  CLMString *v8; // rsi
  LPVOID v9; // rax
  size_t v10; // rdi
  void *v11; // rbx
  wchar_t *Buffer; // rax

  if ( !a2 )
    return -2147467261;
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return -2147024890;
  *((_DWORD *)a2 + 2) = 2;
  if ( *((_DWORD *)this + 50) )
  {
    *((_QWORD *)a2 + 2) = *((_QWORD *)this + 29);
    *((_QWORD *)a2 + 4) = *(_QWORD *)((char *)this + 204);
    *((_QWORD *)a2 + 5) = *(_QWORD *)((char *)this + 212);
    *((_QWORD *)a2 + 3) = *(_QWORD *)((char *)this + 220);
  }
  else
  {
    FileSize = GetFileSize(*((HANDLE *)this + 3), (LPDWORD)a2 + 5);
    *((_DWORD *)a2 + 4) = FileSize;
    if ( FileSize == -1 && GetLastError()
      || !GetFileTime(*((HANDLE *)this + 3), (LPFILETIME)a2 + 4, (LPFILETIME)a2 + 5, (LPFILETIME)a2 + 3) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
  *((_DWORD *)a2 + 12) = *((_DWORD *)this + 48);
  *((_DWORD *)a2 + 13) = 2;
  *((_QWORD *)a2 + 9) = 0;
  *(GUID *)((char *)a2 + 56) = GUID_NULL;
  if ( (a3 & 1) != 0 )
  {
    *(_QWORD *)a2 = 0;
  }
  else
  {
    v8 = (CFileStream *)((char *)this + 32);
    v9 = CoTaskMemAlloc(2LL * (unsigned int)(*((_DWORD *)this + 13) + 1));
    *(_QWORD *)a2 = v9;
    if ( !v9 )
      return -2147024882;
    v10 = 2LL * (unsigned int)(*((_DWORD *)this + 13) + 1);
    v11 = v9;
    Buffer = CLMString::GetBuffer(v8, 0);
    memcpy_0(v11, Buffer, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x14004d9e0  mov     [rsp+arg_0], rbx
0x14004d9e5  mov     [rsp+arg_8], rsi
0x14004d9ea  push    rdi
0x14004d9eb  sub     rsp, 20h
0x14004d9ef  mov     esi, r8d
0x14004d9f2  mov     rbx, rdx
0x14004d9f5  mov     rdi, rcx
0x14004d9f8  test    rdx, rdx
0x14004d9fb  jnz     short loc_14004DA07
0x14004d9fd  mov     eax, 80004003h
0x14004da02  jmp     loc_14004DB2C
0x14004da07  mov     rax, [rcx+18h]
0x14004da0b  inc     rax
0x14004da0e  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004da14  jnz     short loc_14004DA20
0x14004da16  mov     eax, 80070006h
0x14004da1b  jmp     loc_14004DB2C
0x14004da20  mov     dword ptr [rdx+8], 2
0x14004da27  cmp     dword ptr [rcx+0C8h], 0
0x14004da2e  jz      short loc_14004DA5E
0x14004da30  mov     rax, [rcx+0E8h]
0x14004da37  mov     [rdx+10h], rax
0x14004da3b  mov     rax, [rcx+0CCh]
0x14004da42  mov     [rdx+20h], rax
0x14004da46  mov     rax, [rcx+0D4h]
0x14004da4d  mov     [rdx+28h], rax
0x14004da51  mov     rax, [rcx+0DCh]
0x14004da58  mov     [rdx+18h], rax
0x14004da5c  jmp     short loc_14004DAB3
0x14004da5e  mov     rcx, [rcx+18h]; hFile
0x14004da62  add     rdx, 14h; lpFileSizeHigh
0x14004da66  call    cs:__imp_GetFileSize
0x14004da6c  mov     [rbx+10h], eax
0x14004da6f  cmp     eax, 0FFFFFFFFh
0x14004da72  jnz     short loc_14004DA99
0x14004da74  call    cs:__imp_GetLastError
0x14004da7a  test    eax, eax
0x14004da7c  jz      short loc_14004DA99
0x14004da7e  call    cs:__imp_GetLastError
0x14004da84  test    eax, eax
0x14004da86  jle     loc_14004DB2C
0x14004da8c  movzx   eax, ax
0x14004da8f  or      eax, 80070000h
0x14004da94  jmp     loc_14004DB2C
0x14004da99  mov     rcx, [rdi+18h]; hFile
0x14004da9d  lea     r9, [rbx+18h]; lpLastWriteTime
0x14004daa1  lea     r8, [rbx+28h]; lpLastAccessTime
0x14004daa5  lea     rdx, [rbx+20h]; lpCreationTime
0x14004daa9  call    cs:__imp_GetFileTime
0x14004daaf  test    eax, eax
0x14004dab1  jz      short loc_14004DA7E
0x14004dab3  mov     eax, [rdi+0C0h]
0x14004dab9  mov     [rbx+30h], eax
0x14004dabc  mov     dword ptr [rbx+34h], 2
0x14004dac3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14004daca  mov     qword ptr [rbx+48h], 0
0x14004dad2  movdqu  xmmword ptr [rbx+38h], xmm0
0x14004dad7  test    sil, 1
0x14004dadb  jnz     short loc_14004DB23
0x14004dadd  lea     rsi, [rdi+20h]
0x14004dae1  mov     ecx, [rsi+14h]
0x14004dae4  inc     ecx
0x14004dae6  add     rcx, rcx; cb
0x14004dae9  call    cs:__imp_CoTaskMemAlloc
0x14004daef  mov     [rbx], rax
0x14004daf2  test    rax, rax
0x14004daf5  jnz     short loc_14004DAFE
0x14004daf7  mov     eax, 8007000Eh
0x14004dafc  jmp     short loc_14004DB2C
0x14004dafe  mov     edi, [rdi+34h]
0x14004db01  xor     edx, edx; int
0x14004db03  inc     edi
0x14004db05  mov     rcx, rsi; this
0x14004db08  add     rdi, rdi
0x14004db0b  mov     rbx, rax
0x14004db0e  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x14004db13  mov     rdx, rax; Src
0x14004db16  mov     r8, rdi; Size
0x14004db19  mov     rcx, rbx; void *
0x14004db1c  call    memcpy_0
0x14004db21  jmp     short loc_14004DB2A
0x14004db23  mov     qword ptr [rbx], 0
0x14004db2a  xor     eax, eax
0x14004db2c  mov     rbx, [rsp+28h+arg_0]
0x14004db31  mov     rsi, [rsp+28h+arg_8]
0x14004db36  add     rsp, 20h
0x14004db3a  pop     rdi
0x14004db3b  retn
```
