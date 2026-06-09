# MpSetProcessHardeningExclusion

- ea: `0x140036f50`
- end: `0x140037420`
- name: `MpSetProcessHardeningExclusion`
- size: `1232`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002b000`
- `0x140036780`
- `0x140093bf8`

## callees

- `0x140003d20`
- `0x1400051bc`
- `0x140006110`
- `0x140009bf0`
- `0x14000bb38`
- `0x14000bd2c`
- `0x1400118d0`
- `0x140036f50`
- `0x140037420`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400372b6`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1400372b6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037144`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140037144`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140037058`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140037058`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140037285`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140037285`
- `ntoskrnl!KeBugCheck` at `0x1400372a0`
- `ntoskrnl!KeBugCheck` at `0x1400372a0`
- `ntoskrnl!ObfDereferenceObject` at `0x14003724a`
- `ntoskrnl!ObfDereferenceObject` at `0x14003724a`

## pseudocode

```c
void __fastcall MpSetProcessHardeningExclusion(__int64 a1, __int64 a2, const UNICODE_STRING *a3)
{
  char v3; // r15
  _DWORD *v4; // rdi
  BOOLEAN v5; // si
  unsigned __int8 v8; // r12
  char v9; // r13
  bool v10; // r8
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  struct _LIST_ENTRY *Blink; // r14
  struct _LIST_ENTRY *i; // rbx
  int v16; // ecx
  _DWORD *v17; // rdx
  int *v18; // r9
  int *v19; // r8
  unsigned __int8 v20; // cl
  int v21; // r9d
  int v22; // eax
  int v23; // ecx
  NTSTATUS v24; // ecx
  PVOID Object; // [rsp+40h] [rbp-48h] BYREF

  if ( !a1 )
    return;
  v3 = 1;
  v4 = (_DWORD *)(a1 + 288);
  Object = 0;
  v5 = 0;
  v8 = 1;
  v9 = 1;
  v10 = 0;
  if ( (*(_DWORD *)(a1 + 288) & 1) != 0 )
  {
    v20 = *(_BYTE *)(a1 + 184);
    if ( (v20 & 7) != 0 && (unsigned __int8)((v20 >> 4) - 3) <= 4u )
      v10 = 1;
  }
  if ( (*(_DWORD *)(MpData + 864) & 8) != 0 && v10 )
    goto LABEL_17;
  if ( !a2 )
  {
    v24 = PsLookupProcessByProcessId(*(HANDLE *)(a1 + 24), (PEPROCESS *)&Object);
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
          KeGetCurrentThread(),
          v24);
      }
      goto LABEL_17;
    }
    _InterlockedIncrement64(&ObTotalReferences);
  }
  v11 = *(_DWORD *)(a1 + 240);
  if ( v11 == 17 || v11 == 18 )
  {
    v21 = *(_DWORD *)(a1 + 284);
    if ( (v21 & 4) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_ZDD(
          WPP_GLOBAL_Control->AttachedDevice,
          41,
          (unsigned int)WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
          *(_QWORD *)(a1 + 128),
          v11,
          v21);
      goto LABEL_17;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_ZDD(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        (unsigned int)WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
        *(_QWORD *)(a1 + 128),
        v11,
        v21);
  }
  if ( a3 )
  {
    if ( !a3->Length )
    {
      if ( *(_DWORD *)(a1 + 120) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            42,
            WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
            *(_QWORD *)(a1 + 24));
        v16 = *v4;
        v17 = v4;
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          43,
          WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
          *(_QWORD *)(a1 + 24));
      v5 = 1;
LABEL_30:
      v16 = *v4;
      v19 = v4;
      v18 = v4;
      v17 = v4;
      if ( v5 )
        goto LABEL_31;
LABEL_34:
      *v17 = v16 & 0xFFFFFFC7;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids, a3);
      goto LABEL_32;
    }
    MpCreateProcessHardeningExcludeDataIfNeeded();
    if ( qword_1400269A8[1].SystemResourcesList.Blink
      && qword_1400269A8[1].SystemResourcesList.Blink->Flink != qword_1400269A8[1].SystemResourcesList.Blink )
    {
      Blink = qword_1400269A8[1].SystemResourcesList.Blink;
      for ( i = Blink->Flink; i != Blink; i = i->Flink )
      {
        v5 = RtlPrefixUnicodeString((PCUNICODE_STRING)i[1].Flink, a3, 1u);
        if ( v5 == 1 )
        {
          v3 = (char)i[1].Blink;
          v8 = BYTE1(i[1].Blink);
          v9 = BYTE2(i[1].Blink);
          goto LABEL_17;
        }
      }
      if ( !v5 && qword_1400269A8[1].SystemResourcesList.Blink[1].Flink )
        v5 = RtlEqualUnicodeString(a3, (PCUNICODE_STRING)qword_1400269A8[1].SystemResourcesList.Blink[1].Flink, 1u);
      goto LABEL_30;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qqZ(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v13,
        (unsigned int)KeGetCurrentThread(),
        *(_QWORD *)(a1 + 24),
        (__int64)a3);
  }
LABEL_17:
  v16 = *v4;
  v17 = v4;
  v18 = v4;
  v19 = v4;
LABEL_31:
  v22 = v16 ^ ((unsigned __int8)v16 ^ (unsigned __int8)(8 * v3)) & 8;
  *v19 = v22;
  v23 = v22 ^ ((unsigned __int8)v22 ^ (unsigned __int8)(16 * v8)) & 0x10;
  *v18 = v23;
  *v17 = v23 ^ ((unsigned __int8)v23 ^ (unsigned __int8)(32 * v9)) & 0x20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Zddd(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v17, v8, (_DWORD)a3, v3, v8, v9);
LABEL_32:
  if ( Object )
  {
    ObfDereferenceObject(Object);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x140036f50  test    rcx, rcx
0x140036f53  jz      locret_1400371EF
0x140036f59  push    rbx
0x140036f5a  push    rbp
0x140036f5b  push    rsi
0x140036f5c  push    r12
0x140036f5e  push    r13
0x140036f60  push    r15
0x140036f62  sub     rsp, 58h
0x140036f66  mov     rax, cs:__security_cookie
0x140036f6d  xor     rax, rsp
0x140036f70  mov     [rsp+88h+var_40], rax
0x140036f75  mov     r15b, 1
0x140036f78  mov     [rsp+88h+arg_8], rdi
0x140036f80  lea     rdi, [rcx+120h]
0x140036f87  mov     [rsp+88h+Object], 0
0x140036f90  mov     eax, [rdi]
0x140036f92  xor     sil, sil
0x140036f95  mov     [rsp+88h+var_38], r14
0x140036f9a  mov     rbp, r8
0x140036f9d  mov     rbx, rcx
0x140036fa0  movzx   r12d, r15b
0x140036fa4  movzx   r13d, r15b
0x140036fa8  test    r15b, al
0x140036fab  jnz     loc_140037090
0x140036fb1  xor     r8b, r8b
0x140036fb4  mov     rax, cs:MpData
0x140036fbb  lea     r14, WPP_GLOBAL_Control
0x140036fc2  mov     ecx, [rax+360h]
0x140036fc8  test    cl, 8
0x140036fcb  jnz     loc_1400370BD
0x140036fd1  test    rdx, rdx
0x140036fd4  jz      loc_1400372AD
0x140036fda  mov     r8d, [rbx+0F0h]
0x140036fe1  cmp     r8d, 11h
0x140036fe5  jz      loc_1400370C8
0x140036feb  cmp     r8d, 12h
0x140036fef  jz      loc_1400370C8
0x140036ff5  test    rbp, rbp
0x140036ff8  jz      loc_140037080
0x140036ffe  cmp     word ptr [rbp+0], 0
0x140037003  jz      loc_140037368
0x140037009  call    MpCreateProcessHardeningExcludeDataIfNeeded
0x14003700e  mov     rax, cs:qword_1400269A8
0x140037015  mov     rcx, [rax+70h]
0x140037019  test    rcx, rcx
0x14003701c  jz      loc_1400373D9
0x140037022  mov     rax, cs:qword_1400269A8
0x140037029  mov     rcx, [rax+70h]
0x14003702d  cmp     [rcx], rcx
0x140037030  jz      loc_1400373D9
0x140037036  mov     rax, cs:qword_1400269A8
0x14003703d  mov     r14, [rax+70h]
0x140037041  mov     rbx, [r14]
0x140037044  cmp     rbx, r14
0x140037047  jz      loc_140037117
0x14003704d  mov     rcx, [rbx+10h]; String1
0x140037051  movzx   r8d, r12b; CaseInSensitive
0x140037055  mov     rdx, rbp; String2
0x140037058  call    cs:__imp_RtlPrefixUnicodeString
0x14003705f  nop     dword ptr [rax+rax+00h]
0x140037064  movzx   esi, al
0x140037067  cmp     al, r12b
0x14003706a  jz      short loc_140037071
0x14003706c  mov     rbx, [rbx]
0x14003706f  jmp     short loc_140037044
0x140037071  movzx   r15d, byte ptr [rbx+18h]
0x140037076  movzx   r12d, byte ptr [rbx+19h]
0x14003707b  movzx   r13d, byte ptr [rbx+1Ah]
0x140037080  mov     ecx, [rdi]
0x140037082  mov     rdx, rdi
0x140037085  mov     r9, rdi
0x140037088  mov     r8, rdi
0x14003708b  jmp     loc_14003716E
0x140037090  movzx   ecx, byte ptr [rcx+0B8h]
0x140037097  movzx   eax, cl
0x14003709a  and     al, 7
0x14003709c  cmp     al, r12b
0x14003709f  jb      loc_140036FB1
0x1400370a5  shr     cl, 4
0x1400370a8  sub     cl, 3
0x1400370ab  cmp     cl, 4
0x1400370ae  ja      loc_140036FB1
0x1400370b4  movzx   r8d, r12b
0x1400370b8  jmp     loc_140036FB4
0x1400370bd  cmp     r8b, r12b
0x1400370c0  jnz     loc_140036FD1
0x1400370c6  jmp     short loc_140037080
0x1400370c8  mov     r9d, [rbx+11Ch]
0x1400370cf  test    r9b, 4
0x1400370d3  jnz     loc_140037322
0x1400370d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400370e0  cmp     rcx, r14
0x1400370e3  jz      short loc_140037080
0x1400370e5  mov     eax, [rcx+2Ch]
0x1400370e8  test    al, 4
0x1400370ea  jz      short loc_140037080
0x1400370ec  mov     rcx, [rcx+18h]
0x1400370f0  mov     edx, 29h ; ')'
0x1400370f5  mov     dword ptr [rsp+88h+var_60], r9d
0x1400370fa  mov     r9, [rbx+80h]
0x140037101  mov     dword ptr [rsp+88h+var_68], r8d
0x140037106  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x14003710d  call    WPP_SF_ZDD
0x140037112  jmp     loc_140037080
0x140037117  test    sil, sil
0x14003711a  jnz     short loc_140037153
0x14003711c  mov     rax, cs:qword_1400269A8
0x140037123  mov     rcx, [rax+70h]
0x140037127  cmp     qword ptr [rcx+10h], 0
0x14003712c  jz      short loc_140037153
0x14003712e  mov     rax, cs:qword_1400269A8
0x140037135  movzx   r8d, r12b; CaseInSensitive
0x140037139  mov     rcx, rbp; String1
0x14003713c  mov     rdx, [rax+70h]
0x140037140  mov     rdx, [rdx+10h]; String2
0x140037144  call    cs:__imp_RtlEqualUnicodeString
0x14003714b  nop     dword ptr [rax+rax+00h]
0x140037150  movzx   esi, al
0x140037153  lea     r14, WPP_GLOBAL_Control
0x14003715a  mov     ecx, [rdi]
0x14003715c  mov     r8, rdi
0x14003715f  mov     r9, rdi
0x140037162  mov     rdx, rdi
0x140037165  test    sil, sil
0x140037168  jz      loc_1400371F1
0x14003716e  movzx   r10d, r15b
0x140037172  lea     eax, ds:0[r10*8]
0x14003717a  xor     eax, ecx
0x14003717c  and     eax, 8
0x14003717f  xor     eax, ecx
0x140037181  mov     [r8], eax
0x140037184  movzx   r8d, r12b
0x140037188  mov     ecx, r8d
0x14003718b  shl     ecx, 4
0x14003718e  xor     ecx, eax
0x140037190  and     ecx, 10h
0x140037193  xor     ecx, eax
0x140037195  mov     [r9], ecx
0x140037198  movzx   r9d, r13b
0x14003719c  mov     eax, r9d
0x14003719f  shl     eax, 5
0x1400371a2  xor     eax, ecx
0x1400371a4  and     eax, 20h
0x1400371a7  xor     eax, ecx
0x1400371a9  mov     [rdx], eax
0x1400371ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371b2  lea     rax, WPP_GLOBAL_Control
0x1400371b9  cmp     rcx, rax
0x1400371bc  jnz     short loc_140037223
0x1400371be  mov     rcx, [rsp+88h+Object]; Object
0x1400371c3  mov     r14, [rsp+88h+var_38]
0x1400371c8  mov     rdi, [rsp+88h+arg_8]
0x1400371d0  test    rcx, rcx
0x1400371d3  jnz     short loc_14003724A
0x1400371d5  mov     rcx, [rsp+88h+var_40]
0x1400371da  xor     rcx, rsp; StackCookie
0x1400371dd  call    __security_check_cookie
0x1400371e2  add     rsp, 58h
0x1400371e6  pop     r15
0x1400371e8  pop     r13
0x1400371ea  pop     r12
0x1400371ec  pop     rsi
0x1400371ed  pop     rbp
0x1400371ee  pop     rbx
0x1400371ef  retn
0x1400371f1  and     ecx, 0FFFFFFC7h
0x1400371f4  mov     [rdx], ecx
0x1400371f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371fd  cmp     rcx, r14
0x140037200  jz      short loc_1400371BE
0x140037202  mov     eax, [rcx+2Ch]
0x140037205  test    al, 4
0x140037207  jz      short loc_1400371BE
0x140037209  mov     rcx, [rcx+18h]
0x14003720d  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x140037214  mov     edx, 2Eh ; '.'
0x140037219  mov     r9, rbp
0x14003721c  call    WPP_SF_Z
0x140037221  jmp     short loc_1400371BE
0x140037223  mov     eax, [rcx+2Ch]
0x140037226  test    al, 4
0x140037228  jz      short loc_1400371BE
0x14003722a  mov     rcx, [rcx+18h]
0x14003722e  mov     [rsp+88h+var_58], r9d
0x140037233  mov     r9, rbp
0x140037236  mov     dword ptr [rsp+88h+var_60], r8d
0x14003723b  mov     dword ptr [rsp+88h+var_68], r10d
0x140037240  call    WPP_SF_Zddd
0x140037245  jmp     loc_1400371BE
0x14003724a  call    cs:__imp_ObfDereferenceObject
0x140037251  nop     dword ptr [rax+rax+00h]
0x140037256  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14003725d  lock xadd cs:ObTotalReferences, rax
0x140037266  cmp     rax, 1
0x14003726a  jns     loc_1400371D5
0x140037270  mov     rax, cs:MpData
0x140037277  mov     ecx, [rax+364h]
0x14003727d  test    ecx, ecx
0x14003727f  jns     loc_1400371D5
0x140037285  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14003728c  nop     dword ptr [rax+rax+00h]
0x140037291  test    al, al
0x140037293  jnz     short loc_14003729B
0x140037295  int     3; Trap to Debugger
0x140037296  jmp     loc_1400371D5
0x14003729b  mov     ecx, 1; BugCheckCode
0x1400372a0  call    cs:__imp_KeBugCheck
0x1400372ad  mov     rcx, [rbx+18h]; ProcessId
0x1400372b1  lea     rdx, [rsp+88h+Object]; Process
0x1400372b6  call    cs:__imp_PsLookupProcessByProcessId
0x1400372bd  nop     dword ptr [rax+rax+00h]
0x1400372c2  mov     ecx, eax
0x1400372c4  test    eax, eax
0x1400372c6  js      short loc_1400372D5
0x1400372c8  lock inc cs:ObTotalReferences
0x1400372d0  jmp     loc_140036FDA
0x1400372d5  mov     rax, cs:WPP_GLOBAL_Control
0x1400372dc  cmp     rax, r14
0x1400372df  jz      loc_140037080
0x1400372e5  mov     eax, [rax+2Ch]
0x1400372e8  test    r12b, al
0x1400372eb  jz      loc_140037080
0x1400372f1  lfence
0x1400372f4  mov     r9, gs:188h
0x1400372fd  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x140037304  mov     dword ptr [rsp+88h+var_68], ecx
0x140037308  mov     edx, 27h ; '''
0x14003730d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037314  mov     rcx, [rcx+18h]
0x140037318  call    WPP_SF_qD
0x14003731d  jmp     loc_140037080
0x140037322  mov     rcx, cs:WPP_GLOBAL_Control
0x140037329  cmp     rcx, r14
0x14003732c  jz      loc_140036FF5
0x140037332  mov     eax, [rcx+2Ch]
0x140037335  test    al, 2
0x140037337  jz      loc_140036FF5
0x14003733d  mov     rcx, [rcx+18h]
0x140037341  mov     edx, 28h ; '('
0x140037346  mov     dword ptr [rsp+88h+var_60], r9d
0x14003734b  mov     r9, [rbx+80h]
0x140037352  mov     dword ptr [rsp+88h+var_68], r8d
0x140037357  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x14003735e  call    WPP_SF_ZDD
0x140037363  jmp     loc_140036FF5
0x140037368  cmp     dword ptr [rbx+78h], 0
0x14003736c  jz      short loc_1400373A4
0x14003736e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037375  cmp     rcx, r14
0x140037378  jz      short loc_14003739A
0x14003737a  mov     eax, [rcx+2Ch]
0x14003737d  test    al, 4
0x14003737f  jz      short loc_14003739A
0x140037381  mov     r9, [rbx+18h]
0x140037385  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x14003738c  mov     rcx, [rcx+18h]
0x140037390  mov     edx, 2Ah ; '*'
0x140037395  call    WPP_SF_q
0x14003739a  mov     ecx, [rdi]
0x14003739c  mov     rdx, rdi
0x14003739f  jmp     loc_1400371F1
0x1400373a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400373ab  cmp     rcx, r14
0x1400373ae  jz      short loc_1400373D0
0x1400373b0  mov     eax, [rcx+2Ch]
0x1400373b3  test    al, 4
0x1400373b5  jz      short loc_1400373D0
0x1400373b7  mov     r9, [rbx+18h]
0x1400373bb  lea     r8, WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids
0x1400373c2  mov     rcx, [rcx+18h]
0x1400373c6  mov     edx, 2Bh ; '+'
0x1400373cb  call    WPP_SF_q
0x1400373d0  movzx   esi, r12b
0x1400373d4  jmp     loc_14003715A
0x1400373d9  mov     rax, cs:WPP_GLOBAL_Control
0x1400373e0  cmp     rax, r14
0x1400373e3  jz      loc_140037080
0x1400373e9  mov     eax, [rax+2Ch]
0x1400373ec  test    al, 4
0x1400373ee  jz      loc_140037080
0x1400373f4  mov     r9, gs:188h
0x1400373fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140037404  mov     rax, [rbx+18h]
0x140037408  mov     [rsp+88h+var_60], rbp
0x14003740d  mov     [rsp+88h+var_68], rax
0x140037412  mov     rcx, [rcx+18h]
0x140037416  call    WPP_SF_qqZ
0x14003741b  jmp     loc_140037080
```
