# Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>> &)

- ea: `0x14000dc24`
- end: `0x14000dcee`
- name: `?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z`
- size: `202`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000ca40`

## callees

- `0x14000d9a8`
- `0x14000dc24`
- `0x140010010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x14000dc5c`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x14000dc5c`

## pseudocode

```c
char __fastcall Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(
        __int64 a1,
        __int64 a2)
{
  int v3; // esi
  __int64 v4; // rbx
  char v6; // bl
  __int64 v7; // [rsp+28h] [rbp-18h] BYREF
  char v8; // [rsp+30h] [rbp-10h]
  __int64 v9; // [rsp+70h] [rbp+30h] BYREF

  v9 = 0;
  v7 = 0;
  v8 = 1;
  v3 = OpenProvisioningPackageForRead(a1, &v7);
  if ( v8 )
  {
    v4 = v7;
    if ( v7 != v9 )
    {
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 128LL))(v9);
      v9 = v4;
    }
  }
  if ( v3 >= 0 )
  {
    v6 = ProvisioningFileManager::TryCreateProvisioningFileManager(&v9, a2);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 128LL))(v9);
    return v6;
  }
  else
  {
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 128LL))(v9);
    return 0;
  }
}

```

## disassembly

```asm
0x14000dc24  mov     [rsp-18h+arg_0], rbx
0x14000dc29  mov     [rsp-18h+arg_8], rsi
0x14000dc2e  push    rbp
0x14000dc2f  push    rdi
0x14000dc30  push    r14
0x14000dc32  mov     rbp, rsp
0x14000dc35  sub     rsp, 40h
0x14000dc39  mov     r14, rdx
0x14000dc3c  mov     [rbp+arg_10], 0
0x14000dc44  lea     rax, [rbp+arg_10]
0x14000dc48  mov     [rbp+var_20], rax
0x14000dc4c  mov     [rbp+var_18], 0
0x14000dc54  mov     [rbp+var_10], 1
0x14000dc58  lea     rdx, [rbp+var_18]
0x14000dc5c  call    cs:__imp_OpenProvisioningPackageForRead
0x14000dc62  mov     esi, eax
0x14000dc64  cmp     [rbp+var_10], 0
0x14000dc68  jz      short loc_14000DC91
0x14000dc6a  mov     rbx, [rbp+var_18]
0x14000dc6e  mov     rdi, [rbp+var_20]
0x14000dc72  mov     rcx, [rdi]
0x14000dc75  cmp     rbx, rcx
0x14000dc78  jz      short loc_14000DC91
0x14000dc7a  test    rcx, rcx
0x14000dc7d  jz      short loc_14000DC8E
0x14000dc7f  mov     rax, [rcx]
0x14000dc82  mov     rax, [rax+80h]
0x14000dc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dc8e  mov     [rdi], rbx
0x14000dc91  test    esi, esi
0x14000dc93  jns     short loc_14000DCB2
0x14000dc95  mov     rcx, [rbp+arg_10]
0x14000dc99  test    rcx, rcx
0x14000dc9c  jz      short loc_14000DCAE
0x14000dc9e  mov     rax, [rcx]
0x14000dca1  mov     rax, [rax+80h]
0x14000dca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcad  nop
0x14000dcae  xor     al, al
0x14000dcb0  jmp     short loc_14000DCDB
0x14000dcb2  mov     rdx, r14
0x14000dcb5  lea     rcx, [rbp+arg_10]
0x14000dcb9  call    ?TryCreateProvisioningFileManager@ProvisioningFileManager@@SA_N$$QEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@AEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@3@@Z; ProvisioningFileManager::TryCreateProvisioningFileManager(std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> &&,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x14000dcbe  mov     bl, al
0x14000dcc0  mov     rcx, [rbp+arg_10]
0x14000dcc4  test    rcx, rcx
0x14000dcc7  jz      short loc_14000DCD9
0x14000dcc9  mov     rdx, [rcx]
0x14000dccc  mov     rax, [rdx+80h]
0x14000dcd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcd8  nop
0x14000dcd9  mov     al, bl
0x14000dcdb  mov     rbx, [rsp+40h+arg_0]
0x14000dce0  mov     rsi, [rsp+40h+arg_8]
0x14000dce5  add     rsp, 40h
0x14000dce9  pop     r14
0x14000dceb  pop     rdi
0x14000dcec  pop     rbp
0x14000dced  retn
```
