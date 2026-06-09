# BfGetOrCreateUser

- ea: `0x140012570`
- end: `0x14001279a`
- name: `BfGetOrCreateUser`
- size: `554`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000ff58`
- `0x14001f71c`

## callees

- `0x140003098`
- `0x140012570`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x14001264a`
- `ntoskrnl!RtlValidSid` at `0x14001264a`
- `ntoskrnl!RtlLengthSid` at `0x1400125bf`
- `ntoskrnl!RtlLengthSid` at `0x140012620`
- `ntoskrnl!RtlLengthSid` at `0x1400125bf`
- `ntoskrnl!RtlLengthSid` at `0x140012620`
- `ntoskrnl!RtlCopySid` at `0x14001260b`
- `ntoskrnl!RtlCopySid` at `0x14001260b`
- `ntoskrnl!RtlEqualSid` at `0x140012694`
- `ntoskrnl!RtlEqualSid` at `0x140012694`
- `ntoskrnl!ExGetPreviousMode` at `0x140012596`
- `ntoskrnl!ExGetPreviousMode` at `0x1400261de`
- `ntoskrnl!ExGetPreviousMode` at `0x140012596`
- `ntoskrnl!ExGetPreviousMode` at `0x1400261de`
- `ntoskrnl!ProbeForRead` at `0x1400125b0`
- `ntoskrnl!ProbeForRead` at `0x1400125b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012760`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012779`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012760`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012779`
- `ntoskrnl!ExAllocatePool2` at `0x1400125db`
- `ntoskrnl!ExAllocatePool2` at `0x1400126c2`
- `ntoskrnl!ExAllocatePool2` at `0x1400125db`
- `ntoskrnl!ExAllocatePool2` at `0x1400126c2`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001266b`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001266b`
- `FLTMGR!FltReleaseResource` at `0x140012747`
- `FLTMGR!FltReleaseResource` at `0x140012747`

## pseudocode

```c
__int64 __fastcall BfGetOrCreateUser(PSID SourceSid, __int64 *a2)
{
  _QWORD *v4; // rdi
  char v5; // r12
  __int64 v6; // r14
  void *Pool2; // rax
  void *v8; // rsi
  NTSTATUS v9; // ebx
  __int64 i; // r14
  __int64 v11; // rax
  __int64 v12; // rax

  v4 = 0;
  v5 = 0;
  if ( ExGetPreviousMode() == 1 )
    ProbeForRead(SourceSid, 0xCu, 1u);
  v6 = RtlLengthSid(SourceSid);
  Pool2 = (void *)ExAllocatePool2(256, v6, 1937065538);
  v8 = Pool2;
  if ( Pool2 )
  {
    v9 = RtlCopySid(v6, Pool2, SourceSid);
    if ( RtlLengthSid(v8) == (_DWORD)v6 )
    {
      if ( v9 >= 0 )
      {
        if ( RtlValidSid(v8) )
        {
          FltAcquireResourceExclusive(&Resource);
          v5 = 1;
          for ( i = qword_14000B1D8; (__int64 *)i != &qword_14000B1D8; i = *(_QWORD *)i )
          {
            if ( RtlEqualSid(*(PSID *)(i + 16), v8) )
            {
              *a2 = i;
              goto LABEL_21;
            }
          }
          v11 = ExAllocatePool2(256, 32, 1937065538);
          v4 = (_QWORD *)v11;
          if ( v11 )
          {
            *(_QWORD *)(v11 + 16) = v8;
            v8 = 0;
            v9 = BfInitializeMappingContext(v11 + 24);
            if ( v9 >= 0 )
            {
              v12 = qword_14000B1D8;
              if ( *(__int64 **)(qword_14000B1D8 + 8) != &qword_14000B1D8 )
                __fastfail(3u);
              *v4 = qword_14000B1D8;
              v4[1] = &qword_14000B1D8;
              *(_QWORD *)(v12 + 8) = v4;
              qword_14000B1D8 = (__int64)v4;
              *a2 = (__int64)v4;
              v4 = 0;
            }
          }
          else
          {
            v9 = -1073741670;
          }
        }
        else
        {
          v9 = -1073741811;
        }
      }
    }
    else
    {
      v9 = -1073741811;
    }
  }
  else
  {
    v9 = -1073741670;
  }
LABEL_21:
  if ( v5 )
    FltReleaseResource(&Resource);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x73754642u);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x73754642u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140012570  mov     [rsp+arg_0], rbx
