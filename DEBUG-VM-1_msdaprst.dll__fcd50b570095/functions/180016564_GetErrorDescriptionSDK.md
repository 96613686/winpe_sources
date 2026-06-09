# GetErrorDescriptionSDK

- ea: `0x180016564`
- end: `0x1800166a8`
- name: `GetErrorDescriptionSDK`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015b78`

## callees

- `0x18000266c`
- `0x180016564`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800165c4`
- `ole32!CoCreateInstance` at `0x1800165c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetErrorDescriptionSDK(unsigned int a1)
{
  __int64 v2; // rbx
  LPVOID ppv; // [rsp+40h] [rbp-9h] BYREF
  __int64 v5; // [rsp+48h] [rbp-1h] BYREF
  __int64 v6; // [rsp+50h] [rbp+7h] BYREF
  __int64 v7; // [rsp+58h] [rbp+Fh] BYREF
  _OWORD v8[3]; // [rsp+60h] [rbp+17h] BYREF

  memset(v8, 0, 44);
  ppv = 0;
  v7 = 0;
  v5 = 0;
  v6 = 0;
  if ( CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorRecords, &ppv) < 0
    || (*(GUID *)((char *)v8 + 8) = CLSID_MSPersist,
        *(_QWORD *)&v8[0] = a1,
        memset((char *)&v8[1] + 8, 0, 20),
        (*(int (__fastcall **)(LPVOID, _OWORD *, __int64, _QWORD, _QWORD, _DWORD))(*(_QWORD *)ppv + 24LL))(
          ppv,
          v8,
          0x10000000,
          0,
          0,
          0) < 0)
    || (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IErrorInfo, &v5) < 0
    || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 40LL))(v5, &v6) < 0 )
  {
    v2 = 0;
  }
  else
  {
    v2 = v6;
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v5);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v7);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
  return v2;
}

```

## disassembly

```asm
0x180016564  mov     [rsp-8+arg_8], rbx
0x180016569  push    rbp
0x18001656a  lea     rbp, [rsp-57h]
0x18001656f  sub     rsp, 0A0h
0x180016576  mov     rax, cs:__security_cookie
0x18001657d  xor     rax, rsp
0x180016580  mov     [rbp+57h+var_10], rax
0x180016584  mov     ebx, ecx
0x180016586  xorps   xmm0, xmm0
0x180016589  xor     eax, eax
0x18001658b  movups  [rbp+57h+var_40], xmm0
0x18001658f  movups  [rbp+57h+var_30], xmm0
0x180016593  movups  [rbp+57h+var_30+0Ch], xmm0
0x180016597  mov     [rbp+57h+var_60], rax
0x18001659b  mov     [rbp+57h+var_48], rax
0x18001659f  mov     [rbp+57h+var_58], rax
0x1800165a3  mov     [rbp+57h+var_50], rax
0x1800165a7  lea     rax, [rbp+57h+var_60]
0x1800165ab  mov     [rsp+0A0h+ppv], rax; ppv
0x1800165b0  lea     r9, IID_IErrorRecords; riid
0x1800165b7  xor     edx, edx; pUnkOuter
0x1800165b9  lea     r8d, [rdx+1]; dwClsContext
0x1800165bd  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x1800165c4  call    cs:__imp_CoCreateInstance
0x1800165ca  test    eax, eax
0x1800165cc  js      loc_180016669
0x1800165d2  movups  xmm0, xmmword ptr cs:?CLSID_MSPersist@@3U_GUID@@B.Data1; _GUID const CLSID_MSPersist ...
0x1800165d9  movdqu  [rbp+57h+var_40+8], xmm0
0x1800165de  mov     [rbp+57h+var_18], 0
0x1800165e5  mov     dword ptr [rbp+57h+var_40+4], 0
0x1800165ec  mov     dword ptr [rbp+57h+var_40], ebx
0x1800165ef  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800165f6  movdqu  [rbp+57h+var_30+8], xmm0
0x1800165fb  mov     rcx, [rbp+57h+var_60]
0x1800165ff  mov     rax, [rcx]
0x180016602  mov     [rsp+0A0h+var_78], 0
0x18001660a  mov     [rsp+0A0h+ppv], 0
0x180016613  xor     r9d, r9d
0x180016616  mov     r8d, 10000000h
0x18001661c  lea     rdx, [rbp+57h+var_40]
0x180016620  mov     rax, [rax+18h]
0x180016624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016629  test    eax, eax
0x18001662b  js      short loc_180016669
0x18001662d  mov     rcx, [rbp+57h+var_60]
0x180016631  mov     rax, [rcx]
0x180016634  lea     r8, [rbp+57h+var_58]
0x180016638  lea     rdx, IID_IErrorInfo
0x18001663f  mov     rax, [rax]
0x180016642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016647  test    eax, eax
0x180016649  js      short loc_180016669
0x18001664b  mov     rcx, [rbp+57h+var_58]
0x18001664f  mov     rax, [rcx]
0x180016652  lea     rdx, [rbp+57h+var_50]
0x180016656  mov     rax, [rax+28h]
0x18001665a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001665f  test    eax, eax
0x180016661  js      short loc_180016669
0x180016663  mov     rbx, [rbp+57h+var_50]
0x180016667  jmp     short loc_18001666B
0x180016669  xor     ebx, ebx
0x18001666b  lea     rcx, [rbp+57h+var_58]
0x18001666f  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180016674  nop
0x180016675  lea     rcx, [rbp+57h+var_48]
0x180016679  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001667e  nop
0x18001667f  lea     rcx, [rbp+57h+var_60]
0x180016683  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180016688  mov     rax, rbx
0x18001668b  mov     rcx, [rbp+57h+var_10]
0x18001668f  xor     rcx, rsp; StackCookie
0x180016692  call    __security_check_cookie
0x180016697  mov     rbx, [rsp+0A0h+arg_8]
0x18001669f  add     rsp, 0A0h
0x1800166a6  pop     rbp
0x1800166a7  retn
```
