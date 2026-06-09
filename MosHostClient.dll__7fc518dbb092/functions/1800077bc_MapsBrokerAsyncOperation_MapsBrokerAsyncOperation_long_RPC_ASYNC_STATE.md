# MapsBrokerAsyncOperation::MapsBrokerAsyncOperation(long (*)(_RPC_ASYNC_STATE *))

- ea: `0x1800077bc`
- end: `0x1800078f8`
- name: `??0MapsBrokerAsyncOperation@@QEAA@P6AJPEAU_RPC_ASYNC_STATE@@@Z@Z`
- size: `316`
- prototype: `MapsBrokerAsyncOperation *__fastcall(MapsBrokerAsyncOperation *__hidden this, int (*)(struct _RPC_ASYNC_STATE *))`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007fc0`

## callees

- `0x180007158`
- `0x1800077bc`
- `0x180007aa0`
- `0x180007b98`
- `0x180007f0c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007868`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007884`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007890`

## pseudocode

```c
MapsBrokerAsyncOperation *__fastcall MapsBrokerAsyncOperation::MapsBrokerAsyncOperation(
        MapsBrokerAsyncOperation *this,
        int (*a2)(struct _RPC_ASYNC_STATE *))
{
  int v4; // eax
  void **v5; // rdi
  void *v6; // rdx
  HANDLE Event; // rbp
  unsigned int v8; // r8d
  const char *v9; // r9
  void *v10; // rsi
  DWORD LastError; // r14d
  unsigned int v12; // r8d
  const char *v13; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &MapsBrokerAsyncOperation::`vftable';
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  v4 = ATL::CComCriticalSection::Init((MapsBrokerAsyncOperation *)((char *)this + 16));
  if ( v4 < 0 )
    ATL::AtlThrowImpl(v4);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = a2;
  *((_QWORD *)this + 10) = 0;
  v5 = (void **)((char *)this + 88);
  *((_QWORD *)this + 11) = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v6, v8, v9);
  GetLastError();
  v10 = *v5;
  if ( *v5 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
    SetLastError(LastError);
  }
  *v5 = Event;
  *((_DWORD *)this + 24) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  return this;
}

```

## disassembly

```asm
0x1800077bc  mov     [rsp+arg_8], rbx
0x1800077c1  mov     [rsp+arg_18], rbp
0x1800077c6  mov     [rsp+arg_0], rcx
0x1800077cb  push    rsi
0x1800077cc  push    rdi
0x1800077cd  push    r14
0x1800077cf  sub     rsp, 20h
0x1800077d3  mov     rdi, rdx
0x1800077d6  mov     rbx, rcx
0x1800077d9  mov     esi, 1
0x1800077de  mov     [rcx+0Ch], esi
0x1800077e1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMapsBrokerAsyncOperation@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::`vftable'
0x1800077e8  mov     [rcx], rax
0x1800077eb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800077f2  test    rcx, rcx
0x1800077f5  jz      short loc_180007804
0x1800077f7  mov     rax, [rcx]
0x1800077fa  mov     rax, [rax+8]
0x1800077fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007803  nop
0x180007804  lea     rax, ??_7MapsBrokerAsyncOperation@@6B@; const MapsBrokerAsyncOperation::`vftable'
0x18000780b  mov     [rbx], rax
0x18000780e  lea     rcx, [rbx+10h]; this
0x180007812  xorps   xmm0, xmm0
0x180007815  xor     eax, eax
0x180007817  movups  xmmword ptr [rcx], xmm0
0x18000781a  movups  xmmword ptr [rcx+10h], xmm0
0x18000781e  mov     [rcx+20h], rax
0x180007822  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180007827  test    eax, eax
0x180007829  js      loc_1800078F0
0x18000782f  mov     qword ptr [rbx+38h], 0
0x180007837  mov     qword ptr [rbx+40h], 0
0x18000783f  mov     [rbx+48h], rdi
0x180007843  mov     qword ptr [rbx+50h], 0
0x18000784b  lea     rdi, [rbx+58h]
0x18000784f  mov     [rsp+38h+arg_10], rdi
0x180007854  mov     qword ptr [rdi], 0
0x18000785b  mov     r9d, 1F0003h; dwDesiredAccess
0x180007861  mov     r8d, esi; dwFlags
0x180007864  xor     edx, edx; lpName
0x180007866  xor     ecx, ecx; lpEventAttributes
0x180007868  call    cs:__imp_CreateEventExW
0x18000786e  mov     rbp, rax
0x180007871  test    rax, rax
0x180007874  jz      short loc_1800078E5
0x180007876  call    cs:__imp_GetLastError
0x18000787c  mov     rsi, [rdi]
0x18000787f  test    rsi, rsi
0x180007882  jz      short loc_1800078A8
0x180007884  call    cs:__imp_GetLastError
0x18000788a  mov     r14d, eax
0x18000788d  mov     rcx, rsi; hObject
0x180007890  call    cs:__imp_CloseHandle
0x180007896  mov     rcx, [rsp+38h]; this
0x18000789b  test    eax, eax
0x18000789d  jz      short loc_1800078DA
0x18000789f  mov     ecx, r14d; dwErrCode
0x1800078a2  call    cs:__imp_SetLastError
0x1800078a8  mov     [rdi], rbp
0x1800078ab  mov     dword ptr [rbx+60h], 0
0x1800078b2  xorps   xmm0, xmm0
0x1800078b5  movups  xmmword ptr [rbx+68h], xmm0
0x1800078b9  movups  xmmword ptr [rbx+78h], xmm0
0x1800078bd  movups  xmmword ptr [rbx+88h], xmm0
0x1800078c4  mov     rax, rbx
0x1800078c7  mov     rbx, [rsp+38h+arg_8]
0x1800078cc  mov     rbp, [rsp+38h+arg_18]
0x1800078d1  add     rsp, 20h
0x1800078d5  pop     r14
0x1800078d7  pop     rdi
0x1800078d8  pop     rsi
0x1800078d9  retn
0x1800078da  mov     edx, 0A0Bh; void *
0x1800078df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800078e5  mov     rcx, [rsp+38h]; this
0x1800078ea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800078f0  mov     ecx, eax; int
0x1800078f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
