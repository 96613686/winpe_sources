# PrintCore::CreateXpsBitmapProvider(uint,uint,uint,uint,uint,_GUID,Microsoft::WRL::ComPtr<IXpsOMPage>,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *,IPageBitmapProvider * *)

- ea: `0x18001b634`
- end: `0x18001b716`
- name: `?CreateXpsBitmapProvider@PrintCore@@YAJIIIIIU_GUID@@V?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@PEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@PEAPEAUIPageBitmapProvider@@@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000da7c`

## callees

- `0x18001ae80`
- `0x18001b634`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PrintCore::CreateXpsBitmapProvider(
        unsigned int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int128 *a6,
        __int64 *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  __int64 *v10; // rbx
  _QWORD *v11; // rdi
  _QWORD *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  __int64 v15; // rcx
  __int64 v17; // rcx
  unsigned int v18; // [rsp+50h] [rbp-58h] BYREF
  int v19; // [rsp+58h] [rbp-50h] BYREF
  int v20[4]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v21; // [rsp+70h] [rbp-38h] BYREF
  __int64 v22; // [rsp+78h] [rbp-30h] BYREF
  __int64 *v23; // [rsp+80h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v25; // [rsp+C8h] [rbp+20h] BYREF

  v25 = a4;
  try
  {
    v18 = a1;
    v20[0] = a2;
    v19 = a3;
    v10 = a7;
    v23 = a7;
    v22 = a8;
    v21 = a9;
    v11 = a10;
    *a10 = 0;
    v12 = winrt::impl::create_and_initialize<PrintCore::XpsPageBitmapProvider,unsigned int &,unsigned int &,unsigned int &,unsigned int &,unsigned int &,_GUID &,Microsoft::WRL::ComPtr<IXpsOMPage> const &,IXpsRasterizationFactory2 * &,IXpsRasterizerNotificationCallback * &>(
            (int *)&v18,
            v20,
            &v19,
            &v25,
            (unsigned int *)&a5,
            a6,
            v10,
            &v22,
            &v21);
  }
  catch ( ... )
  {
    v18 = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x89, v13, v14);
    v17 = *v23;
    if ( *v23 )
    {
      *v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v18;
  }
  *v11 = v12;
  v15 = *v10;
  if ( *v10 )
  {
    *v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b634  mov     r11, rsp
0x18001b637  mov     [r11+20h], r9d
0x18001b63b  push    rbx
0x18001b63c  push    rdi
0x18001b63d  sub     rsp, 98h
0x18001b644  mov     [rsp+0A8h+var_58], ecx
0x18001b648  mov     [rsp+0A8h+var_48], edx
0x18001b64c  mov     [r11-50h], r8d
0x18001b650  mov     rbx, [rsp+0A8h+arg_30]
0x18001b658  mov     [r11-28h], rbx
0x18001b65c  mov     rax, [rsp+0A8h+arg_38]
0x18001b664  mov     [r11-30h], rax
0x18001b668  mov     rax, [rsp+0A8h+arg_40]
0x18001b670  mov     [r11-38h], rax
0x18001b674  mov     rdi, [rsp+0A8h+arg_48]
0x18001b67c  mov     qword ptr [rdi], 0
0x18001b683  lea     rax, [r11-38h]
0x18001b687  mov     [r11-68h], rax
0x18001b68b  lea     rax, [r11-30h]
0x18001b68f  mov     [r11-70h], rax
0x18001b693  mov     [r11-78h], rbx
0x18001b697  mov     rax, [rsp+0A8h+arg_28]
0x18001b69f  mov     [r11-80h], rax
0x18001b6a3  lea     rax, [r11+28h]
0x18001b6a7  mov     [rsp+0A8h+var_88], rax
0x18001b6ac  lea     r9, [r11+20h]
0x18001b6b0  lea     r8, [r11-50h]
0x18001b6b4  lea     rdx, [r11-48h]
0x18001b6b8  lea     rcx, [r11-58h]
0x18001b6bc  call    ??$create_and_initialize@VXpsPageBitmapProvider@PrintCore@@AEAIAEAIAEAIAEAIAEAIAEAU_GUID@@AEBV?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@AEAPEAUIXpsRasterizationFactory2@@AEAPEAUIXpsRasterizerNotificationCallback@@@impl@winrt@@YAPEAVXpsPageBitmapProvider@PrintCore@@AEAI0000AEAU_GUID@@AEBV?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@AEAPEAUIXpsRasterizationFactory2@@AEAPEAUIXpsRasterizerNotificationCallback@@@Z; winrt::impl::create_and_initialize<PrintCore::XpsPageBitmapProvider,uint &,uint &,uint &,uint &,uint &,_GUID &,Microsoft::WRL::ComPtr<IXpsOMPage> const &,IXpsRasterizationFactory2 * &,IXpsRasterizerNotificationCallback * &>(uint &,uint &,uint &,uint &,uint &,_GUID &,Microsoft::WRL::ComPtr<IXpsOMPage> const &,IXpsRasterizationFactory2 * &,IXpsRasterizerNotificationCallback * &)
0x18001b6c1  mov     [rdi], rax
0x18001b6c4  mov     rcx, [rbx]
0x18001b6c7  test    rcx, rcx
0x18001b6ca  jz      short loc_18001B6E0
0x18001b6cc  mov     qword ptr [rbx], 0
0x18001b6d3  mov     rax, [rcx]
0x18001b6d6  mov     rax, [rax+10h]
0x18001b6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6df  nop
0x18001b6e0  xor     eax, eax
0x18001b6e2  jmp     short loc_18001B70C
0x18001b6e4  mov     rax, [rsp+0A8h+var_28]
0x18001b6ec  mov     rcx, [rax]
0x18001b6ef  test    rcx, rcx
0x18001b6f2  jz      short loc_18001B708
0x18001b6f4  mov     qword ptr [rax], 0
0x18001b6fb  mov     rax, [rcx]
0x18001b6fe  mov     rax, [rax+10h]
0x18001b702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b707  nop
0x18001b708  mov     eax, [rsp+0A8h+var_58]
0x18001b70c  add     rsp, 98h
0x18001b713  pop     rdi
0x18001b714  pop     rbx
0x18001b715  retn
```
