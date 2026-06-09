# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ClientDriver>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x180007bfc`
- end: `0x180007d7a`
- name: `??$GetAllObjectsInner@VClientDriver@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
- size: `382`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c5e0`

## callees

- `0x1800027c0`
- `0x180002bcc`
- `0x1800032e4`
- `0x180007048`
- `0x180007bfc`
- `0x180008450`
- `0x180008478`
- `0x1800085d8`
- `0x180008db0`
- `0x180009028`

## import_xrefs

- `NetSetupApi!NetSetupGetObjects` at `0x180007c7c`
- `NetSetupApi!NetSetupGetObjects` at `0x180007c7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ClientDriver>(
        _QWORD *a1,
        __int64 *a2)
{
  int Objects; // eax
  _QWORD *v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // edi
  char *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  char *pExceptionObject; // [rsp+58h] [rbp-11h] BYREF
  int v15; // [rsp+60h] [rbp-9h]
  unsigned int v16; // [rsp+68h] [rbp-1h] BYREF
  __int64 v17; // [rsp+70h] [rbp+7h]
  __int64 *v18; // [rsp+78h] [rbp+Fh]
  unsigned int v19; // [rsp+80h] [rbp+17h] BYREF
  __int64 v20; // [rsp+88h] [rbp+1Fh] BYREF

  v18 = a2;
  v15 = 0;
  v19 = 0;
  v20 = 0;
  Objects = NetSetupGetObjects(*a1, 6, 0, 0, 0, 0, 0, 0, &v19, &v20);
  if ( Objects < 0 )
  {
    LODWORD(pExceptionObject) = Objects;
    throw (long *)&pExceptionObject;
  }
  v16 = v19;
  v17 = v20;
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(a2);
  v15 = 1;
  v6 = v19;
  pExceptionObject = (char *)v19;
  if ( v19 > (unsigned __int64)((a2[2] - *a2) >> 3) )
  {
    std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(v5, &pExceptionObject);
    v6 = v19;
  }
  v7 = 0;
  if ( v6 )
  {
    do
    {
      v8 = (char *)operator new(0x28u);
      pExceptionObject = v8;
      v9 = 32LL * v7;
      v10 = v20;
      v11 = *(_DWORD *)(v9 + v20);
      *(_QWORD *)v8 = a1;
      *((_QWORD *)v8 + 1) = 0;
      *((_DWORD *)v8 + 4) = v11;
      *(_OWORD *)(v8 + 20) = *(_OWORD *)(v9 + v10 + 4);
      pExceptionObject = v8;
      v12 = a2[1];
      if ( v12 == a2[2] )
        std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(
          a2,
          v12,
          (__int64 *)&pExceptionObject);
      else
        std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(
          (__int64)a2,
          (__int64 *)&pExceptionObject);
      std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(&pExceptionObject);
      ++v7;
    }
    while ( v7 < v19 );
  }
  NetSetup2::details::AutoFreeObjects::~AutoFreeObjects((NetSetup2::details::AutoFreeObjects *)&v16);
  return a2;
}

```

## disassembly

