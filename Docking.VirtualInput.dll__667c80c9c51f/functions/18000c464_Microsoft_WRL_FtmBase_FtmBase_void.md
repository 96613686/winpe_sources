# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000c464`
- end: `0x18000c508`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c354`

## callees

- `0x180004d54`
- `0x18000b3d4`
- `0x18000bf4c`
- `0x18000bf94`
- `0x18000c464`
- `0x18000cd68`
- `0x18000cdf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000c4be`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000c4be`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 v1; // rax
  LPUNKNOWN *v2; // rax
  _QWORD *v3; // rax
  _BYTE v5[8]; // [rsp+20h] [rbp-28h] BYREF
  char *v6; // [rsp+28h] [rbp-20h]
  _BYTE v7[8]; // [rsp+30h] [rbp-18h] BYREF
  _BYTE v8[16]; // [rsp+38h] [rbp-10h] BYREF

  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal>>::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal>>(this);
  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>((char *)this + 24);
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v5);
  v1 = Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(v5, v7);
  v2 = (LPUNKNOWN *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>::operator IUnknown * *(v1);
  if ( CoCreateFreeThreadedMarshaler(0, v2) >= 0 )
  {
    v6 = (char *)this + 24;
    v3 = (_QWORD *)Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
                     (char *)this + 24,
                     v8);
    Microsoft::WRL::ComPtr<IUnknown>::As<IMarshal>(v5, *v3);
  }
  Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(v5);
  return this;
}

```

## disassembly

```asm
0x18000c464  mov     [rsp+arg_0], rcx
0x18000c469  sub     rsp, 48h
0x18000c46d  mov     rcx, [rsp+48h+arg_0]
0x18000c472  call    ??0?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$CloakedIid@UIMarshal@@@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal>>::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal>>(void)
0x18000c477  mov     rax, [rsp+48h+arg_0]
0x18000c47c  lea     rcx, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000c483  mov     [rax], rcx
0x18000c486  mov     rax, [rsp+48h+arg_0]
0x18000c48b  add     rax, 18h
0x18000c48f  mov     rcx, rax
0x18000c492  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x18000c497  lea     rcx, [rsp+48h+var_28]
0x18000c49c  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x18000c4a1  nop
0x18000c4a2  lea     rdx, [rsp+48h+var_18]
0x18000c4a7  lea     rcx, [rsp+48h+var_28]
0x18000c4ac  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x18000c4b1  mov     rcx, rax
0x18000c4b4  call    ??B?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAPEAUIUnknown@@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>::operator IUnknown * *(void)
0x18000c4b9  mov     rdx, rax; ppunkMarshal
0x18000c4bc  xor     ecx, ecx; punkOuter
0x18000c4be  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000c4c4  test    eax, eax
0x18000c4c6  jl      short loc_18000C4F3
0x18000c4c8  mov     rax, [rsp+48h+arg_0]
0x18000c4cd  add     rax, 18h
0x18000c4d1  mov     [rsp+48h+var_20], rax
0x18000c4d6  lea     rdx, [rsp+48h+var_10]
0x18000c4db  mov     rcx, [rsp+48h+var_20]
0x18000c4e0  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x18000c4e5  mov     rdx, [rax]
0x18000c4e8  lea     rcx, [rsp+48h+var_28]
0x18000c4ed  call    ??$As@UIMarshal@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMarshal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<IMarshal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMarshal>>)
0x18000c4f2  nop
0x18000c4f3  lea     rcx, [rsp+48h+var_28]
0x18000c4f8  call    ??1?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IUnknown>::~ComPtr<IUnknown>(void)
0x18000c4fd  nop
0x18000c4fe  mov     rax, [rsp+48h+arg_0]
0x18000c503  add     rsp, 48h
0x18000c507  retn
```
