# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x180007d80`
- end: `0x180007ef8`
- name: `??$GetAllObjectsInner@VNetworkInterface@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
- size: `376`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, __int64, __int64, int, __int64, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c5e0`
- `0x18001eb14`
- `0x180022800`

## callees

- `0x1800027c0`
- `0x180002bcc`
- `0x1800032e4`
- `0x180007048`
- `0x180007d80`
- `0x180008450`
- `0x180008478`
- `0x1800085d8`
- `0x180008db0`
- `0x180009028`

## import_xrefs

- `NetSetupApi!NetSetupGetObjects` at `0x180007dfa`
- `NetSetupApi!NetSetupGetObjects` at `0x180007dfa`

## pseudocode

```c
__int64 *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  int Objects; // eax
  _QWORD *v10; // rcx
  unsigned int v11; // edx
  unsigned int v12; // edi
  char *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  char *pExceptionObject; // [rsp+58h] [rbp-11h] BYREF
  int v20; // [rsp+60h] [rbp-9h]
  unsigned int v21; // [rsp+68h] [rbp-1h] BYREF
  __int64 v22; // [rsp+70h] [rbp+7h]
  __int64 *v23; // [rsp+78h] [rbp+Fh]
  unsigned int v24; // [rsp+80h] [rbp+17h] BYREF
  __int64 v25; // [rsp+88h] [rbp+1Fh] BYREF

  v23 = a2;
  v20 = 0;
  v24 = 0;
  v25 = 0;
  Objects = NetSetupGetObjects(*a1, 2, 0, 0, a5, a4, a7, a6, &v24, &v25);
  if ( Objects < 0 )
  {
    LODWORD(pExceptionObject) = Objects;
    throw (long *)&pExceptionObject;
  }
  v21 = v24;
  v22 = v25;
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(a2);
  v20 = 1;
  v11 = v24;
  pExceptionObject = (char *)v24;
  if ( v24 > (unsigned __int64)((a2[2] - *a2) >> 3) )
  {
    std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(v10, &pExceptionObject);
    v11 = v24;
  }
  v12 = 0;
  if ( v11 )
  {
    do
    {
      v13 = (char *)operator new(0x28u);
      pExceptionObject = v13;
      v14 = 32LL * v12;
      v15 = v25;
      v16 = *(_DWORD *)(v14 + v25);
      *(_QWORD *)v13 = a1;
      *((_QWORD *)v13 + 1) = 0;
      *((_DWORD *)v13 + 4) = v16;
      *(_OWORD *)(v13 + 20) = *(_OWORD *)(v14 + v15 + 4);
      pExceptionObject = v13;
      v17 = a2[1];
      if ( v17 == a2[2] )
        std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(
          a2,
          v17,
          (__int64 *)&pExceptionObject);
      else
        std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(
          (__int64)a2,
          (__int64 *)&pExceptionObject);
      std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(&pExceptionObject);
      ++v12;
    }
    while ( v12 < v24 );
  }
  NetSetup2::details::AutoFreeObjects::~AutoFreeObjects((NetSetup2::details::AutoFreeObjects *)&v21);
  return a2;
}

```

## disassembly

