# BfsFileInPublisherDirectory

- ea: `0x140006630`
- end: `0x140006809`
- name: `BfsFileInPublisherDirectory`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400055d8`

## callees

- `0x140001008`
- `0x140006630`
- `0x140006af4`
- `0x14000748c`
- `0x14000a914`
- `0x140011a38`
- `0x140011ab0`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14000670b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006757`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000670b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006757`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400067da`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400067da`

## string_xrefs

- `0x140006665`: `ProgramData`

## pseudocode

```c
__int64 __fastcall BfsFileInPublisherDirectory(__int64 a1, __int64 a2, _BYTE *a3, __int64 a4)
{
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  int PublisherIdFromToken; // ebx
  __int64 v12; // rcx
  __int128 *v13; // rcx
  __int64 v14; // r8
  int v16; // [rsp+20h] [rbp-89h]
  int v17; // [rsp+30h] [rbp-79h] BYREF
  __int128 v18; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v20[16]; // [rsp+58h] [rbp-51h] BYREF
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
    v18 = *(_OWORD *)BfsGetPathComponent(v20, &v18, &String1);
    if ( !RtlEqualUnicodeString(&String1, &String2, 1u) )
      goto LABEL_16;
    BfsGetPathComponent(v20, &v18, &String1);
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
    v13 = (__int128 *)v20;
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
    v13 = &v18;
    goto LABEL_15;
  }
  v12 = (unsigned int)dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v17 = v8;
LABEL_5:
    v25 = 4;
    v24 = &v17;
    tlgWriteTransfer_EtwWriteTransfer(v12, (unsigned __int8 *)&byte_140016D91, v9, v10, v16, &v23);
  }
LABEL_16:
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)PublisherIdFromToken;
}

