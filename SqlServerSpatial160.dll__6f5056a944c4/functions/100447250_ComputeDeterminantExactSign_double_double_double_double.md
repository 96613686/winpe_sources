# ComputeDeterminantExactSign(double,double,double,double)

- ea: `0x100447250`
- end: `0x10044739c`
- name: `?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z`
- size: `332`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10042c570`
- `0x10042c6f0`
- `0x10042c790`
- `0x10042d820`
- `0x10042df20`
- `0x10043efe0`
- `0x100442fd0`
- `0x100447890`

## callees

- `0x10042a400`
- `0x10042a4e0`
- `0x10042a7a0`
- `0x100447250`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall ComputeDeterminantExactSign(double a1, double a2, double a3, double a4)
{
  double v4; // xmm4_8
  __int64 result; // rax
  unsigned int v6; // ecx
  unsigned int v7; // [rsp+20h] [rbp-C8h] BYREF
  int v8; // [rsp+24h] [rbp-C4h]
  __int64 v9; // [rsp+28h] [rbp-C0h]
  unsigned int v10; // [rsp+48h] [rbp-A0h] BYREF
  int v11; // [rsp+4Ch] [rbp-9Ch]
  __int64 v12; // [rsp+50h] [rbp-98h]
  _BYTE v13[40]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v14[40]; // [rsp+98h] [rbp-50h] BYREF

  v4 = a1 * a4;
  if ( a1 * a4 == a2 * a3 )
  {
    if ( COERCE_DOUBLE(*(_QWORD *)&v4 & _xmm) > 9.007199254740992e15 )
    {
      _mm_lfence();
      RobustIntersections::CZ<128>::CZ<128>(&v7);
      RobustIntersections::CZ<128>::CZ<128>(&v10);
      RobustIntersections::CZ<128>::CZ<128>(v14);
      RobustIntersections::CZ<128>::CZ<128>(v13);
      RobustIntersections::CZ<128>::Multiply(&v7, v13);
      RobustIntersections::CZ<128>::Multiply(&v10, v14);
      v6 = 0;
      if ( v8 <= v11 )
      {
        if ( v8 >= v11 )
        {
          if ( v8 <= 0 )
          {
            if ( v8 < 0 )
              return (unsigned int)RobustIntersections::EaCompare(v12, v10, v9, v7);
            return v6;
          }
          else
          {
            return RobustIntersections::EaCompare(v9, v7, v12, v10);
          }
        }
        else
        {
          return 0xFFFFFFFFLL;
        }
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    result = 0xFFFFFFFFLL;
    if ( v4 > a2 * a3 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x100447250  sub     rsp, 0E8h
0x100447257  movaps  [rsp+0E8h+var_18], xmm6
0x10044725f  mov     rax, cs:__security_cookie
0x100447266  xor     rax, rsp
0x100447269  mov     [rsp+0E8h+var_28], rax
0x100447271  movaps  xmm6, xmm1
0x100447274  movaps  xmm4, xmm0
0x100447277  movaps  xmm5, xmm6
0x10044727a  mulsd   xmm4, xmm3
0x10044727e  mulsd   xmm5, xmm2
0x100447282  movaps  xmm1, xmm0
0x100447285  ucomisd xmm4, xmm5
0x100447289  jp      loc_10044736B
0x10044728f  jnz     loc_10044736B
0x100447295  andps   xmm4, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10044729c  movsd   xmm0, cs:__real@4340000000000000
0x1004472a4  comisd  xmm0, xmm4
0x1004472a8  jb      short loc_1004472B3
0x1004472aa  xor     ecx, ecx
0x1004472ac  mov     eax, ecx
0x1004472ae  jmp     loc_10044737C
0x1004472b3  lfence
0x1004472b6  lea     rcx, [rsp+0E8h+var_C8]
0x1004472bb  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004472c0  movaps  xmm1, xmm6
0x1004472c3  lea     rcx, [rsp+0E8h+var_A0]
0x1004472c8  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004472cd  movaps  xmm1, xmm2
0x1004472d0  lea     rcx, [rsp+0E8h+var_50]
0x1004472d8  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004472dd  movaps  xmm1, xmm3
0x1004472e0  lea     rcx, [rsp+0E8h+var_78]
0x1004472e5  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x1004472ea  lea     rdx, [rsp+0E8h+var_78]
0x1004472ef  lea     rcx, [rsp+0E8h+var_C8]
0x1004472f4  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004472f9  lea     rdx, [rsp+0E8h+var_50]
0x100447301  lea     rcx, [rsp+0E8h+var_A0]
0x100447306  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044730b  mov     eax, [rsp+0E8h+var_C4]
0x10044730f  xor     ecx, ecx
0x100447311  cmp     eax, [rsp+0E8h+var_9C]
0x100447315  jle     short loc_100447320
0x100447317  mov     ecx, 1
0x10044731c  mov     eax, ecx
0x10044731e  jmp     short loc_10044737C
0x100447320  jge     short loc_10044732B
0x100447322  mov     ecx, 0FFFFFFFFh
0x100447327  mov     eax, ecx
0x100447329  jmp     short loc_10044737C
0x10044732b  test    eax, eax
0x10044732d  jle     short loc_10044734B
0x10044732f  mov     r9d, [rsp+0E8h+var_A0]
0x100447334  mov     r8, [rsp+0E8h+var_98]
0x100447339  mov     edx, [rsp+0E8h+var_C8]
0x10044733d  mov     rcx, [rsp+0E8h+var_C0]
0x100447342  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100447347  mov     ecx, eax
0x100447349  jmp     short loc_10044737C
0x10044734b  jns     short loc_100447367
0x10044734d  mov     r9d, [rsp+0E8h+var_C8]
0x100447352  mov     r8, [rsp+0E8h+var_C0]
0x100447357  mov     edx, [rsp+0E8h+var_A0]
0x10044735b  mov     rcx, [rsp+0E8h+var_98]
0x100447360  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100447365  mov     ecx, eax
0x100447367  mov     eax, ecx
0x100447369  jmp     short loc_10044737C
0x10044736b  comisd  xmm4, xmm5
0x10044736f  mov     eax, 0FFFFFFFFh
0x100447374  mov     ecx, 1
0x100447379  cmova   eax, ecx
0x10044737c  mov     rcx, [rsp+0E8h+var_28]
0x100447384  xor     rcx, rsp; StackCookie
0x100447387  call    __security_check_cookie
0x10044738c  movaps  xmm6, [rsp+0E8h+var_18]
0x100447394  add     rsp, 0E8h
0x10044739b  retn
```
