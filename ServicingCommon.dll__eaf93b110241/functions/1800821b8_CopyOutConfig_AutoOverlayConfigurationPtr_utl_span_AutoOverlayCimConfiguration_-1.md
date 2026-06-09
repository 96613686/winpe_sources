# CopyOutConfig(AutoOverlayConfigurationPtr &,utl::span<AutoOverlayCimConfiguration,-1>)

- ea: `0x1800821b8`
- end: `0x1800826ec`
- name: `?CopyOutConfig@@YAJAEAVAutoOverlayConfigurationPtr@@V?$span@UAutoOverlayCimConfiguration@@$0?0@utl@@@Z`
- size: `1332`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180083d74`
- `0x1800840f8`

## callees

- `0x18001f5d4`
- `0x180020958`
- `0x1800293a0`
- `0x18007d93c`
- `0x18007dab4`
- `0x180081c50`
- `0x180081cc0`
- `0x1800821b8`
- `0x1800826f4`

## string_xrefs

- `0x180082496`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800824e4`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008251c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082568`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800825b4`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082600`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008262f`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180082676`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800824b0`: `CopyOutConfig`
- `0x1800824fd`: `CopyOutConfig`
- `0x180082533`: `CopyOutConfig`
- `0x18008257f`: `CopyOutConfig`
- `0x1800825cb`: `CopyOutConfig`
- `0x180082617`: `CopyOutConfig`
- `0x180082649`: `CopyOutConfig`
- `0x180082690`: `CopyOutConfig`
- `0x180082655`: `CimEntry.AutoRelativePath.length() < 0xffffffffUL`

## pseudocode

