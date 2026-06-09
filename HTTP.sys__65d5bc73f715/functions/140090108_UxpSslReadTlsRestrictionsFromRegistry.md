# UxpSslReadTlsRestrictionsFromRegistry

- ea: `0x140090108`
- end: `0x1400903a7`
- name: `UxpSslReadTlsRestrictionsFromRegistry`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008eee4`

## callees

- `0x140090108`
- `0x1400907f0`
- `0x14009ded0`
- `0x140167940`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14009021b`
- `ntoskrnl!ZwOpenKey` at `0x14009021b`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ac0f`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ae2d`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ac0f`
- `ntoskrnl!ZwEnumerateKey` at `0x14017ae2d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017ad53`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017affe`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017ad53`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14017affe`
- `ntoskrnl!ZwClose` at `0x140090314`
- `ntoskrnl!ZwClose` at `0x140090328`
- `ntoskrnl!ZwClose` at `0x14009033c`
- `ntoskrnl!ZwClose` at `0x140090350`
- `ntoskrnl!ZwClose` at `0x140090364`
- `ntoskrnl!ZwClose` at `0x140090378`
- `ntoskrnl!ZwClose` at `0x14017ada9`
- `ntoskrnl!ZwClose` at `0x14017b055`
- `ntoskrnl!ZwClose` at `0x14017b07e`
- `ntoskrnl!ZwClose` at `0x14017b0a2`
- `ntoskrnl!ZwClose` at `0x14017b0c9`
- `ntoskrnl!ZwClose` at `0x14017b112`
- `ntoskrnl!ZwClose` at `0x140090314`
- `ntoskrnl!ZwClose` at `0x140090328`
- `ntoskrnl!ZwClose` at `0x14009033c`
- `ntoskrnl!ZwClose` at `0x140090350`
- `ntoskrnl!ZwClose` at `0x140090364`
- `ntoskrnl!ZwClose` at `0x140090378`
- `ntoskrnl!ZwClose` at `0x14017ada9`
- `ntoskrnl!ZwClose` at `0x14017b055`
- `ntoskrnl!ZwClose` at `0x14017b07e`
- `ntoskrnl!ZwClose` at `0x14017b0a2`
- `ntoskrnl!ZwClose` at `0x14017b0c9`
- `ntoskrnl!ZwClose` at `0x14017b112`
- `ntoskrnl!ExAllocatePool3` at `0x140090182`
- `ntoskrnl!ExAllocatePool3` at `0x1400901ba`
- `ntoskrnl!ExAllocatePool3` at `0x140090182`
- `ntoskrnl!ExAllocatePool3` at `0x1400901ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090240`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009025a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090240`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009025a`

## string_xrefs

- `0x14017acc5`: `DisabledProtocols`

## pseudocode

