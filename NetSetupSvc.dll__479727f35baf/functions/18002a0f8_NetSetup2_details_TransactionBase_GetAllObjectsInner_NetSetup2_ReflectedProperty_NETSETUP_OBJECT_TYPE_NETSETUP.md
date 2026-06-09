# NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ReflectedProperty>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)

- ea: `0x18002a0f8`
- end: `0x18002a293`
- name: `??$GetAllObjectsInner@VReflectedProperty@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z`
- size: `411`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002d964`

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
- `0x18002a0f8`

## import_xrefs

- `NetSetupApi!NetSetupGetObjects` at `0x18002a180`
- `NetSetupApi!NetSetupGetObjects` at `0x18002a180`

## pseudocode

```c
__int64 *__fastcall NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ReflectedProperty>(
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
  Objects = NetSetupGetObjects(*a1, 10, 0, 0, 0, 0, 1, a6, &v24, &v25);
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
0x18002a0f8  mov     [rsp-8+arg_10], rbx
0x18002a0fd  push    rbp
0x18002a0fe  push    rsi
0x18002a0ff  push    rdi
0x18002a100  lea     rbp, [rsp-60h]
0x18002a105  sub     rsp, 160h
0x18002a10c  mov     rax, cs:__security_cookie
0x18002a113  xor     rax, rsp
0x18002a116  mov     [rbp+70h+var_18], rax
0x18002a11a  mov     rbx, rdx
0x18002a11d  mov     rsi, rcx
0x18002a120  mov     [rsp+170h+var_100], rdx
0x18002a125  mov     rax, [rbp+70h+arg_28]
0x18002a12c  mov     [rsp+170h+var_118], 0
0x18002a134  mov     [rbp+70h+var_28], 0
0x18002a13b  mov     [rbp+70h+var_20], 0
0x18002a143  lea     rcx, [rbp+70h+var_20]
0x18002a147  mov     [rsp+170h+var_128], rcx
0x18002a14c  lea     rcx, [rbp+70h+var_28]
0x18002a150  mov     [rsp+170h+var_130], rcx
0x18002a155  mov     [rsp+170h+var_138], rax
0x18002a15a  mov     [rsp+170h+var_140], 1
0x18002a162  mov     [rsp+170h+var_148], 0
0x18002a16b  mov     [rsp+170h+var_150], 0
0x18002a173  xor     r9d, r9d
0x18002a176  xor     r8d, r8d
0x18002a179  lea     edx, [r9+0Ah]
0x18002a17d  mov     rcx, [rsi]
0x18002a180  call    cs:__imp_NetSetupGetObjects
0x18002a186  test    eax, eax
0x18002a188  jns     short loc_18002A1A8
0x18002a18a  mov     edx, eax; int
0x18002a18c  lea     rcx, [rsp+170h+pExceptionObject]; this
0x18002a191  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002a196  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002a19d  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x18002a1a2  call    _CxxThrowException_0
0x18002a1a8  mov     eax, [rbp+70h+var_28]
0x18002a1ab  mov     [rsp+170h+var_110], eax
0x18002a1af  mov     rax, [rbp+70h+var_20]
0x18002a1b3  mov     [rsp+170h+var_108], rax
0x18002a1b8  mov     rcx, rbx
0x18002a1bb  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x18002a1c0  mov     [rsp+170h+var_118], 1
0x18002a1c8  mov     edx, [rbp+70h+var_28]
0x18002a1cb  mov     [rsp+170h+var_120], rdx
0x18002a1d0  mov     rax, [rbx+10h]
0x18002a1d4  sub     rax, [rbx]
0x18002a1d7  sar     rax, 3
0x18002a1db  cmp     rdx, rax
0x18002a1de  jbe     short loc_18002A1ED
0x18002a1e0  lea     rdx, [rsp+170h+var_120]
0x18002a1e5  call    ??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(unsigned __int64 &)
0x18002a1ea  mov     edx, [rbp+70h+var_28]
0x18002a1ed  xor     edi, edi
0x18002a1ef  test    edx, edx
0x18002a1f1  jz      short loc_18002A266
0x18002a1f3  mov     ecx, 28h ; '('; Size
0x18002a1f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a1fd  mov     r8, rax
0x18002a200  mov     [rsp+170h+var_120], rax
0x18002a205  mov     edx, edi
0x18002a207  shl     rdx, 5
0x18002a20b  mov     rcx, [rbp+70h+var_20]
0x18002a20f  mov     eax, [rdx+rcx]
0x18002a212  mov     [r8], rsi
0x18002a215  mov     qword ptr [r8+8], 0
0x18002a21d  mov     [r8+10h], eax
0x18002a221  movups  xmm0, xmmword ptr [rdx+rcx+4]
0x18002a226  movdqu  xmmword ptr [r8+14h], xmm0
0x18002a22c  mov     [rsp+170h+var_120], r8
0x18002a231  mov     rdx, [rbx+8]
0x18002a235  mov     rcx, rbx
0x18002a238  cmp     rdx, [rbx+10h]
0x18002a23c  jz      short loc_18002A24A
0x18002a23e  lea     rdx, [rsp+170h+var_120]
0x18002a243  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Emplace_back_with_unused_capacity<std::unique_ptr<NetSetup2::ReflectedProperty>>(std::unique_ptr<NetSetup2::ReflectedProperty> &&)
0x18002a248  jmp     short loc_18002A255
0x18002a24a  lea     r8, [rsp+170h+var_120]
0x18002a24f  call    ??$_Emplace_reallocate@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(std::unique_ptr<NetSetup2::NetworkInterface> * const,std::unique_ptr<NetSetup2::NetworkInterface> &&)
0x18002a254  nop
0x18002a255  lea     rcx, [rsp+170h+var_120]
0x18002a25a  call    ??1?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@QEAA@XZ; std::unique_ptr<NetSetup2::NetworkInterface>::~unique_ptr<NetSetup2::NetworkInterface>(void)
0x18002a25f  inc     edi
0x18002a261  cmp     edi, [rbp+70h+var_28]
0x18002a264  jb      short loc_18002A1F3
0x18002a266  lea     rcx, [rsp+170h+var_110]; this
0x18002a26b  call    ??1AutoFreeObjects@details@NetSetup2@@QEAA@XZ; NetSetup2::details::AutoFreeObjects::~AutoFreeObjects(void)
0x18002a270  mov     rax, rbx
0x18002a273  mov     rcx, [rbp+70h+var_18]
0x18002a277  xor     rcx, rsp; StackCookie
0x18002a27a  call    __security_check_cookie
0x18002a27f  mov     rbx, [rsp+170h+arg_10]
0x18002a287  add     rsp, 160h
0x18002a28e  pop     rdi
0x18002a28f  pop     rsi
0x18002a290  pop     rbp
0x18002a291  retn
```
