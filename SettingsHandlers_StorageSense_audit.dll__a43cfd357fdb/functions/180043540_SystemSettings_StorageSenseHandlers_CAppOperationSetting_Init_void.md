# SystemSettings::StorageSenseHandlers::CAppOperationSetting::Init(void)

- ea: `0x180043540`
- end: `0x180043843`
- name: `?Init@CAppOperationSetting@StorageSenseHandlers@SystemSettings@@QEAAXXZ`
- size: `771`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::CAppOperationSetting *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003d578`

## callees

- `0x180043540`
- `0x180049f18`
- `0x1800a5ad0`
- `0x1800a7b3c`
- `0x1800a7bc4`
- `0x1800a8694`
- `0x1800a8fc8`
- `0x1800a978c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004366b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800436d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004370e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004366b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800436d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004370e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043787`

## pseudocode

```c
void __fastcall SystemSettings::StorageSenseHandlers::CAppOperationSetting::Init(
        SystemSettings::StorageSenseHandlers::CAppOperationSetting *this)
{
  __int64 v2; // rcx
  char *v3; // rsi
  int v4; // edx
  char v5; // al
  int v6; // eax
  bool v7; // r14
  SystemSettings::StorageSenseHandlers::CAppTileData *v8; // rdi
  SystemSettings::StorageSenseHandlers::CAppTileData *v9; // rdi
  __int64 v10; // rsi
  void (__fastcall *v11)(__int64, char *); // rdi
  SystemSettings::StorageSenseHandlers::CAppTileData *v12; // rdi
  SystemSettings::StorageSenseHandlers::CAppTileData *v13; // rdi
  __int64 v14; // rsi
  void (__fastcall *v15)(__int64, char *); // rdi
  SystemSettings::StorageSenseHandlers::CAppTileData *v16; // rdi
  bool v17; // al

  v2 = *((_QWORD *)this + 31);
  v3 = (char *)this + 258;
  v4 = *(_DWORD *)(*(_QWORD *)(v2 + 240) + 48LL);
  *((_BYTE *)this + 256) = v4 == 2;
  if ( v4 == 2
    && SystemSettings::StorageSenseHandlers::CAppTileData::GetIsDarwinApp(
         *(SystemSettings::StorageSenseHandlers::CAppTileData **)(v2 + 240),
         (unsigned __int8 *)this + 258) >= 0 )
  {
    v5 = *v3;
  }
  else
  {
    v5 = 0;
  }
  *v3 = v5;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
    *((_BYTE *)this + 259) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 31) + 240LL) + 48LL) == 3;
  v6 = *((_DWORD *)this + 60);
  v7 = 1;
  if ( v6 != 1 )
  {
    switch ( v6 )
    {
      case 2:
        if ( *((_BYTE *)this + 256) )
        {
          v16 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL);
          WindowsDeleteString(*((HSTRING *)this + 27));
          *((_QWORD *)this + 27) = 0;
          v17 = SystemSettings::StorageSenseHandlers::CAppTileData::GetModifyCommand(v16, (HSTRING *)this + 27) >= 0;
          *((_BYTE *)this + 272) = v17;
          if ( !v17 && *v3 )
            SystemSettings::StorageSenseHandlers::CAppTileData::GetCanModify(
              *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL),
              (unsigned __int8 *)this + 260);
          goto LABEL_10;
        }
        break;
      case 0:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
        {
          if ( *((_BYTE *)this + 256) || *((_BYTE *)this + 259) )
            v7 = 0;
        }
        else
        {
          v7 = *((_BYTE *)this + 256) == 0;
        }
        *((_BYTE *)this + 272) = v7;
        return;
      case 5:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
        {
          *((_BYTE *)this + 272) = *((_BYTE *)this + 259);
          return;
        }
        break;
      default:
        return;
    }
    *((_BYTE *)this + 272) = 0;
    return;
  }
  if ( *((_BYTE *)this + 256) )
  {
    v8 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL);
    WindowsDeleteString(*((HSTRING *)this + 27));
    *((_QWORD *)this + 27) = 0;
    *((_BYTE *)this + 272) = SystemSettings::StorageSenseHandlers::CAppTileData::GetUninstallCommand(
                               v8,
                               (HSTRING *)this + 27) >= 0;
    v9 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL);
    WindowsDeleteString(*((HSTRING *)this + 29));
    *((_QWORD *)this + 29) = 0;
    SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(v9, (HSTRING *)this + 29);
    v10 = *(_QWORD *)(*((_QWORD *)this + 31) + 240LL);
    v11 = *(void (__fastcall **)(__int64, char *))(*(_QWORD *)v10 + 64LL);
    WindowsDeleteString(*((HSTRING *)this + 28));
    *((_QWORD *)this + 28) = 0;
    v11(v10, (char *)this + 224);
