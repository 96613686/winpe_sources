# A2dpSidebandAudioWdmEndpoint::SetSiop(SIDEBANDAUDIO_SIOP_REQUEST_PARAM * const)

- ea: `0x140081de0`
- end: `0x1400820c8`
- name: `?SetSiop@A2dpSidebandAudioWdmEndpoint@@MEAAJQEATSIDEBANDAUDIO_SIOP_REQUEST_PARAM@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, union SIDEBANDAUDIO_SIOP_REQUEST_PARAM *const)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x140003530`
- `0x14000e690`
- `0x1400202e8`
- `0x14005c7d0`
- `0x14005c870`
- `0x140081de0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140081f00`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140081f00`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140081f0f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140081f0f`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::SetSiop(
        A2dpSidebandAudioWdmEndpoint *this,
        union SIDEBANDAUDIO_SIOP_REQUEST_PARAM *const a2)
{
  union SIDEBANDAUDIO_SIOP_REQUEST_PARAM *v2; // r14
  char v4; // di
  LONGLONG *p_Alignment; // rsi
  LONGLONG v6; // rax
  LONGLONG v8; // rax
  char v9; // bl
  int v10; // edx
  int v11; // r8d
  PDEVICE_OBJECT v12; // rcx
  __int128 v13; // xmm0
  __int64 (__fastcall ***v14)(_QWORD, __int128 *, __int64, LONGLONG *); // rcx
  __int64 Size; // r8
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // ebx
  __int16 v20; // [rsp+30h] [rbp-78h]
  char *v21; // [rsp+50h] [rbp-58h] BYREF
  __int128 v22; // [rsp+58h] [rbp-50h] BYREF
  ULONG TypeId; // [rsp+68h] [rbp-40h]

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      46,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  p_Alignment = &v2->RequestedSiop.Alignment;
  v6 = v2->RequestedSiop.Alignment - SIDEBANDAUDIO_PARAMS_SET_A2DP;
  if ( !v6 )
    v6 = *(&v2->Alignment + 2) - *((_QWORD *)&SIDEBANDAUDIO_PARAMS_SET_A2DP + 1);
  if ( !v6 )
  {
    if ( v2->RequestedSiop.TypeId < 2 )
      return 0;
    return 3221225485LL;
  }
  v8 = *p_Alignment - *(_QWORD *)&SIDEBANDAUDIO_PARAMS_SET_STANDARD.Data1;
  if ( *p_Alignment == *(_QWORD *)&SIDEBANDAUDIO_PARAMS_SET_STANDARD.Data1 )
    v8 = *(&v2->Alignment + 2) - *(_QWORD *)SIDEBANDAUDIO_PARAMS_SET_STANDARD.Data4;
  if ( !v8 )
    return 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 680));
  v21 = (char *)this + 680;
  v9 = *((_BYTE *)this + 736);
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v21);
  if ( !v9 )
    return 3221225860LL;
  if ( (*(_DWORD *)p_Alignment & 0xFFFF0000) != 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225485LL;
    v20 = 47;
LABEL_34:
    LOBYTE(v10) = v4;
    WPP_RECORDER_AND_TRACE_SF_d(
      v12->AttachedDevice,
      v10,
      v11,
      v12->DeviceExtension,
      2,
      18,
      v20,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      13);
    return 3221225485LL;
  }
  if ( !(unsigned __int16)*(_DWORD *)p_Alignment )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225485LL;
    v20 = 48;
    goto LABEL_34;
  }
  v13 = *(_OWORD *)p_Alignment;
  v14 = (__int64 (__fastcall ***)(_QWORD, __int128 *, __int64, LONGLONG *))*((_QWORD *)this + 83);
  Size = v2->RequestedSiop.Size;
  TypeId = v2->RequestedSiop.TypeId;
  v22 = v13;
  v16 = (**v14)(v14, &v22, Size + 24, &v2->RequestedSiop.Alignment);
  v19 = v16;
  if ( v16 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v4 = 0;
  }
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v17) = v4;
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v17,
      v18,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      18,
      49,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      v16);
  }
  return v19;
}

