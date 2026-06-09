# VfsGetInstanceFromVolumeName

- ea: `0x140011520`
- end: `0x140011714`
- name: `VfsGetInstanceFromVolumeName`
- size: `500`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000874c`
- `0x140008c04`
- `0x140008e7c`

## callees

- `0x140011520`
- `0x140013b00`
- `0x140014000`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140011645`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140011645`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001159b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400116ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001159b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400116ce`
- `ntoskrnl!ExAllocatePool2` at `0x1400115c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400115c5`
- `FLTMGR!FltEnumerateInstances` at `0x1400115f8`
- `FLTMGR!FltEnumerateInstances` at `0x1400115f8`
- `FLTMGR!FltObjectDereference` at `0x1400116a6`
- `FLTMGR!FltObjectDereference` at `0x1400116a6`
- `FLTMGR!FltGetInstanceContext` at `0x140011626`
- `FLTMGR!FltGetInstanceContext` at `0x140011626`
- `FLTMGR!FltReleaseContext` at `0x14001165a`
- `FLTMGR!FltReleaseContext` at `0x140011684`
- `FLTMGR!FltReleaseContext` at `0x14001165a`
- `FLTMGR!FltReleaseContext` at `0x140011684`

## pseudocode

```c
NTSTATUS __fastcall VfsGetInstanceFromVolumeName(PCUNICODE_STRING String2, _QWORD *a2)
{
  int v4; // edi
  _BYTE *v5; // rbx
  PFLT_INSTANCE *v6; // r8
  ULONG v7; // r9d
  ULONG v8; // esi
  __int64 Pool2; // rax
  NTSTATUS result; // eax
  ULONG v11; // ecx
  __int64 v12; // rsi
  __int64 v13; // rdi
  struct _FLT_INSTANCE *v14; // rcx
  __int64 i; // rdi
  ULONG InstanceListSize; // [rsp+30h] [rbp-D0h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE P[192]; // [rsp+40h] [rbp-C0h] BYREF

  memset(P, 0, sizeof(P));
  v4 = 0;
  InstanceListSize = 0;
  v5 = P;
  v6 = (PFLT_INSTANCE *)P;
  v7 = 24;
  while ( 1 )
  {
    result = FltEnumerateInstances(0, VfsData, v6, v7, &InstanceListSize);
    if ( result >= 0 )
      break;
    if ( result != -1073741789 )
      return result;
    if ( v5 != P )
      ExFreePoolWithTag(v5, 0x6E474656u);
    if ( v4 == 2 )
      return -1073741823;
    v8 = InstanceListSize;
    Pool2 = ExAllocatePool2(256, 8LL * InstanceListSize, 1850164822);
    v5 = (_BYTE *)Pool2;
    if ( !Pool2 )
      return -1073741670;
    ++v4;
    v7 = v8;
    v6 = (PFLT_INSTANCE *)Pool2;
  }
  v11 = InstanceListSize;
  v12 = 0;
  v13 = 0;
  if ( !InstanceListSize )
    goto LABEL_18;
  while ( 1 )
  {
    v14 = *(struct _FLT_INSTANCE **)&v5[8 * v13];
    Context = 0;
    if ( FltGetInstanceContext(v14, &Context) >= 0 )
      break;
LABEL_13:
    v11 = InstanceListSize;
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= InstanceListSize )
      goto LABEL_18;
  }
  if ( !RtlEqualUnicodeString((PCUNICODE_STRING)((char *)Context + 8), String2, 1u) )
  {
    FltReleaseContext(Context);
    goto LABEL_13;
  }
  v12 = *(_QWORD *)&v5[8 * v13];
  FltReleaseContext(Context);
  v11 = InstanceListSize;
LABEL_18:
  for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
  {
    if ( *(_QWORD *)&v5[8 * i] != v12 )
    {
      FltObjectDereference(*(PVOID *)&v5[8 * i]);
      v11 = InstanceListSize;
    }
  }
  if ( v5 != P )
    ExFreePoolWithTag(v5, 0x6E474656u);
  if ( !v12 )
    return -1073741275;
  *a2 = v12;
  return 0;
}

```

## disassembly

