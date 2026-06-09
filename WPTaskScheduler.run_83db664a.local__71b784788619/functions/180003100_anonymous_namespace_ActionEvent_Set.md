# _anonymous_namespace_::ActionEvent::Set

- ea: `0x180003100`
- end: `0x180003834`
- name: `_anonymous_namespace_::ActionEvent::Set`
- size: `1844`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003c10`

## callees

- `0x180003100`
- `0x180003840`
- `0x18000aa80`
- `0x18000ab70`
- `0x18000b4f0`
- `0x18000d1f0`
- `0x18000e970`
- `0x180010276`
- `0x18001b3f4`
- `0x180020c30`

## import_xrefs

- `UBPM!UbpmTriggerConsumerRegister` at `0x180003413`
- `UBPM!UbpmTriggerConsumerRegister` at `0x180003413`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180003442`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180003442`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000355f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000356e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000357a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800035f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003600`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000360f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000361e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000355f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000356e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000357a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800035f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003600`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000360f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000361e`
- `msvcrt!malloc` at `0x1800032c4`
- `msvcrt!malloc` at `0x1800032c4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003554`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037c3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037fa`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003554`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037c3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800037fa`
- `RPCRT4!UuidCreate` at `0x18000325d`
- `RPCRT4!UuidCreate` at `0x18000325d`

## string_xrefs

- `0x1800033bb`: `NT TASK\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall anonymous_namespace_::ActionEvent::Set(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  char v6; // al
  __int64 v7; // rcx
  const void *v8; // rsi
  _WORD *v9; // rax
  __int64 v10; // rdx
  size_t v11; // rdi
  void *v12; // rax
  void *v13; // rbx
  unsigned __int16 ***v14; // rax
  unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  int SecurityInfo; // esi
  const unsigned __int16 *v18; // r8
  void **v19; // rax
  void *v20; // rax
  void **v21; // rax
  __int64 v22; // rcx
  int v23; // ebx
  void *v24; // rcx
  struct _SID_AND_ATTRIBUTES *v25; // rbx
  BOOL v26; // ebx
  __int64 v28; // rdx
  void *v29; // rax
  __int64 v30; // rdx
  unsigned int v31; // edi
  unsigned int v32; // eax
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  struct _DAB_SID_INFO *v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h]
  __int128 v36; // [rsp+60h] [rbp-A0h]
  __int128 v37; // [rsp+70h] [rbp-90h]
  __int128 v38; // [rsp+80h] [rbp-80h]
  void *v39[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _SID_AND_ATTRIBUTES *v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v41; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int128 v44; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v45; // [rsp+F0h] [rbp-10h]
  __int128 v46; // [rsp+100h] [rbp+0h]
  __int128 v47; // [rsp+110h] [rbp+10h]
  __int128 v48; // [rsp+120h] [rbp+20h]
  __int128 v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+140h] [rbp+40h]
  void *v51[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v52; // [rsp+160h] [rbp+60h]
  unsigned __int64 v53; // [rsp+168h] [rbp+68h]
  void *v54[3]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v55; // [rsp+188h] [rbp+88h]
  void *v56[4]; // [rsp+190h] [rbp+90h] BYREF

  v4 = a2;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)v39 = 0;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v55 = 7;
  v54[2] = 0;
  LOWORD(v54[0]) = 0;
  v53 = 7;
  v52 = 0;
  LOWORD(v51[0]) = 0;
  v6 = byte_180030D09;
  if ( byte_180030D09 < 0 )
  {
    McTemplateU0q_EventWriteTransfer(a1, ErrorActionSetTrace);
    v6 = byte_180030D09;
  }
  if ( !v4 )
  {
    if ( v6 < 0 )
      McTemplateU0q_EventWriteTransfer(a1, ErrorActionSet);
    v53 = 7;
    v52 = 0;
    LOWORD(v51[0]) = 0;
    return 0;
  }
  if ( !a3 )
  {
    if ( v6 < 0 )
      goto LABEL_79;
    goto LABEL_80;
  }
  if ( !*(_QWORD *)(a3 + 8) )
  {
    if ( v6 < 0 )
LABEL_79:
      McTemplateU0q_EventWriteTransfer(a1, ErrorActionSet);
LABEL_80:
    LOBYTE(a2) = 1;
    std::wstring::_Tidy(v51, a2, 0);
    LOBYTE(v28) = 1;
    std::wstring::_Tidy(v54, v28, 0);
    return 0;
  }
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)v39 = 0;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  *(_OWORD *)(a1 + 104) = 0;
  *(_OWORD *)(a1 + 120) = 0;
  *(_OWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 8) = v4;
  if ( byte_180030D09 < 0 )
    McTemplateU0q_EventWriteTransfer(a1, ErrorActionSetTrace);
  if ( !UuidCreate((UUID *)(a1 + 88)) )
  {
    v29 = (void *)TsipGuidToString(v56, a1 + 88);
    std::wstring::operator=(v54, v29);
    LOBYTE(v30) = 1;
    std::wstring::_Tidy(v56, v30, 0);
  }
  *(_OWORD *)(a1 + 160) = *(_OWORD *)a3;
  v8 = *(const void **)(a3 + 8);
  if ( !v8 )
    goto LABEL_65;
  v7 = 0x7FFFFFFF;
  v9 = *(_WORD **)(a3 + 8);
  while ( *v9 )
  {
    ++v9;
    if ( !--v7 )
    {
      v10 = 0;
      goto LABEL_16;
    }
  }
  v10 = 2 * (0x7FFFFFFF - v7);
