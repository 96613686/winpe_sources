# CVaultMemoryStore::CreatePolicy(_GUID const *,uchar *,ulong,ushort const *,eVaultType,VaultPolicy *)

- ea: `0x180041524`
- end: `0x18004169a`
- name: `?CreatePolicy@CVaultMemoryStore@@IEAAKPEBU_GUID@@PEAEKPEBGW4eVaultType@@PEAUVaultPolicy@@@Z`
- size: `374`
- prototype: `unsigned int __fastcall(__int64, _OWORD *, unsigned __int8 *, unsigned int, unsigned __int16 *, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180040944`

## callees

- `0x180003140`
- `0x18000377c`
- `0x180004110`
- `0x1800062a8`
- `0x18001a640`
- `0x180028de4`
- `0x1800393ac`
- `0x180041524`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned int __fastcall CVaultMemoryStore::CreatePolicy(
        __int64 a1,
        _OWORD *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        int a6,
        __int64 a7)
{
  unsigned int result; // eax
  unsigned int CallerPackageSid; // edi
  int v13; // esi
  __int64 v14; // rbx
  int Properties; // r14d
  __int64 i; // rsi
  __int64 v17; // r8
  __int64 v18; // rax
  __int128 v19; // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+30h] [rbp-38h]
  __int64 (__fastcall *v21)(__int64); // [rsp+40h] [rbp-28h] BYREF
  struct CVaultSid *v22; // [rsp+48h] [rbp-20h] BYREF
  int v23; // [rsp+50h] [rbp-18h]

  result = CVaultPolicy::SetVaultName((CVaultPolicy *)(a1 + 72), a5);
  if ( !result )
  {
    *(_OWORD *)(a1 + 84) = *a2;
    *(_DWORD *)(a1 + 112) = a6;
    *(_QWORD *)(a1 + 116) = *(_QWORD *)a7;
    *(_DWORD *)(a1 + 124) = *(_DWORD *)(a7 + 8);
    result = CVaultPolicy::SetProtectionBuffer((CVaultPolicy *)(a1 + 72), a3, a4);
    if ( !result )
    {
      v22 = 0;
      v23 = 0;
      v21 = AutoDereference<IVaultKeyManager>;
      CallerPackageSid = VaultGetCallerPackageSid(&v22);
      if ( CallerPackageSid )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
        return CallerPackageSid;
      }
      v19 = *(_OWORD *)(a1 + 84);
      v13 = VaultCreateVaultSecurable(1, &v19, v22, a1 + 296);
      if ( v13 )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
        return v13;
      }
      v14 = a1 + 152;
      if ( *(_DWORD *)v14 )
      {
        Properties = CVaultGenericPropertyCollection<enum EVaultPropertyId,0>::CreateProperties(v14);
        if ( Properties )
        {
LABEL_13:
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
          return Properties;
        }
        for ( i = 0; (unsigned int)i < *(_DWORD *)v14; i = (unsigned int)(i + 1) )
        {
          **(_DWORD **)(8 * i + *(_QWORD *)(v14 + 8)) = i;
          v17 = 32LL * (unsigned int)i;
          v18 = *(_QWORD *)(v14 + 16);
          v19 = *(_OWORD *)(v17 + v18 + 8);
          v20 = *(_QWORD *)(v17 + v18 + 24);
          Properties = CVaultGenericProperty<enum ECredPropertyId>::SetPropertyValue(
                         *(_QWORD *)(8 * i + *(_QWORD *)(v14 + 8)),
                         &v19);
          if ( Properties )
            goto LABEL_13;
        }
      }
      *(_DWORD *)(v14 + 24) = 1;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180041524  push    rbp
0x180041526  push    rbx
0x180041527  push    rsi
0x180041528  push    rdi
0x180041529  push    r14
0x18004152b  push    r15
0x18004152d  mov     rbp, rsp
0x180041530  sub     rsp, 68h
0x180041534  mov     esi, r9d
0x180041537  mov     r14, r8
0x18004153a  mov     r15, rdx
0x18004153d  mov     rbx, rcx
0x180041540  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x180041544  add     rcx, 48h ; 'H'; this
0x180041548  call    ?SetVaultName@CVaultPolicy@@QEAAKPEBG@Z; CVaultPolicy::SetVaultName(ushort const *)
0x18004154d  test    eax, eax
0x18004154f  jnz     loc_18004168D
0x180041555  movups  xmm0, xmmword ptr [r15]
0x180041559  movdqu  xmmword ptr [rbx+54h], xmm0
0x18004155e  mov     eax, [rbp+arg_28]
0x180041561  mov     [rbx+70h], eax
0x180041564  mov     rax, [rbp+arg_30]
0x180041568  movsd   xmm0, qword ptr [rax]
0x18004156c  movsd   qword ptr [rbx+74h], xmm0
0x180041571  mov     eax, [rax+8]
0x180041574  mov     [rbx+7Ch], eax
0x180041577  mov     r8d, esi; unsigned int
0x18004157a  mov     rdx, r14; unsigned __int8 *
0x18004157d  lea     rcx, [rbx+48h]; this
0x180041581  call    ?SetProtectionBuffer@CVaultPolicy@@QEAAKPEAEK@Z; CVaultPolicy::SetProtectionBuffer(uchar *,ulong)
0x180041586  test    eax, eax
0x180041588  jnz     loc_18004168D
0x18004158e  mov     [rbp+var_20], 0
0x180041596  mov     [rbp+var_18], eax
0x180041599  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800415a0  mov     [rbp+var_28], rax
0x1800415a4  lea     rcx, [rbp+var_20]; struct CVaultSid **
0x1800415a8  call    ?VaultGetCallerPackageSid@@YAKPEAPEAVCVaultSid@@@Z; VaultGetCallerPackageSid(CVaultSid * *)
0x1800415ad  mov     edi, eax
0x1800415af  test    eax, eax
0x1800415b1  jz      short loc_1800415C4
0x1800415b3  lea     rcx, [rbp+var_28]
0x1800415b7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800415bc  nop
0x1800415bd  mov     eax, edi
0x1800415bf  jmp     loc_18004168D
0x1800415c4  movups  xmm0, xmmword ptr [rbx+54h]
0x1800415c8  movdqu  [rbp+var_48], xmm0
0x1800415cd  lea     r9, [rbx+128h]
0x1800415d4  mov     r8, [rbp+var_20]
0x1800415d8  lea     rdx, [rbp+var_48]
0x1800415dc  mov     edi, 1
0x1800415e1  mov     ecx, edi
0x1800415e3  call    ?VaultCreateVaultSecurable@@YAKW4EVaultSecurableType@@AEBU_GUID@@PEAVCVaultSid@@PEAPEAVIVaultSecurable@@@Z; VaultCreateVaultSecurable(EVaultSecurableType,_GUID const &,CVaultSid *,IVaultSecurable * *)
0x1800415e8  mov     esi, eax
0x1800415ea  test    eax, eax
0x1800415ec  jz      short loc_1800415FF
0x1800415ee  lea     rcx, [rbp+var_28]
0x1800415f2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800415f7  nop
0x1800415f8  mov     eax, esi
0x1800415fa  jmp     loc_18004168D
0x1800415ff  add     rbx, 98h
0x180041606  cmp     dword ptr [rbx], 0
0x180041609  jz      short loc_18004167E
0x18004160b  mov     rcx, rbx
0x18004160e  call    ?CreateProperties@?$CVaultGenericPropertyCollection@W4EVaultPropertyId@@$0A@@@AEAAKXZ; CVaultGenericPropertyCollection<EVaultPropertyId,0>::CreateProperties(void)
0x180041613  mov     r14d, eax
0x180041616  test    eax, eax
0x180041618  jnz     short loc_18004166F
0x18004161a  xor     esi, esi
0x18004161c  cmp     esi, [rbx]
0x18004161e  jnb     short loc_18004167E
0x180041620  mov     r8d, esi
0x180041623  lea     r9, ds:0[rsi*8]
0x18004162b  mov     rax, [rbx+8]
0x18004162f  mov     rdx, [r9+rax]
0x180041633  mov     [rdx], esi
0x180041635  shl     r8, 5
0x180041639  mov     rax, [rbx+10h]
0x18004163d  movups  xmm0, xmmword ptr [r8+rax+8]
0x180041643  movaps  [rbp+var_48], xmm0
0x180041647  movsd   xmm1, qword ptr [r8+rax+18h]
0x18004164e  movsd   [rbp+var_38], xmm1
0x180041653  mov     rcx, [rbx+8]
0x180041657  lea     rdx, [rbp+var_48]
0x18004165b  mov     rcx, [r9+rcx]
0x18004165f  call    ?SetPropertyValue@?$CVaultGenericProperty@W4ECredPropertyId@@@@QEAAKU_VAULT_VARIANT@@@Z; CVaultGenericProperty<ECredPropertyId>::SetPropertyValue(_VAULT_VARIANT)
0x180041664  mov     r14d, eax
0x180041667  test    eax, eax
0x180041669  jnz     short loc_18004166F
0x18004166b  add     esi, edi
0x18004166d  jmp     short loc_18004161C
0x18004166f  lea     rcx, [rbp+var_28]
0x180041673  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180041678  nop
0x180041679  mov     eax, r14d
0x18004167c  jmp     short loc_18004168D
0x18004167e  mov     [rbx+18h], edi
0x180041681  lea     rcx, [rbp+var_28]
0x180041685  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004168a  nop
0x18004168b  xor     eax, eax
0x18004168d  add     rsp, 68h
0x180041691  pop     r15
0x180041693  pop     r14
0x180041695  pop     rdi
0x180041696  pop     rsi
0x180041697  pop     rbx
0x180041698  pop     rbp
0x180041699  retn
```
