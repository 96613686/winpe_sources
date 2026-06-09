# UaspDumpIssueBulkOrInterruptRequest

- ea: `0x1400019d0`
- end: `0x140001b5d`
- name: `UaspDumpIssueBulkOrInterruptRequest`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001d6c`

## callees

- `0x1400019d0`
- `0x14000d7f0`
- `0x14000d830`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140001abc`
- `ntoskrnl!DbgPrintEx` at `0x140001b04`
- `ntoskrnl!DbgPrintEx` at `0x140001abc`
- `ntoskrnl!DbgPrintEx` at `0x140001b04`
- `storport!StorPortGetPhysicalAddress` at `0x140001a53`
- `storport!StorPortGetPhysicalAddress` at `0x140001a53`

## string_xrefs

- `0x140001af6`: `UASPSTOR: URB completion. Urb: %p, Status: 0x%lX\n`

## pseudocode

```c
__int64 __fastcall UaspDumpIssueBulkOrInterruptRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v5; // rbx
  int v8; // r12d
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 PhysicalAddress; // rax
  __int64 v12; // rcx
  __int64 (__fastcall *v13)(_QWORD, __int64, _QWORD *); // rax
  unsigned int v14; // ebx
  unsigned int v16[4]; // [rsp+30h] [rbp-F8h] BYREF
  _QWORD v17[20]; // [rsp+40h] [rbp-E8h] BYREF

  v3 = *(_QWORD *)(a1 + 104);
  v5 = *(_QWORD *)(a2 + 40);
  v16[0] = 0;
  memset(v17, 0, sizeof(v17));
  if ( v5 == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 32LL) + 24LL) )
  {
    v8 = *(_DWORD *)(a2 + 36);
    v9 = 0;
    do
    {
      v10 = *(_QWORD *)(a3 + 8);
      v16[0] = 4096;
      PhysicalAddress = StorPortGetPhysicalAddress(a1, *(_QWORD *)(v10 + 32), v5, v16);
      v8 -= v16[0];
      v17[v9] = PhysicalAddress;
      if ( v8 <= 0 )
        break;
      v9 = (unsigned int)(v9 + 1);
      v5 += v16[0];
    }
    while ( (unsigned int)v9 < 0x14 );
    v12 = v17[0];
  }
  else
  {
    v12 = *(_QWORD *)(v3 + 1080) + (unsigned int)(v5 - *(_DWORD *)(v3 + 1072));
    v17[0] = v12;
  }
  DbgPrintEx(
    5u,
    2u,
    "UASPSTOR: Issuing URB. Urb: %p, PA: 0x%I64X, Length: %u\n",
    (const void *)a2,
    v12,
    *(_DWORD *)(a2 + 36));
  v13 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(v3 + 1040);
  if ( !v13 )
    v13 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(v3 + 1032);
  v14 = v13(*(_QWORD *)(v3 + 1016), a2, v17);
  DbgPrintEx(5u, 2u, "UASPSTOR: URB completion. Urb: %p, Status: 0x%lX\n", (const void *)a2, v14);
  if ( v14 != 259 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a3 + 24))(
      *(_QWORD *)(a3 + 8),
      *(_QWORD *)a3,
      v14,
      *(_QWORD *)(a3 + 32));
  return v14;
}

```

## disassembly