```asm
0x180007d80  mov     r11, rsp
0x180007d83  mov     [r11+18h], rbx
0x180007d87  push    rbp
0x180007d88  push    rsi
0x180007d89  push    rdi
0x180007d8a  lea     rbp, [r11-47h]
0x180007d8e  sub     rsp, 90h
0x180007d95  mov     rax, cs:__security_cookie
0x180007d9c  xor     rax, rsp
0x180007d9f  mov     [rbp+3Fh+var_18], rax
0x180007da3  mov     rbx, rdx
0x180007da6  mov     rsi, rcx
0x180007da9  mov     [rbp+3Fh+var_30], rdx
0x180007dad  mov     rax, [rbp+3Fh+arg_28]
0x180007db1  mov     [rbp+3Fh+var_48], 0
0x180007db8  mov     [rbp+3Fh+var_28], 0
0x180007dbf  mov     [rbp+3Fh+var_20], 0
0x180007dc7  lea     rcx, [rbp+3Fh+var_20]
0x180007dcb  mov     [r11-60h], rcx
0x180007dcf  lea     rcx, [rbp+3Fh+var_28]
0x180007dd3  mov     [r11-68h], rcx
0x180007dd7  mov     [r11-70h], rax
0x180007ddb  mov     eax, [rbp+3Fh+arg_30]
0x180007dde  mov     [rsp+30h], eax
0x180007de2  mov     [r11-80h], r9
0x180007de6  mov     eax, [rbp+3Fh+arg_20]
0x180007de9  mov     [rsp+20h], eax
0x180007ded  xor     r9d, r9d
0x180007df0  xor     r8d, r8d
0x180007df3  lea     edx, [r9+2]
0x180007df7  mov     rcx, [rsi]
0x180007dfa  call    cs:__imp_NetSetupGetObjects
0x180007e00  test    eax, eax
0x180007e02  jns     short loc_180007E18
0x180007e04  mov     dword ptr [rbp+3Fh+pExceptionObject], eax
0x180007e07  lea     rdx, _TI1J; pThrowInfo
0x180007e0e  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180007e12  call    _CxxThrowException_0
0x180007e18  mov     eax, [rbp+3Fh+var_28]
0x180007e1b  mov     [rbp+3Fh+var_40], eax
0x180007e1e  mov     rax, [rbp+3Fh+var_20]
0x180007e22  mov     [rbp+3Fh+var_38], rax
0x180007e26  mov     rcx, rbx
0x180007e29  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x180007e2e  mov     [rbp+3Fh+var_48], 1
0x180007e35  mov     edx, [rbp+3Fh+var_28]
0x180007e38  mov     [rbp+3Fh+pExceptionObject], rdx
0x180007e3c  mov     rax, [rbx+10h]
0x180007e40  sub     rax, [rbx]
0x180007e43  sar     rax, 3
0x180007e47  cmp     rdx, rax
0x180007e4a  jbe     short loc_180007E58
0x180007e4c  lea     rdx, [rbp+3Fh+pExceptionObject]
0x180007e50  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(unsigned __int64 &)
0x180007e55  mov     edx, [rbp+3Fh+var_28]
0x180007e58  xor     edi, edi
0x180007e5a  test    edx, edx
0x180007e5c  jz      short loc_180007ECC
0x180007e5e  mov     ecx, 28h ; '('; Size
0x180007e63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007e68  mov     r8, rax
0x180007e6b  mov     [rbp+3Fh+pExceptionObject], rax
0x180007e6f  mov     edx, edi
0x180007e71  shl     rdx, 5
0x180007e75  mov     rcx, [rbp+3Fh+var_20]
0x180007e79  mov     eax, [rdx+rcx]
0x180007e7c  mov     [r8], rsi
0x180007e7f  mov     qword ptr [r8+8], 0
0x180007e87  mov     [r8+10h], eax
0x180007e8b  movups  xmm0, xmmword ptr [rdx+rcx+4]
0x180007e90  movdqu  xmmword ptr [r8+14h], xmm0
0x180007e96  mov     [rbp+3Fh+pExceptionObject], r8
0x180007e9a  mov     rdx, [rbx+8]
0x180007e9e  mov     rcx, rbx
0x180007ea1  cmp     rdx, [rbx+10h]
0x180007ea5  jz      short loc_180007EB2
0x180007ea7  lea     rdx, [rbp+3Fh+pExceptionObject]
0x180007eab  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(std::unique_ptr<NetSetup2::ReflectedProperty> &&)
0x180007eb0  jmp     short loc_180007EBC
0x180007eb2  lea     r8, [rbp+3Fh+pExceptionObject]
0x180007eb6  call    ??$_Emplace_reallocate@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(std::unique_ptr<NetSetup2::NetworkInterface> * const,std::unique_ptr<NetSetup2::NetworkInterface> &&)
0x180007ebb  nop
0x180007ebc  lea     rcx, [rbp+3Fh+pExceptionObject]
0x180007ec0  call    ??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(void)
0x180007ec5  inc     edi
0x180007ec7  cmp     edi, [rbp+3Fh+var_28]
0x180007eca  jb      short loc_180007E5E
0x180007ecc  lea     rcx, [rbp+3Fh+var_40]; this
0x180007ed0  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x180007ed5  mov     rax, rbx
0x180007ed8  mov     rcx, [rbp+3Fh+var_18]
0x180007edc  xor     rcx, rsp; StackCookie
0x180007edf  call    __security_check_cookie
0x180007ee4  mov     rbx, [rsp+0A0h+arg_10]
0x180007eec  add     rsp, 90h
0x180007ef3  pop     rdi
0x180007ef4  pop     rsi
0x180007ef5  pop     rbp
0x180007ef6  retn
```