```c
__int64 __fastcall CopyOutConfig(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // r13
  char v5; // r14
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r15
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm2
  __int64 v14; // xmm3_8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  void *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rax
  unsigned int v30; // ebx
  _QWORD *v31; // rdx
  __int64 v32; // r8
  const char **v33; // rdx
  __int64 v34; // r8
  const char *v36; // [rsp+20h] [rbp-E0h] BYREF
  const char *v37; // [rsp+28h] [rbp-D8h]
  __int64 v38; // [rsp+30h] [rbp-D0h]
  const char *v39; // [rsp+38h] [rbp-C8h]
  __int64 v40; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+48h] [rbp-B8h]
  _QWORD v42[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v43[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v44[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v45[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v46[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v47[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v48; // [rsp+110h] [rbp+10h] BYREF
  void *Destination; // [rsp+118h] [rbp+18h] BYREF
  __int64 v50; // [rsp+120h] [rbp+20h] BYREF
  __int64 v51; // [rsp+128h] [rbp+28h] BYREF
  __int64 v52; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v53[5]; // [rsp+138h] [rbp+38h] BYREF

  v2 = 0;
  v48 = 0;
  v5 = 0;
  utl::make_unique<OVERLAY_CIM_CONFIGURATION [0],0>(&v51, a2[1]);
  v6 = v51;
  if ( !v51 )
  {
    v38 = 681;
    v36 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v33 = &v36;
    v34 = 3221225495LL;
    v37 = "CopyOutConfig";
    v39 = "OutCims";
    goto LABEL_36;
  }
  v7 = *a1;
  v8 = 0;
  v51 = 0;
  *(_QWORD *)(v7 + 32) = v6;
  *(_DWORD *)(*a1 + 24) = *((_DWORD *)a2 + 2);
  v9 = 0;
  v10 = *a2;
  v11 = *a2 + 136LL * a2[1];
  v41 = v11;
LABEL_3:
  if ( v10 == v11 )
  {
    utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v51);
    return 0;
  }
  if ( (unsigned __int64)((__int64)(*(_QWORD *)(v10 + 64) - *(_QWORD *)(v10 + 56)) >> 1) >= 0xFFFFFFFF )
  {
    v38 = 688;
    v36 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v33 = &v36;
    v37 = "CopyOutConfig";
    v39 = "CimEntry.AutoRelativePath.length() < 0xffffffffUL";
    goto LABEL_33;
  }
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v10 + 96) - *(_QWORD *)(v10 + 88)) >> 4) >= 0xFFFFFFFF )
  {
    v47[2] = 689;
    v47[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
    v33 = (const char **)v47;
    v47[1] = "CopyOutConfig";
    v47[3] = "CimEntry.AutoImages.size() < 0xffffffffUL";
LABEL_33:
    v34 = 3221225659LL;
LABEL_36:
    v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v48,
            v33,
            v34);
    goto LABEL_37;
  }
  v12 = *(_OWORD *)(v10 + 16);
  v13 = *(_OWORD *)(v10 + 32);
  v14 = *(_QWORD *)(v10 + 48);
  v15 = 56 * v9;
  v16 = *(_QWORD *)(*a1 + 32);
  *(_OWORD *)(v16 + v15) = *(_OWORD *)v10;
  *(_OWORD *)(v16 + v15 + 16) = v12;
  *(_OWORD *)(v16 + v15 + 32) = v13;
  *(_QWORD *)(v16 + v15 + 48) = v14;
  if ( *(_QWORD *)(v10 + 56) == *(_QWORD *)(v10 + 64) )
  {
    v17 = 56 * v8;
  }
  else
  {
    CopyOutString(v53, v10 + 56);
    v18 = v53[0];
    if ( !v53[0] )
    {
      v46[2] = 696;
      v46[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v46[1] = "CopyOutConfig";
      v46[3] = "OutString";
      v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v48,
              v46,
              3221225495LL);
      utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(v53);
      goto LABEL_37;
    }
    v17 = 56 * v8;
    v19 = *(_QWORD *)(*a1 + 32);
    v53[0] = 0;
    *(_QWORD *)(v19 + 56 * v8 + 32) = v18;
    utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(v53);
  }
  v20 = *(_QWORD *)(v10 + 120);
  if ( *(_QWORD *)(v10 + 112) == v20 )
  {
LABEL_17:
    utl::make_unique<OVERLAY_IMAGE_CONFIGURATION [0],0>(
      &v50,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v10 + 96) - *(_QWORD *)(v10 + 88)) >> 4));
    v23 = v50;
    if ( v50 )
    {
      v24 = *a1;
      v50 = 0;
      *(_QWORD *)(*(_QWORD *)(v24 + 32) + v17 + 48) = v23;
      *(_DWORD *)(*(_QWORD *)(*a1 + 32) + v17 + 40) = -1431655765
                                                    * ((__int64)(*(_QWORD *)(v10 + 96) - *(_QWORD *)(v10 + 88)) >> 4);
      v25 = 0;
      v26 = *(_QWORD *)(v10 + 96);
      v27 = *(_QWORD *)(v10 + 88);
      v40 = v26;
      while ( 1 )
      {
        if ( v27 == v26 )
        {
          utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v50);
          v11 = v41;
          ++v8;
          v10 += 136;
          v9 = v8;
          v2 = 0;
          goto LABEL_3;
        }
        if ( (unsigned __int64)((__int64)(*(_QWORD *)(v27 + 24) - *(_QWORD *)(v27 + 16)) >> 1) >= 0xFFFFFFFF )
          break;
        *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(*a1 + 32) + v17 + 48) + 16 * v25) = *(_OWORD *)v27;
        CopyOutString(&v52, v27 + 16);
        v28 = v52;
        if ( !v52 )
        {
          v42[2] = 722;
          v42[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v42[1] = "CopyOutConfig";
          v42[3] = "OutString";
          v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v48,
                  v42,
                  3221225495LL);
          utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v52);
          goto LABEL_28;
        }
        v29 = *a1;
        v52 = 0;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v29 + 32) + v17 + 48) + 16 * v2 + 8) = v28;
        utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v52);
        v26 = v40;
        v25 = ++v2;
        v27 += 48;
      }
      v43[2] = 717;
      v43[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v31 = v43;
      v32 = 3221225659LL;
      v43[1] = "CopyOutConfig";
      v43[3] = "Image.AutoName.length() < 0xffffffffUL";
    }
    else
    {
      v44[2] = 710;
      v44[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v31 = v44;
      v32 = 3221225495LL;
      v44[1] = "CopyOutConfig";
      v44[3] = "OutImages";
    }
    v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v48,
            v31,
            v32);
LABEL_28:
    utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v50);
    goto LABEL_37;
  }
  utl::make_unique<unsigned char [0],0>(&Destination, v20 - *(_QWORD *)(v10 + 112));
  v21 = Destination;
  if ( Destination )
    memcpy_s(
      Destination,
      *(_QWORD *)(v10 + 120) - *(_QWORD *)(v10 + 112),
      *(const void *const *)(v10 + 112),
      *(_QWORD *)(v10 + 120) - *(_QWORD *)(v10 + 112));
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&Destination);
    v21 = Destination;
  }
  if ( v21 )
  {
    v17 = 56 * v8;
    v22 = *(_QWORD *)(*a1 + 32);
    Destination = 0;
    *(_QWORD *)(v22 + 56 * v8 + 16) = v21;
    utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&Destination);
    goto LABEL_17;
  }
  v45[2] = 704;
  v45[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
  v45[1] = "CopyOutConfig";
  v45[3] = "OutBinary";
  v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
          &v48,
          v45,
          3221225495LL);
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&Destination);
LABEL_37:
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v51);
  return v30;
}

```

