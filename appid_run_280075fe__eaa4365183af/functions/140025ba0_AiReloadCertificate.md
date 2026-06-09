# AiReloadCertificate

- ea: `0x140025ba0`
- end: `0x140025e34`
- name: `AiReloadCertificate`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140033f50`

## callees

- `0x1400016d8`
- `0x140002678`
- `0x14000293c`
- `0x140025ba0`
- `0x1400261bc`
- `0x140026c08`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025dbd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025dbd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025ca9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025ca9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025cf1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025cf1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025cbe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025cbe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140025db1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140025db1`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140025d45`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140025d45`
- `ntoskrnl!ZwClose` at `0x140025e14`
- `ntoskrnl!ZwClose` at `0x140025e14`

## pseudocode

```c
__int64 __fastcall AiReloadCertificate(USHORT *a1, unsigned int a2)
{
  int v3; // edx
  int v4; // ebx
  _QWORD *v5; // rax
  unsigned __int64 v6; // rbx
  _QWORD **v7; // rax
  _QWORD *v8; // rcx
  unsigned __int64 v9; // rax
  UNICODE_STRING String1; // [rsp+20h] [rbp-10h] BYREF
  __int64 v12; // [rsp+70h] [rbp+40h]
  __int64 v13; // [rsp+70h] [rbp+40h]
  __int64 v14; // [rsp+70h] [rbp+40h]
  HANDLE Handle; // [rsp+78h] [rbp+48h] BYREF

  Handle = 0;
  String1 = 0;
  if ( a2 >= 2 && (v3 = *a1, (_WORD)v3) && (v3 & 1) == 0 && v3 == a2 - 2 )
  {
    String1.Length = *a1;
    String1.Buffer = a1 + 1;
    String1.MaximumLength = v3;
    v12 = (unsigned int)Feature_Servicing_ApplockerDeadlock_37068202__private_featureState;
    if ( (Feature_Servicing_ApplockerDeadlock_37068202__private_featureState & 0x10) == 0 )
    {
      LODWORD(v12) = Feature_Servicing_ApplockerDeadlock_37068202__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(
        wil_details_featureDescriptors_a,
        v12,
        3,
        1,
        *(_QWORD *)&String1.Length,
        String1.Buffer);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v12, 3, wil_details_featureDescriptors_a);
    }
    v4 = AiRegOpenKey(0, (struct _UNICODE_STRING *)&qword_140009510, 0x20019u, &Handle);
    if ( v4 >= 0 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(&qword_1400195D8, 0);
      v5 = (_QWORD *)AipCertificateStore;
      v6 = 0;
      while ( v5 )
      {
        v6 = (unsigned __int64)v5;
        v5 = (_QWORD *)*v5;
      }
      while ( v6 )
      {
        if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(v6 + 24), 1u) )
        {
          RtlAvlRemoveNode(&AipCertificateStore, v6);
          AipFreeCert(v6);
          break;
        }
        v7 = *(_QWORD ***)(v6 + 8);
        if ( v7 )
        {
          v8 = *v7;
          if ( *v7 )
          {
            do
            {
              v6 = (unsigned __int64)v8;
              v8 = (_QWORD *)*v8;
            }
            while ( v8 );
          }
          else
          {
            v6 = *(_QWORD *)(v6 + 8);
          }
        }
        else
        {
          do
          {
            v9 = v6;
            v6 = *(_QWORD *)(v6 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
          }
          while ( v6 && *(_QWORD *)v6 != v9 );
        }
      }
      v13 = (unsigned int)Feature_Servicing_ApplockerDeadlock_37068202__private_featureState;
      if ( (Feature_Servicing_ApplockerDeadlock_37068202__private_featureState & 0x10) == 0 )
      {
        LODWORD(v13) = Feature_Servicing_ApplockerDeadlock_37068202__private_featureState | 1;
        wil_details_FeatureReporting_ReportUsageToService(
          wil_details_featureDescriptors_a,
          v13,
          3,
          1,
          *(_QWORD *)&String1.Length,
          String1.Buffer);
        wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v13, 3, wil_details_featureDescriptors_a);
      }
      v4 = AipAddCertFromCertStore(Handle, &String1);
      ExReleasePushLockExclusiveEx(&qword_1400195D8, 0);
      KeLeaveCriticalRegion();
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids,
        (unsigned int)v4);
    }
  }
  else
  {
    v4 = -1073741811;
  }
  v14 = (unsigned int)Feature_Servicing_ApplockerDeadlock_37068202__private_featureState;
  if ( (Feature_Servicing_ApplockerDeadlock_37068202__private_featureState & 0x10) == 0 )
  {
    LODWORD(v14) = Feature_Servicing_ApplockerDeadlock_37068202__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(
      wil_details_featureDescriptors_a,
      v14,
      3,
      1,
      *(_QWORD *)&String1.Length,
      String1.Buffer);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v14, 3, wil_details_featureDescriptors_a);
  }
  ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140025ba0  mov     [rsp-28h+arg_0], rbx
0x140025ba5  push    rbp
0x140025ba6  push    rsi
0x140025ba7  push    rdi
0x140025ba8  push    r12
0x140025baa  push    r15
0x140025bac  mov     rbp, rsp
0x140025baf  sub     rsp, 30h
0x140025bb3  xor     edi, edi
0x140025bb5  lea     r12, wil_details_featureDescriptors_a
0x140025bbc  mov     [rbp+Handle], rdi
0x140025bc0  xorps   xmm0, xmm0
0x140025bc3  mov     eax, edx
0x140025bc5  mov     r8, rcx
0x140025bc8  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140025bcc  lea     esi, [rdi+1]
0x140025bcf  lea     r15d, [rdi+3]
0x140025bd3  cmp     edx, 2
0x140025bd6  jb      loc_140025DCB
0x140025bdc  movzx   edx, word ptr [rcx]
0x140025bdf  test    dx, dx
0x140025be2  jz      loc_140025DCB
0x140025be8  test    sil, dl
0x140025beb  jnz     loc_140025DCB
0x140025bf1  lea     ecx, [rax-2]
0x140025bf4  cmp     edx, ecx
0x140025bf6  jnz     loc_140025DCB
0x140025bfc  lea     rax, [r8+2]
0x140025c00  mov     [rbp+String1.Length], dx
0x140025c04  mov     [rbp+String1.Buffer], rax
0x140025c08  mov     [rbp+String1.MaximumLength], dx
0x140025c0c  mov     ecx, cs:Feature_Servicing_ApplockerDeadlock_37068202__private_featureState
0x140025c12  mov     [rbp+arg_10], rdi
0x140025c16  mov     dword ptr [rbp+arg_10], ecx
0x140025c19  test    cl, 10h
0x140025c1c  jnz     short loc_140025C4C
0x140025c1e  mov     rax, [rbp+arg_10]
0x140025c22  or      ecx, esi
0x140025c24  mov     [rbp+arg_10], rax
0x140025c28  mov     r9d, esi
0x140025c2b  mov     dword ptr [rbp+arg_10], ecx
0x140025c2e  mov     r8d, r15d
0x140025c31  mov     rdx, [rbp+arg_10]
0x140025c35  mov     rcx, r12
0x140025c38  call    wil_details_FeatureReporting_ReportUsageToService
0x140025c3d  mov     rcx, [rbp+arg_10]
0x140025c41  mov     r8, r12
0x140025c44  mov     edx, r15d
0x140025c47  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140025c4c  lea     r9, [rbp+Handle]
0x140025c50  mov     r8d, 20019h
0x140025c56  lea     rdx, qword_140009510
0x140025c5d  xor     ecx, ecx
0x140025c5f  call    AiRegOpenKey
0x140025c64  mov     ebx, eax
0x140025c66  test    eax, eax
0x140025c68  jns     short loc_140025CA9
0x140025c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c71  lea     rax, WPP_GLOBAL_Control
0x140025c78  cmp     rcx, rax
0x140025c7b  jz      loc_140025DD0
0x140025c81  mov     edx, [rcx+2Ch]
0x140025c84  test    dl, dl
0x140025c86  jns     loc_140025DD0
0x140025c8c  mov     rcx, [rcx+18h]
0x140025c90  lea     r8, WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids
0x140025c97  mov     edx, 0Fh
0x140025c9c  mov     r9d, ebx
0x140025c9f  call    WPP_SF_D
0x140025ca4  jmp     loc_140025DD0
0x140025ca9  call    cs:__imp_KeEnterCriticalRegion
0x140025cb0  nop     dword ptr [rax+rax+00h]
0x140025cb5  xor     edx, edx
0x140025cb7  lea     rcx, qword_1400195D8
0x140025cbe  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140025cc5  nop     dword ptr [rax+rax+00h]
0x140025cca  mov     rax, cs:AipCertificateStore
0x140025cd1  mov     rbx, rdi
0x140025cd4  jmp     short loc_140025CDC
0x140025cd6  mov     rbx, rax
0x140025cd9  mov     rax, [rax]
0x140025cdc  test    rax, rax
0x140025cdf  jnz     short loc_140025CD6
0x140025ce1  test    rbx, rbx
0x140025ce4  jz      short loc_140025D59
0x140025ce6  lea     rdx, [rbx+18h]; String2
0x140025cea  mov     r8b, sil; CaseInSensitive
0x140025ced  lea     rcx, [rbp+String1]; String1
0x140025cf1  call    cs:__imp_RtlEqualUnicodeString
0x140025cf8  nop     dword ptr [rax+rax+00h]
0x140025cfd  test    al, al
0x140025cff  jnz     short loc_140025D3B
0x140025d01  mov     rax, [rbx+8]
0x140025d05  test    rax, rax
0x140025d08  jz      short loc_140025D2C
0x140025d0a  mov     rcx, [rax]
0x140025d0d  test    rcx, rcx
0x140025d10  jz      short loc_140025D22
0x140025d12  mov     rax, [rcx]
0x140025d15  mov     rbx, rcx
0x140025d18  mov     rcx, rax
0x140025d1b  test    rax, rax
0x140025d1e  jnz     short loc_140025D12
0x140025d20  jmp     short loc_140025CE1
0x140025d22  mov     rbx, rax
0x140025d25  jmp     short loc_140025CE1
0x140025d27  cmp     [rbx], rax
0x140025d2a  jz      short loc_140025CE1
0x140025d2c  mov     rax, rbx
0x140025d2f  mov     rbx, [rbx+10h]
0x140025d33  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140025d37  jnz     short loc_140025D27
0x140025d39  jmp     short loc_140025CE1
0x140025d3b  mov     rdx, rbx
0x140025d3e  lea     rcx, AipCertificateStore
0x140025d45  call    cs:__imp_RtlAvlRemoveNode
0x140025d4c  nop     dword ptr [rax+rax+00h]
0x140025d51  mov     rcx, rbx
0x140025d54  call    AipFreeCert
0x140025d59  mov     ecx, cs:Feature_Servicing_ApplockerDeadlock_37068202__private_featureState
0x140025d5f  mov     [rbp+arg_10], rdi
0x140025d63  mov     dword ptr [rbp+arg_10], ecx
0x140025d66  test    cl, 10h
0x140025d69  jnz     short loc_140025D99
0x140025d6b  mov     rax, [rbp+arg_10]
0x140025d6f  or      ecx, esi
0x140025d71  mov     [rbp+arg_10], rax
0x140025d75  mov     r9, rsi
0x140025d78  mov     dword ptr [rbp+arg_10], ecx
0x140025d7b  mov     r8d, r15d
0x140025d7e  mov     rdx, [rbp+arg_10]
0x140025d82  mov     rcx, r12
0x140025d85  call    wil_details_FeatureReporting_ReportUsageToService
0x140025d8a  mov     rcx, [rbp+arg_10]
0x140025d8e  mov     r8, r12
0x140025d91  mov     edx, r15d
0x140025d94  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140025d99  mov     rcx, [rbp+Handle]
0x140025d9d  lea     rdx, [rbp+String1]
0x140025da1  call    AipAddCertFromCertStore
0x140025da6  xor     edx, edx
0x140025da8  lea     rcx, qword_1400195D8
0x140025daf  mov     ebx, eax
0x140025db1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140025db8  nop     dword ptr [rax+rax+00h]
0x140025dbd  call    cs:__imp_KeLeaveCriticalRegion
0x140025dc4  nop     dword ptr [rax+rax+00h]
0x140025dc9  jmp     short loc_140025DD0
0x140025dcb  mov     ebx, 0C000000Dh
0x140025dd0  mov     ecx, cs:Feature_Servicing_ApplockerDeadlock_37068202__private_featureState
0x140025dd6  mov     [rbp+arg_10], rdi
0x140025dda  mov     dword ptr [rbp+arg_10], ecx
0x140025ddd  test    cl, 10h
0x140025de0  jnz     short loc_140025E10
0x140025de2  mov     rax, [rbp+arg_10]
0x140025de6  or      ecx, esi
0x140025de8  mov     [rbp+arg_10], rax
0x140025dec  mov     r9, rsi
0x140025def  mov     dword ptr [rbp+arg_10], ecx
0x140025df2  mov     r8d, r15d
0x140025df5  mov     rdx, [rbp+arg_10]
0x140025df9  mov     rcx, r12
0x140025dfc  call    wil_details_FeatureReporting_ReportUsageToService
0x140025e01  mov     rcx, [rbp+arg_10]
0x140025e05  mov     r8, r12
0x140025e08  mov     edx, r15d
0x140025e0b  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140025e10  mov     rcx, [rbp+Handle]; Handle
0x140025e14  call    cs:__imp_ZwClose
0x140025e1b  nop     dword ptr [rax+rax+00h]
0x140025e20  mov     eax, ebx
0x140025e22  mov     rbx, [rsp+30h+arg_0]
0x140025e27  add     rsp, 30h
0x140025e2b  pop     r15
0x140025e2d  pop     r12
0x140025e2f  pop     rdi
0x140025e30  pop     rsi
0x140025e31  pop     rbp
0x140025e32  retn
```
