# FwDecodeHyperVVMCreator(ushort const *,ushort *,_tag_FW_HYPERV_VM_CREATOR0 *)

- ea: `0x180037268`
- end: `0x1800374d8`
- name: `?FwDecodeHyperVVMCreator@@YAJPEBGPEAGPEAU_tag_FW_HYPERV_VM_CREATOR0@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, unsigned __int16 *, struct _tag_FW_HYPERV_VM_CREATOR0 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018614`

## callees

- `0x1800042c4`
- `0x18001f650`
- `0x180031878`
- `0x180037268`
- `0x1800374e0`
- `0x180037658`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800372e0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800372e0`

## pseudocode

```c
__int64 __fastcall FwDecodeHyperVVMCreator(LPCOLESTR lpsz, unsigned __int16 *a2, struct _tag_FW_HYPERV_VM_CREATOR0 *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  LPCOLESTR v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  unsigned __int16 v12; // r14
  unsigned int v13; // esi
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v17; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-18h] BYREF

  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_595a4ed7f1c63ca1a8b677253b30b74f_Traceguids,
      (_DWORD)lpsz,
      (__int64)a2);
  v6 = CLSIDFromString(lpsz, (LPCLSID)((char *)a3 + 12));
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v9 = 21;
LABEL_8:
      v10 = (unsigned int)v6;
LABEL_44:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_595a4ed7f1c63ca1a8b677253b30b74f_Traceguids, v10);
      return v7;
    }
    return v7;
  }
  if ( ((*a2 - 86) & 0xFFDF) != 0 )
    goto LABEL_10;
  v11 = FwHyperVVMCreatorDecodeVersionField(a2 + 1, &v17, &v18, &v19);
  v7 = v11;
  if ( v11 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_18;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_595a4ed7f1c63ca1a8b677253b30b74f_Traceguids,
      (unsigned int)v11);
LABEL_17:
    v8 = WPP_GLOBAL_Control;
LABEL_18:
    if ( (v7 & 0x80000000) == 0 )
    {
      v12 = (unsigned __int8)v18 | ((unsigned __int8)v17 << 8);
      if ( v12 >= 0x220u )
      {
        v13 = 0;
        *((_WORD *)a3 + 4) = v12;
        v14 = 0;
        while ( v19[v13] )
        {
          if ( v19[v13] == 124 )
          {
            if ( v13 <= (unsigned int)v14 )
            {
              v10 = 2147549183LL;
              v7 = -2147418113;
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v9 = 24;
                goto LABEL_44;
              }
              return v7;
            }
            v19[v13] = 0;
            v15 = FwHyperVVMCreatorParseField(v12, &v19[v14], a3);
            v7 = v15;
            if ( v15 < 0 )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v9 = 25;
                v10 = (unsigned int)v15;
                goto LABEL_44;
              }
              return v7;
            }
            v14 = ++v13;
          }
          else
          {
            ++v13;
          }
        }
        if ( v13 != (_DWORD)v14 )
        {
          v10 = 2147549183LL;
          v7 = -2147418113;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v9 = 26;
            goto LABEL_44;
          }
        }
      }
      else
      {
        v10 = 2147549183LL;
        v7 = -2147418113;
        if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
        {
          v9 = 23;
          goto LABEL_44;
        }
      }
      return v7;
    }
    v6 = v7;
    goto LABEL_20;
  }
  if ( *v19 == 124 )
  {
    ++v19;
    goto LABEL_17;
  }
LABEL_10:
  v8 = WPP_GLOBAL_Control;
  v6 = -2147418113;
  v7 = -2147418113;
LABEL_20:
  if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
  {
    v9 = 22;
    goto LABEL_8;
  }
  return v7;
}

