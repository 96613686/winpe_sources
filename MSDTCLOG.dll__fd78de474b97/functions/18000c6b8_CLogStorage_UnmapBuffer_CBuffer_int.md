# CLogStorage::_UnmapBuffer(CBuffer *,int)

- ea: `0x18000c6b8`
- end: `0x18000c7f3`
- name: `?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z`
- size: `315`
- prototype: `void __fastcall(CLogStorage *__hidden this, struct CBuffer *, int)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002900`
- `0x1800073b4`
- `0x18000a088`
- `0x18000a1a8`
- `0x18000a288`
- `0x18000b06c`
- `0x18000b2c8`
- `0x18000b658`
- `0x18000bc44`
- `0x18000ce68`
- `0x18000d160`
- `0x180014042`
- `0x1800140ba`

## callees

- `0x18000c6b8`
- `0x18000d998`
- `0x18001266c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000c6fc`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000c6fc`
- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x18000c6d9`
- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x18000c6d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c706`

## string_xrefs

- `0x18000c719`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLogStorage::_UnmapBuffer(CLogStorage *this, LPCVOID *a2, int a3)
{
  DWORD LastError; // eax
  char *v6; // rdx
  int v7; // r9d
  ulong v8; // ebx
  int v10; // eax
  int v11; // eax
  ulong pExceptionObject; // [rsp+70h] [rbp+18h] BYREF

  if ( a3 && !FlushViewOfFile(a2[3], *((unsigned int *)a2 + 1)) )
  {
    LastError = GetLastError();
    v6 = "FlushViewOfFile";
    v7 = 783;
    goto LABEL_6;
  }
  if ( !UnmapViewOfFile(a2[2]) )
  {
    LastError = GetLastError();
    v6 = "UnmapViewOfFile";
    v7 = 800;
LABEL_6:
    v8 = LastError;
    TraceFile(LastError, v6, "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", v7);
    if ( v8 )
    {
      pExceptionObject = v8;
      throw &pExceptionObject;
    }
    return;
  }
  (**((void (__fastcall ***)(char *))this + 86))((char *)this + 688);
  *a2 = 0;
  *((_DWORD *)a2 + 2) = 0;
  a2[2] = 0;
  a2[3] = 0;
  a2[4] = 0;
  *((_DWORD *)a2 + 10) = 0;
  a2[6] = 0;
  a2[7] = 0;
  a2[8] = 0;
  if ( (*((_DWORD *)this + 186))-- == 1 )
  {
    *((_DWORD *)this + 192) = 1;
    *((_QWORD *)this + 95) = 0;
  }
  else
  {
    v10 = *((_DWORD *)this + 191);
    if ( *((_DWORD *)a2 + 18) == v10 )
    {
      *((_DWORD *)this + 191) = (unsigned int)(v10 - 1) % *((_DWORD *)this + 187);
    }
    else
    {
      v11 = *((_DWORD *)this + 190);
      if ( *((_DWORD *)a2 + 18) == v11 )
        *((_DWORD *)this + 190) = (unsigned int)(v11 + 1) % *((_DWORD *)this + 187);
    }
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 86) + 8LL))((char *)this + 688);
}

```

## disassembly

```asm
0x18000c6b8  push    rbx
0x18000c6ba  push    rbp
0x18000c6bb  push    rsi
0x18000c6bc  push    rdi
0x18000c6bd  push    r14
0x18000c6bf  push    r15
0x18000c6c1  sub     rsp, 28h
0x18000c6c5  mov     rdi, rdx
0x18000c6c8  mov     rbx, rcx
0x18000c6cb  xor     ebp, ebp
0x18000c6cd  test    r8d, r8d
0x18000c6d0  jz      short loc_18000C6F8
0x18000c6d2  mov     edx, [rdx+4]; dwNumberOfBytesToFlush
0x18000c6d5  mov     rcx, [rdi+18h]; lpBaseAddress
0x18000c6d9  call    cs:__imp_FlushViewOfFile
0x18000c6df  test    eax, eax
0x18000c6e1  jnz     short loc_18000C6F8
0x18000c6e3  call    cs:__imp_GetLastError
0x18000c6e9  lea     rdx, aFlushviewoffil; "FlushViewOfFile"
0x18000c6f0  mov     r9d, 30Fh
0x18000c6f6  jmp     short loc_18000C719
0x18000c6f8  mov     rcx, [rdi+10h]; lpBaseAddress
0x18000c6fc  call    cs:__imp_UnmapViewOfFile
0x18000c702  test    eax, eax
0x18000c704  jnz     short loc_18000C736
0x18000c706  call    cs:__imp_GetLastError
0x18000c70c  lea     rdx, aUnmapviewoffil; "UnmapViewOfFile"
0x18000c713  mov     r9d, 320h; unsigned int
0x18000c719  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000c720  mov     ecx, eax; int
0x18000c722  mov     ebx, eax
0x18000c724  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000c729  test    ebx, ebx
0x18000c72b  jnz     loc_18000C7DD
0x18000c731  jmp     loc_18000C7D0
0x18000c736  lea     r15, [rbx+2B0h]
0x18000c73d  mov     rax, [r15]
0x18000c740  mov     rcx, r15
0x18000c743  mov     rax, [rax]
0x18000c746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c74b  mov     [rdi], rbp
0x18000c74e  mov     [rdi+8], ebp
0x18000c751  mov     [rdi+10h], rbp
0x18000c755  mov     [rdi+18h], rbp
0x18000c759  mov     [rdi+20h], rbp
0x18000c75d  mov     [rdi+28h], ebp
0x18000c760  mov     [rdi+30h], rbp
0x18000c764  mov     [rdi+38h], rbp
0x18000c768  mov     [rdi+40h], rbp
0x18000c76c  add     dword ptr [rbx+2E8h], 0FFFFFFFFh
0x18000c773  jnz     short loc_18000C788
0x18000c775  mov     dword ptr [rbx+300h], 1
0x18000c77f  mov     [rbx+2F8h], rbp
0x18000c786  jmp     short loc_18000C7C0
0x18000c788  mov     eax, [rbx+2FCh]
0x18000c78e  cmp     [rdi+48h], eax
0x18000c791  jnz     short loc_18000C7A5
0x18000c793  dec     eax
0x18000c795  xor     edx, edx
0x18000c797  div     dword ptr [rbx+2ECh]
0x18000c79d  mov     [rbx+2FCh], edx
0x18000c7a3  jmp     short loc_18000C7C0
0x18000c7a5  mov     eax, [rbx+2F8h]
0x18000c7ab  cmp     [rdi+48h], eax
0x18000c7ae  jnz     short loc_18000C7C0
0x18000c7b0  inc     eax
0x18000c7b2  xor     edx, edx
0x18000c7b4  div     dword ptr [rbx+2ECh]
0x18000c7ba  mov     [rbx+2F8h], edx
0x18000c7c0  mov     rax, [r15]
0x18000c7c3  mov     rcx, r15
0x18000c7c6  mov     rax, [rax+8]
0x18000c7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7cf  nop
0x18000c7d0  add     rsp, 28h
0x18000c7d4  pop     r15
0x18000c7d6  pop     r14
0x18000c7d8  pop     rdi
0x18000c7d9  pop     rsi
0x18000c7da  pop     rbp
0x18000c7db  pop     rbx
0x18000c7dc  retn
0x18000c7dd  mov     [rsp+58h+pExceptionObject], ebx
0x18000c7e1  lea     rdx, _TI1K; pThrowInfo
0x18000c7e8  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000c7ed  call    _CxxThrowException_0
```
