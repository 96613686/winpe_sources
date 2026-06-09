# CVaultCredmanStore::CreateSspCredSchema(_GUID const *,ushort *)

- ea: `0x180004850`
- end: `0x180004cf5`
- name: `?CreateSspCredSchema@CVaultCredmanStore@@AEAAKPEBU_GUID@@PEAG@Z`
- size: `1189`
- prototype: `__int64 __fastcall(CVaultCredmanStore *this, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180004ed8`

## callees

- `0x180003140`
- `0x180004850`
- `0x18001cb5c`
- `0x18003b7d8`
- `0x18003be38`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall CVaultCredmanStore::CreateSspCredSchema(
        CVaultCredmanStore *this,
        const struct _GUID *a2,
        unsigned __int16 *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int i; // ebx
  unsigned int v17; // eax
  unsigned int v18; // edi
  __int64 (__fastcall *v20)(__int64); // [rsp+30h] [rbp-20h] BYREF
  struct IVaultSchema *v21; // [rsp+38h] [rbp-18h] BYREF
  int v22; // [rsp+40h] [rbp-10h]
  __int64 v23; // [rsp+70h] [rbp+20h] BYREF

  v23 = 0;
  v20 = AutoDereference<IVaultKeyManager>;
  v21 = 0;
  v22 = 0;
  (*(void (__fastcall **)(CVaultCredmanStore *, __int64 *))(*(_QWORD *)this + 72LL))(this, &v23);
  v6 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD, __int64, struct IVaultSchema **))(*(_QWORD *)v23 + 8LL))(
         v23,
         a2,
         0,
         70,
         &v21);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v6);
    goto LABEL_28;
  }
  v8 = (*(__int64 (__fastcall **)(struct IVaultSchema *, unsigned __int16 *))(*(_QWORD *)v21 + 64LL))(v21, a3);
  v7 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v8);
    goto LABEL_28;
  }
  v9 = (*(__int64 (__fastcall **)(struct IVaultSchema *, __int64, _QWORD, __int64))(*(_QWORD *)v21 + 48LL))(
         v21,
         7,
         0,
         4);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v9);
LABEL_16:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
    return v10;
  }
  v11 = (*(__int64 (__fastcall **)(struct IVaultSchema *, __int64, _QWORD, __int64))(*(_QWORD *)v21 + 40LL))(
          v21,
          7,
          0,
          4);
  v7 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v11);
    goto LABEL_28;
  }
  v12 = (*(__int64 (__fastcall **)(struct IVaultSchema *, __int64, _QWORD))(*(_QWORD *)v21 + 56LL))(v21, 8, 0);
  v7 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v12);
    goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(struct IVaultSchema *, __int64, __int64, _QWORD, _DWORD))(*(_QWORD *)v21 + 72LL))(
          v21,
          100,
          4,
          0,
          0);
  v10 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v13);
    goto LABEL_16;
  }
  v14 = (*(__int64 (__fastcall **)(struct IVaultSchema *, __int64, __int64, _QWORD, int))(*(_QWORD *)v21 + 72LL))(
          v21,
          101,
          7,
          0,
          8);
  v7 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v14);
LABEL_28:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
    return v7;
  }
  v15 = (*(__int64 (__fastcall **)(struct IVaultSchema *, __int64, __int64, _QWORD, int))(*(_QWORD *)v21 + 72LL))(
          v21,
          102,
          7,
          0,
          12);
  v10 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v15);
    goto LABEL_16;
  }
  for ( i = 103; ; ++i )
  {
    if ( i >= 0xA7 )
    {
      v10 = CVaultCredmanStore::InternalSubmitSchemaToStore(this, v21);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      return v10;
    }
    v17 = (*(__int64 (__fastcall **)(struct IVaultSchema *, _QWORD, __int64, _QWORD, int))(*(_QWORD *)v21 + 72LL))(
            v21,
            i,
            11,
            0,
            8);
    v18 = v17;
    if ( v17 )
      break;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, i, v17);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
  return v18;
}

