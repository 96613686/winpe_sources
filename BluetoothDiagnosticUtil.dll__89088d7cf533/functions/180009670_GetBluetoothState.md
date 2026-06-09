# GetBluetoothState

- ea: `0x180009670`
- end: `0x18000988c`
- name: `GetBluetoothState`
- size: `540`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c48`
- `0x180006c6c`
- `0x180009670`
- `0x180009c90`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800096f7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800096f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800096b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800096b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetBluetoothState(__int64 a1)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // ebx
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int v13; // [rsp+20h] [rbp-60h] BYREF
  __int64 v14; // [rsp+28h] [rbp-58h] BYREF
  __int64 v15; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+38h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  v15 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Devices.Radios.Radio", 0x1Cu, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18000988BLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4, &v15);
  if ( ActivationFactory >= 0 )
  {
    v17 = 0;
    v18 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 48LL))(v15, &v18);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>(
                            v18,
                            &v17);
      if ( ActivationFactory >= 0 )
      {
        v13 = 0;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 56LL))(v17, &v13);
        if ( ActivationFactory >= 0 )
        {
          v6 = 0;
          if ( v13 )
          {
            while ( 1 )
            {
              v14 = 0;
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 48LL))(
                                    v17,
                                    v6,
                                    &v14);
              if ( ActivationFactory >= 0 )
              {
                v16 = 0;
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 88LL))(v14, &v16);
                if ( ActivationFactory >= 0 && v16 == 3 )
                  break;
              }
              v7 = v14;
              if ( v14 )
              {
                v14 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
              }
              if ( ++v6 >= v13 )
                goto LABEL_16;
            }
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 72LL))(v14, a1);
            v8 = v14;
            if ( v14 )
            {
              v14 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
          }
        }
      }
    }
LABEL_16:
    v9 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180009670  mov     [rsp-18h+arg_8], rbx
0x180009675  mov     [rsp-18h+arg_10], rsi
0x18000967a  push    rbp
0x18000967b  push    rdi
0x18000967c  push    r14
0x18000967e  mov     rbp, rsp
0x180009681  sub     rsp, 80h
0x180009688  mov     rax, cs:__security_cookie
0x18000968f  xor     rax, rsp
0x180009692  mov     [rbp+var_10], rax
0x180009696  mov     rsi, rcx
0x180009699  xor     r14d, r14d
0x18000969c  mov     [rbp+var_50], r14
0x1800096a0  mov     [rbp+string], r14
0x1800096a4  lea     r9, [rbp+string]; string
0x1800096a8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800096ac  lea     edx, [r14+1Ch]; length
0x1800096b0  lea     rcx, ?RuntimeClass_Windows_Devices_Radios_Radio@@3QBGB; "Windows.Devices.Radios.Radio"
0x1800096b7  call    cs:__imp_WindowsCreateStringReference
0x1800096be  nop     dword ptr [rax+rax+00h]
0x1800096c3  test    eax, eax
0x1800096c5  js      loc_180009884
0x1800096cb  mov     rbx, [rbp+string]
0x1800096cf  mov     rcx, [rbp+var_50]
0x1800096d3  test    rcx, rcx
0x1800096d6  jz      short loc_1800096E9
0x1800096d8  mov     [rbp+var_50], r14
0x1800096dc  mov     rax, [rcx]
0x1800096df  mov     rax, [rax+10h]
0x1800096e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e8  nop
0x1800096e9  lea     r8, [rbp+var_50]
0x1800096ed  lea     rdx, _GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4
0x1800096f4  mov     rcx, rbx
0x1800096f7  call    cs:__imp_RoGetActivationFactory
0x1800096fe  nop     dword ptr [rax+rax+00h]
0x180009703  mov     ebx, eax
0x180009705  test    eax, eax
0x180009707  js      loc_180009843
0x18000970d  mov     [rbp+var_40], r14
0x180009711  mov     [rbp+var_38], r14
0x180009715  mov     rcx, [rbp+var_50]
0x180009719  mov     rax, [rcx]
0x18000971c  lea     rdx, [rbp+var_38]
0x180009720  mov     rax, [rax+30h]
0x180009724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009729  mov     ebx, eax
0x18000972b  test    eax, eax
0x18000972d  js      loc_18000980F
0x180009733  lea     rdx, [rbp+var_40]
0x180009737  mov     rcx, [rbp+var_38]
0x18000973b  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@23@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>>,tagCOWAIT_FLAGS,void *)
0x180009740  mov     ebx, eax
0x180009742  test    eax, eax
0x180009744  js      loc_18000980F
0x18000974a  mov     [rbp+var_60], r14d
0x18000974e  mov     rcx, [rbp+var_40]
0x180009752  mov     rax, [rcx]
0x180009755  lea     rdx, [rbp+var_60]
0x180009759  mov     rax, [rax+38h]
0x18000975d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009762  mov     ebx, eax
0x180009764  test    eax, eax
0x180009766  js      loc_18000980F
0x18000976c  mov     edi, r14d
0x18000976f  cmp     [rbp+var_60], r14d
0x180009773  jbe     loc_18000980F
0x180009779  mov     [rbp+var_58], r14
0x18000977d  mov     rcx, [rbp+var_40]
0x180009781  mov     rax, [rcx]
0x180009784  lea     r8, [rbp+var_58]
0x180009788  mov     edx, edi
0x18000978a  mov     rax, [rax+30h]
0x18000978e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009793  mov     ebx, eax
0x180009795  test    eax, eax
0x180009797  js      short loc_1800097BD
0x180009799  mov     [rbp+var_48], r14d
0x18000979d  mov     rcx, [rbp+var_58]
0x1800097a1  mov     rax, [rcx]
0x1800097a4  lea     rdx, [rbp+var_48]
0x1800097a8  mov     rax, [rax+58h]
0x1800097ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b1  mov     ebx, eax
0x1800097b3  test    eax, eax
0x1800097b5  js      short loc_1800097BD
0x1800097b7  cmp     [rbp+var_48], 3
0x1800097bb  jz      short loc_1800097E0
0x1800097bd  mov     rcx, [rbp+var_58]
0x1800097c1  test    rcx, rcx
0x1800097c4  jz      short loc_1800097D7
0x1800097c6  mov     [rbp+var_58], r14
0x1800097ca  mov     rax, [rcx]
0x1800097cd  mov     rax, [rax+10h]
0x1800097d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d6  nop
0x1800097d7  inc     edi
0x1800097d9  cmp     edi, [rbp+var_60]
0x1800097dc  jb      short loc_180009779
0x1800097de  jmp     short loc_18000980F
0x1800097e0  mov     rcx, [rbp+var_58]
0x1800097e4  mov     rax, [rcx]
0x1800097e7  mov     rdx, rsi
0x1800097ea  mov     rax, [rax+48h]
0x1800097ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f3  mov     ebx, eax
0x1800097f5  mov     rcx, [rbp+var_58]
0x1800097f9  test    rcx, rcx
0x1800097fc  jz      short loc_18000980F
0x1800097fe  mov     [rbp+var_58], r14
0x180009802  mov     rax, [rcx]
0x180009805  mov     rax, [rax+10h]
0x180009809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000980e  nop
0x18000980f  mov     rcx, [rbp+var_38]
0x180009813  test    rcx, rcx
0x180009816  jz      short loc_180009829
0x180009818  mov     [rbp+var_38], r14
0x18000981c  mov     rax, [rcx]
0x18000981f  mov     rax, [rax+10h]
0x180009823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009828  nop
0x180009829  mov     rcx, [rbp+var_40]
0x18000982d  test    rcx, rcx
0x180009830  jz      short loc_180009843
0x180009832  mov     [rbp+var_40], r14
0x180009836  mov     rax, [rcx]
0x180009839  mov     rax, [rax+10h]
0x18000983d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009842  nop
0x180009843  mov     rcx, [rbp+var_50]
0x180009847  test    rcx, rcx
0x18000984a  jz      short loc_18000985D
0x18000984c  mov     [rbp+var_50], r14
0x180009850  mov     rax, [rcx]
0x180009853  mov     rax, [rax+10h]
0x180009857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000985c  nop
0x18000985d  mov     eax, ebx
0x18000985f  mov     rcx, [rbp+var_10]
0x180009863  xor     rcx, rsp; StackCookie
0x180009866  call    __security_check_cookie
0x18000986b  lea     r11, [rsp+80h+var_s0]
0x180009873  mov     rbx, [r11+28h]
0x180009877  mov     rsi, [r11+30h]
0x18000987b  mov     rsp, r11
0x18000987e  pop     r14
0x180009880  pop     rdi
0x180009881  pop     rbp
0x180009882  retn
0x180009884  mov     ecx, eax; this
0x180009886  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
