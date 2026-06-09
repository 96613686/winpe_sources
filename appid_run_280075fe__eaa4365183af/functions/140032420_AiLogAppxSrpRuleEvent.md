# AiLogAppxSrpRuleEvent

- ea: `0x140032420`
- end: `0x14003289b`
- name: `AiLogAppxSrpRuleEvent`
- size: `1147`
- prototype: `__int64 __usercall@<rax>(REGHANDLE RegHandle@<rcx>, PCEVENT_DESCRIPTOR EventDescriptor@<rdx>, __int64, __int64, __int64, HANDLE TokenHandle, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140031890`

## callees

- `0x140001970`
- `0x140001b3c`
- `0x140006a20`
- `0x140006c40`
- `0x140006f40`
- `0x14001fe30`
- `0x140032420`
- `0x140032980`
- `0x140032a50`
- `0x140035b60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003283b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032851`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003283b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032851`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032867`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400326a2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400326a2`
- `ntoskrnl!EtwWrite` at `0x1400327e6`
- `ntoskrnl!EtwWrite` at `0x1400327e6`
- `ntoskrnl!EtwEventEnabled` at `0x14003249c`
- `ntoskrnl!EtwEventEnabled` at `0x14003249c`
- `ntoskrnl!RtlLengthSid` at `0x14003263a`
- `ntoskrnl!RtlLengthSid` at `0x14003263a`

## pseudocode

```c
void __fastcall AiLogAppxSrpRuleEvent(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        unsigned __int16 *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6,
        unsigned __int16 *a7,
        HANDLE TokenHandle,
        char a9)
{
  _DWORD *v9; // rbx
  PSID *v10; // rdi
  wchar_t *v14; // rsi
  __int64 *v15; // rdi
  __int64 *v16; // rcx
  __int64 *v17; // rcx
  unsigned __int16 v18; // ax
  int v19; // r13d
  unsigned __int16 v20; // ax
  unsigned __int16 v21; // ax
  unsigned int v22; // ecx
  int UserSid; // eax
  char v24; // cl
  ULONG v25; // eax
  PSID v26; // rcx
  int v27; // eax
  __int64 v28; // r12
  unsigned int v29; // eax
  unsigned __int16 v30; // cx
  wchar_t *v31; // rax
  unsigned __int64 v32; // r9
  __int16 v33; // cx
  __int64 v34; // rax
  NTSTATUS v35; // eax
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+28h] [rbp-D8h]
  __int64 v38; // [rsp+30h] [rbp-D0h]
  _WORD v39[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v40; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v41; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v42; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v43; // [rsp+50h] [rbp-B0h] BYREF
  PSID *v44; // [rsp+58h] [rbp-A8h]
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v46; // [rsp+68h] [rbp-98h]
  __int64 *v47; // [rsp+70h] [rbp-90h]
  __int64 *v48; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v49; // [rsp+80h] [rbp-80h]
  __int128 v50; // [rsp+88h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h]
  int v53; // [rsp+B8h] [rbp-48h]
  int v54; // [rsp+BCh] [rbp-44h]
  _QWORD v55[22]; // [rsp+C0h] [rbp-40h] BYREF

  v9 = 0;
  v49 = a7;
  v10 = 0;
  v46 = a4;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v14 = 0;
  v39[0] = 0;
  v50 = 0;
  v45 = 0;
  v44 = 0;
  if ( EtwEventEnabled(RegHandle, EventDescriptor) )
  {
    v15 = &qword_140009440;
    v16 = &qword_140009440;
    if ( a5 )
      v16 = a5;
    v47 = v16;
    v17 = &qword_140009440;
    if ( a6 )
      v17 = a6;
    v48 = v17;
    memset(v55, 0, sizeof(v55));
    v18 = *a3;
    v53 = *a3;
    v40 = v18 >> 1;
    v51.Ptr = (ULONGLONG)&v40;
    v52 = *((_QWORD *)a3 + 1);
    *(_QWORD *)&v51.Size = 2;
    v54 = 0;
    if ( v46 )
      v15 = v46;
    if ( (int)AipGUIDFromString(v15, &v50) < 0 )
      v50 = 0;
    v19 = (int)v49;
    v55[0] = &v50;
    v55[1] = 16;
    v20 = *(_WORD *)v47;
    v55[5] = *(unsigned __int16 *)v47;
    v41 = v20 >> 1;
    v55[2] = &v41;
    v55[4] = v47[1];
    v55[3] = 2;
    v21 = *(_WORD *)v48;
    v55[9] = *(unsigned __int16 *)v48;
    v22 = *v49;
    v42 = v21 >> 1;
    v55[6] = &v42;
    v55[8] = v48[1];
    v43 = (unsigned __int16)v22 >> 1;
    v55[14] = &v43;
    v55[16] = *((_QWORD *)v49 + 1);
    v39[0] = 1;
    v55[18] = v39;
    v55[17] = v22;
    v55[20] = L"-";
    v55[7] = 2;
    v55[15] = 2;
    v55[19] = 2;
    v55[21] = 2;
    UserSid = AiQueryUserSid(TokenHandle);
    v10 = v44;
    v24 = UserSid;
    if ( UserSid < 0 )
      goto LABEL_25;
    v25 = RtlLengthSid(*v44);
    v26 = *v10;
    v55[11] = v25;
    v55[10] = v26;
    v55[12] = &a9;
    v55[13] = 4;
    v27 = AiQueryTokenAttributes(TokenHandle, &v45);
    v9 = (_DWORD *)v45;
    v24 = v27;
    if ( v27 < 0 )
      goto LABEL_25;
    v28 = *(_QWORD *)(v45 + 8);
    v29 = 0;
    while ( 1 )
    {
      LODWORD(v44) = v29;
      if ( v29 >= v9[1] )
        break;
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)v28, &stru_140009430, 1u) )
      {
        if ( *(_WORD *)(v28 + 16) == 4 && *(_DWORD *)(v28 + 24) == 1 )
        {
          v30 = *(_WORD *)(*(_QWORD *)(v28 + 32) + 8LL);
          if ( (unsigned __int16)(v30 - 1) <= 0xFFCCu )
          {
            v39[0] = v30 >> 1;
            v31 = (wchar_t *)AiAlloc(*(unsigned __int16 *)(*(_QWORD *)(v28 + 32) + 8LL) + 50LL);
            v14 = v31;
            if ( !v31 )
            {
              v24 = 23;
              goto LABEL_25;
            }
            memmove(
              v31,
              *(const void **)(*(_QWORD *)(v28 + 32) + 16LL),
              *(unsigned __int16 *)(*(_QWORD *)(v28 + 32) + 8LL));
            v32 = **(_QWORD **)(v28 + 32);
            LODWORD(v38) = (unsigned __int16)v32;
            LODWORD(v37) = WORD1(v32);
            LODWORD(UserData) = WORD2(v32);
            RtlStringCbPrintfW(&v14[v39[0]], 0x32u, L"\\%u.%u.%u.%02u", HIWORD(v32), UserData, v37, v38);
            v33 = v39[0];
            v34 = -1;
            do
              ++v34;
            while ( v14[v39[0] + v34] );
            v55[19] = 2;
            v39[0] += v34;
            v55[21] = 2 * (unsigned int)(unsigned __int16)(v34 + v33);
            v55[18] = v39;
            v55[20] = v14;
          }
        }
      }
      v29 = (_DWORD)v44 + 1;
      v28 += 40;
    }
    v35 = EtwWrite(RegHandle, EventDescriptor, 0, 0xDu, &v51);
    v24 = v35;
    if ( v35 < 0 )
    {
LABEL_25:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_ZD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          (unsigned int)WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids,
          v19,
          v24);
      }
    }
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
}

