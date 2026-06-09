# VfsMessageAddMappings

- ea: `0x140009784`
- end: `0x140009b06`
- name: `VfsMessageAddMappings`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008650`

## callees

- `0x140005674`
- `0x140005888`
- `0x1400059e8`
- `0x140008fb0`
- `0x140009368`
- `0x140009580`
- `0x140009784`
- `0x140009b0c`
- `0x140012828`
- `0x140012880`
- `0x14001295c`
- `0x140012acc`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140009830`
- `ntoskrnl!RtlLengthSid` at `0x140009830`

## string_xrefs

- `0x140009885`: `VfsMessageAddMappings() - Failed to get or create user context for user: %wZ\n Status: 0x%08X`
- `0x14000994d`: `VfsMessageAddMappings() - Failed to get or create package context for user: %wZ\n PackageId: %wZ\n VersionId: %wZ\n Status: 0x%08X`
- `0x140009a12`: `VfsMessageAddMappings() - Failed to create mapping from message for user: %wZ\n PackageId: %wZ\n VersionId: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsMessageAddMappings(__int64 a1, int a2)
{
  __int64 v3; // r13
  __int64 v4; // r14
  __int64 v5; // rcx
  unsigned int *v6; // rdi
  unsigned int v7; // ebx
  wchar_t *v8; // r15
  CLONG v9; // eax
  int Context; // esi
  __int64 v11; // rax
  struct _RTL_AVL_TABLE *v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  int inserted; // eax
  __int64 v20; // rax
  __int64 v22; // [rsp+20h] [rbp-C8h]
  __int64 v23; // [rsp+20h] [rbp-C8h]
  unsigned int v24; // [rsp+44h] [rbp-A4h] BYREF
  PSID Sid[2]; // [rsp+48h] [rbp-A0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+58h] [rbp-90h] BYREF
  __int64 v27; // [rsp+68h] [rbp-80h] BYREF
  __int64 v28; // [rsp+70h] [rbp-78h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-70h] BYREF
  unsigned int v30; // [rsp+88h] [rbp-60h]
  unsigned int *v31; // [rsp+90h] [rbp-58h]
  GUID Buffer; // [rsp+98h] [rbp-50h] BYREF
  GUID Guid; // [rsp+A8h] [rbp-40h] BYREF

  *(_QWORD *)&GuidString.Length = 0;
  v3 = 0;
  v27 = 0;
  v4 = 0;
  v28 = 0;
  Sid[0] = 0;
  Buffer = 0;
  Guid = 0;
  UnicodeString = 0;
  v24 = 0;
  if ( (int)VfsMessageCommonValidate(a1, a2, (unsigned int)&v24, (unsigned int)&Buffer, (__int64)Sid) < 0 )
    return 3221225485LL;
  v5 = *(unsigned __int16 *)(a1 + 20);
  if ( (unsigned int)v5 > v24 )
    return 3221225485LL;
  v6 = (unsigned int *)(v5 + a1 + 24);
  v7 = v24 - v5;
  v8 = (wchar_t *)Sid[0];
  if ( !Sid[0] )
  {
    v12 = &Table;
LABEL_8:
    Context = VfsCtxTableGetContext(v12, &Buffer, 0x20u, (__int64)&v27);
    if ( Context >= 0 )
    {
      v3 = v27;
      while ( 1 )
      {
        UnicodeString.Buffer = v8;
        Context = VfsCreateMappingEntryFromMessage(v6, v7, &UnicodeString, &GuidString);
        if ( Context < 0 )
          break;
        inserted = VfsInsertMappingEntry(v3 + 40, *(_QWORD *)&GuidString.Length);
        Context = inserted;
        if ( inserted < 0 )
        {
          if ( inserted == -1073741635 )
          {
            Context = 0;
          }
          else
          {
            LODWORD(v23) = inserted;
            LogWrite(
              1,
              0,
              L"VfsMessageAddMappings() - Failed to insert mapping for file: %wZ\n Status: 0x%08X",
              *(_QWORD *)(*(_QWORD *)&GuidString.Length + 40LL),
              v23);
          }
        }
        VfsReleaseMappingEntry(*(PVOID *)&GuidString.Length);
        if ( Context < 0 )
          goto LABEL_20;
        v20 = *v6;
        if ( !(_DWORD)v20 )
          goto LABEL_20;
        v7 -= v20;
        v30 = v7;
        v6 = (unsigned int *)((char *)v6 + v20);
        v31 = v6;
      }
      GuidString = 0;
      *(_OWORD *)Sid = 0;
      UnicodeString = 0;
      v16 = ConvertGuidToString(&Guid, &UnicodeString);
      v17 = ConvertGuidToString(&Buffer, (PUNICODE_STRING)Sid);
      v18 = ConvertSidToString(v8, &GuidString);
      LogWrite(
        1,
        0,
        L"VfsMessageAddMappings() - Failed to create mapping from message for user: %wZ\n"
         " PackageId: %wZ\n"
         " VersionId: %wZ\n"
         " Status: 0x%08X",
        v18,
        v17,
        v16,
        Context);
      FreeSidString(&UnicodeString);
      FreeSidString((PUNICODE_STRING)Sid);
      FreeSidString(&GuidString);
    }
    else
    {
      UnicodeString = 0;
      GuidString = 0;
      *(_OWORD *)Sid = 0;
      v13 = ConvertGuidToString(&Guid, (PUNICODE_STRING)Sid);
      v14 = ConvertGuidToString(&Buffer, &GuidString);
      v15 = ConvertSidToString(v8, &UnicodeString);
      LogWrite(
        1,
        0,
        L"VfsMessageAddMappings() - Failed to get or create package context for user: %wZ\n"
         " PackageId: %wZ\n"
         " VersionId: %wZ\n"
         " Status: 0x%08X",
        v15,
        v14,
        v13,
        Context);
      FreeSidString((PUNICODE_STRING)Sid);
      FreeSidString(&GuidString);
      FreeSidString(&UnicodeString);
      v3 = v27;
    }
    goto LABEL_20;
  }
  v9 = RtlLengthSid(Sid[0]);
  Context = VfsCtxTableGetContext(&stru_14001F470, v8, v9, (__int64)&v28);
  if ( Context >= 0 )
  {
    v4 = v28;
    v12 = (struct _RTL_AVL_TABLE *)(v28 + 96);
    goto LABEL_8;
  }
  *(_OWORD *)Sid = 0;
  v11 = ConvertSidToString(v8, (PUNICODE_STRING)Sid);
  LODWORD(v22) = Context;
  LogWrite(
    1,
    0,
    L"VfsMessageAddMappings() - Failed to get or create user context for user: %wZ\n Status: 0x%08X",
    v11,
    v22);
  FreeSidString((PUNICODE_STRING)Sid);
  v4 = v28;
LABEL_20:
  if ( v3 )
    VfsPkgCtxRelease(v3);
  if ( v4 )
    VfsUserCtxRelease(v4);
  return (unsigned int)Context;
}

```

