# UbpmTakeMaintenancePdcReference(uchar)

- ea: `0x18002fc2c`
- end: `0x18002fd0a`
- name: `?UbpmTakeMaintenancePdcReference@@YAXE@Z`
- size: `222`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180030bb4`
- `0x180030d58`
- `0x180031150`

## callees

- `0x180025c9c`
- `0x180028fe8`
- `0x18002fc2c`

## import_xrefs

- `UMPDC!PdcActivationClientActivityRequest` at `0x18002fc5b`
- `UMPDC!PdcActivationClientActivityRequest` at `0x18002fc5b`
- `UMPDC!PdcTaskClientRequest` at `0x18002fc6b`
- `UMPDC!PdcTaskClientRequest` at `0x18002fc6b`

## pseudocode

```c
void __fastcall UbpmTakeMaintenancePdcReference(char a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  int v5; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // [rsp+50h] [rbp-18h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h] BYREF
  char v11; // [rsp+78h] [rbp+10h] BYREF
  char v12; // [rsp+80h] [rbp+18h] BYREF
  int v13; // [rsp+88h] [rbp+20h] BYREF

  if ( !qword_18004FC38 || byte_18004FC40 == a1 )
    goto LABEL_9;
  v4 = (unsigned int)(dword_18004FC34 - 1);
  if ( dword_18004FC34 == 1 )
  {
    LOBYTE(v4) = a1;
    v5 = PdcTaskClientRequest(qword_18004FC38, v4);
  }
  else
  {
    if ( dword_18004FC34 != 2 )
      goto LABEL_9;
    LOBYTE(a3) = a1;
    v5 = PdcActivationClientActivityRequest(qword_18004FC38, v4, a3);
  }
  if ( v5 >= 0 )
    byte_18004FC40 = a1;
LABEL_9:
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v11 = byte_18004FC40;
    v10 = qword_18004FC38;
    v13 = dword_18004FC34;
    v9 = UbpmpMaintenanceTotalTasksRunning();
    v12 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
      v6,
      (unsigned int)&unk_180047138,
      v7,
      v8,
      (__int64)&v12,
      (__int64)&v9,
      (__int64)&v13,
      (__int64)&v10,
      (__int64)&v11);
  }
}

```

## disassembly

```asm
0x18002fc2c  push    rbx
0x18002fc2e  sub     rsp, 60h
0x18002fc32  mov     bl, cl
0x18002fc34  mov     rcx, cs:qword_18004FC38
0x18002fc3b  test    rcx, rcx
0x18002fc3e  jz      short loc_18002FC81
0x18002fc40  cmp     cs:byte_18004FC40, bl
0x18002fc46  jz      short loc_18002FC81
0x18002fc48  mov     edx, cs:dword_18004FC34
0x18002fc4e  sub     edx, 1
0x18002fc51  jz      short loc_18002FC69
0x18002fc53  cmp     edx, 1
0x18002fc56  jnz     short loc_18002FC81
0x18002fc58  mov     r8b, bl
0x18002fc5b  call    cs:__imp_PdcActivationClientActivityRequest
0x18002fc62  nop     dword ptr [rax+rax+00h]
0x18002fc67  jmp     short loc_18002FC77
0x18002fc69  mov     dl, bl
0x18002fc6b  call    cs:__imp_PdcTaskClientRequest
0x18002fc72  nop     dword ptr [rax+rax+00h]
0x18002fc77  test    eax, eax
0x18002fc79  js      short loc_18002FC81
0x18002fc7b  mov     cs:byte_18004FC40, bl
0x18002fc81  mov     eax, cs:dword_18004F0F0
0x18002fc87  cmp     eax, 4
0x18002fc8a  jbe     short loc_18002FD03
0x18002fc8c  mov     al, cs:byte_18004FC40
0x18002fc92  mov     [rsp+68h+arg_8], al
0x18002fc96  mov     rax, cs:qword_18004FC38
0x18002fc9d  mov     [rsp+68h+var_10], rax
0x18002fca2  mov     eax, cs:dword_18004FC34
0x18002fca8  mov     [rsp+68h+arg_18], eax
0x18002fcaf  call    ?UbpmpMaintenanceTotalTasksRunning@@YAKXZ; UbpmpMaintenanceTotalTasksRunning(void)
0x18002fcb4  mov     [rsp+68h+var_18], eax
0x18002fcb8  lea     rdx, unk_180047138
0x18002fcbf  lea     rax, [rsp+68h+arg_8]
0x18002fcc4  mov     [rsp+68h+arg_10], bl
0x18002fccb  mov     [rsp+68h+var_28], rax
0x18002fcd0  lea     rax, [rsp+68h+var_10]
0x18002fcd5  mov     [rsp+68h+var_30], rax
0x18002fcda  lea     rax, [rsp+68h+arg_18]
0x18002fce2  mov     [rsp+68h+var_38], rax
0x18002fce7  lea     rax, [rsp+68h+var_18]
0x18002fcec  mov     [rsp+68h+var_40], rax
0x18002fcf1  lea     rax, [rsp+68h+arg_10]
0x18002fcf9  mov     [rsp+68h+var_48], rax
0x18002fcfe  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &)
0x18002fd03  add     rsp, 60h
0x18002fd07  pop     rbx
0x18002fd08  retn
```
