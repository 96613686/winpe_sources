# BfsCheckPolicyAndPerformRenameAsUser

- ea: `0x140005d4c`
- end: `0x140006037`
- name: `BfsCheckPolicyAndPerformRenameAsUser`
- size: `747`
- prototype: `__int64 __fastcall(PVOID FltObject, PVOID, PACCESS_TOKEN Token, PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000411c`

## callees

- `0x140001008`
- `0x140005d4c`
- `0x140006040`
- `0x140006af4`
- `0x140006e14`
- `0x140007044`
- `0x140008e84`
- `0x14000ff3c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006008`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006008`
- `ntoskrnl!SeQueryInformationToken` at `0x140005db6`
- `ntoskrnl!SeQueryInformationToken` at `0x140005e10`
- `ntoskrnl!SeQueryInformationToken` at `0x140005db6`
- `ntoskrnl!SeQueryInformationToken` at `0x140005e10`
- `FLTMGR!FltGetFileNameInformation` at `0x140005f42`
- `FLTMGR!FltGetFileNameInformation` at `0x140005f42`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140005fda`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140005fda`
- `FLTMGR!FltParseFileNameInformation` at `0x140005f5c`
- `FLTMGR!FltParseFileNameInformation` at `0x140005f5c`

## pseudocode

```c
__int64 __fastcall BfsCheckPolicyAndPerformRenameAsUser(
        PVOID FltObject,
        PVOID a2,
        PACCESS_TOKEN Token,
        PFLT_CALLBACK_DATA Data,
        __int64 a5)
{
  unsigned int v7; // edi
  NTSTATUS v10; // ecx
  int v11; // r8d
  int v12; // r9d
  _QWORD *v13; // rbx
  NTSTATUS PolicyEntry; // ecx
  int v15; // r8d
  int v16; // r9d
  __m128i v17; // xmm1
  unsigned __int16 v18; // ax
  char *i; // rcx
  NTSTATUS v20; // eax
  int v22; // [rsp+20h] [rbp-91h]
  PSID v23; // [rsp+20h] [rbp-91h]
  _BYTE v24[8]; // [rsp+30h] [rbp-81h] BYREF
  PVOID v25[2]; // [rsp+38h] [rbp-79h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-69h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-61h] BYREF
  PVOID P; // [rsp+58h] [rbp-59h] BYREF
  __int128 v29; // [rsp+60h] [rbp-51h]
  __int128 v30; // [rsp+70h] [rbp-41h]
  __int64 v31; // [rsp+80h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+88h] [rbp-29h] BYREF
  PVOID *v33; // [rsp+A8h] [rbp-9h]
  __int64 v34; // [rsp+B0h] [rbp-1h]

  TokenInformation = 0;
  v31 = 0;
  v25[0] = 0;
  P = 0;
  v7 = 1;
  FileNameInformation = 0;
  v24[0] = 0;
  v29 = 0;
  v30 = 0;
  v10 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( v10 < 0 || (v10 = SeQueryInformationToken(Token, TokenAppContainerSid, &P), v10 < 0) )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v25[0]) = v10;
      v33 = v25;
      v34 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v11, v12, v22, &v32);
    }
  }
  else
  {
    if ( !BfsPolicyEntryExists(
            (int)FltObject,
            (int)a2,
            (__int64)&gBfsPolicyTable,
            *(void **)TokenInformation,
            *(PSID *)P) )
      goto LABEL_22;
    v23 = *(PSID *)P;
    v13 = v25[0];
    PolicyEntry = BfsGetPolicyEntry(FltObject, a2, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
    if ( PolicyEntry < 0 )
      goto LABEL_7;
    v17 = *(__m128i *)BfsGetFileName(v25, a5);
    v18 = _mm_cvtsi128_si32(v17);
    *(__m128i *)v25 = v17;
    if ( v18 )
    {
      for ( i = (char *)v25[1] + 2 * ((unsigned __int64)v18 >> 1) - 2; i > v25[1]; i -= 2 )
      {
        if ( *(_WORD *)i == 92 )
          goto LABEL_15;
      }
      if ( *(_WORD *)i != 92 )
        goto LABEL_16;
LABEL_15:
      LOWORD(v25[0]) = 2 * ((i - (char *)v25[1]) >> 1);
      WORD1(v25[0]) = v25[0];
    }
LABEL_16:
    if ( (unsigned int)BfsGetPolicy(v13[6], a5 + 24, v25, v24) == 1 )
    {
      PolicyEntry = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
      if ( PolicyEntry < 0 || (PolicyEntry = FltParseFileNameInformation(FileNameInformation), PolicyEntry < 0) )
      {
LABEL_7:
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v25[0]) = PolicyEntry;
          v33 = v25;
          v34 = 4;
          tlgWriteTransfer_EtwWriteTransfer(PolicyEntry, (int)&byte_140016D91, v15, v16, (int)v23, &v32);
        }
        goto LABEL_22;
      }
      *((_QWORD *)&v29 + 1) = FileNameInformation;
      BYTE4(v31) = v24[0];
      *(_QWORD *)&v29 = Token;
      *(_QWORD *)&v30 = a5;
      *((_QWORD *)&v30 + 1) = v13;
      LODWORD(v31) = 0;
      v20 = BfsQueueDeferredWorkItemAndWait(FltObject, a2, Data, (__int64)&BfsRenameAsUserCallback);
      Data->IoStatus.Information = 0;
      v7 = 4;
      if ( v20 >= 0 )
        v20 = v31;
      Data->IoStatus.Status = v20;
    }
  }
