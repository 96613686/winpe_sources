# PCIDLIST_ABSOLUTE_UserUnmarshal

- ea: `0x180002470`
- end: `0x1800025c9`
- name: `PCIDLIST_ABSOLUTE_UserUnmarshal`
- size: `345`
- prototype: `unsigned __int8 *__stdcall(unsigned int *, unsigned __int8 *, LPCITEMIDLIST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002460`

## callees

- `0x180002470`
- `0x1800045ba`
- `0x18000b180`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x1800024f1`
- `RPCRT4!RpcRaiseException` at `0x180002588`
- `RPCRT4!RpcRaiseException` at `0x1800025a9`
- `RPCRT4!RpcRaiseException` at `0x1800025c2`
- `RPCRT4!RpcRaiseException` at `0x1800024f1`
- `RPCRT4!RpcRaiseException` at `0x180002588`
- `RPCRT4!RpcRaiseException` at `0x1800025a9`
- `RPCRT4!RpcRaiseException` at `0x1800025c2`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x1800024ab`
- `RPCRT4!NdrGetUserMarshalInfo` at `0x1800024ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180002542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180002542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800025b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800025b3`

## pseudocode

```c
unsigned __int8 *__stdcall PCIDLIST_ABSOLUTE_UserUnmarshal(unsigned int *a1, unsigned __int8 *a2, LPCITEMIDLIST *a3)
{
  RPC_STATUS UserMarshalInfo; // eax
  unsigned __int8 *v7; // rax
  unsigned __int64 v8; // rax
  unsigned __int8 *v9; // rdi
  unsigned int v10; // edx
  unsigned __int8 *v11; // r8
  __int64 v12; // rax
  ITEMIDLIST *v13; // rax
  const ITEMIDLIST *v14; // rbx
  SIZE_T v16; // r9
  size_t v17; // rsi
  NDR_USER_MARSHAL_INFO pMarshalInfo; // [rsp+20h] [rbp-68h] BYREF

  memset_0(&pMarshalInfo, 0, sizeof(pMarshalInfo));
  UserMarshalInfo = NdrGetUserMarshalInfo(a1, 1u, &pMarshalInfo);
  if ( UserMarshalInfo )
    RpcRaiseException(UserMarshalInfo);
  if ( a2 < pMarshalInfo.Level1.Buffer
    || (v7 = (unsigned __int8 *)pMarshalInfo.Level1.Buffer + pMarshalInfo.Level1.BufferSize, a2 > v7) )
  {
    RpcRaiseException(1784);
  }
  v8 = v7 - a2;
  if ( v8 < 4 )
    goto LABEL_5;
  v16 = *(unsigned int *)a2;
  v17 = v16;
  if ( v16 > v8 - 4 )
    goto LABEL_5;
  v9 = a2 + 4;
  if ( !(_DWORD)v16 )
  {
    CoTaskMemFree((LPVOID)*a3);
    v14 = 0;
    goto LABEL_16;
  }
  v10 = 2;
  v11 = v9;
  if ( (unsigned int)v16 < 2 )
    goto LABEL_5;
  while ( 1 )
  {
    v12 = *(unsigned __int16 *)v11;
    if ( (unsigned int)v12 < 2 || (unsigned int)v12 > (unsigned int)v16 - v10 )
      break;
    v10 += v12;
    v11 += v12;
    if ( v10 > (unsigned int)v16 )
      goto LABEL_5;
  }
  if ( v10 > (unsigned int)v16 || (_WORD)v12 )
LABEL_5:
    RpcRaiseException(1783);
  v13 = (ITEMIDLIST *)CoTaskMemRealloc((LPVOID)*a3, v16);
  v14 = v13;
  if ( !v13 )
    RpcRaiseException(-2147024882);
  memcpy_0(v13, v9, v17);
LABEL_16:
  *a3 = v14;
  return &v9[v17];
}

```

## disassembly

