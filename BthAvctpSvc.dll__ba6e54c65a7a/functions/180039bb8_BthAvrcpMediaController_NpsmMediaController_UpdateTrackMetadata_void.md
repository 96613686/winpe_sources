# BthAvrcpMediaController::NpsmMediaController::UpdateTrackMetadata(void)

- ea: `0x180039bb8`
- end: `0x180039f3d`
- name: `?UpdateTrackMetadata@NpsmMediaController@BthAvrcpMediaController@@AEAA?AUMediaStateChanges@12@XZ`
- size: `901`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800360d4`
- `0x1800390a8`

## callees

- `0x180001dd0`
- `0x18000d0c0`
- `0x180019d20`
- `0x1800235bc`
- `0x180023d80`
- `0x180023da8`
- `0x1800358d0`
- `0x180035b80`
- `0x180035f58`
- `0x180038418`
- `0x180039bb8`
- `0x18003a24c`
- `0x18003abb0`
- `0x18003ac2c`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039c3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039c3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ec2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ec2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BthAvrcpMediaController::NpsmMediaController::UpdateTrackMetadata(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rdi
  int v6; // edi
  PVOID *v7; // rcx
  int v8; // eax
  PVOID *v9; // rcx
  const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *v10; // rsi
  const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *i; // rdi
  __int64 v13; // [rsp+20h] [rbp-79h] BYREF
  __int64 v14; // [rsp+28h] [rbp-71h] BYREF
  int v15; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v16[40]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v17[96]; // [rsp+60h] [rbp-39h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, a1);
  }
  *(_DWORD *)a2 = 0;
  *(_WORD *)(a2 + 4) = 0;
  *(_BYTE *)(a2 + 6) = 0;
  v13 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v14 = a1 + 96;
  v4 = *(_QWORD *)(a1 + 328);
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v6 = v5(v4, &v13);
  if ( a1 != -96 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  if ( v6 >= 0 )
  {
    v14 = a1;
    lambda_260b9c963b52c56b05970c7f13608a5f_::operator()(&v14, v17);
    v8 = BthAvrcpMediaController::NpsmMediaController::SetCurrentTrackAttributes(a1, &v13);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          &WPP_95e767cb7999366f67a133efb5540c97_Traceguids,
          (unsigned int)v8);
      }
LABEL_46:
      BthAvrcpMediaController::BthAvMediaTrack::~BthAvMediaTrack((BthAvrcpMediaController::BthAvMediaTrack *)v17);
      goto LABEL_47;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
    v14 = a1 + 96;
    *(_BYTE *)(a1 + 216) = 0;
    if ( BthAvrcpMediaController::BthAvMediaTrack::IsEquivalentTo(
           (BthAvrcpMediaController::BthAvMediaTrack *)(a1 + 136),
           (const struct BthAvrcpMediaController::BthAvMediaTrack *)v17) )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_32;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids);
      goto LABEL_31;
    }
    if ( *(_DWORD *)(a1 + 272) )
      goto LABEL_55;
    if ( BthAvrcpMediaController::BthAvMediaTrack::IsEmpty((BthAvrcpMediaController::BthAvMediaTrack *)(a1 + 136)) )
    {
LABEL_22:
      *(_BYTE *)(a1 + 216) = 1;
      goto LABEL_31;
    }
    if ( *(_DWORD *)(a1 + 272) )
    {
LABEL_55:
      if ( !BthAvrcpMediaController::BthAvMediaTrack::IsEmpty((BthAvrcpMediaController::BthAvMediaTrack *)(a1 + 136)) )
        goto LABEL_22;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      goto LABEL_32;
    }
    BthAvrcpMediaController::BthAvMediaTrack::IsEmpty((BthAvrcpMediaController::BthAvMediaTrack *)(a1 + 136));
    WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 107);
LABEL_31:
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_32:
    if ( *(_BYTE *)(a1 + 216) )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 5u )
        WPP_SF_(v9[2], 109, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids);
      v10 = *(const struct BthAvrcpMediaController::BthAvMediaTrackAttribute **)(a1 + 200);
      for ( i = *(const struct BthAvrcpMediaController::BthAvMediaTrackAttribute **)(a1 + 192);
            i != v10;
            i = (const struct BthAvrcpMediaController::BthAvMediaTrackAttribute *)((char *)i + 40) )
      {
        BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(
          (BthAvrcpMediaController::BthAvMediaTrackAttribute *)&v15,
          i);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 110);
        }
        std::wstring::_Tidy_deallocate(v16);
      }
      *(_BYTE *)(a2 + 4) = 1;
      *(_BYTE *)(a1 + 216) = 0;
    }
    if ( a1 != -96 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
    goto LABEL_46;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_52;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      105,
      &WPP_95e767cb7999366f67a133efb5540c97_Traceguids,
      (unsigned int)v6);
LABEL_47:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_q(v7[2], 111, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, a1);
LABEL_52:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return a2;
}

```

