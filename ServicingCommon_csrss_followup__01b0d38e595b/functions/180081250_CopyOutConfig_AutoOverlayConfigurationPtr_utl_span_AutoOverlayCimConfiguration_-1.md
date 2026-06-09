# CopyOutConfig(AutoOverlayConfigurationPtr &,utl::span<AutoOverlayCimConfiguration,-1>)

- ea: `0x180081250`
- end: `0x180081784`
- name: `?CopyOutConfig@@YAJAEAVAutoOverlayConfigurationPtr@@V?$span@UAutoOverlayCimConfiguration@@$0?0@utl@@@Z`
- size: `1332`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180082e0c`
- `0x180083190`

## callees

- `0x18001f840`
- `0x180023378`
- `0x18002d2b0`
- `0x18007c9a0`
- `0x18007cb18`
- `0x180080ce8`
- `0x180080d58`
- `0x180081250`
- `0x18008178c`

## string_xrefs

- `0x18008152e`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008157c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800815b4`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081600`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008164c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081698`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800816c7`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x18008170e`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x180081548`: `CopyOutConfig`
- `0x180081595`: `CopyOutConfig`
- `0x1800815cb`: `CopyOutConfig`
- `0x180081617`: `CopyOutConfig`
- `0x180081663`: `CopyOutConfig`
- `0x1800816af`: `CopyOutConfig`
- `0x1800816e1`: `CopyOutConfig`
- `0x180081728`: `CopyOutConfig`
- `0x1800816ed`: `CimEntry.AutoRelativePath.length() < 0xffffffffUL`

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
0x180081250  mov     [rsp-8+arg_10], rbx
0x180081255  push    rbp
0x180081256  push    rsi
0x180081257  push    rdi
0x180081258  push    r12
0x18008125a  push    r13
0x18008125c  push    r14
0x18008125e  push    r15
0x180081260  lea     rbp, [rsp-70h]
0x180081265  sub     rsp, 170h
0x18008126c  mov     rax, cs:__security_cookie
0x180081273  xor     rax, rsp
0x180081276  mov     [rbp+0A0h+var_40], rax
0x18008127a  xor     r13d, r13d
0x18008127d  mov     rbx, rdx
0x180081280  mov     [rbp+0A0h+var_90], r13d
0x180081284  mov     r12, rcx
0x180081287  mov     rdx, [rdx+8]
0x18008128b  lea     rcx, [rbp+0A0h+var_78]
0x18008128f  mov     r14d, r13d
0x180081292  mov     [rbp+0A0h+var_90], r13d
0x180081296  call    ??$make_unique@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@0@_K@Z; utl::make_unique<OVERLAY_CIM_CONFIGURATION [0],0>(unsigned __int64)
0x18008129b  mov     rcx, [rbp+0A0h+var_78]
0x18008129f  test    rcx, rcx
0x1800812a2  jz      loc_18008170E
0x1800812a8  mov     rax, [r12]
0x1800812ac  mov     r15d, r13d
0x1800812af  mov     [rbp+0A0h+var_78], r13
0x1800812b3  mov     [rax+20h], rcx
0x1800812b7  mov     rcx, [r12]
0x1800812bb  mov     eax, [rbx+8]
0x1800812be  mov     [rcx+18h], eax
0x1800812c1  mov     ecx, r13d
0x1800812c4  imul    rax, [rbx+8], 88h
0x1800812cc  mov     rdi, [rbx]
0x1800812cf  add     rax, rdi
0x1800812d2  mov     [rsp+1A0h+var_158], rax
0x1800812d7  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1800812e1  mov     edx, 0FFFFFFFFh
0x1800812e6  cmp     rdi, rax
0x1800812e9  jz      loc_180081701
0x1800812ef  lea     r8, [rdi+38h]
0x1800812f3  mov     rax, [r8+8]
0x1800812f7  sub     rax, [r8]
0x1800812fa  sar     rax, 1
0x1800812fd  cmp     rax, rdx
0x180081300  jnb     loc_1800816C7
0x180081306  mov     rax, [rdi+60h]
0x18008130a  sub     rax, [rdi+58h]
0x18008130e  sar     rax, 4
0x180081312  imul    rax, rbx
0x180081316  cmp     rax, rdx
0x180081319  jnb     loc_180081698
0x18008131f  mov     rax, [r12]
0x180081323  movups  xmm0, xmmword ptr [rdi]
0x180081326  movups  xmm1, xmmword ptr [rdi+10h]
0x18008132a  movups  xmm2, xmmword ptr [rdi+20h]
0x18008132e  movsd   xmm3, qword ptr [rdi+30h]
0x180081333  imul    rdx, rcx, 38h ; '8'
0x180081337  mov     rcx, [rax+20h]
0x18008133b  movups  xmmword ptr [rcx+rdx], xmm0
0x18008133f  movups  xmmword ptr [rcx+rdx+10h], xmm1
0x180081344  movups  xmmword ptr [rcx+rdx+20h], xmm2
0x180081349  movsd   qword ptr [rcx+rdx+30h], xmm3
0x18008134f  mov     rax, [rdi+40h]
0x180081353  cmp     [r8], rax
0x180081356  jnz     short loc_18008135E
0x180081358  imul    rsi, r15, 38h ; '8'
0x18008135c  jmp     short loc_180081395
0x18008135e  mov     rdx, r8
0x180081361  lea     rcx, [rbp+0A0h+var_68]
0x180081365  call    ?CopyOutString@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@@Z; CopyOutString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x18008136a  mov     rdx, [rbp+0A0h+var_68]
0x18008136e  test    rdx, rdx
0x180081371  jz      loc_18008164C
0x180081377  mov     rax, [r12]
0x18008137b  imul    rsi, r15, 38h ; '8'
0x18008137f  mov     rcx, [rax+20h]
0x180081383  mov     [rbp+0A0h+var_68], r13
0x180081387  mov     [rcx+rsi+20h], rdx
0x18008138c  lea     rcx, [rbp+0A0h+var_68]
0x180081390  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180081395  mov     rdx, [rdi+78h]
0x180081399  cmp     [rdi+70h], rdx
0x18008139d  jz      short loc_18008141C
0x18008139f  sub     rdx, [rdi+70h]
0x1800813a3  lea     rcx, [rbp+0A0h+Destination]
0x1800813a7  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x1800813ac  mov     rbx, [rbp+0A0h+Destination]
0x1800813b0  mov     esi, r14d
0x1800813b3  test    rbx, rbx
0x1800813b6  setnz   al
0x1800813b9  and     esi, 1
0x1800813bc  test    al, al
0x1800813be  jz      short loc_1800813D6
0x1800813c0  mov     r8, [rdi+70h]; Source
0x1800813c4  mov     rcx, rbx; Destination
0x1800813c7  mov     rdx, [rdi+78h]
0x1800813cb  sub     rdx, r8; DestinationSize
0x1800813ce  mov     r9, rdx; SourceSize
0x1800813d1  call    memcpy_s
0x1800813d6  test    esi, esi
0x1800813d8  jz      short loc_1800813EB
0x1800813da  and     r14d, 0FFFFFFFEh
0x1800813de  lea     rcx, [rbp+0A0h+Destination]
0x1800813e2  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800813e7  mov     rbx, [rbp+0A0h+Destination]
0x1800813eb  test    rbx, rbx
0x1800813ee  jz      loc_180081600
0x1800813f4  mov     rax, [r12]
0x1800813f8  imul    rsi, r15, 38h ; '8'
0x1800813fc  mov     rcx, [rax+20h]
0x180081400  mov     [rbp+0A0h+Destination], r13
0x180081404  mov     [rcx+rsi+10h], rbx
0x180081409  lea     rcx, [rbp+0A0h+Destination]
0x18008140d  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180081412  mov     rbx, 0AAAAAAAAAAAAAAABh
0x18008141c  mov     rdx, [rdi+60h]
0x180081420  lea     rcx, [rbp+0A0h+var_80]
0x180081424  sub     rdx, [rdi+58h]
0x180081428  sar     rdx, 4
0x18008142c  imul    rdx, rbx
0x180081430  call    ??$make_unique@$$BY0A@UOVERLAY_IMAGE_CONFIGURATION@@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@UOVERLAY_IMAGE_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_IMAGE_CONFIGURATION@@@utl@@@0@_K@Z; utl::make_unique<OVERLAY_IMAGE_CONFIGURATION [0],0>(unsigned __int64)
0x180081435  mov     rdx, [rbp+0A0h+var_80]
0x180081439  test    rdx, rdx
0x18008143c  jz      loc_1800815B4
0x180081442  mov     rax, [r12]
0x180081446  mov     [rbp+0A0h+var_80], r13
0x18008144a  mov     rcx, [rax+20h]
0x18008144e  mov     [rcx+rsi+30h], rdx
0x180081453  mov     rax, [r12]
0x180081457  mov     rdx, [rdi+60h]
0x18008145b  sub     rdx, [rdi+58h]
0x18008145f  sar     rdx, 4
0x180081463  mov     rcx, [rax+20h]
0x180081467  imul    rdx, rbx
0x18008146b  mov     [rcx+rsi+28h], edx
0x18008146f  xor     ecx, ecx
0x180081471  mov     rax, [rdi+60h]
0x180081475  mov     rbx, [rdi+58h]
0x180081479  mov     [rsp+1A0h+var_160], rax
0x18008147e  cmp     rbx, rax
0x180081481  jz      loc_18008150B
0x180081487  lea     rdx, [rbx+10h]
0x18008148b  mov     r8d, 0FFFFFFFFh
0x180081491  mov     rax, [rdx+8]
0x180081495  sub     rax, [rdx]
0x180081498  sar     rax, 1
0x18008149b  cmp     rax, r8
0x18008149e  jnb     loc_18008157C
0x1800814a4  mov     rax, [r12]
0x1800814a8  add     rcx, rcx
0x1800814ab  movups  xmm0, xmmword ptr [rbx]
0x1800814ae  mov     rax, [rax+20h]
0x1800814b2  mov     rax, [rax+rsi+30h]
0x1800814b7  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x1800814bc  lea     rcx, [rbp+0A0h+var_70]
0x1800814c0  call    ?CopyOutString@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@@Z; CopyOutString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1800814c5  mov     rdx, [rbp+0A0h+var_70]
0x1800814c9  test    rdx, rdx
0x1800814cc  jz      short loc_18008152E
0x1800814ce  mov     rax, [r12]
0x1800814d2  mov     rcx, r13
0x1800814d5  add     rcx, rcx
0x1800814d8  mov     [rbp+0A0h+var_70], 0
0x1800814e0  mov     rax, [rax+20h]
0x1800814e4  mov     rax, [rax+rsi+30h]
0x1800814e9  mov     [rax+rcx*8+8], rdx
0x1800814ee  lea     rcx, [rbp+0A0h+var_70]
0x1800814f2  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800814f7  mov     rax, [rsp+1A0h+var_160]
0x1800814fc  inc     r13
0x1800814ff  mov     rcx, r13
0x180081502  add     rbx, 30h ; '0'
0x180081506  jmp     loc_18008147E
0x18008150b  lea     rcx, [rbp+0A0h+var_80]
0x18008150f  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180081514  mov     rax, [rsp+1A0h+var_158]
0x180081519  inc     r15
0x18008151c  add     rdi, 88h
0x180081523  mov     rcx, r15
0x180081526  xor     r13d, r13d
0x180081529  jmp     loc_1800812D7
0x18008152e  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081535  mov     [rsp+1A0h+var_140], 2D2h
0x18008153e  mov     [rsp+1A0h+var_150], rax
0x180081543  lea     rdx, [rsp+1A0h+var_150]
0x180081548  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x18008154f  mov     r8d, 0C0000017h
0x180081555  mov     [rsp+1A0h+var_148], rax
0x18008155a  lea     rcx, [rbp+0A0h+var_90]
0x18008155e  lea     rax, aOutstring; "OutString"
0x180081565  mov     [rsp+1A0h+var_138], rax
0x18008156a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008156f  lea     rcx, [rbp+0A0h+var_70]
0x180081573  mov     ebx, eax
0x180081575  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008157a  jmp     short loc_1800815F2
0x18008157c  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081583  mov     [rbp+0A0h+var_120], 2CDh
0x18008158b  mov     [rsp+1A0h+var_130], rax
0x180081590  lea     rdx, [rsp+1A0h+var_130]
0x180081595  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x18008159c  mov     r8d, 0C00000BBh
0x1800815a2  mov     [rsp+1A0h+var_128], rax
0x1800815a7  lea     rax, aImageAutonameL; "Image.AutoName.length() < 0xffffffffUL"
0x1800815ae  mov     [rbp+0A0h+var_118], rax
0x1800815b2  jmp     short loc_1800815E7
0x1800815b4  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800815bb  mov     [rbp+0A0h+var_100], 2C6h
0x1800815c3  mov     [rbp+0A0h+var_110], rax
0x1800815c7  lea     rdx, [rbp+0A0h+var_110]
0x1800815cb  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x1800815d2  mov     r8d, 0C0000017h
0x1800815d8  mov     [rbp+0A0h+var_108], rax
0x1800815dc  lea     rax, aOutimages; "OutImages"
0x1800815e3  mov     [rbp+0A0h+var_F8], rax
0x1800815e7  lea     rcx, [rbp+0A0h+var_90]
0x1800815eb  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800815f0  mov     ebx, eax
0x1800815f2  lea     rcx, [rbp+0A0h+var_80]
0x1800815f6  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800815fb  jmp     loc_180081751
0x180081600  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081607  mov     [rbp+0A0h+var_E0], 2C0h
0x18008160f  mov     [rbp+0A0h+var_F0], rax
0x180081613  lea     rdx, [rbp+0A0h+var_F0]
0x180081617  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x18008161e  mov     r8d, 0C0000017h
0x180081624  mov     [rbp+0A0h+var_E8], rax
0x180081628  lea     rcx, [rbp+0A0h+var_90]
0x18008162c  lea     rax, aOutbinary; "OutBinary"
0x180081633  mov     [rbp+0A0h+var_D8], rax
0x180081637  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008163c  lea     rcx, [rbp+0A0h+Destination]
0x180081640  mov     ebx, eax
0x180081642  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180081647  jmp     loc_180081751
0x18008164c  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081653  mov     [rbp+0A0h+var_C0], 2B8h
0x18008165b  mov     [rbp+0A0h+var_D0], rax
0x18008165f  lea     rdx, [rbp+0A0h+var_D0]
0x180081663  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x18008166a  mov     r8d, 0C0000017h
0x180081670  mov     [rbp+0A0h+var_C8], rax
0x180081674  lea     rcx, [rbp+0A0h+var_90]
0x180081678  lea     rax, aOutstring; "OutString"
0x18008167f  mov     [rbp+0A0h+var_B8], rax
0x180081683  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180081688  lea     rcx, [rbp+0A0h+var_68]
0x18008168c  mov     ebx, eax
0x18008168e  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180081693  jmp     loc_180081751
0x180081698  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x18008169f  mov     [rbp+0A0h+var_A0], 2B1h
0x1800816a7  mov     [rbp+0A0h+var_B0], rax
0x1800816ab  lea     rdx, [rbp+0A0h+var_B0]
0x1800816af  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x1800816b6  mov     [rbp+0A0h+var_A8], rax
0x1800816ba  lea     rax, aCimentryAutoim_0; "CimEntry.AutoImages.size() < 0xffffffff"...
0x1800816c1  mov     [rbp+0A0h+var_98], rax
0x1800816c5  jmp     short loc_1800816F9
0x1800816c7  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x1800816ce  mov     [rsp+1A0h+var_170], 2B0h
0x1800816d7  mov     [rsp+1A0h+var_180], rax
0x1800816dc  lea     rdx, [rsp+1A0h+var_180]
0x1800816e1  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x1800816e8  mov     [rsp+1A0h+var_178], rax
0x1800816ed  lea     rax, aCimentryAutore_2; "CimEntry.AutoRelativePath.length() < 0x"...
0x1800816f4  mov     [rsp+1A0h+var_168], rax
0x1800816f9  mov     r8d, 0C00000BBh
0x1800816ff  jmp     short loc_180081746
0x180081701  lea     rcx, [rbp+0A0h+var_78]
0x180081705  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008170a  xor     eax, eax
0x18008170c  jmp     short loc_18008175C
0x18008170e  lea     rax, aOnecoreBaseSer_3; "onecore\\base\\servicing\\overlayutil\\"...
0x180081715  mov     [rsp+1A0h+var_170], 2A9h
0x18008171e  mov     [rsp+1A0h+var_180], rax
0x180081723  lea     rdx, [rsp+1A0h+var_180]
0x180081728  lea     rax, aCopyoutconfig; "CopyOutConfig"
0x18008172f  mov     r8d, 0C0000017h
0x180081735  mov     [rsp+1A0h+var_178], rax
0x18008173a  lea     rax, aOutcims; "OutCims"
0x180081741  mov     [rsp+1A0h+var_168], rax
0x180081746  lea     rcx, [rbp+0A0h+var_90]
0x18008174a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008174f  mov     ebx, eax
0x180081751  lea     rcx, [rbp+0A0h+var_78]
0x180081755  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008175a  mov     eax, ebx
0x18008175c  mov     rcx, [rbp+0A0h+var_40]
0x180081760  xor     rcx, rsp; StackCookie
0x180081763  call    __security_check_cookie
0x180081768  mov     rbx, [rsp+1A0h+arg_10]
0x180081770  add     rsp, 170h
0x180081777  pop     r15
0x180081779  pop     r14
0x18008177b  pop     r13
0x18008177d  pop     r12
  ... truncated ...
```
