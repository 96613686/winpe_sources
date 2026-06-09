# BfspCreateResumeObject

- ea: `0x18004f244`
- end: `0x18004f44e`
- name: `BfspCreateResumeObject`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180050410`

## callees

- `0x1800078b0`
- `0x18004cdd4`
- `0x18004f244`
- `0x18004f854`
- `0x1800507fc`
- `0x180050894`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18004f368`
- `bcd!BcdCloseObject` at `0x18004f3b7`
- `bcd!BcdCloseObject` at `0x18004f429`
- `bcd!BcdCloseObject` at `0x18004f368`
- `bcd!BcdCloseObject` at `0x18004f3b7`
- `bcd!BcdCloseObject` at `0x18004f429`
- `bcd!BcdOpenObject` at `0x18004f2cc`
- `bcd!BcdOpenObject` at `0x18004f339`
- `bcd!BcdOpenObject` at `0x18004f2cc`
- `bcd!BcdOpenObject` at `0x18004f339`
- `bcd!BcdCopyObjectEx` at `0x18004f3ab`
- `bcd!BcdCopyObjectEx` at `0x18004f3ab`
- `bcd!BcdQueryObject` at `0x18004f3e3`
- `bcd!BcdQueryObject` at `0x18004f3e3`
- `bcd!BcdGetElementData` at `0x18004f35c`
- `bcd!BcdGetElementData` at `0x18004f35c`

## string_xrefs