LABEL_22:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return v7;
}

```

## disassembly

```asm
0x140005d4c  push    rbp
0x140005d4e  push    rbx
0x140005d4f  push    rsi
0x140005d50  push    rdi
0x140005d51  push    r12
0x140005d53  push    r13
0x140005d55  push    r14
0x140005d57  push    r15
0x140005d59  lea     rbp, [rsp-17h]
0x140005d5e  sub     rsp, 0C8h
0x140005d65  mov     rax, cs:__security_cookie
0x140005d6c  xor     rax, rsp
0x140005d6f  mov     [rbp+4Fh+var_48], rax
0x140005d73  mov     r14, [rbp+4Fh+arg_20]
0x140005d77  xor     ebx, ebx
0x140005d79  xor     eax, eax
0x140005d7b  mov     [rbp+4Fh+TokenInformation], rbx
0x140005d7f  mov     r13, r8
0x140005d82  mov     [rbp+4Fh+var_80], rax
0x140005d86  xorps   xmm0, xmm0
0x140005d89  mov     [rbp+4Fh+var_C8], rbx
0x140005d8d  mov     r12, rdx
0x140005d90  mov     [rbp+4Fh+P], rbx
0x140005d94  lea     edi, [rax+1]
0x140005d97  mov     [rbp+4Fh+FileNameInformation], rbx
0x140005d9b  mov     r15, rcx
0x140005d9e  mov     [rsp+100h+var_D0], bl
0x140005da2  mov     edx, edi; TokenInformationClass
0x140005da4  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x140005da8  mov     rcx, r13; Token
0x140005dab  mov     rsi, r9
0x140005dae  movups  [rbp+4Fh+var_A0], xmm0
0x140005db2  movups  [rbp+4Fh+var_90], xmm0
0x140005db6  call    cs:__imp_SeQueryInformationToken
0x140005dbd  nop     dword ptr [rax+rax+00h]
0x140005dc2  mov     ecx, eax; int
0x140005dc4  test    eax, eax
0x140005dc6  jns     short loc_140005E04
0x140005dc8  mov     eax, cs:dword_140019000
0x140005dce  cmp     eax, 3
0x140005dd1  jbe     loc_140005FD1
0x140005dd7  lea     rax, [rbp+4Fh+var_C8]
0x140005ddb  mov     dword ptr [rbp+4Fh+var_C8], ecx
0x140005dde  mov     [rbp+4Fh+var_58], rax
0x140005de2  lea     rdx, byte_140016D91; int
0x140005de9  lea     rax, [rbp+4Fh+var_78]
0x140005ded  mov     [rbp+4Fh+var_50], 4
0x140005df5  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005dfa  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005dff  jmp     loc_140005FD1
0x140005e04  lea     r8, [rbp+4Fh+P]; TokenInformation
0x140005e08  mov     edx, 1Fh; TokenInformationClass
0x140005e0d  mov     rcx, r13; Token
0x140005e10  call    cs:__imp_SeQueryInformationToken
0x140005e17  nop     dword ptr [rax+rax+00h]
0x140005e1c  mov     ecx, eax
0x140005e1e  test    eax, eax
0x140005e20  js      short loc_140005DC8
0x140005e22  mov     rax, [rbp+4Fh+P]
0x140005e26  lea     r8, gBfsPolicyTable
0x140005e2d  mov     r9, [rbp+4Fh+TokenInformation]
0x140005e31  mov     rdx, r12
0x140005e34  mov     rcx, [rax]
0x140005e37  mov     r9, [r9]
0x140005e3a  mov     [rsp+100h+var_E0], rcx
0x140005e3f  mov     rcx, r15
0x140005e42  call    BfsPolicyEntryExists
0x140005e47  test    al, al
0x140005e49  jz      loc_140005FD1
0x140005e4f  mov     r9, [rbp+4Fh+TokenInformation]
0x140005e53  lea     rax, [rbp+4Fh+var_C8]
0x140005e57  mov     [rsp+100h+var_D8], rax
0x140005e5c  lea     r8, gBfsPolicyTable
0x140005e63  mov     rax, [rbp+4Fh+P]
0x140005e67  mov     rdx, r12
0x140005e6a  mov     r9, [r9]
0x140005e6d  mov     rcx, [rax]
0x140005e70  mov     [rsp+100h+var_E0], rcx; int
0x140005e75  mov     rcx, r15
0x140005e78  call    BfsGetPolicyEntry
0x140005e7d  mov     rbx, [rbp+4Fh+var_C8]
0x140005e81  mov     ecx, eax; int
0x140005e83  test    eax, eax
0x140005e85  jns     short loc_140005EC3
0x140005e87  mov     eax, cs:dword_140019000
0x140005e8d  cmp     eax, 3
0x140005e90  jbe     loc_140005FC2
0x140005e96  lea     rax, [rbp+4Fh+var_C8]
0x140005e9a  mov     dword ptr [rbp+4Fh+var_C8], ecx
0x140005e9d  mov     [rbp+4Fh+var_58], rax
0x140005ea1  lea     rdx, byte_140016D91; int
0x140005ea8  lea     rax, [rbp+4Fh+var_78]
0x140005eac  mov     [rbp+4Fh+var_50], 4
0x140005eb4  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005eb9  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005ebe  jmp     loc_140005FC2
0x140005ec3  mov     rdx, r14
0x140005ec6  lea     rcx, [rbp+4Fh+var_C8]
0x140005eca  call    BfsGetFileName
0x140005ecf  movups  xmm1, xmmword ptr [rax]
0x140005ed2  movd    eax, xmm1
0x140005ed6  movups  xmmword ptr [rbp+4Fh+var_C8], xmm1
0x140005eda  test    ax, ax
0x140005edd  jz      short loc_140005F18
0x140005edf  mov     rdx, [rbp+4Fh+var_C8+8]
0x140005ee3  movzx   ecx, ax
0x140005ee6  shr     rcx, 1
0x140005ee9  dec     rcx
0x140005eec  lea     rcx, [rdx+rcx*2]
0x140005ef0  jmp     short loc_140005EFC
0x140005ef2  cmp     word ptr [rcx], 5Ch ; '\'
0x140005ef6  jz      short loc_140005F07
0x140005ef8  sub     rcx, 2
0x140005efc  cmp     rcx, rdx
0x140005eff  ja      short loc_140005EF2
0x140005f01  cmp     word ptr [rcx], 5Ch ; '\'
0x140005f05  jnz     short loc_140005F18
0x140005f07  sub     rcx, rdx
0x140005f0a  sar     rcx, 1
0x140005f0d  add     cx, cx
0x140005f10  mov     word ptr [rbp+4Fh+var_C8], cx
0x140005f14  mov     word ptr [rbp+4Fh+var_C8+2], cx
0x140005f18  mov     rcx, [rbx+30h]
0x140005f1c  lea     rdx, [r14+18h]
0x140005f20  lea     r9, [rsp+100h+var_D0]
0x140005f25  lea     r8, [rbp+4Fh+var_C8]
0x140005f29  call    BfsGetPolicy
0x140005f2e  cmp     eax, edi
0x140005f30  jnz     loc_140005FC2
0x140005f36  lea     r8, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x140005f3a  mov     edx, 101h; NameOptions
0x140005f3f  mov     rcx, rsi; CallbackData
0x140005f42  call    cs:__imp_FltGetFileNameInformation
0x140005f49  nop     dword ptr [rax+rax+00h]
0x140005f4e  mov     ecx, eax
0x140005f50  test    eax, eax
0x140005f52  js      loc_140005E87
0x140005f58  mov     rcx, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x140005f5c  call    cs:__imp_FltParseFileNameInformation
0x140005f63  nop     dword ptr [rax+rax+00h]
0x140005f68  mov     ecx, eax
0x140005f6a  test    eax, eax
0x140005f6c  js      loc_140005E87
0x140005f72  mov     rax, [rbp+4Fh+FileNameInformation]
0x140005f76  lea     r9, [rbp+4Fh+var_A0]
0x140005f7a  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x140005f7e  xor     edi, edi
0x140005f80  mov     al, [rsp+100h+var_D0]
0x140005f84  mov     r8, rsi; Data
0x140005f87  mov     byte ptr [rbp+4Fh+var_80+4], al
0x140005f8a  mov     rdx, r12; PVOID
0x140005f8d  lea     rax, BfsRenameAsUserCallback
0x140005f94  mov     qword ptr [rbp+4Fh+var_A0], r13
0x140005f98  mov     rcx, r15; FltObject
0x140005f9b  mov     [rsp+100h+var_E0], rax; __int64
0x140005fa0  mov     qword ptr [rbp+4Fh+var_90], r14
0x140005fa4  mov     qword ptr [rbp+4Fh+var_90+8], rbx
0x140005fa8  mov     dword ptr [rbp+4Fh+var_80], edi
0x140005fab  call    BfsQueueDeferredWorkItemAndWait
0x140005fb0  test    eax, eax
0x140005fb2  mov     [rsi+20h], rdi
0x140005fb6  mov     edi, 4
0x140005fbb  cmovns  eax, dword ptr [rbp+4Fh+var_80]
0x140005fbf  mov     [rsi+18h], eax
0x140005fc2  test    rbx, rbx
0x140005fc5  jz      short loc_140005FD1
0x140005fc7  xor     edx, edx
0x140005fc9  mov     rcx, rbx; P
0x140005fcc  call    BfsDereferencePolicyEntryEx
0x140005fd1  mov     rcx, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x140005fd5  test    rcx, rcx
0x140005fd8  jz      short loc_140005FE6
0x140005fda  call    cs:__imp_FltReleaseFileNameInformation
0x140005fe1  nop     dword ptr [rax+rax+00h]
0x140005fe6  mov     rcx, [rbp+4Fh+TokenInformation]; P
0x140005fea  test    rcx, rcx
0x140005fed  jz      short loc_140005FFD
0x140005fef  xor     edx, edx; Tag
0x140005ff1  call    cs:__imp_ExFreePoolWithTag
0x140005ff8  nop     dword ptr [rax+rax+00h]
0x140005ffd  mov     rcx, [rbp+4Fh+P]; P
0x140006001  test    rcx, rcx
0x140006004  jz      short loc_140006014
0x140006006  xor     edx, edx; Tag
0x140006008  call    cs:__imp_ExFreePoolWithTag
0x14000600f  nop     dword ptr [rax+rax+00h]
0x140006014  mov     eax, edi
0x140006016  mov     rcx, [rbp+4Fh+var_48]
0x14000601a  xor     rcx, rsp; StackCookie
0x14000601d  call    __security_check_cookie
0x140006022  add     rsp, 0C8h
0x140006029  pop     r15
0x14000602b  pop     r14
0x14000602d  pop     r13
0x14000602f  pop     r12
0x140006031  pop     rdi
0x140006032  pop     rsi
0x140006033  pop     rbx
0x140006034  pop     rbp
0x140006035  retn
```
