# CGetExtendedWhereabouts_State_QueueingResponse::Enter_State(CGetExtendedWhereabouts *)

- ea: `0x180037970`
- end: `0x180037b30`
- name: `?Enter_State@CGetExtendedWhereabouts_State_QueueingResponse@@UEAAXPEAVCGetExtendedWhereabouts@@@Z`
- size: `448`
- prototype: `void(CGetExtendedWhereabouts_State_QueueingResponse *__hidden this, struct CGetExtendedWhereabouts *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180037ba0`

## callees

- `0x18000bc40`
- `0x18000fe9c`
- `0x18001cfd8`
- `0x1800240f0`
- `0x180025104`
- `0x180037970`
- `0x18003c7a4`
- `0x1800846c0`
- `0x1800b83ee`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800379d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800379d7`

## string_xrefs

- `0x180037a05`: `CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\complus\dtc\dtc\tm\src\tmextendedwhereabouts.cpp@206): Mis-calculated whereabouts (1)`
- `0x180037ab0`: `CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\complus\dtc\dtc\tm\src\tmextendedwhereabouts.cpp@228): Mis-calculated whereabouts (2)`
- `0x180037aa3`: `CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\complus\dtc\dtc\tm\src\tmextendedwhereabouts.cpp@235): Mis-calculated whereabouts (3)`
- `0x180037a96`: `CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\complus\dtc\dtc\tm\src\tmextendedwhereabouts.cpp@242): Mis-calculated whereabouts (4)`
- `0x180037a89`: `CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\complus\dtc\dtc\tm\src\tmextendedwhereabouts.cpp@249): Mis-calculated whereabouts (5)`
- `0x180037ac1`: `CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\complus\dtc\dtc\tm\src\tmextendedwhereabouts.cpp@259): Mis-calculated whereabouts (6)`

## pseudocode

```c
void __fastcall CGetExtendedWhereabouts_State_QueueingResponse::Enter_State(
        CGetExtendedWhereabouts_State_QueueingResponse *this,
        struct CGetExtendedWhereabouts *a2)
{
  int Protocols; // eax
  _QWORD *v4; // rsi
  unsigned int v5; // ebp
  __int64 v6; // rdx
  signed int i; // r15d
  __int64 v8; // rcx
  void *v9; // rax
  int v10; // edi
  __int64 v11; // rbx
  __int64 j; // r12
  __int64 v13; // r13
  int v14; // edi
  void *v15; // rbx
  int v16; // edi
  __int64 v17; // rax
  int v18; // edi
  __int64 k; // rdi
  unsigned int v20; // [rsp+70h] [rbp+18h] BYREF
  void *Block; // [rsp+78h] [rbp+20h] BYREF

