# BfspCleanupAdditionalOptions

- ea: `0x140004828`
- end: `0x140004a58`
- name: `BfspCleanupAdditionalOptions`
- size: `560`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140003d30`
- `0x140004f9c`

## callees

- `0x140004828`
- `0x1400064c0`
- `0x140006a14`
- `0x1400078f4`
- `0x14000e628`
- `0x140013b48`
- `0x140013b9c`
- `0x140013ee8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400048eb`
- `KERNEL32!HeapFree` at `0x140004967`
- `KERNEL32!HeapFree` at `0x140004a34`
- `KERNEL32!HeapFree` at `0x1400048eb`
- `KERNEL32!HeapFree` at `0x140004967`
- `KERNEL32!HeapFree` at `0x140004a34`
- `KERNEL32!GetProcessHeap` at `0x1400048dd`
- `KERNEL32!GetProcessHeap` at `0x140004959`
- `KERNEL32!GetProcessHeap` at `0x140004a26`
- `KERNEL32!GetProcessHeap` at `0x1400048dd`
- `KERNEL32!GetProcessHeap` at `0x140004959`
- `KERNEL32!GetProcessHeap` at `0x140004a26`

## string_xrefs

- `0x140004a0c`: `Failed to open object. Status = [%x]`
- `0x1400049ea`: `Failed to delete orphaned ramdisk. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCleanupAdditionalOptions(__int64 a1)
{
  HANDLE v1; // rdi
  __int64 v2; // rsi
  int v3; // eax
  char *v4; // r15
  int BcdElementData; // ebx
  __int64 v6; // r14
  int v7; // eax
  void *v8; // rbx
  char v9; // r12
  __int64 v10; // rsi
  HANDLE ProcessHeap; // rax
  int v12; // eax
  void *v13; // rsi
  HANDLE v14; // rax
  int IsReferenced; // eax
  int v16; // eax
  HANDLE v17; // rax
  HANDLE Handle; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h] BYREF
  char *v21; // [rsp+40h] [rbp-10h]
  char v23; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+50h] BYREF
  int v25; // [rsp+A8h] [rbp+58h] BYREF
  int v26; // [rsp+ACh] [rbp+5Ch]

  v1 = 0;
  v23 = 0;
  v2 = a1;
  Handle = 0;
  lpMem = 0;
  v24 = 0;
  BfspLogMessage(2, L"Cleaning up orphaned ramdisk options.");
  v25 = 1;
  v26 = 805306368;
  v3 = BfspEnumerateObjects(v2, &v25, &v24, &lpMem);
  v4 = (char *)lpMem;
  BcdElementData = v3;
  if ( v3 >= 0 )
  {
    v6 = 0;
    if ( v24 )
    {
      while ( 1 )
      {
        v21 = &v4[24 * v6];
        v7 = BcdOpenObject(v2, v21, &Handle);
        BcdElementData = v7;
        if ( v7 < 0 )
          break;
        v1 = Handle;
        v8 = 0;
        v9 = 0;
        lpMem = 0;
        v10 = 0;
        v25 = 0;
        while ( 1 )
        {
          if ( v8 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v8);
            lpMem = 0;
          }
          BcdElementData = BfspGetBcdElementData(
                             v1,
                             *((unsigned int *)ElementListIsAdditionalOptions + v10),
                             &lpMem,
                             &v25);
          if ( BcdElementData >= 0 )
            break;
          v12 = 0;
          if ( BcdElementData != -1073741275 )
            v12 = BcdElementData;
          BcdElementData = v12;
          if ( v12 < 0 )
          {
            BfspLogMessage(4, L"Failed to get element data. Status = [%x]", (unsigned int)v12);
            goto LABEL_15;
          }
          v10 = (unsigned int)(v10 + 1);
          if ( (unsigned int)v10 >= 7 )
            goto LABEL_15;
          v8 = lpMem;
        }
        v9 = 1;
LABEL_15:
        v13 = lpMem;
        if ( lpMem )
        {
          v14 = GetProcessHeap();
          HeapFree(v14, 0, v13);
        }
        if ( BcdElementData < 0 )
          goto LABEL_30;
        v2 = a1;
        if ( v9 )
        {
          IsReferenced = BfspObjectIsReferenced(
                           a1,
                           (_DWORD)v21,
                           3,
                           (unsigned int)&ReferenceElementListAdditionalOptions,
                           2,
                           (__int64)&v23);
          BcdElementData = IsReferenced;
          if ( IsReferenced < 0 )
          {
            BfspLogMessage(4, L"Failed to get reference count to object. Status = [%x]", (unsigned int)IsReferenced);
            goto LABEL_30;
          }
          if ( !v23 )
          {
            v16 = BcdDeleteObject((__int64)v1);
            v1 = 0;
            BcdElementData = v16;
            Handle = 0;
            if ( v16 < 0 )
            {
              BfspLogMessage(4, L"Failed to delete orphaned ramdisk. Status = [%x]", (unsigned int)v16);
              goto LABEL_30;
            }
          }
        }
        if ( v1 )
        {
          BcdCloseObject(v1);
          v1 = 0;
          Handle = 0;
        }
        v6 = (unsigned int)(v6 + 1);
        if ( (unsigned int)v6 >= v24 )
          goto LABEL_30;
      }
      BfspLogMessage(4, L"Failed to open object. Status = [%x]", (unsigned int)v7);
      v1 = Handle;
    }
  }
