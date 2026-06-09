# _anonymous_namespace_::ActionWNF::Set

- ea: `0x18001aba0`
- end: `0x18001af46`
- name: `_anonymous_namespace_::ActionWNF::Set`
- size: `934`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001af50`

## callees

- `0x180003840`
- `0x18000aa80`
- `0x18000b4f0`
- `0x18000cc50`
- `0x18000cd60`
- `0x18000d1f0`
- `0x18000e2c0`
- `0x18000e454`
- `0x18000ea40`
- `0x18001aba0`
- `0x180020c02`
- `0x180020c30`

## import_xrefs

- `UBPM!UbpmTriggerConsumerRegister` at `0x18001aec9`
- `UBPM!UbpmTriggerConsumerRegister` at `0x18001aec9`
- `msvcrt!free` at `0x18001af22`
- `msvcrt!free` at `0x18001af22`

## string_xrefs

- `0x18001ae5e`: `NT TASK\`

## pseudocode

```c
_BOOL8 __fastcall anonymous_namespace_::ActionWNF::Set(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r14
  int v6; // eax
  BOOL v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdx
  int SecurityInfo; // ebx
  unsigned __int8 *v12; // rdx
  unsigned __int8 *v13; // rcx
  __int64 v14; // r11
  SecurityContext *v15; // rcx
  void *v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  void *v20; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  struct _DAB_SID_INFO *v31[3]; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+84h] [rbp-7Ch]
  int v34; // [rsp+ACh] [rbp-54h]
  void *v35; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v36; // [rsp+C0h] [rbp-40h] BYREF
  struct _SID_AND_ATTRIBUTES *v37; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v38; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v39; // [rsp+E0h] [rbp-20h]
  _QWORD v40[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v41; // [rsp+100h] [rbp+0h]
  int v42; // [rsp+110h] [rbp+10h]
  __int128 *v43; // [rsp+118h] [rbp+18h]
  _QWORD v44[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v45; // [rsp+178h] [rbp+78h]
  _QWORD v46[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v47; // [rsp+198h] [rbp+98h]
  _QWORD v48[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v49; // [rsp+1B8h] [rbp+B8h]
  _BYTE v50[32]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = a2;
  v45 = 7;
  v44[2] = 0;
  LOWORD(v44[0]) = 0;
  v49 = 7;
  v48[2] = 0;
  LOWORD(v48[0]) = 0;
  v47 = 7;
  v46[2] = 0;
  LOWORD(v46[0]) = 0;
  if ( !a2 || !a3 )
    goto LABEL_5;
  v6 = *(_DWORD *)(a3 + 8);
  if ( *(_QWORD *)(a3 + 16) )
  {
    if ( !v6 )
      goto LABEL_5;
  }
  else if ( v6 )
  {
    goto LABEL_5;
  }
  SecurityInfo = 0;
  memset_0(&v30, 0, 0x70u);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset_0(v40, 0, 0x68u);
  *(_OWORD *)(a1 + 104) = 0;
  *(_OWORD *)(a1 + 120) = 0;
  *(_OWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  v38 = 0;
  v39 = 0;
  *(_QWORD *)(a1 + 8) = v4;
  Action::CreateUniqueId(a1, v44);
  *(_OWORD *)(a1 + 160) = *(_OWORD *)a3;
  *(_QWORD *)(a1 + 176) = *(_QWORD *)(a3 + 16);
  v12 = Duplicate(*(unsigned __int8 **)(a3 + 16), *(unsigned int *)(a3 + 8));
  *(_QWORD *)(a1 + 176) = v12;
  *(_QWORD *)&v38 = *(_QWORD *)(a1 + 160);
  DWORD2(v38) = *(_DWORD *)(a1 + 168);
  v13 = v39;
  if ( DWORD2(v38) )
    v13 = v12;
  v39 = v13;
  *(_DWORD *)(a1 + 104) = 4;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 112) = &v38;
  if ( CSchedule::IsScheduleOwner(*(CSchedule **)(a1 + 8), L"S-1-5-18", 0) )
  {
LABEL_14:
    v16 = (void *)std::operator+<unsigned short>(v50, L"Publish Action ", v44);
    std::wstring::operator=(v46, v16);
    LOBYTE(v17) = 1;
    std::wstring::_Tidy(v50, v17, 0);
    LODWORD(v28) = 1;
    v18 = v44;
    if ( v45 >= 8 )
      v18 = (_QWORD *)v44[0];
    *(_QWORD *)&v27 = v18;
    v19 = v46;
    if ( v47 >= 8 )
      v19 = (_QWORD *)v46[0];
    *((_QWORD *)&v27 + 1) = v19;
    *((_QWORD *)&v28 + 1) = a1 + 104;
    v42 = 1;
    v43 = &v27;
    v20 = (void *)std::operator+<unsigned short>(v50, L"NT TASK\\", v44);
    std::wstring::operator=(v48, v20);
    LOBYTE(v21) = 1;
    std::wstring::_Tidy(v50, v21, 0);
    v22 = v48;
    if ( v49 >= 8 )
      v22 = (_QWORD *)v48[0];
    v40[1] = v22;
    v40[0] = a1 + 88;
    v41 = 4;
    v26 = 0;
    if ( !(unsigned int)UbpmTriggerConsumerRegister(v40, &v26) )
    {
      if ( (byte_180030D03 & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(v23, PublishSet, v24, 1, v50);
      goto LABEL_24;
    }
    goto LABEL_21;
  }
  v15 = *(SecurityContext **)(v14 + 272);
  if ( !v15 )
  {
LABEL_21:
    SecurityInfo = -2147467259;
    goto LABEL_24;
  }
  SecurityInfo = SecurityContext::GetSecurityInfo(v15, v31, &v35, &v36, &v37);
  if ( SecurityInfo >= 0 )
  {
    v32 = 2;
    v30 = 1;
    v31[1] = 0;
    v33 = 2;
    v34 = 0;
    *(_QWORD *)(a1 + 136) = &v30;
    goto LABEL_14;
  }
LABEL_24:
  TsiFreeActionAccountInfoSecurityParameters((struct _UBPM_ACTION_ACCOUNT_INFO *)&v30);
  v25 = *(_QWORD *)(a1 + 176);
  if ( SecurityInfo >= 0 )
  {
    v7 = v25 != 0;
    goto LABEL_6;
  }
  if ( v25 )
  {
    free(*(void **)(a1 + 176));
    *(_QWORD *)(a1 + 176) = 0;
  }
LABEL_5:
  v7 = 0;
LABEL_6:
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v46, a2, 0);
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v48, v8, 0);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v44, v9, 0);
  return v7;
}

```

## disassembly

```asm
0x18001aba0  mov     [rsp-8+arg_8], rbx
0x18001aba5  push    rbp
0x18001aba6  push    rsi
0x18001aba7  push    rdi
0x18001aba8  push    r14
0x18001abaa  push    r15
0x18001abac  lea     rbp, [rsp-0F0h]
0x18001abb4  sub     rsp, 1F0h
0x18001abbb  mov     rax, cs:__security_cookie
0x18001abc2  xor     rax, rsp
0x18001abc5  mov     [rbp+110h+var_30], rax
0x18001abcc  mov     rsi, r8
0x18001abcf  mov     r14, rdx
0x18001abd2  mov     rdi, rcx
0x18001abd5  mov     ecx, 7
0x18001abda  mov     [rbp+110h+var_98], rcx
0x18001abde  mov     [rbp+110h+var_A0], 0
0x18001abe6  xor     eax, eax
0x18001abe8  mov     word ptr [rbp+110h+var_B0], ax
0x18001abec  mov     [rbp+110h+var_58], rcx
0x18001abf3  mov     [rbp+110h+var_60], rax
0x18001abfa  mov     word ptr [rbp+110h+var_70], ax
0x18001ac01  mov     [rbp+110h+var_78], rcx
0x18001ac08  mov     [rbp+110h+var_80], rax
0x18001ac0f  mov     word ptr [rbp+110h+var_90], ax
0x18001ac16  test    rdx, rdx
0x18001ac19  jz      short loc_18001AC2F
0x18001ac1b  test    r8, r8
0x18001ac1e  jz      short loc_18001AC2F
0x18001ac20  mov     eax, [r8+8]
0x18001ac24  cmp     qword ptr [r8+10h], 0
0x18001ac29  jnz     short loc_18001AC8B
0x18001ac2b  test    eax, eax
0x18001ac2d  jz      short loc_18001AC8F
0x18001ac2f  xor     ebx, ebx
0x18001ac31  xor     r8d, r8d
0x18001ac34  mov     dl, 1
0x18001ac36  lea     rcx, [rbp+110h+var_90]
0x18001ac3d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ac42  nop
0x18001ac43  xor     r8d, r8d
0x18001ac46  mov     dl, 1
0x18001ac48  lea     rcx, [rbp+110h+var_70]
0x18001ac4f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ac54  nop
0x18001ac55  xor     r8d, r8d
0x18001ac58  mov     dl, 1
0x18001ac5a  lea     rcx, [rbp+110h+var_B0]
0x18001ac5e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ac63  mov     eax, ebx
0x18001ac65  mov     rcx, [rbp+110h+var_30]
0x18001ac6c  xor     rcx, rsp; StackCookie
0x18001ac6f  call    __security_check_cookie
0x18001ac74  mov     rbx, [rsp+210h+arg_8]
0x18001ac7c  add     rsp, 1F0h
0x18001ac83  pop     r15
0x18001ac85  pop     r14
0x18001ac87  pop     rdi
0x18001ac88  pop     rsi
0x18001ac89  pop     rbp
0x18001ac8a  retn
0x18001ac8b  test    eax, eax
0x18001ac8d  jz      short loc_18001AC2F
0x18001ac8f  xor     ebx, ebx
0x18001ac91  xor     edx, edx; Val
0x18001ac93  lea     r8d, [rbx+70h]; Size
0x18001ac97  lea     rcx, [rsp+210h+var_1B0]; void *
0x18001ac9c  call    memset_0
0x18001aca1  xorps   xmm0, xmm0
0x18001aca4  xor     eax, eax
0x18001aca6  movups  [rsp+210h+var_1D8], xmm0
0x18001acab  movups  [rsp+210h+var_1C8], xmm0
0x18001acb0  mov     [rsp+210h+var_1B8], rax
0x18001acb5  xor     edx, edx; Val
0x18001acb7  lea     r8d, [rbx+68h]; Size
0x18001acbb  lea     rcx, [rbp+110h+var_120]; void *
0x18001acbf  call    memset_0
0x18001acc4  lea     r15, [rdi+68h]
0x18001acc8  xorps   xmm0, xmm0
0x18001accb  xor     eax, eax
0x18001accd  movups  xmmword ptr [r15], xmm0
0x18001acd1  movups  xmmword ptr [r15+10h], xmm0
0x18001acd6  movups  xmmword ptr [r15+20h], xmm0
0x18001acdb  mov     [r15+30h], rax
0x18001acdf  movups  [rbp+110h+var_140], xmm0
0x18001ace3  mov     [rbp+110h+var_130], rax
0x18001ace7  mov     [rdi+8], r14
0x18001aceb  lea     rdx, [rbp+110h+var_B0]
0x18001acef  mov     rcx, rdi
0x18001acf2  call    ?CreateUniqueId@Action@@IEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Action::CreateUniqueId(std::wstring *)
0x18001acf7  movups  xmm0, xmmword ptr [rsi]
0x18001acfa  movups  xmmword ptr [rdi+0A0h], xmm0
0x18001ad01  movsd   xmm1, qword ptr [rsi+10h]
0x18001ad06  movsd   qword ptr [rdi+0B0h], xmm1
0x18001ad0e  mov     edx, [rsi+8]; Size
0x18001ad11  mov     rcx, [rsi+10h]; Src
0x18001ad15  call    ?Duplicate@@YAPEAEPEAE_K@Z; Duplicate(uchar *,unsigned __int64)
0x18001ad1a  mov     rdx, rax
0x18001ad1d  mov     [rdi+0B0h], rax
0x18001ad24  mov     rax, [rdi+0A0h]
0x18001ad2b  mov     qword ptr [rbp+110h+var_140], rax
0x18001ad2f  mov     eax, [rdi+0A8h]
0x18001ad35  mov     dword ptr [rbp+110h+var_140+8], eax
0x18001ad38  mov     rcx, [rbp+110h+var_130]
0x18001ad3c  test    eax, eax
0x18001ad3e  cmovnz  rcx, rdx
0x18001ad42  mov     [rbp+110h+var_130], rcx
0x18001ad46  lea     esi, [rbx+4]
0x18001ad49  mov     [r15], esi
0x18001ad4c  mov     [rdi+88h], rbx
0x18001ad53  lea     rax, [rbp+110h+var_140]
0x18001ad57  mov     [rdi+70h], rax
0x18001ad5b  mov     r11, [rdi+8]
0x18001ad5f  xor     r8d, r8d; unsigned __int16 *
0x18001ad62  lea     rdx, aS1518; "S-1-5-18"
0x18001ad69  mov     rcx, r11; this
0x18001ad6c  call    ?IsScheduleOwner@CSchedule@@QEAAHQEAG0@Z; CSchedule::IsScheduleOwner(ushort * const,ushort * const)
0x18001ad71  test    eax, eax
0x18001ad73  jnz     short loc_18001ADD7
0x18001ad75  mov     rcx, [r11+110h]; this
0x18001ad7c  test    rcx, rcx
0x18001ad7f  jz      loc_18001AED3
0x18001ad85  lea     rax, [rbp+110h+var_148]
0x18001ad89  mov     [rsp+210h+var_1F0], rax; struct _SID_AND_ATTRIBUTES **
0x18001ad8e  lea     r9, [rbp+110h+var_150]; unsigned int *
0x18001ad92  lea     r8, [rbp+110h+var_160]; void **
0x18001ad96  lea     rdx, [rsp+210h+var_1A8]; struct _DAB_SID_INFO **
0x18001ad9b  call    ?GetSecurityInfo@SecurityContext@@QEAAJPEAPEAU_DAB_SID_INFO@@PEAPEAXPEAKPEAPEAU_SID_AND_ATTRIBUTES@@@Z; SecurityContext::GetSecurityInfo(_DAB_SID_INFO * *,void * *,ulong *,_SID_AND_ATTRIBUTES * *)
0x18001ada0  mov     ebx, eax
0x18001ada2  test    eax, eax
0x18001ada4  js      loc_18001AF01
0x18001adaa  lea     eax, [rsi-2]
0x18001adad  mov     [rbp+110h+var_190], eax
0x18001adb0  mov     [rsp+210h+var_1B0], 1
0x18001adb8  mov     [rsp+210h+var_1A0], 0
0x18001adc1  mov     [rbp+110h+var_18C], eax
0x18001adc4  mov     [rbp+110h+var_164], 0
0x18001adcb  lea     rax, [rsp+210h+var_1B0]
0x18001add0  mov     [rdi+88h], rax
0x18001add7  lea     r8, [rbp+110h+var_B0]
0x18001addb  lea     rdx, aPublishAction; "Publish Action "
0x18001ade2  lea     rcx, [rbp+110h+var_50]
0x18001ade9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18001adee  mov     rdx, rax; Src
0x18001adf1  lea     rcx, [rbp+110h+var_90]; void *
0x18001adf8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001adfd  xor     r8d, r8d
0x18001ae00  mov     dl, 1
0x18001ae02  lea     rcx, [rbp+110h+var_50]
0x18001ae09  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ae0e  mov     dword ptr [rsp+210h+var_1C8], 1
0x18001ae16  lea     rax, [rbp+110h+var_B0]
0x18001ae1a  cmp     [rbp+110h+var_98], 8
0x18001ae1f  cmovnb  rax, [rbp+110h+var_B0]
0x18001ae24  mov     qword ptr [rsp+210h+var_1D8], rax
0x18001ae29  lea     rax, [rbp+110h+var_90]
0x18001ae30  cmp     [rbp+110h+var_78], 8
0x18001ae38  cmovnb  rax, [rbp+110h+var_90]
0x18001ae40  mov     qword ptr [rsp+210h+var_1D8+8], rax
0x18001ae45  mov     qword ptr [rsp+210h+var_1C8+8], r15
0x18001ae4a  mov     [rbp+110h+var_100], 1
0x18001ae51  lea     rax, [rsp+210h+var_1D8]
0x18001ae56  mov     [rbp+110h+var_F8], rax
0x18001ae5a  lea     r8, [rbp+110h+var_B0]
0x18001ae5e  lea     rdx, aNtTask; "NT TASK\\"
0x18001ae65  lea     rcx, [rbp+110h+var_50]
0x18001ae6c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV10@@Z; std::operator+<ushort>(ushort const *,std::wstring const &)
0x18001ae71  mov     rdx, rax; Src
0x18001ae74  lea     rcx, [rbp+110h+var_70]; void *
0x18001ae7b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ae80  xor     r8d, r8d
0x18001ae83  mov     dl, 1
0x18001ae85  lea     rcx, [rbp+110h+var_50]
0x18001ae8c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ae91  lea     rax, [rbp+110h+var_70]
0x18001ae98  cmp     [rbp+110h+var_58], 8
0x18001aea0  cmovnb  rax, [rbp+110h+var_70]
0x18001aea8  mov     [rbp+110h+var_118], rax
0x18001aeac  lea     rax, [rdi+58h]
0x18001aeb0  mov     [rbp+110h+var_120], rax
0x18001aeb4  mov     [rbp+110h+var_110], esi
0x18001aeb7  mov     [rsp+210h+var_1E0], 0
0x18001aec0  lea     rdx, [rsp+210h+var_1E0]
0x18001aec5  lea     rcx, [rbp+110h+var_120]
0x18001aec9  call    cs:__imp_UbpmTriggerConsumerRegister
0x18001aecf  test    eax, eax
0x18001aed1  jz      short loc_18001AEDA
0x18001aed3  mov     ebx, 80004005h
0x18001aed8  jmp     short loc_18001AF01
0x18001aeda  test    cs:byte_180030D03, sil
0x18001aee1  jz      short loc_18001AF01
0x18001aee3  lea     rax, [rbp+110h+var_50]
0x18001aeea  mov     [rsp+210h+var_1F0], rax
0x18001aeef  mov     r9d, 1
0x18001aef5  lea     rdx, PublishSet
0x18001aefc  call    McGenEventWrite_EventWriteTransfer
0x18001af01  lea     rcx, [rsp+210h+var_1B0]; struct _UBPM_ACTION_ACCOUNT_INFO *
0x18001af06  call    ?TsiFreeActionAccountInfoSecurityParameters@@YAXPEAU_UBPM_ACTION_ACCOUNT_INFO@@@Z; TsiFreeActionAccountInfoSecurityParameters(_UBPM_ACTION_ACCOUNT_INFO *)
0x18001af0b  mov     rax, [rdi+0B0h]
0x18001af12  test    ebx, ebx
0x18001af14  jns     short loc_18001AF38
0x18001af16  test    rax, rax
0x18001af19  jz      loc_18001AC2F
0x18001af1f  mov     rcx, rax; Block
0x18001af22  call    cs:__imp_free
0x18001af28  mov     qword ptr [rdi+0B0h], 0
0x18001af33  jmp     loc_18001AC2F
0x18001af38  xor     ebx, ebx
0x18001af3a  test    rax, rax
0x18001af3d  setnz   bl
0x18001af40  jmp     loc_18001AC31
```
