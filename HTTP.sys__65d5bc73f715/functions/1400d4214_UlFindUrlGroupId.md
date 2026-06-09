# UlFindUrlGroupId

- ea: `0x1400d4214`
- end: `0x1400d44d9`
- name: `UlFindUrlGroupId`
- size: `709`
- prototype: `__int64 __fastcall(__int64, __int64, void *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400cbc50`
- `0x1400efd30`

## callees

- `0x14000a350`
- `0x1400272c8`
- `0x14009620c`
- `0x1400a1f50`
- `0x1400a4770`
- `0x1400d4214`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c8bcc`
- `0x1401c8d4c`
- `0x1401c9134`
- `0x1401c91f8`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d42fb`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d42fb`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d43ea`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d43ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d43f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d43f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4441`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4441`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d42e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d42e6`

## pseudocode

```c
__int64 __fastcall UlFindUrlGroupId(__int64 a1, __int64 a2, void *a3, _QWORD *a4, _QWORD *a5)
{
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  _QWORD *v12; // r12
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // ebx
  __int64 v16; // rdi
  int RegistrationNode; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  PVOID v22; // rcx
  ULONG_PTR v23; // rdx
  int v24; // eax
  ULONG_PTR BugCheckParameter2; // [rsp+40h] [rbp-71h] BYREF
  __int64 v27; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v28[144]; // [rsp+50h] [rbp-61h] BYREF
  PVOID P; // [rsp+128h] [rbp+77h] BYREF

  BugCheckParameter2 = 0;
  P = 0;
  memset(v28, 0, 0x88u);
  v27 = 0;
  v12 = a5;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qSqqq(v10, v9, v11, a1, *(_QWORD *)(a2 + 8), (char)a3, (char)a4, (char)a5);
  *a4 = 0;
  v13 = UlReferenceRequestQueueByHandle(a3, v9, 1u, 15, &BugCheckParameter2);
  v15 = v13;
  if ( v13 < 0 )
  {
    if ( (xmmword_1401A2C90 & 0x10) == 0 )
      goto LABEL_23;
    v21 = 131;
    goto LABEL_22;
  }
  LOBYTE(v14) = 1;
  v13 = UlSanitizeUrl(a1, *(_QWORD *)(a2 + 8), v14, (unsigned int)&P, (__int64)v28);
  v15 = v13;
  if ( v13 < 0 )
  {
    if ( (xmmword_1401A2C90 & 0x10) == 0 )
      goto LABEL_23;
    v21 = 132;
LABEL_22:
    WPP_SF_d(516, v21, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (unsigned int)v13);
    goto LABEL_23;
  }
  KeEnterCriticalRegion();
  v16 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 1368), 0);
  RegistrationNode = UlpTreeFindRegistrationNode(a1, P, &v27);
  v15 = RegistrationNode;
  if ( RegistrationNode < 0 )
  {
    if ( (xmmword_1401A2C90 & 0x10) != 0 )
      WPP_SF_Sd(516, 133, (unsigned int)WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, (_DWORD)P, RegistrationNode);
  }
  else
  {
    v19 = v27;
    v20 = *(_QWORD *)(v27 + 88);
    if ( (*(_DWORD *)(v20 + 64) & 1) != 0 && *(_QWORD *)(v20 + 72) == BugCheckParameter2 )
    {
      *a4 = *(_QWORD *)(v20 + 8);
      *v12 = *(_QWORD *)(v19 + 80);
      v27 = 0;
    }
    else
    {
      if ( UxKirHttpBugFix25Q1 )
      {
        if ( (xmmword_1401A2C90 & 0x10) != 0 )
          WPP_SF_qiDqq(v18, *(_DWORD *)(v20 + 64) & 1, v27, v20);
      }
      else if ( (xmmword_1401A2C90 & 0x10) != 0 )
      {
        WPP_SF_qq(516, 135, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids, v20, *(_QWORD *)(v20 + 8));
      }
      v15 = -1073741790;
    }
  }
  ExReleaseCacheAwarePushLockSharedEx(v16, 0);
  KeLeaveCriticalRegion();
LABEL_23:
  v22 = P;
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  v23 = BugCheckParameter2;
  if ( BugCheckParameter2 )
  {
    v24 = _InterlockedDecrement((volatile signed __int32 *)BugCheckParameter2);
    if ( UxDebugCheckRefcount && v24 <= -1 )
      UlBugCheckEx(3u, v23, 0xAu, v24);
    if ( !v24 )
      UlFreeRequestQueue((PVOID)BugCheckParameter2);
    BugCheckParameter2 = 0;
  }
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_iId(v22, v23, v14, *a4, *v12, v15);
  return v15;
}

