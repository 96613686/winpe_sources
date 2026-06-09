# WimpFSFIntegrityReportReadFailure

- ea: `0x140029f78`
- end: `0x14002a087`
- name: `WimpFSFIntegrityReportReadFailure`
- size: `271`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140027ffc`
- `0x14002962c`

## callees

- `0x140011560`
- `0x1400295e4`
- `0x140029f78`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140029fb8`
- `ntoskrnl!EtwEventEnabled` at `0x140029fb8`
- `ntoskrnl!EtwWrite` at `0x14002a058`
- `ntoskrnl!EtwWrite` at `0x14002a058`

## pseudocode

```c
void __fastcall WimpFSFIntegrityReportReadFailure(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rdx
  int v5; // ecx
  __int16 v6; // [rsp+30h] [rbp-9h] BYREF
  __int64 v7; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp+7h] BYREF
  __int64 v9; // [rsp+50h] [rbp+17h]
  int v10; // [rsp+58h] [rbp+1Fh]
  int v11; // [rsp+5Ch] [rbp+23h]
  __int64 *v12; // [rsp+60h] [rbp+27h]
  __int64 v13; // [rsp+68h] [rbp+2Fh]
  int *v14; // [rsp+70h] [rbp+37h]
  __int64 v15; // [rsp+78h] [rbp+3Fh]
  int v16; // [rsp+B0h] [rbp+77h] BYREF

  v16 = a3;
  v7 = a2;
  v6 = 0;
  if ( EtwEventEnabled(g_WimIntegrityEtwEventHandle, &WofIntegrityInvalidBlockEventId)
    && _InterlockedIncrement((volatile signed __int32 *)(a1 + 192)) <= 8 )
  {
    v4 = *(_QWORD *)(a1 + 160);
    v6 = *(_WORD *)(v4 + 88) >> 1;
    UserData.Ptr = (ULONGLONG)&v6;
    *(_QWORD *)&UserData.Size = 2;
    v5 = *(unsigned __int16 *)(v4 + 88);
    v9 = *(_QWORD *)(v4 + 96);
    v12 = &v7;
    v14 = &v16;
    v10 = v5;
    v11 = 0;
    v13 = 8;
    v15 = 4;
    EtwWrite(g_WimIntegrityEtwEventHandle, &WofIntegrityInvalidBlockEventId, 0, 4u, &UserData);
  }
  WimpFSFBreakForIntegrityFailure();
}

```

## disassembly

```asm
0x140029f78  mov     [rsp-8+arg_18], rbx
0x140029f7d  mov     [rsp-8+arg_10], r8d
0x140029f82  push    rbp
0x140029f83  lea     rbp, [rsp-57h]
0x140029f88  sub     rsp, 90h
0x140029f8f  mov     rax, cs:__security_cookie
0x140029f96  xor     rax, rsp
0x140029f99  mov     [rbp+57h+var_10], rax
0x140029f9d  mov     rbx, rcx
0x140029fa0  mov     [rbp+57h+var_58], rdx
0x140029fa4  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x140029fab  lea     rdx, WofIntegrityInvalidBlockEventId; EventDescriptor
0x140029fb2  xor     eax, eax
0x140029fb4  mov     [rbp+57h+var_60], ax
0x140029fb8  call    cs:__imp_EtwEventEnabled
0x140029fbf  nop     dword ptr [rax+rax+00h]
0x140029fc4  test    al, al
0x140029fc6  jz      loc_14002A064
0x140029fcc  mov     eax, 1
0x140029fd1  lock xadd [rbx+0C0h], eax
0x140029fd9  inc     eax
0x140029fdb  cmp     eax, 8
0x140029fde  jg      loc_14002A064
0x140029fe4  mov     rdx, [rbx+0A0h]
0x140029feb  mov     r9d, 4; UserDataCount
0x140029ff1  xor     r8d, r8d; ActivityId
0x140029ff4  movzx   eax, word ptr [rdx+58h]
0x140029ff8  shr     ax, 1
0x140029ffb  mov     [rbp+57h+var_60], ax
0x140029fff  lea     rax, [rbp+57h+var_60]
0x14002a003  mov     [rbp+57h+var_50.Ptr], rax
0x14002a007  mov     qword ptr [rbp+57h+var_50.Size], 2
0x14002a00f  mov     rax, [rdx+60h]
0x14002a013  movzx   ecx, word ptr [rdx+58h]
0x14002a017  lea     rdx, WofIntegrityInvalidBlockEventId; EventDescriptor
0x14002a01e  mov     [rbp+57h+var_40], rax
0x14002a022  lea     rax, [rbp+57h+var_58]
0x14002a026  mov     [rbp+57h+var_30], rax
0x14002a02a  lea     rax, [rbp+57h+arg_10]
0x14002a02e  mov     [rbp+57h+var_20], rax
0x14002a032  lea     rax, [rbp+57h+var_50]
0x14002a036  mov     [rbp+57h+var_38], ecx
0x14002a039  mov     rcx, cs:g_WimIntegrityEtwEventHandle; RegHandle
0x14002a040  mov     [rsp+90h+UserData], rax; UserData
0x14002a045  mov     [rbp+57h+var_34], 0
0x14002a04c  mov     [rbp+57h+var_28], 8
0x14002a054  mov     [rbp+57h+var_18], r9
0x14002a058  call    cs:__imp_EtwWrite
0x14002a05f  nop     dword ptr [rax+rax+00h]
0x14002a064  call    WimpFSFBreakForIntegrityFailure
0x14002a069  mov     rcx, [rbp+57h+var_10]
0x14002a06d  xor     rcx, rsp; StackCookie
0x14002a070  call    __security_check_cookie
0x14002a075  mov     rbx, [rsp+90h+arg_18]
0x14002a07d  add     rsp, 90h
0x14002a084  pop     rbp
0x14002a085  retn
```
