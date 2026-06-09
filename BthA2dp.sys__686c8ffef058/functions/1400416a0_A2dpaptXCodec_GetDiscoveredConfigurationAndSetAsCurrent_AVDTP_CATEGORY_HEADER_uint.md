# A2dpaptXCodec::GetDiscoveredConfigurationAndSetAsCurrent(_AVDTP_CATEGORY_HEADER * *,uint &)

- ea: `0x1400416a0`
- end: `0x140041988`
- name: `?GetDiscoveredConfigurationAndSetAsCurrent@A2dpaptXCodec@@UEAAJPEAPEAU_AVDTP_CATEGORY_HEADER@@AEAI@Z`
- size: `744`
- prototype: `__int64 __fastcall(A2dpaptXCodec *__hidden this, struct _AVDTP_CATEGORY_HEADER **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x140003530`
- `0x140008810`
- `0x14000f570`
- `0x1400396a4`
- `0x1400416a0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140041754`
- `ntoskrnl!ExAllocatePool2` at `0x140041754`

## pseudocode

```c
__int64 __fastcall A2dpaptXCodec::GetDiscoveredConfigurationAndSetAsCurrent(
        A2dpaptXCodec *this,
        struct _AVDTP_CATEGORY_HEADER **a2,
        unsigned int *a3)
{
  unsigned int *v3; // r14
  struct _AVDTP_CATEGORY_HEADER **v4; // r15
  char v6; // bl
  __int64 v7; // rbp
  __int64 Pool2; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdi
  unsigned int v12; // ebx
  unsigned __int8 v13; // dl
  char v14; // cl
  int v15; // edx
  __int64 v17; // [rsp+80h] [rbp+8h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
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
      5,
      13,
      (__int64)WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids,
      (char)this);
  }
  v7 = *(_BYTE *)(*((_QWORD *)this + 8) + 4LL) != 0 ? 13 : 11;
  Pool2 = ExAllocatePool2(64, v7, 1128354882);
  v17 = Pool2;
  v11 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = *(_QWORD *)((char *)this + 29);
    *(_DWORD *)(Pool2 + 7) = *((_DWORD *)this + 9);
    if ( *(_BYTE *)(*((_QWORD *)this + 8) + 4LL) )
    {
      *(_BYTE *)(Pool2 + 11) = 8;
      *((_BYTE *)this + 72) = 1;
    }
    *(_BYTE *)(Pool2 + 10) &= *((_BYTE *)this + 61) | 0xF0;
    v13 = *(_BYTE *)(Pool2 + 10);
    if ( (v13 & *((_BYTE *)this + 39) & 0xF) != 0 )
    {
      v14 = v13 ^ (v13 ^ *((_BYTE *)this + 39)) & 0xF;
    }
    else
    {
      v14 = *(_BYTE *)(Pool2 + 10);
      if ( (v13 & 2) != 0 )
        v14 = v13 & 0xF0 | 2;
    }
    *(_BYTE *)(Pool2 + 10) = v14 & 0xF | 0x20;
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        15,
        (__int64)WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids);
    }
    v15 = 16;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v6 = 0;
    }
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = v6;
      WPP_RECORDER_AND_TRACE_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        v15,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        16,
        (__int64)WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids,
        *(_BYTE *)(v11 + 10) & 0xF,
        *(_BYTE *)(v11 + 10) >> 4);
    }
    if ( (*(unsigned __int8 (__fastcall **)(A2dpaptXCodec *, __int64, __int64))(*(_QWORD *)this + 208LL))(
           this,
           v11,
           v10) )
    {
      v12 = -1073741823;
    }
    else
    {
      *v4 = (struct _AVDTP_CATEGORY_HEADER *)v11;
      v12 = 0;
      *v3 = v7;
      v17 = 0;
    }
  }
  else
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
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        14,
        (__int64)WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids,
        (char)this);
    }
    v12 = -1073741670;
  }
  wil::details::unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>(
    &v17,
    v9,
    v10);
  return v12;
}

```

## disassembly