## disassembly

```asm
0x180039bb8  mov     [rsp-8+arg_10], rbx
0x180039bbd  mov     [rsp-8+arg_18], rsi
0x180039bc2  push    rbp
0x180039bc3  push    rdi
0x180039bc4  push    r12
0x180039bc6  push    r14
0x180039bc8  push    r15
0x180039bca  lea     rbp, [rsp-37h]
0x180039bcf  sub     rsp, 0D0h
0x180039bd6  mov     rax, cs:__security_cookie
0x180039bdd  xor     rax, rsp
0x180039be0  mov     [rbp+57h+var_30], rax
0x180039be4  mov     r15, rdx
0x180039be7  mov     r14, rcx
0x180039bea  lea     rax, WPP_GLOBAL_Control
0x180039bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180039bf8  cmp     rcx, rax
0x180039bfb  jz      short loc_180039C21
0x180039bfd  test    byte ptr [rcx+1Ch], 1
0x180039c01  jz      short loc_180039C21
0x180039c03  cmp     byte ptr [rcx+19h], 4
0x180039c07  jb      short loc_180039C21
0x180039c09  mov     edx, 68h ; 'h'
0x180039c0e  mov     r9, r14
0x180039c11  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039c18  mov     rcx, [rcx+10h]
0x180039c1c  call    WPP_SF_q
0x180039c21  xor     eax, eax
0x180039c23  mov     [r15], eax
0x180039c26  mov     [r15+4], ax
0x180039c2b  xor     r12d, r12d
0x180039c2e  mov     [r15+6], al
0x180039c32  mov     [rbp+57h+var_D0], r12
0x180039c36  lea     rbx, [r14+60h]
0x180039c3a  mov     rcx, rbx; lpCriticalSection
0x180039c3d  call    cs:__imp_EnterCriticalSection
0x180039c43  mov     [rbp+57h+var_C8], rbx
0x180039c47  mov     rsi, [r14+148h]
0x180039c4e  mov     rax, [rsi]
0x180039c51  mov     rdi, [rax+28h]
0x180039c55  lea     rcx, [rbp+57h+var_D0]
0x180039c59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039c5e  lea     rdx, [rbp+57h+var_D0]
0x180039c62  mov     rcx, rsi
0x180039c65  mov     rax, rdi
0x180039c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c6d  mov     edi, eax
0x180039c6f  test    rbx, rbx
0x180039c72  jz      short loc_180039C7D
0x180039c74  mov     rcx, rbx; lpCriticalSection
0x180039c77  call    cs:__imp_LeaveCriticalSection
0x180039c7d  test    edi, edi
0x180039c7f  jns     short loc_180039CC9
0x180039c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c88  lea     rbx, WPP_GLOBAL_Control
0x180039c8f  cmp     rcx, rbx
0x180039c92  jz      loc_180039F09
0x180039c98  test    byte ptr [rcx+1Ch], 1
0x180039c9c  jz      loc_180039EDF
0x180039ca2  cmp     byte ptr [rcx+19h], 2
0x180039ca6  jb      loc_180039EDF
0x180039cac  mov     edx, 69h ; 'i'
0x180039cb1  mov     r9d, edi
0x180039cb4  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039cbb  mov     rcx, [rcx+10h]
0x180039cbf  call    WPP_SF_d
0x180039cc4  jmp     loc_180039ED8
0x180039cc9  mov     [rbp+57h+var_C8], r14
0x180039ccd  lea     rdx, [rbp+57h+var_90]
0x180039cd1  lea     rcx, [rbp+57h+var_C8]
0x180039cd5  call    _lambda_260b9c963b52c56b05970c7f13608a5f___operator__
0x180039cda  nop
0x180039cdb  lea     rdx, [rbp+57h+var_D0]
0x180039cdf  mov     rcx, r14
0x180039ce2  call    ?SetCurrentTrackAttributes@NpsmMediaController@BthAvrcpMediaController@@AEAAJAEBV?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@Z; BthAvrcpMediaController::NpsmMediaController::SetCurrentTrackAttributes(Microsoft::WRL::ComPtr<IPropertyStore> const &)
0x180039ce7  test    eax, eax
0x180039ce9  jns     short loc_180039D33
0x180039ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180039cf2  lea     rbx, WPP_GLOBAL_Control
0x180039cf9  cmp     rcx, rbx
0x180039cfc  jz      loc_180039ECF
0x180039d02  test    byte ptr [rcx+1Ch], 1
0x180039d06  jz      loc_180039ECF
0x180039d0c  cmp     byte ptr [rcx+19h], 2
0x180039d10  jb      loc_180039ECF
0x180039d16  mov     edx, 6Ah ; 'j'
0x180039d1b  mov     r9d, eax
0x180039d1e  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039d25  mov     rcx, [rcx+10h]
0x180039d29  call    WPP_SF_d
0x180039d2e  jmp     loc_180039ECF
0x180039d33  mov     rcx, rbx; lpCriticalSection
0x180039d36  call    cs:__imp_EnterCriticalSection
0x180039d3c  mov     [rbp+57h+var_C8], rbx
0x180039d40  lea     rdi, [r14+88h]
0x180039d47  mov     [rdi+50h], r12b
0x180039d4b  lea     rdx, [rbp+57h+var_90]; struct BthAvrcpMediaController::BthAvMediaTrack *
0x180039d4f  mov     rcx, rdi; this
0x180039d52  call    ?IsEquivalentTo@BthAvMediaTrack@BthAvrcpMediaController@@QEAA_NAEBU12@@Z; BthAvrcpMediaController::BthAvMediaTrack::IsEquivalentTo(BthAvrcpMediaController::BthAvMediaTrack const &)
0x180039d57  mov     sil, 5
0x180039d5a  test    al, al
0x180039d5c  jnz     short loc_180039DD4
0x180039d5e  cmp     [r14+110h], r12d
0x180039d65  jnz     short loc_180039D7C
0x180039d67  mov     rcx, rdi; this
0x180039d6a  call    ?IsEmpty@BthAvMediaTrack@BthAvrcpMediaController@@QEAA_NXZ; BthAvrcpMediaController::BthAvMediaTrack::IsEmpty(void)
0x180039d6f  test    al, al
0x180039d71  jnz     short loc_180039D88
0x180039d73  cmp     [r14+110h], r12d
0x180039d7a  jz      short loc_180039D92
0x180039d7c  mov     rcx, rdi; this
0x180039d7f  call    ?IsEmpty@BthAvMediaTrack@BthAvrcpMediaController@@QEAA_NXZ; BthAvrcpMediaController::BthAvMediaTrack::IsEmpty(void)
0x180039d84  test    al, al
0x180039d86  jnz     short loc_180039D92
0x180039d88  mov     byte ptr [r14+0D8h], 1
0x180039d90  jmp     short loc_180039E08
0x180039d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180039d99  lea     rax, WPP_GLOBAL_Control
0x180039da0  cmp     rcx, rax
0x180039da3  jz      short loc_180039E16
0x180039da5  test    byte ptr [rcx+1Ch], 1
0x180039da9  jz      short loc_180039E16
0x180039dab  cmp     [rcx+19h], sil
0x180039daf  jb      short loc_180039E16
0x180039db1  mov     rcx, rdi; this
0x180039db4  call    ?IsEmpty@BthAvMediaTrack@BthAvrcpMediaController@@QEAA_NXZ; BthAvrcpMediaController::BthAvMediaTrack::IsEmpty(void)
0x180039db9  movzx   r9d, al
0x180039dbd  mov     edx, 6Bh ; 'k'
0x180039dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dc9  mov     rcx, [rcx+10h]
0x180039dcd  call    WPP_SF_l
0x180039dd2  jmp     short loc_180039E08
0x180039dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ddb  lea     rax, WPP_GLOBAL_Control
0x180039de2  cmp     rcx, rax
0x180039de5  jz      short loc_180039E16
0x180039de7  test    byte ptr [rcx+1Ch], 1
0x180039deb  jz      short loc_180039E16
0x180039ded  cmp     [rcx+19h], sil
0x180039df1  jb      short loc_180039E16
0x180039df3  mov     edx, 6Ch ; 'l'
0x180039df8  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039dff  mov     rcx, [rcx+10h]
0x180039e03  call    WPP_SF_
0x180039e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e0f  lea     rax, WPP_GLOBAL_Control
0x180039e16  cmp     [r14+0D8h], r12b
0x180039e1d  jz      loc_180039EBA
0x180039e23  cmp     rcx, rax
0x180039e26  jz      short loc_180039E49
0x180039e28  test    byte ptr [rcx+1Ch], 1
0x180039e2c  jz      short loc_180039E49
0x180039e2e  cmp     [rcx+19h], sil
0x180039e32  jb      short loc_180039E49
0x180039e34  mov     edx, 6Dh ; 'm'
0x180039e39  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039e40  mov     rcx, [rcx+10h]
0x180039e44  call    WPP_SF_
0x180039e49  mov     rsi, [r14+0C8h]
0x180039e50  mov     rdi, [r14+0C0h]
0x180039e57  cmp     rdi, rsi
0x180039e5a  jz      short loc_180039EAE
0x180039e5c  lea     r12, WPP_GLOBAL_Control
0x180039e63  mov     rdx, rdi; struct BthAvrcpMediaController::BthAvMediaTrackAttribute *
0x180039e66  lea     rcx, [rbp+57h+var_C0]; this
0x180039e6a  call    ??0BthAvMediaTrackAttribute@BthAvrcpMediaController@@QEAA@AEBU01@@Z; BthAvrcpMediaController::BthAvMediaTrackAttribute::BthAvMediaTrackAttribute(BthAvrcpMediaController::BthAvMediaTrackAttribute const &)
0x180039e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e76  cmp     rcx, r12
0x180039e79  jz      short loc_180039E99
0x180039e7b  test    byte ptr [rcx+1Ch], 1
0x180039e7f  jz      short loc_180039E99
0x180039e81  cmp     byte ptr [rcx+19h], 5
0x180039e85  jb      short loc_180039E99
0x180039e87  mov     edx, 6Eh ; 'n'
0x180039e8c  mov     r9d, [rbp+57h+var_C0]
0x180039e90  mov     rcx, [rcx+10h]
0x180039e94  call    WPP_SF_l
0x180039e99  lea     rcx, [rbp+57h+var_B8]
0x180039e9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039ea2  add     rdi, 28h ; '('
0x180039ea6  cmp     rdi, rsi
0x180039ea9  jnz     short loc_180039E63
0x180039eab  xor     r12d, r12d
0x180039eae  mov     byte ptr [r15+4], 1
0x180039eb3  mov     [r14+0D8h], r12b
0x180039eba  test    rbx, rbx
0x180039ebd  jz      short loc_180039EC8
0x180039ebf  mov     rcx, rbx; lpCriticalSection
0x180039ec2  call    cs:__imp_LeaveCriticalSection
0x180039ec8  lea     rbx, WPP_GLOBAL_Control
0x180039ecf  lea     rcx, [rbp+57h+var_90]; this
0x180039ed3  call    ??1BthAvMediaTrack@BthAvrcpMediaController@@QEAA@XZ; BthAvrcpMediaController::BthAvMediaTrack::~BthAvMediaTrack(void)
0x180039ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180039edf  cmp     rcx, rbx
0x180039ee2  jz      short loc_180039F09
0x180039ee4  test    byte ptr [rcx+1Ch], 1
0x180039ee8  jz      short loc_180039F09
0x180039eea  cmp     byte ptr [rcx+19h], 4
0x180039eee  jb      short loc_180039F09
0x180039ef0  mov     edx, 6Fh ; 'o'
0x180039ef5  mov     r9, r14
0x180039ef8  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039eff  mov     rcx, [rcx+10h]
0x180039f03  call    WPP_SF_q
0x180039f08  nop
0x180039f09  lea     rcx, [rbp+57h+var_D0]
0x180039f0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039f12  mov     rax, r15
0x180039f15  mov     rcx, [rbp+57h+var_30]
0x180039f19  xor     rcx, rsp; StackCookie
0x180039f1c  call    __security_check_cookie
0x180039f21  lea     r11, [rsp+0F0h+var_20]
0x180039f29  mov     rbx, [r11+40h]
0x180039f2d  mov     rsi, [r11+48h]
0x180039f31  mov     rsp, r11
0x180039f34  pop     r15
0x180039f36  pop     r14
0x180039f38  pop     r12
0x180039f3a  pop     rdi
0x180039f3b  pop     rbp
0x180039f3c  retn
```