- `0x18004f3cb`: `Failed to copy resume object data. Status = [%x]`
- `0x18004f2f6`: `Failed to open handle to resume object. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateResumeObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  GUID v8; // xmm0
  int Object; // eax
  int v10; // ebx
  const wchar_t *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r15
  unsigned int BcdCopyFlags; // r14d
  char v15; // cl
  int ElementData; // ebx
  __int64 v17; // r8
  int v19; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+38h] [rbp-40h] BYREF
  __int64 v21; // [rsp+40h] [rbp-38h] BYREF
  __int64 v22; // [rsp+48h] [rbp-30h] BYREF
  GUID v23; // [rsp+50h] [rbp-28h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = 0;
  v23 = 0;
  BfspLogMessage(2, L"Creating Resume object.");
  v22 = 0;
  if ( byte_1800A4538 )
    v8 = GUID_WINDOWS_RESUME_TARGET_TEMPLATE_EFI;
  else
    v8 = GUID_WINDOWS_RESUME_TARGET_TEMPLATE_PCAT;
  v23 = v8;
  Object = BcdOpenObject(a1, &v23, &v21);
  v10 = Object;
  if ( Object < 0 )
  {
    if ( Object == -1073741772 )
    {
      BfspLogMessage(
        2,
        L"Resume application not found. Note, if you are servicing Windows PE or Windows RE boot files, you can ignore this message.");
      v10 = 0;
      goto LABEL_24;
    }
    v11 = L"Failed to open handle to resume object. Status = [%x]";
    goto LABEL_8;
  }
  v12 = (unsigned int)dword_1800A453C;
  v13 = 0;
  dword_1800A453C |= 0x400u;
  LODWORD(v12) = dword_1800A453C;
  BcdCopyFlags = BfspGetBcdCopyFlags(v12);
  if ( (v15 & 0x40) != 0 )
  {
    ElementData = BcdOpenObject(a2, a3, &v20);
    if ( ElementData >= 0 )
    {
      v19 = 16;
      ElementData = BcdGetElementData(v20, 587202563, a4, &v19);
      BcdCloseObject(v20);
      v20 = 0;
      v13 = a4;
      if ( ElementData < 0 )
        v13 = 0;
    }
    v17 = BcdCopyFlags | 1;
    if ( ElementData >= 0 )
      v17 = BcdCopyFlags;
  }
  else
  {
    v17 = BcdCopyFlags | 1;
  }
  v10 = BcdCopyObjectEx(a1, v21, v17, a2, v13, &v22);
  BcdCloseObject(v21);
  v21 = 0;
  if ( v10 < 0 )
  {
    BfspLogMessage(4, L"Failed to copy resume object data. Status = [%x]", (unsigned int)v10);
    goto LABEL_24;
  }
  Object = BcdQueryObject(v22, 0, 0, a4);
  v10 = Object;
  if ( Object < 0 )
  {
    v11 = L"Failed to query object data. Status = [%x]";
LABEL_8:
    BfspLogMessage(4, v11, (unsigned int)Object);
    goto LABEL_24;
  }
  v10 = BfspSetObjectDeviceAndPath(a1, a2, &v23, a4);
  if ( v10 >= 0 )
    v10 = BfspSetLocale(a2, a4);
LABEL_24:
  if ( v22 )
    BcdCloseObject(v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004f244  push    rbp
0x18004f246  push    rbx
0x18004f247  push    rsi
0x18004f248  push    rdi
0x18004f249  push    r12
0x18004f24b  push    r13
0x18004f24d  push    r14
0x18004f24f  push    r15
0x18004f251  mov     rbp, rsp
0x18004f254  sub     rsp, 78h
0x18004f258  mov     rax, cs:__security_cookie
0x18004f25f  xor     rax, rsp
0x18004f262  mov     [rbp+var_18], rax
0x18004f266  xor     r14d, r14d
0x18004f269  mov     rsi, rdx
0x18004f26c  mov     r12, rcx
0x18004f26f  mov     [rbp+var_48], r14d
0x18004f273  xorps   xmm0, xmm0
0x18004f276  mov     [rbp+var_40], r14
0x18004f27a  lea     rdx, aCreatingResume; "Creating Resume object."
0x18004f281  mov     [rbp+var_30], r14
0x18004f285  lea     r15d, [r14+2]
0x18004f289  mov     [rbp+var_38], r14
0x18004f28d  mov     ecx, r15d
0x18004f290  mov     rdi, r9
0x18004f293  mov     r13, r8
0x18004f296  movups  [rbp+var_28], xmm0
0x18004f29a  call    BfspLogMessage
0x18004f29f  cmp     cs:byte_1800A4538, r14b
0x18004f2a6  mov     [rbp+var_30], r14
0x18004f2aa  jz      short loc_18004F2B5
0x18004f2ac  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_RESUME_TARGET_TEMPLATE_EFI.Data1
0x18004f2b3  jmp     short loc_18004F2BC
0x18004f2b5  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_RESUME_TARGET_TEMPLATE_PCAT.Data1
0x18004f2bc  lea     r8, [rbp+var_38]
0x18004f2c0  mov     rcx, r12
0x18004f2c3  lea     rdx, [rbp+var_28]
0x18004f2c7  movdqu  [rbp+var_28], xmm0
0x18004f2cc  call    cs:__imp_BcdOpenObject
0x18004f2d2  mov     ebx, eax
0x18004f2d4  test    eax, eax
0x18004f2d6  jns     short loc_18004F30F
0x18004f2d8  cmp     eax, 0C0000034h
0x18004f2dd  jnz     short loc_18004F2F6
0x18004f2df  lea     rdx, aResumeApplicat; "Resume application not found. Note, if "...
0x18004f2e6  mov     ecx, r15d
0x18004f2e9  call    BfspLogMessage
0x18004f2ee  mov     ebx, r14d
0x18004f2f1  jmp     loc_18004F420
0x18004f2f6  lea     rdx, aFailedToOpenHa; "Failed to open handle to resume object."...
0x18004f2fd  mov     r8d, eax
0x18004f300  mov     ecx, 4
0x18004f305  call    BfspLogMessage
0x18004f30a  jmp     loc_18004F420
0x18004f30f  mov     ecx, cs:dword_1800A453C
0x18004f315  mov     r15, r14
0x18004f318  bts     ecx, 0Ah
0x18004f31c  mov     cs:dword_1800A453C, ecx
0x18004f322  call    BfspGetBcdCopyFlags
0x18004f327  mov     r14d, eax
0x18004f32a  test    cl, 40h
0x18004f32d  jz      short loc_18004F38C
0x18004f32f  lea     r8, [rbp+var_40]
0x18004f333  mov     rdx, r13
0x18004f336  mov     rcx, rsi
0x18004f339  call    cs:__imp_BcdOpenObject
0x18004f33f  mov     ebx, eax
0x18004f341  test    eax, eax
0x18004f343  js      short loc_18004F37D
0x18004f345  mov     rcx, [rbp+var_40]
0x18004f349  lea     r9, [rbp+var_48]
0x18004f34d  mov     r8, rdi
0x18004f350  mov     [rbp+var_48], 10h
0x18004f357  mov     edx, 23000003h
0x18004f35c  call    cs:__imp_BcdGetElementData
0x18004f362  mov     rcx, [rbp+var_40]
0x18004f366  mov     ebx, eax
0x18004f368  call    cs:__imp_BcdCloseObject
0x18004f36e  xor     eax, eax
0x18004f370  mov     [rbp+var_40], r15
0x18004f374  test    ebx, ebx
0x18004f376  mov     r15, rdi
0x18004f379  cmovs   r15, rax
0x18004f37d  mov     r8d, r14d
0x18004f380  or      r8d, 1
0x18004f384  test    ebx, ebx
0x18004f386  cmovns  r8d, r14d
0x18004f38a  jmp     short loc_18004F393
0x18004f38c  mov     r8d, r14d
0x18004f38f  or      r8d, 1
0x18004f393  mov     rdx, [rbp+var_38]
0x18004f397  lea     rax, [rbp+var_30]
0x18004f39b  mov     [rsp+78h+var_50], rax
0x18004f3a0  mov     r9, rsi
0x18004f3a3  mov     rcx, r12
0x18004f3a6  mov     [rsp+78h+var_58], r15
0x18004f3ab  call    cs:__imp_BcdCopyObjectEx
0x18004f3b1  mov     rcx, [rbp+var_38]
0x18004f3b5  mov     ebx, eax
0x18004f3b7  call    cs:__imp_BcdCloseObject
0x18004f3bd  xor     r14d, r14d
0x18004f3c0  mov     [rbp+var_38], r14
0x18004f3c4  test    ebx, ebx
0x18004f3c6  jns     short loc_18004F3D7
0x18004f3c8  mov     r8d, ebx
0x18004f3cb  lea     rdx, aFailedToCopyRe; "Failed to copy resume object data. Stat"...
0x18004f3d2  jmp     loc_18004F300
0x18004f3d7  mov     rcx, [rbp+var_30]
0x18004f3db  mov     r9, rdi
0x18004f3de  xor     r8d, r8d
0x18004f3e1  xor     edx, edx
0x18004f3e3  call    cs:__imp_BcdQueryObject
0x18004f3e9  mov     ebx, eax
0x18004f3eb  test    eax, eax
0x18004f3ed  jns     short loc_18004F3FB
0x18004f3ef  lea     rdx, aFailedToQueryO; "Failed to query object data. Status = ["...
0x18004f3f6  jmp     loc_18004F2FD
0x18004f3fb  mov     r9, rdi
0x18004f3fe  lea     r8, [rbp+var_28]
0x18004f402  mov     rdx, rsi
0x18004f405  mov     rcx, r12
0x18004f408  call    BfspSetObjectDeviceAndPath
0x18004f40d  mov     ebx, eax
0x18004f40f  test    eax, eax
0x18004f411  js      short loc_18004F420
0x18004f413  mov     rdx, rdi
0x18004f416  mov     rcx, rsi
0x18004f419  call    BfspSetLocale
0x18004f41e  mov     ebx, eax
0x18004f420  mov     rcx, [rbp+var_30]
0x18004f424  test    rcx, rcx
0x18004f427  jz      short loc_18004F42F
0x18004f429  call    cs:__imp_BcdCloseObject
0x18004f42f  mov     eax, ebx
0x18004f431  mov     rcx, [rbp+var_18]
0x18004f435  xor     rcx, rsp; StackCookie
0x18004f438  call    __security_check_cookie
0x18004f43d  add     rsp, 78h
0x18004f441  pop     r15
0x18004f443  pop     r14
0x18004f445  pop     r13
0x18004f447  pop     r12
0x18004f449  pop     rdi
0x18004f44a  pop     rsi
0x18004f44b  pop     rbx
0x18004f44c  pop     rbp
0x18004f44d  retn
```
