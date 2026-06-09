# RegistryStore::ApplyRegistrySettings(unsigned __int64,unsigned __int64,uchar const *)

- ea: `0x1800809e0`
- end: `0x180080c4d`
- name: `?ApplyRegistrySettings@RegistryStore@@QEAAJ_K0PEBE@Z`
- size: `621`
- prototype: `__int64 __fastcall(RegistryStore *__hidden this, unsigned __int64, unsigned __int64, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18007ac34`

## callees

- `0x1800077c8`
- `0x180017a98`
- `0x18002abc0`
- `0x18002b060`
- `0x180030bcc`
- `0x180037780`
- `0x1800809e0`
- `0x18008128c`
- `0x1800819d0`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180080aa0`
- `ntdll!RtlGetPersistedStateLocation` at `0x180080aa0`

## string_xrefs

- `0x180080ae3`: `\Registry\User\`
- `0x180080afd`: `\Registry\User\`
- `0x180080ba7`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180080bde`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180080c08`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
int __fastcall RegistryStore::ApplyRegistrySettings(
        RegistryStore *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        const unsigned __int8 *a4)
{
  unsigned __int64 v6; // rax
  const unsigned __int8 *v8; // rbx
  unsigned __int64 v9; // r12
  unsigned __int64 v10; // rsi
  unsigned __int8 *v11; // rbp
  unsigned __int16 *DefaultPath; // rax
  unsigned __int8 *v13; // rdx
  __int64 v14; // r8
  int PersistedStateLocation; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ecx
  int v19; // ecx
  int v20; // esi
  unsigned __int64 i; // r14
  struct RegistryDataEntry *v22; // r8
  const unsigned __int16 *v23; // rax
  struct RegistryDataEntry *v24; // r8
  __int64 v25; // rdx
  __int64 v27; // rdx
  unsigned __int16 *v28; // [rsp+20h] [rbp-288h]
  unsigned __int16 v30[264]; // [rsp+50h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v6 = a2;
  v8 = a4;
  v9 = 0;
LABEL_2:
  if ( v9 >= v6 )
    return 0;
  v10 = a3 - 48;
  if ( v8 - a4 > a3 - 48 )
  {
    v27 = 1052;
    goto LABEL_34;
  }
  v11 = (unsigned __int8 *)v8;
  v8 += *(_QWORD *)v8 + *((_QWORD *)v8 + 1) + *((_QWORD *)v8 + 2) + 40;
  if ( v8 - a4 > a3 )
  {
    v27 = 1057;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
      (const char *)0x80070057LL,
      (int)v28);
    return -2147024809;
  }
  DefaultPath = RegistryData::GetDefaultPath((RegistryData *)v11);
  if ( v13 )
    v13 = &v11[v14 + 40];
  v28 = v30;
  PersistedStateLocation = RtlGetPersistedStateLocation(v11 + 40, v13, DefaultPath, *((unsigned int *)v11 + 6));
  if ( PersistedStateLocation < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x42A,
             (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
             (const char *)(unsigned int)PersistedStateLocation,
             (int)v30);
  *((_BYTE *)this + 40) = 0;
  v18 = *((_DWORD *)v11 + 7);
  if ( !v18 )
  {
    *(_QWORD *)this = -2147483646;
LABEL_15:
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_QWORD *)v11 + 4) )
      {
        v6 = a2;
        ++v9;
        goto LABEL_2;
      }
      if ( v8 - a4 > v10 )
        break;
      v22 = (struct RegistryDataEntry *)v8;
      v8 += *((_QWORD *)v8 + 1) + *((_QWORD *)v8 + 2) + *((_QWORD *)v8 + 4) + 42;
      if ( v8 - a4 > a3 )
      {
        v27 = 1092;
        goto LABEL_34;
      }
      if ( *((_BYTE *)this + 40) )
      {
        v23 = RegistryData::GetDefaultPath((RegistryData *)v11);
        v20 = RegistryStore::SetRegistryValue(this, v23, v24);
        if ( v20 < 0 )
        {
          v25 = 1097;
          goto LABEL_26;
        }
      }
      else
      {
        v20 = RegistryStore::SetRegistryValue(this, v30, v22);
        if ( v20 < 0 )
        {
          v25 = 1101;
          goto LABEL_26;
        }
      }
      v10 = a3 - 48;
    }
    v27 = 1089;
    goto LABEL_34;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
    *(_QWORD *)this = -2147483645;
    std::_WChar_traits<unsigned short>::length(L"\\Registry\\User\\", v16, v17);
    std::wstring::_Assign<unsigned short>((char *)this + 8, L"\\Registry\\User\\");
    goto LABEL_15;
  }
  if ( v19 != 1 )
    return -2147024809;
  v20 = RegistryStore::OpenHKUWithUserSidForHKCU(this, v16);
  if ( v20 >= 0 )
  {
    *((_BYTE *)this + 40) = 1;
    v10 = a3 - 48;
    goto LABEL_15;
  }
  v25 = 1079;
LABEL_26:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
    (const char *)(unsigned int)v20,
    (int)v30);
  return v20;
}

```

