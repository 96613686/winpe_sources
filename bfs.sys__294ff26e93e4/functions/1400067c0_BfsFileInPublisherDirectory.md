# BfsFileInPublisherDirectory

- ea: `0x1400067c0`
- end: `0x140006999`
- name: `BfsFileInPublisherDirectory`
- size: `473`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140005768`

## callees

- `0x140001008`
- `0x1400067c0`
- `0x140006c84`
- `0x14000761c`
- `0x14000aaa4`
- `0x140011bc8`
- `0x140011c40`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14000689b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400068e7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000689b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400068e7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000696a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000696a`

## string_xrefs

- `0x1400067f5`: `ProgramData`

## pseudocode

```c
__int64 __fastcall BfsFileInPublisherDirectory(__int64 a1, __int64 a2, _BYTE *a3, __int64 a4)
{
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  int PublisherIdFromToken; // ebx
  int v12; // ecx
  __int16 *v13; // rcx
  __int64 v14; // r8
  int v16; // [rsp+20h] [rbp-89h]
  int v17; // [rsp+30h] [rbp-79h] BYREF
  __int128 v18; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-61h] BYREF
  __int16 v20[8]; // [rsp+58h] [rbp-51h] BYREF
  UNICODE_STRING String2; // [rsp+68h] [rbp-41h] BYREF
  UNICODE_STRING String1; // [rsp+78h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+88h] [rbp-21h] BYREF
  int *v24; // [rsp+A8h] [rbp-1h]
  __int64 v25; // [rsp+B0h] [rbp+7h]

  *(_QWORD *)&String2.Length = 1572886;
  *a3 = 0;
  String1 = 0;
  String2.Buffer = L"ProgramData";
  UnicodeString = 0;
  if ( !*(_WORD *)(a2 + 40) )
  {
    PublisherIdFromToken = 0;
    if ( !RtlEqualUnicodeString((PCUNICODE_STRING)(a2 + 24), &gBfsBootDevice, 1u) )
      goto LABEL_16;
    v18 = *(_OWORD *)BfsGetFileName(v20, a2);
    v18 = *(_OWORD *)BfsGetPathComponent(v20, &v18, (__int64)&String1);
    if ( !RtlEqualUnicodeString(&String1, &String2, 1u) )
      goto LABEL_16;
    BfsGetPathComponent(v20, &v18, (__int64)&String1);
    PublisherIdFromToken = BfsGetPublisherIdFromToken(a1, &UnicodeString);
    if ( PublisherIdFromToken < 0 )
    {
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_16;
      v17 = PublisherIdFromToken;
      goto LABEL_5;
    }
    if ( !(unsigned __int8)BfsUnicodeStringEndsWith(&String1, &UnicodeString) )
      goto LABEL_16;
    v13 = v20;
LABEL_15:
    v18 = *(_OWORD *)BfsGetFileName(v13, a2);
    BfsGetPathComponentEx(v20, &v18, v14, a4);
    *a3 = 1;
    goto LABEL_16;
  }
  v8 = BfsGetPublisherIdFromToken(a1, &UnicodeString);
  PublisherIdFromToken = v8;
  if ( v8 >= 0 )
  {
    if ( !(unsigned __int8)BfsUnicodeStringEndsWith(a2 + 40, &UnicodeString) )
      goto LABEL_16;
    v13 = (__int16 *)&v18;
    goto LABEL_15;
  }
  v12 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v17 = v8;
LABEL_5:
    v25 = 4;
    v24 = &v17;
    tlgWriteTransfer_EtwWriteTransfer(v12, (int)&byte_140016D91, v9, v10, v16, &v23);
  }
LABEL_16:
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)PublisherIdFromToken;
}

```

## disassembly

