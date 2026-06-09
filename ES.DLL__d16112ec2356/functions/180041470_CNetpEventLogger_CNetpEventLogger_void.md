# CNetpEventLogger::~CNetpEventLogger(void)

- ea: `0x180041470`
- end: `0x1800415a8`
- name: `??1CNetpEventLogger@@AEAA@XZ`
- size: `312`
- prototype: `void __fastcall(CNetpEventLogger *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800417d0`

## callees

- `0x180041470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041525`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041525`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004151c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004151c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800414ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800414ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004150a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004152e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004150a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004152e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800414c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800414c5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180041497`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180041497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004155c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004158a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004155c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004158a`

## pseudocode

```c
void __fastcall CNetpEventLogger::~CNetpEventLogger(CNetpEventLogger *this)
{
  void *v2; // rcx
  void *v3; // rcx
  HKEY v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  _QWORD *p_Type; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rdx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx

  *(_QWORD *)this = &CNetpEventLogger::`vftable';
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    UnregisterWaitEx(v2, 0);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 5) = 0;
  }
  v4 = (HKEY)*((_QWORD *)this + 7);
  if ( v4 )
  {
    RegCloseKey(v4);
    *((_QWORD *)this + 7) = 0;
  }
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 4));
    v6 = v5 + 1;
    while ( 1 )
    {
      p_Type = &v6->DebugInfo->Type;
      if ( (struct _RTL_CRITICAL_SECTION *)v6->DebugInfo == v6 )
        break;
      v8 = *p_Type;
      if ( *(_QWORD **)(*p_Type + 8LL) != p_Type || (v9 = (_QWORD *)p_Type[1], (_QWORD *)*v9 != p_Type) )
        __fastfail(3u);
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      LocalFree(p_Type);
    }
    LeaveCriticalSection(v5);
    DeleteCriticalSection(v5);
    LocalFree(v5);
    *((_QWORD *)this + 4) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 8);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 8) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 9);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)this + 9) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 10);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)this + 10) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 11);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)this + 11) = 0;
  }
}

```

## disassembly

```asm
0x180041470  mov     [rsp+arg_0], rbx
0x180041475  mov     [rsp+arg_8], rsi
0x18004147a  push    rdi
0x18004147b  sub     rsp, 20h
0x18004147f  mov     rbx, rcx
0x180041482  lea     rax, ??_7CNetpEventLogger@@6B@; const CNetpEventLogger::`vftable'
0x180041489  mov     [rcx], rax
0x18004148c  mov     rcx, [rcx+30h]; WaitHandle
0x180041490  test    rcx, rcx
0x180041493  jz      short loc_1800414A5
0x180041495  xor     edx, edx; CompletionEvent
0x180041497  call    cs:__imp_UnregisterWaitEx
0x18004149d  mov     qword ptr [rbx+30h], 0
0x1800414a5  mov     rcx, [rbx+28h]; hObject
0x1800414a9  test    rcx, rcx
0x1800414ac  jz      short loc_1800414BC
0x1800414ae  call    cs:__imp_CloseHandle
0x1800414b4  mov     qword ptr [rbx+28h], 0
0x1800414bc  mov     rcx, [rbx+38h]; hKey
0x1800414c0  test    rcx, rcx
0x1800414c3  jz      short loc_1800414D3
0x1800414c5  call    cs:__imp_RegCloseKey
0x1800414cb  mov     qword ptr [rbx+38h], 0
0x1800414d3  mov     rdi, [rbx+20h]
0x1800414d7  test    rdi, rdi
0x1800414da  jz      short loc_18004153C
0x1800414dc  mov     rcx, rdi; lpCriticalSection
0x1800414df  call    cs:__imp_EnterCriticalSection
0x1800414e5  lea     rsi, [rdi+28h]
0x1800414e9  mov     rcx, [rsi]; hMem
0x1800414ec  cmp     rcx, rsi
0x1800414ef  jz      short loc_180041519
0x1800414f1  mov     rax, [rcx]
0x1800414f4  cmp     [rax+8], rcx
0x1800414f8  jnz     short loc_180041512
0x1800414fa  mov     rdx, [rcx+8]
0x1800414fe  cmp     [rdx], rcx
0x180041501  jnz     short loc_180041512
0x180041503  mov     [rdx], rax
0x180041506  mov     [rax+8], rdx
0x18004150a  call    cs:__imp_LocalFree
0x180041510  jmp     short loc_1800414E9
0x180041512  mov     ecx, 3
0x180041517  int     29h; Win8: RtlFailFast(ecx)
0x180041519  mov     rcx, rdi; lpCriticalSection
0x18004151c  call    cs:__imp_LeaveCriticalSection
0x180041522  mov     rcx, rdi; lpCriticalSection
0x180041525  call    cs:__imp_DeleteCriticalSection
0x18004152b  mov     rcx, rdi; hMem
0x18004152e  call    cs:__imp_LocalFree
0x180041534  mov     qword ptr [rbx+20h], 0
0x18004153c  mov     rcx, [rbx+40h]; pv
0x180041540  test    rcx, rcx
0x180041543  jz      short loc_180041553
0x180041545  call    cs:__imp_CoTaskMemFree
0x18004154b  mov     qword ptr [rbx+40h], 0
0x180041553  mov     rcx, [rbx+48h]; pv
0x180041557  test    rcx, rcx
0x18004155a  jz      short loc_18004156A
0x18004155c  call    cs:__imp_CoTaskMemFree
0x180041562  mov     qword ptr [rbx+48h], 0
0x18004156a  mov     rcx, [rbx+50h]; pv
0x18004156e  test    rcx, rcx
0x180041571  jz      short loc_180041581
0x180041573  call    cs:__imp_CoTaskMemFree
0x180041579  mov     qword ptr [rbx+50h], 0
0x180041581  mov     rcx, [rbx+58h]; pv
0x180041585  test    rcx, rcx
0x180041588  jz      short loc_180041598
0x18004158a  call    cs:__imp_CoTaskMemFree
0x180041590  mov     qword ptr [rbx+58h], 0
0x180041598  mov     rbx, [rsp+28h+arg_0]
0x18004159d  mov     rsi, [rsp+28h+arg_8]
0x1800415a2  add     rsp, 20h
0x1800415a6  pop     rdi
0x1800415a7  retn
```
