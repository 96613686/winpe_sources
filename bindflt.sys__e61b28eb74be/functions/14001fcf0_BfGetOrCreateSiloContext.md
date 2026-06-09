# BfGetOrCreateSiloContext

- ea: `0x14001fcf0`
- end: `0x140020016`
- name: `BfGetOrCreateSiloContext`
- size: `806`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001010`
- `0x14001f71c`

## callees

- `0x140001348`
- `0x140003074`
- `0x140003304`
- `0x14001fcf0`

## import_xrefs

- `ntoskrnl!PsDereferenceSiloContext` at `0x14001ff4e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140020005`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001ff4e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140020005`
- `ntoskrnl!PsCreateSiloContext` at `0x14001fdc1`
- `ntoskrnl!PsCreateSiloContext` at `0x14001fdc1`
- `ntoskrnl!PsInsertSiloContext` at `0x14001fdfe`
- `ntoskrnl!PsInsertSiloContext` at `0x14001fdfe`
- `ntoskrnl!PsGetSiloContext` at `0x14001fd42`
- `ntoskrnl!PsGetSiloContext` at `0x14001ff73`
- `ntoskrnl!PsGetSiloContext` at `0x14001fd42`
- `ntoskrnl!PsGetSiloContext` at `0x14001ff73`
- `ntoskrnl!PsIsHostSilo` at `0x14001fd1d`
- `ntoskrnl!PsIsHostSilo` at `0x14001fd1d`

## pseudocode

```c
__int64 __fastcall BfGetOrCreateSiloContext(__int64 a1, char a2, _QWORD *a3)
{
  int v6; // edx
  int SiloContext; // eax
  int v8; // edx
  unsigned int v9; // ebx
  int v11; // eax
  int v12; // eax
  int inserted; // eax
  int v14; // r9d
  int v15; // eax
  char v16; // [rsp+30h] [rbp-38h]
  int v17; // [rsp+38h] [rbp-30h]
  __int64 v18; // [rsp+80h] [rbp+18h] BYREF

  v18 = 0;
  *a3 = 0;
  if ( (unsigned __int8)PsIsHostSilo(a1) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        7,
        27,
        (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
        21);
    }
    v9 = -1073741811;
    goto LABEL_4;
  }
  SiloContext = PsGetSiloContext(a1, (unsigned int)dword_14000B1D0, &v18);
  v9 = SiloContext;
  if ( SiloContext != -1073741275 )
  {
    if ( SiloContext < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_4;
      v17 = SiloContext;
      v14 = 33;
      v16 = 94;
      goto LABEL_29;
    }
    goto LABEL_8;
  }
  if ( !a2 )
  {
    v11 = PsCreateSiloContext(a1, 16, 512, BfCleanupSiloContext, &v18);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_4;
      v17 = v11;
      v14 = 28;
      v16 = 48;
      goto LABEL_29;
    }
    v12 = BfInitializeSiloContext(a1, v18);
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_4;
      v17 = v12;
      v14 = 29;
      v16 = 56;
      goto LABEL_29;
    }
    inserted = PsInsertSiloContext(a1, (unsigned int)dword_14000B1D0, v18);
    v9 = inserted;
    if ( inserted == -1073741637 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 3;
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          7,
          30,
          (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
          73);
      }
      PsDereferenceSiloContext(v18);
      v18 = 0;
      v15 = PsGetSiloContext(a1, (unsigned int)dword_14000B1D0, &v18);
      v9 = v15;
      if ( v15 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_4;
        v17 = v15;
        v14 = 31;
        v16 = 82;
        goto LABEL_29;
      }
    }
    else if ( inserted < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_4;
      v17 = inserted;
      v14 = 32;
      v16 = 88;
LABEL_29:
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        7,
        v14,
        (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
        v16,
        v17);
      goto LABEL_4;
    }
LABEL_8:
    *a3 = v18;
    return 0;
  }
LABEL_4:
  if ( v18 )
    PsDereferenceSiloContext(v18);
  return v9;
}

```

## disassembly

