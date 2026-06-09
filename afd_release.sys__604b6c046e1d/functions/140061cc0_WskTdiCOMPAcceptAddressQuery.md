# WskTdiCOMPAcceptAddressQuery

- ea: `0x140061cc0`
- end: `0x140061f28`
- name: `WskTdiCOMPAcceptAddressQuery`
- size: `616`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140002150`
- `0x140003670`
- `0x140005b60`
- `0x140015990`
- `0x140061828`
- `0x140061cc0`
- `0x14006280c`
- `0x1400638bc`
- `0x140063aa4`
- `0x140063eac`
- `0x140063fc0`
- `0x1400726a0`
- `0x140072780`
- `0x140072800`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140061d35`
- `ntoskrnl!IoFreeIrp` at `0x140061d35`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061df6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061ee5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061df6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061ee5`
- `ntoskrnl!IoFreeMdl` at `0x140061d22`
- `ntoskrnl!IoFreeMdl` at `0x140061d22`

## pseudocode

```c
__int64 __fastcall WskTdiCOMPAcceptAddressQuery(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // rbp
  volatile signed __int32 *v6; // r15
  _WORD *v7; // r14
  int Status; // ebx
  __int64 v9; // rcx
  size_t v10; // rbx
  void *PoolPriority; // rax
  size_t v12; // rdx
  __int64 v13; // rcx
  __int64 ZeroedFromLookasideList; // rax
  __int64 v15; // rdx
  _QWORD v17[10]; // [rsp+20h] [rbp-88h] BYREF

  v3 = *(_QWORD *)(a3 + 192);
  if ( (*(_DWORD *)(v3 + 16) & 0x20) == 0
    || (v6 = (volatile signed __int32 *)(v3 + 180), (*(_DWORD *)(a3 + 16) & 0x10) == 0) )
  {
    v6 = (volatile signed __int32 *)(v3 + 176);
  }
  v7 = *(_WORD **)(a3 + 48);
  *(_QWORD *)(a3 + 48) = 0;
  IoFreeMdl(a2->MdlAddress);
  Status = a2->IoStatus.Status;
  IoFreeIrp(a2);
  if ( Status < 0 )
    goto LABEL_24;
  if ( (*(_DWORD *)(a3 + 16) & 0x10) == 0 )
  {
    v10 = (unsigned __int16)(v7[8] + 2);
    if ( (unsigned int)v10 > (unsigned int)AfdStandardAddressLength )
      PoolPriority = (void *)AfdAllocatePoolPriority(64, v10, 1382311489, 0);
    else
      PoolPriority = AfdAllocateZeroedFromLookasideList(v9, v10);
    *(_QWORD *)(a3 + 48) = PoolPriority;
    if ( PoolPriority )
    {
      memmove(PoolPriority, v7 + 9, v10);
      goto LABEL_16;
    }
LABEL_24:
    if ( v7 )
      ExFreeToNPagedLookasideList(&stru_1400877C0, v7);
    goto LABEL_26;
  }
  v12 = SOCKADDR_SIZE(0x17u);
  if ( (unsigned int)v12 > (unsigned int)AfdStandardAddressLength )
    ZeroedFromLookasideList = AfdAllocatePoolPriority(64, v12, 1382311489, 0);
  else
    ZeroedFromLookasideList = (__int64)AfdAllocateZeroedFromLookasideList(v13, v12);
  *(_QWORD *)(a3 + 48) = ZeroedFromLookasideList;
  if ( !ZeroedFromLookasideList )
    goto LABEL_24;
  IN6ADDR_SETV4MAPPED(ZeroedFromLookasideList, v7 + 11, 0, (unsigned __int16)v7[10]);
LABEL_16:
  ExFreeToNPagedLookasideList(&stru_1400877C0, v7);
  if ( !(unsigned __int8)WskTdiRetainTDIEndpoint(v3) )
  {
LABEL_26:
    WskTdiCloseConnectionAndPopulate(a3);
    return 3221225494LL;
  }
  memset(v17, 0, sizeof(v17));
  LODWORD(v17[1]) = *(_DWORD *)(a3 + 256);
  v17[2] = *(_QWORD *)(a3 + 48);
  v17[3] = *(_QWORD *)(a3 + 200);
  v17[5] = WskTdiTLProviderConnectDispatch;
  v17[0] = a3;
  v17[4] = a3;
  _InterlockedIncrement((volatile signed __int32 *)(a3 + 24));
  if ( (*(int (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v3 + 288) + 8LL))(*(_QWORD *)(v3 + 280), v17) < 0 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 24), 0xFFFFFFFF) == 1 )
      WskTdiFreeEndpoint(a3);
    WskTdiReleaseTDIEndpoint(v3);
    goto LABEL_26;
  }
  *(_QWORD *)(a3 + 280) = v17[7];
  WskTdiAllowDelivery(a3);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 24), 0xFFFFFFFF) == 1 )
    WskTdiFreeEndpoint(a3);
  _InterlockedIncrement(v6);
  LOBYTE(v15) = 1;
  WskTdiInitiatePopulate(v3, v15, *(unsigned int *)v6);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140061cc0  mov     [rsp+arg_0], rbx
