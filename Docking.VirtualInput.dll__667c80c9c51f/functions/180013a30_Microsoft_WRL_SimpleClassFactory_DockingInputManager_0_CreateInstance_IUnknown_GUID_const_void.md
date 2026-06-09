# Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180013a30`
- end: `0x180013ada`
- name: `?CreateInstance@?$SimpleClassFactory@VDockingInputManager@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013ae0`

## callees

- `0x180004d54`
- `0x18000b810`
- `0x18000bf4c`
- `0x1800130c8`
- `0x1800139cc`
- `0x180013a30`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180013a63`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180013a63`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v5; // rax
  int v6; // [rsp+20h] [rbp-28h]
  unsigned int v7; // [rsp+28h] [rbp-20h]
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  else
  {
    Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v8);
    v5 = Microsoft::WRL::Details::Forward<std::nullptr_t>(v8);
    v6 = Microsoft::WRL::Details::MakeAndInitialize<DockingInputManager,IUnknown,>(v5);
    if ( v6 >= 0 )
    {
      v7 = Microsoft::WRL::ComPtr<IInspectable>::CopyTo(v8, a3, a4);
      Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(v8);
      return v7;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(v8);
      return (unsigned int)v6;
    }
  }
}

```

## disassembly

```asm
0x180013a30  mov     [rsp+arg_18], r9
0x180013a35  mov     [rsp+arg_10], r8
0x180013a3a  mov     [rsp+arg_8], rdx
0x180013a3f  mov     [rsp+arg_0], rcx
0x180013a44  sub     rsp, 48h
0x180013a48  mov     rax, [rsp+48h+arg_18]
0x180013a4d  mov     qword ptr [rax], 0
0x180013a54  cmp     [rsp+48h+arg_8], 0
0x180013a5a  jz      short loc_180013A70
0x180013a5c  xor     edx, edx
0x180013a5e  mov     ecx, 80040110h
0x180013a63  call    cs:__imp_RoOriginateError
0x180013a69  mov     eax, 80040110h
0x180013a6e  jmp     short loc_180013AD5
0x180013a70  lea     rcx, [rsp+48h+var_18]
0x180013a75  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180013a7a  lea     rcx, [rsp+48h+var_18]
0x180013a7f  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180013a84  mov     rcx, rax
0x180013a87  call    ??$MakeAndInitialize@VDockingInputManager@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DockingInputManager,IUnknown,>(IUnknown * *)
0x180013a8c  mov     [rsp+48h+var_28], eax
0x180013a90  cmp     [rsp+48h+var_28], 0
0x180013a95  jge     short loc_180013AAF
0x180013a97  mov     eax, [rsp+48h+var_28]
0x180013a9b  mov     [rsp+48h+var_24], eax
0x180013a9f  lea     rcx, [rsp+48h+var_18]
0x180013aa4  call    ??1?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(void)
0x180013aa9  mov     eax, [rsp+48h+var_24]
0x180013aad  jmp     short loc_180013AD5
0x180013aaf  mov     r8, [rsp+48h+arg_18]
0x180013ab4  mov     rdx, [rsp+48h+arg_10]
0x180013ab9  lea     rcx, [rsp+48h+var_18]
0x180013abe  call    ?CopyTo@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IInspectable>::CopyTo(_GUID const &,void * *)
0x180013ac3  mov     [rsp+48h+var_20], eax
0x180013ac7  lea     rcx, [rsp+48h+var_18]
0x180013acc  call    ??1?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(void)
0x180013ad1  mov     eax, [rsp+48h+var_20]
0x180013ad5  add     rsp, 48h
0x180013ad9  retn
```
