# Data::Stack::RestoreEllipticClient<Binary::Policy::CompleteKernel,64,Binary::ActiveCategory const &>(Data::Stack::OddMenu &,Binary::ActiveCategory const &)

- ea: `0x1800511f0`
- end: `0x180051378`
- name: `??$RestoreEllipticClient@VCompleteKernel@Policy@Binary@@$0EA@AEBVActiveCategory@3@@Stack@Data@@YA?AV?$ConstructInstruction@VCompleteKernel@Policy@Binary@@$0EA@@01@AEAVOddMenu@01@AEBVActiveCategory@Binary@@@Z`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800524b0`

## callees

- `0x180003180`
- `0x180003cc4`
- `0x1800511f0`
- `0x180086d20`
- `0x180087670`
- `0x180087770`
- `0x180087b50`
- `0x1800bf3b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Data::Stack::RestoreEllipticClient<Binary::Policy::CompleteKernel,64,Binary::ActiveCategory const &>(
        __int64 *a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64),
        const struct Binary::ActiveCategory *a3)
{
  unsigned __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // rsi
  _BYTE v14[208]; // [rsp+40h] [rbp-108h] BYREF

  v6 = 0;
  *a1 = 0;
  v7 = (**a2)(a2, 240);
  v8 = v7;
  if ( v7 )
  {
    v9 = v7 + 32;
    v10 = ((_BYTE)v7 + 32) & 0x3F;
    v11 = 64 - v10;
    if ( !v10 )
      v11 = 0;
    if ( v11 <= 0xD0 && 208 - v11 >= 0x90 )
      v6 = v11 + v9;
    *(_DWORD *)v8 = 1;
    *(_QWORD *)(v8 + 8) = v6;
    *(_BYTE *)(v8 + 16) = 0;
    *(_QWORD *)(v8 + 24) = a2;
    *a1 = v8;
    if ( !*(_BYTE *)(v8 + 16) )
    {
      v12 = *(_QWORD *)(v8 + 8);
      if ( v12 )
      {
        *(_QWORD *)v12 = &Binary::Policy::CompleteKernel::`vftable';
        *(_QWORD *)(v12 + 16) = &Binary::Policy::FlatFunction<Binary::Policy::NextInformation>::`vftable';
        *(_QWORD *)(v12 + 32) = &Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::SlowSource>>::`vftable';
        *(_QWORD *)(v12 + 48) = &Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::EasyQuantity>>::`vftable';
        *(_QWORD *)(v12 + 64) = &Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::StripedXPS>>::`vftable';
        *(_QWORD *)(v12 + 80) = &Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::SmoothArticle>>::`vftable';
        *(_QWORD *)(v12 + 96) = &Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::UniqueFact>>::`vftable';
        *(_QWORD *)(v12 + 112) = &Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::NewMode>>::`vftable';
        Binary::Policy::CompleteOperation::CompleteOperation((Binary::Policy::CompleteOperation *)(v12 + 128));
        memset_0(v14, 0, 0xC8u);
        Binary::Definition::FastResource::FastResource((Binary::Definition::FastResource *)v14);
        Binary::Definition::FastResource::OfferEllipticServer((Binary::Definition::FastResource *)v14, a3);
        *(_DWORD *)(v12 + 8) = Binary::Definition::FastResource::OutlineRightInput(v14);
        *(_BYTE *)(v8 + 16) = 1;
      }
    }
  }
  else
  {
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800511f0  push    rbx
0x1800511f2  push    rbp
0x1800511f3  push    rsi
0x1800511f4  push    rdi
0x1800511f5  push    r14
0x1800511f7  sub     rsp, 120h
0x1800511fe  mov     rax, cs:__security_cookie
0x180051205  xor     rax, rsp
0x180051208  mov     [rsp+148h+var_38], rax
0x180051210  mov     rbp, r8
0x180051213  mov     r14, rdx
0x180051216  mov     rdi, rcx
0x180051219  mov     [rsp+148h+var_120], rcx
0x18005121e  xor     esi, esi
0x180051220  mov     [rsp+148h+var_128], esi
0x180051224  mov     [rcx], rsi
0x180051227  mov     [rsp+148h+var_128], 1
0x18005122f  mov     rax, [rdx]
0x180051232  mov     edx, 0F0h
0x180051237  mov     rcx, r14
0x18005123a  mov     rax, [rax]
0x18005123d  call    cs:__guard_dispatch_icall_fptr
0x180051243  mov     rbx, rax
0x180051246  test    rax, rax
0x180051249  jz      loc_180051353
0x18005124f  lea     rdx, [rax+20h]
0x180051253  mov     rcx, rdx
0x180051256  and     ecx, 3Fh
0x180051259  mov     eax, 40h ; '@'
0x18005125e  sub     rax, rcx
0x180051261  test    rcx, rcx
0x180051264  cmovz   rax, rcx
0x180051268  mov     ecx, 0D0h
0x18005126d  cmp     rax, rcx
0x180051270  ja      short loc_180051282
0x180051272  sub     rcx, rax
0x180051275  cmp     rcx, 90h
0x18005127c  jb      short loc_180051282
0x18005127e  lea     rsi, [rax+rdx]
0x180051282  mov     dword ptr [rbx], 1
0x180051288  mov     [rbx+8], rsi
0x18005128c  mov     byte ptr [rbx+10h], 0
0x180051290  mov     [rbx+18h], r14
0x180051294  mov     [rdi], rbx
0x180051297  cmp     byte ptr [rbx+10h], 0
0x18005129b  jnz     loc_180051356
0x1800512a1  mov     rsi, [rbx+8]
0x1800512a5  test    rsi, rsi
0x1800512a8  jz      loc_180051356
0x1800512ae  mov     [rsp+148h+var_118], rsi
0x1800512b3  lea     rax, ??_7CompleteKernel@Policy@Binary@@6B@; const Binary::Policy::CompleteKernel::`vftable'
0x1800512ba  mov     [rsi], rax
0x1800512bd  lea     rax, ??_7?$FlatFunction@VNextInformation@Policy@Binary@@@Policy@Binary@@6B@; const Binary::Policy::FlatFunction<Binary::Policy::NextInformation>::`vftable'
0x1800512c4  mov     [rsi+10h], rax
0x1800512c8  lea     rax, ??_7?$FlatFunction@V?$ImmediateSetting@VSlowSource@Policy@Binary@@@Policy@Binary@@@Policy@Binary@@6B@; const Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::SlowSource>>::`vftable'
0x1800512cf  mov     [rsi+20h], rax
0x1800512d3  lea     rax, ??_7?$FlatFunction@V?$ImmediateSetting@VEasyQuantity@Policy@Binary@@@Policy@Binary@@@Policy@Binary@@6B@; const Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::EasyQuantity>>::`vftable'
0x1800512da  mov     [rsi+30h], rax
0x1800512de  lea     rax, ??_7?$FlatFunction@V?$ImmediateSetting@VStripedXPS@Policy@Binary@@@Policy@Binary@@@Policy@Binary@@6B@; const Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::StripedXPS>>::`vftable'
0x1800512e5  mov     [rsi+40h], rax
0x1800512e9  lea     rax, ??_7?$FlatFunction@V?$ImmediateSetting@VSmoothArticle@Policy@Binary@@@Policy@Binary@@@Policy@Binary@@6B@; const Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::SmoothArticle>>::`vftable'
0x1800512f0  mov     [rsi+50h], rax
0x1800512f4  lea     rax, ??_7?$FlatFunction@V?$ImmediateSetting@VUniqueFact@Policy@Binary@@@Policy@Binary@@@Policy@Binary@@6B@; const Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::UniqueFact>>::`vftable'
0x1800512fb  mov     [rsi+60h], rax
0x1800512ff  lea     rax, ??_7?$FlatFunction@V?$ImmediateSetting@VNewMode@Policy@Binary@@@Policy@Binary@@@Policy@Binary@@6B@; const Binary::Policy::FlatFunction<Binary::Policy::ImmediateSetting<Binary::Policy::NewMode>>::`vftable'
0x180051306  mov     [rsi+70h], rax
0x18005130a  lea     rcx, [rsi+80h]; this
0x180051311  call    ??0CompleteOperation@Policy@Binary@@QEAA@XZ; Binary::Policy::CompleteOperation::CompleteOperation(void)
0x180051316  nop
0x180051317  xor     edx, edx; Val
0x180051319  mov     r8d, 0C8h; Size
0x18005131f  lea     rcx, [rsp+148h+var_108]; void *
0x180051324  call    memset_0
0x180051329  lea     rcx, [rsp+148h+var_108]; this
0x18005132e  call    ??0FastResource@Definition@Binary@@QEAA@XZ; Binary::Definition::FastResource::FastResource(void)
0x180051333  mov     rdx, rbp; struct Binary::ActiveCategory *
0x180051336  lea     rcx, [rsp+148h+var_108]; this
0x18005133b  call    ?OfferEllipticServer@FastResource@Definition@Binary@@QEAAXAEBVActiveCategory@3@@Z; Binary::Definition::FastResource::OfferEllipticServer(Binary::ActiveCategory const &)
0x180051340  lea     rcx, [rsp+148h+var_108]
0x180051345  call    ?OutlineRightInput@FastResource@Definition@Binary@@QEBA?AW4ResolutionBucket@123@XZ; Binary::Definition::FastResource::OutlineRightInput(void)
0x18005134a  mov     [rsi+8], eax
0x18005134d  mov     byte ptr [rbx+10h], 1
0x180051351  jmp     short loc_180051356
0x180051353  mov     [rdi], rsi
0x180051356  mov     rax, rdi
0x180051359  mov     rcx, [rsp+148h+var_38]
0x180051361  xor     rcx, rsp; StackCookie
0x180051364  call    __security_check_cookie
0x180051369  add     rsp, 120h
0x180051370  pop     r14
0x180051372  pop     rdi
0x180051373  pop     rsi
0x180051374  pop     rbp
0x180051375  pop     rbx
0x180051376  retn
```
