# Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp(Windows::Foundation::Collections::Internal::Vector<Windows::System::Inventory::InstalledDesktopApp *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Inventory::InstalledDesktopApp *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Inventory::InstalledDesktopApp *>> *)

- ea: `0x180025ef4`
- end: `0x1800260e2`
- name: `?GetInventoryFromArp@CInstalledDesktopAppStatics@Inventory@System@Windows@@CAJPEAV?$Vector@PEAVInstalledDesktopApp@Inventory@System@Windows@@U?$DefaultEqualityPredicate@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@U?$DefaultVectorOptions@PEAVInstalledDesktopApp@Inventory@System@Windows@@@6784@@Internal@Collections@Foundation@4@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025d34`

## callees

- `0x180005890`
- `0x180007514`
- `0x18001d608`
- `0x180022448`
- `0x1800236d0`
- `0x1800243d0`
- `0x180025108`
- `0x180025ef4`
- `0x180026b04`
- `0x1800295dc`
- `0x1800eb010`

## import_xrefs

- `ext-ms-win-appcompat-aeinv-l1-1-0!GetAppInventory` at `0x180025f75`
- `ext-ms-win-appcompat-aeinv-l1-1-0!GetAppInventory` at `0x180025f75`

## string_xrefs

- `0x180025f92`: `Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp`
- `0x180025fb5`: `Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp`
- `0x18002608b`: `Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp(__int64 a1)
{
  int AppInventory; // eax
  unsigned int v3; // ebx
  const unsigned __int16 **i; // rbx
  const unsigned __int16 **v5; // r14
  const unsigned __int16 *v6; // rsi
  Windows::System::Inventory::CInstalledDesktopApp *v7; // rdi
  int v8; // eax
  int v9; // edi
  Windows::System::Inventory::CInstalledDesktopApp *v11; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h]
  _QWORD v14[4]; // [rsp+50h] [rbp-B0h] BYREF
  void **v15; // [rsp+70h] [rbp-90h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v17[131]; // [rsp+80h] [rbp-80h] BYREF
  char v18; // [rsp+8B0h] [rbp+7B0h]

  v15 = &Windows::System::Inventory::CDesktopAppReceiver::`vftable';
  v16 = 0;
  v17[0] = 0;
  v18 = 0;
  v14[0] = 24;
  v14[1] = 0;
  v14[2] = 806158337;
  if ( (unsigned __int8)IsGetAppInventoryPresent() )
  {
    AppInventory = GetAppInventory(&v15, v14, 0);
    v3 = AppInventory;
    if ( AppInventory < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp",
        382,
        "GetAppInventory failed [%#x]",
        AppInventory);
      goto LABEL_12;
    }
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp",
      388,
      "GetAppInventory is not present.");
  }
  Windows::System::Inventory::CDesktopAppReceiver::CompleteItem((Windows::System::Inventory::CDesktopAppReceiver *)&v15);
  v12 = 0;
  v13 = 0;
  std::vector<Windows::Compat::Inventory::IFileInfo const *>::_Construct_n<Windows::Compat::Inventory::IFileInfo const * * const &,Windows::Compat::Inventory::IFileInfo const * * const &>(
    &v12,
    (*(_QWORD *)&v17[0] - v16) >> 3,
    &v16,
    v17);
  v5 = (const unsigned __int16 **)*((_QWORD *)&v12 + 1);
  for ( i = (const unsigned __int16 **)v12; i != v5; ++i )
  {
    v6 = *i;
    Microsoft::WRL::Details::Make<Windows::System::Inventory::CInstalledDesktopApp,>(&v11);
    v7 = v11;
    if ( v11 )
    {
      Windows::System::Inventory::CInstalledDesktopApp::Initialize(v11, v6, v6 + 260, v6 + 520, v6 + 780);
      v11 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, Windows::System::Inventory::CInstalledDesktopApp *))(*(_QWORD *)a1 + 104LL))(
             a1,
             v7);
      v9 = v8;
      if ( v8 < 0 )
      {
        AslLogCallPrintf(
          1,
          "Windows::System::Inventory::CInstalledDesktopAppStatics::GetInventoryFromArp",
          401,
          "Vector::Append [%#x]",
          v8);
        std::vector<Windows::System::Inventory::DesktopAppInfo *>::_Tidy(&v12);
        v3 = v9;
        goto LABEL_12;
      }
    }
  }
  std::vector<Windows::System::Inventory::DesktopAppInfo *>::_Tidy(&v12);
  v3 = 0;
