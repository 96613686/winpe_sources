# WriteErode

- ea: `0x18004ab80`
- end: `0x18004ad8e`
- name: `WriteErode`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18004bb20`
- `0x18004cc6c`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180048fe4`
- `0x180049b98`
- `0x180049c40`
- `0x180049e14`
- `0x18004ab80`
- `0x180053114`
- `0x180053190`

## pseudocode

```c
__int64 __fastcall WriteErode(_DWORD *a1, int a2)
{
  _DWORD *v4; // rdi
  __int64 result; // rax
  unsigned int v6; // r14d
  unsigned int v7; // eax
  unsigned int v8; // r9d
  __int64 v9; // r10
  unsigned int fixed; // eax
  __int64 v11; // r10
  int v12; // eax
  int v13; // r9d
  int v14; // r10d
  int v15; // r11d
  int i; // esi
  unsigned int v17; // eax
  _BYTE v18[192]; // [rsp+40h] [rbp-E8h] BYREF

  memset_0(v18, 0, sizeof(v18));
  v4 = a1 + 461;
  result = Blend((_DWORD)a1, (int)a1 + 1844, a1[460], 1, (__int64)v18);
  v6 = result;
  if ( a1[460] && *v4 )
  {
    PutString(a1, "/Erode{\r\n");
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
            fixed = XCF_FixDiv((unsigned int)a1[v9 + 461], 0x80000);
            v12 = XCF_FixMul(fixed, (unsigned int)a1[v11 + 123]);
            v8 = v12 + v13;
            v9 = (unsigned int)(v14 + 1);
          }
          while ( (int)v9 < v15 );
        }
        PutNumber(a1, v8, 0);
        PutString(a1, " ");
      }
      else
      {
        PutString(a1, "{ ");
        for ( i = 0; i < a1[460]; ++i )
        {
          v17 = XCF_FixDiv((unsigned int)a1[i + 461], 0x80000);
          PutNumber(a1, v17, 0);
          PutString(a1, " ");
        }
        PutString(a1, "}");
      }
    }
    else
    {
      v7 = XCF_FixDiv((unsigned int)*v4, 0x80000);
      PutNumber(a1, v7, 0);
    }
    PutString(a1, " dup 3 -1 roll 0.1 mul exch 0.5 sub mul cvi sub dup mul\r\n");
    if ( a2 || !a1[122] )
    {
      PutNumber(a1, v6, 0);
    }
    else
    {
      PutString(a1, "{ ");
      PutNumberList(a1, a1 + 461, (unsigned int)a1[460], 0);
      PutString(a1, "}");
    }
    return PutString(a1, " 0 dtransform dup mul exch dup mul add\r\nle{pop pop 1.0 1.0}{pop pop 0.0 1.5}ifelse}def\r\n");
  }
  return result;
}

```

## disassembly

