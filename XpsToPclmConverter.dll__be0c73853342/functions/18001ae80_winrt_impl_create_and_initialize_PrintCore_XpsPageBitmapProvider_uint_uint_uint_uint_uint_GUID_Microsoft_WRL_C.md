# winrt::impl::create_and_initialize<PrintCore::XpsPageBitmapProvider,uint &,uint &,uint &,uint &,uint &,_GUID &,Microsoft::WRL::ComPtr<IXpsOMPage> const &,IXpsRasterizationFactory2 * &,IXpsRasterizerNotificationCallback * &>(uint &,uint &,uint &,uint &,uint &,_GUID &,Microsoft::WRL::ComPtr<IXpsOMPage> const &,IXpsRasterizationFactory2 * &,IXpsRasterizerNotificationCallback * &)

- ea: `0x18001ae80`
- end: `0x18001af44`
- name: `??$create_and_initialize@VXpsPageBitmapProvider@PrintCore@@AEAIAEAIAEAIAEAIAEAIAEAU_GUID@@AEBV?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@AEAPEAUIXpsRasterizationFactory2@@AEAPEAUIXpsRasterizerNotificationCallback@@@impl@winrt@@YAPEAVXpsPageBitmapProvider@PrintCore@@AEAI0000AEAU_GUID@@AEBV?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@AEAPEAUIXpsRasterizationFactory2@@AEAPEAUIXpsRasterizerNotificationCallback@@@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b634`

## callees

- `0x180001f6c`
- `0x18000df0c`
- `0x18001afe4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::create_and_initialize<PrintCore::XpsPageBitmapProvider,unsigned int &,unsigned int &,unsigned int &,unsigned int &,unsigned int &,_GUID &,Microsoft::WRL::ComPtr<IXpsOMPage> const &,IXpsRasterizationFactory2 * &,IXpsRasterizerNotificationCallback * &>(
        int *a1,
        int *a2,
        int *a3,
        int *a4,
        unsigned int *a5,
        __int128 *a6,
        __int64 *a7,
        __int64 *a8,
        __int64 *a9)
{
  _QWORD *v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v17[2]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v18[4]; // [rsp+60h] [rbp-48h] BYREF

  v13 = operator new(0x78u);
  v17[1] = (__int64)v13;
  v14 = *a9;
  v15 = *a8;
  v17[0] = *a7;
  Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(v17);
  v18[0] = *a6;
  return winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::heap_implements<PrintCore::XpsPageBitmapProvider>(
           v13,
           *a1,
           *a2,
           *a3,
           *a4,
           *a5,
           v18,
           v17,
           v15,
           v14);
}

```

## disassembly

```asm
0x18001ae80  push    rbx
0x18001ae82  push    rbp
0x18001ae83  push    rsi
0x18001ae84  push    rdi
0x18001ae85  push    r12
0x18001ae87  push    r14
0x18001ae89  push    r15
0x18001ae8b  sub     rsp, 70h
0x18001ae8f  mov     r14, r9
0x18001ae92  mov     r15, r8
0x18001ae95  mov     rbp, rdx
0x18001ae98  mov     r12, rcx
0x18001ae9b  mov     ecx, 78h ; 'x'; Size
0x18001aea0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aea5  mov     rsi, rax
0x18001aea8  mov     [rsp+0A8h+var_50], rax
0x18001aead  mov     r10, [rsp+0A8h+arg_40]
0x18001aeb5  mov     rdi, [r10]
0x18001aeb8  mov     r10, [rsp+0A8h+arg_38]
0x18001aec0  mov     rbx, [r10]
0x18001aec3  mov     rdx, [rsp+0A8h+arg_30]
0x18001aecb  mov     rcx, [rdx]
0x18001aece  mov     [rsp+0A8h+var_58], rcx
0x18001aed3  lea     rcx, [rsp+0A8h+var_58]
0x18001aed8  call    ?InternalAddRef@?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(void)
0x18001aedd  mov     rax, [rsp+0A8h+arg_28]
0x18001aee5  movups  xmm0, xmmword ptr [rax]
0x18001aee8  movdqu  [rsp+0A8h+var_48], xmm0
0x18001aeee  mov     [rsp+0A8h+var_60], rdi
0x18001aef3  mov     [rsp+0A8h+var_68], rbx
0x18001aef8  lea     rax, [rsp+0A8h+var_58]
0x18001aefd  mov     [rsp+0A8h+var_70], rax
0x18001af02  lea     rax, [rsp+0A8h+var_48]
0x18001af07  mov     [rsp+0A8h+var_78], rax
0x18001af0c  mov     rax, [rsp+0A8h+arg_20]
0x18001af14  mov     ecx, [rax]
0x18001af16  mov     [rsp+0A8h+var_80], ecx
0x18001af1a  mov     eax, [r14]
0x18001af1d  mov     [rsp+0A8h+var_88], eax
0x18001af21  mov     r9d, [r15]
0x18001af24  mov     r8d, [rbp+0]
0x18001af28  mov     edx, [r12]
0x18001af2c  mov     rcx, rsi
0x18001af2f  call    ??0?$heap_implements@VXpsPageBitmapProvider@PrintCore@@@impl@winrt@@QEAA@IIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@@Z; winrt::impl::heap_implements<PrintCore::XpsPageBitmapProvider>::heap_implements<PrintCore::XpsPageBitmapProvider>(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *)
0x18001af34  nop
0x18001af35  add     rsp, 70h
0x18001af39  pop     r15
0x18001af3b  pop     r14
0x18001af3d  pop     r12
0x18001af3f  pop     rdi
0x18001af40  pop     rsi
0x18001af41  pop     rbp
0x18001af42  pop     rbx
0x18001af43  retn
```
