# VltRemoveItem

- ea: `0x180012470`
- end: `0x18001282e`
- name: `VltRemoveItem`
- size: `958`
- prototype: `__int64 __fastcall(__int64, __int64, struct _GUID *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x180012470`
- `0x180013080`
- `0x180013390`
- `0x180015568`
- `0x18002e9c0`
- `0x1800358a0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003be38`
- `0x1800489f8`
- `0x180048c64`
- `0x180048ccc`

## string_xrefs

- `0x1800124c3`: `VltRemoveItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VltRemoveItem(
        __int64 a1,
        __int64 a2,
        struct _GUID *a3,
        struct _VAULT_ITEM_ELEMENT *a4,
        struct _VAULT_ITEM_ELEMENT *a5,
        struct _VAULT_ITEM_ELEMENT *a6,
        unsigned int a7)
{
  _BYTE *v7; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  const char *v13; // r8
  _BYTE *v14; // rax
  PVOID *v15; // rcx
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // edi
  PVOID *v23; // r10
  unsigned int v24; // ebx
  PVOID *v26; // r10
  int v27; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v28[8]; // [rsp+48h] [rbp-69h] BYREF
  __int64 v29; // [rsp+50h] [rbp-61h]
  _BYTE v30[64]; // [rsp+60h] [rbp-51h] BYREF
  int *v31; // [rsp+A0h] [rbp-11h]

  v7 = v30;
  v27 = 0;
  v28[0] = 0;
  v29 = 0;
  v11 = 64;
  v12 = 2147483646;
  v13 = "VltRemoveItem";
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *v7++ = *v13++;
    --v12;
    --v11;
  }
  while ( v11 );
  v14 = v7 - 1;
  if ( v11 )
    v14 = v7;
  *v14 = 0;
  v31 = &v27;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v13, v30);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v24 = 87;
    v27 = 87;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
    {
      WPP_SF_(v15[2], 95, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
      v24 = v27;
    }
    goto LABEL_48;
  }
  if ( v15 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v15 + 28) & 8) != 0 )
    {
      WPP_SF_SLLD_guid_((TRACEHANDLE)v15[2], *(_DWORD *)(a2 + 80), *(_DWORD *)(a2 + 76), a7, (__int64)a3);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
      WPP_SF_(v15[2], 97, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
  }
  DumpVaultItemElement(a4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
  DumpVaultItemElement(a5);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
  DumpVaultItemElement(a6);
  if ( !a7 )
  {
    v18 = CVaultRpcImpersonate::Impersonate((CVaultRpcImpersonate *)v28, 1);
    v27 = v18;
    if ( !v18 )
    {
      v19 = VaultDeleteCredential((struct VaultContext *)a2, a3, a5, a4, a6);
      v27 = v19;
      v22 = v19;
      if ( v19 )
      {
        v23 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_24:
          v24 = v22;
          goto LABEL_25;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_21:
          if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
            WPP_SF_sD((unsigned int)v23[2], v20, v21, (unsigned int)v30, *v31);
          goto LABEL_24;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, v19);
        v22 = v27;
      }
      v23 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, v18);
      v18 = v27;
    }
    v24 = v18;
LABEL_48:
    FnTracer::~FnTracer((FnTracer *)v30);
    goto LABEL_25;
  }
  v26 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, a7, 0);
    v26 = (PVOID *)WPP_GLOBAL_Control;
  }
  v24 = 87;
  v27 = 87;
  if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
    WPP_SF_sD((unsigned int)v26[2], v16, v17, (unsigned int)v30, *v31);
LABEL_25:
  CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v28);
  return v24;
}

```

## disassembly

