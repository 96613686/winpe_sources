# _lambda_8cb54a1c1e43e189d8dd2cb217321a92_::operator()

- ea: `0x18000dda4`
- end: `0x18000de87`
- name: `_lambda_8cb54a1c1e43e189d8dd2cb217321a92_::operator()`
- size: `227`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000d344`

## callees

- `0x180004b20`
- `0x1800050a0`
- `0x1800060f8`
- `0x180006608`
- `0x18000895c`
- `0x18000dda4`
- `0x18000fd1c`
- `0x1800119f0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000de35`
- `RPCRT4!UuidCreate` at `0x18000de35`

## pseudocode

```c
void __fastcall lambda_8cb54a1c1e43e189d8dd2cb217321a92_::operator()(_QWORD *a1)
{
  _BYTE pExceptionObject[208]; // [rsp+28h] [rbp-120h] BYREF
  UUID Uuid; // [rsp+F8h] [rbp-50h] BYREF
  _BYTE v3[48]; // [rsp+108h] [rbp-40h] BYREF

  if ( *a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_f1172f7f51b138cada6e87324e167680_Traceguids,
        "Reserved == 0");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  Uuid = 0;
  UuidCreate(&Uuid);
  NetSetupRpcClient::NetSetupRpcClient((__int64)v3, &Uuid, 0);
  NetSetupExecuteInRpc__lambda_e2361734dd3cd8eaf5ba86d4d3e018f6_(v3);
  NetSetupRpcClient::~NetSetupRpcClient((NetSetupRpcClient *)v3);
}

```

## disassembly

```asm
0x18000dda4  sub     rsp, 148h
0x18000ddab  mov     [rsp+148h+var_128], 0FFFFFFFFFFFFFFFEh
0x18000ddb4  mov     rax, cs:__security_cookie
0x18000ddbb  xor     rax, rsp
0x18000ddbe  mov     [rsp+148h+var_10], rax
0x18000ddc6  cmp     qword ptr [rcx], 0
0x18000ddca  jz      short loc_18000DE22
0x18000ddcc  lea     rax, WPP_GLOBAL_Control
0x18000ddd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddda  cmp     rcx, rax
0x18000dddd  jz      short loc_18000DE01
0x18000dddf  cmp     byte ptr [rcx+19h], 2
0x18000dde3  jb      short loc_18000DE01
0x18000dde5  mov     edx, 1Ah
0x18000ddea  lea     r9, aReserved0; "Reserved == 0"
0x18000ddf1  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000ddf8  mov     rcx, [rcx+10h]
0x18000ddfc  call    WPP_SF_s
0x18000de01  mov     edx, 80070057h; int
0x18000de06  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18000de0b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000de10  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000de17  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18000de1c  call    _CxxThrowException_0
0x18000de22  xorps   xmm0, xmm0
0x18000de25  movups  xmmword ptr [rsp+148h+Uuid.Data1], xmm0
0x18000de2d  lea     rcx, [rsp+148h+Uuid]; Uuid
0x18000de35  call    cs:__imp_UuidCreate
0x18000de3b  xor     r8d, r8d
0x18000de3e  lea     rdx, [rsp+148h+Uuid]
0x18000de46  lea     rcx, [rsp+148h+var_40]
0x18000de4e  call    ??0NetSetupRpcClient@@QEAA@AEBU_GUID@@W4_NETSETUP_ENVIRONMENT_TYPE@@@Z; NetSetupRpcClient::NetSetupRpcClient(_GUID const &,_NETSETUP_ENVIRONMENT_TYPE)
0x18000de53  nop
0x18000de54  lea     rcx, [rsp+148h+var_40]
0x18000de5c  call    NetSetupExecuteInRpc__lambda_e2361734dd3cd8eaf5ba86d4d3e018f6___; NetSetupExecuteInRpc__lambda_e2361734dd3cd8eaf5ba86d4d3e018f6_
0x18000de61  nop
0x18000de62  lea     rcx, [rsp+148h+var_40]; this
0x18000de6a  call    ??1NetSetupRpcClient@@UEAA@XZ; NetSetupRpcClient::~NetSetupRpcClient(void)
0x18000de6f  mov     rcx, [rsp+148h+var_10]
0x18000de77  xor     rcx, rsp; StackCookie
0x18000de7a  call    __security_check_cookie
0x18000de7f  add     rsp, 148h
0x18000de86  retn
```
