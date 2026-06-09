# CInkRoot::_CreateCrossDeviceVisual(IUnknown *,BranchType,IDCompositionVisual * *,IDCompositionTarget * *)

- ea: `0x1800e16a8`
- end: `0x1800e1877`
- name: `?_CreateCrossDeviceVisual@CInkRoot@@AEAAJPEAUIUnknown@@W4BranchType@@PEAPEAUIDCompositionVisual@@PEAPEAUIDCompositionTarget@@@Z`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800e1dd4`

## callees

- `0x1800101bc`
- `0x180019248`
- `0x180089558`
- `0x180089648`
- `0x1800de4a0`
- `0x1800de4f0`
- `0x1800e16a8`
- `0x1800fb010`

## import_xrefs

- `dcomp!__imp_DCompositionCreateTargetForHandle` at `0x1800e17cf`
- `dcomp!__imp_DCompositionCreateTargetForHandle` at `0x1800e17cf`
- `dcomp!__imp_DCompositionCreateCrossDeviceVisual` at `0x1800e16f5`
- `dcomp!__imp_DCompositionCreateCrossDeviceVisual` at `0x1800e16f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CInkRoot::_CreateCrossDeviceVisual(__int64 a1, __int64 a2, int a3, _QWORD *a4, __int64 a5)
{
  int v8; // eax
  int TargetForHandle; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rcx
  int v13; // esi
  int v14; // esi
  __int64 v15; // rdx
  __int64 v17; // [rsp+20h] [rbp-38h] BYREF
  __int64 v18; // [rsp+28h] [rbp-30h] BYREF
  __int64 v19; // [rsp+30h] [rbp-28h] BYREF
  __int64 v20; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v22; // [rsp+98h] [rbp+40h] BYREF

  v18 = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v18);
  v20 = 0;
  v8 = Microsoft::WRL::ComPtr<IUnknown>::As<IDCompositionVisual>(&v18, &v20);
  TargetForHandle = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147467262 )
      goto LABEL_26;
    v19 = 0;
    TargetForHandle = Microsoft::WRL::ComPtr<Windows::UI::Composition::IContainerVisual>::As<Windows::UI::Composition::ICompositionObject>(
                        &v18,
                        &v19);
    if ( TargetForHandle >= 0 )
    {
      v17 = 0;
      v10 = v19;
      v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      TargetForHandle = v11(v10, &v17);
      if ( TargetForHandle >= 0 )
      {
        v22 = 0;
        TargetForHandle = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<IDCompositionDesktopDevicePartner>(
                            &v17,
                            &v22);
        if ( TargetForHandle >= 0 )
        {
          v21[0] = 0;
          TargetForHandle = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v22 + 216LL))(
                              v22,
                              &GUID_4d93059d_097b_4651_9a60_f0f25116e2f3,
                              a4);
          if ( TargetForHandle >= 0 )
          {
            TargetForHandle = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v22 + 224LL))(
                                v22,
                                *a4,
                                v21);
            if ( TargetForHandle >= 0 )
              TargetForHandle = DCompositionCreateTargetForHandle(v21[0], a5);
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  }
  else
  {
    TargetForHandle = DCompositionCreateCrossDeviceVisual(v20, a4, a5);
  }
  if ( TargetForHandle >= 0 )
  {
    v12 = *a4;
    v22 = v12;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    if ( a3 )
    {
      v13 = a3 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          if ( v14 != 1 )
          {
LABEL_25:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
            goto LABEL_26;
          }
          v15 = a1 + 160;
        }
        else
        {
          v15 = a1 + 104;
        }
      }
      else
      {
        v15 = a1 + 120;
      }
    }
    else
    {
      v15 = a1 + 136;
    }
    TargetForHandle = Microsoft::WRL::ComPtr<IUnknown>::As<IDCompositionVisual2>(&v22, v15);
    goto LABEL_25;
  }
LABEL_26:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return (unsigned int)TargetForHandle;
}

