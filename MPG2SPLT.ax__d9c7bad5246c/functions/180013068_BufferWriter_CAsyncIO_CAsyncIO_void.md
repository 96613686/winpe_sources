# BufferWriter::CAsyncIO::~CAsyncIO(void)

- ea: `0x180013068`
- end: `0x18001311d`
- name: `??1CAsyncIO@BufferWriter@@UEAA@XZ`
- size: `181`
- prototype: `void __fastcall(BufferWriter::CAsyncIO *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180013124`
- `0x1800134c0`

## callees

- `0x180013068`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180013098`
- `KERNEL32!WaitForSingleObject` at `0x1800130c7`
- `KERNEL32!WaitForSingleObject` at `0x180013098`
- `KERNEL32!WaitForSingleObject` at `0x1800130c7`
- `KERNEL32!CloseHandle` at `0x1800130d5`
- `KERNEL32!CloseHandle` at `0x1800130f5`
- `KERNEL32!CloseHandle` at `0x1800130d5`
- `KERNEL32!CloseHandle` at `0x1800130f5`
- `KERNEL32!DeleteCriticalSection` at `0x1800130fe`
- `KERNEL32!DeleteCriticalSection` at `0x1800130fe`
- `KERNEL32!DeleteCriticalSection` at `0x180013116`
- `KERNEL32!LeaveCriticalSection` at `0x1800130ae`
- `KERNEL32!LeaveCriticalSection` at `0x1800130e6`
- `KERNEL32!LeaveCriticalSection` at `0x1800130ae`
- `KERNEL32!LeaveCriticalSection` at `0x1800130e6`
- `KERNEL32!EnterCriticalSection` at `0x18001308b`
- `KERNEL32!EnterCriticalSection` at `0x1800130a5`
- `KERNEL32!EnterCriticalSection` at `0x18001308b`
- `KERNEL32!EnterCriticalSection` at `0x1800130a5`

## pseudocode

```c
void __fastcall BufferWriter::CAsyncIO::~CAsyncIO(BufferWriter::CAsyncIO *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  void *v3; // rcx
  void *v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  *(_QWORD *)this = &BufferWriter::CAsyncIO::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v3 = (void *)*((_QWORD *)this + 8);
  *((_DWORD *)this + 14) = 1;
  if ( v3 && !WaitForSingleObject(v3, 0xFFFFFFFF) )
  {
    CloseHandle(*((HANDLE *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  LeaveCriticalSection(v2);
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
    CloseHandle(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x180013068  mov     [rsp+arg_0], rbx
0x18001306d  mov     [rsp+arg_8], rsi
0x180013072  push    rdi
0x180013073  sub     rsp, 20h
0x180013077  lea     rax, ??_7CAsyncIO@BufferWriter@@6B@; const BufferWriter::CAsyncIO::`vftable'
0x18001307e  mov     rbx, rcx
0x180013081  lea     rdi, [rcx+10h]
0x180013085  mov     [rcx], rax
0x180013088  mov     rcx, rdi; lpCriticalSection
0x18001308b  call    cs:__imp_EnterCriticalSection
0x180013091  mov     rcx, [rbx+48h]; hHandle
0x180013095  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013098  call    cs:__imp_WaitForSingleObject
0x18001309e  lea     rsi, [rbx+58h]
0x1800130a2  mov     rcx, rsi; lpCriticalSection
0x1800130a5  call    cs:__imp_EnterCriticalSection
0x1800130ab  mov     rcx, rsi; lpCriticalSection
0x1800130ae  call    cs:__imp_LeaveCriticalSection
0x1800130b4  mov     rcx, [rbx+40h]; hHandle
0x1800130b8  mov     dword ptr [rbx+38h], 1
0x1800130bf  test    rcx, rcx
0x1800130c2  jz      short loc_1800130E3
0x1800130c4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800130c7  call    cs:__imp_WaitForSingleObject
0x1800130cd  test    eax, eax
0x1800130cf  jnz     short loc_1800130E3
0x1800130d1  mov     rcx, [rbx+40h]; hObject
0x1800130d5  call    cs:__imp_CloseHandle
0x1800130db  mov     qword ptr [rbx+40h], 0
0x1800130e3  mov     rcx, rdi; lpCriticalSection
0x1800130e6  call    cs:__imp_LeaveCriticalSection
0x1800130ec  mov     rcx, [rbx+48h]; hObject
0x1800130f0  test    rcx, rcx
0x1800130f3  jz      short loc_1800130FB
0x1800130f5  call    cs:__imp_CloseHandle
0x1800130fb  mov     rcx, rsi; lpCriticalSection
0x1800130fe  call    cs:__imp_DeleteCriticalSection
0x180013104  mov     rcx, rdi
0x180013107  mov     rbx, [rsp+28h+arg_0]
0x18001310c  mov     rsi, [rsp+28h+arg_8]
0x180013111  add     rsp, 20h
0x180013115  pop     rdi
0x180013116  jmp     cs:__imp_DeleteCriticalSection
```