LABEL_12:
  Windows::System::Inventory::CDesktopAppReceiver::~CDesktopAppReceiver((Windows::System::Inventory::CDesktopAppReceiver *)&v15);
  return v3;
}

```

## disassembly

```asm
0x180025ef4  push    rbp
0x180025ef6  push    rbx
0x180025ef7  push    rsi
0x180025ef8  push    rdi
0x180025ef9  push    r14
0x180025efb  push    r15
0x180025efd  lea     rbp, [rsp-7D8h]
0x180025f05  sub     rsp, 8D8h
0x180025f0c  mov     rax, cs:__security_cookie
0x180025f13  xor     rax, rsp
0x180025f16  mov     [rbp+800h+var_40], rax
0x180025f1d  mov     r15, rcx
0x180025f20  lea     rax, ??_7CDesktopAppReceiver@Inventory@System@Windows@@6B@; const Windows::System::Inventory::CDesktopAppReceiver::`vftable'
0x180025f27  mov     [rsp+900h+var_890], rax
0x180025f2c  mov     [rsp+900h+var_888], 0
0x180025f35  xorps   xmm0, xmm0
0x180025f38  movdqa  [rbp+800h+var_880], xmm0
0x180025f3d  mov     [rbp+800h+var_50], 0
0x180025f44  mov     [rsp+900h+var_8B0], 18h
0x180025f4d  mov     [rsp+900h+var_8A8], 0
0x180025f56  mov     [rsp+900h+var_8A0], 300D0001h
0x180025f5f  call    IsGetAppInventoryPresent
0x180025f64  test    al, al
0x180025f66  jz      short loc_180025FA8
0x180025f68  xor     r8d, r8d
0x180025f6b  lea     rdx, [rsp+900h+var_8B0]
0x180025f70  lea     rcx, [rsp+900h+var_890]
0x180025f75  call    cs:__imp_GetAppInventory
0x180025f7b  mov     ebx, eax
0x180025f7d  test    eax, eax
0x180025f7f  jns     short loc_180025FC6
0x180025f81  mov     dword ptr [rsp+900h+var_8E0], eax
0x180025f85  lea     r9, aGetappinventor_1; "GetAppInventory failed [%#x]"
0x180025f8c  mov     r8d, 17Eh
0x180025f92  lea     rdx, aWindowsSystemI_1; "Windows::System::Inventory::CInstalledD"...
0x180025f99  mov     ecx, 1
0x180025f9e  call    AslLogCallPrintf
0x180025fa3  jmp     loc_1800260B7
0x180025fa8  lea     r9, aGetappinventor_2; "GetAppInventory is not present."
0x180025faf  mov     r8d, 184h
0x180025fb5  lea     rdx, aWindowsSystemI_1; "Windows::System::Inventory::CInstalledD"...
0x180025fbc  mov     ecx, 3
0x180025fc1  call    AslLogCallPrintf
0x180025fc6  lea     rcx, [rsp+900h+var_890]; this
0x180025fcb  call    ?CompleteItem@CDesktopAppReceiver@Inventory@System@Windows@@AEAAJXZ; Windows::System::Inventory::CDesktopAppReceiver::CompleteItem(void)
0x180025fd0  xorps   xmm0, xmm0
0x180025fd3  movdqu  [rsp+900h+var_8C8], xmm0
0x180025fd9  mov     [rsp+900h+var_8B8], 0
0x180025fe2  mov     rdx, qword ptr [rbp+800h+var_880]
0x180025fe6  sub     rdx, [rsp+900h+var_888]
0x180025feb  sar     rdx, 3
0x180025fef  lea     r9, [rbp+800h+var_880]
0x180025ff3  lea     r8, [rsp+900h+var_888]
0x180025ff8  lea     rcx, [rsp+900h+var_8C8]
0x180025ffd  call    ??$_Construct_n@AEBQEAPEBVIFileInfo@Inventory@Compat@Windows@@AEBQEAPEBV1234@@?$vector@PEBVIFileInfo@Inventory@Compat@Windows@@V?$allocator@PEBVIFileInfo@Inventory@Compat@Windows@@@std@@@std@@AEAAX_KAEBQEAPEBVIFileInfo@Inventory@Compat@Windows@@1@Z; std::vector<Windows::Compat::Inventory::IFileInfo const *>::_Construct_n<Windows::Compat::Inventory::IFileInfo const * * const &,Windows::Compat::Inventory::IFileInfo const * * const &>(unsigned __int64,Windows::Compat::Inventory::IFileInfo const * * const &,Windows::Compat::Inventory::IFileInfo const * * const &)
0x180026002  nop
0x180026003  mov     rbx, qword ptr [rsp+900h+var_8C8]
0x180026008  mov     r14, qword ptr [rsp+900h+var_8C8+8]
0x18002600d  cmp     rbx, r14
0x180026010  jz      loc_1800260AB
0x180026016  mov     rsi, [rbx]
0x180026019  lea     rcx, [rsp+900h+var_8D0]
0x18002601e  call    ??$Make@VCInstalledDesktopApp@Inventory@System@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInstalledDesktopApp@Inventory@System@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::System::Inventory::CInstalledDesktopApp,>(void)
0x180026023  nop
0x180026024  mov     rdi, [rsp+900h+var_8D0]
0x180026029  test    rdi, rdi
0x18002602c  jz      short loc_180026074
0x18002602e  lea     rax, [rsi+618h]
0x180026035  lea     r9, [rsi+410h]; unsigned __int16 *
0x18002603c  lea     r8, [rsi+208h]; unsigned __int16 *
0x180026043  mov     [rsp+900h+var_8E0], rax; unsigned __int16 *
0x180026048  mov     rdx, rsi; unsigned __int16 *
0x18002604b  mov     rcx, rdi; this
0x18002604e  call    ?Initialize@CInstalledDesktopApp@Inventory@System@Windows@@QEAAXPEBG000@Z; Windows::System::Inventory::CInstalledDesktopApp::Initialize(ushort const *,ushort const *,ushort const *,ushort const *)
0x180026053  mov     [rsp+900h+var_8D0], 0
0x18002605c  mov     rax, [r15]
0x18002605f  mov     rdx, rdi
0x180026062  mov     rcx, r15
0x180026065  mov     rax, [rax+68h]
0x180026069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002606e  mov     edi, eax
0x180026070  test    eax, eax
0x180026072  js      short loc_18002607A
0x180026074  add     rbx, 8
0x180026078  jmp     short loc_18002600D
0x18002607a  mov     dword ptr [rsp+900h+var_8E0], edi
0x18002607e  lea     r9, aVectorAppendX; "Vector::Append [%#x]"
0x180026085  mov     r8d, 191h
0x18002608b  lea     rdx, aWindowsSystemI_1; "Windows::System::Inventory::CInstalledD"...
0x180026092  mov     ecx, 1
0x180026097  call    AslLogCallPrintf
0x18002609c  nop
0x18002609d  lea     rcx, [rsp+900h+var_8C8]
0x1800260a2  call    ?_Tidy@?$vector@PEAUDesktopAppInfo@Inventory@System@Windows@@V?$allocator@PEAUDesktopAppInfo@Inventory@System@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::System::Inventory::DesktopAppInfo *>::_Tidy(void)
0x1800260a7  mov     ebx, edi
0x1800260a9  jmp     short loc_1800260B7
0x1800260ab  lea     rcx, [rsp+900h+var_8C8]
0x1800260b0  call    ?_Tidy@?$vector@PEAUDesktopAppInfo@Inventory@System@Windows@@V?$allocator@PEAUDesktopAppInfo@Inventory@System@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::System::Inventory::DesktopAppInfo *>::_Tidy(void)
0x1800260b5  xor     ebx, ebx
0x1800260b7  lea     rcx, [rsp+900h+var_890]; this
0x1800260bc  call    ??1CDesktopAppReceiver@Inventory@System@Windows@@QEAA@XZ; Windows::System::Inventory::CDesktopAppReceiver::~CDesktopAppReceiver(void)
0x1800260c1  mov     eax, ebx
0x1800260c3  mov     rcx, [rbp+800h+var_40]
0x1800260ca  xor     rcx, rsp; StackCookie
0x1800260cd  call    __security_check_cookie
0x1800260d2  add     rsp, 8D8h
0x1800260d9  pop     r15
0x1800260db  pop     r14
0x1800260dd  pop     rdi
0x1800260de  pop     rsi
0x1800260df  pop     rbx
0x1800260e0  pop     rbp
0x1800260e1  retn
```
