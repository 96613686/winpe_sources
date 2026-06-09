# CfpGetSyncRootInfoByHandle

- ea: `0x18000f6fc`
- end: `0x18000f7bb`
- name: `CfpGetSyncRootInfoByHandle`
- size: `191`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ac0`
- `0x180006060`
- `0x1800073b0`
- `0x1800079c0`
- `0x18000d7b0`
- `0x18000f520`
- `0x18000f7c4`
- `0x180011e18`

## callees

- `0x1800022ee`
- `0x18000f6fc`
- `0x18001bb5c`

## pseudocode

```c
__int64 __fastcall CfpGetSyncRootInfoByHandle(unsigned __int64 hFile, int a2, void *a3, DWORD a4, DWORD *a5)
{
  int v9; // ebx
  __int64 result; // rax
  int v11; // [rsp+40h] [rbp-C8h] BYREF
  int v12[49]; // [rsp+44h] [rbp-C4h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+118h] [rbp+10h] BYREF

  memset_0(v12, 0, 0x94u);
  NumberOfBytesTransferred = 0;
  v11 = -1879048166;
  if ( a2 )
  {
    v9 = a2 - 1;
    if ( v9 )
    {
      if ( v9 != 1 )
        return 2147942487LL;
      v12[0] = -1073741818;
    }
    else
    {
      v12[0] = -1073741817;
    }
  }
  else
  {
    v12[0] = -1073741819;
  }
  result = IssueHsmControl(hFile, &v11, 0x98u, a3, a4, &NumberOfBytesTransferred, 0);
  if ( a5 )
    *a5 = NumberOfBytesTransferred;
  return result;
}

```

## disassembly

```asm
0x18000f6fc  push    rbx
0x18000f6fe  push    rbp
0x18000f6ff  push    rsi
0x18000f700  push    rdi
0x18000f701  sub     rsp, 0E8h
0x18000f708  mov     rsi, r8
0x18000f70b  mov     ebx, edx
0x18000f70d  mov     rbp, rcx
0x18000f710  xor     edx, edx; Val
0x18000f712  mov     r8d, 94h; Size
0x18000f718  lea     rcx, [rsp+108h+var_C4]; void *
0x18000f71d  mov     edi, r9d
0x18000f720  call    memset_0
0x18000f725  mov     [rsp+108h+NumberOfBytesTransferred], 0
0x18000f730  mov     [rsp+108h+var_C8], 9000001Ah
0x18000f738  test    ebx, ebx
0x18000f73a  jz      short loc_18000F761
0x18000f73c  sub     ebx, 1
0x18000f73f  jz      short loc_18000F757
0x18000f741  cmp     ebx, 1
0x18000f744  jz      short loc_18000F74D
0x18000f746  mov     eax, 80070057h
0x18000f74b  jmp     short loc_18000F7AF
0x18000f74d  mov     [rsp+108h+var_C4], 0C0000006h
0x18000f755  jmp     short loc_18000F769
0x18000f757  mov     [rsp+108h+var_C4], 0C0000007h
0x18000f75f  jmp     short loc_18000F769
0x18000f761  mov     [rsp+108h+var_C4], 0C0000005h
0x18000f769  lea     rax, [rsp+108h+NumberOfBytesTransferred]
0x18000f771  mov     [rsp+108h+var_D8], 0; __int64
0x18000f77a  mov     [rsp+108h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000f77f  lea     rdx, [rsp+108h+var_C8]
0x18000f784  mov     r9, rsi
0x18000f787  mov     [rsp+108h+var_E8], edi; DWORD
0x18000f78b  mov     r8d, 98h
0x18000f791  mov     rcx, rbp; hFile
0x18000f794  call    IssueHsmControl
0x18000f799  mov     rdx, [rsp+108h+arg_20]
0x18000f7a1  test    rdx, rdx
0x18000f7a4  jz      short loc_18000F7AF
0x18000f7a6  mov     ecx, [rsp+108h+NumberOfBytesTransferred]
0x18000f7ad  mov     [rdx], ecx
0x18000f7af  add     rsp, 0E8h
0x18000f7b6  pop     rdi
0x18000f7b7  pop     rsi
0x18000f7b8  pop     rbp
0x18000f7b9  pop     rbx
0x18000f7ba  retn
```
