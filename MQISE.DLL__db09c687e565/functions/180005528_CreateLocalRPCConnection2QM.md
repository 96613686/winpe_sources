# CreateLocalRPCConnection2QM

- ea: `0x180005528`
- end: `0x180005914`
- name: `CreateLocalRPCConnection2QM`
- size: `1004`
- prototype: `RPC_BINDING_HANDLE __fastcall(WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006834`

## callees

- `0x180001c0c`
- `0x180005528`
- `0x18000dbb4`
- `0x18000dc4c`
- `0x18000dca0`
- `0x18000e61c`
- `0x18000ecf8`
- `0x18000edd0`
- `0x18000f5f0`

## import_xrefs

- `msvcrt!free` at `0x18000564f`
- `msvcrt!free` at `0x18000577a`
- `msvcrt!free` at `0x180005784`
- `msvcrt!free` at `0x18000564f`
- `msvcrt!free` at `0x18000577a`
- `msvcrt!free` at `0x180005784`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800057cc`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180005823`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000586e`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800058b5`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800058fc`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800057cc`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180005823`
- `msvcrt!??0exception@@QEAA@XZ` at `0x18000586e`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800058b5`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800058fc`
- `mqsec!mqrpcUnbindQMService` at `0x1800057b7`
- `mqsec!mqrpcUnbindQMService` at `0x1800057b7`
- `mqsec!MQSec_SetLocalRpcMutualAuth` at `0x180005766`
- `mqsec!MQSec_SetLocalRpcMutualAuth` at `0x180005766`
- `mqsec!ComposeRPCEndPointName` at `0x1800056cb`
- `mqsec!ComposeRPCEndPointName` at `0x1800056cb`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000573f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000573f`
- `RPCRT4!RpcStringBindingComposeW` at `0x180005722`
- `RPCRT4!RpcStringBindingComposeW` at `0x180005722`
- `RPCRT4!RpcStringFreeW` at `0x180005753`
- `RPCRT4!RpcStringFreeW` at `0x180005753`
- `USER32!CharLowerW` at `0x1800055c9`
- `USER32!CharLowerW` at `0x1800055c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RPC_BINDING_HANDLE __fastcall CreateLocalRPCConnection2QM(WCHAR *a1, unsigned int a2)
{
  WCHAR *v3; // r14
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rdx
  WCHAR *v7; // r9
  WCHAR v8; // r8
  __int64 v9; // r8
  WCHAR *v10; // rcx
  wchar_t *v11; // rbx
  unsigned int v12; // esi
  const wchar_t *v13; // rcx
  const wchar_t *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // r8
  wchar_t v17; // cx
  wchar_t *v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // eax
  unsigned int v21; // esi
  RPC_BINDING_HANDLE v22; // rdi
  RPC_WSTR String; // [rsp+30h] [rbp-D0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-C8h] BYREF
  RPC_WSTR Endpoint; // [rsp+40h] [rbp-C0h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  const wchar_t *v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  wchar_t *v32; // [rsp+70h] [rbp-90h]
  wchar_t *v33; // [rsp+78h] [rbp-88h]
  WCHAR sz[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[528]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = 0;
  v4 = 2147483646;
  if ( a1 )
  {
    if ( a2 > 0x7FFFFFFE )
    {
      v9 = 2147942487LL;
      sz[0] = 0;
    }
    else
    {
      v5 = a2;
      v6 = 16;
      v7 = sz;
      do
      {
        if ( !v5 )
          break;
        v8 = *a1;
        if ( !*a1 )
          break;
        ++a1;
        *v7++ = v8;
        --v5;
        --v6;
      }
      while ( v6 );
      v9 = v6 == 0 ? 0x8007007A : 0;
      v10 = v7 - 1;
      if ( v6 )
        v10 = v7;
      *v10 = 0;
      if ( v6 )
      {
        CharLowerW(sz);
        v3 = sz;
        goto LABEL_11;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, v9, a2, v9);
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
LABEL_11:
  pExceptionObject = 0;
  v28 = 0;
  v29 = L"RpcLocalEp";
  v30 = 0;
  v31 = 0;
  v11 = 0;
  v32 = 0;
  v12 = QueryValueSize(&pExceptionObject);
  if ( v12
    && (v11 = (wchar_t *)MmAllocate(saturated_mul((unsigned __int64)v12 >> 1, 2u)),
        v33 = v11,
        QueryValueInternal(&pExceptionObject, 1, v11, v12),
        v32 = v11,
        free(0),
        v11) )
  {
    v13 = v11;
  }
  else
  {
    v14 = L"QMsvc";
    v15 = 260;
    v16 = (wchar_t *)v35;
    do
    {
      if ( !v4 )
        break;
      v17 = *v14;
      if ( !*v14 )
        break;
      ++v14;
      *v16++ = v17;
      --v4;
      --v15;
    }
    while ( v15 );
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    *v18 = 0;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          29,
          &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids,
          v15 == 0 ? 0x8007007A : 0);
      exception::exception((exception *)&pExceptionObject);
      throw (exception *)&pExceptionObject;
    }
    v13 = (const wchar_t *)v35;
  }
  Endpoint = 0;
  ComposeRPCEndPointName(v13, v3, &Endpoint);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, v19, Endpoint);
  String = 0;
  v20 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids, v20);
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  Binding = 0;
  v21 = RpcBindingFromStringBindingW(String, &Binding);
  if ( String )
    RpcStringFreeW(&String);
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 32, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids, v21);
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  if ( MQSec_SetLocalRpcMutualAuth(&Binding) )
  {
    mqrpcUnbindQMService(&Binding, &String);
    Binding = 0;
    String = 0;
    exception::exception((exception *)&pExceptionObject);
    throw (exception *)&pExceptionObject;
  }
  v22 = Binding;
  free(Endpoint);
  free(v11);
  return v22;
}

```

