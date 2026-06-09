# SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(HSTRING__ * *)

- ea: `0x1800a8fc8`
- end: `0x1800a91d7`
- name: `?GetPublisher@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z`
- size: `527`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppTileData *__hidden this, HSTRING *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041bc0`
- `0x180043540`
- `0x180048168`
- `0x18004b9b0`
- `0x1800bba54`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x180049f18`
- `0x1800a0338`
- `0x1800a0388`
- `0x1800a03d8`
- `0x1800a8fc8`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a9083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800a9083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a902d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a90d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9177`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a902d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a90d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9177`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(
        SystemSettings::StorageSenseHandlers::CAppTileData *this,
        HSTRING *a2)
{
  HSTRING *v4; // rsi
  int v5; // eax
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v18; // [rsp+40h] [rbp+20h] BYREF

  v4 = (HSTRING *)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
    return WindowsDuplicateString(*v4, a2);
  v5 = *((_DWORD *)this + 12);
  if ( v5 == 2 )
  {
    v18 = 0;
    v6 = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IDesktopAppInfo>(
           (char *)this + 40,
           &v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1249;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
        (const char *)(unsigned int)v6,
        savedregs);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v18);
      return v7;
    }
    v9 = v18;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 104LL);
    WindowsDeleteString(*v4);
    *v4 = 0;
    v6 = v10(v9, v4);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1250;
      goto LABEL_7;
    }
    goto LABEL_8;
  }
  if ( !v5 )
  {
    v18 = 0;
    v6 = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(
           (char *)this + 40,
           &v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1255;
      goto LABEL_7;
    }
    v12 = v18;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 120LL);
    WindowsDeleteString(*v4);
    *v4 = 0;
    v6 = v13(v12, v4);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1256;
      goto LABEL_7;
    }
    goto LABEL_8;
  }
  if ( v5 == 3
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
  {
    v18 = 0;
    v6 = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IMcpServerInfo>(
           (char *)this + 40,
           &v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1263;
      goto LABEL_7;
    }
    v14 = v18;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 96LL);
    WindowsDeleteString(*v4);
    *v4 = 0;
    v6 = v15(v14, v4);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1264;
      goto LABEL_7;
    }
LABEL_8:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v18);
    return WindowsDuplicateString(*v4, a2);
  }
  return -2147024809;
}