LABEL_10:
    SystemSettings::StorageSenseHandlers::CAppTileData::GetIsHKCU(
      *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL),
      (unsigned __int8 *)this + 257);
    return;
  }
  if ( *((_BYTE *)this + 259) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
    {
      v12 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL);
      WindowsDeleteString(*((HSTRING *)this + 27));
      *((_QWORD *)this + 27) = 0;
      *((_BYTE *)this + 272) = SystemSettings::StorageSenseHandlers::CAppTileData::GetUninstallCommand(
                                 v12,
                                 (HSTRING *)this + 27) >= 0;
      v13 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(*((_QWORD *)this + 31) + 240LL);
      WindowsDeleteString(*((HSTRING *)this + 29));
      *((_QWORD *)this + 29) = 0;
      SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(v13, (HSTRING *)this + 29);
      v14 = *(_QWORD *)(*((_QWORD *)this + 31) + 240LL);
      v15 = *(void (__fastcall **)(__int64, char *))(*(_QWORD *)v14 + 64LL);
      WindowsDeleteString(*((HSTRING *)this + 28));
      *((_QWORD *)this + 28) = 0;
      v15(v14, (char *)this + 224);
    }
  }
}

```

## disassembly

```asm
0x180043540  push    rbx
0x180043542  push    rbp
0x180043543  push    rsi
0x180043544  push    rdi
0x180043545  push    r14
0x180043547  push    r15
0x180043549  sub     rsp, 28h
0x18004354d  mov     rbp, rcx
0x180043550  mov     rcx, [rcx+0F8h]
0x180043557  mov     rax, [rcx+0F0h]
0x18004355e  lea     rsi, [rbp+102h]
0x180043565  mov     edx, [rax+30h]
0x180043568  cmp     edx, 2
0x18004356b  setz    al
0x18004356e  xor     r15d, r15d
0x180043571  mov     [rbp+100h], al
0x180043577  cmp     edx, 2
0x18004357a  jnz     short loc_180043593
0x18004357c  mov     rcx, [rcx+0F0h]; this
0x180043583  mov     rdx, rsi; unsigned __int8 *
0x180043586  call    ?GetIsDarwinApp@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAE@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetIsDarwinApp(uchar *)
0x18004358b  test    eax, eax
0x18004358d  js      short loc_180043593
0x18004358f  mov     al, [rsi]
0x180043591  jmp     short loc_180043596
0x180043593  mov     al, r15b
0x180043596  mov     [rsi], al
0x180043598  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59787121@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121> `wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl(void)'::`2'::impl
0x18004359f  mov     rcx, rbx
0x1800435a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x1800435a7  test    al, al
0x1800435a9  jz      short loc_1800435C6
0x1800435ab  mov     rax, [rbp+0F8h]
0x1800435b2  mov     rcx, [rax+0F0h]
0x1800435b9  cmp     dword ptr [rcx+30h], 3
0x1800435bd  setz    al
0x1800435c0  mov     [rbp+103h], al
0x1800435c6  mov     eax, [rbp+0F0h]
0x1800435cc  mov     r14d, 1
0x1800435d2  cmp     eax, r14d
0x1800435d5  jnz     loc_18004375D
0x1800435db  cmp     [rbp+100h], r15b
0x1800435e2  jz      loc_1800436A1
0x1800435e8  mov     rax, [rbp+0F8h]
0x1800435ef  lea     rbx, [rbp+0D8h]
0x1800435f6  mov     rcx, [rbx]; string
0x1800435f9  mov     rdi, [rax+0F0h]
0x180043600  call    cs:__imp_WindowsDeleteString
0x180043606  mov     rdx, rbx; HSTRING *
0x180043609  mov     [rbx], r15
0x18004360c  mov     rcx, rdi; this
0x18004360f  call    ?GetUninstallCommand@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetUninstallCommand(HSTRING__ * *)
0x180043614  shr     eax, 1Fh
0x180043617  lea     rbx, [rbp+0E8h]
0x18004361e  xor     al, r14b
0x180043621  mov     [rbp+110h], al
0x180043627  mov     rax, [rbp+0F8h]
0x18004362e  mov     rcx, [rbx]; string
0x180043631  mov     rdi, [rax+0F0h]
0x180043638  call    cs:__imp_WindowsDeleteString
0x18004363e  mov     rdx, rbx; HSTRING *
0x180043641  mov     [rbx], r15
0x180043644  mov     rcx, rdi; this
0x180043647  call    ?GetPublisher@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(HSTRING__ * *)
0x18004364c  mov     rax, [rbp+0F8h]
0x180043653  lea     rbx, [rbp+0E0h]
0x18004365a  mov     rcx, [rbx]; string
0x18004365d  mov     rsi, [rax+0F0h]
0x180043664  mov     rax, [rsi]
0x180043667  mov     rdi, [rax+40h]
0x18004366b  call    cs:__imp_WindowsDeleteString
0x180043671  mov     rdx, rbx
0x180043674  mov     [rbx], r15
0x180043677  mov     rcx, rsi
0x18004367a  mov     rax, rdi
0x18004367d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043682  mov     rcx, [rbp+0F8h]
0x180043689  lea     rdx, [rbp+101h]; unsigned __int8 *
0x180043690  mov     rcx, [rcx+0F0h]; this
0x180043697  call    ?GetIsHKCU@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAE@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetIsHKCU(uchar *)
0x18004369c  jmp     loc_180043836
0x1800436a1  cmp     [rbp+103h], r15b
0x1800436a8  jz      loc_180043836
0x1800436ae  mov     rcx, rbx
0x1800436b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x1800436b6  test    al, al
0x1800436b8  jz      loc_180043836
0x1800436be  mov     rax, [rbp+0F8h]
0x1800436c5  lea     rbx, [rbp+0D8h]
0x1800436cc  mov     rcx, [rbx]; string
0x1800436cf  mov     rdi, [rax+0F0h]
0x1800436d6  call    cs:__imp_WindowsDeleteString
0x1800436dc  mov     rdx, rbx; HSTRING *
0x1800436df  mov     [rbx], r15
0x1800436e2  mov     rcx, rdi; this
0x1800436e5  call    ?GetUninstallCommand@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetUninstallCommand(HSTRING__ * *)
0x1800436ea  shr     eax, 1Fh
0x1800436ed  lea     rbx, [rbp+0E8h]
0x1800436f4  xor     al, r14b
0x1800436f7  mov     [rbp+110h], al
0x1800436fd  mov     rax, [rbp+0F8h]
0x180043704  mov     rcx, [rbx]; string
0x180043707  mov     rdi, [rax+0F0h]
0x18004370e  call    cs:__imp_WindowsDeleteString
0x180043714  mov     rdx, rbx; HSTRING *
0x180043717  mov     [rbx], r15
0x18004371a  mov     rcx, rdi; this
0x18004371d  call    ?GetPublisher@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(HSTRING__ * *)
0x180043722  mov     rax, [rbp+0F8h]
0x180043729  lea     rbx, [rbp+0E0h]
0x180043730  mov     rcx, [rbx]; string
0x180043733  mov     rsi, [rax+0F0h]
0x18004373a  mov     rax, [rsi]
0x18004373d  mov     rdi, [rax+40h]
0x180043741  call    cs:__imp_WindowsDeleteString
0x180043747  mov     rdx, rbx
0x18004374a  mov     [rbx], r15
0x18004374d  mov     rcx, rsi
0x180043750  mov     rax, rdi
0x180043753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043758  jmp     loc_180043836
0x18004375d  cmp     eax, 2
0x180043760  jnz     short loc_1800437D5
0x180043762  cmp     [rbp+100h], r15b
0x180043769  jz      loc_18004382F
0x18004376f  mov     rax, [rbp+0F8h]
0x180043776  lea     rbx, [rbp+0D8h]
0x18004377d  mov     rcx, [rbx]; string
0x180043780  mov     rdi, [rax+0F0h]
0x180043787  call    cs:__imp_WindowsDeleteString
0x18004378d  mov     rdx, rbx; HSTRING *
0x180043790  mov     [rbx], r15
0x180043793  mov     rcx, rdi; this
0x180043796  call    ?GetModifyCommand@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetModifyCommand(HSTRING__ * *)
0x18004379b  shr     eax, 1Fh
0x18004379e  xor     al, r14b
0x1800437a1  mov     [rbp+110h], al
0x1800437a7  jnz     loc_180043682
0x1800437ad  cmp     [rsi], r15b
0x1800437b0  jz      loc_180043682
0x1800437b6  mov     rcx, [rbp+0F8h]
0x1800437bd  lea     rdx, [rbp+104h]; unsigned __int8 *
0x1800437c4  mov     rcx, [rcx+0F0h]; this
0x1800437cb  call    ?GetCanModify@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAE@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetCanModify(uchar *)
0x1800437d0  jmp     loc_180043682
0x1800437d5  test    eax, eax
0x1800437d7  jnz     short loc_180043810
0x1800437d9  mov     rcx, rbx
0x1800437dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x1800437e1  test    al, al
0x1800437e3  jz      short loc_1800437FC
0x1800437e5  cmp     [rbp+100h], r15b
0x1800437ec  jnz     short loc_1800437F7
0x1800437ee  cmp     [rbp+103h], r15b
0x1800437f5  jz      short loc_180043807
0x1800437f7  mov     r14b, r15b
0x1800437fa  jmp     short loc_180043807
0x1800437fc  cmp     [rbp+100h], r15b
0x180043803  setz    r14b
0x180043807  mov     [rbp+110h], r14b
0x18004380e  jmp     short loc_180043836
0x180043810  cmp     eax, 5
0x180043813  jnz     short loc_180043836
0x180043815  mov     rcx, rbx
0x180043818  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x18004381d  test    al, al
0x18004381f  jz      short loc_18004382F
0x180043821  mov     al, [rbp+103h]
0x180043827  mov     [rbp+110h], al
0x18004382d  jmp     short loc_180043836
0x18004382f  mov     [rbp+110h], r15b
0x180043836  add     rsp, 28h
0x18004383a  pop     r15
0x18004383c  pop     r14
0x18004383e  pop     rdi
0x18004383f  pop     rsi
0x180043840  pop     rbp
0x180043841  pop     rbx
0x180043842  retn
```
