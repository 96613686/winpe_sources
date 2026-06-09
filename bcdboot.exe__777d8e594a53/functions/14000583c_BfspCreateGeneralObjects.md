# BfspCreateGeneralObjects

- ea: `0x14000583c`
- end: `0x1400058db`
- name: `BfspCreateGeneralObjects`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140005e18`
- `0x140007cdc`

## callees

- `0x14000583c`
- `0x1400069e0`
- `0x14000e628`
- `0x140014ec8`

## string_xrefs

- `0x1400058b2`: `Failed to copy objects of type %08x data. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateGeneralObjects(__int64 a1, __int64 a2)
{
  unsigned int BcdCopyFlags; // r14d
  __int64 v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  unsigned int v9; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v10; // [rsp+54h] [rbp+1Ch]

  BfspLogMessage(2, L"Creating General objects.");
  v9 = 1;
  BcdCopyFlags = BfspGetBcdCopyFlags((unsigned int)dword_14003F8FC);
  v5 = 0;
  while ( 1 )
  {
    v10 = *((_DWORD *)GeneralObjectList + v5);
    v6 = BcdCopyObjects(a1, &v9, BcdCopyFlags, a2);
    v7 = v6;
    if ( v6 < 0 )
      break;
    v5 = (unsigned int)(v5 + 1);
    if ( (unsigned int)v5 >= 2 )
      return v7;
  }
  BfspLogMessage(4, L"Failed to copy objects of type %08x data. Status = [%x]", v10, (unsigned int)v6);
  return v7;
}

```

## disassembly

```asm
0x14000583c  mov     [rsp+arg_0], rbx
0x140005841  mov     [rsp+arg_8], rbp
0x140005846  push    rsi
0x140005847  push    rdi
0x140005848  push    r14
0x14000584a  sub     rsp, 20h
0x14000584e  mov     rsi, rdx
0x140005851  mov     rbp, rcx
0x140005854  lea     rdx, aCreatingGenera; "Creating General objects."
0x14000585b  mov     ecx, 2
0x140005860  call    BfspLogMessage
0x140005865  mov     ecx, cs:dword_14003F8FC
0x14000586b  mov     [rsp+38h+arg_10], 1
0x140005873  call    BfspGetBcdCopyFlags
0x140005878  mov     r14d, eax
0x14000587b  xor     ebx, ebx
0x14000587d  lea     rax, GeneralObjectList
0x140005884  mov     r9, rsi
0x140005887  mov     ecx, [rax+rbx*4]
0x14000588a  lea     rdx, [rsp+38h+arg_10]
0x14000588f  mov     [rsp+38h+arg_14], ecx
0x140005893  mov     r8d, r14d
0x140005896  mov     rcx, rbp
0x140005899  call    BcdCopyObjects
0x14000589e  mov     edi, eax
0x1400058a0  test    eax, eax
0x1400058a2  js      short loc_1400058AD
0x1400058a4  inc     ebx
0x1400058a6  cmp     ebx, 2
0x1400058a9  jb      short loc_14000587D
0x1400058ab  jmp     short loc_1400058C6
0x1400058ad  mov     r8d, [rsp+38h+arg_14]
0x1400058b2  lea     rdx, aFailedToCopyOb; "Failed to copy objects of type %08x dat"...
0x1400058b9  mov     r9d, edi
0x1400058bc  mov     ecx, 4
0x1400058c1  call    BfspLogMessage
0x1400058c6  mov     rbx, [rsp+38h+arg_0]
0x1400058cb  mov     eax, edi
0x1400058cd  mov     rbp, [rsp+38h+arg_8]
0x1400058d2  add     rsp, 20h
0x1400058d6  pop     r14
0x1400058d8  pop     rdi
0x1400058d9  pop     rsi
0x1400058da  retn
```