```

## disassembly

```asm
0x140032420  mov     [rsp-8+arg_10], rbx
0x140032425  push    rbp
0x140032426  push    rsi
0x140032427  push    rdi
0x140032428  push    r12
0x14003242a  push    r13
0x14003242c  push    r14
0x14003242e  push    r15
0x140032430  lea     rbp, [rsp-80h]
0x140032435  sub     rsp, 180h
0x14003243c  mov     rax, cs:__security_cookie
0x140032443  xor     rax, rsp
0x140032446  mov     [rbp+0B0h+var_40], rax
0x14003244a  mov     rax, [rbp+0B0h+arg_30]
0x140032451  xorps   xmm0, xmm0
0x140032454  mov     r12, [rbp+0B0h+TokenHandle]
0x14003245b  xor     ebx, ebx
0x14003245d  mov     [rbp+0B0h+var_130], rax
0x140032461  xor     edi, edi
0x140032463  xor     eax, eax
0x140032465  mov     [rsp+1B0h+var_148], r9
0x14003246a  mov     [rsp+1B0h+var_16C], ax
0x14003246f  mov     r13, r8
0x140032472  mov     [rsp+1B0h+var_168], ax
0x140032477  mov     r15, rdx
0x14003247a  mov     [rsp+1B0h+var_164], ax
0x14003247f  mov     r14, rcx
0x140032482  mov     [rsp+1B0h+var_160], ax
0x140032487  xor     esi, esi
0x140032489  mov     [rsp+1B0h+var_170], ax
0x14003248e  movups  [rbp+0B0h+var_128], xmm0
0x140032492  mov     [rsp+1B0h+var_150], rbx
0x140032497  mov     [rsp+1B0h+var_158], rdi
0x14003249c  call    cs:__imp_EtwEventEnabled
0x1400324a3  nop     dword ptr [rax+rax+00h]
0x1400324a8  test    al, al
0x1400324aa  jz      loc_140032831
0x1400324b0  mov     rax, [rbp+0B0h+arg_20]
0x1400324b7  lea     rdi, qword_140009440
0x1400324be  test    rax, rax
0x1400324c1  mov     rcx, rdi
0x1400324c4  mov     r8d, 0B0h; Size
0x1400324ca  cmovnz  rcx, rax
0x1400324ce  mov     rax, [rbp+0B0h+arg_28]
0x1400324d5  mov     [rsp+1B0h+var_140], rcx
0x1400324da  test    rax, rax
0x1400324dd  mov     rcx, rdi
0x1400324e0  cmovnz  rcx, rax
0x1400324e4  xor     edx, edx; Val
0x1400324e6  mov     [rsp+1B0h+var_138], rcx
0x1400324eb  lea     rcx, [rbp+0B0h+var_F0]; void *
0x1400324ef  call    memset
0x1400324f4  movzx   ecx, word ptr [r13+0]
0x1400324f9  lea     rdx, [rbp+0B0h+var_128]
0x1400324fd  movzx   eax, cx
0x140032500  mov     [rbp+0B0h+var_F8], ecx
0x140032503  shr     ax, 1
0x140032506  mov     [rsp+1B0h+var_16C], ax
0x14003250b  lea     rax, [rsp+1B0h+var_16C]
0x140032510  mov     [rbp+0B0h+var_110.Ptr], rax
0x140032514  mov     rax, [r13+8]
0x140032518  mov     [rbp+0B0h+var_100], rax
0x14003251c  mov     rax, [rsp+1B0h+var_148]
0x140032521  test    rax, rax
0x140032524  mov     qword ptr [rbp+0B0h+var_110.Size], 2
0x14003252c  mov     [rbp+0B0h+var_F4], ebx
0x14003252f  cmovnz  rdi, rax
0x140032533  mov     rcx, rdi
0x140032536  call    AipGUIDFromString
0x14003253b  test    eax, eax
0x14003253d  jns     short loc_140032546
0x14003253f  xorps   xmm0, xmm0
0x140032542  movups  [rbp+0B0h+var_128], xmm0
0x140032546  mov     rdx, [rsp+1B0h+var_140]
0x14003254b  lea     rax, [rbp+0B0h+var_128]
0x14003254f  mov     r13, [rbp+0B0h+var_130]
0x140032553  mov     [rbp+0B0h+var_F0], rax
0x140032557  mov     [rbp+0B0h+var_E8], 10h
0x14003255f  movzx   ecx, word ptr [rdx]
0x140032562  movzx   eax, cx
0x140032565  mov     [rbp+0B0h+var_C8], ecx
0x140032568  shr     ax, 1
0x14003256b  mov     [rsp+1B0h+var_168], ax
0x140032570  lea     rax, [rsp+1B0h+var_168]
0x140032575  mov     [rbp+0B0h+var_E0], rax
0x140032579  mov     rax, [rdx+8]
0x14003257d  mov     rdx, [rsp+1B0h+var_138]
0x140032582  mov     [rbp+0B0h+var_D0], rax
0x140032586  mov     [rbp+0B0h+var_D8], 2
0x14003258e  mov     [rbp+0B0h+var_C4], ebx
0x140032591  movzx   ecx, word ptr [rdx]
0x140032594  movzx   eax, cx
0x140032597  mov     [rbp+0B0h+var_A8], ecx
0x14003259a  movzx   ecx, word ptr [r13+0]
0x14003259f  shr     ax, 1
0x1400325a2  mov     [rsp+1B0h+var_164], ax
0x1400325a7  lea     rax, [rsp+1B0h+var_164]
0x1400325ac  mov     [rbp+0B0h+var_C0], rax
0x1400325b0  mov     rax, [rdx+8]
0x1400325b4  lea     rdx, [rsp+1B0h+var_158]
0x1400325b9  mov     [rbp+0B0h+var_B0], rax
0x1400325bd  movzx   eax, cx
0x1400325c0  shr     ax, 1
0x1400325c3  mov     [rsp+1B0h+var_160], ax
0x1400325c8  lea     rax, [rsp+1B0h+var_160]
0x1400325cd  mov     [rbp+0B0h+var_80], rax
0x1400325d1  mov     rax, [r13+8]
0x1400325d5  mov     [rbp+0B0h+var_70], rax
0x1400325d9  mov     eax, 1
0x1400325de  mov     [rsp+1B0h+var_170], ax
0x1400325e3  lea     rax, [rsp+1B0h+var_170]
0x1400325e8  mov     [rbp+0B0h+var_60], rax
0x1400325ec  lea     rax, asc_14000A410; "-"
0x1400325f3  mov     [rbp+0B0h+var_68], ecx
0x1400325f6  mov     rcx, r12; TokenHandle
0x1400325f9  mov     [rbp+0B0h+var_50], rax
0x1400325fd  mov     [rbp+0B0h+var_B8], 2
0x140032605  mov     [rbp+0B0h+var_A4], ebx
0x140032608  mov     [rbp+0B0h+var_78], 2
0x140032610  mov     [rbp+0B0h+var_64], ebx
0x140032613  mov     [rbp+0B0h+var_58], 2
0x14003261b  mov     [rbp+0B0h+var_48], 2
0x140032623  call    AiQueryUserSid
0x140032628  mov     rdi, [rsp+1B0h+var_158]
0x14003262d  mov     ecx, eax
0x14003262f  test    eax, eax
0x140032631  js      loc_1400327F8
0x140032637  mov     rcx, [rdi]; Sid
0x14003263a  call    cs:__imp_RtlLengthSid
0x140032641  nop     dword ptr [rax+rax+00h]
0x140032646  mov     rcx, [rdi]
0x140032649  lea     rdx, [rsp+1B0h+var_150]
0x14003264e  mov     [rbp+0B0h+var_98], eax
0x140032651  lea     rax, [rbp+0B0h+arg_40]
0x140032658  mov     [rbp+0B0h+var_A0], rcx
0x14003265c  mov     rcx, r12
0x14003265f  mov     [rbp+0B0h+var_90], rax
0x140032663  mov     [rbp+0B0h+var_94], ebx
0x140032666  mov     [rbp+0B0h+var_88], 4
0x14003266e  call    AiQueryTokenAttributes
0x140032673  mov     rbx, [rsp+1B0h+var_150]
0x140032678  mov     ecx, eax
0x14003267a  test    eax, eax
0x14003267c  js      loc_1400327F8
0x140032682  mov     r12, [rbx+8]
0x140032686  xor     eax, eax
0x140032688  mov     dword ptr [rsp+1B0h+var_158], eax
0x14003268c  cmp     eax, [rbx+4]
0x14003268f  jnb     loc_1400327CE
0x140032695  mov     r8b, 1; CaseInSensitive
0x140032698  lea     rdx, stru_140009430; String2
0x14003269f  mov     rcx, r12; String1
0x1400326a2  call    cs:__imp_RtlEqualUnicodeString
0x1400326a9  nop     dword ptr [rax+rax+00h]
0x1400326ae  test    al, al
0x1400326b0  jz      loc_1400327B8
0x1400326b6  cmp     word ptr [r12+10h], 4
0x1400326bd  jnz     loc_1400327B8
0x1400326c3  cmp     dword ptr [r12+18h], 1
0x1400326c9  jnz     loc_1400327B8
0x1400326cf  mov     rax, [r12+20h]
0x1400326d4  mov     edx, 0FFCCh
0x1400326d9  movzx   ecx, word ptr [rax+8]
0x1400326dd  lea     eax, [rcx-1]
0x1400326e0  cmp     ax, dx
0x1400326e3  ja      loc_1400327B8
0x1400326e9  shr     cx, 1
0x1400326ec  mov     [rsp+1B0h+var_170], cx
0x1400326f1  mov     rax, [r12+20h]
0x1400326f6  movzx   ecx, word ptr [rax+8]
0x1400326fa  add     rcx, 32h ; '2'
0x1400326fe  call    AiAlloc
0x140032703  mov     rsi, rax
0x140032706  test    rax, rax
0x140032709  jz      loc_1400327C7
0x14003270f  mov     rdx, [r12+20h]
0x140032714  mov     rcx, rax; void *
0x140032717  movzx   r8d, word ptr [rdx+8]; Size
0x14003271c  mov     rdx, [rdx+10h]; Src
0x140032720  call    memmove
0x140032725  mov     rcx, [r12+20h]
0x14003272a  mov     r9, [rcx]
0x14003272d  mov     rax, r9
0x140032730  movzx   r10d, r9w
0x140032734  shr     rax, 20h
0x140032738  mov     rcx, r9
0x14003273b  movzx   edx, ax
0x14003273e  movzx   eax, [rsp+1B0h+var_170]
0x140032743  shr     rcx, 10h
0x140032747  movzx   r8d, cx
0x14003274b  mov     [rsp+1B0h+var_180], r10d
0x140032750  mov     dword ptr [rsp+1B0h+var_188], r8d
0x140032755  lea     rcx, [rsi+rax*2]; pszDest
0x140032759  mov     dword ptr [rsp+1B0h+UserData], edx
0x14003275d  lea     r8, aUUU02u; "\\%u.%u.%u.%02u"
0x140032764  shr     r9, 30h
0x140032768  mov     edx, 32h ; '2'; cbDest
0x14003276d  call    RtlStringCbPrintfW
0x140032772  movzx   ecx, [rsp+1B0h+var_170]
0x140032777  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14003277e  lea     rdx, [rsi+rcx*2]
0x140032782  inc     rax
0x140032785  cmp     word ptr [rdx+rax*2], 0
0x14003278a  jnz     short loc_140032782
0x14003278c  add     cx, ax
0x14003278f  mov     [rbp+0B0h+var_58], 2
0x140032797  movzx   eax, cx
0x14003279a  mov     [rsp+1B0h+var_170], cx
0x14003279f  add     eax, eax
0x1400327a1  lea     rcx, [rsp+1B0h+var_170]
0x1400327a6  mov     dword ptr [rbp+0B0h+var_48], eax
0x1400327a9  mov     [rbp+0B0h+var_60], rcx
0x1400327ad  mov     [rbp+0B0h+var_50], rsi
0x1400327b1  mov     dword ptr [rbp+0B0h+var_48+4], 0
0x1400327b8  mov     eax, dword ptr [rsp+1B0h+var_158]
0x1400327bc  inc     eax
0x1400327be  add     r12, 28h ; '('
0x1400327c2  jmp     loc_140032688
0x1400327c7  mov     ecx, 0C0000017h
0x1400327cc  jmp     short loc_1400327F8
0x1400327ce  lea     rax, [rbp+0B0h+var_110]
0x1400327d2  mov     r9d, 0Dh; UserDataCount
0x1400327d8  xor     r8d, r8d; ActivityId
0x1400327db  mov     [rsp+1B0h+UserData], rax; UserData
0x1400327e0  mov     rdx, r15; EventDescriptor
0x1400327e3  mov     rcx, r14; RegHandle
0x1400327e6  call    cs:__imp_EtwWrite
0x1400327ed  nop     dword ptr [rax+rax+00h]
0x1400327f2  mov     ecx, eax
0x1400327f4  test    eax, eax
0x1400327f6  jns     short loc_140032831
0x1400327f8  mov     r10, cs:WPP_GLOBAL_Control
0x1400327ff  lea     rax, WPP_GLOBAL_Control
0x140032806  cmp     r10, rax
0x140032809  jz      short loc_140032831
0x14003280b  test    dword ptr [r10+2Ch], 200h
0x140032813  jz      short loc_140032831
0x140032815  mov     dword ptr [rsp+1B0h+UserData], ecx
0x140032819  lea     r8, WPP_ba82aeedd69c3fe8448d5535e4644288_Traceguids
0x140032820  mov     rcx, [r10+18h]
0x140032824  mov     edx, 10h
0x140032829  mov     r9, r13
0x14003282c  call    WPP_SF_ZD
0x140032831  test    rdi, rdi
0x140032834  jz      short loc_140032847
0x140032836  xor     edx, edx; Tag
0x140032838  mov     rcx, rdi; P
0x14003283b  call    cs:__imp_ExFreePoolWithTag
0x140032842  nop     dword ptr [rax+rax+00h]
0x140032847  test    rbx, rbx
0x14003284a  jz      short loc_14003285D
0x14003284c  xor     edx, edx; Tag
0x14003284e  mov     rcx, rbx; P
0x140032851  call    cs:__imp_ExFreePoolWithTag
0x140032858  nop     dword ptr [rax+rax+00h]
0x14003285d  test    rsi, rsi
0x140032860  jz      short loc_140032873
0x140032862  xor     edx, edx; Tag
0x140032864  mov     rcx, rsi; P
0x140032867  call    cs:__imp_ExFreePoolWithTag
0x14003286e  nop     dword ptr [rax+rax+00h]
0x140032873  mov     rcx, [rbp+0B0h+var_40]
0x140032877  xor     rcx, rsp; StackCookie
0x14003287a  call    __security_check_cookie
0x14003287f  mov     rbx, [rsp+1B0h+arg_10]
0x140032887  add     rsp, 180h
0x14003288e  pop     r15
0x140032890  pop     r14
0x140032892  pop     r13
0x140032894  pop     r12
0x140032896  pop     rdi
0x140032897  pop     rsi
0x140032898  pop     rbp
0x140032899  retn
```