## disassembly

```asm
0x140009784  mov     r11, rsp
0x140009787  mov     [r11+18h], rbx
0x14000978b  mov     [r11+20h], rsi
0x14000978f  push    rdi
0x140009790  push    r12
0x140009792  push    r13
0x140009794  push    r14
0x140009796  push    r15
0x140009798  sub     rsp, 0C0h
0x14000979f  mov     rax, cs:__security_cookie
0x1400097a6  xor     rax, rsp
0x1400097a9  mov     [rsp+0E8h+var_30], rax
0x1400097b1  mov     rdi, rcx
0x1400097b4  xor     esi, esi
0x1400097b6  mov     qword ptr [rsp+0E8h+GuidString.Length], rsi
0x1400097bb  mov     r13d, esi
0x1400097be  mov     [r11-80h], rsi
0x1400097c2  mov     r14d, esi
0x1400097c5  mov     [r11-78h], rsi
0x1400097c9  mov     [rsp+0E8h+Sid], rsi
0x1400097ce  xorps   xmm0, xmm0
0x1400097d1  movups  xmmword ptr [r11-50h], xmm0
0x1400097d6  movups  xmmword ptr [r11-40h], xmm0
0x1400097db  movups  xmmword ptr [rsp+0E8h+UnicodeString.Length], xmm0
0x1400097e0  mov     [rsp+0E8h+var_A4], esi
0x1400097e4  lea     rax, [rsp+0E8h+Sid]
0x1400097e9  mov     [rsp+0E8h+var_C8], rax
0x1400097ee  lea     r9, [r11-50h]
0x1400097f2  lea     r8, [rsp+0E8h+var_A4]
0x1400097f7  call    VfsMessageCommonValidate
0x1400097fc  test    eax, eax
0x1400097fe  js      loc_140009AD3
0x140009804  movzx   ecx, word ptr [rdi+14h]
0x140009808  mov     ebx, [rsp+0E8h+var_A4]
0x14000980c  cmp     ecx, ebx
0x14000980e  ja      loc_140009AD3
0x140009814  mov     eax, ecx
0x140009816  add     rdi, 18h
0x14000981a  add     rdi, rcx
0x14000981d  sub     ebx, ecx
0x14000981f  mov     r15, [rsp+0E8h+Sid]
0x140009824  test    r15, r15
0x140009827  jz      loc_1400098B5
0x14000982d  mov     rcx, r15; Sid
0x140009830  call    cs:__imp_RtlLengthSid
0x140009837  nop     dword ptr [rax+rax+00h]
0x14000983c  mov     r8d, eax; BufferSize
0x14000983f  lea     rax, [rsp+0E8h+var_78]
0x140009844  mov     [rsp+0E8h+var_C8], rax; __int64
0x140009849  lea     r12d, [rsi+1]
0x14000984d  mov     r9b, r12b
0x140009850  mov     rdx, r15; Buffer
0x140009853  lea     rcx, stru_14001F470; Table
0x14000985a  call    VfsCtxTableGetContext
0x14000985f  mov     esi, eax
0x140009861  mov     [rsp+0E8h+var_A8], eax
0x140009865  test    eax, eax
0x140009867  jns     short loc_1400098AA
0x140009869  xorps   xmm0, xmm0
0x14000986c  movups  xmmword ptr [rsp+0E8h+Sid], xmm0
0x140009871  lea     rdx, [rsp+0E8h+Sid]; UnicodeString
0x140009876  mov     rcx, r15; Sid
0x140009879  call    ConvertSidToString
0x14000987e  mov     r9, rax
0x140009881  mov     dword ptr [rsp+0E8h+var_C8], esi
0x140009885  lea     r8, aVfsmessageaddm_0; "VfsMessageAddMappings() - Failed to get"...
0x14000988c  xor     edx, edx
0x14000988e  mov     ecx, r12d
0x140009891  call    LogWrite
0x140009896  lea     rcx, [rsp+0E8h+Sid]; UnicodeString
0x14000989b  call    FreeSidString
0x1400098a0  mov     r14, [rsp+0E8h+var_78]
0x1400098a5  jmp     loc_140009AB5
0x1400098aa  mov     r14, [rsp+0E8h+var_78]
0x1400098af  lea     rcx, [r14+60h]
0x1400098b3  jmp     short loc_1400098C2
0x1400098b5  lea     rcx, Table; Table
0x1400098bc  mov     r12d, 1
0x1400098c2  lea     rax, [rsp+0E8h+var_80]
0x1400098c7  mov     [rsp+0E8h+var_C8], rax; __int64
0x1400098cc  mov     r9b, r12b
0x1400098cf  mov     r8d, 20h ; ' '; BufferSize
0x1400098d5  lea     rdx, [rsp+0E8h+Buffer]; Buffer
0x1400098dd  call    VfsCtxTableGetContext
0x1400098e2  mov     esi, eax
0x1400098e4  mov     [rsp+0E8h+var_A8], eax
0x1400098e8  test    eax, eax
0x1400098ea  jns     loc_140009986
0x1400098f0  xorps   xmm0, xmm0
0x1400098f3  movups  xmmword ptr [rsp+0E8h+UnicodeString.Length], xmm0
0x1400098f8  xorps   xmm1, xmm1
0x1400098fb  movups  xmmword ptr [rsp+0E8h+GuidString.Length], xmm1
0x140009900  movups  xmmword ptr [rsp+0E8h+Sid], xmm0
0x140009905  lea     rdx, [rsp+0E8h+Sid]; GuidString
0x14000990a  lea     rcx, [rsp+0E8h+Guid]; Guid
0x140009912  call    ConvertGuidToString
0x140009917  mov     rdi, rax
0x14000991a  lea     rdx, [rsp+0E8h+GuidString]; GuidString
0x14000991f  lea     rcx, [rsp+0E8h+Buffer]; Guid
0x140009927  call    ConvertGuidToString
0x14000992c  mov     rbx, rax
0x14000992f  lea     rdx, [rsp+0E8h+UnicodeString]; UnicodeString
0x140009934  mov     rcx, r15; Sid
0x140009937  call    ConvertSidToString
0x14000993c  mov     r9, rax
0x14000993f  mov     [rsp+0E8h+var_B8], esi
0x140009943  mov     [rsp+0E8h+var_C0], rdi
0x140009948  mov     [rsp+0E8h+var_C8], rbx
0x14000994d  lea     r8, aVfsmessageaddm_2; "VfsMessageAddMappings() - Failed to get"...
0x140009954  xor     edx, edx
0x140009956  mov     ecx, r12d
0x140009959  call    LogWrite
0x14000995e  lea     rcx, [rsp+0E8h+Sid]; UnicodeString
0x140009963  call    FreeSidString
0x140009968  lea     rcx, [rsp+0E8h+GuidString]; UnicodeString
0x14000996d  call    FreeSidString
0x140009972  lea     rcx, [rsp+0E8h+UnicodeString]; UnicodeString
0x140009977  call    FreeSidString
0x14000997c  mov     r13, [rsp+0E8h+var_80]
0x140009981  jmp     loc_140009AB5
0x140009986  mov     r13, [rsp+0E8h+var_80]
0x14000998b  mov     [rsp+0E8h+UnicodeString.Buffer], r15
0x140009993  lea     r9, [rsp+0E8h+GuidString]
0x140009998  lea     r8, [rsp+0E8h+UnicodeString]
0x14000999d  mov     edx, ebx
0x14000999f  mov     rcx, rdi
0x1400099a2  call    VfsCreateMappingEntryFromMessage
0x1400099a7  mov     esi, eax
0x1400099a9  mov     [rsp+0E8h+var_A8], eax
0x1400099ad  test    eax, eax
0x1400099af  jns     loc_140009A43
0x1400099b5  xorps   xmm0, xmm0
0x1400099b8  movups  xmmword ptr [rsp+0E8h+GuidString.Length], xmm0
0x1400099bd  xorps   xmm1, xmm1
0x1400099c0  movups  xmmword ptr [rsp+0E8h+Sid], xmm1
0x1400099c5  movups  xmmword ptr [rsp+0E8h+UnicodeString.Length], xmm0
0x1400099ca  lea     rdx, [rsp+0E8h+UnicodeString]; GuidString
0x1400099cf  lea     rcx, [rsp+0E8h+Guid]; Guid
0x1400099d7  call    ConvertGuidToString
0x1400099dc  mov     rdi, rax
0x1400099df  lea     rdx, [rsp+0E8h+Sid]; GuidString
0x1400099e4  lea     rcx, [rsp+0E8h+Buffer]; Guid
0x1400099ec  call    ConvertGuidToString
0x1400099f1  mov     rbx, rax
0x1400099f4  lea     rdx, [rsp+0E8h+GuidString]; UnicodeString
0x1400099f9  mov     rcx, r15; Sid
0x1400099fc  call    ConvertSidToString
0x140009a01  mov     r9, rax
0x140009a04  mov     [rsp+0E8h+var_B8], esi
0x140009a08  mov     [rsp+0E8h+var_C0], rdi
0x140009a0d  mov     [rsp+0E8h+var_C8], rbx
0x140009a12  lea     r8, aVfsmessageaddm_1; "VfsMessageAddMappings() - Failed to cre"...
0x140009a19  xor     edx, edx
0x140009a1b  mov     ecx, r12d
0x140009a1e  call    LogWrite
0x140009a23  lea     rcx, [rsp+0E8h+UnicodeString]; UnicodeString
0x140009a28  call    FreeSidString
0x140009a2d  lea     rcx, [rsp+0E8h+Sid]; UnicodeString
0x140009a32  call    FreeSidString
0x140009a37  lea     rcx, [rsp+0E8h+GuidString]; UnicodeString
0x140009a3c  call    FreeSidString
0x140009a41  jmp     short loc_140009AB5
0x140009a43  mov     rdx, qword ptr [rsp+0E8h+GuidString.Length]
0x140009a48  lea     rcx, [r13+28h]
0x140009a4c  call    VfsInsertMappingEntry
0x140009a51  mov     esi, eax
0x140009a53  mov     [rsp+0E8h+var_A8], eax
0x140009a57  test    eax, eax
0x140009a59  jns     short loc_140009A88
0x140009a5b  cmp     eax, 0C00000BDh
0x140009a60  jnz     short loc_140009A6A
0x140009a62  xor     esi, esi
0x140009a64  mov     [rsp+0E8h+var_A8], esi
0x140009a68  jmp     short loc_140009A88
0x140009a6a  mov     dword ptr [rsp+0E8h+var_C8], eax
0x140009a6e  mov     rax, qword ptr [rsp+0E8h+GuidString.Length]
0x140009a73  mov     r9, [rax+28h]
0x140009a77  lea     r8, aVfsmessageaddm; "VfsMessageAddMappings() - Failed to ins"...
0x140009a7e  xor     edx, edx
0x140009a80  mov     ecx, r12d
0x140009a83  call    LogWrite
0x140009a88  mov     rcx, qword ptr [rsp+0E8h+GuidString.Length]; P
0x140009a8d  call    VfsReleaseMappingEntry
0x140009a92  test    esi, esi
0x140009a94  js      short loc_140009AB5
0x140009a96  mov     eax, [rdi]
0x140009a98  test    eax, eax
0x140009a9a  jz      short loc_140009AB5
0x140009a9c  sub     ebx, eax
0x140009a9e  mov     [rsp+0E8h+var_60], ebx
0x140009aa5  add     rdi, rax
0x140009aa8  mov     [rsp+0E8h+var_58], rdi
0x140009ab0  jmp     loc_14000998B
0x140009ab5  test    r13, r13
0x140009ab8  jz      short loc_140009AC2
0x140009aba  mov     rcx, r13
0x140009abd  call    VfsPkgCtxRelease
0x140009ac2  test    r14, r14
0x140009ac5  jz      short loc_140009ACF
0x140009ac7  mov     rcx, r14
0x140009aca  call    VfsUserCtxRelease
0x140009acf  mov     eax, esi
0x140009ad1  jmp     short loc_140009AD8
0x140009ad3  mov     eax, 0C000000Dh
0x140009ad8  mov     rcx, [rsp+0E8h+var_30]
0x140009ae0  xor     rcx, rsp; StackCookie
0x140009ae3  call    __security_check_cookie
0x140009ae8  lea     r11, [rsp+0E8h+var_28]
0x140009af0  mov     rbx, [r11+40h]
0x140009af4  mov     rsi, [r11+48h]
0x140009af8  mov     rsp, r11
0x140009afb  pop     r15
0x140009afd  pop     r14
0x140009aff  pop     r13
0x140009b01  pop     r12
0x140009b03  pop     rdi
0x140009b04  retn
0x140014db4  push    rbp
0x140014db6  sub     rsp, 40h
0x140014dba  mov     rbp, rdx
0x140014dbd  mov     rcx, [rbp+68h]
0x140014dc1  test    rcx, rcx
0x140014dc4  jz      short loc_140014DCC
0x140014dc6  call    VfsPkgCtxRelease
0x140014dcb  nop
0x140014dcc  mov     rcx, [rbp+70h]
0x140014dd0  test    rcx, rcx
0x140014dd3  jz      short loc_140014DDB
0x140014dd5  call    VfsUserCtxRelease
0x140014dda  nop
0x140014ddb  add     rsp, 40h
0x140014ddf  pop     rbp
0x140014de0  retn
```
