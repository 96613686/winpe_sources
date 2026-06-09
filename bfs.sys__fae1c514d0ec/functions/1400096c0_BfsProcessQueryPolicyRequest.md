# BfsProcessQueryPolicyRequest

- ea: `0x1400096c0`
- end: `0x140009ae6`
- name: `BfsProcessQueryPolicyRequest`
- size: `1062`
- prototype: `__int64 __fastcall(HANDLE Handle, char *, SIZE_T Length)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003770`

## callees

- `0x140001008`
- `0x140003340`
- `0x1400061d0`
- `0x140006330`
- `0x1400071d4`
- `0x140009014`
- `0x1400096c0`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009788`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009788`
- `ntoskrnl!SeTokenObjectType` at `0x140009776`
- `ntoskrnl!ProbeForWrite` at `0x140009753`
- `ntoskrnl!ProbeForWrite` at `0x140009753`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009a3d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009a3d`
- `ntoskrnl!ObfDereferenceObject` at `0x140009a7e`
- `ntoskrnl!ObfDereferenceObject` at `0x140009a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009a4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009a96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009aae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009a4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009a96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009aae`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000997f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000997f`
- `ntoskrnl!SeQueryInformationToken` at `0x140009819`
- `ntoskrnl!SeQueryInformationToken` at `0x14000983a`
- `ntoskrnl!SeQueryInformationToken` at `0x140009819`
- `ntoskrnl!SeQueryInformationToken` at `0x14000983a`

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
  PVOID v29; // [rsp+70h] [rbp-78h]
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
    if ( (unsigned __int8)BfsIsApplicableToken(*(PVOID *)&Size[1]) )
    {
      PolicyEntry = SeQueryInformationToken(*(PACCESS_TOKEN *)&Size[1], TokenUser, &TokenInformation);
      if ( PolicyEntry >= 0 )
      {
        PolicyEntry = SeQueryInformationToken(*(PACCESS_TOKEN *)&Size[1], TokenAppContainerSid, &v25);
        if ( PolicyEntry >= 0 )
        {
          if ( !(unsigned __int8)BfsPolicyEntryExists(
                                   gBfsFilterHandle,
                                   0,
                                   &gBfsPolicyTable,
                                   *(_QWORD *)TokenInformation,
                                   *(_QWORD *)v25) )
            goto LABEL_22;
          Object = *(PVOID **)v25;
          PolicyEntry = BfsGetPolicyEntry(gBfsFilterHandle, 0, &gBfsPolicyTable, *(_QWORD *)TokenInformation);
          if ( PolicyEntry >= 0 )
          {
            PolicyEntry = BfsEnumeratePolicy(v29, P, &v21, Size);
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
0x1400096c0  push    rbx
0x1400096c2  push    rsi
0x1400096c3  push    r12
0x1400096c5  push    r14
0x1400096c7  push    r15
0x1400096c9  sub     rsp, 0C0h
0x1400096d0  mov     rax, cs:__security_cookie
0x1400096d7  xor     rax, rsp
0x1400096da  mov     [rsp+0E8h+var_30], rax
0x1400096e2  mov     esi, r8d
0x1400096e5  mov     r14, rdx
0x1400096e8  mov     rbx, rcx
0x1400096eb  mov     [rsp+0E8h+var_90], 0
0x1400096f4  mov     [rsp+0E8h+var_78], 0
0x1400096fd  mov     qword ptr [rsp+0E8h+Size+4], 0
0x140009706  mov     [rsp+0E8h+TokenInformation], 0
0x14000970f  test    rdx, rdx
0x140009712  jz      loc_140009AC0
0x140009718  test    r8d, r8d
0x14000971b  jz      loc_140009AC0
0x140009721  mov     dword ptr [rsp+0E8h+Size], 0
0x140009729  mov     [rsp+0E8h+var_B8], 0
0x140009731  lea     rax, [rsp+0E8h+P]
0x140009736  mov     [rsp+0E8h+var_A0], rax
0x14000973b  lea     rax, [rsp+0E8h+P]
0x140009740  mov     [rsp+0E8h+P], rax
0x140009745  mov     edx, esi; Length
0x140009747  mov     r15d, 4
0x14000974d  mov     r8d, r15d; Alignment
0x140009750  mov     rcx, r14; Address
0x140009753  call    cs:__imp_ProbeForWrite
0x14000975a  nop     dword ptr [rax+rax+00h]
0x14000975f  nop
0x140009760  mov     [rsp+0E8h+HandleInformation], 0; HandleInformation
0x140009769  lea     rax, [rsp+0E8h+Size+4]
0x14000976e  mov     [rsp+0E8h+Object], rax; int
0x140009773  mov     r9b, 1; AccessMode
0x140009776  mov     r8, cs:__imp_SeTokenObjectType
0x14000977d  mov     r8, [r8]; ObjectType
0x140009780  mov     edx, 8; DesiredAccess
0x140009785  mov     rcx, rbx; Handle
0x140009788  call    cs:__imp_ObReferenceObjectByHandle
0x14000978f  nop     dword ptr [rax+rax+00h]
0x140009794  mov     ebx, eax
0x140009796  test    eax, eax
0x140009798  jns     short loc_1400097E0
0x14000979a  mov     ecx, cs:dword_140019000; int
0x1400097a0  cmp     ecx, 3
0x1400097a3  jbe     loc_140009A08
0x1400097a9  mov     [rsp+0E8h+var_B8], eax
0x1400097ad  lea     rax, [rsp+0E8h+var_B8]
0x1400097b2  mov     [rsp+0E8h+var_40], rax
0x1400097ba  mov     [rsp+0E8h+var_38], r15
0x1400097c2  lea     rax, [rsp+0E8h+var_60]
0x1400097ca  mov     [rsp+0E8h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x1400097cf  lea     rdx, byte_140016D91; int
0x1400097d6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400097db  jmp     loc_140009A08
0x1400097e0  mov     dl, 1
0x1400097e2  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Object
0x1400097e7  call    BfsIsApplicableToken
0x1400097ec  test    al, al
0x1400097ee  jnz     short loc_14000980A
0x1400097f0  mov     ebx, 0C000A200h
0x1400097f5  mov     eax, cs:dword_140019000
0x1400097fb  cmp     eax, 3
0x1400097fe  jbe     loc_140009A08
0x140009804  mov     [rsp+0E8h+var_B8], ebx
0x140009808  jmp     short loc_1400097AD
0x14000980a  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x14000980f  mov     edx, 1; TokenInformationClass
0x140009814  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Token
0x140009819  call    cs:__imp_SeQueryInformationToken
0x140009820  nop     dword ptr [rax+rax+00h]
0x140009825  mov     ebx, eax
0x140009827  test    eax, eax
0x140009829  js      short loc_1400097F5
0x14000982b  lea     r8, [rsp+0E8h+var_90]; TokenInformation
0x140009830  mov     edx, 1Fh; TokenInformationClass
0x140009835  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Token
0x14000983a  call    cs:__imp_SeQueryInformationToken
0x140009841  nop     dword ptr [rax+rax+00h]
0x140009846  mov     ebx, eax
0x140009848  test    eax, eax
0x14000984a  js      short loc_1400097F5
0x14000984c  mov     rax, [rsp+0E8h+var_90]
0x140009851  mov     rcx, [rax]
0x140009854  mov     [rsp+0E8h+Object], rcx
0x140009859  mov     r9, [rsp+0E8h+TokenInformation]
0x14000985e  mov     r9, [r9]
0x140009861  lea     r8, gBfsPolicyTable
0x140009868  xor     edx, edx
0x14000986a  mov     rcx, cs:gBfsFilterHandle
0x140009871  call    BfsPolicyEntryExists
0x140009876  test    al, al
0x140009878  jz      loc_140009A08
0x14000987e  lea     rax, [rsp+0E8h+var_78]
0x140009883  mov     [rsp+0E8h+HandleInformation], rax
0x140009888  mov     rax, [rsp+0E8h+var_90]
0x14000988d  mov     rcx, [rax]
0x140009890  mov     [rsp+0E8h+Object], rcx
0x140009895  mov     r9, [rsp+0E8h+TokenInformation]
0x14000989a  mov     r9, [r9]
0x14000989d  lea     r8, gBfsPolicyTable
0x1400098a4  xor     edx, edx
0x1400098a6  mov     rcx, cs:gBfsFilterHandle
0x1400098ad  call    BfsGetPolicyEntry
0x1400098b2  mov     ebx, eax
0x1400098b4  test    eax, eax
0x1400098b6  js      loc_1400097F5
0x1400098bc  lea     r9, [rsp+0E8h+Size]
0x1400098c1  lea     r8, [rsp+0E8h+var_B8]
0x1400098c6  lea     rdx, [rsp+0E8h+P]
0x1400098cb  mov     rcx, [rsp+0E8h+var_78]
0x1400098d0  call    BfsEnumeratePolicy
0x1400098d5  mov     ebx, eax
0x1400098d7  test    eax, eax
0x1400098d9  js      loc_1400097F5
0x1400098df  cmp     esi, dword ptr [rsp+0E8h+Size]
0x1400098e3  jnb     short loc_1400098EF
0x1400098e5  mov     ebx, 0C0000023h
0x1400098ea  jmp     loc_1400097F5
0x1400098ef  mov     r8d, dword ptr [rsp+0E8h+Size]; Size
0x1400098f4  xor     edx, edx; Val
0x1400098f6  mov     rcx, r14; void *
0x1400098f9  call    memset
0x1400098fe  mov     ecx, [rsp+0E8h+var_B8]
0x140009902  mov     [r14], ecx
0x140009905  xor     r12d, r12d
0x140009908  mov     [rsp+0E8h+var_88], r12d
0x14000990d  mov     [rsp+0E8h+var_80], r14
0x140009912  lea     rax, [r14+8]
0x140009916  mov     [rsp+0E8h+var_80], rax
0x14000991b  mov     r15d, ecx
0x14000991e  shl     r15, 5
0x140009922  add     r15, rax
0x140009925  mov     [rsp+0E8h+var_80], r15
0x14000992a  mov     rsi, [rsp+0E8h+P]
0x14000992f  lea     rax, [rsp+0E8h+P]
0x140009934  cmp     rsi, rax
0x140009937  jz      short loc_1400099B3
0x140009939  xorps   xmm0, xmm0
0x14000993c  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x140009941  mov     ebx, r12d
0x140009944  shl     rbx, 5
0x140009948  mov     eax, [rsi+10h]
0x14000994b  mov     [rbx+r14+8], eax
0x140009950  mov     eax, [rsi+18h]
0x140009953  mov     [rbx+r14+10h], eax
0x140009958  mov     eax, [rsi+14h]
0x14000995b  mov     [rbx+r14+0Ch], eax
0x140009960  movzx   eax, word ptr [rsi+22h]
0x140009964  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x140009969  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x14000996e  mov     [rsp+0E8h+DestinationString.Buffer], r15
0x140009976  lea     rdx, [rsi+20h]; SourceString
0x14000997a  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x14000997f  call    cs:__imp_RtlCopyUnicodeString
0x140009986  nop     dword ptr [rax+rax+00h]
0x14000998b  movups  xmm0, xmmword ptr [rsp+0E8h+DestinationString.Length]
0x140009990  movdqu  xmmword ptr [rbx+r14+18h], xmm0
0x140009997  movzx   eax, word ptr [rsi+22h]
0x14000999b  add     r15, rax
0x14000999e  mov     [rsp+0E8h+var_80], r15
0x1400099a3  inc     r12d
0x1400099a6  mov     [rsp+0E8h+var_88], r12d
0x1400099ab  mov     rsi, [rsi]
0x1400099ae  jmp     loc_14000992F
0x1400099b3  xor     ebx, ebx
0x1400099b5  mov     [rsp+0E8h+var_84], ebx
0x1400099b9  jmp     short loc_140009A08
0x1400099bb  mov     ebx, eax
0x1400099bd  mov     [rsp+0E8h+var_84], eax
0x1400099c1  test    eax, eax
0x1400099c3  jns     short loc_140009A08
0x1400099c5  mov     eax, cs:dword_140019000
0x1400099cb  cmp     eax, 3
0x1400099ce  jbe     short loc_140009A06
0x1400099d0  mov     [rsp+0E8h+var_B8], ebx
0x1400099d4  lea     rax, [rsp+0E8h+var_B8]
0x1400099d9  mov     [rsp+0E8h+var_40], rax
0x1400099e1  mov     [rsp+0E8h+var_38], 4
0x1400099ed  lea     rax, [rsp+0E8h+var_60]
0x1400099f5  mov     [rsp+0E8h+HandleInformation], rax; PEVENT_DATA_DESCRIPTOR
0x1400099fa  lea     rdx, byte_140016D91; int
0x140009a01  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009a06  jmp     short $+2
0x140009a08  mov     rsi, [rsp+0E8h+P]
0x140009a0d  lea     rax, [rsp+0E8h+P]
0x140009a12  cmp     rsi, rax
0x140009a15  jz      short loc_140009A63
0x140009a17  lea     rax, [rsp+0E8h+P]
0x140009a1c  cmp     [rsi+8], rax
0x140009a20  jnz     short loc_140009A5C
0x140009a22  mov     rax, [rsi]
0x140009a25  cmp     [rax+8], rsi
0x140009a29  jnz     short loc_140009A5C
0x140009a2b  mov     [rsp+0E8h+P], rax
0x140009a30  lea     rcx, [rsp+0E8h+P]
0x140009a35  mov     [rax+8], rcx
0x140009a39  lea     rcx, [rsi+20h]; UnicodeString
0x140009a3d  call    cs:__imp_RtlFreeUnicodeString
0x140009a44  nop     dword ptr [rax+rax+00h]
0x140009a49  xor     edx, edx; Tag
0x140009a4b  mov     rcx, rsi; P
0x140009a4e  call    cs:__imp_ExFreePoolWithTag
0x140009a55  nop     dword ptr [rax+rax+00h]
0x140009a5a  jmp     short loc_140009A08
0x140009a5c  mov     ecx, 3
0x140009a61  int     29h; Win8: RtlFailFast(ecx)
0x140009a63  mov     rcx, [rsp+0E8h+var_78]; P
0x140009a68  test    rcx, rcx
0x140009a6b  jz      short loc_140009A74
0x140009a6d  xor     edx, edx
0x140009a6f  call    BfsDereferencePolicyEntryEx
0x140009a74  mov     rcx, qword ptr [rsp+0E8h+Size+4]; Object
0x140009a79  test    rcx, rcx
0x140009a7c  jz      short loc_140009A8A
0x140009a7e  call    cs:__imp_ObfDereferenceObject
0x140009a85  nop     dword ptr [rax+rax+00h]
0x140009a8a  mov     rcx, [rsp+0E8h+TokenInformation]; P
0x140009a8f  test    rcx, rcx
0x140009a92  jz      short loc_140009AA2
0x140009a94  xor     edx, edx; Tag
0x140009a96  call    cs:__imp_ExFreePoolWithTag
0x140009a9d  nop     dword ptr [rax+rax+00h]
0x140009aa2  mov     rcx, [rsp+0E8h+var_90]; P
0x140009aa7  test    rcx, rcx
0x140009aaa  jz      short loc_140009ABA
0x140009aac  xor     edx, edx; Tag
0x140009aae  call    cs:__imp_ExFreePoolWithTag
0x140009ab5  nop     dword ptr [rax+rax+00h]
0x140009aba  mov     eax, ebx
0x140009abc  jmp     short loc_140009AC5
0x140009abe  jmp     short loc_140009AC5
0x140009ac0  mov     eax, 0C000000Dh
0x140009ac5  mov     rcx, [rsp+0E8h+var_30]
0x140009acd  xor     rcx, rsp; StackCookie
0x140009ad0  call    __security_check_cookie
0x140009ad5  add     rsp, 0C0h
0x140009adc  pop     r15
0x140009ade  pop     r14
0x140009ae0  pop     r12
0x140009ae2  pop     rsi
0x140009ae3  pop     rbx
0x140009ae4  retn
```