```

## disassembly

```asm
0x140081de0  mov     [rsp+arg_10], rbx
0x140081de5  mov     [rsp+arg_18], rbp
0x140081dea  push    rsi
0x140081deb  push    rdi
0x140081dec  push    r12
0x140081dee  push    r14
0x140081df0  push    r15
0x140081df2  sub     rsp, 80h
0x140081df9  mov     rax, cs:__security_cookie
0x140081e00  xor     rax, rsp
0x140081e03  mov     [rsp+0A8h+var_38], rax
0x140081e08  mov     r14, rdx
0x140081e0b  mov     rbp, rcx
0x140081e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140081e15  lea     r15, WPP_GLOBAL_Control
0x140081e1c  mov     dil, 1
0x140081e1f  cmp     rcx, r15
0x140081e22  jz      short loc_140081E38
0x140081e24  test    dword ptr [rcx+2Ch], 40000h
0x140081e2b  jz      short loc_140081E38
0x140081e2d  cmp     byte ptr [rcx+29h], 4
0x140081e31  jb      short loc_140081E38
0x140081e33  mov     dl, dil
0x140081e36  jmp     short loc_140081E3A
0x140081e38  xor     dl, dl
0x140081e3a  lea     r12, WPP_RECORDER_INITIALIZED
0x140081e41  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140081e48  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140081e4f  setnz   r8b
0x140081e53  test    dl, dl
0x140081e55  jnz     short loc_140081E5C
0x140081e57  test    r8b, r8b
0x140081e5a  jz      short loc_140081E87
0x140081e5c  mov     [rsp+0A8h+var_68], rbp
0x140081e61  mov     [rsp+0A8h+var_70], r9
0x140081e66  mov     r9, [rcx+40h]
0x140081e6a  mov     rcx, [rcx+18h]
0x140081e6e  mov     [rsp+0A8h+var_78], 2Eh ; '.'
0x140081e75  mov     [rsp+0A8h+var_80], 13h
0x140081e7d  mov     [rsp+0A8h+var_88], 4
0x140081e82  call    WPP_RECORDER_AND_TRACE_SF_q
0x140081e87  lea     rsi, [r14+8]
0x140081e8b  mov     rax, [rsi]
0x140081e8e  sub     rax, qword ptr cs:SIDEBANDAUDIO_PARAMS_SET_A2DP
0x140081e95  jnz     short loc_140081EA2
0x140081e97  mov     rax, [rsi+8]
0x140081e9b  sub     rax, qword ptr cs:SIDEBANDAUDIO_PARAMS_SET_A2DP+8
0x140081ea2  test    rax, rax
0x140081ea5  jnz     short loc_140081EDD
0x140081ea7  cmp     dword ptr [rsi+10h], 2
0x140081eab  jnb     loc_140082007
0x140081eb1  xor     eax, eax
0x140081eb3  mov     rcx, [rsp+0A8h+var_38]
0x140081eb8  xor     rcx, rsp; StackCookie
0x140081ebb  call    __security_check_cookie
0x140081ec0  lea     r11, [rsp+0A8h+var_28]
0x140081ec8  mov     rbx, [r11+40h]
0x140081ecc  mov     rbp, [r11+48h]
0x140081ed0  mov     rsp, r11
0x140081ed3  pop     r15
0x140081ed5  pop     r14
0x140081ed7  pop     r12
0x140081ed9  pop     rdi
0x140081eda  pop     rsi
0x140081edb  retn
0x140081edd  mov     rax, [rsi]
0x140081ee0  sub     rax, qword ptr cs:SIDEBANDAUDIO_PARAMS_SET_STANDARD.Data1
0x140081ee7  jnz     short loc_140081EF4
0x140081ee9  mov     rax, [rsi+8]
0x140081eed  sub     rax, qword ptr cs:SIDEBANDAUDIO_PARAMS_SET_STANDARD.Data4
0x140081ef4  test    rax, rax
0x140081ef7  jz      short loc_140081EB1
0x140081ef9  lea     rbx, [rbp+2A8h]
0x140081f00  call    cs:__imp_KeEnterCriticalRegion
0x140081f07  nop     dword ptr [rax+rax+00h]
0x140081f0c  mov     rcx, rbx; FastMutex
0x140081f0f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140081f16  nop     dword ptr [rax+rax+00h]
0x140081f1b  mov     [rsp+0A8h+var_58], rbx
0x140081f20  lea     rcx, [rsp+0A8h+var_58]
0x140081f25  mov     bl, [rbp+2E0h]
0x140081f2b  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140081f30  test    bl, bl
0x140081f32  jz      loc_1400820BE
0x140081f38  mov     eax, [rsi]
0x140081f3a  test    eax, 0FFFF0000h
0x140081f3f  jz      short loc_140081F95
0x140081f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140081f48  cmp     rcx, r15
0x140081f4b  jz      short loc_140081F5C
0x140081f4d  test    dword ptr [rcx+2Ch], 20000h
0x140081f54  jz      short loc_140081F5C
0x140081f56  cmp     byte ptr [rcx+29h], 2
0x140081f5a  jnb     short loc_140081F5F
0x140081f5c  xor     dil, dil
0x140081f5f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140081f66  setnz   r8b
0x140081f6a  test    dil, dil
0x140081f6d  jnz     short loc_140081F78
0x140081f6f  test    r8b, r8b
0x140081f72  jz      loc_140082007
0x140081f78  mov     dword ptr [rsp+0A8h+var_68], 0C000000Dh
0x140081f80  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140081f87  mov     [rsp+0A8h+var_70], r9
0x140081f8c  mov     [rsp+0A8h+var_78], 2Fh ; '/'
0x140081f93  jmp     short loc_140081FEA
0x140081f95  movzx   eax, ax
0x140081f98  test    eax, eax
0x140081f9a  jnz     short loc_140082011
0x140081f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140081fa3  cmp     rcx, r15
0x140081fa6  jz      short loc_140081FB7
0x140081fa8  test    dword ptr [rcx+2Ch], 20000h
0x140081faf  jz      short loc_140081FB7
0x140081fb1  cmp     byte ptr [rcx+29h], 2
0x140081fb5  jnb     short loc_140081FBA
0x140081fb7  xor     dil, dil
0x140081fba  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140081fc1  setnz   r8b
0x140081fc5  test    dil, dil
0x140081fc8  jnz     short loc_140081FCF
0x140081fca  test    r8b, r8b
0x140081fcd  jz      short loc_140082007
0x140081fcf  mov     dword ptr [rsp+0A8h+var_68], 0C000000Dh
0x140081fd7  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140081fde  mov     [rsp+0A8h+var_70], r9
0x140081fe3  mov     [rsp+0A8h+var_78], 30h ; '0'
0x140081fea  mov     r9, [rcx+40h]
0x140081fee  mov     dl, dil
0x140081ff1  mov     rcx, [rcx+18h]
0x140081ff5  mov     [rsp+0A8h+var_80], 12h
0x140081ffd  mov     [rsp+0A8h+var_88], 2
0x140082002  call    WPP_RECORDER_AND_TRACE_SF_d
0x140082007  mov     eax, 0C000000Dh
0x14008200c  jmp     loc_140081EB3
0x140082011  mov     eax, [r14+18h]
0x140082015  lea     rdx, [rsp+0A8h+var_50]
0x14008201a  movups  xmm0, xmmword ptr [rsi]
0x14008201d  mov     rcx, [rbp+298h]
0x140082024  mov     r9, rsi
0x140082027  mov     r8d, [r14+1Ch]
0x14008202b  mov     [rsp+0A8h+var_40], eax
0x14008202f  add     r8, 18h
0x140082033  movdqu  [rsp+0A8h+var_50], xmm0
0x140082039  mov     rax, [rcx]
0x14008203c  mov     rax, [rax]
0x14008203f  call    _guard_dispatch_icall
0x140082044  mov     ebx, eax
0x140082046  test    eax, eax
0x140082048  jns     loc_140081EB1
0x14008204e  mov     r10, cs:WPP_GLOBAL_Control
0x140082055  cmp     r10, r15
0x140082058  jz      short loc_14008206B
0x14008205a  test    dword ptr [r10+2Ch], 20000h
0x140082062  jz      short loc_14008206B
0x140082064  cmp     byte ptr [r10+29h], 2
0x140082069  jnb     short loc_14008206E
0x14008206b  xor     dil, dil
0x14008206e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140082075  setnz   r8b
0x140082079  test    dil, dil
0x14008207c  jnz     short loc_140082083
0x14008207e  test    r8b, r8b
0x140082081  jz      short loc_1400820B7
0x140082083  mov     rcx, [r10+18h]
0x140082087  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008208e  mov     dword ptr [rsp+0A8h+var_68], ebx
0x140082092  mov     dl, dil
0x140082095  mov     [rsp+0A8h+var_70], r9
0x14008209a  mov     r9, [r10+40h]
0x14008209e  mov     [rsp+0A8h+var_78], 31h ; '1'
0x1400820a5  mov     [rsp+0A8h+var_80], 12h
0x1400820ad  mov     [rsp+0A8h+var_88], 2
0x1400820b2  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400820b7  mov     eax, ebx
0x1400820b9  jmp     loc_140081EB3
0x1400820be  mov     eax, 0C0000184h
0x1400820c3  jmp     loc_140081EB3
```