```

## disassembly

```asm
0x1800e16a8  push    rbp
0x1800e16aa  push    rbx
0x1800e16ab  push    rsi
0x1800e16ac  push    rdi
0x1800e16ad  push    r14
0x1800e16af  push    r15
0x1800e16b1  mov     rbp, rsp
0x1800e16b4  sub     rsp, 58h
0x1800e16b8  mov     r15, r9
0x1800e16bb  mov     esi, r8d
0x1800e16be  mov     r14, rcx
0x1800e16c1  mov     [rbp+var_30], rdx
0x1800e16c5  lea     rcx, [rbp+var_30]
0x1800e16c9  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x1800e16ce  nop
0x1800e16cf  mov     [rbp+var_20], 0
0x1800e16d7  lea     rdx, [rbp+var_20]
0x1800e16db  lea     rcx, [rbp+var_30]
0x1800e16df  call    ??$As@UIDCompositionVisual@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompositionVisual@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<IDCompositionVisual>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionVisual>>)
0x1800e16e4  mov     ebx, eax
0x1800e16e6  test    eax, eax
0x1800e16e8  js      short loc_1800E1702
0x1800e16ea  mov     r8, [rbp+arg_20]
0x1800e16ee  mov     rdx, r15
0x1800e16f1  mov     rcx, [rbp+var_20]
0x1800e16f5  call    cs:__imp_DCompositionCreateCrossDeviceVisual
0x1800e16fb  mov     ebx, eax
0x1800e16fd  jmp     loc_1800E17F4
0x1800e1702  cmp     eax, 80004002h
0x1800e1707  jnz     loc_1800E1855
0x1800e170d  mov     [rbp+var_28], 0
0x1800e1715  lea     rdx, [rbp+var_28]
0x1800e1719  lea     rcx, [rbp+var_30]
0x1800e171d  call    ??$As@UICompositionObject@Composition@UI@Windows@@@?$ComPtr@UIContainerVisual@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::IContainerVisual>::As<Windows::UI::Composition::ICompositionObject>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject>>)
0x1800e1722  mov     ebx, eax
0x1800e1724  test    eax, eax
0x1800e1726  js      loc_1800E17EB
0x1800e172c  mov     [rbp+var_38], 0
0x1800e1734  mov     rdi, [rbp+var_28]
0x1800e1738  mov     rax, [rdi]
0x1800e173b  mov     rbx, [rax+30h]
0x1800e173f  lea     rcx, [rbp+var_38]
0x1800e1743  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e1748  lea     rdx, [rbp+var_38]
0x1800e174c  mov     rcx, rdi
0x1800e174f  mov     rax, rbx
0x1800e1752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1757  mov     ebx, eax
0x1800e1759  test    eax, eax
0x1800e175b  js      loc_1800E17E1
0x1800e1761  mov     [rbp+arg_8], 0
0x1800e1769  lea     rdx, [rbp+arg_8]
0x1800e176d  lea     rcx, [rbp+var_38]
0x1800e1771  call    ??$As@UIDCompositionDesktopDevicePartner@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompositionDesktopDevicePartner@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<IDCompositionDesktopDevicePartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionDesktopDevicePartner>>)
0x1800e1776  mov     ebx, eax
0x1800e1778  test    eax, eax
0x1800e177a  js      short loc_1800E17D7
0x1800e177c  mov     [rbp+var_18], 0
0x1800e1784  mov     rcx, [rbp+arg_8]
0x1800e1788  mov     rax, [rcx]
0x1800e178b  mov     r8, r15
0x1800e178e  lea     rdx, _GUID_4d93059d_097b_4651_9a60_f0f25116e2f3
0x1800e1795  mov     rax, [rax+0D8h]
0x1800e179c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e17a1  mov     ebx, eax
0x1800e17a3  test    eax, eax
0x1800e17a5  js      short loc_1800E17D7
0x1800e17a7  mov     rcx, [rbp+arg_8]
0x1800e17ab  mov     rax, [rcx]
0x1800e17ae  lea     r8, [rbp+var_18]
0x1800e17b2  mov     rdx, [r15]
0x1800e17b5  mov     rax, [rax+0E0h]
0x1800e17bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e17c1  mov     ebx, eax
0x1800e17c3  test    eax, eax
0x1800e17c5  js      short loc_1800E17D7
0x1800e17c7  mov     rdx, [rbp+arg_20]
0x1800e17cb  mov     rcx, [rbp+var_18]
0x1800e17cf  call    cs:__imp_DCompositionCreateTargetForHandle
0x1800e17d5  mov     ebx, eax
0x1800e17d7  lea     rcx, [rbp+arg_8]
0x1800e17db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e17e0  nop
0x1800e17e1  lea     rcx, [rbp+var_38]
0x1800e17e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e17ea  nop
0x1800e17eb  lea     rcx, [rbp+var_28]
0x1800e17ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e17f4  test    ebx, ebx
0x1800e17f6  js      short loc_1800E1855
0x1800e17f8  mov     rcx, [r15]
0x1800e17fb  mov     [rbp+arg_8], rcx
0x1800e17ff  test    rcx, rcx
0x1800e1802  jz      short loc_1800E1811
0x1800e1804  mov     rax, [rcx]
0x1800e1807  mov     rax, [rax+8]
0x1800e180b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1810  nop
0x1800e1811  test    esi, esi
0x1800e1813  jz      short loc_1800E1839
0x1800e1815  sub     esi, 1
0x1800e1818  jz      short loc_1800E1833
0x1800e181a  sub     esi, 1
0x1800e181d  jz      short loc_1800E182D
0x1800e181f  cmp     esi, 1
0x1800e1822  jnz     short loc_1800E184B
0x1800e1824  lea     rdx, [r14+0A0h]
0x1800e182b  jmp     short loc_1800E1840
0x1800e182d  lea     rdx, [r14+68h]
0x1800e1831  jmp     short loc_1800E1840
0x1800e1833  lea     rdx, [r14+78h]
0x1800e1837  jmp     short loc_1800E1840
0x1800e1839  lea     rdx, [r14+88h]
0x1800e1840  lea     rcx, [rbp+arg_8]
0x1800e1844  call    ??$As@UIDCompositionVisual2@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompositionVisual2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<IDCompositionVisual2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionVisual2>>)
0x1800e1849  mov     ebx, eax
0x1800e184b  lea     rcx, [rbp+arg_8]
0x1800e184f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e1854  nop
0x1800e1855  lea     rcx, [rbp+var_20]
0x1800e1859  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e185e  nop
0x1800e185f  lea     rcx, [rbp+var_30]
0x1800e1863  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e1868  mov     eax, ebx
0x1800e186a  add     rsp, 58h
0x1800e186e  pop     r15
0x1800e1870  pop     r14
0x1800e1872  pop     rdi
0x1800e1873  pop     rsi
0x1800e1874  pop     rbx
0x1800e1875  pop     rbp
0x1800e1876  retn
```
