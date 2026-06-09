# AiLogSrpRuleEvent

- ea: `0x140031d90`
- end: `0x140032414`
- name: `AiLogSrpRuleEvent`
- size: `1668`
- prototype: `void __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, unsigned __int16 *, __int64 *, __int64 *, __int64 *, PCUNICODE_STRING String2, void *, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140031890`

## callees

- `0x140001970`
- `0x140001b3c`
- `0x140006a20`
- `0x140006c40`
- `0x140006f40`
- `0x14001fc80`
- `0x14001fe30`
- `0x140031d90`
- `0x140032980`
- `0x140032a50`
- `0x140035b60`
- `0x1400369f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140032395`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032395`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323dd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400320da`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032153`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400321d2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400320da`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140032153`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400321d2`
- `ntoskrnl!EtwWrite` at `0x140032333`
- `ntoskrnl!EtwWrite` at `0x140032333`
- `ntoskrnl!EtwEventEnabled` at `0x140031e29`
- `ntoskrnl!EtwEventEnabled` at `0x140031e29`
- `ntoskrnl!RtlLengthSid` at `0x140032054`
- `ntoskrnl!RtlLengthSid` at `0x140032054`

## pseudocode

```c
void __fastcall AiLogSrpRuleEvent(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        unsigned __int16 *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6,
        PCUNICODE_STRING String2,
        void *a8,
        char a9)
{
  UNICODE_STRING *v9; // rbx
  __int64 *v10; // rdi
  void *v13; // rsi
  int v14; // eax
  PWSTR v15; // r14
  char v16; // cl
  __int64 *v17; // rdi
  __int64 *v18; // rcx
  __int64 *v19; // rcx
  unsigned __int16 v20; // ax
  HANDLE v21; // rdi
  unsigned __int16 v22; // ax
  unsigned __int16 v23; // ax
  int UserSid; // eax
  int LogonId; // eax
  ULONG v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  const UNICODE_STRING *Buffer; // r9
  unsigned int v30; // eax
  PCUNICODE_STRING v31; // r9
  unsigned __int16 v32; // cx
  unsigned __int16 *v33; // rax
  unsigned int v34; // ecx
  __int16 v35; // cx
  __int64 v36; // rax
  unsigned int v37; // ecx
  BOOLEAN v38; // al
  unsigned __int16 v39; // cx
  unsigned __int64 v40; // r9
  __int16 v41; // cx
  __int64 v42; // rax
  NTSTATUS v43; // eax
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+28h] [rbp-D8h]
  __int64 v46; // [rsp+30h] [rbp-D0h]
  _WORD v47[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v48[2]; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v49; // [rsp+48h] [rbp-B8h] BYREF
  PCUNICODE_STRING String1; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v51; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v52; // [rsp+5Ch] [rbp-A4h] BYREF
  __int16 v53; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v54; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID P; // [rsp+68h] [rbp-98h]
  __int64 v56; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h]
  PVOID v58[2]; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v59; // [rsp+90h] [rbp-70h]
  __int64 *v60; // [rsp+98h] [rbp-68h]
  __int64 *v61; // [rsp+A0h] [rbp-60h]
  __int64 *v62; // [rsp+A8h] [rbp-58h]
  __int128 v63; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v64; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h]
  int v66; // [rsp+D8h] [rbp-28h]
  int v67; // [rsp+DCh] [rbp-24h]
  _QWORD v68[32]; // [rsp+E0h] [rbp-20h] BYREF

  TokenHandle = a8;
  v9 = 0;
  v60 = a4;
  v10 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v48[0] = 0;
  v13 = 0;
  v54 = 0;
  v49 = 0;
  v47[0] = 0;
  v56 = 0;
  v59 = a3;
  v63 = 0;
  String1 = 0;
  *(_OWORD *)v58 = 0;
  P = 0;
  if ( !EtwEventEnabled(RegHandle, EventDescriptor) )
  {
    v15 = (PWSTR)v58[1];
    goto LABEL_41;
  }
  v14 = AipNtPathToDosPath(String2);
  v15 = (PWSTR)v58[1];
  v16 = v14;
  if ( v14 < 0 )
    goto LABEL_37;
  v17 = &qword_140009420;
  v18 = &qword_140009420;
  if ( a5 )
    v18 = a5;
  v61 = v18;
  v19 = &qword_140009420;
  if ( a6 )
    v19 = a6;
  v62 = v19;
  memset(v68, 0, sizeof(v68));
  *(_QWORD *)&v64.Size = 2;
  v67 = 0;
  v20 = *v59;
  v66 = *v59;
  v51 = v20 >> 1;
  v64.Ptr = (ULONGLONG)&v51;
  v65 = *((_QWORD *)v59 + 1);
  if ( v60 )
    v17 = v60;
  if ( (int)AipGUIDFromString(v17, &v63) < 0 )
    v63 = 0;
  v21 = TokenHandle;
  v68[0] = &v63;
  v68[1] = 16;
  v22 = *(_WORD *)v61;
  v68[5] = *(unsigned __int16 *)v61;
  v52 = v22 >> 1;
  v68[2] = &v52;
  v68[4] = v61[1];
  v68[3] = 2;
  v23 = *(_WORD *)v62;
  v68[9] = *(unsigned __int16 *)v62;
  v53 = v23 >> 1;
  v68[6] = &v53;
  v68[8] = v62[1];
  v68[17] = LOWORD(v58[0]);
  v68[14] = v48;
  v48[0] = LOWORD(v58[0]) >> 1;
  v49 = 0;
  v68[18] = &v49;
  v47[0] = 1;
  v68[22] = v47;
  v54 = LOWORD(v58[0]) >> 1;
  v68[31] = LOWORD(v58[0]);
  v68[28] = &v54;
  v68[7] = 2;
  v68[15] = 2;
  v68[16] = v15;
  v68[19] = 2;
  v68[20] = L"-";
  v68[21] = 0;
  v68[23] = 2;
  v68[24] = L"-";
  v68[25] = 2;
  v68[29] = 2;
  v68[30] = v15;
  UserSid = AiQueryUserSid(TokenHandle);
  v16 = UserSid;
  if ( UserSid < 0 || (LogonId = AiQueryLogonId(v21), v16 = LogonId, LogonId < 0) )
  {
    v10 = (__int64 *)P;
LABEL_37:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_ZD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        (unsigned int)WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids,
        (_DWORD)String2,
        v16);
    goto LABEL_41;
  }
  v10 = (__int64 *)P;
  v26 = RtlLengthSid(*(PSID *)P);
  v27 = *v10;
  v68[11] = v26;
  v68[12] = &a9;
  v68[10] = v27;
  v68[26] = &v56;
  v68[13] = 4;
  v68[27] = 8;
  v28 = AiQueryTokenAttributes(TokenHandle, &String1);
  v9 = (UNICODE_STRING *)String1;
  v16 = v28;
  if ( v28 < 0 )
    goto LABEL_37;
  Buffer = (const UNICODE_STRING *)String1->Buffer;
  v30 = 0;
  while ( 1 )
  {
    String1 = Buffer;
    LODWORD(P) = v30;
    if ( v30 >= *(_DWORD *)(&v9->MaximumLength + 1) )
      break;
    if ( RtlEqualUnicodeString(Buffer, &stru_140009410, 1u) )
    {
      v31 = String1;
      if ( String1[1].Length == 3 )
      {
        if ( LODWORD(String1[1].Buffer) )
        {
          v32 = **(_WORD **)&String1[2].Length;
          v68[14] = v48;
          v68[15] = 2;
          v48[0] = v32 >> 1;
          v33 = *(unsigned __int16 **)&String1[2].Length;
          v34 = *v33;
          v68[16] = *((_QWORD *)v33 + 1);
          v68[17] = v34;
        }
      }
    }
    else if ( RtlEqualUnicodeString(String1, &stru_140009400, 1u) )
    {
      v31 = String1;
      if ( String1[1].Length == 16 && LODWORD(String1[1].Buffer) == 1 )
      {
        v35 = *(_WORD *)(*(_QWORD *)&String1[2].Length + 8LL);
        v68[18] = &v49;
        v49 = v35;
        v68[19] = 2;
        v36 = *(_QWORD *)&String1[2].Length;
        v37 = *(_DWORD *)(v36 + 8);
        v68[20] = *(_QWORD *)v36;
        v68[21] = v37;
      }
    }
    else
    {
      v38 = RtlEqualUnicodeString(String1, &stru_1400093F0, 1u);
      v31 = String1;
      if ( v38 )
      {
        if ( String1[1].Length == 4 && LODWORD(String1[1].Buffer) == 1 )
        {
          v39 = *(_WORD *)(*(_QWORD *)&String1[2].Length + 8LL);
          if ( (unsigned __int16)(v39 - 1) <= 0xFFCCu )
          {
            v47[0] = v39 >> 1;
            v13 = (void *)AiAlloc(*(unsigned __int16 *)(*(_QWORD *)&String1[2].Length + 8LL) + 50LL);
            if ( !v13 )
            {
              v16 = 23;
              goto LABEL_37;
            }
            memmove(
              v13,
              *(const void **)(*(_QWORD *)&String1[2].Length + 16LL),
              *(unsigned __int16 *)(*(_QWORD *)&String1[2].Length + 8LL));
            v40 = **(_QWORD **)&String1[2].Length;
            LODWORD(v46) = (unsigned __int16)v40;
            LODWORD(v45) = WORD1(v40);
            LODWORD(UserData) = WORD2(v40);
            RtlStringCbPrintfW(
              (NTSTRSAFE_PWSTR)v13 + v47[0],
              0x32u,
              L"\\%u.%u.%u.%02u",
              HIWORD(v40),
              UserData,
              v45,
              v46);
            v41 = v47[0];
            v42 = -1;
            do
              ++v42;
            while ( *((_WORD *)v13 + v47[0] + v42) );
            v31 = String1;
            v47[0] += v42;
            v68[25] = 2 * (unsigned int)(unsigned __int16)(v42 + v41);
            v68[22] = v47;
            v68[23] = 2;
            v68[24] = v13;
          }
        }
      }
    }
    v30 = (_DWORD)P + 1;
    Buffer = (PCUNICODE_STRING)((char *)v31 + 40);
  }
  v43 = EtwWrite(RegHandle, EventDescriptor, 0, 0x12u, &v64);
  v16 = v43;
  if ( v43 < 0 )
    goto LABEL_37;
LABEL_41:
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  if ( v15 != String2->Buffer && v15 )
    ExFreePoolWithTag(v15, 0);
}

```