LABEL_30:
  if ( v4 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v4);
  }
  if ( v1 )
    BcdCloseObject(v1);
  return (unsigned int)BcdElementData;
}

```

## disassembly

```asm
0x140004828  mov     [rsp-38h+arg_0], rcx
0x14000482d  push    rbp
0x14000482e  push    rbx
0x14000482f  push    rsi
0x140004830  push    rdi
0x140004831  push    r12
0x140004833  push    r14
0x140004835  push    r15
0x140004837  mov     rbp, rsp
0x14000483a  sub     rsp, 50h
0x14000483e  xor     edi, edi
0x140004840  mov     [rbp+arg_8], 0
0x140004844  mov     rsi, rcx
0x140004847  mov     [rbp+Handle], rdi
0x14000484b  lea     rdx, aCleaningUpOrph; "Cleaning up orphaned ramdisk options."
0x140004852  mov     [rbp+lpMem], rdi
0x140004856  mov     [rbp+arg_10], edi
0x140004859  lea     ecx, [rdi+2]
0x14000485c  call    BfspLogMessage
0x140004861  lea     r9, [rbp+lpMem]
0x140004865  mov     [rbp+arg_18], 1
0x14000486c  lea     r8, [rbp+arg_10]
0x140004870  mov     [rbp+arg_1C], 30000000h
0x140004877  lea     rdx, [rbp+arg_18]
0x14000487b  mov     rcx, rsi
0x14000487e  call    BfspEnumerateObjects
0x140004883  mov     r15, [rbp+lpMem]
0x140004887  mov     ebx, eax
0x140004889  test    eax, eax
0x14000488b  js      loc_140004A21
0x140004891  xor     r14d, r14d
0x140004894  cmp     [rbp+arg_10], edi
0x140004897  jbe     loc_140004A21
0x14000489d  lea     rcx, [r14+r14*2]
0x1400048a1  lea     rax, [r15+rcx*8]
0x1400048a5  mov     rcx, rsi
0x1400048a8  mov     rdx, rax
0x1400048ab  mov     [rbp+var_10], rax
0x1400048af  lea     r8, [rbp+Handle]
0x1400048b3  call    BcdOpenObject
0x1400048b8  mov     ebx, eax
0x1400048ba  test    eax, eax
0x1400048bc  js      loc_140004A09
0x1400048c2  mov     rdi, [rbp+Handle]
0x1400048c6  xor     ebx, ebx
0x1400048c8  xor     r12b, r12b
0x1400048cb  mov     [rbp+lpMem], rbx
0x1400048cf  xor     esi, esi
0x1400048d1  mov     [rbp+arg_18], 0
0x1400048d8  test    rbx, rbx
0x1400048db  jz      short loc_1400048F9
0x1400048dd  call    cs:__imp_GetProcessHeap
0x1400048e3  mov     r8, rbx; lpMem
0x1400048e6  xor     edx, edx; dwFlags
0x1400048e8  mov     rcx, rax; hHeap
0x1400048eb  call    cs:__imp_HeapFree
0x1400048f1  mov     [rbp+lpMem], 0
0x1400048f9  lea     rax, ElementListIsAdditionalOptions
0x140004900  mov     rcx, rdi
0x140004903  mov     edx, [rax+rsi*4]
0x140004906  lea     r9, [rbp+arg_18]
0x14000490a  lea     r8, [rbp+lpMem]
0x14000490e  call    BfspGetBcdElementData
0x140004913  mov     ebx, eax
0x140004915  test    eax, eax
0x140004917  jns     short loc_14000494D
0x140004919  xor     eax, eax
0x14000491b  cmp     ebx, 0C0000225h
0x140004921  cmovnz  eax, ebx
0x140004924  mov     ebx, eax
0x140004926  test    eax, eax
0x140004928  js      short loc_140004937
0x14000492a  inc     esi
0x14000492c  cmp     esi, 7
0x14000492f  jnb     short loc_140004950
0x140004931  mov     rbx, [rbp+lpMem]
0x140004935  jmp     short loc_1400048D8
0x140004937  mov     r8d, eax
0x14000493a  lea     rdx, aFailedToGetEle_2; "Failed to get element data. Status = [%"...
0x140004941  mov     ecx, 4
0x140004946  call    BfspLogMessage
0x14000494b  jmp     short loc_140004950
0x14000494d  mov     r12b, 1
0x140004950  mov     rsi, [rbp+lpMem]
0x140004954  test    rsi, rsi
0x140004957  jz      short loc_14000496D
0x140004959  call    cs:__imp_GetProcessHeap
0x14000495f  mov     r8, rsi; lpMem
0x140004962  xor     edx, edx; dwFlags
0x140004964  mov     rcx, rax; hHeap
0x140004967  call    cs:__imp_HeapFree
0x14000496d  test    ebx, ebx
0x14000496f  js      loc_140004A21
0x140004975  mov     rsi, [rbp+arg_0]
0x140004979  test    r12b, r12b
0x14000497c  jz      short loc_1400049C8
0x14000497e  mov     rdx, [rbp+var_10]
0x140004982  lea     rax, [rbp+arg_8]
0x140004986  mov     [rsp+50h+var_28], rax
0x14000498b  lea     r9, ReferenceElementListAdditionalOptions
0x140004992  mov     r8d, 3
0x140004998  mov     [rsp+50h+var_30], 2
0x1400049a0  mov     rcx, rsi
0x1400049a3  call    BfspObjectIsReferenced
0x1400049a8  mov     ebx, eax
0x1400049aa  test    eax, eax
0x1400049ac  js      short loc_1400049F3
0x1400049ae  cmp     [rbp+arg_8], 0
0x1400049b2  jnz     short loc_1400049C8
0x1400049b4  mov     rcx, rdi
0x1400049b7  call    BcdDeleteObject
0x1400049bc  xor     edi, edi
0x1400049be  mov     ebx, eax
0x1400049c0  mov     [rbp+Handle], rdi
0x1400049c4  test    eax, eax
0x1400049c6  js      short loc_1400049EA
0x1400049c8  test    rdi, rdi
0x1400049cb  jz      short loc_1400049DB
0x1400049cd  mov     rcx, rdi; Handle
0x1400049d0  call    BcdCloseObject
0x1400049d5  xor     edi, edi
0x1400049d7  mov     [rbp+Handle], rdi
0x1400049db  inc     r14d
0x1400049de  cmp     r14d, [rbp+arg_10]
0x1400049e2  jb      loc_14000489D
0x1400049e8  jmp     short loc_140004A21
0x1400049ea  lea     rdx, aFailedToDelete_1; "Failed to delete orphaned ramdisk. Stat"...
0x1400049f1  jmp     short loc_1400049FA
0x1400049f3  lea     rdx, aFailedToGetRef; "Failed to get reference count to object"...
0x1400049fa  mov     r8d, eax
0x1400049fd  mov     ecx, 4
0x140004a02  call    BfspLogMessage
0x140004a07  jmp     short loc_140004A21
0x140004a09  mov     r8d, eax
0x140004a0c  lea     rdx, aFailedToOpenOb_1; "Failed to open object. Status = [%x]"
0x140004a13  mov     ecx, 4
0x140004a18  call    BfspLogMessage
0x140004a1d  mov     rdi, [rbp+Handle]
0x140004a21  test    r15, r15
0x140004a24  jz      short loc_140004A3A
0x140004a26  call    cs:__imp_GetProcessHeap
0x140004a2c  mov     r8, r15; lpMem
0x140004a2f  xor     edx, edx; dwFlags
0x140004a31  mov     rcx, rax; hHeap
0x140004a34  call    cs:__imp_HeapFree
0x140004a3a  test    rdi, rdi
0x140004a3d  jz      short loc_140004A47
0x140004a3f  mov     rcx, rdi; Handle
0x140004a42  call    BcdCloseObject
0x140004a47  mov     eax, ebx
0x140004a49  add     rsp, 50h
0x140004a4d  pop     r15
0x140004a4f  pop     r14
0x140004a51  pop     r12
0x140004a53  pop     rdi
0x140004a54  pop     rsi
0x140004a55  pop     rbx
0x140004a56  pop     rbp
0x140004a57  retn
```
