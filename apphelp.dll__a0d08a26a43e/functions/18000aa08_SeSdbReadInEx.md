# SeSdbReadInEx

- ea: `0x18000aa08`
- end: `0x18000ae66`
- name: `SeSdbReadInEx`
- size: `1118`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180005740`
- `0x18000607c`

## callees

- `0x180008390`
- `0x180009a14`
- `0x180009f10`
- `0x18000a804`
- `0x18000aa08`
- `0x18000ae70`
- `0x18000f114`
- `0x18002d2d8`
- `0x180059169`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x18000add5`
- `ntdll!RtlReAllocateHeap` at `0x18000ade9`
- `ntdll!RtlReAllocateHeap` at `0x18000add5`
- `ntdll!RtlReAllocateHeap` at `0x18000ade9`
- `ntdll!RtlFreeHeap` at `0x18000abf0`
- `ntdll!RtlFreeHeap` at `0x18000abf0`
- `ntdll!RtlAllocateHeap` at `0x18000accb`
- `ntdll!RtlAllocateHeap` at `0x18000ad67`
- `ntdll!RtlAllocateHeap` at `0x18000accb`
- `ntdll!RtlAllocateHeap` at `0x18000ad67`

## string_xrefs

- `0x18000aaef`: `SeSdbReadInEx`
- `0x18000adb4`: `SeSdbReadInEx`
- `0x18000ada7`: `Failed to read module name from tagref`

## pseudocode

```c
__int64 __fastcall SeSdbReadInEx(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  int v4; // edi
  unsigned int v5; // r14d
  PVOID ProcessHeap; // rbx
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // r15
  unsigned int *v10; // rsi
  unsigned int FirstGlobalIn; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // r12d
  int v15; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  __int64 v18; // r8
  unsigned __int64 i; // rdi
  unsigned int *v21; // rax
  unsigned int v22; // ebx
  unsigned int FirstTagRef; // eax
  int v24; // eax
  unsigned __int64 v25; // rdi
  unsigned __int128 v26; // rax
  unsigned int *v27; // rax
  unsigned int *v28; // rbx
  unsigned __int128 v29; // rax
  unsigned int *v30; // rax
  unsigned int *Heap; // rbx
  HANDLE HeapHandle; // [rsp+40h] [rbp-158h]
  _BYTE v36[256]; // [rsp+50h] [rbp-148h] BYREF

  v4 = a4;
  v5 = a3;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  HeapHandle = ProcessHeap;
  if ( !ProcessHeap )
  {
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    HeapHandle = ProcessHeap;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a4 )
    FirstGlobalIn = SdbFindFirstGlobalInExTagRef(a2);
  else
    FirstGlobalIn = SdbFindFirstTagRef(a2, a3, 28675);
  while ( 1 )
  {
    v12 = 3221225621LL;
    v13 = 8;
    v14 = FirstGlobalIn;
    if ( !FirstGlobalIn )
      break;
    if ( !v8 )
    {
      if ( v9 )
        goto LABEL_26;
      if ( is_mul_ok(0, 8u) )
      {
        v29 = 0x10 * (unsigned __int128)8uLL;
        if ( is_mul_ok(0x10u, 8u) )
        {
          if ( v10 )
          {
            Heap = (unsigned int *)RtlReAllocateHeap(ProcessHeap, DWORD2(v29), v10, 0x80u);
          }
          else
          {
            v30 = (unsigned int *)RtlAllocateHeap(ProcessHeap, DWORD2(v29), 0x80u);
            Heap = v30;
            if ( v30 )
              memset_0(v30, 0, 0x80u);
          }
          v5 = a3;
          if ( Heap )
          {
            v9 = 16;
            v10 = Heap;
            v4 = a4;
            v12 = 3221225621LL;
            v13 = 8;
LABEL_26:
            if ( is_mul_ok(8u, 0) )
            {
              v8 = 1;
              *v10 = v14;
              v15 = 0;
            }
            else
            {
              v15 = -1073741675;
            }
LABEL_31:
            v16 = v15;
            if ( v15 < 0 )
              goto LABEL_10;
            goto LABEL_32;
          }
LABEL_56:
          v15 = -1073741801;
LABEL_30:
          v4 = a4;
          goto LABEL_31;
        }
LABEL_28:
        v5 = a3;
      }
LABEL_29:
      v15 = -1073741675;
      goto LABEL_30;
    }
    if ( v8 >= v9 )
    {
      if ( v8 + 1 <= v9 )
      {
        v15 = -1073741811;
        goto LABEL_31;
      }
      if ( v8 + 16 < v8 + 1 || !is_mul_ok(v9, 8u) )
        goto LABEL_29;
      v25 = (v8 + 16) & 0xFFFFFFFFFFFFFFF0uLL;
      v26 = v25 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v25, 8u) )
        goto LABEL_28;
      if ( v10 )
      {
        v28 = (unsigned int *)RtlReAllocateHeap(ProcessHeap, DWORD2(v26), v10, 8 * v25);
      }
      else
      {
        v27 = (unsigned int *)RtlAllocateHeap(ProcessHeap, DWORD2(v26), 8 * v25);
        v28 = v27;
        if ( v27 )
          memset_0(v27, 0, 8 * v25);
      }
      v5 = a3;
      if ( !v28 )
        goto LABEL_56;
      v9 = (v8 + 16) & 0xFFFFFFFFFFFFFFF0uLL;
      v10 = v28;
      v4 = a4;
    }
    if ( !is_mul_ok(8u, 0) || !is_mul_ok(8u, 1u) || v10 + 2 < v10 || !is_mul_ok(v8, 8u) )
    {
      v15 = -1073741675;
      v16 = -1073741675;
LABEL_10:
      v17 = "Failed to insert tag in tagref array: %08lx";
      v18 = 119;
LABEL_11:
      AslLogCallPrintf(1, "SeSdbReadInEx", v18, v17, v15);
      goto LABEL_12;
    }
    memmove_0(v10 + 2, v10, 8 * v8++);
    *v10 = v14;
LABEL_32:
    if ( v4 )
      FirstGlobalIn = SdbFindNextGlobalInExTagRef(a2, v14, v12, v13);
    else
      FirstGlobalIn = SdbFindNextTagRef(a2, v5, v14);
    ProcessHeap = HeapHandle;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v8 )
    {
      v16 = 0;
      goto LABEL_12;
    }
    if ( !is_mul_ok(8u, i) || (v21 = &v10[2 * i], v21 < v10) )
      v21 = 0;
    v22 = *v21;
    FirstTagRef = SdbFindFirstTagRef(a2, *v21, 24579);
    if ( !(unsigned int)SdbReadStringTagRef(a2, FirstTagRef, v36, 128) )
      break;
    v24 = SdbFindFirstTagRef(a2, v22, 4097);
    v15 = SeInExAppend(a1, v36, v24 == 0);
    v16 = v15;
    if ( v15 < 0 )
    {
      v17 = "Failed to append module name to inex list: %08lx";
      v18 = 172;
      goto LABEL_11;
    }
  }
  v16 = -1073741595;
  AslLogCallPrintf(1, "SeSdbReadInEx", 155, "Failed to read module name from tagref");
LABEL_12:
  if ( v10 )
    RtlFreeHeap(HeapHandle, 0, v10);
  return v16;
}

```

