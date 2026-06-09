# CAxInstaller::Initialize2(HWND__ *,ulong,ushort *,ushort *,ushort *,ushort *,ushort * *,IUnknown * *)

- ea: `0x180006a20`
- end: `0x180006ae4`
- name: `?Initialize2@CAxInstaller@@UEAAJPEAUHWND__@@KPEAG111PEAPEAGPEAPEAUIUnknown@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CAxInstaller *__hidden this, HWND, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002c00`
- `0x180005cc0`
- `0x180005de0`
- `0x180006a20`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CAxInstaller::Initialize2(
        CAxInstaller *this,
        HWND a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 **a8,
        struct IUnknown **a9)
{
  unsigned int v13; // ebx
  _BYTE v15[56]; // [rsp+50h] [rbp-38h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v15,
    (char *)this + 592);
  if ( *((_DWORD *)this + 176) )
  {
    v13 = -2147024891;
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v15);
  }
  else
  {
    *((_DWORD *)this + 176) = 1;
    ATL::CComBSTR::operator=((BSTR *)this + 80, a7);
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v15);
    return (*(unsigned int (__fastcall **)(CAxInstaller *, HWND, _QWORD, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, struct IUnknown **))(*(_QWORD *)this + 24LL))(
             this,
             a2,
             a3,
             a4,
             a5,
             a6,
             a8,
             a9);
  }
  return v13;
}

```

## disassembly

```asm
0x180006a20  push    rbx
0x180006a22  push    rbp
0x180006a23  push    rsi
0x180006a24  push    rdi
0x180006a25  sub     rsp, 68h
0x180006a29  mov     rbp, rdx
0x180006a2c  mov     rbx, rcx
0x180006a2f  lea     rdx, [rcx+250h]
0x180006a36  mov     rdi, r9
0x180006a39  lea     rcx, [rsp+88h+var_38]
0x180006a3e  mov     esi, r8d
0x180006a41  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180006a46  cmp     dword ptr [rbx+2C0h], 0
0x180006a4d  jz      short loc_180006A60
0x180006a4f  lea     rcx, [rsp+88h+var_38]
0x180006a54  mov     ebx, 80070005h
0x180006a59  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x180006a5e  jmp     short loc_180006AD9
0x180006a60  mov     rdx, [rsp+88h+arg_30]
0x180006a68  lea     rcx, [rbx+280h]
0x180006a6f  mov     dword ptr [rbx+2C0h], 1
0x180006a79  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180006a7e  lea     rcx, [rsp+88h+var_38]
0x180006a83  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x180006a88  mov     rax, [rbx]
0x180006a8b  mov     r9, rdi
0x180006a8e  mov     r8d, esi
0x180006a91  mov     rdx, rbp
0x180006a94  mov     rcx, rbx
0x180006a97  mov     r10, [rax+18h]
0x180006a9b  mov     rax, [rsp+88h+arg_40]
0x180006aa3  mov     [rsp+88h+var_50], rax
0x180006aa8  mov     rax, [rsp+88h+arg_38]
0x180006ab0  mov     [rsp+88h+var_58], rax
0x180006ab5  mov     rax, [rsp+88h+arg_28]
0x180006abd  mov     [rsp+88h+var_60], rax
0x180006ac2  mov     rax, [rsp+88h+arg_20]
0x180006aca  mov     [rsp+88h+var_68], rax
0x180006acf  mov     rax, r10
0x180006ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad7  mov     ebx, eax
0x180006ad9  mov     eax, ebx
0x180006adb  add     rsp, 68h
0x180006adf  pop     rdi
0x180006ae0  pop     rsi
0x180006ae1  pop     rbp
0x180006ae2  pop     rbx
0x180006ae3  retn
```
