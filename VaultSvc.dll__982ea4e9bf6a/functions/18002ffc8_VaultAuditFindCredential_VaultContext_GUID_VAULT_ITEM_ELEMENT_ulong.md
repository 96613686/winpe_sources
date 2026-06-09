# VaultAuditFindCredential(VaultContext *,_GUID *,_VAULT_ITEM_ELEMENT *,ulong)

- ea: `0x18002ffc8`
- end: `0x180030310`
- name: `?VaultAuditFindCredential@@YAXPEAUVaultContext@@PEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@K@Z`
- size: `840`
- prototype: `void(struct VaultContext *, struct _GUID *, struct _VAULT_ITEM_ELEMENT *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002f5e0`

## callees

- `0x180003140`
- `0x180007aa0`
- `0x1800091d0`
- `0x18000f2e0`
- `0x180012210`
- `0x180027340`
- `0x18002ffc8`
- `0x18003a580`
- `0x18003af10`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `LSASRV!LsapQueryClientInfo` at `0x18003011d`
- `LSASRV!LsapQueryClientInfo` at `0x18003011d`
- `LSASRV!LsapAdtGetCallerProcessInfo` at `0x18003010b`
- `LSASRV!LsapAdtGetCallerProcessInfo` at `0x18003010b`
- `LSASRV!LsapAuditFailed` at `0x18003014d`
- `LSASRV!LsapAuditFailed` at `0x18003014d`
- `LSASRV!LsapAdtWriteLog` at `0x1800302c8`
- `LSASRV!LsapAdtWriteLog` at `0x1800302c8`
- `ntdll!RtlInitUnicodeString` at `0x1800301b5`
- `ntdll!RtlInitUnicodeString` at `0x1800301d5`
- `ntdll!RtlInitUnicodeString` at `0x1800301e6`
- `ntdll!RtlInitUnicodeString` at `0x1800301b5`
- `ntdll!RtlInitUnicodeString` at `0x1800301d5`
- `ntdll!RtlInitUnicodeString` at `0x1800301e6`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x1800300f3`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x1800300f3`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x1800302b6`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x1800302b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall VaultAuditFindCredential(
        struct VaultContext *a1,
        struct _GUID *a2,
        struct _VAULT_ITEM_ELEMENT *a3,
        int a4)
{
  int VaultStore; // eax
  _BYTE *v9; // rbx
  bool v10; // sf
  bool v11; // cc
  __int64 v12; // rdx
  __int64 v13; // rcx
  _BYTE *v14; // rax
  const WCHAR *v15; // rax
  int v16; // [rsp+C0h] [rbp-80h] BYREF
  int v17; // [rsp+C4h] [rbp-7Ch] BYREF
  __int64 v18; // [rsp+C8h] [rbp-78h] BYREF
  _QWORD *v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 (__fastcall *v20)(__int64); // [rsp+D8h] [rbp-68h]
  HLOCAL hMem; // [rsp+E0h] [rbp-60h] BYREF
  unsigned int v22; // [rsp+E8h] [rbp-58h]
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  _QWORD v24[2]; // [rsp+F8h] [rbp-48h] BYREF
  PCWSTR SourceString; // [rsp+108h] [rbp-38h]
  __int64 (__fastcall *v26)(__int64); // [rsp+110h] [rbp-30h] BYREF
  struct IVaultSchema *v27; // [rsp+118h] [rbp-28h] BYREF
  int v28; // [rsp+120h] [rbp-20h]
  struct _UNICODE_STRING v29; // [rsp+128h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+138h] [rbp-8h] BYREF
  struct _UNICODE_STRING v31; // [rsp+148h] [rbp+8h] BYREF
  __int128 Buf2; // [rsp+158h] [rbp+18h] BYREF
  _BYTE v33[1056]; // [rsp+170h] [rbp+30h] BYREF

  memset_0(v33, 0, 0x418u);
  LOBYTE(v16) = 1;
  v17 = 0;
  v18 = 0;
  v29 = 0;
  DestinationString = 0;
  v23 = 0;
  v19 = 0;
  v31 = 0;
  v26 = AutoDereference<IVaultKeyManager>;
  v27 = 0;
  v28 = 0;
  v24[0] = 0;
  v24[1] = VaultGlobals::g_HeapAlloc;
  SourceString = 0;
  v20 = AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v22 = 0;
  Buf2 = 0;
  VaultStore = CUserVault::GetVaultStore(*(CUserVault **)a1, (struct IVaultStore **)&hMem, 1);
  v9 = hMem;
  v10 = VaultStore < 0;
  v11 = VaultStore <= 0;
  if ( !VaultStore )
  {
    VaultStore = (*(__int64 (__fastcall **)(HLOCAL, __int128 *))(*(_QWORD *)hMem + 24LL))(hMem, &Buf2);
    v10 = VaultStore < 0;
    v11 = VaultStore <= 0;
    if ( !VaultStore )
    {
      if ( memcmp_0(&Vault_DefaultVault_ID, &Buf2, 0x10u) && memcmp_0(&Vault_CredmanVault_ID, &Buf2, 0x10u) )
        goto LABEL_14;
      VaultStore = LsapAdtAuditingEnabledByLogonId(146, (char *)a1 + 76, 8, &v16);
      if ( VaultStore < 0 )
        goto LABEL_13;
      if ( !(_BYTE)v16 )
        goto LABEL_14;
      VaultStore = LsapAdtGetCallerProcessInfo(&v17, &v18);
      if ( VaultStore < 0 )
        goto LABEL_13;
      VaultStore = LsapQueryClientInfo(&v19, &v23);
      if ( VaultStore < 0 )
        goto LABEL_13;
      VaultStore = VaultGetSchema(*(struct CUserVault **)a1, a2, &v27, 1u);
      v10 = VaultStore < 0;
      v11 = VaultStore <= 0;
      if ( !VaultStore )
      {
        if ( a3 )
        {
          VaultStore = VaultVariantToUnicodeString(a3, v12, v24);
          if ( VaultStore < 0 )
            goto LABEL_13;
          RtlInitUnicodeString(&DestinationString, SourceString);
        }
        v15 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IVaultSchema *))(*(_QWORD *)v27 + 136LL))(v27);
        RtlInitUnicodeString(&v29, v15);
        RtlInitUnicodeString(&v31, L"VAULT");
        VaultStore = LsapAdtInitParametersArray(
                       v33,
                       7,
                       5380,
                       146,
                       8,
                       9,
                       4,
                       *v19,
                       1,
                       &v31,
                       5,
                       *(_QWORD *)((char *)a1 + 76),
                       1,
                       &DestinationString,
                       1,
                       &v29,
                       13,
                       a2,
                       27,
                       a4,
                       12,
                       v18,
                       27,
                       v17,
                       v16,
                       v18,
                       (_DWORD)v19,
                       v20,
                       (_DWORD)hMem,
                       v22);
        if ( VaultStore >= 0 )
        {
          LsapAdtWriteLog(v33);
          goto LABEL_14;
        }
LABEL_13:
        LsapAuditFailed((unsigned int)VaultStore);
        goto LABEL_14;
      }
    }
  }
  if ( !v11 )
  {
    VaultStore = (unsigned __int16)VaultStore | 0x80070000;
    v10 = VaultStore < 0;
  }
  if ( v10 )
    goto LABEL_13;
LABEL_14:
  if ( v9 )
  {
    if ( v22 )
    {
      v13 = v22;
      v14 = v9;
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    if ( v20 )
      v20((__int64)v9);
    else
      VaultFreeInternal(v9);
  }
  CVaultAutoPtr2<unsigned char *,void>::Delete((__int64)v24);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v26);
}

```

