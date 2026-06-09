# ScoChannelOpenBrbBuild(WDFREQUEST__ *,WDFDEVICE__ *,void *,_SCO_OPEN_CONTEXT const *,_BRB *)

- ea: `0x14000df64`
- end: `0x14000e16d`
- name: `?ScoChannelOpenBrbBuild@@YAJPEAUWDFREQUEST__@@PEAUWDFDEVICE__@@PEAXPEBU_SCO_OPEN_CONTEXT@@PEAU_BRB@@@Z`
- size: `521`
- prototype: `int(struct WDFREQUEST__ *, struct WDFDEVICE__ *, void *, const struct _SCO_OPEN_CONTEXT *, struct _BRB *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d76c`

## callees

- `0x140004810`
- `0x14000d238`
- `0x14000d3dc`
- `0x14000df64`
- `0x14000f500`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall ScoChannelOpenBrbBuild(
        struct WDFREQUEST__ *a1,
        struct WDFDEVICE__ *a2,
        void *a3,
        const struct _SCO_OPEN_CONTEXT *a4,
        struct _BRB *a5)
{
  __int64 v9; // rdi
  char v10; // si
  int RemotePacketTypes; // ebx
  __int64 v12; // rax
  int v13; // edx
  int v14; // r8d
  __int64 v15; // rcx
  const struct ScoConfigurationOptions **v16; // rax
  const struct ScoConfigurationOptions *v17; // r8
  unsigned __int16 v18; // dx
  int v20; // eax
  __int64 v21; // [rsp+50h] [rbp-21h] BYREF
  __int128 v22; // [rsp+58h] [rbp-19h] BYREF
  __int64 v23; // [rsp+68h] [rbp-9h]
  __int64 v24; // [rsp+70h] [rbp-1h]
  __int128 v25; // [rsp+78h] [rbp+7h]
  __int64 *v26; // [rsp+88h] [rbp+17h]

  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a2,
         off_140022150);
  v26 = off_140022178;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  v10 = 1;
  LODWORD(v22) = 56;
  v25 = 0;
  v24 = 0x100000001LL;
  RemotePacketTypes = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, __int128 *, __int64 *))(WdfFunctions_01015 + 1624))(
                        WdfDriverGlobals,
                        a1,
                        &v22,
                        &v21);
  if ( RemotePacketTypes >= 0 )
  {
    v12 = v21;
    *(_OWORD *)v21 = *(_OWORD *)a4;
    *(_OWORD *)(v12 + 16) = *((_OWORD *)a4 + 1);
    RemotePacketTypes = ScoGetRemotePacketTypes((struct _SCOCONTEXT *)v9);
    if ( RemotePacketTypes >= 0 )
    {
      v15 = v21;
      if ( *(int *)(v21 + 16) <= 0 )
      {
        return *(unsigned int *)a4;
      }
      else
      {
        while ( 1 )
        {
          v16 = *(const struct ScoConfigurationOptions ***)(v15 + 8);
          v17 = *v16;
          *(_QWORD *)(v15 + 8) = v16 + 1;
          --*(_DWORD *)(v21 + 16);
          v18 = *(_WORD *)v17 & 0x3C0
              | *(_WORD *)(v9 + 60) & (*(_WORD *)v17 | 0x3C0) & 0x3C0
              | *(_WORD *)(v9 + 68) & (*(_WORD *)(v9 + 60) & (*(_WORD *)v17 | 0x3C0) & 0x3F | 0x3C0);
          if ( v18 != 960 )
            break;
          v15 = v21;
          if ( *(int *)(v21 + 16) <= 0 )
            return *(unsigned int *)a4;
        }
        v20 = *(_DWORD *)(v9 + 28);
        if ( v20 == 514 || v20 == 528 )
        {
          ScoBuildOpenChannelBrb(a5, v18, a2, a3, v17, (struct _SCOCONTEXT *)v9);
        }
        else if ( v20 == 33281 )
        {
          ScoBuildOpenEnchancedChannelBrb(a5, v18, a2, a3, v17, (struct _SCOCONTEXT *)v9);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v10 = 0;
      }
      if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = v10;
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v14,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          45,
          (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
          RemotePacketTypes);
      }
    }
  }
  return (unsigned int)RemotePacketTypes;
}

