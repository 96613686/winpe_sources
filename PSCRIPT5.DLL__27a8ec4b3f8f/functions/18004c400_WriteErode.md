# WriteErode

- ea: `0x18004c400`
- end: `0x18004c60f`
- name: `WriteErode`
- size: `527`
- prototype: `__int64 __fastcall(_DWORD *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18004d3a8`
- `0x18004e4fc`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18004a858`
- `0x18004b410`
- `0x18004b4bc`
- `0x18004b690`
- `0x18004c400`
- `0x180054aa8`
- `0x180054b28`

## pseudocode

```c
__int64 __fastcall WriteErode(_DWORD *a1, int a2)
{
  int *v4; // rdi
  __int64 result; // rax
  int v6; // r14d
  int v7; // eax
  int v8; // r9d
  __int64 v9; // r10
  int fixed; // eax
  __int64 v11; // r10
  int v12; // eax
  int v13; // r9d
  int v14; // r10d
  int v15; // r11d
  const char *v16; // rdx
  int i; // esi
  int v18; // eax
  int v19; // [rsp+28h] [rbp-100h]
  _DWORD v20[48]; // [rsp+40h] [rbp-E8h] BYREF

  memset_0(v20, 0, sizeof(v20));
  v4 = a1 + 461;
  result = Blend((__int64)a1, a1 + 461, a1[460], 1, v20, v19, 0);
  v6 = result;
  if ( a1[460] && *v4 )
  {
    PutString((__int64)a1, (__int64)"/Erode{\r\n");
    if ( a1[122] )
    {
      if ( a2 )
      {
        v8 = 0;
        v9 = 0;
        if ( (int)a1[460] > 0 )
        {
          do
          {
            fixed = XCF_FixDiv(a1[v9 + 461], 0x80000);
            v12 = XCF_FixMul(fixed, a1[v11 + 123]);
            v8 = v12 + v13;
            v9 = (unsigned int)(v14 + 1);
          }
          while ( (int)v9 < v15 );
        }
        PutNumber((__int64)a1, v8, 0);
        v16 = " ";
      }
      else
      {
        PutString((__int64)a1, (__int64)"{ ");
        for ( i = 0; i < a1[460]; ++i )
        {
          v18 = XCF_FixDiv(a1[i + 461], 0x80000);
          PutNumber((__int64)a1, v18, 0);
          PutString((__int64)a1, (__int64)" ");
        }
        v16 = "}";
      }
      PutString((__int64)a1, (__int64)v16);
    }
    else
    {
      v7 = XCF_FixDiv(*v4, 0x80000);
      PutNumber((__int64)a1, v7, 0);
    }
    PutString((__int64)a1, (__int64)" dup 3 -1 roll 0.1 mul exch 0.5 sub mul cvi sub dup mul\r\n");
    if ( a2 || !a1[122] )
    {
      PutNumber((__int64)a1, v6, 0);
    }
    else
    {
      PutString((__int64)a1, (__int64)"{ ");
      PutNumberList((__int64)a1, (__int64)(a1 + 461), a1[460], 0);
      PutString((__int64)a1, (__int64)"}");
    }
    return PutString(
             (__int64)a1,
             (__int64)" 0 dtransform dup mul exch dup mul add\r\nle{pop pop 1.0 1.0}{pop pop 0.0 1.5}ifelse}def\r\n");
  }
  return result;
}

