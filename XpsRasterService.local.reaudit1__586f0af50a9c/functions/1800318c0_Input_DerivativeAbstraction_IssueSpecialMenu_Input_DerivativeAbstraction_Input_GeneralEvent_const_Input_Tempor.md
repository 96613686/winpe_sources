# Input::DerivativeAbstraction::IssueSpecialMenu(Input::DerivativeAbstraction &,Input::GeneralEvent const &,Input::TemporaryArea<Input::IntegralSink<short,11,int>> const &)

- ea: `0x1800318c0`
- end: `0x180031d49`
- name: `?IssueSpecialMenu@DerivativeAbstraction@Input@@SAXAEAV12@AEBVGeneralEvent@2@AEBV?$TemporaryArea@V?$IntegralSink@F$0L@H@Input@@@2@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(struct Input::OddStrategy *, struct Input::GeneralEvent *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x1800318c0`
- `0x180031d50`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall Input::DerivativeAbstraction::IssueSpecialMenu(
        struct Input::OddStrategy *a1,
        struct Input::GeneralEvent *a2)
{
  unsigned int v2; // ebx
  int v3; // r14d
  char v4; // r11
  int v7; // eax
  int v8; // ebp
  int v9; // edi
  char v10; // si
  __int64 (__fastcall *v11)(struct Input::OddStrategy *, struct Input::GeneralEvent *); // r9
  char *v12; // r10
  __int64 v13; // r8
  unsigned int v14; // eax
  _BYTE *v15; // r9
  void (__fastcall *MixedProvider)(__int64 (__fastcall *)(struct Input::OddStrategy *, struct Input::GeneralEvent *), unsigned __int64, __int64); // rax
  _BYTE *retaddr; // [rsp+58h] [rbp+0h]

  v2 = IntegralRelation::OddMap;
  v3 = 0;
  v4 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 2;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  do
  {
    if ( v7 > 663870 )
    {
      if ( v13 <= 0 )
      {
        if ( v13 < 0 && (__int64)v12 < (__int64)(0x8000000000000000uLL - v13) )
          goto LABEL_36;
        v7 = 221290;
      }
      else
      {
        if ( (__int64)v12 > 0x7FFFFFFFFFFFFFFFLL - v13 )
          goto LABEL_36;
        v7 = 221290;
      }
    }
    else if ( v7 == 663870 )
    {
      --v9;
      if ( *(_BYTE *)v11 == (unsigned __int8)((IntegralRelation::OddMap ^ 0x9EA96EAB) / 0x7F464A) )
      {
        v10 = 1;
        v4 = 1;
      }
      v7 = 331935;
      if ( v9 < 0 )
        v4 = 1;
    }
    else if ( v7 > 331935 )
    {
      if ( v7 == 442580 )
      {
        if ( *(_BYTE *)v11 != (unsigned __int8)((IntegralRelation::OddMap ^ 0x8F10E9BD) / 0x7F464A) )
          break;
        v13 = *((char *)v11 + 1);
        v8 = 2;
        v7 = 110645;
      }
      else
      {
        v7 = 331935;
        if ( *(_BYTE *)v11 == (unsigned __int8)((IntegralRelation::OddMap ^ 0xF0A4EE17) / 0xE482B) )
          v10 = 1;
        if ( --v9 < 0 )
          v4 = 1;
      }
    }
    else if ( v7 == 331935 )
    {
      if ( *(_BYTE *)v11 == (unsigned __int8)((IntegralRelation::OddMap ^ 0xE52BAB35) / 0x21FC76) )
      {
        v13 = *(int *)((char *)v11 + 1);
        v8 = 5;
        v7 = 110645;
      }
      else
      {
        v7 = 442580;
      }
    }
    else if ( v7 )
    {
      if ( v7 == 110645 )
      {
        v12 = (char *)Input::DerivativeAbstraction::MoveComplexServer + v8;
        v7 = 774515;
      }
      else
      {
        v11 = (__int64 (__fastcall *)(struct Input::OddStrategy *, struct Input::GeneralEvent *))&v12[v13];
        v7 = 553225;
      }
    }
    else
    {
      v11 = Input::DerivativeAbstraction::MoveComplexServer;
      v7 = 663870;
    }
  }
  while ( !v4 );
  if ( v10 )
    v2 = ++IntegralRelation::OddMap;
LABEL_36:
  v14 = 4455871;
  v15 = 0;
LABEL_37:
  LOBYTE(v13) = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( v14 > 0x43FDD0 )
        {
          if ( v14 == 4455942 )
          {
            if ( *v15 == (unsigned __int8)((v2 ^ v3) / 0x103B05) )
            {
              v14 = 952138;
              goto LABEL_37;
            }
            v14 = 952192;
          }
          else if ( v14 == 5407992 )
          {
            v15 = retaddr;
            v14 = 4455888;
          }
          else
          {
            v14 = 4455942;
            v3 = -148214865;
          }
        }
        if ( v14 != 4455888 )
          break;
        v13 = (unsigned __int8)v13;
        v14 = 952138;
        if ( (v2 ^ 0xFBAC9E91) == 0x69F2C2 )
          v14 = 6943426;
        else
          v13 = 1;
      }
      if ( v14 != 952138 )
        break;
      v14 = 952192;
      if ( (_BYTE)v13 != 1 )
        v14 = 5407992;
    }
    if ( v14 == 952192 )
      break;
    LOBYTE(v13) = 0;
    v14 = 952138;
  }
  if ( (_BYTE)v13 )
    IntegralRelation::OddMap = v2 + 1;
  MixedProvider = (void (__fastcall *)(__int64 (__fastcall *)(struct Input::OddStrategy *, struct Input::GeneralEvent *), unsigned __int64, __int64))GenerateMixedProvider(0xF4FBF7F8090F010LL, 3790880938LL, v13);
  MixedProvider(
    Input::DerivativeAbstraction::IssueSpecialMenu,
    (unsigned __int64)Input::DerivativeAbstraction::IssueSpecialMenu ^ 0x342325,
    2368277);
  return Input::DerivativeAbstraction::MoveComplexServer(a1, a2);
}

