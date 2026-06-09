# BampProcessWindowReportApply

- ea: `0x14001202c`
- end: `0x14001235f`
- name: `BampProcessWindowReportApply`
- size: `819`
- prototype: `__int64 __fastcall(unsigned int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140011ee0`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x1400102d4`
- `0x140010684`
- `0x140010760`
- `0x1400107a0`
- `0x1400107f0`
- `0x1400114e4`
- `0x14001202c`
- `0x1400153a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400122a9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001231c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400122a9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001231c`
- `ntoskrnl!PsProcessType` at `0x14001213c`
- `ntoskrnl!PsGetProcessSessionId` at `0x140012111`
- `ntoskrnl!PsGetProcessSessionId` at `0x140012124`
- `ntoskrnl!PsGetProcessSessionId` at `0x140012111`
- `ntoskrnl!PsGetProcessSessionId` at `0x140012124`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400120fa`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400120fa`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14001216a`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14001216a`

## pseudocode

```c
__int64 __fastcall BampProcessWindowReportApply(unsigned int *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r15d
  KPROCESSOR_MODE v6; // r12
  int ProcessSessionId; // ebx
  _QWORD *ThrottledProcessInformation; // rdi
  __int64 v9; // rax
  int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int *v15; // [rsp+40h] [rbp-C0h] BYREF
  PEPROCESS Process; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v19; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v22; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+98h] [rbp-68h]
  int *v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  _BYTE v26[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int **v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  int *v29; // [rsp+E0h] [rbp-20h]
  __int64 v30; // [rsp+E8h] [rbp-18h]
  int *v31; // [rsp+F0h] [rbp-10h]
  __int64 v32; // [rsp+F8h] [rbp-8h]

  Process = 0;
  if ( (unsigned int)dword_140007010 > 4 )
  {
    v25 = 4;
    v22 = v20;
    v17 = *(_DWORD *)(a3 + 464);
    v20[0] = a1;
    v24 = &v17;
    v23 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140007010, &byte_140004BCF, 0, 0, 4, v21);
  }
  v5 = 0;
  v6 = *((_BYTE *)KeGetCurrentThread() + 562);
  while ( v5 < *a1 )
  {
    if ( a1[4 * v5 + 4] == 5 )
    {
      if ( PsLookupProcessByProcessId((HANDLE)a1[4 * v5 + 2], &Process) >= 0 )
      {
        ProcessSessionId = PsGetProcessSessionId(a3);
        if ( (unsigned int)PsGetProcessSessionId(Process) == ProcessSessionId )
        {
LABEL_9:
          BampAcquireThrottlingLockShared();
          ThrottledProcessInformation = (_QWORD *)BampFindThrottledProcessInformation(Process);
          BampReleaseThrottlingLockShared();
          if ( ThrottledProcessInformation )
          {
            if ( (unsigned int)dword_140007010 > 4 )
            {
              v15 = a1;
              v27 = &v15;
              v9 = ThrottledProcessInformation[1];
              v28 = 8;
              v10 = *(_DWORD *)(v9 + 464);
              v29 = &v18;
              v19 = a1[4 * v5 + 4];
              v31 = (int *)&v19;
              v18 = v10;
              v30 = 4;
              v32 = 4;
              tlgWriteTransfer_EtwWriteTransfer(&dword_140007010, &unk_140004B90, 0, 0, 5, v26);
            }
            v11 = a1[4 * v5 + 4];
            LODWORD(v15) = 0;
            if ( v11 )
            {
              LODWORD(v15) = 1;
              v12 = v11 - 2;
              if ( v12 )
              {
                v13 = v12 - 1;
                if ( v13 )
                {
                  if ( v13 - 1 <= 1 )
                    LODWORD(v15) = 7;
                }
                else
                {
                  LODWORD(v15) = 5;
                }
              }
              else
              {
                LODWORD(v15) = 9;
              }
            }
            BampAcquireThrottledProcessLock(ThrottledProcessInformation);
            BampUpdateThrottledProcessState((__int64)ThrottledProcessInformation, &v15, 0, 0, 0);
            BampReleaseThrottledProcessLock(ThrottledProcessInformation);
            BampDereferenceThrottledProcessInformation(ThrottledProcessInformation);
          }
        }
      }
    }
    else if ( ObReferenceObjectByHandleWithTag(
                *(HANDLE *)&a1[4 * v5 + 2],
                0x2000u,
                (POBJECT_TYPE)PsProcessType,
                v6,
                0x4B6D6142u,
                (PVOID *)&Process,
                0) >= 0 )
    {
      goto LABEL_9;
    }
    if ( Process )
    {
      ObfDereferenceObject(Process);
      Process = 0;
    }
    ++v5;
  }
  if ( (unsigned int)dword_140007010 > 4 )
  {
    v20[0] = a1;
    v22 = v20;
    v23 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140007010, &dword_140004B64, 0, 0, 3, v21);
  }
  if ( Process )
    ObfDereferenceObject(Process);
  return 0;
}