```

## disassembly

```asm
0x18004c400  mov     [rsp+arg_8], rbx
0x18004c405  mov     [rsp+arg_10], rbp
0x18004c40a  push    rsi
0x18004c40b  push    rdi
0x18004c40c  push    r14
0x18004c40e  sub     rsp, 110h
0x18004c415  mov     rax, cs:__security_cookie
0x18004c41c  xor     rax, rsp
0x18004c41f  mov     [rsp+128h+var_28], rax
0x18004c427  mov     ebp, edx
0x18004c429  mov     rbx, rcx
0x18004c42c  xor     edx, edx; Val
0x18004c42e  lea     rcx, [rsp+128h+var_E8]; void *
0x18004c433  mov     r8d, 0C0h; Size
0x18004c439  call    memset_0
0x18004c43e  mov     r8d, [rbx+730h]
0x18004c445  lea     rax, [rsp+128h+var_E8]
0x18004c44a  lea     rdi, [rbx+734h]
0x18004c451  mov     [rsp+128h+var_F8], 0
0x18004c459  mov     rdx, rdi
0x18004c45c  mov     [rsp+128h+var_108], rax
0x18004c461  mov     r9d, 1
0x18004c467  mov     rcx, rbx
0x18004c46a  call    Blend
0x18004c46f  cmp     dword ptr [rbx+730h], 0
0x18004c476  mov     r14d, eax
0x18004c479  jz      loc_18004C5E6
0x18004c47f  cmp     dword ptr [rdi], 0
0x18004c482  jz      loc_18004C5E6
0x18004c488  lea     rdx, aErode; "/Erode{\r\n"
0x18004c48f  mov     rcx, rbx
0x18004c492  call    PutString
0x18004c497  cmp     dword ptr [rbx+1E8h], 0
0x18004c49e  jnz     short loc_18004C4BE
0x18004c4a0  mov     ecx, [rdi]
0x18004c4a2  mov     edx, 80000h
0x18004c4a7  call    XCF_FixDiv
0x18004c4ac  mov     edx, eax
0x18004c4ae  mov     rcx, rbx
0x18004c4b1  xor     r8d, r8d
0x18004c4b4  call    PutNumber
0x18004c4b9  jmp     loc_18004C579
0x18004c4be  test    ebp, ebp
0x18004c4c0  jz      short loc_18004C517
0x18004c4c2  mov     r11d, [rbx+730h]
0x18004c4c9  xor     r9d, r9d
0x18004c4cc  xor     r10d, r10d
0x18004c4cf  test    r11d, r11d
0x18004c4d2  jle     short loc_18004C500
0x18004c4d4  mov     ecx, [rbx+r10*4+734h]
0x18004c4dc  mov     edx, 80000h
0x18004c4e1  call    XCF_FixDiv
0x18004c4e6  mov     edx, [rbx+r10*4+1ECh]
0x18004c4ee  mov     ecx, eax
0x18004c4f0  call    XCF_FixMul
0x18004c4f5  add     r9d, eax
0x18004c4f8  inc     r10d
0x18004c4fb  cmp     r10d, r11d
0x18004c4fe  jl      short loc_18004C4D4
0x18004c500  xor     r8d, r8d
0x18004c503  mov     edx, r9d
0x18004c506  mov     rcx, rbx
0x18004c509  call    PutNumber
0x18004c50e  lea     rdx, asc_180064A10; " "
0x18004c515  jmp     short loc_18004C571
0x18004c517  lea     rdx, asc_18006ABEC; "{ "
0x18004c51e  mov     rcx, rbx
0x18004c521  call    PutString
0x18004c526  xor     esi, esi
0x18004c528  cmp     [rbx+730h], esi
0x18004c52e  jle     short loc_18004C56A
0x18004c530  movsxd  rcx, esi
0x18004c533  mov     edx, 80000h
0x18004c538  mov     ecx, [rbx+rcx*4+734h]
0x18004c53f  call    XCF_FixDiv
0x18004c544  mov     edx, eax
0x18004c546  mov     rcx, rbx
0x18004c549  xor     r8d, r8d
0x18004c54c  call    PutNumber
0x18004c551  lea     rdx, asc_180064A10; " "
0x18004c558  mov     rcx, rbx
0x18004c55b  call    PutString
0x18004c560  inc     esi
0x18004c562  cmp     esi, [rbx+730h]
0x18004c568  jl      short loc_18004C530
0x18004c56a  lea     rdx, asc_18006ABE8; "}"
0x18004c571  mov     rcx, rbx
0x18004c574  call    PutString
0x18004c579  lea     rdx, aDup31Roll01Mul; " dup 3 -1 roll 0.1 mul exch 0.5 sub mul"...
0x18004c580  mov     rcx, rbx
0x18004c583  call    PutString
0x18004c588  test    ebp, ebp
0x18004c58a  jnz     short loc_18004C5C9
0x18004c58c  cmp     [rbx+1E8h], ebp
0x18004c592  jz      short loc_18004C5C9
0x18004c594  lea     rdx, asc_18006ABEC; "{ "
0x18004c59b  mov     rcx, rbx
0x18004c59e  call    PutString
0x18004c5a3  mov     r8d, [rbx+730h]
0x18004c5aa  xor     r9d, r9d
0x18004c5ad  mov     rdx, rdi
0x18004c5b0  mov     rcx, rbx
0x18004c5b3  call    PutNumberList
0x18004c5b8  lea     rdx, asc_18006ABE8; "}"
0x18004c5bf  mov     rcx, rbx
0x18004c5c2  call    PutString
0x18004c5c7  jmp     short loc_18004C5D7
0x18004c5c9  xor     r8d, r8d
0x18004c5cc  mov     edx, r14d
0x18004c5cf  mov     rcx, rbx
0x18004c5d2  call    PutNumber
0x18004c5d7  lea     rdx, a0DtransformDup; " 0 dtransform dup mul exch dup mul add"...
0x18004c5de  mov     rcx, rbx
0x18004c5e1  call    PutString
0x18004c5e6  mov     rcx, [rsp+128h+var_28]
0x18004c5ee  xor     rcx, rsp; StackCookie
0x18004c5f1  call    __security_check_cookie
0x18004c5f6  lea     r11, [rsp+128h+var_18]
0x18004c5fe  mov     rbx, [r11+28h]
0x18004c602  mov     rbp, [r11+30h]
0x18004c606  mov     rsp, r11
0x18004c609  pop     r14
0x18004c60b  pop     rdi
0x18004c60c  pop     rsi
0x18004c60d  retn
```
