# VidExoBrokerIoctlReceive

- ea: `0x140078c58`
- end: `0x140078e99`
- name: `VidExoBrokerIoctlReceive`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140038040`

## callees

- `0x140022340`
- `0x140023fe0`
- `0x140024088`
- `0x1400248f4`
- `0x1400386a0`
- `0x140078c58`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x140078d26`
- `ntoskrnl!IoGetRequestorProcess` at `0x140078d26`
- `ntoskrnl!ObDuplicateObject` at `0x140078d94`
- `ntoskrnl!ObDuplicateObject` at `0x140078d94`
- `ntoskrnl!IofCompleteRequest` at `0x140078e15`
- `ntoskrnl!IofCompleteRequest` at `0x140078e15`
- `ntoskrnl!ZwClose` at `0x140078dbf`
- `ntoskrnl!ZwClose` at `0x140078dbf`
- `ntoskrnl!PsGetCurrentProcess` at `0x140078d3a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140078d3a`

## string_xrefs

- `0x140078c91`: `VidExoBrokerIoctlReceive`
- `0x140078ddc`: `VidExoBrokerIoctlReceive`
- `0x140078e42`: `VidExoBrokerIoctlReceive`
- `0x140078e79`: `VidExoBrokerIoctlReceive`
- `0x140078c8a`: `onecore\vm\vid\sys\driver\videxobroker.c`
- `0x140078dd5`: `onecore\vm\vid\sys\driver\videxobroker.c`
- `0x140078e3b`: `onecore\vm\vid\sys\driver\videxobroker.c`
- `0x140078e72`: `onecore\vm\vid\sys\driver\videxobroker.c`

## pseudocode

