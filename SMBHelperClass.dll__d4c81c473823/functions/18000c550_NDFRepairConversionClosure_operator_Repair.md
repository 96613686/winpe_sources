# NDFRepairConversionClosure::operator()(Repair * &)

- ea: `0x18000c550`
- end: `0x18000c6d4`
- name: `??RNDFRepairConversionClosure@@UEAAHAEAPEAVRepair@@@Z`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000c550`
- `0x18000d750`
- `0x18000dd04`
- `0x18000e594`
- `0x180012010`

## string_xrefs

- `0x18000c657`: `HelpLinkURL`
- `0x18000c67f`: `HelpLinkURL`

## pseudocode

```c
__int64 __fastcall NDFRepairConversionClosure::operator()(__int64 a1, _QWORD *a2)
{
  AttributeList *v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 Attribute; // rax
  int v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+24h] [rbp-34h] BYREF
  int v11; // [rsp+28h] [rbp-30h] BYREF
  int v12; // [rsp+2Ch] [rbp-2Ch] BYREF
  _BYTE v13[40]; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)*(_QWORD *)(a1 + 8) = *(_OWORD *)(*a2 + 40LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 24LL) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a2 + 8LL))(
                                              *a2,
                                              *(_QWORD *)(a1 + 16));
  try
  {
    AllocateAndLoadString((unsigned __int16 **)(*(_QWORD *)(a1 + 8) + 16LL), L"SMBHelperClass");
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 32LL) = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 44LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL) = 2;
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL) = 0;
    v4 = (AttributeList *)(*a2 + 8LL);
  }
  catch ( TestException v12 )
  {
    FreeTestMemory(*(LPVOID *)(*(_QWORD *)(a1 + 8) + 24LL));
    v10 = v12;
    throw (TestException *)&v10;
  }
  if ( (unsigned int)AttributeList::attributeExists(v4, L"RequiresUserAction") )
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL) |= 0x10000000u;
  if ( (unsigned int)AttributeList::attributeExists((AttributeList *)(*a2 + 8LL), L"RequiresUserConfirmation") )
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL) |= 0x8000000u;
  if ( (unsigned int)AttributeList::attributeExists((AttributeList *)(*a2 + 8LL), L"Informational") )
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL) |= 0x2000000u;
  if ( (unsigned int)AttributeList::attributeExists((AttributeList *)(*a2 + 8LL), L"ContactAdmin") )
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL) |= 0x20000u;
  try
  {
    v5 = AttributeList::attributeExists((AttributeList *)(*a2 + 8LL), L"HelpLinkURL");
    v6 = *(_QWORD *)(a1 + 8);
    if ( v5 )
    {
      *(_DWORD *)(v6 + 56) = 3;
      Attribute = AttributeList::getAttribute(*a2 + 8LL, v13, L"HelpLinkURL", 1);
      AllocateAndLoadString((unsigned __int16 **)(*(_QWORD *)(a1 + 8) + 64LL), *(unsigned __int16 **)(Attribute + 8));
    }
    else
    {
      *(_DWORD *)(v6 + 56) = 4;
      AllocateAndLoadString(
        (unsigned __int16 **)(*(_QWORD *)(a1 + 8) + 64LL),
        *(unsigned __int16 **)(*(_QWORD *)(a1 + 8) + 24LL));
    }
  }
  catch ( TestException v11 )
  {
    FreeTestMemory(*(LPVOID *)(*(_QWORD *)(a1 + 8) + 24LL));
    FreeTestMemory(*(LPVOID *)(*(_QWORD *)(a1 + 8) + 16LL));
    v9 = v11;
    throw (TestException *)&v9;
  }
  *(_QWORD *)(a1 + 8) += 112LL;
  ++*(_DWORD *)(a1 + 24);
  return 1;
}