## disassembly

```asm
0x1800821b8  mov     [rsp-8+arg_10], rbx
0x1800821bd  push    rbp
0x1800821be  push    rsi
0x1800821bf  push    rdi
0x1800821c0  push    r12
0x1800821c2  push    r13
0x1800821c4  push    r14
0x1800821c6  push    r15
0x1800821c8  lea     rbp, [rsp-70h]
0x1800821cd  sub     rsp, 170h
0x1800821d4  mov     rax, cs:__security_cookie
0x1800821db  xor     rax, rsp
0x1800821de  mov     [rbp+0A0h+var_40], rax
0x1800821e2  xor     r13d, r13d
0x1800821e5  mov     rbx, rdx
0x1800821e8  mov     [rbp+0A0h+var_90], r13d
0x1800821ec  mov     r12, rcx
0x1800821ef  mov     rdx, [rdx+8]
0x1800821f3  lea     rcx, [rbp+0A0h+var_78]
0x1800821f7  mov     r14d, r13d
0x1800821fa  mov     [rbp+0A0h+var_90], r13d
0x1800821fe  call    ??$make_unique@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@0@_K@Z; utl::make_unique<OVERLAY_CIM_CONFIGURATION [0],0>(unsigned __int64)
0x180082203  mov     rcx, [rbp+0A0h+var_78]
0x180082207  test    rcx, rcx
0x18008220a  jz      loc_180082676
0x180082210  mov     rax, [r12]
0x180082214  mov     r15d, r13d
0x180082217  mov     [rbp+0A0h+var_78], r13
0x18008221b  mov     [rax+20h], rcx
0x18008221f  mov     rcx, [r12]
0x180082223  mov     eax, [rbx+8]
0x180082226  mov     [rcx+18h], eax
0x180082229  mov     ecx, r13d
0x18008222c  imul    rax, [rbx+8], 88h
0x180082234  mov     rdi, [rbx]
0x180082237  add     rax, rdi
0x18008223a  mov     [rsp+1A0h+var_158], rax
0x18008223f  mov     rbx, 0AAAAAAAAAAAAAAABh
0x180082249  mov     edx, 0FFFFFFFFh
0x18008224e  cmp     rdi, rax
0x180082251  jz      loc_180082669
0x180082257  lea     r8, [rdi+38h]
0x18008225b  mov     rax, [r8+8]
0x18008225f  sub     rax, [r8]
0x180082262  sar     rax, 1
0x180082265  cmp     rax, rdx
0x180082268  jnb     loc_18008262F
0x18008226e  mov     rax, [rdi+60h]
0x180082272  sub     rax, [rdi+58h]
0x180082276  sar     rax, 4
0x18008227a  imul    rax, rbx
0x18008227e  cmp     rax, rdx
0x180082281  jnb     loc_180082600
0x180082287  mov     rax, [r12]
0x18008228b  movups  xmm0, xmmword ptr [rdi]
0x18008228e  movups  xmm1, xmmword ptr [rdi+10h]
0x180082292  movups  xmm2, xmmword ptr [rdi+20h]
0x180082296  movsd   xmm3, qword ptr [rdi+30h]
0x18008229b  imul    rdx, rcx, 38h ; '8'
0x18008229f  mov     rcx, [rax+20h]
0x1800822a3  movups  xmmword ptr [rcx+rdx], xmm0
0x1800822a7  movups  xmmword ptr [rcx+rdx+10h], xmm1
0x1800822ac  movups  xmmword ptr [rcx+rdx+20h], xmm2
0x1800822b1  movsd   qword ptr [rcx+rdx+30h], xmm3
0x1800822b7  mov     rax, [rdi+40h]
0x1800822bb  cmp     [r8], rax
0x1800822be  jnz     short loc_1800822C6
0x1800822c0  imul    rsi, r15, 38h ; '8'
0x1800822c4  jmp     short loc_1800822FD
0x1800822c6  mov     rdx, r8
0x1800822c9  lea     rcx, [rbp+0A0h+var_68]
0x1800822cd  call    ?CopyOutString@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@@Z; CopyOutString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1800822d2  mov     rdx, [rbp+0A0h+var_68]
0x1800822d6  test    rdx, rdx
0x1800822d9  jz      loc_1800825B4
0x1800822df  mov     rax, [r12]
0x1800822e3  imul    rsi, r15, 38h ; '8'
0x1800822e7  mov     rcx, [rax+20h]
0x1800822eb  mov     [rbp+0A0h+var_68], r13
0x1800822ef  mov     [rcx+rsi+20h], rdx
0x1800822f4  lea     rcx, [rbp+0A0h+var_68]
0x1800822f8  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800822fd  mov     rdx, [rdi+78h]
0x180082301  cmp     [rdi+70h], rdx
0x180082305  jz      short loc_180082384
0x180082307  sub     rdx, [rdi+70h]
0x18008230b  lea     rcx, [rbp+0A0h+Destination]
0x18008230f  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180082314  mov     rbx, [rbp+0A0h+Destination]
0x180082318  mov     esi, r14d
0x18008231b  test    rbx, rbx
0x18008231e  setnz   al
0x180082321  and     esi, 1
0x180082324  test    al, al
0x180082326  jz      short loc_18008233E
0x180082328  mov     r8, [rdi+70h]; Source
0x18008232c  mov     rcx, rbx; Destination
0x18008232f  mov     rdx, [rdi+78h]
0x180082333  sub     rdx, r8; DestinationSize
0x180082336  mov     r9, rdx; SourceSize
0x180082339  call    memcpy_s
0x18008233e  test    esi, esi
0x180082340  jz      short loc_180082353
0x180082342  and     r14d, 0FFFFFFFEh
0x180082346  lea     rcx, [rbp+0A0h+Destination]
0x18008234a  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008234f  mov     rbx, [rbp+0A0h+Destination]
0x180082353  test    rbx, rbx
0x180082356  jz      loc_180082568
0x18008235c  mov     rax, [r12]
0x180082360  imul    rsi, r15, 38h ; '8'
0x180082364  mov     rcx, [rax+20h]
0x180082368  mov     [rbp+0A0h+Destination], r13
0x18008236c  mov     [rcx+rsi+10h], rbx
0x180082371  lea     rcx, [rbp+0A0h+Destination]
0x180082375  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008237a  mov     rbx, 0AAAAAAAAAAAAAAABh
0x180082384  mov     rdx, [rdi+60h]
0x180082388  lea     rcx, [rbp+0A0h+var_80]
0x18008238c  sub     rdx, [rdi+58h]
0x180082390  sar     rdx, 4
0x180082394  imul    rdx, rbx
0x180082398  call    ??$make_unique@$$BY0A@UOVERLAY_IMAGE_CONFIGURATION@@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@UOVERLAY_IMAGE_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_IMAGE_CONFIGURATION@@@utl@@@0@_K@Z; utl::make_unique<OVERLAY_IMAGE_CONFIGURATION [0],0>(unsigned __int64)
0x18008239d  mov     rdx, [rbp+0A0h+var_80]
0x1800823a1  test    rdx, rdx
0x1800823a4  jz      loc_18008251C
0x1800823aa  mov     rax, [r12]
0x1800823ae  mov     [rbp+0A0h+var_80], r13
0x1800823b2  mov     rcx, [rax+20h]
0x1800823b6  mov     [rcx+rsi+30h], rdx
0x1800823bb  mov     rax, [r12]
0x1800823bf  mov     rdx, [rdi+60h]
0x1800823c3  sub     rdx, [rdi+58h]
0x1800823c7  sar     rdx, 4
0x1800823cb  mov     rcx, [rax+20h]
0x1800823cf  imul    rdx, rbx
0x1800823d3  mov     [rcx+rsi+28h], edx
0x1800823d7  xor     ecx, ecx
0x1800823d9  mov     rax, [rdi+60h]
0x1800823dd  mov     rbx, [rdi+58h]
0x1800823e1  mov     [rsp+1A0h+var_160], rax
0x1800823e6  cmp     rbx, rax
0x1800823e9  jz      loc_180082473
0x1800823ef  lea     rdx, [rbx+10h]
0x1800823f3  mov     r8d, 0FFFFFFFFh
0x1800823f9  mov     rax, [rdx+8]
0x1800823fd  sub     rax, [rdx]
0x180082400  sar     rax, 1
0x180082403  cmp     rax, r8
0x180082406  jnb     loc_1800824E4
0x18008240c  mov     rax, [r12]
0x180082410  add     rcx, rcx
0x180082413  movups  xmm0, xmmword ptr [rbx]
0x180082416  mov     rax, [rax+20h]
0x18008241a  mov     rax, [rax+rsi+30h]
0x18008241f  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180082424  lea     rcx, [rbp+0A0h+var_70]
0x180082428  call    ?CopyOutString@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@@Z; CopyOutString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x18008242d  mov     rdx, [rbp+0A0h+var_70]
0x180082431  test    rdx, rdx
0x180082434  jz      short loc_180082496
0x180082436  mov     rax, [r12]
0x18008243a  mov     rcx, r13
0x18008243d  add     rcx, rcx
0x180082440  mov     [rbp+0A0h+var_70], 0
0x180082448  mov     rax, [rax+20h]
0x18008244c  mov     rax, [rax+rsi+30h]
0x180082451  mov     [rax+rcx*8+8], rdx
0x180082456  lea     rcx, [rbp+0A0h+var_70]
0x18008245a  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008245f  mov     rax, [rsp+1A0h+var_160]
0x180082464  inc     r13
0x180082467  mov     rcx, r13
0x18008246a  add     rbx, 30h ; '0'
0x18008246e  jmp     loc_1800823E6
0x180082473  lea     rcx, [rbp+0A0h+var_80]
0x180082477  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008247c  mov     rax, [rsp+1A0h+var_158]
0x180082481  inc     r15
0x180082484  add     rdi, 88h
0x18008248b  mov     rcx, r15
0x18008248e  xor     r13d, r13d
0x180082491  jmp     loc_18008223F
0x180082496  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008249d  mov     [rsp+1A0h+var_140], 2D2h
0x1800824a6  mov     [rsp+1A0h+var_150], rax
0x1800824ab  lea     rdx, [rsp+1A0h+var_150]
0x1800824b0  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x1800824b7  mov     r8d, 0C0000017h
0x1800824bd  mov     [rsp+1A0h+var_148], rax
0x1800824c2  lea     rcx, [rbp+0A0h+var_90]
0x1800824c6  lea     rax, aOutstring; "OutString"
0x1800824cd  mov     [rsp+1A0h+var_138], rax
0x1800824d2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800824d7  lea     rcx, [rbp+0A0h+var_70]
0x1800824db  mov     ebx, eax
0x1800824dd  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800824e2  jmp     short loc_18008255A
0x1800824e4  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800824eb  mov     [rbp+0A0h+var_120], 2CDh
0x1800824f3  mov     [rsp+1A0h+var_130], rax
0x1800824f8  lea     rdx, [rsp+1A0h+var_130]
0x1800824fd  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x180082504  mov     r8d, 0C00000BBh
0x18008250a  mov     [rsp+1A0h+var_128], rax
0x18008250f  lea     rax, aImageAutonameL; "Image.AutoName.length() < 0xffffffffUL"
0x180082516  mov     [rbp+0A0h+var_118], rax
0x18008251a  jmp     short loc_18008254F
0x18008251c  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082523  mov     [rbp+0A0h+var_100], 2C6h
0x18008252b  mov     [rbp+0A0h+var_110], rax
0x18008252f  lea     rdx, [rbp+0A0h+var_110]
0x180082533  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x18008253a  mov     r8d, 0C0000017h
0x180082540  mov     [rbp+0A0h+var_108], rax
0x180082544  lea     rax, aOutimages; "OutImages"
0x18008254b  mov     [rbp+0A0h+var_F8], rax
0x18008254f  lea     rcx, [rbp+0A0h+var_90]
0x180082553  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180082558  mov     ebx, eax
0x18008255a  lea     rcx, [rbp+0A0h+var_80]
0x18008255e  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180082563  jmp     loc_1800826B9
0x180082568  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008256f  mov     [rbp+0A0h+var_E0], 2C0h
0x180082577  mov     [rbp+0A0h+var_F0], rax
0x18008257b  lea     rdx, [rbp+0A0h+var_F0]
0x18008257f  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x180082586  mov     r8d, 0C0000017h
0x18008258c  mov     [rbp+0A0h+var_E8], rax
0x180082590  lea     rcx, [rbp+0A0h+var_90]
0x180082594  lea     rax, aOutbinary; "OutBinary"
0x18008259b  mov     [rbp+0A0h+var_D8], rax
0x18008259f  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800825a4  lea     rcx, [rbp+0A0h+Destination]
0x1800825a8  mov     ebx, eax
0x1800825aa  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800825af  jmp     loc_1800826B9
0x1800825b4  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800825bb  mov     [rbp+0A0h+var_C0], 2B8h
0x1800825c3  mov     [rbp+0A0h+var_D0], rax
0x1800825c7  lea     rdx, [rbp+0A0h+var_D0]
0x1800825cb  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x1800825d2  mov     r8d, 0C0000017h
0x1800825d8  mov     [rbp+0A0h+var_C8], rax
0x1800825dc  lea     rcx, [rbp+0A0h+var_90]
0x1800825e0  lea     rax, aOutstring; "OutString"
0x1800825e7  mov     [rbp+0A0h+var_B8], rax
0x1800825eb  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800825f0  lea     rcx, [rbp+0A0h+var_68]
0x1800825f4  mov     ebx, eax
0x1800825f6  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800825fb  jmp     loc_1800826B9
0x180082600  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082607  mov     [rbp+0A0h+var_A0], 2B1h
0x18008260f  mov     [rbp+0A0h+var_B0], rax
0x180082613  lea     rdx, [rbp+0A0h+var_B0]
0x180082617  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x18008261e  mov     [rbp+0A0h+var_A8], rax
0x180082622  lea     rax, aCimentryAutoim_0; "CimEntry.AutoImages.size() < 0xffffffff"...
0x180082629  mov     [rbp+0A0h+var_98], rax
0x18008262d  jmp     short loc_180082661
0x18008262f  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180082636  mov     [rsp+1A0h+var_170], 2B0h
0x18008263f  mov     [rsp+1A0h+var_180], rax
0x180082644  lea     rdx, [rsp+1A0h+var_180]
0x180082649  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x180082650  mov     [rsp+1A0h+var_178], rax
0x180082655  lea     rax, aCimentryAutore_2; "CimEntry.AutoRelativePath.length() < 0x"...
0x18008265c  mov     [rsp+1A0h+var_168], rax
0x180082661  mov     r8d, 0C00000BBh
0x180082667  jmp     short loc_1800826AE
0x180082669  lea     rcx, [rbp+0A0h+var_78]
0x18008266d  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180082672  xor     eax, eax
0x180082674  jmp     short loc_1800826C4
0x180082676  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008267d  mov     [rsp+1A0h+var_170], 2A9h
0x180082686  mov     [rsp+1A0h+var_180], rax
0x18008268b  lea     rdx, [rsp+1A0h+var_180]
0x180082690  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x180082697  mov     r8d, 0C0000017h
0x18008269d  mov     [rsp+1A0h+var_178], rax
0x1800826a2  lea     rax, aOutcims; "OutCims"
0x1800826a9  mov     [rsp+1A0h+var_168], rax
0x1800826ae  lea     rcx, [rbp+0A0h+var_90]
0x1800826b2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800826b7  mov     ebx, eax
0x1800826b9  lea     rcx, [rbp+0A0h+var_78]
0x1800826bd  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800826c2  mov     eax, ebx
0x1800826c4  mov     rcx, [rbp+0A0h+var_40]
0x1800826c8  xor     rcx, rsp; StackCookie
0x1800826cb  call    __security_check_cookie
0x1800826d0  mov     rbx, [rsp+1A0h+arg_10]
0x1800826d8  add     rsp, 170h
0x1800826df  pop     r15
0x1800826e1  pop     r14
0x1800826e3  pop     r13
0x1800826e5  pop     r12
  ... truncated ...
```
