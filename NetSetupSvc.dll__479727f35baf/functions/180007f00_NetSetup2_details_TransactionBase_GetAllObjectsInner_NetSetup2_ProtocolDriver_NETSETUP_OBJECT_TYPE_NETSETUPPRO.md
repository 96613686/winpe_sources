# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ProtocolDriver>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x180007f00`
- end: `0x18000807e`
- name: `??$GetAllObjectsInner@VProtocolDriver@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VProtocolDriver@NetSetup2@@U?$default_delete@VProtocolDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VProtocolDriver@NetSetup2@@U?$default_delete@VProtocolDriver@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
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
- `0x180007f00`
- `0x180008450`
- `0x180008478`
- `0x1800085d8`
- `0x180008db0`
- `0x180009028`

## import_xrefs

- `NetSetupApi!NetSetupGetObjects` at `0x180007f80`
- `NetSetupApi!NetSetupGetObjects` at `0x180007f80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ProtocolDriver>(
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
  Objects = NetSetupGetObjects(*a1, 4, 0, 0, 0, 0, 0, 0, &v19, &v20);
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
0x180007f00  mov     r11, rsp
0x180007f03  mov     [r11+18h], rbx
0x180007f07  push    rbp
0x180007f08  push    rsi
0x180007f09  push    rdi
0x180007f0a  lea     rbp, [r11-47h]
0x180007f0e  sub     rsp, 90h
0x180007f15  mov     rax, cs:__security_cookie
0x180007f1c  xor     rax, rsp
0x180007f1f  mov     [rbp+3Fh+var_18], rax
0x180007f23  mov     rbx, rdx
0x180007f26  mov     rsi, rcx
0x180007f29  mov     [rbp+3Fh+var_30], rdx
0x180007f2d  mov     [rbp+3Fh+var_48], 0
0x180007f34  mov     [rbp+3Fh+var_28], 0
0x180007f3b  mov     [rbp+3Fh+var_20], 0
0x180007f43  lea     rax, [rbp+3Fh+var_20]
0x180007f47  mov     [r11-60h], rax
0x180007f4b  lea     rax, [rbp+3Fh+var_28]
0x180007f4f  mov     [r11-68h], rax
0x180007f53  mov     qword ptr [r11-70h], 0
0x180007f5b  mov     dword ptr [rsp+30h], 0
0x180007f63  mov     qword ptr [r11-80h], 0
0x180007f6b  mov     dword ptr [rsp+20h], 0
0x180007f73  xor     r9d, r9d
0x180007f76  xor     r8d, r8d
0x180007f79  lea     edx, [r9+4]
0x180007f7d  mov     rcx, [rcx]
0x180007f80  call    cs:__imp_NetSetupGetObjects
0x180007f86  test    eax, eax
0x180007f88  jns     short loc_180007F9E
0x180007f8a  mov     dword ptr [rbp+3Fh+pExceptionObject], eax
0x180007f8d  lea     rdx, _TI1J; pThrowInfo
0x180007f94  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180007f98  call    _CxxThrowException_0
0x180007f9e  mov     eax, [rbp+3Fh+var_28]
0x180007fa1  mov     [rbp+3Fh+var_40], eax
0x180007fa4  mov     rax, [rbp+3Fh+var_20]
0x180007fa8  mov     [rbp+3Fh+var_38], rax
0x180007fac  mov     rcx, rbx
0x180007faf  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x180007fb4  mov     [rbp+3Fh+var_48], 1
0x180007fbb  mov     edx, [rbp+3Fh+var_28]
0x180007fbe  mov     [rbp+3Fh+pExceptionObject], rdx
0x180007fc2  mov     rax, [rbx+10h]
0x180007fc6  sub     rax, [rbx]
0x180007fc9  sar     rax, 3
0x180007fcd  cmp     rdx, rax
0x180007fd0  jbe     short loc_180007FDE
0x180007fd2  lea     rdx, [rbp+3Fh+pExceptionObject]
0x180007fd6  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(unsigned __int64 &)
0x180007fdb  mov     edx, [rbp+3Fh+var_28]
0x180007fde  xor     edi, edi
0x180007fe0  test    edx, edx
0x180007fe2  jz      short loc_180008052
0x180007fe4  mov     ecx, 28h ; '('; Size
0x180007fe9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007fee  mov     r8, rax
0x180007ff1  mov     [rbp+3Fh+pExceptionObject], rax
0x180007ff5  mov     edx, edi
0x180007ff7  shl     rdx, 5
0x180007ffb  mov     rcx, [rbp+3Fh+var_20]
0x180007fff  mov     eax, [rdx+rcx]
0x180008002  mov     [r8], rsi
0x180008005  mov     qword ptr [r8+8], 0
0x18000800d  mov     [r8+10h], eax
0x180008011  movups  xmm0, xmmword ptr [rdx+rcx+4]
0x180008016  movdqu  xmmword ptr [r8+14h], xmm0
0x18000801c  mov     [rbp+3Fh+pExceptionObject], r8
0x180008020  mov     rdx, [rbx+8]
0x180008024  mov     rcx, rbx
0x180008027  cmp     rdx, [rbx+10h]
0x18000802b  jz      short loc_180008038
0x18000802d  lea     rdx, [rbp+3Fh+pExceptionObject]
0x180008031  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(std::unique_ptr<NetSetup2::ReflectedProperty> &&)
0x180008036  jmp     short loc_180008042
0x180008038  lea     r8, [rbp+3Fh+pExceptionObject]
0x18000803c  call    ??$_Emplace_reallocate@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(std::unique_ptr<NetSetup2::NetworkInterface> * const,std::unique_ptr<NetSetup2::NetworkInterface> &&)
0x180008041  nop
0x180008042  lea     rcx, [rbp+3Fh+pExceptionObject]
0x180008046  call    ??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(void)
0x18000804b  inc     edi
0x18000804d  cmp     edi, [rbp+3Fh+var_28]
0x180008050  jb      short loc_180007FE4
0x180008052  lea     rcx, [rbp+3Fh+var_40]; this
0x180008056  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x18000805b  mov     rax, rbx
0x18000805e  mov     rcx, [rbp+3Fh+var_18]
0x180008062  xor     rcx, rsp; StackCookie
0x180008065  call    __security_check_cookie
0x18000806a  mov     rbx, [rsp+0A0h+arg_10]
0x180008072  add     rsp, 90h
0x180008079  pop     rdi
0x18000807a  pop     rsi
0x18000807b  pop     rbp
0x18000807c  retn
```
