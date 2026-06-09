# RdVhd::Uvhd::CDirectoryHelper::GetDefaultSD(ushort const *,void * *)

- ea: `0x18004e41c`
- end: `0x18004e692`
- name: `?GetDefaultSD@CDirectoryHelper@Uvhd@RdVhd@@AEBAJPEBGPEAPEAX@Z`
- size: `630`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f96c`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x18003114c`
- `0x180031178`
- `0x1800488e4`
- `0x180048b28`
- `0x18004e41c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e607`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e678`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e678`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e5fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004e5fd`

## string_xrefs

- `0x18004e493`: `szUserSID`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::GetDefaultSD(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2,
        void **a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  int v8; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v9; // rcx
  __int64 v10; // rdx
  const WCHAR *v11; // rax
  signed int LastError; // eax
  const int *v14; // [rsp+20h] [rbp-38h] BYREF
  int v15; // [rsp+28h] [rbp-30h]
  __int64 v16; // [rsp+2Ch] [rbp-2Ch]
  int v17; // [rsp+34h] [rbp-24h]
  __int64 v18; // [rsp+38h] [rbp-20h]
  int v19; // [rsp+40h] [rbp-18h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+28h] BYREF

  v16 = 128;
  v14 = &CBaseStringT<unsigned short>::`vftable';
  v18 = 0;
  v17 = 0;
  v19 = 0x8000000;
  v15 = 0;
  SecurityDescriptor = 0;
  if ( !a2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 148;
    v7 = L"szUserSID";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, v7);
LABEL_7:
    v8 = -2147024809;
    goto LABEL_41;
  }
  if ( !a3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 149;
    v7 = L"ppDefaultSD";
    goto LABEL_6;
  }
  *a3 = 0;
  v8 = CBaseStringT<unsigned short>::Append((__int64)&v14, L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;FA;;;", 0x32u);
  if ( v8 >= 0 )
  {
    v8 = CBaseStringT<unsigned short>::Append((__int64)&v14, (__int64)a2);
    if ( v8 >= 0 )
    {
      v8 = CBaseStringT<unsigned short>::Append((__int64)&v14, L")", 1u);
      if ( v8 >= 0 )
      {
        v11 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v14);
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v11, 1u, &SecurityDescriptor, 0) )
          goto LABEL_40;
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError && (LastError & 0xFFFF0000) == 0 )
        {
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          v8 = v8 & 0x8000FFFF | 0x50190000;
        }
        if ( v8 >= 0 )
        {
LABEL_40:
          *a3 = SecurityDescriptor;
          SecurityDescriptor = 0;
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 153;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 152;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 151;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 150;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, (unsigned int)v8);
    }
  }
