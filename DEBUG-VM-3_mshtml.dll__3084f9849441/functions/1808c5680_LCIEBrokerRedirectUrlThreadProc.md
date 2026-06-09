# _LCIEBrokerRedirectUrlThreadProc

- ea: `0x1808c5680`
- end: `0x1808c5948`
- name: `_LCIEBrokerRedirectUrlThreadProc`
- size: `712`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18076a3f0`
- `0x1808c1410`
- `0x1808c5680`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1808c5756`
- `KERNEL32!GetCurrentProcessId` at `0x1808c5756`
- `USER32!AllowSetForegroundWindow` at `0x1808c5736`
- `USER32!AllowSetForegroundWindow` at `0x1808c5813`
- `USER32!AllowSetForegroundWindow` at `0x1808c5736`
- `USER32!AllowSetForegroundWindow` at `0x1808c5813`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1808c57db`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1808c57db`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808c577c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1808c577c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c56d4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c57af`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c56d4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1808c57af`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1808c5912`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1808c5912`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1808c56af`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1808c56af`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808c5785`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808c5785`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808c5764`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1808c5764`

## pseudocode

```c
__int64 __fastcall LCIEBrokerRedirectUrlThreadProc(_QWORD *Parameter)
{
  unsigned int v2; // edx
  IStream *v3; // rcx
  HRESULT InterfaceAndReleaseStream; // eax
  DWORD v5; // edi
  char Integrity; // al
  struct IE_GLOBAL_THREAD_STATE *v7; // rax
  IStream *v8; // rcx
  __int128 v9; // xmm0
  unsigned int v10; // ecx
  int v11; // edi
  DWORD dwProcessId; // [rsp+30h] [rbp-59h] BYREF
  struct IEUserBroker *v14; // [rsp+38h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-49h] BYREF
  __int64 v16; // [rsp+48h] [rbp-41h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  LPVOID v18; // [rsp+58h] [rbp-31h] BYREF
  __int128 v19; // [rsp+60h] [rbp-29h] BYREF
  __int64 v20; // [rsp+70h] [rbp-19h]
  _DWORD v21[13]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v22; // [rsp+B4h] [rbp+2Bh]

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    v3 = (IStream *)Parameter[3];
    ppv = 0;
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v3, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    Parameter[3] = 0;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      v20 = 0;
      v19 = 0;
      LOWORD(v19) = 11;
      WORD4(v19) = -1;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v19, 0);
      v5 = -1;
      AllowSetForegroundWindow(0xFFFFFFFF);
      memset_0(v21, 0, 0x44u);
      v21[0] = *(_DWORD *)Parameter;
      v21[1] = *((_DWORD *)Parameter + 1);
      v21[6] = GetCurrentProcessId();
      Integrity = IsoGetIntegrity(1);
      v21[8] = 0;
      v21[7] = Integrity & 0x7F;
      v21[10] = IEConfiguration_GetDWORD(536870929);
      v7 = GlobalThreadState();
      v8 = (IStream *)Parameter[4];
      v9 = *(_OWORD *)v7;
      v18 = 0;
      v22 = v9;
      if ( v8 )
      {
        CoGetInterfaceAndReleaseStream(v8, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &v18);
        Parameter[4] = 0;
      }
      v10 = *((_DWORD *)Parameter + 4);
      v21[4] = 1;
      v17 = 0;
      v14 = 0;
      if ( (int)CoCreateUserBrokerForThread(v10, &v14) >= 0 )
      {
        dwProcessId = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v14 + 24LL))(
          v14,
          0,
          0,
          &dwProcessId);
        if ( dwProcessId )
          v5 = dwProcessId;
        AllowSetForegroundWindow(v5);
        v16 = 0;
        v11 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v14 + 48LL))(
                v14,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v16);
        if ( v11 >= 0 )
        {
          v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IShdocvwBroker, &v17);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v11 >= 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, LPVOID))(*(_QWORD *)v17 + 24LL))(
            v17,
            Parameter[1],
            *((unsigned int *)Parameter + 1),
            v21,
            v18);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      WORD4(v19) = 0;
      g_pfn_IUnknown_Exec((_DWORD)ppv, (unsigned int)&CGID_DocHostCmdPriv, 15, 0, (__int64)&v19, 0);
      if ( v18 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
  if ( Parameter )
    LCIESRedirectUrlInfo::`scalar deleting destructor'((LCIESRedirectUrlInfo *)Parameter, v2);
  return 0;
}