```

## disassembly

```asm
0x180037268  push    rbp
0x18003726a  push    rbx
0x18003726b  push    rsi
0x18003726c  push    r12
0x18003726e  push    r13
0x180037270  push    r14
0x180037272  push    r15
0x180037274  mov     rbp, rsp
0x180037277  sub     rsp, 50h
0x18003727b  mov     rax, cs:__security_cookie
0x180037282  xor     rax, rsp
0x180037285  mov     [rbp+var_10], rax
0x180037289  xor     r13d, r13d
0x18003728c  mov     r15, r8
0x18003728f  mov     [rbp+var_20], r13d
0x180037293  mov     rsi, rdx
0x180037296  mov     [rbp+var_1C], r13d
0x18003729a  mov     rbx, rcx
0x18003729d  mov     [rbp+var_18], r13
0x1800372a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372a8  lea     r12, WPP_GLOBAL_Control
0x1800372af  lea     r14, WPP_595a4ed7f1c63ca1a8b677253b30b74f_Traceguids
0x1800372b6  cmp     rcx, r12
0x1800372b9  jz      short loc_1800372D9
0x1800372bb  test    byte ptr [rcx+1Ch], 4
0x1800372bf  jz      short loc_1800372D9
0x1800372c1  mov     rcx, [rcx+10h]
0x1800372c5  lea     edx, [r13+14h]
0x1800372c9  mov     r9, rbx
0x1800372cc  mov     [rsp+50h+var_30], rsi
0x1800372d1  mov     r8, r14
0x1800372d4  call    WPP_SF_SS
0x1800372d9  lea     rdx, [r15+0Ch]; pclsid
0x1800372dd  mov     rcx, rbx; lpsz
0x1800372e0  call    cs:__imp_CLSIDFromString
0x1800372e6  mov     ebx, eax
0x1800372e8  test    eax, eax
0x1800372ea  jns     short loc_180037316
0x1800372ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372f3  cmp     rcx, r12
0x1800372f6  jz      loc_1800374BA
0x1800372fc  test    byte ptr [rcx+1Ch], 1
0x180037300  jz      loc_1800374BA
0x180037306  mov     edx, 15h
0x18003730b  mov     r9d, eax
0x18003730e  mov     r8, r14
0x180037311  jmp     loc_1800374B1
0x180037316  movzx   eax, word ptr [rsi]
0x180037319  mov     ecx, 0FFDFh
0x18003731e  sub     ax, 56h ; 'V'
0x180037322  test    cx, ax
0x180037325  jz      short loc_18003733C
0x180037327  mov     rcx, cs:WPP_GLOBAL_Control
0x18003732e  mov     r9d, 8000FFFFh
0x180037334  mov     eax, r9d
0x180037337  mov     ebx, r9d
0x18003733a  jmp     short loc_18003739B
0x18003733c  lea     rcx, [rsi+2]; unsigned __int16 *
0x180037340  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180037344  lea     r8, [rbp+var_1C]; unsigned int *
0x180037348  lea     rdx, [rbp+var_20]; unsigned int *
0x18003734c  call    ?FwHyperVVMCreatorDecodeVersionField@@YAJPEBGPEAK1PEAPEAG@Z; FwHyperVVMCreatorDecodeVersionField(ushort const *,ulong *,ulong *,ushort * *)
0x180037351  mov     ebx, eax
0x180037353  test    eax, eax
0x180037355  jns     short loc_18003737F
0x180037357  mov     rcx, cs:WPP_GLOBAL_Control
0x18003735e  cmp     rcx, r12
0x180037361  jz      short loc_180037395
0x180037363  test    byte ptr [rcx+1Ch], 1
0x180037367  jz      short loc_180037395
0x180037369  mov     rcx, [rcx+10h]
0x18003736d  mov     edx, 13h
0x180037372  mov     r9d, eax
0x180037375  mov     r8, r14
0x180037378  call    WPP_SF_d
0x18003737d  jmp     short loc_18003738E
0x18003737f  mov     rax, [rbp+var_18]
0x180037383  cmp     word ptr [rax], 7Ch ; '|'
0x180037387  jnz     short loc_180037327
0x180037389  add     [rbp+var_18], 2
0x18003738e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037395  test    ebx, ebx
0x180037397  jns     short loc_1800373B8
0x180037399  mov     eax, ebx
0x18003739b  cmp     rcx, r12
0x18003739e  jz      loc_1800374BA
0x1800373a4  test    byte ptr [rcx+1Ch], 1
0x1800373a8  jz      loc_1800374BA
0x1800373ae  mov     edx, 16h
0x1800373b3  jmp     loc_18003730B
0x1800373b8  movzx   eax, byte ptr [rbp+var_1C]
0x1800373bc  movzx   r14d, byte ptr [rbp+var_20]
0x1800373c1  shl     r14w, 8
0x1800373c6  or      r14w, ax
0x1800373ca  mov     eax, 220h
0x1800373cf  cmp     r14w, ax
0x1800373d3  jnb     short loc_1800373FB
0x1800373d5  mov     r9d, 8000FFFFh
0x1800373db  mov     ebx, r9d
0x1800373de  cmp     rcx, r12
0x1800373e1  jz      loc_1800374BA
0x1800373e7  test    byte ptr [rcx+1Ch], 1
0x1800373eb  jz      loc_1800374BA
0x1800373f1  mov     edx, 17h
0x1800373f6  jmp     loc_1800374AA
0x1800373fb  mov     esi, r13d
0x1800373fe  mov     [r15+8], r14w
0x180037403  mov     ecx, r13d
0x180037406  mov     r8, [rbp+var_18]
0x18003740a  mov     edx, esi
0x18003740c  cmp     [r8+rdx*2], r13w
0x180037411  jz      short loc_180037486
0x180037413  cmp     word ptr [r8+rdx*2], 7Ch ; '|'
0x180037419  jnz     short loc_180037444
0x18003741b  cmp     esi, ecx
0x18003741d  jbe     short loc_180037464
0x18003741f  mov     [r8+rdx*2], r13w
0x180037424  mov     r8, r15; struct _tag_FW_HYPERV_VM_CREATOR0 *
0x180037427  mov     rax, [rbp+var_18]
0x18003742b  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18003742f  movzx   ecx, r14w; unsigned __int16
0x180037433  call    ?FwHyperVVMCreatorParseField@@YAJGPEBGPEAU_tag_FW_HYPERV_VM_CREATOR0@@@Z; FwHyperVVMCreatorParseField(ushort,ushort const *,_tag_FW_HYPERV_VM_CREATOR0 *)
0x180037438  mov     ebx, eax
0x18003743a  test    eax, eax
0x18003743c  js      short loc_180037448
0x18003743e  inc     esi
0x180037440  mov     ecx, esi
0x180037442  jmp     short loc_180037406
0x180037444  inc     esi
0x180037446  jmp     short loc_180037406
0x180037448  mov     rcx, cs:WPP_GLOBAL_Control
0x18003744f  cmp     rcx, r12
0x180037452  jz      short loc_1800374BA
0x180037454  test    byte ptr [rcx+1Ch], 1
0x180037458  jz      short loc_1800374BA
0x18003745a  mov     edx, 19h
0x18003745f  mov     r9d, eax
0x180037462  jmp     short loc_1800374AA
0x180037464  mov     r9d, 8000FFFFh
0x18003746a  mov     ebx, r9d
0x18003746d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037474  cmp     rcx, r12
0x180037477  jz      short loc_1800374BA
0x180037479  test    byte ptr [rcx+1Ch], 1
0x18003747d  jz      short loc_1800374BA
0x18003747f  mov     edx, 18h
0x180037484  jmp     short loc_1800374AA
0x180037486  cmp     esi, ecx
0x180037488  jz      short loc_1800374BA
0x18003748a  mov     r9d, 8000FFFFh
0x180037490  mov     ebx, r9d
0x180037493  mov     rcx, cs:WPP_GLOBAL_Control
0x18003749a  cmp     rcx, r12
0x18003749d  jz      short loc_1800374BA
0x18003749f  test    byte ptr [rcx+1Ch], 1
0x1800374a3  jz      short loc_1800374BA
0x1800374a5  mov     edx, 1Ah
0x1800374aa  lea     r8, WPP_595a4ed7f1c63ca1a8b677253b30b74f_Traceguids
0x1800374b1  mov     rcx, [rcx+10h]
0x1800374b5  call    WPP_SF_d
0x1800374ba  mov     eax, ebx
0x1800374bc  mov     rcx, [rbp+var_10]
0x1800374c0  xor     rcx, rsp; StackCookie
0x1800374c3  call    __security_check_cookie
0x1800374c8  add     rsp, 50h
0x1800374cc  pop     r15
0x1800374ce  pop     r14
0x1800374d0  pop     r13
0x1800374d2  pop     r12
0x1800374d4  pop     rsi
0x1800374d5  pop     rbx
0x1800374d6  pop     rbp
0x1800374d7  retn
```
