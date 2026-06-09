# BufferWriter::CBufferWriter::CreateInstance(ushort const *,ulong,BufferWriter::CBufferWriter * *)

- ea: `0x180013d34`
- end: `0x180013e8e`
- name: `?CreateInstance@CBufferWriter@BufferWriter@@SAJPEBGKPEAPEAV12@@Z`
- size: `346`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, struct BufferWriter::CBufferWriter **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013bb8`
- `0x1800168c4`

## callees

- `0x180001008`
- `0x18001367c`
- `0x180013d34`
- `0x180015190`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013dac`
- `KERNEL32!GetLastError` at `0x180013e33`
- `KERNEL32!GetLastError` at `0x180013dac`
- `KERNEL32!GetLastError` at `0x180013e33`
- `KERNEL32!CreateEventW` at `0x180013d9d`
- `KERNEL32!CreateEventW` at `0x180013d9d`
- `KERNEL32!InitializeCriticalSection` at `0x180013d74`
- `KERNEL32!InitializeCriticalSection` at `0x180013d8c`
- `KERNEL32!InitializeCriticalSection` at `0x180013d74`
- `KERNEL32!InitializeCriticalSection` at `0x180013d8c`

## pseudocode

```c
__int64 __fastcall BufferWriter::CBufferWriter::CreateInstance(
        LPCWSTR lpFileName,
        __int64 a2,
        struct BufferWriter::CBufferWriter **a3)
{
  char *v5; // rdi
  signed int v6; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  struct _SECURITY_ATTRIBUTES *v9; // r9
  BufferWriter::CAsyncIO *v10; // rbx
  __int64 v11; // rax
  signed int v12; // eax
  BufferWriter::CAsyncIO *v13; // rcx

  *a3 = 0;
  v5 = (char *)operator new(0x98u);
  if ( v5 )
  {
    v6 = 0;
    *(_QWORD *)v5 = &BufferWriter::CAsyncIO::`vftable';
    *((_QWORD *)v5 + 1) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
    *((_DWORD *)v5 + 14) = 0;
    *((_QWORD *)v5 + 8) = 0;
    *((_QWORD *)v5 + 9) = 0;
    *((_DWORD *)v5 + 20) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 88));
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)v5 + 9) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    *((_QWORD *)v5 + 16) = -1;
    *(_QWORD *)v5 = &BufferWriter::CBufferWriter::`vftable';
    *((_DWORD *)v5 + 34) = 0;
    *a3 = (struct BufferWriter::CBufferWriter *)v5;
    if ( v6 >= 0 )
    {
      v6 = BufferWriter::CAsyncIO::Active((BufferWriter::CAsyncIO *)v5);
      if ( v6 >= 0 )
      {
        v10 = *a3;
        if ( *((_QWORD *)*a3 + 16) == -1 )
        {
          v11 = BufferWriter::CAsyncIO::IOCreateFile(*a3, (ULONG_PTR)*a3, lpFileName, v9);
          *((_QWORD *)v10 + 16) = v11;
          if ( v11 == -1 )
          {
            v12 = GetLastError();
            v6 = v12;
            if ( v12 > 0 )
              v6 = (unsigned __int16)v12 | 0x80070000;
          }
          else
          {
            *((_QWORD *)v10 + 18) = 0;
            v6 = 0;
          }
        }
        else
        {
          v6 = -2147418113;
        }
      }
    }
    v13 = *a3;
    if ( v6 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v13 + 34);
      return (unsigned int)v6;
    }
  }
  else
  {
    *a3 = 0;
    v6 = -2147024882;
    v13 = *a3;
  }
  if ( v13 )
    (**(void (__fastcall ***)(BufferWriter::CAsyncIO *, __int64))v13)(v13, 1);
  *a3 = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013d34  push    rbx
0x180013d36  push    rbp
0x180013d37  push    rsi
0x180013d38  push    rdi
0x180013d39  sub     rsp, 38h
0x180013d3d  mov     rbp, rcx
0x180013d40  mov     qword ptr [r8], 0
0x180013d47  mov     ecx, 98h; Size
0x180013d4c  mov     rsi, r8
0x180013d4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013d54  mov     rdi, rax
0x180013d57  test    rax, rax
0x180013d5a  jz      loc_180013E58
0x180013d60  lea     rax, ??_7CAsyncIO@BufferWriter@@6B@; const BufferWriter::CAsyncIO::`vftable'
0x180013d67  xor     ebx, ebx
0x180013d69  lea     rcx, [rdi+10h]; lpCriticalSection
0x180013d6d  mov     [rdi], rax
0x180013d70  mov     [rdi+8], rbx
0x180013d74  call    cs:__imp_InitializeCriticalSection
0x180013d7a  mov     [rdi+38h], ebx
0x180013d7d  lea     rcx, [rdi+58h]; lpCriticalSection
0x180013d81  mov     [rdi+40h], rbx
0x180013d85  mov     [rdi+48h], rbx
0x180013d89  mov     [rdi+50h], ebx
0x180013d8c  call    cs:__imp_InitializeCriticalSection
0x180013d92  lea     edx, [rbx+1]; bManualReset
0x180013d95  xor     r9d, r9d; lpName
0x180013d98  mov     r8d, edx; bInitialState
0x180013d9b  xor     ecx, ecx; lpEventAttributes
0x180013d9d  call    cs:__imp_CreateEventW
0x180013da3  mov     [rdi+48h], rax
0x180013da7  test    rax, rax
0x180013daa  jnz     short loc_180013DC1
0x180013dac  call    cs:__imp_GetLastError
0x180013db2  mov     ebx, eax
0x180013db4  test    eax, eax
0x180013db6  jle     short loc_180013DC1
0x180013db8  movzx   ebx, ax
0x180013dbb  or      ebx, 80070000h
0x180013dc1  mov     qword ptr [rdi+80h], 0FFFFFFFFFFFFFFFFh
0x180013dcc  lea     rax, ??_7CBufferWriter@BufferWriter@@6B@; const BufferWriter::CBufferWriter::`vftable'
0x180013dd3  mov     [rdi], rax
0x180013dd6  mov     dword ptr [rdi+88h], 0
0x180013de0  mov     [rsi], rdi
0x180013de3  test    ebx, ebx
0x180013de5  js      short loc_180013E48
0x180013de7  mov     rcx, rdi; this
0x180013dea  call    ?Active@CAsyncIO@BufferWriter@@QEAAKXZ; BufferWriter::CAsyncIO::Active(void)
0x180013def  mov     ebx, eax
0x180013df1  test    eax, eax
0x180013df3  js      short loc_180013E48
0x180013df5  mov     rbx, [rsi]
0x180013df8  cmp     qword ptr [rbx+80h], 0FFFFFFFFFFFFFFFFh
0x180013e00  jz      short loc_180013E09
0x180013e02  mov     ebx, 8000FFFFh
0x180013e07  jmp     short loc_180013E48
0x180013e09  mov     r8, rbp; lpFileName
0x180013e0c  mov     rdx, rbx; CompletionKey
0x180013e0f  mov     rcx, rbx; this
0x180013e12  call    ?IOCreateFile@CAsyncIO@BufferWriter@@QEAAPEAX_KPEBGPEAU_SECURITY_ATTRIBUTES@@K@Z; BufferWriter::CAsyncIO::IOCreateFile(unsigned __int64,ushort const *,_SECURITY_ATTRIBUTES *,ulong)
0x180013e17  mov     [rbx+80h], rax
0x180013e1e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013e22  jz      short loc_180013E33
0x180013e24  mov     qword ptr [rbx+90h], 0
0x180013e2f  xor     ebx, ebx
0x180013e31  jmp     short loc_180013E48
0x180013e33  call    cs:__imp_GetLastError
0x180013e39  mov     ebx, eax
0x180013e3b  test    eax, eax
0x180013e3d  jle     short loc_180013E48
0x180013e3f  movzx   ebx, ax
0x180013e42  or      ebx, 80070000h
0x180013e48  mov     rcx, [rsi]
0x180013e4b  test    ebx, ebx
0x180013e4d  js      short loc_180013E67
0x180013e4f  lock inc dword ptr [rcx+88h]
0x180013e56  jmp     short loc_180013E83
0x180013e58  mov     qword ptr [rsi], 0
0x180013e5f  mov     ebx, 8007000Eh
0x180013e64  mov     rcx, [rsi]
0x180013e67  test    rcx, rcx
0x180013e6a  jz      short loc_180013E7C
0x180013e6c  mov     rax, [rcx]
0x180013e6f  mov     edx, 1
0x180013e74  mov     rax, [rax]
0x180013e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e7c  mov     qword ptr [rsi], 0
0x180013e83  mov     eax, ebx
0x180013e85  add     rsp, 38h
0x180013e89  pop     rdi
0x180013e8a  pop     rsi
0x180013e8b  pop     rbp
0x180013e8c  pop     rbx
0x180013e8d  retn
```
