# ATL::CRegObject::~CRegObject(void)

- ea: `0x180049cb8`
- end: `0x180049d2f`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180060064`
- `0x1801088f3`

## callees

- `0x180002740`
- `0x180049cb8`

## import_xrefs

- `msvcrt!free` at `0x180049d28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180049d17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180049d17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049ccb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049ccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049d0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049d0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049ce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049ce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049cef`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  int i; // ebp
  LPVOID *v4; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v4 = *(LPVOID **)(*(_QWORD *)this + 8LL * i);
    CoTaskMemFree(v4[1]);
    CoTaskMemFree(*v4);
    WinFree(v4);
  }
  *((_DWORD *)this + 2) = 0;
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  free(*(void **)this);
}

```

## disassembly

```asm
0x180049cb8  push    rbx
0x180049cba  push    rbp
0x180049cbb  push    rsi
0x180049cbc  push    rdi
0x180049cbd  sub     rsp, 28h
0x180049cc1  lea     rsi, [rcx+10h]
0x180049cc5  mov     rdi, rcx
0x180049cc8  mov     rcx, rsi; lpCriticalSection
0x180049ccb  call    cs:__imp_EnterCriticalSection
0x180049cd1  xor     ebp, ebp
0x180049cd3  cmp     [rdi+8], ebp
0x180049cd6  jle     short loc_180049D04
0x180049cd8  mov     rax, [rdi]
0x180049cdb  movsxd  rcx, ebp
0x180049cde  mov     rbx, [rax+rcx*8]
0x180049ce2  mov     rcx, [rbx+8]; pv
0x180049ce6  call    cs:__imp_CoTaskMemFree
0x180049cec  mov     rcx, [rbx]; pv
0x180049cef  call    cs:__imp_CoTaskMemFree
0x180049cf5  mov     rcx, rbx; void *
0x180049cf8  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180049cfd  inc     ebp
0x180049cff  cmp     ebp, [rdi+8]
0x180049d02  jl      short loc_180049CD8
0x180049d04  mov     rcx, rsi; lpCriticalSection
0x180049d07  mov     dword ptr [rdi+8], 0
0x180049d0e  call    cs:__imp_LeaveCriticalSection
0x180049d14  mov     rcx, rsi; lpCriticalSection
0x180049d17  call    cs:__imp_DeleteCriticalSection
0x180049d1d  mov     rcx, [rdi]
0x180049d20  add     rsp, 28h
0x180049d24  pop     rdi
0x180049d25  pop     rsi
0x180049d26  pop     rbp
0x180049d27  pop     rbx
0x180049d28  jmp     cs:__imp_free
```
