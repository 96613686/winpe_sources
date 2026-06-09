# BfsProcessQueryPolicyRequest

- ea: `0x140009530`
- end: `0x140009956`
- name: `BfsProcessQueryPolicyRequest`
- size: `1062`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, SIZE_T Length)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003640`

## callees

- `0x140001008`
- `0x140003210`
- `0x140006040`
- `0x1400061a0`
- `0x140007044`
- `0x140008e84`
- `0x140009530`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400095f8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400095f8`
- `ntoskrnl!SeTokenObjectType` at `0x1400095e6`
- `ntoskrnl!ProbeForWrite` at `0x1400095c3`
- `ntoskrnl!ProbeForWrite` at `0x1400095c3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400098ad`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400098ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400098ee`
- `ntoskrnl!ObfDereferenceObject` at `0x1400098ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009906`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000991e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009906`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000991e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400097ef`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400097ef`
- `ntoskrnl!SeQueryInformationToken` at `0x140009689`
- `ntoskrnl!SeQueryInformationToken` at `0x1400096aa`
- `ntoskrnl!SeQueryInformationToken` at `0x140009689`
- `ntoskrnl!SeQueryInformationToken` at `0x1400096aa`

## pseudocode

```c
__int64 __fastcall BfsProcessQueryPolicyRequest(HANDLE Handle, char *a2, SIZE_T Length)
{
  unsigned int v3; // esi
  NTSTATUS v6; // eax
  int v7; // r8d
  int v8; // r9d
  NTSTATUS PolicyEntry; // ebx
  int v10; // ecx
  NTSTATUS v11; // ecx
  unsigned int v12; // r12d
  WCHAR *v13; // r15
  PVOID *i; // rsi
  __int64 v15; // rbx
  USHORT v16; // ax
  struct _UNICODE_STRING *v17; // rsi
  __int64 v18; // rax
  PVOID *Object; // [rsp+20h] [rbp-C8h]
  NTSTATUS v21; // [rsp+30h] [rbp-B8h] BYREF
  _DWORD Size[3]; // [rsp+34h] [rbp-B4h] BYREF
  PVOID P[2]; // [rsp+40h] [rbp-A8h] BYREF
  PVOID TokenInformation; // [rsp+50h] [rbp-98h] BYREF
  PVOID v25; // [rsp+58h] [rbp-90h] BYREF
  int v26; // [rsp+60h] [rbp-88h]
  int v27; // [rsp+64h] [rbp-84h]
  WCHAR *v28; // [rsp+68h] [rbp-80h]
  PVOID v29; // [rsp+70h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+88h] [rbp-60h] BYREF
  NTSTATUS *v32; // [rsp+A8h] [rbp-40h]
  __int64 v33; // [rsp+B0h] [rbp-38h]

  v3 = Length;
  v25 = 0;
  v29 = 0;
  *(_QWORD *)&Size[1] = 0;
  TokenInformation = 0;
  if ( !a2 || !(_DWORD)Length )
    return 3221225485LL;
  Size[0] = 0;
  v21 = 0;
  P[1] = P;
  P[0] = P;
  ProbeForWrite(a2, (unsigned int)Length, 4u);
  v6 = ObReferenceObjectByHandle(Handle, 8u, (POBJECT_TYPE)SeTokenObjectType, 1, (PVOID *)&Size[1], 0);
  PolicyEntry = v6;
  if ( v6 >= 0 )
  {
    if ( BfsIsApplicableToken(*(PVOID *)&Size[1], 1) )
    {
      PolicyEntry = SeQueryInformationToken(*(PACCESS_TOKEN *)&Size[1], TokenUser, &TokenInformation);
      if ( PolicyEntry >= 0 )
      {
        PolicyEntry = SeQueryInformationToken(*(PACCESS_TOKEN *)&Size[1], TokenAppContainerSid, &v25);
        if ( PolicyEntry >= 0 )
        {
          if ( !BfsPolicyEntryExists(
                  (int)gBfsFilterHandle,
                  0,
                  (__int64)&gBfsPolicyTable,
                  *(void **)TokenInformation,
                  *(PSID *)v25) )
            goto LABEL_22;
          Object = *(PVOID **)v25;
          PolicyEntry = BfsGetPolicyEntry(gBfsFilterHandle, 0, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
          if ( PolicyEntry >= 0 )
          {
            PolicyEntry = BfsEnumeratePolicy(v29, P, &v21, Size, Object, &v29);
            if ( PolicyEntry >= 0 )
            {
              if ( v3 >= Size[0] )
              {
                memset(a2, 0, Size[0]);
                v11 = v21;
                *(_DWORD *)a2 = v21;
                v12 = 0;
                v26 = 0;
                v13 = (WCHAR *)&a2[32 * v11 + 8];
                v28 = v13;
                for ( i = (PVOID *)P[0]; i != P; i = (PVOID *)*i )
                {
                  DestinationString = 0;
                  v15 = 32LL * v12;
                  *(_DWORD *)&a2[v15 + 8] = *((_DWORD *)i + 4);
                  *(_DWORD *)&a2[v15 + 16] = *((_DWORD *)i + 6);
                  *(_DWORD *)&a2[v15 + 12] = *((_DWORD *)i + 5);
                  v16 = *((_WORD *)i + 17);
                  *(_QWORD *)&DestinationString.Length = 0;
                  DestinationString.MaximumLength = v16;
                  DestinationString.Buffer = v13;
                  RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)i + 2);
                  *(struct _UNICODE_STRING *)&a2[v15 + 24] = DestinationString;
                  v13 = (WCHAR *)((char *)v13 + *((unsigned __int16 *)i + 17));
                  v28 = v13;
                  v26 = ++v12;
                }
                PolicyEntry = 0;
                v27 = 0;
                goto LABEL_22;
              }
              PolicyEntry = -1073741789;
            }
          }
        }
      }
    }
    else
    {
      PolicyEntry = -1073700352;
    }
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v21 = PolicyEntry;
      goto LABEL_6;
    }
  }
  else
  {
    v10 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v21 = v6;
LABEL_6:
      v32 = &v21;
      v33 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v7, v8, (int)Object, &v31);
    }
  }
LABEL_22:
  while ( 1 )
  {
    v17 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] == P )
      break;
    if ( *((PVOID **)P[0] + 1) != P || (v18 = *(_QWORD *)P[0], *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0]) )
      __fastfail(3u);
    P[0] = *(PVOID *)P[0];
    *(_QWORD *)(v18 + 8) = P;
    RtlFreeUnicodeString(v17 + 2);
    ExFreePoolWithTag(v17, 0);
  }
  if ( v29 )
    BfsDereferencePolicyEntryEx(v29);
  if ( *(_QWORD *)&Size[1] )
    ObfDereferenceObject(*(PVOID *)&Size[1]);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v25 )
    ExFreePoolWithTag(v25, 0);
  return (unsigned int)PolicyEntry;
}

```

