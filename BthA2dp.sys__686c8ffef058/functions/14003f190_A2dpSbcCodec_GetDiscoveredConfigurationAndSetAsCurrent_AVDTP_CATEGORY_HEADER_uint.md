# A2dpSbcCodec::GetDiscoveredConfigurationAndSetAsCurrent(_AVDTP_CATEGORY_HEADER * *,uint &)

- ea: `0x14003f190`
- end: `0x14003f7e2`
- name: `?GetDiscoveredConfigurationAndSetAsCurrent@A2dpSbcCodec@@UEAAJPEAPEAU_AVDTP_CATEGORY_HEADER@@AEAI@Z`
- size: `1618`
- prototype: `__int64 __fastcall(A2dpSbcCodec *__hidden this, struct _AVDTP_CATEGORY_HEADER **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x140003530`
- `0x140008810`
- `0x14000e690`
- `0x14000f570`
- `0x140010504`
- `0x1400396a4`
- `0x14003f190`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003f24d`
- `ntoskrnl!ExAllocatePool2` at `0x14003f24d`

## pseudocode

```c
__int64 __fastcall A2dpSbcCodec::GetDiscoveredConfigurationAndSetAsCurrent(
        A2dpSbcCodec *this,
        struct _AVDTP_CATEGORY_HEADER **a2,
        unsigned int *a3)
{
  unsigned int *v3; // r14
  struct _AVDTP_CATEGORY_HEADER **v4; // r15
  char v6; // di
  __int64 v7; // rbp
  __int64 Pool2; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  struct _AVDTP_CATEGORY_HEADER *v11; // rbx
  unsigned int v12; // ebx
  unsigned __int64 v13; // rax
  unsigned __int8 v14; // r9
  char v15; // dl
  unsigned __int8 v16; // r8
  char v17; // dl
  char v18; // r8
  char v19; // r8
  unsigned __int8 v20; // r9
  char v21; // r8
  unsigned __int8 v22; // r9
  char v23; // cl
  unsigned __int8 v24; // dl
  char v25; // r8
  char v26; // dl
  int v27; // edx
  __int64 v28; // r8
  unsigned __int8 v29; // r9
  unsigned __int64 v30; // rax
  unsigned __int8 v31; // cl
  unsigned __int8 v32; // al
  __int64 v34; // [rsp+90h] [rbp+8h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      16,
      15,
      (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
      (char)this);
  }
  v7 = *(_BYTE *)(*((_QWORD *)this + 7) + 4LL) != 0 ? 10 : 8;
  Pool2 = ExAllocatePool2(64, v7, 1128354882);
  v34 = Pool2;
  v11 = (struct _AVDTP_CATEGORY_HEADER *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v6;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        10,
        16,
        (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
        (char)this);
    }
    v12 = -1073741670;
    goto LABEL_111;
  }
  *(_QWORD *)Pool2 = *(_QWORD *)((char *)this + 34);
  if ( *(_BYTE *)(*((_QWORD *)this + 7) + 4LL) )
  {
    *(_BYTE *)(Pool2 + 8) = 8;
    *((_BYTE *)this + 64) = 1;
  }
  v13 = *(_QWORD *)((char *)this + 42);
  *((_BYTE *)v11 + 4) &= BYTE4(v13) | 0xF0;
  v14 = *((_BYTE *)v11 + 4);
  if ( (v14 & *((_BYTE *)this + 30) & 0xF) != 0 )
  {
    v15 = v14 ^ (v14 ^ *((_BYTE *)this + 30)) & 0xF;
  }
  else
  {
    v15 = *((_BYTE *)v11 + 4);
    if ( (v14 & 2) != 0 )
    {
      v15 = v14 & 0xF0 | 2;
    }
    else if ( (v14 & 1) != 0 )
    {
      v15 = v14 & 0xF0 | 1;
    }
    else if ( (v14 & 4) != 0 )
    {
      v15 = v14 & 0xF0 | 4;
    }
    else if ( (v14 & 8) != 0 )
    {
      v15 = v14 & 0xF0 | 8;
    }
  }
  v16 = v15 & (BYTE4(v13) | 0xF);
  *((_BYTE *)v11 + 4) = v16;
  v17 = v16 >> 4;
  if ( ((*((_BYTE *)this + 30) >> 4) & (v16 >> 4)) != 0 )
  {
    v18 = *((_BYTE *)this + 30) ^ (*((_BYTE *)this + 30) ^ v16) & 0xF;
  }
  else
  {
    v19 = v16 & 0xF;
    if ( (v17 & 1) != 0 )
      v18 = v19 | 0x10;
    else
      v18 = v19 | 0x20;
  }
  *((_BYTE *)v11 + 4) = v18;
  *((_BYTE *)v11 + 5) &= BYTE5(v13) | 0xFC;
  v20 = *((_BYTE *)v11 + 5);
  if ( (v20 & *((_BYTE *)this + 31) & 3) != 0 )
  {
    v21 = v20 ^ (v20 ^ *((_BYTE *)this + 31)) & 3;
  }
  else
  {
    v21 = *((_BYTE *)v11 + 5);
    if ( (v20 & 1) != 0 )
    {
      v21 = v20 & 0xFC | 1;
    }
    else if ( (v20 & 2) != 0 )
    {
      v21 = v20 & 0xFC | 2;
    }
  }
  v22 = v21 & (BYTE5(v13) | 0xF3);
  *((_BYTE *)v11 + 5) = v22;
  v23 = v22;
  if ( ((v22 >> 2) & (*((_BYTE *)this + 31) >> 2) & 3) != 0 )
  {
    v23 = v22 ^ (*((_BYTE *)this + 31) ^ v22) & 0xC;
  }
  else if ( (v22 & 4) != 0 )
  {
    v23 = v22 & 0xF3 | 4;
  }
  else if ( ((v22 >> 2) & 2) != 0 )
  {
    v23 = v22 & 0xF3 | 8;
  }
  v24 = v23 & (BYTE5(v13) | 0xF);
  *((_BYTE *)v11 + 5) = v24;
  v25 = v24 >> 4;
  if ( ((*((_BYTE *)this + 31) >> 4) & (v24 >> 4)) != 0 )
  {
    v26 = *((_BYTE *)this + 31) ^ (*((_BYTE *)this + 31) ^ v24) & 0xF;
LABEL_57:
    *((_BYTE *)v11 + 5) = v26;
    goto LABEL_58;
  }
  if ( (v24 & 0x10) != 0 )
  {
    v26 = v24 & 0xF | 0x10;
    goto LABEL_57;
  }
  if ( (v25 & 2) != 0 )
  {
    v26 = v24 & 0xF | 0x20;
    goto LABEL_57;
  }
  if ( (v25 & 4) != 0 )
  {
    v26 = v24 & 0xF | 0x40;
    goto LABEL_57;
  }
  if ( (v25 & 8) != 0 )
  {
    v26 = v24 & 0xF | 0x80;
    goto LABEL_57;
  }
