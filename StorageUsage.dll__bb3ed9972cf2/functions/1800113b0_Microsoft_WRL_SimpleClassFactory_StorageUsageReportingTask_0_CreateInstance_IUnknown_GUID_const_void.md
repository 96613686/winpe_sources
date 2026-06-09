# Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800113b0`
- end: `0x180011430`
- name: `?CreateInstance@?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000decc`
- `0x1800113b0`
- `0x180013ae4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800113da`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800113da`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 (__fastcall ***v8)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v8 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<StorageUsageReportingTask,IUnknown,>(&v8);
    if ( v6 >= 0 )
      v6 = (**v8)(v8, a3, a4);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800113b0  mov     [rsp+arg_0], rbx
0x1800113b5  mov     [rsp+arg_10], rsi
0x1800113ba  push    rdi
0x1800113bb  sub     rsp, 20h
0x1800113bf  mov     rdi, r9
0x1800113c2  mov     rsi, r8
0x1800113c5  mov     qword ptr [r9], 0
0x1800113cc  test    rdx, rdx
0x1800113cf  jz      short loc_1800113E2
0x1800113d1  xor     edx, edx
0x1800113d3  mov     ebx, 80040110h
0x1800113d8  mov     ecx, ebx
0x1800113da  call    cs:__imp_RoOriginateError
0x1800113e0  jmp     short loc_18001141E
0x1800113e2  mov     [rsp+28h+arg_8], 0
0x1800113eb  lea     rcx, [rsp+28h+arg_8]
0x1800113f0  call    ??$MakeAndInitialize@VStorageUsageReportingTask@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<StorageUsageReportingTask,IUnknown,>(IUnknown * *)
0x1800113f5  mov     ebx, eax
0x1800113f7  test    eax, eax
0x1800113f9  js      short loc_180011414
0x1800113fb  mov     rcx, [rsp+28h+arg_8]
0x180011400  mov     rax, [rcx]
0x180011403  mov     r8, rdi
0x180011406  mov     rdx, rsi
0x180011409  mov     rax, [rax]
0x18001140c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011411  nop
0x180011412  mov     ebx, eax
0x180011414  lea     rcx, [rsp+28h+arg_8]
0x180011419  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001141e  mov     eax, ebx
0x180011420  mov     rbx, [rsp+28h+arg_0]
0x180011425  mov     rsi, [rsp+28h+arg_10]
0x18001142a  add     rsp, 20h
0x18001142e  pop     rdi
0x18001142f  retn
```
