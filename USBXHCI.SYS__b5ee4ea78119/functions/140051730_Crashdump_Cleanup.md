# Crashdump_Cleanup

- ea: `0x140051730`
- end: `0x14005197f`
- name: `Crashdump_Cleanup`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140051730`
- `0x1400534f8`
- `0x1400536cc`
- `0x14005378c`
- `0x140054118`
- `0x140054bf0`
- `0x140055218`
- `0x140056148`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140051754`
- `ntoskrnl!DbgPrintEx` at `0x14005179c`
- `ntoskrnl!DbgPrintEx` at `0x140051808`
- `ntoskrnl!DbgPrintEx` at `0x14005183b`
- `ntoskrnl!DbgPrintEx` at `0x14005186a`
- `ntoskrnl!DbgPrintEx` at `0x14005192f`
- `ntoskrnl!DbgPrintEx` at `0x140051949`
- `ntoskrnl!DbgPrintEx` at `0x140051964`
- `ntoskrnl!DbgPrintEx` at `0x140051754`
- `ntoskrnl!DbgPrintEx` at `0x14005179c`
- `ntoskrnl!DbgPrintEx` at `0x140051808`
- `ntoskrnl!DbgPrintEx` at `0x14005183b`
- `ntoskrnl!DbgPrintEx` at `0x14005186a`
- `ntoskrnl!DbgPrintEx` at `0x14005192f`
- `ntoskrnl!DbgPrintEx` at `0x140051949`
- `ntoskrnl!DbgPrintEx` at `0x140051964`

## string_xrefs