```c
__int64 __fastcall UxpSslReadTlsRestrictionsFromRegistry(void *a1, __int64 a2)
{
  void *v2; // rdi
  HANDLE v3; // rsi
  HANDLE v4; // r13
  HANDLE v5; // r15
  HANDLE v6; // r14
  HANDLE v7; // r12
  NTSTATUS v9; // eax
  int RegistryKeyValue; // ebx
  _WORD *v12; // r12
  NTSTATUS v13; // eax
  ULONG *v14; // r12
  ULONG v15; // r12d
  int v16; // eax
  NTSTATUS v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  _WORD *v20; // r12
  NTSTATUS v21; // eax
  __int64 v22; // r12
  void *v23; // rax
  ULONG v24; // r12d
  NTSTATUS v25; // eax
  unsigned int v26; // eax
  NTSTATUS v27; // eax
  void *v28; // [rsp+30h] [rbp-79h]
  HANDLE v29; // [rsp+40h] [rbp-69h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  PVOID P; // [rsp+50h] [rbp-59h]
  HANDLE v32; // [rsp+58h] [rbp-51h] BYREF
  ULONG *v33; // [rsp+60h] [rbp-49h]
  HANDLE v34; // [rsp+68h] [rbp-41h] BYREF
  HANDLE v35; // [rsp+70h] [rbp-39h] BYREF
  PVOID Pool3; // [rsp+78h] [rbp-31h]
  void *KeyHandle; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v38[2]; // [rsp+88h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-11h] BYREF
  ULONG Index; // [rsp+120h] [rbp+77h]
  ULONG ResultLength; // [rsp+128h] [rbp+7Fh] BYREF

  v2 = 0;
  ResultLength = 0;
  v3 = 0;
  v32 = 0;
  v4 = 0;
  Handle = 0;
  v5 = 0;
  v35 = 0;
  v6 = 0;
  v34 = 0;
  v7 = 0;
  v29 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1041, 36, WPP_b370fe665b8033233cc44e642047166f_Traceguids, a1, a2);
  P = (PVOID)ExAllocatePool3(258, 544, 1146252373, UxLowPriorityPool, 1);
  if ( P )
  {
    Pool3 = (PVOID)ExAllocatePool3(258, 21056, 1381264469, UxLowPriorityPool, 1);
    if ( Pool3 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      v38[1] = L"TlsRestrictions";
      *(_QWORD *)&ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v38;
      v38[0] = 1966110;
      KeyHandle = 0;
      ObjectAttributes.RootDirectory = a1;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      RegistryKeyValue = v9;
      if ( v9 >= 0 )
      {
        v2 = KeyHandle;
        KeyHandle = 0;
        while ( 1 )
        {
          Index = (unsigned int)v7;
          if ( (unsigned int)v7 >= 4 )
            break;
          v12 = P;
          v13 = ZwEnumerateKey(v2, Index, KeyBasicInformation, P, 0x220u, &ResultLength);
          RegistryKeyValue = v13;
          if ( v13 == -2147483622 )
          {
            LODWORD(v7) = Index;
            break;
          }
          if ( v13 < 0 )
            goto LABEL_27;
          RegistryKeyValue = UxOpenKey(v2, (__int64)(v12 + 8), v12[6], 0x20019u, 0, &v32);
          if ( RegistryKeyValue < 0 )
          {
            v3 = v32;
            goto LABEL_27;
          }
          v14 = (ULONG *)((char *)Pool3 + 5264 * Index);
          v33 = v14;
          v3 = v32;
          RegistryKeyValue = UxReadRegistryKeyValue(v32, 0, 0, v14 + 1315, 4u);
          if ( RegistryKeyValue < 0 )
            goto LABEL_27;
          v28 = v14 + 129;
          v15 = 0;
          RegistryKeyValue = UxReadRegistryKeyValue(v3, 0, 0, v28, 4u);
          if ( RegistryKeyValue < 0 )
            goto LABEL_27;
          v16 = UxOpenKey(v3, (__int64)L"AlpnIds", 14, 0x20019u, 0, &Handle);
          v4 = Handle;
          RegistryKeyValue = v16;
          if ( v16 < 0 )
            goto LABEL_27;
          while ( v15 < 8 )
          {
            v17 = ZwEnumerateValueKey(v4, v15, KeyValueFullInformation, P, 0x220u, &ResultLength);
            RegistryKeyValue = v17;
            if ( v17 == -2147483622 )
              break;
            if ( v17 < 0 )
              goto LABEL_27;
            v18 = *((_DWORD *)P + 3);
            if ( v18 > 0x40 )
              v18 = 64;
            memmove(&v33[16 * (unsigned __int64)v15++ + 1], (char *)P + *((unsigned int *)P + 2), v18);
          }
          RegistryKeyValue = ZwClose(v4);
          if ( RegistryKeyValue < 0 )
            goto LABEL_27;
          v4 = 0;
          Handle = 0;
          *v33 = v15;
          v19 = UxOpenKey(v3, (__int64)L"CryptoSettings", 28, 0x20019u, 0, &v35);
          v5 = v35;
          RegistryKeyValue = v19;
          if ( v19 < 0 )
            goto LABEL_27;
          while ( (unsigned int)v4 < 8 )
          {
            v20 = P;
            v21 = ZwEnumerateKey(v5, (ULONG)v4, KeyBasicInformation, P, 0x220u, &ResultLength);
            RegistryKeyValue = v21;
            if ( v21 == -2147483622 )
              break;
            if ( v21 < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxOpenKey(v5, (__int64)(v20 + 8), v20[6], 0x20019u, 0, &v34);
            if ( RegistryKeyValue < 0 )
            {
              v6 = v34;
              goto LABEL_66;
            }
            v22 = (__int64)&v33[148 * (unsigned int)v4 + 131];
            v6 = v34;
            v32 = (HANDLE)v22;
            RegistryKeyValue = UxReadRegistryKeyValue(v34, 0, 0, (void *)v22, 4u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxReadRegistryKeyValue(v6, 0, 0, (void *)(v22 + 584), 4u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxReadRegistryKeyValue(v6, 0, 0, (void *)(v22 + 588), 4u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            v23 = (void *)(v22 + 4);
            v24 = 0;
            RegistryKeyValue = UxReadRegistryKeyValue(v6, 0, 0, v23, 0x40u);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            RegistryKeyValue = UxOpenKey(v6, (__int64)L"ChainingModes", 26, 0x20019u, 0, &v29);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            while ( v24 < 8 )
            {
              v25 = ZwEnumerateValueKey(v29, v24, KeyValueFullInformation, P, 0x220u, &ResultLength);
              RegistryKeyValue = v25;
              if ( v25 == -2147483622 )
                break;
              if ( v25 < 0 )
                goto LABEL_66;
              v26 = *((_DWORD *)P + 3);
              if ( v26 > 0x40 )
                v26 = 64;
              memmove((char *)v32 + 64 * (unsigned __int64)v24++ + 72, (char *)P + *((unsigned int *)P + 2), v26);
            }
            RegistryKeyValue = ZwClose(v29);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            v29 = 0;
            *((_DWORD *)v32 + 17) = v24;
            RegistryKeyValue = ZwClose(v6);
            if ( RegistryKeyValue < 0 )
              goto LABEL_66;
            v6 = 0;
            v34 = 0;
            LODWORD(v4) = (_DWORD)v4 + 1;
          }
          RegistryKeyValue = ZwClose(v5);
          if ( RegistryKeyValue < 0 )
          {
LABEL_66:
            v4 = Handle;
            goto LABEL_27;
          }
          v5 = 0;
          v35 = 0;
          v33[130] = (unsigned int)v4;
          v27 = ZwClose(v3);
          v4 = Handle;
          RegistryKeyValue = v27;
          if ( v27 < 0 )
            goto LABEL_27;
          v3 = 0;
          v32 = 0;
          LODWORD(v7) = Index + 1;
        }
        RegistryKeyValue = ZwClose(v2);
        if ( RegistryKeyValue >= 0 )
        {
          v2 = 0;
          if ( (_DWORD)v7 )
          {
            *(_QWORD *)(a2 + 8) = Pool3;
            Pool3 = 0;
          }
          *(_DWORD *)a2 = (_DWORD)v7;
        }
LABEL_27:
        v7 = v29;
      }
      else if ( v9 == -1073741772 )
      {
        RegistryKeyValue = 0;
      }
    }
    else
    {
      RegistryKeyValue = -1073741670;
    }
    ExFreePoolWithTag(P, 0);
    if ( Pool3 )
      ExFreePoolWithTag(Pool3, 0);
    if ( v2 )
      ZwClose(v2);
    if ( v3 )
      ZwClose(v3);
    if ( v4 )
      ZwClose(v4);
    if ( v5 )
      ZwClose(v5);
    if ( v6 )
      ZwClose(v6);
    if ( v7 )
      ZwClose(v7);
  }
  else
  {
    RegistryKeyValue = -1073741670;
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 37, WPP_b370fe665b8033233cc44e642047166f_Traceguids, (unsigned int)RegistryKeyValue);
  return (unsigned int)RegistryKeyValue;
}

```

