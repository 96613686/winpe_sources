# Smb2UpdateSessionWithClaims

- ea: `0x140069d7c`
- end: `0x14006a0c2`
- name: `Smb2UpdateSessionWithClaims`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400921f0`

## callees

- `0x14002019c`
- `0x1400224b8`
- `0x1400315dc`
- `0x140031d6c`
- `0x140068560`
- `0x140069d7c`
- `0x140077600`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140069e82`
- `ntoskrnl!RtlInitUnicodeString` at `0x140069e82`
- `ntoskrnl!NtClose` at `0x14006a094`
- `ntoskrnl!NtClose` at `0x14006a094`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140069fb9`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140069fb9`
- `ntoskrnl!NtSetInformationThread` at `0x140069f85`
- `ntoskrnl!NtSetInformationThread` at `0x140069f85`
- `srvnet!SrvLibS4U2SelfAuth` at `0x140069f5a`
- `srvnet!SrvLibS4U2SelfAuth` at `0x140069f5a`
- `ksecdd!FreeContextBuffer` at `0x14006a07f`
- `ksecdd!FreeContextBuffer` at `0x14006a07f`
- `ksecdd!MapSecurityError` at `0x140069e15`
- `ksecdd!MapSecurityError` at `0x140069e15`
- `ksecdd!QueryContextAttributesW` at `0x140069e07`
- `ksecdd!QueryContextAttributesW` at `0x140069e07`

## pseudocode

```c
__int64 __fastcall Smb2UpdateSessionWithClaims(__int64 a1, int a2)
{
  __int64 v2; // r15
  int v3; // r13d
  __int64 v4; // rdi
  NTSTATUS AuthenticationIdToken; // ebx
  SECURITY_STATUS v6; // eax
  USHORT Length; // dx
  unsigned __int16 v8; // cx
  int v9; // eax
  NTSTATUS v10; // eax
  void *v11; // rcx
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  PWSTR v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  PWSTR Buffer; // [rsp+58h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  WCHAR *pBuffer; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE ThreadInformation; // [rsp+B8h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  pBuffer = 0;
  DestinationString = 0;
  v13 = 0;
  v3 = a1;
  v14 = 0;
  v15 = 0;
  Buffer = 0;
  v4 = *(_QWORD *)(v2 + 48);
  ThreadInformation = 0;
  if ( !v4 || !*(_QWORD *)(v4 + 32) && !*(_QWORD *)(v4 + 40) || *(_BYTE *)(v4 + 24) )
    return 3221225480LL;
  if ( Smb2S4U2SelfContext )
  {
    v6 = QueryContextAttributesW((PCtxtHandle)(v4 + 32), 1u, &pBuffer);
    AuthenticationIdToken = MapSecurityError(v6);
    if ( AuthenticationIdToken >= 0 )
    {
      if ( pBuffer && *pBuffer )
      {
        RtlInitUnicodeString(&DestinationString, pBuffer);
        Length = DestinationString.Length;
        v8 = 0;
        Buffer = DestinationString.Buffer;
        if ( DestinationString.Length >> 1 )
        {
          do
          {
            if ( DestinationString.Buffer[v8] == 92 )
              break;
            ++v8;
          }
          while ( v8 < (unsigned __int16)(DestinationString.Length >> 1) );
        }
        if ( DestinationString.Buffer[v8] == 92 )
        {
          LOWORD(v15) = 2 * v8;
          WORD1(v15) = 2 * v8;
          Length = DestinationString.Length - 2 * v8 - 2;
          v14 = &DestinationString.Buffer[v8 + 1];
        }
        else
        {
          LODWORD(v15) = 0;
          v14 = DestinationString.Buffer;
        }
        LOWORD(v13) = Length;
        WORD1(v13) = Length;
      }
      else
      {
        LOWORD(v13) = 0;
        LOWORD(v15) = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          (unsigned int)&WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids,
          (unsigned int)&v15,
          (__int64)&v13);
      }
      v9 = SrvLibS4U2SelfAuth(Smb2S4U2SelfContext, &v13, &v15, &ThreadInformation);
      AuthenticationIdToken = v9;
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            50,
            &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids,
            (unsigned int)v9);
        }
      }
      else
      {
        v10 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
        AuthenticationIdToken = v10;
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              49,
              &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids,
              (unsigned int)v10);
          }
        }
        else
        {
          Smb2SecurityContextCaptureThreadToken(v4);
          if ( *(_BYTE *)(v4 + 24) )
          {
            v11 = *(void **)(v4 + 48);
            if ( v11 )
              AuthenticationIdToken = SeQueryAuthenticationIdToken(v11, (PLUID)(*(_QWORD *)(v2 + 32) + 160LL));
          }
          Smb2Revert();
        }
        if ( AuthenticationIdToken >= 0 )
          goto LABEL_44;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, &WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids);
    }
  }
  else
  {
    AuthenticationIdToken = -1073741275;
  }
  if ( (byte_14004C339 & 0x40) != 0 )
    McTemplateK0hzr0hzr2q_EtwWriteTransfer(
      (unsigned __int16)v15 >> 1,
      a2,
      v3 + 584,
      (unsigned __int16)v13 >> 1,
      (__int64)v14,
      (unsigned __int16)v15 >> 1,
      (__int64)Buffer,
      AuthenticationIdToken);
LABEL_44:
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  if ( ThreadInformation )
    NtClose(ThreadInformation);
  return (unsigned int)AuthenticationIdToken;
}

```