```asm
0x1400019d0  mov     [rsp+arg_18], rbx
0x1400019d5  push    rbp
0x1400019d6  push    rsi
0x1400019d7  push    rdi
0x1400019d8  push    r12
0x1400019da  push    r13
0x1400019dc  push    r14
0x1400019de  push    r15
0x1400019e0  sub     rsp, 0F0h
0x1400019e7  mov     rax, cs:__security_cookie
0x1400019ee  xor     rax, rsp
0x1400019f1  mov     [rsp+128h+var_48], rax
0x1400019f9  mov     rbp, [rcx+68h]
0x1400019fd  mov     rdi, r8
0x140001a00  mov     rbx, [rdx+28h]
0x140001a04  mov     r14, rdx
0x140001a07  mov     r13, rcx
0x140001a0a  mov     [rsp+128h+var_F8], 0
0x140001a12  xor     edx, edx; Val
0x140001a14  lea     rcx, [rsp+128h+var_E8]; void *
0x140001a19  mov     r8d, 0A0h; Size
0x140001a1f  call    memset
0x140001a24  mov     rax, [rdi+8]
0x140001a28  mov     rcx, [rax+20h]
0x140001a2c  cmp     rbx, [rcx+18h]
0x140001a30  jnz     short loc_140001A83
0x140001a32  mov     r12d, [r14+24h]
0x140001a36  xor     esi, esi
0x140001a38  mov     rdx, [rdi+8]
0x140001a3c  lea     r9, [rsp+128h+var_F8]
0x140001a41  mov     [rsp+128h+var_F8], 1000h
0x140001a49  mov     r8, rbx
0x140001a4c  mov     rcx, r13
0x140001a4f  mov     rdx, [rdx+20h]
0x140001a53  call    cs:__imp_StorPortGetPhysicalAddress
0x140001a5a  nop     dword ptr [rax+rax+00h]
0x140001a5f  sub     r12d, [rsp+128h+var_F8]
0x140001a64  mov     [rsp+rsi*8+128h+var_E8], rax
0x140001a69  test    r12d, r12d
0x140001a6c  jle     short loc_140001A7C
0x140001a6e  mov     eax, [rsp+128h+var_F8]
0x140001a72  inc     esi
0x140001a74  add     rbx, rax
0x140001a77  cmp     esi, 14h
0x140001a7a  jb      short loc_140001A38
0x140001a7c  mov     rcx, [rsp+128h+var_E8]
0x140001a81  jmp     short loc_140001A97
0x140001a83  sub     ebx, [rbp+430h]
0x140001a89  mov     ecx, ebx
0x140001a8b  add     rcx, [rbp+438h]
0x140001a92  mov     [rsp+128h+var_E8], rcx
0x140001a97  mov     eax, [r14+24h]
0x140001a9b  lea     r8, Format; "UASPSTOR: Issuing URB. Urb: %p, PA: 0x%"...
0x140001aa2  mov     esi, 2
0x140001aa7  mov     [rsp+128h+var_100], eax
0x140001aab  mov     [rsp+128h+var_108], rcx
0x140001ab0  mov     r9, r14
0x140001ab3  mov     edx, esi; Level
0x140001ab5  lea     r15d, [rsi+3]
0x140001ab9  mov     ecx, r15d; ComponentId
0x140001abc  call    cs:__imp_DbgPrintEx
0x140001ac3  nop     dword ptr [rax+rax+00h]
0x140001ac8  mov     rax, [rbp+410h]
0x140001acf  lea     r8, [rsp+128h+var_E8]
0x140001ad4  mov     rcx, [rbp+3F8h]
0x140001adb  mov     rdx, r14
0x140001ade  test    rax, rax
0x140001ae1  jnz     short loc_140001AEA
0x140001ae3  mov     rax, [rbp+408h]
0x140001aea  call    _guard_dispatch_icall
0x140001aef  mov     r9, r14
0x140001af2  mov     dword ptr [rsp+128h+var_108], eax
0x140001af6  lea     r8, aUaspstorUrbCom; "UASPSTOR: URB completion. Urb: %p, Stat"...
0x140001afd  mov     edx, esi; Level
0x140001aff  mov     ecx, r15d; ComponentId
0x140001b02  mov     ebx, eax
0x140001b04  call    cs:__imp_DbgPrintEx
0x140001b0b  nop     dword ptr [rax+rax+00h]
0x140001b10  cmp     ebx, 103h
0x140001b16  jz      short loc_140001B2F
0x140001b18  mov     rax, [rdi+18h]
0x140001b1c  mov     r8d, ebx
0x140001b1f  mov     r9, [rdi+20h]
0x140001b23  mov     rdx, [rdi]
0x140001b26  mov     rcx, [rdi+8]
0x140001b2a  call    _guard_dispatch_icall
0x140001b2f  mov     eax, ebx
0x140001b31  mov     rcx, [rsp+128h+var_48]
0x140001b39  xor     rcx, rsp; StackCookie
0x140001b3c  call    __security_check_cookie
0x140001b41  mov     rbx, [rsp+128h+arg_18]
0x140001b49  add     rsp, 0F0h
0x140001b50  pop     r15
0x140001b52  pop     r14
0x140001b54  pop     r13
0x140001b56  pop     r12
0x140001b58  pop     rdi
0x140001b59  pop     rsi
0x140001b5a  pop     rbp
0x140001b5b  retn
```
