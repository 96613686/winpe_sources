# BfspSetParentDevices

- ea: `0x180050e74`
- end: `0x18005107e`
- name: `BfspSetParentDevices`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180050894`

## callees

- `0x18004cdd4`
- `0x18004f888`
- `0x180050e74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051047`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180051047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051039`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051039`
- `bcd!BcdSetElementDataWithFlags` at `0x180050f4c`
- `bcd!BcdSetElementDataWithFlags` at `0x180051014`
- `bcd!BcdSetElementDataWithFlags` at `0x180050f4c`
- `bcd!BcdSetElementDataWithFlags` at `0x180051014`
- `bcd!BcdCloseObject` at `0x180050fa9`
- `bcd!BcdCloseObject` at `0x180050fbb`
- `bcd!BcdCloseObject` at `0x180051056`
- `bcd!BcdCloseObject` at `0x180051065`
- `bcd!BcdCloseObject` at `0x180050fa9`
- `bcd!BcdCloseObject` at `0x180050fbb`
- `bcd!BcdCloseObject` at `0x180051056`
- `bcd!BcdCloseObject` at `0x180051065`
- `bcd!BcdOpenObject` at `0x180050f04`
- `bcd!BcdOpenObject` at `0x180050f27`
- `bcd!BcdOpenObject` at `0x180050fd4`
- `bcd!BcdOpenObject` at `0x180050fef`
- `bcd!BcdOpenObject` at `0x180050f04`
- `bcd!BcdOpenObject` at `0x180050f27`
- `bcd!BcdOpenObject` at `0x180050fd4`
- `bcd!BcdOpenObject` at `0x180050fef`

## pseudocode

```c
__int64 __fastcall BfspSetParentDevices(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        int a7)
{
  int BcdElementData; // eax
  int v11; // ebx
  char *v12; // rdi
  const wchar_t *v13; // rdx
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  int v17; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-20h] BYREF
  __int64 v19; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-10h] BYREF

  v17 = 0;
  lpMem = 0;
  v20[0] = 0;
  v19 = 0;
  BcdElementData = BfspGetBcdElementData(a3, a5, &lpMem, &v17);
  v11 = BcdElementData;
  if ( BcdElementData < 0 )
    goto LABEL_2;
  v12 = (char *)lpMem;
  if ( *(_DWORD *)lpMem != 10 )
  {
LABEL_4:
    v11 = -1073741637;
    BfspLogMessage(4, L"Found unsupported device. Status = [%x]");
    goto LABEL_16;
  }
  v11 = BcdOpenObject(a1, (char *)lpMem + 4, v20);
  if ( v11 >= 0 )
  {
    v11 = BcdOpenObject(a2, v12 + 4, &v19);
    if ( v11 >= 0 )
    {
      v11 = BcdSetElementDataWithFlags(v19, 822083598, a4, a6, a7);
      if ( v11 < 0 )
      {
LABEL_14:
        v13 = L"Failed to set element parent device. Status = [%x]";
        goto LABEL_15;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      lpMem = 0;
      BcdElementData = BfspGetBcdElementData(v20[0], 822083599, &lpMem, &v17);
      v11 = BcdElementData;
      if ( BcdElementData < 0 )
      {
LABEL_2:
        BfspLogMessage(4, L"Failed to get element device. Status = [%x]", (unsigned int)BcdElementData);
        v12 = (char *)lpMem;
        goto LABEL_16;
      }
      v12 = (char *)lpMem;
      if ( *(_DWORD *)lpMem != 11 )
        goto LABEL_4;
      BcdCloseObject(v20[0]);
      v20[0] = 0;
      BcdCloseObject(v19);
      v19 = 0;
      v11 = BcdOpenObject(a1, v12 + 4, v20);
      if ( v11 >= 0 )
      {
        v11 = BcdOpenObject(a2, v12 + 4, &v19);
        if ( v11 >= 0 )
        {
          v11 = BcdSetElementDataWithFlags(v19, 822083602, a4, a6, a7);
          if ( v11 >= 0 )
            goto LABEL_16;
          goto LABEL_14;
        }
      }
    }
  }
  v13 = L"Failed to get handle to the additional options. Status = [%x]";
LABEL_15:
  BfspLogMessage(4, v13);
LABEL_16:
  if ( v12 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v12);
  }
  if ( v20[0] )
    BcdCloseObject(v20[0]);
  if ( v19 )
    BcdCloseObject(v19);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180050e74  push    rbp