```

## disassembly

```asm
0x180004850  mov     [rsp-18h+arg_8], rbx
0x180004855  mov     [rsp-18h+arg_10], rsi
0x18000485a  push    rbp
0x18000485b  push    rdi
0x18000485c  push    r14
0x18000485e  mov     rbp, rsp
0x180004861  sub     rsp, 50h
0x180004865  mov     rdi, r8
0x180004868  mov     rbx, rdx
0x18000486b  mov     rsi, rcx
0x18000486e  xor     r14d, r14d
0x180004871  mov     [rbp+arg_0], r14
0x180004875  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18000487c  mov     [rbp+var_20], rax
0x180004880  mov     [rbp+var_18], r14
0x180004884  mov     [rbp+var_10], r14d
0x180004888  mov     rax, [rcx]
0x18000488b  lea     rdx, [rbp+arg_0]
0x18000488f  mov     rax, [rax+48h]
0x180004893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004898  mov     rcx, [rbp+arg_0]
0x18000489c  mov     rax, [rcx]
0x18000489f  lea     rdx, [rbp+var_18]
0x1800048a3  mov     [rsp+50h+var_30], rdx
0x1800048a8  mov     r9d, 46h ; 'F'
0x1800048ae  xor     r8d, r8d
0x1800048b1  mov     rdx, rbx
0x1800048b4  mov     rax, [rax+8]
0x1800048b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048bd  mov     ebx, eax
0x1800048bf  test    eax, eax
0x1800048c1  jnz     loc_180004A7B
0x1800048c7  mov     rcx, [rbp+var_18]
0x1800048cb  mov     rax, [rcx]
0x1800048ce  mov     rdx, rdi
0x1800048d1  mov     rax, [rax+40h]
0x1800048d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048da  mov     ebx, eax
0x1800048dc  test    eax, eax
0x1800048de  jnz     loc_180004AA0
0x1800048e4  mov     rcx, [rbp+var_18]
0x1800048e8  mov     rax, [rcx]
0x1800048eb  mov     r9d, 4
0x1800048f1  xor     r8d, r8d
0x1800048f4  mov     edx, 7
0x1800048f9  mov     rax, [rax+30h]
0x1800048fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004902  mov     ebx, eax
0x180004904  test    eax, eax
0x180004906  jnz     loc_180004BAB
0x18000490c  mov     rcx, [rbp+var_18]
0x180004910  mov     rax, [rcx]
0x180004913  mov     r9d, 4
0x180004919  xor     r8d, r8d
0x18000491c  mov     edx, 7
0x180004921  mov     rax, [rax+28h]
0x180004925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492a  mov     ebx, eax
0x18000492c  test    eax, eax
0x18000492e  jnz     loc_180004AC8
0x180004934  mov     rcx, [rbp+var_18]
0x180004938  mov     rax, [rcx]
0x18000493b  xor     r8d, r8d
0x18000493e  mov     edx, 8
0x180004943  mov     rax, [rax+38h]
0x180004947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494c  mov     ebx, eax
0x18000494e  test    eax, eax
0x180004950  jnz     loc_180004B35
0x180004956  mov     rcx, [rbp+var_18]
0x18000495a  mov     rax, [rcx]
0x18000495d  mov     dword ptr [rsp+50h+var_30], r14d
0x180004962  xor     r9d, r9d
0x180004965  mov     edx, 64h ; 'd'
0x18000496a  mov     r8d, 4
0x180004970  mov     rax, [rax+48h]
0x180004974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004979  mov     ebx, eax
0x18000497b  test    eax, eax
0x18000497d  jnz     loc_180004C3A
0x180004983  mov     rcx, [rbp+var_18]
0x180004987  mov     rax, [rcx]
0x18000498a  mov     dword ptr [rsp+50h+var_30], 8
0x180004992  xor     r9d, r9d
0x180004995  mov     edx, 65h ; 'e'
0x18000499a  mov     r8d, 7
0x1800049a0  mov     rax, [rax+48h]
0x1800049a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a9  mov     ebx, eax
0x1800049ab  test    eax, eax
0x1800049ad  jnz     loc_180004AF0
0x1800049b3  mov     rcx, [rbp+var_18]
0x1800049b7  mov     rax, [rcx]
0x1800049ba  mov     dword ptr [rsp+50h+var_30], 0Ch
0x1800049c2  xor     r9d, r9d
0x1800049c5  mov     edx, 66h ; 'f'
0x1800049ca  mov     r8d, 7
0x1800049d0  mov     rax, [rax+48h]
0x1800049d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d9  mov     ebx, eax
0x1800049db  test    eax, eax
0x1800049dd  jnz     short loc_180004A56
0x1800049df  mov     ebx, 67h ; 'g'
0x1800049e4  cmp     ebx, 0A7h
0x1800049ea  jnb     loc_180004B18
0x1800049f0  mov     rcx, [rbp+var_18]
0x1800049f4  mov     rax, [rcx]
0x1800049f7  mov     dword ptr [rsp+50h+var_30], 8
0x1800049ff  xor     r9d, r9d
0x180004a02  mov     r8d, 0Bh
0x180004a08  mov     edx, ebx
0x180004a0a  mov     rax, [rax+48h]
0x180004a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a13  mov     edi, eax
0x180004a15  test    eax, eax
0x180004a17  jnz     short loc_180004A1D
0x180004a19  inc     ebx
0x180004a1b  jmp     short loc_1800049E4
0x180004a1d  lea     rdx, WPP_GLOBAL_Control
0x180004a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a2b  cmp     rcx, rdx
0x180004a2e  jnz     loc_180004CC9
0x180004a34  lea     rcx, [rbp+var_20]
0x180004a38  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004a3d  nop
0x180004a3e  mov     eax, edi
0x180004a40  mov     rbx, [rsp+50h+arg_8]
0x180004a45  mov     rsi, [rsp+50h+arg_10]
0x180004a4d  add     rsp, 50h
0x180004a51  pop     r14
0x180004a53  pop     rdi
0x180004a54  pop     rbp
0x180004a55  retn
0x180004a56  lea     rdx, WPP_GLOBAL_Control
0x180004a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a64  cmp     rcx, rdx
0x180004a67  jnz     loc_180004CA2
0x180004a6d  lea     rcx, [rbp+var_20]
0x180004a71  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004a76  nop
0x180004a77  mov     eax, ebx
0x180004a79  jmp     short loc_180004A40
0x180004a7b  lea     rdx, WPP_GLOBAL_Control
0x180004a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a89  cmp     rcx, rdx
0x180004a8c  jnz     loc_180004B5D
0x180004a92  lea     rcx, [rbp+var_20]
0x180004a96  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004a9b  nop
0x180004a9c  mov     eax, ebx
0x180004a9e  jmp     short loc_180004A40
0x180004aa0  lea     rdx, WPP_GLOBAL_Control
0x180004aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004aae  cmp     rcx, rdx
0x180004ab1  jnz     loc_180004B84
0x180004ab7  lea     rcx, [rbp+var_20]
0x180004abb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004ac0  nop
0x180004ac1  mov     eax, ebx
0x180004ac3  jmp     loc_180004A40
0x180004ac8  lea     rdx, WPP_GLOBAL_Control
0x180004acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ad6  cmp     rcx, rdx
0x180004ad9  jnz     loc_180004BEC
0x180004adf  lea     rcx, [rbp+var_20]
0x180004ae3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004ae8  nop
0x180004ae9  mov     eax, ebx
0x180004aeb  jmp     loc_180004A40
0x180004af0  lea     rdx, WPP_GLOBAL_Control
0x180004af7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004afe  cmp     rcx, rdx
0x180004b01  jnz     loc_180004C7B
0x180004b07  lea     rcx, [rbp+var_20]
0x180004b0b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004b10  nop
0x180004b11  mov     eax, ebx
0x180004b13  jmp     loc_180004A40
0x180004b18  mov     rdx, [rbp+var_18]; struct IVaultSchema *
0x180004b1c  mov     rcx, rsi; this
0x180004b1f  call    ?InternalSubmitSchemaToStore@CVaultCredmanStore@@AEAAKPEAUIVaultSchema@@@Z; CVaultCredmanStore::InternalSubmitSchemaToStore(IVaultSchema *)
0x180004b24  mov     ebx, eax
0x180004b26  lea     rcx, [rbp+var_20]
0x180004b2a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004b2f  nop
0x180004b30  jmp     loc_180004A77
0x180004b35  lea     rdx, WPP_GLOBAL_Control
0x180004b3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b43  cmp     rcx, rdx
0x180004b46  jnz     loc_180004C13
0x180004b4c  lea     rcx, [rbp+var_20]
0x180004b50  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004b55  nop
0x180004b56  mov     eax, ebx
0x180004b58  jmp     loc_180004A40
0x180004b5d  test    byte ptr [rcx+1Ch], 2
0x180004b61  jz      loc_180004A92
0x180004b67  mov     edx, 0Ah
0x180004b6c  mov     r9d, ebx
0x180004b6f  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004b76  mov     rcx, [rcx+10h]
0x180004b7a  call    WPP_SF_d
0x180004b7f  jmp     loc_180004A92
0x180004b84  test    byte ptr [rcx+1Ch], 2
0x180004b88  jz      loc_180004AB7
0x180004b8e  mov     edx, 0Bh
0x180004b93  mov     r9d, ebx
0x180004b96  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004b9d  mov     rcx, [rcx+10h]
0x180004ba1  call    WPP_SF_d
0x180004ba6  jmp     loc_180004AB7
0x180004bab  lea     rdx, WPP_GLOBAL_Control
0x180004bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bb9  cmp     rcx, rdx
0x180004bbc  jz      short loc_180004BDD
0x180004bbe  test    byte ptr [rcx+1Ch], 2
0x180004bc2  jz      short loc_180004BDD
0x180004bc4  mov     edx, 0Ch
0x180004bc9  mov     r9d, ebx
0x180004bcc  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004bd3  mov     rcx, [rcx+10h]
0x180004bd7  call    WPP_SF_d
0x180004bdc  nop
0x180004bdd  lea     rcx, [rbp+var_20]
0x180004be1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004be6  nop
0x180004be7  jmp     loc_180004A77
0x180004bec  test    byte ptr [rcx+1Ch], 2
0x180004bf0  jz      loc_180004ADF
0x180004bf6  mov     edx, 0Dh
0x180004bfb  mov     r9d, ebx
0x180004bfe  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004c05  mov     rcx, [rcx+10h]
0x180004c09  call    WPP_SF_d
0x180004c0e  jmp     loc_180004ADF
0x180004c13  test    byte ptr [rcx+1Ch], 2
0x180004c17  jz      loc_180004B4C
0x180004c1d  mov     edx, 0Eh
0x180004c22  mov     r9d, ebx
0x180004c25  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004c2c  mov     rcx, [rcx+10h]
0x180004c30  call    WPP_SF_d
0x180004c35  jmp     loc_180004B4C
0x180004c3a  lea     rdx, WPP_GLOBAL_Control
0x180004c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c48  cmp     rcx, rdx
0x180004c4b  jz      short loc_180004C6C
0x180004c4d  test    byte ptr [rcx+1Ch], 2
0x180004c51  jz      short loc_180004C6C
0x180004c53  mov     edx, 0Fh
0x180004c58  mov     r9d, ebx
0x180004c5b  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004c62  mov     rcx, [rcx+10h]
0x180004c66  call    WPP_SF_d
0x180004c6b  nop
0x180004c6c  lea     rcx, [rbp+var_20]
0x180004c70  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180004c75  nop
0x180004c76  jmp     loc_180004A77
0x180004c7b  test    byte ptr [rcx+1Ch], 2
0x180004c7f  jz      loc_180004B07
0x180004c85  mov     edx, 10h
0x180004c8a  mov     r9d, ebx
0x180004c8d  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004c94  mov     rcx, [rcx+10h]
0x180004c98  call    WPP_SF_d
0x180004c9d  jmp     loc_180004B07
0x180004ca2  test    byte ptr [rcx+1Ch], 2
0x180004ca6  jz      loc_180004A6D
0x180004cac  mov     edx, 11h
0x180004cb1  mov     r9d, ebx
0x180004cb4  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004cbb  mov     rcx, [rcx+10h]
0x180004cbf  call    WPP_SF_d
0x180004cc4  jmp     loc_180004A6D
0x180004cc9  test    byte ptr [rcx+1Ch], 2
0x180004ccd  jz      loc_180004A34
0x180004cd3  mov     edx, 12h
0x180004cd8  mov     dword ptr [rsp+50h+var_30], edi
0x180004cdc  mov     r9d, ebx
0x180004cdf  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x180004ce6  mov     rcx, [rcx+10h]
0x180004cea  call    WPP_SF_dd
0x180004cef  jmp     loc_180004A34
```
