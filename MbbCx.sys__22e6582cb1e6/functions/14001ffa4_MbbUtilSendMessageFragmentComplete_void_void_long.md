# MbbUtilSendMessageFragmentComplete(void *,void *,long)

- ea: `0x14001ffa4`
- end: `0x14002032a`
- name: `?MbbUtilSendMessageFragmentComplete@@YAXPEAX0J@Z`
- size: `902`
- prototype: `void __fastcall(void *, _QWORD *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000efa4`

## callees

- `0x1400010b4`
- `0x140001db8`
- `0x14000d684`
- `0x14001a87c`
- `0x14001b818`
- `0x14001ddf4`
- `0x14001ffa4`
- `0x140020330`
- `0x1400244b4`
- `0x14003e100`
- `0x140041664`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140020033`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020033`

## pseudocode

```c
void __fastcall MbbUtilSendMessageFragmentComplete(void *a1, _QWORD *a2, int a3)
{
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  __int64 v6; // r14
  int v7; // esi
  int v8; // ebx
  int v9; // edx
  int v10; // r8d
  int v11; // ebx
  char (near **CommandString)[32]; // r9
  __int64 v13; // rax
  int v14; // edx
  int *v15; // rcx
  int *v16; // rax
  int v17; // ecx
  _DWORD *v18; // rax
  unsigned int v19; // [rsp+A0h] [rbp-29h] BYREF
  int v20; // [rsp+A4h] [rbp-25h] BYREF
  int v21; // [rsp+A8h] [rbp-21h] BYREF
  BOOL v22; // [rsp+ACh] [rbp-1Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23[2]; // [rsp+B0h] [rbp-19h] BYREF
  BOOL *v24; // [rsp+D0h] [rbp+7h]
  __int64 v25; // [rsp+D8h] [rbp+Fh]
  int *v26; // [rsp+E0h] [rbp+17h]
  __int64 v27; // [rsp+E8h] [rbp+1Fh]

  v3 = a2 - 2;
  v4 = *(a2 - 1);
  v19 = a3 != 0 ? 0xC0000001 : 0;
  v6 = *(_QWORD *)(v4 + 48);
  v7 = *(_DWORD *)(v4 + 588);
  MbbReqMgrLockManager((struct _MBB_REQUEST_MANAGER *)v6);
  MbbAllocMgrFree(v3);
  v8 = ++*(_DWORD *)(v4 + 636);
  if ( v19 )
    *(_DWORD *)(v4 + 640) = v19;
  else
    v19 = *(_DWORD *)(v4 + 640);
  KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 176), *(_BYTE *)(v6 + 184));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_DDddd(WPP_GLOBAL_Control->DeviceExtension, v9, v10, 20);
  }
  if ( v8 == v7 )
  {
    v11 = -1;
    v20 = 0;
    CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)(v4 + 604));
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)CommandString + v13) );
    MbbWriteEvent(
      &CID_SEND_COMPLETE,
      (LPCGUID)(v4 + 24),
      0,
      8u,
      v4 + 432,
      8,
      v4 + 16,
      4,
      v4 + 604,
      16,
      CommandString,
      v13 + 1,
      v4 + 620,
      4,
      &v20,
      4,
      0,
      0,
      &v19,
      4);
    MbxQueueMessage(*(_QWORD *)(v4 + 48), 2, v4);
    if ( a3 == -1073741643 )
    {
      if ( (unsigned int)dword_14005E0C8 > 5
        && (qword_14005E0D8 & 0x400000000000LL) != 0
        && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
      {
        v15 = *(int **)(v4 + 80);
        if ( v15 )
          v11 = *v15;
        v21 = v11;
        v27 = 4;
        v25 = 4;
        v22 = v15 != 0;
        v26 = &v21;
        v24 = &v22;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14005E0C8, (unsigned __int8 *)word_14005899A, 0, 0, 4u, v23);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = *(int **)(v4 + 80);
        if ( v16 )
          v17 = *v16;
        else
          LOBYTE(v17) = -1;
        WPP_RECORDER_SF_ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          4,
          21,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          *(_DWORD *)(v4 + 16),
          *(_DWORD *)(v4 + 20),
          v17);
      }
      v18 = *(_DWORD **)(v4 + 80);
      if ( v18 && *v18 == 234946828 )
      {
        if ( (unsigned int)dword_14005E0C8 > 5 )
        {
          v14 = qword_14005E0E0;
          if ( (qword_14005E0D8 & 0x400000000000LL) != 0 && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
            tlgWriteTransfer_EtwWriteTransfer(
              (__int64)&dword_14005E0C8,
              (unsigned __int8 *)byte_1400588F9,
              0,
              0,
              2u,
              v23);
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            9,
            22,
            (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
            *(_DWORD *)(v4 + 16));
        }
      }
    }
  }
  else
  {
    MbbUtilSendMessageFragments((struct _MBB_REQUEST_CONTEXT *)v4);
  }
}

```