```c
__int64 __fastcall VidExoBrokerIoctlReceive(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v8; // rax
  IRP *v9; // rbp
  int v10; // ebx
  __int64 v11; // r8
  unsigned int *v12; // rsi
  unsigned __int64 v13; // rax
  unsigned int v14; // ecx
  unsigned int v15; // r15d
  PEPROCESS RequestorProcess; // rbx
  __int64 CurrentProcess; // rcx
  char *v18; // r12
  char *v19; // rax
  __int64 v20; // rdi
  int v22; // [rsp+38h] [rbp-70h]
  char *v23; // [rsp+40h] [rbp-68h]
  struct _KPROCESS *v24; // [rsp+48h] [rbp-60h]
  __int64 v25; // [rsp+50h] [rbp-58h]

  v8 = VidExoBrokerpFindAndDequeueSendIrpForFileObject();
  v9 = (IRP *)v8;
  if ( !v8 )
  {
    v10 = -1073741811;
    VidTraceErrorInternal0("VidExoBrokerIoctlReceive", "onecore\\vm\\vid\\sys\\driver\\videxobroker.c", 186);
LABEL_23:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidExoBrokerIoctlReceive",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\videxobroker.c",
      316,
      v10,
      a1 + 656);
    return (unsigned int)v10;
  }
  if ( a4 < 0x10 )
  {
    v10 = -1073741306;
    v11 = 199;
LABEL_21:
    VidTraceErrorInternal0("VidExoBrokerIoctlReceive", "onecore\\vm\\vid\\sys\\driver\\videxobroker.c", v11);
    VidExoBrokerpQueueSendIrp(a1, v9);
    goto LABEL_22;
  }
  v12 = *(unsigned int **)(v8 + 24);
  *a3 = 16;
  a3[1] = v12[1];
  v13 = 8LL * v12[1];
  if ( v13 > 0xFFFFFFFF || (v14 = v13 + 16, (unsigned int)(v13 + 16) < 0x10) )
  {
    v10 = -1073741306;
    v11 = 211;
    goto LABEL_21;
  }
  a3[2] = v14;
  a3[3] = v12[3];
  v15 = v14 + v12[3];
  if ( v15 < v14 )
  {
    v10 = -1073741306;
    v11 = 221;
    goto LABEL_21;
  }
  if ( a4 < v15 )
  {
    v10 = -2147483643;
    *a5 = 16;
    v11 = 243;
    goto LABEL_21;
  }
  RequestorProcess = IoGetRequestorProcess(v9);
  v24 = RequestorProcess;
  CurrentProcess = PsGetCurrentProcess();
  v25 = CurrentProcess;
  v18 = (char *)a3 + *a3;
  v19 = (char *)v12 + *v12;
  v23 = v19;
  v20 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v20 >= v12[1] )
    {
      memmove((char *)a3 + a3[2], (char *)v12 + v12[2], v12[3]);
      v10 = 0;
      *a5 = v15;
      goto LABEL_18;
    }
    LOBYTE(v22) = 1;
    v10 = ObDuplicateObject(RequestorProcess, *(_QWORD *)&v19[8 * v20], CurrentProcess, &v18[8 * v20], 0, 0, 10, v22);
    if ( v10 < 0 )
      break;
    v19 = v23;
    v20 = (unsigned int)(v20 + 1);
    RequestorProcess = v24;
    CurrentProcess = v25;
  }
  while ( (_DWORD)v20 )
  {
    LODWORD(v20) = v20 - 1;
    ZwClose(*(HANDLE *)&v18[8 * (unsigned int)v20]);
  }
  VidTraceErrorInternal0("VidExoBrokerIoctlReceive", "onecore\\vm\\vid\\sys\\driver\\videxobroker.c", 282);
LABEL_18:
  v9->IoStatus.Status = v10;
  IofCompleteRequest(v9, 0);
LABEL_22:
  if ( v10 < 0 )
    goto LABEL_23;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140078c58  push    rbx
0x140078c5a  push    rbp
0x140078c5b  push    rsi
0x140078c5c  push    rdi
0x140078c5d  push    r12
0x140078c5f  push    r13
0x140078c61  push    r14
0x140078c63  push    r15
0x140078c65  sub     rsp, 68h
0x140078c69  mov     ebx, r9d
0x140078c6c  mov     r14, r8
0x140078c6f  mov     r13, rcx
0x140078c72  call    VidExoBrokerpFindAndDequeueSendIrpForFileObject
0x140078c77  mov     rbp, rax
0x140078c7a  test    rax, rax
0x140078c7d  jnz     short loc_140078CA2
0x140078c7f  mov     ebx, 0C000000Dh
0x140078c84  mov     r8d, 0BAh
0x140078c8a  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140078c91  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140078c98  call    VidTraceErrorInternal0
0x140078c9d  jmp     loc_140078E5D
0x140078ca2  mov     edx, 10h
0x140078ca7  cmp     ebx, edx
0x140078ca9  jnb     short loc_140078CBB
0x140078cab  mov     ebx, 0C0000206h
0x140078cb0  mov     r8d, 0C7h
0x140078cb6  jmp     loc_140078E3B
0x140078cbb  mov     rsi, [rax+18h]
0x140078cbf  mov     ecx, 0FFFFFFFFh
0x140078cc4  mov     [r14], edx
0x140078cc7  mov     eax, [rsi+4]
0x140078cca  mov     [r14+4], eax
0x140078cce  mov     eax, [rsi+4]
0x140078cd1  shl     rax, 3
0x140078cd5  cmp     rax, rcx
0x140078cd8  ja      loc_140078E30
0x140078cde  lea     ecx, [rax+10h]
0x140078ce1  cmp     ecx, edx
0x140078ce3  jb      loc_140078E30
0x140078ce9  mov     [r14+8], ecx
0x140078ced  mov     eax, [rsi+0Ch]
0x140078cf0  mov     [r14+0Ch], eax
0x140078cf4  mov     r15d, [rsi+0Ch]
0x140078cf8  add     r15d, ecx
0x140078cfb  cmp     r15d, ecx
0x140078cfe  jb      loc_140078E23
0x140078d04  cmp     ebx, r15d
0x140078d07  jnb     short loc_140078D23
0x140078d09  mov     rax, [rsp+0A8h+arg_20]
0x140078d11  mov     ebx, 80000005h
0x140078d16  mov     [rax], edx
0x140078d18  mov     r8d, 0F3h
0x140078d1e  jmp     loc_140078E3B
0x140078d23  mov     rcx, rbp; Irp
0x140078d26  call    cs:__imp_IoGetRequestorProcess
0x140078d2d  nop     dword ptr [rax+rax+00h]
0x140078d32  mov     rbx, rax
0x140078d35  mov     [rsp+0A8h+var_60], rax
0x140078d3a  call    cs:__imp_PsGetCurrentProcess
0x140078d41  nop     dword ptr [rax+rax+00h]
0x140078d46  mov     r12d, [r14]
0x140078d49  mov     rcx, rax
0x140078d4c  mov     [rsp+0A8h+var_58], rax
0x140078d51  add     r12, r14
0x140078d54  mov     eax, [rsi]
0x140078d56  add     rax, rsi
0x140078d59  mov     [rsp+0A8h+var_68], rax
0x140078d5e  xor     edi, edi
0x140078d60  cmp     edi, [rsi+4]
0x140078d63  jnb     loc_140078DEA
0x140078d69  mov     rdx, [rax+rdi*8]
0x140078d6d  lea     r9, [r12+rdi*8]
0x140078d71  mov     [rsp+0A8h+var_70], 1
0x140078d76  mov     r8, rcx
0x140078d79  mov     [rsp+0A8h+var_78], 0Ah
0x140078d81  mov     rcx, rbx
0x140078d84  mov     [rsp+0A8h+var_80], 0
0x140078d8c  mov     dword ptr [rsp+0A8h+var_88], 0
0x140078d94  call    cs:__imp_ObDuplicateObject
0x140078d9b  nop     dword ptr [rax+rax+00h]
0x140078da0  mov     ebx, eax
0x140078da2  test    eax, eax
0x140078da4  js      short loc_140078DCB
0x140078da6  mov     rax, [rsp+0A8h+var_68]
0x140078dab  inc     edi
0x140078dad  mov     rbx, [rsp+0A8h+var_60]
0x140078db2  mov     rcx, [rsp+0A8h+var_58]
0x140078db7  jmp     short loc_140078D60
0x140078db9  dec     edi
0x140078dbb  mov     rcx, [r12+rdi*8]; Handle
0x140078dbf  call    cs:__imp_ZwClose
0x140078dc6  nop     dword ptr [rax+rax+00h]
0x140078dcb  test    edi, edi
0x140078dcd  jnz     short loc_140078DB9
0x140078dcf  mov     r8d, 11Ah
0x140078dd5  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140078ddc  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140078de3  call    VidTraceErrorInternal0
0x140078de8  jmp     short loc_140078E0D
0x140078dea  mov     edx, [rsi+8]
0x140078ded  mov     ecx, [r14+8]
0x140078df1  add     rdx, rsi; Src
0x140078df4  mov     r8d, [rsi+0Ch]; Size
0x140078df8  add     rcx, r14; void *
0x140078dfb  call    memmove
0x140078e00  mov     rax, [rsp+0A8h+arg_20]
0x140078e08  xor     ebx, ebx
0x140078e0a  mov     [rax], r15d
0x140078e0d  xor     edx, edx; PriorityBoost
0x140078e0f  mov     [rbp+30h], ebx
0x140078e12  mov     rcx, rbp; Irp
0x140078e15  call    cs:__imp_IofCompleteRequest
0x140078e1c  nop     dword ptr [rax+rax+00h]
0x140078e21  jmp     short loc_140078E59
0x140078e23  mov     ebx, 0C0000206h
0x140078e28  mov     r8d, 0DDh
0x140078e2e  jmp     short loc_140078E3B
0x140078e30  mov     ebx, 0C0000206h
0x140078e35  mov     r8d, 0D3h
0x140078e3b  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140078e42  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140078e49  call    VidTraceErrorInternal0
0x140078e4e  mov     rdx, rbp
0x140078e51  mov     rcx, r13
0x140078e54  call    VidExoBrokerpQueueSendIrp
0x140078e59  test    ebx, ebx
0x140078e5b  jns     short loc_140078E85
0x140078e5d  lea     rax, [r13+290h]
0x140078e64  mov     r9d, ebx
0x140078e67  mov     r8d, 13Ch
0x140078e6d  mov     [rsp+0A8h+var_88], rax
0x140078e72  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140078e79  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140078e80  call    VidTraceErrorStatusPartitionInternal0
0x140078e85  mov     eax, ebx
0x140078e87  add     rsp, 68h
0x140078e8b  pop     r15
0x140078e8d  pop     r14
0x140078e8f  pop     r13
0x140078e91  pop     r12
0x140078e93  pop     rdi
0x140078e94  pop     rsi
0x140078e95  pop     rbp
0x140078e96  pop     rbx
0x140078e97  retn
```
