# CVaultRoamingCredential::DeserializeCredProperties(uchar * &,ulong &,IVaultSchema *)

- ea: `0x180009a20`
- end: `0x180009c89`
- name: `?DeserializeCredProperties@CVaultRoamingCredential@@AEAAKAEAPEAEAEAKPEAUIVaultSchema@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(CVaultRoamingCredential *this, unsigned int **, unsigned int *, struct IVaultSchema *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002a9e0`

## callees

- `0x180003140`
- `0x180007af0`
- `0x180009a20`
- `0x18003b7d8`
- `0x18003c2e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009b6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009b6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVaultRoamingCredential::DeserializeCredProperties(
        CVaultRoamingCredential *this,
        unsigned int **a2,
        unsigned int *a3,
        struct IVaultSchema *a4)
{
  unsigned int v8; // r10d
  unsigned int v9; // ebx
  __int64 v10; // r9
  int v11; // r8d
  unsigned int v12; // ecx
  __int64 result; // rax
  unsigned int i; // eax
  unsigned int v15; // esi
  struct CVaultCredElement *v16; // rdx
  _QWORD *v17; // rcx
  HLOCAL v18; // rax
  unsigned int v19; // ebx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  void (__fastcall *v23)(HLOCAL); // [rsp+30h] [rbp-58h] BYREF
  struct CVaultCredElement *v24; // [rsp+38h] [rbp-50h] BYREF
  int v25; // [rsp+40h] [rbp-48h]

  v8 = (*(__int64 (__fastcall **)(struct IVaultSchema *))(*(_QWORD *)a4 + 104LL))(a4);
  if ( *a3 < 4 )
  {
    v19 = 122;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return v19;
    v21 = 38;
    goto LABEL_23;
  }
  v9 = *(*a2)++;
  *a3 -= 4;
  v10 = *((unsigned int *)this + 15);
  v11 = v8 + 3;
  if ( (unsigned int)v10 > v8 + 3 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 87;
    v22 = 40;
    goto LABEL_26;
  }
  if ( v9 > v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_ddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v9, v8);
    return 87;
  }
  v12 = v9 + 3;
  v11 = -1;
  if ( v9 + 3 >= v9 )
    v11 = v9 + 3;
  result = v12 < v9 ? 0x80070216 : 0;
  if ( (_DWORD)v10 != v11 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 87;
    v22 = 42;
LABEL_26:
    WPP_SF_ddD(v17[2], v22, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v10, v11);
    return 87;
  }
  if ( v12 >= v9 )
  {
    if ( v9 )
    {
      v18 = LocalAlloc(0x40u, 64LL * v9);
      *((_QWORD *)this + 18) = v18;
      if ( !v18 )
      {
        v19 = 14;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return v19;
        v21 = 39;
LABEL_23:
        WPP_SF_d(v20[2], v21, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v19);
        return v19;
      }
    }
    *((_DWORD *)this + 34) = 0;
    for ( i = 0; ; i = *((_DWORD *)this + 34) )
    {
      if ( i >= v9 )
        return 0;
      v24 = 0;
      v25 = 0;
      v23 = CVaultCredElement::FreeCredElement;
      v15 = CVaultRoamingCredential::DeserializeCredElement((unsigned __int8 **)a2, a3, a4, &v24);
      if ( v15 )
        break;
      v16 = v24;
      v24 = 0;
      *(_QWORD *)(*((_QWORD *)this + 18) + 8LL * *((unsigned int *)this + 34)) = v16;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v23);
      ++*((_DWORD *)this + 34);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v23);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x180009a20  push    rbx
0x180009a22  push    rbp
0x180009a23  push    rsi
0x180009a24  push    rdi
0x180009a25  push    r14
0x180009a27  push    r15
0x180009a29  sub     rsp, 58h
0x180009a2d  mov     r15, r9
0x180009a30  mov     rbp, r8
0x180009a33  mov     r14, rdx
0x180009a36  mov     rdi, rcx
0x180009a39  mov     rax, [r9]
0x180009a3c  mov     rcx, r9
0x180009a3f  mov     rax, [rax+68h]
0x180009a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a48  mov     r10d, eax
0x180009a4b  cmp     dword ptr [rbp+0], 4
0x180009a4f  jb      loc_180009BA6
0x180009a55  mov     rax, [r14]
0x180009a58  mov     ebx, [rax]
0x180009a5a  add     rax, 4
0x180009a5e  mov     [r14], rax
0x180009a61  add     dword ptr [rbp+0], 0FFFFFFFCh
0x180009a65  mov     r9d, [rdi+3Ch]
0x180009a69  lea     r8d, [r10+3]
0x180009a6d  cmp     r9d, r8d
0x180009a70  ja      loc_180009B3C
0x180009a76  cmp     ebx, r10d
0x180009a79  ja      loc_180009C22
0x180009a7f  lea     ecx, [rbx+3]
0x180009a82  or      r8d, 0FFFFFFFFh
0x180009a86  cmp     ecx, ebx
0x180009a88  cmovnb  r8d, ecx
0x180009a8c  sbb     eax, eax
0x180009a8e  and     eax, 80070216h
0x180009a93  cmp     r9d, r8d
0x180009a96  jnz     loc_180009C45
0x180009a9c  cmp     ecx, ebx
0x180009a9e  jb      short loc_180009ABA
0x180009aa0  test    ebx, ebx
0x180009aa2  jnz     loc_180009B5D
0x180009aa8  mov     dword ptr [rdi+88h], 0
0x180009ab2  xor     eax, eax
0x180009ab4  cmp     eax, ebx
0x180009ab6  jb      short loc_180009AC7
0x180009ab8  xor     eax, eax
0x180009aba  add     rsp, 58h
0x180009abe  pop     r15
0x180009ac0  pop     r14
0x180009ac2  pop     rdi
0x180009ac3  pop     rsi
0x180009ac4  pop     rbp
0x180009ac5  pop     rbx
0x180009ac6  retn
0x180009ac7  mov     [rsp+88h+var_50], 0
0x180009ad0  mov     [rsp+88h+var_48], 0
0x180009ad8  lea     rax, ?FreeCredElement@CVaultCredElement@@SAXPEAV1@@Z; CVaultCredElement::FreeCredElement(CVaultCredElement *)
0x180009adf  mov     [rsp+88h+var_58], rax
0x180009ae4  lea     r9, [rsp+88h+var_50]; struct CVaultCredElement **
0x180009ae9  mov     r8, r15; struct IVaultSchema *
0x180009aec  mov     rdx, rbp; unsigned int *
0x180009aef  mov     rcx, r14; unsigned __int8 **
0x180009af2  call    ?DeserializeCredElement@CVaultRoamingCredential@@CAKAEAPEAEAEAKPEAUIVaultSchema@@PEAPEAVCVaultCredElement@@@Z; CVaultRoamingCredential::DeserializeCredElement(uchar * &,ulong &,IVaultSchema *,CVaultCredElement * *)
0x180009af7  mov     esi, eax
0x180009af9  test    eax, eax
0x180009afb  jnz     loc_180009C77
0x180009b01  mov     rdx, [rsp+88h+var_50]
0x180009b06  mov     [rsp+88h+var_50], 0
0x180009b0f  mov     ecx, [rdi+88h]
0x180009b15  mov     rax, [rdi+90h]
0x180009b1c  mov     [rax+rcx*8], rdx
0x180009b20  lea     rcx, [rsp+88h+var_58]
0x180009b25  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180009b2a  nop
0x180009b2b  inc     dword ptr [rdi+88h]
0x180009b31  mov     eax, [rdi+88h]
0x180009b37  jmp     loc_180009AB4
0x180009b3c  lea     rax, WPP_GLOBAL_Control
0x180009b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b4a  cmp     rcx, rax
0x180009b4d  jnz     loc_180009BE3
0x180009b53  mov     eax, 57h ; 'W'
0x180009b58  jmp     loc_180009ABA
0x180009b5d  lea     edx, ds:0[rbx*8]
0x180009b64  shl     rdx, 3; uBytes
0x180009b68  mov     ecx, 40h ; '@'; uFlags
0x180009b6d  call    cs:__imp_LocalAlloc
0x180009b73  mov     [rdi+90h], rax
0x180009b7a  test    rax, rax
0x180009b7d  jnz     loc_180009AA8
0x180009b83  lea     rax, WPP_GLOBAL_Control
0x180009b8a  mov     ebx, 0Eh
0x180009b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b96  cmp     rcx, rax
0x180009b99  jnz     loc_180009C68
0x180009b9f  mov     eax, ebx
0x180009ba1  jmp     loc_180009ABA
0x180009ba6  lea     rax, WPP_GLOBAL_Control
0x180009bad  mov     ebx, 7Ah ; 'z'
0x180009bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bb9  cmp     rcx, rax
0x180009bbc  jz      short loc_180009B9F
0x180009bbe  test    byte ptr [rcx+1Ch], 2
0x180009bc2  jz      short loc_180009B9F
0x180009bc4  lea     edx, [rbx-54h]
0x180009bc7  jmp     short loc_180009BCE
0x180009bc9  mov     edx, 27h ; '''
0x180009bce  mov     r9d, ebx
0x180009bd1  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x180009bd8  mov     rcx, [rcx+10h]
0x180009bdc  call    WPP_SF_d
0x180009be1  jmp     short loc_180009B9F
0x180009be3  test    byte ptr [rcx+1Ch], 2
0x180009be7  jz      loc_180009B53
0x180009bed  mov     edx, 28h ; '('
0x180009bf2  jmp     short loc_180009BF9
0x180009bf4  mov     edx, 2Ah ; '*'
0x180009bf9  mov     [rsp+88h+var_68], r8d
0x180009bfe  jmp     short loc_180009C0D
0x180009c00  mov     edx, 29h ; ')'
0x180009c05  mov     [rsp+88h+var_68], r10d
0x180009c0a  mov     r9d, ebx
0x180009c0d  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x180009c14  mov     rcx, [rcx+10h]
0x180009c18  call    WPP_SF_ddD
0x180009c1d  jmp     loc_180009B53
0x180009c22  lea     rax, WPP_GLOBAL_Control
0x180009c29  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c30  cmp     rcx, rax
0x180009c33  jz      loc_180009B53
0x180009c39  test    byte ptr [rcx+1Ch], 2
0x180009c3d  jz      loc_180009B53
0x180009c43  jmp     short loc_180009C00
0x180009c45  lea     rax, WPP_GLOBAL_Control
0x180009c4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c53  cmp     rcx, rax
0x180009c56  jz      loc_180009B53
0x180009c5c  test    byte ptr [rcx+1Ch], 2
0x180009c60  jz      loc_180009B53
0x180009c66  jmp     short loc_180009BF4
0x180009c68  test    byte ptr [rcx+1Ch], 2
0x180009c6c  jz      loc_180009B9F
0x180009c72  jmp     loc_180009BC9
0x180009c77  lea     rcx, [rsp+88h+var_58]
0x180009c7c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180009c81  nop
0x180009c82  mov     eax, esi
0x180009c84  jmp     loc_180009ABA
```
