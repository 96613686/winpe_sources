# Smb2AdmRegisterFile

- ea: `0x14007cbf0`
- end: `0x14007d053`
- name: `Smb2AdmRegisterFile`
- size: `1123`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14007a84c`

## callees

- `0x140013810`
- `0x140013920`
- `0x140016d30`
- `0x1400224b8`
- `0x14002a410`
- `0x140038490`
- `0x140038980`
- `0x140063bf4`
- `0x140077340`
- `0x14007cbf0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007cf71`
- `ntoskrnl!ExAllocatePool2` at `0x14007cf71`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007cedf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098432`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007cedf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098432`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007ceb9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098412`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007ceb9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098412`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cf36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cfa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cf36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cfa1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007cd23`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007cd23`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14007ccea`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14007ccea`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007cf52`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14007cf52`
- `srvnet!SrvAdminRegisterFile` at `0x14007cdcf`
- `srvnet!SrvAdminRegisterFile` at `0x14007cdcf`

## pseudocode

```c
__int64 __fastcall Smb2AdmRegisterFile(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  volatile signed __int64 *v3; // r12
  int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  int v8; // r8d
  __int64 v9; // rdi
  unsigned int v10; // esi
  PVOID v11; // rbx
  __int64 v12; // rcx
  USHORT Length; // ax
  __int64 v14; // rsi
  bool v15; // cf
  const UNICODE_STRING *v16; // rsi
  unsigned __int16 v17; // dx
  unsigned __int16 v18; // cx
  WCHAR *Pool2; // rax
  char v20; // r10
  char v21; // dl
  signed __int64 v22; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  volatile signed __int64 **v26; // rdi
  volatile signed __int64 *v28; // r14
  volatile signed __int64 *v29; // r15
  signed __int64 v30; // r13
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 *v33; // rax
  struct _ERESOURCE *v34; // rcx
  struct _ERESOURCE *v35; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  _BYTE v40[1024]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = 0;
  v39 = a3;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v37 = 0;
  P = 0;
  v6 = Smb2ReferenceSessionAndTreeConnectFromFile(a1, &v37, &P);
  v9 = v37;
  v10 = v6;
  v11 = P;
  if ( v6 < 0 )
    goto LABEL_18;
  v12 = *(_QWORD *)(a1 + 128);
  Length = a2->Length;
  v14 = 152;
  v15 = *(_WORD *)(v12 + 152) < 6u;
  DestinationString.MaximumLength = 0;
  if ( v15 )
    v14 = 120;
  v16 = (const UNICODE_STRING *)(v12 + v14);
  v17 = v16->Length + Length;
  if ( v17 < Length )
  {
    v10 = -1073741675;
    DestinationString.MaximumLength = -1;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_18;
    }
    v24 = 17;
LABEL_60:
    WPP_SF_d(v7->AttachedDevice, v24, &WPP_026a9657692237905df4630b7666c8cd_Traceguids, 3221225621LL);
    goto LABEL_18;
  }
  v18 = v17 + 2;
  if ( (unsigned __int16)(v17 + 2) < v17 )
  {
    v10 = -1073741675;
    DestinationString.MaximumLength = -1;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_18;
    }
    v24 = 18;
    goto LABEL_60;
  }
  DestinationString.MaximumLength = v17 + 2;
  DestinationString.Length = 0;
  if ( v18 > 0x200u )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, v18, 1647465292);
    DestinationString.Buffer = Pool2;
    LODWORD(v7) = 1;
    if ( Pool2 )
      LODWORD(v3) = 1;
  }
  else
  {
    DestinationString.Buffer = (PWSTR)v40;
    memset(v40, 0, sizeof(v40));
    Pool2 = (WCHAR *)v40;
  }
  if ( Pool2 )
  {
    RtlCopyUnicodeString(&DestinationString, v16);
    if ( !DestinationString.Length
      || DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92 )
    {
      RtlAppendUnicodeToString(&DestinationString, L"\\");
    }
    RtlAppendUnicodeStringToString(&DestinationString, a2);
    if ( *((_BYTE *)v11 + 90) || *(_BYTE *)(v9 + 59) )
    {
      v21 = 1;
      v20 = 0;
    }
    else
    {
      v20 = *(_BYTE *)(v9 + 57);
      v21 = 0;
    }
    v10 = SrvAdminRegisterFile(
            &DestinationString,
            *(unsigned int *)(a1 + 184),
            a1 + 248,
            *(_QWORD *)(v9 + 64),
            *(_DWORD *)(*(_QWORD *)(a1 + 128) + 356LL),
            Smb2ProviderId,
            -1,
            *(_QWORD *)(a1 + 80),
            *(_BYTE *)(v39 + 380),
            *(_BYTE *)(v9 + 285),
            v21,
            v20,
            *(_BYTE *)(v39 + 309),
            a1 + 320,
            **(unsigned __int8 **)(a1 + 64));
    Pool2 = DestinationString.Buffer;
  }
  else
  {
    v10 = -1073741670;
  }
  if ( (_DWORD)v3 == 1 )
    ExFreePoolWithTag(Pool2, 0);
  v3 = 0;
