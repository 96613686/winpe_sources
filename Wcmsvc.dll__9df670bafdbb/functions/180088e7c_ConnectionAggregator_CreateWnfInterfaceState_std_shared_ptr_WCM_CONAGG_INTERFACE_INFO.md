# ConnectionAggregator::CreateWnfInterfaceState(std::shared_ptr<WCM_CONAGG_INTERFACE_INFO> &)

- ea: `0x180088e7c`
- end: `0x18008911a`
- name: `?CreateWnfInterfaceState@ConnectionAggregator@@AEAAXAEAV?$shared_ptr@UWCM_CONAGG_INTERFACE_INFO@@@std@@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a8c8`

## callees

- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180019434`
- `0x18003b208`
- `0x180084f50`
- `0x180088e7c`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x180088f78`
- `ntdll!NtCreateWnfStateName` at `0x180089025`
- `ntdll!NtCreateWnfStateName` at `0x180088f78`
- `ntdll!NtCreateWnfStateName` at `0x180089025`
- `ntdll!NtDeleteWnfStateName` at `0x180089064`
- `ntdll!NtDeleteWnfStateName` at `0x180089064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800890be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800890be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180088f0c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180088f0c`

## string_xrefs

- `0x180088ed4`: `ConnectionAggregator::CreateWnfInterfaceState`
- `0x1800890e0`: `ConnectionAggregator::CreateWnfInterfaceState`

## pseudocode

```c
PSECURITY_DESCRIPTOR __fastcall ConnectionAggregator::CreateWnfInterfaceState(__int64 a1, __int64 a2)
{
  char v2; // di
  __int64 v4; // rcx
  int WnfStateName; // eax
  int v6; // eax
  PSECURITY_DESCRIPTOR result; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  SecurityDescriptor = 0;
  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      186,
      WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
      "ConnectionAggregator::CreateWnfInterfaceState");
    v4 = WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)(*(_QWORD *)a2 + 80LL) )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;;1;;;WD)(A;;GA;;;S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888)",
           1u,
           &SecurityDescriptor,
           0) )
    {
      WnfStateName = NtCreateWnfStateName(*(_QWORD *)a2 + 64LL, 3, 0);
      v2 = WnfStateName;
      if ( WnfStateName >= 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_DD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 189, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids);
        }
        v6 = NtCreateWnfStateName(*(_QWORD *)a2 + 72LL, 3, 0);
        v2 = v6;
        if ( v6 >= 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_DD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 191, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids);
          }
          *(_DWORD *)(*(_QWORD *)a2 + 80LL) = 1;
        }
        else
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              190,
              WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
              (unsigned int)v6);
          }
          NtDeleteWnfStateName(*(_QWORD *)a2 + 64LL);
        }
        goto LABEL_31;
      }
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          188,
          WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
          (unsigned int)WnfStateName);
        goto LABEL_31;
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 187, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids);
LABEL_31:
        v4 = WPP_GLOBAL_Control;
      }
    }
  }
  result = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    result = LocalFree(SecurityDescriptor);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v4 != &WPP_GLOBAL_Control && *(_BYTE *)(v4 + 25) >= 5u && (*(_BYTE *)(v4 + 28) & 1) != 0 )
    return (PSECURITY_DESCRIPTOR)WPP_SF_sL(
                                   *(_QWORD *)(v4 + 16),
                                   192,
                                   (unsigned int)WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
                                   (unsigned int)"ConnectionAggregator::CreateWnfInterfaceState",
                                   v2);
  return result;
}

```

## disassembly

