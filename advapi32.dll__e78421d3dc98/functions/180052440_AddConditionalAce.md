# AddConditionalAce

- ea: `0x180052440`
- end: `0x1800526da`
- name: `AddConditionalAce`
- size: `666`
- prototype: `BOOL __stdcall(PACL pAcl, DWORD dwAceRevision, DWORD AceFlags, UCHAR AceType, DWORD AccessMask, PSID pSid, PWCHAR ConditionStr, DWORD *ReturnLength)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18003073c`
- `0x180052440`
- `0x180065042`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800525aa`
- `ntdll!RtlLengthSid` at `0x1800525f3`
- `ntdll!RtlLengthSid` at `0x180052622`
- `ntdll!RtlLengthSid` at `0x1800525aa`
- `ntdll!RtlLengthSid` at `0x1800525f3`
- `ntdll!RtlLengthSid` at `0x180052622`
- `ntdll!RtlValidSid` at `0x1800524b9`
- `ntdll!RtlValidSid` at `0x1800524b9`
- `ntdll!RtlCopySid` at `0x180052607`
- `ntdll!RtlCopySid` at `0x180052607`
- `ntdll!RtlAddAce` at `0x180052654`
- `ntdll!RtlAddAce` at `0x180052654`
- `ntdll!RtlNtStatusToDosError` at `0x1800526b1`
- `ntdll!RtlNtStatusToDosError` at `0x1800526b1`
- `KERNELBASE!LocalAlloc` at `0x1800525c4`
- `KERNELBASE!LocalAlloc` at `0x1800525c4`
- `KERNEL32!LocalFree` at `0x180052508`
- `KERNEL32!LocalFree` at `0x180052516`
- `KERNEL32!LocalFree` at `0x180052508`
- `KERNEL32!LocalFree` at `0x180052516`
- `KERNEL32!SetLastError` at `0x1800524f4`
- `KERNEL32!SetLastError` at `0x1800524f4`

## pseudocode

```c
BOOL __stdcall AddConditionalAce(
        PACL pAcl,
        DWORD dwAceRevision,
        DWORD AceFlags,
        UCHAR AceType,
        DWORD AccessMask,
        PSID pSid,
        PWCHAR ConditionStr,
        DWORD *ReturnLength)
{
  DWORD *v8; // r13
  char *v9; // rdi
  int v14; // ebp
  ULONG ConditionForString; // edx
  BOOL v16; // ebx
  unsigned int v18; // eax
  ULONG v19; // ebp
  ULONG AceListLength; // r14d
  char *v21; // rax
  PSID v22; // rcx
  ULONG v23; // eax
  unsigned int v24; // ebx
  ULONG v25; // eax
  int v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  PACL v29; // rcx
  HLOCAL hMem; // [rsp+58h] [rbp-40h] BYREF
  __int64 v31; // [rsp+60h] [rbp-38h] BYREF
  size_t Size; // [rsp+A0h] [rbp+8h] BYREF
  ULONG AceRevision; // [rsp+A8h] [rbp+10h]

  AceRevision = dwAceRevision;
  v8 = ReturnLength;
  v9 = 0;
  hMem = 0;
  LODWORD(Size) = 0;
  *ReturnLength = 0;
  v31 = 0;
  if ( !pAcl )
    goto LABEL_11;
  v14 = (int)ConditionStr;
  if ( !ConditionStr || ((AceType - 9) & 0xFA) != 0 || AceType == 14 )
    goto LABEL_11;
  if ( !RtlValidSid(pSid) )
  {
    ConditionForString = 1337;
LABEL_12:
    SetLastError(ConditionForString);
LABEL_13:
    v16 = 0;
    goto LABEL_14;
  }
  if ( pAcl->AclRevision > 4u || dwAceRevision > 4 )
  {
    ConditionForString = 1306;
    goto LABEL_12;
  }
  if ( AceType == 13 )
  {
    if ( (AceFlags & 0xFFFFFF20) != 0 )
      goto LABEL_11;
  }
  else if ( (AceFlags & 0xFFFFFFE0) != 0 )
  {
LABEL_11:
    ConditionForString = 87;
    goto LABEL_12;
  }
  ConditionForString = LocalGetConditionForString(
                         v14,
                         (unsigned int)&v31,
                         (unsigned int)&hMem,
                         (unsigned int)&Size,
                         0,
                         0,
                         0,
                         0,
                         1);
  if ( ConditionForString )
    goto LABEL_12;
  if ( (unsigned int)Size > 0xFFFFFFFC
    || (v18 = (Size + 3) & 0xFFFFFFFC, v19 = v18 + 12, v18 + 12 < v18)
    || (AceListLength = RtlLengthSid(pSid) + v18 + 8, AceListLength < v19) )
  {
    ConditionForString = 534;
    goto LABEL_12;
  }
  v21 = (char *)LocalAlloc(0x40u, AceListLength);
  v9 = v21;
  if ( !v21 )
  {
    ConditionForString = 8;
    goto LABEL_12;
  }
  v22 = pSid;
  *v21 = AceType;
  v21[1] = AceFlags;
  *((_WORD *)v21 + 1) = AceListLength;
  *((_DWORD *)v21 + 1) = AccessMask;
  v23 = RtlLengthSid(v22);
  RtlCopySid(v23, v9 + 8, pSid);
  if ( (_DWORD)Size )
  {
    v24 = Size;
    v25 = RtlLengthSid(pSid);
    memcpy_0(&v9[v25 + 8], hMem, v24);
  }
  v26 = RtlAddAce(pAcl, AceRevision, 0xFFFFFFFF, v9, AceListLength);
  v27 = 8;
  *v8 = 8;
  if ( pAcl->AceCount )
  {
    v28 = 0;
    v29 = pAcl + 1;
    do
    {
      ++v28;
      v27 += v29->AclSize;
      *v8 = v27;
      v29 = (PACL)((char *)v29 + v29->AclSize);
    }
    while ( v28 < pAcl->AceCount );
  }
  if ( v26 < 0 )
  {
    *v8 = (v27 + AceListLength + 3) & 0xFFFFFFFC;
    ConditionForString = RtlNtStatusToDosError(v26);
    if ( !ConditionForString )
      goto LABEL_13;
    goto LABEL_12;
  }
  v16 = 1;
LABEL_14:
  if ( hMem )
    LocalFree(hMem);
  if ( v9 )
    LocalFree(v9);
  return v16;
}

