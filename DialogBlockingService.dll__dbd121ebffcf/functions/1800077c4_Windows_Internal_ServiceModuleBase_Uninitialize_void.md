# Windows::Internal::ServiceModuleBase::Uninitialize(void)

- ea: `0x1800077c4`
- end: `0x1800078bb`
- name: `?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ`
- size: `247`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800023c8`
- `0x180003e90`
- `0x180007fa0`

## callees

- `0x1800077c4`
- `0x180007d38`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180007884`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180007884`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000788c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000788c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007879`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000789c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000789c`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180007836`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180007836`

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
0x1800077c4  mov     [rsp+arg_0], rbx
0x1800077c9  mov     [rsp+arg_8], rsi
0x1800077ce  push    rdi
0x1800077cf  sub     rsp, 40h
0x1800077d3  mov     rdi, rcx
0x1800077d6  mov     rcx, [rcx+18h]
0x1800077da  test    rcx, rcx
0x1800077dd  jz      short loc_18000782C
0x1800077df  mov     rax, [rcx]
0x1800077e2  mov     [rsp+48h+var_20], 0
0x1800077eb  mov     [rsp+48h+var_28], 5; int
0x1800077f3  lea     r9, IID_IContextCallback
0x1800077fa  mov     r8, rdi
0x1800077fd  lea     rdx, ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x180007804  mov     rax, [rax+18h]
0x180007808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000780d  nop
0x18000780e  mov     rcx, [rdi+18h]
0x180007812  test    rcx, rcx
0x180007815  jz      short loc_18000782C
0x180007817  mov     qword ptr [rdi+18h], 0
0x18000781f  mov     rax, [rcx]
0x180007822  mov     rax, [rax+10h]
0x180007826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782b  nop
0x18000782c  cmp     byte ptr [rdi+15h], 0
0x180007830  jz      short loc_180007851
0x180007832  xor     edx, edx
0x180007834  xor     ecx, ecx
0x180007836  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000783c  test    eax, eax
0x18000783e  jns     short loc_18000784D
0x180007840  mov     rcx, [rsp+48h]; this
0x180007845  mov     r9d, eax; char *
0x180007848  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000784d  mov     byte ptr [rdi+15h], 0
0x180007851  cmp     byte ptr [rdi+14h], 0
0x180007855  jz      short loc_18000786A
0x180007857  mov     rax, [rdi]
0x18000785a  mov     rcx, rdi
0x18000785d  mov     rax, [rax+18h]
0x180007861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007866  mov     byte ptr [rdi+14h], 0
0x18000786a  cmp     dword ptr [rdi+10h], 0
0x18000786e  jl      short loc_1800078A9
0x180007870  mov     rsi, [rdi+8]
0x180007874  test    rsi, rsi
0x180007877  jz      short loc_18000789C
0x180007879  call    cs:__imp_GetLastError
0x18000787f  mov     ebx, eax
0x180007881  mov     rcx, rsi
0x180007884  call    cs:__imp_CoDecrementMTAUsage
0x18000788a  mov     ecx, ebx; dwErrCode
0x18000788c  call    cs:__imp_SetLastError
0x180007892  mov     qword ptr [rdi+8], 0
0x18000789a  jmp     short loc_1800078A2
0x18000789c  call    cs:__imp_RoUninitialize
0x1800078a2  mov     dword ptr [rdi+10h], 80004005h
0x1800078a9  xor     eax, eax
0x1800078ab  mov     rbx, [rsp+48h+arg_0]
0x1800078b0  mov     rsi, [rsp+48h+arg_8]
0x1800078b5  add     rsp, 40h
0x1800078b9  pop     rdi
0x1800078ba  retn
```