```asm
0x180012470  mov     [rsp-8+arg_0], rbx
0x180012475  push    rbp
0x180012476  push    rsi
0x180012477  push    rdi
0x180012478  push    r12
0x18001247a  push    r13
0x18001247c  push    r14
0x18001247e  push    r15
0x180012480  lea     rbp, [rsp-0Fh]
0x180012485  sub     rsp, 0C0h
0x18001248c  mov     rax, cs:__security_cookie
0x180012493  xor     rax, rsp
0x180012496  mov     [rbp+3Fh+var_40], rax
0x18001249a  mov     r12, [rbp+3Fh+arg_20]
0x18001249e  lea     rcx, [rbp+3Fh+var_90]
0x1800124a2  mov     r14, [rbp+3Fh+arg_28]
0x1800124a6  xor     ebx, ebx
0x1800124a8  mov     r13, r8
0x1800124ab  mov     [rbp+3Fh+var_B0], ebx
0x1800124ae  mov     rsi, rdx
0x1800124b1  mov     [rbp+3Fh+var_A8], bl
0x1800124b4  mov     r15, r9
0x1800124b7  mov     [rbp+3Fh+var_A0], rbx
0x1800124bb  lea     edx, [rbx+40h]
0x1800124be  mov     eax, 7FFFFFFEh
0x1800124c3  lea     r8, aVltremoveitem; "VltRemoveItem"
0x1800124ca  test    rax, rax
0x1800124cd  jz      short loc_1800124E9
0x1800124cf  mov     r9b, [r8]
0x1800124d2  test    r9b, r9b
0x1800124d5  jz      short loc_1800124E9
0x1800124d7  mov     [rcx], r9b
0x1800124da  inc     r8
0x1800124dd  inc     rcx
0x1800124e0  dec     rax
0x1800124e3  sub     rdx, 1
0x1800124e7  jnz     short loc_1800124CA
0x1800124e9  test    rdx, rdx
0x1800124ec  lea     rax, [rcx-1]
0x1800124f0  cmovnz  rax, rcx
0x1800124f4  mov     [rax], bl
0x1800124f6  lea     rax, [rbp+3Fh+var_B0]
0x1800124fa  mov     [rbp+3Fh+var_50], rax
0x1800124fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012505  lea     rax, WPP_GLOBAL_Control
0x18001250c  cmp     rcx, rax
0x18001250f  jnz     loc_180012620
0x180012515  test    rsi, rsi
0x180012518  jz      loc_180012717
0x18001251e  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x180012521  lea     rbx, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180012528  cmp     rcx, rax
0x18001252b  jz      short loc_180012546
0x18001252d  test    byte ptr [rcx+1Ch], 8
0x180012531  jnz     loc_18001274D
0x180012537  cmp     rcx, rax
0x18001253a  jz      short loc_180012546
0x18001253c  test    byte ptr [rcx+1Ch], 8
0x180012540  jnz     loc_180012789
0x180012546  mov     rcx, r15; struct _VAULT_ITEM_ELEMENT *
0x180012549  call    ?DumpVaultItemElement@@YAXPEAU_VAULT_ITEM_ELEMENT@@@Z; DumpVaultItemElement(_VAULT_ITEM_ELEMENT *)
0x18001254e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012555  lea     rax, WPP_GLOBAL_Control
0x18001255c  cmp     rcx, rax
0x18001255f  jnz     loc_1800126B9
0x180012565  mov     rcx, r12; struct _VAULT_ITEM_ELEMENT *
0x180012568  call    ?DumpVaultItemElement@@YAXPEAU_VAULT_ITEM_ELEMENT@@@Z; DumpVaultItemElement(_VAULT_ITEM_ELEMENT *)
0x18001256d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012574  lea     rax, WPP_GLOBAL_Control
0x18001257b  cmp     rcx, rax
0x18001257e  jnz     loc_18001264A
0x180012584  mov     rcx, r14; struct _VAULT_ITEM_ELEMENT *
0x180012587  call    ?DumpVaultItemElement@@YAXPEAU_VAULT_ITEM_ELEMENT@@@Z; DumpVaultItemElement(_VAULT_ITEM_ELEMENT *)
0x18001258c  test    edi, edi
0x18001258e  jnz     loc_18001266A
0x180012594  lea     edx, [rdi+1]; int
0x180012597  lea     rcx, [rbp+3Fh+var_A8]; this
0x18001259b  call    ?Impersonate@CVaultRpcImpersonate@@QEAAKH@Z; CVaultRpcImpersonate::Impersonate(int)
0x1800125a0  mov     [rbp+3Fh+var_B0], eax
0x1800125a3  test    eax, eax
0x1800125a5  jnz     loc_1800127D2
0x1800125ab  mov     r9, r15; struct _VAULT_ITEM_ELEMENT *
0x1800125ae  mov     [rsp+0F0h+var_D0], r14; struct _VAULT_ITEM_ELEMENT *
0x1800125b3  mov     r8, r12; struct _VAULT_ITEM_ELEMENT *
0x1800125b6  mov     rdx, r13; struct _GUID *
0x1800125b9  mov     rcx, rsi; struct VaultContext *
0x1800125bc  call    ?VaultDeleteCredential@@YAKPEAUVaultContext@@PEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@22@Z; VaultDeleteCredential(VaultContext *,_GUID *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *)
0x1800125c1  mov     [rbp+3Fh+var_B0], eax
0x1800125c4  mov     edi, eax
0x1800125c6  test    eax, eax
0x1800125c8  jnz     loc_1800126D9
0x1800125ce  lea     rsi, WPP_GLOBAL_Control
0x1800125d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800125dc  cmp     r10, rsi
0x1800125df  jz      short loc_1800125EC
0x1800125e1  test    byte ptr [r10+1Ch], 8
0x1800125e6  jnz     loc_180012812
0x1800125ec  mov     ebx, edi
0x1800125ee  lea     rcx, [rbp+3Fh+var_A8]; this
0x1800125f2  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x1800125f7  mov     eax, ebx
0x1800125f9  mov     rcx, [rbp+3Fh+var_40]
0x1800125fd  xor     rcx, rsp; StackCookie
0x180012600  call    __security_check_cookie
0x180012605  mov     rbx, [rsp+0F0h+arg_0]
0x18001260d  add     rsp, 0C0h
0x180012614  pop     r15
0x180012616  pop     r14
0x180012618  pop     r13
0x18001261a  pop     r12
0x18001261c  pop     rdi
0x18001261d  pop     rsi
0x18001261e  pop     rbp
0x18001261f  retn
0x180012620  test    byte ptr [rcx+1Ch], 8
0x180012624  jz      loc_180012515
0x18001262a  mov     rcx, [rcx+10h]
0x18001262e  lea     r9, [rbp+3Fh+var_90]
0x180012632  call    WPP_SF_s
0x180012637  mov     rcx, cs:WPP_GLOBAL_Control
0x18001263e  lea     rax, WPP_GLOBAL_Control
0x180012645  jmp     loc_180012515
0x18001264a  test    byte ptr [rcx+1Ch], 8
0x18001264e  jz      loc_180012584
0x180012654  mov     rcx, [rcx+10h]
0x180012658  mov     edx, 63h ; 'c'
0x18001265d  mov     r8, rbx
0x180012660  call    WPP_SF_
0x180012665  jmp     loc_180012584
0x18001266a  mov     r10, cs:WPP_GLOBAL_Control
0x180012671  lea     rsi, WPP_GLOBAL_Control
0x180012678  cmp     r10, rsi
0x18001267b  jnz     loc_18001279F
0x180012681  mov     ebx, 57h ; 'W'
0x180012686  mov     [rbp+3Fh+var_B0], ebx
0x180012689  cmp     r10, rsi
0x18001268c  jz      loc_1800125EE
0x180012692  test    byte ptr [r10+1Ch], 8
0x180012697  jz      loc_1800125EE
0x18001269d  mov     rax, [rbp+3Fh+var_50]
0x1800126a1  lea     r9, [rbp+3Fh+var_90]
0x1800126a5  mov     ecx, [rax]
0x1800126a7  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x1800126ab  mov     rcx, [r10+10h]
0x1800126af  call    WPP_SF_sD
0x1800126b4  jmp     loc_1800125EE
0x1800126b9  test    byte ptr [rcx+1Ch], 8
0x1800126bd  jz      loc_180012565
0x1800126c3  mov     rcx, [rcx+10h]
0x1800126c7  mov     edx, 62h ; 'b'
0x1800126cc  mov     r8, rbx
0x1800126cf  call    WPP_SF_
0x1800126d4  jmp     loc_180012565
0x1800126d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800126e0  lea     rsi, WPP_GLOBAL_Control
0x1800126e7  cmp     r10, rsi
0x1800126ea  jz      loc_1800125EC
0x1800126f0  test    byte ptr [r10+1Ch], 2
0x1800126f5  jz      loc_1800125DC
0x1800126fb  mov     rcx, [r10+10h]
0x1800126ff  mov     edx, 66h ; 'f'
0x180012704  mov     r9d, eax
0x180012707  mov     r8, rbx
0x18001270a  call    WPP_SF_d
0x18001270f  mov     edi, [rbp+3Fh+var_B0]
0x180012712  jmp     loc_1800125D5
0x180012717  mov     ebx, 57h ; 'W'
0x18001271c  mov     [rbp+3Fh+var_B0], ebx
0x18001271f  cmp     rcx, rax
0x180012722  jz      loc_180012804
0x180012728  test    byte ptr [rcx+1Ch], 2
0x18001272c  jz      loc_180012804
0x180012732  mov     rcx, [rcx+10h]
0x180012736  lea     edx, [rbx+8]
0x180012739  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180012740  call    WPP_SF_
0x180012745  mov     ebx, [rbp+3Fh+var_B0]
0x180012748  jmp     loc_180012804
0x18001274d  mov     eax, [rsi+4Ch]
0x180012750  lea     r9, [rsi+56h]
0x180012754  mov     rcx, [rcx+10h]; LoggerHandle
0x180012758  mov     edx, 60h ; '`'
0x18001275d  mov     [rsp+0F0h+var_B8], r13; __int64
0x180012762  mov     dword ptr [rsp+0F0h+var_C0], edi; char
0x180012766  mov     dword ptr [rsp+0F0h+var_C8], eax; char
0x18001276a  mov     eax, [rsi+50h]
0x18001276d  mov     dword ptr [rsp+0F0h+var_D0], eax; char
0x180012771  call    WPP_SF_SLLD_guid_
0x180012776  mov     rcx, cs:WPP_GLOBAL_Control
0x18001277d  lea     rax, WPP_GLOBAL_Control
0x180012784  jmp     loc_180012537
0x180012789  mov     rcx, [rcx+10h]
0x18001278d  mov     edx, 61h ; 'a'
0x180012792  mov     r8, rbx
0x180012795  call    WPP_SF_
0x18001279a  jmp     loc_180012546
0x18001279f  test    byte ptr [r10+1Ch], 2
0x1800127a4  jz      loc_180012681
0x1800127aa  mov     rcx, [r10+10h]
0x1800127ae  mov     edx, 64h ; 'd'
0x1800127b3  mov     r9d, edi
0x1800127b6  mov     dword ptr [rsp+0F0h+var_D0], 0
0x1800127be  mov     r8, rbx
0x1800127c1  call    WPP_SF_dd
0x1800127c6  mov     r10, cs:WPP_GLOBAL_Control
0x1800127cd  jmp     loc_180012681
0x1800127d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127d9  lea     rsi, WPP_GLOBAL_Control
0x1800127e0  cmp     rcx, rsi
0x1800127e3  jz      short loc_180012802
0x1800127e5  test    byte ptr [rcx+1Ch], 2
0x1800127e9  jz      short loc_180012802
0x1800127eb  mov     rcx, [rcx+10h]
0x1800127ef  mov     edx, 65h ; 'e'
0x1800127f4  mov     r9d, eax
0x1800127f7  mov     r8, rbx
0x1800127fa  call    WPP_SF_d
0x1800127ff  mov     eax, [rbp+3Fh+var_B0]
0x180012802  mov     ebx, eax
0x180012804  lea     rcx, [rbp+3Fh+var_90]; this
0x180012808  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x18001280d  jmp     loc_1800125EE
0x180012812  mov     rax, [rbp+3Fh+var_50]
0x180012816  lea     r9, [rbp+3Fh+var_90]
0x18001281a  mov     ecx, [rax]
0x18001281c  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180012820  mov     rcx, [r10+10h]
0x180012824  call    WPP_SF_sD
0x180012829  jmp     loc_1800125EC
```
