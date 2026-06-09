# BfsCheckPolicyAndPerformRenameAsUser

- ea: `0x140005edc`
- end: `0x1400061c7`
- name: `BfsCheckPolicyAndPerformRenameAsUser`
- size: `747`
- prototype: `__int64 __fastcall(PVOID FltObject, PVOID, PACCESS_TOKEN Token, PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000424c`

## callees

- `0x140001008`
- `0x140005edc`
- `0x1400061d0`
- `0x140006c84`
- `0x140006fa4`
- `0x1400071d4`
- `0x140009014`
- `0x1400100e0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006181`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006198`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006181`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006198`
- `ntoskrnl!SeQueryInformationToken` at `0x140005f46`
- `ntoskrnl!SeQueryInformationToken` at `0x140005fa0`
- `ntoskrnl!SeQueryInformationToken` at `0x140005f46`
- `ntoskrnl!SeQueryInformationToken` at `0x140005fa0`
- `FLTMGR!FltGetFileNameInformation` at `0x1400060d2`
- `FLTMGR!FltGetFileNameInformation` at `0x1400060d2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000616a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000616a`
- `FLTMGR!FltParseFileNameInformation` at `0x1400060ec`
- `FLTMGR!FltParseFileNameInformation` at `0x1400060ec`

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
  int PolicyEntry; // eax
  int v14; // r8d
  int v15; // r9d
  char *v16; // rbx
  NTSTATUS v17; // ecx
  __m128i v18; // xmm1
  unsigned __int16 v19; // ax
  char *i; // rcx
  NTSTATUS v21; // eax
  int v23; // [rsp+20h] [rbp-91h]
  int v24; // [rsp+20h] [rbp-91h]
  char v25[8]; // [rsp+30h] [rbp-81h] BYREF
  PVOID v26[2]; // [rsp+38h] [rbp-79h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-69h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-61h] BYREF
  PVOID P; // [rsp+58h] [rbp-59h] BYREF
  __int128 v30; // [rsp+60h] [rbp-51h]
  __int128 v31; // [rsp+70h] [rbp-41h]
  __int64 v32; // [rsp+80h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+88h] [rbp-29h] BYREF
  PVOID *v34; // [rsp+A8h] [rbp-9h]
  __int64 v35; // [rsp+B0h] [rbp-1h]

  TokenInformation = 0;
  v32 = 0;
  v26[0] = 0;
  P = 0;
  v7 = 1;
  FileNameInformation = 0;
  v25[0] = 0;
  v30 = 0;
  v31 = 0;
  v10 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( v10 >= 0 )
  {
    v10 = SeQueryInformationToken(Token, TokenAppContainerSid, &P);
    if ( v10 >= 0 )
    {
      if ( !(unsigned __int8)BfsPolicyEntryExists(
                               FltObject,
                               a2,
                               &gBfsPolicyTable,
                               *(_QWORD *)TokenInformation,
                               *(_QWORD *)P) )
        goto LABEL_24;
      PolicyEntry = BfsGetPolicyEntry(
                      (int)FltObject,
                      (__int64)a2,
                      (__int64)&gBfsPolicyTable,
                      *(void **)TokenInformation,
                      *(PSID *)P,
                      (__int64 *)v26);
      v16 = (char *)v26[0];
      v17 = PolicyEntry;
      if ( PolicyEntry < 0 )
        goto LABEL_7;
      v18 = *(__m128i *)BfsGetFileName(v26, a5);
      v19 = _mm_cvtsi128_si32(v18);
      *(__m128i *)v26 = v18;
      if ( v19 )
      {
        for ( i = (char *)v26[1] + 2 * ((unsigned __int64)v19 >> 1) - 2; i > v26[1]; i -= 2 )
        {
          if ( *(_WORD *)i == 92 )
            goto LABEL_15;
        }
        if ( *(_WORD *)i != 92 )
          goto LABEL_16;
LABEL_15:
        LOWORD(v26[0]) = 2 * ((i - (char *)v26[1]) >> 1);
        WORD1(v26[0]) = v26[0];
      }
LABEL_16:
      if ( (unsigned int)BfsGetPolicy(*((_QWORD *)v16 + 6), a5 + 24, (__int128 *)v26, v25) != 1 )
        goto LABEL_22;
      v17 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
      if ( v17 < 0 || (v17 = FltParseFileNameInformation(FileNameInformation), v17 < 0) )
      {
LABEL_7:
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v26[0]) = v17;
          v34 = v26;
          v35 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v17, (int)&byte_140016D91, v14, v15, v24, &v33);
        }
      }
      else
      {
        *((_QWORD *)&v30 + 1) = FileNameInformation;
        BYTE4(v32) = v25[0];
        *(_QWORD *)&v30 = Token;
        *(_QWORD *)&v31 = a5;
        *((_QWORD *)&v31 + 1) = v16;
        LODWORD(v32) = 0;
        v21 = BfsQueueDeferredWorkItemAndWait(FltObject, a2, Data, (__int64)BfsRenameAsUserCallback);
        Data->IoStatus.Information = 0;
        v7 = 4;
        if ( v21 >= 0 )
          v21 = v32;
        Data->IoStatus.Status = v21;
      }
LABEL_22:
      if ( v16 )
        BfsDereferencePolicyEntryEx(v16, 0);
      goto LABEL_24;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v26[0]) = v10;
    v34 = v26;
    v35 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v11, v12, v23, &v33);
  }
LABEL_24:
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
0x140005edc  push    rbp
0x140005ede  push    rbx
0x140005edf  push    rsi
0x140005ee0  push    rdi
0x140005ee1  push    r12
0x140005ee3  push    r13
0x140005ee5  push    r14
0x140005ee7  push    r15
0x140005ee9  lea     rbp, [rsp-17h]
0x140005eee  sub     rsp, 0C8h
0x140005ef5  mov     rax, cs:__security_cookie
0x140005efc  xor     rax, rsp
0x140005eff  mov     [rbp+4Fh+var_48], rax
0x140005f03  mov     r14, [rbp+4Fh+arg_20]
0x140005f07  xor     ebx, ebx
0x140005f09  xor     eax, eax
0x140005f0b  mov     [rbp+4Fh+TokenInformation], rbx
0x140005f0f  mov     r13, r8
0x140005f12  mov     [rbp+4Fh+var_80], rax
0x140005f16  xorps   xmm0, xmm0
0x140005f19  mov     [rbp+4Fh+var_C8], rbx
0x140005f1d  mov     r12, rdx
0x140005f20  mov     [rbp+4Fh+P], rbx
0x140005f24  lea     edi, [rax+1]
0x140005f27  mov     [rbp+4Fh+FileNameInformation], rbx
0x140005f2b  mov     r15, rcx
0x140005f2e  mov     [rsp+100h+var_D0], bl
0x140005f32  mov     edx, edi; TokenInformationClass
0x140005f34  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x140005f38  mov     rcx, r13; Token
0x140005f3b  mov     rsi, r9
0x140005f3e  movups  [rbp+4Fh+var_A0], xmm0
0x140005f42  movups  [rbp+4Fh+var_90], xmm0
0x140005f46  call    cs:__imp_SeQueryInformationToken
0x140005f4d  nop     dword ptr [rax+rax+00h]
0x140005f52  mov     ecx, eax; int
0x140005f54  test    eax, eax
0x140005f56  jns     short loc_140005F94
0x140005f58  mov     eax, cs:dword_140019000
0x140005f5e  cmp     eax, 3
0x140005f61  jbe     loc_140006161
0x140005f67  lea     rax, [rbp+4Fh+var_C8]
0x140005f6b  mov     dword ptr [rbp+4Fh+var_C8], ecx
0x140005f6e  mov     [rbp+4Fh+var_58], rax
0x140005f72  lea     rdx, byte_140016D91; int
0x140005f79  lea     rax, [rbp+4Fh+var_78]
0x140005f7d  mov     [rbp+4Fh+var_50], 4
0x140005f85  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140005f8a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005f8f  jmp     loc_140006161
0x140005f94  lea     r8, [rbp+4Fh+P]; TokenInformation
0x140005f98  mov     edx, 1Fh; TokenInformationClass
0x140005f9d  mov     rcx, r13; Token
0x140005fa0  call    cs:__imp_SeQueryInformationToken
0x140005fa7  nop     dword ptr [rax+rax+00h]
0x140005fac  mov     ecx, eax
0x140005fae  test    eax, eax
0x140005fb0  js      short loc_140005F58
0x140005fb2  mov     rax, [rbp+4Fh+P]
0x140005fb6  lea     r8, gBfsPolicyTable
0x140005fbd  mov     r9, [rbp+4Fh+TokenInformation]
0x140005fc1  mov     rdx, r12
0x140005fc4  mov     rcx, [rax]
0x140005fc7  mov     r9, [r9]
0x140005fca  mov     [rsp+100h+var_E0], rcx
0x140005fcf  mov     rcx, r15
0x140005fd2  call    BfsPolicyEntryExists
0x140005fd7  test    al, al
0x140005fd9  jz      loc_140006161
0x140005fdf  mov     r9, [rbp+4Fh+TokenInformation]
0x140005fe3  lea     rax, [rbp+4Fh+var_C8]
0x140005fe7  mov     [rsp+100h+var_D8], rax
0x140005fec  lea     r8, gBfsPolicyTable
0x140005ff3  mov     rax, [rbp+4Fh+P]
0x140005ff7  mov     rdx, r12
0x140005ffa  mov     r9, [r9]
0x140005ffd  mov     rcx, [rax]
0x140006000  mov     [rsp+100h+var_E0], rcx; int
0x140006005  mov     rcx, r15
0x140006008  call    BfsGetPolicyEntry
0x14000600d  mov     rbx, [rbp+4Fh+var_C8]
0x140006011  mov     ecx, eax; int
0x140006013  test    eax, eax
0x140006015  jns     short loc_140006053
0x140006017  mov     eax, cs:dword_140019000
0x14000601d  cmp     eax, 3
0x140006020  jbe     loc_140006152
0x140006026  lea     rax, [rbp+4Fh+var_C8]
0x14000602a  mov     dword ptr [rbp+4Fh+var_C8], ecx
0x14000602d  mov     [rbp+4Fh+var_58], rax
0x140006031  lea     rdx, byte_140016D91; int
0x140006038  lea     rax, [rbp+4Fh+var_78]
0x14000603c  mov     [rbp+4Fh+var_50], 4
0x140006044  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140006049  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000604e  jmp     loc_140006152
0x140006053  mov     rdx, r14
0x140006056  lea     rcx, [rbp+4Fh+var_C8]
0x14000605a  call    BfsGetFileName
0x14000605f  movups  xmm1, xmmword ptr [rax]
0x140006062  movd    eax, xmm1
0x140006066  movups  xmmword ptr [rbp+4Fh+var_C8], xmm1
0x14000606a  test    ax, ax
0x14000606d  jz      short loc_1400060A8
0x14000606f  mov     rdx, [rbp+4Fh+var_C8+8]
0x140006073  movzx   ecx, ax
0x140006076  shr     rcx, 1
0x140006079  dec     rcx
0x14000607c  lea     rcx, [rdx+rcx*2]
0x140006080  jmp     short loc_14000608C
0x140006082  cmp     word ptr [rcx], 5Ch ; '\'
0x140006086  jz      short loc_140006097
0x140006088  sub     rcx, 2
0x14000608c  cmp     rcx, rdx
0x14000608f  ja      short loc_140006082
0x140006091  cmp     word ptr [rcx], 5Ch ; '\'
0x140006095  jnz     short loc_1400060A8
0x140006097  sub     rcx, rdx
0x14000609a  sar     rcx, 1
0x14000609d  add     cx, cx
0x1400060a0  mov     word ptr [rbp+4Fh+var_C8], cx
0x1400060a4  mov     word ptr [rbp+4Fh+var_C8+2], cx
0x1400060a8  mov     rcx, [rbx+30h]
0x1400060ac  lea     rdx, [r14+18h]
0x1400060b0  lea     r9, [rsp+100h+var_D0]
0x1400060b5  lea     r8, [rbp+4Fh+var_C8]
0x1400060b9  call    BfsGetPolicy
0x1400060be  cmp     eax, edi
0x1400060c0  jnz     loc_140006152
0x1400060c6  lea     r8, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x1400060ca  mov     edx, 101h; NameOptions
0x1400060cf  mov     rcx, rsi; CallbackData
0x1400060d2  call    cs:__imp_FltGetFileNameInformation
0x1400060d9  nop     dword ptr [rax+rax+00h]
0x1400060de  mov     ecx, eax
0x1400060e0  test    eax, eax
0x1400060e2  js      loc_140006017
0x1400060e8  mov     rcx, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x1400060ec  call    cs:__imp_FltParseFileNameInformation
0x1400060f3  nop     dword ptr [rax+rax+00h]
0x1400060f8  mov     ecx, eax
0x1400060fa  test    eax, eax
0x1400060fc  js      loc_140006017
0x140006102  mov     rax, [rbp+4Fh+FileNameInformation]
0x140006106  lea     r9, [rbp+4Fh+var_A0]
0x14000610a  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x14000610e  xor     edi, edi
0x140006110  mov     al, [rsp+100h+var_D0]
0x140006114  mov     r8, rsi; Data
0x140006117  mov     byte ptr [rbp+4Fh+var_80+4], al
0x14000611a  mov     rdx, r12; PVOID
0x14000611d  lea     rax, BfsRenameAsUserCallback
0x140006124  mov     qword ptr [rbp+4Fh+var_A0], r13
0x140006128  mov     rcx, r15; FltObject
0x14000612b  mov     [rsp+100h+var_E0], rax; __int64
0x140006130  mov     qword ptr [rbp+4Fh+var_90], r14
0x140006134  mov     qword ptr [rbp+4Fh+var_90+8], rbx
0x140006138  mov     dword ptr [rbp+4Fh+var_80], edi
0x14000613b  call    BfsQueueDeferredWorkItemAndWait
0x140006140  test    eax, eax
0x140006142  mov     [rsi+20h], rdi
0x140006146  mov     edi, 4
0x14000614b  cmovns  eax, dword ptr [rbp+4Fh+var_80]
0x14000614f  mov     [rsi+18h], eax
0x140006152  test    rbx, rbx
0x140006155  jz      short loc_140006161
0x140006157  xor     edx, edx
0x140006159  mov     rcx, rbx; P
0x14000615c  call    BfsDereferencePolicyEntryEx
0x140006161  mov     rcx, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x140006165  test    rcx, rcx
0x140006168  jz      short loc_140006176
0x14000616a  call    cs:__imp_FltReleaseFileNameInformation
0x140006171  nop     dword ptr [rax+rax+00h]
0x140006176  mov     rcx, [rbp+4Fh+TokenInformation]; P
0x14000617a  test    rcx, rcx
0x14000617d  jz      short loc_14000618D
0x14000617f  xor     edx, edx; Tag
0x140006181  call    cs:__imp_ExFreePoolWithTag
0x140006188  nop     dword ptr [rax+rax+00h]
0x14000618d  mov     rcx, [rbp+4Fh+P]; P
0x140006191  test    rcx, rcx
0x140006194  jz      short loc_1400061A4
0x140006196  xor     edx, edx; Tag
0x140006198  call    cs:__imp_ExFreePoolWithTag
0x14000619f  nop     dword ptr [rax+rax+00h]
0x1400061a4  mov     eax, edi
0x1400061a6  mov     rcx, [rbp+4Fh+var_48]
0x1400061aa  xor     rcx, rsp; StackCookie
0x1400061ad  call    __security_check_cookie
0x1400061b2  add     rsp, 0C8h
0x1400061b9  pop     r15
0x1400061bb  pop     r14
0x1400061bd  pop     r13
0x1400061bf  pop     r12
0x1400061c1  pop     rdi
0x1400061c2  pop     rsi
0x1400061c3  pop     rbx
0x1400061c4  pop     rbp
0x1400061c5  retn
```