## disassembly

```asm
0x140009530  push    rbx
0x140009532  push    rsi
0x140009533  push    r12
0x140009535  push    r14
0x140009537  push    r15
0x140009539  sub     rsp, 0C0h
0x140009540  mov     rax, cs:__security_cookie
0x140009547  xor     rax, rsp
0x14000954a  mov     [rsp+0E8h+var_30], rax
0x140009552  mov     esi, r8d
0x140009555  mov     r14, rdx
0x140009558  mov     rbx, rcx
0x14000955b  mov     [rsp+0E8h+var_90], 0
0x140009564  mov     [rsp+0E8h+var_78], 0
0x14000956d  mov     qword ptr [rsp+0E8h+Size+4], 0
0x140009576  mov     [rsp+0E8h+TokenInformation], 0
0x14000957f  test    rdx, rdx
0x140009582  jz      loc_140009930
0x140009588  test    r8d, r8d
0x14000958b  jz      loc_140009930
0x140009591  mov     dword ptr [rsp+0E8h+Size], 0
0x140009599  mov     [rsp+0E8h+var_B8], 0
0x1400095a1  lea     rax, [rsp+0E8h+P]
0x1400095a6  mov     [rsp+0E8h+var_A0], rax
0x1400095ab  lea     rax, [rsp+0E8h+P]
0x1400095b0  mov     [rsp+0E8h+P], rax
0x1400095b5  mov     edx, esi; Length
0x1400095b7  mov     r15d, 4
0x1400095bd  mov     r8d, r15d; Alignment
0x1400095c0  mov     rcx, r14; Address
0x1400095c3  call    cs:__imp_ProbeForWrite
0x1400095ca  nop     dword ptr [rax+rax+00h]
0x1400095cf  nop
0x1400095d0  mov     [rsp+0E8h+HandleInformation], 0; HandleInformation
0x1400095d9  lea     rax, [rsp+0E8h+Size+4]
0x1400095de  mov     [rsp+0E8h+Object], rax; int
0x1400095e3  mov     r9b, 1; AccessMode
0x1400095e6  mov     r8, cs:__imp_SeTokenObjectType
0x1400095ed  mov     r8, [r8]; ObjectType
0x1400095f0  mov     edx, 8; DesiredAccess
0x1400095f5  mov     rcx, rbx; Handle
0x1400095f8  call    cs:__imp_ObReferenceObjectByHandle
0x1400095ff  nop     dword ptr [rax+rax+00h]
0x140009604  mov     ebx, eax
0x140009606  test    eax, eax
0x140009608  jns     short loc_140009650
0x14000960a  mov     ecx, cs:dword_140019000; int
0x140009610  cmp     ecx, 3
0x140009613  jbe     loc_140009878
0x140009619  mov     [rsp+0E8h+var_B8], eax
0x14000961d  lea     rax, [rsp+0E8h+var_B8]
0x140009622  mov     [rsp+0E8h+var_40], rax
0x14000962a  mov     [rsp+0E8h+var_38], r15
0x140009632  lea     rax, [rsp+0E8h+var_60]
0x14000963a  mov     [rsp+0E8h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000963f  lea     rdx, byte_140016D91; int
0x140009646  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000964b  jmp     loc_140009878
0x140009650  mov     dl, 1
0x140009652  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Object
0x140009657  call    BfsIsApplicableToken
0x14000965c  test    al, al
0x14000965e  jnz     short loc_14000967A
0x140009660  mov     ebx, 0C000A200h
0x140009665  mov     eax, cs:dword_140019000
0x14000966b  cmp     eax, 3
0x14000966e  jbe     loc_140009878
0x140009674  mov     [rsp+0E8h+var_B8], ebx
0x140009678  jmp     short loc_14000961D
0x14000967a  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x14000967f  mov     edx, 1; TokenInformationClass
0x140009684  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Token
0x140009689  call    cs:__imp_SeQueryInformationToken
0x140009690  nop     dword ptr [rax+rax+00h]
0x140009695  mov     ebx, eax
0x140009697  test    eax, eax
0x140009699  js      short loc_140009665
0x14000969b  lea     r8, [rsp+0E8h+var_90]; TokenInformation
0x1400096a0  mov     edx, 1Fh; TokenInformationClass
0x1400096a5  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Token
0x1400096aa  call    cs:__imp_SeQueryInformationToken
0x1400096b1  nop     dword ptr [rax+rax+00h]
0x1400096b6  mov     ebx, eax
0x1400096b8  test    eax, eax
0x1400096ba  js      short loc_140009665
0x1400096bc  mov     rax, [rsp+0E8h+var_90]
0x1400096c1  mov     rcx, [rax]
0x1400096c4  mov     [rsp+0E8h+Object], rcx
0x1400096c9  mov     r9, [rsp+0E8h+TokenInformation]
0x1400096ce  mov     r9, [r9]
0x1400096d1  lea     r8, gBfsPolicyTable
0x1400096d8  xor     edx, edx
0x1400096da  mov     rcx, cs:gBfsFilterHandle
0x1400096e1  call    BfsPolicyEntryExists
0x1400096e6  test    al, al
0x1400096e8  jz      loc_140009878
0x1400096ee  lea     rax, [rsp+0E8h+var_78]
0x1400096f3  mov     [rsp+0E8h+HandleInformation], rax
0x1400096f8  mov     rax, [rsp+0E8h+var_90]
0x1400096fd  mov     rcx, [rax]
0x140009700  mov     [rsp+0E8h+Object], rcx
0x140009705  mov     r9, [rsp+0E8h+TokenInformation]
0x14000970a  mov     r9, [r9]
0x14000970d  lea     r8, gBfsPolicyTable
0x140009714  xor     edx, edx
0x140009716  mov     rcx, cs:gBfsFilterHandle
0x14000971d  call    BfsGetPolicyEntry
0x140009722  mov     ebx, eax
0x140009724  test    eax, eax
0x140009726  js      loc_140009665
0x14000972c  lea     r9, [rsp+0E8h+Size]
0x140009731  lea     r8, [rsp+0E8h+var_B8]
0x140009736  lea     rdx, [rsp+0E8h+P]
0x14000973b  mov     rcx, [rsp+0E8h+var_78]
0x140009740  call    BfsEnumeratePolicy
0x140009745  mov     ebx, eax
0x140009747  test    eax, eax
0x140009749  js      loc_140009665
0x14000974f  cmp     esi, dword ptr [rsp+0E8h+Size]
0x140009753  jnb     short loc_14000975F
0x140009755  mov     ebx, 0C0000023h
0x14000975a  jmp     loc_140009665
0x14000975f  mov     r8d, dword ptr [rsp+0E8h+Size]; Size
0x140009764  xor     edx, edx; Val
0x140009766  mov     rcx, r14; void *
0x140009769  call    memset
0x14000976e  mov     ecx, [rsp+0E8h+var_B8]
0x140009772  mov     [r14], ecx
0x140009775  xor     r12d, r12d
0x140009778  mov     [rsp+0E8h+var_88], r12d
0x14000977d  mov     [rsp+0E8h+var_80], r14
0x140009782  lea     rax, [r14+8]
0x140009786  mov     [rsp+0E8h+var_80], rax
0x14000978b  mov     r15d, ecx
0x14000978e  shl     r15, 5
0x140009792  add     r15, rax
0x140009795  mov     [rsp+0E8h+var_80], r15
0x14000979a  mov     rsi, [rsp+0E8h+P]
0x14000979f  lea     rax, [rsp+0E8h+P]
0x1400097a4  cmp     rsi, rax
0x1400097a7  jz      short loc_140009823
0x1400097a9  xorps   xmm0, xmm0
0x1400097ac  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1400097b1  mov     ebx, r12d
0x1400097b4  shl     rbx, 5
0x1400097b8  mov     eax, [rsi+10h]
0x1400097bb  mov     [rbx+r14+8], eax
0x1400097c0  mov     eax, [rsi+18h]
0x1400097c3  mov     [rbx+r14+10h], eax
0x1400097c8  mov     eax, [rsi+14h]
0x1400097cb  mov     [rbx+r14+0Ch], eax
0x1400097d0  movzx   eax, word ptr [rsi+22h]
0x1400097d4  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1400097d9  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x1400097de  mov     [rsp+0E8h+DestinationString.Buffer], r15
0x1400097e6  lea     rdx, [rsi+20h]; SourceString
0x1400097ea  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x1400097ef  call    cs:__imp_RtlCopyUnicodeString
0x1400097f6  nop     dword ptr [rax+rax+00h]
0x1400097fb  movups  xmm0, xmmword ptr [rsp+0E8h+DestinationString.Length]
0x140009800  movdqu  xmmword ptr [rbx+r14+18h], xmm0
0x140009807  movzx   eax, word ptr [rsi+22h]
0x14000980b  add     r15, rax
0x14000980e  mov     [rsp+0E8h+var_80], r15
0x140009813  inc     r12d
0x140009816  mov     [rsp+0E8h+var_88], r12d
0x14000981b  mov     rsi, [rsi]
0x14000981e  jmp     loc_14000979F
0x140009823  xor     ebx, ebx
0x140009825  mov     [rsp+0E8h+var_84], ebx
0x140009829  jmp     short loc_140009878
0x14000982b  mov     ebx, eax
0x14000982d  mov     [rsp+0E8h+var_84], eax
0x140009831  test    eax, eax
0x140009833  jns     short loc_140009878
0x140009835  mov     eax, cs:dword_140019000
0x14000983b  cmp     eax, 3
0x14000983e  jbe     short loc_140009876
0x140009840  mov     [rsp+0E8h+var_B8], ebx
0x140009844  lea     rax, [rsp+0E8h+var_B8]
0x140009849  mov     [rsp+0E8h+var_40], rax
0x140009851  mov     [rsp+0E8h+var_38], 4
0x14000985d  lea     rax, [rsp+0E8h+var_60]
0x140009865  mov     [rsp+0E8h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000986a  lea     rdx, byte_140016D91; int
0x140009871  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009876  jmp     short $+2
0x140009878  mov     rsi, [rsp+0E8h+P]
0x14000987d  lea     rax, [rsp+0E8h+P]
0x140009882  cmp     rsi, rax
0x140009885  jz      short loc_1400098D3
0x140009887  lea     rax, [rsp+0E8h+P]
0x14000988c  cmp     [rsi+8], rax
0x140009890  jnz     short loc_1400098CC
0x140009892  mov     rax, [rsi]
0x140009895  cmp     [rax+8], rsi
0x140009899  jnz     short loc_1400098CC
0x14000989b  mov     [rsp+0E8h+P], rax
0x1400098a0  lea     rcx, [rsp+0E8h+P]
0x1400098a5  mov     [rax+8], rcx
0x1400098a9  lea     rcx, [rsi+20h]; UnicodeString
0x1400098ad  call    cs:__imp_RtlFreeUnicodeString
0x1400098b4  nop     dword ptr [rax+rax+00h]
0x1400098b9  xor     edx, edx; Tag
0x1400098bb  mov     rcx, rsi; P
0x1400098be  call    cs:__imp_ExFreePoolWithTag
0x1400098c5  nop     dword ptr [rax+rax+00h]
0x1400098ca  jmp     short loc_140009878
0x1400098cc  mov     ecx, 3
0x1400098d1  int     29h; Win8: RtlFailFast(ecx)
0x1400098d3  mov     rcx, [rsp+0E8h+var_78]; P
0x1400098d8  test    rcx, rcx
0x1400098db  jz      short loc_1400098E4
0x1400098dd  xor     edx, edx
0x1400098df  call    BfsDereferencePolicyEntryEx
0x1400098e4  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Object
0x1400098e9  test    rcx, rcx
0x1400098ec  jz      short loc_1400098FA
0x1400098ee  call    cs:__imp_ObfDereferenceObject
0x1400098f5  nop     dword ptr [rax+rax+00h]
0x1400098fa  mov     rcx, [rsp+0E8h+TokenInformation]; P
0x1400098ff  test    rcx, rcx
0x140009902  jz      short loc_140009912
0x140009904  xor     edx, edx; Tag
0x140009906  call    cs:__imp_ExFreePoolWithTag
0x14000990d  nop     dword ptr [rax+rax+00h]
0x140009912  mov     rcx, [rsp+0E8h+var_90]; P
0x140009917  test    rcx, rcx
0x14000991a  jz      short loc_14000992A
0x14000991c  xor     edx, edx; Tag
0x14000991e  call    cs:__imp_ExFreePoolWithTag
0x140009925  nop     dword ptr [rax+rax+00h]
0x14000992a  mov     eax, ebx
0x14000992c  jmp     short loc_140009935
0x14000992e  jmp     short loc_140009935
0x140009930  mov     eax, 0C000000Dh
0x140009935  mov     rcx, [rsp+0E8h+var_30]
0x14000993d  xor     rcx, rsp; StackCookie
0x140009940  call    __security_check_cookie
0x140009945  add     rsp, 0C0h
0x14000994c  pop     r15
0x14000994e  pop     r14
0x140009950  pop     r12
0x140009952  pop     rsi
0x140009953  pop     rbx
0x140009954  retn
```