```

## disassembly

```asm
0x1808c5680  mov     [rsp-8+arg_8], rbx
0x1808c5685  mov     [rsp-8+arg_10], rdi
0x1808c568a  push    rbp
0x1808c568b  lea     rbp, [rsp-57h]
0x1808c5690  sub     rsp, 0E0h
0x1808c5697  mov     rax, cs:__security_cookie
0x1808c569e  xor     rax, rsp
0x1808c56a1  mov     [rbp+57h+var_10], rax
0x1808c56a5  mov     rbx, rcx
0x1808c56a8  mov     edx, 2; dwCoInit
0x1808c56ad  xor     ecx, ecx; pvReserved
0x1808c56af  call    cs:__imp_CoInitializeEx
0x1808c56b5  test    eax, eax
0x1808c56b7  js      loc_1808C5918
0x1808c56bd  mov     rcx, [rbx+18h]; pStm
0x1808c56c1  lea     r8, [rbp+57h+ppv]; ppv
0x1808c56c5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; iid
0x1808c56cc  mov     [rbp+57h+ppv], 0
0x1808c56d4  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808c56da  mov     qword ptr [rbx+18h], 0
0x1808c56e2  test    eax, eax
0x1808c56e4  js      loc_1808C5912
0x1808c56ea  mov     rcx, [rbp+57h+ppv]
0x1808c56ee  lea     rdx, CGID_DocHostCmdPriv
0x1808c56f5  xor     eax, eax
0x1808c56f7  mov     [rsp+0E0h+var_B8], 0
0x1808c5700  mov     [rbp+57h+var_70], rax
0x1808c5704  xorps   xmm0, xmm0
0x1808c5707  mov     eax, 0Bh
0x1808c570c  xor     r9d, r9d
0x1808c570f  movups  [rbp+57h+var_80], xmm0
0x1808c5713  mov     word ptr [rbp+57h+var_80], ax
0x1808c5717  or      eax, 0FFFFFFFFh
0x1808c571a  mov     word ptr [rbp+57h+var_80+8], ax
0x1808c571e  lea     rax, [rbp+57h+var_80]
0x1808c5722  lea     r8d, [r9+0Fh]
0x1808c5726  mov     [rsp+0E0h+var_C0], rax
0x1808c572b  call    cs:g_pfn_IUnknown_Exec
0x1808c5731  or      edi, 0FFFFFFFFh
0x1808c5734  mov     ecx, edi; dwProcessId
0x1808c5736  call    cs:__imp_AllowSetForegroundWindow
0x1808c573c  xor     edx, edx; Val
0x1808c573e  lea     rcx, [rbp+57h+var_60]; void *
0x1808c5742  lea     r8d, [rdx+44h]; Size
0x1808c5746  call    memset_0
0x1808c574b  mov     eax, [rbx]
0x1808c574d  mov     [rbp+57h+var_60], eax
0x1808c5750  mov     eax, [rbx+4]
0x1808c5753  mov     [rbp+57h+var_5C], eax
0x1808c5756  call    cs:__imp_GetCurrentProcessId
0x1808c575c  mov     ecx, 1
0x1808c5761  mov     [rbp+57h+var_48], eax
0x1808c5764  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1808c576a  mov     ecx, 20000011h
0x1808c576f  mov     [rbp+57h+var_40], 0
0x1808c5776  and     eax, 7Fh
0x1808c5779  mov     [rbp+57h+var_44], eax
0x1808c577c  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1808c5782  mov     [rbp+57h+var_38], eax
0x1808c5785  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808c578b  mov     rcx, [rbx+20h]; pStm
0x1808c578f  movups  xmm0, xmmword ptr [rax]
0x1808c5792  mov     [rbp+57h+var_88], 0
0x1808c579a  movdqu  [rbp+57h+var_2C], xmm0
0x1808c579f  test    rcx, rcx
0x1808c57a2  jz      short loc_1808C57BD
0x1808c57a4  lea     r8, [rbp+57h+var_88]; ppv
0x1808c57a8  lea     rdx, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; iid
0x1808c57af  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1808c57b5  mov     qword ptr [rbx+20h], 0
0x1808c57bd  mov     ecx, [rbx+10h]
0x1808c57c0  lea     rdx, [rbp+57h+var_A8]
0x1808c57c4  mov     [rbp+57h+var_50], 1
0x1808c57cb  mov     [rbp+57h+var_90], 0
0x1808c57d3  mov     [rbp+57h+var_A8], 0
0x1808c57db  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1808c57e1  test    eax, eax
0x1808c57e3  js      loc_1808C58C1
0x1808c57e9  mov     rcx, [rbp+57h+var_A8]
0x1808c57ed  lea     r9, [rbp+57h+dwProcessId]
0x1808c57f1  mov     [rbp+57h+dwProcessId], 0
0x1808c57f8  xor     r8d, r8d
0x1808c57fb  xor     edx, edx
0x1808c57fd  mov     rax, [rcx]
0x1808c5800  mov     rax, [rax+18h]
0x1808c5804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c5809  mov     eax, [rbp+57h+dwProcessId]
0x1808c580c  test    eax, eax
0x1808c580e  cmovnz  edi, eax
0x1808c5811  mov     ecx, edi; dwProcessId
0x1808c5813  call    cs:__imp_AllowSetForegroundWindow
0x1808c5819  mov     rcx, [rbp+57h+var_A8]
0x1808c581d  lea     r9, [rbp+57h+var_98]
0x1808c5821  mov     [rbp+57h+var_98], 0
0x1808c5829  lea     r8, IID_IUnknown
0x1808c5830  lea     rdx, CLSID_CShdocvwBroker
0x1808c5837  mov     rax, [rcx]
0x1808c583a  mov     rax, [rax+30h]
0x1808c583e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c5843  mov     edi, eax
0x1808c5845  test    eax, eax
0x1808c5847  js      short loc_1808C5875
0x1808c5849  mov     rcx, [rbp+57h+var_98]
0x1808c584d  lea     r8, [rbp+57h+var_90]
0x1808c5851  lea     rdx, IID_IShdocvwBroker
0x1808c5858  mov     rax, [rcx]
0x1808c585b  mov     rax, [rax]
0x1808c585e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c5863  mov     rcx, [rbp+57h+var_98]
0x1808c5867  mov     edi, eax
0x1808c5869  mov     rax, [rcx]
0x1808c586c  mov     rax, [rax+10h]
0x1808c5870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c5875  mov     rcx, [rbp+57h+var_A8]
0x1808c5879  mov     rax, [rcx]
0x1808c587c  mov     rax, [rax+10h]
0x1808c5880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c5885  test    edi, edi
0x1808c5887  js      short loc_1808C58C1
0x1808c5889  mov     r10, [rbp+57h+var_90]
0x1808c588d  lea     r9, [rbp+57h+var_60]
0x1808c5891  mov     rcx, [rbp+57h+var_88]
0x1808c5895  mov     r8d, [rbx+4]
0x1808c5899  mov     rdx, [rbx+8]
0x1808c589d  mov     rax, [r10]
0x1808c58a0  mov     [rsp+0E0h+var_C0], rcx
0x1808c58a5  mov     rcx, r10
0x1808c58a8  mov     rax, [rax+18h]
0x1808c58ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c58b1  mov     rcx, [rbp+57h+var_90]
0x1808c58b5  mov     rax, [rcx]
0x1808c58b8  mov     rax, [rax+10h]
0x1808c58bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c58c1  mov     rcx, [rbp+57h+ppv]
0x1808c58c5  lea     rdx, CGID_DocHostCmdPriv
0x1808c58cc  xor     eax, eax
0x1808c58ce  xor     r9d, r9d
0x1808c58d1  mov     [rsp+0E0h+var_B8], rax
0x1808c58d6  mov     word ptr [rbp+57h+var_80+8], ax
0x1808c58da  lea     rax, [rbp+57h+var_80]
0x1808c58de  mov     [rsp+0E0h+var_C0], rax
0x1808c58e3  lea     r8d, [r9+0Fh]
0x1808c58e7  call    cs:g_pfn_IUnknown_Exec
0x1808c58ed  mov     rcx, [rbp+57h+var_88]
0x1808c58f1  test    rcx, rcx
0x1808c58f4  jz      short loc_1808C5902
0x1808c58f6  mov     rax, [rcx]
0x1808c58f9  mov     rax, [rax+10h]
0x1808c58fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c5902  mov     rcx, [rbp+57h+ppv]
0x1808c5906  mov     rax, [rcx]
0x1808c5909  mov     rax, [rax+10h]
0x1808c590d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c5912  call    cs:__imp_CoUninitialize
0x1808c5918  test    rbx, rbx
0x1808c591b  jz      short loc_1808C5925
0x1808c591d  mov     rcx, rbx; this
0x1808c5920  call    ??_GLCIESRedirectUrlInfo@@QEAAPEAXI@Z; LCIESRedirectUrlInfo::`scalar deleting destructor'(uint)
0x1808c5925  xor     eax, eax
0x1808c5927  mov     rcx, [rbp+57h+var_10]
0x1808c592b  xor     rcx, rsp; StackCookie
0x1808c592e  call    __security_check_cookie
0x1808c5933  lea     r11, [rsp+0E0h+var_s0]
0x1808c593b  mov     rbx, [r11+18h]
0x1808c593f  mov     rdi, [r11+20h]
0x1808c5943  mov     rsp, r11
0x1808c5946  pop     rbp
0x1808c5947  retn
```
