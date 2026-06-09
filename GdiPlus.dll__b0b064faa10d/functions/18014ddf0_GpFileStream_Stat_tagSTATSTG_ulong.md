# GpFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x18014ddf0`
- end: `0x18014def2`
- name: `?Stat@GpFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `258`
- prototype: `__int64 __fastcall(GpFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800386f0`
- `0x18008e8c0`
- `0x1800f05d0`
- `0x18014ddf0`
- `0x180168478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014de60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014de60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014deb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014deb2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18014de52`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18014de52`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18014de83`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18014de83`

## pseudocode

```c
__int64 __fastcall GpFileStream::Stat(GpFileStream *this, struct tagSTATSTG *a2, char a3)
{
  unsigned int Win32HRESULT; // ecx
  DWORD FileSize; // eax
  const unsigned __int16 *v8; // rdx
  SIZE_T v9; // rsi
  void *v10; // rax
  int v12; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-10h]

  GpRuntime::GpLock::GpLock((GpRuntime::GpLock *)&v12, (GpFileStream *)((char *)this + 16));
  if ( v12 )
  {
    Win32HRESULT = -2147024726;
  }
  else
  {
    *((_DWORD *)a2 + 2) = 2;
    *((_DWORD *)a2 + 12) = *((_DWORD *)this + 10);
    *((_QWORD *)a2 + 9) = 0;
    *(_OWORD *)((char *)a2 + 56) = 0;
    *((_DWORD *)a2 + 13) = 0;
    FileSize = GetFileSize(*((HANDLE *)this + 3), (LPDWORD)a2 + 5);
    *((_DWORD *)a2 + 4) = FileSize;
    if ( (FileSize != -1 || !GetLastError())
      && GetFileTime(*((HANDLE *)this + 3), (LPFILETIME)a2 + 4, (LPFILETIME)a2 + 5, (LPFILETIME)a2 + 3) )
    {
      if ( (a3 & 1) != 0 )
      {
        *(_QWORD *)a2 = 0;
      }
      else
      {
        v9 = (int)(2 * GpRuntime::UnicodeStringLength(*((GpRuntime **)this + 4), v8) + 2);
        v10 = CoTaskMemAlloc(v9);
        *(_QWORD *)a2 = v10;
        if ( !v10 )
        {
          Win32HRESULT = -2147024882;
          goto LABEL_13;
        }
        memcpy_0(v10, *((const void **)this + 4), v9);
      }
      Win32HRESULT = 0;
      goto LABEL_13;
    }
    Win32HRESULT = GetWin32HRESULT();
  }
LABEL_13:
  _InterlockedDecrement(v13);
  return Win32HRESULT;
}

```

## disassembly

```asm
0x18014ddf0  mov     [rsp+arg_0], rbx
0x18014ddf5  mov     [rsp+arg_8], rsi
0x18014ddfa  push    rdi
0x18014ddfb  sub     rsp, 30h
0x18014ddff  mov     rbx, rdx
0x18014de02  mov     rdi, rcx
0x18014de05  lea     rdx, [rcx+10h]; struct GpRuntime::GpLockable *
0x18014de09  mov     esi, r8d
0x18014de0c  lea     rcx, [rsp+38h+var_18]; this
0x18014de11  call    ??0GpLock@GpRuntime@@QEAA@PEAVGpLockable@1@@Z; GpRuntime::GpLock::GpLock(GpRuntime::GpLockable *)
0x18014de16  cmp     [rsp+38h+var_18], 0
0x18014de1b  jz      short loc_18014DE27
0x18014de1d  mov     ecx, 800700AAh
0x18014de22  jmp     loc_18014DED8
0x18014de27  mov     dword ptr [rbx+8], 2
0x18014de2e  lea     rdx, [rbx+14h]; lpFileSizeHigh
0x18014de32  mov     eax, [rdi+28h]
0x18014de35  xorps   xmm0, xmm0
0x18014de38  mov     [rbx+30h], eax
0x18014de3b  mov     qword ptr [rbx+48h], 0
0x18014de43  movups  xmmword ptr [rbx+38h], xmm0
0x18014de47  mov     dword ptr [rbx+34h], 0
0x18014de4e  mov     rcx, [rdi+18h]; hFile
0x18014de52  call    cs:__imp_GetFileSize
0x18014de58  mov     [rbx+10h], eax
0x18014de5b  cmp     eax, 0FFFFFFFFh
0x18014de5e  jnz     short loc_18014DE73
0x18014de60  call    cs:__imp_GetLastError
0x18014de66  test    eax, eax
0x18014de68  jz      short loc_18014DE73
0x18014de6a  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x18014de6f  mov     ecx, eax
0x18014de71  jmp     short loc_18014DED8
0x18014de73  mov     rcx, [rdi+18h]; hFile
0x18014de77  lea     r9, [rbx+18h]; lpLastWriteTime
0x18014de7b  lea     r8, [rbx+28h]; lpLastAccessTime
0x18014de7f  lea     rdx, [rbx+20h]; lpCreationTime
0x18014de83  call    cs:__imp_GetFileTime
0x18014de89  test    eax, eax
0x18014de8b  jz      short loc_18014DE6A
0x18014de8d  test    sil, 1
0x18014de91  jz      short loc_18014DE9C
0x18014de93  mov     qword ptr [rbx], 0
0x18014de9a  jmp     short loc_18014DED6
0x18014de9c  mov     rcx, [rdi+20h]; this
0x18014dea0  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x18014dea5  lea     eax, ds:2[rax*2]
0x18014deac  movsxd  rsi, eax
0x18014deaf  mov     rcx, rsi; cb
0x18014deb2  call    cs:__imp_CoTaskMemAlloc
0x18014deb8  mov     [rbx], rax
0x18014debb  test    rax, rax
0x18014debe  jnz     short loc_18014DEC7
0x18014dec0  mov     ecx, 8007000Eh
0x18014dec5  jmp     short loc_18014DED8
0x18014dec7  mov     rdx, [rdi+20h]; Src
0x18014decb  mov     r8, rsi; Size
0x18014dece  mov     rcx, rax; void *
0x18014ded1  call    memcpy_0
0x18014ded6  xor     ecx, ecx
0x18014ded8  mov     rax, [rsp+38h+var_10]
0x18014dedd  mov     rbx, [rsp+38h+arg_0]
0x18014dee2  mov     rsi, [rsp+38h+arg_8]
0x18014dee7  lock dec dword ptr [rax]
0x18014deea  mov     eax, ecx
0x18014deec  add     rsp, 30h
0x18014def0  pop     rdi
0x18014def1  retn
```