LABEL_18:
  if ( v9 )
    Smb2DereferenceSession(v9);
  if ( v11 )
  {
    v22 = _InterlockedDecrement64((volatile signed __int64 *)v11);
    if ( v22 == -1 )
    {
      __int2c();
    }
    else if ( !v22 )
    {
      if ( (byte_14004C339 & 1) != 0 )
      {
        v32 = *((_QWORD *)v11 + 14);
        if ( v32 )
          v33 = (__int64 *)(v32 + 72);
        else
          v33 = &Srv2ZeroGuid;
        McTemplateK0jj_EtwWriteTransfer(
          (_DWORD)v7,
          (unsigned int)&SMB2_EVENT_TREECONNECT_TERMINATE,
          v8,
          (_DWORD)v11 + 24,
          (__int64)v33);
      }
      v25 = *((_QWORD *)v11 + 14);
      if ( v25 )
        Smb2DereferenceSession(v25);
      v26 = (volatile signed __int64 **)*((_QWORD *)v11 + 12);
      if ( v26 )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(*v26 + 12), 1u);
        if ( (*((_DWORD *)v26 + 50))-- == 1 )
        {
          v3 = v26[40];
          v34 = (struct _ERESOURCE *)(*v26 + 25);
          v29 = v26[39];
          v28 = v26[41];
          v26[40] = 0;
          v26[39] = 0;
          v26[41] = 0;
          ExAcquireResourceExclusiveLite(v34, 1u);
          v35 = (struct _ERESOURCE *)(*v26 + 25);
          *((_DWORD *)v26 + 88) = 0;
          ExReleaseResourceLite(v35);
        }
        else
        {
          v28 = 0;
          v29 = 0;
        }
        ExReleaseResourceLite((PERESOURCE)(*v26 + 12));
        v30 = _InterlockedDecrement64(*v26);
        if ( v30 == -1 )
        {
          __int2c();
        }
        else if ( !v30 )
        {
          Smb2FreeShare((char *)v26);
        }
        if ( v3 )
          Smb2DereferenceHandle((PVOID)v3);
        if ( v29 )
          Smb2DereferenceHandle((PVOID)v29);
        if ( v28 )
          Smb2DereferenceHandle((PVOID)v28);
      }
      v31 = *((_QWORD *)v11 + 15);
      if ( v31 )
        Smb2DereferenceSecurityContext(v31);
      ExFreePoolWithTag(v11, 0);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x14007cbf0  mov     [rsp-8+arg_18], rbx
