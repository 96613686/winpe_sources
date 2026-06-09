# DllGetClassObject

- ea: `0x18000f020`
- end: `0x18000f1ed`
- name: `DllGetClassObject`
- size: `461`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032b9c`

## callees

- `0x18000a420`
- `0x18000edd0`
- `0x18000f020`
- `0x1800140d4`
- `0x180022068`
- `0x1800223d0`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800bd010`

## import_xrefs

- `ole32!ComPs_NdrDllGetClassObject` at `0x18000f110`
- `ole32!ComPs_NdrDllGetClassObject` at `0x18000f146`
- `ole32!ComPs_NdrDllGetClassObject` at `0x18000f18f`
- `ole32!ComPs_NdrDllGetClassObject` at `0x18000f110`
- `ole32!ComPs_NdrDllGetClassObject` at `0x18000f146`
- `ole32!ComPs_NdrDllGetClassObject` at `0x18000f18f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v7; // rax
  CFTm *v8; // rax
  CFTm *v9; // rdi
  HRESULT v10; // ebx
  __int64 ****v11; // rcx
  __int64 **v12; // rcx
  int ClassObject; // eax
  HRESULT v14; // edx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v7 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_DTCTM.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_DTCTM.Data1 )
    v7 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_DTCTM.Data4;
  if ( v7 )
  {
    if ( (int)UisDllGetClassObject(rclsid, riid, ppv) >= 0
      || (int)ComPs_NdrDllGetClassObject(
                rclsid,
                riid,
                ppv,
                &TcpCm_aProxyFileList,
                &TcpCm_CLSID_PSFactoryBuffer,
                TcpCm_gPFactory) >= 0
      || (int)ComPs_NdrDllGetClassObject(rclsid, riid, ppv, &Sm_aProxyFileList, &Sm_CLSID_PSFactoryBuffer, Sm_gPFactory) >= 0 )
    {
      return 0;
    }
    v11 = TipConn_aProxyFileList[1];
    v12 = *v11 ? **v11 : 0LL;
    if ( (int)ComPs_NdrDllGetClassObject(rclsid, riid, ppv, &TipConn_aProxyFileList, v12, TipConn_gPFactory) >= 0
      || (int)XaTmDllGetClassObject(rclsid, riid, ppv) >= 0
      || (int)MapGwTxDllGetClassObject(rclsid, riid, ppv) >= 0 )
    {
      return 0;
    }
    else
    {
      ClassObject = MapTxDllGetClassObject(rclsid, riid, ppv);
      v14 = -2147221231;
      if ( ClassObject >= 0 )
        return 0;
      return v14;
    }
  }
  else
  {
    v8 = (CFTm *)operator new(0x48u);
    if ( v8 )
      v9 = CFTm::CFTm(v8);
    else
      v9 = 0;
    if ( v9 )
    {
      v10 = (**(__int64 (__fastcall ***)(CFTm *, const IID *const, LPVOID *))v9)(v9, riid, ppv);
      if ( v10 < 0 )
        operator delete(v9);
      return v10;
    }
    else
    {
      return -2147024882;
    }
  }
}

```

## disassembly

