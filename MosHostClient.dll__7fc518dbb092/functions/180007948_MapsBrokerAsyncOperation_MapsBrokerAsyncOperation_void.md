# MapsBrokerAsyncOperation::~MapsBrokerAsyncOperation(void)

- ea: `0x180007948`
- end: `0x1800079eb`
- name: `??1MapsBrokerAsyncOperation@@UEAA@XZ`
- size: `163`
- prototype: `void __fastcall(MapsBrokerAsyncOperation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007a30`

## callees

- `0x180007158`
- `0x180007948`
- `0x180007ad0`
- `0x180007f30`
- `0x180007f90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800079ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800079ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800079c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800079c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079ba`

## string_xrefs

- `0x18000796e`: `onecoreuap\windows\maps\moshost\client\mapsbrokerasyncoperation.cpp`
- `0x180007993`: `onecoreuap\windows\maps\moshost\client\mapsbrokerasyncoperation.cpp`

## pseudocode

```c
void __fastcall MapsBrokerAsyncOperation::~MapsBrokerAsyncOperation(MapsBrokerAsyncOperation *this)
{
  int v2; // eax
  int v3; // eax
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &MapsBrokerAsyncOperation::`vftable';
  v2 = MapsBrokerAsyncOperation::Cancel(this, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\mapsbrokerasyncoperation.cpp",
      (const char *)(unsigned int)v2,
      v7);
  v3 = MapsBrokerAsyncOperation::WaitForCompletion(this);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\mapsbrokerasyncoperation.cpp",
      (const char *)(unsigned int)v3,
      v7);
  free(*((void **)this + 17));
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180007948  push    rbx; int
0x18000794a  sub     rsp, 20h
0x18000794e  mov     rbx, rcx
0x180007951  lea     rax, ??_7MapsBrokerAsyncOperation@@6B@; const MapsBrokerAsyncOperation::`vftable'
0x180007958  mov     [rcx], rax
0x18000795b  xor     edx, edx; bool
0x18000795d  call    ?Cancel@MapsBrokerAsyncOperation@@UEAAJ_N@Z; MapsBrokerAsyncOperation::Cancel(bool)
0x180007962  test    eax, eax
0x180007964  jns     short loc_18000797F
0x180007966  mov     rcx, [rsp+28h]; this
0x18000796b  mov     r9d, eax; char *
0x18000796e  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180007975  mov     edx, 10h; void *
0x18000797a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000797f  mov     rcx, rbx; this
0x180007982  call    ?WaitForCompletion@MapsBrokerAsyncOperation@@UEAAJXZ; MapsBrokerAsyncOperation::WaitForCompletion(void)
0x180007987  test    eax, eax
0x180007989  jns     short loc_1800079A4
0x18000798b  mov     rcx, [rsp+28h]; this
0x180007990  mov     r9d, eax; char *
0x180007993  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000799a  mov     edx, 11h; void *
0x18000799f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800079a4  mov     rcx, [rbx+88h]; Block
0x1800079ab  call    cs:__imp_free
0x1800079b1  mov     rcx, [rbx+58h]; hObject
0x1800079b5  test    rcx, rcx
0x1800079b8  jz      short loc_1800079C4
0x1800079ba  call    cs:__imp_CloseHandle
0x1800079c0  test    eax, eax
0x1800079c2  jz      short loc_1800079DB
0x1800079c4  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800079c8  call    cs:__imp_DeleteCriticalSection
0x1800079ce  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1800079d5  add     rsp, 20h
0x1800079d9  pop     rbx
0x1800079da  retn
0x1800079db  mov     rcx, [rsp+28h]; this
0x1800079e0  mov     edx, 0A0Bh; void *
0x1800079e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