```asm
0x180007bfc  mov     r11, rsp
0x180007bff  mov     [r11+18h], rbx
0x180007c03  push    rbp
0x180007c04  push    rsi
0x180007c05  push    rdi
0x180007c06  lea     rbp, [r11-47h]
0x180007c0a  sub     rsp, 90h
0x180007c11  mov     rax, cs:__security_cookie
0x180007c18  xor     rax, rsp
0x180007c1b  mov     [rbp+3Fh+var_18], rax
0x180007c1f  mov     rbx, rdx
0x180007c22  mov     rsi, rcx
0x180007c25  mov     [rbp+3Fh+var_30], rdx
0x180007c29  mov     [rbp+3Fh+var_48], 0
0x180007c30  mov     [rbp+3Fh+var_28], 0
0x180007c37  mov     [rbp+3Fh+var_20], 0
0x180007c3f  lea     rax, [rbp+3Fh+var_20]
0x180007c43  mov     [r11-60h], rax
0x180007c47  lea     rax, [rbp+3Fh+var_28]
0x180007c4b  mov     [r11-68h], rax
0x180007c4f  mov     qword ptr [r11-70h], 0
0x180007c57  mov     dword ptr [rsp+30h], 0
0x180007c5f  mov     qword ptr [r11-80h], 0
0x180007c67  mov     dword ptr [rsp+20h], 0
0x180007c6f  xor     r9d, r9d
0x180007c72  xor     r8d, r8d
0x180007c75  lea     edx, [r9+6]
0x180007c79  mov     rcx, [rcx]
0x180007c7c  call    cs:__imp_NetSetupGetObjects
0x180007c82  test    eax, eax
0x180007c84  jns     short loc_180007C9A
0x180007c86  mov     dword ptr [rbp+3Fh+pExceptionObject], eax
0x180007c89  lea     rdx, _TI1J; pThrowInfo
0x180007c90  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180007c94  call    _CxxThrowException_0
0x180007c9a  mov     eax, [rbp+3Fh+var_28]
0x180007c9d  mov     [rbp+3Fh+var_40], eax
0x180007ca0  mov     rax, [rbp+3Fh+var_20]
0x180007ca4  mov     [rbp+3Fh+var_38], rax
0x180007ca8  mov     rcx, rbx
0x180007cab  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x180007cb0  mov     [rbp+3Fh+var_48], 1
0x180007cb7  mov     edx, [rbp+3Fh+var_28]
0x180007cba  mov     [rbp+3Fh+pExceptionObject], rdx
0x180007cbe  mov     rax, [rbx+10h]
0x180007cc2  sub     rax, [rbx]
0x180007cc5  sar     rax, 3
0x180007cc9  cmp     rdx, rax
0x180007ccc  jbe     short loc_180007CDA
0x180007cce  lea     rdx, [rbp+3Fh+pExceptionObject]
0x180007cd2  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(unsigned __int64 &)
0x180007cd7  mov     edx, [rbp+3Fh+var_28]
0x180007cda  xor     edi, edi
0x180007cdc  test    edx, edx
0x180007cde  jz      short loc_180007D4E
0x180007ce0  mov     ecx, 28h ; '('; Size
0x180007ce5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007cea  mov     r8, rax
0x180007ced  mov     [rbp+3Fh+pExceptionObject], rax
0x180007cf1  mov     edx, edi
0x180007cf3  shl     rdx, 5
0x180007cf7  mov     rcx, [rbp+3Fh+var_20]
0x180007cfb  mov     eax, [rdx+rcx]
0x180007cfe  mov     [r8], rsi
0x180007d01  mov     qword ptr [r8+8], 0
0x180007d09  mov     [r8+10h], eax
0x180007d0d  movups  xmm0, xmmword ptr [rdx+rcx+4]
0x180007d12  movdqu  xmmword ptr [r8+14h], xmm0
0x180007d18  mov     [rbp+3Fh+pExceptionObject], r8
0x180007d1c  mov     rdx, [rbx+8]
0x180007d20  mov     rcx, rbx
0x180007d23  cmp     rdx, [rbx+10h]
0x180007d27  jz      short loc_180007D34
0x180007d29  lea     rdx, [rbp+3Fh+pExceptionObject]
0x180007d2d  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(std::unique_ptr<NetSetup2::ReflectedProperty> &&)
0x180007d32  jmp     short loc_180007D3E
0x180007d34  lea     r8, [rbp+3Fh+pExceptionObject]
0x180007d38  call    ??$_Emplace_reallocate@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(std::unique_ptr<NetSetup2::NetworkInterface> * const,std::unique_ptr<NetSetup2::NetworkInterface> &&)
0x180007d3d  nop
0x180007d3e  lea     rcx, [rbp+3Fh+pExceptionObject]
0x180007d42  call    ??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(void)
0x180007d47  inc     edi
0x180007d49  cmp     edi, [rbp+3Fh+var_28]
0x180007d4c  jb      short loc_180007CE0
0x180007d4e  lea     rcx, [rbp+3Fh+var_40]; this
0x180007d52  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x180007d57  mov     rax, rbx
0x180007d5a  mov     rcx, [rbp+3Fh+var_18]
0x180007d5e  xor     rcx, rsp; StackCookie
0x180007d61  call    __security_check_cookie
0x180007d66  mov     rbx, [rsp+0A0h+arg_10]
0x180007d6e  add     rsp, 90h
0x180007d75  pop     rdi
0x180007d76  pop     rsi
0x180007d77  pop     rbp
0x180007d78  retn
```
