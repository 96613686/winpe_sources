# NsipIsNotificationForContainer

- ea: `0x1400ad754`
- end: `0x1400ad853`
- name: `NsipIsNotificationForContainer`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400205f0`

## callees

- `0x140060c44`
- `0x1400ad754`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400aded0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400adeed`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aded0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400adeed`
- `ntoskrnl!PsIsHostSilo` at `0x1400ade9f`
- `ntoskrnl!PsIsHostSilo` at `0x1400ade9f`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400adec0`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400adec0`
- `ntoskrnl!PsGetJobServerSilo` at `0x1400ade89`
- `ntoskrnl!PsGetJobServerSilo` at `0x1400ade89`
- `ntoskrnl!ExAllocatePool2` at `0x1400ade02`
- `ntoskrnl!ExAllocatePool2` at `0x1400ade02`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ad805`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ad839`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ad805`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ad839`
- `NDIS!NdisGetAndReferenceCompartmentJobObject` at `0x1400ad7a2`
- `NDIS!NdisGetAndReferenceCompartmentJobObject` at `0x1400ad7a2`

## pseudocode

```c
char __fastcall NsipIsNotificationForContainer(unsigned int *a1, __int64 a2)
{
  char v2; // r12
  bool v3; // zf
  unsigned int *v5; // rsi
  _QWORD *Pool2; // rbx
  int v7; // eax
  __int64 v8; // r8
  int JobServerSilo; // edi
  bool v10; // sf
  unsigned int v11; // eax
  _QWORD *v13; // rsi
  __int64 v14; // r13
  __int64 v15; // r15
  _QWORD P[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+50h] BYREF
  PVOID Object; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  Object = 0;
  v3 = *a1 == 0;
  v5 = a1;
  P[0] = 0;
  if ( !v3 )
  {
    Pool2 = P;
    v18 = 1;
    while ( 1 )
    {
      v7 = NdisGetAndReferenceCompartmentJobObject(*v5, &v18, Pool2);
      JobServerSilo = v7;
      if ( v7 != 261 )
        break;
      if ( Pool2 != P )
        ExFreePoolWithTag(Pool2, 0x6349534Eu);
      Pool2 = (_QWORD *)ExAllocatePool2(64, 8LL * v18, 1665749838);
      if ( !Pool2 )
      {
        v11 = v18;
        JobServerSilo = -1073741670;
        goto LABEL_20;
      }
    }
    v10 = v7 < 0;
    v11 = v18;
    if ( v10 || !v18 )
      goto LABEL_7;
    v13 = 0;
    if ( a2 )
    {
      v13 = (_QWORD *)a2;
      if ( v18 > 1 )
        v13 = Pool2;
    }
    v14 = 0;
    v15 = 0;
    do
    {
      Object = 0;
      JobServerSilo = PsGetJobServerSilo(Pool2[v15], &Object);
      if ( JobServerSilo < 0 || (unsigned __int8)PsIsHostSilo(Object) || (v2 = 1, !v13) )
      {
        ObfDereferenceObject((PVOID)Pool2[v15]);
      }
      else
      {
        ObfReferenceObjectWithTag(Object, 0x4369734Eu);
        ObfDereferenceObject((PVOID)Pool2[v15]);
        v13[v14] = Object;
        v14 = (unsigned int)(v14 + 1);
      }
      v11 = v18;
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < v18 );
    if ( !v2 || !a2 || (*(_QWORD *)(a2 + 16) = v13, *(_DWORD *)(a2 + 8) = v14, v13 != Pool2) )
    {
LABEL_7:
      if ( Pool2 && Pool2 != P )
      {
        ExFreePoolWithTag(Pool2, 0x6349534Eu);
        v11 = v18;
      }
    }
    if ( JobServerSilo < 0 )
    {
      v5 = a1;
LABEL_20:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_Ddd(WPP_GLOBAL_Control->AttachedDevice, *v5, v8, (unsigned int)JobServerSilo, *v5, v11, P[0]);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400ad754  mov     [rsp-38h+arg_8], rbx
0x1400ad759  mov     [rsp-38h+arg_0], rcx
0x1400ad75e  push    rbp
0x1400ad75f  push    rsi
0x1400ad760  push    rdi
0x1400ad761  push    r12
0x1400ad763  push    r13
0x1400ad765  push    r14
0x1400ad767  push    r15
0x1400ad769  mov     rbp, rsp
0x1400ad76c  sub     rsp, 40h
0x1400ad770  xor     r12b, r12b
0x1400ad773  mov     [rbp+Object], 0
0x1400ad77b  cmp     dword ptr [rcx], 0
0x1400ad77e  mov     r14, rdx
0x1400ad781  mov     rsi, rcx
0x1400ad784  mov     [rbp+P], 0
0x1400ad78c  jz      short loc_1400AD7D4
0x1400ad78e  lea     rbx, [rbp+P]
0x1400ad792  mov     [rbp+arg_10], 1
0x1400ad799  mov     ecx, [rsi]
0x1400ad79b  lea     rdx, [rbp+arg_10]
0x1400ad79f  mov     r8, rbx
0x1400ad7a2  call    cs:__imp_NdisGetAndReferenceCompartmentJobObject
0x1400ad7a9  nop     dword ptr [rax+rax+00h]
0x1400ad7ae  mov     edi, eax
0x1400ad7b0  cmp     eax, 105h
0x1400ad7b5  jz      short loc_1400AD7F0
0x1400ad7b7  test    eax, eax
0x1400ad7b9  mov     eax, [rbp+arg_10]
0x1400ad7bc  js      short loc_1400AD7C2
0x1400ad7be  test    eax, eax
0x1400ad7c0  jnz     short loc_1400AD817
0x1400ad7c2  test    rbx, rbx
0x1400ad7c5  jz      short loc_1400AD7D0
0x1400ad7c7  lea     rcx, [rbp+P]
0x1400ad7cb  cmp     rbx, rcx
0x1400ad7ce  jnz     short loc_1400AD831
0x1400ad7d0  test    edi, edi
0x1400ad7d2  js      short loc_1400AD84A
0x1400ad7d4  mov     rbx, [rsp+40h+arg_8]
0x1400ad7dc  mov     al, r12b
0x1400ad7df  add     rsp, 40h
0x1400ad7e3  pop     r15
0x1400ad7e5  pop     r14
0x1400ad7e7  pop     r13
0x1400ad7e9  pop     r12
0x1400ad7eb  pop     rdi
0x1400ad7ec  pop     rsi
0x1400ad7ed  pop     rbp
0x1400ad7ee  retn
0x1400ad7f0  lea     rax, [rbp+P]
0x1400ad7f4  cmp     rbx, rax
0x1400ad7f7  jz      loc_1400ADDF0
0x1400ad7fd  mov     edx, 6349534Eh; Tag
0x1400ad802  mov     rcx, rbx; P
0x1400ad805  call    cs:__imp_ExFreePoolWithTag
0x1400ad80c  nop     dword ptr [rax+rax+00h]
0x1400ad811  nop
0x1400ad812  jmp     loc_1400ADDF0
0x1400ad817  xor     esi, esi
0x1400ad819  test    r14, r14
0x1400ad81c  jz      loc_1400ADE6B
0x1400ad822  cmp     eax, 1
0x1400ad825  mov     rsi, r14
0x1400ad828  cmova   rsi, rbx
0x1400ad82c  jmp     loc_1400ADE6B
0x1400ad831  mov     edx, 6349534Eh; Tag
0x1400ad836  mov     rcx, rbx; P
0x1400ad839  call    cs:__imp_ExFreePoolWithTag
0x1400ad840  nop     dword ptr [rax+rax+00h]
0x1400ad845  mov     eax, [rbp+arg_10]
0x1400ad848  jmp     short loc_1400AD7D0
0x1400ad84a  mov     rsi, [rbp+arg_0]
0x1400ad84e  jmp     loc_1400ADE22
0x1400addf0  mov     edx, [rbp+arg_10]
0x1400addf3  mov     ecx, 40h ; '@'
0x1400addf8  shl     rdx, 3
0x1400addfc  mov     r8d, 6349534Eh
0x1400ade02  call    cs:__imp_ExAllocatePool2
0x1400ade09  nop     dword ptr [rax+rax+00h]
0x1400ade0e  mov     rbx, rax
0x1400ade11  test    rax, rax
0x1400ade14  jnz     loc_1400AD799
0x1400ade1a  mov     eax, [rbp+arg_10]
0x1400ade1d  mov     edi, 0C000009Ah
0x1400ade22  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ade29  lea     rdx, WPP_GLOBAL_Control
0x1400ade30  cmp     rcx, rdx
0x1400ade33  jz      loc_1400AD7D4
0x1400ade39  cmp     byte ptr [rcx+29h], 2
0x1400ade3d  jb      loc_1400AD7D4
0x1400ade43  mov     edx, [rcx+2Ch]
0x1400ade46  test    dl, 10h
0x1400ade49  jz      loc_1400AD7D4
0x1400ade4f  mov     edx, [rsi]
0x1400ade51  mov     r9d, edi
0x1400ade54  mov     rcx, [rcx+18h]
0x1400ade58  mov     [rsp+40h+var_18], eax
0x1400ade5c  mov     [rsp+40h+var_20], edx
0x1400ade60  call    WPP_SF_Ddd
0x1400ade65  nop
0x1400ade66  jmp     loc_1400AD7D4
0x1400ade6b  xor     r13d, r13d
0x1400ade6e  xor     r15d, r15d
0x1400ade71  test    eax, eax
0x1400ade73  jz      loc_1400AD7C2
0x1400ade79  mov     [rbp+Object], 0
0x1400ade81  lea     rdx, [rbp+Object]
0x1400ade85  mov     rcx, [rbx+r15*8]
0x1400ade89  call    cs:__imp_PsGetJobServerSilo
0x1400ade90  nop     dword ptr [rax+rax+00h]
0x1400ade95  mov     edi, eax
0x1400ade97  test    eax, eax
0x1400ade99  js      short loc_1400ADEE9
0x1400ade9b  mov     rcx, [rbp+Object]
0x1400ade9f  call    cs:__imp_PsIsHostSilo
0x1400adea6  nop     dword ptr [rax+rax+00h]
0x1400adeab  test    al, al
0x1400adead  jnz     short loc_1400ADEE9
0x1400adeaf  mov     r12b, 1
0x1400adeb2  test    rsi, rsi
0x1400adeb5  jz      short loc_1400ADEE9
0x1400adeb7  mov     rcx, [rbp+Object]; Object
0x1400adebb  mov     edx, 4369734Eh; Tag
0x1400adec0  call    cs:__imp_ObfReferenceObjectWithTag
0x1400adec7  nop     dword ptr [rax+rax+00h]
0x1400adecc  mov     rcx, [rbx+r15*8]; Object
0x1400aded0  call    cs:__imp_ObfDereferenceObject
0x1400aded7  nop     dword ptr [rax+rax+00h]
0x1400adedc  mov     rax, [rbp+Object]
0x1400adee0  mov     [rsi+r13*8], rax
0x1400adee4  inc     r13d
0x1400adee7  jmp     short loc_1400ADEF9
0x1400adee9  mov     rcx, [rbx+r15*8]; Object
0x1400adeed  call    cs:__imp_ObfDereferenceObject
0x1400adef4  nop     dword ptr [rax+rax+00h]
0x1400adef9  mov     eax, [rbp+arg_10]
0x1400adefc  inc     r15d
0x1400adeff  cmp     r15d, eax
0x1400adf02  jb      loc_1400ADE79
0x1400adf08  test    r12b, r12b
0x1400adf0b  jz      loc_1400AD7C2
0x1400adf11  test    r14, r14
0x1400adf14  jz      loc_1400AD7C2
0x1400adf1a  mov     [r14+10h], rsi
0x1400adf1e  mov     [r14+8], r13d
0x1400adf22  cmp     rsi, rbx
0x1400adf25  jz      loc_1400AD7D0
0x1400adf2b  jmp     loc_1400AD7C2
```
