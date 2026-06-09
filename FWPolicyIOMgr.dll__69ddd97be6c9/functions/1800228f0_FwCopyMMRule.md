# FwCopyMMRule

- ea: `0x1800228f0`
- end: `0x180022c95`
- name: `FwCopyMMRule`
- size: `933`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800042c4`
- `0x1800088a0`
- `0x18001e2c0`
- `0x18001ffd4`
- `0x1800228f0`

## import_xrefs

- `fwbase!FwAlloc` at `0x180022913`
- `fwbase!FwAlloc` at `0x180022913`
- `fwbase!FwArrayCopy` at `0x1800229ab`
- `fwbase!FwArrayCopy` at `0x1800229ab`
- `fwbase!FwStringCopy` at `0x180022a6f`
- `fwbase!FwStringCopy` at `0x180022ab1`
- `fwbase!FwStringCopy` at `0x180022af9`
- `fwbase!FwStringCopy` at `0x180022b41`
- `fwbase!FwStringCopy` at `0x180022b89`
- `fwbase!FwStringCopy` at `0x180022bd1`
- `fwbase!FwStringCopy` at `0x180022c26`
- `fwbase!FwStringCopy` at `0x180022a6f`
- `fwbase!FwStringCopy` at `0x180022ab1`
- `fwbase!FwStringCopy` at `0x180022af9`
- `fwbase!FwStringCopy` at `0x180022b41`
- `fwbase!FwStringCopy` at `0x180022b89`
- `fwbase!FwStringCopy` at `0x180022bd1`
- `fwbase!FwStringCopy` at `0x180022c26`

## pseudocode

```c
__int64 __fastcall FwCopyMMRule(__int64 a1, void **a2)
{
  void *v4; // rax
  int v5; // ebx
  LPCOLESTR v6; // rcx
  __int64 v7; // rdx

  *a2 = 0;
  v4 = (void *)FwAlloc(272);
  *a2 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x110u);
    *((_WORD *)*a2 + 4) = *(_WORD *)(a1 + 8);
    *((_WORD *)*a2 + 104) = *(_WORD *)(a1 + 208);
    *((_DWORD *)*a2 + 10) = *(_DWORD *)(a1 + 40);
    v5 = FwArrayCopy(
           4,
           FwCopyPlatform,
           wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
           a1 + 224,
           (char *)*a2 + 224);
    if ( v5 >= 0 )
    {
      v5 = FwCopyWFAddressesContents(a1 + 48, (char *)*a2 + 48);
      if ( v5 >= 0 )
      {
        v5 = FwCopyWFAddressesContents(a1 + 120, (char *)*a2 + 120);
        if ( v5 >= 0 )
        {
          v5 = FwStringCopy(*(_QWORD *)(a1 + 24), (char *)*a2 + 24);
          if ( v5 >= 0 )
          {
            v5 = FwStringCopy(*(_QWORD *)(a1 + 32), (char *)*a2 + 32);
            if ( v5 >= 0 )
            {
              v5 = FwStringCopy(*(_QWORD *)(a1 + 216), (char *)*a2 + 216);
              if ( v5 >= 0 )
              {
                v5 = FwStringCopy(*(_QWORD *)(a1 + 192), (char *)*a2 + 192);
                if ( v5 >= 0 )
                {
                  v5 = FwStringCopy(*(_QWORD *)(a1 + 200), (char *)*a2 + 200);
                  if ( v5 >= 0 )
                  {
                    v5 = FwStringCopy(*(_QWORD *)(a1 + 248), (char *)*a2 + 248);
                    if ( v5 >= 0 )
                    {
                      *((_DWORD *)*a2 + 64) = *(_DWORD *)(a1 + 256);
                      *((_DWORD *)*a2 + 60) = *(_DWORD *)(a1 + 240);
                      v5 = FwStringCopy(*(_QWORD *)(a1 + 16), (char *)*a2 + 16);
                      if ( v5 >= 0 )
                      {
                        *(_QWORD *)*a2 = 0;
                        return (unsigned int)v5;
                      }
                      v6 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                      {
                        v7 = 92;
                        goto LABEL_45;
                      }
                    }
                    else
                    {
                      v6 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                      {
                        v7 = 91;
                        goto LABEL_45;
                      }
                    }
                  }
                  else
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                    {
                      v7 = 90;
                      goto LABEL_45;
                    }
                  }
                }
                else
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v7 = 89;
                    goto LABEL_45;
                  }
                }
              }
              else
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v7 = 88;
                  goto LABEL_45;
                }
              }
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v7 = 87;
                goto LABEL_45;
              }
            }
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v7 = 86;
              goto LABEL_45;
            }
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v7 = 85;
            goto LABEL_45;
          }
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v7 = 84;
          goto LABEL_45;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v7 = 83;
        goto LABEL_45;
      }
    }
  }
  else
  {
    v5 = -2147024882;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 82;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v5);
    }
  }
  if ( *a2 )
  {
    FwMMRuleFree(*a2);
    *a2 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800228f0  mov     [rsp+arg_0], rbx
0x1800228f5  mov     [rsp+arg_8], rsi
0x1800228fa  push    rdi
0x1800228fb  sub     rsp, 30h
0x1800228ff  mov     rsi, rcx
0x180022902  mov     qword ptr [rdx], 0
0x180022909  mov     ebx, 110h
0x18002290e  mov     rdi, rdx
0x180022911  mov     ecx, ebx
0x180022913  call    cs:__imp_FwAlloc
0x180022919  mov     [rdi], rax
0x18002291c  test    rax, rax
0x18002291f  jnz     short loc_180022951
0x180022921  mov     ebx, 8007000Eh
0x180022926  mov     rcx, cs:WPP_GLOBAL_Control
0x18002292d  lea     rax, WPP_GLOBAL_Control
0x180022934  cmp     rcx, rax
0x180022937  jz      loc_180022C63
0x18002293d  test    byte ptr [rcx+1Ch], 1
0x180022941  jz      loc_180022C63
0x180022947  mov     edx, 52h ; 'R'
0x18002294c  jmp     loc_180022C50
0x180022951  mov     r8, rbx; Size
0x180022954  xor     edx, edx; Val
0x180022956  mov     rcx, rax; void *
0x180022959  call    memset_0
0x18002295e  movzx   eax, word ptr [rsi+8]
0x180022962  lea     r9, [rsi+0E0h]
0x180022969  mov     rcx, [rdi]
0x18002296c  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180022973  lea     rdx, FwCopyPlatform
0x18002297a  mov     [rcx+8], ax
0x18002297e  movzx   eax, word ptr [rsi+0D0h]
0x180022985  mov     rcx, [rdi]
0x180022988  mov     [rcx+0D0h], ax
0x18002298f  mov     rcx, [rdi]
0x180022992  mov     eax, [rsi+28h]
0x180022995  mov     [rcx+28h], eax
0x180022998  mov     ecx, 4
0x18002299d  mov     rax, [rdi]
0x1800229a0  add     rax, 0E0h
0x1800229a6  mov     [rsp+38h+var_18], rax
0x1800229ab  call    cs:__imp_FwArrayCopy
0x1800229b1  mov     ebx, eax
0x1800229b3  test    eax, eax
0x1800229b5  jns     short loc_1800229E2
0x1800229b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229be  lea     rax, WPP_GLOBAL_Control
0x1800229c5  cmp     rcx, rax
0x1800229c8  jz      loc_180022C63
0x1800229ce  test    byte ptr [rcx+1Ch], 1
0x1800229d2  jz      loc_180022C63
0x1800229d8  mov     edx, 53h ; 'S'
0x1800229dd  jmp     loc_180022C50
0x1800229e2  mov     rdx, [rdi]
0x1800229e5  lea     rcx, [rsi+30h]
0x1800229e9  add     rdx, 30h ; '0'
0x1800229ed  call    FwCopyWFAddressesContents
0x1800229f2  mov     ebx, eax
0x1800229f4  test    eax, eax
0x1800229f6  jns     short loc_180022A23
0x1800229f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229ff  lea     rax, WPP_GLOBAL_Control
0x180022a06  cmp     rcx, rax
0x180022a09  jz      loc_180022C63
0x180022a0f  test    byte ptr [rcx+1Ch], 1
0x180022a13  jz      loc_180022C63
0x180022a19  mov     edx, 54h ; 'T'
0x180022a1e  jmp     loc_180022C50
0x180022a23  mov     rdx, [rdi]
0x180022a26  lea     rcx, [rsi+78h]
0x180022a2a  add     rdx, 78h ; 'x'
0x180022a2e  call    FwCopyWFAddressesContents
0x180022a33  mov     ebx, eax
0x180022a35  test    eax, eax
0x180022a37  jns     short loc_180022A64
0x180022a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a40  lea     rax, WPP_GLOBAL_Control
0x180022a47  cmp     rcx, rax
0x180022a4a  jz      loc_180022C63
0x180022a50  test    byte ptr [rcx+1Ch], 1
0x180022a54  jz      loc_180022C63
0x180022a5a  mov     edx, 55h ; 'U'
0x180022a5f  jmp     loc_180022C50
0x180022a64  mov     rdx, [rdi]
0x180022a67  mov     rcx, [rsi+18h]
0x180022a6b  add     rdx, 18h
0x180022a6f  call    cs:__imp_FwStringCopy
0x180022a75  mov     ebx, eax
0x180022a77  test    eax, eax
0x180022a79  jns     short loc_180022AA6
0x180022a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a82  lea     rax, WPP_GLOBAL_Control
0x180022a89  cmp     rcx, rax
0x180022a8c  jz      loc_180022C63
0x180022a92  test    byte ptr [rcx+1Ch], 1
0x180022a96  jz      loc_180022C63
0x180022a9c  mov     edx, 56h ; 'V'
0x180022aa1  jmp     loc_180022C50
0x180022aa6  mov     rdx, [rdi]
0x180022aa9  mov     rcx, [rsi+20h]
0x180022aad  add     rdx, 20h ; ' '
0x180022ab1  call    cs:__imp_FwStringCopy
0x180022ab7  mov     ebx, eax
0x180022ab9  test    eax, eax
0x180022abb  jns     short loc_180022AE8
0x180022abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ac4  lea     rax, WPP_GLOBAL_Control
0x180022acb  cmp     rcx, rax
0x180022ace  jz      loc_180022C63
0x180022ad4  test    byte ptr [rcx+1Ch], 1
0x180022ad8  jz      loc_180022C63
0x180022ade  mov     edx, 57h ; 'W'
0x180022ae3  jmp     loc_180022C50
0x180022ae8  mov     rdx, [rdi]
0x180022aeb  mov     rcx, [rsi+0D8h]
0x180022af2  add     rdx, 0D8h
0x180022af9  call    cs:__imp_FwStringCopy
0x180022aff  mov     ebx, eax
0x180022b01  test    eax, eax
0x180022b03  jns     short loc_180022B30
0x180022b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b0c  lea     rax, WPP_GLOBAL_Control
0x180022b13  cmp     rcx, rax
0x180022b16  jz      loc_180022C63
0x180022b1c  test    byte ptr [rcx+1Ch], 1
0x180022b20  jz      loc_180022C63
0x180022b26  mov     edx, 58h ; 'X'
0x180022b2b  jmp     loc_180022C50
0x180022b30  mov     rdx, [rdi]
0x180022b33  mov     rcx, [rsi+0C0h]
0x180022b3a  add     rdx, 0C0h
0x180022b41  call    cs:__imp_FwStringCopy
0x180022b47  mov     ebx, eax
0x180022b49  test    eax, eax
0x180022b4b  jns     short loc_180022B78
0x180022b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b54  lea     rax, WPP_GLOBAL_Control
0x180022b5b  cmp     rcx, rax
0x180022b5e  jz      loc_180022C63
0x180022b64  test    byte ptr [rcx+1Ch], 1
0x180022b68  jz      loc_180022C63
0x180022b6e  mov     edx, 59h ; 'Y'
0x180022b73  jmp     loc_180022C50
0x180022b78  mov     rdx, [rdi]
0x180022b7b  mov     rcx, [rsi+0C8h]
0x180022b82  add     rdx, 0C8h
0x180022b89  call    cs:__imp_FwStringCopy
0x180022b8f  mov     ebx, eax
0x180022b91  test    eax, eax
0x180022b93  jns     short loc_180022BC0
0x180022b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b9c  lea     rax, WPP_GLOBAL_Control
0x180022ba3  cmp     rcx, rax
0x180022ba6  jz      loc_180022C63
0x180022bac  test    byte ptr [rcx+1Ch], 1
0x180022bb0  jz      loc_180022C63
0x180022bb6  mov     edx, 5Ah ; 'Z'
0x180022bbb  jmp     loc_180022C50
0x180022bc0  mov     rdx, [rdi]
0x180022bc3  mov     rcx, [rsi+0F8h]
0x180022bca  add     rdx, 0F8h
0x180022bd1  call    cs:__imp_FwStringCopy
0x180022bd7  mov     ebx, eax
0x180022bd9  test    eax, eax
0x180022bdb  jns     short loc_180022BFD
0x180022bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022be4  lea     rax, WPP_GLOBAL_Control
0x180022beb  cmp     rcx, rax
0x180022bee  jz      short loc_180022C63
0x180022bf0  test    byte ptr [rcx+1Ch], 1
0x180022bf4  jz      short loc_180022C63
0x180022bf6  mov     edx, 5Bh ; '['
0x180022bfb  jmp     short loc_180022C50
0x180022bfd  mov     rcx, [rdi]
0x180022c00  mov     eax, [rsi+100h]
0x180022c06  mov     [rcx+100h], eax
0x180022c0c  mov     rcx, [rdi]
0x180022c0f  mov     eax, [rsi+0F0h]
0x180022c15  mov     [rcx+0F0h], eax
0x180022c1b  mov     rdx, [rdi]
0x180022c1e  mov     rcx, [rsi+10h]
0x180022c22  add     rdx, 10h
0x180022c26  call    cs:__imp_FwStringCopy
0x180022c2c  mov     ebx, eax
0x180022c2e  test    eax, eax
0x180022c30  jns     short loc_180022C79
0x180022c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c39  lea     rax, WPP_GLOBAL_Control
0x180022c40  cmp     rcx, rax
0x180022c43  jz      short loc_180022C63
0x180022c45  test    byte ptr [rcx+1Ch], 1
0x180022c49  jz      short loc_180022C63
0x180022c4b  mov     edx, 5Ch ; '\'
0x180022c50  mov     rcx, [rcx+10h]
0x180022c54  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180022c5b  mov     r9d, ebx
0x180022c5e  call    WPP_SF_d
0x180022c63  mov     rcx, [rdi]; void *
0x180022c66  test    rcx, rcx
0x180022c69  jz      short loc_180022C83
0x180022c6b  call    FwMMRuleFree
0x180022c70  mov     qword ptr [rdi], 0
0x180022c77  jmp     short loc_180022C83
0x180022c79  mov     rax, [rdi]
0x180022c7c  mov     qword ptr [rax], 0
0x180022c83  mov     rsi, [rsp+38h+arg_8]
0x180022c88  mov     eax, ebx
0x180022c8a  mov     rbx, [rsp+38h+arg_0]
0x180022c8f  add     rsp, 30h
0x180022c93  pop     rdi
0x180022c94  retn
```