## disassembly

```asm
0x140090108  mov     [rsp-8+arg_0], rbx
0x14009010d  mov     [rsp-8+arg_8], rdx
0x140090112  push    rbp
0x140090113  push    rsi
0x140090114  push    rdi
0x140090115  push    r12
0x140090117  push    r13
0x140090119  push    r14
0x14009011b  push    r15
0x14009011d  lea     rbp, [rsp-27h]
0x140090122  sub     rsp, 0D0h
0x140090129  xor     edi, edi
0x14009012b  mov     r8, rdx
0x14009012e  mov     [rbp+57h+arg_18], edi
0x140090131  mov     esi, edi
0x140090133  mov     [rbp+57h+var_A8], rdi
0x140090137  mov     r13d, edi
0x14009013a  mov     [rbp+57h+Handle], rdi
0x14009013e  mov     r15d, edi
0x140090141  mov     [rbp+57h+var_90], rdi
0x140090145  mov     r14d, edi
0x140090148  mov     [rbp+57h+var_98], rdi
0x14009014c  mov     r12d, edi
0x14009014f  mov     [rbp+57h+var_C0], rdi
0x140090153  mov     rbx, rcx
0x140090156  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14009015d  jnz     loc_1400902E7
0x140090163  lea     r9, UxLowPriorityPool
0x14009016a  mov     [rsp+100h+Length], 1
0x140090172  mov     edx, 220h
0x140090177  mov     ecx, 102h
0x14009017c  mov     r8d, 44526C55h
0x140090182  call    cs:__imp_ExAllocatePool3
0x140090189  nop     dword ptr [rax+rax+00h]
0x14009018e  mov     [rbp+57h+P], rax
0x140090192  test    rax, rax
0x140090195  jz      loc_14009030A
0x14009019b  lea     r9, UxLowPriorityPool
0x1400901a2  mov     [rsp+100h+Length], 1
0x1400901aa  mov     edx, 5240h
0x1400901af  mov     ecx, 102h
0x1400901b4  mov     r8d, 52546C55h
0x1400901ba  call    cs:__imp_ExAllocatePool3
0x1400901c1  nop     dword ptr [rax+rax+00h]
0x1400901c6  mov     [rbp+57h+var_88], rax
0x1400901ca  test    rax, rax
0x1400901cd  jz      loc_1400902D4
0x1400901d3  lea     rax, aTlsrestriction; "TlsRestrictions"
0x1400901da  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400901e2  mov     [rbp+57h+var_70], rax
0x1400901e6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400901ea  lea     rax, [rbp+57h+var_78]
0x1400901ee  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400901f6  xorps   xmm0, xmm0
0x1400901f9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400901fd  mov     edx, 20019h; DesiredAccess
0x140090202  mov     [rbp+57h+var_78], 1E001Eh
0x14009020a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14009020e  mov     [rbp+57h+KeyHandle], rdi
0x140090212  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x140090216  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009021b  call    cs:__imp_ZwOpenKey
0x140090222  nop     dword ptr [rax+rax+00h]
0x140090227  mov     ebx, eax
0x140090229  test    eax, eax
0x14009022b  jns     loc_1400902C7
0x140090231  cmp     eax, 0C0000034h
0x140090236  jnz     short loc_14009023A
0x140090238  mov     ebx, edi
0x14009023a  mov     rcx, [rbp+57h+P]; P
0x14009023e  xor     edx, edx; Tag
0x140090240  call    cs:__imp_ExFreePoolWithTag
0x140090247  nop     dword ptr [rax+rax+00h]
0x14009024c  mov     rax, [rbp+57h+var_88]
0x140090250  test    rax, rax
0x140090253  jz      short loc_140090266
0x140090255  xor     edx, edx; Tag
0x140090257  mov     rcx, rax; P
0x14009025a  call    cs:__imp_ExFreePoolWithTag
0x140090261  nop     dword ptr [rax+rax+00h]
0x140090266  test    rdi, rdi
0x140090269  jnz     loc_140090311
0x14009026f  test    rsi, rsi
0x140090272  jnz     loc_140090325
0x140090278  test    r13, r13
0x14009027b  jnz     loc_140090339
0x140090281  test    r15, r15
0x140090284  jnz     loc_14009034D
0x14009028a  test    r14, r14
0x14009028d  jnz     loc_140090361
0x140090293  test    r12, r12
0x140090296  jnz     loc_140090375
0x14009029c  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x1400902a3  jnz     loc_140090389
0x1400902a9  mov     eax, ebx
0x1400902ab  mov     rbx, [rsp+100h+arg_0]
0x1400902b3  add     rsp, 0D0h
0x1400902ba  pop     r15
0x1400902bc  pop     r14
0x1400902be  pop     r13
0x1400902c0  pop     r12
0x1400902c2  pop     rdi
0x1400902c3  pop     rsi
0x1400902c4  pop     rbp
0x1400902c5  retn
0x1400902c7  mov     rdi, [rbp+57h+KeyHandle]
0x1400902cb  mov     [rbp+57h+KeyHandle], rsi
0x1400902cf  jmp     loc_14017ABE0
0x1400902d4  mov     ebx, 0C000009Ah
0x1400902d9  jmp     loc_14009023A
0x1400902de  mov     r12, [rbp+57h+var_C0]
0x1400902e2  jmp     loc_14009023A
0x1400902e7  mov     qword ptr [rsp+100h+Length], r8
0x1400902ec  mov     edx, 24h ; '$'
0x1400902f1  lea     r8, WPP_b370fe665b8033233cc44e642047166f_Traceguids
0x1400902f8  mov     ecx, 411h
0x1400902fd  mov     r9, rbx
0x140090300  call    WPP_SF_qq
0x140090305  jmp     loc_140090163
0x14009030a  mov     ebx, 0C000009Ah
0x14009030f  jmp     short loc_14009029C
0x140090311  mov     rcx, rdi; Handle
0x140090314  call    cs:__imp_ZwClose
0x14009031b  nop     dword ptr [rax+rax+00h]
0x140090320  jmp     loc_14009026F
0x140090325  mov     rcx, rsi; Handle
0x140090328  call    cs:__imp_ZwClose
0x14009032f  nop     dword ptr [rax+rax+00h]
0x140090334  jmp     loc_140090278
0x140090339  mov     rcx, r13; Handle
0x14009033c  call    cs:__imp_ZwClose
0x140090343  nop     dword ptr [rax+rax+00h]
0x140090348  jmp     loc_140090281
0x14009034d  mov     rcx, r15; Handle
0x140090350  call    cs:__imp_ZwClose
0x140090357  nop     dword ptr [rax+rax+00h]
0x14009035c  jmp     loc_14009028A
0x140090361  mov     rcx, r14; Handle
0x140090364  call    cs:__imp_ZwClose
0x14009036b  nop     dword ptr [rax+rax+00h]
0x140090370  jmp     loc_140090293
0x140090375  mov     rcx, r12; Handle
0x140090378  call    cs:__imp_ZwClose
0x14009037f  nop     dword ptr [rax+rax+00h]
0x140090384  jmp     loc_14009029C
0x140090389  mov     edx, 25h ; '%'
0x14009038e  lea     r8, WPP_b370fe665b8033233cc44e642047166f_Traceguids
0x140090395  mov     ecx, 411h
0x14009039a  mov     r9d, ebx
0x14009039d  call    WPP_SF_d
0x1400903a2  jmp     loc_1400902A9
0x14017abe0  mov     [rbp+57h+Index], r12d
0x14017abe4  cmp     r12d, 4
0x14017abe8  jnb     loc_14017B10F
0x14017abee  mov     r12, [rbp+57h+P]
0x14017abf2  lea     rax, [rbp+57h+arg_18]
0x14017abf6  mov     edx, [rbp+57h+Index]; Index
0x14017abf9  mov     r9, r12; KeyInformation
0x14017abfc  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14017ac01  xor     r8d, r8d; KeyInformationClass
0x14017ac04  mov     rcx, rdi; KeyHandle
0x14017ac07  mov     [rsp+100h+Length], 220h; Length
0x14017ac0f  call    cs:__imp_ZwEnumerateKey
0x14017ac16  nop     dword ptr [rax+rax+00h]
0x14017ac1b  mov     ebx, eax
0x14017ac1d  cmp     eax, 8000001Ah
0x14017ac22  jz      loc_14017B10B
0x14017ac28  test    eax, eax
0x14017ac2a  js      loc_1400902DE
0x14017ac30  movzx   r8d, word ptr [r12+0Ch]
0x14017ac36  lea     rcx, [rbp+57h+var_A8]
0x14017ac3a  mov     [rsp+100h+ResultLength], rcx
0x14017ac3f  lea     rdx, [r12+10h]
0x14017ac44  xor     esi, esi
0x14017ac46  mov     rcx, rdi
0x14017ac49  mov     r9d, 20019h
0x14017ac4f  mov     byte ptr [rsp+100h+Length], sil
0x14017ac54  call    UxOpenKey
0x14017ac59  mov     ebx, eax
0x14017ac5b  test    eax, eax
0x14017ac5d  js      loc_14017B102
0x14017ac63  mov     eax, [rbp+57h+Index]
0x14017ac66  lea     r8d, [rsi+4]
0x14017ac6a  mov     [rsp+100h+var_C8], r8d; ULONG
0x14017ac6f  lea     rdx, aFlags; "Flags"
0x14017ac76  imul    r12, rax, 1490h
0x14017ac7d  xor     r9d, r9d
0x14017ac80  add     r12, [rbp+57h+var_88]
0x14017ac84  mov     [rbp+57h+var_A0], r12
0x14017ac88  lea     rax, [r12+148Ch]
0x14017ac90  mov     [rsp+100h+var_D0], rax; void *
0x14017ac95  mov     dword ptr [rsp+100h+ResultLength], esi; int
0x14017ac99  mov     qword ptr [rsp+100h+Length], rsi; Src
0x14017ac9e  mov     rsi, [rbp+57h+var_A8]
0x14017aca2  mov     rcx, rsi; KeyHandle
0x14017aca5  call    UxReadRegistryKeyValue
0x14017acaa  mov     ebx, eax
0x14017acac  test    eax, eax
0x14017acae  js      loc_1400902DE
0x14017acb4  mov     ecx, 4
0x14017acb9  lea     rax, [r12+204h]
0x14017acc1  mov     [rsp+100h+var_C8], ecx; ULONG
0x14017acc5  lea     rdx, aDisabledprotoc; "DisabledProtocols"
0x14017accc  mov     [rsp+100h+var_D0], rax; void *
0x14017acd1  xor     r12d, r12d
0x14017acd4  mov     r8d, ecx
0x14017acd7  mov     dword ptr [rsp+100h+ResultLength], r12d; int
0x14017acdc  xor     r9d, r9d
0x14017acdf  mov     qword ptr [rsp+100h+Length], r12; Src
0x14017ace4  mov     rcx, rsi; KeyHandle
0x14017ace7  call    UxReadRegistryKeyValue
0x14017acec  mov     ebx, eax
0x14017acee  test    eax, eax
0x14017acf0  js      loc_1400902DE
0x14017acf6  lea     rax, [rbp+57h+Handle]
0x14017acfa  mov     r9d, 20019h
0x14017ad00  mov     [rsp+100h+ResultLength], rax
0x14017ad05  lea     r8d, [r12+0Eh]
0x14017ad0a  lea     rdx, aAlpnids; "AlpnIds"
0x14017ad11  mov     byte ptr [rsp+100h+Length], r12b
0x14017ad16  mov     rcx, rsi
0x14017ad19  call    UxOpenKey
0x14017ad1e  mov     r13, [rbp+57h+Handle]
0x14017ad22  mov     ebx, eax
0x14017ad24  test    eax, eax
0x14017ad26  js      loc_1400902DE
0x14017ad2c  cmp     r12d, 8
0x14017ad30  jnb     short loc_14017ADA6
0x14017ad32  mov     r9, [rbp+57h+P]; KeyValueInformation
0x14017ad36  lea     rax, [rbp+57h+arg_18]
0x14017ad3a  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14017ad3f  mov     r8d, 1; KeyValueInformationClass
0x14017ad45  mov     edx, r12d; Index
0x14017ad48  mov     [rsp+100h+Length], 220h; Length
0x14017ad50  mov     rcx, r13; KeyHandle
0x14017ad53  call    cs:__imp_ZwEnumerateValueKey
0x14017ad5a  nop     dword ptr [rax+rax+00h]
0x14017ad5f  mov     ebx, eax
0x14017ad61  cmp     eax, 8000001Ah
0x14017ad66  jz      short loc_14017ADA6
0x14017ad68  test    eax, eax
0x14017ad6a  js      loc_1400902DE
0x14017ad70  mov     rcx, [rbp+57h+P]
0x14017ad74  mov     edx, 40h ; '@'
0x14017ad79  mov     eax, [rcx+0Ch]
0x14017ad7c  cmp     eax, edx
0x14017ad7e  cmova   eax, edx
0x14017ad81  mov     edx, [rcx+8]
0x14017ad84  add     rdx, rcx; Src
0x14017ad87  mov     r8d, eax; Size
0x14017ad8a  mov     rcx, [rbp+57h+var_A0]
0x14017ad8e  add     rcx, 4
0x14017ad92  mov     eax, r12d
0x14017ad95  shl     rax, 6
0x14017ad99  add     rcx, rax; void *
0x14017ad9c  call    memmove
0x14017ada1  inc     r12d
0x14017ada4  jmp     short loc_14017AD2C
0x14017ada6  mov     rcx, r13; Handle
0x14017ada9  call    cs:__imp_ZwClose
0x14017adb0  nop     dword ptr [rax+rax+00h]
0x14017adb5  mov     ebx, eax
0x14017adb7  test    eax, eax
0x14017adb9  js      loc_1400902DE
0x14017adbf  mov     rax, [rbp+57h+var_A0]
0x14017adc3  lea     rdx, aCryptosettings; "CryptoSettings"
0x14017adca  xor     r13d, r13d
0x14017adcd  mov     r9d, 20019h
0x14017add3  mov     rcx, rsi
0x14017add6  mov     [rbp+57h+Handle], r13
0x14017adda  mov     [rax], r12d
0x14017addd  lea     rax, [rbp+57h+var_90]
0x14017ade1  mov     [rsp+100h+ResultLength], rax
0x14017ade6  lea     r8d, [r13+1Ch]
0x14017adea  mov     byte ptr [rsp+100h+Length], r13b
0x14017adef  call    UxOpenKey
0x14017adf4  mov     r15, [rbp+57h+var_90]
0x14017adf8  mov     ebx, eax
0x14017adfa  test    eax, eax
0x14017adfc  js      loc_1400902DE
0x14017ae02  cmp     r13d, 8
0x14017ae06  jnb     loc_14017B09F
0x14017ae0c  mov     r12, [rbp+57h+P]
0x14017ae10  lea     rax, [rbp+57h+arg_18]
0x14017ae14  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14017ae19  mov     r9, r12; KeyInformation
0x14017ae1c  xor     r8d, r8d; KeyInformationClass
0x14017ae1f  mov     [rsp+100h+Length], 220h; Length
0x14017ae27  mov     edx, r13d; Index
0x14017ae2a  mov     rcx, r15; KeyHandle
0x14017ae2d  call    cs:__imp_ZwEnumerateKey
0x14017ae34  nop     dword ptr [rax+rax+00h]
0x14017ae39  mov     ebx, eax
0x14017ae3b  cmp     eax, 8000001Ah
0x14017ae40  jz      loc_14017B09F
0x14017ae46  test    eax, eax
0x14017ae48  js      loc_14017B0F9
0x14017ae4e  movzx   r8d, word ptr [r12+0Ch]
0x14017ae54  lea     rax, [rbp+57h+var_98]
0x14017ae58  mov     [rsp+100h+ResultLength], rax
  ... truncated ...
```
