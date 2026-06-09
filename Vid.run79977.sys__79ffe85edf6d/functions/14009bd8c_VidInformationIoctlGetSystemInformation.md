# VidInformationIoctlGetSystemInformation

- ea: `0x14009bd8c`
- end: `0x14009c04a`
- name: `VidInformationIoctlGetSystemInformation`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14003782c`
- `0x14009bd54`

## callees

- `0x140008990`
- `0x14001609c`
- `0x140021c36`
- `0x140021c60`
- `0x14009bd8c`
- `0x14009c08c`
- `0x14009c13c`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14009bfbf`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14009bfbf`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14009bfd8`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14009bfd8`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14009bf8b`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14009bf8b`
- `winhvr!WinHvGetSystemInformation` at `0x14009c020`
- `winhvr!WinHvGetSystemInformation` at `0x14009c020`

## pseudocode

```c
NTSTATUS __fastcall VidInformationIoctlGetSystemInformation(
        int a1,
        ULONG *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        _DWORD *a6)
{
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  NTSTATUS result; // eax
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  bool v20; // r15
  _PROCESSOR_NUMBER ProcNumber; // [rsp+30h] [rbp-78h] BYREF
  NTSTATUS v27; // [rsp+34h] [rbp-74h]
  char Str1[16]; // [rsp+38h] [rbp-70h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+48h] [rbp-60h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+58h] [rbp-50h] BYREF

  *a6 = 0;
  v9 = 6;
  if ( a1 <= 6 )
  {
    if ( a1 != 6 )
    {
      if ( a1 )
      {
        v10 = a1 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( v13 )
              {
                if ( v13 == 1 )
                  return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
                return -1073741821;
              }
              v9 = 5;
            }
            else
            {
              v9 = 4;
            }
          }
          else
          {
            v9 = 2;
          }
        }
        else
        {
          v9 = 1;
        }
      }
      else
      {
        v9 = 0;
      }
      return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
    }
    if ( a5 >= 2 )
    {
      result = VidCppcQuerySupport(a4);
      v27 = result;
      if ( result >= 0 )
      {
        result = VidCppcQueryResourcePrioritiesSupport(a4 + 1);
        v27 = result;
        *a6 = 2;
      }
      return result;
    }
    return -1073741789;
  }
  v15 = a1 - 7;
  if ( !v15 )
  {
    v9 = 11;
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v9 = 12;
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  v17 = v16 - 1;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
          return -1073741821;
        v9 = 9;
      }
      else
      {
        v9 = 14;
      }
    }
    else
    {
      v9 = 3;
    }
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  *(_OWORD *)Str1 = 0;
  HviGetHypervisorFeatures(Str1);
  v20 = 0;
  if ( (*(_QWORD *)Str1 & 0x100000000LL) != 0 )
  {
    *(_OWORD *)Str1 = 0;
    HviGetHypervisorFeatures(Str1);
    if ( (*(_QWORD *)Str1 & 0x100000000000LL) == 0 )
      v20 = 1;
  }
  *(_DWORD *)&Str1[12] = 0;
  ProcNumber = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  _RAX = 0;
  __asm { cpuid }
  *(_DWORD *)Str1 = _RBX;
  *(_DWORD *)&Str1[4] = _RDX;
  *(_DWORD *)&Str1[8] = _RCX;
  if ( strncmp_0(Str1, "AuthenticAMD", 0xCu) || !v20 )
  {
    v9 = 13;
    return WinHvGetSystemInformation(v9, a2, a3, a4, a5, a6);
  }
  if ( a3 != 4 || a5 != 256 )
    return -1073741789;
  result = KeGetProcessorNumberFromIndex(*a2, &ProcNumber);
  if ( result >= 0 )
  {
    Affinity.Group = ProcNumber.Group;
    Affinity.Mask = 1LL << ProcNumber.Number;
    KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
    VidBuildSystemTopology(a4);
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
    *a6 = 256;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14009bd8c  push    rbx
0x14009bd8e  push    rsi
0x14009bd8f  push    rdi
0x14009bd90  push    r12
0x14009bd92  push    r13
0x14009bd94  push    r14
0x14009bd96  push    r15
0x14009bd98  sub     rsp, 70h
0x14009bd9c  mov     rax, cs:__security_cookie
0x14009bda3  xor     rax, rsp
0x14009bda6  mov     [rsp+0A8h+var_40], rax
0x14009bdab  mov     rsi, r9
0x14009bdae  mov     r12d, r8d
0x14009bdb1  mov     r13, rdx
0x14009bdb4  mov     r14, [rsp+0A8h+arg_28]
0x14009bdbc  mov     dword ptr [r14], 0
0x14009bdc3  mov     ebx, 6
0x14009bdc8  cmp     ecx, ebx
0x14009bdca  jg      loc_14009BE6B
0x14009bdd0  jz      short loc_14009BE27
0x14009bdd2  test    ecx, ecx
0x14009bdd4  jz      short loc_14009BE20
0x14009bdd6  sub     ecx, 1
0x14009bdd9  jz      short loc_14009BE16
0x14009bddb  sub     ecx, 1
0x14009bdde  jz      short loc_14009BE0C
0x14009bde0  sub     ecx, 1
0x14009bde3  jz      short loc_14009BE02
0x14009bde5  sub     ecx, 1
0x14009bde8  jz      short loc_14009BDF8
0x14009bdea  cmp     ecx, 1
0x14009bded  jnz     loc_14009BE91
0x14009bdf3  jmp     loc_14009C005
0x14009bdf8  mov     ebx, 5
0x14009bdfd  jmp     loc_14009C005
0x14009be02  mov     ebx, 4
0x14009be07  jmp     loc_14009C005
0x14009be0c  mov     ebx, 2
0x14009be11  jmp     loc_14009C005
0x14009be16  mov     ebx, 1
0x14009be1b  jmp     loc_14009C005
0x14009be20  xor     ebx, ebx
0x14009be22  jmp     loc_14009C005
0x14009be27  mov     ebx, 2
0x14009be2c  cmp     [rsp+0A8h+arg_20], ebx
0x14009be33  jb      loc_14009BFEB
0x14009be39  mov     rcx, rsi
0x14009be3c  call    VidCppcQuerySupport
0x14009be41  mov     [rsp+0A8h+var_74], eax
0x14009be45  test    eax, eax
0x14009be47  js      loc_14009C02C
0x14009be4d  lea     rcx, [rsi+1]
0x14009be51  call    VidCppcQueryResourcePrioritiesSupport
0x14009be56  mov     [rsp+0A8h+var_74], eax
0x14009be5a  mov     [r14], ebx
0x14009be5d  jmp     loc_14009C02C
0x14009be62  mov     [rsp+0A8h+var_74], eax
0x14009be66  jmp     loc_14009C02C
0x14009be6b  sub     ecx, 7
0x14009be6e  jz      loc_14009C000
0x14009be74  sub     ecx, 1
0x14009be77  jz      loc_14009BFF9
0x14009be7d  sub     ecx, 1
0x14009be80  jz      short loc_14009BEB9
0x14009be82  sub     ecx, 1
0x14009be85  jz      short loc_14009BEAF
0x14009be87  sub     ecx, 1
0x14009be8a  jz      short loc_14009BEA5
0x14009be8c  cmp     ecx, 1
0x14009be8f  jz      short loc_14009BE9B
0x14009be91  mov     eax, 0C0000003h
0x14009be96  jmp     loc_14009C02C
0x14009be9b  mov     ebx, 9
0x14009bea0  jmp     loc_14009C005
0x14009bea5  mov     ebx, 0Eh
0x14009beaa  jmp     loc_14009C005
0x14009beaf  mov     ebx, 3
0x14009beb4  jmp     loc_14009C005
0x14009beb9  xorps   xmm0, xmm0
0x14009bebc  movups  xmmword ptr [rsp+0A8h+Str1], xmm0
0x14009bec1  lea     rcx, [rsp+0A8h+Str1]
0x14009bec6  call    HviGetHypervisorFeatures
0x14009becb  mov     rax, 100000000h
0x14009bed5  test    qword ptr [rsp+0A8h+Str1], rax
0x14009beda  jz      short loc_14009BF09
0x14009bedc  xorps   xmm0, xmm0
0x14009bedf  movups  xmmword ptr [rsp+0A8h+Str1], xmm0
0x14009bee4  lea     rcx, [rsp+0A8h+Str1]
0x14009bee9  call    HviGetHypervisorFeatures
0x14009beee  mov     rax, 100000000000h
0x14009bef8  test    qword ptr [rsp+0A8h+Str1], rax
0x14009befd  jnz     short loc_14009BF09
0x14009beff  mov     edi, 1
0x14009bf04  mov     r15b, dil
0x14009bf07  jmp     short loc_14009BF11
0x14009bf09  xor     r15b, r15b
0x14009bf0c  mov     edi, 1
0x14009bf11  xorps   xmm0, xmm0
0x14009bf14  movups  xmmword ptr [rsp+0A8h+Str1], xmm0
0x14009bf19  mov     dword ptr [rsp+0A8h+ProcNumber.Group], 0
0x14009bf21  xorps   xmm1, xmm1
0x14009bf24  movups  xmmword ptr [rsp+0A8h+Affinity.Mask], xmm1
0x14009bf29  movups  xmmword ptr [rsp+0A8h+PreviousAffinity.Mask], xmm0
0x14009bf2e  xor     eax, eax
0x14009bf30  xor     ecx, ecx
0x14009bf32  cpuid
0x14009bf34  mov     dword ptr [rsp+0A8h+Str1], eax
0x14009bf38  mov     dword ptr [rsp+0A8h+Str1], ebx
0x14009bf3c  mov     dword ptr [rsp+0A8h+Str1+4], edx
0x14009bf40  mov     dword ptr [rsp+0A8h+Str1+8], ecx
0x14009bf44  mov     r8d, 0Ch; MaxCount
0x14009bf4a  lea     rdx, Str2; "AuthenticAMD"
0x14009bf51  lea     rcx, [rsp+0A8h+Str1]; Str1
0x14009bf56  call    strncmp_0
0x14009bf5b  test    eax, eax
0x14009bf5d  jnz     loc_14009BFF2
0x14009bf63  test    r15b, r15b
0x14009bf66  jz      loc_14009BFF2
0x14009bf6c  lea     ebx, [rax+4]
0x14009bf6f  cmp     r12d, ebx
0x14009bf72  jnz     short loc_14009BFEB
0x14009bf74  mov     ebx, 100h
0x14009bf79  cmp     [rsp+0A8h+arg_20], ebx
0x14009bf80  jnz     short loc_14009BFEB
0x14009bf82  lea     rdx, [rsp+0A8h+ProcNumber]; ProcNumber
0x14009bf87  mov     ecx, [r13+0]; ProcIndex
0x14009bf8b  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14009bf92  nop     dword ptr [rax+rax+00h]
0x14009bf97  test    eax, eax
0x14009bf99  js      loc_14009C02C
0x14009bf9f  movzx   eax, [rsp+0A8h+ProcNumber.Group]
0x14009bfa4  mov     [rsp+0A8h+Affinity.Group], ax
0x14009bfa9  mov     cl, [rsp+0A8h+ProcNumber.Number]
0x14009bfad  shl     rdi, cl
0x14009bfb0  mov     [rsp+0A8h+Affinity.Mask], rdi
0x14009bfb5  lea     rdx, [rsp+0A8h+PreviousAffinity]; PreviousAffinity
0x14009bfba  lea     rcx, [rsp+0A8h+Affinity]; Affinity
0x14009bfbf  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14009bfc6  nop     dword ptr [rax+rax+00h]
0x14009bfcb  mov     rcx, rsi
0x14009bfce  call    VidBuildSystemTopology
0x14009bfd3  lea     rcx, [rsp+0A8h+PreviousAffinity]; PreviousAffinity
0x14009bfd8  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14009bfdf  nop     dword ptr [rax+rax+00h]
0x14009bfe4  mov     [r14], ebx
0x14009bfe7  xor     eax, eax
0x14009bfe9  jmp     short loc_14009C02C
0x14009bfeb  mov     eax, 0C0000023h
0x14009bff0  jmp     short loc_14009C02C
0x14009bff2  mov     ebx, 0Dh
0x14009bff7  jmp     short loc_14009C005
0x14009bff9  mov     ebx, 0Ch
0x14009bffe  jmp     short loc_14009C005
0x14009c000  mov     ebx, 0Bh
0x14009c005  mov     [rsp+0A8h+var_80], r14
0x14009c00a  mov     eax, [rsp+0A8h+arg_20]
0x14009c011  mov     [rsp+0A8h+var_88], eax
0x14009c015  mov     r9, rsi
0x14009c018  mov     r8d, r12d
0x14009c01b  mov     rdx, r13
0x14009c01e  mov     ecx, ebx
0x14009c020  call    cs:__imp_WinHvGetSystemInformation
0x14009c027  nop     dword ptr [rax+rax+00h]
0x14009c02c  mov     rcx, [rsp+0A8h+var_40]
0x14009c031  xor     rcx, rsp; StackCookie
0x14009c034  call    __security_check_cookie
0x14009c039  add     rsp, 70h
0x14009c03d  pop     r15
0x14009c03f  pop     r14
0x14009c041  pop     r13
0x14009c043  pop     r12
0x14009c045  pop     rdi
0x14009c046  pop     rsi
0x14009c047  pop     rbx
0x14009c048  retn
```
