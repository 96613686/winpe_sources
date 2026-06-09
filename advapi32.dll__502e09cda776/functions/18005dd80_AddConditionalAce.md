# AddConditionalAce

- ea: `0x18005dd80`
- end: `0x18005e05d`
- name: `AddConditionalAce`
- size: `733`
- prototype: `BOOL __stdcall(PACL pAcl, DWORD dwAceRevision, DWORD AceFlags, UCHAR AceType, DWORD AccessMask, PSID pSid, PWCHAR ConditionStr, DWORD *ReturnLength)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180030854`
- `0x18005dd80`
- `0x180072042`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18005df03`
- `ntdll!RtlLengthSid` at `0x18005df58`
- `ntdll!RtlLengthSid` at `0x18005df93`
- `ntdll!RtlLengthSid` at `0x18005df03`
- `ntdll!RtlLengthSid` at `0x18005df58`
- `ntdll!RtlLengthSid` at `0x18005df93`
- `ntdll!RtlValidSid` at `0x18005ddf9`
- `ntdll!RtlValidSid` at `0x18005ddf9`
- `ntdll!RtlCopySid` at `0x18005df72`
- `ntdll!RtlCopySid` at `0x18005df72`
- `ntdll!RtlAddAce` at `0x18005dfcb`
- `ntdll!RtlAddAce` at `0x18005dfcb`
- `ntdll!RtlNtStatusToDosError` at `0x18005e02e`
- `ntdll!RtlNtStatusToDosError` at `0x18005e02e`
- `KERNELBASE!LocalAlloc` at `0x18005df23`
- `KERNELBASE!LocalAlloc` at `0x18005df23`
- `KERNEL32!LocalFree` at `0x18005de54`
- `KERNEL32!LocalFree` at `0x18005de68`
- `KERNEL32!LocalFree` at `0x18005de54`
- `KERNEL32!LocalFree` at `0x18005de68`
- `KERNEL32!SetLastError` at `0x18005de3a`
- `KERNEL32!SetLastError` at `0x18005de3a`

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
0x18005dd80  mov     rax, rsp
0x18005dd83  mov     [rax+18h], rbx
0x18005dd87  mov     [rax+20h], rbp
0x18005dd8b  mov     [rax+10h], edx
0x18005dd8e  push    rsi
0x18005dd8f  push    rdi
0x18005dd90  push    r12
0x18005dd92  push    r13
0x18005dd94  push    r14
0x18005dd96  sub     rsp, 70h
0x18005dd9a  mov     r13, [rsp+98h+ReturnLength]
0x18005dda2  xor     edi, edi
0x18005dda4  mov     [rsp+98h+var_48], 0
0x18005ddac  mov     bl, r9b
0x18005ddaf  mov     qword ptr [rax-40h], 0
0x18005ddb7  mov     r12d, r8d
0x18005ddba  mov     dword ptr [rax+8], 0
0x18005ddc1  mov     r14d, edx
0x18005ddc4  mov     [r13+0], edi
0x18005ddc8  mov     rsi, rcx
0x18005ddcb  mov     qword ptr [rax-38h], 0
0x18005ddd3  test    rcx, rcx
0x18005ddd6  jz      short loc_18005DE33
0x18005ddd8  mov     rbp, [rsp+98h+ConditionStr]
0x18005dde0  test    rbp, rbp
0x18005dde3  jz      short loc_18005DE33
0x18005dde5  lea     eax, [rbx-9]
0x18005dde8  test    al, 0FAh
0x18005ddea  jnz     short loc_18005DE33
0x18005ddec  cmp     bl, 0Eh
0x18005ddef  jz      short loc_18005DE33
0x18005ddf1  mov     rcx, [rsp+98h+pSid]; Sid
0x18005ddf9  call    cs:__imp_RtlValidSid
0x18005de00  nop     dword ptr [rax+rax+00h]
0x18005de05  xor     ecx, ecx
0x18005de07  test    al, al
0x18005de09  jnz     short loc_18005DE12
0x18005de0b  mov     edx, 539h
0x18005de10  jmp     short loc_18005DE38
0x18005de12  cmp     byte ptr [rsi], 4
0x18005de15  ja      loc_18005E053
0x18005de1b  cmp     r14d, 4
0x18005de1f  ja      loc_18005E053
0x18005de25  cmp     bl, 0Dh
0x18005de28  jz      short loc_18005DE90
0x18005de2a  test    r12d, 0FFFFFFE0h
0x18005de31  jz      short loc_18005DE99
0x18005de33  mov     edx, 57h ; 'W'
0x18005de38  mov     ecx, edx; dwErrCode
0x18005de3a  call    cs:__imp_SetLastError
0x18005de41  nop     dword ptr [rax+rax+00h]
0x18005de46  mov     ebx, [rsp+98h+var_48]
0x18005de4a  mov     rcx, [rsp+98h+hMem]; hMem
0x18005de4f  test    rcx, rcx
0x18005de52  jz      short loc_18005DE60
0x18005de54  call    cs:__imp_LocalFree
0x18005de5b  nop     dword ptr [rax+rax+00h]
0x18005de60  test    rdi, rdi
0x18005de63  jz      short loc_18005DE74
0x18005de65  mov     rcx, rdi; hMem
0x18005de68  call    cs:__imp_LocalFree
0x18005de6f  nop     dword ptr [rax+rax+00h]
0x18005de74  lea     r11, [rsp+98h+var_28]
0x18005de79  mov     eax, ebx
0x18005de7b  mov     rbx, [r11+40h]
0x18005de7f  mov     rbp, [r11+48h]
0x18005de83  mov     rsp, r11
0x18005de86  pop     r14
0x18005de88  pop     r13
0x18005de8a  pop     r12
0x18005de8c  pop     rdi
0x18005de8d  pop     rsi
0x18005de8e  retn
0x18005de90  test    r12d, 0FFFFFF20h
0x18005de97  jnz     short loc_18005DE33
0x18005de99  mov     [rsp+98h+var_58], 1
0x18005de9e  lea     r9, [rsp+98h+Size]
0x18005dea6  mov     [rsp+98h+var_60], cl
0x18005deaa  lea     r8, [rsp+98h+hMem]
0x18005deaf  mov     [rsp+98h+var_68], rcx
0x18005deb4  lea     rdx, [rsp+98h+var_38]
0x18005deb9  mov     [rsp+98h+var_70], rcx
0x18005debe  mov     qword ptr [rsp+98h+AceListLength], rcx
0x18005dec3  mov     rcx, rbp
0x18005dec6  call    LocalGetConditionForString
0x18005decb  mov     edx, eax
0x18005decd  test    eax, eax
0x18005decf  jnz     loc_18005DE38
0x18005ded5  mov     eax, dword ptr [rsp+98h+Size]
0x18005dedc  mov     ecx, 0FFFFFFFCh
0x18005dee1  cmp     eax, ecx
0x18005dee3  jbe     short loc_18005DEEF
0x18005dee5  mov     edx, 216h
0x18005deea  jmp     loc_18005DE38
0x18005deef  add     eax, 3
0x18005def2  and     eax, ecx
0x18005def4  lea     ebp, [rax+0Ch]
0x18005def7  cmp     ebp, eax
0x18005def9  jb      short loc_18005DEE5
0x18005defb  mov     rcx, [rsp+98h+pSid]; Sid
0x18005df03  call    cs:__imp_RtlLengthSid
0x18005df0a  nop     dword ptr [rax+rax+00h]
0x18005df0f  lea     r14d, [rbp-4]
0x18005df13  add     r14d, eax
0x18005df16  cmp     r14d, ebp
0x18005df19  jb      short loc_18005DEE5
0x18005df1b  mov     edx, r14d; uBytes
0x18005df1e  mov     ecx, 40h ; '@'; uFlags
0x18005df23  call    cs:__imp_LocalAlloc
0x18005df2a  nop     dword ptr [rax+rax+00h]
0x18005df2f  mov     rdi, rax
0x18005df32  test    rax, rax
0x18005df35  jz      loc_18005E049
0x18005df3b  mov     rcx, [rsp+98h+pSid]; Sid
0x18005df43  mov     [rax], bl
0x18005df45  mov     [rax+1], r12b
0x18005df49  mov     [rax+2], r14w
0x18005df4e  mov     eax, [rsp+98h+AccessMask]
0x18005df55  mov     [rdi+4], eax
0x18005df58  call    cs:__imp_RtlLengthSid
0x18005df5f  nop     dword ptr [rax+rax+00h]
0x18005df64  mov     r8, [rsp+98h+pSid]; SourceSid
0x18005df6c  lea     rdx, [rdi+8]; DestinationSid
0x18005df70  mov     ecx, eax; DestinationSidLength
0x18005df72  call    cs:__imp_RtlCopySid
0x18005df79  nop     dword ptr [rax+rax+00h]
0x18005df7e  mov     eax, dword ptr [rsp+98h+Size]
0x18005df85  test    eax, eax
0x18005df87  jz      short loc_18005DFB5
0x18005df89  mov     rcx, [rsp+98h+pSid]; Sid
0x18005df91  mov     ebx, eax
0x18005df93  call    cs:__imp_RtlLengthSid
0x18005df9a  nop     dword ptr [rax+rax+00h]
0x18005df9f  mov     rdx, [rsp+98h+hMem]; Src
0x18005dfa4  mov     r8d, ebx; Size
0x18005dfa7  mov     ecx, eax
0x18005dfa9  add     rcx, 8
0x18005dfad  add     rcx, rdi; void *
0x18005dfb0  call    memcpy_0
0x18005dfb5  mov     edx, [rsp+98h+AceRevision]; AceRevision
0x18005dfbc  mov     r9, rdi; AceList
0x18005dfbf  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18005dfc3  mov     [rsp+98h+AceListLength], r14d; AceListLength
0x18005dfc8  mov     rcx, rsi; Acl
0x18005dfcb  call    cs:__imp_RtlAddAce
0x18005dfd2  nop     dword ptr [rax+rax+00h]
0x18005dfd7  mov     edx, 8
0x18005dfdc  xor     ecx, ecx
0x18005dfde  mov     [r13+0], edx
0x18005dfe2  mov     r9d, eax
0x18005dfe5  cmp     cx, [rsi+4]
0x18005dfe9  jnb     short loc_18005E00F
0x18005dfeb  xor     r8d, r8d
0x18005dfee  lea     rcx, [rsi+8]
0x18005dff2  movzx   eax, word ptr [rcx+2]
0x18005dff6  inc     r8d
0x18005dff9  add     edx, eax
0x18005dffb  mov     [r13+0], edx
0x18005dfff  movzx   eax, word ptr [rcx+2]
0x18005e003  add     rcx, rax
0x18005e006  movzx   eax, word ptr [rsi+4]
0x18005e00a  cmp     r8d, eax
0x18005e00d  jb      short loc_18005DFF2
0x18005e00f  test    r9d, r9d
0x18005e012  js      short loc_18005E01E
0x18005e014  mov     ebx, 1
0x18005e019  jmp     loc_18005DE4A
0x18005e01e  lea     eax, [r14+3]
0x18005e022  mov     ecx, r9d; Status
0x18005e025  add     eax, edx
0x18005e027  and     eax, 0FFFFFFFCh
0x18005e02a  mov     [r13+0], eax
0x18005e02e  call    cs:__imp_RtlNtStatusToDosError
0x18005e035  nop     dword ptr [rax+rax+00h]
0x18005e03a  mov     edx, eax
0x18005e03c  test    eax, eax
0x18005e03e  jz      loc_18005DE46
0x18005e044  jmp     loc_18005DE38
0x18005e049  mov     edx, 8
0x18005e04e  jmp     loc_18005DE38
0x18005e053  mov     edx, 51Ah
0x18005e058  jmp     loc_18005DE38
```
