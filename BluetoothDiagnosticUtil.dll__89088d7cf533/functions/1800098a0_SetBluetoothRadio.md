# SetBluetoothRadio

- ea: `0x1800098a0`
- end: `0x180009b34`
- name: `SetBluetoothRadio`
- size: `660`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c48`
- `0x1800030a0`
- `0x180006c6c`
- `0x1800098a0`
- `0x180009c90`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009924`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009924`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800098e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800098e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetBluetoothRadio(unsigned __int8 a1)
{
  int v1; // esi
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // ebx
  unsigned int v6; // edi
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rsi
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v19; // [rsp+20h] [rbp-60h] BYREF
  __int64 v20; // [rsp+28h] [rbp-58h] BYREF
  __int64 v21; // [rsp+30h] [rbp-50h] BYREF
  __int64 v22; // [rsp+38h] [rbp-48h] BYREF
  int v23; // [rsp+40h] [rbp-40h] BYREF
  int v24; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  __int64 v26; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF

  v1 = a1;
  v22 = 0;
  v21 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Devices.Radios.Radio", 0x1Cu, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x180009B33LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4, &v22);
  if ( ActivationFactory >= 0 )
  {
    v25 = 0;
    v26 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v26);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>(
                            v26,
                            &v25);
      if ( ActivationFactory >= 0 )
      {
        v19 = 0;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(v25, &v19);
        if ( ActivationFactory >= 0 )
        {
          v6 = 0;
          if ( v19 )
          {
            while ( 1 )
            {
              v20 = 0;
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL))(
                                    v25,
                                    v6,
                                    &v20);
              if ( ActivationFactory >= 0 )
              {
                v23 = 0;
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 88LL))(v20, &v23);
                if ( ActivationFactory >= 0 && v23 == 3 )
                  break;
              }
              v7 = v20;
              if ( v20 )
              {
                v20 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
              }
              if ( ++v6 >= v19 )
                goto LABEL_24;
            }
            v8 = v1 ^ 1;
            v9 = v20;
            v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 48LL);
            v11 = v21;
            if ( v21 )
            {
              v21 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            }
            ActivationFactory = v10(v9, (unsigned int)(v8 + 1), &v21);
            if ( ActivationFactory >= 0 )
            {
              v24 = 0;
              v12 = v21;
              ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus>>(v21);
              if ( ActivationFactory >= 0 )
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v24);
              if ( ActivationFactory >= 0 && v24 != 1 )
                ActivationFactory = -2147023728;
            }
            v13 = v20;
            if ( v20 )
            {
              v20 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
          }
        }
      }
    }
LABEL_24:
    v14 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800098a0  push    rbp
0x1800098a2  push    rbx
0x1800098a3  push    rsi
0x1800098a4  push    rdi
0x1800098a5  push    r14
0x1800098a7  mov     rbp, rsp
0x1800098aa  sub     rsp, 80h
0x1800098b1  mov     rax, cs:__security_cookie
0x1800098b8  xor     rax, rsp
0x1800098bb  mov     [rbp+var_8], rax
0x1800098bf  movzx   esi, cl
0x1800098c2  xor     r14d, r14d
0x1800098c5  mov     [rbp+var_48], r14
0x1800098c9  mov     [rbp+var_50], r14
0x1800098cd  mov     [rbp+string], r14
0x1800098d1  lea     r9, [rbp+string]; string
0x1800098d5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800098d9  lea     edx, [r14+1Ch]; length
0x1800098dd  lea     rcx, ?RuntimeClass_Windows_Devices_Radios_Radio@@3QBGB; "Windows.Devices.Radios.Radio"
0x1800098e4  call    cs:__imp_WindowsCreateStringReference
0x1800098eb  nop     dword ptr [rax+rax+00h]
0x1800098f0  test    eax, eax
0x1800098f2  js      loc_180009B2C
0x1800098f8  mov     rbx, [rbp+string]
0x1800098fc  mov     rcx, [rbp+var_48]
0x180009900  test    rcx, rcx
0x180009903  jz      short loc_180009916
0x180009905  mov     [rbp+var_48], r14
0x180009909  mov     rax, [rcx]
0x18000990c  mov     rax, [rax+10h]
0x180009910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009915  nop
0x180009916  lea     r8, [rbp+var_48]
0x18000991a  lea     rdx, _GUID_5fb6a12e_67cb_46ae_aae9_65919f86eff4
0x180009921  mov     rcx, rbx
0x180009924  call    cs:__imp_RoGetActivationFactory
0x18000992b  nop     dword ptr [rax+rax+00h]
0x180009930  mov     ebx, eax
0x180009932  test    eax, eax
0x180009934  js      loc_180009ADB
0x18000993a  mov     [rbp+var_38], r14
0x18000993e  mov     [rbp+var_30], r14
0x180009942  mov     rcx, [rbp+var_48]
0x180009946  mov     rax, [rcx]
0x180009949  lea     rdx, [rbp+var_30]
0x18000994d  mov     rax, [rax+30h]
0x180009951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009956  mov     ebx, eax
0x180009958  test    eax, eax
0x18000995a  js      loc_180009AA7
0x180009960  lea     rdx, [rbp+var_38]
0x180009964  mov     rcx, [rbp+var_30]
0x180009968  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@23@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *>>>,tagCOWAIT_FLAGS,void *)
0x18000996d  mov     ebx, eax
0x18000996f  test    eax, eax
0x180009971  js      loc_180009AA7
0x180009977  mov     [rbp+var_60], r14d
0x18000997b  mov     rcx, [rbp+var_38]
0x18000997f  mov     rax, [rcx]
0x180009982  lea     rdx, [rbp+var_60]
0x180009986  mov     rax, [rax+38h]
0x18000998a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998f  mov     ebx, eax
0x180009991  test    eax, eax
0x180009993  js      loc_180009AA7
0x180009999  mov     edi, r14d
0x18000999c  cmp     [rbp+var_60], r14d
0x1800099a0  jbe     loc_180009AA7
0x1800099a6  mov     [rbp+var_58], r14
0x1800099aa  mov     rcx, [rbp+var_38]
0x1800099ae  mov     rax, [rcx]
0x1800099b1  lea     r8, [rbp+var_58]
0x1800099b5  mov     edx, edi
0x1800099b7  mov     rax, [rax+30h]
0x1800099bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c0  mov     ebx, eax
0x1800099c2  test    eax, eax
0x1800099c4  js      short loc_1800099EA
0x1800099c6  mov     [rbp+var_40], r14d
0x1800099ca  mov     rcx, [rbp+var_58]
0x1800099ce  mov     rax, [rcx]
0x1800099d1  lea     rdx, [rbp+var_40]
0x1800099d5  mov     rax, [rax+58h]
0x1800099d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099de  mov     ebx, eax
0x1800099e0  test    eax, eax
0x1800099e2  js      short loc_1800099EA
0x1800099e4  cmp     [rbp+var_40], 3
0x1800099e8  jz      short loc_180009A10
0x1800099ea  mov     rcx, [rbp+var_58]
0x1800099ee  test    rcx, rcx
0x1800099f1  jz      short loc_180009A04
0x1800099f3  mov     [rbp+var_58], r14
0x1800099f7  mov     rax, [rcx]
0x1800099fa  mov     rax, [rax+10h]
0x1800099fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a03  nop
0x180009a04  inc     edi
0x180009a06  cmp     edi, [rbp+var_60]
0x180009a09  jb      short loc_1800099A6
0x180009a0b  jmp     loc_180009AA7
0x180009a10  mov     edi, esi
0x180009a12  xor     edi, 1
0x180009a15  mov     rbx, [rbp+var_58]
0x180009a19  mov     rax, [rbx]
0x180009a1c  mov     rsi, [rax+30h]
0x180009a20  mov     rcx, [rbp+var_50]
0x180009a24  test    rcx, rcx
0x180009a27  jz      short loc_180009A3A
0x180009a29  mov     [rbp+var_50], r14
0x180009a2d  mov     r8, [rcx]
0x180009a30  mov     rax, [r8+10h]
0x180009a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a39  nop
0x180009a3a  lea     r8, [rbp+var_50]
0x180009a3e  lea     edx, [rdi+1]
0x180009a41  mov     rcx, rbx
0x180009a44  mov     rax, rsi
0x180009a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a4c  mov     ebx, eax
0x180009a4e  test    eax, eax
0x180009a50  js      short loc_180009A8D
0x180009a52  mov     [rbp+var_3C], r14d
0x180009a56  mov     rdi, [rbp+var_50]
0x180009a5a  mov     rcx, rdi
0x180009a5d  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,void *)
0x180009a62  mov     ebx, eax
0x180009a64  test    eax, eax
0x180009a66  js      short loc_180009A7D
0x180009a68  mov     rax, [rdi]
0x180009a6b  lea     rdx, [rbp+var_3C]
0x180009a6f  mov     rcx, rdi
0x180009a72  mov     rax, [rax+40h]
0x180009a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7b  mov     ebx, eax
0x180009a7d  test    ebx, ebx
0x180009a7f  js      short loc_180009A8D
0x180009a81  mov     eax, 80070490h
0x180009a86  cmp     [rbp+var_3C], 1
0x180009a8a  cmovnz  ebx, eax
0x180009a8d  mov     rcx, [rbp+var_58]
0x180009a91  test    rcx, rcx
0x180009a94  jz      short loc_180009AA7
0x180009a96  mov     [rbp+var_58], r14
0x180009a9a  mov     rax, [rcx]
0x180009a9d  mov     rax, [rax+10h]
0x180009aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aa6  nop
0x180009aa7  mov     rcx, [rbp+var_30]
0x180009aab  test    rcx, rcx
0x180009aae  jz      short loc_180009AC1
0x180009ab0  mov     [rbp+var_30], r14
0x180009ab4  mov     rax, [rcx]
0x180009ab7  mov     rax, [rax+10h]
0x180009abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac0  nop
0x180009ac1  mov     rcx, [rbp+var_38]
0x180009ac5  test    rcx, rcx
0x180009ac8  jz      short loc_180009ADB
0x180009aca  mov     [rbp+var_38], r14
0x180009ace  mov     rax, [rcx]
0x180009ad1  mov     rax, [rax+10h]
0x180009ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ada  nop
0x180009adb  mov     rcx, [rbp+var_50]
0x180009adf  test    rcx, rcx
0x180009ae2  jz      short loc_180009AF5
0x180009ae4  mov     [rbp+var_50], r14
0x180009ae8  mov     rax, [rcx]
0x180009aeb  mov     rax, [rax+10h]
0x180009aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009af4  nop
0x180009af5  mov     rcx, [rbp+var_48]
0x180009af9  test    rcx, rcx
0x180009afc  jz      short loc_180009B0F
0x180009afe  mov     [rbp+var_48], r14
0x180009b02  mov     rax, [rcx]
0x180009b05  mov     rax, [rax+10h]
0x180009b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0e  nop
0x180009b0f  mov     eax, ebx
0x180009b11  mov     rcx, [rbp+var_8]
0x180009b15  xor     rcx, rsp; StackCookie
0x180009b18  call    __security_check_cookie
0x180009b1d  add     rsp, 80h
0x180009b24  pop     r14
0x180009b26  pop     rdi
0x180009b27  pop     rsi
0x180009b28  pop     rbx
0x180009b29  pop     rbp
0x180009b2a  retn
0x180009b2c  mov     ecx, eax; this
0x180009b2e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