LABEL_41:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  CPathString::~CPathString((CPathString *)&v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004e41c  mov     [rsp-20h+SecurityDescriptor], rcx
0x18004e421  push    rbp
0x18004e422  push    rbx
0x18004e423  push    rsi
0x18004e424  push    rdi
0x18004e425  mov     rbp, rsp
0x18004e428  sub     rsp, 58h
0x18004e42c  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x18004e433  mov     [rbp+var_2C], 80h
0x18004e43b  mov     [rbp+var_38], rax
0x18004e43f  mov     rdi, r8
0x18004e442  mov     rsi, rdx
0x18004e445  mov     [rbp+var_20], 0
0x18004e44d  mov     [rbp+var_24], 0
0x18004e454  mov     [rbp+var_18], 8000000h
0x18004e45b  mov     [rbp+var_30], 0
0x18004e462  mov     [rbp+SecurityDescriptor], 0
0x18004e46a  test    rdx, rdx
0x18004e46d  jnz     short loc_18004E4B4
0x18004e46f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e476  lea     rax, WPP_GLOBAL_Control
0x18004e47d  cmp     rcx, rax
0x18004e480  jz      short loc_18004E4AA
0x18004e482  test    byte ptr [rcx+1Ch], 4
0x18004e486  jz      short loc_18004E4AA
0x18004e488  cmp     byte ptr [rcx+19h], 2
0x18004e48c  jb      short loc_18004E4AA
0x18004e48e  mov     edx, 94h
0x18004e493  lea     r9, aSzusersid_0; "szUserSID"
0x18004e49a  mov     rcx, [rcx+10h]
0x18004e49e  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004e4a5  call    WPP_SF_S
0x18004e4aa  mov     ebx, 80070057h
0x18004e4af  jmp     loc_18004E66F
0x18004e4b4  test    rdi, rdi
0x18004e4b7  jnz     short loc_18004E4E6
0x18004e4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e4c0  lea     rax, WPP_GLOBAL_Control
0x18004e4c7  cmp     rcx, rax
0x18004e4ca  jz      short loc_18004E4AA
0x18004e4cc  test    byte ptr [rcx+1Ch], 4
0x18004e4d0  jz      short loc_18004E4AA
0x18004e4d2  cmp     byte ptr [rcx+19h], 2
0x18004e4d6  jb      short loc_18004E4AA
0x18004e4d8  mov     edx, 95h
0x18004e4dd  lea     r9, aPpdefaultsd; "ppDefaultSD"
0x18004e4e4  jmp     short loc_18004E49A
0x18004e4e6  mov     qword ptr [r8], 0
0x18004e4ed  lea     rdx, aDPaiAOiciFaSyA_1; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A"...
0x18004e4f4  mov     r8d, 32h ; '2'
0x18004e4fa  lea     rcx, [rbp+var_38]
0x18004e4fe  call    ?Append@?$CBaseStringT@G@@QEAAJPEBGK@Z; CBaseStringT<ushort>::Append(ushort const *,ulong)
0x18004e503  mov     ebx, eax
0x18004e505  test    eax, eax
0x18004e507  jns     short loc_18004E551
0x18004e509  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e510  lea     rax, WPP_GLOBAL_Control
0x18004e517  cmp     rcx, rax
0x18004e51a  jz      loc_18004E66F
0x18004e520  test    byte ptr [rcx+1Ch], 4
0x18004e524  jz      loc_18004E66F
0x18004e52a  cmp     byte ptr [rcx+19h], 2
0x18004e52e  jb      loc_18004E66F
0x18004e534  mov     edx, 96h
0x18004e539  mov     rcx, [rcx+10h]
0x18004e53d  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004e544  mov     r9d, ebx
0x18004e547  call    WPP_SF_d
0x18004e54c  jmp     loc_18004E66F
0x18004e551  mov     rdx, rsi
0x18004e554  lea     rcx, [rbp+var_38]
0x18004e558  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x18004e55d  mov     ebx, eax
0x18004e55f  test    eax, eax
0x18004e561  jns     short loc_18004E595
0x18004e563  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e56a  lea     rax, WPP_GLOBAL_Control
0x18004e571  cmp     rcx, rax
0x18004e574  jz      loc_18004E66F
0x18004e57a  test    byte ptr [rcx+1Ch], 4
0x18004e57e  jz      loc_18004E66F
0x18004e584  cmp     byte ptr [rcx+19h], 2
0x18004e588  jb      loc_18004E66F
0x18004e58e  mov     edx, 97h
0x18004e593  jmp     short loc_18004E539
0x18004e595  mov     esi, 1
0x18004e59a  lea     rdx, asc_180075E68; ")"
0x18004e5a1  mov     r8d, esi
0x18004e5a4  lea     rcx, [rbp+var_38]
0x18004e5a8  call    ?Append@?$CBaseStringT@G@@QEAAJPEBGK@Z; CBaseStringT<ushort>::Append(ushort const *,ulong)
0x18004e5ad  mov     ebx, eax
0x18004e5af  test    eax, eax
0x18004e5b1  jns     short loc_18004E5E8
0x18004e5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e5ba  lea     rax, WPP_GLOBAL_Control
0x18004e5c1  cmp     rcx, rax
0x18004e5c4  jz      loc_18004E66F
0x18004e5ca  test    byte ptr [rcx+1Ch], 4
0x18004e5ce  jz      loc_18004E66F
0x18004e5d4  cmp     byte ptr [rcx+19h], 2
0x18004e5d8  jb      loc_18004E66F
0x18004e5de  mov     edx, 98h
0x18004e5e3  jmp     loc_18004E539
0x18004e5e8  lea     rcx, [rbp+var_38]
0x18004e5ec  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004e5f1  mov     rcx, rax; StringSecurityDescriptor
0x18004e5f4  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004e5f8  xor     r9d, r9d; SecurityDescriptorSize
0x18004e5fb  mov     edx, esi; StringSDRevision
0x18004e5fd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004e603  test    eax, eax
0x18004e605  jnz     short loc_18004E660
0x18004e607  call    cs:__imp_GetLastError
0x18004e60d  mov     ebx, eax
0x18004e60f  test    eax, eax
0x18004e611  jz      short loc_18004E633
0x18004e613  test    eax, 0FFFF0000h
0x18004e618  jnz     short loc_18004E633
0x18004e61a  test    eax, eax
0x18004e61c  jle     short loc_18004E627
0x18004e61e  movzx   ebx, ax
0x18004e621  or      ebx, 80070000h
0x18004e627  and     ebx, 0D019FFFFh
0x18004e62d  or      ebx, 50190000h
0x18004e633  test    ebx, ebx
0x18004e635  jns     short loc_18004E660
0x18004e637  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e63e  lea     rax, WPP_GLOBAL_Control
0x18004e645  cmp     rcx, rax
0x18004e648  jz      short loc_18004E66F
0x18004e64a  test    byte ptr [rcx+1Ch], 4
0x18004e64e  jz      short loc_18004E66F
0x18004e650  cmp     byte ptr [rcx+19h], 2
0x18004e654  jb      short loc_18004E66F
0x18004e656  mov     edx, 99h
0x18004e65b  jmp     loc_18004E539
0x18004e660  mov     rax, [rbp+SecurityDescriptor]
0x18004e664  mov     [rdi], rax
0x18004e667  mov     [rbp+SecurityDescriptor], 0
0x18004e66f  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18004e673  test    rcx, rcx
0x18004e676  jz      short loc_18004E67E
0x18004e678  call    cs:__imp_LocalFree
0x18004e67e  lea     rcx, [rbp+var_38]; this
0x18004e682  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004e687  mov     eax, ebx
0x18004e689  add     rsp, 58h
0x18004e68d  pop     rdi
0x18004e68e  pop     rsi
0x18004e68f  pop     rbx
0x18004e690  pop     rbp
0x18004e691  retn
```