```

## disassembly

```asm
0x18000c550  mov     [rsp+arg_8], rbx
0x18000c555  mov     [rsp+arg_0], rcx
0x18000c55a  push    rdi
0x18000c55b  sub     rsp, 50h
0x18000c55f  mov     rdi, rdx
0x18000c562  mov     rbx, rcx
0x18000c565  mov     rax, [rdx]
0x18000c568  movups  xmm0, xmmword ptr [rax+28h]
0x18000c56c  mov     rax, [rcx+8]
0x18000c570  movdqu  xmmword ptr [rax], xmm0
0x18000c574  mov     rcx, [rdx]
0x18000c577  mov     rax, [rcx]
0x18000c57a  mov     rdx, [rbx+10h]
0x18000c57e  mov     rax, [rax+8]
0x18000c582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c587  mov     rcx, [rbx+8]
0x18000c58b  mov     [rcx+18h], rax
0x18000c58f  mov     rcx, [rbx+8]
0x18000c593  add     rcx, 10h; unsigned __int16 **
0x18000c597  lea     rdx, aSmbhelperclass_0; "SMBHelperClass"
0x18000c59e  call    ?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z; AllocateAndLoadString(ushort * *,ushort *)
0x18000c5a3  nop
0x18000c5a4  mov     rax, [rbx+8]
0x18000c5a8  mov     dword ptr [rax+20h], 1
0x18000c5af  mov     rax, [rbx+8]
0x18000c5b3  mov     dword ptr [rax+2Ch], 0
0x18000c5ba  mov     rax, [rbx+8]
0x18000c5be  mov     dword ptr [rax+30h], 2
0x18000c5c5  mov     rax, [rbx+8]
0x18000c5c9  mov     dword ptr [rax+28h], 0
0x18000c5d0  mov     rcx, [rdi]
0x18000c5d3  add     rcx, 8; this
0x18000c5d7  lea     rdx, aRequiresuserac; "RequiresUserAction"
0x18000c5de  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c5e3  test    eax, eax
0x18000c5e5  jz      short loc_18000C5F0
0x18000c5e7  mov     rax, [rbx+8]
0x18000c5eb  bts     dword ptr [rax+28h], 1Ch
0x18000c5f0  mov     rcx, [rdi]
0x18000c5f3  add     rcx, 8; this
0x18000c5f7  lea     rdx, aRequiresuserco; "RequiresUserConfirmation"
0x18000c5fe  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c603  test    eax, eax
0x18000c605  jz      short loc_18000C610
0x18000c607  mov     rax, [rbx+8]
0x18000c60b  bts     dword ptr [rax+28h], 1Bh
0x18000c610  mov     rcx, [rdi]
0x18000c613  add     rcx, 8; this
0x18000c617  lea     rdx, aInformational; "Informational"
0x18000c61e  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c623  test    eax, eax
0x18000c625  jz      short loc_18000C630
0x18000c627  mov     rax, [rbx+8]
0x18000c62b  bts     dword ptr [rax+28h], 19h
0x18000c630  mov     rcx, [rdi]
0x18000c633  add     rcx, 8; this
0x18000c637  lea     rdx, aContactadmin; "ContactAdmin"
0x18000c63e  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c643  test    eax, eax
0x18000c645  jz      short loc_18000C650
0x18000c647  mov     rax, [rbx+8]
0x18000c64b  bts     dword ptr [rax+28h], 11h
0x18000c650  mov     rcx, [rdi]
0x18000c653  add     rcx, 8; this
0x18000c657  lea     rdx, aHelplinkurl; "HelpLinkURL"
0x18000c65e  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x18000c663  mov     rcx, [rbx+8]
0x18000c667  test    eax, eax
0x18000c669  jz      short loc_18000C6A3
0x18000c66b  mov     dword ptr [rcx+38h], 3
0x18000c672  mov     rcx, [rdi]
0x18000c675  add     rcx, 8
0x18000c679  mov     r9d, 1
0x18000c67f  lea     r8, aHelplinkurl; "HelpLinkURL"
0x18000c686  lea     rdx, [rsp+58h+var_28]
0x18000c68b  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x18000c690  mov     rcx, [rbx+8]
0x18000c694  add     rcx, 40h ; '@'; unsigned __int16 **
0x18000c698  mov     rdx, [rax+8]; unsigned __int16 *
0x18000c69c  call    ?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z; AllocateAndLoadString(ushort * *,ushort *)
0x18000c6a1  jmp     short loc_18000C6BC
0x18000c6a3  mov     dword ptr [rcx+38h], 4
0x18000c6aa  mov     rdx, [rbx+8]
0x18000c6ae  lea     rcx, [rdx+40h]; unsigned __int16 **
0x18000c6b2  mov     rdx, [rdx+18h]; unsigned __int16 *
0x18000c6b6  call    ?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z; AllocateAndLoadString(ushort * *,ushort *)
0x18000c6bb  nop
0x18000c6bc  add     qword ptr [rbx+8], 70h ; 'p'
0x18000c6c1  inc     dword ptr [rbx+18h]
0x18000c6c4  mov     eax, 1
0x18000c6c9  mov     rbx, [rsp+58h+arg_8]
0x18000c6ce  add     rsp, 50h
0x18000c6d2  pop     rdi
0x18000c6d3  retn
```