```asm
0x1400067c0  push    rbp
0x1400067c2  push    rbx
0x1400067c3  push    rsi
0x1400067c4  push    rdi
0x1400067c5  push    r12
0x1400067c7  push    r13
0x1400067c9  push    r14
0x1400067cb  push    r15
0x1400067cd  lea     rbp, [rsp-1Fh]
0x1400067d2  sub     rsp, 0C8h
0x1400067d9  mov     rax, cs:__security_cookie
0x1400067e0  xor     rax, rsp
0x1400067e3  mov     [rbp+57h+var_48], rax
0x1400067e7  xor     r13d, r13d
0x1400067ea  mov     qword ptr [rbp+57h+String2.Length], 180016h
0x1400067f2  mov     [r8], r13b
0x1400067f5  lea     rax, aProgramdata; "ProgramData"
0x1400067fc  xorps   xmm0, xmm0
0x1400067ff  xorps   xmm1, xmm1
0x140006802  mov     r12, r9
0x140006805  mov     r14, r8
0x140006808  mov     rdi, rdx
0x14000680b  mov     rsi, rcx
0x14000680e  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140006812  mov     [rbp+57h+String2.Buffer], rax
0x140006816  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x14000681a  cmp     [rdx+28h], r13w
0x14000681f  jbe     short loc_14000688A
0x140006821  lea     rdx, [rbp+57h+UnicodeString]
0x140006825  call    BfsGetPublisherIdFromToken
0x14000682a  mov     ebx, eax
0x14000682c  test    eax, eax
0x14000682e  jns     short loc_14000686C
0x140006830  mov     ecx, cs:dword_140019000; int
0x140006836  cmp     ecx, 3
0x140006839  jbe     loc_140006966
0x14000683f  mov     [rbp+57h+var_D0], eax
0x140006842  lea     rax, [rbp+57h+var_D0]
0x140006846  mov     [rbp+57h+var_50], 4
0x14000684e  mov     [rbp+57h+var_58], rax
0x140006852  lea     rdx, byte_140016D91; int
0x140006859  lea     rax, [rbp+57h+var_78]
0x14000685d  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140006862  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006867  jmp     loc_140006966
0x14000686c  lea     rdx, [rbp+57h+UnicodeString]
0x140006870  lea     rcx, [rdi+28h]
0x140006874  call    BfsUnicodeStringEndsWith
0x140006879  test    al, al
0x14000687b  jz      loc_140006966
0x140006881  lea     rcx, [rbp+57h+var_C8]
0x140006885  jmp     loc_140006942
0x14000688a  lea     rcx, [rdx+18h]; String1
0x14000688e  mov     r8b, 1; CaseInSensitive
0x140006891  lea     rdx, gBfsBootDevice; String2
0x140006898  mov     ebx, r13d
0x14000689b  call    cs:__imp_RtlEqualUnicodeString
0x1400068a2  nop     dword ptr [rax+rax+00h]
0x1400068a7  test    al, al
0x1400068a9  jz      loc_140006966
0x1400068af  mov     rdx, rdi
0x1400068b2  lea     rcx, [rbp+57h+var_A8]
0x1400068b6  call    BfsGetFileName
0x1400068bb  lea     r8, [rbp+57h+String1]
0x1400068bf  lea     rdx, [rbp+57h+var_C8]
0x1400068c3  lea     rcx, [rbp+57h+var_A8]
0x1400068c7  movups  xmm1, xmmword ptr [rax]
0x1400068ca  movdqu  [rbp+57h+var_C8], xmm1
0x1400068cf  call    BfsGetPathComponent
0x1400068d4  mov     r8b, 1; CaseInSensitive
0x1400068d7  lea     rdx, [rbp+57h+String2]; String2
0x1400068db  lea     rcx, [rbp+57h+String1]; String1
0x1400068df  movups  xmm1, xmmword ptr [rax]
0x1400068e2  movdqu  [rbp+57h+var_C8], xmm1
0x1400068e7  call    cs:__imp_RtlEqualUnicodeString
0x1400068ee  nop     dword ptr [rax+rax+00h]
0x1400068f3  test    al, al
0x1400068f5  jz      short loc_140006966
0x1400068f7  lea     r8, [rbp+57h+String1]
0x1400068fb  lea     rdx, [rbp+57h+var_C8]
0x1400068ff  lea     rcx, [rbp+57h+var_A8]
0x140006903  call    BfsGetPathComponent
0x140006908  lea     rdx, [rbp+57h+UnicodeString]
0x14000690c  mov     rcx, rsi
0x14000690f  call    BfsGetPublisherIdFromToken
0x140006914  mov     ebx, eax
0x140006916  test    eax, eax
0x140006918  jns     short loc_14000692D
0x14000691a  mov     eax, cs:dword_140019000
0x140006920  cmp     eax, 3
0x140006923  jbe     short loc_140006966
0x140006925  mov     [rbp+57h+var_D0], ebx
0x140006928  jmp     loc_140006842
0x14000692d  lea     rdx, [rbp+57h+UnicodeString]
0x140006931  lea     rcx, [rbp+57h+String1]
0x140006935  call    BfsUnicodeStringEndsWith
0x14000693a  test    al, al
0x14000693c  jz      short loc_140006966
0x14000693e  lea     rcx, [rbp+57h+var_A8]
0x140006942  mov     rdx, rdi
0x140006945  call    BfsGetFileName
0x14000694a  mov     r9, r12
0x14000694d  lea     rdx, [rbp+57h+var_C8]
0x140006951  lea     rcx, [rbp+57h+var_A8]
0x140006955  movups  xmm1, xmmword ptr [rax]
0x140006958  movdqu  [rbp+57h+var_C8], xmm1
0x14000695d  call    BfsGetPathComponentEx
0x140006962  mov     byte ptr [r14], 1
0x140006966  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x14000696a  call    cs:__imp_RtlFreeUnicodeString
0x140006971  nop     dword ptr [rax+rax+00h]
0x140006976  mov     eax, ebx
0x140006978  mov     rcx, [rbp+57h+var_48]
0x14000697c  xor     rcx, rsp; StackCookie
0x14000697f  call    __security_check_cookie
0x140006984  add     rsp, 0C8h
0x14000698b  pop     r15
0x14000698d  pop     r14
0x14000698f  pop     r13
0x140006991  pop     r12
0x140006993  pop     rdi
0x140006994  pop     rsi
0x140006995  pop     rbx
0x140006996  pop     rbp
0x140006997  retn
```
