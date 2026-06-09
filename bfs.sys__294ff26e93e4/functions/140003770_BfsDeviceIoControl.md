# BfsDeviceIoControl

- ea: `0x140003770`
- end: `0x140003a2a`
- name: `BfsDeviceIoControl`
- size: `698`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001008`
- `0x140003770`
- `0x140009520`
- `0x1400096c0`
- `0x140009aec`
- `0x140009d2c`
- `0x14000c344`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400038bf`
- `ntoskrnl!ProbeForRead` at `0x1400038bf`
- `ntoskrnl!IofCompleteRequest` at `0x1400039f5`
- `ntoskrnl!IofCompleteRequest` at `0x1400039f5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400039ce`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400039ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400037a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400039bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400037a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400039bb`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400037b5`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400037b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400037c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400039da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400037c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400039da`

## pseudocode

```c
__int64 __fastcall BfsDeviceIoControl(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
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
    v6 = -1073741808;
    *(_DWORD *)(a2 + 48) = -1073741808;
    goto LABEL_29;
  }
  v3 = BfsCheckDeleteList(gBfsFilterHandle, 0);
  v6 = v3;
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
            v6 = BfsProcessQueryPolicySizeRequest(**(_QWORD **)(a2 + 24), &v13);
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
          PolicyRequest = BfsProcessQueryPolicyRequest(Handle, *(void **)(a2 + 112), *(unsigned int *)(v8 + 8));
          goto LABEL_14;
        }
        v7 = -1073741789;
LABEL_21:
        v6 = -1073741789;
        if ( (unsigned int)dword_140019000 <= 3 )
          goto LABEL_27;
        LODWORD(v13) = -1073741789;
        goto LABEL_5;
      case 0x228004:
        PolicyRequest = BfsProcessSetPolicyRequest(*(_QWORD *)(a2 + 24), *(unsigned int *)(v8 + 16));
        goto LABEL_14;
      case 0x228010:
        if ( *(_DWORD *)(v8 + 16) >= 8u )
        {
          PolicyRequest = BfsProcessDeletePolicyEntryRequest(**(_QWORD **)(a2 + 24));
LABEL_14:
          v6 = PolicyRequest;
          *(_DWORD *)(a2 + 48) = PolicyRequest;
          goto LABEL_27;
        }
        break;
      default:
        v6 = -1073741808;
LABEL_26:
        *(_DWORD *)(a2 + 48) = v6;
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
  return v6;
}

