# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ServiceDriver>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x180008084`
- end: `0x180008202`
- name: `??$GetAllObjectsInner@VServiceDriver@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VServiceDriver@NetSetup2@@U?$default_delete@VServiceDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VServiceDriver@NetSetup2@@U?$default_delete@VServiceDriver@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
- size: `382`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c5e0`

## callees

- `0x1800027c0`
- `0x180002bcc`
- `0x1800032e4`
- `0x180007048`
- `0x180008084`
- `0x180008450`
- `0x180008478`
- `0x1800085d8`
- `0x180008db0`
- `0x180009028`

## import_xrefs

- `NetSetupApi!NetSetupGetObjects` at `0x180008104`
- `NetSetupApi!NetSetupGetObjects` at `0x180008104`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ServiceDriver>(
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
  Objects = NetSetupGetObjects(*a1, 5, 0, 0, 0, 0, 0, 0, &v19, &v20);
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
0x180008084  mov     r11, rsp
0x180008087  mov     [r11+18h], rbx
0x18000808b  push    rbp
0x18000808c  push    rsi
0x18000808d  push    rdi
0x18000808e  lea     rbp, [r11-47h]
0x180008092  sub     rsp, 90h
0x180008099  mov     rax, cs:__security_cookie
0x1800080a0  xor     rax, rsp
0x1800080a3  mov     [rbp+3Fh+var_18], rax
0x1800080a7  mov     rbx, rdx
0x1800080aa  mov     rsi, rcx
0x1800080ad  mov     [rbp+3Fh+var_30], rdx
0x1800080b1  mov     [rbp+3Fh+var_48], 0
0x1800080b8  mov     [rbp+3Fh+var_28], 0
0x1800080bf  mov     [rbp+3Fh+var_20], 0
0x1800080c7  lea     rax, [rbp+3Fh+var_20]
0x1800080cb  mov     [r11-60h], rax
0x1800080cf  lea     rax, [rbp+3Fh+var_28]
0x1800080d3  mov     [r11-68h], rax
0x1800080d7  mov     qword ptr [r11-70h], 0
0x1800080df  mov     dword ptr [rsp+30h], 0
0x1800080e7  mov     qword ptr [r11-80h], 0
0x1800080ef  mov     dword ptr [rsp+20h], 0
0x1800080f7  xor     r9d, r9d
0x1800080fa  xor     r8d, r8d
0x1800080fd  lea     edx, [r9+5]
0x180008101  mov     rcx, [rcx]
0x180008104  call    cs:__imp_NetSetupGetObjects
0x18000810a  test    eax, eax
0x18000810c  jns     short loc_180008122
0x18000810e  mov     dword ptr [rbp+3Fh+pExceptionObject], eax
0x180008111  lea     rdx, _TI1J; pThrowInfo
0x180008118  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x18000811c  call    _CxxThrowException_0
0x180008122  mov     eax, [rbp+3Fh+var_28]
0x180008125  mov     [rbp+3Fh+var_40], eax
0x180008128  mov     rax, [rbp+3Fh+var_20]
0x18000812c  mov     [rbp+3Fh+var_38], rax
0x180008130  mov     rcx, rbx
0x180008133  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x180008138  mov     [rbp+3Fh+var_48], 1
0x18000813f  mov     edx, [rbp+3Fh+var_28]
0x180008142  mov     [rbp+3Fh+pExceptionObject], rdx
0x180008146  mov     rax, [rbx+10h]
0x18000814a  sub     rax, [rbx]
0x18000814d  sar     rax, 3
0x180008151  cmp     rdx, rax
0x180008154  jbe     short loc_180008162
0x180008156  lea     rdx, [rbp+3Fh+pExceptionObject]
0x18000815a  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(unsigned __int64 &)
0x18000815f  mov     edx, [rbp+3Fh+var_28]
0x180008162  xor     edi, edi
0x180008164  test    edx, edx
0x180008166  jz      short loc_1800081D6
0x180008168  mov     ecx, 28h ; '('; Size
0x18000816d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008172  mov     r8, rax
0x180008175  mov     [rbp+3Fh+pExceptionObject], rax
0x180008179  mov     edx, edi
0x18000817b  shl     rdx, 5
0x18000817f  mov     rcx, [rbp+3Fh+var_20]
0x180008183  mov     eax, [rdx+rcx]
0x180008186  mov     [r8], rsi
0x180008189  mov     qword ptr [r8+8], 0
0x180008191  mov     [r8+10h], eax
0x180008195  movups  xmm0, xmmword ptr [rdx+rcx+4]
0x18000819a  movdqu  xmmword ptr [r8+14h], xmm0
0x1800081a0  mov     [rbp+3Fh+pExceptionObject], r8
0x1800081a4  mov     rdx, [rbx+8]
0x1800081a8  mov     rcx, rbx
0x1800081ab  cmp     rdx, [rbx+10h]
0x1800081af  jz      short loc_1800081BC
0x1800081b1  lea     rdx, [rbp+3Fh+pExceptionObject]
0x1800081b5  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(std::unique_ptr<NetSetup2::ReflectedProperty> &&)
0x1800081ba  jmp     short loc_1800081C6
0x1800081bc  lea     r8, [rbp+3Fh+pExceptionObject]
0x1800081c0  call    ??$_Emplace_reallocate@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(std::unique_ptr<NetSetup2::NetworkInterface> * const,std::unique_ptr<NetSetup2::NetworkInterface> &&)
0x1800081c5  nop
0x1800081c6  lea     rcx, [rbp+3Fh+pExceptionObject]
0x1800081ca  call    ??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(void)
0x1800081cf  inc     edi
0x1800081d1  cmp     edi, [rbp+3Fh+var_28]
0x1800081d4  jb      short loc_180008168
0x1800081d6  lea     rcx, [rbp+3Fh+var_40]; this
0x1800081da  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x1800081df  mov     rax, rbx
0x1800081e2  mov     rcx, [rbp+3Fh+var_18]
0x1800081e6  xor     rcx, rsp; StackCookie
0x1800081e9  call    __security_check_cookie
0x1800081ee  mov     rbx, [rsp+0A0h+arg_10]
0x1800081f6  add     rsp, 90h
0x1800081fd  pop     rdi
0x1800081fe  pop     rsi
0x1800081ff  pop     rbp
0x180008200  retn
```