LABEL_58:
  v27 = *((unsigned __int8 *)this + 32);
  v28 = *((unsigned __int8 *)this + 33);
  v29 = BYTE6(v13);
  if ( BYTE6(v13) >= (unsigned __int8)v27 )
    v27 = BYTE6(v13);
  v30 = HIBYTE(v13);
  if ( (unsigned __int8)v28 >= (unsigned __int8)v30 )
    v28 = (unsigned int)v30;
  if ( (unsigned __int8)v27 <= (unsigned __int8)v28 )
  {
    v31 = v27;
    LOBYTE(v27) = v28;
  }
  else
  {
    v31 = *((_BYTE *)v11 + 6);
    v27 = *((unsigned __int8 *)v11 + 7);
    if ( v29 >= v31 )
      v31 = v29;
    if ( (unsigned __int8)v27 >= (unsigned __int8)v30 )
      v27 = v30;
  }
  *((_BYTE *)v11 + 6) = v31;
  *((_BYTE *)v11 + 7) = v27;
  LOBYTE(v27) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v27,
      v28,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      17,
      (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids);
  }
  LOBYTE(v27) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (v27 = 16, (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0)
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      v27,
      v28,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      18,
      (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
      *((_BYTE *)v11 + 4) & 0xF,
      *((_BYTE *)v11 + 4) >> 4);
  }
  LOBYTE(v27) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_DDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v27,
      v28,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      19,
      (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
      *((_BYTE *)v11 + 5) & 3,
      (*((_BYTE *)v11 + 5) >> 2) & 3,
      *((_BYTE *)v11 + 5) >> 4);
  }
  LOBYTE(v27) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      v27,
      v28,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      20,
      (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
      *((_BYTE *)v11 + 6),
      *((_BYTE *)v11 + 7));
  v32 = (*(__int64 (__fastcall **)(A2dpSbcCodec *, struct _AVDTP_CATEGORY_HEADER *, __int64))(*(_QWORD *)this + 208LL))(
          this,
          v11,
          v28);
  v9 = v32;
  if ( v32 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v6;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        21,
        (__int64)WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids,
        v32);
    }
    v12 = -1073741823;
  }
  else
  {
    *v4 = v11;
    v12 = 0;
    *v3 = v7;
    v34 = 0;
  }