0x140012575  push    rsi
0x140012576  push    rdi
0x140012577  push    r12
0x140012579  push    r13
0x14001257b  push    r14
0x14001257d  sub     rsp, 30h
0x140012581  mov     r13, rdx
0x140012584  mov     rbx, rcx
0x140012587  xor     edi, edi
0x140012589  mov     [rsp+58h+arg_18], rdi
0x14001258e  mov     [rsp+58h+var_30], rdi
0x140012593  xor     r12b, r12b
0x140012596  call    cs:__imp_ExGetPreviousMode
0x14001259d  nop     dword ptr [rax+rax+00h]
0x1400125a2  cmp     al, 1
0x1400125a4  jnz     short loc_1400125BC
0x1400125a6  lea     edx, [rdi+0Ch]; Length
0x1400125a9  lea     r8d, [rdi+1]; Alignment
0x1400125ad  mov     rcx, rbx; Address
0x1400125b0  call    cs:__imp_ProbeForRead
0x1400125b7  nop     dword ptr [rax+rax+00h]
0x1400125bc  mov     rcx, rbx; Sid
0x1400125bf  call    cs:__imp_RtlLengthSid
0x1400125c6  nop     dword ptr [rax+rax+00h]
0x1400125cb  mov     r14d, eax
0x1400125ce  mov     edx, eax
0x1400125d0  mov     ecx, 100h
0x1400125d5  mov     r8d, 73754642h
0x1400125db  call    cs:__imp_ExAllocatePool2
0x1400125e2  nop     dword ptr [rax+rax+00h]
0x1400125e7  mov     rsi, rax
0x1400125ea  mov     [rsp+58h+var_30], rax
0x1400125ef  test    rax, rax
0x1400125f2  jnz     short loc_140012602
0x1400125f4  mov     ebx, 0C000009Ah
0x1400125f9  mov     [rsp+58h+var_38], ebx
0x1400125fd  jmp     loc_14001273B
0x140012602  mov     r8, rbx; SourceSid
0x140012605  mov     rdx, rsi; DestinationSid
0x140012608  mov     ecx, r14d; DestinationSidLength
0x14001260b  call    cs:__imp_RtlCopySid
0x140012612  nop     dword ptr [rax+rax+00h]
0x140012617  mov     ebx, eax
0x140012619  mov     [rsp+58h+var_38], eax
0x14001261d  mov     rcx, rsi; Sid
0x140012620  call    cs:__imp_RtlLengthSid
0x140012627  nop     dword ptr [rax+rax+00h]
0x14001262c  cmp     eax, r14d
0x14001262f  jz      short loc_14001263F
0x140012631  mov     ebx, 0C000000Dh
0x140012636  mov     [rsp+58h+var_38], ebx
0x14001263a  jmp     loc_14001273B
0x14001263f  test    ebx, ebx
0x140012641  js      loc_14001273B
0x140012647  mov     rcx, rsi; Sid
0x14001264a  call    cs:__imp_RtlValidSid
0x140012651  nop     dword ptr [rax+rax+00h]
0x140012656  test    al, al
0x140012658  jnz     short loc_140012664
0x14001265a  mov     ebx, 0C000000Dh
0x14001265f  jmp     loc_14001273B
0x140012664  lea     rcx, Resource; Resource
0x14001266b  call    cs:__imp_FltAcquireResourceExclusive
0x140012672  nop     dword ptr [rax+rax+00h]
0x140012677  mov     r12b, 1
0x14001267a  mov     r14, cs:qword_14000B1D8
0x140012681  lea     rax, qword_14000B1D8
0x140012688  cmp     r14, rax
0x14001268b  jz      short loc_1400126B2
0x14001268d  mov     rdx, rsi; Sid2
0x140012690  mov     rcx, [r14+10h]; Sid1
0x140012694  call    cs:__imp_RtlEqualSid
0x14001269b  nop     dword ptr [rax+rax+00h]
0x1400126a0  test    al, al
0x1400126a2  jnz     short loc_1400126A9
0x1400126a4  mov     r14, [r14]
0x1400126a7  jmp     short loc_140012681
0x1400126a9  mov     [r13+0], r14
0x1400126ad  jmp     loc_14001273B
0x1400126b2  mov     edx, 20h ; ' '
0x1400126b7  mov     ecx, 100h
0x1400126bc  mov     r8d, 73754642h
0x1400126c2  call    cs:__imp_ExAllocatePool2
0x1400126c9  nop     dword ptr [rax+rax+00h]
0x1400126ce  mov     rdi, rax
0x1400126d1  test    rax, rax
0x1400126d4  jnz     short loc_1400126DD
0x1400126d6  mov     ebx, 0C000009Ah
0x1400126db  jmp     short loc_14001273B
0x1400126dd  mov     [rax+10h], rsi
0x1400126e1  xor     esi, esi
0x1400126e3  lea     rcx, [rax+18h]
0x1400126e7  call    BfInitializeMappingContext
0x1400126ec  mov     ebx, eax
0x1400126ee  test    eax, eax
0x1400126f0  js      short loc_14001273B
0x1400126f2  mov     rax, cs:qword_14000B1D8
0x1400126f9  lea     rcx, qword_14000B1D8
0x140012700  cmp     [rax+8], rcx
0x140012704  jz      short loc_14001270B
0x140012706  lea     ecx, [rsi+3]
0x140012709  int     29h; Win8: RtlFailFast(ecx)
0x14001270b  mov     [rdi], rax
0x14001270e  mov     [rdi+8], rcx
0x140012712  mov     [rax+8], rdi
0x140012716  mov     cs:qword_14000B1D8, rdi
0x14001271d  mov     [r13+0], rdi
0x140012721  xor     edi, edi
0x140012723  jmp     short loc_14001273B
0x140012725  mov     ebx, 0C00000E8h
0x14001272a  mov     [rsp+58h+var_38], ebx
0x14001272e  mov     rdi, [rsp+58h+arg_18]
0x140012733  mov     rsi, [rsp+58h+var_30]
0x140012738  mov     r12b, dil
0x14001273b  test    r12b, r12b
0x14001273e  jz      short loc_140012753
0x140012740  lea     rcx, Resource; Resource
0x140012747  call    cs:__imp_FltReleaseResource
0x14001274e  nop     dword ptr [rax+rax+00h]
0x140012753  test    rdi, rdi
0x140012756  jz      short loc_14001276C
0x140012758  mov     edx, 73754642h; Tag
0x14001275d  mov     rcx, rdi; P
0x140012760  call    cs:__imp_ExFreePoolWithTag
0x140012767  nop     dword ptr [rax+rax+00h]
0x14001276c  test    rsi, rsi
0x14001276f  jz      short loc_140012785
0x140012771  mov     edx, 73754642h; Tag
0x140012776  mov     rcx, rsi; P
0x140012779  call    cs:__imp_ExFreePoolWithTag
0x140012780  nop     dword ptr [rax+rax+00h]
0x140012785  mov     eax, ebx
0x140012787  mov     rbx, [rsp+58h+arg_0]
0x14001278c  add     rsp, 30h
0x140012790  pop     r14
0x140012792  pop     r13
0x140012794  pop     r12
0x140012796  pop     rdi
0x140012797  pop     rsi
0x140012798  retn
0x1400261d5  push    rbp
0x1400261d7  sub     rsp, 20h
0x1400261db  mov     rbp, rdx
0x1400261de  call    cs:__imp_ExGetPreviousMode
0x1400261e5  nop     dword ptr [rax+rax+00h]
0x1400261ea  xor     ecx, ecx
0x1400261ec  cmp     al, 1
0x1400261ee  setz    cl
0x1400261f1  mov     eax, ecx
0x1400261f3  add     rsp, 20h
0x1400261f7  pop     rbp
0x1400261f8  retn
```
