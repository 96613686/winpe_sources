# FwFieldParserCertCriteriaEku(ushort const *,_tag_FW_CERT_CRITERIA *)

- ea: `0x180036400`
- end: `0x1800365c1`
- name: `?FwFieldParserCertCriteriaEku@@YAJPEBGPEAU_tag_FW_CERT_CRITERIA@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_CERT_CRITERIA *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x180036400`

## import_xrefs

- `fwbase!FwStringCopyWtoAAlloc` at `0x18003650e`
- `fwbase!FwStringCopyWtoAAlloc` at `0x18003650e`
- `fwbase!FwFree` at `0x180036555`
- `fwbase!FwFree` at `0x180036564`
- `fwbase!FwFree` at `0x180036588`
- `fwbase!FwFree` at `0x180036598`
- `fwbase!FwFree` at `0x180036555`
- `fwbase!FwFree` at `0x180036564`
- `fwbase!FwFree` at `0x180036588`
- `fwbase!FwFree` at `0x180036598`
- `fwbase!FwAlloc` at `0x180036487`
- `fwbase!FwAlloc` at `0x180036487`
- `fwbase!FwStringCopyA` at `0x1800364d4`
- `fwbase!FwStringCopyA` at `0x1800364d4`

## pseudocode

```c
__int64 __fastcall FwFieldParserCertCriteriaEku(const unsigned __int16 *a1, struct _tag_FW_CERT_CRITERIA *a2)
{
  int v4; // ebx
  LPCOLESTR v5; // rcx
  __int64 v6; // rdx
  int v7; // esi
  unsigned int v8; // esi
  __int64 v9; // r14
  __int64 i; // rbp
  LPCOLESTR v11; // rcx
  __int64 v12; // rdx
  __int64 j; // rdi
  __int64 v14; // rbp
  __int64 v15; // r15
  __int64 v17; // [rsp+20h] [rbp-38h] BYREF

  v17 = 0;
  if ( a1 )
  {
    v7 = *((_DWORD *)a2 + 6);
    if ( !v7 )
      v7 = 0;
    v8 = v7 + 1;
    v9 = FwAlloc(8LL * v8);
    if ( v9 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 6); i = (unsigned int)(i + 1) )
      {
        v4 = FwStringCopyA(*(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * i), v9 + 8 * i);
        if ( v4 < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v12 = 12;
            goto LABEL_23;
          }
          goto LABEL_24;
        }
      }
      v4 = FwStringCopyWtoAAlloc(a1, 0, &v17);
      if ( v4 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 13;
LABEL_23:
          WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids, (unsigned int)v4);
        }
LABEL_24:
        for ( j = 0; (unsigned int)j < v8; j = (unsigned int)(j + 1) )
          FwFree(*(_QWORD *)(v9 + 8 * j));
        FwFree(v9);
        return (unsigned int)v4;
      }
      *(_QWORD *)(v9 + 8 * i) = v17;
      v14 = 0;
      v15 = *((_QWORD *)a2 + 4);
      for ( *((_QWORD *)a2 + 4) = v9; (unsigned int)v14 < *((_DWORD *)a2 + 6); v14 = (unsigned int)(v14 + 1) )
        FwFree(*(_QWORD *)(v15 + 8 * v14));
      FwFree(v15);
      *((_DWORD *)a2 + 6) = v8;
    }
    else
    {
      v4 = -2147024882;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 11;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = -2147418113;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v6 = 10;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids, (unsigned int)v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180036400  mov     [rsp+arg_10], rbx
0x180036405  push    rbp
0x180036406  push    rsi
0x180036407  push    rdi
0x180036408  push    r14
0x18003640a  push    r15
0x18003640c  sub     rsp, 30h
0x180036410  mov     rax, cs:__security_cookie
0x180036417  xor     rax, rsp
0x18003641a  mov     [rsp+58h+var_30], rax
0x18003641f  mov     [rsp+58h+var_38], 0
0x180036428  mov     rdi, rdx
0x18003642b  mov     r15, rcx
0x18003642e  test    rcx, rcx
0x180036431  jnz     short loc_180036475
0x180036433  mov     ebx, 8000FFFFh
0x180036438  mov     rcx, cs:WPP_GLOBAL_Control
0x18003643f  lea     rax, WPP_GLOBAL_Control
0x180036446  cmp     rcx, rax
0x180036449  jz      loc_1800365A1
0x18003644f  test    byte ptr [rcx+1Ch], 1
0x180036453  jz      loc_1800365A1
0x180036459  lea     edx, [r15+0Ah]
0x18003645d  mov     rcx, [rcx+10h]
0x180036461  lea     r8, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids
0x180036468  mov     r9d, ebx
0x18003646b  call    WPP_SF_d
0x180036470  jmp     loc_1800365A1
0x180036475  mov     esi, [rdx+18h]
0x180036478  xor     eax, eax
0x18003647a  test    esi, esi
0x18003647c  cmovz   esi, eax
0x18003647f  inc     esi
0x180036481  mov     ecx, esi
0x180036483  shl     rcx, 3
0x180036487  call    cs:__imp_FwAlloc
0x18003648d  mov     r14, rax
0x180036490  test    rax, rax
0x180036493  jnz     short loc_1800364C1
0x180036495  mov     ebx, 8007000Eh
0x18003649a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364a1  lea     rax, WPP_GLOBAL_Control
0x1800364a8  cmp     rcx, rax
0x1800364ab  jz      loc_1800365A1
0x1800364b1  test    byte ptr [rcx+1Ch], 1
0x1800364b5  jz      loc_1800365A1
0x1800364bb  lea     edx, [r14+0Bh]
0x1800364bf  jmp     short loc_18003645D
0x1800364c1  xor     ebp, ebp
0x1800364c3  cmp     ebp, [rdi+18h]
0x1800364c6  jnb     short loc_180036504
0x1800364c8  mov     rcx, [rdi+20h]
0x1800364cc  lea     rdx, [r14+rbp*8]
0x1800364d0  mov     rcx, [rcx+rbp*8]
0x1800364d4  call    cs:__imp_FwStringCopyA
0x1800364da  mov     ebx, eax
0x1800364dc  test    eax, eax
0x1800364de  js      short loc_1800364E4
0x1800364e0  inc     ebp
0x1800364e2  jmp     short loc_1800364C3
0x1800364e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364eb  lea     rax, WPP_GLOBAL_Control
0x1800364f2  cmp     rcx, rax
0x1800364f5  jz      short loc_18003654B
0x1800364f7  test    byte ptr [rcx+1Ch], 1
0x1800364fb  jz      short loc_18003654B
0x1800364fd  mov     edx, 0Ch
0x180036502  jmp     short loc_180036538
0x180036504  lea     r8, [rsp+58h+var_38]
0x180036509  xor     edx, edx
0x18003650b  mov     rcx, r15
0x18003650e  call    cs:__imp_FwStringCopyWtoAAlloc
0x180036514  mov     ebx, eax
0x180036516  test    eax, eax
0x180036518  jns     short loc_18003656C
0x18003651a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036521  lea     rax, WPP_GLOBAL_Control
0x180036528  cmp     rcx, rax
0x18003652b  jz      short loc_18003654B
0x18003652d  test    byte ptr [rcx+1Ch], 1
0x180036531  jz      short loc_18003654B
0x180036533  mov     edx, 0Dh
0x180036538  mov     rcx, [rcx+10h]
0x18003653c  lea     r8, WPP_f20136b4c9eb33c7c75d2ebfaec1363c_Traceguids
0x180036543  mov     r9d, ebx
0x180036546  call    WPP_SF_d
0x18003654b  xor     edi, edi
0x18003654d  test    esi, esi
0x18003654f  jz      short loc_180036561
0x180036551  mov     rcx, [r14+rdi*8]
0x180036555  call    cs:__imp_FwFree
0x18003655b  inc     edi
0x18003655d  cmp     edi, esi
0x18003655f  jb      short loc_180036551
0x180036561  mov     rcx, r14
0x180036564  call    cs:__imp_FwFree
0x18003656a  jmp     short loc_1800365A1
0x18003656c  mov     rax, [rsp+58h+var_38]
0x180036571  mov     [r14+rbp*8], rax
0x180036575  xor     ebp, ebp
0x180036577  mov     r15, [rdi+20h]
0x18003657b  mov     [rdi+20h], r14
0x18003657f  cmp     [rdi+18h], ebp
0x180036582  jbe     short loc_180036595
0x180036584  mov     rcx, [r15+rbp*8]
0x180036588  call    cs:__imp_FwFree
0x18003658e  inc     ebp
0x180036590  cmp     ebp, [rdi+18h]
0x180036593  jb      short loc_180036584
0x180036595  mov     rcx, r15
0x180036598  call    cs:__imp_FwFree
0x18003659e  mov     [rdi+18h], esi
0x1800365a1  mov     eax, ebx
0x1800365a3  mov     rcx, [rsp+58h+var_30]
0x1800365a8  xor     rcx, rsp; StackCookie
0x1800365ab  call    __security_check_cookie
0x1800365b0  mov     rbx, [rsp+58h+arg_10]
0x1800365b5  add     rsp, 30h
0x1800365b9  pop     r15
0x1800365bb  pop     r14
0x1800365bd  pop     rdi
0x1800365be  pop     rsi
0x1800365bf  pop     rbp
0x1800365c0  retn
```
