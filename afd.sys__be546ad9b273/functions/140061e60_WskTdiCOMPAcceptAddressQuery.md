# WskTdiCOMPAcceptAddressQuery

- ea: `0x140061e60`
- end: `0x1400620c8`
- name: `WskTdiCOMPAcceptAddressQuery`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140002150`
- `0x140003670`
- `0x140005b60`
- `0x140015990`
- `0x1400619c8`
- `0x140061e60`
- `0x1400629ac`
- `0x140063a5c`
- `0x140063c44`
- `0x14006404c`
- `0x140064160`
- `0x140072840`
- `0x140072920`
- `0x140072980`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140061ed5`
- `ntoskrnl!IoFreeIrp` at `0x140061ed5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061f96`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062085`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140061f96`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062085`
- `ntoskrnl!IoFreeMdl` at `0x140061ec2`
- `ntoskrnl!IoFreeMdl` at `0x140061ec2`

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
0x140061e60  mov     [rsp+arg_0], rbx
0x140061e65  mov     [rsp+arg_18], rbp
0x140061e6a  push    rsi
0x140061e6b  push    rdi
0x140061e6c  push    r13
0x140061e6e  push    r14
0x140061e70  push    r15
0x140061e72  sub     rsp, 80h
0x140061e79  mov     rax, cs:__security_cookie
0x140061e80  xor     rax, rsp
0x140061e83  mov     [rsp+0A8h+var_38], rax
0x140061e88  mov     rbp, [r8+0C0h]
0x140061e8f  mov     rdi, r8
0x140061e92  mov     r13, rdx
0x140061e95  mov     eax, [rbp+10h]
0x140061e98  test    al, 20h
0x140061e9a  jz      short loc_140061EAB
0x140061e9c  mov     eax, [r8+10h]
0x140061ea0  lea     r15, [rbp+0B4h]
0x140061ea7  test    al, 10h
0x140061ea9  jnz     short loc_140061EB2
0x140061eab  lea     r15, [rbp+0B0h]
0x140061eb2  mov     r14, [r8+30h]
0x140061eb6  mov     qword ptr [r8+30h], 0
0x140061ebe  mov     rcx, [rdx+8]; Mdl
0x140061ec2  call    cs:__imp_IoFreeMdl
0x140061ec9  nop     dword ptr [rax+rax+00h]
0x140061ece  mov     ebx, [r13+30h]
0x140061ed2  mov     rcx, r13; Irp
0x140061ed5  call    cs:__imp_IoFreeIrp
0x140061edc  nop     dword ptr [rax+rax+00h]
0x140061ee1  test    ebx, ebx
0x140061ee3  js      loc_140062076
0x140061ee9  mov     eax, [rdi+10h]
0x140061eec  test    al, 10h
0x140061eee  jnz     short loc_140061F3D
0x140061ef0  movzx   eax, word ptr [r14+10h]
0x140061ef5  add     ax, 2
0x140061ef9  movzx   ebx, ax
0x140061efc  cmp     ebx, cs:AfdStandardAddressLength
0x140061f02  mov     edx, ebx
0x140061f04  ja      short loc_140061F0D
0x140061f06  call    AfdAllocateZeroedFromLookasideList
0x140061f0b  jmp     short loc_140061F1F
0x140061f0d  xor     r9d, r9d
0x140061f10  mov     r8d, 52646641h
0x140061f16  lea     ecx, [r9+40h]
0x140061f1a  call    AfdAllocatePoolPriority
0x140061f1f  mov     [rdi+30h], rax
0x140061f23  test    rax, rax
0x140061f26  jz      loc_140062076
0x140061f2c  mov     r8, rbx; Size
0x140061f2f  lea     rdx, [r14+12h]; Src
0x140061f33  mov     rcx, rax; void *
0x140061f36  call    memmove
0x140061f3b  jmp     short loc_140061F8C
0x140061f3d  mov     ecx, 17h; af
0x140061f42  call    SOCKADDR_SIZE
0x140061f47  movzx   edx, al
0x140061f4a  cmp     edx, cs:AfdStandardAddressLength
0x140061f50  ja      short loc_140061F59
0x140061f52  call    AfdAllocateZeroedFromLookasideList
0x140061f57  jmp     short loc_140061F6B
0x140061f59  xor     r9d, r9d
0x140061f5c  mov     r8d, 52646641h
0x140061f62  lea     ecx, [r9+40h]
0x140061f66  call    AfdAllocatePoolPriority
0x140061f6b  mov     [rdi+30h], rax
0x140061f6f  test    rax, rax
0x140061f72  jz      loc_140062076
0x140061f78  movzx   r9d, word ptr [r14+14h]
0x140061f7d  lea     rdx, [r14+16h]
0x140061f81  xor     r8d, r8d
0x140061f84  mov     rcx, rax
0x140061f87  call    IN6ADDR_SETV4MAPPED
0x140061f8c  mov     rdx, r14; Entry
0x140061f8f  lea     rcx, stru_1400877C0; Lookaside
0x140061f96  call    cs:__imp_ExFreeToNPagedLookasideList
0x140061f9d  nop     dword ptr [rax+rax+00h]
0x140061fa2  mov     rcx, rbp
0x140061fa5  call    WskTdiRetainTDIEndpoint
0x140061faa  test    al, al
0x140061fac  jz      loc_140062091
0x140061fb2  xor     edx, edx; Val
0x140061fb4  lea     rcx, [rsp+0A8h+var_88]; void *
0x140061fb9  lea     r8d, [rdx+50h]; Size
0x140061fbd  call    memset
0x140061fc2  mov     eax, [rdi+100h]
0x140061fc8  mov     [rsp+0A8h+var_80], eax
0x140061fcc  mov     rax, [rdi+30h]
0x140061fd0  mov     [rsp+0A8h+var_78], rax
0x140061fd5  mov     rax, [rdi+0C8h]
0x140061fdc  mov     [rsp+0A8h+var_70], rax
0x140061fe1  lea     rax, WskTdiTLProviderConnectDispatch
0x140061fe8  mov     [rsp+0A8h+var_60], rax
0x140061fed  mov     [rsp+0A8h+var_88], rdi
0x140061ff2  mov     [rsp+0A8h+var_68], rdi
0x140061ff7  lock inc dword ptr [rdi+18h]
0x140061ffb  mov     rax, [rbp+120h]
0x140062002  lea     rdx, [rsp+0A8h+var_88]
0x140062007  mov     rcx, [rbp+118h]
0x14006200e  mov     rax, [rax+8]
0x140062012  call    _guard_dispatch_icall
0x140062017  test    eax, eax
0x140062019  js      short loc_140062057
0x14006201b  mov     rax, [rsp+0A8h+var_50]
0x140062020  mov     rcx, rdi
0x140062023  mov     [rdi+118h], rax
0x14006202a  call    WskTdiAllowDelivery
0x14006202f  or      eax, 0FFFFFFFFh
0x140062032  lock xadd [rdi+18h], eax
0x140062037  cmp     eax, 1
0x14006203a  jnz     short loc_140062044
0x14006203c  mov     rcx, rdi
0x14006203f  call    WskTdiFreeEndpoint
0x140062044  lock inc dword ptr [r15]
0x140062048  mov     r8d, [r15]
0x14006204b  mov     dl, 1
0x14006204d  mov     rcx, rbp
0x140062050  call    WskTdiInitiatePopulate
0x140062055  jmp     short loc_140062099
0x140062057  or      eax, 0FFFFFFFFh
0x14006205a  lock xadd [rdi+18h], eax
0x14006205f  cmp     eax, 1
0x140062062  jnz     short loc_14006206C
0x140062064  mov     rcx, rdi
0x140062067  call    WskTdiFreeEndpoint
0x14006206c  mov     rcx, rbp
0x14006206f  call    WskTdiReleaseTDIEndpoint
0x140062074  jmp     short loc_140062091
0x140062076  test    r14, r14
0x140062079  jz      short loc_140062091
0x14006207b  mov     rdx, r14; Entry
0x14006207e  lea     rcx, stru_1400877C0; Lookaside
0x140062085  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006208c  nop     dword ptr [rax+rax+00h]
0x140062091  mov     rcx, rdi
0x140062094  call    WskTdiCloseConnectionAndPopulate
0x140062099  mov     eax, 0C0000016h
0x14006209e  mov     rcx, [rsp+0A8h+var_38]
0x1400620a3  xor     rcx, rsp; StackCookie
0x1400620a6  call    __security_check_cookie
0x1400620ab  lea     r11, [rsp+0A8h+var_28]
0x1400620b3  mov     rbx, [r11+30h]
0x1400620b7  mov     rbp, [r11+48h]
0x1400620bb  mov     rsp, r11
0x1400620be  pop     r15
0x1400620c0  pop     r14
0x1400620c2  pop     r13
0x1400620c4  pop     rdi
0x1400620c5  pop     rsi
0x1400620c6  retn
```
