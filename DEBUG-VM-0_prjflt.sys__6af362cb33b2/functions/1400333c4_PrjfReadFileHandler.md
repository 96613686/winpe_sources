# PrjfReadFileHandler

- ea: `0x1400333c4`
- end: `0x140033871`
- name: `PrjfReadFileHandler`
- size: `1197`
- prototype: `__int64 __fastcall(PFLT_INSTANCE InitiatingInstance)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d008`
- `0x14000d128`
- `0x14000d5e8`
- `0x140021f8c`
- `0x1400333c4`
- `0x14003ee54`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140033652`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140033652`
- `ntoskrnl!ObfReferenceObject` at `0x1400336d3`
- `ntoskrnl!ObfReferenceObject` at `0x1400336d3`
- `ntoskrnl!ObfDereferenceObject` at `0x140033838`
- `ntoskrnl!ObfDereferenceObject` at `0x140033838`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003359f`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003359f`
- `FLTMGR!FltReadFile` at `0x1400337a1`
- `FLTMGR!FltReadFile` at `0x1400337a1`
- `FLTMGR!FltReleaseResource` at `0x140033669`
- `FLTMGR!FltReleaseResource` at `0x1400336f5`
- `FLTMGR!FltReleaseResource` at `0x140033669`
- `FLTMGR!FltReleaseResource` at `0x1400336f5`
- `FLTMGR!FltAcquireResourceShared` at `0x14003363a`
- `FLTMGR!FltAcquireResourceShared` at `0x14003363a`

## pseudocode

```c
__int64 __fastcall PrjfReadFileHandler(PFLT_INSTANCE InitiatingInstance, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // r13
  unsigned int v6; // r9d
  __int64 v7; // rbp
  NTSTATUS File; // ebx
  __int64 UnionContextByVirtualizationInstanceInfo; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rsi
  struct _KPROCESS *v14; // rbx
  int v15; // edx
  int v16; // r8d
  struct _FILE_OBJECT **v17; // rax
  struct _FILE_OBJECT **v18; // rbx
  int v19; // edx
  int v20; // r8d
  struct _FILE_OBJECT *v21; // rdi
  int v22; // edx
  __int64 v23; // rcx
  int v24; // r8d
  int v25; // edx
  int v26; // r8d
  _OWORD Buffer[2]; // [rsp+60h] [rbp-68h] BYREF

  v5 = a3;
  v6 = *(_DWORD *)(a2 + 104) + 8;
  v7 = a2;
  memset(Buffer, 0, sizeof(Buffer));
  if ( v6 >= 8 )
  {
    if ( a4 >= v6 )
    {
      UnionContextByVirtualizationInstanceInfo = PrjfGetUnionContextByVirtualizationInstanceInfo(a2, InitiatingInstance);
      v13 = UnionContextByVirtualizationInstanceInfo;
      if ( UnionContextByVirtualizationInstanceInfo )
      {
        v14 = *(struct _KPROCESS **)(UnionContextByVirtualizationInstanceInfo + 32);
        if ( IoGetCurrentProcess() == v14 )
        {
          Buffer[0] = *(_OWORD *)(v7 + 80);
          FltAcquireResourceShared((PERESOURCE)(v13 + 96));
          v17 = (struct _FILE_OBJECT **)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(v13 + 200), Buffer);
          v18 = v17;
          if ( v17 )
          {
            v21 = v17[2];
            ObfReferenceObject(v21);
            File = PrjfValidateHandleAccess(v18[3], 1, v21);
            FltReleaseResource((PERESOURCE)(v13 + 96));
            if ( File >= 0 )
            {
              if ( (v21->Flags & 0x40) == 0 )
                MicrosoftTelemetryAssertTriggeredNoArgsKM(v23);
              File = FltReadFile(
                       InitiatingInstance,
                       v21,
                       (PLARGE_INTEGER)(v7 + 96),
                       *(_DWORD *)(v7 + 104),
                       (PVOID)(v5 + 8),
                       4u,
                       (PULONG)(v5 + 4),
                       0,
                       0);
              if ( File == -1073741807 )
              {
                File = 0;
                *(_DWORD *)(v5 + 4) = 0;
              }
              else if ( File < 0
                     && ((BYTE1(xmmword_14001A3D0) & 0x40) != 0
                      || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
              {
                LOBYTE(v25) = BYTE1(xmmword_14001A3D0) & 0x40;
                LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_sDL(
                  526,
                  v25,
                  v26,
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  2,
                  14,
                  50,
                  (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                  (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                  89,
                  File);
              }
            }
            else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                   || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v22) = BYTE1(xmmword_14001A3D0) & 0x40;
              LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDL(
                526,
                v22,
                v24,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                14,
                49,
                (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                50,
                File);
            }
            if ( v21 )
              ObfDereferenceObject(v21);
          }
          else
          {
            FltReleaseResource((PERESOURCE)(v13 + 96));
            File = -1073741816;
            if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 0x40;
              LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sD(
                526,
                v19,
                v20,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                14,
                48,
                (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                28);
            }
          }
        }
        else
        {
          File = -1073741790;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 0x40;
            LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sD(
              526,
              v15,
              v16,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              47,
              (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              9);
          }
        }
        PrjfReleaseUnionContext((char *)v13);
      }
      else
      {
        File = -1073741811;
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            526,
            v11,
            v12,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            46,
            (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            253);
        }
      }
    }
    else
    {
      File = -1073741811;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdd(526, a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 8));
      }
    }
  }
  else
  {
    File = -1073741675;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        44,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        235,
        149);
    }
  }
  return (unsigned int)File;
}

```

