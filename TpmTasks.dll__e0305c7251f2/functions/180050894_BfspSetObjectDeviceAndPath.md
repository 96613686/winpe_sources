# BfspSetObjectDeviceAndPath

- ea: `0x180050894`
- end: `0x180050c8d`
- name: `BfspSetObjectDeviceAndPath`
- size: `1017`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004e544`
- `0x18004eb2c`
- `0x18004ed34`
- `0x18004ede8`
- `0x18004f244`

## callees

- `0x1800078b0`
- `0x180008724`
- `0x18004cdd4`
- `0x180050894`
- `0x180050e74`

## import_xrefs

- `bcd!BcdSetElementDataWithFlags` at `0x180050a8a`
- `bcd!BcdSetElementDataWithFlags` at `0x180050aef`
- `bcd!BcdSetElementDataWithFlags` at `0x180050a8a`
- `bcd!BcdSetElementDataWithFlags` at `0x180050aef`
- `bcd!BcdSetElementData` at `0x180050b65`
- `bcd!BcdSetElementData` at `0x180050bfd`
- `bcd!BcdSetElementData` at `0x180050b65`
- `bcd!BcdSetElementData` at `0x180050bfd`
- `bcd!BcdCloseObject` at `0x180050c52`
- `bcd!BcdCloseObject` at `0x180050c62`
- `bcd!BcdCloseObject` at `0x180050c52`
- `bcd!BcdCloseObject` at `0x180050c62`
- `bcd!BcdOpenObject` at `0x180050902`
- `bcd!BcdOpenObject` at `0x180050932`
- `bcd!BcdOpenObject` at `0x180050902`
- `bcd!BcdOpenObject` at `0x180050932`
- `bcd!BcdGetElementData` at `0x180050963`
- `bcd!BcdGetElementData` at `0x1800509fb`
- `bcd!BcdGetElementData` at `0x180050abe`
- `bcd!BcdGetElementData` at `0x180050b9f`
- `bcd!BcdGetElementData` at `0x180050c2b`
- `bcd!BcdGetElementData` at `0x180050963`
- `bcd!BcdGetElementData` at `0x1800509fb`
- `bcd!BcdGetElementData` at `0x180050abe`
- `bcd!BcdGetElementData` at `0x180050b9f`
- `bcd!BcdGetElementData` at `0x180050c2b`

## string_xrefs

- `0x18005090e`: `Failed to get handle to the template store. Status = [%x]`
- `0x180050c09`: `Failed to set element application path. Status = [%x]`
- `0x180050c37`: `Failed to get element application path. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspSetObjectDeviceAndPath(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r12d
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int ElementData; // eax
  const wchar_t *v12; // rdi
  LPVOID v13; // r14
  int v14; // r15d
  int v15; // eax
  int v16; // eax
  __int64 v17; // rsi
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // r9
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v26; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  wchar_t Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[528]; // [rsp+280h] [rbp+180h] BYREF

  v4 = 0;
  v31 = a1;
  v30 = 0;
  v25 = 0;
  v27 = 0;
  v29 = 0;
  v28 = 0;
  v26 = 1;
  v8 = BcdOpenObject(a1, a3, &v28);
  v9 = v8;
  if ( v8 < 0 )
  {
    BfspLogMessage(4, L"Failed to get handle to the template store. Status = [%x]", (unsigned int)v8);
    goto LABEL_42;
  }
  v10 = BcdOpenObject(a2, a4, &v29);
  v9 = v10;
  if ( v10 < 0 )
  {
    BfspLogMessage(4, L"Failed to get handle to the system store. Status = [%x]", (unsigned int)v10);
    goto LABEL_42;
  }
  v25 = 8;
  ElementData = BcdGetElementData(v28, 1157627905, &v30, &v25);
  v9 = ElementData;
  if ( ElementData < 0 )
  {
    BfspLogMessage(4, L"Failed to get element device type. Status = [%x]", (unsigned int)ElementData);
    goto LABEL_42;
  }
  if ( v30 == 1 )
  {
    v12 = L"\\EFI\\Microsoft\\Boot\\";
    v13 = lpMem;
    v14 = dword_1800A4560;
    if ( !byte_1800A4538 )
      v12 = L"\\boot\\";
  }
  else
  {
    if ( v30 != 2 )
    {
      v9 = -1073741637;
      goto LABEL_42;
    }
    v13 = BfspGlobals;
    v14 = dword_1800A4528;
    v12 = (const wchar_t *)qword_1800A4570;
    LOBYTE(v26) = 0;
  }
  v25 = 2;
  if ( qword_1800A4578 )
    v12 = (const wchar_t *)qword_1800A4578;
  BcdGetElementData(v28, 1174405128, &v27, &v25);
  if ( byte_1800A4539 && (v30 != 2 || !byte_1800A453A) )
  {
    v4 = 64;
    BfspLogMessage(2, L"VHD device detection disabled");
  }
  if ( (_BYTE)v27 && byte_1800A4538 )
  {
    v15 = BfspSetParentDevices(a1, a2, v28, v4, 0x11000001u, (__int64)v13, v14);
    v9 = v15;
    if ( v15 < 0 )
    {
LABEL_22:
      BfspLogMessage(4, L"Failed to set parent device. Status = [%x]", (unsigned int)v15);
      goto LABEL_42;
    }
  }
  else
  {
    v16 = BcdSetElementDataWithFlags(v29, 285212673, v4, v13, v14);
    v9 = v16;
    if ( v16 < 0 )
    {
      BfspLogMessage(4, L"Failed to set element application device. Status = [%x]", (unsigned int)v16);
      goto LABEL_42;
    }
  }
  v25 = 2;
  BcdGetElementData(v28, 1174405124, &v26, &v25);
  v17 = -1;
  if ( !(_BYTE)v26 )
  {
    if ( (_BYTE)v27 )
    {
      v15 = BfspSetParentDevices(v31, a2, v28, v4, 0x21000001u, (__int64)v13, v14);
      v9 = v15;
      if ( v15 < 0 )
        goto LABEL_22;
    }
    else
    {
      v18 = BcdSetElementDataWithFlags(v29, 553648129, v4, v13, v14);
      v9 = v18;
      if ( v18 < 0 )
      {
        BfspLogMessage(4, L"Failed to set element OS device. Status = [%x]", (unsigned int)v18);
        goto LABEL_42;
      }
    }
    v19 = -1;
    do
      ++v19;
    while ( v12[v19] );
    v20 = (unsigned int)(2 * v19 + 2);
    v25 = v20;
    v21 = BcdSetElementData(v29, 570425346, v12, v20);
    v9 = v21;
    if ( v21 < 0 )
    {
      BfspLogMessage(4, L"Failed to set element system root. Status = [%x]", (unsigned int)v21);
      goto LABEL_42;
    }
  }
  v25 = 520;
  if ( (int)BcdGetElementData(v28, 1107296258, v33, &v25) < 0 )
  {
    v25 = 520;
    v23 = BcdGetElementData(v28, 301989890, Buffer, &v25);
    v9 = v23;
    if ( v23 < 0 )
    {
      BfspLogMessage(4, L"Failed to get element application path. Status = [%x]", (unsigned int)v23);
      goto LABEL_42;
    }
  }
  else
  {
    swprintf_s(Buffer, 0x104u, L"%s%s", v12, v33);
  }
  do
    ++v17;
  while ( Buffer[v17] );
  v25 = 2 * v17 + 2;
  v22 = BcdSetElementData(v29, 301989890, Buffer, v25);
  v9 = v22;
  if ( v22 < 0 )
    BfspLogMessage(4, L"Failed to set element application path. Status = [%x]", (unsigned int)v22);
LABEL_42:
  if ( v29 )
    BcdCloseObject(v29);
  if ( v28 )
    BcdCloseObject(v28);
  return v9;
}

