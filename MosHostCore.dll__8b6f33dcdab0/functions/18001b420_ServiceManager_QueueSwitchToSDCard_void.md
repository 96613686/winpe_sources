# ServiceManager::QueueSwitchToSDCard(void)

- ea: `0x18001b420`
- end: `0x18001b56c`
- name: `?QueueSwitchToSDCard@ServiceManager@@UEAAJXZ`
- size: `332`
- prototype: `__int64 __fastcall(PTP_CALLBACK_ENVIRON *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180003410`
- `0x180003f58`
- `0x180003f7c`
- `0x1800079d4`
- `0x18000816c`
- `0x18000c598`
- `0x18001189c`
- `0x18001b420`

## import_xrefs

- `MosStorage!MosStorageGetCurrentLocation` at `0x18001b4bb`
- `MosStorage!MosStorageGetCurrentLocation` at `0x18001b4bb`
- `MosStorage!MosStorageGetDefaultExternalStorage` at `0x18001b48e`
- `MosStorage!MosStorageGetDefaultExternalStorage` at `0x18001b48e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b4aa`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b4aa`

## string_xrefs

- `0x18001b4a1`: `ServiceManager::QueueSwitchToSDCard`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::QueueSwitchToSDCard(PTP_CALLBACK_ENVIRON *this)
{
  int DefaultExternalStorage; // eax
  int v3; // r8d
  unsigned int v4; // edi
  _BYTE v6[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v8[1084]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buf1[564]; // [rsp+4ACh] [rbp+3ACh] BYREF
  _BYTE v10[1084]; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE Buf2[564]; // [rsp+B1Ch] [rbp+A1Ch] BYREF

  std::wstring::wstring(v7);
  std::wstring::wstring(v6);
  memset_0(v10, 0, 0x670u);
  memset_0(v8, 0, 0x670u);
  DefaultExternalStorage = MosStorageGetDefaultExternalStorage((struct _STORAGE_DEVICE_DATA *)v8);
  if ( DefaultExternalStorage >= 0 )
  {
    DefaultExternalStorage = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v10);
    if ( DefaultExternalStorage >= 0 )
    {
      v4 = 0;
      if ( !memcmp_0(Buf1, Buf2, 0x10u) )
        goto LABEL_10;
      DefaultExternalStorage = MigrationEngine::SetPendingMigration(
                                 (MigrationEngine *)(this + 1),
                                 (const struct _STORAGE_DEVICE_DATA *)v8);
      if ( DefaultExternalStorage >= 0 )
      {
        Threadpool::QueueThis<ServiceManager>(this[424]);
        goto LABEL_10;
      }
      v3 = 3796;
    }
    else
    {
      v3 = 3791;
    }
  }
  else
  {
    v3 = 3790;
  }
  v4 = ZTraceReportPropagation(DefaultExternalStorage, "ServiceManager::QueueSwitchToSDCard", v3, this);
LABEL_10:
  std::wstring::_Tidy_deallocate(v6);
  std::wstring::_Tidy_deallocate(v7);
  return v4;
}

```

## disassembly