```asm
0x180088e7c  mov     [rsp+arg_0], rbx
0x180088e81  mov     [rsp+arg_10], rbp
0x180088e86  push    rsi
0x180088e87  push    rdi
0x180088e88  push    r15
0x180088e8a  sub     rsp, 50h
0x180088e8e  mov     rax, cs:__security_cookie
0x180088e95  xor     rax, rsp
0x180088e98  mov     [rsp+68h+var_20], rax
0x180088e9d  xor     edi, edi
0x180088e9f  mov     rbx, rdx
0x180088ea2  mov     [rsp+68h+SecurityDescriptor], rdi
0x180088ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180088eae  lea     rbp, WPP_GLOBAL_Control
0x180088eb5  lea     esi, [rdi+1]
0x180088eb8  lea     r15, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x180088ebf  cmp     rcx, rbp
0x180088ec2  jz      short loc_180088EEF
0x180088ec4  cmp     byte ptr [rcx+19h], 5
0x180088ec8  jb      short loc_180088EEF
0x180088eca  test    [rcx+1Ch], sil
0x180088ece  jz      short loc_180088EEF
0x180088ed0  mov     rcx, [rcx+10h]
0x180088ed4  lea     r9, aConnectionaggr_13; "ConnectionAggregator::CreateWnfInterfac"...
0x180088edb  mov     edx, 0BAh
0x180088ee0  mov     r8, r15
0x180088ee3  call    WPP_SF_s
0x180088ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180088eef  mov     rax, [rbx]
0x180088ef2  cmp     [rax+50h], edi
0x180088ef5  jnz     loc_1800890B1
0x180088efb  xor     r9d, r9d; SecurityDescriptorSize
0x180088efe  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180088f03  mov     edx, esi; StringSDRevision
0x180088f05  lea     rcx, StringSecurityDescriptor; "D:(A;;1;;;WD)(A;;GA;;;S-1-5-80-41557679"...
0x180088f0c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180088f12  test    eax, eax
0x180088f14  jnz     short loc_180088F50
0x180088f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180088f1d  cmp     rcx, rbp
0x180088f20  jz      loc_1800890B1
0x180088f26  cmp     byte ptr [rcx+19h], 4
0x180088f2a  jb      loc_1800890B1
0x180088f30  test    [rcx+1Ch], sil
0x180088f34  jz      loc_1800890B1
0x180088f3a  mov     rcx, [rcx+10h]
0x180088f3e  mov     edx, 0BBh
0x180088f43  mov     r8, r15
0x180088f46  call    WPP_SF_
0x180088f4b  jmp     loc_1800890AA
0x180088f50  mov     rax, [rsp+68h+SecurityDescriptor]
0x180088f55  xor     r9d, r9d
0x180088f58  mov     rcx, [rbx]
0x180088f5b  xor     r8d, r8d
0x180088f5e  mov     [rsp+68h+var_38], rax
0x180088f63  add     rcx, 40h ; '@'
0x180088f67  mov     [rsp+68h+var_40], 25Ch
0x180088f6f  lea     edx, [r9+3]
0x180088f73  mov     [rsp+68h+var_48], rdi
0x180088f78  call    cs:__imp_NtCreateWnfStateName
0x180088f7e  mov     edi, eax
0x180088f80  test    eax, eax
0x180088f82  jns     short loc_180088FC1
0x180088f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180088f8b  cmp     rcx, rbp
0x180088f8e  jz      loc_1800890B1
0x180088f94  cmp     [rcx+19h], sil
0x180088f98  jb      loc_1800890B1
0x180088f9e  test    [rcx+1Ch], sil
0x180088fa2  jz      loc_1800890B1
0x180088fa8  mov     rcx, [rcx+10h]
0x180088fac  mov     edx, 0BCh
0x180088fb1  mov     r9d, eax
0x180088fb4  mov     r8, r15
0x180088fb7  call    WPP_SF_d
0x180088fbc  jmp     loc_1800890AA
0x180088fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180088fc8  cmp     rcx, rbp
0x180088fcb  jz      short loc_180088FF9
0x180088fcd  cmp     byte ptr [rcx+19h], 4
0x180088fd1  jb      short loc_180088FF9
0x180088fd3  test    [rcx+1Ch], sil
0x180088fd7  jz      short loc_180088FF9
0x180088fd9  mov     r9, [rbx]
0x180088fdc  mov     edx, 0BDh
0x180088fe1  mov     rcx, [rcx+10h]
0x180088fe5  mov     r8, r15
0x180088fe8  mov     eax, [r9+44h]
0x180088fec  mov     r9d, [r9+40h]
0x180088ff0  mov     dword ptr [rsp+68h+var_48], eax
0x180088ff4  call    WPP_SF_DD
0x180088ff9  mov     rax, [rsp+68h+SecurityDescriptor]
0x180088ffe  xor     r9d, r9d
0x180089001  mov     rcx, [rbx]
0x180089004  xor     r8d, r8d
0x180089007  mov     [rsp+68h+var_38], rax
0x18008900c  add     rcx, 48h ; 'H'
0x180089010  mov     [rsp+68h+var_40], 4
0x180089018  lea     edx, [r9+3]
0x18008901c  mov     [rsp+68h+var_48], 0
0x180089025  call    cs:__imp_NtCreateWnfStateName
0x18008902b  mov     edi, eax
0x18008902d  test    eax, eax
0x18008902f  jns     short loc_18008906C
0x180089031  mov     rcx, cs:WPP_GLOBAL_Control
0x180089038  cmp     rcx, rbp
0x18008903b  jz      short loc_18008905D
0x18008903d  cmp     [rcx+19h], sil
0x180089041  jb      short loc_18008905D
0x180089043  test    [rcx+1Ch], sil
0x180089047  jz      short loc_18008905D
0x180089049  mov     rcx, [rcx+10h]
0x18008904d  mov     edx, 0BEh
0x180089052  mov     r9d, eax
0x180089055  mov     r8, r15
0x180089058  call    WPP_SF_d
0x18008905d  mov     rcx, [rbx]
0x180089060  add     rcx, 40h ; '@'
0x180089064  call    cs:__imp_NtDeleteWnfStateName
0x18008906a  jmp     short loc_1800890AA
0x18008906c  mov     rcx, cs:WPP_GLOBAL_Control
0x180089073  cmp     rcx, rbp
0x180089076  jz      short loc_1800890A4
0x180089078  cmp     byte ptr [rcx+19h], 4
0x18008907c  jb      short loc_1800890A4
0x18008907e  test    [rcx+1Ch], sil
0x180089082  jz      short loc_1800890A4
0x180089084  mov     r9, [rbx]
0x180089087  mov     edx, 0BFh
0x18008908c  mov     rcx, [rcx+10h]
0x180089090  mov     r8, r15
0x180089093  mov     eax, [r9+44h]
0x180089097  mov     r9d, [r9+40h]
0x18008909b  mov     dword ptr [rsp+68h+var_48], eax
0x18008909f  call    WPP_SF_DD
0x1800890a4  mov     rax, [rbx]
0x1800890a7  mov     [rax+50h], esi
0x1800890aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800890b1  mov     rax, [rsp+68h+SecurityDescriptor]
0x1800890b6  test    rax, rax
0x1800890b9  jz      short loc_1800890CB
0x1800890bb  mov     rcx, rax; hMem
0x1800890be  call    cs:__imp_LocalFree
0x1800890c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800890cb  cmp     rcx, rbp
0x1800890ce  jz      short loc_1800890F8
0x1800890d0  cmp     byte ptr [rcx+19h], 5
0x1800890d4  jb      short loc_1800890F8
0x1800890d6  test    [rcx+1Ch], sil
0x1800890da  jz      short loc_1800890F8
0x1800890dc  mov     rcx, [rcx+10h]
0x1800890e0  lea     r9, aConnectionaggr_13; "ConnectionAggregator::CreateWnfInterfac"...
0x1800890e7  mov     edx, 0C0h
0x1800890ec  mov     dword ptr [rsp+68h+var_48], edi
0x1800890f0  mov     r8, r15
0x1800890f3  call    WPP_SF_sL
0x1800890f8  mov     rcx, [rsp+68h+var_20]
0x1800890fd  xor     rcx, rsp; StackCookie
0x180089100  call    __security_check_cookie
0x180089105  lea     r11, [rsp+68h+var_18]
0x18008910a  mov     rbx, [r11+20h]
0x18008910e  mov     rbp, [r11+30h]
0x180089112  mov     rsp, r11
0x180089115  pop     r15
0x180089117  pop     rdi
0x180089118  pop     rsi
0x180089119  retn
```
