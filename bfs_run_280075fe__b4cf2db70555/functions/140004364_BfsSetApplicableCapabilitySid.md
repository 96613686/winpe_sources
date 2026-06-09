# BfsSetApplicableCapabilitySid

- ea: `0x140004364`
- end: `0x1400044de`
- name: `BfsSetApplicableCapabilitySid`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140004364`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlDeriveCapabilitySidsFromName` at `0x140004471`
- `ntoskrnl!RtlDeriveCapabilitySidsFromName` at `0x140004471`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000445b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000445b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044b7`
- `ntoskrnl!ExAllocatePool2` at `0x14000439e`
- `ntoskrnl!ExAllocatePool2` at `0x140004400`
- `ntoskrnl!ExAllocatePool2` at `0x14000439e`
- `ntoskrnl!ExAllocatePool2` at `0x140004400`

## string_xrefs

- `0x140004450`: `AgenticAppContainer`

## pseudocode

```c
__int64 BfsSetApplicableCapabilitySid()
{
  int v0; // ecx
  void *Pool2; // rsi
  int v2; // r8d
  int v3; // r9d
  unsigned int v4; // edi
  void *v5; // rbx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-29h]
  int v12; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+48h] [rbp-1h] BYREF
  int *v15; // [rsp+68h] [rbp+1Fh]
  __int64 v16; // [rsp+70h] [rbp+27h]

  DestinationString = 0;
  Pool2 = (void *)ExAllocatePool2(256, 44, 1400071746);
  if ( !Pool2 )
  {
    v4 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v12 = -1073741801;
      v15 = &v12;
      v16 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v0, (int)&byte_140016D91, v2, v3, v11, &v14);
    }
    return v4;
  }
  v5 = (void *)ExAllocatePool2(256, 48, 1400071746);
  if ( !v5 )
  {
    v8 = dword_140019000;
    v4 = -1073741801;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_12;
    v12 = -1073741801;
    goto LABEL_7;
  }
  RtlInitUnicodeString(&DestinationString, L"AgenticAppContainer");
  v9 = RtlDeriveCapabilitySidsFromName(&DestinationString, Pool2, v5);
  v4 = v9;
  if ( v9 >= 0 )
  {
    gApplicableCapabilitySid = v5;
    v5 = 0;
  }
  else
  {
    v8 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v12 = v9;
LABEL_7:
      v16 = 4;
      v15 = &v12;
      tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v6, v7, v11, &v14);
    }
  }
LABEL_12:
  ExFreePoolWithTag(Pool2, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return v4;
}

```

## disassembly

```asm
0x140004364  push    rbp
0x140004366  push    rbx
0x140004367  push    rsi
0x140004368  push    rdi
0x140004369  lea     rbp, [rsp-3Fh]
0x14000436e  sub     rsp, 88h
0x140004375  mov     rax, cs:__security_cookie
0x14000437c  xor     rax, rsp
0x14000437f  mov     [rbp+57h+var_28], rax
0x140004383  xorps   xmm0, xmm0
0x140004386  mov     ebx, 53736642h
0x14000438b  mov     edi, 100h
0x140004390  mov     r8d, ebx
0x140004393  mov     ecx, edi
0x140004395  mov     edx, 2Ch ; ','
0x14000439a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000439e  call    cs:__imp_ExAllocatePool2
0x1400043a5  nop     dword ptr [rax+rax+00h]
0x1400043aa  mov     rsi, rax
0x1400043ad  test    rax, rax
0x1400043b0  jnz     short loc_1400043F5
0x1400043b2  mov     eax, cs:dword_140019000
0x1400043b8  mov     edx, 0C0000017h
0x1400043bd  mov     edi, edx
0x1400043bf  cmp     eax, 3
0x1400043c2  jbe     loc_1400044C3
0x1400043c8  lea     rax, [rbp+57h+var_70]
0x1400043cc  mov     [rbp+57h+var_70], edx
0x1400043cf  mov     [rbp+57h+var_38], rax
0x1400043d3  lea     rdx, byte_140016D91; int
0x1400043da  lea     rax, [rbp+57h+var_58]
0x1400043de  mov     [rbp+57h+var_30], 4
0x1400043e6  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x1400043eb  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400043f0  jmp     loc_1400044C3
0x1400043f5  mov     r8d, ebx
0x1400043f8  mov     edx, 30h ; '0'
0x1400043fd  mov     rcx, rdi
0x140004400  call    cs:__imp_ExAllocatePool2
0x140004407  nop     dword ptr [rax+rax+00h]
0x14000440c  mov     rbx, rax
0x14000440f  test    rax, rax
0x140004412  jnz     short loc_140004450
0x140004414  mov     ecx, cs:dword_140019000; int
0x14000441a  mov     edx, 0C0000017h
0x14000441f  mov     edi, edx
0x140004421  cmp     ecx, 3
0x140004424  jbe     short loc_14000449C
0x140004426  mov     [rbp+57h+var_70], edx
0x140004429  lea     rax, [rbp+57h+var_70]
0x14000442d  mov     [rbp+57h+var_30], 4
0x140004435  mov     [rbp+57h+var_38], rax
0x140004439  lea     rdx, byte_140016D91; int
0x140004440  lea     rax, [rbp+57h+var_58]
0x140004444  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x140004449  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000444e  jmp     short loc_14000449C
0x140004450  lea     rdx, aAgenticappcont; "AgenticAppContainer"
0x140004457  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000445b  call    cs:__imp_RtlInitUnicodeString
0x140004462  nop     dword ptr [rax+rax+00h]
0x140004467  mov     r8, rbx
0x14000446a  lea     rcx, [rbp+57h+DestinationString]
0x14000446e  mov     rdx, rsi
0x140004471  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x140004478  nop     dword ptr [rax+rax+00h]
0x14000447d  mov     edi, eax
0x14000447f  test    eax, eax
0x140004481  jns     short loc_140004493
0x140004483  mov     ecx, cs:dword_140019000
0x140004489  cmp     ecx, 3
0x14000448c  jbe     short loc_14000449C
0x14000448e  mov     [rbp+57h+var_70], eax
0x140004491  jmp     short loc_140004429
0x140004493  mov     cs:gApplicableCapabilitySid, rbx
0x14000449a  xor     ebx, ebx
0x14000449c  xor     edx, edx; Tag
0x14000449e  mov     rcx, rsi; P
0x1400044a1  call    cs:__imp_ExFreePoolWithTag
0x1400044a8  nop     dword ptr [rax+rax+00h]
0x1400044ad  test    rbx, rbx
0x1400044b0  jz      short loc_1400044C3
0x1400044b2  xor     edx, edx; Tag
0x1400044b4  mov     rcx, rbx; P
0x1400044b7  call    cs:__imp_ExFreePoolWithTag
0x1400044be  nop     dword ptr [rax+rax+00h]
0x1400044c3  mov     eax, edi
0x1400044c5  mov     rcx, [rbp+57h+var_28]
0x1400044c9  xor     rcx, rsp; StackCookie
0x1400044cc  call    __security_check_cookie
0x1400044d1  add     rsp, 88h
0x1400044d8  pop     rdi
0x1400044d9  pop     rsi
0x1400044da  pop     rbx
0x1400044db  pop     rbp
0x1400044dc  retn
```
