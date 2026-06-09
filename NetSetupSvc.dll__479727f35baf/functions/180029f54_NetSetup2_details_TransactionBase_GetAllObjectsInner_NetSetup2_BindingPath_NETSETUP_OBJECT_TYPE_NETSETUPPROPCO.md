# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::BindingPath>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x180029f54`
- end: `0x18002a0ef`
- name: `??$GetAllObjectsInner@VBindingPath@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
- size: `411`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002bd50`
- `0x18002d7d8`

## callees

- `0x1800027c0`
- `0x180002bcc`
- `0x1800032e4`
- `0x180007048`
- `0x180008450`
- `0x180008478`
- `0x1800085d8`
- `0x180008854`
- `0x180008db0`
- `0x180009028`
- `0x180029f54`

## import_xrefs

- `NetSetupApi!NetSetupGetObjects` at `0x180029fdc`
- `NetSetupApi!NetSetupGetObjects` at `0x180029fdc`

## pseudocode

```c
__int64 *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::BindingPath>(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int Objects; // eax
  _QWORD *v9; // rcx
  unsigned int v10; // edx
  unsigned int v11; // edi
  char *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  char *v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  unsigned int v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  __int64 *v22; // [rsp+70h] [rbp-90h]
  _BYTE pExceptionObject[208]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v24; // [rsp+148h] [rbp+48h] BYREF
  __int64 v25; // [rsp+150h] [rbp+50h] BYREF

  v22 = a2;
  v19 = 0;
  v24 = 0;
  v25 = 0;
  Objects = NetSetupGetObjects(*a1, 7, 0, 0, 0, 0, 1, a6, &v24, &v25);
  if ( Objects < 0 )
  {
    HResultException::HResultException((HResultException *)pExceptionObject, Objects);
    throw (HResultException *)pExceptionObject;
  }
  v20 = v24;
  v21 = v25;
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(a2);
  v19 = 1;
  v10 = v24;
  v18 = (char *)v24;
  if ( v24 > (unsigned __int64)((a2[2] - *a2) >> 3) )
  {
    std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(v9, &v18);
    v10 = v24;
  }
  v11 = 0;
  if ( v10 )
  {
    do
    {
      v12 = (char *)operator new(0x28u);
      v18 = v12;
      v13 = 32LL * v11;
      v14 = v25;
      v15 = *(_DWORD *)(v13 + v25);
      *(_QWORD *)v12 = a1;
      *((_QWORD *)v12 + 1) = 0;
      *((_DWORD *)v12 + 4) = v15;
      *(_OWORD *)(v12 + 20) = *(_OWORD *)(v13 + v14 + 4);
      v18 = v12;
      v16 = a2[1];
      if ( v16 == a2[2] )
        std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(
          a2,
          v16,
          (__int64 *)&v18);
      else
        std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(
          (__int64)a2,
          (__int64 *)&v18);
      std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(&v18);
      ++v11;
    }
    while ( v11 < v24 );
  }
  NetSetup2::details::AutoFreeObjects::~AutoFreeObjects((NetSetup2::details::AutoFreeObjects *)&v20);
  return a2;
}

```

## disassembly

