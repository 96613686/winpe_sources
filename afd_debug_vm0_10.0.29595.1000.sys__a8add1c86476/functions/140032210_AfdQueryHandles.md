# AfdQueryHandles

- ea: `0x140032210`
- end: `0x1400325cc`
- name: `AfdQueryHandles`
- size: `956`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x14001c708`
- `0x14001e7e0`
- `0x14002fd7c`
- `0x140032210`
- `0x140032798`
- `0x140033bfc`
- `0x140072870`
- `0x140092008`
- `0x14009214c`
- `0x14009220c`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x14003246e`
- `ntoskrnl!ObCloseHandle` at `0x140032576`
- `ntoskrnl!ObCloseHandle` at `0x140032598`
- `ntoskrnl!ObCloseHandle` at `0x14003246e`
- `ntoskrnl!ObCloseHandle` at `0x140032576`
- `ntoskrnl!ObCloseHandle` at `0x140032598`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032389`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032423`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032389`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140032423`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003229a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400324e2`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003229a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400324e2`
- `ntoskrnl!IoFileObjectType` at `0x14003236d`
- `ntoskrnl!IoFileObjectType` at `0x140032403`
- `ntoskrnl!IoIs32bitProcess` at `0x140032247`
- `ntoskrnl!IoIs32bitProcess` at `0x140032247`

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
0x140032210  mov     [rsp+PreviousMode], r8b
0x140032215  push    rbx
0x140032216  push    rdi
0x140032217  push    r12
0x140032219  push    r13
0x14003221b  push    r14
0x14003221d  push    r15
0x14003221f  sub     rsp, 68h
0x140032223  mov     r14, r9
0x140032226  mov     dil, r8b
0x140032229  xorps   xmm0, xmm0
0x14003222c  movups  xmmword ptr [rsp+98h+var_50], xmm0
0x140032231  mov     r13, [rsp+98h+Src]
0x140032239  mov     qword ptr [r13+0], 0
0x140032241  mov     rbx, [rcx+18h]
0x140032245  xor     ecx, ecx; Irp
0x140032247  call    cs:__imp_IoIs32bitProcess
0x14003224e  nop     dword ptr [rax+rax+00h]
0x140032253  mov     r12b, al
0x140032256  mov     byte ptr [rsp+98h+Src], al
0x14003225d  cmp     [rsp+98h+arg_20], 4
0x140032265  jb      loc_1400325B7
0x14003226b  test    al, al
0x14003226d  jz      short loc_140032279
0x14003226f  cmp     [rsp+98h+arg_30], 8
0x140032277  jmp     short loc_140032281
0x140032279  cmp     [rsp+98h+arg_30], 10h
0x140032281  jb      loc_1400325B7
0x140032287  xor     r15d, r15d
0x14003228a  mov     [rsp+98h+var_58], r15d
0x14003228f  test    dil, dil
0x140032292  jz      short loc_1400322B9
0x140032294  test    r14b, 3
0x140032298  jz      short loc_1400322A7
0x14003229a  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400322a1  nop     dword ptr [rax+rax+00h]
0x1400322a6  int     3; Trap to Debugger
0x1400322a7  test    dil, dil
0x1400322aa  jz      short loc_1400322B9
0x1400322ac  mov     rcx, r14
0x1400322af  call    RtlReadULongFromUser
0x1400322b4  mov     r14d, eax
0x1400322b7  jmp     short loc_1400322BC
0x1400322b9  mov     r14d, [r14]
0x1400322bc  mov     [rsp+98h+var_54], r14d
0x1400322c1  test    r14d, 0FFFFFFFCh
0x1400322c8  jnz     loc_1400325AA
0x1400322ce  test    r14d, r14d
0x1400322d1  jz      loc_1400325AA
0x1400322d7  mov     eax, [rbx+8]
0x1400322da  bt      eax, 8
0x1400322de  jb      loc_140032482
0x1400322e4  mov     eax, [rbx+8]
0x1400322e7  bt      eax, 9
0x1400322eb  jb      loc_140032482
0x1400322f1  xor     r12b, r12b
0x1400322f4  xorps   xmm0, xmm0
0x1400322f7  movdqu  xmmword ptr [rsp+98h+var_50], xmm0
0x1400322fd  movzx   eax, word ptr [rbx]
0x140032300  mov     ecx, 0AFD1h
0x140032305  cmp     ax, cx
0x140032308  jz      short loc_140032346
0x14003230a  mov     ecx, 1AFDh
0x14003230f  cmp     ax, cx
0x140032312  jz      short loc_140032346
0x140032314  test    byte ptr [rbx+5], 10h
0x140032318  jz      short loc_140032320
0x14003231a  test    byte ptr [rbx+6], 1
0x14003231e  jnz     short loc_140032346
0x140032320  mov     eax, [rbx+8]
0x140032323  test    al, 1
0x140032325  jnz     short loc_140032346
0x140032327  cmp     byte ptr [rbx+2], 4
0x14003232b  jz      short loc_140032346
0x14003232d  mov     rcx, rbx
0x140032330  call    AfdPreventUnbind
0x140032335  test    al, al
0x140032337  jnz     short loc_140032343
0x140032339  mov     eax, 0C0000184h
0x14003233e  jmp     loc_1400325BC
0x140032343  mov     r12b, 1
0x140032346  test    r14b, 1
0x14003234a  jz      short loc_14003239C
0x14003234c  mov     al, [rbx+2]
0x14003234f  sub     al, 3
0x140032351  cmp     al, 1
0x140032353  ja      short loc_14003239C
0x140032355  mov     rcx, [rbx+18h]; Object
0x140032359  test    rcx, rcx
0x14003235c  jz      short loc_14003239C
0x14003235e  lea     rax, [rsp+98h+var_50]
0x140032363  mov     [rsp+98h+Handle], rax; Handle
0x140032368  mov     [rsp+98h+AccessMode], dil; AccessMode
0x14003236d  mov     rax, cs:__imp_IoFileObjectType
0x140032374  mov     rdx, [rax]
0x140032377  mov     [rsp+98h+ObjectType], rdx; ObjectType
0x14003237c  mov     r9d, 2000000h; DesiredAccess
0x140032382  xor     r8d, r8d; PassedAccessState
0x140032385  lea     edx, [r8+40h]; HandleAttributes
0x140032389  call    cs:__imp_ObOpenObjectByPointer
0x140032390  nop     dword ptr [rax+rax+00h]
0x140032395  mov     r15d, eax
0x140032398  mov     [rsp+98h+var_58], eax
0x14003239c  test    r12b, r12b
0x14003239f  jz      short loc_1400323A9
0x1400323a1  mov     rcx, rbx
0x1400323a4  call    AfdReallowUnbind
0x1400323a9  test    r15d, r15d
0x1400323ac  jns     short loc_1400323B6
0x1400323ae  mov     eax, r15d
0x1400323b1  jmp     loc_1400325BC
0x1400323b6  movzx   eax, word ptr [rbx]
0x1400323b9  mov     ecx, 0AFD2h
0x1400323be  and     ax, cx
0x1400323c1  cmp     ax, cx
0x1400323c4  setz    dl
0x1400323c7  test    r14b, 2
0x1400323cb  setnz   al
0x1400323ce  test    al, dl
0x1400323d0  jz      loc_140032492
0x1400323d6  cmp     byte ptr [rbx+2], 4
0x1400323da  jnz     loc_140032492
0x1400323e0  mov     rcx, rbx
0x1400323e3  call    AfdGetConnectionReferenceFromEndpoint
0x1400323e8  mov     rbx, rax
0x1400323eb  test    rax, rax
0x1400323ee  jz      loc_140032492
0x1400323f4  lea     rax, [rsp+98h+var_50+8]
0x1400323f9  mov     [rsp+98h+Handle], rax; Handle
0x1400323fe  mov     [rsp+98h+AccessMode], dil; AccessMode
0x140032403  mov     rcx, cs:__imp_IoFileObjectType
0x14003240a  mov     r8, [rcx]
0x14003240d  mov     [rsp+98h+ObjectType], r8; ObjectType
0x140032412  mov     r9d, 2000000h; DesiredAccess
0x140032418  xor     r8d, r8d; PassedAccessState
0x14003241b  lea     edx, [r8+40h]; HandleAttributes
0x14003241f  mov     rcx, [rbx+10h]; Object
0x140032423  call    cs:__imp_ObOpenObjectByPointer
0x14003242a  nop     dword ptr [rax+rax+00h]
0x14003242f  mov     r14d, eax
0x140032432  mov     [rsp+98h+var_58], eax
0x140032436  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003243a  lock xadd [rbx+30h], rax
0x140032440  sub     rax, 1
0x140032444  jg      short loc_14003245C
0x140032446  test    rax, rax
0x140032449  jz      short loc_140032454
0x14003244b  mov     ecx, 0Eh
0x140032450  int     29h; Win8: RtlFailFast(ecx)
0x140032452  jmp     short loc_14003245C
0x140032454  mov     rcx, rbx
0x140032457  call    AfdCloseConnection
0x14003245c  test    r14d, r14d
0x14003245f  jns     short loc_140032492
0x140032461  mov     rcx, [rsp+98h+var_50]; Handle
0x140032466  test    rcx, rcx
0x140032469  jz      short loc_14003247A
0x14003246b  mov     dl, dil; PreviousMode
0x14003246e  call    cs:__imp_ObCloseHandle
0x140032475  nop     dword ptr [rax+rax+00h]
0x14003247a  mov     eax, r14d
0x14003247d  jmp     loc_1400325BC
0x140032482  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14003248a  movdqu  xmmword ptr [rsp+98h+var_50], xmm0
0x140032490  jmp     short loc_14003249A
0x140032492  mov     r12b, byte ptr [rsp+98h+Src]
0x14003249a  test    r12b, r12b
0x14003249d  jz      loc_140032530
0x1400324a3  mov     [rsp+98h+Src], 0
0x1400324af  mov     [rsp+98h+Src], 0
0x1400324bb  mov     rax, [rsp+98h+var_50]
0x1400324c0  mov     dword ptr [rsp+98h+Src], eax
0x1400324c7  mov     rax, [rsp+98h+var_50+8]
0x1400324cc  mov     dword ptr [rsp+98h+Src+4], eax
0x1400324d3  test    dil, dil
0x1400324d6  jz      short loc_14003250B
0x1400324d8  test    byte ptr [rsp+98h+arg_28], 3
0x1400324e0  jz      short loc_1400324EF
0x1400324e2  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400324e9  nop     dword ptr [rax+rax+00h]
0x1400324ee  int     3; Trap to Debugger
0x1400324ef  test    dil, dil
0x1400324f2  jz      short loc_14003250B
0x1400324f4  mov     rdx, [rsp+98h+Src]
0x1400324fc  mov     rcx, [rsp+98h+arg_28]
0x140032504  call    RtlWriteULong64ToUser
0x140032509  jmp     short loc_140032526
0x14003250b  mov     r8d, 8; Size
0x140032511  lea     rdx, [rsp+98h+Src]; Src
0x140032519  mov     rcx, [rsp+98h+arg_28]; void *
0x140032521  call    RtlCopyVolatileMemory
0x140032526  mov     qword ptr [r13+0], 8
0x14003252e  jmp     short loc_14003255C
0x140032530  mov     r8d, 10h; Size
0x140032536  lea     rdx, [rsp+98h+var_50]; Src
0x14003253b  mov     rcx, [rsp+98h+arg_28]; void *
0x140032543  test    dil, dil
0x140032546  jz      short loc_14003254F
0x140032548  call    RtlCopyToUser
0x14003254d  jmp     short loc_140032554
0x14003254f  call    RtlCopyVolatileMemory
0x140032554  mov     qword ptr [r13+0], 10h
0x14003255c  xor     eax, eax
0x14003255e  jmp     short loc_1400325BC
0x140032560  mov     rcx, [rsp+98h+var_50]; Handle
0x140032565  lea     rax, [rcx-1]
0x140032569  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003256d  ja      short loc_140032582
0x14003256f  mov     dl, [rsp+98h+PreviousMode]; PreviousMode
0x140032576  call    cs:__imp_ObCloseHandle
0x14003257d  nop     dword ptr [rax+rax+00h]
0x140032582  mov     rcx, [rsp+98h+var_50+8]; Handle
0x140032587  lea     rax, [rcx-1]
0x14003258b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003258f  ja      short loc_1400325A4
0x140032591  mov     dl, [rsp+98h+PreviousMode]; PreviousMode
0x140032598  call    cs:__imp_ObCloseHandle
0x14003259f  nop     dword ptr [rax+rax+00h]
0x1400325a4  mov     eax, [rsp+98h+var_58]
0x1400325a8  jmp     short loc_1400325BC
0x1400325aa  mov     eax, 0C000000Dh
0x1400325af  jmp     short loc_1400325BC
0x1400325b1  mov     eax, [rsp+98h+var_58]
0x1400325b5  jmp     short loc_1400325BC
0x1400325b7  mov     eax, 0C0000023h
0x1400325bc  add     rsp, 68h
0x1400325c0  pop     r15
0x1400325c2  pop     r14
0x1400325c4  pop     r13
0x1400325c6  pop     r12
0x1400325c8  pop     rdi
0x1400325c9  pop     rbx
0x1400325ca  retn
0x140073a7e  push    rbp
0x140073a80  sub     rsp, 40h
0x140073a84  mov     rbp, rdx
0x140073a87  mov     r8, rcx
0x140073a8a  lea     r9, [rbp+40h]
0x140073a8e  mov     edx, 43Fh
0x140073a93  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073a9a  call    AfdExceptionFilter
0x140073a9f  nop
0x140073aa0  add     rsp, 40h
0x140073aa4  pop     rbp
0x140073aa5  retn
0x140073aa7  push    rbp
0x140073aa9  sub     rsp, 40h
0x140073aad  mov     rbp, rdx
0x140073ab0  mov     r8, rcx
0x140073ab3  lea     r9, [rbp+40h]
0x140073ab7  mov     edx, 4DAh
0x140073abc  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073ac3  call    AfdExceptionFilter
0x140073ac8  nop
0x140073ac9  add     rsp, 40h
0x140073acd  pop     rbp
0x140073ace  retn
```