0x180050e76  push    rbx
0x180050e77  push    rsi
0x180050e78  push    rdi
0x180050e79  push    r12
0x180050e7b  push    r13
0x180050e7d  push    r14
0x180050e7f  push    r15
0x180050e81  mov     rbp, rsp
0x180050e84  sub     rsp, 58h
0x180050e88  xor     edi, edi
0x180050e8a  mov     rax, r8
0x180050e8d  mov     r13d, r9d
0x180050e90  mov     [rbp+var_28], edi
0x180050e93  mov     r15, rdx
0x180050e96  mov     [rbp+lpMem], rdi
0x180050e9a  mov     edx, [rbp+arg_20]
0x180050e9d  lea     r9, [rbp+var_28]
0x180050ea1  mov     r12, rcx
0x180050ea4  mov     [rbp+var_10], rdi
0x180050ea8  mov     rcx, rax
0x180050eab  mov     [rbp+var_18], rdi
0x180050eaf  lea     r8, [rbp+lpMem]
0x180050eb3  call    BfspGetBcdElementData
0x180050eb8  mov     ebx, eax
0x180050eba  test    eax, eax
0x180050ebc  jns     short loc_180050EDB
0x180050ebe  mov     r8d, eax
0x180050ec1  lea     rdx, aFailedToGetEle_0; "Failed to get element device. Status = "...
0x180050ec8  mov     ecx, 4
0x180050ecd  call    BfspLogMessage
0x180050ed2  mov     rdi, [rbp+lpMem]
0x180050ed6  jmp     loc_180051034
0x180050edb  mov     rdi, [rbp+lpMem]
0x180050edf  cmp     dword ptr [rdi], 0Ah
0x180050ee2  jz      short loc_180050EF9
0x180050ee4  mov     r8d, 0C00000BBh
0x180050eea  lea     rdx, aFoundUnsupport; "Found unsupported device. Status = [%x]"
0x180050ef1  mov     ebx, r8d
0x180050ef4  jmp     loc_18005102A
0x180050ef9  lea     r8, [rbp+var_10]
0x180050efd  mov     rcx, r12
0x180050f00  lea     rdx, [rdi+4]
0x180050f04  call    cs:__imp_BcdOpenObject
0x180050f0a  mov     ebx, eax
0x180050f0c  test    eax, eax
0x180050f0e  jns     short loc_180050F1C
0x180050f10  lea     rdx, aFailedToGetHan; "Failed to get handle to the additional "...
0x180050f17  jmp     loc_180051027
0x180050f1c  lea     r8, [rbp+var_18]
0x180050f20  mov     rcx, r15
0x180050f23  lea     rdx, [rdi+4]
0x180050f27  call    cs:__imp_BcdOpenObject
0x180050f2d  mov     ebx, eax
0x180050f2f  test    eax, eax
0x180050f31  js      short loc_180050F10
0x180050f33  mov     r14d, [rbp+arg_30]
0x180050f37  mov     r8d, r13d
0x180050f3a  mov     r9, [rbp+arg_28]
0x180050f3e  mov     edx, 3100000Eh
0x180050f43  mov     rcx, [rbp+var_18]
0x180050f47  mov     [rsp+58h+var_38], r14d
0x180050f4c  call    cs:__imp_BcdSetElementDataWithFlags
0x180050f52  mov     ebx, eax
0x180050f54  test    eax, eax
0x180050f56  js      loc_180051020
0x180050f5c  call    cs:__imp_GetProcessHeap
0x180050f62  mov     r8, rdi; lpMem
0x180050f65  xor     edx, edx; dwFlags
0x180050f67  mov     rcx, rax; hHeap
0x180050f6a  call    cs:__imp_HeapFree
0x180050f70  mov     rcx, [rbp+var_10]
0x180050f74  lea     r9, [rbp+var_28]
0x180050f78  lea     r8, [rbp+lpMem]
0x180050f7c  mov     [rbp+lpMem], 0
0x180050f84  mov     edx, 3100000Fh
0x180050f89  call    BfspGetBcdElementData
0x180050f8e  mov     ebx, eax
0x180050f90  test    eax, eax
0x180050f92  js      loc_180050EBE
0x180050f98  mov     rdi, [rbp+lpMem]
0x180050f9c  cmp     dword ptr [rdi], 0Bh
0x180050f9f  jnz     loc_180050EE4
0x180050fa5  mov     rcx, [rbp+var_10]
0x180050fa9  call    cs:__imp_BcdCloseObject
0x180050faf  mov     rcx, [rbp+var_18]
0x180050fb3  mov     [rbp+var_10], 0
0x180050fbb  call    cs:__imp_BcdCloseObject
0x180050fc1  lea     r8, [rbp+var_10]
0x180050fc5  mov     [rbp+var_18], 0
0x180050fcd  lea     rdx, [rdi+4]
0x180050fd1  mov     rcx, r12
0x180050fd4  call    cs:__imp_BcdOpenObject
0x180050fda  mov     ebx, eax
0x180050fdc  test    eax, eax
0x180050fde  js      loc_180050F10
0x180050fe4  lea     r8, [rbp+var_18]
0x180050fe8  mov     rcx, r15
0x180050feb  lea     rdx, [rdi+4]
0x180050fef  call    cs:__imp_BcdOpenObject
0x180050ff5  mov     ebx, eax
0x180050ff7  test    eax, eax
0x180050ff9  js      loc_180050F10
0x180050fff  mov     r9, [rbp+arg_28]
0x180051003  mov     r8d, r13d
0x180051006  mov     rcx, [rbp+var_18]
0x18005100a  mov     edx, 31000012h
0x18005100f  mov     [rsp+58h+var_38], r14d
0x180051014  call    cs:__imp_BcdSetElementDataWithFlags
0x18005101a  mov     ebx, eax
0x18005101c  test    eax, eax
0x18005101e  jns     short loc_180051034
0x180051020  lea     rdx, aFailedToSetEle_6; "Failed to set element parent device. St"...
0x180051027  mov     r8d, eax
0x18005102a  mov     ecx, 4
0x18005102f  call    BfspLogMessage
0x180051034  test    rdi, rdi
0x180051037  jz      short loc_18005104D
0x180051039  call    cs:__imp_GetProcessHeap
0x18005103f  mov     r8, rdi; lpMem
0x180051042  xor     edx, edx; dwFlags
0x180051044  mov     rcx, rax; hHeap
0x180051047  call    cs:__imp_HeapFree
0x18005104d  mov     rcx, [rbp+var_10]
0x180051051  test    rcx, rcx
0x180051054  jz      short loc_18005105C
0x180051056  call    cs:__imp_BcdCloseObject
0x18005105c  mov     rcx, [rbp+var_18]
0x180051060  test    rcx, rcx
0x180051063  jz      short loc_18005106B
0x180051065  call    cs:__imp_BcdCloseObject
0x18005106b  mov     eax, ebx
0x18005106d  add     rsp, 58h
0x180051071  pop     r15
0x180051073  pop     r14
0x180051075  pop     r13
0x180051077  pop     r12
0x180051079  pop     rdi
0x18005107a  pop     rsi
0x18005107b  pop     rbx
0x18005107c  pop     rbp
0x18005107d  retn
```
