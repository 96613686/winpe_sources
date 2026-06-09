# BfspSetObjectDeviceAndPath

- ea: `0x140008844`
- end: `0x140008c6c`
- name: `BfspSetObjectDeviceAndPath`
- size: `1064`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400052bc`
- `0x1400058e4`
- `0x140005ae8`
- `0x140005b98`
- `0x140005fc4`

## callees

- `0x140008844`
- `0x140008e68`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x140018890`
- `0x140018b54`
- `0x140026650`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140008bb1`
- `msvcrt!swprintf_s` at `0x140008bb1`

## string_xrefs

- `0x1400088c0`: `Failed to get handle to the template store. Status = [%x]`
- `0x140008c1a`: `Failed to get element application path. Status = [%x]`
- `0x140008beb`: `Failed to set element application path. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspSetObjectDeviceAndPath(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  int v6; // eax
  HANDLE v7; // rsi
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  int ElementDataWithFlags; // eax
  __int64 v12; // r8
  const wchar_t *v13; // rdi
  LPVOID v14; // r15
  unsigned int v15; // r12d
  unsigned int v16; // ebx
  int v17; // eax
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r14
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  int v28; // eax
  __int16 v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v32; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h]
  __int64 v37; // [rsp+70h] [rbp-90h]
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v39[528]; // [rsp+290h] [rbp+190h] BYREF

  v37 = a2;
  v36 = a1;
  v35 = 0;
  v32 = 0;
  Handle = 0;
  v34 = 0;
  v30[0] = 1;
  v6 = BcdOpenObject(a1, a3, &v34);
  v7 = v34;
  v8 = v6;
  if ( v6 < 0 )
  {
    BfspLogMessage(4, L"Failed to get handle to the template store. Status = [%x]", (unsigned int)v6);
    goto LABEL_45;
  }
  v9 = BcdOpenObject(a2, a4, &Handle);
  v8 = v9;
  if ( v9 < 0 )
  {
    BfspLogMessage(4, L"Failed to get handle to the system store. Status = [%x]", (unsigned int)v9);
    goto LABEL_43;
  }
  v31 = 8;
  ElementDataWithFlags = BcdGetElementDataWithFlags((__int64)v7, 0x45000001u, v10, (__int64)&v35, &v31);
  v8 = ElementDataWithFlags;
  if ( ElementDataWithFlags < 0 )
  {
    BfspLogMessage(4, L"Failed to get element device type. Status = [%x]", (unsigned int)ElementDataWithFlags);
    goto LABEL_43;
  }
  if ( v35 == 1 )
  {
    v13 = L"\\EFI\\Microsoft\\Boot\\";
    v14 = lpMem;
    v15 = dword_14003F920;
    if ( !byte_14003F8F8 )
      v13 = L"\\boot\\";
  }
  else
  {
    if ( v35 != 2 )
    {
      v8 = -1073741637;
      goto LABEL_43;
    }
    v15 = dword_14003F8E8;
    v13 = (const wchar_t *)qword_14003F930;
    LOBYTE(v30[0]) = 0;
    v14 = BfspGlobals;
  }
  v16 = 0;
  v31 = 2;
  LODWORD(v34) = 0;
  if ( qword_14003F938 )
    v13 = (const wchar_t *)qword_14003F938;
  BcdGetElementDataWithFlags((__int64)v7, 0x46000008u, v12, (__int64)&v32, &v31);
  if ( byte_14003F8F9 && (v35 != 2 || !byte_14003F8FA) )
  {
    v16 = 64;
    LODWORD(v34) = 64;
    BfspLogMessage(2, L"VHD device detection disabled");
  }
  if ( (_BYTE)v32 && byte_14003F8F8 )
  {
    v17 = BfspSetParentDevices(v36, a2, (_DWORD)v7, v16, 285212673, (__int64)v14, v15);
    v8 = v17;
    if ( v17 < 0 )
    {
      BfspLogMessage(4, L"Failed to set parent device. Status = [%x]", (unsigned int)v17);
      goto LABEL_43;
    }
  }
  else
  {
    v19 = BcdSetElementDataWithFlags((__int64)Handle, 285212673, v16, (__int64)v14, v15);
    v8 = v19;
    if ( v19 < 0 )
    {
      BfspLogMessage(4, L"Failed to set element application device. Status = [%x]", (unsigned int)v19);
      goto LABEL_43;
    }
  }
  v31 = 2;
  BcdGetElementDataWithFlags((__int64)v7, 0x46000004u, v18, (__int64)v30, &v31);
  v21 = -1;
  if ( !LOBYTE(v30[0]) )
  {
    if ( (_BYTE)v32 )
    {
      v23 = BfspSetParentDevices(v36, v37, (_DWORD)v7, (_DWORD)v34, 553648129, (__int64)v14, v15);
      v8 = v23;
      if ( v23 < 0 )
      {
        BfspLogMessage(4, L"Failed to set parent device. Status = [%x]", (unsigned int)v23);
        goto LABEL_43;
      }
    }
    else
    {
      v22 = BcdSetElementDataWithFlags((__int64)Handle, 553648129, (unsigned int)v34, (__int64)v14, v15);
      v8 = v22;
      if ( v22 < 0 )
      {
        BfspLogMessage(4, L"Failed to set element OS device. Status = [%x]", (unsigned int)v22);
        goto LABEL_43;
      }
    }
    v24 = -1;
    do
      ++v24;
    while ( v13[v24] );
    v25 = BcdSetElementDataWithFlags((__int64)Handle, 570425346, 0, (__int64)v13, 2 * (int)v24 + 2);
    v8 = v25;
    if ( v25 < 0 )
    {
      BfspLogMessage(4, L"Failed to set element system root. Status = [%x]", (unsigned int)v25);
      goto LABEL_43;
    }
  }
  v31 = 520;
  if ( (int)BcdGetElementDataWithFlags((__int64)v7, 0x42000002u, v20, (__int64)v39, &v31) >= 0 )
  {
    swprintf_s(Buffer, 0x104u, L"%s%s", v13, v39);
    goto LABEL_37;
  }
  v31 = 520;
  v28 = BcdGetElementDataWithFlags((__int64)v7, 0x12000002u, v26, (__int64)Buffer, &v31);
  v8 = v28;
  if ( v28 >= 0 )
  {
    do
LABEL_37:
      ++v21;
    while ( Buffer[v21] );
    v27 = BcdSetElementDataWithFlags((__int64)Handle, 301989890, 0, (__int64)Buffer, 2 * (int)v21 + 2);
    v8 = v27;
    if ( v27 < 0 )
      BfspLogMessage(4, L"Failed to set element application path. Status = [%x]", (unsigned int)v27);
    goto LABEL_43;
  }
  BfspLogMessage(4, L"Failed to get element application path. Status = [%x]", (unsigned int)v28);