LABEL_16:
  if ( v7 && (v11 = v10 + 2, v10 != -2) && (v12 = malloc(v10 + 2), (v13 = v12) != 0) )
    memcpy_0(v12, v8, v11);
  else
LABEL_65:
    v13 = 0;
  *(_QWORD *)(a1 + 168) = v13;
  *(_DWORD *)(a1 + 104) = 3;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 112) = v13;
  v14 = *(unsigned __int16 ****)(*(_QWORD *)(a1 + 8) + 272LL);
  if ( v14 )
  {
    if ( *((_BYTE *)v14 + 16) )
    {
      v15 = **v14;
      if ( v15 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        if ( v16 == 8 )
        {
          SecurityInfo = 0;
          v18 = L"S-1-5-18";
          while ( v16 )
          {
            v7 = *v15;
            if ( *v18 != (_WORD)v7 )
              goto LABEL_46;
            ++v18;
            ++v15;
            --v16;
          }
          goto LABEL_30;
        }
      }
    }
  }
LABEL_46:
  if ( byte_180030D09 < 0 )
    McTemplateU0q_EventWriteTransfer(v7, ErrorActionSetTrace);
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 272LL);
  if ( v7 )
  {
    SecurityInfo = SecurityContext::GetSecurityInfo((SecurityContext *)v7, &v34[1], v39, (unsigned int *)v40, &v40[1]);
    if ( SecurityInfo >= 0 )
    {
      *(_QWORD *)&v36 = 0x200000002LL;
      LODWORD(v34[0]) = 1;
      *(_QWORD *)&v35 = 0;
      HIDWORD(v38) = 0;
      *(_QWORD *)(a1 + 136) = v34;
LABEL_30:
      if ( byte_180030D09 < 0 )
        McTemplateU0q_EventWriteTransfer(v7, ErrorActionSetTrace);
      LODWORD(v42) = 1;
      if ( v55 >= 8 )
        v19 = (void **)v54[0];
      else
        v19 = v54;
      *(_QWORD *)&v41 = v19;
      *((_QWORD *)&v41 + 1) = *(_QWORD *)(a1 + 168);
      *((_QWORD *)&v42 + 1) = a1 + 104;
      LODWORD(v46) = 1;
      *((_QWORD *)&v46 + 1) = &v41;
      v20 = (void *)std::operator+<unsigned short>(v56, L"NT TASK\\", v54);
      std::wstring::operator=(v51, v20);
      if ( v56[3] >= (void *)8 )
        operator delete(v56[0]);
      v21 = v51;
      if ( v53 >= 8 )
        v21 = (void **)v51[0];
      *((_QWORD *)&v44 + 1) = v21;
      *(_QWORD *)&v44 = a1 + 88;
      LODWORD(v45) = 4;
      v33 = 0;
      v23 = UbpmTriggerConsumerRegister(&v44, &v33);
      if ( byte_180030D09 < 0 )
        McTemplateU0q_EventWriteTransfer(v22, ErrorActionSetTrace);
      if ( v23 )
      {
        if ( byte_180030D09 < 0 )
          McTemplateU0q_EventWriteTransfer(v22, ErrorActionSet);
        SecurityInfo = -2147467259;
      }
      else
      {
        if ( (byte_180030D03 & 4) != 0 )
          McTemplateU0jz_EventWriteTransfer(v22, EventSet, *(_QWORD *)(a1 + 8) + 16LL, *(_QWORD *)(a1 + 168));
        UbpmCloseTriggerConsumer(v33);
      }
      goto LABEL_44;
    }
  }
  else
  {
    SecurityInfo = -2147467259;
  }
  if ( byte_180030D09 >= 0 )
    goto LABEL_51;
  McTemplateU0q_EventWriteTransfer(v7, ErrorActionSet);
