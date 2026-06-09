# SqmUploadMachineConfig

- ea: `0x18000662c`
- end: `0x180006751`
- name: `SqmUploadMachineConfig`
- size: `293`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180006758`

## callees

- `0x18000654c`
- `0x18000662c`

## import_xrefs

- `RPCRT4!I_RpcSystemFunction001` at `0x18000667c`
- `RPCRT4!I_RpcSystemFunction001` at `0x1800066b7`
- `RPCRT4!I_RpcSystemFunction001` at `0x18000667c`
- `RPCRT4!I_RpcSystemFunction001` at `0x1800066b7`
- `ntdll!WinSqmSetDWORD` at `0x18000673d`
- `ntdll!WinSqmSetDWORD` at `0x18000673d`
- `ntdll!RtlGetNtProductType` at `0x180006655`
- `ntdll!RtlGetNtProductType` at `0x180006655`

## pseudocode

```c
char SqmUploadMachineConfig()
{
  int v0; // eax
  unsigned int v1; // ebx
  BOOL v2; // edi
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v6; // [rsp+40h] [rbp+20h] BYREF
  int v7; // [rsp+48h] [rbp+28h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+50h] [rbp+30h] BYREF

  ProductType = 0;
  v7 = 0;
  v6 = 0;
  LOBYTE(v0) = RtlGetNtProductType(&ProductType);
  if ( (_BYTE)v0 )
  {
    v1 = 0;
    v2 = ProductType != NtProductWinNt;
    I_RpcSystemFunction001(4);
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        v1 = 4 * v2;
      }
      else if ( v6 == 2 )
      {
        v1 = v2 ? 8 : 2;
      }
    }
    else
    {
      v1 = !v2;
    }
    I_RpcSystemFunction001(16);
    if ( v6 )
      v1 |= 0x10u;
    if ( !(unsigned int)ReadRpcPolicy(v3, L"DgClientSupportOn", &v7, &v6) && v7 && v6 )
      v1 |= 0x20u;
    v0 = ReadRpcPolicy(v4, L"DgServerSupportOn", &v7, &v6);
    if ( !v0 && v7 && v6 )
      v1 |= 0x40u;
    if ( PortData == 1 && (dword_180013DA8 != 3 || dword_180013DA4 == 1) )
      v1 |= 0x80u;
    if ( v1 )
      LOBYTE(v0) = WinSqmSetDWORD(0, 1181, v1);
  }
  return v0;
}

```

## disassembly

```asm
0x18000662c  mov     [rsp-18h+arg_18], rbx
0x180006631  push    rbp
0x180006632  push    rdi
0x180006633  push    r14
0x180006635  mov     rbp, rsp
0x180006638  sub     rsp, 20h
0x18000663c  lea     rcx, [rbp+ProductType]; ProductType
0x180006640  mov     [rbp+ProductType], 0
0x180006647  mov     [rbp+arg_8], 0
0x18000664e  mov     [rbp+arg_0], 0
0x180006655  call    cs:__imp_RtlGetNtProductType
0x18000665b  test    al, al
0x18000665d  jz      loc_180006743
0x180006663  xor     ebx, ebx
0x180006665  lea     r8, [rbp+arg_0]
0x180006669  xor     edi, edi
0x18000666b  lea     r14d, [rbx+1]
0x18000666f  cmp     [rbp+ProductType], r14d
0x180006673  lea     ecx, [rbx+4]
0x180006676  setnz   dil
0x18000667a  xor     edx, edx
0x18000667c  call    cs:__imp_I_RpcSystemFunction001
0x180006682  mov     eax, [rbp+arg_0]
0x180006685  test    eax, eax
0x180006687  jz      short loc_1800066A8
0x180006689  sub     eax, r14d
0x18000668c  jz      short loc_18000669F
0x18000668e  cmp     eax, r14d
0x180006691  jnz     short loc_1800066AE
0x180006693  neg     edi
0x180006695  sbb     ebx, ebx
0x180006697  and     ebx, 6
0x18000669a  add     ebx, 2
0x18000669d  jmp     short loc_1800066AE
0x18000669f  lea     ebx, ds:0[rdi*4]
0x1800066a6  jmp     short loc_1800066AE
0x1800066a8  test    edi, edi
0x1800066aa  cmovz   ebx, r14d
0x1800066ae  xor     edx, edx
0x1800066b0  lea     r8, [rbp+arg_0]
0x1800066b4  lea     ecx, [rdx+10h]
0x1800066b7  call    cs:__imp_I_RpcSystemFunction001
0x1800066bd  cmp     [rbp+arg_0], 0
0x1800066c1  jz      short loc_1800066C6
0x1800066c3  or      ebx, 10h
0x1800066c6  lea     r9, [rbp+arg_0]
0x1800066ca  lea     r8, [rbp+arg_8]
0x1800066ce  lea     rdx, aDgclientsuppor; "DgClientSupportOn"
0x1800066d5  call    ReadRpcPolicy
0x1800066da  test    eax, eax
0x1800066dc  jnz     short loc_1800066EB
0x1800066de  cmp     [rbp+arg_8], eax
0x1800066e1  jz      short loc_1800066EB
0x1800066e3  cmp     [rbp+arg_0], eax
0x1800066e6  jz      short loc_1800066EB
0x1800066e8  or      ebx, 20h
0x1800066eb  lea     r9, [rbp+arg_0]
0x1800066ef  lea     r8, [rbp+arg_8]
0x1800066f3  lea     rdx, aDgserversuppor; "DgServerSupportOn"
0x1800066fa  call    ReadRpcPolicy
0x1800066ff  test    eax, eax
0x180006701  jnz     short loc_180006710
0x180006703  cmp     [rbp+arg_8], eax
0x180006706  jz      short loc_180006710
0x180006708  cmp     [rbp+arg_0], eax
0x18000670b  jz      short loc_180006710
0x18000670d  or      ebx, 40h
0x180006710  cmp     cs:PortData, r14d
0x180006717  jnz     short loc_18000672F
0x180006719  cmp     cs:dword_180013DA8, 3
0x180006720  jnz     short loc_18000672B
0x180006722  cmp     cs:dword_180013DA4, r14d
0x180006729  jnz     short loc_18000672F
0x18000672b  bts     ebx, 7
0x18000672f  test    ebx, ebx
0x180006731  jz      short loc_180006743
0x180006733  mov     r8d, ebx
0x180006736  mov     edx, 49Dh
0x18000673b  xor     ecx, ecx
0x18000673d  call    cs:__imp_WinSqmSetDWORD
0x180006743  mov     rbx, [rsp+20h+arg_18]
0x180006748  add     rsp, 20h
0x18000674c  pop     r14
0x18000674e  pop     rdi
0x18000674f  pop     rbp
0x180006750  retn
```