```asm
0x140011520  mov     [rsp-8+arg_10], rbx
0x140011525  mov     [rsp-8+arg_18], rsi
0x14001152a  push    rbp
0x14001152b  push    rdi
0x14001152c  push    r12
0x14001152e  push    r14
0x140011530  push    r15
0x140011532  lea     rbp, [rsp-10h]
0x140011537  sub     rsp, 110h
0x14001153e  mov     rax, cs:__security_cookie
0x140011545  xor     rax, rsp
0x140011548  mov     [rbp+30h+var_30], rax
0x14001154c  mov     r15, rdx
0x14001154f  mov     r12, rcx
0x140011552  xor     edx, edx; Val
0x140011554  lea     rcx, [rsp+130h+P]; void *
0x140011559  mov     r8d, 0C0h; Size
0x14001155f  call    memset
0x140011564  xor     edi, edi
0x140011566  mov     [rsp+130h+InstanceListSize], 0
0x14001156e  lea     rbx, [rsp+130h+P]
0x140011573  lea     r8, [rsp+130h+P]
0x140011578  lea     r9d, [rdi+18h]
0x14001157c  jmp     short loc_1400115E5
0x14001157e  cmp     eax, 0C0000023h
0x140011583  jnz     loc_1400116EB
0x140011589  lea     rax, [rsp+130h+P]
0x14001158e  cmp     rbx, rax
0x140011591  jz      short loc_1400115A7
0x140011593  mov     edx, 6E474656h; Tag
0x140011598  mov     rcx, rbx; P
0x14001159b  call    cs:__imp_ExFreePoolWithTag
0x1400115a2  nop     dword ptr [rax+rax+00h]
0x1400115a7  cmp     edi, 2
0x1400115aa  jz      loc_140011679
0x1400115b0  mov     esi, [rsp+130h+InstanceListSize]
0x1400115b4  mov     ecx, 100h
0x1400115b9  mov     edx, esi
0x1400115bb  mov     r8d, 6E474656h
0x1400115c1  shl     rdx, 3
0x1400115c5  call    cs:__imp_ExAllocatePool2
0x1400115cc  nop     dword ptr [rax+rax+00h]
0x1400115d1  mov     rbx, rax
0x1400115d4  test    rax, rax
0x1400115d7  jz      loc_140011672
0x1400115dd  inc     edi
0x1400115df  mov     r9d, esi; InstanceListSize
0x1400115e2  mov     r8, rax; InstanceList
0x1400115e5  mov     rdx, cs:VfsData; Filter
0x1400115ec  lea     rax, [rsp+130h+InstanceListSize]
0x1400115f1  xor     ecx, ecx; Volume
0x1400115f3  mov     [rsp+130h+NumberInstancesReturned], rax; NumberInstancesReturned
0x1400115f8  call    cs:__imp_FltEnumerateInstances
0x1400115ff  nop     dword ptr [rax+rax+00h]
0x140011604  test    eax, eax
0x140011606  js      loc_14001157E
0x14001160c  mov     ecx, [rsp+130h+InstanceListSize]
0x140011610  xor     esi, esi
0x140011612  xor     edi, edi
0x140011614  test    ecx, ecx
0x140011616  jz      short loc_140011694
0x140011618  mov     rcx, [rbx+rdi*8]; Instance
0x14001161c  lea     rdx, [rsp+130h+Context]; Context
0x140011621  mov     [rsp+130h+Context], rsi
0x140011626  call    cs:__imp_FltGetInstanceContext
0x14001162d  nop     dword ptr [rax+rax+00h]
0x140011632  test    eax, eax
0x140011634  js      short loc_140011666
0x140011636  mov     rcx, [rsp+130h+Context]
0x14001163b  mov     r8b, 1; CaseInSensitive
0x14001163e  add     rcx, 8; String1
0x140011642  mov     rdx, r12; String2
0x140011645  call    cs:__imp_RtlEqualUnicodeString
0x14001164c  nop     dword ptr [rax+rax+00h]
0x140011651  mov     rcx, [rsp+130h+Context]; Context
0x140011656  test    al, al
0x140011658  jnz     short loc_140011680
0x14001165a  call    cs:__imp_FltReleaseContext
0x140011661  nop     dword ptr [rax+rax+00h]
0x140011666  mov     ecx, [rsp+130h+InstanceListSize]
0x14001166a  inc     edi
0x14001166c  cmp     edi, ecx
0x14001166e  jb      short loc_140011618
0x140011670  jmp     short loc_140011694
0x140011672  mov     eax, 0C000009Ah
0x140011677  jmp     short loc_1400116EB
0x140011679  mov     eax, 0C0000001h
0x14001167e  jmp     short loc_1400116EB
0x140011680  mov     rsi, [rbx+rdi*8]
0x140011684  call    cs:__imp_FltReleaseContext
0x14001168b  nop     dword ptr [rax+rax+00h]
0x140011690  mov     ecx, [rsp+130h+InstanceListSize]
0x140011694  xor     edi, edi
0x140011696  test    ecx, ecx
0x140011698  jz      short loc_1400116BC
0x14001169a  mov     rdx, [rbx+rdi*8]
0x14001169e  cmp     rdx, rsi
0x1400116a1  jz      short loc_1400116B6
0x1400116a3  mov     rcx, rdx; FltObject
0x1400116a6  call    cs:__imp_FltObjectDereference
0x1400116ad  nop     dword ptr [rax+rax+00h]
0x1400116b2  mov     ecx, [rsp+130h+InstanceListSize]
0x1400116b6  inc     edi
0x1400116b8  cmp     edi, ecx
0x1400116ba  jb      short loc_14001169A
0x1400116bc  lea     rax, [rsp+130h+P]
0x1400116c1  cmp     rbx, rax
0x1400116c4  jz      short loc_1400116DA
0x1400116c6  mov     edx, 6E474656h; Tag
0x1400116cb  mov     rcx, rbx; P
0x1400116ce  call    cs:__imp_ExFreePoolWithTag
0x1400116d5  nop     dword ptr [rax+rax+00h]
0x1400116da  test    rsi, rsi
0x1400116dd  jnz     short loc_1400116E6
0x1400116df  mov     eax, 0C0000225h
0x1400116e4  jmp     short loc_1400116EB
0x1400116e6  mov     [r15], rsi
0x1400116e9  xor     eax, eax
0x1400116eb  mov     rcx, [rbp+30h+var_30]
0x1400116ef  xor     rcx, rsp; StackCookie
0x1400116f2  call    __security_check_cookie
0x1400116f7  lea     r11, [rsp+130h+var_20]
0x1400116ff  mov     rbx, [r11+40h]
0x140011703  mov     rsi, [r11+48h]
0x140011707  mov     rsp, r11
0x14001170a  pop     r15
0x14001170c  pop     r14
0x14001170e  pop     r12
0x140011710  pop     rdi
0x140011711  pop     rbp
0x140011712  retn
```
