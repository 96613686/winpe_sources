# SIPolicyPmEnumerateTokens

- ea: `0x180020e20`
- end: `0x180020ec4`
- name: `SIPolicyPmEnumerateTokens`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001c714`

## callees

- `0x180020e20`
- `0x180021758`
- `0x180022404`
- `0x180022f2c`

## string_xrefs

- `0x180020e4e`: `Tokens\Active`

## pseudocode

```c
__int64 __fastcall SIPolicyPmEnumerateTokens(__int64 a1, __int64 a2, int a3, __int64 a4, int a5, __int64 a6)
{
  int v8; // ecx
  int BootPartitionPolicyFolder; // ebx
  int v10; // r8d
  UNICODE_STRING v12; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING v13; // [rsp+50h] [rbp-28h] BYREF
  __int64 v14; // [rsp+60h] [rbp-18h]

  *(_QWORD *)&v12.Length = 1835034;
  v13 = 0;
  v14 = 0;
  v12.Buffer = L"Tokens\\Active";
  BootPartitionPolicyFolder = SIPolicyPmGetBootPartitionPolicyFolder(&v13, &v12);
  if ( BootPartitionPolicyFolder >= 0 )
  {
    BootPartitionPolicyFolder = SIPolicyPmGetTokenFolderFiles(v8, (unsigned int)&v13, v10, a3, a4, a5, a6);
    if ( BootPartitionPolicyFolder == -1073741275 )
      BootPartitionPolicyFolder = 0;
  }
  SIPolicyPmFreeFileItems(&v13, 1);
  return (unsigned int)BootPartitionPolicyFolder;
}

```

## disassembly

```asm
0x180020e20  mov     r11, rsp
0x180020e23  mov     [r11+8], rbx
0x180020e27  mov     [r11+10h], rsi
0x180020e2b  push    rdi
0x180020e2c  sub     rsp, 70h
0x180020e30  xor     eax, eax
0x180020e32  mov     qword ptr [r11-38h], 1C001Ah
0x180020e3a  xorps   xmm0, xmm0
0x180020e3d  lea     rdx, [r11-38h]
0x180020e41  movups  [rsp+78h+var_28], xmm0
0x180020e46  mov     [r11-18h], rax
0x180020e4a  lea     rcx, [r11-28h]
0x180020e4e  lea     rax, aTokensActive; "Tokens\\Active"
0x180020e55  mov     rdi, r9
0x180020e58  mov     [r11-30h], rax
0x180020e5c  mov     rsi, r8
0x180020e5f  call    SIPolicyPmGetBootPartitionPolicyFolder
0x180020e64  mov     ebx, eax
0x180020e66  test    eax, eax
0x180020e68  js      short loc_180020EA1
0x180020e6a  mov     rax, [rsp+78h+arg_28]
0x180020e72  lea     rdx, [rsp+78h+var_28]
0x180020e77  mov     [rsp+78h+var_48], rax
0x180020e7c  mov     r9, rsi
0x180020e7f  mov     eax, [rsp+78h+arg_20]
0x180020e86  mov     [rsp+78h+var_50], eax
0x180020e8a  mov     [rsp+78h+var_58], rdi
0x180020e8f  call    SIPolicyPmGetTokenFolderFiles
0x180020e94  mov     ebx, eax
0x180020e96  xor     eax, eax
0x180020e98  cmp     ebx, 0C0000225h
0x180020e9e  cmovz   ebx, eax
0x180020ea1  mov     edx, 1
0x180020ea6  lea     rcx, [rsp+78h+var_28]
0x180020eab  call    SIPolicyPmFreeFileItems
0x180020eb0  lea     r11, [rsp+78h+var_8]
0x180020eb5  mov     eax, ebx
0x180020eb7  mov     rbx, [r11+10h]
0x180020ebb  mov     rsi, [r11+18h]
0x180020ebf  mov     rsp, r11
0x180020ec2  pop     rdi
0x180020ec3  retn
```
