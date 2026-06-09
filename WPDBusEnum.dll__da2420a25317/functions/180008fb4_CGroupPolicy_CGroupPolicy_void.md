# CGroupPolicy::~CGroupPolicy(void)

- ea: `0x180008fb4`
- end: `0x180009084`
- name: `??1CGroupPolicy@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(CGroupPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ea84`

## callees

- `0x180002fa0`
- `0x180008fb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008fdb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008fdb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180008fd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180008fd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009063`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ff9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000900c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000902b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009034`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008ff9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000900c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000902b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009034`

## string_xrefs

- `0x18000903f`: `Deleted GP object\n`

## pseudocode

```c
void __fastcall CGroupPolicy::~CGroupPolicy(CGroupPolicy *this)
{
  struct _TP_WORK *v2; // rcx
  HLOCAL *v3; // rsi
  HLOCAL *v4; // rbx
  HLOCAL *v5; // rsi
  HLOCAL *v6; // rbx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 0);
    CloseThreadpoolWork(*((PTP_WORK *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  v3 = (HLOCAL *)*((_QWORD *)this + 1);
  while ( v3 )
  {
    v4 = v3;
    v3 = (HLOCAL *)*v3;
    LocalFree(v4[1]);
    LocalFree(v4[2]);
    LocalFree(v4);
  }
  *((_QWORD *)this + 1) = 0;
  v5 = (HLOCAL *)*((_QWORD *)this + 2);
  while ( v5 )
  {
    v6 = v5;
    v5 = (HLOCAL *)*v5;
    LocalFree(v6[1]);
    LocalFree(v6);
  }
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  GPDebugPrintX(8, "Deleted GP object\n");
  if ( GPLogFileHandle != (HANDLE)-1LL )
  {
    CloseHandle(GPLogFileHandle);
    GPLogFileHandle = (HANDLE)-1LL;
  }
}

```

## disassembly

```asm
0x180008fb4  mov     [rsp+arg_0], rbx
0x180008fb9  mov     [rsp+arg_8], rsi
0x180008fbe  push    rdi
0x180008fbf  sub     rsp, 20h
0x180008fc3  mov     rdi, rcx
0x180008fc6  mov     rcx, [rcx+28h]; pwk
0x180008fca  test    rcx, rcx
0x180008fcd  jz      short loc_180008FE9
0x180008fcf  xor     edx, edx; fCancelPendingCallbacks
0x180008fd1  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180008fd7  mov     rcx, [rdi+28h]; pwk
0x180008fdb  call    cs:__imp_CloseThreadpoolWork
0x180008fe1  mov     qword ptr [rdi+28h], 0
0x180008fe9  mov     rsi, [rdi+8]
0x180008fed  jmp     short loc_180009012
0x180008fef  mov     rbx, rsi
0x180008ff2  mov     rsi, [rsi]
0x180008ff5  mov     rcx, [rbx+8]; hMem
0x180008ff9  call    cs:__imp_LocalFree
0x180008fff  mov     rcx, [rbx+10h]; hMem
0x180009003  call    cs:__imp_LocalFree
0x180009009  mov     rcx, rbx; hMem
0x18000900c  call    cs:__imp_LocalFree
0x180009012  test    rsi, rsi
0x180009015  jnz     short loc_180008FEF
0x180009017  mov     [rdi+8], rsi
0x18000901b  mov     rsi, [rdi+10h]
0x18000901f  jmp     short loc_18000903A
0x180009021  mov     rbx, rsi
0x180009024  mov     rsi, [rsi]
0x180009027  mov     rcx, [rbx+8]; hMem
0x18000902b  call    cs:__imp_LocalFree
0x180009031  mov     rcx, rbx; hMem
0x180009034  call    cs:__imp_LocalFree
0x18000903a  test    rsi, rsi
0x18000903d  jnz     short loc_180009021
0x18000903f  lea     rdx, aDeletedGpObjec; "Deleted GP object\n"
0x180009046  mov     [rdi+10h], rsi
0x18000904a  lea     ecx, [rsi+8]; unsigned int
0x18000904d  mov     [rdi+18h], rsi
0x180009051  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180009056  mov     rcx, cs:?GPLogFileHandle@@3PEAXEA; hObject
0x18000905d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009061  jz      short loc_180009074
0x180009063  call    cs:__imp_CloseHandle
0x180009069  mov     cs:?GPLogFileHandle@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * GPLogFileHandle
0x180009074  mov     rbx, [rsp+28h+arg_0]
0x180009079  mov     rsi, [rsp+28h+arg_8]
0x18000907e  add     rsp, 20h
0x180009082  pop     rdi
0x180009083  retn
```
