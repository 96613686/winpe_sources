# RAiGetPackageActivationTokenForAlias

- ea: `0x18000bfd0`
- end: `0x18000c1a0`
- name: `RAiGetPackageActivationTokenForAlias`
- size: `464`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000a1f0`
- `0x18000bfd0`
- `0x180026b48`
- `0x180027c34`
- `0x18002bf84`
- `0x18003c7b4`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c172`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c172`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c127`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c127`

## string_xrefs

- `0x18000c0f3`: `[GetPackageToken]`

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
  int v13; // eax
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
  v9 = lambda_45b8fde58cee030302110ef33f1d94f7_::_lambda_45b8fde58cee030302110ef33f1d94f7_(
         (unsigned int)&v22,
         (unsigned int)&v21,
         (unsigned int)&v20,
         (unsigned int)&v19,
         (__int64)v24,
         (__int64)v23,
         (__int64)&hMem,
         (__int64)&v15,
         (__int64)&v18);
  v10 = lambda_45b8fde58cee030302110ef33f1d94f7_::operator()(v9);
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
0x18000bfd0  push    rbp
0x18000bfd2  push    rbx
0x18000bfd3  push    rsi
0x18000bfd4  push    rdi
0x18000bfd5  push    r12
0x18000bfd7  push    r14
0x18000bfd9  push    r15
0x18000bfdb  lea     rbp, [rsp-1E0h]
0x18000bfe3  sub     rsp, 2E0h
0x18000bfea  mov     rax, cs:__security_cookie
0x18000bff1  xor     rax, rsp
0x18000bff4  mov     [rbp+210h+var_40], rax
0x18000bffb  mov     rbx, [rbp+210h+arg_20]
0x18000c002  mov     rsi, r9
0x18000c005  mov     r15, r8
0x18000c008  mov     r14, rdx
0x18000c00b  mov     rdi, rcx
0x18000c00e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c015  lea     r12, WPP_GLOBAL_Control
0x18000c01c  cmp     rcx, r12
0x18000c01f  jz      short loc_18000C03C
0x18000c021  test    byte ptr [rcx+1Ch], 1
0x18000c025  jz      short loc_18000C03C
0x18000c027  mov     rcx, [rcx+10h]
0x18000c02b  mov     edx, 1Eh
0x18000c030  mov     r9, r8
0x18000c033  mov     dword ptr [rsp+310h+var_2F0], esi
0x18000c037  call    WPP_SF_SD
0x18000c03c  mov     [rsp+310h+var_2A0], rsi
0x18000c041  lea     rcx, [rbp+210h+var_250]; void *
0x18000c045  xorps   xmm0, xmm0
0x18000c048  mov     [rsp+310h+var_2B0], rbx
0x18000c04d  xor     esi, esi
0x18000c04f  mov     [rsp+310h+var_2A8], r15
0x18000c054  mov     [rsp+310h+var_298], r14
0x18000c059  xor     edx, edx; Val
0x18000c05b  movups  xmmword ptr [rbx], xmm0
0x18000c05e  mov     r8d, 100h; Size
0x18000c064  mov     [rsp+310h+var_2C0], esi
0x18000c068  call    memset_0
0x18000c06d  xor     edx, edx; Val
0x18000c06f  lea     rcx, [rbp+210h+var_150]; void *
0x18000c076  mov     r8d, 104h; Size
0x18000c07c  call    memset_0
0x18000c081  lea     rax, [rsp+310h+var_2B0]
0x18000c086  mov     [rsp+310h+hMem], rsi
0x18000c08b  mov     [rsp+310h+var_2D0], rax
0x18000c090  lea     r9, [rsp+310h+var_2A8]
0x18000c095  lea     rax, [rsp+310h+var_2C0]
0x18000c09a  mov     [rsp+310h+var_2D8], rax
0x18000c09f  lea     r8, [rsp+310h+var_2A0]
0x18000c0a4  lea     rax, [rsp+310h+hMem]
0x18000c0a9  mov     [rsp+310h+var_2E0], rax
0x18000c0ae  lea     rdx, [rsp+310h+var_298]
0x18000c0b3  lea     rax, [rbp+210h+var_250]
0x18000c0b7  mov     [rsp+310h+var_2E8], rax
0x18000c0bc  lea     rcx, [rbp+210h+var_290]
0x18000c0c0  lea     rax, [rbp+210h+var_150]
0x18000c0c7  mov     [rsp+310h+var_2F0], rax
0x18000c0cc  call    _lambda_45b8fde58cee030302110ef33f1d94f7____lambda_45b8fde58cee030302110ef33f1d94f7_
0x18000c0d1  mov     rcx, rax
0x18000c0d4  call    _lambda_45b8fde58cee030302110ef33f1d94f7___operator__
0x18000c0d9  mov     ebx, eax
0x18000c0db  test    eax, eax
0x18000c0dd  jns     short loc_18000C11D
0x18000c0df  mov     rcx, [rsp+310h+hMem]; unsigned __int16 *
0x18000c0e4  test    rcx, rcx
0x18000c0e7  jz      short loc_18000C0F0
0x18000c0e9  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18000c0ee  jmp     short loc_18000C0F3
0x18000c0f0  mov     rax, rsi
0x18000c0f3  lea     rcx, aGetpackagetoke; "[GetPackageToken]"
0x18000c0fa  mov     r9, rax
0x18000c0fd  mov     [rsp+310h+var_2E8], rcx
0x18000c102  lea     r8, [rbp+210h+var_250]
0x18000c106  lea     rcx, [rbp+210h+var_150]
0x18000c10d  mov     edx, ebx
0x18000c10f  mov     [rsp+310h+var_2F0], rcx
0x18000c114  mov     ecx, [rsp+310h+var_2C0]
0x18000c118  call    ?AipLogDesktopAppXProcessStartFailure@@YAXW4DesktopAppXProcessStartFailureCheckpoint@@JPEBG111@Z; AipLogDesktopAppXProcessStartFailure(DesktopAppXProcessStartFailureCheckpoint,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000c11d  mov     rcx, [rsp+310h+hMem]; hMem
0x18000c122  test    rcx, rcx
0x18000c125  jz      short loc_18000C133
0x18000c127  call    cs:__imp_LocalFree
0x18000c12e  nop     dword ptr [rax+rax+00h]
0x18000c133  test    ebx, ebx
0x18000c135  jns     short loc_18000C15E
0x18000c137  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c13e  cmp     rcx, r12
0x18000c141  jz      short loc_18000C15E
0x18000c143  test    byte ptr [rcx+1Ch], 1
0x18000c147  jz      short loc_18000C15E
0x18000c149  mov     rcx, [rcx+10h]
0x18000c14d  mov     edx, 1Fh
0x18000c152  mov     r9, r15
0x18000c155  mov     dword ptr [rsp+310h+var_2F0], ebx
0x18000c159  call    WPP_SF_SD
0x18000c15e  test    ebx, ebx
0x18000c160  movzx   eax, bx
0x18000c163  lea     rdx, [rsp+310h+Reply]; Reply
0x18000c168  mov     rcx, rdi; pAsync
0x18000c16b  cmovns  eax, esi
0x18000c16e  mov     [rsp+310h+Reply], eax
0x18000c172  call    cs:__imp_RpcAsyncCompleteCall
0x18000c179  nop     dword ptr [rax+rax+00h]
0x18000c17e  mov     rcx, [rbp+210h+var_40]
0x18000c185  xor     rcx, rsp; StackCookie
0x18000c188  call    __security_check_cookie
0x18000c18d  add     rsp, 2E0h
0x18000c194  pop     r15
0x18000c196  pop     r14
0x18000c198  pop     r12
0x18000c19a  pop     rdi
0x18000c19b  pop     rsi
0x18000c19c  pop     rbx
0x18000c19d  pop     rbp
0x18000c19e  retn
```