  Block = 0;
  v20 = 0;
  Protocols = CGatewayProtocolList::GetProtocols(this, &v20, (struct CGatewayProtocol ***)&Block);
  v4 = Block;
  v5 = v20;
  if ( Protocols < 0 )
    goto LABEL_21;
  v6 = 0;
  for ( i = 4; (unsigned int)v6 < v20; i += *(_DWORD *)(v8 + 132) )
  {
    v8 = *((_QWORD *)Block + v6);
    v6 = (unsigned int)(v6 + 1);
  }
  v9 = CoTaskMemAlloc(i);
  *((_QWORD *)a2 + 8) = v9;
  if ( v9 )
  {
    memset_0(v9, 0, i);
    v10 = i - 4;
    **((_DWORD **)a2 + 8) = v5;
    if ( i - 4 < 0 )
      DtcInternalErrorW(
        L"CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\\complus\\dtc\\dtc\\tm\\src\\tmextendedwhereabo"
         "uts.cpp@206): Mis-calculated whereabouts (1)");
    v11 = *((_QWORD *)a2 + 8) + 4LL;
    for ( j = 0; (unsigned int)j < v5; j = (unsigned int)(j + 1) )
    {
      v13 = v4[j];
      v14 = v10 - 8;
      *(_DWORD *)v11 = 4;
      *(_DWORD *)(v11 + 4) = *(_DWORD *)(v13 + 128) + 16;
      if ( v14 <= 0 )
        DtcInternalErrorW(
          L"CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\\complus\\dtc\\dtc\\tm\\src\\tmextendedwherea"
           "bouts.cpp@228): Mis-calculated whereabouts (2)");
      *(_OWORD *)(v11 + 8) = *(_OWORD *)(v13 + 96);
      v15 = (void *)(v11 + 24);
      v16 = v14 - 16;
      if ( v16 < 0 )
        DtcInternalErrorW(
          L"CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\\complus\\dtc\\dtc\\tm\\src\\tmextendedwherea"
           "bouts.cpp@235): Mis-calculated whereabouts (3)");
      memcpy_0(v15, *(const void **)(v13 + 120), *(unsigned int *)(v13 + 128));
      v17 = *(unsigned int *)(v13 + 128);
      v11 = (__int64)v15 + v17;
      v18 = v16 - v17;
      if ( v18 < 0 )
        DtcInternalErrorW(
          L"CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\\complus\\dtc\\dtc\\tm\\src\\tmextendedwherea"
           "bouts.cpp@242): Mis-calculated whereabouts (4)");
      v10 = v11 + v18 - ((v11 + 3) & 0xFFFFFFFC);
      if ( v10 < 0 )
        DtcInternalErrorW(
          L"CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\\complus\\dtc\\dtc\\tm\\src\\tmextendedwherea"
           "bouts.cpp@249): Mis-calculated whereabouts (5)");
    }
    if ( v10 )
      DtcInternalErrorW(
        L"CGetExtendedWhereabouts_State_QueueingResponse::Enter_State (com\\complus\\dtc\\dtc\\tm\\src\\tmextendedwhereabo"
         "uts.cpp@259): Mis-calculated whereabouts (6)");
    CConnectionHelper::SendBuffer(a2, 0x5A02u, *((void **)a2 + 8), i);
  }
  else
  {
LABEL_21:
    CConnectionHelper::QueueMessageTag(a2, 0x5A03u);
  }
  if ( v4 )
  {
    for ( k = 0; (unsigned int)k < v5; k = (unsigned int)(k + 1) )
    {
      CGatewayProtocol::Release((CGatewayProtocol *)v4[k]);
      v4[k] = 0;
    }
    operator delete(v4);
  }
}

