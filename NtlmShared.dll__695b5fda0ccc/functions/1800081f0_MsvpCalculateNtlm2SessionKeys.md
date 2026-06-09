# MsvpCalculateNtlm2SessionKeys

- ea: `0x1800081f0`
- end: `0x18000835f`
- name: `MsvpCalculateNtlm2SessionKeys`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800081f0`
- `0x180009664`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180008286`
- `bcrypt!BCryptHashData` at `0x1800082c9`
- `bcrypt!BCryptHashData` at `0x180008286`
- `bcrypt!BCryptHashData` at `0x1800082c9`
- `bcrypt!BCryptCreateHash` at `0x18000822d`
- `bcrypt!BCryptCreateHash` at `0x18000822d`
- `bcrypt!BCryptDestroyHash` at `0x18000834e`
- `bcrypt!BCryptDestroyHash` at `0x18000834e`
- `bcrypt!BCryptFinishHash` at `0x180008307`
- `bcrypt!BCryptFinishHash` at `0x180008307`

## pseudocode

```c
__int64 __fastcall MsvpCalculateNtlm2SessionKeys(UCHAR *a1, UCHAR *a2, UCHAR *a3, UCHAR *a4, _QWORD *a5)
{
  NTSTATUS v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-38h] BYREF

  hHash = 0;
  v8 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &hHash, 0, 0, a1, 0x10u, 0);
  if ( v8 >= 0 )
  {
    v8 = BCryptHashData(hHash, a2, 8u, 0);
    if ( v8 >= 0 )
    {
      v8 = BCryptHashData(hHash, a3, 8u, 0);
      if ( v8 >= 0 )
      {
        v8 = BCryptFinishHash(hHash, a4, 0x10u, 0);
        if ( v8 >= 0 )
        {
          *a5 = *(_QWORD *)a4;
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v10 = 17;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v10 = 16;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v10 = 15;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v10 = 14;
LABEL_5:
      WPP_SF_D(v9[2], v10, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids, (unsigned int)v8);
    }
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800081f0  mov     rax, rsp
0x1800081f3  push    rbx
0x1800081f4  push    rbp
0x1800081f5  push    rsi
0x1800081f6  push    rdi
0x1800081f7  sub     rsp, 58h
0x1800081fb  mov     dword ptr [rax-48h], 0
0x180008202  mov     rdi, r9
0x180008205  mov     dword ptr [rax-50h], 10h
0x18000820c  mov     rbp, r8
0x18000820f  mov     [rax-58h], rcx
0x180008213  mov     rsi, rdx
0x180008216  mov     ecx, 91h; hAlgorithm
0x18000821b  mov     qword ptr [rax-38h], 0
0x180008223  xor     r9d, r9d; cbHashObject
0x180008226  lea     rdx, [rax-38h]; phHash
0x18000822a  xor     r8d, r8d; pbHashObject
0x18000822d  call    cs:__imp_BCryptCreateHash
0x180008233  mov     ebx, eax
0x180008235  test    eax, eax
0x180008237  jns     short loc_180008277
0x180008239  mov     rcx, cs:WPP_GLOBAL_Control
0x180008240  lea     rax, WPP_GLOBAL_Control
0x180008247  cmp     rcx, rax
0x18000824a  jz      loc_180008344
0x180008250  test    byte ptr [rcx+1Ch], 8
0x180008254  jz      loc_180008344
0x18000825a  mov     edx, 0Eh
0x18000825f  mov     rcx, [rcx+10h]
0x180008263  lea     r8, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids
0x18000826a  mov     r9d, ebx
0x18000826d  call    WPP_SF_D
0x180008272  jmp     loc_180008344
0x180008277  mov     rcx, [rsp+78h+hHash]; hHash
0x18000827c  xor     r9d, r9d; dwFlags
0x18000827f  mov     rdx, rsi; pbInput
0x180008282  lea     r8d, [r9+8]; cbInput
0x180008286  call    cs:__imp_BCryptHashData
0x18000828c  mov     ebx, eax
0x18000828e  test    eax, eax
0x180008290  jns     short loc_1800082BA
0x180008292  mov     rcx, cs:WPP_GLOBAL_Control
0x180008299  lea     rax, WPP_GLOBAL_Control
0x1800082a0  cmp     rcx, rax
0x1800082a3  jz      loc_180008344
0x1800082a9  test    byte ptr [rcx+1Ch], 8
0x1800082ad  jz      loc_180008344
0x1800082b3  mov     edx, 0Fh
0x1800082b8  jmp     short loc_18000825F
0x1800082ba  mov     rcx, [rsp+78h+hHash]; hHash
0x1800082bf  xor     r9d, r9d; dwFlags
0x1800082c2  mov     rdx, rbp; pbInput
0x1800082c5  lea     r8d, [r9+8]; cbInput
0x1800082c9  call    cs:__imp_BCryptHashData
0x1800082cf  mov     ebx, eax
0x1800082d1  test    eax, eax
0x1800082d3  jns     short loc_1800082F8
0x1800082d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082dc  lea     rax, WPP_GLOBAL_Control
0x1800082e3  cmp     rcx, rax
0x1800082e6  jz      short loc_180008344
0x1800082e8  test    byte ptr [rcx+1Ch], 8
0x1800082ec  jz      short loc_180008344
0x1800082ee  mov     edx, 10h
0x1800082f3  jmp     loc_18000825F
0x1800082f8  mov     rcx, [rsp+78h+hHash]; hHash
0x1800082fd  xor     r9d, r9d; dwFlags
0x180008300  mov     rdx, rdi; pbOutput
0x180008303  lea     r8d, [r9+10h]; cbOutput
0x180008307  call    cs:__imp_BCryptFinishHash
0x18000830d  mov     ebx, eax
0x18000830f  test    eax, eax
0x180008311  jns     short loc_180008336
0x180008313  mov     rcx, cs:WPP_GLOBAL_Control
0x18000831a  lea     rax, WPP_GLOBAL_Control
0x180008321  cmp     rcx, rax
0x180008324  jz      short loc_180008344
0x180008326  test    byte ptr [rcx+1Ch], 8
0x18000832a  jz      short loc_180008344
0x18000832c  mov     edx, 11h
0x180008331  jmp     loc_18000825F
0x180008336  mov     rax, [rsp+78h+arg_20]
0x18000833e  mov     rcx, [rdi]
0x180008341  mov     [rax], rcx
0x180008344  mov     rcx, [rsp+78h+hHash]; hHash
0x180008349  test    rcx, rcx
0x18000834c  jz      short loc_180008354
0x18000834e  call    cs:__imp_BCryptDestroyHash
0x180008354  mov     eax, ebx
0x180008356  add     rsp, 58h
0x18000835a  pop     rdi
0x18000835b  pop     rsi
0x18000835c  pop     rbp
0x18000835d  pop     rbx
0x18000835e  retn
```