```asm
0x18004ab80  mov     [rsp+arg_8], rbx
0x18004ab85  mov     [rsp+arg_10], rbp
0x18004ab8a  push    rsi
0x18004ab8b  push    rdi
0x18004ab8c  push    r14
0x18004ab8e  sub     rsp, 110h
0x18004ab95  mov     rax, cs:__security_cookie
0x18004ab9c  xor     rax, rsp
0x18004ab9f  mov     [rsp+128h+var_28], rax
0x18004aba7  mov     ebp, edx
0x18004aba9  mov     rbx, rcx
0x18004abac  xor     edx, edx; Val
0x18004abae  lea     rcx, [rsp+128h+var_E8]; void *
0x18004abb3  mov     r8d, 0C0h; Size
0x18004abb9  call    memset_0
0x18004abbe  mov     r8d, [rbx+730h]
0x18004abc5  lea     rax, [rsp+128h+var_E8]
0x18004abca  lea     rdi, [rbx+734h]
0x18004abd1  mov     [rsp+128h+var_F8], 0
0x18004abd9  mov     rdx, rdi
0x18004abdc  mov     [rsp+128h+var_108], rax
0x18004abe1  mov     r9d, 1
0x18004abe7  mov     rcx, rbx
0x18004abea  call    Blend
0x18004abef  cmp     dword ptr [rbx+730h], 0
0x18004abf6  mov     r14d, eax
0x18004abf9  jz      loc_18004AD66
0x18004abff  cmp     dword ptr [rdi], 0
0x18004ac02  jz      loc_18004AD66
0x18004ac08  lea     rdx, aErode; "/Erode{\r\n"
0x18004ac0f  mov     rcx, rbx
0x18004ac12  call    PutString
0x18004ac17  cmp     dword ptr [rbx+1E8h], 0
0x18004ac1e  jnz     short loc_18004AC3E
0x18004ac20  mov     ecx, [rdi]
0x18004ac22  mov     edx, 80000h
0x18004ac27  call    XCF_FixDiv
0x18004ac2c  mov     edx, eax
0x18004ac2e  mov     rcx, rbx
0x18004ac31  xor     r8d, r8d
0x18004ac34  call    PutNumber
0x18004ac39  jmp     loc_18004ACF9
0x18004ac3e  test    ebp, ebp
0x18004ac40  jz      short loc_18004AC97
0x18004ac42  mov     r11d, [rbx+730h]
0x18004ac49  xor     r9d, r9d
0x18004ac4c  xor     r10d, r10d
0x18004ac4f  test    r11d, r11d
0x18004ac52  jle     short loc_18004AC80
0x18004ac54  mov     ecx, [rbx+r10*4+734h]
0x18004ac5c  mov     edx, 80000h
0x18004ac61  call    XCF_FixDiv
0x18004ac66  mov     edx, [rbx+r10*4+1ECh]
0x18004ac6e  mov     ecx, eax
0x18004ac70  call    XCF_FixMul
0x18004ac75  add     r9d, eax
0x18004ac78  inc     r10d
0x18004ac7b  cmp     r10d, r11d
0x18004ac7e  jl      short loc_18004AC54
0x18004ac80  xor     r8d, r8d
0x18004ac83  mov     edx, r9d
0x18004ac86  mov     rcx, rbx
0x18004ac89  call    PutNumber
0x18004ac8e  lea     rdx, asc_180062A20; " "
0x18004ac95  jmp     short loc_18004ACF1
0x18004ac97  lea     rdx, asc_180068C2C; "{ "
0x18004ac9e  mov     rcx, rbx
0x18004aca1  call    PutString
0x18004aca6  xor     esi, esi
0x18004aca8  cmp     [rbx+730h], esi
0x18004acae  jle     short loc_18004ACEA
0x18004acb0  movsxd  rcx, esi
0x18004acb3  mov     edx, 80000h
0x18004acb8  mov     ecx, [rbx+rcx*4+734h]
0x18004acbf  call    XCF_FixDiv
0x18004acc4  mov     edx, eax
0x18004acc6  mov     rcx, rbx
0x18004acc9  xor     r8d, r8d
0x18004accc  call    PutNumber
0x18004acd1  lea     rdx, asc_180062A20; " "
0x18004acd8  mov     rcx, rbx
0x18004acdb  call    PutString
0x18004ace0  inc     esi
0x18004ace2  cmp     esi, [rbx+730h]
0x18004ace8  jl      short loc_18004ACB0
0x18004acea  lea     rdx, asc_180068C28; "}"
0x18004acf1  mov     rcx, rbx
0x18004acf4  call    PutString
0x18004acf9  lea     rdx, aDup31Roll01Mul; " dup 3 -1 roll 0.1 mul exch 0.5 sub mul"...
0x18004ad00  mov     rcx, rbx
0x18004ad03  call    PutString
0x18004ad08  test    ebp, ebp
0x18004ad0a  jnz     short loc_18004AD49
0x18004ad0c  cmp     [rbx+1E8h], ebp
0x18004ad12  jz      short loc_18004AD49
0x18004ad14  lea     rdx, asc_180068C2C; "{ "
0x18004ad1b  mov     rcx, rbx
0x18004ad1e  call    PutString
0x18004ad23  mov     r8d, [rbx+730h]
0x18004ad2a  xor     r9d, r9d
0x18004ad2d  mov     rdx, rdi
0x18004ad30  mov     rcx, rbx
0x18004ad33  call    PutNumberList
0x18004ad38  lea     rdx, asc_180068C28; "}"
0x18004ad3f  mov     rcx, rbx
0x18004ad42  call    PutString
0x18004ad47  jmp     short loc_18004AD57
0x18004ad49  xor     r8d, r8d
0x18004ad4c  mov     edx, r14d
0x18004ad4f  mov     rcx, rbx
0x18004ad52  call    PutNumber
0x18004ad57  lea     rdx, a0DtransformDup; " 0 dtransform dup mul exch dup mul add"...
0x18004ad5e  mov     rcx, rbx
0x18004ad61  call    PutString
0x18004ad66  mov     rcx, [rsp+128h+var_28]
0x18004ad6e  xor     rcx, rsp; StackCookie
0x18004ad71  call    __security_check_cookie
0x18004ad76  lea     r11, [rsp+128h+var_18]
0x18004ad7e  mov     rbx, [r11+28h]
0x18004ad82  mov     rbp, [r11+30h]
0x18004ad86  mov     rsp, r11
0x18004ad89  pop     r14
0x18004ad8b  pop     rdi
0x18004ad8c  pop     rsi
0x18004ad8d  retn
```