```

## disassembly

```asm
0x180037970  mov     rax, rsp
0x180037973  mov     [rax+8], rbx
0x180037977  push    rbp
0x180037978  push    rsi
0x180037979  push    rdi
0x18003797a  push    r12
0x18003797c  push    r13
0x18003797e  push    r14
0x180037980  push    r15
0x180037982  sub     rsp, 20h
0x180037986  mov     r14, rdx
0x180037989  mov     qword ptr [rax+20h], 0
0x180037991  lea     rdx, [rax+18h]; unsigned int *
0x180037995  mov     dword ptr [rax+18h], 0
0x18003799c  lea     r8, [rax+20h]; struct CGatewayProtocol ***
0x1800379a0  call    ?GetProtocols@CGatewayProtocolList@@QEAAJPEAKPEAPEAPEAVCGatewayProtocol@@@Z; CGatewayProtocolList::GetProtocols(ulong *,CGatewayProtocol * * *)
0x1800379a5  mov     rsi, [rsp+58h+Block]
0x1800379aa  mov     ebp, [rsp+58h+arg_10]
0x1800379ae  test    eax, eax
0x1800379b0  js      loc_180037AE4
0x1800379b6  xor     edx, edx
0x1800379b8  lea     r15d, [rdx+4]
0x1800379bc  test    ebp, ebp
0x1800379be  jz      short loc_1800379D1
0x1800379c0  mov     rcx, [rsi+rdx*8]
0x1800379c4  inc     edx
0x1800379c6  add     r15d, [rcx+84h]
0x1800379cd  cmp     edx, ebp
0x1800379cf  jb      short loc_1800379C0
0x1800379d1  movsxd  rbx, r15d
0x1800379d4  mov     rcx, rbx; cb
0x1800379d7  call    cs:__imp_CoTaskMemAlloc
0x1800379dd  mov     [r14+40h], rax
0x1800379e1  test    rax, rax
0x1800379e4  jz      loc_180037AE4
0x1800379ea  mov     r8, rbx; Size
0x1800379ed  xor     edx, edx; Val
0x1800379ef  mov     rcx, rax; void *
0x1800379f2  call    memset_0
0x1800379f7  mov     rax, [r14+40h]
0x1800379fb  lea     edi, [r15-4]
0x1800379ff  mov     [rax], ebp
0x180037a01  test    edi, edi
0x180037a03  jns     short loc_180037A12
0x180037a05  lea     rcx, aCgetextendedwh; "CGetExtendedWhereabouts_State_QueueingR"...
0x180037a0c  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180037a12  mov     rbx, [r14+40h]
0x180037a16  add     rbx, 4
0x180037a1a  xor     r12d, r12d
0x180037a1d  cmp     r12d, ebp
0x180037a20  jnb     loc_180037ABD
0x180037a26  mov     r13, [rsi+r12*8]
0x180037a2a  add     edi, 0FFFFFFF8h
0x180037a2d  mov     dword ptr [rbx], 4
0x180037a33  mov     eax, [r13+80h]
0x180037a3a  add     eax, 10h
0x180037a3d  mov     [rbx+4], eax
0x180037a40  test    edi, edi
0x180037a42  jle     short loc_180037AB0
0x180037a44  movups  xmm0, xmmword ptr [r13+60h]
0x180037a49  movdqu  xmmword ptr [rbx+8], xmm0
0x180037a4e  add     rbx, 18h
0x180037a52  add     edi, 0FFFFFFF0h
0x180037a55  js      short loc_180037AA3
0x180037a57  mov     r8d, [r13+80h]; Size
0x180037a5e  mov     rcx, rbx; void *
0x180037a61  mov     rdx, [r13+78h]; Src
0x180037a65  call    memcpy_0
0x180037a6a  mov     eax, [r13+80h]
0x180037a71  add     rbx, rax
0x180037a74  sub     edi, eax
0x180037a76  js      short loc_180037A96
0x180037a78  lea     eax, [rbx+3]
0x180037a7b  and     eax, 0FFFFFFFCh
0x180037a7e  sub     edi, eax
0x180037a80  add     edi, ebx
0x180037a82  js      short loc_180037A89
0x180037a84  inc     r12d
0x180037a87  jmp     short loc_180037A1D
0x180037a89  lea     rcx, aCgetextendedwh_1; "CGetExtendedWhereabouts_State_QueueingR"...
0x180037a90  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180037a96  lea     rcx, aCgetextendedwh_4; "CGetExtendedWhereabouts_State_QueueingR"...
0x180037a9d  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180037aa3  lea     rcx, aCgetextendedwh_2; "CGetExtendedWhereabouts_State_QueueingR"...
0x180037aaa  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180037ab0  lea     rcx, aCgetextendedwh_0; "CGetExtendedWhereabouts_State_QueueingR"...
0x180037ab7  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180037abd  test    edi, edi
0x180037abf  jz      short loc_180037ACE
0x180037ac1  lea     rcx, aCgetextendedwh_3; "CGetExtendedWhereabouts_State_QueueingR"...
0x180037ac8  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180037ace  mov     r8, [r14+40h]; void *
0x180037ad2  mov     r9d, r15d; unsigned int
0x180037ad5  mov     edx, 5A02h; unsigned int
0x180037ada  mov     rcx, r14; this
0x180037add  call    ?SendBuffer@CConnectionHelper@@QEAAXKPEAXK@Z; CConnectionHelper::SendBuffer(ulong,void *,ulong)
0x180037ae2  jmp     short loc_180037AF1
0x180037ae4  mov     edx, 5A03h; unsigned int
0x180037ae9  mov     rcx, r14; this
0x180037aec  call    ?QueueMessageTag@CConnectionHelper@@QEAAXK@Z; CConnectionHelper::QueueMessageTag(ulong)
0x180037af1  test    rsi, rsi
0x180037af4  jz      short loc_180037B1B
0x180037af6  xor     edi, edi
0x180037af8  test    ebp, ebp
0x180037afa  jz      short loc_180037B13
0x180037afc  mov     rcx, [rsi+rdi*8]; this
0x180037b00  call    ?Release@CGatewayProtocol@@QEAAXXZ; CGatewayProtocol::Release(void)
0x180037b05  mov     qword ptr [rsi+rdi*8], 0
0x180037b0d  inc     edi
0x180037b0f  cmp     edi, ebp
0x180037b11  jb      short loc_180037AFC
0x180037b13  mov     rcx, rsi; Block
0x180037b16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037b1b  mov     rbx, [rsp+58h+arg_0]
0x180037b20  add     rsp, 20h
0x180037b24  pop     r15
0x180037b26  pop     r14
0x180037b28  pop     r13
0x180037b2a  pop     r12
0x180037b2c  pop     rdi
0x180037b2d  pop     rsi
0x180037b2e  pop     rbp
0x180037b2f  retn
```