```asm
0x14001fcf0  mov     [rsp+arg_0], rbx
0x14001fcf5  mov     [rsp+arg_8], rbp
0x14001fcfa  push    rsi
0x14001fcfb  push    rdi
0x14001fcfc  push    r12
0x14001fcfe  push    r14
0x14001fd00  push    r15
0x14001fd02  sub     rsp, 40h
0x14001fd06  xor     r12d, r12d
0x14001fd09  mov     rsi, r8
0x14001fd0c  mov     [rsp+68h+arg_10], r12
0x14001fd14  movzx   ebp, dl
0x14001fd17  mov     [r8], r12
0x14001fd1a  mov     rdi, rcx
0x14001fd1d  call    cs:__imp_PsIsHostSilo
0x14001fd24  nop     dword ptr [rax+rax+00h]
0x14001fd29  test    al, al
0x14001fd2b  jnz     loc_14001FEA0
0x14001fd31  mov     edx, cs:dword_14000B1D0
0x14001fd37  lea     r8, [rsp+68h+arg_10]
0x14001fd3f  mov     rcx, rdi
0x14001fd42  call    cs:__imp_PsGetSiloContext
0x14001fd49  nop     dword ptr [rax+rax+00h]
0x14001fd4e  mov     ebx, eax
0x14001fd50  cmp     eax, 0C0000225h
0x14001fd55  jnz     short loc_14001FD87
0x14001fd57  test    bpl, bpl
0x14001fd5a  jz      short loc_14001FD9F
0x14001fd5c  mov     rcx, [rsp+68h+arg_10]
0x14001fd64  test    rcx, rcx
0x14001fd67  jnz     loc_140020005
0x14001fd6d  mov     eax, ebx
0x14001fd6f  mov     rbx, [rsp+68h+arg_0]
0x14001fd74  mov     rbp, [rsp+68h+arg_8]
0x14001fd79  add     rsp, 40h
0x14001fd7d  pop     r15
0x14001fd7f  pop     r14
0x14001fd81  pop     r12
0x14001fd83  pop     rdi
0x14001fd84  pop     rsi
0x14001fd85  retn
0x14001fd87  test    eax, eax
0x14001fd89  js      loc_14001FFAA
0x14001fd8f  mov     rax, [rsp+68h+arg_10]
0x14001fd97  mov     [rsi], rax
0x14001fd9a  mov     eax, r12d
0x14001fd9d  jmp     short loc_14001FD6F
0x14001fd9f  lea     rax, [rsp+68h+arg_10]
0x14001fda7  mov     edx, 10h
0x14001fdac  lea     r9, BfCleanupSiloContext
0x14001fdb3  mov     [rsp+68h+var_48], rax
0x14001fdb8  mov     r8d, 200h
0x14001fdbe  mov     rcx, rdi
0x14001fdc1  call    cs:__imp_PsCreateSiloContext
0x14001fdc8  nop     dword ptr [rax+rax+00h]
0x14001fdcd  mov     ebx, eax
0x14001fdcf  test    eax, eax
0x14001fdd1  js      short loc_14001FE4A
0x14001fdd3  mov     rdx, [rsp+68h+arg_10]
0x14001fddb  mov     rcx, rdi
0x14001fdde  call    BfInitializeSiloContext
0x14001fde3  mov     ebx, eax
0x14001fde5  test    eax, eax
0x14001fde7  js      loc_14001FE75
0x14001fded  mov     r8, [rsp+68h+arg_10]
0x14001fdf5  mov     rcx, rdi
0x14001fdf8  mov     edx, cs:dword_14000B1D0
0x14001fdfe  call    cs:__imp_PsInsertSiloContext
0x14001fe05  nop     dword ptr [rax+rax+00h]
0x14001fe0a  mov     ebx, eax
0x14001fe0c  cmp     eax, 0C00000BBh
0x14001fe11  jz      loc_14001FEF8
0x14001fe17  test    eax, eax
0x14001fe19  jns     loc_14001FD8F
0x14001fe1f  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001fe26  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001fe2d  jz      loc_14001FD5C
0x14001fe33  mov     [rsp+68h+var_30], eax
0x14001fe37  mov     r9d, 20h ; ' '
0x14001fe3d  mov     dword ptr [rsp+68h+var_38], 558h
0x14001fe45  jmp     loc_14001FFD0
0x14001fe4a  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001fe51  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001fe58  jz      loc_14001FD5C
0x14001fe5e  mov     [rsp+68h+var_30], eax
0x14001fe62  mov     r9d, 1Ch
0x14001fe68  mov     dword ptr [rsp+68h+var_38], 530h
0x14001fe70  jmp     loc_14001FFD0
0x14001fe75  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001fe7c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001fe83  jz      loc_14001FD5C
0x14001fe89  mov     [rsp+68h+var_30], eax
0x14001fe8d  mov     r9d, 1Dh
0x14001fe93  mov     dword ptr [rsp+68h+var_38], 538h
0x14001fe9b  jmp     loc_14001FFD0
0x14001fea0  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001fea7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001feae  jz      short loc_14001FEEE
0x14001feb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001feb7  lea     r14, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001febe  mov     dword ptr [rsp+68h+var_38], 515h
0x14001fec6  lea     r15, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x14001fecd  mov     r9d, 1Bh
0x14001fed3  mov     [rsp+68h+var_40], r14
0x14001fed8  mov     r8d, 7
0x14001fede  mov     [rsp+68h+var_48], r15
0x14001fee3  mov     rcx, [rcx+40h]
0x14001fee7  mov     dl, 2
0x14001fee9  call    WPP_RECORDER_SF_sD
0x14001feee  mov     ebx, 0C000000Dh
0x14001fef3  jmp     loc_14001FD5C
0x14001fef8  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001feff  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001ff06  lea     r14, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001ff0d  lea     r15, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x14001ff14  jz      short loc_14001FF46
0x14001ff16  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ff1d  mov     r9d, 1Eh
0x14001ff23  mov     dword ptr [rsp+68h+var_38], 549h
0x14001ff2b  mov     r8d, 7
0x14001ff31  mov     [rsp+68h+var_40], r14
0x14001ff36  mov     dl, 3
0x14001ff38  mov     [rsp+68h+var_48], r15
0x14001ff3d  mov     rcx, [rcx+40h]
0x14001ff41  call    WPP_RECORDER_SF_sD
0x14001ff46  mov     rcx, [rsp+68h+arg_10]
0x14001ff4e  call    cs:__imp_PsDereferenceSiloContext
0x14001ff55  nop     dword ptr [rax+rax+00h]
0x14001ff5a  mov     edx, cs:dword_14000B1D0
0x14001ff60  lea     r8, [rsp+68h+arg_10]
0x14001ff68  mov     rcx, rdi
0x14001ff6b  mov     [rsp+68h+arg_10], r12
0x14001ff73  call    cs:__imp_PsGetSiloContext
0x14001ff7a  nop     dword ptr [rax+rax+00h]
0x14001ff7f  mov     ebx, eax
0x14001ff81  test    eax, eax
0x14001ff83  jns     loc_14001FD8F
0x14001ff89  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001ff90  jz      loc_14001FD5C
0x14001ff96  mov     [rsp+68h+var_30], eax
0x14001ff9a  mov     r9d, 1Fh
0x14001ffa0  mov     dword ptr [rsp+68h+var_38], 552h
0x14001ffa8  jmp     short loc_14001FFDE
0x14001ffaa  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001ffb1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001ffb8  jz      loc_14001FD5C
0x14001ffbe  mov     [rsp+68h+var_30], eax
0x14001ffc2  mov     r9d, 21h ; '!'
0x14001ffc8  mov     dword ptr [rsp+68h+var_38], 55Eh
0x14001ffd0  lea     r15, WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids
0x14001ffd7  lea     r14, aOnecoreBaseFsW; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001ffde  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ffe5  mov     r8d, 7
0x14001ffeb  mov     [rsp+68h+var_40], r14
0x14001fff0  mov     dl, 2
0x14001fff2  mov     [rsp+68h+var_48], r15
0x14001fff7  mov     rcx, [rcx+40h]
0x14001fffb  call    WPP_RECORDER_SF_sDd
0x140020000  jmp     loc_14001FD5C
0x140020005  call    cs:__imp_PsDereferenceSiloContext
0x14002000c  nop     dword ptr [rax+rax+00h]
0x140020011  jmp     loc_14001FD6D
```