```

## disassembly

```asm
0x1800318c0  mov     [rsp+arg_18], rbx
0x1800318c5  push    rbp
0x1800318c6  push    rsi
0x1800318c7  push    rdi
0x1800318c8  push    r12
0x1800318ca  push    r13
0x1800318cc  push    r14
0x1800318ce  push    r15
0x1800318d0  sub     rsp, 20h
0x1800318d4  mov     ebx, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x1800318da  xor     r14d, r14d
0x1800318dd  xor     r11b, r11b
0x1800318e0  mov     r13, r8
0x1800318e3  mov     r12, rdx
0x1800318e6  mov     r15, rcx
0x1800318e9  mov     eax, r14d
0x1800318ec  mov     ebp, r14d
0x1800318ef  lea     edi, [r14+2]
0x1800318f3  xor     sil, sil
0x1800318f6  lea     edx, [rdi-1]
0x1800318f9  mov     r9d, r14d
0x1800318fc  mov     r10d, r14d
0x1800318ff  mov     r8d, r14d
0x180031902  mov     ecx, 3606Ah
0x180031907  nop     word ptr [rax+rax+00000000h]
0x180031910  cmp     eax, 0A213Eh
0x180031915  jg      loc_180031A80
0x18003191b  jz      loc_180031A3C
0x180031921  cmp     eax, 5109Fh
0x180031926  jg      loc_1800319B3
0x18003192c  jz      short loc_180031977
0x18003192e  test    eax, eax
0x180031930  jz      short loc_180031966
0x180031932  cmp     eax, 1B035h
0x180031937  jz      short loc_18003194F
0x180031939  cmp     eax, ecx
0x18003193b  jnz     loc_180031BFB
0x180031941  lea     r9, [r8+r10]
0x180031945  mov     eax, 87109h
0x18003194a  jmp     loc_180031BFB
0x18003194f  lea     rax, ?MoveComplexServer@DerivativeAbstraction@Input@@QEAAXAEBVGeneralEvent@2@AEBV?$TemporaryArea@V?$IntegralSink@F$0L@H@Input@@@2@@Z; Input::DerivativeAbstraction::MoveComplexServer(Input::GeneralEvent const &,Input::TemporaryArea<Input::IntegralSink<short,11,int>> const &)
0x180031956  movsxd  r10, ebp
0x180031959  add     r10, rax
0x18003195c  mov     eax, 0BD173h
0x180031961  jmp     loc_180031BFB
0x180031966  lea     r9, ?MoveComplexServer@DerivativeAbstraction@Input@@QEAAXAEBVGeneralEvent@2@AEBV?$TemporaryArea@V?$IntegralSink@F$0L@H@Input@@@2@@Z; Input::DerivativeAbstraction::MoveComplexServer(Input::GeneralEvent const &,Input::TemporaryArea<Input::IntegralSink<short,11,int>> const &)
0x18003196d  mov     eax, 0A213Eh
0x180031972  jmp     loc_180031BFB
0x180031977  mov     ecx, ebx
0x180031979  mov     eax, 788503F7h
0x18003197e  xor     ecx, 0E52BAB35h
0x180031984  mul     ecx
0x180031986  mov     ecx, 3606Ah
0x18003198b  shr     edx, 14h
0x18003198e  cmp     [r9], dl
0x180031991  mov     edx, 1
0x180031996  jnz     short loc_1800319A9
0x180031998  movsxd  r8, dword ptr [r9+1]
0x18003199c  lea     ebp, [rdx+4]
0x18003199f  mov     eax, 1B035h
0x1800319a4  jmp     loc_180031BFB
0x1800319a9  mov     eax, 6C0D4h
0x1800319ae  jmp     loc_180031BFB
0x1800319b3  cmp     eax, 6C0D4h
0x1800319b8  jz      short loc_1800319FF
0x1800319ba  cmp     eax, 87109h
0x1800319bf  jnz     loc_180031BFB
0x1800319c5  mov     ecx, ebx
0x1800319c7  movzx   esi, sil
0x1800319cb  xor     ecx, 0F0A4EE17h
0x1800319d1  movzx   r11d, r11b
0x1800319d5  mov     eax, 8F65F221h
0x1800319da  mul     ecx
0x1800319dc  mov     eax, 5109Fh
0x1800319e1  mov     ecx, 3606Ah
0x1800319e6  shr     edx, 13h
0x1800319e9  cmp     [r9], dl
0x1800319ec  mov     edx, 1
0x1800319f1  cmovz   esi, edx
0x1800319f4  sub     edi, edx
0x1800319f6  cmovs   r11d, edx
0x1800319fa  jmp     loc_180031BFB
0x1800319ff  mov     ecx, ebx
0x180031a01  mov     eax, 17589F5h
0x180031a06  xor     ecx, 8F10E9BDh
0x180031a0c  mul     ecx
0x180031a0e  sub     ecx, edx
0x180031a10  shr     ecx, 1
0x180031a12  add     ecx, edx
0x180031a14  shr     ecx, 16h
0x180031a17  cmp     [r9], cl
0x180031a1a  jnz     loc_180031C04
0x180031a20  movsx   r8, byte ptr [r9+1]
0x180031a25  mov     ebp, 2
0x180031a2a  mov     eax, 1B035h
0x180031a2f  mov     ecx, 3606Ah
0x180031a34  lea     edx, [rbp-1]
0x180031a37  jmp     loc_180031BFB
0x180031a3c  mov     ecx, ebx
0x180031a3e  mov     eax, 17589F5h
0x180031a43  xor     ecx, 9EA96EABh
0x180031a49  dec     edi
0x180031a4b  mul     ecx
0x180031a4d  sub     ecx, edx
0x180031a4f  shr     ecx, 1
0x180031a51  add     ecx, edx
0x180031a53  shr     ecx, 16h
0x180031a56  cmp     [r9], cl
0x180031a59  jnz     short loc_180031A62
0x180031a5b  mov     sil, 1
0x180031a5e  movzx   r11d, sil
0x180031a62  test    edi, edi
0x180031a64  movzx   r11d, r11b
0x180031a68  mov     edx, 1
0x180031a6d  mov     eax, 5109Fh
0x180031a72  cmovs   r11d, edx
0x180031a76  mov     ecx, 3606Ah
0x180031a7b  jmp     loc_180031BFB
0x180031a80  cmp     eax, 17A2E6h
0x180031a85  jg      loc_180031B9C
0x180031a8b  jz      loc_180031B4B
0x180031a91  cmp     eax, 0BD173h
0x180031a96  jz      short loc_180031AFC
0x180031a98  cmp     eax, 129247h
0x180031a9d  jz      short loc_180031AC3
0x180031a9f  cmp     eax, 15F2B1h
0x180031aa4  jnz     loc_180031BFB
0x180031aaa  movzx   eax, byte ptr [r9+3]
0x180031aaf  and     al, 0FCh
0x180031ab1  cmp     al, 14h
0x180031ab3  jnz     loc_180031C04
0x180031ab9  mov     eax, 17A2E6h
0x180031abe  jmp     loc_180031BFB
0x180031ac3  movzx   eax, byte ptr [r9]
0x180031ac7  dec     edi
0x180031ac9  or      al, 0E0h
0x180031acb  cmp     al, 0E0h
0x180031acd  jnz     short loc_180031AE8
0x180031acf  movzx   eax, byte ptr [r9+2]
0x180031ad4  or      al, 20h
0x180031ad6  cmp     al, 40h ; '@'
0x180031ad8  jnb     short loc_180031AE8
0x180031ada  cmp     byte ptr [r9+3], 0D4h
0x180031adf  jnz     short loc_180031AE8
0x180031ae1  mov     sil, 1
0x180031ae4  movzx   r11d, sil
0x180031ae8  test    edi, edi
0x180031aea  movzx   r11d, r11b
0x180031aee  mov     eax, 15F2B1h
0x180031af3  cmovs   r11d, edx
0x180031af7  jmp     loc_180031BFB
0x180031afc  test    r8, r8
0x180031aff  jle     short loc_180031B1E
0x180031b01  mov     rax, 7FFFFFFFFFFFFFFFh
0x180031b0b  sub     rax, r8
0x180031b0e  cmp     r10, rax
0x180031b11  jg      loc_180031C16
0x180031b17  mov     eax, ecx
0x180031b19  jmp     loc_180031BFB
0x180031b1e  mov     rax, r8
0x180031b21  neg     rax
0x180031b24  test    r8, r8
0x180031b27  jns     short loc_180031B44
0x180031b29  mov     rcx, 8000000000000000h
0x180031b33  add     rax, rcx
0x180031b36  mov     ecx, 3606Ah
0x180031b3b  cmp     r10, rax
0x180031b3e  jl      loc_180031C16
0x180031b44  mov     eax, ecx
0x180031b46  jmp     loc_180031BFB
0x180031b4b  movzx   eax, byte ptr [r9+3]
0x180031b50  and     al, 3
0x180031b52  movzx   r8d, al
0x180031b56  test    r8b, 2
0x180031b5a  lea     eax, [r8-4]
0x180031b5e  movzx   ecx, al
0x180031b61  movzx   eax, byte ptr [r9+2]
0x180031b66  cmovz   ecx, r8d
0x180031b6a  movsx   edx, cl
0x180031b6d  mov     ecx, 3606Ah
0x180031b72  shl     edx, 8
0x180031b75  add     edx, eax
0x180031b77  movzx   eax, byte ptr [r9+1]
0x180031b7c  shl     edx, 8
0x180031b7f  add     edx, eax
0x180031b81  movzx   eax, byte ptr [r9]
0x180031b85  shl     edx, 8
0x180031b88  add     edx, eax
0x180031b8a  mov     eax, 19531Bh
0x180031b8f  movsxd  r8, edx
0x180031b92  mov     edx, 1
0x180031b97  cmovz   eax, ecx
0x180031b9a  jmp     short loc_180031BFB
0x180031b9c  cmp     eax, 19531Bh
0x180031ba1  jz      short loc_180031BB5
0x180031ba3  cmp     eax, 237459h
0x180031ba8  jnz     short loc_180031BFB
0x180031baa  lea     r9, [r10+r8*4]
0x180031bae  mov     eax, 129247h
0x180031bb3  jmp     short loc_180031BFB
0x180031bb5  mov     rax, r8
0x180031bb8  neg     rax
0x180031bbb  shl     rax, 2
0x180031bbf  test    r8, r8
0x180031bc2  jle     short loc_180031BDD
0x180031bc4  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180031bce  add     rax, rcx
0x180031bd1  mov     ecx, 3606Ah
0x180031bd6  cmp     r10, rax
0x180031bd9  jg      short loc_180031C16
0x180031bdb  jmp     short loc_180031BF6
0x180031bdd  jns     short loc_180031BF6
0x180031bdf  mov     rdx, 8000000000000000h
0x180031be9  add     rax, rdx
0x180031bec  mov     edx, 1
0x180031bf1  cmp     r10, rax
0x180031bf4  jl      short loc_180031C16
0x180031bf6  mov     eax, 237459h
0x180031bfb  test    r11b, r11b
0x180031bfe  jz      loc_180031910
0x180031c04  mov     edx, 1
0x180031c09  test    sil, sil
0x180031c0c  jz      short loc_180031C16
0x180031c0e  inc     ebx
0x180031c10  mov     cs:?OddMap@IntegralRelation@@2IA, ebx; uint IntegralRelation::OddMap
0x180031c16  mov     eax, 43FDBFh
0x180031c1b  mov     r9, r14
0x180031c1e  mov     r11d, 5284F8h
0x180031c24  mov     r10d, 69F2C2h
0x180031c2a  mov     r8b, 1
0x180031c2d  nop     dword ptr [rax]
0x180031c30  cmp     eax, 43FDD0h
0x180031c35  ja      short loc_180031C8B
0x180031c37  jz      short loc_180031C6D
0x180031c39  mov     ecx, eax
0x180031c3b  sub     ecx, 0E874Ah
0x180031c41  jz      short loc_180031C5E
0x180031c43  sub     ecx, 36h ; '6'
0x180031c46  jz      loc_180031CE5
0x180031c4c  cmp     ecx, 35763Fh
0x180031c52  jnz     short loc_180031C30
0x180031c54  xor     r8b, r8b
0x180031c57  mov     eax, 0E874Ah
0x180031c5c  jmp     short loc_180031C30
0x180031c5e  cmp     r8b, 1
0x180031c62  mov     eax, 0E8780h
0x180031c67  cmovnz  eax, r11d
0x180031c6b  jmp     short loc_180031C30
0x180031c6d  mov     ecx, ebx
0x180031c6f  movzx   r8d, r8b
0x180031c73  xor     ecx, 0FBAC9E91h
0x180031c79  mov     eax, 0E874Ah
0x180031c7e  cmp     ecx, r10d
0x180031c81  cmovnz  r8d, edx
0x180031c85  cmovz   eax, r10d
0x180031c89  jmp     short loc_180031C30
0x180031c8b  cmp     eax, 43FE06h
0x180031c90  jz      short loc_180031CB8
0x180031c92  cmp     eax, r11d
0x180031c95  jz      short loc_180031CA9
0x180031c97  cmp     eax, r10d
0x180031c9a  jnz     short loc_180031C30
0x180031c9c  mov     eax, 43FE06h
0x180031ca1  mov     r14d, 0F72A6BAFh
0x180031ca7  jmp     short loc_180031C30
0x180031ca9  mov     r9, [rsp+58h]
0x180031cae  mov     eax, 43FDD0h
0x180031cb3  jmp     loc_180031C30
0x180031cb8  mov     ecx, r14d
0x180031cbb  mov     eax, 3F174675h
0x180031cc0  xor     ecx, ebx
0x180031cc2  mul     ecx
0x180031cc4  shr     edx, 12h
0x180031cc7  cmp     [r9], dl
0x180031cca  mov     edx, 1
0x180031ccf  jnz     short loc_180031CDB
0x180031cd1  mov     eax, 0E874Ah
0x180031cd6  jmp     loc_180031C2A
0x180031cdb  mov     eax, 0E8780h
0x180031ce0  jmp     loc_180031C30
0x180031ce5  test    r8b, r8b
0x180031ce8  jz      short loc_180031CF2
0x180031cea  inc     ebx
0x180031cec  mov     cs:?OddMap@IntegralRelation@@2IA, ebx; uint IntegralRelation::OddMap
0x180031cf2  mov     edx, 0E1F440AAh
0x180031cf7  mov     rcx, 0F4FBF7F8090F010h
0x180031d01  call    GenerateMixedProvider
0x180031d06  lea     rdx, ?IssueSpecialMenu@DerivativeAbstraction@Input@@SAXAEAV12@AEBVGeneralEvent@2@AEBV?$TemporaryArea@V?$IntegralSink@F$0L@H@Input@@@2@@Z; Input::DerivativeAbstraction::IssueSpecialMenu(Input::DerivativeAbstraction &,Input::GeneralEvent const &,Input::TemporaryArea<Input::IntegralSink<short,11,int>> const &)
0x180031d0d  mov     r8d, 242315h
0x180031d13  xor     rdx, 342325h
0x180031d1a  lea     rcx, ?IssueSpecialMenu@DerivativeAbstraction@Input@@SAXAEAV12@AEBVGeneralEvent@2@AEBV?$TemporaryArea@V?$IntegralSink@F$0L@H@Input@@@2@@Z; Input::DerivativeAbstraction::IssueSpecialMenu(Input::DerivativeAbstraction &,Input::GeneralEvent const &,Input::TemporaryArea<Input::IntegralSink<short,11,int>> const &)
0x180031d21  call    cs:__guard_dispatch_icall_fptr
0x180031d27  mov     r8, r13
0x180031d2a  mov     rdx, r12; struct Input::GeneralEvent *
0x180031d2d  mov     rcx, r15; struct Input::OddStrategy *
0x180031d30  mov     rbx, [rsp+58h+arg_18]
0x180031d35  add     rsp, 20h
0x180031d39  pop     r15
0x180031d3b  pop     r14
0x180031d3d  pop     r13
  ... truncated ...
```
