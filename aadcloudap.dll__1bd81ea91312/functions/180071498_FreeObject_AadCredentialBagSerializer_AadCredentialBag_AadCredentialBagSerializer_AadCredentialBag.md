# FreeObject<AadCredentialBagSerializer,_AadCredentialBag>(AadCredentialBagSerializer &,_AadCredentialBag *)

- ea: `0x180071498`
- end: `0x18007158a`
- name: `??$FreeObject@VAadCredentialBagSerializer@@U_AadCredentialBag@@@@YAJAEAVAadCredentialBagSerializer@@PEAU_AadCredentialBag@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180071958`

## callees

- `0x180003c20`
- `0x180071498`
- `0x1800719c4`
- `0x1800719f8`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18007156a`
- `RPCRT4!MesHandleFree` at `0x18007156a`
- `RPCRT4!NdrMesTypeFree3` at `0x180071530`
- `RPCRT4!NdrMesTypeFree3` at `0x180071530`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x1800714f0`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x1800714f0`

## pseudocode

```c
__int64 __fastcall FreeObject<AadCredentialBagSerializer,_AadCredentialBag>(__int64 a1, _OWORD *a2)
{
  unsigned int v3; // ebx
  int v4; // esp
  unsigned int v5; // edx
  RPC_STATUS v6; // eax
  unsigned int pEncodedSize; // [rsp+34h] [rbp-34h] BYREF
  handle_t pHandle; // [rsp+38h] [rbp-30h] BYREF
  char v10[7]; // [rsp+40h] [rbp-28h] BYREF

  pHandle = 0;
  pEncodedSize = 0;
  if ( a2 )
  {
    v3 = 0;
    v5 = v4 + 88 - (unsigned int)v10;
    v6 = MesEncodeFixedBufferHandleCreate(v10, v5, &pEncodedSize, &pHandle);
    if ( v6 )
    {
      v3 = HandleRpcError(v6);
    }
    else
    {
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, a2);
      *a2 = 0;
    }
  }
  else
  {
    v3 = -2147024809;
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return v3;
}

```

## disassembly

```asm
0x180071498  mov     [rsp+arg_0], rbx
0x18007149d  push    rdi
0x18007149e  sub     rsp, 60h
0x1800714a2  mov     rax, cs:__security_cookie
0x1800714a9  xor     rax, rsp
0x1800714ac  mov     [rsp+68h+var_10], rax
0x1800714b1  mov     rdi, rdx
0x1800714b4  mov     [rsp+68h+pHandle], 0
0x1800714bd  mov     [rsp+68h+pEncodedSize], 0
0x1800714c5  test    rdx, rdx
0x1800714c8  jnz     short loc_1800714D4
0x1800714ca  mov     ebx, 80070057h
0x1800714cf  jmp     loc_180071560
0x1800714d4  xor     ebx, ebx
0x1800714d6  lea     rcx, [rsp+68h+var_21]
0x1800714db  and     rcx, 0FFFFFFFFFFFFFFF8h; pBuffer
0x1800714df  lea     rdx, [rsp+68h+var_10]
0x1800714e4  sub     edx, ecx; BufferSize
0x1800714e6  lea     r9, [rsp+68h+pHandle]; pHandle
0x1800714eb  lea     r8, [rsp+68h+pEncodedSize]; pEncodedSize
0x1800714f0  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x1800714f6  test    eax, eax
0x1800714f8  jz      short loc_180071509
0x1800714fa  mov     ecx, eax; int
0x1800714fc  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x180071501  mov     ebx, eax
0x180071503  mov     [rsp+68h+var_38], eax
0x180071507  jmp     short loc_180071560
0x180071509  mov     [rsp+68h+pObject], rdi; pObject
0x18007150e  mov     [rsp+68h+nTypeIndex], 0; nTypeIndex
0x180071516  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18007151d  lea     r8, pProxyInfo; pProxyInfo
0x180071524  lea     rdx, pPicklingInfo; pPicklingInfo
0x18007152b  mov     rcx, [rsp+68h+pHandle]; Handle
0x180071530  call    cs:__imp_NdrMesTypeFree3
0x180071536  nop
0x180071537  xorps   xmm0, xmm0
0x18007153a  movups  xmmword ptr [rdi], xmm0
0x18007153d  jmp     short loc_180071560
0x18007153f  mov     ebx, eax
0x180071541  test    eax, eax
0x180071543  jle     short loc_18007154E
0x180071545  movzx   ebx, ax
0x180071548  or      ebx, 80070000h
0x18007154e  mov     [rsp+68h+var_38], ebx
0x180071552  mov     eax, 8000FFFFh
0x180071557  test    ebx, ebx
0x180071559  cmovns  ebx, eax
0x18007155c  mov     [rsp+68h+var_38], ebx
0x180071560  mov     rcx, [rsp+68h+pHandle]; Handle
0x180071565  test    rcx, rcx
0x180071568  jz      short loc_180071570
0x18007156a  call    cs:__imp_MesHandleFree
0x180071570  mov     eax, ebx
0x180071572  mov     rcx, [rsp+68h+var_10]
0x180071577  xor     rcx, rsp; StackCookie
0x18007157a  call    __security_check_cookie
0x18007157f  mov     rbx, [rsp+68h+arg_0]
0x180071584  add     rsp, 60h
0x180071588  pop     rdi
0x180071589  retn
0x1800a602b  push    rbp
0x1800a602d  sub     rsp, 30h
0x1800a6031  mov     rbp, rdx
0x1800a6034  mov     rcx, [rcx]
0x1800a6037  mov     ecx, [rcx]; unsigned int
0x1800a6039  call    ?SerializationExceptionFilter@@YAHK@Z; SerializationExceptionFilter(ulong)
0x1800a603e  nop
0x1800a603f  add     rsp, 30h
0x1800a6043  pop     rbp
0x1800a6044  retn
```
