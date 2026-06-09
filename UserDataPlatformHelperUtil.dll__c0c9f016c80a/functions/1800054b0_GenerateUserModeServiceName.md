# GenerateUserModeServiceName

- ea: `0x1800054b0`
- end: `0x180005596`
- name: `GenerateUserModeServiceName`
- size: `230`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800059e0`
- `0x180005d90`

## callees

- `0x1800024c4`
- `0x1800054b0`
- `0x1800058d0`

## import_xrefs

- `api-ms-win-service-private-l1-1-3!QueryUserServiceNameForContext` at `0x18000556d`
- `api-ms-win-service-private-l1-1-3!QueryUserServiceNameForContext` at `0x18000556d`
- `api-ms-win-service-private-l1-1-2!QueryLocalUserServiceName` at `0x18000558e`
- `api-ms-win-service-private-l1-1-2!QueryLocalUserServiceName` at `0x18000558e`

## pseudocode

```c
__int64 __fastcall GenerateUserModeServiceName(_WORD *a1, _WORD *a2, unsigned __int64 a3, __int64 a4)
{
  unsigned __int64 v4; // rdi
  _WORD *v6; // rbx
  __int64 v8; // rax
  int v9; // ecx
  __int64 result; // rax
  int v11; // [rsp+48h] [rbp+10h] BYREF

  v4 = a3;
  v11 = a3;
  *a2 = 0;
  v6 = a2;
  if ( IsCommsSystemService() )
  {
    if ( v4 )
    {
      if ( v4 <= 0x7FFFFFFF )
      {
        v8 = 2147483646;
        v9 = 0;
        while ( v8 )
        {
          if ( *a1 )
          {
            *v6++ = *a1++;
            --v8;
            if ( --v4 )
              continue;
          }
          if ( !v4 )
          {
            --v6;
            v9 = -2147024774;
          }
          break;
        }
        *v6 = 0;
        if ( v9 >= 0 )
          return 0;
        return (unsigned int)v9;
      }
      *v6 = 0;
    }
    return (unsigned int)-2147024809;
  }
  if ( a4 && (unsigned __int8)IsUMgrQueryUserContextPresent() )
    result = QueryUserServiceNameForContext(a1, a4, v6, &v11);
  else
    result = QueryLocalUserServiceName(a1, v6, &v11);
  if ( !(_DWORD)result )
    return 0;
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800054b0  mov     [rsp+arg_0], rbx
0x1800054b5  mov     [rsp+arg_10], rbp
0x1800054ba  push    rsi
0x1800054bb  push    rdi
0x1800054bc  push    r14
0x1800054be  sub     rsp, 20h
0x1800054c2  mov     rdi, r8
0x1800054c5  xor     r14d, r14d
0x1800054c8  mov     [rsp+38h+arg_8], edi
0x1800054cc  mov     rbp, r9
0x1800054cf  mov     [rdx], r14w
0x1800054d3  mov     rbx, rdx
0x1800054d6  mov     rsi, rcx
0x1800054d9  call    IsCommsSystemService
0x1800054de  test    eax, eax
0x1800054e0  jz      short loc_180005551
0x1800054e2  test    rdi, rdi
0x1800054e5  jz      short loc_180005548
0x1800054e7  cmp     rdi, 7FFFFFFFh
0x1800054ee  ja      short loc_180005544
0x1800054f0  mov     eax, 7FFFFFFEh
0x1800054f5  mov     ecx, r14d
0x1800054f8  test    rax, rax
0x1800054fb  jz      short loc_180005527
0x1800054fd  movzx   edx, word ptr [rsi]
0x180005500  test    dx, dx
0x180005503  jz      short loc_180005519
0x180005505  mov     [rbx], dx
0x180005508  add     rsi, 2
0x18000550c  add     rbx, 2
0x180005510  dec     rax
0x180005513  sub     rdi, 1
0x180005517  jnz     short loc_1800054F8
0x180005519  test    rdi, rdi
0x18000551c  jnz     short loc_180005527
0x18000551e  sub     rbx, 2
0x180005522  mov     ecx, 8007007Ah
0x180005527  mov     [rbx], r14w
0x18000552b  test    ecx, ecx
0x18000552d  js      short loc_18000554D
0x18000552f  xor     eax, eax
0x180005531  mov     rbx, [rsp+38h+arg_0]
0x180005536  mov     rbp, [rsp+38h+arg_10]
0x18000553b  add     rsp, 20h
0x18000553f  pop     r14
0x180005541  pop     rdi
0x180005542  pop     rsi
0x180005543  retn
0x180005544  mov     [rbx], r14w
0x180005548  mov     ecx, 80070057h
0x18000554d  mov     eax, ecx
0x18000554f  jmp     short loc_180005531
0x180005551  test    rbp, rbp
0x180005554  jz      short loc_180005583
0x180005556  call    IsUMgrQueryUserContextPresent
0x18000555b  test    al, al
0x18000555d  jz      short loc_180005583
0x18000555f  lea     r9, [rsp+38h+arg_8]
0x180005564  mov     r8, rbx
0x180005567  mov     rdx, rbp
0x18000556a  mov     rcx, rsi
0x18000556d  call    cs:__imp_QueryUserServiceNameForContext
0x180005573  test    eax, eax
0x180005575  jz      short loc_18000552F
0x180005577  jle     short loc_180005531
0x180005579  movzx   eax, ax
0x18000557c  or      eax, 80070000h
0x180005581  jmp     short loc_180005531
0x180005583  lea     r8, [rsp+38h+arg_8]
0x180005588  mov     rdx, rbx
0x18000558b  mov     rcx, rsi
0x18000558e  call    cs:__imp_QueryLocalUserServiceName
0x180005594  jmp     short loc_180005573
```