0x14007cbf5  push    rbp
0x14007cbf6  push    rsi
0x14007cbf7  push    rdi
0x14007cbf8  push    r12
0x14007cbfa  push    r13
0x14007cbfc  push    r14
0x14007cbfe  push    r15
0x14007cc00  lea     rbp, [rsp-3C0h]
0x14007cc08  sub     rsp, 4C0h
0x14007cc0f  mov     rax, cs:__security_cookie
0x14007cc16  xor     rax, rsp
0x14007cc19  mov     [rbp+3F0h+var_40], rax
0x14007cc20  xor     r12d, r12d
0x14007cc23  mov     [rbp+3F0h+var_450], r8
0x14007cc27  mov     r15, rdx
0x14007cc2a  mov     qword ptr [rbp+3F0h+DestinationString.Length], r12
0x14007cc2e  lea     r8, [rbp+3F0h+P]
0x14007cc32  mov     [rbp+3F0h+DestinationString.Buffer], r12
0x14007cc36  lea     rdx, [rbp+3F0h+var_460]
0x14007cc3a  mov     [rbp+3F0h+var_460], r12
0x14007cc3e  mov     [rbp+3F0h+P], r12
0x14007cc42  mov     r14, rcx
0x14007cc45  call    Smb2ReferenceSessionAndTreeConnectFromFile
0x14007cc4a  mov     rdi, [rbp+3F0h+var_460]
0x14007cc4e  mov     esi, eax
0x14007cc50  mov     rbx, [rbp+3F0h+P]
0x14007cc54  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14007cc5b  test    eax, eax
0x14007cc5d  js      loc_14007CDEE
0x14007cc63  mov     rcx, [r14+80h]
0x14007cc6a  mov     edx, 78h ; 'x'
0x14007cc6f  movzx   eax, word ptr [r15]
0x14007cc73  mov     esi, 98h
0x14007cc78  cmp     word ptr [rcx+98h], 6
0x14007cc80  mov     [rbp+3F0h+DestinationString.MaximumLength], r12w
0x14007cc85  cmovb   esi, edx
0x14007cc88  movzx   edx, ax
0x14007cc8b  add     rsi, rcx
0x14007cc8e  add     dx, [rsi]
0x14007cc91  cmp     dx, ax
0x14007cc94  jb      loc_14007CE46
0x14007cc9a  lea     ecx, [rdx+2]
0x14007cc9d  cmp     cx, dx
0x14007cca0  jb      loc_14007CFB2
0x14007cca6  mov     eax, 200h
0x14007ccab  mov     [rbp+3F0h+DestinationString.MaximumLength], cx
0x14007ccaf  mov     [rbp+3F0h+DestinationString.Length], r12w
0x14007ccb4  cmp     cx, ax
0x14007ccb7  ja      loc_14007CF63
0x14007ccbd  lea     rax, [rbp+3F0h+var_440]
0x14007ccc1  xor     edx, edx; Val
0x14007ccc3  mov     r8d, 400h; Size
0x14007ccc9  mov     [rbp+3F0h+DestinationString.Buffer], rax
0x14007cccd  lea     rcx, [rbp+3F0h+var_440]; void *
0x14007ccd1  call    memset
0x14007ccd6  mov     rax, [rbp+3F0h+DestinationString.Buffer]
0x14007ccda  test    rax, rax
0x14007ccdd  jz      loc_14007CF92
0x14007cce3  mov     rdx, rsi; SourceString
0x14007cce6  lea     rcx, [rbp+3F0h+DestinationString]; DestinationString
0x14007ccea  call    cs:__imp_RtlCopyUnicodeString
0x14007ccf1  nop     dword ptr [rax+rax+00h]
0x14007ccf6  movzx   ecx, [rbp+3F0h+DestinationString.Length]
0x14007ccfa  xor     eax, eax
0x14007ccfc  cmp     ax, cx
0x14007ccff  jz      loc_14007CF47
0x14007cd05  mov     rax, [rbp+3F0h+DestinationString.Buffer]
0x14007cd09  mov     edx, 5Ch ; '\'
0x14007cd0e  shr     rcx, 1
0x14007cd11  cmp     dx, [rax+rcx*2-2]
0x14007cd16  jnz     loc_14007CF47
0x14007cd1c  mov     rdx, r15; Source
0x14007cd1f  lea     rcx, [rbp+3F0h+DestinationString]; Destination
0x14007cd23  call    cs:__imp_RtlAppendUnicodeStringToString
0x14007cd2a  nop     dword ptr [rax+rax+00h]
0x14007cd2f  cmp     byte ptr [rbx+5Ah], 0
0x14007cd33  jnz     loc_14007CE82
0x14007cd39  cmp     byte ptr [rdi+3Bh], 0
0x14007cd3d  jnz     loc_14007CE82
0x14007cd43  movzx   r10d, byte ptr [rdi+39h]
0x14007cd48  xor     dl, dl
0x14007cd4a  mov     rax, [r14+40h]
0x14007cd4e  lea     r8, [r14+0F8h]
0x14007cd55  mov     r9, [r14+80h]
0x14007cd5c  movzx   ecx, byte ptr [rax]
0x14007cd5f  lea     rax, [r14+140h]
0x14007cd66  mov     [rsp+4F0h+var_480], ecx
0x14007cd6a  mov     rcx, [rbp+3F0h+var_450]
0x14007cd6e  mov     [rsp+4F0h+var_488], rax
0x14007cd73  movzx   eax, byte ptr [rcx+135h]
0x14007cd7a  mov     [rsp+4F0h+var_490], al
0x14007cd7e  movzx   eax, byte ptr [rdi+11Dh]
0x14007cd85  mov     [rsp+4F0h+var_498], r10b
0x14007cd8a  mov     [rsp+4F0h+var_4A0], dl
0x14007cd8e  mov     edx, [r14+0B8h]
0x14007cd95  mov     [rsp+4F0h+var_4A8], al
0x14007cd99  movzx   eax, byte ptr [rcx+17Ch]
0x14007cda0  lea     rcx, [rbp+3F0h+DestinationString]
0x14007cda4  mov     [rsp+4F0h+var_4B0], al
0x14007cda8  mov     rax, [r14+50h]
0x14007cdac  mov     [rsp+4F0h+var_4B8], rax
0x14007cdb1  mov     eax, cs:Smb2ProviderId
0x14007cdb7  mov     [rsp+4F0h+var_4C0], r13
0x14007cdbc  mov     [rsp+4F0h+var_4C8], eax
0x14007cdc0  mov     eax, [r9+164h]
0x14007cdc7  mov     r9, [rdi+40h]
0x14007cdcb  mov     dword ptr [rsp+4F0h+var_4D0], eax
0x14007cdcf  call    cs:__imp_SrvAdminRegisterFile
0x14007cdd6  nop     dword ptr [rax+rax+00h]
0x14007cddb  mov     esi, eax
0x14007cddd  mov     rax, [rbp+3F0h+DestinationString.Buffer]
0x14007cde1  cmp     r12d, 1
0x14007cde5  jz      loc_14007CF9C
0x14007cdeb  xor     r12d, r12d
0x14007cdee  test    rdi, rdi
0x14007cdf1  jz      short loc_14007CDFB
0x14007cdf3  mov     rcx, rdi
0x14007cdf6  call    Smb2DereferenceSession
0x14007cdfb  test    rbx, rbx
0x14007cdfe  jz      short loc_14007CE19
0x14007ce00  mov     rax, r13
0x14007ce03  lock xadd [rbx], rax
0x14007ce08  dec     rax
0x14007ce0b  cmp     rax, r13
0x14007ce0e  jnb     loc_14007CFF1
0x14007ce14  test    rax, rax
0x14007ce17  jz      short loc_14007CE8C
0x14007ce19  mov     eax, esi
0x14007ce1b  mov     rcx, [rbp+3F0h+var_40]
0x14007ce22  xor     rcx, rsp; StackCookie
0x14007ce25  call    __security_check_cookie
0x14007ce2a  mov     rbx, [rsp+4F0h+arg_18]
0x14007ce32  add     rsp, 4C0h
0x14007ce39  pop     r15
0x14007ce3b  pop     r14
0x14007ce3d  pop     r13
0x14007ce3f  pop     r12
0x14007ce41  pop     rdi
0x14007ce42  pop     rsi
0x14007ce43  pop     rbp
0x14007ce44  retn
0x14007ce46  mov     eax, 0FFFFh
0x14007ce4b  mov     esi, 0C0000095h
0x14007ce50  mov     [rbp+3F0h+DestinationString.MaximumLength], ax
0x14007ce54  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ce5b  lea     rax, WPP_GLOBAL_Control
0x14007ce62  cmp     rcx, rax
0x14007ce65  jz      short loc_14007CDEE
0x14007ce67  mov     eax, [rcx+2Ch]
0x14007ce6a  test    al, 1
0x14007ce6c  jz      short loc_14007CDEE
0x14007ce6e  cmp     byte ptr [rcx+29h], 1
0x14007ce72  jb      loc_14007CDEE
0x14007ce78  mov     edx, 11h
0x14007ce7d  jmp     loc_140098395
0x14007ce82  mov     dl, 1
0x14007ce84  xor     r10b, r10b
0x14007ce87  jmp     loc_14007CD4A
0x14007ce8c  test    cs:byte_14004C339, 1
0x14007ce93  jnz     loc_14007CFF8
0x14007ce99  mov     rcx, [rbx+70h]
0x14007ce9d  test    rcx, rcx
0x14007cea0  jz      short loc_14007CEA7
0x14007cea2  call    Smb2DereferenceSession
0x14007cea7  mov     rdi, [rbx+60h]
0x14007ceab  test    rdi, rdi
0x14007ceae  jz      short loc_14007CF24
0x14007ceb0  mov     rcx, [rdi]
0x14007ceb3  mov     dl, 1; Wait
0x14007ceb5  add     rcx, 60h ; '`'; Resource
0x14007ceb9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14007cec0  nop     dword ptr [rax+rax+00h]
0x14007cec5  add     dword ptr [rdi+0C8h], 0FFFFFFFFh
0x14007cecc  jz      loc_1400983D0
0x14007ced2  xor     r14d, r14d
0x14007ced5  xor     r15d, r15d
0x14007ced8  mov     rcx, [rdi]
0x14007cedb  add     rcx, 60h ; '`'; Resource
0x14007cedf  call    cs:__imp_ExReleaseResourceLite
0x14007cee6  nop     dword ptr [rax+rax+00h]
0x14007ceeb  mov     rax, [rdi]
0x14007ceee  lock xadd [rax], r13
0x14007cef3  dec     r13
0x14007cef6  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x14007cefa  jnb     loc_14007D00E
0x14007cf00  test    r13, r13
0x14007cf03  jz      loc_14007D015
0x14007cf09  test    r12, r12
0x14007cf0c  jnz     loc_14007D022
0x14007cf12  test    r15, r15
0x14007cf15  jnz     loc_14007D02F
0x14007cf1b  test    r14, r14
0x14007cf1e  jnz     loc_14007D03C
0x14007cf24  mov     rcx, [rbx+78h]
0x14007cf28  test    rcx, rcx
0x14007cf2b  jnz     loc_14007D049
0x14007cf31  xor     edx, edx; Tag
0x14007cf33  mov     rcx, rbx; P
0x14007cf36  call    cs:__imp_ExFreePoolWithTag
0x14007cf3d  nop     dword ptr [rax+rax+00h]
0x14007cf42  jmp     loc_14007CE19
0x14007cf47  lea     rdx, Source; "\\"
0x14007cf4e  lea     rcx, [rbp+3F0h+DestinationString]; Destination
0x14007cf52  call    cs:__imp_RtlAppendUnicodeToString
0x14007cf59  nop     dword ptr [rax+rax+00h]
0x14007cf5e  jmp     loc_14007CD1C
0x14007cf63  movzx   edx, cx
0x14007cf66  mov     r8d, 6232534Ch
0x14007cf6c  mov     ecx, 100h
0x14007cf71  call    cs:__imp_ExAllocatePool2
0x14007cf78  nop     dword ptr [rax+rax+00h]
0x14007cf7d  test    rax, rax
0x14007cf80  mov     [rbp+3F0h+DestinationString.Buffer], rax
0x14007cf84  mov     ecx, 1
0x14007cf89  cmovnz  r12d, ecx
0x14007cf8d  jmp     loc_14007CCDA
0x14007cf92  mov     esi, 0C000009Ah
0x14007cf97  jmp     loc_14007CDE1
0x14007cf9c  xor     edx, edx; Tag
0x14007cf9e  mov     rcx, rax; P
0x14007cfa1  call    cs:__imp_ExFreePoolWithTag
0x14007cfa8  nop     dword ptr [rax+rax+00h]
0x14007cfad  jmp     loc_14007CDEB
0x14007cfb2  mov     eax, 0FFFFh
0x14007cfb7  mov     esi, 0C0000095h
0x14007cfbc  mov     [rbp+3F0h+DestinationString.MaximumLength], ax
0x14007cfc0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cfc7  lea     rax, WPP_GLOBAL_Control
0x14007cfce  cmp     rcx, rax
0x14007cfd1  jz      loc_14007CDEE
0x14007cfd7  mov     eax, [rcx+2Ch]
0x14007cfda  test    al, 1
0x14007cfdc  jz      loc_14007CDEE
0x14007cfe2  cmp     byte ptr [rcx+29h], 1
0x14007cfe6  jb      loc_14007CDEE
0x14007cfec  jmp     loc_140098390
0x14007cff1  int     2Ch; Windows NT - assertion failure
0x14007cff3  jmp     loc_14007CE19
0x14007cff8  mov     rax, [rbx+70h]
0x14007cffc  test    rax, rax
0x14007cfff  jz      loc_1400983AE
0x14007d005  add     rax, 48h ; 'H'
0x14007d009  jmp     loc_1400983B5
0x14007d00e  int     2Ch; Windows NT - assertion failure
0x14007d010  jmp     loc_14007CF09
0x14007d015  mov     rcx, rdi; P
0x14007d018  call    Smb2FreeShare
0x14007d01d  jmp     loc_14007CF09
0x14007d022  mov     rcx, r12; P
0x14007d025  call    Smb2DereferenceHandle
0x14007d02a  jmp     loc_14007CF12
0x14007d02f  mov     rcx, r15; P
0x14007d032  call    Smb2DereferenceHandle
0x14007d037  jmp     loc_14007CF1B
0x14007d03c  mov     rcx, r14; P
0x14007d03f  call    Smb2DereferenceHandle
0x14007d044  jmp     loc_14007CF24
0x14007d049  call    Smb2DereferenceSecurityContext
0x14007d04e  jmp     loc_14007CF31
0x140098390  mov     edx, 12h
0x140098395  mov     rcx, [rcx+18h]
0x140098399  lea     r8, WPP_026a9657692237905df4630b7666c8cd_Traceguids
0x1400983a0  mov     r9d, esi
0x1400983a3  call    WPP_SF_d
0x1400983a8  nop
0x1400983a9  jmp     loc_14007CDEE
0x1400983ae  lea     rax, Srv2ZeroGuid
0x1400983b5  lea     r9, [rbx+18h]
0x1400983b9  mov     [rsp+4F0h+var_4D0], rax
0x1400983be  lea     rdx, SMB2_EVENT_TREECONNECT_TERMINATE
0x1400983c5  call    McTemplateK0jj_EtwWriteTransfer
0x1400983ca  nop
0x1400983cb  jmp     loc_14007CE99
0x1400983d0  mov     rcx, [rdi]
0x1400983d3  mov     dl, 1; Wait
0x1400983d5  mov     r12, [rdi+140h]
0x1400983dc  add     rcx, 0C8h; Resource
0x1400983e3  mov     r15, [rdi+138h]
0x1400983ea  mov     r14, [rdi+148h]
0x1400983f1  mov     qword ptr [rdi+140h], 0
0x1400983fc  mov     qword ptr [rdi+138h], 0
0x140098407  mov     qword ptr [rdi+148h], 0
0x140098412  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140098419  nop     dword ptr [rax+rax+00h]
0x14009841e  mov     rcx, [rdi]
0x140098421  add     rcx, 0C8h; Resource
0x140098428  mov     dword ptr [rdi+160h], 0
0x140098432  call    cs:__imp_ExReleaseResourceLite
0x140098439  nop     dword ptr [rax+rax+00h]
0x14009843e  nop
0x14009843f  jmp     loc_14007CED8
```
