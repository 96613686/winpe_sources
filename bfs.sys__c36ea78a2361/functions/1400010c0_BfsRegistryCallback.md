# BfsRegistryCallback

- ea: `0x1400010c0`
- end: `0x140001264`
- name: `BfsRegistryCallback`
- size: `420`
- prototype: `__int64 __fastcall(PVOID CallbackContext, PVOID Argument1, __int64 Argument2)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001008`
- `0x1400010c0`
- `0x140003340`
- `0x14000f100`
- `0x14000f304`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x1400010f2`
- `ntoskrnl!ExGetPreviousMode` at `0x1400010f2`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140001225`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140001225`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140001217`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140001217`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000114f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000114f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000115e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000115e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000113b`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000113b`

## pseudocode

```c
__int64 __fastcall BfsRegistryCallback(PVOID CallbackContext, PVOID Argument1, __int64 Argument2)
{
  int v4; // esi
  int Callback; // edi
  PACCESS_TOKEN v7; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  char v9; // bp
  __int64 v10; // rcx
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // [rsp+20h] [rbp-78h]
  unsigned __int8 EffectiveOnly; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+31h] [rbp-67h] BYREF
  int v18; // [rsp+34h] [rbp-64h] BYREF
  _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+40h] [rbp-58h] BYREF
  int *v21; // [rsp+60h] [rbp-38h]
  __int64 v22; // [rsp+68h] [rbp-30h]

  CopyOnOpen[0] = 0;
  v4 = (int)Argument1;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  if ( !ExGetPreviousMode() )
    return 0;
  Callback = 0;
  v7 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  if ( v7 )
  {
    v9 = 1;
  }
  else
  {
    CurrentProcess = IoGetCurrentProcess();
    v7 = PsReferencePrimaryToken(CurrentProcess);
    v9 = 0;
  }
  if ( BfsIsApplicableToken(v7, 0) )
  {
    if ( v4 == 26 )
      goto LABEL_14;
    v10 = (unsigned int)(v4 - 27);
    if ( v4 == 27 )
      goto LABEL_11;
    v10 = (unsigned int)(v4 - 28);
    if ( v4 == 28 )
    {
LABEL_14:
      Callback = BfsRegistryPreCreateCallback(v4, Argument2, v7);
      if ( Callback >= 0 || (unsigned int)dword_140019000 <= 3 )
        goto LABEL_18;
      v18 = Callback;
LABEL_17:
      v22 = 4;
      v21 = &v18;
      tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140016D91, v12, v13, v15, &v20);
      goto LABEL_18;
    }
    if ( v4 == 29 )
    {
LABEL_11:
      v11 = BfsRegistryPostCreateCallback(v10, Argument2, v7);
      Callback = v11;
      if ( v11 >= 0 )
        goto LABEL_18;
      v14 = dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_18;
      v18 = v11;
      goto LABEL_17;
    }
  }
LABEL_18:
  if ( v7 )
  {
    if ( v9 )
      PsDereferenceImpersonationToken(v7);
    else
      PsDereferencePrimaryToken(v7);
  }
  return (unsigned int)Callback;
}

