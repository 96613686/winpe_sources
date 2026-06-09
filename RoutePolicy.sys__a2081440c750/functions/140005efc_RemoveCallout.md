# RemoveCallout

- ea: `0x140005efc`
- end: `0x140006008`
- name: `RemoveCallout`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003f18`
- `0x140005034`

## callees

- `0x1400012f0`
- `0x140005efc`
- `0x14000a680`

## import_xrefs

- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140005f86`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140005f86`
- `fwpkclnt!FwpmCalloutDeleteByKey0` at `0x140005f1f`
- `fwpkclnt!FwpmCalloutDeleteByKey0` at `0x140005f1f`

## pseudocode

```c
int __fastcall RemoveCallout(void *a1, const GUID *a2)
{
  NTSTATUS v3; // eax
  int result; // eax
  _DWORD v5[4]; // [rsp+30h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp+7h] BYREF
  _DWORD *v7; // [rsp+60h] [rbp+27h]
  __int64 v8; // [rsp+68h] [rbp+2Fh]
  const GUID *v9; // [rsp+70h] [rbp+37h]
  __int64 v10; // [rsp+78h] [rbp+3Fh]

  v3 = FwpmCalloutDeleteByKey0(a1, a2);
  if ( v3 < 0 && (unsigned int)dword_140012050 > 3 )
  {
    v5[0] = v3;
    v9 = a2;
    v7 = v5;
    v10 = 16;
    v8 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&word_14000F36A, 0, 0, 4u, &v6);
  }
  result = FwpsCalloutUnregisterByKey0(a2);
  if ( result < 0 && (unsigned int)dword_140012050 > 3 )
  {
    v5[0] = result;
    v9 = a2;
    v7 = v5;
    v10 = 16;
    v8 = 4;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140012050,
             (unsigned __int8 *)&byte_140010059,
             0,
             0,
             4u,
             &v6);
  }
  return result;
}

```

## disassembly

```asm
0x140005efc  mov     [rsp-8+arg_10], rbx
0x140005f01  push    rbp
0x140005f02  lea     rbp, [rsp-57h]
0x140005f07  sub     rsp, 90h
0x140005f0e  mov     rax, cs:__security_cookie
0x140005f15  xor     rax, rsp
0x140005f18  mov     [rbp+57h+var_10], rax
0x140005f1c  mov     rbx, rdx
0x140005f1f  call    cs:__imp_FwpmCalloutDeleteByKey0
0x140005f26  nop     dword ptr [rax+rax+00h]
0x140005f2b  test    eax, eax
0x140005f2d  jns     short loc_140005F83
0x140005f2f  mov     ecx, cs:dword_140012050
0x140005f35  cmp     ecx, 3
0x140005f38  jbe     short loc_140005F83
0x140005f3a  mov     [rbp+57h+var_60], eax
0x140005f3d  lea     rdx, word_14000F36A; int
0x140005f44  lea     rax, [rbp+57h+var_60]
0x140005f48  mov     [rbp+57h+var_20], rbx
0x140005f4c  mov     [rbp+57h+var_30], rax
0x140005f50  lea     rcx, dword_140012050; int
0x140005f57  lea     rax, [rbp+57h+var_50]
0x140005f5b  mov     [rbp+57h+var_18], 10h
0x140005f63  mov     [rsp+90h+var_68], rax; PEVENT_DATA_DESCRIPTOR
0x140005f68  xor     r9d, r9d; int
0x140005f6b  xor     r8d, r8d; int
0x140005f6e  mov     [rsp+90h+var_70], 4; ULONG
0x140005f76  mov     [rbp+57h+var_28], 4
0x140005f7e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005f83  mov     rcx, rbx; calloutKey
0x140005f86  call    cs:__imp_FwpsCalloutUnregisterByKey0
0x140005f8d  nop     dword ptr [rax+rax+00h]
0x140005f92  test    eax, eax
0x140005f94  jns     short loc_140005FEA
0x140005f96  mov     ecx, cs:dword_140012050
0x140005f9c  cmp     ecx, 3
0x140005f9f  jbe     short loc_140005FEA
0x140005fa1  mov     [rbp+57h+var_60], eax
0x140005fa4  lea     rdx, byte_140010059; int
0x140005fab  lea     rax, [rbp+57h+var_60]
0x140005faf  mov     [rbp+57h+var_20], rbx
0x140005fb3  mov     [rbp+57h+var_30], rax
0x140005fb7  lea     rcx, dword_140012050; int
0x140005fbe  lea     rax, [rbp+57h+var_50]
0x140005fc2  mov     [rbp+57h+var_18], 10h
0x140005fca  mov     [rsp+90h+var_68], rax; PEVENT_DATA_DESCRIPTOR
0x140005fcf  xor     r9d, r9d; int
0x140005fd2  xor     r8d, r8d; int
0x140005fd5  mov     [rsp+90h+var_70], 4; ULONG
0x140005fdd  mov     [rbp+57h+var_28], 4
0x140005fe5  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005fea  mov     rcx, [rbp+57h+var_10]
0x140005fee  xor     rcx, rsp; StackCookie
0x140005ff1  call    __security_check_cookie
0x140005ff6  mov     rbx, [rsp+90h+arg_10]
0x140005ffe  add     rsp, 90h
0x140006005  pop     rbp
0x140006006  retn
```