## disassembly

```asm
0x140069d7c  mov     [rsp-38h+arg_10], rbx
0x140069d81  push    rbp
0x140069d82  push    rsi
0x140069d83  push    rdi
0x140069d84  push    r12
0x140069d86  push    r13
0x140069d88  push    r14
0x140069d8a  push    r15
0x140069d8c  mov     rbp, rsp
0x140069d8f  sub     rsp, 70h
0x140069d93  mov     r15, [rcx+230h]
0x140069d9a  xor     r12d, r12d
0x140069d9d  xorps   xmm0, xmm0
0x140069da0  mov     [rbp+pBuffer], r12
0x140069da4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140069da8  mov     [rbp+var_30], r12
0x140069dac  mov     r13, rcx
0x140069daf  mov     [rbp+var_28], r12
0x140069db3  mov     [rbp+var_20], r12
0x140069db7  mov     [rbp+var_18], r12
0x140069dbb  mov     rdi, [r15+30h]
0x140069dbf  mov     [rbp+ThreadInformation], r12
0x140069dc3  test    rdi, rdi
0x140069dc6  jz      loc_14006A0A4
0x140069dcc  lea     rcx, [rdi+20h]; phContext
0x140069dd0  cmp     [rcx], r12
0x140069dd3  jnz     short loc_140069DDF
0x140069dd5  cmp     [rdi+28h], r12
0x140069dd9  jz      loc_14006A0A4
0x140069ddf  cmp     [rdi+18h], r12b
0x140069de3  jnz     loc_14006A0A4
0x140069de9  cmp     cs:Smb2S4U2SelfContext, r12
0x140069df0  jnz     short loc_140069DFC
0x140069df2  mov     ebx, 0C0000225h
0x140069df7  jmp     loc_14006A036
0x140069dfc  mov     esi, 1
0x140069e01  lea     r8, [rbp+pBuffer]; pBuffer
0x140069e05  mov     edx, esi; ulAttribute
0x140069e07  call    cs:__imp_QueryContextAttributesW
0x140069e0e  nop     dword ptr [rax+rax+00h]
0x140069e13  mov     ecx, eax; SecStatus
0x140069e15  call    cs:__imp_MapSecurityError
0x140069e1c  nop     dword ptr [rax+rax+00h]
0x140069e21  mov     ebx, eax
0x140069e23  test    eax, eax
0x140069e25  jns     short loc_140069E6B
0x140069e27  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069e2e  lea     r14, WPP_GLOBAL_Control
0x140069e35  cmp     rcx, r14
0x140069e38  jz      loc_14006A036
0x140069e3e  bt      dword ptr [rcx+2Ch], 11h
0x140069e43  jnb     loc_14006A036
0x140069e49  cmp     byte ptr [rcx+29h], 2
0x140069e4d  jb      loc_14006A036
0x140069e53  mov     rcx, [rcx+18h]
0x140069e57  lea     edx, [rsi+2Eh]
0x140069e5a  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x140069e61  call    WPP_SF_
0x140069e66  jmp     loc_14006A036
0x140069e6b  mov     rdx, [rbp+pBuffer]; SourceString
0x140069e6f  test    rdx, rdx
0x140069e72  jz      loc_140069EFB
0x140069e78  cmp     [rdx], r12w
0x140069e7c  jz      short loc_140069EFB
0x140069e7e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140069e82  call    cs:__imp_RtlInitUnicodeString
0x140069e89  nop     dword ptr [rax+rax+00h]
0x140069e8e  movzx   edx, [rbp+DestinationString.Length]
0x140069e92  mov     ecx, r12d
0x140069e95  mov     r8, [rbp+DestinationString.Buffer]
0x140069e99  movzx   r9d, dx
0x140069e9d  shr     r9w, 1
0x140069ea1  mov     [rbp+var_18], r8
0x140069ea5  cmp     r12w, r9w
0x140069ea9  jnb     short loc_140069EBF
0x140069eab  movzx   eax, cx
0x140069eae  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140069eb4  jz      short loc_140069EBF
0x140069eb6  add     cx, si
0x140069eb9  cmp     cx, r9w
0x140069ebd  jb      short loc_140069EAB
0x140069ebf  movzx   eax, cx
0x140069ec2  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140069ec8  jnz     short loc_140069EF1
0x140069eca  add     cx, cx
0x140069ecd  inc     rax
0x140069ed0  sub     dx, cx
0x140069ed3  mov     word ptr [rbp+var_20], cx
0x140069ed7  mov     word ptr [rbp+var_20+2], cx
0x140069edb  sub     dx, 2
0x140069edf  lea     rax, [r8+rax*2]
0x140069ee3  mov     [rbp+var_28], rax
0x140069ee7  mov     word ptr [rbp+var_30], dx
0x140069eeb  mov     word ptr [rbp+var_30+2], dx
0x140069eef  jmp     short loc_140069F05
0x140069ef1  mov     dword ptr [rbp+var_20], r12d
0x140069ef5  mov     [rbp+var_28], r8
0x140069ef9  jmp     short loc_140069EE7
0x140069efb  mov     word ptr [rbp+var_30], r12w
0x140069f00  mov     word ptr [rbp+var_20], r12w
0x140069f05  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069f0c  lea     r14, WPP_GLOBAL_Control
0x140069f13  cmp     rcx, r14
0x140069f16  jz      short loc_140069F47
0x140069f18  bt      dword ptr [rcx+2Ch], 11h
0x140069f1d  jnb     short loc_140069F47
0x140069f1f  cmp     byte ptr [rcx+29h], 4
0x140069f23  jb      short loc_140069F47
0x140069f25  mov     rcx, [rcx+18h]
0x140069f29  lea     rax, [rbp+var_30]
0x140069f2d  mov     edx, 30h ; '0'
0x140069f32  mov     [rsp+70h+var_50], rax
0x140069f37  lea     r9, [rbp+var_20]
0x140069f3b  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x140069f42  call    WPP_SF_ZZ
0x140069f47  mov     rcx, cs:Smb2S4U2SelfContext
0x140069f4e  lea     r9, [rbp+ThreadInformation]
0x140069f52  lea     r8, [rbp+var_20]
0x140069f56  lea     rdx, [rbp+var_30]
0x140069f5a  call    cs:__imp_SrvLibS4U2SelfAuth
0x140069f61  nop     dword ptr [rax+rax+00h]
0x140069f66  mov     ebx, eax
0x140069f68  test    eax, eax
0x140069f6a  js      loc_14006A005
0x140069f70  mov     r9d, 8; ThreadInformationLength
0x140069f76  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x140069f7a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140069f81  lea     edx, [r9-3]; ThreadInformationClass
0x140069f85  call    cs:__imp_NtSetInformationThread
0x140069f8c  nop     dword ptr [rax+rax+00h]
0x140069f91  mov     ebx, eax
0x140069f93  test    eax, eax
0x140069f95  js      short loc_140069FCE
0x140069f97  mov     rcx, rdi
0x140069f9a  call    Smb2SecurityContextCaptureThreadToken
0x140069f9f  cmp     [rdi+18h], r12b
0x140069fa3  jz      short loc_140069FC7
0x140069fa5  mov     rcx, [rdi+30h]; Token
0x140069fa9  test    rcx, rcx
0x140069fac  jz      short loc_140069FC7
0x140069fae  mov     rdx, [r15+20h]
0x140069fb2  add     rdx, 0A0h; AuthenticationId
0x140069fb9  call    cs:__imp_SeQueryAuthenticationIdToken
0x140069fc0  nop     dword ptr [rax+rax+00h]
0x140069fc5  mov     ebx, eax
0x140069fc7  call    Smb2Revert
0x140069fcc  jmp     short loc_140069FFF
0x140069fce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140069fd5  cmp     rcx, r14
0x140069fd8  jz      short loc_140069FFF
0x140069fda  bt      dword ptr [rcx+2Ch], 11h
0x140069fdf  jnb     short loc_140069FFF
0x140069fe1  cmp     [rcx+29h], sil
0x140069fe5  jb      short loc_140069FFF
0x140069fe7  mov     rcx, [rcx+18h]
0x140069feb  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x140069ff2  mov     edx, 31h ; '1'
0x140069ff7  mov     r9d, eax
0x140069ffa  call    WPP_SF_d
0x140069fff  test    ebx, ebx
0x14006a001  js      short loc_14006A036
0x14006a003  jmp     short loc_14006A076
0x14006a005  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a00c  cmp     rcx, r14
0x14006a00f  jz      short loc_14006A036
0x14006a011  bt      dword ptr [rcx+2Ch], 11h
0x14006a016  jnb     short loc_14006A036
0x14006a018  cmp     [rcx+29h], sil
0x14006a01c  jb      short loc_14006A036
0x14006a01e  mov     rcx, [rcx+18h]
0x14006a022  lea     r8, WPP_e0e359be8cf43294cb4320ac1055cae3_Traceguids
0x14006a029  mov     edx, 32h ; '2'
0x14006a02e  mov     r9d, eax
0x14006a031  call    WPP_SF_d
0x14006a036  test    cs:byte_14004C339, 40h
0x14006a03d  jz      short loc_14006A076
0x14006a03f  mov     rax, [rbp+var_18]
0x14006a043  lea     r8, [r13+248h]
0x14006a04a  movzx   ecx, word ptr [rbp+var_20]
0x14006a04e  movzx   r9d, word ptr [rbp+var_30]
0x14006a053  mov     [rsp+70h+var_38], ebx
0x14006a057  mov     [rsp+70h+var_40], rax
0x14006a05c  mov     rax, [rbp+var_28]
0x14006a060  shr     cx, 1
0x14006a063  mov     [rsp+70h+var_48], cx
0x14006a068  shr     r9w, 1
0x14006a06c  mov     [rsp+70h+var_50], rax
0x14006a071  call    McTemplateK0hzr0hzr2q_EtwWriteTransfer
0x14006a076  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x14006a07a  test    rcx, rcx
0x14006a07d  jz      short loc_14006A08B
0x14006a07f  call    cs:__imp_FreeContextBuffer
0x14006a086  nop     dword ptr [rax+rax+00h]
0x14006a08b  mov     rcx, [rbp+ThreadInformation]; Handle
0x14006a08f  test    rcx, rcx
0x14006a092  jz      short loc_14006A0A0
0x14006a094  call    cs:__imp_NtClose
0x14006a09b  nop     dword ptr [rax+rax+00h]
0x14006a0a0  mov     eax, ebx
0x14006a0a2  jmp     short loc_14006A0A9
0x14006a0a4  mov     eax, 0C0000008h
0x14006a0a9  mov     rbx, [rsp+70h+arg_10]
0x14006a0b1  add     rsp, 70h
0x14006a0b5  pop     r15
0x14006a0b7  pop     r14
0x14006a0b9  pop     r13
0x14006a0bb  pop     r12
0x14006a0bd  pop     rdi
0x14006a0be  pop     rsi
0x14006a0bf  pop     rbp
0x14006a0c0  retn
```
