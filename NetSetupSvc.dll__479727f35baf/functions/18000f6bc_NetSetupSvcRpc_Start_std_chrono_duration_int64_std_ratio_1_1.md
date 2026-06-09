# NetSetupSvcRpc::Start(std::chrono::duration<__int64,std::ratio<1,1>>)

- ea: `0x18000f6bc`
- end: `0x18000f879`
- name: `?Start@NetSetupSvcRpc@@QEAAXV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x18000f6bc`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000f78d`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000f78d`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000f7f7`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000f7f7`

## pseudocode

```c
__int64 __fastcall NetSetupSvcRpc::Start(_DWORD *a1)
{
  __int64 *v1; // rsi
  unsigned int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 result; // rax
  int v7; // ebx
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v9[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v10; // [rsp+120h] [rbp+20h]
  __int64 v11; // [rsp+130h] [rbp+30h]
  _QWORD v12[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v13; // [rsp+150h] [rbp+50h]
  int v14; // [rsp+160h] [rbp+60h]
  int v15; // [rsp+164h] [rbp+64h]
  __int64 v16; // [rsp+168h] [rbp+68h]
  __int64 v17; // [rsp+170h] [rbp+70h]
  __int64 v18; // [rsp+178h] [rbp+78h]
  const wchar_t *v19; // [rsp+180h] [rbp+80h]
  __int64 v20; // [rsp+188h] [rbp+88h]

  v1 = (__int64 *)(a1 + 2);
  v12[0] = 0;
  v12[1] = qword_180032750;
  v19 = L"NetSetup API";
  v16 = 0;
  v9[1] = L"ncalrpc";
  v13 = 0;
  v14 = 41;
  v15 = 1234;
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v9[0] = 0;
  v11 = 10;
  v10 = 0;
  v3 = RpcServerInterfaceGroupCreateW(v12, 1, v9);
  v4 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_42d1e36e1ebd354e1d184b1a71050c64_Traceguids, v3);
    HResultException::HResultException((HResultException *)pExceptionObject, v4 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  v5 = *v1;
  *a1 = 1;
  result = RpcServerInterfaceGroupActivate(v5);
  v7 = result;
  if ( (_DWORD)result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_42d1e36e1ebd354e1d184b1a71050c64_Traceguids,
        (unsigned int)result);
    HResultException::HResultException((HResultException *)pExceptionObject, v7 | 0x80010000);
    throw (HResultException *)pExceptionObject;
  }
  *a1 = 2;
  return result;
}

```

## disassembly

```asm
0x18000f6bc  push    rbp
0x18000f6be  push    rbx
0x18000f6bf  push    rsi
0x18000f6c0  push    rdi
0x18000f6c1  lea     rbp, [rsp-0A8h]
0x18000f6c9  sub     rsp, 1A8h
0x18000f6d0  mov     rax, cs:__security_cookie
0x18000f6d7  xor     rax, rsp
0x18000f6da  mov     [rbp+0C0h+var_30], rax
0x18000f6e1  lea     rsi, [rcx+8]
0x18000f6e5  mov     [rbp+0C0h+var_80], 0
0x18000f6ed  mov     [rsp+1C0h+var_188], rsi
0x18000f6f2  lea     rax, qword_180032750
0x18000f6f9  mov     [rbp+0C0h+var_78], rax
0x18000f6fd  lea     r8, [rbp+0C0h+var_B0]
0x18000f701  mov     [rsp+1C0h+var_190], rcx
0x18000f706  lea     rax, aNetsetupApi; "NetSetup API"
0x18000f70d  mov     [rbp+0C0h+var_40], rax
0x18000f714  xorps   xmm0, xmm0
0x18000f717  lea     rax, aNcalrpc; "ncalrpc"
0x18000f71e  mov     [rbp+0C0h+var_58], 0
0x18000f726  mov     [rbp+0C0h+var_A8], rax
0x18000f72a  mov     r9d, 1
0x18000f730  lea     rax, ?IdleCallbackThunk@NetSetupSvcRpc@@CAXPEAX0K@Z; NetSetupSvcRpc::IdleCallbackThunk(void *,void *,ulong)
0x18000f737  movdqa  [rbp+0C0h+var_70], xmm0
0x18000f73c  mov     [rsp+1C0h+var_198], rax
0x18000f741  mov     rdi, rcx
0x18000f744  mov     [rsp+1C0h+var_1A0], edx
0x18000f748  lea     rcx, [rbp+0C0h+var_80]
0x18000f74c  mov     edx, r9d
0x18000f74f  mov     [rbp+0C0h+var_60], 29h ; ')'
0x18000f756  mov     [rbp+0C0h+var_5C], 4D2h
0x18000f75d  mov     [rbp+0C0h+var_50], 0
0x18000f765  mov     [rbp+0C0h+var_48], 0
0x18000f76d  mov     [rbp+0C0h+var_38], 0
0x18000f778  mov     [rbp+0C0h+var_B0], 0
0x18000f780  mov     [rbp+0C0h+var_90], 0Ah
0x18000f788  movdqu  [rbp+0C0h+var_A0], xmm0
0x18000f78d  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18000f793  mov     ebx, eax
0x18000f795  test    eax, eax
0x18000f797  jz      short loc_18000F7EE
0x18000f799  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7a0  lea     r8, WPP_GLOBAL_Control
0x18000f7a7  cmp     rcx, r8
0x18000f7aa  jz      short loc_18000F7CA
0x18000f7ac  cmp     byte ptr [rcx+19h], 2
0x18000f7b0  jb      short loc_18000F7CA
0x18000f7b2  mov     rcx, [rcx+10h]
0x18000f7b6  lea     r8, WPP_42d1e36e1ebd354e1d184b1a71050c64_Traceguids
0x18000f7bd  mov     edx, 0Ah
0x18000f7c2  mov     r9d, eax
0x18000f7c5  call    WPP_SF_d
0x18000f7ca  or      ebx, 80010000h
0x18000f7d0  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18000f7d5  mov     edx, ebx; int
0x18000f7d7  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000f7dc  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000f7e3  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18000f7e8  call    _CxxThrowException_0
0x18000f7ee  mov     rcx, [rsi]
0x18000f7f1  mov     dword ptr [rdi], 1
0x18000f7f7  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000f7fd  mov     ebx, eax
0x18000f7ff  test    eax, eax
0x18000f801  jz      short loc_18000F858
0x18000f803  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f80a  lea     r8, WPP_GLOBAL_Control
0x18000f811  cmp     rcx, r8
0x18000f814  jz      short loc_18000F834
0x18000f816  cmp     byte ptr [rcx+19h], 2
0x18000f81a  jb      short loc_18000F834
0x18000f81c  mov     rcx, [rcx+10h]
0x18000f820  lea     r8, WPP_42d1e36e1ebd354e1d184b1a71050c64_Traceguids
0x18000f827  mov     edx, 0Bh
0x18000f82c  mov     r9d, eax
0x18000f82f  call    WPP_SF_d
0x18000f834  or      ebx, 80010000h
0x18000f83a  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x18000f83f  mov     edx, ebx; int
0x18000f841  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000f846  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000f84d  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x18000f852  call    _CxxThrowException_0
0x18000f858  mov     dword ptr [rdi], 2
0x18000f85e  mov     rcx, [rbp+0C0h+var_30]
0x18000f865  xor     rcx, rsp; StackCookie
0x18000f868  call    __security_check_cookie
0x18000f86d  add     rsp, 1A8h
0x18000f874  pop     rdi
0x18000f875  pop     rsi
0x18000f876  pop     rbx
0x18000f877  pop     rbp
0x18000f878  retn
```