## disassembly

```asm
0x180005528  push    rbp
0x18000552a  push    rbx
0x18000552b  push    rsi
0x18000552c  push    rdi
0x18000552d  push    r14
0x18000552f  push    r15
0x180005531  lea     rbp, [rsp-1C8h]
0x180005539  sub     rsp, 2C8h
0x180005540  mov     rax, cs:__security_cookie
0x180005547  xor     rax, rsp
0x18000554a  mov     [rbp+1F0h+var_40], rax
0x180005551  mov     r10d, edx
0x180005554  xor     r15d, r15d
0x180005557  mov     r14d, r15d
0x18000555a  mov     edi, 7FFFFFFEh
0x18000555f  test    rcx, rcx
0x180005562  jz      short loc_1800055D3
0x180005564  cmp     r10d, edi
0x180005567  ja      loc_1800057E4
0x18000556d  mov     rax, r10
0x180005570  mov     edx, 10h
0x180005575  lea     r9, [rbp+1F0h+sz]
0x180005579  test    rax, rax
0x18000557c  jz      short loc_18000559D
0x18000557e  movzx   r8d, word ptr [rcx]
0x180005582  test    r8w, r8w
0x180005586  jz      short loc_18000559D
0x180005588  add     rcx, 2
0x18000558c  mov     [r9], r8w
0x180005590  add     r9, 2
0x180005594  dec     rax
0x180005597  sub     rdx, 1
0x18000559b  jnz     short loc_180005579
0x18000559d  mov     rax, rdx
0x1800055a0  neg     rax
0x1800055a3  sbb     r8d, r8d
0x1800055a6  not     r8d
0x1800055a9  and     r8d, 8007007Ah
0x1800055b0  lea     rcx, [r9-2]
0x1800055b4  test    rdx, rdx
0x1800055b7  cmovnz  rcx, r9
0x1800055bb  mov     [rcx], r15w
0x1800055bf  jz      loc_1800057EF
0x1800055c5  lea     rcx, [rbp+1F0h+sz]; lpsz
0x1800055c9  call    cs:__imp_CharLowerW
0x1800055cf  lea     r14, [rbp+1F0h+sz]
0x1800055d3  mov     [rsp+2F0h+pExceptionObject], r15d
0x1800055d8  mov     [rsp+2F0h+var_2A0], r15
0x1800055dd  lea     rax, aRpclocalep; "RpcLocalEp"
0x1800055e4  mov     [rsp+2F0h+var_298], rax
0x1800055e9  mov     [rsp+2F0h+var_290], r15d
0x1800055ee  mov     [rsp+2F0h+var_288], r15
0x1800055f3  mov     rbx, r15
0x1800055f6  mov     [rsp+2F0h+var_280], rbx
0x1800055fb  lea     rcx, [rsp+2F0h+pExceptionObject]
0x180005600  call    QueryValueSize
0x180005605  mov     esi, eax
0x180005607  test    eax, eax
0x180005609  jz      short loc_180005660
0x18000560b  mov     ecx, esi
0x18000560d  shr     rcx, 1
0x180005610  mov     eax, 2
0x180005615  mul     rcx
0x180005618  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000561f  cmovb   rax, rcx
0x180005623  mov     rcx, rax; unsigned __int64
0x180005626  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000562b  mov     rbx, rax
0x18000562e  mov     [rsp+2F0h+var_278], rax
0x180005633  mov     r9d, esi
0x180005636  mov     r8, rax
0x180005639  mov     edx, 1
0x18000563e  lea     rcx, [rsp+2F0h+pExceptionObject]
0x180005643  call    QueryValueInternal
0x180005648  mov     [rsp+2F0h+var_280], rbx
0x18000564d  xor     ecx, ecx; Block
0x18000564f  call    cs:__imp_free
0x180005655  nop
0x180005656  test    rbx, rbx
0x180005659  jz      short loc_180005660
0x18000565b  mov     rcx, rbx
0x18000565e  jmp     short loc_1800056BE
0x180005660  lea     rax, aQmsvc; "QMsvc"
0x180005667  mov     edx, 104h
0x18000566c  lea     r8, [rbp+1F0h+var_250]
0x180005670  test    rdi, rdi
0x180005673  jz      short loc_180005692
0x180005675  movzx   ecx, word ptr [rax]
0x180005678  test    cx, cx
0x18000567b  jz      short loc_180005692
0x18000567d  add     rax, 2
0x180005681  mov     [r8], cx
0x180005685  add     r8, 2
0x180005689  dec     rdi
0x18000568c  sub     rdx, 1
0x180005690  jnz     short loc_180005670
0x180005692  mov     rax, rdx
0x180005695  neg     rax
0x180005698  sbb     r9d, r9d
0x18000569b  not     r9d
0x18000569e  and     r9d, 8007007Ah
0x1800056a5  lea     rcx, [r8-2]
0x1800056a9  test    rdx, rdx
0x1800056ac  cmovnz  rcx, r8
0x1800056b0  mov     [rcx], r15w
0x1800056b4  jz      loc_18000583B
0x1800056ba  lea     rcx, [rbp+1F0h+var_250]
0x1800056be  mov     [rsp+2F0h+Endpoint], r15
0x1800056c3  lea     r8, [rsp+2F0h+Endpoint]
0x1800056c8  mov     rdx, r14
0x1800056cb  call    cs:__imp_?ComposeRPCEndPointName@@YAXPEB_W0PEAPEA_W@Z; ComposeRPCEndPointName(wchar_t const *,wchar_t const *,wchar_t * *)
0x1800056d1  lea     rdi, WPP_GLOBAL_Control
0x1800056d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056df  cmp     rcx, rdi
0x1800056e2  jz      short loc_1800056FD
0x1800056e4  test    byte ptr [rcx+6Ch], 4
0x1800056e8  jz      short loc_1800056FD
0x1800056ea  mov     edx, 1Eh
0x1800056ef  mov     r9, [rsp+2F0h+Endpoint]
0x1800056f4  mov     rcx, [rcx+60h]
0x1800056f8  call    WPP_SF_S
0x1800056fd  mov     [rsp+2F0h+String], r15
0x180005702  lea     rax, [rsp+2F0h+String]
0x180005707  mov     [rsp+2F0h+StringBinding], rax; StringBinding
0x18000570c  mov     [rsp+2F0h+Options], r15; Options
0x180005711  mov     r9, [rsp+2F0h+Endpoint]; Endpoint
0x180005716  xor     r8d, r8d; NetworkAddr
0x180005719  lea     rdx, ProtSeq; "ncalrpc"
0x180005720  xor     ecx, ecx; ObjUuid
0x180005722  call    cs:__imp_RpcStringBindingComposeW
0x180005728  test    eax, eax
0x18000572a  jnz     loc_180005886
0x180005730  mov     [rsp+2F0h+Binding], r15
0x180005735  lea     rdx, [rsp+2F0h+Binding]; Binding
0x18000573a  mov     rcx, [rsp+2F0h+String]; StringBinding
0x18000573f  call    cs:__imp_RpcBindingFromStringBindingW
0x180005745  mov     esi, eax
0x180005747  cmp     [rsp+2F0h+String], r15
0x18000574c  jz      short loc_180005759
0x18000574e  lea     rcx, [rsp+2F0h+String]; String
0x180005753  call    cs:__imp_RpcStringFreeW
0x180005759  test    esi, esi
0x18000575b  jnz     loc_1800058CD
0x180005761  lea     rcx, [rsp+2F0h+Binding]
0x180005766  call    cs:__imp_?MQSec_SetLocalRpcMutualAuth@@YAJPEAPEAX@Z; MQSec_SetLocalRpcMutualAuth(void * *)
0x18000576c  test    eax, eax
0x18000576e  jnz     short loc_1800057AD
0x180005770  mov     rdi, [rsp+2F0h+Binding]
0x180005775  mov     rcx, [rsp+2F0h+Endpoint]; Block
0x18000577a  call    cs:__imp_free
0x180005780  nop
0x180005781  mov     rcx, rbx; Block
0x180005784  call    cs:__imp_free
0x18000578a  nop
0x18000578b  mov     rax, rdi
0x18000578e  mov     rcx, [rbp+1F0h+var_40]
0x180005795  xor     rcx, rsp; StackCookie
0x180005798  call    __security_check_cookie
0x18000579d  add     rsp, 2C8h
0x1800057a4  pop     r15
0x1800057a6  pop     r14
0x1800057a8  pop     rdi
0x1800057a9  pop     rsi
0x1800057aa  pop     rbx
0x1800057ab  pop     rbp
0x1800057ac  retn
0x1800057ad  lea     rdx, [rsp+2F0h+String]
0x1800057b2  lea     rcx, [rsp+2F0h+Binding]
0x1800057b7  call    cs:__imp_?mqrpcUnbindQMService@@YAJPEAPEAXPEAPEA_W@Z; mqrpcUnbindQMService(void * *,wchar_t * *)
0x1800057bd  mov     [rsp+2F0h+Binding], r15
0x1800057c2  mov     [rsp+2F0h+String], r15
0x1800057c7  lea     rcx, [rsp+2F0h+pExceptionObject]
0x1800057cc  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800057d2  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800057d9  lea     rcx, [rsp+2F0h+pExceptionObject]; pExceptionObject
0x1800057de  call    _CxxThrowException_0
0x1800057e4  mov     r8d, 80070057h
0x1800057ea  mov     [rbp+1F0h+sz], r15w
0x1800057ef  lea     rdi, WPP_GLOBAL_Control
0x1800057f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057fd  cmp     rcx, rdi
0x180005800  jz      short loc_18000581E
0x180005802  test    byte ptr [rcx+6Ch], 1
0x180005806  jz      short loc_18000581E
0x180005808  mov     edx, 1Ch
0x18000580d  mov     dword ptr [rsp+2F0h+Options], r8d
0x180005812  mov     r9d, r10d
0x180005815  mov     rcx, [rcx+60h]
0x180005819  call    WPP_SF_Dd
0x18000581e  lea     rcx, [rsp+2F0h+pExceptionObject]
0x180005823  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180005829  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180005830  lea     rcx, [rsp+2F0h+pExceptionObject]; pExceptionObject
0x180005835  call    _CxxThrowException_0
0x18000583b  lea     rdi, WPP_GLOBAL_Control
0x180005842  mov     rcx, cs:WPP_GLOBAL_Control
0x180005849  cmp     rcx, rdi
0x18000584c  jz      short loc_180005869
0x18000584e  test    byte ptr [rcx+6Ch], 1
0x180005852  jz      short loc_180005869
0x180005854  mov     edx, 1Dh
0x180005859  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x180005860  mov     rcx, [rcx+60h]
0x180005864  call    WPP_SF_d
0x180005869  lea     rcx, [rsp+2F0h+pExceptionObject]
0x18000586e  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180005874  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18000587b  lea     rcx, [rsp+2F0h+pExceptionObject]; pExceptionObject
0x180005880  call    _CxxThrowException_0
0x180005886  mov     rcx, cs:WPP_GLOBAL_Control
0x18000588d  cmp     rcx, rdi
0x180005890  jz      short loc_1800058B0
0x180005892  test    byte ptr [rcx+6Ch], 1
0x180005896  jz      short loc_1800058B0
0x180005898  mov     edx, 1Fh
0x18000589d  mov     r9d, eax
0x1800058a0  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x1800058a7  mov     rcx, [rcx+60h]
0x1800058ab  call    WPP_SF_d
0x1800058b0  lea     rcx, [rsp+2F0h+pExceptionObject]
0x1800058b5  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800058bb  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800058c2  lea     rcx, [rsp+2F0h+pExceptionObject]; pExceptionObject
0x1800058c7  call    _CxxThrowException_0
0x1800058cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058d4  cmp     rcx, rdi
0x1800058d7  jz      short loc_1800058F7
0x1800058d9  test    byte ptr [rcx+6Ch], 1
0x1800058dd  jz      short loc_1800058F7
0x1800058df  mov     edx, 20h ; ' '
0x1800058e4  mov     r9d, esi
0x1800058e7  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x1800058ee  mov     rcx, [rcx+60h]
0x1800058f2  call    WPP_SF_d
0x1800058f7  lea     rcx, [rsp+2F0h+pExceptionObject]
0x1800058fc  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180005902  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180005909  lea     rcx, [rsp+2F0h+pExceptionObject]; pExceptionObject
0x18000590e  call    _CxxThrowException_0
```
