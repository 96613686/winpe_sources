# BfspCompareObjects

- ea: `0x140005100`
- end: `0x1400052b4`
- name: `BfspCompareObjects`
- size: `436`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007e20`
- `0x140008104`

## callees

- `0x140005100`
- `0x140006a14`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400051f5`
- `msvcrt!_wcsicmp` at `0x1400051f5`
- `msvcrt!_wcsupr` at `0x1400051af`
- `msvcrt!_wcsupr` at `0x1400051b8`
- `msvcrt!_wcsupr` at `0x1400051af`
- `msvcrt!_wcsupr` at `0x1400051b8`
- `KERNEL32!HeapFree` at `0x140005212`
- `KERNEL32!HeapFree` at `0x14000522b`
- `KERNEL32!HeapFree` at `0x14000526b`
- `KERNEL32!HeapFree` at `0x140005284`
- `KERNEL32!HeapFree` at `0x140005212`
- `KERNEL32!HeapFree` at `0x14000522b`
- `KERNEL32!HeapFree` at `0x14000526b`
- `KERNEL32!HeapFree` at `0x140005284`
- `KERNEL32!GetProcessHeap` at `0x140005204`
- `KERNEL32!GetProcessHeap` at `0x14000521d`
- `KERNEL32!GetProcessHeap` at `0x14000525d`
- `KERNEL32!GetProcessHeap` at `0x140005276`
- `KERNEL32!GetProcessHeap` at `0x140005204`
- `KERNEL32!GetProcessHeap` at `0x14000521d`
- `KERNEL32!GetProcessHeap` at `0x14000525d`
- `KERNEL32!GetProcessHeap` at `0x140005276`
- `ntdll!RtlCompareMemory` at `0x1400051c7`
- `ntdll!RtlCompareMemory` at `0x1400051c7`

## pseudocode

```c
__int64 __fastcall BfspCompareObjects(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, char *a5)
{
  wchar_t *v5; // rdi
  wchar_t *v6; // rsi
  char v7; // r12
  __int64 v8; // r15
  __int64 v10; // rbx
  unsigned int v11; // r14d
  SIZE_T v12; // rbx
  int v13; // r14d
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  int v19; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *v20; // [rsp+28h] [rbp-20h] BYREF
  wchar_t *String; // [rsp+30h] [rbp-18h] BYREF
  __int64 v22; // [rsp+90h] [rbp+48h]
  __int64 v24; // [rsp+A0h] [rbp+58h]
  SIZE_T Length; // [rsp+A8h] [rbp+60h] BYREF

  v24 = a3;
  v22 = a1;
  v5 = 0;
  v19 = 0;
  v6 = 0;
  LODWORD(Length) = 0;
  v7 = 0;
  v20 = 0;
  v8 = 0;
  String = 0;
  v10 = a2;
  if ( a4 )
  {
    while ( 1 )
    {
      v11 = *(_DWORD *)(a3 + 4 * v8);
      if ( (int)BfspGetBcdElementData(a1, v11, &v20, &v19) < 0 )
        break;
      if ( (int)BfspGetBcdElementData(v10, v11, &String, &Length) < 0
        || (v12 = (unsigned int)Length, (_DWORD)Length != v19) )
      {
        v5 = v20;
        v6 = String;
        goto LABEL_19;
      }
      v5 = v20;
      v13 = v11 & 0xF000000;
      v6 = String;
      if ( v13 == 0x2000000 )
      {
        _wcsupr(String);
        _wcsupr(v5);
      }
      if ( RtlCompareMemory(v5, v6, v12) != v12
        && (v13 != 0x1000000
         || *(_DWORD *)v5 != 4
         || *(_DWORD *)v6 != 4
         || *((_DWORD *)v5 + 5) != *((_DWORD *)v6 + 5)
         || _wcsicmp(v5 + 12, v6 + 12)) )
      {
        goto LABEL_19;
      }
      if ( v6 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
      }
      if ( v5 )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v5);
      }
      v10 = a2;
      v6 = 0;
      a3 = v24;
      v5 = 0;
      a1 = v22;
      v8 = (unsigned int)(v8 + 1);
      String = 0;
      v20 = 0;
      if ( (unsigned int)v8 >= a4 )
        goto LABEL_18;
    }
    v5 = v20;
  }
  else
  {
LABEL_18:
    v7 = 1;
LABEL_19:
    if ( v6 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v6);
    }
  }
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
  }
  *a5 = v7;
  return 0;
}

```

## disassembly

