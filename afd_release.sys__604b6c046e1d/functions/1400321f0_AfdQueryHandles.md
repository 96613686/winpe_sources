# AfdQueryHandles

- ea: `0x1400321f0`
- end: `0x1400325ac`
- name: `AfdQueryHandles`
- size: `956`
- prototype: `__int64 __fastcall(__int64, __int64, KPROCESSOR_MODE, int *, unsigned int, void *, unsigned int, _QWORD *Src)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x14001c708`
- `0x14001e7e0`
- `0x14002fd5c`
- `0x1400321f0`
- `0x140032778`
- `0x140033bdc`
- `0x1400726d0`
- `0x140092008`
- `0x14009214c`
- `0x14009220c`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x14003244e`
- `ntoskrnl!ObCloseHandle` at `0x140032556`
- `ntoskrnl!ObCloseHandle` at `0x140032578`
- `ntoskrnl!ObCloseHandle` at `0x14003244e`
- `ntoskrnl!ObCloseHandle` at `0x140032556`
- `ntoskrnl!ObCloseHandle` at `0x140032578`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032369`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032403`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032369`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032403`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003227a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400324c2`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003227a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400324c2`
- `ntoskrnl!IoFileObjectType` at `0x14003234d`
- `ntoskrnl!IoFileObjectType` at `0x1400323e3`
- `ntoskrnl!IoIs32bitProcess` at `0x140032227`
- `ntoskrnl!IoIs32bitProcess` at `0x140032227`

## pseudocode

```c
__int64 __fastcall AfdQueryHandles(
        __int64 a1,
        __int64 a2,
        KPROCESSOR_MODE a3,
        int *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7,
        _QWORD *Src)
{
  _QWORD *v10; // r13
  __int64 v11; // rbx
  BOOLEAN v12; // al
  BOOLEAN v13; // r12
  NTSTATUS v15; // r15d
  int ULongFromUser; // r14d
  char v17; // r12
  void *v19; // rcx
  __int64 ConnectionReferenceFromEndpoint; // rbx
  NTSTATUS v21; // r14d
  signed __int64 v22; // rax
  bool v23; // cc
  signed __int64 v24; // rax
  HANDLE Handle[10]; // [rsp+48h] [rbp-50h] BYREF

  *(_OWORD *)Handle = 0;
  v10 = Src;
  *Src = 0;
  v11 = *(_QWORD *)(a1 + 24);
  v12 = IoIs32bitProcess(0);
  v13 = v12;
  LOBYTE(Src) = v12;
  if ( a5 < 4 )
    return 3221225507LL;
  if ( v12 ? a7 < 8 : a7 < 0x10 )
    return 3221225507LL;
  v15 = 0;
  if ( a3 )
  {
    if ( ((unsigned __int8)a4 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    ULongFromUser = RtlReadULongFromUser(a4);
  }
  else
  {
    ULongFromUser = *a4;
  }
  if ( (ULongFromUser & 0xFFFFFFFC) != 0 || !ULongFromUser )
    return 3221225485LL;
  if ( (*(_DWORD *)(v11 + 8) & 0x100) != 0 || (*(_DWORD *)(v11 + 8) & 0x200) != 0 )
  {
    *(__m128i *)Handle = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  }
  else
  {
    v17 = 0;
    *(_OWORD *)Handle = 0;
    if ( *(_WORD *)v11 != 0xAFD1
      && *(_WORD *)v11 != 6909
      && ((*(_BYTE *)(v11 + 5) & 0x10) == 0 || (*(_BYTE *)(v11 + 6) & 1) == 0)
      && (*(_DWORD *)(v11 + 8) & 1) == 0
      && *(_BYTE *)(v11 + 2) != 4 )
    {
      if ( !(unsigned __int8)AfdPreventUnbind(v11) )
        return 3221225860LL;
      v17 = 1;
    }
    if ( (ULongFromUser & 1) != 0 && (unsigned __int8)(*(_BYTE *)(v11 + 2) - 3) <= 1u )
    {
      v19 = *(void **)(v11 + 24);
      if ( v19 )
        v15 = ObOpenObjectByPointer(v19, 0x40u, 0, 0x2000000u, (POBJECT_TYPE)IoFileObjectType, a3, Handle);
    }
    if ( v17 )
      AfdReallowUnbind(v11);
    if ( v15 < 0 )
      return (unsigned int)v15;
    if ( (*(_WORD *)v11 & 0xAFD2) == 0xAFD2 && (ULongFromUser & 2) != 0 && *(_BYTE *)(v11 + 2) == 4 )
    {
      ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v11);
      if ( ConnectionReferenceFromEndpoint )
      {
        v21 = ObOpenObjectByPointer(
                *(PVOID *)(ConnectionReferenceFromEndpoint + 16),
                0x40u,
                0,
                0x2000000u,
                (POBJECT_TYPE)IoFileObjectType,
                a3,
                &Handle[1]);
        v22 = _InterlockedExchangeAdd64(
                (volatile signed __int64 *)(ConnectionReferenceFromEndpoint + 48),
                0xFFFFFFFFFFFFFFFFuLL);
        v23 = v22 <= 1;
        v24 = v22 - 1;
        if ( v23 )
        {
          if ( v24 )
            __fastfail(0xEu);
          AfdCloseConnection(ConnectionReferenceFromEndpoint);
        }
        if ( v21 < 0 )
        {
          if ( Handle[0] )
            ObCloseHandle(Handle[0], a3);
          return (unsigned int)v21;
        }
      }
    }
    v13 = (unsigned __int8)Src;
  }
  if ( v13 )
  {
    Src = (_QWORD *)__PAIR64__((unsigned int)Handle[1], (unsigned int)Handle[0]);
    if ( a3 )
    {
      if ( ((unsigned __int8)a6 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlWriteULong64ToUser(a6, Src);
    }
    else
    {
      RtlCopyVolatileMemory(a6, &Src, 8u);
    }
    *v10 = 8;
  }
  else
  {
    if ( a3 )
      RtlCopyToUser(a6, Handle, 0x10u);
    else
      RtlCopyVolatileMemory(a6, Handle, 0x10u);
    *v10 = 16;
  }
  return 0;
}

```

## disassembly

```asm
0x1400321f0  mov     [rsp+PreviousMode], r8b
0x1400321f5  push    rbx
0x1400321f6  push    rdi
0x1400321f7  push    r12
0x1400321f9  push    r13
0x1400321fb  push    r14
0x1400321fd  push    r15
0x1400321ff  sub     rsp, 68h
0x140032203  mov     r14, r9
0x140032206  mov     dil, r8b
0x140032209  xorps   xmm0, xmm0
0x14003220c  movups  xmmword ptr [rsp+98h+var_50], xmm0
0x140032211  mov     r13, [rsp+98h+Src]
0x140032219  mov     qword ptr [r13+0], 0
0x140032221  mov     rbx, [rcx+18h]
0x140032225  xor     ecx, ecx; Irp
0x140032227  call    cs:__imp_IoIs32bitProcess
0x14003222e  nop     dword ptr [rax+rax+00h]
0x140032233  mov     r12b, al
0x140032236  mov     byte ptr [rsp+98h+Src], al
0x14003223d  cmp     [rsp+98h+arg_20], 4
0x140032245  jb      loc_140032597
0x14003224b  test    al, al
0x14003224d  jz      short loc_140032259
0x14003224f  cmp     [rsp+98h+arg_30], 8
0x140032257  jmp     short loc_140032261
0x140032259  cmp     [rsp+98h+arg_30], 10h
0x140032261  jb      loc_140032597
0x140032267  xor     r15d, r15d
0x14003226a  mov     [rsp+98h+var_58], r15d
0x14003226f  test    dil, dil
0x140032272  jz      short loc_140032299
0x140032274  test    r14b, 3
0x140032278  jz      short loc_140032287
0x14003227a  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140032281  nop     dword ptr [rax+rax+00h]
0x140032286  int     3; Trap to Debugger
0x140032287  test    dil, dil
0x14003228a  jz      short loc_140032299
0x14003228c  mov     rcx, r14
0x14003228f  call    RtlReadULongFromUser
0x140032294  mov     r14d, eax
0x140032297  jmp     short loc_14003229C
0x140032299  mov     r14d, [r14]
0x14003229c  mov     [rsp+98h+var_54], r14d
0x1400322a1  test    r14d, 0FFFFFFFCh
0x1400322a8  jnz     loc_14003258A
0x1400322ae  test    r14d, r14d
0x1400322b1  jz      loc_14003258A
0x1400322b7  mov     eax, [rbx+8]
0x1400322ba  bt      eax, 8
0x1400322be  jb      loc_140032462
0x1400322c4  mov     eax, [rbx+8]
0x1400322c7  bt      eax, 9
0x1400322cb  jb      loc_140032462
0x1400322d1  xor     r12b, r12b
0x1400322d4  xorps   xmm0, xmm0
0x1400322d7  movdqu  xmmword ptr [rsp+98h+var_50], xmm0
0x1400322dd  movzx   eax, word ptr [rbx]
0x1400322e0  mov     ecx, 0AFD1h
0x1400322e5  cmp     ax, cx
0x1400322e8  jz      short loc_140032326
0x1400322ea  mov     ecx, 1AFDh
0x1400322ef  cmp     ax, cx
0x1400322f2  jz      short loc_140032326
0x1400322f4  test    byte ptr [rbx+5], 10h
0x1400322f8  jz      short loc_140032300
0x1400322fa  test    byte ptr [rbx+6], 1
0x1400322fe  jnz     short loc_140032326
0x140032300  mov     eax, [rbx+8]
0x140032303  test    al, 1
0x140032305  jnz     short loc_140032326
0x140032307  cmp     byte ptr [rbx+2], 4
0x14003230b  jz      short loc_140032326
0x14003230d  mov     rcx, rbx
0x140032310  call    AfdPreventUnbind
0x140032315  test    al, al
0x140032317  jnz     short loc_140032323
0x140032319  mov     eax, 0C0000184h
0x14003231e  jmp     loc_14003259C
0x140032323  mov     r12b, 1
0x140032326  test    r14b, 1
0x14003232a  jz      short loc_14003237C
0x14003232c  mov     al, [rbx+2]
0x14003232f  sub     al, 3
0x140032331  cmp     al, 1
0x140032333  ja      short loc_14003237C
0x140032335  mov     rcx, [rbx+18h]; Object
0x140032339  test    rcx, rcx
0x14003233c  jz      short loc_14003237C
0x14003233e  lea     rax, [rsp+98h+var_50]
0x140032343  mov     [rsp+98h+Handle], rax; Handle
0x140032348  mov     [rsp+98h+AccessMode], dil; AccessMode
0x14003234d  mov     rax, cs:__imp_IoFileObjectType
0x140032354  mov     rdx, [rax]
0x140032357  mov     [rsp+98h+ObjectType], rdx; ObjectType
0x14003235c  mov     r9d, 2000000h; DesiredAccess
0x140032362  xor     r8d, r8d; PassedAccessState
0x140032365  lea     edx, [r8+40h]; HandleAttributes
0x140032369  call    cs:__imp_ObOpenObjectByPointer
0x140032370  nop     dword ptr [rax+rax+00h]
0x140032375  mov     r15d, eax
0x140032378  mov     [rsp+98h+var_58], eax
0x14003237c  test    r12b, r12b
0x14003237f  jz      short loc_140032389
0x140032381  mov     rcx, rbx
0x140032384  call    AfdReallowUnbind
0x140032389  test    r15d, r15d
0x14003238c  jns     short loc_140032396
0x14003238e  mov     eax, r15d
0x140032391  jmp     loc_14003259C
0x140032396  movzx   eax, word ptr [rbx]
0x140032399  mov     ecx, 0AFD2h
0x14003239e  and     ax, cx
0x1400323a1  cmp     ax, cx
0x1400323a4  setz    dl
0x1400323a7  test    r14b, 2
0x1400323ab  setnz   al
0x1400323ae  test    al, dl
0x1400323b0  jz      loc_140032472
0x1400323b6  cmp     byte ptr [rbx+2], 4
0x1400323ba  jnz     loc_140032472
0x1400323c0  mov     rcx, rbx
0x1400323c3  call    AfdGetConnectionReferenceFromEndpoint
0x1400323c8  mov     rbx, rax
0x1400323cb  test    rax, rax
0x1400323ce  jz      loc_140032472
0x1400323d4  lea     rax, [rsp+98h+var_50+8]
0x1400323d9  mov     [rsp+98h+Handle], rax; Handle
0x1400323de  mov     [rsp+98h+AccessMode], dil; AccessMode
0x1400323e3  mov     rcx, cs:__imp_IoFileObjectType
0x1400323ea  mov     r8, [rcx]
0x1400323ed  mov     [rsp+98h+ObjectType], r8; ObjectType
0x1400323f2  mov     r9d, 2000000h; DesiredAccess
0x1400323f8  xor     r8d, r8d; PassedAccessState
0x1400323fb  lea     edx, [r8+40h]; HandleAttributes
0x1400323ff  mov     rcx, [rbx+10h]; Object
0x140032403  call    cs:__imp_ObOpenObjectByPointer
0x14003240a  nop     dword ptr [rax+rax+00h]
0x14003240f  mov     r14d, eax
0x140032412  mov     [rsp+98h+var_58], eax
0x140032416  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003241a  lock xadd [rbx+30h], rax
0x140032420  sub     rax, 1
0x140032424  jg      short loc_14003243C
0x140032426  test    rax, rax
0x140032429  jz      short loc_140032434
0x14003242b  mov     ecx, 0Eh
0x140032430  int     29h; Win8: RtlFailFast(ecx)
0x140032432  jmp     short loc_14003243C
0x140032434  mov     rcx, rbx
0x140032437  call    AfdCloseConnection
0x14003243c  test    r14d, r14d
0x14003243f  jns     short loc_140032472
0x140032441  mov     rcx, [rsp+98h+var_50]; Handle
0x140032446  test    rcx, rcx
0x140032449  jz      short loc_14003245A
0x14003244b  mov     dl, dil; PreviousMode
0x14003244e  call    cs:__imp_ObCloseHandle
0x140032455  nop     dword ptr [rax+rax+00h]
0x14003245a  mov     eax, r14d
0x14003245d  jmp     loc_14003259C
0x140032462  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14003246a  movdqu  xmmword ptr [rsp+98h+var_50], xmm0
0x140032470  jmp     short loc_14003247A
0x140032472  mov     r12b, byte ptr [rsp+98h+Src]
0x14003247a  test    r12b, r12b
0x14003247d  jz      loc_140032510
0x140032483  mov     [rsp+98h+Src], 0
0x14003248f  mov     [rsp+98h+Src], 0
0x14003249b  mov     rax, [rsp+98h+var_50]
0x1400324a0  mov     dword ptr [rsp+98h+Src], eax
0x1400324a7  mov     rax, [rsp+98h+var_50+8]
0x1400324ac  mov     dword ptr [rsp+98h+Src+4], eax
0x1400324b3  test    dil, dil
0x1400324b6  jz      short loc_1400324EB
0x1400324b8  test    byte ptr [rsp+98h+arg_28], 3
0x1400324c0  jz      short loc_1400324CF
0x1400324c2  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400324c9  nop     dword ptr [rax+rax+00h]
0x1400324ce  int     3; Trap to Debugger
0x1400324cf  test    dil, dil
0x1400324d2  jz      short loc_1400324EB
0x1400324d4  mov     rdx, [rsp+98h+Src]
0x1400324dc  mov     rcx, [rsp+98h+arg_28]
0x1400324e4  call    RtlWriteULong64ToUser
0x1400324e9  jmp     short loc_140032506
0x1400324eb  mov     r8d, 8; Size
0x1400324f1  lea     rdx, [rsp+98h+Src]; Src
0x1400324f9  mov     rcx, [rsp+98h+arg_28]; void *
0x140032501  call    RtlCopyVolatileMemory
0x140032506  mov     qword ptr [r13+0], 8
0x14003250e  jmp     short loc_14003253C
0x140032510  mov     r8d, 10h; Size
0x140032516  lea     rdx, [rsp+98h+var_50]; Src
0x14003251b  mov     rcx, [rsp+98h+arg_28]; void *
0x140032523  test    dil, dil
0x140032526  jz      short loc_14003252F
0x140032528  call    RtlCopyToUser
0x14003252d  jmp     short loc_140032534
0x14003252f  call    RtlCopyVolatileMemory
0x140032534  mov     qword ptr [r13+0], 10h
0x14003253c  xor     eax, eax
0x14003253e  jmp     short loc_14003259C
0x140032540  mov     rcx, [rsp+98h+var_50]; Handle
0x140032545  lea     rax, [rcx-1]
0x140032549  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003254d  ja      short loc_140032562
0x14003254f  mov     dl, [rsp+98h+PreviousMode]; PreviousMode
0x140032556  call    cs:__imp_ObCloseHandle
0x14003255d  nop     dword ptr [rax+rax+00h]
0x140032562  mov     rcx, [rsp+98h+var_50+8]; Handle
0x140032567  lea     rax, [rcx-1]
0x14003256b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003256f  ja      short loc_140032584
0x140032571  mov     dl, [rsp+98h+PreviousMode]; PreviousMode
0x140032578  call    cs:__imp_ObCloseHandle
0x14003257f  nop     dword ptr [rax+rax+00h]
0x140032584  mov     eax, [rsp+98h+var_58]
0x140032588  jmp     short loc_14003259C
0x14003258a  mov     eax, 0C000000Dh
0x14003258f  jmp     short loc_14003259C
0x140032591  mov     eax, [rsp+98h+var_58]
0x140032595  jmp     short loc_14003259C
0x140032597  mov     eax, 0C0000023h
0x14003259c  add     rsp, 68h
0x1400325a0  pop     r15
0x1400325a2  pop     r14
0x1400325a4  pop     r13
0x1400325a6  pop     r12
0x1400325a8  pop     rdi
0x1400325a9  pop     rbx
0x1400325aa  retn
0x1400738fe  push    rbp
0x140073900  sub     rsp, 40h
0x140073904  mov     rbp, rdx
0x140073907  mov     r8, rcx
0x14007390a  lea     r9, [rbp+40h]
0x14007390e  mov     edx, 43Fh
0x140073913  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007391a  call    AfdExceptionFilter
0x14007391f  nop
0x140073920  add     rsp, 40h
0x140073924  pop     rbp
0x140073925  retn
0x140073927  push    rbp
0x140073929  sub     rsp, 40h
0x14007392d  mov     rbp, rdx
0x140073930  mov     r8, rcx
0x140073933  lea     r9, [rbp+40h]
0x140073937  mov     edx, 4DAh
0x14007393c  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073943  call    AfdExceptionFilter
0x140073948  nop
0x140073949  add     rsp, 40h
0x14007394d  pop     rbp
0x14007394e  retn
```