```asm
0x18000f020  mov     [rsp+arg_0], rbx
0x18000f025  mov     [rsp+arg_8], rsi
0x18000f02a  push    rdi
0x18000f02b  sub     rsp, 30h
0x18000f02f  mov     rbx, r8
0x18000f032  mov     rsi, rdx
0x18000f035  mov     rdi, rcx
0x18000f038  test    r8, r8
0x18000f03b  jnz     short loc_18000F047
0x18000f03d  mov     eax, 80070057h
0x18000f042  jmp     loc_18000F1DD
0x18000f047  mov     qword ptr [r8], 0
0x18000f04e  mov     rax, [rcx]
0x18000f051  sub     rax, qword ptr cs:CLSID_DTCTM.Data1
0x18000f058  jnz     short loc_18000F065
0x18000f05a  mov     rax, [rcx+8]
0x18000f05e  sub     rax, qword ptr cs:CLSID_DTCTM.Data4
0x18000f065  test    rax, rax
0x18000f068  jnz     short loc_18000F0DB
0x18000f06a  mov     ecx, 48h ; 'H'; Size
0x18000f06f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f074  mov     [rsp+38h+arg_10], rax
0x18000f079  test    rax, rax
0x18000f07c  jz      short loc_18000F08B
0x18000f07e  mov     rcx, rax; this
0x18000f081  call    ??0CFTm@@QEAA@XZ; CFTm::CFTm(void)
0x18000f086  mov     rdi, rax
0x18000f089  jmp     short loc_18000F08D
0x18000f08b  xor     edi, edi
0x18000f08d  test    rdi, rdi
0x18000f090  jnz     short loc_18000F0A7
0x18000f092  mov     eax, 8007000Eh
0x18000f097  mov     rbx, [rsp+38h+arg_0]
0x18000f09c  mov     rsi, [rsp+38h+arg_8]
0x18000f0a1  add     rsp, 30h
0x18000f0a5  pop     rdi
0x18000f0a6  retn
0x18000f0a7  mov     rax, [rdi]
0x18000f0aa  mov     r8, rbx
0x18000f0ad  mov     rdx, rsi
0x18000f0b0  mov     rcx, rdi
0x18000f0b3  mov     rax, [rax]
0x18000f0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0bb  mov     ebx, eax
0x18000f0bd  test    eax, eax
0x18000f0bf  jns     short loc_18000F0C9
0x18000f0c1  mov     rcx, rdi; Block
0x18000f0c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f0c9  mov     eax, ebx
0x18000f0cb  mov     rbx, [rsp+38h+arg_0]
0x18000f0d0  mov     rsi, [rsp+38h+arg_8]
0x18000f0d5  add     rsp, 30h
0x18000f0d9  pop     rdi
0x18000f0da  retn
0x18000f0db  call    UisDllGetClassObject
0x18000f0e0  test    eax, eax
0x18000f0e2  jns     loc_18000F1DB
0x18000f0e8  lea     rax, TcpCm_gPFactory
0x18000f0ef  mov     [rsp+38h+var_10], rax
0x18000f0f4  lea     rax, TcpCm_CLSID_PSFactoryBuffer
0x18000f0fb  mov     [rsp+38h+var_18], rax
0x18000f100  lea     r9, TcpCm_aProxyFileList
0x18000f107  mov     r8, rbx
0x18000f10a  mov     rdx, rsi
0x18000f10d  mov     rcx, rdi
0x18000f110  call    cs:__imp_ComPs_NdrDllGetClassObject
0x18000f116  test    eax, eax
0x18000f118  jns     loc_18000F1DB
0x18000f11e  lea     rax, Sm_gPFactory
0x18000f125  mov     [rsp+38h+var_10], rax
0x18000f12a  lea     rax, Sm_CLSID_PSFactoryBuffer
0x18000f131  mov     [rsp+38h+var_18], rax
0x18000f136  lea     r9, Sm_aProxyFileList
0x18000f13d  mov     r8, rbx
0x18000f140  mov     rdx, rsi
0x18000f143  mov     rcx, rdi
0x18000f146  call    cs:__imp_ComPs_NdrDllGetClassObject
0x18000f14c  test    eax, eax
0x18000f14e  jns     loc_18000F1DB
0x18000f154  mov     rax, cs:TipConn_aProxyFileList
0x18000f15b  mov     rcx, [rax+8]
0x18000f15f  mov     rax, [rcx]
0x18000f162  test    rax, rax
0x18000f165  jz      short loc_18000F16C
0x18000f167  mov     rcx, [rax]
0x18000f16a  jmp     short loc_18000F16E
0x18000f16c  xor     ecx, ecx
0x18000f16e  lea     rax, TipConn_gPFactory
0x18000f175  mov     [rsp+38h+var_10], rax
0x18000f17a  mov     [rsp+38h+var_18], rcx
0x18000f17f  lea     r9, TipConn_aProxyFileList
0x18000f186  mov     r8, rbx
0x18000f189  mov     rdx, rsi
0x18000f18c  mov     rcx, rdi
0x18000f18f  call    cs:__imp_ComPs_NdrDllGetClassObject
0x18000f195  test    eax, eax
0x18000f197  jns     short loc_18000F1DB
0x18000f199  mov     r8, rbx
0x18000f19c  mov     rdx, rsi
0x18000f19f  mov     rcx, rdi
0x18000f1a2  call    XaTmDllGetClassObject
0x18000f1a7  test    eax, eax
0x18000f1a9  jns     short loc_18000F1DB
0x18000f1ab  mov     r8, rbx
0x18000f1ae  mov     rdx, rsi
0x18000f1b1  mov     rcx, rdi
0x18000f1b4  call    MapGwTxDllGetClassObject
0x18000f1b9  test    eax, eax
0x18000f1bb  jns     short loc_18000F1DB
0x18000f1bd  mov     r8, rbx
0x18000f1c0  mov     rdx, rsi
0x18000f1c3  mov     rcx, rdi
0x18000f1c6  call    MapTxDllGetClassObject
0x18000f1cb  mov     edx, 80040111h
0x18000f1d0  xor     ecx, ecx
0x18000f1d2  test    eax, eax
0x18000f1d4  cmovns  edx, ecx
0x18000f1d7  mov     eax, edx
0x18000f1d9  jmp     short loc_18000F1DD
0x18000f1db  xor     eax, eax
0x18000f1dd  mov     rbx, [rsp+38h+arg_0]
0x18000f1e2  mov     rsi, [rsp+38h+arg_8]
0x18000f1e7  add     rsp, 30h
0x18000f1eb  pop     rdi
0x18000f1ec  retn
```