```

## disassembly

```asm
0x1800a8fc8  mov     [rsp-18h+arg_8], rbx
0x1800a8fcd  mov     [rsp-18h+arg_10], rsi
0x1800a8fd2  push    rbp
0x1800a8fd3  push    rdi
0x1800a8fd4  push    r14; int
0x1800a8fd6  mov     rbp, rsp
0x1800a8fd9  sub     rsp, 20h
0x1800a8fdd  mov     r14, rdx
0x1800a8fe0  mov     rbx, rcx
0x1800a8fe3  lea     rsi, [rcx+20h]
0x1800a8fe7  cmp     qword ptr [rsi], 0
0x1800a8feb  jnz     loc_1800A907D
0x1800a8ff1  mov     eax, [rcx+30h]
0x1800a8ff4  cmp     eax, 2
0x1800a8ff7  jnz     loc_1800A909C
0x1800a8ffd  mov     [rbp+arg_0], 0
0x1800a9005  add     rcx, 28h ; '('
0x1800a9009  lea     rdx, [rbp+arg_0]
0x1800a900d  call    ??$As@UIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IDesktopAppInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IDesktopAppInfo>>)
0x1800a9012  mov     ebx, eax
0x1800a9014  test    eax, eax
0x1800a9016  jns     short loc_1800A901F
0x1800a9018  mov     edx, 4E1h
0x1800a901d  jmp     short loc_1800A9053
0x1800a901f  mov     rdi, [rbp+arg_0]
0x1800a9023  mov     rax, [rdi]
0x1800a9026  mov     rbx, [rax+68h]
0x1800a902a  mov     rcx, [rsi]; string
0x1800a902d  call    cs:__imp_WindowsDeleteString
0x1800a9033  mov     qword ptr [rsi], 0
0x1800a903a  mov     rdx, rsi
0x1800a903d  mov     rcx, rdi
0x1800a9040  mov     rax, rbx
0x1800a9043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9048  mov     ebx, eax
0x1800a904a  test    eax, eax
0x1800a904c  jns     short loc_1800A9074
0x1800a904e  mov     edx, 4E2h; void *
0x1800a9053  mov     r9d, eax; char *
0x1800a9056  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a905d  mov     rcx, [rbp+18h]; this
0x1800a9061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9066  nop
0x1800a9067  lea     rcx, [rbp+arg_0]
0x1800a906b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9070  mov     eax, ebx
0x1800a9072  jmp     short loc_1800A9089
0x1800a9074  lea     rcx, [rbp+arg_0]
0x1800a9078  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a907d  mov     rdx, r14; newString
0x1800a9080  mov     rcx, [rsi]; string
0x1800a9083  call    cs:__imp_WindowsDuplicateString
0x1800a9089  mov     rbx, [rsp+20h+arg_8]
0x1800a908e  mov     rsi, [rsp+20h+arg_10]
0x1800a9093  add     rsp, 20h
0x1800a9097  pop     r14
0x1800a9099  pop     rdi
0x1800a909a  pop     rbp
0x1800a909b  retn
0x1800a909c  test    eax, eax
0x1800a909e  jnz     loc_1800A912A
0x1800a90a4  mov     [rbp+arg_0], 0
0x1800a90ac  add     rcx, 28h ; '('
0x1800a90b0  lea     rdx, [rbp+arg_0]
0x1800a90b4  call    ??$As@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IPackageInfo>>)
0x1800a90b9  mov     ebx, eax
0x1800a90bb  test    eax, eax
0x1800a90bd  jns     short loc_1800A90C6
0x1800a90bf  mov     edx, 4E7h
0x1800a90c4  jmp     short loc_1800A90FA
0x1800a90c6  mov     rdi, [rbp+arg_0]
0x1800a90ca  mov     rax, [rdi]
0x1800a90cd  mov     rbx, [rax+78h]
0x1800a90d1  mov     rcx, [rsi]; string
0x1800a90d4  call    cs:__imp_WindowsDeleteString
0x1800a90da  mov     qword ptr [rsi], 0
0x1800a90e1  mov     rdx, rsi
0x1800a90e4  mov     rcx, rdi
0x1800a90e7  mov     rax, rbx
0x1800a90ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a90ef  mov     ebx, eax
0x1800a90f1  test    eax, eax
0x1800a90f3  jns     short loc_1800A911C
0x1800a90f5  mov     edx, 4E8h; void *
0x1800a90fa  mov     r9d, eax; char *
0x1800a90fd  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a9104  mov     rcx, [rbp+18h]; this
0x1800a9108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a910d  nop
0x1800a910e  lea     rcx, [rbp+arg_0]
0x1800a9112  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9117  jmp     loc_1800A9070
0x1800a911c  lea     rcx, [rbp+arg_0]
0x1800a9120  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9125  jmp     loc_1800A907D
0x1800a912a  cmp     eax, 3
0x1800a912d  jnz     loc_1800A91CD
0x1800a9133  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59787121@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121> `wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl(void)'::`2'::impl
0x1800a913a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x1800a913f  test    al, al
0x1800a9141  jz      loc_1800A91CD
0x1800a9147  mov     [rbp+arg_0], 0
0x1800a914f  lea     rcx, [rbx+28h]
0x1800a9153  lea     rdx, [rbp+arg_0]
0x1800a9157  call    ??$As@UIMcpServerInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMcpServerInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IMcpServerInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IMcpServerInfo>>)
0x1800a915c  mov     ebx, eax
0x1800a915e  test    eax, eax
0x1800a9160  jns     short loc_1800A9169
0x1800a9162  mov     edx, 4EFh
0x1800a9167  jmp     short loc_1800A919D
0x1800a9169  mov     rdi, [rbp+arg_0]
0x1800a916d  mov     rax, [rdi]
0x1800a9170  mov     rbx, [rax+60h]
0x1800a9174  mov     rcx, [rsi]; string
0x1800a9177  call    cs:__imp_WindowsDeleteString
0x1800a917d  mov     qword ptr [rsi], 0
0x1800a9184  mov     rdx, rsi
0x1800a9187  mov     rcx, rdi
0x1800a918a  mov     rax, rbx
0x1800a918d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9192  mov     ebx, eax
0x1800a9194  test    eax, eax
0x1800a9196  jns     short loc_1800A91BF
0x1800a9198  mov     edx, 4F0h; void *
0x1800a919d  mov     r9d, eax; char *
0x1800a91a0  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a91a7  mov     rcx, [rbp+18h]; this
0x1800a91ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a91b0  nop
0x1800a91b1  lea     rcx, [rbp+arg_0]
0x1800a91b5  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a91ba  jmp     loc_1800A9070
0x1800a91bf  lea     rcx, [rbp+arg_0]
0x1800a91c3  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a91c8  jmp     loc_1800A907D
0x1800a91cd  mov     eax, 80070057h
0x1800a91d2  jmp     loc_1800A9089
```
