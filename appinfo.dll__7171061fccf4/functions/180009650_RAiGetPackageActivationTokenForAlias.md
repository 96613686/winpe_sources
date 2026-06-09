# RAiGetPackageActivationTokenForAlias

- ea: `0x180009650`
- end: `0x180009813`
- name: `RAiGetPackageActivationTokenForAlias`
- size: `451`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int64, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180009650`
- `0x180009ba8`
- `0x180009d10`
- `0x18002aa34`
- `0x18002bc04`
- `0x18003ea48`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800097ec`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800097ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800097a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800097a7`

## string_xrefs

- `0x180009773`: `[GetPackageToken]`

## pseudocode

```c
RPC_STATUS __fastcall RAiGetPackageActivationTokenForAlias(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5)
{
  __int64 v9; // rax
  int v10; // ebx
  int v11; // r8d
  const unsigned __int16 *v12; // rax
  int v13; // edx
  unsigned int v15; // [rsp+50h] [rbp-B0h] BYREF
  int Reply; // [rsp+54h] [rbp-ACh] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD *v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  char v22; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[256]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[272]; // [rsp+1C0h] [rbp+C0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, a3, a3, a4);
  v20 = a4;
  v18 = a5;
  v19 = a3;
  v21 = a2;
  *a5 = 0;
  v15 = 0;
  memset_0(v23, 0, sizeof(v23));
  memset_0(v24, 0, 0x104u);
  hMem = 0;
  v9 = lambda_cc9f5f9dcf4736fa4d92ceeeb3ad16cb_::_lambda_cc9f5f9dcf4736fa4d92ceeeb3ad16cb_(
         (unsigned int)&v22,
         (unsigned int)&v21,
         (unsigned int)&v20,
         (unsigned int)&v19,
         (__int64)v24,
         (__int64)v23,
         (__int64)&hMem,
         (__int64)&v15,
         (__int64)&v18);
  v10 = lambda_cc9f5f9dcf4736fa4d92ceeeb3ad16cb_::operator()(v9);
  if ( v10 < 0 )
  {
    if ( hMem )
      v12 = AipJustFileName((const unsigned __int16 *)hMem);
    else
      v12 = 0;
    AipLogDesktopAppXProcessStartFailure(v15, (unsigned int)v10, v23, v12, v24, L"[GetPackageToken]");
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v10 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v11, a3, v10);
  }
  v13 = (unsigned __int16)v10;
  if ( v10 >= 0 )
    v13 = 0;
  Reply = v13;
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180009650  push    rbp
0x180009652  push    rbx
0x180009653  push    rsi
0x180009654  push    rdi
0x180009655  push    r12
0x180009657  push    r14
0x180009659  push    r15
0x18000965b  lea     rbp, [rsp-1E0h]
0x180009663  sub     rsp, 2E0h
0x18000966a  mov     rax, cs:__security_cookie
0x180009671  xor     rax, rsp
0x180009674  mov     [rbp+210h+var_40], rax
0x18000967b  mov     rbx, [rbp+210h+arg_20]
0x180009682  mov     rsi, r9
0x180009685  mov     r15, r8
0x180009688  mov     r14, rdx
0x18000968b  mov     rdi, rcx
0x18000968e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009695  lea     r12, WPP_GLOBAL_Control
0x18000969c  cmp     rcx, r12
0x18000969f  jz      short loc_1800096BC
0x1800096a1  test    byte ptr [rcx+1Ch], 1
0x1800096a5  jz      short loc_1800096BC
0x1800096a7  mov     rcx, [rcx+10h]
0x1800096ab  mov     edx, 1Eh
0x1800096b0  mov     r9, r8
0x1800096b3  mov     dword ptr [rsp+310h+var_2F0], esi
0x1800096b7  call    WPP_SF_SD
0x1800096bc  mov     [rsp+310h+var_2A0], rsi
0x1800096c1  lea     rcx, [rbp+210h+var_250]; void *
0x1800096c5  xorps   xmm0, xmm0
0x1800096c8  mov     [rsp+310h+var_2B0], rbx
0x1800096cd  xor     esi, esi
0x1800096cf  mov     [rsp+310h+var_2A8], r15
0x1800096d4  mov     [rsp+310h+var_298], r14
0x1800096d9  xor     edx, edx; Val
0x1800096db  movups  xmmword ptr [rbx], xmm0
0x1800096de  mov     r8d, 100h; Size
0x1800096e4  mov     [rsp+310h+var_2C0], esi
0x1800096e8  call    memset_0
0x1800096ed  xor     edx, edx; Val
0x1800096ef  lea     rcx, [rbp+210h+var_150]; void *
0x1800096f6  mov     r8d, 104h; Size
0x1800096fc  call    memset_0
0x180009701  lea     rax, [rsp+310h+var_2B0]
0x180009706  mov     [rsp+310h+hMem], rsi
0x18000970b  mov     [rsp+310h+var_2D0], rax
0x180009710  lea     r9, [rsp+310h+var_2A8]
0x180009715  lea     rax, [rsp+310h+var_2C0]
0x18000971a  mov     [rsp+310h+var_2D8], rax
0x18000971f  lea     r8, [rsp+310h+var_2A0]
0x180009724  lea     rax, [rsp+310h+hMem]
0x180009729  mov     [rsp+310h+var_2E0], rax
0x18000972e  lea     rdx, [rsp+310h+var_298]
0x180009733  lea     rax, [rbp+210h+var_250]
0x180009737  mov     [rsp+310h+var_2E8], rax
0x18000973c  lea     rcx, [rbp+210h+var_290]
0x180009740  lea     rax, [rbp+210h+var_150]
0x180009747  mov     [rsp+310h+var_2F0], rax
0x18000974c  call    _lambda_cc9f5f9dcf4736fa4d92ceeeb3ad16cb____lambda_cc9f5f9dcf4736fa4d92ceeeb3ad16cb_
0x180009751  mov     rcx, rax
0x180009754  call    _lambda_cc9f5f9dcf4736fa4d92ceeeb3ad16cb___operator__
0x180009759  mov     ebx, eax
0x18000975b  test    eax, eax
0x18000975d  jns     short loc_18000979D
0x18000975f  mov     rcx, [rsp+310h+hMem]; unsigned __int16 *
0x180009764  test    rcx, rcx
0x180009767  jz      short loc_180009770
0x180009769  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18000976e  jmp     short loc_180009773
0x180009770  mov     rax, rsi
0x180009773  lea     rcx, aGetpackagetoke; "[GetPackageToken]"
0x18000977a  mov     r9, rax
0x18000977d  mov     [rsp+310h+var_2E8], rcx
0x180009782  lea     r8, [rbp+210h+var_250]
0x180009786  lea     rcx, [rbp+210h+var_150]
0x18000978d  mov     edx, ebx
0x18000978f  mov     [rsp+310h+var_2F0], rcx
0x180009794  mov     ecx, [rsp+310h+var_2C0]
0x180009798  call    ?AipLogDesktopAppXProcessStartFailure@@YAXW4DesktopAppXProcessStartFailureCheckpoint@@JPEBG111@Z; AipLogDesktopAppXProcessStartFailure(DesktopAppXProcessStartFailureCheckpoint,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000979d  mov     rcx, [rsp+310h+hMem]; hMem
0x1800097a2  test    rcx, rcx
0x1800097a5  jz      short loc_1800097AD
0x1800097a7  call    cs:__imp_LocalFree
0x1800097ad  test    ebx, ebx
0x1800097af  jns     short loc_1800097D8
0x1800097b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097b8  cmp     rcx, r12
0x1800097bb  jz      short loc_1800097D8
0x1800097bd  test    byte ptr [rcx+1Ch], 1
0x1800097c1  jz      short loc_1800097D8
0x1800097c3  mov     rcx, [rcx+10h]
0x1800097c7  mov     edx, 1Fh
0x1800097cc  mov     r9, r15
0x1800097cf  mov     dword ptr [rsp+310h+var_2F0], ebx
0x1800097d3  call    WPP_SF_SD
0x1800097d8  test    ebx, ebx
0x1800097da  movzx   edx, bx
0x1800097dd  mov     rcx, rdi; pAsync
0x1800097e0  cmovns  edx, esi
0x1800097e3  mov     [rsp+310h+Reply], edx
0x1800097e7  lea     rdx, [rsp+310h+Reply]; Reply
0x1800097ec  call    cs:__imp_RpcAsyncCompleteCall
0x1800097f2  mov     rcx, [rbp+210h+var_40]
0x1800097f9  xor     rcx, rsp; StackCookie
0x1800097fc  call    __security_check_cookie
0x180009801  add     rsp, 2E0h
0x180009808  pop     r15
0x18000980a  pop     r14
0x18000980c  pop     r12
0x18000980e  pop     rdi
0x18000980f  pop     rsi
0x180009810  pop     rbx
0x180009811  pop     rbp
0x180009812  retn
```