```asm
0x180002470  mov     [rsp+arg_8], rbx
0x180002475  mov     [rsp+arg_10], rdi
0x18000247a  push    r14
0x18000247c  sub     rsp, 80h
0x180002483  mov     r14, r8
0x180002486  mov     rdi, rdx
0x180002489  mov     rbx, rcx
0x18000248c  xor     edx, edx; Val
0x18000248e  mov     r8d, 58h ; 'X'; Size
0x180002494  lea     rcx, [rsp+88h+pMarshalInfo]; void *
0x180002499  call    memset_0
0x18000249e  lea     r8, [rsp+88h+pMarshalInfo]; pMarshalInfo
0x1800024a3  mov     edx, 1; InformationLevel
0x1800024a8  mov     rcx, rbx; pFlags
0x1800024ab  call    cs:__imp_NdrGetUserMarshalInfo
0x1800024b1  test    eax, eax
0x1800024b3  jnz     loc_1800025A7
0x1800024b9  mov     rcx, qword ptr [rsp+88h+pMarshalInfo.8]
0x1800024be  cmp     rdi, rcx
0x1800024c1  jb      loc_1800025BD
0x1800024c7  mov     eax, dword ptr [rsp+88h+pMarshalInfo.8+8]
0x1800024cb  add     rax, rcx
0x1800024ce  cmp     rdi, rax
0x1800024d1  ja      loc_1800025BD
0x1800024d7  sub     rax, rdi
0x1800024da  mov     [rsp+88h+arg_0], rsi
0x1800024e2  cmp     rax, 4
0x1800024e6  jnb     loc_18000258F
0x1800024ec  mov     ecx, 6F7h; exception
0x1800024f1  call    cs:__imp_RpcRaiseException
0x1800024f7  int     3; Trap to Debugger
0x1800024f8  add     rdi, 4
0x1800024fc  test    r9d, r9d
0x1800024ff  jz      loc_1800025B0
0x180002505  mov     edx, 2
0x18000250a  mov     r8, rdi
0x18000250d  cmp     r9d, edx
0x180002510  jb      short loc_1800024EC
0x180002512  movzx   eax, word ptr [r8]
0x180002516  cmp     eax, 2
0x180002519  jb      short loc_180002530
0x18000251b  mov     ecx, r9d
0x18000251e  sub     ecx, edx
0x180002520  cmp     eax, ecx
0x180002522  ja      short loc_180002530
0x180002524  add     edx, eax
0x180002526  add     r8, rax
0x180002529  cmp     edx, r9d
0x18000252c  jbe     short loc_180002512
0x18000252e  jmp     short loc_1800024EC
0x180002530  cmp     edx, r9d
0x180002533  ja      short loc_1800024EC
0x180002535  xor     ebx, ebx
0x180002537  cmp     bx, ax
0x18000253a  jnz     short loc_1800024EC
0x18000253c  mov     rcx, [r14]; pv
0x18000253f  mov     rdx, rsi; cb
0x180002542  call    cs:__imp_CoTaskMemRealloc
0x180002548  mov     rbx, rax
0x18000254b  test    rax, rax
0x18000254e  jz      short loc_180002583
0x180002550  mov     r8, rsi; Size
0x180002553  mov     rdx, rdi; Src
0x180002556  mov     rcx, rax; void *
0x180002559  call    memcpy_0
0x18000255e  mov     [r14], rbx
0x180002561  lea     r11, [rsp+88h+var_8]
0x180002569  mov     rbx, [r11+18h]
0x18000256d  lea     rax, [rdi+rsi]
0x180002571  mov     rdi, [r11+20h]
0x180002575  mov     rsi, [rsp+88h+arg_0]
0x18000257d  mov     rsp, r11
0x180002580  pop     r14
0x180002582  retn
0x180002583  mov     ecx, 8007000Eh; exception
0x180002588  call    cs:__imp_RpcRaiseException
0x18000258e  int     3; Trap to Debugger
0x18000258f  mov     r9d, [rdi]
0x180002592  add     rax, 0FFFFFFFFFFFFFFFCh
0x180002596  mov     esi, r9d
0x180002599  cmp     r9, rax
0x18000259c  ja      loc_1800024EC
0x1800025a2  jmp     loc_1800024F8
0x1800025a7  mov     ecx, eax; exception
0x1800025a9  call    cs:__imp_RpcRaiseException
0x1800025af  int     3; Trap to Debugger
0x1800025b0  mov     rcx, [r14]; pv
0x1800025b3  call    cs:__imp_CoTaskMemFree
0x1800025b9  xor     ebx, ebx
0x1800025bb  jmp     short loc_18000255E
0x1800025bd  mov     ecx, 6F8h; exception
0x1800025c2  call    cs:__imp_RpcRaiseException
```
