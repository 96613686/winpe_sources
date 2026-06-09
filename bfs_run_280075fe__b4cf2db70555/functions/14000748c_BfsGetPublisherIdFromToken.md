# BfsGetPublisherIdFromToken

- ea: `0x14000748c`
- end: `0x14000760e`
- name: `BfsGetPublisherIdFromToken`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140006630`

## callees

- `0x140001008`
- `0x14000748c`
- `0x140013730`
- `0x140013b40`
- `0x14001ecc8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140007548`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007548`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400075dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400075dc`
- `ntoskrnl!ExAllocatePool2` at `0x140007574`
- `ntoskrnl!ExAllocatePool2` at `0x140007574`
- `ntoskrnl!RtlQueryPackageIdentityEx` at `0x140007518`
- `ntoskrnl!RtlQueryPackageIdentityEx` at `0x140007518`

## pseudocode

```c
__int64 __fastcall BfsGetPublisherIdFromToken(__int64 a1, struct _UNICODE_STRING *a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 Pool2; // rax
  __int64 v11; // rdx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+68h] [rbp-98h] BYREF
  int *v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  WCHAR SourceString[128]; // [rsp+A0h] [rbp-60h] BYREF

  v14 = 0;
  DestinationString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  v15 = 256;
  *(_DWORD *)&a2->Length = 0;
  a2->Buffer = 0;
  v4 = RtlQueryPackageIdentityEx(a1, SourceString, &v15, 0);
  v7 = v4;
  if ( v4 < 0 )
  {
    v8 = (unsigned int)dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v13 = v4;
LABEL_10:
      v19 = 4;
      v18 = &v13;
      tlgWriteTransfer_EtwWriteTransfer(v8, (unsigned __int8 *)&byte_140016D91, v5, v6, 0, &v17);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v7 = KappxParsePackageFullNameFromToken(&DestinationString, v9, a2);
  if ( v7 < 0 )
    goto LABEL_8;
  Pool2 = ExAllocatePool2(256, a2->MaximumLength, 1316185666);
  a2->Buffer = (PWSTR)Pool2;
  if ( !Pool2 )
  {
    v7 = -1073741801;
    goto LABEL_8;
  }
  v7 = KappxParsePackageFullNameFromToken(&DestinationString, v11, a2);
  if ( v7 < 0 )
  {
LABEL_8:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v13 = v7;
      goto LABEL_10;
    }
LABEL_11:
    RtlFreeUnicodeString(a2);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000748c  mov     [rsp-8+arg_10], rbx
0x140007491  push    rbp
0x140007492  push    rdi
0x140007493  push    r14
0x140007495  lea     rbp, [rsp-0B0h]
0x14000749d  sub     rsp, 1B0h
0x1400074a4  mov     rax, cs:__security_cookie
0x1400074ab  xor     rax, rsp
0x1400074ae  mov     [rbp+0C0h+var_20], rax
0x1400074b5  mov     rdi, rdx
0x1400074b8  mov     [rsp+1C0h+var_178], 0
0x1400074c1  mov     rbx, rcx
0x1400074c4  xorps   xmm0, xmm0
0x1400074c7  mov     r14d, 100h
0x1400074cd  lea     rcx, [rbp+0C0h+SourceString]; void *
0x1400074d1  mov     r8d, r14d; Size
0x1400074d4  xor     edx, edx; Val
0x1400074d6  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x1400074db  call    memset
0x1400074e0  xor     eax, eax
0x1400074e2  mov     [rsp+1C0h+var_170], r14
0x1400074e7  mov     [rdi], eax
0x1400074e9  lea     r8, [rsp+1C0h+var_170]
0x1400074ee  mov     [rdi+8], rax
0x1400074f2  lea     rdx, [rbp+0C0h+SourceString]
0x1400074f6  lea     rax, [rsp+1C0h+var_178]
0x1400074fb  xor     r9d, r9d
0x1400074fe  mov     [rsp+1C0h+var_190], rax
0x140007503  mov     rcx, rbx
0x140007506  mov     [rsp+1C0h+var_198], 0
0x14000750f  mov     qword ptr [rsp+1C0h+var_1A0], 0; int
0x140007518  call    cs:__imp_RtlQueryPackageIdentityEx
0x14000751f  nop     dword ptr [rax+rax+00h]
0x140007524  mov     ebx, eax
0x140007526  test    eax, eax
0x140007528  jns     short loc_14000753F
0x14000752a  mov     ecx, cs:dword_140019000
0x140007530  cmp     ecx, 3
0x140007533  jbe     loc_1400075D9
0x140007539  mov     [rsp+1C0h+var_180], eax
0x14000753d  jmp     short loc_1400075B2
0x14000753f  lea     rdx, [rbp+0C0h+SourceString]; SourceString
0x140007543  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x140007548  call    cs:__imp_RtlInitUnicodeString
0x14000754f  nop     dword ptr [rax+rax+00h]
0x140007554  mov     r8, rdi
0x140007557  lea     rcx, [rsp+1C0h+DestinationString]
0x14000755c  call    KappxParsePackageFullNameFromToken
0x140007561  mov     ebx, eax
0x140007563  test    eax, eax
0x140007565  js      short loc_1400075A3
0x140007567  movzx   edx, word ptr [rdi+2]
0x14000756b  mov     r8d, 4E736642h
0x140007571  mov     rcx, r14
0x140007574  call    cs:__imp_ExAllocatePool2
0x14000757b  nop     dword ptr [rax+rax+00h]
0x140007580  mov     [rdi+8], rax
0x140007584  test    rax, rax
0x140007587  jnz     short loc_140007590
0x140007589  mov     ebx, 0C0000017h
0x14000758e  jmp     short loc_1400075A3
0x140007590  mov     r8, rdi
0x140007593  lea     rcx, [rsp+1C0h+DestinationString]
0x140007598  call    KappxParsePackageFullNameFromToken
0x14000759d  mov     ebx, eax
0x14000759f  test    eax, eax
0x1400075a1  jns     short loc_1400075E8
0x1400075a3  mov     eax, cs:dword_140019000
0x1400075a9  cmp     eax, 3
0x1400075ac  jbe     short loc_1400075D9
0x1400075ae  mov     [rsp+1C0h+var_180], ebx
0x1400075b2  lea     rax, [rsp+1C0h+var_180]
0x1400075b7  mov     [rbp+0C0h+var_130], 4
0x1400075bf  mov     [rbp+0C0h+var_138], rax
0x1400075c3  lea     rdx, byte_140016D91; int
0x1400075ca  lea     rax, [rsp+1C0h+var_158]
0x1400075cf  mov     [rsp+1C0h+var_198], rax; PEVENT_DATA_DESCRIPTOR
0x1400075d4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400075d9  mov     rcx, rdi; UnicodeString
0x1400075dc  call    cs:__imp_RtlFreeUnicodeString
0x1400075e3  nop     dword ptr [rax+rax+00h]
0x1400075e8  mov     eax, ebx
0x1400075ea  mov     rcx, [rbp+0C0h+var_20]
0x1400075f1  xor     rcx, rsp; StackCookie
0x1400075f4  call    __security_check_cookie
0x1400075f9  mov     rbx, [rsp+1C0h+arg_10]
0x140007601  add     rsp, 1B0h
0x140007608  pop     r14
0x14000760a  pop     rdi
0x14000760b  pop     rbp
0x14000760c  retn
```