## disassembly

```asm
0x18000aa08  mov     [rsp+arg_18], rbx
0x18000aa0d  push    rbp
0x18000aa0e  push    rsi
0x18000aa0f  push    rdi
0x18000aa10  push    r12
0x18000aa12  push    r13
0x18000aa14  push    r14
0x18000aa16  push    r15
0x18000aa18  sub     rsp, 160h
0x18000aa1f  mov     rax, cs:__security_cookie
0x18000aa26  xor     rax, rsp
0x18000aa29  mov     [rsp+198h+var_48], rax
0x18000aa31  mov     rax, gs:60h
0x18000aa3a  mov     edi, r9d
0x18000aa3d  mov     [rsp+198h+var_168], r9d
0x18000aa42  mov     r14d, r8d
0x18000aa45  mov     [rsp+198h+var_164], r8d
0x18000aa4a  mov     r13, rdx
0x18000aa4d  mov     [rsp+198h+var_150], rcx
0x18000aa52  mov     rbx, [rax+30h]
0x18000aa56  mov     [rsp+198h+HeapHandle], rbx
0x18000aa5b  test    rbx, rbx
0x18000aa5e  jnz     short loc_18000AA72
0x18000aa60  mov     rax, gs:60h
0x18000aa69  mov     rbx, [rax+30h]
0x18000aa6d  mov     [rsp+198h+HeapHandle], rbx
0x18000aa72  xor     ebp, ebp
0x18000aa74  xor     r15d, r15d
0x18000aa77  xor     esi, esi
0x18000aa79  mov     rcx, r13
0x18000aa7c  test    r9d, r9d
0x18000aa7f  jnz     loc_18000ABDC
0x18000aa85  mov     r8d, 7003h
0x18000aa8b  mov     edx, r14d
0x18000aa8e  call    SdbFindFirstTagRef
0x18000aa93  mov     r8d, 0C0000095h
0x18000aa99  mov     r9d, 8
0x18000aa9f  mov     r12d, eax
0x18000aaa2  test    eax, eax
0x18000aaa4  jz      loc_18000AB3A
0x18000aaaa  test    rbp, rbp
0x18000aaad  jz      loc_18000ABFB
0x18000aab3  cmp     rbp, r15
0x18000aab6  jnb     loc_18000AC77
0x18000aabc  xor     eax, eax
0x18000aabe  mov     [rsp+198h+var_160], 0
0x18000aac7  mul     r9
0x18000aaca  test    rdx, rdx
0x18000aacd  jnz     short loc_18000AADC
0x18000aacf  lea     rbx, [rsi+rax]
0x18000aad3  cmp     rbx, rsi
0x18000aad6  jnb     loc_18000AE08
0x18000aadc  mov     eax, r8d
0x18000aadf  mov     ebx, r8d
0x18000aae2  lea     r9, aFailedToInsert_0; "Failed to insert tag in tagref array: %"...
0x18000aae9  mov     r8d, 77h ; 'w'
0x18000aaef  lea     rdx, aSesdbreadinex; "SeSdbReadInEx"
0x18000aaf6  mov     [rsp+198h+var_178], eax
0x18000aafa  mov     ecx, 1
0x18000aaff  call    AslLogCallPrintf
0x18000ab04  test    rsi, rsi
0x18000ab07  jnz     loc_18000ABE6
0x18000ab0d  mov     eax, ebx
0x18000ab0f  mov     rcx, [rsp+198h+var_48]
0x18000ab17  xor     rcx, rsp; StackCookie
0x18000ab1a  call    __security_check_cookie
0x18000ab1f  mov     rbx, [rsp+198h+arg_18]
0x18000ab27  add     rsp, 160h
0x18000ab2e  pop     r15
0x18000ab30  pop     r14
0x18000ab32  pop     r13
0x18000ab34  pop     r12
0x18000ab36  pop     rdi
0x18000ab37  pop     rsi
0x18000ab38  pop     rbp
0x18000ab39  retn
0x18000ab3a  mov     r14, [rsp+198h+var_150]
0x18000ab3f  xor     edi, edi
0x18000ab41  cmp     rdi, rbp
0x18000ab44  jnb     loc_18000ABD5
0x18000ab4a  mov     rax, rdi
0x18000ab4d  mov     [rsp+198h+var_160], 0
0x18000ab56  mul     r9
0x18000ab59  test    rdx, rdx
0x18000ab5c  jnz     short loc_18000AB66
0x18000ab5e  add     rax, rsi
0x18000ab61  cmp     rax, rsi
0x18000ab64  jnb     short loc_18000AB68
0x18000ab66  xor     eax, eax
0x18000ab68  mov     ebx, [rax]
0x18000ab6a  mov     r8d, 6003h
0x18000ab70  mov     edx, ebx
0x18000ab72  mov     rcx, r13
0x18000ab75  call    SdbFindFirstTagRef
0x18000ab7a  mov     r9d, 80h
0x18000ab80  lea     r8, [rsp+198h+var_148]
0x18000ab85  mov     edx, eax
0x18000ab87  mov     rcx, r13
0x18000ab8a  call    SdbReadStringTagRef
0x18000ab8f  test    eax, eax
0x18000ab91  jz      loc_18000ADA7
0x18000ab97  mov     r8d, 1001h
0x18000ab9d  mov     edx, ebx
0x18000ab9f  mov     rcx, r13
0x18000aba2  call    SdbFindFirstTagRef
0x18000aba7  xor     r8d, r8d
0x18000abaa  lea     rdx, [rsp+198h+var_148]
0x18000abaf  test    eax, eax
0x18000abb1  mov     rcx, r14
0x18000abb4  setz    r8b
0x18000abb8  call    SeInExAppend
0x18000abbd  mov     ebx, eax
0x18000abbf  test    eax, eax
0x18000abc1  js      loc_18000AC65
0x18000abc7  inc     rdi
0x18000abca  mov     r9d, 8
0x18000abd0  jmp     loc_18000AB41
0x18000abd5  xor     ebx, ebx
0x18000abd7  jmp     loc_18000AB04
0x18000abdc  call    SdbFindFirstGlobalInExTagRef
0x18000abe1  jmp     loc_18000AA93
0x18000abe6  mov     rcx, [rsp+198h+HeapHandle]; HeapHandle
0x18000abeb  mov     r8, rsi; P
0x18000abee  xor     edx, edx; Flags
0x18000abf0  call    cs:__imp_RtlFreeHeap
0x18000abf6  jmp     loc_18000AB0D
0x18000abfb  cmp     rbp, r15
0x18000abfe  jnb     loc_18000AD0F
0x18000ac04  mov     rax, rbp
0x18000ac07  mov     [rsp+198h+var_160], 0
0x18000ac10  mul     r9
0x18000ac13  test    rdx, rdx
0x18000ac16  jnz     short loc_18000AC24
0x18000ac18  add     rax, rsi
0x18000ac1b  cmp     rax, rsi
0x18000ac1e  jnb     loc_18000AE59
0x18000ac24  mov     eax, r8d
0x18000ac27  jmp     short loc_18000AC35
0x18000ac29  mov     r14d, [rsp+198h+var_164]
0x18000ac2e  mov     eax, r8d
0x18000ac31  mov     edi, [rsp+198h+var_168]
0x18000ac35  mov     ebx, eax
0x18000ac37  test    eax, eax
0x18000ac39  js      loc_18000AAE2
0x18000ac3f  mov     rcx, r13
0x18000ac42  test    edi, edi
0x18000ac44  jz      short loc_18000AC58
0x18000ac46  mov     edx, r12d
0x18000ac49  call    SdbFindNextGlobalInExTagRef
0x18000ac4e  mov     rbx, [rsp+198h+HeapHandle]
0x18000ac53  jmp     loc_18000AA93
0x18000ac58  mov     r8d, r12d
0x18000ac5b  mov     edx, r14d
0x18000ac5e  call    SdbFindNextTagRef
0x18000ac63  jmp     short loc_18000AC4E
0x18000ac65  lea     r9, aFailedToAppend_1; "Failed to append module name to inex li"...
0x18000ac6c  mov     r8d, 0ACh
0x18000ac72  jmp     loc_18000AAEF
0x18000ac77  lea     rax, [rbp+1]
0x18000ac7b  cmp     rax, r15
0x18000ac7e  jbe     loc_18000ADFE
0x18000ac84  lea     rdi, [rax+0Fh]
0x18000ac88  cmp     rdi, rax
0x18000ac8b  jb      short loc_18000AC2E
0x18000ac8d  mov     rax, r9
0x18000ac90  mov     [rsp+198h+var_160], 0
0x18000ac99  mul     r15
0x18000ac9c  test    rdx, rdx
0x18000ac9f  jnz     short loc_18000AC2E
0x18000aca1  and     rdi, 0FFFFFFFFFFFFFFF0h
0x18000aca5  mov     [rsp+198h+var_160], rdx
0x18000acaa  mov     rax, r9
0x18000acad  mul     rdi
0x18000acb0  mov     r14, rax
0x18000acb3  test    rdx, rdx
0x18000acb6  jnz     loc_18000AC29
0x18000acbc  mov     rcx, rbx; Heap
0x18000acbf  test    rsi, rsi
0x18000acc2  jnz     loc_18000ADCF
0x18000acc8  mov     r8, rax; Size
0x18000accb  call    cs:__imp_RtlAllocateHeap
0x18000acd1  mov     rbx, rax
0x18000acd4  test    rax, rax
0x18000acd7  jz      short loc_18000ACE6
0x18000acd9  mov     r8, r14; Size
0x18000acdc  xor     edx, edx; Val
0x18000acde  mov     rcx, rax; void *
0x18000ace1  call    memset_0
0x18000ace6  mov     r14d, [rsp+198h+var_164]
0x18000aceb  test    rbx, rbx
0x18000acee  jz      loc_18000ADF4
0x18000acf4  mov     r15, rdi
0x18000acf7  mov     rsi, rbx
0x18000acfa  mov     edi, [rsp+198h+var_168]
0x18000acfe  mov     r8d, 0C0000095h
0x18000ad04  mov     r9d, 8
0x18000ad0a  jmp     loc_18000AABC
0x18000ad0f  lea     rax, [rbp+1]
0x18000ad13  cmp     rax, r15
0x18000ad16  jbe     loc_18000ADFE
0x18000ad1c  lea     rdi, [rax+0Fh]
0x18000ad20  cmp     rdi, rax
0x18000ad23  jb      loc_18000AC2E
0x18000ad29  mov     rax, r9
0x18000ad2c  mov     [rsp+198h+var_160], 0
0x18000ad35  mul     r15
0x18000ad38  test    rdx, rdx
0x18000ad3b  jnz     loc_18000AC2E
0x18000ad41  and     rdi, 0FFFFFFFFFFFFFFF0h
0x18000ad45  mov     [rsp+198h+var_160], rdx
0x18000ad4a  mov     rax, r9
0x18000ad4d  mul     rdi
0x18000ad50  mov     r14, rax
0x18000ad53  test    rdx, rdx
0x18000ad56  jnz     loc_18000AC29
0x18000ad5c  mov     rcx, rbx; Heap
0x18000ad5f  test    rsi, rsi
0x18000ad62  jnz     short loc_18000ADE3
0x18000ad64  mov     r8, rax; Size
0x18000ad67  call    cs:__imp_RtlAllocateHeap
0x18000ad6d  mov     rbx, rax
0x18000ad70  test    rax, rax
0x18000ad73  jz      short loc_18000AD82
0x18000ad75  mov     r8, r14; Size
0x18000ad78  xor     edx, edx; Val
0x18000ad7a  mov     rcx, rax; void *
0x18000ad7d  call    memset_0
0x18000ad82  mov     r14d, [rsp+198h+var_164]
0x18000ad87  test    rbx, rbx
0x18000ad8a  jz      short loc_18000ADF4
0x18000ad8c  mov     r15, rdi
0x18000ad8f  mov     rsi, rbx
0x18000ad92  mov     edi, [rsp+198h+var_168]
0x18000ad96  mov     r8d, 0C0000095h
0x18000ad9c  mov     r9d, 8
0x18000ada2  jmp     loc_18000AC04
0x18000ada7  lea     r9, aFailedToReadMo; "Failed to read module name from tagref"
0x18000adae  mov     r8d, 9Bh
0x18000adb4  lea     rdx, aSesdbreadinex; "SeSdbReadInEx"
0x18000adbb  mov     ecx, 1
0x18000adc0  mov     ebx, 0C00000E5h
0x18000adc5  call    AslLogCallPrintf
0x18000adca  jmp     loc_18000AB04
0x18000adcf  mov     r9, r14; Size
0x18000add2  mov     r8, rsi; Ptr
0x18000add5  call    cs:__imp_RtlReAllocateHeap
0x18000addb  mov     rbx, rax
0x18000adde  jmp     loc_18000ACE6
0x18000ade3  mov     r9, r14; Size
0x18000ade6  mov     r8, rsi; Ptr
0x18000ade9  call    cs:__imp_RtlReAllocateHeap
0x18000adef  mov     rbx, rax
0x18000adf2  jmp     short loc_18000AD82
0x18000adf4  mov     eax, 0C0000017h
0x18000adf9  jmp     loc_18000AC31
0x18000adfe  mov     eax, 0C000000Dh
0x18000ae03  jmp     loc_18000AC35
0x18000ae08  mov     eax, 1
0x18000ae0d  mov     [rsp+198h+var_160], 0
0x18000ae16  mul     r9
0x18000ae19  test    rdx, rdx
0x18000ae1c  jnz     loc_18000AADC
0x18000ae22  lea     rcx, [rax+rsi]; void *
0x18000ae26  cmp     rcx, rsi
0x18000ae29  jb      loc_18000AADC
0x18000ae2f  mov     rax, r9
0x18000ae32  mov     [rsp+198h+var_160], rdx
0x18000ae37  mul     rbp
0x18000ae3a  test    rdx, rdx
0x18000ae3d  jnz     loc_18000AADC
0x18000ae43  mov     r8, rax; Size
0x18000ae46  mov     rdx, rbx; Src
0x18000ae49  call    memmove_0
0x18000ae4e  inc     rbp
0x18000ae51  mov     [rbx], r12d
0x18000ae54  jmp     loc_18000AC3F
0x18000ae59  inc     rbp
0x18000ae5c  mov     [rax], r12d
0x18000ae5f  xor     eax, eax
0x18000ae61  jmp     loc_18000AC35
```