```asm
0x180029f54  mov     [rsp-8+arg_10], rbx
0x180029f59  push    rbp
0x180029f5a  push    rsi
0x180029f5b  push    rdi
0x180029f5c  lea     rbp, [rsp-60h]
0x180029f61  sub     rsp, 160h
0x180029f68  mov     rax, cs:__security_cookie
0x180029f6f  xor     rax, rsp
0x180029f72  mov     [rbp+70h+var_18], rax
0x180029f76  mov     rbx, rdx
0x180029f79  mov     rsi, rcx
0x180029f7c  mov     [rsp+170h+var_100], rdx
0x180029f81  mov     rax, [rbp+70h+arg_28]
0x180029f88  mov     [rsp+170h+var_118], 0
0x180029f90  mov     [rbp+70h+var_28], 0
0x180029f97  mov     [rbp+70h+var_20], 0
0x180029f9f  lea     rcx, [rbp+70h+var_20]
0x180029fa3  mov     [rsp+170h+var_128], rcx
0x180029fa8  lea     rcx, [rbp+70h+var_28]
0x180029fac  mov     [rsp+170h+var_130], rcx
0x180029fb1  mov     [rsp+170h+var_138], rax
0x180029fb6  mov     [rsp+170h+var_140], 1
0x180029fbe  mov     [rsp+170h+var_148], 0
0x180029fc7  mov     [rsp+170h+var_150], 0
0x180029fcf  xor     r9d, r9d
0x180029fd2  xor     r8d, r8d
0x180029fd5  lea     edx, [r9+7]
0x180029fd9  mov     rcx, [rsi]
0x180029fdc  call    cs:__imp_NetSetupGetObjects
0x180029fe2  test    eax, eax
0x180029fe4  jns     short loc_18002A004
0x180029fe6  mov     edx, eax; int
0x180029fe8  lea     rcx, [rsp+170h+pExceptionObject]; this
0x180029fed  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180029ff2  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180029ff9  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x180029ffe  call    _CxxThrowException_0
0x18002a004  mov     eax, [rbp+70h+var_28]
0x18002a007  mov     [rsp+170h+var_110], eax
0x18002a00b  mov     rax, [rbp+70h+var_20]
0x18002a00f  mov     [rsp+170h+var_108], rax
0x18002a014  mov     rcx, rbx
0x18002a017  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x18002a01c  mov     [rsp+170h+var_118], 1
0x18002a024  mov     edx, [rbp+70h+var_28]
0x18002a027  mov     [rsp+170h+var_120], rdx
0x18002a02c  mov     rax, [rbx+10h]
0x18002a030  sub     rax, [rbx]
0x18002a033  sar     rax, 3
0x18002a037  cmp     rdx, rax
0x18002a03a  jbe     short loc_18002A049
0x18002a03c  lea     rdx, [rsp+170h+var_120]
0x18002a041  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(unsigned __int64 &)
0x18002a046  mov     edx, [rbp+70h+var_28]
0x18002a049  xor     edi, edi
0x18002a04b  test    edx, edx
0x18002a04d  jz      short loc_18002A0C2
0x18002a04f  mov     ecx, 28h ; '('; Size
0x18002a054  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a059  mov     r8, rax
0x18002a05c  mov     [rsp+170h+var_120], rax
0x18002a061  mov     edx, edi
0x18002a063  shl     rdx, 5
0x18002a067  mov     rcx, [rbp+70h+var_20]
0x18002a06b  mov     eax, [rdx+rcx]
0x18002a06e  mov     [r8], rsi
0x18002a071  mov     qword ptr [r8+8], 0
0x18002a079  mov     [r8+10h], eax
0x18002a07d  movups  xmm0, xmmword ptr [rdx+rcx+4]
0x18002a082  movdqu  xmmword ptr [r8+14h], xmm0
0x18002a088  mov     [rsp+170h+var_120], r8
0x18002a08d  mov     rdx, [rbx+8]
0x18002a091  mov     rcx, rbx
0x18002a094  cmp     rdx, [rbx+10h]
0x18002a098  jz      short loc_18002A0A6
0x18002a09a  lea     rdx, [rsp+170h+var_120]
0x18002a09f  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(std::unique_ptr<NetSetup2::ReflectedProperty> &&)
0x18002a0a4  jmp     short loc_18002A0B1
0x18002a0a6  lea     r8, [rsp+170h+var_120]
0x18002a0ab  call    ??$_Emplace_reallocate@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(std::unique_ptr<NetSetup2::NetworkInterface> * const,std::unique_ptr<NetSetup2::NetworkInterface> &&)
0x18002a0b0  nop
0x18002a0b1  lea     rcx, [rsp+170h+var_120]
0x18002a0b6  call    ??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(void)
0x18002a0bb  inc     edi
0x18002a0bd  cmp     edi, [rbp+70h+var_28]
0x18002a0c0  jb      short loc_18002A04F
0x18002a0c2  lea     rcx, [rsp+170h+var_110]; this
0x18002a0c7  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x18002a0cc  mov     rax, rbx
0x18002a0cf  mov     rcx, [rbp+70h+var_18]
0x18002a0d3  xor     rcx, rsp; StackCookie
0x18002a0d6  call    __security_check_cookie
0x18002a0db  mov     rbx, [rsp+170h+arg_10]
0x18002a0e3  add     rsp, 160h
0x18002a0ea  pop     rdi
0x18002a0eb  pop     rsi
0x18002a0ec  pop     rbp
0x18002a0ed  retn
```
