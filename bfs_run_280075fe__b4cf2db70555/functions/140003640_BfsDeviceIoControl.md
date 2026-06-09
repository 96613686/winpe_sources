# BfsDeviceIoControl

- ea: `0x140003640`
- end: `0x1400038fa`
- name: `BfsDeviceIoControl`
- size: `698`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001008`
- `0x140003640`
- `0x140009390`
- `0x140009530`
- `0x14000995c`
- `0x140009b9c`
- `0x14000c1b4`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000378f`
- `ntoskrnl!ProbeForRead` at `0x14000378f`
- `ntoskrnl!IofCompleteRequest` at `0x1400038c5`
- `ntoskrnl!IofCompleteRequest` at `0x1400038c5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000389e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000389e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003672`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000388b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003672`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000388b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140003685`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140003685`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003698`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400038aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003698`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400038aa`

## pseudocode

```c
__int64 __fastcall BfsDeviceIoControl(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v4; // r8d
  int v5; // r9d
  unsigned int PolicySizeRequest; // ebx
  int v7; // ecx
  __int64 v8; // rbx
  unsigned int PolicyRequest; // eax
  int v11; // [rsp+20h] [rbp-78h]
  BOOLEAN v12; // [rsp+30h] [rbp-68h]
  __int64 v13; // [rsp+38h] [rbp-60h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-58h]
  __int64 v15; // [rsp+48h] [rbp-50h]
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+50h] [rbp-48h] BYREF
  __int64 *v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v13 = a2;
  KeEnterCriticalRegion();
  v12 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( !v12 )
  {
    PolicySizeRequest = -1073741808;
    *(_DWORD *)(a2 + 48) = -1073741808;
    goto LABEL_29;
  }
  v3 = BfsCheckDeleteList(gBfsFilterHandle, 0);
  PolicySizeRequest = v3;
  if ( v3 >= 0 )
  {
    v8 = *(_QWORD *)(a2 + 184);
    v15 = v8;
    switch ( *(_DWORD *)(v8 + 24) )
    {
      case 0x224008:
        LODWORD(v13) = 0;
        if ( *(_DWORD *)(v8 + 16) >= 8u )
        {
          if ( *(_DWORD *)(v8 + 8) >= 4u )
          {
            PolicySizeRequest = BfsProcessQueryPolicySizeRequest(**(void ***)(a2 + 24), (__int64)&v13);
            **(_DWORD **)(a2 + 24) = v13;
            *(_QWORD *)(a2 + 56) = 4;
            goto LABEL_26;
          }
          *(_QWORD *)(a2 + 56) = 4;
          goto LABEL_20;
        }
        break;
      case 0x22400F:
        Handle = 0;
        if ( *(_DWORD *)(v8 + 16) >= 8u )
        {
          ProbeForRead(*(volatile void **)(v8 + 32), *(unsigned int *)(v8 + 16), 8u);
          Handle = **(HANDLE **)(v8 + 32);
          PolicyRequest = BfsProcessQueryPolicyRequest(Handle, *(char **)(a2 + 112), *(unsigned int *)(v8 + 8));
          goto LABEL_14;
        }
        v7 = -1073741789;
LABEL_21:
        PolicySizeRequest = -1073741789;
        if ( (unsigned int)dword_140019000 <= 3 )
          goto LABEL_27;
        LODWORD(v13) = -1073741789;
        goto LABEL_5;
      case 0x228004:
        PolicyRequest = BfsProcessSetPolicyRequest(*(_QWORD *)(a2 + 24), *(_DWORD *)(v8 + 16));
        goto LABEL_14;
      case 0x228010:
        if ( *(_DWORD *)(v8 + 16) >= 8u )
        {
          PolicyRequest = BfsProcessDeletePolicyEntryRequest(**(void ***)(a2 + 24));
LABEL_14:
          PolicySizeRequest = PolicyRequest;
          *(_DWORD *)(a2 + 48) = PolicyRequest;
          goto LABEL_27;
        }
        break;
      default:
        PolicySizeRequest = -1073741808;
LABEL_26:
        *(_DWORD *)(a2 + 48) = PolicySizeRequest;
        goto LABEL_27;
    }
    *(_QWORD *)(a2 + 56) = 8;
LABEL_20:
    v7 = -1073741789;
    *(_DWORD *)(a2 + 48) = -1073741789;
    goto LABEL_21;
  }
  v7 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v13) = v3;
LABEL_5:
    v17 = &v13;
    v18 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v7, (int)&byte_140016D91, v4, v5, v11, &v16);
  }
LABEL_27:
  KeEnterCriticalRegion();
  ExReleaseRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
LABEL_29:
  IofCompleteRequest((PIRP)a2, 0);
  return PolicySizeRequest;
}

```