```

## disassembly

```asm
0x140003770  mov     [rsp+arg_0], rbx
0x140003775  mov     [rsp+arg_10], rdi
0x14000377a  push    r14
0x14000377c  sub     rsp, 90h
0x140003783  mov     rax, cs:__security_cookie
0x14000378a  xor     rax, rsp
0x14000378d  mov     [rsp+98h+var_18], rax
0x140003795  mov     rdi, rdx
0x140003798  mov     [rsp+98h+var_60], rdx
0x14000379d  mov     ebx, 0C0000001h
0x1400037a2  call    cs:__imp_KeEnterCriticalRegion
0x1400037a9  nop     dword ptr [rax+rax+00h]
0x1400037ae  lea     rcx, gBfsRundownProtection; RunRef
0x1400037b5  call    cs:__imp_ExAcquireRundownProtection
0x1400037bc  nop     dword ptr [rax+rax+00h]
0x1400037c1  mov     r14b, al
0x1400037c4  mov     [rsp+98h+var_68], al
0x1400037c8  call    cs:__imp_KeLeaveCriticalRegion
0x1400037cf  nop     dword ptr [rax+rax+00h]
0x1400037d4  test    r14b, r14b
0x1400037d7  jz      loc_1400039E8
0x1400037dd  xor     edx, edx
0x1400037df  mov     rcx, cs:gBfsFilterHandle
0x1400037e6  call    BfsCheckDeleteList
0x1400037eb  mov     ebx, eax
0x1400037ed  test    eax, eax
0x1400037ef  jns     short loc_140003832
0x1400037f1  mov     ecx, cs:dword_140019000; int
0x1400037f7  cmp     ecx, 3
0x1400037fa  jbe     loc_1400039B6
0x140003800  mov     dword ptr [rsp+98h+var_60], eax
0x140003804  lea     rax, [rsp+98h+var_60]
0x140003809  mov     [rsp+98h+var_28], rax
0x14000380e  mov     [rsp+98h+var_20], 4
0x140003817  lea     rax, [rsp+98h+var_48]
0x14000381c  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x140003821  lea     rdx, byte_140016D91; int
0x140003828  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000382d  jmp     loc_1400039B6
0x140003832  mov     rbx, [rdi+0B8h]
0x140003839  mov     [rsp+98h+var_50], rbx
0x14000383e  mov     ecx, [rbx+18h]
0x140003841  sub     ecx, 224008h
0x140003847  jz      loc_14000394A
0x14000384d  sub     ecx, 7
0x140003850  jz      short loc_140003897
0x140003852  sub     ecx, 3FF5h
0x140003858  jz      short loc_140003881
0x14000385a  cmp     ecx, 0Ch
0x14000385d  jz      short loc_140003869
0x14000385f  mov     ebx, 0C0000010h
0x140003864  jmp     loc_1400039B3
0x140003869  cmp     dword ptr [rbx+10h], 8
0x14000386d  jb      loc_140003958
0x140003873  mov     rcx, [rdi+18h]
0x140003877  mov     rcx, [rcx]
0x14000387a  call    BfsProcessDeletePolicyEntryRequest
0x14000387f  jmp     short loc_14000388D
0x140003881  mov     edx, [rbx+10h]
0x140003884  mov     rcx, [rdi+18h]
0x140003888  call    BfsProcessSetPolicyRequest
0x14000388d  mov     ebx, eax
0x14000388f  mov     [rdi+30h], eax
0x140003892  jmp     loc_1400039B6
0x140003897  mov     [rsp+98h+Handle], 0
0x1400038a0  mov     eax, [rbx+10h]
0x1400038a3  cmp     eax, 8
0x1400038a6  jnb     short loc_1400038B2
0x1400038a8  mov     ecx, 0C0000023h
0x1400038ad  jmp     loc_140003968
0x1400038b2  mov     rdx, rax; Length
0x1400038b5  mov     r8d, 8; Alignment
0x1400038bb  mov     rcx, [rbx+20h]; Address
0x1400038bf  call    cs:__imp_ProbeForRead
0x1400038c6  nop     dword ptr [rax+rax+00h]
0x1400038cb  mov     rax, [rbx+20h]
0x1400038cf  mov     rcx, [rax]; int
0x1400038d2  mov     [rsp+98h+Handle], rcx
0x1400038d7  jmp     short loc_140003938
0x1400038d9  mov     ebx, eax
0x1400038db  mov     rdi, [rsp+98h+var_60]
0x1400038e0  mov     [rdi+30h], eax
0x1400038e3  test    eax, eax
0x1400038e5  jns     short loc_140003929
0x1400038e7  mov     eax, cs:dword_140019000
0x1400038ed  cmp     eax, 3
0x1400038f0  jbe     short loc_14000391F
0x1400038f2  mov     dword ptr [rsp+98h+var_60], ebx
0x1400038f6  lea     rax, [rsp+98h+var_60]
0x1400038fb  mov     [rsp+98h+var_28], rax
0x140003900  mov     [rsp+98h+var_20], 4
0x140003909  lea     rax, [rsp+98h+var_48]
0x14000390e  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x140003913  lea     rdx, byte_140016D91; int
0x14000391a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000391f  mov     r14b, [rsp+98h+var_68]
0x140003924  jmp     loc_1400039B6
0x140003929  mov     rcx, [rsp+98h+Handle]; Handle
0x14000392e  mov     r14b, [rsp+98h+var_68]
0x140003933  mov     rbx, [rsp+98h+var_50]
0x140003938  mov     r8d, [rbx+8]; Length
0x14000393c  mov     rdx, [rdi+70h]; void *
0x140003940  call    BfsProcessQueryPolicyRequest
0x140003945  jmp     loc_14000388D
0x14000394a  mov     dword ptr [rsp+98h+var_60], 0
0x140003952  cmp     dword ptr [rbx+10h], 8
0x140003956  jnb     short loc_14000397E
0x140003958  mov     qword ptr [rdi+38h], 8
0x140003960  mov     ecx, 0C0000023h
0x140003965  mov     [rdi+30h], ecx
0x140003968  mov     ebx, ecx
0x14000396a  mov     eax, cs:dword_140019000
0x140003970  cmp     eax, 3
0x140003973  jbe     short loc_1400039B6
0x140003975  mov     dword ptr [rsp+98h+var_60], ecx
0x140003979  jmp     loc_140003804
0x14000397e  cmp     dword ptr [rbx+8], 4
0x140003982  jnb     short loc_14000398E
0x140003984  mov     qword ptr [rdi+38h], 4
0x14000398c  jmp     short loc_140003960
0x14000398e  mov     rcx, [rdi+18h]
0x140003992  lea     rdx, [rsp+98h+var_60]
0x140003997  mov     rcx, [rcx]
0x14000399a  call    BfsProcessQueryPolicySizeRequest
0x14000399f  mov     ebx, eax
0x1400039a1  mov     rcx, [rdi+18h]
0x1400039a5  mov     eax, dword ptr [rsp+98h+var_60]
0x1400039a9  mov     [rcx], eax
0x1400039ab  mov     qword ptr [rdi+38h], 4
0x1400039b3  mov     [rdi+30h], ebx
0x1400039b6  test    r14b, r14b
0x1400039b9  jz      short loc_1400039E8
0x1400039bb  call    cs:__imp_KeEnterCriticalRegion
0x1400039c2  nop     dword ptr [rax+rax+00h]
0x1400039c7  lea     rcx, gBfsRundownProtection; RunRef
0x1400039ce  call    cs:__imp_ExReleaseRundownProtection
0x1400039d5  nop     dword ptr [rax+rax+00h]
0x1400039da  call    cs:__imp_KeLeaveCriticalRegion
0x1400039e1  nop     dword ptr [rax+rax+00h]
0x1400039e6  jmp     short loc_1400039F0
0x1400039e8  mov     ebx, 0C0000010h
0x1400039ed  mov     [rdi+30h], ebx
0x1400039f0  xor     edx, edx; PriorityBoost
0x1400039f2  mov     rcx, rdi; Irp
0x1400039f5  call    cs:__imp_IofCompleteRequest
0x1400039fc  nop     dword ptr [rax+rax+00h]
0x140003a01  mov     eax, ebx
0x140003a03  mov     rcx, [rsp+98h+var_18]
0x140003a0b  xor     rcx, rsp; StackCookie
0x140003a0e  call    __security_check_cookie
0x140003a13  lea     r11, [rsp+98h+var_8]
0x140003a1b  mov     rbx, [r11+10h]
0x140003a1f  mov     rdi, [r11+20h]
0x140003a23  mov     rsp, r11
0x140003a26  pop     r14
0x140003a28  retn
```
