# MpPluginDlpSetFeatureControls

- ea: `0x1800944d0`
- end: `0x1800947c0`
- name: `MpPluginDlpSetFeatureControls`
- size: `752`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callees

- `0x180057e60`
- `0x18005815c`
- `0x180058164`
- `0x18008c634`
- `0x18008d7f0`
- `0x18008e93c`
- `0x1800905c8`
- `0x1800944d0`
- `0x180095ae0`
- `0x180095b98`
- `0x1800979f8`
- `0x1800e9cdc`
- `0x1800e9f64`
- `0x1800ea6a0`
- `0x180271ab0`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x1800946a2`
- `MpClient!MpConfigSetValue` at `0x1800946a2`
- `MpClient!MpConfigClose` at `0x1800946b9`
- `MpClient!MpConfigClose` at `0x1800946f5`
- `MpClient!MpConfigClose` at `0x1800946b9`
- `MpClient!MpConfigClose` at `0x1800946f5`
- `MpClient!MpConfigOpen` at `0x180094679`
- `MpClient!MpConfigOpen` at `0x180094679`

## pseudocode

```c
__int64 __fastcall MpPluginDlpSetFeatureControls(unsigned int a1, __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v5; // rax
  unsigned int v6; // esi
  _QWORD *v7; // rcx
  __int64 v8; // r8
  int v9; // r12d
  __int64 v10; // rax
  wchar_t *v11; // rsi
  __int64 v12; // rcx
  wchar_t *v13; // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  char v18; // r15
  __int64 v19; // rcx
  int v20; // eax
  _QWORD **v21; // rcx
  _QWORD *v22; // rcx
  _QWORD *v23; // rbx
  int v24; // [rsp+38h] [rbp-90h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-88h] BYREF
  int v26; // [rsp+50h] [rbp-78h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-70h]
  __int64 v28; // [rsp+60h] [rbp-68h]
  __int64 v29; // [rsp+68h] [rbp-60h] BYREF
  __int128 v30; // [rsp+70h] [rbp-58h]
  __int64 v31; // [rsp+80h] [rbp-48h]
  __int64 v32; // [rsp+88h] [rbp-40h]

  v3 = a1;
  if ( !a2 && a1 )
    return 2147942487LL;
  sub_180271AB0(&v26, 0, 64);
  v26 = 0;
  lpMem = 0;
  v28 = 0;
  v5 = (_QWORD *)sub_180058164(32);
  *v5 = v5;
  v5[1] = v5;
  lpMem = v5;
  v29 = 0;
  v30 = 0;
  v31 = 7;
  v32 = 8;
  v26 = 1065353216;
  sub_18008E93C(&v29, 16, v5);
  sub_1800905C8(&v26, v3);
  v6 = 0;
  v7 = off_18033CF60;
  while ( v6 < (unsigned int)v3 )
  {
    v8 = a2 + 16LL * v6;
    if ( (unsigned __int64)(*(_QWORD *)v8 - 1LL) <= 0x137 )
    {
      v9 = *(_DWORD *)(v8 + 8);
      *(_DWORD *)(*(_QWORD *)sub_18008C634(&v26, v25) + 24LL) = v9;
LABEL_11:
      v7 = off_18033CF60;
      goto LABEL_12;
    }
    if ( v7 != &off_18033CF60 && (*((_BYTE *)v7 + 28) & 1) != 0 )
    {
      sub_180095B98(v7[2], 54, &MessageGuid, *(_QWORD *)v8);
      goto LABEL_11;
    }
LABEL_12:
    ++v6;
  }
  v10 = sub_1800E9CDC(v7);
  sub_1800EA6A0(v10, &v26);
  v11 = (wchar_t *)qword_1802B7930;
  do
  {
    v12 = *(_QWORD *)v11;
    if ( (unsigned __int64)(*(_QWORD *)v11 - 1LL) <= 0x137 )
    {
      _mm_lfence();
      v13 = off_1802B4CF0[v12];
      if ( v13 )
      {
        v24 = sub_1800E9F64(v12);
        v25[0] = 0;
        v14 = MpConfigOpen(L"Features", v25);
        v18 = v14;
        v19 = v25[0];
        if ( v14 >= 0 && (v20 = MpConfigSetValue(v25[0], v13, 1, 4, &v24), v18 = v20, v19 = v25[0], v20 >= 0) )
        {
          if ( v25[0] )
            MpConfigClose(v25[0], v15, v16, v17);
        }
        else
        {
          if ( v19 )
            MpConfigClose(v19, v15, v16, v17);
          if ( off_18033CF60 != (_UNKNOWN *)&off_18033CF60 && (*((_BYTE *)off_18033CF60 + 28) & 1) != 0 )
            sub_1800979F8(*((_QWORD *)off_18033CF60 + 2), 11, (unsigned int)qword_1802B7918, (_DWORD)v13, v18);
        }
      }
    }
    v11 += 4;
  }
  while ( v11 != L"MpDlp_NetworkShareGroupsSettings" );
  sub_18008D7F0(&v29);
  v21 = (_QWORD **)lpMem;
  **((_QWORD **)lpMem + 1) = 0;
  v22 = *v21;
  if ( v22 )
  {
    do
    {
      v23 = (_QWORD *)*v22;
      sub_18005815C(v22);
      v22 = v23;
    }
    while ( v23 );
  }
  sub_18005815C(lpMem);
  return 0;
}