```

## disassembly

```asm
0x14000df64  push    rbp
0x14000df66  push    rbx
0x14000df67  push    rsi
0x14000df68  push    rdi
0x14000df69  push    r12
0x14000df6b  push    r14
0x14000df6d  push    r15
0x14000df6f  lea     rbp, [rsp-1Fh]
0x14000df74  sub     rsp, 90h
0x14000df7b  mov     rax, cs:WdfFunctions_01015
0x14000df82  mov     r12, r8
0x14000df85  mov     r8, cs:off_140022150
0x14000df8c  mov     rbx, rcx
0x14000df8f  mov     rcx, cs:WdfDriverGlobals
0x14000df96  mov     r14, r9
0x14000df99  mov     r15, rdx
0x14000df9c  mov     rax, [rax+650h]
0x14000dfa3  call    _guard_dispatch_icall
0x14000dfa8  mov     rcx, cs:off_140022178
0x14000dfaf  lea     r9, [rbp+4Fh+var_70]
0x14000dfb3  mov     rdi, rax
0x14000dfb6  mov     [rbp+4Fh+var_38], rcx
0x14000dfba  mov     rcx, cs:WdfDriverGlobals
0x14000dfc1  lea     r8, [rbp+4Fh+var_68]
0x14000dfc5  xor     eax, eax
0x14000dfc7  xorps   xmm0, xmm0
0x14000dfca  movups  [rbp+4Fh+var_58], xmm0
0x14000dfce  mov     [rbp+4Fh+var_70], rax
0x14000dfd2  mov     rdx, rbx
0x14000dfd5  movups  [rbp+4Fh+var_68], xmm0
0x14000dfd9  lea     esi, [rax+1]
0x14000dfdc  mov     dword ptr [rbp+4Fh+var_68], 38h ; '8'
0x14000dfe3  mov     rax, cs:WdfFunctions_01015
0x14000dfea  movups  [rbp+4Fh+var_48], xmm0
0x14000dfee  mov     dword ptr [rbp+4Fh+var_58+8], esi
0x14000dff1  mov     dword ptr [rbp+4Fh+var_58+0Ch], esi
0x14000dff4  mov     rax, [rax+658h]
0x14000dffb  call    _guard_dispatch_icall
0x14000e000  mov     ebx, eax
0x14000e002  test    eax, eax
0x14000e004  js      loc_14000E10A
0x14000e00a  mov     rax, [rbp+4Fh+var_70]
0x14000e00e  mov     rcx, rdi; struct _SCOCONTEXT *
0x14000e011  movups  xmm0, xmmword ptr [r14]
0x14000e015  movups  xmmword ptr [rax], xmm0
0x14000e018  movups  xmm1, xmmword ptr [r14+10h]
0x14000e01d  movups  xmmword ptr [rax+10h], xmm1
0x14000e021  call    ?ScoGetRemotePacketTypes@@YAJPEAU_SCOCONTEXT@@@Z; ScoGetRemotePacketTypes(_SCOCONTEXT *)
0x14000e026  mov     ebx, eax
0x14000e028  test    eax, eax
0x14000e02a  jns     short loc_14000E0A5
0x14000e02c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e033  lea     rax, WPP_GLOBAL_Control
0x14000e03a  cmp     rcx, rax
0x14000e03d  jz      short loc_14000E04C
0x14000e03f  mov     eax, [rcx+2Ch]
0x14000e042  test    al, 10h
0x14000e044  jz      short loc_14000E04C
0x14000e046  cmp     byte ptr [rcx+29h], 2
0x14000e04a  jnb     short loc_14000E04F
0x14000e04c  xor     sil, sil
0x14000e04f  lea     rax, WPP_RECORDER_INITIALIZED
0x14000e056  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000e05d  setnz   r8b
0x14000e061  test    sil, sil
0x14000e064  jnz     short loc_14000E06F
0x14000e066  test    r8b, r8b
0x14000e069  jz      loc_14000E10A
0x14000e06f  mov     r9, [rcx+40h]
0x14000e073  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000e07a  mov     rcx, [rcx+18h]
0x14000e07e  mov     dl, sil
0x14000e081  mov     [rsp+0C0h+var_80], ebx
0x14000e085  mov     [rsp+0C0h+var_88], rax
0x14000e08a  mov     [rsp+0C0h+var_90], 2Dh ; '-'
0x14000e091  mov     dword ptr [rsp+0C0h+var_98], 5
0x14000e099  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14000e09e  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000e0a3  jmp     short loc_14000E10A
0x14000e0a5  mov     rcx, [rbp+4Fh+var_70]
0x14000e0a9  cmp     dword ptr [rcx+10h], 0
0x14000e0ad  jle     short loc_14000E107
0x14000e0af  mov     r9d, 3C0h
0x14000e0b5  mov     rax, [rcx+8]
0x14000e0b9  mov     r8, [rax]
0x14000e0bc  add     rax, 8
0x14000e0c0  mov     [rcx+8], rax
0x14000e0c4  mov     rax, [rbp+4Fh+var_70]
0x14000e0c8  dec     dword ptr [rax+10h]
0x14000e0cb  movzx   eax, word ptr [r8]
0x14000e0cf  movzx   ecx, ax
0x14000e0d2  and     ax, r9w
0x14000e0d6  or      cx, r9w
0x14000e0da  and     cx, [rdi+3Ch]
0x14000e0de  or      cx, ax
0x14000e0e1  movzx   edx, cx
0x14000e0e4  and     cx, r9w
0x14000e0e8  and     dx, 3Fh
0x14000e0ec  or      dx, r9w
0x14000e0f0  and     dx, [rdi+44h]
0x14000e0f4  or      dx, cx; unsigned __int16
0x14000e0f7  cmp     dx, r9w
0x14000e0fb  jnz     short loc_14000E11F
0x14000e0fd  mov     rcx, [rbp+4Fh+var_70]
0x14000e101  cmp     dword ptr [rcx+10h], 0
0x14000e105  jg      short loc_14000E0B5
0x14000e107  mov     ebx, [r14]
0x14000e10a  mov     eax, ebx
0x14000e10c  add     rsp, 90h
0x14000e113  pop     r15
0x14000e115  pop     r14
0x14000e117  pop     r12
0x14000e119  pop     rdi
0x14000e11a  pop     rsi
0x14000e11b  pop     rbx
0x14000e11c  pop     rbp
0x14000e11d  retn
0x14000e11f  mov     eax, [rdi+1Ch]
0x14000e122  cmp     eax, 202h
0x14000e127  jz      short loc_14000E152
0x14000e129  cmp     eax, 210h
0x14000e12e  jz      short loc_14000E152
0x14000e130  cmp     eax, 8201h
0x14000e135  jnz     short loc_14000E10A
0x14000e137  mov     rcx, [rbp+4Fh+arg_20]; struct _BRB *
0x14000e13b  mov     r9, r12; void *
0x14000e13e  mov     [rsp+0C0h+var_98], rdi; struct _SCOCONTEXT *
0x14000e143  mov     [rsp+0C0h+var_A0], r8; struct ScoConfigurationOptions *
0x14000e148  mov     r8, r15; struct WDFDEVICE__ *
0x14000e14b  call    ?ScoBuildOpenEnchancedChannelBrb@@YAXPEAU_BRB@@GPEAUWDFDEVICE__@@PEAXPEBUScoConfigurationOptions@@PEAU_SCOCONTEXT@@@Z; ScoBuildOpenEnchancedChannelBrb(_BRB *,ushort,WDFDEVICE__ *,void *,ScoConfigurationOptions const *,_SCOCONTEXT *)
0x14000e150  jmp     short loc_14000E10A
0x14000e152  mov     rcx, [rbp+4Fh+arg_20]; struct _BRB *
0x14000e156  mov     r9, r12; void *
0x14000e159  mov     [rsp+0C0h+var_98], rdi; struct _SCOCONTEXT *
0x14000e15e  mov     [rsp+0C0h+var_A0], r8; struct ScoConfigurationOptions *
0x14000e163  mov     r8, r15; struct WDFDEVICE__ *
0x14000e166  call    ?ScoBuildOpenChannelBrb@@YAXPEAU_BRB@@GPEAUWDFDEVICE__@@PEAXPEBUScoConfigurationOptions@@PEAU_SCOCONTEXT@@@Z; ScoBuildOpenChannelBrb(_BRB *,ushort,WDFDEVICE__ *,void *,ScoConfigurationOptions const *,_SCOCONTEXT *)
0x14000e16b  jmp     short loc_14000E10A
```