## disassembly

```asm
0x140003640  mov     [rsp+arg_0], rbx
0x140003645  mov     [rsp+arg_10], rdi
0x14000364a  push    r14
0x14000364c  sub     rsp, 90h
0x140003653  mov     rax, cs:__security_cookie
0x14000365a  xor     rax, rsp
0x14000365d  mov     [rsp+98h+var_18], rax
0x140003665  mov     rdi, rdx
0x140003668  mov     [rsp+98h+var_60], rdx
0x14000366d  mov     ebx, 0C0000001h
0x140003672  call    cs:__imp_KeEnterCriticalRegion
0x140003679  nop     dword ptr [rax+rax+00h]
0x14000367e  lea     rcx, gBfsRundownProtection; RunRef
0x140003685  call    cs:__imp_ExAcquireRundownProtection
0x14000368c  nop     dword ptr [rax+rax+00h]
0x140003691  mov     r14b, al
0x140003694  mov     [rsp+98h+var_68], al
0x140003698  call    cs:__imp_KeLeaveCriticalRegion
0x14000369f  nop     dword ptr [rax+rax+00h]
0x1400036a4  test    r14b, r14b
0x1400036a7  jz      loc_1400038B8
0x1400036ad  xor     edx, edx
0x1400036af  mov     rcx, cs:gBfsFilterHandle
0x1400036b6  call    BfsCheckDeleteList
0x1400036bb  mov     ebx, eax
0x1400036bd  test    eax, eax
0x1400036bf  jns     short loc_140003702
0x1400036c1  mov     ecx, cs:dword_140019000; int
0x1400036c7  cmp     ecx, 3
0x1400036ca  jbe     loc_140003886
0x1400036d0  mov     dword ptr [rsp+98h+var_60], eax
0x1400036d4  lea     rax, [rsp+98h+var_60]
0x1400036d9  mov     [rsp+98h+var_28], rax
0x1400036de  mov     [rsp+98h+var_20], 4
0x1400036e7  lea     rax, [rsp+98h+var_48]
0x1400036ec  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x1400036f1  lea     rdx, byte_140016D91; int
0x1400036f8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400036fd  jmp     loc_140003886
0x140003702  mov     rbx, [rdi+0B8h]
0x140003709  mov     [rsp+98h+var_50], rbx
0x14000370e  mov     ecx, [rbx+18h]
0x140003711  sub     ecx, 224008h
0x140003717  jz      loc_14000381A
0x14000371d  sub     ecx, 7
0x140003720  jz      short loc_140003767
0x140003722  sub     ecx, 3FF5h
0x140003728  jz      short loc_140003751
0x14000372a  cmp     ecx, 0Ch
0x14000372d  jz      short loc_140003739
0x14000372f  mov     ebx, 0C0000010h
0x140003734  jmp     loc_140003883
0x140003739  cmp     dword ptr [rbx+10h], 8
0x14000373d  jb      loc_140003828
0x140003743  mov     rcx, [rdi+18h]
0x140003747  mov     rcx, [rcx]
0x14000374a  call    BfsProcessDeletePolicyEntryRequest
0x14000374f  jmp     short loc_14000375D
0x140003751  mov     edx, [rbx+10h]
0x140003754  mov     rcx, [rdi+18h]
0x140003758  call    BfsProcessSetPolicyRequest
0x14000375d  mov     ebx, eax
0x14000375f  mov     [rdi+30h], eax
0x140003762  jmp     loc_140003886
0x140003767  mov     [rsp+98h+Handle], 0
0x140003770  mov     eax, [rbx+10h]
0x140003773  cmp     eax, 8
0x140003776  jnb     short loc_140003782
0x140003778  mov     ecx, 0C0000023h
0x14000377d  jmp     loc_140003838
0x140003782  mov     rdx, rax; Length
0x140003785  mov     r8d, 8; Alignment
0x14000378b  mov     rcx, [rbx+20h]; Address
0x14000378f  call    cs:__imp_ProbeForRead
0x140003796  nop     dword ptr [rax+rax+00h]
0x14000379b  mov     rax, [rbx+20h]
0x14000379f  mov     rcx, [rax]; int
0x1400037a2  mov     [rsp+98h+Handle], rcx
0x1400037a7  jmp     short loc_140003808
0x1400037a9  mov     ebx, eax
0x1400037ab  mov     rdi, [rsp+98h+var_60]
0x1400037b0  mov     [rdi+30h], eax
0x1400037b3  test    eax, eax
0x1400037b5  jns     short loc_1400037F9
0x1400037b7  mov     eax, cs:dword_140019000
0x1400037bd  cmp     eax, 3
0x1400037c0  jbe     short loc_1400037EF
0x1400037c2  mov     dword ptr [rsp+98h+var_60], ebx
0x1400037c6  lea     rax, [rsp+98h+var_60]
0x1400037cb  mov     [rsp+98h+var_28], rax
0x1400037d0  mov     [rsp+98h+var_20], 4
0x1400037d9  lea     rax, [rsp+98h+var_48]
0x1400037de  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x1400037e3  lea     rdx, byte_140016D91; int
0x1400037ea  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400037ef  mov     r14b, [rsp+98h+var_68]
0x1400037f4  jmp     loc_140003886
0x1400037f9  mov     rcx, [rsp+98h+Handle]; Handle
0x1400037fe  mov     r14b, [rsp+98h+var_68]
0x140003803  mov     rbx, [rsp+98h+var_50]
0x140003808  mov     r8d, [rbx+8]; Length
0x14000380c  mov     rdx, [rdi+70h]; void *
0x140003810  call    BfsProcessQueryPolicyRequest
0x140003815  jmp     loc_14000375D
0x14000381a  mov     dword ptr [rsp+98h+var_60], 0
0x140003822  cmp     dword ptr [rbx+10h], 8
0x140003826  jnb     short loc_14000384E
0x140003828  mov     qword ptr [rdi+38h], 8
0x140003830  mov     ecx, 0C0000023h
0x140003835  mov     [rdi+30h], ecx
0x140003838  mov     ebx, ecx
0x14000383a  mov     eax, cs:dword_140019000
0x140003840  cmp     eax, 3
0x140003843  jbe     short loc_140003886
0x140003845  mov     dword ptr [rsp+98h+var_60], ecx
0x140003849  jmp     loc_1400036D4
0x14000384e  cmp     dword ptr [rbx+8], 4
0x140003852  jnb     short loc_14000385E
0x140003854  mov     qword ptr [rdi+38h], 4
0x14000385c  jmp     short loc_140003830
0x14000385e  mov     rcx, [rdi+18h]
0x140003862  lea     rdx, [rsp+98h+var_60]
0x140003867  mov     rcx, [rcx]
0x14000386a  call    BfsProcessQueryPolicySizeRequest
0x14000386f  mov     ebx, eax
0x140003871  mov     rcx, [rdi+18h]
0x140003875  mov     eax, dword ptr [rsp+98h+var_60]
0x140003879  mov     [rcx], eax
0x14000387b  mov     qword ptr [rdi+38h], 4
0x140003883  mov     [rdi+30h], ebx
0x140003886  test    r14b, r14b
0x140003889  jz      short loc_1400038B8
0x14000388b  call    cs:__imp_KeEnterCriticalRegion
0x140003892  nop     dword ptr [rax+rax+00h]
0x140003897  lea     rcx, gBfsRundownProtection; RunRef
0x14000389e  call    cs:__imp_ExReleaseRundownProtection
0x1400038a5  nop     dword ptr [rax+rax+00h]
0x1400038aa  call    cs:__imp_KeLeaveCriticalRegion
0x1400038b1  nop     dword ptr [rax+rax+00h]
0x1400038b6  jmp     short loc_1400038C0
0x1400038b8  mov     ebx, 0C0000010h
0x1400038bd  mov     [rdi+30h], ebx
0x1400038c0  xor     edx, edx; PriorityBoost
0x1400038c2  mov     rcx, rdi; Irp
0x1400038c5  call    cs:__imp_IofCompleteRequest
0x1400038cc  nop     dword ptr [rax+rax+00h]
0x1400038d1  mov     eax, ebx
0x1400038d3  mov     rcx, [rsp+98h+var_18]
0x1400038db  xor     rcx, rsp; StackCookie
0x1400038de  call    __security_check_cookie
0x1400038e3  lea     r11, [rsp+98h+var_8]
0x1400038eb  mov     rbx, [r11+10h]
0x1400038ef  mov     rdi, [r11+20h]
0x1400038f3  mov     rsp, r11
0x1400038f6  pop     r14
0x1400038f8  retn
```