## disassembly

```asm
0x1400333c4  push    rbx
0x1400333c6  push    rbp
0x1400333c7  push    rsi
0x1400333c8  push    rdi
0x1400333c9  push    r13
0x1400333cb  push    r14
0x1400333cd  push    r15
0x1400333cf  sub     rsp, 90h
0x1400333d6  mov     rax, cs:__security_cookie
0x1400333dd  xor     rax, rsp
0x1400333e0  mov     [rsp+0C8h+var_48], rax
0x1400333e8  mov     r10d, r9d
0x1400333eb  xorps   xmm0, xmm0
0x1400333ee  mov     r9d, [rdx+68h]
0x1400333f2  mov     r13, r8
0x1400333f5  add     r9d, 8
0x1400333f9  mov     rbp, rdx
0x1400333fc  mov     r15, rcx
0x1400333ff  movups  [rsp+0C8h+Buffer], xmm0
0x140033404  movups  [rsp+0C8h+var_58], xmm0
0x140033409  cmp     r9d, 8
0x14003340d  jnb     short loc_14003348C
0x14003340f  mov     ebx, 0C0000095h
0x140033414  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003341a  lea     rax, WPP_RECORDER_INITIALIZED
0x140033421  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033428  setnz   r8b
0x14003342c  and     dl, 40h
0x14003342f  jnz     short loc_14003343A
0x140033431  test    r8b, r8b
0x140033434  jz      loc_14003384C
0x14003343a  mov     r9, cs:WPP_GLOBAL_Control
0x140033441  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140033448  mov     [rsp+0C8h+var_78], ebx
0x14003344c  mov     ecx, 20Eh
0x140033451  mov     [rsp+0C8h+var_80], 4EBh
0x140033459  mov     [rsp+0C8h+CallbackContext], rax
0x14003345e  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140033465  mov     r9, [r9+40h]
0x140033469  mov     [rsp+0C8h+CallbackRoutine], rax
0x14003346e  mov     word ptr [rsp+0C8h+BytesRead], 2Ch ; ','
0x140033475  mov     [rsp+0C8h+Flags], 0Eh
0x14003347d  mov     byte ptr [rsp+0C8h+var_A8], 2
0x140033482  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140033487  jmp     loc_14003384C
0x14003348c  cmp     r10d, r9d
0x14003348f  jnb     short loc_14003350F
0x140033491  mov     ebx, 0C000000Dh
0x140033496  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003349c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400334a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400334aa  setnz   r8b
0x1400334ae  and     dl, 40h
0x1400334b1  jnz     short loc_1400334BC
0x1400334b3  test    r8b, r8b
0x1400334b6  jz      loc_14003384C
0x1400334bc  mov     [rsp+0C8h+var_70], r9d
0x1400334c1  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400334c8  mov     r9, cs:WPP_GLOBAL_Control
0x1400334cf  mov     ecx, 20Eh
0x1400334d4  mov     [rsp+0C8h+var_78], r10d
0x1400334d9  mov     [rsp+0C8h+var_80], 4F3h
0x1400334e1  mov     [rsp+0C8h+CallbackContext], rax
0x1400334e6  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400334ed  mov     r9, [r9+40h]
0x1400334f1  mov     [rsp+0C8h+CallbackRoutine], rax
0x1400334f6  mov     word ptr [rsp+0C8h+BytesRead], 2Dh ; '-'
0x1400334fd  mov     [rsp+0C8h+Flags], 0Eh
0x140033505  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x14003350a  jmp     loc_14003384C
0x14003350f  mov     rdx, r15
0x140033512  mov     rcx, rbp
0x140033515  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x14003351a  mov     rsi, rax
0x14003351d  test    rax, rax
0x140033520  jnz     short loc_14003359B
0x140033522  mov     ebx, 0C000000Dh
0x140033527  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003352d  lea     rax, WPP_RECORDER_INITIALIZED
0x140033534  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003353b  setnz   r8b
0x14003353f  and     dl, 40h
0x140033542  jnz     short loc_14003354D
0x140033544  test    r8b, r8b
0x140033547  jz      loc_14003384C
0x14003354d  mov     r9, cs:WPP_GLOBAL_Control
0x140033554  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003355b  mov     [rsp+0C8h+var_80], 4FDh
0x140033563  mov     ecx, 20Eh
0x140033568  mov     [rsp+0C8h+CallbackContext], rax
0x14003356d  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140033574  mov     [rsp+0C8h+CallbackRoutine], rax
0x140033579  mov     r9, [r9+40h]
0x14003357d  mov     word ptr [rsp+0C8h+BytesRead], 2Eh ; '.'
0x140033584  mov     [rsp+0C8h+Flags], 0Eh
0x14003358c  mov     byte ptr [rsp+0C8h+var_A8], 2
0x140033591  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140033596  jmp     loc_14003384C
0x14003359b  mov     rbx, [rax+20h]
0x14003359f  call    cs:__imp_IoGetCurrentProcess
0x1400335a6  nop     dword ptr [rax+rax+00h]
0x1400335ab  cmp     rax, rbx
0x1400335ae  jz      short loc_140033629
0x1400335b0  mov     ebx, 0C0000022h
0x1400335b5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400335bb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400335c2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400335c9  setnz   r8b
0x1400335cd  and     dl, 40h
0x1400335d0  jnz     short loc_1400335DB
0x1400335d2  test    r8b, r8b
0x1400335d5  jz      loc_140033844
0x1400335db  mov     [rsp+0C8h+var_80], 509h
0x1400335e3  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400335ea  mov     [rsp+0C8h+CallbackContext], rax
0x1400335ef  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400335f6  mov     [rsp+0C8h+CallbackRoutine], rax
0x1400335fb  mov     word ptr [rsp+0C8h+BytesRead], 2Fh ; '/'
0x140033602  mov     r9, cs:WPP_GLOBAL_Control
0x140033609  mov     ecx, 20Eh
0x14003360e  mov     [rsp+0C8h+Flags], 0Eh
0x140033616  mov     byte ptr [rsp+0C8h+var_A8], 2
0x14003361b  mov     r9, [r9+40h]
0x14003361f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140033624  jmp     loc_140033844
0x140033629  movups  xmm0, xmmword ptr [rbp+50h]
0x14003362d  lea     r14, [rsi+60h]
0x140033631  mov     rcx, r14; Resource
0x140033634  movdqu  [rsp+0C8h+Buffer], xmm0
0x14003363a  call    cs:__imp_FltAcquireResourceShared
0x140033641  nop     dword ptr [rax+rax+00h]
0x140033646  lea     rcx, [rsi+0C8h]; Table
0x14003364d  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x140033652  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140033659  nop     dword ptr [rax+rax+00h]
0x14003365e  mov     rbx, rax
0x140033661  test    rax, rax
0x140033664  jnz     short loc_1400336CC
0x140033666  mov     rcx, r14; Resource
0x140033669  call    cs:__imp_FltReleaseResource
0x140033670  nop     dword ptr [rax+rax+00h]
0x140033675  mov     ebx, 0C0000008h
0x14003367a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033680  lea     rax, WPP_RECORDER_INITIALIZED
0x140033687  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003368e  setnz   r8b
0x140033692  and     dl, 40h
0x140033695  jnz     short loc_1400336A0
0x140033697  test    r8b, r8b
0x14003369a  jz      loc_140033844
0x1400336a0  mov     [rsp+0C8h+var_80], 51Ch
0x1400336a8  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400336af  mov     [rsp+0C8h+CallbackContext], rax
0x1400336b4  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400336bb  mov     [rsp+0C8h+CallbackRoutine], rax
0x1400336c0  mov     word ptr [rsp+0C8h+BytesRead], 30h ; '0'
0x1400336c7  jmp     loc_140033602
0x1400336cc  mov     rdi, [rax+10h]
0x1400336d0  mov     rcx, rdi; Object
0x1400336d3  call    cs:__imp_ObfReferenceObject
0x1400336da  nop     dword ptr [rax+rax+00h]
0x1400336df  mov     rcx, [rbx+18h]
0x1400336e3  mov     r8, rdi
0x1400336e6  mov     edx, 1
0x1400336eb  call    PrjfValidateHandleAccess
0x1400336f0  mov     rcx, r14; Resource
0x1400336f3  mov     ebx, eax
0x1400336f5  call    cs:__imp_FltReleaseResource
0x1400336fc  nop     dword ptr [rax+rax+00h]
0x140033701  test    ebx, ebx
0x140033703  jns     short loc_14003375B
0x140033705  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003370b  lea     rax, WPP_RECORDER_INITIALIZED
0x140033712  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033719  setnz   r8b
0x14003371d  and     dl, 40h
0x140033720  jnz     short loc_14003372B
0x140033722  test    r8b, r8b
0x140033725  jz      loc_140033830
0x14003372b  mov     [rsp+0C8h+var_78], ebx
0x14003372f  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140033736  mov     [rsp+0C8h+var_80], 532h
0x14003373e  mov     [rsp+0C8h+CallbackContext], rax
0x140033743  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003374a  mov     [rsp+0C8h+CallbackRoutine], rax
0x14003374f  mov     word ptr [rsp+0C8h+BytesRead], 31h ; '1'
0x140033756  jmp     loc_14003380E
0x14003375b  mov     eax, [rdi+50h]
0x14003375e  test    al, 40h
0x140033760  jnz     short loc_140033767
0x140033762  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033767  mov     r9d, [rbp+68h]; Length
0x14003376b  lea     rax, [r13+8]
0x14003376f  mov     [rsp+0C8h+CallbackContext], 0; CallbackContext
0x140033778  lea     r14, [r13+4]
0x14003377c  mov     [rsp+0C8h+CallbackRoutine], 0; CallbackRoutine
0x140033785  lea     r8, [rbp+60h]; ByteOffset
0x140033789  mov     [rsp+0C8h+BytesRead], r14; BytesRead
0x14003378e  mov     rdx, rdi; FileObject
0x140033791  mov     [rsp+0C8h+Flags], 4; Flags
0x140033799  mov     rcx, r15; InitiatingInstance
0x14003379c  mov     [rsp+0C8h+var_A8], rax; Buffer
0x1400337a1  call    cs:__imp_FltReadFile
0x1400337a8  nop     dword ptr [rax+rax+00h]
0x1400337ad  mov     ebx, eax
0x1400337af  cmp     eax, 0C0000011h
0x1400337b4  jnz     short loc_1400337BD
0x1400337b6  xor     ebx, ebx
0x1400337b8  mov     [r14], ebx
0x1400337bb  jmp     short loc_140033830
0x1400337bd  test    ebx, ebx
0x1400337bf  jns     short loc_140033830
0x1400337c1  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400337c7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400337ce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400337d5  setnz   r8b
0x1400337d9  and     dl, 40h
0x1400337dc  jnz     short loc_1400337E3
0x1400337de  test    r8b, r8b
0x1400337e1  jz      short loc_140033830
0x1400337e3  mov     [rsp+0C8h+var_78], ebx
0x1400337e7  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400337ee  mov     [rsp+0C8h+var_80], 559h
0x1400337f6  mov     [rsp+0C8h+CallbackContext], rax
0x1400337fb  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140033802  mov     [rsp+0C8h+CallbackRoutine], rax
0x140033807  mov     word ptr [rsp+0C8h+BytesRead], 32h ; '2'
0x14003380e  mov     r9, cs:WPP_GLOBAL_Control
0x140033815  mov     ecx, 20Eh
0x14003381a  mov     [rsp+0C8h+Flags], 0Eh
0x140033822  mov     byte ptr [rsp+0C8h+var_A8], 2
0x140033827  mov     r9, [r9+40h]
0x14003382b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140033830  test    rdi, rdi
0x140033833  jz      short loc_140033844
0x140033835  mov     rcx, rdi; Object
0x140033838  call    cs:__imp_ObfDereferenceObject
0x14003383f  nop     dword ptr [rax+rax+00h]
0x140033844  mov     rcx, rsi; P
0x140033847  call    PrjfReleaseUnionContext
0x14003384c  mov     eax, ebx
0x14003384e  mov     rcx, [rsp+0C8h+var_48]
0x140033856  xor     rcx, rsp; StackCookie
0x140033859  call    __security_check_cookie
0x14003385e  add     rsp, 90h
0x140033865  pop     r15
0x140033867  pop     r14
0x140033869  pop     r13
0x14003386b  pop     rdi
0x14003386c  pop     rsi
0x14003386d  pop     rbp
0x14003386e  pop     rbx
0x14003386f  retn
```