```

## disassembly

```asm
0x180052440  mov     rax, rsp
0x180052443  mov     [rax+18h], rbx
0x180052447  mov     [rax+20h], rbp
0x18005244b  mov     [rax+10h], edx
0x18005244e  push    rsi
0x18005244f  push    rdi
0x180052450  push    r12
0x180052452  push    r13
0x180052454  push    r14
0x180052456  sub     rsp, 70h
0x18005245a  mov     r13, [rsp+98h+ReturnLength]
0x180052462  xor     edi, edi
0x180052464  mov     [rsp+98h+var_48], 0
0x18005246c  mov     bl, r9b
0x18005246f  mov     qword ptr [rax-40h], 0
0x180052477  mov     r12d, r8d
0x18005247a  mov     dword ptr [rax+8], 0
0x180052481  mov     r14d, edx
0x180052484  mov     [r13+0], edi
0x180052488  mov     rsi, rcx
0x18005248b  mov     qword ptr [rax-38h], 0
0x180052493  test    rcx, rcx
0x180052496  jz      short loc_1800524ED
0x180052498  mov     rbp, [rsp+98h+ConditionStr]
0x1800524a0  test    rbp, rbp
0x1800524a3  jz      short loc_1800524ED
0x1800524a5  lea     eax, [rbx-9]
0x1800524a8  test    al, 0FAh
0x1800524aa  jnz     short loc_1800524ED
0x1800524ac  cmp     bl, 0Eh
0x1800524af  jz      short loc_1800524ED
0x1800524b1  mov     rcx, [rsp+98h+pSid]; Sid
0x1800524b9  call    cs:__imp_RtlValidSid
0x1800524bf  xor     ecx, ecx
0x1800524c1  test    al, al
0x1800524c3  jnz     short loc_1800524CC
0x1800524c5  mov     edx, 539h
0x1800524ca  jmp     short loc_1800524F2
0x1800524cc  cmp     byte ptr [rsi], 4
0x1800524cf  ja      loc_1800526D0
0x1800524d5  cmp     r14d, 4
0x1800524d9  ja      loc_1800526D0
0x1800524df  cmp     bl, 0Dh
0x1800524e2  jz      short loc_180052537
0x1800524e4  test    r12d, 0FFFFFFE0h
0x1800524eb  jz      short loc_180052540
0x1800524ed  mov     edx, 57h ; 'W'
0x1800524f2  mov     ecx, edx; dwErrCode
0x1800524f4  call    cs:__imp_SetLastError
0x1800524fa  mov     ebx, [rsp+98h+var_48]
0x1800524fe  mov     rcx, [rsp+98h+hMem]; hMem
0x180052503  test    rcx, rcx
0x180052506  jz      short loc_18005250E
0x180052508  call    cs:__imp_LocalFree
0x18005250e  test    rdi, rdi
0x180052511  jz      short loc_18005251C
0x180052513  mov     rcx, rdi; hMem
0x180052516  call    cs:__imp_LocalFree
0x18005251c  lea     r11, [rsp+98h+var_28]
0x180052521  mov     eax, ebx
0x180052523  mov     rbx, [r11+40h]
0x180052527  mov     rbp, [r11+48h]
0x18005252b  mov     rsp, r11
0x18005252e  pop     r14
0x180052530  pop     r13
0x180052532  pop     r12
0x180052534  pop     rdi
0x180052535  pop     rsi
0x180052536  retn
0x180052537  test    r12d, 0FFFFFF20h
0x18005253e  jnz     short loc_1800524ED
0x180052540  mov     [rsp+98h+var_58], 1
0x180052545  lea     r9, [rsp+98h+Size]
0x18005254d  mov     [rsp+98h+var_60], cl
0x180052551  lea     r8, [rsp+98h+hMem]
0x180052556  mov     [rsp+98h+var_68], rcx
0x18005255b  lea     rdx, [rsp+98h+var_38]
0x180052560  mov     [rsp+98h+var_70], rcx
0x180052565  mov     qword ptr [rsp+98h+AceListLength], rcx
0x18005256a  mov     rcx, rbp
0x18005256d  call    LocalGetConditionForString
0x180052572  mov     edx, eax
0x180052574  test    eax, eax
0x180052576  jnz     loc_1800524F2
0x18005257c  mov     eax, dword ptr [rsp+98h+Size]
0x180052583  mov     ecx, 0FFFFFFFCh
0x180052588  cmp     eax, ecx
0x18005258a  jbe     short loc_180052596
0x18005258c  mov     edx, 216h
0x180052591  jmp     loc_1800524F2
0x180052596  add     eax, 3
0x180052599  and     eax, ecx
0x18005259b  lea     ebp, [rax+0Ch]
0x18005259e  cmp     ebp, eax
0x1800525a0  jb      short loc_18005258C
0x1800525a2  mov     rcx, [rsp+98h+pSid]; Sid
0x1800525aa  call    cs:__imp_RtlLengthSid
0x1800525b0  lea     r14d, [rbp-4]
0x1800525b4  add     r14d, eax
0x1800525b7  cmp     r14d, ebp
0x1800525ba  jb      short loc_18005258C
0x1800525bc  mov     edx, r14d; uBytes
0x1800525bf  mov     ecx, 40h ; '@'; uFlags
0x1800525c4  call    cs:__imp_LocalAlloc
0x1800525ca  mov     rdi, rax
0x1800525cd  test    rax, rax
0x1800525d0  jz      loc_1800526C6
0x1800525d6  mov     rcx, [rsp+98h+pSid]; Sid
0x1800525de  mov     [rax], bl
0x1800525e0  mov     [rax+1], r12b
0x1800525e4  mov     [rax+2], r14w
0x1800525e9  mov     eax, [rsp+98h+AccessMask]
0x1800525f0  mov     [rdi+4], eax
0x1800525f3  call    cs:__imp_RtlLengthSid
0x1800525f9  mov     r8, [rsp+98h+pSid]; SourceSid
0x180052601  lea     rdx, [rdi+8]; DestinationSid
0x180052605  mov     ecx, eax; DestinationSidLength
0x180052607  call    cs:__imp_RtlCopySid
0x18005260d  mov     eax, dword ptr [rsp+98h+Size]
0x180052614  test    eax, eax
0x180052616  jz      short loc_18005263E
0x180052618  mov     rcx, [rsp+98h+pSid]; Sid
0x180052620  mov     ebx, eax
0x180052622  call    cs:__imp_RtlLengthSid
0x180052628  mov     rdx, [rsp+98h+hMem]; Src
0x18005262d  mov     r8d, ebx; Size
0x180052630  mov     ecx, eax
0x180052632  add     rcx, 8
0x180052636  add     rcx, rdi; void *
0x180052639  call    memcpy_0
0x18005263e  mov     edx, [rsp+98h+AceRevision]; AceRevision
0x180052645  mov     r9, rdi; AceList
0x180052648  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18005264c  mov     [rsp+98h+AceListLength], r14d; AceListLength
0x180052651  mov     rcx, rsi; Acl
0x180052654  call    cs:__imp_RtlAddAce
0x18005265a  mov     edx, 8
0x18005265f  xor     ecx, ecx
0x180052661  mov     [r13+0], edx
0x180052665  mov     r9d, eax
0x180052668  cmp     cx, [rsi+4]
0x18005266c  jnb     short loc_180052692
0x18005266e  xor     r8d, r8d
0x180052671  lea     rcx, [rsi+8]
0x180052675  movzx   eax, word ptr [rcx+2]
0x180052679  inc     r8d
0x18005267c  add     edx, eax
0x18005267e  mov     [r13+0], edx
0x180052682  movzx   eax, word ptr [rcx+2]
0x180052686  add     rcx, rax
0x180052689  movzx   eax, word ptr [rsi+4]
0x18005268d  cmp     r8d, eax
0x180052690  jb      short loc_180052675
0x180052692  test    r9d, r9d
0x180052695  js      short loc_1800526A1
0x180052697  mov     ebx, 1
0x18005269c  jmp     loc_1800524FE
0x1800526a1  lea     eax, [r14+3]
0x1800526a5  mov     ecx, r9d; Status
0x1800526a8  add     eax, edx
0x1800526aa  and     eax, 0FFFFFFFCh
0x1800526ad  mov     [r13+0], eax
0x1800526b1  call    cs:__imp_RtlNtStatusToDosError
0x1800526b7  mov     edx, eax
0x1800526b9  test    eax, eax
0x1800526bb  jz      loc_1800524FA
0x1800526c1  jmp     loc_1800524F2
0x1800526c6  mov     edx, 8
0x1800526cb  jmp     loc_1800524F2
0x1800526d0  mov     edx, 51Ah
0x1800526d5  jmp     loc_1800524F2
```