LABEL_44:
  if ( byte_180030D09 < 0 )
    McTemplateU0q_EventWriteTransfer(v22, ErrorActionSetTrace);
LABEL_51:
  if ( v34[1] )
  {
    operator delete[](*((void **)v34[1] + 1));
    operator delete(v34[1]);
  }
  v24 = v39[0];
  if ( v39[0] )
    operator delete[](v39[0]);
  v25 = v40[1];
  if ( v40[1] )
  {
    v31 = 0;
    v32 = (unsigned int)v40[0];
    if ( LODWORD(v40[0]) )
    {
      do
      {
        if ( v25->Sid )
        {
          operator delete[](v25->Sid);
          v32 = (unsigned int)v40[0];
        }
        ++v31;
        ++v25;
      }
      while ( v31 < v32 );
      v25 = v40[1];
    }
    operator delete[](v25);
  }
  if ( SecurityInfo < 0 )
  {
    if ( byte_180030D09 < 0 )
      McTemplateU0q_EventWriteTransfer(v24, ErrorActionSet);
    if ( v53 >= 8 )
      operator delete(v51[0]);
    v53 = 7;
    v52 = 0;
    LOWORD(v51[0]) = 0;
    if ( v55 >= 8 )
      operator delete(v54[0]);
    return 0;
  }
  if ( byte_180030D09 < 0 )
    McTemplateU0q_EventWriteTransfer(v24, ErrorActionSetTrace);
  v26 = *(_QWORD *)(a1 + 168) != 0;
  if ( v53 >= 8 )
    operator delete(v51[0]);
  v53 = 7;
  v52 = 0;
  LOWORD(v51[0]) = 0;
  if ( v55 >= 8 )
    operator delete(v54[0]);
  return v26;
}