## disassembly

```asm
0x14001ffa4  mov     [rsp-8+arg_0], rbx
0x14001ffa9  mov     [rsp-8+arg_10], rsi
0x14001ffae  push    rbp
0x14001ffaf  push    rdi
0x14001ffb0  push    r13
0x14001ffb2  push    r14
0x14001ffb4  push    r15
0x14001ffb6  lea     rbp, [rsp-37h]
0x14001ffbb  sub     rsp, 100h
0x14001ffc2  mov     rax, cs:__security_cookie
0x14001ffc9  xor     rax, rsp
0x14001ffcc  mov     [rbp+57h+var_30], rax
0x14001ffd0  mov     eax, r8d
0x14001ffd3  lea     rbx, [rdx-10h]
0x14001ffd7  mov     rdi, [rbx+8]
0x14001ffdb  neg     eax
0x14001ffdd  mov     r15d, r8d
0x14001ffe0  sbb     ecx, ecx
0x14001ffe2  and     ecx, 0C0000001h
0x14001ffe8  mov     [rbp+57h+var_80], ecx
0x14001ffeb  mov     r14, [rdi+30h]
0x14001ffef  mov     esi, [rdi+24Ch]
0x14001fff5  mov     rcx, r14; struct _MBB_REQUEST_MANAGER *
0x14001fff8  call    ?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)
0x14001fffd  mov     rcx, rbx; void *
0x140020000  call    ?MbbAllocMgrFree@@YAXPEAX@Z; MbbAllocMgrFree(void *)
0x140020005  inc     dword ptr [rdi+27Ch]
0x14002000b  mov     eax, [rbp+57h+var_80]
0x14002000e  mov     ebx, [rdi+27Ch]
0x140020014  test    eax, eax
0x140020016  jz      short loc_140020020
0x140020018  mov     [rdi+280h], eax
0x14002001e  jmp     short loc_140020029
0x140020020  mov     eax, [rdi+280h]
0x140020026  mov     [rbp+57h+var_80], eax
0x140020029  lea     rcx, [r14+0B0h]; SpinLock
0x140020030  mov     dl, [rcx+8]; NewIrql
0x140020033  call    cs:__imp_KeReleaseSpinLock
0x14002003a  nop     dword ptr [rax+rax+00h]
0x14002003f  lea     rax, WPP_RECORDER_INITIALIZED
0x140020046  mov     r13d, 4
0x14002004c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020053  jz      short loc_140020087
0x140020055  mov     eax, [rdi+14h]
0x140020058  lea     r9d, [r13+10h]
0x14002005c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020063  mov     dl, r13b
0x140020066  mov     dword ptr [rsp+120h+var_D8], r15d
0x14002006b  mov     dword ptr [rsp+120h+var_E0], esi
0x14002006f  mov     dword ptr [rsp+120h+var_E8], ebx
0x140020073  mov     rcx, [rcx+40h]
0x140020077  mov     dword ptr [rsp+120h+var_F0], eax
0x14002007b  mov     eax, [rdi+10h]
0x14002007e  mov     dword ptr [rsp+120h+var_F8], eax
0x140020082  call    WPP_RECORDER_SF_DDddd
0x140020087  cmp     ebx, esi
0x140020089  jnz     loc_1400202F9
0x14002008f  lea     rsi, [rdi+25Ch]
0x140020096  mov     rcx, rsi; Source1
0x140020099  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14002009e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400200a2  mov     [rbp+57h+var_7C], 0
0x1400200a9  mov     r9, rax
0x1400200ac  lea     r10, [rsi+10h]
0x1400200b0  mov     rax, rbx
0x1400200b3  inc     rax
0x1400200b6  cmp     byte ptr [r9+rax], 0
0x1400200bb  jnz     short loc_1400200B3
0x1400200bd  mov     [rsp+120h+var_88], r13
0x1400200c5  lea     r11, [rbp+57h+var_80]
0x1400200c9  mov     [rsp+120h+var_90], r11
0x1400200d1  lea     rcx, [rdi+10h]
0x1400200d5  mov     [rsp+120h+var_98], 0
0x1400200e1  lea     r11, [rbp+57h+var_7C]
0x1400200e5  mov     [rsp+120h+var_A0], 0
0x1400200f1  lea     r8, [rdi+1B0h]
0x1400200f8  mov     [rsp+120h+var_A8], r13
0x1400200fd  lea     rdx, [rdi+18h]; ActivityId
0x140020101  mov     [rsp+120h+var_B0], r11
0x140020106  inc     rax
0x140020109  mov     [rsp+120h+var_B8], r13
0x14002010e  mov     r14d, 8
0x140020114  mov     [rsp+120h+var_C0], r10
0x140020119  mov     [rsp+120h+var_C8], rax
0x14002011e  mov     [rsp+120h+var_D0], r9
0x140020123  mov     r9d, r14d; unsigned __int16
0x140020126  mov     [rsp+120h+var_D8], 10h
0x14002012f  mov     [rsp+120h+var_E0], rsi
0x140020134  mov     [rsp+120h+var_E8], r13
0x140020139  mov     [rsp+120h+var_F0], rcx
0x14002013e  lea     rcx, CID_SEND_COMPLETE; EventDescriptor
0x140020145  mov     [rsp+120h+var_F8], r14
0x14002014a  mov     [rsp+120h+var_100], r8
0x14002014f  xor     r8d, r8d; RelatedActivityId
0x140020152  call    ?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x140020157  mov     r9d, [rbp+57h+var_80]
0x14002015b  lea     edx, [r14-6]
0x14002015f  mov     rcx, [rdi+30h]
0x140020163  mov     r8, rdi
0x140020166  call    ?MbxQueueMessage@@YAHPEAU_MBB_REQUEST_MANAGER@@W4MBX_MESSAGE@@PEAX2@Z; MbxQueueMessage(_MBB_REQUEST_MANAGER *,MBX_MESSAGE,void *,void *)
0x14002016b  cmp     r15d, 0C00000B5h
0x140020172  jnz     loc_140020301
0x140020178  mov     eax, cs:dword_14005E0C8
0x14002017e  mov     rsi, 400000000000h
0x140020188  cmp     eax, 5
0x14002018b  jbe     short loc_140020203
0x14002018d  mov     rcx, cs:qword_14005E0E0
0x140020194  mov     rax, cs:qword_14005E0D8
0x14002019b  test    rsi, rax
0x14002019e  jz      short loc_140020203
0x1400201a0  mov     rax, rcx
0x1400201a3  and     rax, rsi
0x1400201a6  cmp     rax, rcx
0x1400201a9  jnz     short loc_140020203
0x1400201ab  mov     rcx, [rdi+50h]
0x1400201af  test    rcx, rcx
0x1400201b2  jz      short loc_1400201B6
0x1400201b4  mov     ebx, [rcx]
0x1400201b6  xor     eax, eax
0x1400201b8  mov     [rbp+57h+var_78], ebx
0x1400201bb  test    rcx, rcx
0x1400201be  mov     [rbp+57h+var_38], r13
0x1400201c2  lea     rdx, word_14005899A
0x1400201c9  mov     [rbp+57h+var_48], r13
0x1400201cd  setnz   al
0x1400201d0  lea     rcx, dword_14005E0C8
0x1400201d7  mov     [rbp+57h+var_74], eax
0x1400201da  xor     r9d, r9d
0x1400201dd  lea     rax, [rbp+57h+var_78]
0x1400201e1  xor     r8d, r8d
0x1400201e4  mov     [rbp+57h+var_40], rax
0x1400201e8  lea     rax, [rbp+57h+var_74]
0x1400201ec  mov     [rbp+57h+var_50], rax
0x1400201f0  lea     rax, [rbp+57h+var_70]
0x1400201f4  mov     [rsp+120h+var_F8], rax
0x1400201f9  mov     dword ptr [rsp+120h+var_100], r13d
0x1400201fe  call    _tlgWriteTransfer_EtwWriteTransfer
0x140020203  lea     rbx, WPP_RECORDER_INITIALIZED
0x14002020a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140020211  lea     r14, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140020218  jz      short loc_14002025A
0x14002021a  mov     rax, [rdi+50h]
0x14002021e  test    rax, rax
0x140020221  jz      short loc_140020227
0x140020223  mov     ecx, [rax]
0x140020225  jmp     short loc_14002022A
0x140020227  or      ecx, 0FFFFFFFFh
0x14002022a  mov     eax, [rdi+14h]
0x14002022d  mov     r9d, 15h
0x140020233  mov     dword ptr [rsp+120h+var_E8], ecx
0x140020237  mov     r8d, r13d
0x14002023a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020241  mov     dword ptr [rsp+120h+var_F0], eax
0x140020245  mov     eax, [rdi+10h]
0x140020248  mov     dword ptr [rsp+120h+var_F8], eax
0x14002024c  mov     rcx, [rcx+40h]
0x140020250  mov     [rsp+120h+var_100], r14
0x140020255  call    WPP_RECORDER_SF_ddd
0x14002025a  mov     rax, [rdi+50h]
0x14002025e  test    rax, rax
0x140020261  jz      loc_140020301
0x140020267  cmp     dword ptr [rax], 0E01010Ch
0x14002026d  jnz     loc_140020301
0x140020273  mov     eax, cs:dword_14005E0C8
0x140020279  cmp     eax, 5
0x14002027c  jbe     short loc_1400202C6
0x14002027e  mov     rdx, cs:qword_14005E0E0
0x140020285  mov     rax, cs:qword_14005E0D8
0x14002028c  test    rsi, rax
0x14002028f  jz      short loc_1400202C6
0x140020291  mov     rax, rdx
0x140020294  and     rax, rsi
0x140020297  cmp     rax, rdx
0x14002029a  jnz     short loc_1400202C6
0x14002029c  lea     rax, [rbp+57h+var_70]
0x1400202a0  xor     r9d, r9d
0x1400202a3  mov     [rsp+120h+var_F8], rax
0x1400202a8  lea     rdx, byte_1400588F9
0x1400202af  xor     r8d, r8d
0x1400202b2  mov     dword ptr [rsp+120h+var_100], 2
0x1400202ba  lea     rcx, dword_14005E0C8
0x1400202c1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400202c6  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400202cd  jz      short loc_140020301
0x1400202cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400202d6  mov     r9d, 16h
0x1400202dc  mov     eax, [rdi+10h]
0x1400202df  mov     dl, 2
0x1400202e1  mov     dword ptr [rsp+120h+var_F8], eax
0x1400202e5  mov     [rsp+120h+var_100], r14
0x1400202ea  mov     rcx, [rcx+40h]
0x1400202ee  lea     r8d, [r9-0Dh]
0x1400202f2  call    WPP_RECORDER_SF_d
0x1400202f7  jmp     short loc_140020301
0x1400202f9  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x1400202fc  call    ?MbbUtilSendMessageFragments@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragments(_MBB_REQUEST_CONTEXT *)
0x140020301  mov     rcx, [rbp+57h+var_30]
0x140020305  xor     rcx, rsp; StackCookie
0x140020308  call    __security_check_cookie
0x14002030d  lea     r11, [rsp+120h+var_20]
0x140020315  mov     rbx, [r11+30h]
0x140020319  mov     rsi, [r11+40h]
0x14002031d  mov     rsp, r11
0x140020320  pop     r15
0x140020322  pop     r14
0x140020324  pop     r13
0x140020326  pop     rdi
0x140020327  pop     rbp
0x140020328  retn
```
