# CTnoRecovery::ApplyNewSecurityDescriptorToKey(HKEY__ *,void *)

- ea: `0x18011b0b4`
- end: `0x18011b336`
- name: `?ApplyNewSecurityDescriptorToKey@CTnoRecovery@@CAJPEAUHKEY__@@PEAX@Z`
- size: `642`
- prototype: `__int64 __fastcall(HKEY hKey, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18011bae8`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x180008290`
- `0x18001fc30`
- `0x18011ae54`
- `0x18011b0b4`
- `0x18011b33c`
- `0x18011b424`
- `0x18011b638`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x18011b233`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x18011b233`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b112`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b120`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b29b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b305`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b112`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b120`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b29b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b305`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011b313`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18011b17c`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18011b17c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18011b1eb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18011b1eb`

## pseudocode

```c
__int64 __fastcall CTnoRecovery::ApplyNewSecurityDescriptorToKey(HKEY hKey, PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  HLOCAL v3; // rcx
  signed int RegKeySecurityDescriptor; // ebx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  struct _ACL *v9; // rbx
  int v10; // eax
  HLOCAL v11; // [rsp+30h] [rbp-20h] BYREF
  void *Block; // [rsp+38h] [rbp-18h] BYREF
  PACL OldAcl; // [rsp+40h] [rbp-10h] BYREF
  PACL pacl; // [rsp+48h] [rbp-8h] BYREF
  bool v15; // [rsp+80h] [rbp+30h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+90h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+48h] BYREF

  v15 = 0;
  v3 = 0;
  hMem = 0;
  pcCountOfExplicitEntries = 0;
  pacl = 0;
  OldAcl = 0;
  Block = 0;
  v11 = 0;
  if ( hKey && pSecurityDescriptor )
  {
    RegKeySecurityDescriptor = CTnoRecovery::GetRegKeySecurityDescriptor(hKey, (unsigned __int8 **)&Block);
    if ( RegKeySecurityDescriptor < 0 )
      goto LABEL_4;
    RegKeySecurityDescriptor = CTnoRecovery::GetDaclsFromSecurityDescriptors(Block, pSecurityDescriptor, &OldAcl, &pacl);
    if ( RegKeySecurityDescriptor < 0 )
      goto LABEL_4;
    RegKeySecurityDescriptor = CTnoRecovery::CheckSecurityDescriptorProtectedFlag(pSecurityDescriptor, &v15);
    if ( RegKeySecurityDescriptor < 0 )
      goto LABEL_4;
    if ( v15 )
    {
      v9 = pacl;
    }
    else
    {
      RegKeySecurityDescriptor = GetExplicitEntriesFromAclW(
                                   pacl,
                                   &pcCountOfExplicitEntries,
                                   (PEXPLICIT_ACCESS_W *)&hMem);
      if ( RegKeySecurityDescriptor )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_14;
        }
        v8 = 20;
LABEL_13:
        WPP_SF_d(
          *((_QWORD *)v7 + 12),
          v8,
          WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
          (unsigned int)RegKeySecurityDescriptor);
LABEL_14:
        if ( RegKeySecurityDescriptor > 0 )
          RegKeySecurityDescriptor = (unsigned __int16)RegKeySecurityDescriptor | 0x80070000;
        goto LABEL_4;
      }
      if ( pcCountOfExplicitEntries )
      {
        RegKeySecurityDescriptor = SetEntriesInAclW(
                                     pcCountOfExplicitEntries,
                                     (PEXPLICIT_ACCESS_W)hMem,
                                     OldAcl,
                                     (PACL *)&v11);
        if ( RegKeySecurityDescriptor )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_14;
          }
          v8 = 21;
          goto LABEL_13;
        }
        v9 = (struct _ACL *)v11;
      }
      else
      {
        v9 = OldAcl;
      }
    }
    if ( !IsValidAcl(v9) )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids);
      }
      RegKeySecurityDescriptor = -2147024883;
      goto LABEL_4;
    }
    v10 = CTnoRecovery::ApplyMergedSecurityDescriptor(hKey, pSecurityDescriptor, v9);
    if ( v10 < 0 )
    {
      RegKeySecurityDescriptor = v10;
LABEL_4:
      LocalFree(hMem);
      hMem = 0;
      LocalFree(v11);
      v11 = 0;
      operator delete(Block);
      return (unsigned int)RegKeySecurityDescriptor;
    }
    LocalFree(hMem);
    hMem = 0;
    LocalFree(v11);
    v11 = 0;
    operator delete(Block);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        19,
        WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
        hKey,
        pSecurityDescriptor);
      v3 = hMem;
    }
    LocalFree(v3);
    hMem = 0;
    LocalFree(v11);
    operator delete(Block);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18011b0b4  push    rbp
0x18011b0b6  push    rbx
0x18011b0b7  push    rsi
0x18011b0b8  push    rdi
0x18011b0b9  push    r14
0x18011b0bb  mov     rbp, rsp
0x18011b0be  sub     rsp, 50h
0x18011b0c2  xor     r14d, r14d
0x18011b0c5  mov     rsi, rcx
0x18011b0c8  mov     [rbp+arg_0], r14b
0x18011b0cc  mov     ecx, r14d
0x18011b0cf  mov     [rbp+hMem], rcx
0x18011b0d3  mov     rdi, rdx
0x18011b0d6  mov     [rbp+pcCountOfExplicitEntries], r14d
0x18011b0da  mov     [rbp+pacl], r14
0x18011b0de  mov     [rbp+OldAcl], r14
0x18011b0e2  mov     [rbp+Block], r14
0x18011b0e6  mov     [rbp+var_20], r14
0x18011b0ea  test    rsi, rsi
0x18011b0ed  jz      loc_18011B2C0
0x18011b0f3  test    rdx, rdx
0x18011b0f6  jz      loc_18011B2C0
0x18011b0fc  lea     rdx, [rbp+Block]; unsigned __int8 **
0x18011b100  mov     rcx, rsi; hKey
0x18011b103  call    ?GetRegKeySecurityDescriptor@CTnoRecovery@@CAJPEAUHKEY__@@PEAPEAE@Z; CTnoRecovery::GetRegKeySecurityDescriptor(HKEY__ *,uchar * *)
0x18011b108  mov     ebx, eax
0x18011b10a  test    eax, eax
0x18011b10c  jns     short loc_18011B13A
0x18011b10e  mov     rcx, [rbp+hMem]; hMem
0x18011b112  call    cs:__imp_LocalFree
0x18011b118  mov     rcx, [rbp+var_20]; hMem
0x18011b11c  mov     [rbp+hMem], r14
0x18011b120  call    cs:__imp_LocalFree
0x18011b126  mov     rcx, [rbp+Block]; Block
0x18011b12a  mov     [rbp+var_20], r14
0x18011b12e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b133  mov     eax, ebx
0x18011b135  jmp     loc_18011B32B
0x18011b13a  mov     rcx, [rbp+Block]; void *
0x18011b13e  lea     r9, [rbp+pacl]; struct _ACL **
0x18011b142  lea     r8, [rbp+OldAcl]; struct _ACL **
0x18011b146  mov     rdx, rdi; void *
0x18011b149  call    ?GetDaclsFromSecurityDescriptors@CTnoRecovery@@CAJPEAX0PEAPEAU_ACL@@1@Z; CTnoRecovery::GetDaclsFromSecurityDescriptors(void *,void *,_ACL * *,_ACL * *)
0x18011b14e  mov     ebx, eax
0x18011b150  test    eax, eax
0x18011b152  js      short loc_18011B10E
0x18011b154  lea     rdx, [rbp+arg_0]; bool *
0x18011b158  mov     rcx, rdi; void *
0x18011b15b  call    ?CheckSecurityDescriptorProtectedFlag@CTnoRecovery@@CAJPEAXPEA_N@Z; CTnoRecovery::CheckSecurityDescriptorProtectedFlag(void *,bool *)
0x18011b160  mov     ebx, eax
0x18011b162  test    eax, eax
0x18011b164  js      short loc_18011B10E
0x18011b166  cmp     [rbp+arg_0], r14b
0x18011b16a  jnz     loc_18011B22C
0x18011b170  mov     rcx, [rbp+pacl]; pacl
0x18011b174  lea     r8, [rbp+hMem]; pListOfExplicitEntries
0x18011b178  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x18011b17c  call    cs:__imp_GetExplicitEntriesFromAclW
0x18011b182  mov     ebx, eax
0x18011b184  test    eax, eax
0x18011b186  jz      short loc_18011B1D8
0x18011b188  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b18f  lea     rax, WPP_GLOBAL_Control
0x18011b196  cmp     rcx, rax
0x18011b199  jz      short loc_18011B1C2
0x18011b19b  test    dword ptr [rcx+6Ch], 8000000h
0x18011b1a2  jz      short loc_18011B1C2
0x18011b1a4  cmp     byte ptr [rcx+69h], 1
0x18011b1a8  jb      short loc_18011B1C2
0x18011b1aa  mov     edx, 14h
0x18011b1af  mov     rcx, [rcx+60h]
0x18011b1b3  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b1ba  mov     r9d, ebx
0x18011b1bd  call    WPP_SF_d
0x18011b1c2  test    ebx, ebx
0x18011b1c4  jle     loc_18011B10E
0x18011b1ca  movzx   ebx, bx
0x18011b1cd  or      ebx, 80070000h
0x18011b1d3  jmp     loc_18011B10E
0x18011b1d8  mov     ecx, [rbp+pcCountOfExplicitEntries]; cCountOfExplicitEntries
0x18011b1db  test    ecx, ecx
0x18011b1dd  jz      short loc_18011B226
0x18011b1df  mov     r8, [rbp+OldAcl]; OldAcl
0x18011b1e3  lea     r9, [rbp+var_20]; NewAcl
0x18011b1e7  mov     rdx, [rbp+hMem]; pListOfExplicitEntries
0x18011b1eb  call    cs:__imp_SetEntriesInAclW
0x18011b1f1  mov     ebx, eax
0x18011b1f3  test    eax, eax
0x18011b1f5  jz      short loc_18011B220
0x18011b1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b1fe  lea     rax, WPP_GLOBAL_Control
0x18011b205  cmp     rcx, rax
0x18011b208  jz      short loc_18011B1C2
0x18011b20a  test    dword ptr [rcx+6Ch], 8000000h
0x18011b211  jz      short loc_18011B1C2
0x18011b213  cmp     byte ptr [rcx+69h], 1
0x18011b217  jb      short loc_18011B1C2
0x18011b219  mov     edx, 15h
0x18011b21e  jmp     short loc_18011B1AF
0x18011b220  mov     rbx, [rbp+var_20]
0x18011b224  jmp     short loc_18011B230
0x18011b226  mov     rbx, [rbp+OldAcl]
0x18011b22a  jmp     short loc_18011B230
0x18011b22c  mov     rbx, [rbp+pacl]
0x18011b230  mov     rcx, rbx; pAcl
0x18011b233  call    cs:__imp_IsValidAcl
0x18011b239  test    eax, eax
0x18011b23b  jnz     short loc_18011B27E
0x18011b23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b244  lea     rax, WPP_GLOBAL_Control
0x18011b24b  cmp     rcx, rax
0x18011b24e  jz      short loc_18011B274
0x18011b250  test    dword ptr [rcx+6Ch], 8000000h
0x18011b257  jz      short loc_18011B274
0x18011b259  cmp     byte ptr [rcx+69h], 1
0x18011b25d  jb      short loc_18011B274
0x18011b25f  mov     rcx, [rcx+60h]
0x18011b263  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b26a  mov     edx, 16h
0x18011b26f  call    WPP_SF_
0x18011b274  mov     ebx, 8007000Dh
0x18011b279  jmp     loc_18011B10E
0x18011b27e  mov     r8, rbx; pDacl
0x18011b281  mov     rdx, rdi; pSecurityDescriptor
0x18011b284  mov     rcx, rsi; hKey
0x18011b287  call    ?ApplyMergedSecurityDescriptor@CTnoRecovery@@CAJPEAUHKEY__@@PEAXPEAU_ACL@@@Z; CTnoRecovery::ApplyMergedSecurityDescriptor(HKEY__ *,void *,_ACL *)
0x18011b28c  test    eax, eax
0x18011b28e  jns     short loc_18011B297
0x18011b290  mov     ebx, eax
0x18011b292  jmp     loc_18011B10E
0x18011b297  mov     rcx, [rbp+hMem]; hMem
0x18011b29b  call    cs:__imp_LocalFree
0x18011b2a1  mov     rcx, [rbp+var_20]; hMem
0x18011b2a5  mov     [rbp+hMem], r14
0x18011b2a9  call    cs:__imp_LocalFree
0x18011b2af  mov     rcx, [rbp+Block]; Block
0x18011b2b3  mov     [rbp+var_20], r14
0x18011b2b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b2bc  xor     eax, eax
0x18011b2be  jmp     short loc_18011B32B
0x18011b2c0  mov     r10, cs:WPP_GLOBAL_Control
0x18011b2c7  lea     rax, WPP_GLOBAL_Control
0x18011b2ce  cmp     r10, rax
0x18011b2d1  jz      short loc_18011B305
0x18011b2d3  test    dword ptr [r10+6Ch], 8000000h
0x18011b2db  jz      short loc_18011B305
0x18011b2dd  cmp     byte ptr [r10+69h], 1
0x18011b2e2  jb      short loc_18011B305
0x18011b2e4  mov     rcx, [r10+60h]
0x18011b2e8  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b2ef  mov     edx, 13h
0x18011b2f4  mov     [rsp+50h+var_30], rdi
0x18011b2f9  mov     r9, rsi
0x18011b2fc  call    WPP_SF_qq
0x18011b301  mov     rcx, [rbp+hMem]; hMem
0x18011b305  call    cs:__imp_LocalFree
0x18011b30b  mov     rcx, [rbp+var_20]; hMem
0x18011b30f  mov     [rbp+hMem], r14
0x18011b313  call    cs:__imp_LocalFree
0x18011b319  mov     rcx, [rbp+Block]; Block
0x18011b31d  mov     [rbp+var_20], r14
0x18011b321  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b326  mov     eax, 80070057h
0x18011b32b  add     rsp, 50h
0x18011b32f  pop     r14
0x18011b331  pop     rdi
0x18011b332  pop     rsi
0x18011b333  pop     rbx
0x18011b334  pop     rbp
0x18011b335  retn
```
