# MpDlpGetProcessContextFromTokenAttribute

- ea: `0x14003a2c0`
- end: `0x14003a565`
- name: `MpDlpGetProcessContextFromTokenAttribute`
- size: `677`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002f9f0`
- `0x14002fe00`
- `0x140039f70`
- `0x14003c990`
- `0x14006e4f4`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x14003a2c0`
- `0x14003a570`

## import_xrefs

- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14003a344`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14003a54a`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14003a344`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14003a54a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14003a37c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14003a37c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a3c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a4b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a3c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a4b0`

## pseudocode

```c
__int64 __fastcall MpDlpGetProcessContextFromTokenAttribute(__int64 a1, __int64 a2)
{
  __int64 PoolWithTag; // rax
  __int64 v6; // rsi
  int ProcessContextByIdAndCreationTime; // edi
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // [rsp+30h] [rbp-28h] BYREF

  v11 = 1024;
  if ( !a1 || !a2 )
    return 3221225485LL;
  PoolWithTag = MpAllocatePoolWithTag(1, 1024, 1885622349);
  v6 = PoolWithTag;
  if ( !PoolWithTag )
  {
    ProcessContextByIdAndCreationTime = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        73,
        WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
        KeGetCurrentThread(),
        -1073741670);
    return (unsigned int)ProcessContextByIdAndCreationTime;
  }
  ProcessContextByIdAndCreationTime = SeQuerySecurityAttributesToken(a1, &String2, 1, PoolWithTag, v11, &v11);
  if ( ProcessContextByIdAndCreationTime >= 0 )
    goto LABEL_31;
  if ( ProcessContextByIdAndCreationTime != -1073741275 )
  {
    if ( ProcessContextByIdAndCreationTime != -1073741789 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          74,
          WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
          KeGetCurrentThread(),
          ProcessContextByIdAndCreationTime);
      }
      goto LABEL_11;
    }
    ExFreePoolWithTag((PVOID)v6, 0x7064504Du);
    v10 = MpAllocatePoolWithTag(1, v11, 1885622349);
    v6 = v10;
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          75,
          WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
          KeGetCurrentThread(),
          -1073741789);
      return (unsigned int)-1073741670;
    }
    ProcessContextByIdAndCreationTime = SeQuerySecurityAttributesToken(a1, &String2, 1, v10, v11, &v11);
    if ( ProcessContextByIdAndCreationTime >= 0 )
    {
LABEL_31:
      if ( *(_DWORD *)(v6 + 4) == 1
        && (v8 = *(_QWORD *)(v6 + 8), *(_DWORD *)(v8 + 24) == 2)
        && RtlEqualUnicodeString((PCUNICODE_STRING)v8, &String2, 0)
        && (v9 = *(_QWORD *)(v6 + 8), *(_WORD *)(v9 + 16) == 2) )
      {
        ProcessContextByIdAndCreationTime = MpGetProcessContextByIdAndCreationTime(
                                              **(_QWORD **)(v9 + 32),
                                              *(_QWORD *)(*(_QWORD *)(v9 + 32) + 8LL),
                                              a2);
      }
      else
      {
        ProcessContextByIdAndCreationTime = -1073741811;
      }
    }
  }
LABEL_11:
  ExFreePoolWithTag((PVOID)v6, 0x7064504Du);
  return (unsigned int)ProcessContextByIdAndCreationTime;
}

```

## disassembly