## disassembly

```asm
0x1800809e0  mov     [rsp+arg_8], rbx
0x1800809e5  push    rbp
0x1800809e6  push    rsi
0x1800809e7  push    rdi
0x1800809e8  push    r12
0x1800809ea  push    r13
0x1800809ec  push    r14
0x1800809ee  push    r15
0x1800809f0  sub     rsp, 270h
0x1800809f7  mov     rax, cs:__security_cookie
0x1800809fe  xor     rax, rsp
0x180080a01  mov     [rsp+2A8h+var_48], rax
0x180080a09  mov     r15, r9
0x180080a0c  mov     [rsp+2A8h+var_268], rdx
0x180080a11  mov     r13, r8
0x180080a14  mov     rax, rdx
0x180080a17  mov     rdi, rcx
0x180080a1a  mov     rbx, r9
0x180080a1d  xor     r12d, r12d
0x180080a20  cmp     r12, rax
0x180080a23  jnb     loc_180080C20
0x180080a29  mov     rax, rbx
0x180080a2c  lea     rsi, [r13-30h]
0x180080a30  sub     rax, r15
0x180080a33  cmp     rax, rsi
0x180080a36  ja      loc_180080BFB
0x180080a3c  mov     rax, [rbx+10h]
0x180080a40  mov     rbp, rbx
0x180080a43  mov     rdx, [rbx+8]
0x180080a47  add     rax, 28h ; '('
0x180080a4b  mov     r8, [rbx]
0x180080a4e  add     rax, rdx
0x180080a51  add     rax, r8
0x180080a54  add     rbx, rax
0x180080a57  mov     rax, rbx
0x180080a5a  sub     rax, r15
0x180080a5d  cmp     rax, r13
0x180080a60  ja      loc_180080BF4
0x180080a66  mov     rcx, rbp; this
0x180080a69  call    ?GetDefaultPath@RegistryData@@QEAAPEAGXZ; RegistryData::GetDefaultPath(void)
0x180080a6e  test    rdx, rdx
0x180080a71  jz      short loc_180080A7A
0x180080a73  lea     rdx, [rbp+28h]
0x180080a77  add     rdx, r8
0x180080a7a  mov     r9d, [rbp+18h]
0x180080a7e  lea     r8, [rsp+2A8h+var_258]
0x180080a83  mov     [rsp+2A8h+var_278], 0
0x180080a8c  lea     rcx, [rbp+28h]
0x180080a90  mov     [rsp+2A8h+var_280], 208h
0x180080a98  mov     qword ptr [rsp+2A8h+var_288], r8; int
0x180080a9d  mov     r8, rax
0x180080aa0  call    cs:__imp_RtlGetPersistedStateLocation
0x180080aa6  test    eax, eax
0x180080aa8  js      loc_180080BD6
0x180080aae  mov     byte ptr [rdi+28h], 0
0x180080ab2  mov     ecx, [rbp+1Ch]
0x180080ab5  test    ecx, ecx
0x180080ab7  jz      short loc_180080B0B
0x180080ab9  sub     ecx, 1
0x180080abc  jz      short loc_180080AE3
0x180080abe  cmp     ecx, 1
0x180080ac1  jnz     loc_180080BBA
0x180080ac7  mov     rcx, rdi; this
0x180080aca  call    ?OpenHKUWithUserSidForHKCU@RegistryStore@@AEAAJXZ; RegistryStore::OpenHKUWithUserSidForHKCU(void)
0x180080acf  mov     esi, eax
0x180080ad1  test    eax, eax
0x180080ad3  js      loc_180080B9A
0x180080ad9  mov     byte ptr [rdi+28h], 1
0x180080add  lea     rsi, [r13-30h]
0x180080ae1  jmp     short loc_180080B12
0x180080ae3  lea     rcx, aRegistryUser; "\\Registry\\User\\"
0x180080aea  mov     qword ptr [rdi], 0FFFFFFFF80000003h
0x180080af1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180080af6  mov     r8, rax
0x180080af9  lea     rcx, [rdi+8]
0x180080afd  lea     rdx, aRegistryUser; "\\Registry\\User\\"
0x180080b04  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180080b09  jmp     short loc_180080B12
0x180080b0b  mov     qword ptr [rdi], 0FFFFFFFF80000002h
0x180080b12  xor     r14d, r14d
0x180080b15  cmp     r14, [rbp+20h]
0x180080b19  jnb     short loc_180080B8D
0x180080b1b  mov     rax, rbx
0x180080b1e  sub     rax, r15
0x180080b21  cmp     rax, rsi
0x180080b24  ja      loc_180080BCF
0x180080b2a  mov     rax, [rbx+20h]
0x180080b2e  mov     r8, rbx; struct RegistryDataEntry *
0x180080b31  add     rax, 2Ah ; '*'
0x180080b35  add     rax, [rbx+10h]
0x180080b39  add     rax, [rbx+8]
0x180080b3d  add     rbx, rax
0x180080b40  mov     rax, rbx
0x180080b43  sub     rax, r15
0x180080b46  cmp     rax, r13
0x180080b49  ja      short loc_180080BC8
0x180080b4b  cmp     byte ptr [rdi+28h], 0
0x180080b4f  jz      short loc_180080B71
0x180080b51  mov     rcx, rbp; this
0x180080b54  call    ?GetDefaultPath@RegistryData@@QEAAPEAGXZ; RegistryData::GetDefaultPath(void)
0x180080b59  mov     rdx, rax; unsigned __int16 *
0x180080b5c  mov     rcx, rdi; this
0x180080b5f  call    ?SetRegistryValue@RegistryStore@@QEAAJPEBGPEAURegistryDataEntry@@@Z; RegistryStore::SetRegistryValue(ushort const *,RegistryDataEntry *)
0x180080b64  mov     esi, eax
0x180080b66  test    eax, eax
0x180080b68  jns     short loc_180080B84
0x180080b6a  mov     edx, 449h
0x180080b6f  jmp     short loc_180080B9F
0x180080b71  lea     rdx, [rsp+2A8h+var_258]; unsigned __int16 *
0x180080b76  mov     rcx, rdi; this
0x180080b79  call    ?SetRegistryValue@RegistryStore@@QEAAJPEBGPEAURegistryDataEntry@@@Z; RegistryStore::SetRegistryValue(ushort const *,RegistryDataEntry *)
0x180080b7e  mov     esi, eax
0x180080b80  test    eax, eax
0x180080b82  js      short loc_180080BC1
0x180080b84  inc     r14
0x180080b87  lea     rsi, [r13-30h]
0x180080b8b  jmp     short loc_180080B15
0x180080b8d  mov     rax, [rsp+2A8h+var_268]
0x180080b92  inc     r12
0x180080b95  jmp     loc_180080A20
0x180080b9a  mov     edx, 437h; void *
0x180080b9f  mov     rcx, [rsp+2A8h]; this
0x180080ba7  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180080bae  mov     r9d, esi; char *
0x180080bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080bb6  mov     eax, esi
0x180080bb8  jmp     short loc_180080C22
0x180080bba  mov     eax, 80070057h
0x180080bbf  jmp     short loc_180080C22
0x180080bc1  mov     edx, 44Dh
0x180080bc6  jmp     short loc_180080B9F
0x180080bc8  mov     edx, 444h
0x180080bcd  jmp     short loc_180080C00
0x180080bcf  mov     edx, 441h
0x180080bd4  jmp     short loc_180080C00
0x180080bd6  mov     rcx, [rsp+2A8h]; this
0x180080bde  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180080be5  mov     r9d, eax; char *
0x180080be8  mov     edx, 42Ah; void *
0x180080bed  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180080bf2  jmp     short loc_180080C22
0x180080bf4  mov     edx, 421h
0x180080bf9  jmp     short loc_180080C00
0x180080bfb  mov     edx, 41Ch; void *
0x180080c00  mov     rcx, [rsp+2A8h]; this
0x180080c08  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180080c0f  mov     ebx, 80070057h
0x180080c14  mov     r9d, ebx; char *
0x180080c17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080c1c  mov     eax, ebx
0x180080c1e  jmp     short loc_180080C22
0x180080c20  xor     eax, eax
0x180080c22  mov     rcx, [rsp+2A8h+var_48]
0x180080c2a  xor     rcx, rsp; StackCookie
0x180080c2d  call    __security_check_cookie
0x180080c32  mov     rbx, [rsp+2A8h+arg_8]
0x180080c3a  add     rsp, 270h
0x180080c41  pop     r15
0x180080c43  pop     r14
0x180080c45  pop     r13
0x180080c47  pop     r12
0x180080c49  pop     rdi
0x180080c4a  pop     rsi
0x180080c4b  pop     rbp
0x180080c4c  retn
```