- `0x14005185d`: `XHCIDUMP: Crashdump_Command_Stop failed with error 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Cleanup(__int64 a1)
{
  unsigned int v2; // edi
  unsigned int i; // esi
  __int64 v4; // rdi
  int v5; // eax
  bool v6; // zf
  __int64 j; // rdi
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  int v12; // edi
  __int64 v13; // rcx
  int v14; // eax

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Cleanup: begin\n");
  v2 = *(_DWORD *)(a1 + 536);
  for ( i = 0; i < v2; ++i )
  {
    v4 = 376LL * i;
    v5 = Crashdump_UsbDevice_Cleanup(v4 + *(_QWORD *)(a1 + 568));
    if ( v5 < 0 )
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_UsbDevice_Cleanup failed with error 0x%X\n", v5);
    if ( *(_BYTE *)(a1 + 625) && (int)Crashdump_UsbDevice_ConfigureEndpointsForSaveState(v4 + *(_QWORD *)(a1 + 568)) < 0 )
      *(_BYTE *)(a1 + 625) = 0;
    v2 = *(_DWORD *)(a1 + 536);
  }
  LODWORD(j) = v2 - 1;
  v6 = (_DWORD)j == 0;
  for ( j = (unsigned int)j; ; v6 = (_DWORD)j == 0 )
  {
    v9 = *(unsigned int *)(a1 + 4 * j + 544);
    if ( v6 )
      break;
    j = (unsigned int)(j - 1);
    v8 = Crashdump_UsbDevice_SuspendPort(*(_QWORD *)(a1 + 568) + 376LL * (unsigned int)j, v9);
    if ( v8 < 0 )
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_UsbDevice_SuspendPort failed with error 0x%X\n", v8);
  }
  v10 = Crashdump_Register_SuspendPort(a1, v9);
  if ( v10 < 0 )
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Register_SuspendPort failed with error 0x%X\n", v10);
  v11 = Crashdump_Command_Stop((__int64 *)(a1 + 328), 1);
  if ( v11 < 0 )
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Command_Stop failed with error 0x%X\n", v11);
  v12 = Crashdump_Register_StopController(a1);
  if ( v12 >= 0 && *(_BYTE *)(a1 + 625) )
  {
    v13 = **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(a1 + 616) + 128LL) + 32LL);
    *(_QWORD *)(v13 + 152) = *(_QWORD *)(a1 + 272);
    *(_DWORD *)(v13 + 128) = *(_DWORD *)(a1 + 280);
    *(_DWORD *)(v13 + 132) = *(_DWORD *)(a1 + 284);
    *(_DWORD *)(v13 + 136) = *(_DWORD *)(a1 + 288);
    *(_DWORD *)(v13 + 140) = *(_DWORD *)(a1 + 292);
    *(_DWORD *)(v13 + 144) = *(_DWORD *)(a1 + 296);
    *(_QWORD *)(v13 + 160) = *(_QWORD *)(a1 + 304);
    *(_OWORD *)(v13 + 176) = *(_OWORD *)(a1 + 312);
    v14 = Crashdump_Register_SaveStateForHybridSleep(a1);
    v12 = v14;
    if ( v14 >= 0 )
      DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Register_SaveStateForHybridSleep succeeded.\n");
    else
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Register_SaveStateForHybridSleep failed with error 0x%X\n", v14);
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Cleanup: end\n");
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140051730  push    rbx
0x140051732  push    rsi
0x140051733  push    rdi
0x140051734  push    r14
0x140051736  push    r15
0x140051738  sub     rsp, 20h
0x14005173c  mov     rbx, rcx
0x14005173f  lea     r8, aXhcidumpCrashd_5; "XHCIDUMP: Crashdump_Cleanup: begin\n"
0x140051746  mov     r14d, 93h
0x14005174c  mov     edx, 3; Level
0x140051751  mov     ecx, r14d; ComponentId
0x140051754  call    cs:__imp_DbgPrintEx
0x14005175b  nop     dword ptr [rax+rax+00h]
0x140051760  mov     edi, [rbx+218h]
0x140051766  xor     esi, esi
0x140051768  lea     r15d, [rsi+1]
0x14005176c  test    edi, edi
0x14005176e  jz      short loc_1400517D8
0x140051770  mov     rcx, [rbx+238h]
0x140051777  mov     eax, esi
0x140051779  imul    rdi, rax, 178h
0x140051780  add     rcx, rdi
0x140051783  call    Crashdump_UsbDevice_Cleanup
0x140051788  test    eax, eax
0x14005178a  jns     short loc_1400517A8
0x14005178c  mov     r9d, eax
0x14005178f  lea     r8, aXhcidumpCrashd_43; "XHCIDUMP: Crashdump_UsbDevice_Cleanup f"...
0x140051796  mov     edx, r15d; Level
0x140051799  mov     ecx, r14d; ComponentId
0x14005179c  call    cs:__imp_DbgPrintEx
0x1400517a3  nop     dword ptr [rax+rax+00h]
0x1400517a8  cmp     byte ptr [rbx+271h], 0
0x1400517af  jz      short loc_1400517CB
0x1400517b1  mov     rcx, [rbx+238h]
0x1400517b8  add     rcx, rdi
0x1400517bb  call    Crashdump_UsbDevice_ConfigureEndpointsForSaveState
0x1400517c0  test    eax, eax
0x1400517c2  jns     short loc_1400517CB
0x1400517c4  mov     byte ptr [rbx+271h], 0
0x1400517cb  mov     edi, [rbx+218h]
0x1400517d1  add     esi, r15d
0x1400517d4  cmp     esi, edi
0x1400517d6  jb      short loc_140051770
0x1400517d8  sub     edi, r15d
0x1400517db  jmp     short loc_140051816
0x1400517dd  dec     edi
0x1400517df  mov     esi, edi
0x1400517e1  imul    rcx, rsi, 178h
0x1400517e8  add     rcx, [rbx+238h]
0x1400517ef  call    Crashdump_UsbDevice_SuspendPort
0x1400517f4  test    eax, eax
0x1400517f6  jns     short loc_140051814
0x1400517f8  mov     r9d, eax
0x1400517fb  lea     r8, aXhcidumpCrashd_6; "XHCIDUMP: Crashdump_UsbDevice_SuspendPo"...
0x140051802  mov     edx, r15d; Level
0x140051805  mov     ecx, r14d; ComponentId
0x140051808  call    cs:__imp_DbgPrintEx
0x14005180f  nop     dword ptr [rax+rax+00h]
0x140051814  test    edi, edi
0x140051816  mov     edx, [rbx+rdi*4+220h]
0x14005181d  jnz     short loc_1400517DD
0x14005181f  mov     rcx, rbx
0x140051822  call    Crashdump_Register_SuspendPort
0x140051827  test    eax, eax
0x140051829  jns     short loc_140051847
0x14005182b  mov     r9d, eax
0x14005182e  lea     r8, aXhcidumpCrashd_39; "XHCIDUMP: Crashdump_Register_SuspendPor"...
0x140051835  mov     edx, r15d; Level
0x140051838  mov     ecx, r14d; ComponentId
0x14005183b  call    cs:__imp_DbgPrintEx
0x140051842  nop     dword ptr [rax+rax+00h]
0x140051847  lea     rcx, [rbx+148h]
0x14005184e  mov     dl, r15b
0x140051851  call    Crashdump_Command_Stop
0x140051856  test    eax, eax
0x140051858  jns     short loc_140051876
0x14005185a  mov     r9d, eax
0x14005185d  lea     r8, aXhcidumpCrashd_34; "XHCIDUMP: Crashdump_Command_Stop failed"...
0x140051864  mov     edx, r15d; Level
0x140051867  mov     ecx, r14d; ComponentId
0x14005186a  call    cs:__imp_DbgPrintEx
0x140051871  nop     dword ptr [rax+rax+00h]
0x140051876  mov     rcx, rbx
0x140051879  call    Crashdump_Register_StopController
0x14005187e  mov     edi, eax
0x140051880  test    eax, eax
0x140051882  js      loc_140051955
0x140051888  cmp     byte ptr [rbx+271h], 0
0x14005188f  jz      loc_140051955
0x140051895  mov     rax, [rbx+268h]
0x14005189c  mov     rcx, [rax+80h]
0x1400518a3  mov     rax, [rcx+20h]
0x1400518a7  mov     rcx, [rax]
0x1400518aa  mov     rax, [rbx+110h]
0x1400518b1  mov     [rcx+98h], rax
0x1400518b8  mov     eax, [rbx+118h]
0x1400518be  mov     [rcx+80h], eax
0x1400518c4  mov     eax, [rbx+11Ch]
0x1400518ca  mov     [rcx+84h], eax
0x1400518d0  mov     eax, [rbx+120h]
0x1400518d6  mov     [rcx+88h], eax
0x1400518dc  mov     eax, [rbx+124h]
0x1400518e2  mov     [rcx+8Ch], eax
0x1400518e8  mov     eax, [rbx+128h]
0x1400518ee  mov     [rcx+90h], eax
0x1400518f4  mov     rax, [rbx+130h]
0x1400518fb  mov     [rcx+0A0h], rax
0x140051902  movups  xmm0, xmmword ptr [rbx+138h]
0x140051909  movdqu  xmmword ptr [rcx+0B0h], xmm0
0x140051911  mov     rcx, rbx
0x140051914  call    Crashdump_Register_SaveStateForHybridSleep
0x140051919  mov     edi, eax
0x14005191b  mov     ecx, r14d; ComponentId
0x14005191e  test    eax, eax
0x140051920  jns     short loc_14005193D
0x140051922  mov     r9d, eax
0x140051925  lea     r8, aXhcidumpCrashd_29; "XHCIDUMP: Crashdump_Register_SaveStateF"...
0x14005192c  mov     edx, r15d; Level
0x14005192f  call    cs:__imp_DbgPrintEx
0x140051936  nop     dword ptr [rax+rax+00h]
0x14005193b  jmp     short loc_140051955
0x14005193d  lea     r8, aXhcidumpCrashd_22; "XHCIDUMP: Crashdump_Register_SaveStateF"...
0x140051944  mov     edx, 3; Level
0x140051949  call    cs:__imp_DbgPrintEx
0x140051950  nop     dword ptr [rax+rax+00h]
0x140051955  lea     r8, aXhcidumpCrashd_52; "XHCIDUMP: Crashdump_Cleanup: end\n"
0x14005195c  mov     edx, 3; Level
0x140051961  mov     ecx, r14d; ComponentId
0x140051964  call    cs:__imp_DbgPrintEx
0x14005196b  nop     dword ptr [rax+rax+00h]
0x140051970  mov     eax, edi
0x140051972  add     rsp, 20h
0x140051976  pop     r15
0x140051978  pop     r14
0x14005197a  pop     rdi
0x14005197b  pop     rsi
0x14005197c  pop     rbx
0x14005197d  retn
```
