# CPenProcess::ShutdownWatchDogThread(void)

- ea: `0x18002d378`
- end: `0x18002d433`
- name: `?ShutdownWatchDogThread@CPenProcess@@AEAAXXZ`
- size: `187`
- prototype: `void __fastcall(CPenProcess *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180015660`
- `0x18002bfac`
- `0x18002d43c`

## callees

- `0x1800024c0`
- `0x180012dc0`
- `0x180015630`
- `0x18002d378`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d403`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d403`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d40f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d40f`

## pseudocode

```c
void __fastcall CPenProcess::ShutdownWatchDogThread(CPenProcess *this)
{
  __int64 v2; // rcx
  const WCHAR *v3; // r8
  __int64 v4; // r9
  void *v5; // rcx
  int v6; // [rsp+40h] [rbp+8h] BYREF
  const WCHAR *v7; // [rsp+48h] [rbp+10h] BYREF

  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v6 = *((_DWORD *)this + 271);
    v7 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v2,
      (int)byte_18003AFD1,
      (__int64)v3,
      v4,
      &v7,
      (__int64)&v6);
  }
  if ( *((_QWORD *)this + 141) )
  {
    v5 = (void *)*((_QWORD *)this + 142);
    if ( v5 )
    {
      SetEvent(v5);
      WaitForSingleObject(*((HANDLE *)this + 141), 0xFFFFFFFF);
    }
  }
  SH<void *,SH_HANDLE>::Reset((char *)this + 1128);
  SH<void *,SH_HANDLE>::Reset((char *)this + 1136);
}

```

## disassembly

```asm
0x18002d378  mov     [rsp+arg_10], rbx
0x18002d37d  push    rdi
0x18002d37e  sub     rsp, 30h
0x18002d382  mov     rax, [rcx]
0x18002d385  lea     r8, aUnknown; "(unknown)"
0x18002d38c  mov     rbx, rcx
0x18002d38f  test    rax, rax
0x18002d392  jz      short loc_18002D39B
0x18002d394  mov     r8, [rax+220h]
0x18002d39b  mov     eax, cs:dword_1800411A8
0x18002d3a1  cmp     eax, 5
0x18002d3a4  jbe     short loc_18002D3EA
0x18002d3a6  mov     edx, 4000000h
0x18002d3ab  lea     rcx, dword_1800411A8
0x18002d3b2  call    _tlgKeywordOn
0x18002d3b7  test    al, al
0x18002d3b9  jz      short loc_18002D3EA
0x18002d3bb  mov     eax, [rbx+43Ch]
0x18002d3c1  lea     rdx, byte_18003AFD1
0x18002d3c8  mov     [rsp+38h+arg_0], eax
0x18002d3cc  lea     rax, [rsp+38h+arg_0]
0x18002d3d1  mov     [rsp+38h+var_10], rax
0x18002d3d6  lea     rax, [rsp+38h+arg_8]
0x18002d3db  mov     [rsp+38h+var_18], rax
0x18002d3e0  mov     [rsp+38h+arg_8], r8
0x18002d3e5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002d3ea  lea     rdi, [rbx+468h]
0x18002d3f1  cmp     qword ptr [rdi], 0
0x18002d3f5  jz      short loc_18002D415
0x18002d3f7  mov     rcx, [rbx+470h]; hEvent
0x18002d3fe  test    rcx, rcx
0x18002d401  jz      short loc_18002D415
0x18002d403  call    cs:__imp_SetEvent
0x18002d409  mov     rcx, [rdi]; hHandle
0x18002d40c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002d40f  call    cs:__imp_WaitForSingleObject
0x18002d415  mov     rcx, rdi
0x18002d418  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002d41d  lea     rcx, [rbx+470h]
0x18002d424  mov     rbx, [rsp+38h+arg_10]
0x18002d429  add     rsp, 30h
0x18002d42d  pop     rdi
0x18002d42e  jmp     ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
```