LABEL_43:
  if ( Handle )
    BcdCloseObject(Handle);
LABEL_45:
  if ( v7 )
    BcdCloseObject(v7);
  return v8;
}

```

## disassembly

```asm
0x140008844  push    rbp
0x140008846  push    rbx
0x140008847  push    rsi
0x140008848  push    rdi
0x140008849  push    r12
0x14000884b  push    r14
0x14000884d  push    r15
0x14000884f  lea     rbp, [rsp-3B0h]
0x140008857  sub     rsp, 4B0h
0x14000885e  mov     rax, cs:__security_cookie
0x140008865  xor     rax, rsp
0x140008868  mov     [rbp+3E0h+var_40], rax
0x14000886f  xor     r15d, r15d
0x140008872  mov     [rsp+4E0h+var_470], rdx
0x140008877  mov     rdi, r9
0x14000887a  mov     [rsp+4E0h+var_4A0], r15w
0x140008880  mov     r9, r8
0x140008883  mov     [rsp+4E0h+var_478], rcx
0x140008888  mov     r14, rdx
0x14000888b  mov     [rsp+4E0h+var_480], r15
0x140008890  mov     rdx, r9
0x140008893  mov     [rsp+4E0h+var_498], r15w
0x140008899  lea     r8, [rsp+4E0h+var_488]
0x14000889e  mov     [rsp+4E0h+Handle], r15
0x1400088a3  mov     [rsp+4E0h+var_488], r15
0x1400088a8  mov     byte ptr [rsp+4E0h+var_4A0], 1
0x1400088ad  call    BcdOpenObject
0x1400088b2  mov     rsi, [rsp+4E0h+var_488]
0x1400088b7  mov     ebx, eax
0x1400088b9  test    eax, eax
0x1400088bb  jns     short loc_1400088D5
0x1400088bd  mov     r8d, eax
0x1400088c0  lea     rdx, aFailedToGetHan_1; "Failed to get handle to the template st"...
0x1400088c7  lea     ecx, [r15+4]
0x1400088cb  call    BfspLogMessage
0x1400088d0  jmp     loc_140008C3C
0x1400088d5  lea     r8, [rsp+4E0h+Handle]
0x1400088da  mov     rdx, rdi
0x1400088dd  mov     rcx, r14
0x1400088e0  call    BcdOpenObject
0x1400088e5  mov     ebx, eax
0x1400088e7  test    eax, eax
0x1400088e9  jns     short loc_140008904
0x1400088eb  lea     rdx, aFailedToGetHan_0; "Failed to get handle to the system stor"...
0x1400088f2  mov     r8d, eax
0x1400088f5  mov     ecx, 4
0x1400088fa  call    BfspLogMessage
0x1400088ff  jmp     loc_140008C2B
0x140008904  lea     rax, [rsp+4E0h+var_49C]
0x140008909  mov     [rsp+4E0h+var_49C], 8
0x140008911  lea     r9, [rsp+4E0h+var_480]
0x140008916  mov     [rsp+4E0h+var_4C0], rax
0x14000891b  mov     edx, 45000001h
0x140008920  mov     rcx, rsi
0x140008923  call    BcdGetElementDataWithFlags
0x140008928  mov     ebx, eax
0x14000892a  test    eax, eax
0x14000892c  jns     short loc_140008937
0x14000892e  lea     rdx, aFailedToGetEle; "Failed to get element device type. Stat"...
0x140008935  jmp     short loc_1400088F2
0x140008937  cmp     [rsp+4E0h+var_480], 1
0x14000893d  jnz     short loc_140008968
0x14000893f  cmp     cs:byte_14003F8F8, 0
0x140008946  lea     rdi, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\"
0x14000894d  mov     r15, cs:lpMem
0x140008954  lea     rax, aBoot_0; "\\boot\\"
0x14000895b  mov     r12d, cs:dword_14003F920
0x140008962  cmovz   rdi, rax
0x140008966  jmp     short loc_14000898E
0x140008968  cmp     [rsp+4E0h+var_480], 2
0x14000896e  jnz     loc_140008C26
0x140008974  mov     r12d, cs:dword_14003F8E8
0x14000897b  mov     rdi, cs:qword_14003F930
0x140008982  mov     byte ptr [rsp+4E0h+var_4A0], r15b
0x140008987  mov     r15, cs:BfspGlobals
0x14000898e  mov     rax, cs:qword_14003F938
0x140008995  lea     r9, [rsp+4E0h+var_498]
0x14000899a  xor     ebx, ebx
0x14000899c  mov     [rsp+4E0h+var_49C], 2
0x1400089a4  test    rax, rax
0x1400089a7  mov     dword ptr [rsp+4E0h+var_488], ebx
0x1400089ab  mov     edx, 46000008h
0x1400089b0  mov     rcx, rsi
0x1400089b3  cmovnz  rdi, rax
0x1400089b7  lea     rax, [rsp+4E0h+var_49C]
0x1400089bc  mov     [rsp+4E0h+var_4C0], rax
0x1400089c1  call    BcdGetElementDataWithFlags
0x1400089c6  cmp     cs:byte_14003F8F9, bl
0x1400089cc  jz      short loc_1400089F6
0x1400089ce  cmp     [rsp+4E0h+var_480], 2
0x1400089d4  jnz     short loc_1400089DE
0x1400089d6  cmp     cs:byte_14003F8FA, bl
0x1400089dc  jnz     short loc_1400089F6
0x1400089de  mov     ebx, 40h ; '@'
0x1400089e3  lea     rdx, aVhdDeviceDetec; "VHD device detection disabled"
0x1400089ea  mov     dword ptr [rsp+4E0h+var_488], ebx
0x1400089ee  lea     ecx, [rbx-3Eh]
0x1400089f1  call    BfspLogMessage
0x1400089f6  cmp     byte ptr [rsp+4E0h+var_498], 0
0x1400089fb  jz      short loc_140008A3A
0x1400089fd  cmp     cs:byte_14003F8F8, 0
0x140008a04  jz      short loc_140008A3A
0x140008a06  mov     rcx, [rsp+4E0h+var_478]
0x140008a0b  mov     r9d, ebx
0x140008a0e  mov     [rsp+4E0h+var_4B0], r12d
0x140008a13  mov     r8, rsi
0x140008a16  mov     [rsp+4E0h+var_4B8], r15
0x140008a1b  mov     rdx, r14
0x140008a1e  mov     dword ptr [rsp+4E0h+var_4C0], 11000001h
0x140008a26  call    BfspSetParentDevices
0x140008a2b  mov     ebx, eax
0x140008a2d  test    eax, eax
0x140008a2f  jns     short loc_140008A76
0x140008a31  lea     rdx, aFailedToSetPar; "Failed to set parent device. Status = ["...
0x140008a38  jmp     short loc_140008A61
0x140008a3a  mov     rcx, [rsp+4E0h+Handle]
0x140008a3f  mov     r9, r15
0x140008a42  mov     r8d, ebx
0x140008a45  mov     dword ptr [rsp+4E0h+var_4C0], r12d
0x140008a4a  mov     edx, 11000001h
0x140008a4f  call    BcdSetElementDataWithFlags
0x140008a54  mov     ebx, eax
0x140008a56  test    eax, eax
0x140008a58  jns     short loc_140008A76
0x140008a5a  lea     rdx, aFailedToSetEle_3; "Failed to set element application devic"...
0x140008a61  mov     r8d, eax
0x140008a64  mov     ecx, 4
0x140008a69  call    BfspLogMessage
0x140008a6e  xor     r15d, r15d
0x140008a71  jmp     loc_140008C2B
0x140008a76  lea     rax, [rsp+4E0h+var_49C]
0x140008a7b  mov     [rsp+4E0h+var_49C], 2
0x140008a83  lea     r9, [rsp+4E0h+var_4A0]
0x140008a88  mov     [rsp+4E0h+var_4C0], rax
0x140008a8d  mov     edx, 46000004h
0x140008a92  mov     rcx, rsi
0x140008a95  call    BcdGetElementDataWithFlags
0x140008a9a  or      r14, 0FFFFFFFFFFFFFFFFh
0x140008a9e  cmp     byte ptr [rsp+4E0h+var_4A0], 0
0x140008aa3  jnz     loc_140008B5E
0x140008aa9  cmp     byte ptr [rsp+4E0h+var_498], 0
0x140008aae  jnz     short loc_140008AE1
0x140008ab0  mov     r8d, dword ptr [rsp+4E0h+var_488]
0x140008ab5  mov     r9, r15
0x140008ab8  mov     rcx, [rsp+4E0h+Handle]
0x140008abd  mov     edx, 21000001h
0x140008ac2  mov     dword ptr [rsp+4E0h+var_4C0], r12d
0x140008ac7  call    BcdSetElementDataWithFlags
0x140008acc  xor     r15d, r15d
0x140008acf  mov     ebx, eax
0x140008ad1  test    eax, eax
0x140008ad3  jns     short loc_140008B1F
0x140008ad5  lea     rdx, aFailedToSetEle_4; "Failed to set element OS device. Status"...
0x140008adc  jmp     loc_1400088F2
0x140008ae1  mov     r9d, dword ptr [rsp+4E0h+var_488]
0x140008ae6  mov     r8, rsi
0x140008ae9  mov     rdx, [rsp+4E0h+var_470]
0x140008aee  mov     rcx, [rsp+4E0h+var_478]
0x140008af3  mov     [rsp+4E0h+var_4B0], r12d
0x140008af8  mov     [rsp+4E0h+var_4B8], r15
0x140008afd  mov     dword ptr [rsp+4E0h+var_4C0], 21000001h
0x140008b05  call    BfspSetParentDevices
0x140008b0a  xor     r15d, r15d
0x140008b0d  mov     ebx, eax
0x140008b0f  test    eax, eax
0x140008b11  jns     short loc_140008B1F
0x140008b13  lea     rdx, aFailedToSetPar; "Failed to set parent device. Status = ["...
0x140008b1a  jmp     loc_1400088F2
0x140008b1f  mov     rax, r14
0x140008b22  inc     rax
0x140008b25  cmp     [rdi+rax*2], r15w
0x140008b2a  jnz     short loc_140008B22
0x140008b2c  mov     rcx, [rsp+4E0h+Handle]
0x140008b31  lea     eax, ds:2[rax*2]
0x140008b38  mov     r9, rdi
0x140008b3b  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x140008b3f  xor     r8d, r8d
0x140008b42  mov     edx, 22000002h
0x140008b47  call    BcdSetElementDataWithFlags
0x140008b4c  mov     ebx, eax
0x140008b4e  test    eax, eax
0x140008b50  jns     short loc_140008B61
0x140008b52  lea     rdx, aFailedToSetEle_2; "Failed to set element system root. Stat"...
0x140008b59  jmp     loc_1400088F2
0x140008b5e  xor     r15d, r15d
0x140008b61  lea     rax, [rsp+4E0h+var_49C]
0x140008b66  mov     ebx, 208h
0x140008b6b  lea     r9, [rbp+3E0h+var_250]
0x140008b72  mov     [rsp+4E0h+var_49C], ebx
0x140008b76  mov     edx, 42000002h
0x140008b7b  mov     [rsp+4E0h+var_4C0], rax
0x140008b80  mov     rcx, rsi
0x140008b83  call    BcdGetElementDataWithFlags
0x140008b88  mov     r12d, 12000002h
0x140008b8e  test    eax, eax
0x140008b90  js      short loc_140008BF7
0x140008b92  lea     rax, [rbp+3E0h+var_250]
0x140008b99  mov     r9, rdi
0x140008b9c  lea     r8, aSS_0; "%s%s"
0x140008ba3  mov     [rsp+4E0h+var_4C0], rax
0x140008ba8  mov     edx, 104h; BufferCount
0x140008bad  lea     rcx, [rbp+3E0h+Buffer]; Buffer
0x140008bb1  call    cs:__imp_swprintf_s
0x140008bb7  lea     rax, [rbp+3E0h+Buffer]
0x140008bbb  inc     r14
0x140008bbe  cmp     [rax+r14*2], r15w
0x140008bc3  jnz     short loc_140008BBB
0x140008bc5  mov     rcx, [rsp+4E0h+Handle]
0x140008bca  lea     eax, ds:2[r14*2]
0x140008bd2  lea     r9, [rbp+3E0h+Buffer]
0x140008bd6  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x140008bda  xor     r8d, r8d
0x140008bdd  mov     edx, r12d
0x140008be0  call    BcdSetElementDataWithFlags
0x140008be5  mov     ebx, eax
0x140008be7  test    eax, eax
0x140008be9  jns     short loc_140008C2B
0x140008beb  lea     rdx, aFailedToSetEle_1; "Failed to set element application path."...
0x140008bf2  jmp     loc_1400088F2
0x140008bf7  lea     rax, [rsp+4E0h+var_49C]
0x140008bfc  mov     [rsp+4E0h+var_49C], ebx
0x140008c00  lea     r9, [rbp+3E0h+Buffer]
0x140008c04  mov     [rsp+4E0h+var_4C0], rax
0x140008c09  mov     edx, r12d
0x140008c0c  mov     rcx, rsi
0x140008c0f  call    BcdGetElementDataWithFlags
0x140008c14  mov     ebx, eax
0x140008c16  test    eax, eax
0x140008c18  jns     short loc_140008BB7
0x140008c1a  lea     rdx, aFailedToGetEle_1; "Failed to get element application path."...
0x140008c21  jmp     loc_1400088F2
0x140008c26  mov     ebx, 0C00000BBh
0x140008c2b  cmp     [rsp+4E0h+Handle], r15
0x140008c30  jz      short loc_140008C3C
0x140008c32  mov     rcx, [rsp+4E0h+Handle]; Handle
0x140008c37  call    BcdCloseObject
0x140008c3c  test    rsi, rsi
0x140008c3f  jz      short loc_140008C49
0x140008c41  mov     rcx, rsi; Handle
0x140008c44  call    BcdCloseObject
0x140008c49  mov     eax, ebx
0x140008c4b  mov     rcx, [rbp+3E0h+var_40]
0x140008c52  xor     rcx, rsp; StackCookie
0x140008c55  call    __security_check_cookie
0x140008c5a  add     rsp, 4B0h
0x140008c61  pop     r15
0x140008c63  pop     r14
0x140008c65  pop     r12
0x140008c67  pop     rdi
0x140008c68  pop     rsi
0x140008c69  pop     rbx
0x140008c6a  pop     rbp
0x140008c6b  retn
```