## disassembly

```asm
0x140031d90  mov     [rsp-8+arg_10], rbx
0x140031d95  push    rbp
0x140031d96  push    rsi
0x140031d97  push    rdi
0x140031d98  push    r12
0x140031d9a  push    r13
0x140031d9c  push    r14
0x140031d9e  push    r15
0x140031da0  lea     rbp, [rsp-0F0h]
0x140031da8  sub     rsp, 1F0h
0x140031daf  mov     rax, cs:__security_cookie
0x140031db6  xor     rax, rsp
0x140031db9  mov     [rbp+120h+var_40], rax
0x140031dc0  mov     rax, [rbp+120h+arg_38]
0x140031dc7  xorps   xmm0, xmm0
0x140031dca  mov     r15, [rbp+120h+String2]
0x140031dd1  xorps   xmm1, xmm1
0x140031dd4  mov     [rsp+220h+TokenHandle], rax
0x140031dd9  xor     ebx, ebx
0x140031ddb  xor     eax, eax
0x140031ddd  mov     [rbp+120h+var_188], r9
0x140031de1  xor     edi, edi
0x140031de3  mov     [rsp+220h+var_1C8], ax
0x140031de8  mov     [rsp+220h+var_1C4], ax
0x140031ded  mov     r13, rdx
0x140031df0  mov     [rsp+220h+var_1C0], ax
0x140031df5  mov     r12, rcx
0x140031df8  mov     [rsp+220h+var_1DC], ax
0x140031dfd  xor     esi, esi
0x140031dff  mov     [rsp+220h+var_1BC], ax
0x140031e04  mov     [rsp+220h+var_1D8], ax
0x140031e09  mov     [rsp+220h+var_1E0], ax
0x140031e0e  mov     [rsp+220h+var_1B0], rax
0x140031e13  mov     [rbp+120h+var_190], r8
0x140031e17  movups  [rbp+120h+var_170], xmm0
0x140031e1b  mov     [rsp+220h+String1], rbx
0x140031e20  movups  xmmword ptr [rbp+120h+var_1A0], xmm1
0x140031e24  mov     [rsp+220h+P], rdi
0x140031e29  call    cs:__imp_EtwEventEnabled
0x140031e30  nop     dword ptr [rax+rax+00h]
0x140031e35  test    al, al
0x140031e37  jz      loc_140032387
0x140031e3d  lea     rdx, [rbp+120h+var_1A0]
0x140031e41  mov     rcx, r15; String2
0x140031e44  call    AipNtPathToDosPath
0x140031e49  mov     r14, [rbp+120h+var_1A0+8]
0x140031e4d  mov     ecx, eax
0x140031e4f  test    eax, eax
0x140031e51  js      loc_14003234C
0x140031e57  mov     rax, [rbp+120h+arg_20]
0x140031e5e  lea     rdi, qword_140009420
0x140031e65  test    rax, rax
0x140031e68  mov     rcx, rdi
0x140031e6b  mov     r8d, 100h; Size
0x140031e71  cmovnz  rcx, rax
0x140031e75  mov     rax, [rbp+120h+arg_28]
0x140031e7c  mov     [rbp+120h+var_180], rcx
0x140031e80  test    rax, rax
0x140031e83  mov     rcx, rdi
0x140031e86  cmovnz  rcx, rax
0x140031e8a  xor     edx, edx; Val
0x140031e8c  mov     [rbp+120h+var_178], rcx
0x140031e90  lea     rcx, [rbp+120h+var_140]; void *
0x140031e94  call    memset
0x140031e99  mov     rdx, [rbp+120h+var_190]
0x140031e9d  mov     qword ptr [rbp+120h+var_160.Size], 2
0x140031ea5  mov     [rbp+120h+var_144], ebx
0x140031ea8  movzx   ecx, word ptr [rdx]
0x140031eab  movzx   eax, cx
0x140031eae  mov     [rbp+120h+var_148], ecx
0x140031eb1  shr     ax, 1
0x140031eb4  mov     [rsp+220h+var_1C8], ax
0x140031eb9  lea     rax, [rsp+220h+var_1C8]
0x140031ebe  mov     [rbp+120h+var_160.Ptr], rax
0x140031ec2  mov     rax, [rdx+8]
0x140031ec6  lea     rdx, [rbp+120h+var_170]
0x140031eca  mov     [rbp+120h+var_150], rax
0x140031ece  mov     rax, [rbp+120h+var_188]
0x140031ed2  test    rax, rax
0x140031ed5  cmovnz  rdi, rax
0x140031ed9  mov     rcx, rdi
0x140031edc  call    AipGUIDFromString
0x140031ee1  test    eax, eax
0x140031ee3  jns     short loc_140031EEC
0x140031ee5  xorps   xmm0, xmm0
0x140031ee8  movups  [rbp+120h+var_170], xmm0
0x140031eec  mov     rdx, [rbp+120h+var_180]
0x140031ef0  lea     rax, [rbp+120h+var_170]
0x140031ef4  mov     rdi, [rsp+220h+TokenHandle]
0x140031ef9  lea     r8, asc_14000A410; "-"
0x140031f00  mov     [rbp+120h+var_140], rax
0x140031f04  mov     [rbp+120h+var_138], 10h
0x140031f0c  movzx   ecx, word ptr [rdx]
0x140031f0f  movzx   eax, cx
0x140031f12  mov     [rbp+120h+var_118], ecx
0x140031f15  shr     ax, 1
0x140031f18  mov     [rsp+220h+var_1C4], ax
0x140031f1d  lea     rax, [rsp+220h+var_1C4]
0x140031f22  mov     [rbp+120h+var_130], rax
0x140031f26  mov     rax, [rdx+8]
0x140031f2a  mov     rdx, [rbp+120h+var_178]
0x140031f2e  mov     [rbp+120h+var_120], rax
0x140031f32  mov     [rbp+120h+var_128], 2
0x140031f3a  mov     [rbp+120h+var_114], ebx
0x140031f3d  movzx   ecx, word ptr [rdx]
0x140031f40  movzx   eax, cx
0x140031f43  mov     [rbp+120h+var_F8], ecx
0x140031f46  shr     ax, 1
0x140031f49  lea     rcx, [rsp+220h+var_1DC]
0x140031f4e  mov     [rsp+220h+var_1C0], ax
0x140031f53  lea     rax, [rsp+220h+var_1C0]
0x140031f58  mov     [rbp+120h+var_110], rax
0x140031f5c  mov     rax, [rdx+8]
0x140031f60  mov     [rbp+120h+var_100], rax
0x140031f64  movzx   eax, word ptr [rbp+120h+var_1A0]
0x140031f68  movzx   edx, ax
0x140031f6b  mov     [rbp+120h+var_B8], eax
0x140031f6e  shr     dx, 1
0x140031f71  mov     [rbp+120h+var_D0], rcx
0x140031f75  mov     ecx, eax
0x140031f77  xor     eax, eax
0x140031f79  mov     [rsp+220h+var_1DC], dx
0x140031f7e  mov     [rsp+220h+var_1D8], ax
0x140031f83  lea     rax, [rsp+220h+var_1D8]
0x140031f88  mov     [rbp+120h+var_B0], rax
0x140031f8c  mov     eax, 1
0x140031f91  mov     [rsp+220h+var_1E0], ax
0x140031f96  lea     rax, [rsp+220h+var_1E0]
0x140031f9b  mov     [rbp+120h+var_90], rax
0x140031fa2  lea     rax, [rsp+220h+var_1BC]
0x140031fa7  mov     [rsp+220h+var_1BC], dx
0x140031fac  lea     rdx, [rsp+220h+P]
0x140031fb1  mov     [rbp+120h+var_48], ecx
0x140031fb7  mov     rcx, rdi; TokenHandle
0x140031fba  mov     [rbp+120h+var_60], rax
0x140031fc1  mov     [rbp+120h+var_108], 2
0x140031fc9  mov     [rbp+120h+var_F4], ebx
0x140031fcc  mov     [rbp+120h+var_C8], 2
0x140031fd4  mov     [rbp+120h+var_C0], r14
0x140031fd8  mov     [rbp+120h+var_B4], ebx
0x140031fdb  mov     [rbp+120h+var_A8], 2
0x140031fe3  mov     [rbp+120h+var_A0], r8
0x140031fea  mov     [rbp+120h+var_98], rbx
0x140031ff1  mov     [rbp+120h+var_88], 2
0x140031ffc  mov     [rbp+120h+var_80], r8
0x140032003  mov     [rbp+120h+var_78], 2
0x14003200e  mov     [rbp+120h+var_58], 2
0x140032019  mov     [rbp+120h+var_50], r14
0x140032020  mov     [rbp+120h+var_44], ebx
0x140032026  call    AiQueryUserSid
0x14003202b  mov     ecx, eax
0x14003202d  test    eax, eax
0x14003202f  js      loc_140032347
0x140032035  lea     rdx, [rsp+220h+var_1B0]
0x14003203a  mov     rcx, rdi; TokenHandle
0x14003203d  call    AiQueryLogonId
0x140032042  mov     ecx, eax
0x140032044  test    eax, eax
0x140032046  js      loc_140032347
0x14003204c  mov     rdi, [rsp+220h+P]
0x140032051  mov     rcx, [rdi]; Sid
0x140032054  call    cs:__imp_RtlLengthSid
0x14003205b  nop     dword ptr [rax+rax+00h]
0x140032060  mov     rcx, [rdi]
0x140032063  lea     rdx, [rsp+220h+String1]
0x140032068  mov     [rbp+120h+var_E8], eax
0x14003206b  lea     rax, [rbp+120h+arg_40]
0x140032072  mov     [rbp+120h+var_E0], rax
0x140032076  lea     rax, [rsp+220h+var_1B0]
0x14003207b  mov     [rbp+120h+var_F0], rcx
0x14003207f  mov     rcx, [rsp+220h+TokenHandle]
0x140032084  mov     [rbp+120h+var_70], rax
0x14003208b  mov     [rbp+120h+var_E4], ebx
0x14003208e  mov     [rbp+120h+var_D8], 4
0x140032096  mov     [rbp+120h+var_68], 8
0x1400320a1  call    AiQueryTokenAttributes
0x1400320a6  mov     rbx, [rsp+220h+String1]
0x1400320ab  mov     ecx, eax
0x1400320ad  test    eax, eax
0x1400320af  js      loc_14003234C
0x1400320b5  mov     r9, [rbx+8]
0x1400320b9  xor     eax, eax
0x1400320bb  mov     [rsp+220h+String1], r9
0x1400320c0  mov     dword ptr [rsp+220h+P], eax
0x1400320c4  cmp     eax, [rbx+4]
0x1400320c7  jnb     loc_14003231B
0x1400320cd  mov     r8b, 1; CaseInSensitive
0x1400320d0  lea     rdx, stru_140009410; String2
0x1400320d7  mov     rcx, r9; String1
0x1400320da  call    cs:__imp_RtlEqualUnicodeString
0x1400320e1  nop     dword ptr [rax+rax+00h]
0x1400320e6  test    al, al
0x1400320e8  jz      short loc_140032144
0x1400320ea  mov     r9, [rsp+220h+String1]
0x1400320ef  cmp     word ptr [r9+10h], 3
0x1400320f5  jnz     loc_140032305
0x1400320fb  cmp     dword ptr [r9+18h], 1
0x140032100  jb      loc_140032305
0x140032106  mov     rax, [r9+20h]
0x14003210a  movzx   ecx, word ptr [rax]
0x14003210d  lea     rax, [rsp+220h+var_1DC]
0x140032112  mov     [rbp+120h+var_D0], rax
0x140032116  mov     [rbp+120h+var_C8], 2
0x14003211e  shr     cx, 1
0x140032121  mov     [rsp+220h+var_1DC], cx
0x140032126  mov     rax, [r9+20h]
0x14003212a  movzx   ecx, word ptr [rax]
0x14003212d  mov     rax, [rax+8]
0x140032131  mov     [rbp+120h+var_C0], rax
0x140032135  mov     [rbp+120h+var_B8], ecx
0x140032138  mov     [rbp+120h+var_B4], 0
0x14003213f  jmp     loc_140032305
0x140032144  mov     rcx, [rsp+220h+String1]; String1
0x140032149  lea     rdx, stru_140009400; String2
0x140032150  mov     r8b, 1; CaseInSensitive
0x140032153  call    cs:__imp_RtlEqualUnicodeString
0x14003215a  nop     dword ptr [rax+rax+00h]
0x14003215f  test    al, al
0x140032161  jz      short loc_1400321C3
0x140032163  mov     r9, [rsp+220h+String1]
0x140032168  cmp     word ptr [r9+10h], 10h
0x14003216e  jnz     loc_140032305
0x140032174  cmp     dword ptr [r9+18h], 1
0x140032179  jnz     loc_140032305
0x14003217f  mov     rax, [r9+20h]
0x140032183  movzx   ecx, word ptr [rax+8]
0x140032187  lea     rax, [rsp+220h+var_1D8]
0x14003218c  mov     [rbp+120h+var_B0], rax
0x140032190  mov     [rsp+220h+var_1D8], cx
0x140032195  mov     [rbp+120h+var_A8], 2
0x14003219d  mov     rax, [r9+20h]
0x1400321a1  mov     ecx, [rax+8]
0x1400321a4  mov     rax, [rax]
0x1400321a7  mov     [rbp+120h+var_A0], rax
0x1400321ae  mov     dword ptr [rbp+120h+var_98], ecx
0x1400321b4  mov     dword ptr [rbp+120h+var_98+4], 0
0x1400321be  jmp     loc_140032305
0x1400321c3  mov     rcx, [rsp+220h+String1]; String1
0x1400321c8  lea     rdx, stru_1400093F0; String2
0x1400321cf  mov     r8b, 1; CaseInSensitive
0x1400321d2  call    cs:__imp_RtlEqualUnicodeString
0x1400321d9  nop     dword ptr [rax+rax+00h]
0x1400321de  mov     r9, [rsp+220h+String1]
0x1400321e3  test    al, al
0x1400321e5  jz      loc_140032305
0x1400321eb  cmp     word ptr [r9+10h], 4
0x1400321f1  jnz     loc_140032305
0x1400321f7  cmp     dword ptr [r9+18h], 1
0x1400321fc  jnz     loc_140032305
0x140032202  mov     rax, [r9+20h]
0x140032206  mov     edx, 0FFCCh
0x14003220b  movzx   ecx, word ptr [rax+8]
0x14003220f  lea     eax, [rcx-1]
0x140032212  cmp     ax, dx
0x140032215  ja      loc_140032305
0x14003221b  shr     cx, 1
0x14003221e  mov     [rsp+220h+var_1E0], cx
0x140032223  mov     rax, [r9+20h]
0x140032227  movzx   ecx, word ptr [rax+8]
0x14003222b  add     rcx, 32h ; '2'
0x14003222f  call    AiAlloc
0x140032234  mov     rsi, rax
0x140032237  test    rax, rax
0x14003223a  jz      loc_140032314
0x140032240  mov     rax, [rsp+220h+String1]
0x140032245  mov     rcx, rsi; void *
0x140032248  mov     rdx, [rax+20h]
0x14003224c  movzx   r8d, word ptr [rdx+8]; Size
0x140032251  mov     rdx, [rdx+10h]; Src
0x140032255  call    memmove
0x14003225a  mov     rax, [rsp+220h+String1]
0x14003225f  mov     rcx, [rax+20h]
0x140032263  mov     r9, [rcx]
0x140032266  mov     rax, r9
0x140032269  movzx   r10d, r9w
0x14003226d  shr     rax, 20h
0x140032271  mov     rcx, r9
0x140032274  movzx   edx, ax
0x140032277  movzx   eax, [rsp+220h+var_1E0]
0x14003227c  shr     rcx, 10h
0x140032280  movzx   r8d, cx
0x140032284  mov     [rsp+220h+var_1F0], r10d
0x140032289  mov     dword ptr [rsp+220h+var_1F8], r8d
0x14003228e  lea     rcx, [rsi+rax*2]; pszDest
0x140032292  mov     dword ptr [rsp+220h+UserData], edx
0x140032296  lea     r8, aUUU02u; "\\%u.%u.%u.%02u"
0x14003229d  shr     r9, 30h
0x1400322a1  mov     edx, 32h ; '2'; cbDest
0x1400322a6  call    RtlStringCbPrintfW
0x1400322ab  movzx   ecx, [rsp+220h+var_1E0]
0x1400322b0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400322b7  lea     rdx, [rsi+rcx*2]
0x1400322bb  inc     rax
0x1400322be  cmp     word ptr [rdx+rax*2], 0
0x1400322c3  jnz     short loc_1400322BB
0x1400322c5  mov     r9, [rsp+220h+String1]
0x1400322ca  add     cx, ax
0x1400322cd  movzx   eax, cx
0x1400322d0  mov     [rsp+220h+var_1E0], cx
0x1400322d5  add     eax, eax
  ... truncated ...
```