```

## disassembly

```asm
0x1400d4214  mov     [rsp-8+arg_0], rbx
0x1400d4219  mov     [rsp-8+arg_8], rsi
0x1400d421e  push    rbp
0x1400d421f  push    rdi
0x1400d4220  push    r12
0x1400d4222  push    r14
0x1400d4224  push    r15
0x1400d4226  lea     rbp, [rsp-2Fh]
0x1400d422b  sub     rsp, 0E0h
0x1400d4232  mov     r14, r8
0x1400d4235  mov     [rbp+4Fh+BugCheckParameter2], 0
0x1400d423d  mov     rdi, rdx
0x1400d4240  mov     [rbp+4Fh+P], 0
0x1400d4248  mov     rsi, rcx
0x1400d424b  xor     edx, edx; Val
0x1400d424d  mov     r8d, 88h; Size
0x1400d4253  lea     rcx, [rbp+4Fh+var_B0]; void *
0x1400d4257  mov     r15, r9
0x1400d425a  call    memset
0x1400d425f  mov     [rbp+4Fh+var_B8], 0
0x1400d4267  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d426e  mov     r12, [rbp+4Fh+arg_20]
0x1400d4272  jz      short loc_1400D4294
0x1400d4274  mov     rax, [rdi+8]
0x1400d4278  mov     r9, rsi
0x1400d427b  mov     [rsp+100h+var_C8], r12
0x1400d4280  mov     [rsp+100h+var_D0], r15
0x1400d4285  mov     [rsp+100h+var_D8], r14
0x1400d428a  mov     [rsp+100h+var_E0], rax
0x1400d428f  call    WPP_SF_qSqqq
0x1400d4294  mov     r9d, 0Fh
0x1400d429a  mov     qword ptr [r15], 0
0x1400d42a1  lea     rax, [rbp+4Fh+BugCheckParameter2]
0x1400d42a5  mov     rcx, r14; Handle
0x1400d42a8  mov     [rsp+100h+var_E0], rax; PVOID
0x1400d42ad  lea     r8d, [r9-0Eh]
0x1400d42b1  call    UlReferenceRequestQueueByHandle
0x1400d42b6  mov     ebx, eax
0x1400d42b8  test    eax, eax
0x1400d42ba  js      loc_1400D4414
0x1400d42c0  mov     rdx, [rdi+8]
0x1400d42c4  lea     rax, [rbp+4Fh+var_B0]
0x1400d42c8  lea     r9, [rbp+4Fh+P]
0x1400d42cc  mov     [rsp+100h+var_E0], rax
0x1400d42d1  mov     r8b, 1
0x1400d42d4  mov     rcx, rsi
0x1400d42d7  call    UlSanitizeUrl
0x1400d42dc  mov     ebx, eax
0x1400d42de  test    eax, eax
0x1400d42e0  js      loc_1400D4404
0x1400d42e6  call    cs:__imp_KeEnterCriticalRegion
0x1400d42ed  nop     dword ptr [rax+rax+00h]
0x1400d42f2  mov     rcx, [rsi+558h]
0x1400d42f9  xor     edx, edx
0x1400d42fb  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d4302  nop     dword ptr [rax+rax+00h]
0x1400d4307  mov     rdx, [rbp+4Fh+P]
0x1400d430b  lea     r8, [rbp+4Fh+var_B8]
0x1400d430f  mov     rcx, rsi
0x1400d4312  mov     rdi, rax
0x1400d4315  call    UlpTreeFindRegistrationNode
0x1400d431a  mov     ebx, eax
0x1400d431c  test    eax, eax
0x1400d431e  js      loc_1400D43BE
0x1400d4324  mov     r8, [rbp+4Fh+var_B8]
0x1400d4328  mov     r10, [rbp+4Fh+BugCheckParameter2]
0x1400d432c  mov     r9, [r8+58h]
0x1400d4330  mov     edx, [r9+40h]
0x1400d4334  and     edx, 1
0x1400d4337  jz      short loc_1400D435B
0x1400d4339  cmp     [r9+48h], r10
0x1400d433d  jnz     short loc_1400D435B
0x1400d433f  mov     rax, [r9+8]
0x1400d4343  mov     [r15], rax
0x1400d4346  mov     rax, [r8+50h]
0x1400d434a  mov     [r12], rax
0x1400d434e  mov     [rbp+4Fh+var_B8], 0
0x1400d4356  jmp     loc_1400D43E5
0x1400d435b  cmp     cs:UxKirHttpBugFix25Q1, 0
0x1400d4362  jz      short loc_1400D438F
0x1400d4364  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d436b  jz      short loc_1400D43B7
0x1400d436d  mov     rax, [r9+48h]
0x1400d4371  mov     [rsp+100h+var_C8], r10
0x1400d4376  mov     [rsp+100h+var_D0], rax
0x1400d437b  mov     rax, [r9+8]
0x1400d437f  mov     dword ptr [rsp+100h+var_D8], edx
0x1400d4383  mov     [rsp+100h+var_E0], rax
0x1400d4388  call    WPP_SF_qiDqq
0x1400d438d  jmp     short loc_1400D43B7
0x1400d438f  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d4396  jz      short loc_1400D43B7
0x1400d4398  mov     rax, [r9+8]
0x1400d439c  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d43a3  mov     edx, 87h
0x1400d43a8  mov     [rsp+100h+var_E0], rax
0x1400d43ad  mov     ecx, 204h
0x1400d43b2  call    WPP_SF_qq
0x1400d43b7  mov     ebx, 0C0000022h
0x1400d43bc  jmp     short loc_1400D43E5
0x1400d43be  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d43c5  jz      short loc_1400D43E5
0x1400d43c7  mov     r9, [rbp+4Fh+P]
0x1400d43cb  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d43d2  mov     edx, 85h
0x1400d43d7  mov     dword ptr [rsp+100h+var_E0], eax
0x1400d43db  mov     ecx, 204h
0x1400d43e0  call    WPP_SF_Sd
0x1400d43e5  xor     edx, edx
0x1400d43e7  mov     rcx, rdi
0x1400d43ea  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d43f1  nop     dword ptr [rax+rax+00h]
0x1400d43f6  call    cs:__imp_KeLeaveCriticalRegion
0x1400d43fd  nop     dword ptr [rax+rax+00h]
0x1400d4402  jmp     short loc_1400D4436
0x1400d4404  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d440b  jz      short loc_1400D4436
0x1400d440d  mov     edx, 84h
0x1400d4412  jmp     short loc_1400D4422
0x1400d4414  test    byte ptr cs:xmmword_1401A2C90, 10h
0x1400d441b  jz      short loc_1400D4436
0x1400d441d  mov     edx, 83h
0x1400d4422  mov     r9d, eax
0x1400d4425  lea     r8, WPP_1afab14d2023349dcdd3f873f7453800_Traceguids
0x1400d442c  mov     ecx, 204h
0x1400d4431  call    WPP_SF_d
0x1400d4436  mov     rcx, [rbp+4Fh+P]; P
0x1400d443a  test    rcx, rcx
0x1400d443d  jz      short loc_1400D4455
0x1400d443f  xor     edx, edx; Tag
0x1400d4441  call    cs:__imp_ExFreePoolWithTag
0x1400d4448  nop     dword ptr [rax+rax+00h]
0x1400d444d  mov     [rbp+4Fh+P], 0
0x1400d4455  mov     rdx, [rbp+4Fh+BugCheckParameter2]; BugCheckParameter2
0x1400d4459  test    rdx, rdx
0x1400d445c  jz      short loc_1400D449C
0x1400d445e  or      eax, 0FFFFFFFFh
0x1400d4461  lock xadd [rdx], eax
0x1400d4465  dec     eax
0x1400d4467  cmp     cs:UxDebugCheckRefcount, 0
0x1400d446e  jz      short loc_1400D4487
0x1400d4470  cmp     eax, 0FFFFFFFFh
0x1400d4473  jg      short loc_1400D4487
0x1400d4475  mov     ecx, 3; BugCheckParameter1
0x1400d447a  movsxd  r9, eax; BugCheckParameter4
0x1400d447d  lea     r8d, [rcx+7]; BugCheckParameter3
0x1400d4481  call    UlBugCheckEx
0x1400d4487  test    eax, eax
0x1400d4489  jnz     short loc_1400D4494
0x1400d448b  mov     rcx, [rbp+4Fh+BugCheckParameter2]; P
0x1400d448f  call    UlFreeRequestQueue
0x1400d4494  mov     [rbp+4Fh+BugCheckParameter2], 0
0x1400d449c  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x1400d44a3  jz      short loc_1400D44BA
0x1400d44a5  mov     rax, [r12]
0x1400d44a9  mov     r9, [r15]
0x1400d44ac  mov     dword ptr [rsp+100h+var_D8], ebx
0x1400d44b0  mov     [rsp+100h+var_E0], rax
0x1400d44b5  call    WPP_SF_iId
0x1400d44ba  lea     r11, [rsp+100h+var_20]
0x1400d44c2  mov     eax, ebx
0x1400d44c4  mov     rbx, [r11+30h]
0x1400d44c8  mov     rsi, [r11+38h]
0x1400d44cc  mov     rsp, r11
0x1400d44cf  pop     r15
0x1400d44d1  pop     r14
0x1400d44d3  pop     r12
0x1400d44d5  pop     rdi
0x1400d44d6  pop     rbp
0x1400d44d7  retn
```