## disassembly

```asm
0x18002ffc8  push    rbp
0x18002ffca  push    rbx
0x18002ffcb  push    rsi
0x18002ffcc  push    rdi
0x18002ffcd  push    r12
0x18002ffcf  push    r13
0x18002ffd1  push    r14
0x18002ffd3  push    r15
0x18002ffd5  lea     rbp, [rsp-468h]
0x18002ffdd  sub     rsp, 5A8h
0x18002ffe4  mov     rax, cs:__security_cookie
0x18002ffeb  xor     rax, rsp
0x18002ffee  mov     [rbp+4A0h+var_50], rax
0x18002fff5  mov     r12d, r9d
0x18002fff8  mov     rsi, r8
0x18002fffb  mov     r15, rdx
0x18002fffe  mov     rdi, rcx
0x180030001  xor     edx, edx; Val
0x180030003  mov     r8d, 418h; Size
0x180030009  lea     rcx, [rbp+4A0h+var_470]; void *
0x18003000d  call    memset_0
0x180030012  mov     byte ptr [rbp+4A0h+var_520], 1
0x180030016  xor     r13d, r13d
0x180030019  mov     [rbp+4A0h+var_51C], r13d
0x18003001d  mov     [rbp+4A0h+var_518], r13
0x180030021  xorps   xmm0, xmm0
0x180030024  movups  xmmword ptr [rbp+4A0h+var_4B8.Length], xmm0
0x180030028  xorps   xmm1, xmm1
0x18003002b  movups  xmmword ptr [rbp+4A0h+DestinationString.Length], xmm1
0x18003002f  mov     [rbp+4A0h+var_4F0], r13
0x180030033  mov     [rbp+4A0h+var_510], r13
0x180030037  movups  xmmword ptr [rbp+4A0h+var_498.Length], xmm0
0x18003003b  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180030042  mov     [rbp+4A0h+var_4D0], rax
0x180030046  mov     [rbp+4A0h+var_4C8], r13
0x18003004a  mov     [rbp+4A0h+var_4C0], r13d
0x18003004e  mov     [rbp+4A0h+var_4E8], r13
0x180030052  lea     rax, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; CVaultHeapAllocator VaultGlobals::g_HeapAlloc
0x180030059  mov     [rbp+4A0h+var_4E0], rax
0x18003005d  mov     [rbp+4A0h+SourceString], r13
0x180030061  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180030068  mov     [rbp+4A0h+var_508], rax
0x18003006c  mov     [rbp+4A0h+hMem], r13
0x180030070  mov     [rbp+4A0h+var_4F8], r13d
0x180030074  movups  [rbp+4A0h+Buf2], xmm0
0x180030078  mov     r8b, 1; unsigned __int8
0x18003007b  lea     rdx, [rbp+4A0h+hMem]; struct IVaultStore **
0x18003007f  mov     rcx, [rdi]; this
0x180030082  call    ?GetVaultStore@CUserVault@@QEAAKPEAPEAUIVaultStore@@E@Z; CUserVault::GetVaultStore(IVaultStore * *,uchar)
0x180030087  mov     rbx, [rbp+4A0h+hMem]
0x18003008b  test    eax, eax
0x18003008d  jnz     loc_18003013D
0x180030093  mov     rax, [rbx]
0x180030096  lea     rdx, [rbp+4A0h+Buf2]
0x18003009a  mov     rcx, rbx
0x18003009d  mov     rax, [rax+18h]
0x1800300a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300a6  test    eax, eax
0x1800300a8  jnz     loc_18003013D
0x1800300ae  lea     r14d, [r13+10h]
0x1800300b2  mov     r8d, r14d; Size
0x1800300b5  lea     rdx, [rbp+4A0h+Buf2]; Buf2
0x1800300b9  lea     rcx, Vault_DefaultVault_ID; Buf1
0x1800300c0  call    memcmp_0
0x1800300c5  test    eax, eax
0x1800300c7  jz      short loc_1800300E0
0x1800300c9  mov     r8d, r14d; Size
0x1800300cc  lea     rdx, [rbp+4A0h+Buf2]; Buf2
0x1800300d0  lea     rcx, Vault_CredmanVault_ID; Buf1
0x1800300d7  call    memcmp_0
0x1800300dc  test    eax, eax
0x1800300de  jnz     short loc_180030154
0x1800300e0  lea     r9, [rbp+4A0h+var_520]
0x1800300e4  mov     r8d, 8
0x1800300ea  lea     rdx, [rdi+4Ch]
0x1800300ee  mov     ecx, 92h
0x1800300f3  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x1800300f9  test    eax, eax
0x1800300fb  js      short loc_18003014B
0x1800300fd  cmp     byte ptr [rbp+4A0h+var_520], r13b
0x180030101  jz      short loc_180030154
0x180030103  lea     rdx, [rbp+4A0h+var_518]
0x180030107  lea     rcx, [rbp+4A0h+var_51C]
0x18003010b  call    cs:__imp_LsapAdtGetCallerProcessInfo
0x180030111  test    eax, eax
0x180030113  js      short loc_18003014B
0x180030115  lea     rdx, [rbp+4A0h+var_4F0]
0x180030119  lea     rcx, [rbp+4A0h+var_510]
0x18003011d  call    cs:__imp_LsapQueryClientInfo
0x180030123  test    eax, eax
0x180030125  js      short loc_18003014B
0x180030127  mov     r9b, 1; unsigned __int8
0x18003012a  lea     r8, [rbp+4A0h+var_4C8]; struct IVaultSchema **
0x18003012e  mov     rdx, r15; struct _GUID *
0x180030131  mov     rcx, [rdi]; this
0x180030134  call    ?VaultGetSchema@@YAKPEAVCUserVault@@PEBU_GUID@@PEAPEAUIVaultSchema@@E@Z; VaultGetSchema(CUserVault *,_GUID const *,IVaultSchema * *,uchar)
0x180030139  test    eax, eax
0x18003013b  jz      short loc_180030198
0x18003013d  jle     short loc_180030149
0x18003013f  movzx   eax, ax
0x180030142  or      eax, 80070000h
0x180030147  test    eax, eax
0x180030149  jns     short loc_180030154
0x18003014b  mov     ecx, eax
0x18003014d  call    cs:__imp_LsapAuditFailed
0x180030153  nop
0x180030154  test    rbx, rbx
0x180030157  jz      loc_1800302D9
0x18003015d  mov     eax, [rbp+4A0h+var_4F8]
0x180030160  test    eax, eax
0x180030162  jz      short loc_18003017E
0x180030164  test    rbx, rbx
0x180030167  jz      short loc_18003017E
0x180030169  mov     ecx, eax
0x18003016b  test    eax, eax
0x18003016d  jz      short loc_18003017E
0x18003016f  mov     rax, rbx
0x180030172  mov     [rax], r13b
0x180030175  inc     rax
0x180030178  sub     rcx, 1
0x18003017c  jnz     short loc_180030172
0x18003017e  mov     rax, [rbp+4A0h+var_508]
0x180030182  mov     rcx, rbx; hMem
0x180030185  test    rax, rax
0x180030188  jz      loc_1800302D3
0x18003018e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030193  jmp     loc_1800302D9
0x180030198  test    rsi, rsi
0x18003019b  jz      short loc_1800301BB
0x18003019d  lea     r8, [rbp+4A0h+var_4E8]
0x1800301a1  mov     rcx, rsi
0x1800301a4  call    ?VaultVariantToUnicodeString@@YAJPEAU_VAULT_ITEM_ELEMENT@@PEAUIVaultAllocator@@AEAV?$CVaultAutoPtr2@PEAGX@@@Z; VaultVariantToUnicodeString(_VAULT_ITEM_ELEMENT *,IVaultAllocator *,CVaultAutoPtr2<ushort *,void> &)
0x1800301a9  test    eax, eax
0x1800301ab  js      short loc_18003014B
0x1800301ad  mov     rdx, [rbp+4A0h+SourceString]; SourceString
0x1800301b1  lea     rcx, [rbp+4A0h+DestinationString]; DestinationString
0x1800301b5  call    cs:__imp_RtlInitUnicodeString
0x1800301bb  mov     rcx, [rbp+4A0h+var_4C8]
0x1800301bf  mov     rax, [rcx]
0x1800301c2  mov     rax, [rax+88h]
0x1800301c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301ce  mov     rdx, rax; SourceString
0x1800301d1  lea     rcx, [rbp+4A0h+var_4B8]; DestinationString
0x1800301d5  call    cs:__imp_RtlInitUnicodeString
0x1800301db  lea     rdx, SourceString; "VAULT"
0x1800301e2  lea     rcx, [rbp+4A0h+var_498]; DestinationString
0x1800301e6  call    cs:__imp_RtlInitUnicodeString
0x1800301ec  mov     eax, [rbp+4A0h+var_51C]
0x1800301ef  mov     [rsp+5E0h+var_528], eax
0x1800301f6  mov     ecx, 1Bh
0x1800301fb  mov     [rsp+5E0h+var_530], ecx
0x180030202  mov     rax, [rbp+4A0h+var_518]
0x180030206  mov     [rsp+5E0h+var_538], rax
0x18003020e  mov     [rsp+5E0h+var_540], 0Ch
0x180030219  mov     [rsp+5E0h+var_548], r12d
0x180030221  mov     [rsp+5E0h+var_550], ecx
0x180030228  mov     [rsp+5E0h+var_558], r15
0x180030230  mov     [rsp+5E0h+var_560], 0Dh
0x18003023b  lea     rax, [rbp+4A0h+var_4B8]
0x18003023f  mov     [rsp+5E0h+var_568], rax
0x180030244  mov     [rsp+5E0h+var_570], 1
0x18003024c  lea     rax, [rbp+4A0h+DestinationString]
0x180030250  mov     [rsp+5E0h+var_578], rax
0x180030255  mov     [rsp+5E0h+var_580], 1
0x18003025d  mov     rax, [rdi+4Ch]
0x180030261  mov     [rsp+5E0h+var_588], rax
0x180030266  mov     [rsp+5E0h+var_590], 5
0x18003026e  lea     rax, [rbp+4A0h+var_498]
0x180030272  mov     [rsp+5E0h+var_598], rax
0x180030277  mov     [rsp+5E0h+var_5A0], 1
0x18003027f  mov     rax, [rbp+4A0h+var_510]
0x180030283  mov     rcx, [rax]
0x180030286  mov     [rsp+5E0h+var_5A8], rcx
0x18003028b  mov     [rsp+5E0h+var_5B0], 4
0x180030293  mov     [rsp+5E0h+var_5B8], 9
0x18003029a  mov     [rsp+5E0h+var_5C0], 8
0x1800302a1  mov     edx, 7
0x1800302a6  mov     r9d, 92h
0x1800302ac  mov     r8d, 1504h
0x1800302b2  lea     rcx, [rbp+4A0h+var_470]
0x1800302b6  call    cs:__imp_LsapAdtInitParametersArray
0x1800302bc  test    eax, eax
0x1800302be  js      loc_18003014B
0x1800302c4  lea     rcx, [rbp+4A0h+var_470]
0x1800302c8  call    cs:__imp_LsapAdtWriteLog
0x1800302ce  jmp     loc_180030154
0x1800302d3  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x1800302d8  nop
0x1800302d9  lea     rcx, [rbp+4A0h+var_4E8]
0x1800302dd  call    ?Delete@?$CVaultAutoPtr2@PEAEX@@QEAAXXZ; CVaultAutoPtr2<uchar *,void>::Delete(void)
0x1800302e2  nop
0x1800302e3  lea     rcx, [rbp+4A0h+var_4D0]
0x1800302e7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800302ec  nop
0x1800302ed  mov     rcx, [rbp+4A0h+var_50]
0x1800302f4  xor     rcx, rsp; StackCookie
0x1800302f7  call    __security_check_cookie
0x1800302fc  add     rsp, 5A8h
0x180030303  pop     r15
0x180030305  pop     r14
0x180030307  pop     r13
0x180030309  pop     r12
0x18003030b  pop     rdi
0x18003030c  pop     rsi
0x18003030d  pop     rbx
0x18003030e  pop     rbp
0x18003030f  retn
```
