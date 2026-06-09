# DSUtils::MakeDestinationDir(ushort const *)

- ea: `0x18001a654`
- end: `0x18001a6e7`
- name: `?MakeDestinationDir@DSUtils@@YAJPEBG@Z`
- size: `147`
- prototype: `__int64 __fastcall(DSUtils *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800109d8`

## callees

- `0x1800065a4`
- `0x18000c93c`
- `0x18001a654`
- `0x18001afe8`
- `0x18001b090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a688`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a688`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001a6bc`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001a6bc`

## pseudocode

```c
__int64 __fastcall DSUtils::MakeDestinationDir(DSUtils *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  unsigned __int64 v4; // rsi
  unsigned __int16 *v5; // rax
  WCHAR *v6; // rdi
  int DirectoryTree; // ebx
  unsigned __int16 *v9; // [rsp+50h] [rbp+8h] BYREF

  if ( !this )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  v9 = 0;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)this + v3) );
  v4 = v3 + 1;
  v5 = (unsigned __int16 *)LocalAlloc(0, 2 * (v3 + 1));
  v6 = v5;
  v9 = v5;
  if ( v5 )
  {
    DirectoryTree = StringCchCopyW(v5, v4, (const unsigned __int16 *)this);
    if ( DirectoryTree >= 0 )
    {
      DirectoryTree = PathCchRemoveFileSpec(v6, v4);
      if ( DirectoryTree >= 0 )
        DirectoryTree = CreateDirectoryTree(v6);
    }
  }
  else
  {
    DirectoryTree = -2147024882;
  }
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v9);
  return (unsigned int)DirectoryTree;
}

```

## disassembly

```asm
0x18001a654  push    rbx
0x18001a656  push    rbp
0x18001a657  push    rsi
0x18001a658  push    rdi
0x18001a659  sub     rsp, 28h
0x18001a65d  mov     rbx, rcx
0x18001a660  xor     ebp, ebp
0x18001a662  test    rcx, rcx
0x18001a665  jnz     short loc_18001A66C
0x18001a667  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a66c  mov     [rsp+48h+arg_0], rbp
0x18001a671  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a675  inc     rax
0x18001a678  cmp     [rbx+rax*2], bp
0x18001a67c  jnz     short loc_18001A675
0x18001a67e  lea     rsi, [rax+1]
0x18001a682  lea     rdx, [rsi+rsi]; uBytes
0x18001a686  xor     ecx, ecx; uFlags
0x18001a688  call    cs:__imp_LocalAlloc
0x18001a68e  mov     rdi, rax
0x18001a691  mov     [rsp+48h+arg_0], rax
0x18001a696  test    rax, rax
0x18001a699  jnz     short loc_18001A6A2
0x18001a69b  mov     ebx, 8007000Eh
0x18001a6a0  jmp     short loc_18001A6D2
0x18001a6a2  mov     r8, rbx; unsigned __int16 *
0x18001a6a5  mov     rdx, rsi; unsigned __int64
0x18001a6a8  mov     rcx, rdi; unsigned __int16 *
0x18001a6ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a6b0  mov     ebx, eax
0x18001a6b2  test    eax, eax
0x18001a6b4  js      short loc_18001A6D2
0x18001a6b6  mov     rdx, rsi; cchPath
0x18001a6b9  mov     rcx, rdi; pszPath
0x18001a6bc  call    cs:__imp_PathCchRemoveFileSpec
0x18001a6c2  mov     ebx, eax
0x18001a6c4  test    eax, eax
0x18001a6c6  js      short loc_18001A6D2
0x18001a6c8  mov     rcx, rdi
0x18001a6cb  call    CreateDirectoryTree
0x18001a6d0  mov     ebx, eax
0x18001a6d2  lea     rcx, [rsp+48h+arg_0]
0x18001a6d7  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x18001a6dc  mov     eax, ebx
0x18001a6de  add     rsp, 28h
0x18001a6e2  pop     rdi
0x18001a6e3  pop     rsi
0x18001a6e4  pop     rbp
0x18001a6e5  pop     rbx
0x18001a6e6  retn
```