```

## disassembly

```asm
0x1400010c0  push    rsi
0x1400010c2  push    r14
0x1400010c4  sub     rsp, 88h
0x1400010cb  mov     rax, cs:__security_cookie
0x1400010d2  xor     rax, rsp
0x1400010d5  mov     [rsp+98h+var_28], rax
0x1400010da  mov     r14, r8
0x1400010dd  mov     [rsp+98h+CopyOnOpen], 0
0x1400010e2  mov     rsi, rdx
0x1400010e5  mov     [rsp+98h+EffectiveOnly], 0
0x1400010ea  mov     [rsp+98h+ImpersonationLevel], 0
0x1400010f2  call    cs:__imp_ExGetPreviousMode
0x1400010f9  nop     dword ptr [rax+rax+00h]
0x1400010fe  test    al, al
0x140001100  jnz     short loc_140001109
0x140001102  xor     eax, eax
0x140001104  jmp     loc_14000124B
0x140001109  mov     rcx, gs:188h; Thread
0x140001112  lea     r9, [rsp+98h+ImpersonationLevel]; ImpersonationLevel
0x140001117  mov     [rsp+98h+arg_0], rbx
0x14000111f  lea     r8, [rsp+98h+EffectiveOnly]; EffectiveOnly
0x140001124  mov     [rsp+98h+arg_18], rbp
0x14000112c  lea     rdx, [rsp+98h+CopyOnOpen]; CopyOnOpen
0x140001131  mov     [rsp+98h+var_18], rdi
0x140001139  xor     edi, edi
0x14000113b  call    cs:__imp_PsReferenceImpersonationToken
0x140001142  nop     dword ptr [rax+rax+00h]
0x140001147  mov     rbx, rax
0x14000114a  test    rax, rax
0x14000114d  jnz     short loc_140001172
0x14000114f  call    cs:__imp_IoGetCurrentProcess
0x140001156  nop     dword ptr [rax+rax+00h]
0x14000115b  mov     rcx, rax; Process
0x14000115e  call    cs:__imp_PsReferencePrimaryToken
0x140001165  nop     dword ptr [rax+rax+00h]
0x14000116a  mov     rbx, rax
0x14000116d  xor     bpl, bpl
0x140001170  jmp     short loc_140001175
0x140001172  mov     bpl, 1
0x140001175  xor     edx, edx
0x140001177  mov     rcx, rbx; Object
0x14000117a  call    BfsIsApplicableToken
0x14000117f  test    al, al
0x140001181  jz      loc_14000120A
0x140001187  mov     ecx, esi
0x140001189  sub     ecx, 1Ah
0x14000118c  jz      short loc_1400011BF
0x14000118e  sub     ecx, 1
0x140001191  jz      short loc_14000119D
0x140001193  sub     ecx, 1
0x140001196  jz      short loc_1400011BF
0x140001198  cmp     ecx, 1
0x14000119b  jnz     short loc_14000120A
0x14000119d  mov     r8, rbx
0x1400011a0  mov     rdx, r14
0x1400011a3  call    BfsRegistryPostCreateCallback
0x1400011a8  mov     edi, eax
0x1400011aa  test    eax, eax
0x1400011ac  jns     short loc_14000120A
0x1400011ae  mov     ecx, cs:dword_140019000
0x1400011b4  cmp     ecx, 3
0x1400011b7  jbe     short loc_14000120A
0x1400011b9  mov     [rsp+98h+var_64], eax
0x1400011bd  jmp     short loc_1400011E1
0x1400011bf  mov     r8, rbx
0x1400011c2  mov     rdx, r14
0x1400011c5  mov     ecx, esi
0x1400011c7  call    BfsRegistryPreCreateCallback
0x1400011cc  mov     edi, eax
0x1400011ce  test    eax, eax
0x1400011d0  jns     short loc_14000120A
0x1400011d2  mov     eax, cs:dword_140019000
0x1400011d8  cmp     eax, 3
0x1400011db  jbe     short loc_14000120A
0x1400011dd  mov     [rsp+98h+var_64], edi
0x1400011e1  lea     rax, [rsp+98h+var_64]
0x1400011e6  mov     [rsp+98h+var_30], 4
0x1400011ef  mov     [rsp+98h+var_38], rax
0x1400011f4  lea     rdx, byte_140016D91; int
0x1400011fb  lea     rax, [rsp+98h+var_58]
0x140001200  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x140001205  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000120a  test    rbx, rbx
0x14000120d  jz      short loc_140001231
0x14000120f  mov     rcx, rbx; PrimaryToken
0x140001212  test    bpl, bpl
0x140001215  jz      short loc_140001225
0x140001217  call    cs:__imp_PsDereferenceImpersonationToken
0x14000121e  nop     dword ptr [rax+rax+00h]
0x140001223  jmp     short loc_140001231
0x140001225  call    cs:__imp_PsDereferencePrimaryToken
0x14000122c  nop     dword ptr [rax+rax+00h]
0x140001231  mov     rbp, [rsp+98h+arg_18]
0x140001239  mov     eax, edi
0x14000123b  mov     rdi, [rsp+98h+var_18]
0x140001243  mov     rbx, [rsp+98h+arg_0]
0x14000124b  mov     rcx, [rsp+98h+var_28]
0x140001250  xor     rcx, rsp; StackCookie
0x140001253  call    __security_check_cookie
0x140001258  add     rsp, 88h
0x14000125f  pop     r14
0x140001261  pop     rsi
0x140001262  retn
```