```asm
0x14003a2c0  push    rbx
0x14003a2c2  push    rbp
0x14003a2c3  push    rdi
0x14003a2c4  sub     rsp, 40h
0x14003a2c8  mov     rax, cs:__security_cookie
0x14003a2cf  xor     rax, rsp
0x14003a2d2  mov     [rsp+58h+var_20], rax
0x14003a2d7  mov     [rsp+58h+var_28], 400h
0x14003a2df  mov     rbp, rdx
0x14003a2e2  mov     rbx, rcx
0x14003a2e5  test    rcx, rcx
0x14003a2e8  jnz     short loc_14003A2F4
0x14003a2ea  mov     eax, 0C000000Dh
0x14003a2ef  jmp     loc_14003A3D3
0x14003a2f4  test    rbp, rbp
0x14003a2f7  jz      short loc_14003A2EA
0x14003a2f9  mov     edx, 400h
0x14003a2fe  mov     [rsp+58h+arg_10], rsi
0x14003a303  mov     ecx, 1
0x14003a308  mov     r8d, 7064504Dh
0x14003a30e  call    MpAllocatePoolWithTag
0x14003a313  mov     rsi, rax
0x14003a316  test    rax, rax
0x14003a319  jz      loc_14003A3E9
0x14003a31f  lea     rax, [rsp+58h+var_28]
0x14003a324  mov     r9, rsi
0x14003a327  mov     [rsp+58h+var_30], rax
0x14003a32c  lea     rdx, String2
0x14003a333  mov     eax, [rsp+58h+var_28]
0x14003a337  mov     r8d, 1
0x14003a33d  mov     rcx, rbx
0x14003a340  mov     [rsp+58h+var_38], eax
0x14003a344  call    cs:__imp_SeQuerySecurityAttributesToken
0x14003a34b  nop     dword ptr [rax+rax+00h]
0x14003a350  mov     edi, eax
0x14003a352  test    eax, eax
0x14003a354  js      loc_14003A437
0x14003a35a  cmp     dword ptr [rsi+4], 1
0x14003a35e  jnz     loc_14003A49E
0x14003a364  mov     rcx, [rsi+8]; String1
0x14003a368  cmp     dword ptr [rcx+18h], 2
0x14003a36c  jnz     loc_14003A49E
0x14003a372  xor     r8d, r8d; CaseInSensitive
0x14003a375  lea     rdx, String2; String2
0x14003a37c  call    cs:__imp_RtlEqualUnicodeString
0x14003a383  nop     dword ptr [rax+rax+00h]
0x14003a388  test    al, al
0x14003a38a  jz      loc_14003A49E
0x14003a390  mov     rcx, [rsi+8]
0x14003a394  mov     eax, 2
0x14003a399  cmp     ax, [rcx+10h]
0x14003a39d  jnz     loc_14003A49E
0x14003a3a3  mov     rcx, [rcx+20h]
0x14003a3a7  mov     r8, rbp
0x14003a3aa  mov     rdx, [rcx+8]
0x14003a3ae  mov     rcx, [rcx]
0x14003a3b1  call    MpGetProcessContextByIdAndCreationTime
0x14003a3b6  mov     edi, eax
0x14003a3b8  mov     edx, 7064504Dh; Tag
0x14003a3bd  mov     rcx, rsi; P
0x14003a3c0  call    cs:__imp_ExFreePoolWithTag
0x14003a3c7  nop     dword ptr [rax+rax+00h]
0x14003a3cc  mov     rsi, [rsp+58h+arg_10]
0x14003a3d1  mov     eax, edi
0x14003a3d3  mov     rcx, [rsp+58h+var_20]
0x14003a3d8  xor     rcx, rsp; StackCookie
0x14003a3db  call    __security_check_cookie
0x14003a3e0  add     rsp, 40h
0x14003a3e4  pop     rdi
0x14003a3e5  pop     rbp
0x14003a3e6  pop     rbx
0x14003a3e7  retn
0x14003a3e9  mov     edi, 0C000009Ah
0x14003a3ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a3f5  lea     rax, WPP_GLOBAL_Control
0x14003a3fc  cmp     rcx, rax
0x14003a3ff  jz      short loc_14003A3CC
0x14003a401  mov     eax, [rcx+2Ch]
0x14003a404  test    al, 1
0x14003a406  jz      short loc_14003A3CC
0x14003a408  mov     r9, gs:188h
0x14003a411  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14003a418  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a41f  mov     edx, 49h ; 'I'
0x14003a424  mov     [rsp+58h+var_38], 0C000009Ah
0x14003a42c  mov     rcx, [rcx+18h]
0x14003a430  call    WPP_SF_qD
0x14003a435  jmp     short loc_14003A3CC
0x14003a437  cmp     edi, 0C0000225h
0x14003a43d  jz      loc_14003A3B8
0x14003a443  cmp     edi, 0C0000023h
0x14003a449  jz      short loc_14003A4A8
0x14003a44b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a452  lea     rax, WPP_GLOBAL_Control
0x14003a459  cmp     rcx, rax
0x14003a45c  jz      loc_14003A3B8
0x14003a462  mov     eax, [rcx+2Ch]
0x14003a465  test    al, 1
0x14003a467  jz      loc_14003A3B8
0x14003a46d  lfence
0x14003a470  mov     r9, gs:188h
0x14003a479  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14003a480  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a487  mov     edx, 4Ah ; 'J'
0x14003a48c  mov     [rsp+58h+var_38], edi
0x14003a490  mov     rcx, [rcx+18h]
0x14003a494  call    WPP_SF_qD
0x14003a499  jmp     loc_14003A3B8
0x14003a49e  mov     edi, 0C000000Dh
0x14003a4a3  jmp     loc_14003A3B8
0x14003a4a8  mov     edx, 7064504Dh; Tag
0x14003a4ad  mov     rcx, rsi; P
0x14003a4b0  call    cs:__imp_ExFreePoolWithTag
0x14003a4b7  nop     dword ptr [rax+rax+00h]
0x14003a4bc  mov     edx, [rsp+58h+var_28]
0x14003a4c0  mov     ecx, 1
0x14003a4c5  mov     r8d, 7064504Dh
0x14003a4cb  call    MpAllocatePoolWithTag
0x14003a4d0  mov     rsi, rax
0x14003a4d3  test    rax, rax
0x14003a4d6  jnz     short loc_14003A525
0x14003a4d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a4df  lea     rax, WPP_GLOBAL_Control
0x14003a4e6  cmp     rcx, rax
0x14003a4e9  jz      short loc_14003A51B
0x14003a4eb  mov     eax, [rcx+2Ch]
0x14003a4ee  test    al, 1
0x14003a4f0  jz      short loc_14003A51B
0x14003a4f2  mov     r9, gs:188h
0x14003a4fb  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14003a502  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a509  mov     edx, 4Bh ; 'K'
0x14003a50e  mov     [rsp+58h+var_38], edi
0x14003a512  mov     rcx, [rcx+18h]
0x14003a516  call    WPP_SF_qD
0x14003a51b  mov     edi, 0C000009Ah
0x14003a520  jmp     loc_14003A3CC
0x14003a525  lea     rax, [rsp+58h+var_28]
0x14003a52a  mov     r9, rsi
0x14003a52d  mov     [rsp+58h+var_30], rax
0x14003a532  lea     rdx, String2
0x14003a539  mov     eax, [rsp+58h+var_28]
0x14003a53d  mov     r8d, 1
0x14003a543  mov     rcx, rbx
0x14003a546  mov     [rsp+58h+var_38], eax
0x14003a54a  call    cs:__imp_SeQuerySecurityAttributesToken
0x14003a551  nop     dword ptr [rax+rax+00h]
0x14003a556  mov     edi, eax
0x14003a558  test    eax, eax
0x14003a55a  js      loc_14003A3B8
0x14003a560  jmp     loc_14003A35A
```
