# BufferWriter::CBufferWriter::PendWrite(uchar *,long,IUnknown *)

- ea: `0x1800162f4`
- end: `0x180016407`
- name: `?PendWrite@CBufferWriter@BufferWriter@@QEAAJPEAEJPEAUIUnknown@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(BufferWriter::CBufferWriter *__hidden this, LPCVOID lpBuffer, int, struct IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800168c4`

## callees

- `0x180001008`
- `0x180001048`
- `0x180015000`
- `0x1800162f4`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016397`
- `KERNEL32!GetLastError` at `0x180016397`

## pseudocode

```c
__int64 __fastcall BufferWriter::CBufferWriter::PendWrite(
        BufferWriter::CBufferWriter *this,
        LPCVOID lpBuffer,
        int a3,
        struct IUnknown *a4)
{
  __int64 v5; // rbp
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rbx
  unsigned int v11; // ebx
  signed int LastError; // eax
  void (__fastcall ***v13)(_QWORD, __int64); // rcx

  v5 = a3;
  v8 = operator new(0x30u);
  v9 = v8;
  if ( v8 )
  {
    v10 = *((_QWORD *)this + 18);
    *v8 = this;
    v8[1] = a4;
    _InterlockedIncrement((volatile signed __int32 *)this + 34);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8[1] + 8LL))(v8[1]);
    v9[2] = 0;
    v9[3] = 0;
    v9[5] = 0;
    v9[4] = v10;
    if ( (unsigned int)BufferWriter::CAsyncIO::IOAsyncWrite(
                         this,
                         *((HANDLE *)this + 16),
                         lpBuffer,
                         v5,
                         (LPOVERLAPPED)(v9 + 2)) )
    {
      *((_QWORD *)this + 18) += v5;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v13 = (void (__fastcall ***)(_QWORD, __int64))*v9;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*v9 + 136LL), 0xFFFFFFFF) == 1 && v13 )
        (**v13)(v13, 1);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[1] + 16LL))(v9[1]);
      operator delete(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v11;
}

```

## disassembly

```asm
0x1800162f4  push    rbx
0x1800162f6  push    rbp
0x1800162f7  push    rsi
0x1800162f8  push    rdi
0x1800162f9  push    r14
0x1800162fb  push    r15
0x1800162fd  sub     rsp, 48h
0x180016301  mov     rsi, rcx
0x180016304  movsxd  rbp, r8d
0x180016307  mov     ecx, 30h ; '0'; Size
0x18001630c  mov     r14, r9
0x18001630f  mov     r15, rdx
0x180016312  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016317  mov     rdi, rax
0x18001631a  test    rax, rax
0x18001631d  jz      loc_1800163F3
0x180016323  mov     rbx, [rsi+90h]
0x18001632a  mov     [rax], rsi
0x18001632d  mov     [rax+8], r14
0x180016331  lock inc dword ptr [rsi+88h]
0x180016338  mov     rcx, [rax+8]
0x18001633c  mov     rdx, [rcx]
0x18001633f  mov     rax, [rdx+8]
0x180016343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016348  mov     qword ptr [rdi+10h], 0
0x180016350  lea     rax, [rdi+10h]
0x180016354  mov     qword ptr [rdi+18h], 0
0x18001635c  mov     r9d, ebp; nNumberOfBytesToWrite
0x18001635f  mov     qword ptr [rdi+28h], 0
0x180016367  mov     r8, r15; lpBuffer
0x18001636a  mov     [rdi+20h], ebx
0x18001636d  mov     rcx, rsi; this
0x180016370  shr     rbx, 20h
0x180016374  mov     [rdi+24h], ebx
0x180016377  mov     rdx, [rsi+80h]; hFile
0x18001637e  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180016383  call    ?IOAsyncWrite@CAsyncIO@BufferWriter@@QEAAHPEAXPEBXKPEAU_OVERLAPPED@@@Z; BufferWriter::CAsyncIO::IOAsyncWrite(void *,void const *,ulong,_OVERLAPPED *)
0x180016388  test    eax, eax
0x18001638a  jz      short loc_180016397
0x18001638c  add     [rsi+90h], rbp
0x180016393  xor     ebx, ebx
0x180016395  jmp     short loc_1800163F8
0x180016397  call    cs:__imp_GetLastError
0x18001639d  mov     ebx, eax
0x18001639f  test    eax, eax
0x1800163a1  jle     short loc_1800163AC
0x1800163a3  movzx   ebx, ax
0x1800163a6  or      ebx, 80070000h
0x1800163ac  mov     rcx, [rdi]
0x1800163af  or      eax, 0FFFFFFFFh
0x1800163b2  lock xadd [rcx+88h], eax
0x1800163ba  cmp     eax, 1
0x1800163bd  jnz     short loc_1800163D4
0x1800163bf  test    rcx, rcx
0x1800163c2  jz      short loc_1800163D4
0x1800163c4  mov     rax, [rcx]
0x1800163c7  mov     edx, 1
0x1800163cc  mov     rax, [rax]
0x1800163cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163d4  mov     rcx, [rdi+8]
0x1800163d8  mov     rax, [rcx]
0x1800163db  mov     rax, [rax+10h]
0x1800163df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163e4  mov     edx, 30h ; '0'; unsigned __int64
0x1800163e9  mov     rcx, rdi; void *
0x1800163ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800163f1  jmp     short loc_1800163F8
0x1800163f3  mov     ebx, 8007000Eh
0x1800163f8  mov     eax, ebx
0x1800163fa  add     rsp, 48h
0x1800163fe  pop     r15
0x180016400  pop     r14
0x180016402  pop     rdi
0x180016403  pop     rsi
0x180016404  pop     rbp
0x180016405  pop     rbx
0x180016406  retn
```
