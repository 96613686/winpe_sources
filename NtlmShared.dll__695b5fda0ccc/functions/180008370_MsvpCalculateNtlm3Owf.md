# MsvpCalculateNtlm3Owf

- ea: `0x180008370`
- end: `0x180008520`
- name: `MsvpCalculateNtlm3Owf`
- size: `432`
- prototype: `__int64 __fastcall(PUCHAR pbSecret)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008c90`
- `0x180009090`

## callees

- `0x180008370`
- `0x180009664`
- `0x18000c560`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeString` at `0x1800083c2`
- `ntdll!RtlUpcaseUnicodeString` at `0x1800083c2`
- `bcrypt!BCryptHashData` at `0x180008437`
- `bcrypt!BCryptHashData` at `0x18000847b`
- `bcrypt!BCryptHashData` at `0x180008437`
- `bcrypt!BCryptHashData` at `0x18000847b`
- `bcrypt!BCryptCreateHash` at `0x1800083ed`
- `bcrypt!BCryptCreateHash` at `0x1800083ed`
- `bcrypt!BCryptDestroyHash` at `0x1800084fd`
- `bcrypt!BCryptDestroyHash` at `0x1800084fd`
- `bcrypt!BCryptFinishHash` at `0x1800084b6`
- `bcrypt!BCryptFinishHash` at `0x1800084b6`

## pseudocode

```c
__int64 __fastcall MsvpCalculateNtlm3Owf(PUCHAR pbSecret, const UNICODE_STRING *a2, PUCHAR *a3, UCHAR *a4)
{
  NTSTATUS v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-C0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  char v13; // [rsp+60h] [rbp-A0h] BYREF

  phHash = 0;
  *(_QWORD *)&DestinationString.Length = 67239936;
  DestinationString.Buffer = (PWSTR)&v13;
  RtlUpcaseUnicodeString(&DestinationString, a2, 0);
  v7 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, pbSecret, 0x10u, 0);
  if ( v7 >= 0 )
  {
    v7 = BCryptHashData(phHash, (PUCHAR)DestinationString.Buffer, DestinationString.Length, 0);
    if ( v7 >= 0 )
    {
      v7 = BCryptHashData(phHash, a3[1], *(unsigned __int16 *)a3, 0);
      if ( v7 >= 0 )
      {
        v7 = BCryptFinishHash(phHash, a4, 0x10u, 0);
        if ( v7 < 0 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v9 = 21;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v9 = 20;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v9 = 19;
        goto LABEL_17;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v9 = 18;
LABEL_17:
      WPP_SF_D(v8[2], v9, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids, (unsigned int)v7);
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008370  push    rbp
0x180008372  push    rbx
0x180008373  push    rsi
0x180008374  push    rdi
0x180008375  lea     rbp, [rsp-388h]
0x18000837d  sub     rsp, 488h
0x180008384  mov     rax, cs:__security_cookie
0x18000838b  xor     rax, rsp
0x18000838e  mov     [rbp+3A0h+var_30], rax
0x180008395  mov     rdi, r8
0x180008398  mov     [rsp+4A0h+phHash], 0
0x1800083a1  mov     rbx, rcx
0x1800083a4  mov     qword ptr [rsp+4A0h+DestinationString.Length], 4020000h
0x1800083ad  lea     rax, [rsp+4A0h+var_440]
0x1800083b2  xor     r8d, r8d; AllocateDestinationString
0x1800083b5  lea     rcx, [rsp+4A0h+DestinationString]; DestinationString
0x1800083ba  mov     [rsp+4A0h+DestinationString.Buffer], rax
0x1800083bf  mov     rsi, r9
0x1800083c2  call    cs:__imp_RtlUpcaseUnicodeString
0x1800083c8  mov     [rsp+4A0h+dwFlags], 0; dwFlags
0x1800083d0  lea     rdx, [rsp+4A0h+phHash]; phHash
0x1800083d5  mov     [rsp+4A0h+cbSecret], 10h; cbSecret
0x1800083dd  xor     r9d, r9d; cbHashObject
0x1800083e0  xor     r8d, r8d; pbHashObject
0x1800083e3  mov     [rsp+4A0h+pbSecret], rbx; pbSecret
0x1800083e8  mov     ecx, 91h; hAlgorithm
0x1800083ed  call    cs:__imp_BCryptCreateHash
0x1800083f3  mov     ebx, eax
0x1800083f5  test    eax, eax
0x1800083f7  jns     short loc_180008424
0x1800083f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008400  lea     rax, WPP_GLOBAL_Control
0x180008407  cmp     rcx, rax
0x18000840a  jz      loc_1800084F3
0x180008410  test    byte ptr [rcx+1Ch], 8
0x180008414  jz      loc_1800084F3
0x18000841a  mov     edx, 12h
0x18000841f  jmp     loc_1800084E0
0x180008424  movzx   r8d, [rsp+4A0h+DestinationString.Length]; cbInput
0x18000842a  xor     r9d, r9d; dwFlags
0x18000842d  mov     rdx, [rsp+4A0h+DestinationString.Buffer]; pbInput
0x180008432  mov     rcx, [rsp+4A0h+phHash]; hHash
0x180008437  call    cs:__imp_BCryptHashData
0x18000843d  mov     ebx, eax
0x18000843f  test    eax, eax
0x180008441  jns     short loc_18000846B
0x180008443  mov     rcx, cs:WPP_GLOBAL_Control
0x18000844a  lea     rax, WPP_GLOBAL_Control
0x180008451  cmp     rcx, rax
0x180008454  jz      loc_1800084F3
0x18000845a  test    byte ptr [rcx+1Ch], 8
0x18000845e  jz      loc_1800084F3
0x180008464  mov     edx, 13h
0x180008469  jmp     short loc_1800084E0
0x18000846b  movzx   r8d, word ptr [rdi]; cbInput
0x18000846f  xor     r9d, r9d; dwFlags
0x180008472  mov     rdx, [rdi+8]; pbInput
0x180008476  mov     rcx, [rsp+4A0h+phHash]; hHash
0x18000847b  call    cs:__imp_BCryptHashData
0x180008481  mov     ebx, eax
0x180008483  test    eax, eax
0x180008485  jns     short loc_1800084A7
0x180008487  mov     rcx, cs:WPP_GLOBAL_Control
0x18000848e  lea     rax, WPP_GLOBAL_Control
0x180008495  cmp     rcx, rax
0x180008498  jz      short loc_1800084F3
0x18000849a  test    byte ptr [rcx+1Ch], 8
0x18000849e  jz      short loc_1800084F3
0x1800084a0  mov     edx, 14h
0x1800084a5  jmp     short loc_1800084E0
0x1800084a7  mov     rcx, [rsp+4A0h+phHash]; hHash
0x1800084ac  xor     r9d, r9d; dwFlags
0x1800084af  mov     rdx, rsi; pbOutput
0x1800084b2  lea     r8d, [r9+10h]; cbOutput
0x1800084b6  call    cs:__imp_BCryptFinishHash
0x1800084bc  mov     ebx, eax
0x1800084be  test    eax, eax
0x1800084c0  jns     short loc_1800084F3
0x1800084c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084c9  lea     rax, WPP_GLOBAL_Control
0x1800084d0  cmp     rcx, rax
0x1800084d3  jz      short loc_1800084F3
0x1800084d5  test    byte ptr [rcx+1Ch], 8
0x1800084d9  jz      short loc_1800084F3
0x1800084db  mov     edx, 15h
0x1800084e0  mov     rcx, [rcx+10h]
0x1800084e4  lea     r8, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids
0x1800084eb  mov     r9d, ebx
0x1800084ee  call    WPP_SF_D
0x1800084f3  mov     rcx, [rsp+4A0h+phHash]; hHash
0x1800084f8  test    rcx, rcx
0x1800084fb  jz      short loc_180008503
0x1800084fd  call    cs:__imp_BCryptDestroyHash
0x180008503  mov     eax, ebx
0x180008505  mov     rcx, [rbp+3A0h+var_30]
0x18000850c  xor     rcx, rsp; StackCookie
0x18000850f  call    __security_check_cookie
0x180008514  add     rsp, 488h
0x18000851b  pop     rdi
0x18000851c  pop     rsi
0x18000851d  pop     rbx
0x18000851e  pop     rbp
0x18000851f  retn
```
