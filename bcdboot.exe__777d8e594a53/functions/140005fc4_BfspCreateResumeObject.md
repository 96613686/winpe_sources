# BfspCreateResumeObject

- ea: `0x140005fc4`
- end: `0x140006196`
- name: `BfspCreateResumeObject`
- size: `466`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x140007cdc`

## callees

- `0x140005fc4`
- `0x1400069e0`
- `0x1400087a8`
- `0x140008844`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x1400140c4`
- `0x14001474c`
- `0x140018890`

## string_xrefs

- `0x14000605c`: `Failed to open handle to resume object. Status = [%x]`
- `0x140006126`: `Failed to copy resume object data. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateResumeObject(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  GUID v8; // xmm0
  int Object; // eax
  int v10; // ebx
  const wchar_t *v11; // rdx
  __int64 v12; // rcx
  __int128 *v13; // r12
  unsigned int BcdCopyFlags; // r14d
  char v15; // cl
  int ElementDataWithFlags; // ebx
  __int64 v17; // r8
  unsigned int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // r8
  int v22; // [rsp+30h] [rbp-38h] BYREF
  HANDLE v23; // [rsp+38h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-28h] BYREF
  HANDLE v25; // [rsp+48h] [rbp-20h] BYREF
  GUID v26; // [rsp+50h] [rbp-18h] BYREF

  Handle = 0;
  v25 = 0;
  BfspLogMessage(2, L"Creating Resume object.");
  v23 = 0;
  if ( byte_14003F8F8 )
    v8 = GUID_WINDOWS_RESUME_TARGET_TEMPLATE_EFI;
  else
    v8 = GUID_WINDOWS_RESUME_TARGET_TEMPLATE_PCAT;
  v26 = v8;
  Object = BcdOpenObject(a1, &v26, &v25);
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
  v12 = (unsigned int)dword_14003F8FC;
  v13 = 0;
  dword_14003F8FC |= 0x400u;
  LODWORD(v12) = dword_14003F8FC;
  BcdCopyFlags = BfspGetBcdCopyFlags(v12);
  if ( (v15 & 0x40) != 0 )
  {
    ElementDataWithFlags = BcdOpenObject(a2, a3, &Handle);
    if ( ElementDataWithFlags >= 0 )
    {
      v22 = 16;
      ElementDataWithFlags = BcdGetElementDataWithFlags((__int64)Handle, 0x23000003u, v17, a4, &v22);
      BcdCloseObject(Handle);
      v13 = (__int128 *)a4;
      if ( ElementDataWithFlags < 0 )
        v13 = 0;
    }
    v18 = BcdCopyFlags | 1;
    if ( ElementDataWithFlags >= 0 )
      v18 = BcdCopyFlags;
  }
  else
  {
    v18 = BcdCopyFlags | 1;
  }
  v10 = BcdCopyObjectEx(a1, (__int64)v25, v18, a2, v13, &v23);
  BcdCloseObject(v25);
  if ( v10 < 0 )
  {
    BfspLogMessage(4, L"Failed to copy resume object data. Status = [%x]", (unsigned int)v10);
    goto LABEL_24;
  }
  Object = BcdQueryObject((__int64)v23, v19, v20, a4);
  v10 = Object;
  if ( Object < 0 )
  {
    v11 = L"Failed to query object data. Status = [%x]";
LABEL_8:
    BfspLogMessage(4, v11, (unsigned int)Object);
    goto LABEL_24;
  }
  v10 = BfspSetObjectDeviceAndPath(a1, a2, &v26, a4);
  if ( v10 >= 0 )
    v10 = BfspSetLocale(a2, a4);
LABEL_24:
  if ( v23 )
    BcdCloseObject(v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005fc4  push    rbp
0x140005fc6  push    rbx
0x140005fc7  push    rsi
0x140005fc8  push    rdi
0x140005fc9  push    r12
0x140005fcb  push    r13
0x140005fcd  push    r14
0x140005fcf  push    r15
0x140005fd1  mov     rbp, rsp
0x140005fd4  sub     rsp, 68h
0x140005fd8  xor     r14d, r14d
0x140005fdb  mov     rsi, rdx
0x140005fde  mov     r15, rcx
0x140005fe1  mov     [rbp+Handle], r14
0x140005fe5  lea     rdx, aCreatingResume; "Creating Resume object."
0x140005fec  mov     [rbp+var_30], r14
0x140005ff0  mov     rdi, r9
0x140005ff3  mov     [rbp+var_20], r14
0x140005ff7  lea     r12d, [r14+2]
0x140005ffb  mov     r13, r8
0x140005ffe  mov     ecx, r12d
0x140006001  call    BfspLogMessage
0x140006006  cmp     cs:byte_14003F8F8, r14b
0x14000600d  mov     [rbp+var_30], r14
0x140006011  jz      short loc_14000601C
0x140006013  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_RESUME_TARGET_TEMPLATE_EFI.Data1
0x14000601a  jmp     short loc_140006023
0x14000601c  movups  xmm0, xmmword ptr cs:GUID_WINDOWS_RESUME_TARGET_TEMPLATE_PCAT.Data1
0x140006023  lea     r8, [rbp+var_20]
0x140006027  mov     rcx, r15
0x14000602a  lea     rdx, [rbp+var_18]
0x14000602e  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x140006033  call    BcdOpenObject
0x140006038  mov     ebx, eax
0x14000603a  test    eax, eax
0x14000603c  jns     short loc_140006075
0x14000603e  cmp     eax, 0C0000034h
0x140006043  jnz     short loc_14000605C
0x140006045  lea     rdx, aResumeApplicat; "Resume application not found. Note, if "...
0x14000604c  mov     ecx, r12d
0x14000604f  call    BfspLogMessage
0x140006054  mov     ebx, r14d
0x140006057  jmp     loc_140006175
0x14000605c  lea     rdx, aFailedToOpenHa; "Failed to open handle to resume object."...
0x140006063  mov     r8d, eax
0x140006066  mov     ecx, 4
0x14000606b  call    BfspLogMessage
0x140006070  jmp     loc_140006175
0x140006075  mov     ecx, cs:dword_14003F8FC
0x14000607b  mov     r12, r14
0x14000607e  bts     ecx, 0Ah
0x140006082  mov     cs:dword_14003F8FC, ecx
0x140006088  call    BfspGetBcdCopyFlags
0x14000608d  mov     r14d, eax
0x140006090  test    cl, 40h
0x140006093  jz      short loc_1400060F0
0x140006095  lea     r8, [rbp+Handle]
0x140006099  mov     rdx, r13
0x14000609c  mov     rcx, rsi
0x14000609f  call    BcdOpenObject
0x1400060a4  mov     ebx, eax
0x1400060a6  test    eax, eax
0x1400060a8  js      short loc_1400060E1
0x1400060aa  mov     rcx, [rbp+Handle]
0x1400060ae  lea     rax, [rbp+var_38]
0x1400060b2  mov     r9, rdi
0x1400060b5  mov     [rsp+68h+var_48], rax
0x1400060ba  mov     edx, 23000003h
0x1400060bf  mov     [rbp+var_38], 10h
0x1400060c6  call    BcdGetElementDataWithFlags
0x1400060cb  mov     rcx, [rbp+Handle]; Handle
0x1400060cf  mov     ebx, eax
0x1400060d1  call    BcdCloseObject
0x1400060d6  xor     eax, eax
0x1400060d8  mov     r12, rdi
0x1400060db  test    ebx, ebx
0x1400060dd  cmovs   r12, rax
0x1400060e1  mov     r8d, r14d
0x1400060e4  or      r8d, 1
0x1400060e8  test    ebx, ebx
0x1400060ea  cmovns  r8d, r14d
0x1400060ee  jmp     short loc_1400060F7
0x1400060f0  mov     r8d, r14d
0x1400060f3  or      r8d, 1
0x1400060f7  mov     rdx, [rbp+var_20]
0x1400060fb  lea     rax, [rbp+var_30]
0x1400060ff  mov     [rsp+68h+var_40], rax
0x140006104  mov     r9, rsi
0x140006107  mov     rcx, r15
0x14000610a  mov     [rsp+68h+var_48], r12
0x14000610f  call    BcdCopyObjectEx
0x140006114  mov     rcx, [rbp+var_20]; Handle
0x140006118  mov     ebx, eax
0x14000611a  call    BcdCloseObject
0x14000611f  test    ebx, ebx
0x140006121  jns     short loc_140006132
0x140006123  mov     r8d, ebx
0x140006126  lea     rdx, aFailedToCopyRe; "Failed to copy resume object data. Stat"...
0x14000612d  jmp     loc_140006066
0x140006132  mov     rcx, [rbp+var_30]
0x140006136  mov     r9, rdi
0x140006139  call    BcdQueryObject
0x14000613e  mov     ebx, eax
0x140006140  test    eax, eax
0x140006142  jns     short loc_140006150
0x140006144  lea     rdx, aFailedToQueryO; "Failed to query object data. Status = ["...
0x14000614b  jmp     loc_140006063
0x140006150  mov     r9, rdi
0x140006153  lea     r8, [rbp+var_18]
0x140006157  mov     rdx, rsi
0x14000615a  mov     rcx, r15
0x14000615d  call    BfspSetObjectDeviceAndPath
0x140006162  mov     ebx, eax
0x140006164  test    eax, eax
0x140006166  js      short loc_140006175
0x140006168  mov     rdx, rdi
0x14000616b  mov     rcx, rsi
0x14000616e  call    BfspSetLocale
0x140006173  mov     ebx, eax
0x140006175  mov     rcx, [rbp+var_30]; Handle
0x140006179  test    rcx, rcx
0x14000617c  jz      short loc_140006183
0x14000617e  call    BcdCloseObject
0x140006183  mov     eax, ebx
0x140006185  add     rsp, 68h
0x140006189  pop     r15
0x14000618b  pop     r14
0x14000618d  pop     r13
0x14000618f  pop     r12
0x140006191  pop     rdi
0x140006192  pop     rsi
0x140006193  pop     rbx
0x140006194  pop     rbp
0x140006195  retn
```