```

## disassembly

```asm
0x1800944d0  mov     [rsp+arg_10], rbx
0x1800944d5  push    rsi
0x1800944d6  push    r12
0x1800944d8  push    r13
0x1800944da  push    r14
0x1800944dc  push    r15
0x1800944de  sub     rsp, 0A0h
0x1800944e5  mov     rax, cs:__security_cookie
0x1800944ec  xor     rax, rsp
0x1800944ef  mov     [rsp+0C8h+var_38], rax
0x1800944f7  mov     r15, rdx
0x1800944fa  mov     ebx, ecx
0x1800944fc  test    rdx, rdx
0x1800944ff  jnz     short loc_18009450F
0x180094501  test    ecx, ecx
0x180094503  jz      short loc_18009450F
0x180094505  mov     eax, 80070057h
0x18009450a  jmp     loc_180094797
0x18009450f  xor     edx, edx
0x180094511  lea     r8d, [rdx+40h]
0x180094515  lea     rcx, [rsp+0C8h+var_78]
0x18009451a  call    sub_180271AB0
0x18009451f  mov     [rsp+0C8h+var_78], 0
0x180094527  mov     [rsp+0C8h+lpMem], 0
0x180094530  mov     [rsp+0C8h+var_68], 0
0x180094539  mov     r13d, 20h ; ' '
0x18009453f  mov     ecx, r13d
0x180094542  call    sub_180058164
0x180094547  mov     [rax], rax
0x18009454a  mov     [rax+8], rax
0x18009454e  mov     [rsp+0C8h+lpMem], rax
0x180094553  mov     [rsp+0C8h+var_60], 0
0x18009455c  xorps   xmm0, xmm0
0x18009455f  movdqa  [rsp+0C8h+var_58], xmm0
0x180094565  mov     [rsp+0C8h+var_48], 7
0x180094571  mov     [rsp+0C8h+var_40], 8
0x18009457d  mov     [rsp+0C8h+var_78], 3F800000h
0x180094585  mov     r8, rax
0x180094588  lea     edx, [r13-10h]
0x18009458c  lea     rcx, [rsp+0C8h+var_60]
0x180094591  call    sub_18008E93C
0x180094596  nop
0x180094597  mov     rdx, rbx
0x18009459a  lea     rcx, [rsp+0C8h+var_78]
0x18009459f  call    sub_1800905C8
0x1800945a4  xor     esi, esi
0x1800945a6  lea     r14, off_18033CF60
0x1800945ad  mov     rcx, cs:off_18033CF60
0x1800945b4  cmp     esi, ebx
0x1800945b6  jnb     short loc_180094618
0x1800945b8  mov     r8d, esi
0x1800945bb  shl     r8, 4
0x1800945bf  add     r8, r15
0x1800945c2  mov     r9, [r8]
0x1800945c5  lea     rax, [r9-1]
0x1800945c9  cmp     rax, 137h
0x1800945cf  ja      short loc_1800945ED
0x1800945d1  mov     r12d, [r8+8]
0x1800945d5  lea     rdx, [rsp+0C8h+var_88]
0x1800945da  lea     rcx, [rsp+0C8h+var_78]
0x1800945df  call    sub_18008C634
0x1800945e4  mov     rax, [rax]
0x1800945e7  mov     [rax+18h], r12d
0x1800945eb  jmp     short loc_18009460D
0x1800945ed  cmp     rcx, r14
0x1800945f0  jz      short loc_180094614
0x1800945f2  test    byte ptr [rcx+1Ch], 1
0x1800945f6  jz      short loc_180094614
0x1800945f8  mov     edx, 36h ; '6'
0x1800945fd  lea     r8, MessageGuid
0x180094604  mov     rcx, [rcx+10h]
0x180094608  call    sub_180095B98
0x18009460d  mov     rcx, cs:off_18033CF60
0x180094614  inc     esi
0x180094616  jmp     short loc_1800945B4
0x180094618  call    sub_1800E9CDC
0x18009461d  lea     rdx, [rsp+0C8h+var_78]
0x180094622  mov     rcx, rax
0x180094625  call    sub_1800EA6A0
0x18009462a  lea     rsi, qword_1802B7930
0x180094631  mov     rcx, [rsi]
0x180094634  lea     rax, [rcx-1]
0x180094638  cmp     rax, 137h
0x18009463e  ja      loc_1800946FB
0x180094644  lfence
0x180094647  lea     rbx, off_1802B4CF0; "MpFC_Unknown"
0x18009464e  mov     rbx, [rbx+rcx*8]
0x180094652  test    rbx, rbx
0x180094655  jz      loc_1800946FB
0x18009465b  call    sub_1800E9F64
0x180094660  mov     [rsp+0C8h+var_90], eax
0x180094664  mov     [rsp+0C8h+var_88], 0
0x18009466d  lea     rdx, [rsp+0C8h+var_88]
0x180094672  lea     rcx, aFeatures_0; "Features"
0x180094679  call    cs:MpConfigOpen
0x18009467f  mov     r15d, eax
0x180094682  mov     rcx, [rsp+0C8h+var_88]
0x180094687  test    eax, eax
0x180094689  js      short loc_1800946B4
0x18009468b  lea     rax, [rsp+0C8h+var_90]
0x180094690  mov     [rsp+0C8h+var_A8], rax
0x180094695  mov     r9d, 4
0x18009469b  lea     r8d, [r9-3]
0x18009469f  mov     rdx, rbx
0x1800946a2  call    cs:MpConfigSetValue
0x1800946a8  mov     r15d, eax
0x1800946ab  mov     rcx, [rsp+0C8h+var_88]
0x1800946b0  test    eax, eax
0x1800946b2  jns     short loc_1800946F0
0x1800946b4  test    rcx, rcx
0x1800946b7  jz      short loc_1800946BF
0x1800946b9  call    cs:MpConfigClose
0x1800946bf  mov     rcx, cs:off_18033CF60
0x1800946c6  cmp     rcx, r14
0x1800946c9  jz      short loc_1800946FB
0x1800946cb  test    byte ptr [rcx+1Ch], 1
0x1800946cf  jz      short loc_1800946FB
0x1800946d1  mov     edx, 0Bh
0x1800946d6  mov     dword ptr [rsp+0C8h+var_A8], r15d
0x1800946db  mov     r9, rbx
0x1800946de  lea     r8, qword_1802B7918
0x1800946e5  mov     rcx, [rcx+10h]
0x1800946e9  call    sub_1800979F8
0x1800946ee  jmp     short loc_1800946FB
0x1800946f0  test    rcx, rcx
0x1800946f3  jz      short loc_1800946FB
0x1800946f5  call    cs:MpConfigClose
0x1800946fb  add     rsi, 8
0x1800946ff  lea     rax, aMpdlpNetworksh; "MpDlp_NetworkShareGroupsSettings"
0x180094706  cmp     rsi, rax
0x180094709  jnz     loc_180094631
0x18009470f  lea     rcx, [rsp+0C8h+var_60]
0x180094714  call    sub_18008D7F0
0x180094719  mov     rcx, [rsp+0C8h+lpMem]
0x18009471e  mov     rax, [rcx+8]
0x180094722  mov     qword ptr [rax], 0
0x180094729  mov     rcx, [rcx]; lpMem
0x18009472c  test    rcx, rcx
0x18009472f  jz      short loc_180094744
0x180094731  mov     rbx, [rcx]
0x180094734  mov     rdx, r13
0x180094737  call    sub_18005815C
0x18009473c  mov     rcx, rbx
0x18009473f  test    rbx, rbx
0x180094742  jnz     short loc_180094731
0x180094744  mov     rdx, r13
0x180094747  mov     rcx, [rsp+0C8h+lpMem]; lpMem
0x18009474c  call    sub_18005815C
0x180094751  nop
0x180094752  jmp     short loc_18009475C
0x180094754  mov     ebx, [rsp+0C8h+var_90]
0x180094758  test    ebx, ebx
0x18009475a  js      short loc_180094764
0x18009475c  xor     eax, eax
0x18009475e  jmp     short loc_180094797
0x180094760  mov     ebx, [rsp+0C8h+var_90]
0x180094764  lea     r14, off_18033CF60
0x18009476b  mov     rcx, cs:off_18033CF60
0x180094772  cmp     rcx, r14
0x180094775  jz      short loc_180094795
0x180094777  test    byte ptr [rcx+1Ch], 1
0x18009477b  jz      short loc_180094795
0x18009477d  mov     edx, 37h ; '7'
0x180094782  mov     r9d, ebx
0x180094785  lea     r8, MessageGuid
0x18009478c  mov     rcx, [rcx+10h]
0x180094790  call    sub_180095AE0
0x180094795  mov     eax, ebx
0x180094797  mov     rcx, [rsp+0C8h+var_38]
0x18009479f  xor     rcx, rsp; StackCookie
0x1800947a2  call    __security_check_cookie
0x1800947a7  mov     rbx, [rsp+0C8h+arg_10]
0x1800947af  add     rsp, 0A0h
0x1800947b6  pop     r15
0x1800947b8  pop     r14
0x1800947ba  pop     r13
0x1800947bc  pop     r12
0x1800947be  pop     rsi
0x1800947bf  retn
```