```

## disassembly

```asm
0x180050894  push    rbp
0x180050896  push    rbx
0x180050897  push    rsi
0x180050898  push    rdi
0x180050899  push    r12
0x18005089b  push    r13
0x18005089d  push    r14
0x18005089f  push    r15
0x1800508a1  lea     rbp, [rsp-3A8h]
0x1800508a9  sub     rsp, 4A8h
0x1800508b0  mov     rax, cs:__security_cookie
0x1800508b7  xor     rax, rsp
0x1800508ba  mov     [rbp+3E0h+var_50], rax
0x1800508c1  xor     r12d, r12d
0x1800508c4  mov     [rsp+4E0h+var_478], rcx
0x1800508c9  mov     rdi, r9
0x1800508cc  mov     [rsp+4E0h+var_49C], r12w
0x1800508d2  mov     r9, r8
0x1800508d5  mov     [rsp+4E0h+var_480], r12
0x1800508da  mov     r13, rdx
0x1800508dd  mov     [rsp+4E0h+var_4A0], r12d
0x1800508e2  mov     rdx, r9
0x1800508e5  mov     [rsp+4E0h+var_498], r12w
0x1800508eb  lea     r8, [rsp+4E0h+var_490]
0x1800508f0  mov     [rsp+4E0h+var_488], r12
0x1800508f5  mov     rsi, rcx
0x1800508f8  mov     [rsp+4E0h+var_490], r12
0x1800508fd  mov     byte ptr [rsp+4E0h+var_49C], 1
0x180050902  call    cs:__imp_BcdOpenObject
0x180050908  mov     ebx, eax
0x18005090a  test    eax, eax
0x18005090c  jns     short loc_180050927
0x18005090e  lea     rdx, aFailedToGetHan_1; "Failed to get handle to the template st"...
0x180050915  mov     r8d, eax
0x180050918  mov     ecx, 4
0x18005091d  call    BfspLogMessage
0x180050922  jmp     loc_180050C48
0x180050927  lea     r8, [rsp+4E0h+var_488]
0x18005092c  mov     rdx, rdi
0x18005092f  mov     rcx, r13
0x180050932  call    cs:__imp_BcdOpenObject
0x180050938  mov     ebx, eax
0x18005093a  test    eax, eax
0x18005093c  jns     short loc_180050947
0x18005093e  lea     rdx, aFailedToGetHan_0; "Failed to get handle to the system stor"...
0x180050945  jmp     short loc_180050915
0x180050947  mov     rcx, [rsp+4E0h+var_490]
0x18005094c  lea     r9, [rsp+4E0h+var_4A0]
0x180050951  lea     r8, [rsp+4E0h+var_480]
0x180050956  mov     [rsp+4E0h+var_4A0], 8
0x18005095e  mov     edx, 45000001h
0x180050963  call    cs:__imp_BcdGetElementData
0x180050969  mov     ebx, eax
0x18005096b  test    eax, eax
0x18005096d  jns     short loc_180050978
0x18005096f  lea     rdx, aFailedToGetEle; "Failed to get element device type. Stat"...
0x180050976  jmp     short loc_180050915
0x180050978  cmp     [rsp+4E0h+var_480], 1
0x18005097e  jnz     short loc_1800509A9
0x180050980  cmp     cs:byte_1800A4538, r12b
0x180050987  lea     rdi, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\"
0x18005098e  mov     r14, cs:lpMem
0x180050995  lea     rax, aBoot_0; "\\boot\\"
0x18005099c  mov     r15d, cs:dword_1800A4560
0x1800509a3  cmovz   rdi, rax
0x1800509a7  jmp     short loc_1800509CF
0x1800509a9  cmp     [rsp+4E0h+var_480], 2
0x1800509af  jnz     loc_180050C43
0x1800509b5  mov     r14, cs:BfspGlobals
0x1800509bc  mov     r15d, cs:dword_1800A4528
0x1800509c3  mov     rdi, cs:qword_1800A4570
0x1800509ca  mov     byte ptr [rsp+4E0h+var_49C], r12b
0x1800509cf  mov     rax, cs:qword_1800A4578
0x1800509d6  lea     r9, [rsp+4E0h+var_4A0]
0x1800509db  mov     rcx, [rsp+4E0h+var_490]
0x1800509e0  lea     r8, [rsp+4E0h+var_498]
0x1800509e5  xor     ebx, ebx
0x1800509e7  mov     [rsp+4E0h+var_4A0], 2
0x1800509ef  test    rax, rax
0x1800509f2  mov     edx, 46000008h
0x1800509f7  cmovnz  rdi, rax
0x1800509fb  call    cs:__imp_BcdGetElementData
0x180050a01  cmp     cs:byte_1800A4539, bl
0x180050a07  jz      short loc_180050A30
0x180050a09  cmp     [rsp+4E0h+var_480], 2
0x180050a0f  jnz     short loc_180050A19
0x180050a11  cmp     cs:byte_1800A453A, bl
0x180050a17  jnz     short loc_180050A30
0x180050a19  mov     r12d, 40h ; '@'
0x180050a1f  lea     rdx, aVhdDeviceDetec; "VHD device detection disabled"
0x180050a26  lea     ecx, [r12-3Eh]
0x180050a2b  call    BfspLogMessage
0x180050a30  cmp     byte ptr [rsp+4E0h+var_498], bl
0x180050a34  jz      short loc_180050A75
0x180050a36  cmp     cs:byte_1800A4538, bl
0x180050a3c  jz      short loc_180050A75
0x180050a3e  mov     r8, [rsp+4E0h+var_490]
0x180050a43  mov     r9d, r12d
0x180050a46  mov     [rsp+4E0h+var_4B0], r15d
0x180050a4b  mov     rdx, r13
0x180050a4e  mov     [rsp+4E0h+var_4B8], r14
0x180050a53  mov     rcx, rsi
0x180050a56  mov     dword ptr [rsp+4E0h+var_4C0], 11000001h
0x180050a5e  call    BfspSetParentDevices
0x180050a63  mov     ebx, eax
0x180050a65  test    eax, eax
0x180050a67  jns     short loc_180050AA2
0x180050a69  lea     rdx, aFailedToSetPar; "Failed to set parent device. Status = ["...
0x180050a70  jmp     loc_180050915
0x180050a75  mov     rcx, [rsp+4E0h+var_488]
0x180050a7a  mov     r9, r14
0x180050a7d  mov     r8d, r12d
0x180050a80  mov     dword ptr [rsp+4E0h+var_4C0], r15d
0x180050a85  mov     edx, 11000001h
0x180050a8a  call    cs:__imp_BcdSetElementDataWithFlags
0x180050a90  mov     ebx, eax
0x180050a92  test    eax, eax
0x180050a94  jns     short loc_180050AA2
0x180050a96  lea     rdx, aFailedToSetEle_3; "Failed to set element application devic"...
0x180050a9d  jmp     loc_180050915
0x180050aa2  mov     rcx, [rsp+4E0h+var_490]
0x180050aa7  lea     r9, [rsp+4E0h+var_4A0]
0x180050aac  lea     r8, [rsp+4E0h+var_49C]
0x180050ab1  mov     [rsp+4E0h+var_4A0], 2
0x180050ab9  mov     edx, 46000004h
0x180050abe  call    cs:__imp_BcdGetElementData
0x180050ac4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180050ac8  cmp     byte ptr [rsp+4E0h+var_49C], 0
0x180050acd  jnz     loc_180050B7D
0x180050ad3  cmp     byte ptr [rsp+4E0h+var_498], 0
0x180050ad8  jnz     short loc_180050B0A
0x180050ada  mov     rcx, [rsp+4E0h+var_488]
0x180050adf  mov     r9, r14
0x180050ae2  mov     r8d, r12d
0x180050ae5  mov     dword ptr [rsp+4E0h+var_4C0], r15d
0x180050aea  mov     edx, 21000001h
0x180050aef  call    cs:__imp_BcdSetElementDataWithFlags
0x180050af5  xor     r12d, r12d
0x180050af8  mov     ebx, eax
0x180050afa  test    eax, eax
0x180050afc  jns     short loc_180050B3E
0x180050afe  lea     rdx, aFailedToSetEle_4; "Failed to set element OS device. Status"...
0x180050b05  jmp     loc_180050915
0x180050b0a  mov     r8, [rsp+4E0h+var_490]
0x180050b0f  mov     r9d, r12d
0x180050b12  mov     rcx, [rsp+4E0h+var_478]
0x180050b17  mov     rdx, r13
0x180050b1a  mov     [rsp+4E0h+var_4B0], r15d
0x180050b1f  mov     [rsp+4E0h+var_4B8], r14
0x180050b24  mov     dword ptr [rsp+4E0h+var_4C0], 21000001h
0x180050b2c  call    BfspSetParentDevices
0x180050b31  xor     r12d, r12d
0x180050b34  mov     ebx, eax
0x180050b36  test    eax, eax
0x180050b38  js      loc_180050A69
0x180050b3e  mov     r9, rsi
0x180050b41  inc     r9
0x180050b44  cmp     [rdi+r9*2], r12w
0x180050b49  jnz     short loc_180050B41
0x180050b4b  mov     rcx, [rsp+4E0h+var_488]
0x180050b50  lea     r9d, ds:2[r9*2]
0x180050b58  mov     r8, rdi
0x180050b5b  mov     [rsp+4E0h+var_4A0], r9d
0x180050b60  mov     edx, 22000002h
0x180050b65  call    cs:__imp_BcdSetElementData
0x180050b6b  mov     ebx, eax
0x180050b6d  test    eax, eax
0x180050b6f  jns     short loc_180050B80
0x180050b71  lea     rdx, aFailedToSetEle_2; "Failed to set element system root. Stat"...
0x180050b78  jmp     loc_180050915
0x180050b7d  xor     r12d, r12d
0x180050b80  mov     rcx, [rsp+4E0h+var_490]
0x180050b85  lea     r9, [rsp+4E0h+var_4A0]
0x180050b8a  mov     ebx, 208h
0x180050b8f  lea     r8, [rbp+3E0h+var_260]
0x180050b96  mov     edx, 42000002h
0x180050b9b  mov     [rsp+4E0h+var_4A0], ebx
0x180050b9f  call    cs:__imp_BcdGetElementData
0x180050ba5  mov     r14d, 12000002h
0x180050bab  test    eax, eax
0x180050bad  js      short loc_180050C15
0x180050baf  lea     rax, [rbp+3E0h+var_260]
0x180050bb6  mov     r9, rdi
0x180050bb9  lea     r8, aSS_0; "%s%s"
0x180050bc0  mov     [rsp+4E0h+var_4C0], rax
0x180050bc5  mov     edx, 104h; BufferCount
0x180050bca  lea     rcx, [rsp+4E0h+Buffer]; Buffer
0x180050bcf  call    swprintf_s
0x180050bd4  lea     rax, [rsp+4E0h+Buffer]
0x180050bd9  inc     rsi
0x180050bdc  cmp     [rax+rsi*2], r12w
0x180050be1  jnz     short loc_180050BD9
0x180050be3  mov     rcx, [rsp+4E0h+var_488]
0x180050be8  lea     r9d, ds:2[rsi*2]
0x180050bf0  lea     r8, [rsp+4E0h+Buffer]
0x180050bf5  mov     [rsp+4E0h+var_4A0], r9d
0x180050bfa  mov     edx, r14d
0x180050bfd  call    cs:__imp_BcdSetElementData
0x180050c03  mov     ebx, eax
0x180050c05  test    eax, eax
0x180050c07  jns     short loc_180050C48
0x180050c09  lea     rdx, aFailedToSetEle_1; "Failed to set element application path."...
0x180050c10  jmp     loc_180050915
0x180050c15  mov     rcx, [rsp+4E0h+var_490]
0x180050c1a  lea     r9, [rsp+4E0h+var_4A0]
0x180050c1f  lea     r8, [rsp+4E0h+Buffer]
0x180050c24  mov     [rsp+4E0h+var_4A0], ebx
0x180050c28  mov     edx, r14d
0x180050c2b  call    cs:__imp_BcdGetElementData
0x180050c31  mov     ebx, eax
0x180050c33  test    eax, eax
0x180050c35  jns     short loc_180050BD4
0x180050c37  lea     rdx, aFailedToGetEle_1; "Failed to get element application path."...
0x180050c3e  jmp     loc_180050915
0x180050c43  mov     ebx, 0C00000BBh
0x180050c48  mov     rcx, [rsp+4E0h+var_488]
0x180050c4d  test    rcx, rcx
0x180050c50  jz      short loc_180050C58
0x180050c52  call    cs:__imp_BcdCloseObject
0x180050c58  mov     rcx, [rsp+4E0h+var_490]
0x180050c5d  test    rcx, rcx
0x180050c60  jz      short loc_180050C68
0x180050c62  call    cs:__imp_BcdCloseObject
0x180050c68  mov     eax, ebx
0x180050c6a  mov     rcx, [rbp+3E0h+var_50]
0x180050c71  xor     rcx, rsp; StackCookie
0x180050c74  call    __security_check_cookie
0x180050c79  add     rsp, 4A8h
0x180050c80  pop     r15
0x180050c82  pop     r14
0x180050c84  pop     r13
0x180050c86  pop     r12
0x180050c88  pop     rdi
0x180050c89  pop     rsi
0x180050c8a  pop     rbx
0x180050c8b  pop     rbp
0x180050c8c  retn
```