```

## disassembly

```asm
0x140006630  push    rbp
0x140006632  push    rbx
0x140006633  push    rsi
0x140006634  push    rdi
0x140006635  push    r12
0x140006637  push    r13
0x140006639  push    r14
0x14000663b  push    r15
0x14000663d  lea     rbp, [rsp-1Fh]
0x140006642  sub     rsp, 0C8h
0x140006649  mov     rax, cs:__security_cookie
0x140006650  xor     rax, rsp
0x140006653  mov     [rbp+57h+var_48], rax
0x140006657  xor     r13d, r13d
0x14000665a  mov     qword ptr [rbp+57h+String2.Length], 180016h
0x140006662  mov     [r8], r13b
0x140006665  lea     rax, aProgramdata; "ProgramData"
0x14000666c  xorps   xmm0, xmm0
0x14000666f  xorps   xmm1, xmm1
0x140006672  mov     r12, r9
0x140006675  mov     r14, r8
0x140006678  mov     rdi, rdx
0x14000667b  mov     rsi, rcx
0x14000667e  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140006682  mov     [rbp+57h+String2.Buffer], rax
0x140006686  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x14000668a  cmp     [rdx+28h], r13w
0x14000668f  jbe     short loc_1400066FA
0x140006691  lea     rdx, [rbp+57h+UnicodeString]
0x140006695  call    BfsGetPublisherIdFromToken
0x14000669a  mov     ebx, eax
0x14000669c  test    eax, eax
0x14000669e  jns     short loc_1400066DC
0x1400066a0  mov     ecx, cs:dword_140019000; int
0x1400066a6  cmp     ecx, 3
0x1400066a9  jbe     loc_1400067D6
0x1400066af  mov     [rbp+57h+var_D0], eax
0x1400066b2  lea     rax, [rbp+57h+var_D0]
0x1400066b6  mov     [rbp+57h+var_50], 4
0x1400066be  mov     [rbp+57h+var_58], rax
0x1400066c2  lea     rdx, byte_140016D91; int
0x1400066c9  lea     rax, [rbp+57h+var_78]
0x1400066cd  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x1400066d2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400066d7  jmp     loc_1400067D6
0x1400066dc  lea     rdx, [rbp+57h+UnicodeString]
0x1400066e0  lea     rcx, [rdi+28h]
0x1400066e4  call    BfsUnicodeStringEndsWith
0x1400066e9  test    al, al
0x1400066eb  jz      loc_1400067D6
0x1400066f1  lea     rcx, [rbp+57h+var_C8]
0x1400066f5  jmp     loc_1400067B2
0x1400066fa  lea     rcx, [rdx+18h]; String1
0x1400066fe  mov     r8b, 1; CaseInSensitive
0x140006701  lea     rdx, gBfsBootDevice; String2
0x140006708  mov     ebx, r13d
0x14000670b  call    cs:__imp_RtlEqualUnicodeString
0x140006712  nop     dword ptr [rax+rax+00h]
0x140006717  test    al, al
0x140006719  jz      loc_1400067D6
0x14000671f  mov     rdx, rdi
0x140006722  lea     rcx, [rbp+57h+var_A8]
0x140006726  call    BfsGetFileName
0x14000672b  lea     r8, [rbp+57h+String1]
0x14000672f  lea     rdx, [rbp+57h+var_C8]
0x140006733  lea     rcx, [rbp+57h+var_A8]
0x140006737  movups  xmm1, xmmword ptr [rax]
0x14000673a  movdqu  [rbp+57h+var_C8], xmm1
0x14000673f  call    BfsGetPathComponent
0x140006744  mov     r8b, 1; CaseInSensitive
0x140006747  lea     rdx, [rbp+57h+String2]; String2
0x14000674b  lea     rcx, [rbp+57h+String1]; String1
0x14000674f  movups  xmm1, xmmword ptr [rax]
0x140006752  movdqu  [rbp+57h+var_C8], xmm1
0x140006757  call    cs:__imp_RtlEqualUnicodeString
0x14000675e  nop     dword ptr [rax+rax+00h]
0x140006763  test    al, al
0x140006765  jz      short loc_1400067D6
0x140006767  lea     r8, [rbp+57h+String1]
0x14000676b  lea     rdx, [rbp+57h+var_C8]
0x14000676f  lea     rcx, [rbp+57h+var_A8]
0x140006773  call    BfsGetPathComponent
0x140006778  lea     rdx, [rbp+57h+UnicodeString]
0x14000677c  mov     rcx, rsi
0x14000677f  call    BfsGetPublisherIdFromToken
0x140006784  mov     ebx, eax
0x140006786  test    eax, eax
0x140006788  jns     short loc_14000679D
0x14000678a  mov     eax, cs:dword_140019000
0x140006790  cmp     eax, 3
0x140006793  jbe     short loc_1400067D6
0x140006795  mov     [rbp+57h+var_D0], ebx
0x140006798  jmp     loc_1400066B2
0x14000679d  lea     rdx, [rbp+57h+UnicodeString]
0x1400067a1  lea     rcx, [rbp+57h+String1]
0x1400067a5  call    BfsUnicodeStringEndsWith
0x1400067aa  test    al, al
0x1400067ac  jz      short loc_1400067D6
0x1400067ae  lea     rcx, [rbp+57h+var_A8]
0x1400067b2  mov     rdx, rdi
0x1400067b5  call    BfsGetFileName
0x1400067ba  mov     r9, r12
0x1400067bd  lea     rdx, [rbp+57h+var_C8]
0x1400067c1  lea     rcx, [rbp+57h+var_A8]
0x1400067c5  movups  xmm1, xmmword ptr [rax]
0x1400067c8  movdqu  [rbp+57h+var_C8], xmm1
0x1400067cd  call    BfsGetPathComponentEx
0x1400067d2  mov     byte ptr [r14], 1
0x1400067d6  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1400067da  call    cs:__imp_RtlFreeUnicodeString
0x1400067e1  nop     dword ptr [rax+rax+00h]
0x1400067e6  mov     eax, ebx
0x1400067e8  mov     rcx, [rbp+57h+var_48]
0x1400067ec  xor     rcx, rsp; StackCookie
0x1400067ef  call    __security_check_cookie
0x1400067f4  add     rsp, 0C8h
0x1400067fb  pop     r15
0x1400067fd  pop     r14
0x1400067ff  pop     r13
0x140006801  pop     r12
0x140006803  pop     rdi
0x140006804  pop     rsi
0x140006805  pop     rbx
0x140006806  pop     rbp
0x140006807  retn
```