0x140061cc5  mov     [rsp+arg_18], rbp
0x140061cca  push    rsi
0x140061ccb  push    rdi
0x140061ccc  push    r13
0x140061cce  push    r14
0x140061cd0  push    r15
0x140061cd2  sub     rsp, 80h
0x140061cd9  mov     rax, cs:__security_cookie
0x140061ce0  xor     rax, rsp
0x140061ce3  mov     [rsp+0A8h+var_38], rax
0x140061ce8  mov     rbp, [r8+0C0h]
0x140061cef  mov     rdi, r8
0x140061cf2  mov     r13, rdx
0x140061cf5  mov     eax, [rbp+10h]
0x140061cf8  test    al, 20h
0x140061cfa  jz      short loc_140061D0B
0x140061cfc  mov     eax, [r8+10h]
0x140061d00  lea     r15, [rbp+0B4h]
0x140061d07  test    al, 10h
0x140061d09  jnz     short loc_140061D12
0x140061d0b  lea     r15, [rbp+0B0h]
0x140061d12  mov     r14, [r8+30h]
0x140061d16  mov     qword ptr [r8+30h], 0
0x140061d1e  mov     rcx, [rdx+8]; Mdl
0x140061d22  call    cs:__imp_IoFreeMdl
0x140061d29  nop     dword ptr [rax+rax+00h]
0x140061d2e  mov     ebx, [r13+30h]
0x140061d32  mov     rcx, r13; Irp
0x140061d35  call    cs:__imp_IoFreeIrp
0x140061d3c  nop     dword ptr [rax+rax+00h]
0x140061d41  test    ebx, ebx
0x140061d43  js      loc_140061ED6
0x140061d49  mov     eax, [rdi+10h]
0x140061d4c  test    al, 10h
0x140061d4e  jnz     short loc_140061D9D
0x140061d50  movzx   eax, word ptr [r14+10h]
0x140061d55  add     ax, 2
0x140061d59  movzx   ebx, ax
0x140061d5c  cmp     ebx, cs:AfdStandardAddressLength
0x140061d62  mov     edx, ebx
0x140061d64  ja      short loc_140061D6D
0x140061d66  call    AfdAllocateZeroedFromLookasideList
0x140061d6b  jmp     short loc_140061D7F
0x140061d6d  xor     r9d, r9d
0x140061d70  mov     r8d, 52646641h
0x140061d76  lea     ecx, [r9+40h]
0x140061d7a  call    AfdAllocatePoolPriority
0x140061d7f  mov     [rdi+30h], rax
0x140061d83  test    rax, rax
0x140061d86  jz      loc_140061ED6
0x140061d8c  mov     r8, rbx; Size
0x140061d8f  lea     rdx, [r14+12h]; Src
0x140061d93  mov     rcx, rax; void *
0x140061d96  call    memmove
0x140061d9b  jmp     short loc_140061DEC
0x140061d9d  mov     ecx, 17h; af
0x140061da2  call    SOCKADDR_SIZE
0x140061da7  movzx   edx, al
0x140061daa  cmp     edx, cs:AfdStandardAddressLength
0x140061db0  ja      short loc_140061DB9
0x140061db2  call    AfdAllocateZeroedFromLookasideList
0x140061db7  jmp     short loc_140061DCB
0x140061db9  xor     r9d, r9d
0x140061dbc  mov     r8d, 52646641h
0x140061dc2  lea     ecx, [r9+40h]
0x140061dc6  call    AfdAllocatePoolPriority
0x140061dcb  mov     [rdi+30h], rax
0x140061dcf  test    rax, rax
0x140061dd2  jz      loc_140061ED6
0x140061dd8  movzx   r9d, word ptr [r14+14h]
0x140061ddd  lea     rdx, [r14+16h]
0x140061de1  xor     r8d, r8d
0x140061de4  mov     rcx, rax
0x140061de7  call    IN6ADDR_SETV4MAPPED
0x140061dec  mov     rdx, r14; Entry
0x140061def  lea     rcx, stru_1400877C0; Lookaside
0x140061df6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061dfd  nop     dword ptr [rax+rax+00h]
0x140061e02  mov     rcx, rbp
0x140061e05  call    WskTdiRetainTDIEndpoint
0x140061e0a  test    al, al
0x140061e0c  jz      loc_140061EF1
0x140061e12  xor     edx, edx; Val
0x140061e14  lea     rcx, [rsp+0A8h+var_88]; void *
0x140061e19  lea     r8d, [rdx+50h]; Size
0x140061e1d  call    memset
0x140061e22  mov     eax, [rdi+100h]
0x140061e28  mov     [rsp+0A8h+var_80], eax
0x140061e2c  mov     rax, [rdi+30h]
0x140061e30  mov     [rsp+0A8h+var_78], rax
0x140061e35  mov     rax, [rdi+0C8h]
0x140061e3c  mov     [rsp+0A8h+var_70], rax
0x140061e41  lea     rax, WskTdiTLProviderConnectDispatch
0x140061e48  mov     [rsp+0A8h+var_60], rax
0x140061e4d  mov     [rsp+0A8h+var_88], rdi
0x140061e52  mov     [rsp+0A8h+var_68], rdi
0x140061e57  lock inc dword ptr [rdi+18h]
0x140061e5b  mov     rax, [rbp+120h]
0x140061e62  lea     rdx, [rsp+0A8h+var_88]
0x140061e67  mov     rcx, [rbp+118h]
0x140061e6e  mov     rax, [rax+8]
0x140061e72  call    _guard_dispatch_icall
0x140061e77  test    eax, eax
0x140061e79  js      short loc_140061EB7
0x140061e7b  mov     rax, [rsp+0A8h+var_50]
0x140061e80  mov     rcx, rdi
0x140061e83  mov     [rdi+118h], rax
0x140061e8a  call    WskTdiAllowDelivery
0x140061e8f  or      eax, 0FFFFFFFFh
0x140061e92  lock xadd [rdi+18h], eax
0x140061e97  cmp     eax, 1
0x140061e9a  jnz     short loc_140061EA4
0x140061e9c  mov     rcx, rdi
0x140061e9f  call    WskTdiFreeEndpoint
0x140061ea4  lock inc dword ptr [r15]
0x140061ea8  mov     r8d, [r15]
0x140061eab  mov     dl, 1
0x140061ead  mov     rcx, rbp
0x140061eb0  call    WskTdiInitiatePopulate
0x140061eb5  jmp     short loc_140061EF9
0x140061eb7  or      eax, 0FFFFFFFFh
0x140061eba  lock xadd [rdi+18h], eax
0x140061ebf  cmp     eax, 1
0x140061ec2  jnz     short loc_140061ECC
0x140061ec4  mov     rcx, rdi
0x140061ec7  call    WskTdiFreeEndpoint
0x140061ecc  mov     rcx, rbp
0x140061ecf  call    WskTdiReleaseTDIEndpoint
0x140061ed4  jmp     short loc_140061EF1
0x140061ed6  test    r14, r14
0x140061ed9  jz      short loc_140061EF1
0x140061edb  mov     rdx, r14; Entry
0x140061ede  lea     rcx, stru_1400877C0; Lookaside
0x140061ee5  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061eec  nop     dword ptr [rax+rax+00h]
0x140061ef1  mov     rcx, rdi
0x140061ef4  call    WskTdiCloseConnectionAndPopulate
0x140061ef9  mov     eax, 0C0000016h
0x140061efe  mov     rcx, [rsp+0A8h+var_38]
0x140061f03  xor     rcx, rsp; StackCookie
0x140061f06  call    __security_check_cookie
0x140061f0b  lea     r11, [rsp+0A8h+var_28]
0x140061f13  mov     rbx, [r11+30h]
0x140061f17  mov     rbp, [r11+48h]
0x140061f1b  mov     rsp, r11
0x140061f1e  pop     r15
0x140061f20  pop     r14
0x140061f22  pop     r13
0x140061f24  pop     rdi
0x140061f25  pop     rsi
0x140061f26  retn
```