```asm
0x140005100  mov     [rsp-40h+arg_10], r8
0x140005105  mov     [rsp-40h+arg_8], rdx
0x14000510a  mov     [rsp-40h+arg_0], rcx
0x14000510f  push    rbp
0x140005110  push    rbx
0x140005111  push    rsi
0x140005112  push    rdi
0x140005113  push    r12
0x140005115  push    r13
0x140005117  push    r14
0x140005119  push    r15
0x14000511b  mov     rbp, rsp
0x14000511e  sub     rsp, 48h
0x140005122  xor     edi, edi
0x140005124  mov     [rbp+var_28], 0
0x14000512b  xor     esi, esi
0x14000512d  mov     dword ptr [rbp+Length], 0
0x140005134  xor     r12b, r12b
0x140005137  mov     [rbp+var_20], rdi
0x14000513b  xor     r15d, r15d
0x14000513e  mov     [rbp+String], rsi
0x140005142  mov     r13d, r9d
0x140005145  mov     rbx, rdx
0x140005148  test    r9d, r9d
0x14000514b  jz      loc_140005255
0x140005151  mov     r14d, [r8+r15*4]
0x140005155  lea     r9, [rbp+var_28]
0x140005159  lea     r8, [rbp+var_20]
0x14000515d  mov     edx, r14d
0x140005160  call    BfspGetBcdElementData
0x140005165  test    eax, eax
0x140005167  js      loc_1400052AE
0x14000516d  lea     r9, [rbp+Length]
0x140005171  mov     edx, r14d
0x140005174  lea     r8, [rbp+String]
0x140005178  mov     rcx, rbx
0x14000517b  call    BfspGetBcdElementData
0x140005180  test    eax, eax
0x140005182  js      loc_1400052A4
0x140005188  mov     ebx, dword ptr [rbp+Length]
0x14000518b  cmp     ebx, [rbp+var_28]
0x14000518e  jnz     loc_1400052A4
0x140005194  mov     rdi, [rbp+var_20]
0x140005198  and     r14d, 0F000000h
0x14000519f  mov     rsi, [rbp+String]
0x1400051a3  cmp     r14d, 2000000h
0x1400051aa  jnz     short loc_1400051BE
0x1400051ac  mov     rcx, rsi; String
0x1400051af  call    cs:__imp__wcsupr
0x1400051b5  mov     rcx, rdi; String
0x1400051b8  call    cs:__imp__wcsupr
0x1400051be  mov     r8, rbx; Length
0x1400051c1  mov     rdx, rsi; Source2
0x1400051c4  mov     rcx, rdi; Source1
0x1400051c7  call    cs:__imp_RtlCompareMemory
0x1400051cd  cmp     rax, rbx
0x1400051d0  jz      short loc_1400051FF
0x1400051d2  cmp     r14d, 1000000h
0x1400051d9  jnz     short loc_140005258
0x1400051db  cmp     dword ptr [rdi], 4
0x1400051de  jnz     short loc_140005258
0x1400051e0  cmp     dword ptr [rsi], 4
0x1400051e3  jnz     short loc_140005258
0x1400051e5  mov     eax, [rsi+14h]
0x1400051e8  cmp     [rdi+14h], eax
0x1400051eb  jnz     short loc_140005258
0x1400051ed  lea     rdx, [rsi+18h]; String2
0x1400051f1  lea     rcx, [rdi+18h]; String1
0x1400051f5  call    cs:__imp__wcsicmp
0x1400051fb  test    eax, eax
0x1400051fd  jnz     short loc_140005258
0x1400051ff  test    rsi, rsi
0x140005202  jz      short loc_140005218
0x140005204  call    cs:__imp_GetProcessHeap
0x14000520a  mov     r8, rsi; lpMem
0x14000520d  xor     edx, edx; dwFlags
0x14000520f  mov     rcx, rax; hHeap
0x140005212  call    cs:__imp_HeapFree
0x140005218  test    rdi, rdi
0x14000521b  jz      short loc_140005231
0x14000521d  call    cs:__imp_GetProcessHeap
0x140005223  mov     r8, rdi; lpMem
0x140005226  xor     edx, edx; dwFlags
0x140005228  mov     rcx, rax; hHeap
0x14000522b  call    cs:__imp_HeapFree
0x140005231  mov     rbx, [rbp+arg_8]
0x140005235  xor     esi, esi
0x140005237  mov     r8, [rbp+arg_10]
0x14000523b  xor     edi, edi
0x14000523d  mov     rcx, [rbp+arg_0]
0x140005241  inc     r15d
0x140005244  mov     [rbp+String], rsi
0x140005248  mov     [rbp+var_20], rdi
0x14000524c  cmp     r15d, r13d
0x14000524f  jb      loc_140005151
0x140005255  mov     r12b, 1
0x140005258  test    rsi, rsi
0x14000525b  jz      short loc_140005271
0x14000525d  call    cs:__imp_GetProcessHeap
0x140005263  mov     r8, rsi; lpMem
0x140005266  xor     edx, edx; dwFlags
0x140005268  mov     rcx, rax; hHeap
0x14000526b  call    cs:__imp_HeapFree
0x140005271  test    rdi, rdi
0x140005274  jz      short loc_14000528A
0x140005276  call    cs:__imp_GetProcessHeap
0x14000527c  mov     r8, rdi; lpMem
0x14000527f  xor     edx, edx; dwFlags
0x140005281  mov     rcx, rax; hHeap
0x140005284  call    cs:__imp_HeapFree
0x14000528a  mov     rax, [rbp+arg_20]
0x14000528e  mov     [rax], r12b
0x140005291  xor     eax, eax
0x140005293  add     rsp, 48h
0x140005297  pop     r15
0x140005299  pop     r14
0x14000529b  pop     r13
0x14000529d  pop     r12
0x14000529f  pop     rdi
0x1400052a0  pop     rsi
0x1400052a1  pop     rbx
0x1400052a2  pop     rbp
0x1400052a3  retn
0x1400052a4  mov     rdi, [rbp+var_20]
0x1400052a8  mov     rsi, [rbp+String]
0x1400052ac  jmp     short loc_140005258
0x1400052ae  mov     rdi, [rbp+var_20]
0x1400052b2  jmp     short loc_140005271
```