```

## disassembly

```asm
0x14001202c  mov     [rsp-8+arg_8], rbx
0x140012031  push    rbp
0x140012032  push    rsi
0x140012033  push    rdi
0x140012034  push    r12
0x140012036  push    r13
0x140012038  push    r14
0x14001203a  push    r15
0x14001203c  lea     rbp, [rsp-10h]
0x140012041  sub     rsp, 110h
0x140012048  mov     rax, cs:__security_cookie
0x14001204f  xor     rax, rsp
0x140012052  mov     [rbp+40h+var_40], rax
0x140012056  mov     eax, cs:dword_140007010
0x14001205c  xor     ebx, ebx
0x14001205e  mov     rsi, rcx
0x140012061  mov     [rsp+140h+Process], rbx
0x140012066  mov     r13, r8
0x140012069  mov     edi, ebx
0x14001206b  lea     ecx, [rbx+4]
0x14001206e  cmp     eax, ecx
0x140012070  jbe     short loc_1400120C7
0x140012072  lea     rax, [rsp+140h+var_E0]
0x140012077  mov     [rbp+40h+var_98], rcx
0x14001207b  mov     [rbp+40h+var_B0], rax
0x14001207f  lea     rdx, byte_140004BCF
0x140012086  mov     eax, [r8+1D0h]
0x14001208d  xor     r9d, r9d
0x140012090  mov     [rsp+140h+var_F0], eax
0x140012094  xor     r8d, r8d
0x140012097  lea     rax, [rsp+140h+var_F0]
0x14001209c  mov     [rsp+140h+var_E0], rsi
0x1400120a1  mov     [rbp+40h+var_A0], rax
0x1400120a5  lea     rax, [rsp+140h+var_D0]
0x1400120aa  mov     [rsp+140h+Object], rax
0x1400120af  mov     [rsp+140h+Tag], ecx
0x1400120b3  lea     rcx, dword_140007010
0x1400120ba  mov     [rbp+40h+var_A8], 8
0x1400120c2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400120c7  mov     rax, gs:188h
0x1400120d0  mov     r15d, ebx
0x1400120d3  mov     r12b, [rax+232h]
0x1400120da  cmp     [rsi], ebx
0x1400120dc  jbe     loc_1400122C6
0x1400120e2  mov     r14d, r15d
0x1400120e5  add     r14, r14
0x1400120e8  cmp     dword ptr [rsi+r14*8+10h], 5
0x1400120ee  jnz     short loc_14001213C
0x1400120f0  mov     ecx, [rsi+r14*8+8]; ProcessId
0x1400120f5  lea     rdx, [rsp+140h+Process]; Process
0x1400120fa  call    cs:__imp_PsLookupProcessByProcessId
0x140012101  nop     dword ptr [rax+rax+00h]
0x140012106  test    eax, eax
0x140012108  js      loc_14001228F
0x14001210e  mov     rcx, r13
0x140012111  call    cs:__imp_PsGetProcessSessionId
0x140012118  nop     dword ptr [rax+rax+00h]
0x14001211d  mov     rcx, [rsp+140h+Process]
0x140012122  mov     ebx, eax
0x140012124  call    cs:__imp_PsGetProcessSessionId
0x14001212b  nop     dword ptr [rax+rax+00h]
0x140012130  cmp     eax, ebx
0x140012132  jnz     loc_14001228D
0x140012138  xor     ebx, ebx
0x14001213a  jmp     short loc_14001217E
0x14001213c  mov     r8, cs:__imp_PsProcessType
0x140012143  lea     rax, [rsp+140h+Process]
0x140012148  mov     rcx, [rsi+r14*8+8]; Handle
0x14001214d  mov     r9b, r12b; AccessMode
0x140012150  mov     [rsp+140h+HandleInformation], rbx; HandleInformation
0x140012155  mov     edx, 2000h; DesiredAccess
0x14001215a  mov     [rsp+140h+Object], rax; Object
0x14001215f  mov     r8, [r8]; ObjectType
0x140012162  mov     [rsp+140h+Tag], 4B6D6142h; Tag
0x14001216a  call    cs:__imp_ObReferenceObjectByHandleWithTag
0x140012171  nop     dword ptr [rax+rax+00h]
0x140012176  test    eax, eax
0x140012178  js      loc_14001228F
0x14001217e  call    BampAcquireThrottlingLockShared
0x140012183  mov     rcx, [rsp+140h+Process]
0x140012188  call    BampFindThrottledProcessInformation
0x14001218d  mov     rdi, rax
0x140012190  call    BampReleaseThrottlingLockShared
0x140012195  test    rdi, rdi
0x140012198  jz      loc_14001229F
0x14001219e  mov     ecx, cs:dword_140007010
0x1400121a4  mov     edx, 4
0x1400121a9  cmp     ecx, edx
0x1400121ab  jbe     short loc_14001221E
0x1400121ad  lea     rax, [rsp+140h+var_100]
0x1400121b2  mov     [rsp+140h+var_100], rsi
0x1400121b7  mov     [rbp+40h+var_70], rax
0x1400121bb  xor     r9d, r9d
0x1400121be  mov     rax, [rdi+8]
0x1400121c2  xor     r8d, r8d
0x1400121c5  mov     [rbp+40h+var_68], 8
0x1400121cd  mov     ecx, [rax+1D0h]
0x1400121d3  lea     rax, [rsp+140h+var_EC]
0x1400121d8  mov     [rbp+40h+var_60], rax
0x1400121dc  mov     eax, [rsi+r14*8+10h]
0x1400121e1  mov     [rsp+140h+var_E8], eax
0x1400121e5  lea     rax, [rsp+140h+var_E8]
0x1400121ea  mov     [rbp+40h+var_50], rax
0x1400121ee  lea     rax, [rbp+40h+var_90]
0x1400121f2  mov     [rsp+140h+var_EC], ecx
0x1400121f6  lea     rcx, dword_140007010
0x1400121fd  mov     [rbp+40h+var_58], rdx
0x140012201  mov     [rbp+40h+var_48], rdx
0x140012205  lea     rdx, unk_140004B90
0x14001220c  mov     [rsp+140h+Object], rax
0x140012211  mov     [rsp+140h+Tag], 5
0x140012219  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001221e  mov     ecx, [rsi+r14*8+10h]
0x140012223  mov     dword ptr [rsp+140h+var_100], ebx
0x140012227  test    ecx, ecx
0x140012229  jz      short loc_140012263
0x14001222b  mov     dword ptr [rsp+140h+var_100], 1
0x140012233  sub     ecx, 2
0x140012236  jz      short loc_14001225B
0x140012238  sub     ecx, 1
0x14001223b  jz      short loc_140012251
0x14001223d  sub     ecx, 1
0x140012240  jz      short loc_140012247
0x140012242  cmp     ecx, 1
0x140012245  jnz     short loc_140012263
0x140012247  mov     dword ptr [rsp+140h+var_100], 7
0x14001224f  jmp     short loc_140012263
0x140012251  mov     dword ptr [rsp+140h+var_100], 5
0x140012259  jmp     short loc_140012263
0x14001225b  mov     dword ptr [rsp+140h+var_100], 9
0x140012263  mov     rcx, rdi
0x140012266  call    BampAcquireThrottledProcessLock
0x14001226b  xor     r9d, r9d
0x14001226e  mov     qword ptr [rsp+140h+Tag], rbx
0x140012273  xor     r8d, r8d
0x140012276  lea     rdx, [rsp+140h+var_100]
0x14001227b  mov     rcx, rdi
0x14001227e  call    BampUpdateThrottledProcessState
0x140012283  mov     rcx, rdi
0x140012286  call    BampReleaseThrottledProcessLock
0x14001228b  jmp     short loc_140012294
0x14001228d  xor     ebx, ebx
0x14001228f  test    rdi, rdi
0x140012292  jz      short loc_14001229F
0x140012294  mov     rcx, rdi; P
0x140012297  call    BampDereferenceThrottledProcessInformation
0x14001229c  mov     rdi, rbx
0x14001229f  mov     rcx, [rsp+140h+Process]; Object
0x1400122a4  test    rcx, rcx
0x1400122a7  jz      short loc_1400122BA
0x1400122a9  call    cs:__imp_ObfDereferenceObject
0x1400122b0  nop     dword ptr [rax+rax+00h]
0x1400122b5  mov     [rsp+140h+Process], rbx
0x1400122ba  inc     r15d
0x1400122bd  cmp     r15d, [rsi]
0x1400122c0  jb      loc_1400120E2
0x1400122c6  mov     eax, cs:dword_140007010
0x1400122cc  cmp     eax, 4
0x1400122cf  jbe     short loc_140012312
0x1400122d1  lea     rax, [rsp+140h+var_E0]
0x1400122d6  mov     [rsp+140h+var_E0], rsi
0x1400122db  mov     [rbp+40h+var_B0], rax
0x1400122df  lea     rdx, dword_140004B64
0x1400122e6  lea     rax, [rsp+140h+var_D0]
0x1400122eb  mov     [rbp+40h+var_A8], 8
0x1400122f3  mov     [rsp+140h+Object], rax
0x1400122f8  lea     rcx, dword_140007010
0x1400122ff  xor     r9d, r9d
0x140012302  mov     [rsp+140h+Tag], 3
0x14001230a  xor     r8d, r8d
0x14001230d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012312  mov     rcx, [rsp+140h+Process]; Object
0x140012317  test    rcx, rcx
0x14001231a  jz      short loc_140012328
0x14001231c  call    cs:__imp_ObfDereferenceObject
0x140012323  nop     dword ptr [rax+rax+00h]
0x140012328  test    rdi, rdi
0x14001232b  jz      short loc_140012335
0x14001232d  mov     rcx, rdi; P
0x140012330  call    BampDereferenceThrottledProcessInformation
0x140012335  xor     eax, eax
0x140012337  mov     rcx, [rbp+40h+var_40]
0x14001233b  xor     rcx, rsp; StackCookie
0x14001233e  call    __security_check_cookie
0x140012343  mov     rbx, [rsp+140h+arg_8]
0x14001234b  add     rsp, 110h
0x140012352  pop     r15
0x140012354  pop     r14
0x140012356  pop     r13
0x140012358  pop     r12
0x14001235a  pop     rdi
0x14001235b  pop     rsi
0x14001235c  pop     rbp
0x14001235d  retn
```
