# PrjfSendCancelCommandWorker

- ea: `0x140004640`
- end: `0x1400047c3`
- name: `PrjfSendCancelCommandWorker`
- size: `387`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140003480`
- `0x140003e6c`
- `0x140004640`
- `0x14000d128`
- `0x14001104c`
- `0x14003a5cc`

## import_xrefs

- `FLTMGR!FltSendMessage` at `0x14000472a`
- `FLTMGR!FltSendMessage` at `0x14000472a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000478d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000478d`

## pseudocode

```c
void __fastcall PrjfSendCancelCommandWorker(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, char *Context)
{
  __int64 UnionContext; // rax
  int v6; // r8d
  char *v7; // rdi
  PFLT_PORT *v8; // rdx
  int v9; // edx
  int v10; // r8d
  int ReplyBuffer; // [rsp+20h] [rbp-58h]
  int ReplyLength; // [rsp+28h] [rbp-50h]
  int Timeout; // [rsp+30h] [rbp-48h]
  __int128 v14; // [rsp+60h] [rbp-18h] BYREF

  v14 = *(_OWORD *)(Context + 8);
  UnionContext = PrjfGetUnionContext(FltObject, &v14);
  v7 = (char *)UnionContext;
  if ( UnionContext )
  {
    v8 = (PFLT_PORT *)(UnionContext + 80);
    if ( *(_QWORD *)(UnionContext + 80) )
    {
      if ( FltSendMessage(Globals, v8, Context, *(_DWORD *)Context, 0, 0, 0) < 0
        && ((BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDld(
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          ReplyBuffer,
          ReplyLength,
          Timeout);
      }
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
           || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        (_DWORD)v8,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        143,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        205,
        1);
    }
  }
  if ( FltWorkItem )
    FltFreeGenericWorkItem(FltWorkItem);
  PrjfFreeCommandBuffer(Context, *(_DWORD *)Context);
  if ( v7 )
    PrjfReleaseUnionContext(v7);
}

```

## disassembly

```asm
0x140004640  mov     [rsp+arg_0], rbx
0x140004645  mov     [rsp+arg_8], rsi
0x14000464a  push    rdi
0x14000464b  sub     rsp, 70h
0x14000464f  movups  xmm0, xmmword ptr [r8+8]
0x140004654  mov     rax, rdx
0x140004657  mov     rsi, rcx
0x14000465a  lea     rdx, [rsp+78h+var_18]
0x14000465f  mov     rcx, rax
0x140004662  movdqu  [rsp+78h+var_18], xmm0
0x140004668  mov     rbx, r8
0x14000466b  call    PrjfGetUnionContext
0x140004670  mov     rdi, rax
0x140004673  test    rax, rax
0x140004676  jz      loc_140004785
0x14000467c  lea     rdx, [rax+50h]; ClientPort
0x140004680  cmp     qword ptr [rdx], 0
0x140004684  jnz     short loc_140004702
0x140004686  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000468c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140004693  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000469a  setnz   r8b
0x14000469e  and     dl, 40h
0x1400046a1  jnz     short loc_1400046AC
0x1400046a3  test    r8b, r8b
0x1400046a6  jz      loc_140004785
0x1400046ac  mov     r9, cs:WPP_GLOBAL_Control
0x1400046b3  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400046ba  mov     [rsp+78h+var_28], 0C000CE01h
0x1400046c2  mov     ecx, 20Eh
0x1400046c7  mov     [rsp+78h+var_30], 0FCDh
0x1400046cf  mov     [rsp+78h+var_38], rax
0x1400046d4  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400046db  mov     r9, [r9+40h]
0x1400046df  mov     [rsp+78h+var_40], rax
0x1400046e4  mov     word ptr [rsp+78h+Timeout], 8Fh
0x1400046eb  mov     dword ptr [rsp+78h+ReplyLength], 0Eh
0x1400046f3  mov     byte ptr [rsp+78h+ReplyBuffer], 2
0x1400046f8  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400046fd  jmp     loc_140004785
0x140004702  mov     r9d, [rbx]; SenderBufferLength
0x140004705  mov     r8, rbx; SenderBuffer
0x140004708  mov     rcx, cs:Globals; Filter
0x14000470f  mov     [rsp+78h+Timeout], 0; Timeout
0x140004718  mov     [rsp+78h+ReplyLength], 0; ReplyLength
0x140004721  mov     [rsp+78h+ReplyBuffer], 0; ReplyBuffer
0x14000472a  call    cs:__imp_FltSendMessage
0x140004731  nop     dword ptr [rax+rax+00h]
0x140004736  cmp     eax, 0C0000037h
0x14000473b  jnz     short loc_140004744
0x14000473d  mov     eax, 0C000CE01h
0x140004742  jmp     short loc_140004748
0x140004744  test    eax, eax
0x140004746  jns     short loc_140004785
0x140004748  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000474e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140004755  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000475c  setnz   r8b
0x140004760  and     dl, 40h
0x140004763  jnz     short loc_14000476A
0x140004765  test    r8b, r8b
0x140004768  jz      short loc_140004785
0x14000476a  mov     r9, cs:WPP_GLOBAL_Control
0x140004771  mov     [rsp+78h+var_20], eax
0x140004775  mov     eax, [rbx+18h]
0x140004778  mov     [rsp+78h+var_28], eax
0x14000477c  mov     r9, [r9+40h]
0x140004780  call    WPP_RECORDER_AND_TRACE_SF_sDld
0x140004785  test    rsi, rsi
0x140004788  jz      short loc_140004799
0x14000478a  mov     rcx, rsi; FltWorkItem
0x14000478d  call    cs:__imp_FltFreeGenericWorkItem
0x140004794  nop     dword ptr [rax+rax+00h]
0x140004799  mov     edx, [rbx]
0x14000479b  mov     rcx, rbx; Entry
0x14000479e  call    PrjfFreeCommandBuffer
0x1400047a3  test    rdi, rdi
0x1400047a6  jz      short loc_1400047B0
0x1400047a8  mov     rcx, rdi; P
0x1400047ab  call    PrjfReleaseUnionContext
0x1400047b0  lea     r11, [rsp+78h+var_8]
0x1400047b5  mov     rbx, [r11+10h]
0x1400047b9  mov     rsi, [r11+18h]
0x1400047bd  mov     rsp, r11
0x1400047c0  pop     rdi
0x1400047c1  retn
```
