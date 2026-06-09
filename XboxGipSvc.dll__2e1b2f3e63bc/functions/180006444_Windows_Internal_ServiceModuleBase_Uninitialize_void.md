# Windows::Internal::ServiceModuleBase::Uninitialize(void)

- ea: `0x180006444`
- end: `0x18000653b`
- name: `?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ`
- size: `247`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800031fc`
- `0x180004480`
- `0x180006240`

## callees

- `0x180006444`
- `0x180006968`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000650c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000650c`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180006504`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180006504`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000651c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000651c`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800064b6`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800064b6`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Uninitialize(Windows::Internal::ServiceModuleBase *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  int v4; // eax
  void *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rsi
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), Windows::Internal::ServiceModuleBase *, GUID *, int, _QWORD))(*(_QWORD *)v2 + 24LL))(
      v2,
      Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk,
      this,
      &IID_IContextCallback,
      5,
      0);
    v3 = *((_QWORD *)this + 3);
    if ( v3 )
    {
      *((_QWORD *)this + 3) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
  if ( *((_BYTE *)this + 21) )
  {
    v4 = CoRegisterServerShutdownDelay(0, 0);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, v5, v6, (const char *)(unsigned int)v4);
    *((_BYTE *)this + 21) = 0;
  }
  if ( *((_BYTE *)this + 20) )
  {
    (*(void (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 24LL))(this);
    *((_BYTE *)this + 20) = 0;
  }
  if ( *((int *)this + 4) >= 0 )
  {
    v7 = *((_QWORD *)this + 1);
    if ( v7 )
    {
      LastError = GetLastError();
      CoDecrementMTAUsage(v7);
      SetLastError(LastError);
      *((_QWORD *)this + 1) = 0;
    }
    else
    {
      RoUninitialize();
    }
    *((_DWORD *)this + 4) = -2147467259;
  }
  return 0;
}

```

## disassembly

```asm
0x180006444  mov     [rsp+arg_0], rbx
0x180006449  mov     [rsp+arg_8], rsi
0x18000644e  push    rdi
0x18000644f  sub     rsp, 40h
0x180006453  mov     rdi, rcx
0x180006456  mov     rcx, [rcx+18h]
0x18000645a  test    rcx, rcx
0x18000645d  jz      short loc_1800064AC
0x18000645f  mov     rax, [rcx]
0x180006462  mov     [rsp+48h+var_20], 0
0x18000646b  mov     [rsp+48h+var_28], 5; int
0x180006473  lea     r9, IID_IContextCallback
0x18000647a  mov     r8, rdi
0x18000647d  lea     rdx, ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x180006484  mov     rax, [rax+18h]
0x180006488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648d  nop
0x18000648e  mov     rcx, [rdi+18h]
0x180006492  test    rcx, rcx
0x180006495  jz      short loc_1800064AC
0x180006497  mov     qword ptr [rdi+18h], 0
0x18000649f  mov     rax, [rcx]
0x1800064a2  mov     rax, [rax+10h]
0x1800064a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ab  nop
0x1800064ac  cmp     byte ptr [rdi+15h], 0
0x1800064b0  jz      short loc_1800064D1
0x1800064b2  xor     edx, edx
0x1800064b4  xor     ecx, ecx
0x1800064b6  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800064bc  test    eax, eax
0x1800064be  jns     short loc_1800064CD
0x1800064c0  mov     rcx, [rsp+48h]; this
0x1800064c5  mov     r9d, eax; char *
0x1800064c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800064cd  mov     byte ptr [rdi+15h], 0
0x1800064d1  cmp     byte ptr [rdi+14h], 0
0x1800064d5  jz      short loc_1800064EA
0x1800064d7  mov     rax, [rdi]
0x1800064da  mov     rcx, rdi
0x1800064dd  mov     rax, [rax+18h]
0x1800064e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e6  mov     byte ptr [rdi+14h], 0
0x1800064ea  cmp     dword ptr [rdi+10h], 0
0x1800064ee  jl      short loc_180006529
0x1800064f0  mov     rsi, [rdi+8]
0x1800064f4  test    rsi, rsi
0x1800064f7  jz      short loc_18000651C
0x1800064f9  call    cs:__imp_GetLastError
0x1800064ff  mov     ebx, eax
0x180006501  mov     rcx, rsi
0x180006504  call    cs:__imp_CoDecrementMTAUsage
0x18000650a  mov     ecx, ebx; dwErrCode
0x18000650c  call    cs:__imp_SetLastError
0x180006512  mov     qword ptr [rdi+8], 0
0x18000651a  jmp     short loc_180006522
0x18000651c  call    cs:__imp_RoUninitialize
0x180006522  mov     dword ptr [rdi+10h], 80004005h
0x180006529  xor     eax, eax
0x18000652b  mov     rbx, [rsp+48h+arg_0]
0x180006530  mov     rsi, [rsp+48h+arg_8]
0x180006535  add     rsp, 40h
0x180006539  pop     rdi
0x18000653a  retn
```