```

## disassembly

```asm
0x180003100  mov     [rsp-8+arg_8], rbx
0x180003105  push    rbp
0x180003106  push    rsi
0x180003107  push    rdi
0x180003108  push    r12
0x18000310a  push    r13
0x18000310c  push    r14
0x18000310e  push    r15
0x180003110  lea     rbp, [rsp-0C0h]
0x180003118  sub     rsp, 1C0h
0x18000311f  mov     rax, cs:__security_cookie
0x180003126  xor     rax, rsp
0x180003129  mov     [rbp+0F0h+var_40], rax
0x180003130  mov     rbx, r8
0x180003133  mov     rdi, rdx
0x180003136  mov     r14, rcx
0x180003139  xorps   xmm0, xmm0
0x18000313c  movups  xmmword ptr [rsp+1F0h+var_1B0], xmm0
0x180003141  movups  [rsp+1F0h+var_1A0], xmm0
0x180003146  movups  [rsp+1F0h+var_190], xmm0
0x18000314b  movups  [rsp+1F0h+var_180], xmm0
0x180003150  movups  [rbp+0F0h+var_170], xmm0
0x180003154  movups  xmmword ptr [rbp+0F0h+var_160], xmm0
0x180003158  movups  xmmword ptr [rbp+0F0h+var_150], xmm0
0x18000315c  xor     eax, eax
0x18000315e  movups  [rbp+0F0h+var_140], xmm0
0x180003162  movups  [rbp+0F0h+var_130], xmm0
0x180003166  mov     [rbp+0F0h+var_120], rax
0x18000316a  xorps   xmm1, xmm1
0x18000316d  movups  [rbp+0F0h+var_110], xmm1
0x180003171  movups  [rbp+0F0h+var_100], xmm1
0x180003175  movups  [rbp+0F0h+var_F0], xmm1
0x180003179  movups  [rbp+0F0h+var_E0], xmm1
0x18000317d  movups  [rbp+0F0h+var_D0], xmm1
0x180003181  movups  [rbp+0F0h+var_C0], xmm1
0x180003185  mov     [rbp+0F0h+var_B0], rax
0x180003189  mov     [rbp+0F0h+var_68], 7
0x180003194  xor     r13d, r13d
0x180003197  mov     [rbp+0F0h+var_70], r13
0x18000319e  mov     word ptr [rbp+0F0h+var_80], r13w
0x1800031a3  mov     [rbp+0F0h+var_88], 7
0x1800031ab  mov     [rbp+0F0h+var_90], r13
0x1800031af  mov     word ptr [rbp+0F0h+var_A0], r13w
0x1800031b4  movzx   eax, cs:byte_180030D09
0x1800031bb  test    al, al
0x1800031bd  js      loc_180003626
0x1800031c3  test    rdi, rdi
0x1800031c6  jz      loc_1800035CA
0x1800031cc  test    rbx, rbx
0x1800031cf  jz      loc_180003658
0x1800031d5  cmp     qword ptr [rbx+8], 0
0x1800031da  jz      loc_180003664
0x1800031e0  xorps   xmm0, xmm0
0x1800031e3  movups  xmmword ptr [rsp+1F0h+var_1B0], xmm0
0x1800031e8  movups  [rsp+1F0h+var_1A0], xmm0
0x1800031ed  movups  [rsp+1F0h+var_190], xmm0
0x1800031f2  movups  [rsp+1F0h+var_180], xmm0
0x1800031f7  movups  [rbp+0F0h+var_170], xmm0
0x1800031fb  movups  xmmword ptr [rbp+0F0h+var_160], xmm0
0x1800031ff  movups  xmmword ptr [rbp+0F0h+var_150], xmm0
0x180003203  xor     eax, eax
0x180003205  movups  [rbp+0F0h+var_140], xmm0
0x180003209  movups  [rbp+0F0h+var_130], xmm0
0x18000320d  mov     [rbp+0F0h+var_120], rax
0x180003211  xorps   xmm1, xmm1
0x180003214  movups  [rbp+0F0h+var_110], xmm1
0x180003218  movups  [rbp+0F0h+var_100], xmm1
0x18000321c  movups  [rbp+0F0h+var_F0], xmm1
0x180003220  movups  [rbp+0F0h+var_E0], xmm1
0x180003224  movups  [rbp+0F0h+var_D0], xmm1
0x180003228  movups  [rbp+0F0h+var_C0], xmm1
0x18000322c  mov     [rbp+0F0h+var_B0], rax
0x180003230  lea     r15, [r14+68h]
0x180003234  movups  xmmword ptr [r15], xmm0
0x180003238  movups  xmmword ptr [r15+10h], xmm0
0x18000323d  movups  xmmword ptr [r15+20h], xmm0
0x180003242  mov     [r15+30h], rax
0x180003246  mov     [r14+8], rdi
0x18000324a  cmp     cs:byte_180030D09, al
0x180003250  jl      loc_18000369F
0x180003256  lea     r12, [r14+58h]
0x18000325a  mov     rcx, r12; Uuid
0x18000325d  call    cs:__imp_UuidCreate
0x180003263  test    eax, eax
0x180003265  jz      loc_1800036B6
0x18000326b  movups  xmm0, xmmword ptr [rbx]
0x18000326e  movups  xmmword ptr [r14+0A0h], xmm0
0x180003276  mov     rsi, [rbx+8]
0x18000327a  test    rsi, rsi
0x18000327d  jz      loc_18000358C
0x180003283  mov     edx, 7FFFFFFFh
0x180003288  mov     ecx, edx
0x18000328a  mov     rax, rsi
0x18000328d  nop     dword ptr [rax]
0x180003290  cmp     word ptr [rax], 0
0x180003294  jz      short loc_1800032A5
0x180003296  add     rax, 2
0x18000329a  sub     rcx, 1
0x18000329e  jnz     short loc_180003290
0x1800032a0  mov     rdx, r13
0x1800032a3  jmp     short loc_1800032AB
0x1800032a5  sub     rdx, rcx
0x1800032a8  add     rdx, rdx
0x1800032ab  test    rcx, rcx
0x1800032ae  jz      loc_18000358C
0x1800032b4  lea     rdi, [rdx+2]
0x1800032b8  test    rdi, rdi
0x1800032bb  jz      loc_18000358C
0x1800032c1  mov     rcx, rdi; Size
0x1800032c4  call    cs:__imp_malloc
0x1800032ca  mov     rbx, rax
0x1800032cd  test    rax, rax
0x1800032d0  jz      loc_18000358C
0x1800032d6  mov     r8, rdi; Size
0x1800032d9  mov     rdx, rsi; Src
0x1800032dc  mov     rcx, rax; void *
0x1800032df  call    memcpy_0
0x1800032e4  mov     [r14+0A8h], rbx
0x1800032eb  mov     dword ptr [r15], 3
0x1800032f2  mov     [r14+88h], r13
0x1800032f9  mov     [r14+70h], rbx
0x1800032fd  mov     rax, [r14+8]
0x180003301  mov     rax, [rax+110h]
0x180003308  test    rax, rax
0x18000330b  jz      loc_180003465
0x180003311  cmp     byte ptr [rax+10h], 0
0x180003315  jz      loc_180003465
0x18000331b  mov     rax, [rax]
0x18000331e  mov     rdx, [rax]
0x180003321  test    rdx, rdx
0x180003324  jz      loc_180003465
0x18000332a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003331  inc     rax
0x180003334  cmp     word ptr [rdx+rax*2], 0
0x180003339  jnz     short loc_180003331
0x18000333b  cmp     rax, 8
0x18000333f  jnz     loc_180003465
0x180003345  mov     esi, r13d
0x180003348  lea     r8, aS1518; "S-1-5-18"
0x18000334f  nop
0x180003350  test    rax, rax
0x180003353  jz      short loc_18000336F
0x180003355  movzx   ecx, word ptr [rdx]
0x180003358  cmp     [r8], cx
0x18000335c  jnz     loc_180003465
0x180003362  add     r8, 2
0x180003366  add     rdx, 2
0x18000336a  dec     rax
0x18000336d  jmp     short loc_180003350
0x18000336f  cmp     cs:byte_180030D09, 0
0x180003376  jl      loc_180003747
0x18000337c  mov     dword ptr [rbp+0F0h+var_130], 1
0x180003383  cmp     [rbp+0F0h+var_68], 8
0x18000338b  jnb     loc_18000375E
0x180003391  lea     rax, [rbp+0F0h+var_80]
0x180003395  mov     qword ptr [rbp+0F0h+var_140], rax
0x180003399  mov     rax, [r14+0A8h]
0x1800033a0  mov     qword ptr [rbp+0F0h+var_140+8], rax
0x1800033a4  mov     qword ptr [rbp+0F0h+var_130+8], r15
0x1800033a8  mov     dword ptr [rbp+0F0h+var_F0], 1
0x1800033af  lea     rax, [rbp+0F0h+var_140]
0x1800033b3  mov     qword ptr [rbp+0F0h+var_F0+8], rax
0x1800033b7  lea     r8, [rbp+0F0h+var_80]
0x1800033bb  lea     rdx, aNtTask; "NT TASK\\"
0x1800033c2  lea     rcx, [rbp+0F0h+var_60]
0x1800033c9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x1800033ce  mov     rdx, rax; Src
0x1800033d1  lea     rcx, [rbp+0F0h+var_A0]; void *
0x1800033d5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800033da  cmp     [rbp+0F0h+var_48], 8
0x1800033e2  jnb     loc_180003608
0x1800033e8  lea     rax, [rbp+0F0h+var_A0]
0x1800033ec  cmp     [rbp+0F0h+var_88], 8
0x1800033f1  cmovnb  rax, [rbp+0F0h+var_A0]
0x1800033f6  mov     qword ptr [rbp+0F0h+var_110+8], rax
0x1800033fa  mov     qword ptr [rbp+0F0h+var_110], r12
0x1800033fe  mov     dword ptr [rbp+0F0h+var_100], 4
0x180003405  mov     [rsp+1F0h+var_1C0], r13
0x18000340a  lea     rdx, [rsp+1F0h+var_1C0]
0x18000340f  lea     rcx, [rbp+0F0h+var_110]
0x180003413  call    cs:__imp_UbpmTriggerConsumerRegister
0x180003419  mov     ebx, eax
0x18000341b  cmp     cs:byte_180030D09, 0
0x180003422  jl      loc_180003767
0x180003428  test    ebx, ebx
0x18000342a  jnz     loc_18000377E
0x180003430  test    cs:byte_180030D03, 4
0x180003437  jnz     loc_1800037A3
0x18000343d  mov     rcx, [rsp+1F0h+var_1C0]
0x180003442  call    cs:__imp_UbpmCloseTriggerConsumer
0x180003448  cmp     cs:byte_180030D09, 0
0x18000344f  jge     short loc_1800034B8
0x180003451  mov     r8d, 36Eh
0x180003457  lea     rdx, ErrorActionSetTrace
0x18000345e  call    McTemplateU0q_EventWriteTransfer
0x180003463  jmp     short loc_1800034B8
0x180003465  cmp     cs:byte_180030D09, 0
0x18000346c  jl      loc_1800036E7
0x180003472  mov     rax, [r14+8]
0x180003476  mov     rcx, [rax+110h]; this
0x18000347d  test    rcx, rcx
0x180003480  jz      loc_180003582
0x180003486  lea     rax, [rbp+0F0h+var_150+8]
0x18000348a  mov     [rsp+1F0h+var_1D0], rax; struct _SID_AND_ATTRIBUTES **
0x18000348f  lea     r9, [rbp+0F0h+var_150]; unsigned int *
0x180003493  lea     r8, [rbp+0F0h+var_160]; void **
0x180003497  lea     rdx, [rsp+1F0h+var_1B0+8]; struct _DAB_SID_INFO **
0x18000349c  call    ?GetSecurityInfo@SecurityContext@@QEAAJPEAPEAU_DAB_SID_INFO@@PEAPEAXPEAKPEAPEAU_SID_AND_ATTRIBUTES@@@Z; SecurityContext::GetSecurityInfo(_DAB_SID_INFO * *,void * *,ulong *,_SID_AND_ATTRIBUTES * *)
0x1800034a1  mov     esi, eax
0x1800034a3  test    eax, eax
0x1800034a5  jns     loc_180003715
0x1800034ab  cmp     cs:byte_180030D09, 0
0x1800034b2  jl      loc_1800036FE
0x1800034b8  mov     rcx, [rsp+1F0h+var_1B0+8]
0x1800034bd  test    rcx, rcx
0x1800034c0  jnz     loc_180003550
0x1800034c6  mov     rcx, [rbp+0F0h+var_160]
0x1800034ca  test    rcx, rcx
0x1800034cd  jnz     loc_1800037C3
0x1800034d3  mov     rbx, [rbp+0F0h+var_150+8]
0x1800034d7  test    rbx, rbx
0x1800034da  jnz     loc_1800037CE
0x1800034e0  test    esi, esi
0x1800034e2  js      loc_180003594
0x1800034e8  cmp     cs:byte_180030D09, 0
0x1800034ef  jl      loc_18000381C
0x1800034f5  mov     ebx, r13d
0x1800034f8  cmp     [r14+0A8h], rbx
0x1800034ff  setnz   bl
0x180003502  cmp     [rbp+0F0h+var_88], 8
0x180003507  jnb     short loc_18000356A
0x180003509  mov     [rbp+0F0h+var_88], 7
0x180003511  mov     [rbp+0F0h+var_90], r13
0x180003515  mov     word ptr [rbp+0F0h+var_A0], r13w
0x18000351a  cmp     [rbp+0F0h+var_68], 8
0x180003522  jnb     short loc_180003576
0x180003524  mov     eax, ebx
0x180003526  mov     rcx, [rbp+0F0h+var_40]
0x18000352d  xor     rcx, rsp; StackCookie
0x180003530  call    __security_check_cookie
0x180003535  mov     rbx, [rsp+1F0h+arg_8]
0x18000353d  add     rsp, 1C0h
0x180003544  pop     r15
0x180003546  pop     r14
0x180003548  pop     r13
0x18000354a  pop     r12
0x18000354c  pop     rdi
0x18000354d  pop     rsi
0x18000354e  pop     rbp
0x18000354f  retn
0x180003550  mov     rcx, [rcx+8]
0x180003554  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000355a  mov     rcx, [rsp+1F0h+var_1B0+8]
0x18000355f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003565  jmp     loc_1800034C6
0x18000356a  mov     rcx, [rbp+0F0h+var_A0]
0x18000356e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003574  jmp     short loc_180003509
0x180003576  mov     rcx, [rbp+0F0h+var_80]
0x18000357a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003580  jmp     short loc_180003524
0x180003582  mov     esi, 80004005h
0x180003587  jmp     loc_1800034AB
0x18000358c  mov     rbx, r13
0x18000358f  jmp     loc_1800032E4
0x180003594  cmp     cs:byte_180030D09, 0
0x18000359b  jl      loc_180003805
0x1800035a1  cmp     [rbp+0F0h+var_88], 8
0x1800035a6  jnb     short loc_18000361A
0x1800035a8  mov     [rbp+0F0h+var_88], 7
0x1800035b0  mov     [rbp+0F0h+var_90], r13
0x1800035b4  mov     word ptr [rbp+0F0h+var_A0], r13w
0x1800035b9  cmp     [rbp+0F0h+var_68], 8
0x1800035c1  jnb     short loc_1800035F0
0x1800035c3  xor     eax, eax
0x1800035c5  jmp     loc_180003526
0x1800035ca  test    al, al
0x1800035cc  js      short loc_180003644
0x1800035ce  cmp     [rbp+0F0h+var_88], 8
0x1800035d3  jnb     short loc_1800035FC
0x1800035d5  mov     [rbp+0F0h+var_88], 7
0x1800035dd  mov     [rbp+0F0h+var_90], r13
0x1800035e1  mov     word ptr [rbp+0F0h+var_A0], r13w
0x1800035e6  cmp     [rbp+0F0h+var_68], 8
0x1800035ee  jb      short loc_1800035C3
0x1800035f0  mov     rcx, [rbp+0F0h+var_80]
0x1800035f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800035fa  jmp     short loc_1800035C3
0x1800035fc  mov     rcx, [rbp+0F0h+var_A0]
0x180003600  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003606  jmp     short loc_1800035D5
0x180003608  mov     rcx, [rbp+0F0h+var_60]
0x18000360f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003615  jmp     loc_1800033E8
0x18000361a  mov     rcx, [rbp+0F0h+var_A0]
0x18000361e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003624  jmp     short loc_1800035A8
0x180003626  mov     r8d, 30Dh
0x18000362c  lea     rdx, ErrorActionSetTrace
0x180003633  call    McTemplateU0q_EventWriteTransfer
  ... truncated ...
```