```asm
0x18001b420  mov     [rsp-8+arg_8], rbx
0x18001b425  mov     [rsp-8+arg_10], rdi
0x18001b42a  push    rbp
0x18001b42b  lea     rbp, [rsp-0C60h]
0x18001b433  sub     rsp, 0D60h
0x18001b43a  mov     rax, cs:__security_cookie
0x18001b441  xor     rax, rsp
0x18001b444  mov     [rbp+0C60h+var_10], rax
0x18001b44b  mov     rbx, rcx
0x18001b44e  lea     rcx, [rsp+0D60h+var_D10]
0x18001b453  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b458  nop
0x18001b459  lea     rcx, [rsp+0D60h+var_D30]
0x18001b45e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b463  nop
0x18001b464  mov     edi, 670h
0x18001b469  mov     r8d, edi; Size
0x18001b46c  xor     edx, edx; Val
0x18001b46e  lea     rcx, [rbp+0C60h+var_680]; void *
0x18001b475  call    memset_0
0x18001b47a  mov     r8d, edi; Size
0x18001b47d  xor     edx, edx; Val
0x18001b47f  lea     rcx, [rsp+0D60h+var_CF0]; void *
0x18001b484  call    memset_0
0x18001b489  lea     rcx, [rsp+0D60h+var_CF0]
0x18001b48e  call    cs:__imp_?MosStorageGetDefaultExternalStorage@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetDefaultExternalStorage(_STORAGE_DEVICE_DATA *)
0x18001b494  test    eax, eax
0x18001b496  jns     short loc_18001B4B4
0x18001b498  mov     r8d, 0ECEh
0x18001b49e  mov     r9, rbx
0x18001b4a1  lea     rdx, aServicemanager_74; "ServiceManager::QueueSwitchToSDCard"
0x18001b4a8  mov     ecx, eax
0x18001b4aa  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b4b0  mov     edi, eax
0x18001b4b2  jmp     short loc_18001B531
0x18001b4b4  lea     rcx, [rbp+0C60h+var_680]
0x18001b4bb  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x18001b4c1  test    eax, eax
0x18001b4c3  jns     short loc_18001B4CD
0x18001b4c5  mov     r8d, 0ECFh
0x18001b4cb  jmp     short loc_18001B49E
0x18001b4cd  xor     edi, edi
0x18001b4cf  lea     r8d, [rdi+10h]; Size
0x18001b4d3  lea     rdx, [rbp+0C60h+Buf2]; Buf2
0x18001b4da  lea     rcx, [rbp+0C60h+Buf1]; Buf1
0x18001b4e1  call    memcmp_0
0x18001b4e6  test    eax, eax
0x18001b4e8  jz      short loc_18001B531
0x18001b4ea  lea     rcx, [rbx+8]; this
0x18001b4ee  lea     rdx, [rsp+0D60h+var_CF0]; struct _STORAGE_DEVICE_DATA *
0x18001b4f3  call    ?SetPendingMigration@MigrationEngine@@IEAAJAEBU_STORAGE_DEVICE_DATA@@@Z; MigrationEngine::SetPendingMigration(_STORAGE_DEVICE_DATA const &)
0x18001b4f8  test    eax, eax
0x18001b4fa  jns     short loc_18001B504
0x18001b4fc  mov     r8d, 0ED4h
0x18001b502  jmp     short loc_18001B49E
0x18001b504  lea     rax, ??_9ServiceManager@@$BGI@AA; [thunk]: ServiceManager::`vcall'{104,{flat}}
0x18001b50b  mov     [rsp+0D60h+var_D40], rax
0x18001b510  mov     [rsp+0D60h+var_D38], edi
0x18001b514  mov     eax, [rsp+0D60h+var_D34]
0x18001b518  mov     [rsp+0D60h+var_D34], eax
0x18001b51c  lea     r8, [rsp+0D60h+var_D40]
0x18001b521  mov     rdx, rbx
0x18001b524  mov     rcx, [rbx+0D40h]; pcbe
0x18001b52b  call    ??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z; Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))
0x18001b530  nop
0x18001b531  lea     rcx, [rsp+0D60h+var_D30]
0x18001b536  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b53b  nop
0x18001b53c  lea     rcx, [rsp+0D60h+var_D10]
0x18001b541  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b546  mov     eax, edi
0x18001b548  mov     rcx, [rbp+0C60h+var_10]
0x18001b54f  xor     rcx, rsp; StackCookie
0x18001b552  call    __security_check_cookie
0x18001b557  lea     r11, [rsp+0D60h+var_s0]
0x18001b55f  mov     rbx, [r11+18h]
0x18001b563  mov     rdi, [r11+20h]
0x18001b567  mov     rsp, r11
0x18001b56a  pop     rbp
0x18001b56b  retn
```