LABEL_111:
  wil::details::unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>(
    &v34,
    v9,
    v10);
  return v12;
}

```

## disassembly

```asm
0x14003f190  mov     [rsp+arg_8], rbx
0x14003f195  mov     [rsp+arg_10], rbp
0x14003f19a  push    rsi
0x14003f19b  push    rdi
0x14003f19c  push    r12
0x14003f19e  push    r14
0x14003f1a0  push    r15
0x14003f1a2  sub     rsp, 60h
0x14003f1a6  mov     r14, r8
0x14003f1a9  mov     r15, rdx
0x14003f1ac  mov     rsi, rcx
0x14003f1af  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f1b6  lea     rax, WPP_GLOBAL_Control
0x14003f1bd  mov     dil, 1
0x14003f1c0  cmp     rcx, rax
0x14003f1c3  jz      short loc_14003F1D9
0x14003f1c5  test    dword ptr [rcx+2Ch], 8000h
0x14003f1cc  jz      short loc_14003F1D9
0x14003f1ce  cmp     byte ptr [rcx+29h], 4
0x14003f1d2  jb      short loc_14003F1D9
0x14003f1d4  mov     dl, dil
0x14003f1d7  jmp     short loc_14003F1DB
0x14003f1d9  xor     dl, dl
0x14003f1db  lea     rax, WPP_RECORDER_INITIALIZED
0x14003f1e2  mov     r12d, 0Fh
0x14003f1e8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f1ef  lea     rax, WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids
0x14003f1f6  setnz   r8b
0x14003f1fa  test    dl, dl
0x14003f1fc  jnz     short loc_14003F203
0x14003f1fe  test    r8b, r8b
0x14003f201  jz      short loc_14003F22D
0x14003f203  mov     r9, [rcx+40h]
0x14003f207  mov     rcx, [rcx+18h]
0x14003f20b  mov     [rsp+88h+var_48], rsi
0x14003f210  mov     [rsp+88h+var_50], rax
0x14003f215  mov     [rsp+88h+var_58], r12w
0x14003f21b  mov     [rsp+88h+var_60], 10h
0x14003f223  mov     [rsp+88h+var_68], 4
0x14003f228  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003f22d  mov     rax, [rsi+38h]
0x14003f231  mov     r8d, 43415442h
0x14003f237  mov     cl, [rax+4]
0x14003f23a  neg     cl
0x14003f23c  mov     ecx, 40h ; '@'
0x14003f241  sbb     eax, eax
0x14003f243  and     eax, 2
0x14003f246  add     eax, 8
0x14003f249  mov     edx, eax
0x14003f24b  mov     ebp, eax
0x14003f24d  call    cs:__imp_ExAllocatePool2
0x14003f254  nop     dword ptr [rax+rax+00h]
0x14003f259  mov     [rsp+88h+arg_0], rax
0x14003f261  mov     rbx, rax
0x14003f264  test    rax, rax
0x14003f267  jnz     loc_14003F2ED
0x14003f26d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f274  lea     rax, WPP_GLOBAL_Control
0x14003f27b  cmp     rcx, rax
0x14003f27e  jz      short loc_14003F28F
0x14003f280  test    dword ptr [rcx+2Ch], 200h
0x14003f287  jz      short loc_14003F28F
0x14003f289  cmp     byte ptr [rcx+29h], 2
0x14003f28d  jnb     short loc_14003F292
0x14003f28f  xor     dil, dil
0x14003f292  lea     rax, WPP_RECORDER_INITIALIZED
0x14003f299  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f2a0  setnz   r8b
0x14003f2a4  test    dil, dil
0x14003f2a7  jnz     short loc_14003F2AE
0x14003f2a9  test    r8b, r8b
0x14003f2ac  jz      short loc_14003F2E3
0x14003f2ae  mov     [rsp+88h+var_48], rsi
0x14003f2b3  lea     r9, WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids
0x14003f2ba  mov     [rsp+88h+var_50], r9
0x14003f2bf  mov     dl, dil
0x14003f2c2  mov     r9, [rcx+40h]
0x14003f2c6  mov     rcx, [rcx+18h]
0x14003f2ca  mov     [rsp+88h+var_58], 10h
0x14003f2d1  mov     [rsp+88h+var_60], 0Ah
0x14003f2d9  mov     [rsp+88h+var_68], 2
0x14003f2de  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003f2e3  mov     ebx, 0C000009Ah
0x14003f2e8  jmp     loc_14003F7B9
0x14003f2ed  mov     rax, [rsi+22h]
0x14003f2f1  mov     [rbx], rax
0x14003f2f4  mov     rax, [rsi+38h]
0x14003f2f8  cmp     byte ptr [rax+4], 0
0x14003f2fc  jz      short loc_14003F306
0x14003f2fe  mov     byte ptr [rbx+8], 8
0x14003f302  mov     [rsi+40h], dil
0x14003f306  mov     rax, [rsi+2Ah]
0x14003f30a  mov     r8, rax
0x14003f30d  shr     r8, 20h
0x14003f311  mov     cl, r8b
0x14003f314  or      cl, 0F0h
0x14003f317  and     [rbx+4], cl
0x14003f31a  mov     dl, [rsi+1Eh]
0x14003f31d  mov     r9b, [rbx+4]
0x14003f321  mov     cl, dl
0x14003f323  and     cl, r9b
0x14003f326  test    r12b, cl
0x14003f329  jz      short loc_14003F336
0x14003f32b  xor     dl, r9b
0x14003f32e  and     dl, r12b
0x14003f331  xor     dl, r9b
0x14003f334  jmp     short loc_14003F36E
0x14003f336  mov     dl, r9b
0x14003f339  test    r9b, 2
0x14003f33d  jz      short loc_14003F347
0x14003f33f  and     dl, 0F2h
0x14003f342  or      dl, 2
0x14003f345  jmp     short loc_14003F36E
0x14003f347  test    dil, r9b
0x14003f34a  jz      short loc_14003F354
0x14003f34c  and     dl, 0F1h
0x14003f34f  or      dl, dil
0x14003f352  jmp     short loc_14003F36E
0x14003f354  test    r9b, 4
0x14003f358  jz      short loc_14003F362
0x14003f35a  and     dl, 0F4h
0x14003f35d  or      dl, 4
0x14003f360  jmp     short loc_14003F36E
0x14003f362  test    r9b, 8
0x14003f366  jz      short loc_14003F36E
0x14003f368  and     dl, 0F8h
0x14003f36b  or      dl, 8
0x14003f36e  or      r8b, r12b
0x14003f371  and     r8b, dl
0x14003f374  mov     [rbx+4], r8b
0x14003f378  mov     dl, r8b
0x14003f37b  mov     r9b, [rsi+1Eh]
0x14003f37f  mov     cl, r9b
0x14003f382  shr     dl, 4
0x14003f385  shr     cl, 4
0x14003f388  test    dl, cl
0x14003f38a  jz      short loc_14003F397
0x14003f38c  xor     r8b, r9b
0x14003f38f  and     r8b, r12b
0x14003f392  xor     r8b, r9b
0x14003f395  jmp     short loc_14003F3A9
0x14003f397  and     r8b, r12b
0x14003f39a  test    dil, dl
0x14003f39d  jz      short loc_14003F3A5
0x14003f39f  or      r8b, 10h
0x14003f3a3  jmp     short loc_14003F3A9
0x14003f3a5  or      r8b, 20h
0x14003f3a9  mov     [rbx+4], r8b
0x14003f3ad  mov     rdx, rax
0x14003f3b0  shr     rdx, 28h
0x14003f3b4  mov     cl, dl
0x14003f3b6  or      cl, 0FCh
0x14003f3b9  and     [rbx+5], cl
0x14003f3bc  mov     r8b, [rsi+1Fh]
0x14003f3c0  mov     r9b, [rbx+5]
0x14003f3c4  mov     cl, r8b
0x14003f3c7  and     cl, r9b
0x14003f3ca  test    cl, 3
0x14003f3cd  jz      short loc_14003F3DB
0x14003f3cf  xor     r8b, r9b
0x14003f3d2  and     r8b, 3
0x14003f3d6  xor     r8b, r9b
0x14003f3d9  jmp     short loc_14003F3FA
0x14003f3db  mov     r8b, r9b
0x14003f3de  test    dil, r9b
0x14003f3e1  jz      short loc_14003F3EC
0x14003f3e3  and     r8b, 0FDh
0x14003f3e7  or      r8b, dil
0x14003f3ea  jmp     short loc_14003F3FA
0x14003f3ec  test    r9b, 2
0x14003f3f0  jz      short loc_14003F3FA
0x14003f3f2  and     r8b, 0FEh
0x14003f3f6  or      r8b, 2
0x14003f3fa  mov     r9b, dl
0x14003f3fd  or      r9b, 0F3h
0x14003f401  and     r9b, r8b
0x14003f404  mov     [rbx+5], r9b
0x14003f408  mov     r8b, r9b
0x14003f40b  mov     r10b, [rsi+1Fh]
0x14003f40f  shr     r8b, 2
0x14003f413  mov     cl, r10b
0x14003f416  shr     cl, 2
0x14003f419  and     cl, r8b
0x14003f41c  test    cl, 3
0x14003f41f  mov     cl, r9b
0x14003f422  jz      short loc_14003F42F
0x14003f424  xor     cl, r10b
0x14003f427  and     cl, 0Ch
0x14003f42a  xor     cl, r9b
0x14003f42d  jmp     short loc_14003F448
0x14003f42f  test    dil, r8b
0x14003f432  jz      short loc_14003F43C
0x14003f434  and     cl, 0F7h
0x14003f437  or      cl, 4
0x14003f43a  jmp     short loc_14003F448
0x14003f43c  test    r8b, 2
0x14003f440  jz      short loc_14003F448
0x14003f442  and     cl, 0FBh
0x14003f445  or      cl, 8
0x14003f448  or      dl, r12b
0x14003f44b  and     dl, cl
0x14003f44d  mov     [rbx+5], dl
0x14003f450  mov     r8b, dl
0x14003f453  mov     r9b, [rsi+1Fh]
0x14003f457  mov     cl, r9b
0x14003f45a  shr     r8b, 4
0x14003f45e  shr     cl, 4
0x14003f461  test    r8b, cl
0x14003f464  jz      short loc_14003F471
0x14003f466  xor     dl, r9b
0x14003f469  and     dl, r12b
0x14003f46c  xor     dl, r9b
0x14003f46f  jmp     short loc_14003F4A6
0x14003f471  test    dil, r8b
0x14003f474  jz      short loc_14003F47E
0x14003f476  and     dl, r12b
0x14003f479  or      dl, 10h
0x14003f47c  jmp     short loc_14003F4A6
0x14003f47e  test    r8b, 2
0x14003f482  jz      short loc_14003F48C
0x14003f484  and     dl, r12b
0x14003f487  or      dl, 20h
0x14003f48a  jmp     short loc_14003F4A6
0x14003f48c  test    r8b, 4
0x14003f490  jz      short loc_14003F49A
0x14003f492  and     dl, r12b
0x14003f495  or      dl, 40h
0x14003f498  jmp     short loc_14003F4A6
0x14003f49a  test    r8b, 8
0x14003f49e  jz      short loc_14003F4A9
0x14003f4a0  and     dl, r12b
0x14003f4a3  or      dl, 80h
0x14003f4a6  mov     [rbx+5], dl
0x14003f4a9  movzx   edx, byte ptr [rsi+20h]
0x14003f4ad  mov     rcx, rax
0x14003f4b0  movzx   r8d, byte ptr [rsi+21h]
0x14003f4b5  shr     rcx, 30h
0x14003f4b9  movzx   r9d, cl
0x14003f4bd  cmp     r9b, dl
0x14003f4c0  cmovnb  edx, r9d
0x14003f4c4  shr     rax, 38h
0x14003f4c8  cmp     r8b, al
0x14003f4cb  cmovnb  r8d, eax
0x14003f4cf  cmp     dl, r8b
0x14003f4d2  jbe     short loc_14003F4EA
0x14003f4d4  movzx   ecx, byte ptr [rbx+6]
0x14003f4d8  movzx   edx, byte ptr [rbx+7]
0x14003f4dc  cmp     r9b, cl
0x14003f4df  cmovnb  ecx, r9d
0x14003f4e3  cmp     dl, al
0x14003f4e5  cmovnb  edx, eax
0x14003f4e8  jmp     short loc_14003F4EF
0x14003f4ea  mov     cl, dl
0x14003f4ec  mov     dl, r8b
0x14003f4ef  mov     [rbx+6], cl
0x14003f4f2  mov     [rbx+7], dl
0x14003f4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f4fc  lea     rax, WPP_GLOBAL_Control
0x14003f503  cmp     rcx, rax
0x14003f506  jz      short loc_14003F51A
0x14003f508  mov     eax, [rcx+2Ch]
0x14003f50b  test    al, 10h
0x14003f50d  jz      short loc_14003F51A
0x14003f50f  cmp     byte ptr [rcx+29h], 4
0x14003f513  jb      short loc_14003F51A
0x14003f515  mov     dl, dil
0x14003f518  jmp     short loc_14003F51C
0x14003f51a  xor     dl, dl
0x14003f51c  lea     r9, WPP_RECORDER_INITIALIZED
0x14003f523  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14003f52a  setnz   r8b
0x14003f52e  test    dl, dl
0x14003f530  jnz     short loc_14003F537
0x14003f532  test    r8b, r8b
0x14003f535  jz      short loc_14003F56B
0x14003f537  lea     r9, WPP_3d3725b6925c3aba701f93e71ec4d2db_Traceguids
0x14003f53e  mov     [rsp+88h+var_50], r9
0x14003f543  mov     r9, [rcx+40h]
0x14003f547  mov     rcx, [rcx+18h]
0x14003f54b  mov     [rsp+88h+var_58], 11h
0x14003f552  mov     [rsp+88h+var_60], 5
0x14003f55a  mov     [rsp+88h+var_68], 4
0x14003f55f  call    WPP_RECORDER_AND_TRACE_SF_
0x14003f564  lea     r9, WPP_RECORDER_INITIALIZED
0x14003f56b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f572  lea     rax, WPP_GLOBAL_Control
0x14003f579  cmp     rcx, rax
0x14003f57c  jz      short loc_14003F595
0x14003f57e  mov     eax, [rcx+2Ch]
0x14003f581  mov     edx, 10h
0x14003f586  test    dl, al
0x14003f588  jz      short loc_14003F595
0x14003f58a  cmp     byte ptr [rcx+29h], 4
0x14003f58e  jb      short loc_14003F595
0x14003f590  mov     dl, dil
0x14003f593  jmp     short loc_14003F597
0x14003f595  xor     dl, dl
0x14003f597  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14003f59e  setnz   r8b
0x14003f5a2  test    dl, dl
  ... truncated ...
```