```asm
0x1400416a0  mov     [rsp+arg_8], rbx
0x1400416a5  mov     [rsp+arg_10], rbp
0x1400416aa  push    rsi
0x1400416ab  push    rdi
0x1400416ac  push    r13
0x1400416ae  push    r14
0x1400416b0  push    r15
0x1400416b2  sub     rsp, 50h
0x1400416b6  mov     r14, r8
0x1400416b9  mov     r15, rdx
0x1400416bc  mov     rsi, rcx
0x1400416bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400416c6  lea     r13, WPP_GLOBAL_Control
0x1400416cd  mov     bl, 1
0x1400416cf  cmp     rcx, r13
0x1400416d2  jz      short loc_1400416E5
0x1400416d4  mov     eax, [rcx+2Ch]
0x1400416d7  test    al, 10h
0x1400416d9  jz      short loc_1400416E5
0x1400416db  cmp     byte ptr [rcx+29h], 4
0x1400416df  jb      short loc_1400416E5
0x1400416e1  mov     dl, bl
0x1400416e3  jmp     short loc_1400416E7
0x1400416e5  xor     dl, dl
0x1400416e7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400416ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400416f5  lea     r9, WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids
0x1400416fc  setnz   r8b
0x140041700  test    dl, dl
0x140041702  jnz     short loc_140041709
0x140041704  test    r8b, r8b
0x140041707  jz      short loc_140041734
0x140041709  mov     [rsp+78h+var_38], rsi
0x14004170e  mov     [rsp+78h+var_40], r9
0x140041713  mov     r9, [rcx+40h]
0x140041717  mov     rcx, [rcx+18h]
0x14004171b  mov     [rsp+78h+var_48], 0Dh
0x140041722  mov     [rsp+78h+var_50], 5
0x14004172a  mov     [rsp+78h+var_58], 4
0x14004172f  call    WPP_RECORDER_AND_TRACE_SF_q
0x140041734  mov     rax, [rsi+40h]
0x140041738  mov     r8d, 43415442h
0x14004173e  mov     cl, [rax+4]
0x140041741  neg     cl
0x140041743  mov     ecx, 40h ; '@'
0x140041748  sbb     eax, eax
0x14004174a  and     eax, 2
0x14004174d  add     eax, 0Bh
0x140041750  mov     edx, eax
0x140041752  mov     ebp, eax
0x140041754  call    cs:__imp_ExAllocatePool2
0x14004175b  nop     dword ptr [rax+rax+00h]
0x140041760  mov     [rsp+78h+arg_0], rax
0x140041768  mov     rdi, rax
0x14004176b  test    rax, rax
0x14004176e  jnz     short loc_1400417E4
0x140041770  mov     rcx, cs:WPP_GLOBAL_Control
0x140041777  cmp     rcx, r13
0x14004177a  jz      short loc_140041789
0x14004177c  mov     eax, [rcx+2Ch]
0x14004177f  test    al, 10h
0x140041781  jz      short loc_140041789
0x140041783  cmp     byte ptr [rcx+29h], 2
0x140041787  jnb     short loc_14004178B
0x140041789  xor     bl, bl
0x14004178b  lea     rax, WPP_RECORDER_INITIALIZED
0x140041792  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041799  setnz   r8b
0x14004179d  test    bl, bl
0x14004179f  jnz     short loc_1400417A6
0x1400417a1  test    r8b, r8b
0x1400417a4  jz      short loc_1400417DA
0x1400417a6  mov     [rsp+78h+var_38], rsi
0x1400417ab  lea     r9, WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids
0x1400417b2  mov     [rsp+78h+var_40], r9
0x1400417b7  mov     dl, bl
0x1400417b9  mov     r9, [rcx+40h]
0x1400417bd  mov     rcx, [rcx+18h]
0x1400417c1  mov     [rsp+78h+var_48], 0Eh
0x1400417c8  mov     [rsp+78h+var_50], 5
0x1400417d0  mov     [rsp+78h+var_58], 2
0x1400417d5  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400417da  mov     ebx, 0C000009Ah
0x1400417df  jmp     loc_14004195F
0x1400417e4  movsd   xmm0, qword ptr [rsi+1Dh]
0x1400417e9  movsd   qword ptr [rax], xmm0
0x1400417ed  mov     eax, [rsi+24h]
0x1400417f0  mov     [rdi+7], eax
0x1400417f3  mov     rax, [rsi+40h]
0x1400417f7  cmp     byte ptr [rax+4], 0
0x1400417fb  jz      short loc_140041804
0x1400417fd  mov     byte ptr [rdi+0Bh], 8
0x140041801  mov     [rsi+48h], bl
0x140041804  mov     al, [rsi+3Dh]
0x140041807  mov     r10d, 0Fh
0x14004180d  or      al, 0F0h
0x14004180f  and     [rdi+0Ah], al
0x140041812  mov     cl, [rsi+27h]
0x140041815  mov     dl, [rdi+0Ah]
0x140041818  mov     al, cl
0x14004181a  and     al, dl
0x14004181c  test    r10b, al
0x14004181f  jz      short loc_14004182A
0x140041821  xor     cl, dl
0x140041823  and     cl, r10b
0x140041826  xor     cl, dl
0x140041828  jmp     short loc_140041837
0x14004182a  mov     cl, dl
0x14004182c  test    dl, 2
0x14004182f  jz      short loc_140041837
0x140041831  and     cl, 0F2h
0x140041834  or      cl, 2
0x140041837  and     cl, r10b
0x14004183a  or      cl, 20h
0x14004183d  mov     [rdi+0Ah], cl
0x140041840  mov     rcx, cs:WPP_GLOBAL_Control
0x140041847  cmp     rcx, r13
0x14004184a  jz      short loc_14004185D
0x14004184c  mov     eax, [rcx+2Ch]
0x14004184f  test    al, 10h
0x140041851  jz      short loc_14004185D
0x140041853  cmp     byte ptr [rcx+29h], 4
0x140041857  jb      short loc_14004185D
0x140041859  mov     dl, bl
0x14004185b  jmp     short loc_14004185F
0x14004185d  xor     dl, dl
0x14004185f  lea     r9, WPP_RECORDER_INITIALIZED
0x140041866  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14004186d  setnz   r8b
0x140041871  test    dl, dl
0x140041873  jnz     short loc_14004187A
0x140041875  test    r8b, r8b
0x140041878  jz      short loc_1400418B3
0x14004187a  lea     r9, WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids
0x140041881  mov     [rsp+78h+var_40], r9
0x140041886  mov     r9, [rcx+40h]
0x14004188a  mov     rcx, [rcx+18h]
0x14004188e  mov     [rsp+78h+var_48], r10w
0x140041894  mov     [rsp+78h+var_50], 5
0x14004189c  mov     [rsp+78h+var_58], 4
0x1400418a1  call    WPP_RECORDER_AND_TRACE_SF_
0x1400418a6  lea     r9, WPP_RECORDER_INITIALIZED
0x1400418ad  mov     r10d, 0Fh
0x1400418b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400418ba  mov     edx, 10h
0x1400418bf  cmp     rcx, r13
0x1400418c2  jz      short loc_1400418D1
0x1400418c4  mov     eax, [rcx+2Ch]
0x1400418c7  test    dl, al
0x1400418c9  jz      short loc_1400418D1
0x1400418cb  cmp     byte ptr [rcx+29h], 4
0x1400418cf  jnb     short loc_1400418D3
0x1400418d1  xor     bl, bl
0x1400418d3  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1400418da  setnz   r8b
0x1400418de  test    bl, bl
0x1400418e0  jnz     short loc_1400418E7
0x1400418e2  test    r8b, r8b
0x1400418e5  jz      short loc_14004192B
0x1400418e7  movzx   r9d, byte ptr [rdi+0Ah]
0x1400418ec  mov     eax, r9d
0x1400418ef  and     r9d, r10d
0x1400418f2  shr     eax, 4
0x1400418f5  mov     [rsp+78h+var_30], eax
0x1400418f9  lea     rax, WPP_47dc67d3deae3f84c079e0b8a5af774a_Traceguids
0x140041900  mov     dword ptr [rsp+78h+var_38], r9d
0x140041905  mov     r9, [rcx+40h]
0x140041909  mov     rcx, [rcx+18h]
0x14004190d  mov     [rsp+78h+var_40], rax
0x140041912  mov     [rsp+78h+var_48], dx
0x140041917  mov     dl, bl
0x140041919  mov     [rsp+78h+var_50], 5
0x140041921  mov     [rsp+78h+var_58], 4
0x140041926  call    WPP_RECORDER_AND_TRACE_SF_DD
0x14004192b  mov     rax, [rsi]
0x14004192e  mov     rdx, rdi
0x140041931  mov     rcx, rsi
0x140041934  mov     rax, [rax+0D0h]
0x14004193b  call    _guard_dispatch_icall
0x140041940  test    al, al
0x140041942  jz      short loc_14004194B
0x140041944  mov     ebx, 0C0000001h
0x140041949  jmp     short loc_14004195F
0x14004194b  mov     [r15], rdi
0x14004194e  xor     ebx, ebx
0x140041950  mov     [r14], ebp
0x140041953  mov     [rsp+78h+arg_0], 0
0x14004195f  lea     rcx, [rsp+78h+arg_0]
0x140041967  call    ??1?$unique_storage@U?$resource_policy@PEAU_AVDTP_CATEGORY_HEADER@@P6AXPEAX@Z$1?ExFreePool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>(void)
0x14004196c  lea     r11, [rsp+78h+var_28]
0x140041971  mov     eax, ebx
0x140041973  mov     rbx, [r11+38h]
0x140041977  mov     rbp, [r11+40h]
0x14004197b  mov     rsp, r11
0x14004197e  pop     r15
0x140041980  pop     r14
0x140041982  pop     r13
0x140041984  pop     rdi
0x140041985  pop     rsi
0x140041986  retn
```
