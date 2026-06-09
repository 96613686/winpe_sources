# std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(char const *,char const *)

- ea: `0x1832c94c0`
- end: `0x1832c9798`
- name: `?from_bytes@?$wstring_convert@V?$codecvt_utf8@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@PEBD0@Z`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1832c9480`

## callees

- `0x182da9d20`
- `0x182fd89d0`
- `0x1832c4780`
- `0x1832c89f0`
- `0x1832c8b50`
- `0x1832c94c0`
- `0x1832ce3b0`
- `0x1832dbe96`

## import_xrefs

- `MSVCP140!?in@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEA_W3AEAPEA_W@Z` at `0x1832c95a0`
- `MSVCP140!?in@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEA_W3AEAPEA_W@Z` at `0x1832c95a0`
- `VCRUNTIME140!memmove` at `0x1832c9727`
- `VCRUNTIME140!memmove` at `0x1832c9727`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 i; // rdx
  void **v9; // rsi
  int v10; // eax
  _WORD *v11; // rax
  _WORD *v12; // rax
  unsigned __int64 v13; // rcx
  int v15; // [rsp+40h] [rbp-69h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v17; // [rsp+60h] [rbp-49h]
  __int64 v18; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int64 v19; // [rsp+70h] [rbp-39h] BYREF
  _QWORD Src[2]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v21; // [rsp+88h] [rbp-21h]
  unsigned __int64 v22; // [rsp+90h] [rbp-19h]
  void *v23[2]; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v24; // [rsp+A8h] [rbp-1h]
  unsigned __int64 v25; // [rsp+B0h] [rbp+7h]

  v17 = -2;
  v18 = a3;
  v15 = 0;
  v25 = 7;
  v24 = 0;
  LOWORD(v23[0]) = 0;
  v22 = 7;
  v21 = 0;
  LOWORD(Src[0]) = 0;
  if ( !*(_BYTE *)(a1 + 104) )
    *(_QWORD *)(a1 + 96) = 0;
  std::wstring::append(v23, 8);
  *(_QWORD *)(a1 + 112) = 0;
  i = v18;
  if ( v18 == a4 )
  {
LABEL_28:
    a2[3] = 7;
    a2[2] = 0;
    if ( a2[3] < 8u )
      v12 = a2;
    else
      v12 = (_WORD *)*a2;
    *v12 = 0;
    v13 = v22;
    if ( v22 >= 8 )
    {
      *a2 = Src[0];
      Src[0] = 0;
    }
    else if ( v21 != -1 )
    {
      memmove(a2, Src, 2 * (v21 + 1));
      v13 = v22;
    }
    a2[2] = v21;
    a2[3] = v13;
    goto LABEL_36;
  }
  while ( 1 )
  {
    v9 = v23;
    if ( v25 >= 8 )
      v9 = (void **)v23[0];
    v10 = std::codecvt<wchar_t,char,_Mbstatet>::in(
            *(_QWORD *)(a1 + 8),
            a1 + 96,
            i,
            a4,
            &v18,
            v9,
            (char *)v9 + 2 * v24,
            &v19,
            v15);
    if ( v10 < 0 )
    {
LABEL_26:
      if ( !*(_BYTE *)(a1 + 106) )
      {
        std::range_error::range_error((std::range_error *)pExceptionObject, "bad conversion");
        throw (std::range_error *)pExceptionObject;
      }
      goto LABEL_20;
    }
    if ( v10 <= 1 )
      break;
    if ( v10 != 3 )
      goto LABEL_26;
    for ( i = v18; i != a4; v18 = i )
    {
      std::wstring::append(Src, 1);
      i = v18 + 1;
    }
LABEL_17:
    *(_QWORD *)(a1 + 112) = i - a3;
    if ( i == a4 )
      goto LABEL_28;
  }
  if ( (unsigned __int64)v9 < v19 )
  {
    std::wstring::append(Src, v9);
LABEL_16:
    i = v18;
    goto LABEL_17;
  }
  if ( v24 < 0x10 )
  {
    std::wstring::append(v23, 8);
    goto LABEL_16;
  }
  if ( !*(_BYTE *)(a1 + 106) )
  {
    std::range_error::range_error((std::range_error *)pExceptionObject, "bad conversion");
    throw (std::range_error *)pExceptionObject;
  }
LABEL_20:
  a2[3] = 7;
  a2[2] = 0;
  if ( a2[3] < 8u )
    v11 = a2;
  else
    v11 = (_WORD *)*a2;
  *v11 = 0;
  std::wstring::assign(a2);
  if ( v22 >= 8 )
    std::allocator<wchar_t>::deallocate(Src, Src[0], v22 + 1);
LABEL_36:
  v22 = 7;
  v21 = 0;
  LOWORD(Src[0]) = 0;
  if ( v25 >= 8 )
    std::allocator<wchar_t>::deallocate(v23, v23[0], v25 + 1);
  return a2;
}

```

## disassembly

```asm
0x1832c94c0  push    rbp
0x1832c94c2  push    rbx
0x1832c94c3  push    rsi
0x1832c94c4  push    rdi
0x1832c94c5  push    r12
0x1832c94c7  push    r13
0x1832c94c9  push    r14
0x1832c94cb  push    r15
0x1832c94cd  lea     rbp, [rsp-1Fh]
0x1832c94d2  sub     rsp, 0C8h
0x1832c94d9  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1832c94e1  mov     rax, cs:__security_cookie
0x1832c94e8  xor     rax, rsp
0x1832c94eb  mov     [rbp+57h+var_48], rax
0x1832c94ef  mov     rdi, r9
0x1832c94f2  mov     r15, r8
0x1832c94f5  mov     rbx, rdx
0x1832c94f8  mov     r14, rcx
0x1832c94fb  mov     [rbp+57h+var_98], r8
0x1832c94ff  xor     r13d, r13d
0x1832c9502  mov     [rbp+57h+var_C0], r13d
0x1832c9506  mov     [rbp+57h+var_50], 7
0x1832c950e  mov     [rbp+57h+var_58], r13
0x1832c9512  mov     word ptr [rbp+57h+var_68], r13w
0x1832c9517  mov     [rbp+57h+var_70], 7
0x1832c951f  mov     [rbp+57h+var_78], r13
0x1832c9523  mov     word ptr [rbp+57h+Src], r13w
0x1832c9528  cmp     [rcx+68h], r13b
0x1832c952c  jnz     short loc_1832C9534
0x1832c952e  xor     eax, eax
0x1832c9530  mov     [rcx+60h], rax
0x1832c9534  xor     r8d, r8d
0x1832c9537  lea     edx, [r8+8]
0x1832c953b  lea     rcx, [rbp+57h+var_68]
0x1832c953f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1832c9544  mov     [r14+70h], r13
0x1832c9548  mov     rdx, [rbp+57h+var_98]
0x1832c954c  cmp     rdx, rdi
0x1832c954f  jz      loc_1832C96EA
0x1832c9555  nop     word ptr [rax+rax+00000000h]
0x1832c9560  lea     rsi, [rbp+57h+var_68]
0x1832c9564  cmp     [rbp+57h+var_50], 8
0x1832c9569  cmovnb  rsi, [rbp+57h+var_68]
0x1832c956e  mov     rax, [rbp+57h+var_58]
0x1832c9572  lea     rcx, [rsi+rax*2]
0x1832c9576  lea     rax, [rbp+57h+var_90]
0x1832c957a  mov     [rsp+100h+var_C8], rax
0x1832c957f  mov     [rsp+100h+var_D0], rcx
0x1832c9584  mov     [rsp+100h+var_D8], rsi
0x1832c9589  lea     rax, [rbp+57h+var_98]
0x1832c958d  mov     [rsp+100h+var_E0], rax
0x1832c9592  mov     r9, rdi
0x1832c9595  mov     r8, rdx
0x1832c9598  lea     rdx, [r14+60h]
0x1832c959c  mov     rcx, [r14+8]
0x1832c95a0  call    cs:__imp_?in@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEA_W3AEAPEA_W@Z; std::codecvt<wchar_t,char,_Mbstatet>::in(_Mbstatet &,char const *,char const *,char const * &,wchar_t *,wchar_t *,wchar_t * &)
0x1832c95a6  test    eax, eax
0x1832c95a8  js      loc_1832C96C2
0x1832c95ae  cmp     eax, 1
0x1832c95b1  jle     short loc_1832C95F4
0x1832c95b3  cmp     eax, 3
0x1832c95b6  jnz     loc_1832C96C2
0x1832c95bc  mov     rdx, [rbp+57h+var_98]
0x1832c95c0  cmp     rdx, rdi
0x1832c95c3  jz      short loc_1832C962C
0x1832c95c5  nop     word ptr [rax+rax+00000000h]
0x1832c95d0  movzx   r8d, byte ptr [rdx]
0x1832c95d4  mov     edx, 1
0x1832c95d9  lea     rcx, [rbp+57h+Src]
0x1832c95dd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1832c95e2  mov     rdx, [rbp+57h+var_98]
0x1832c95e6  inc     rdx
0x1832c95e9  mov     [rbp+57h+var_98], rdx
0x1832c95ed  cmp     rdx, rdi
0x1832c95f0  jnz     short loc_1832C95D0
0x1832c95f2  jmp     short loc_1832C962C
0x1832c95f4  mov     r8, [rbp+57h+var_90]
0x1832c95f8  cmp     rsi, r8
0x1832c95fb  jnb     short loc_1832C9611
0x1832c95fd  sub     r8, rsi
0x1832c9600  sar     r8, 1
0x1832c9603  mov     rdx, rsi; void *
0x1832c9606  lea     rcx, [rbp+57h+Src]; Src
0x1832c960a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W_K@Z; std::wstring::append(wchar_t const *,unsigned __int64)
0x1832c960f  jmp     short loc_1832C9628
0x1832c9611  cmp     [rbp+57h+var_58], 10h
0x1832c9616  jnb     short loc_1832C9644
0x1832c9618  xor     r8d, r8d
0x1832c961b  lea     edx, [r8+8]
0x1832c961f  lea     rcx, [rbp+57h+var_68]
0x1832c9623  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1832c9628  mov     rdx, [rbp+57h+var_98]
0x1832c962c  mov     rax, rdx
0x1832c962f  sub     rax, r15
0x1832c9632  mov     [r14+70h], rax
0x1832c9636  cmp     rdx, rdi
0x1832c9639  jnz     loc_1832C9560
0x1832c963f  jmp     loc_1832C96EA
0x1832c9644  cmp     byte ptr [r14+6Ah], 0
0x1832c9649  jz      short loc_1832C96A1
0x1832c964b  lea     rdx, [r14+40h]
0x1832c964f  mov     qword ptr [rbx+18h], 7
0x1832c9657  mov     [rbx+10h], r13
0x1832c965b  cmp     qword ptr [rbx+18h], 8
0x1832c9660  jb      short loc_1832C9667
0x1832c9662  mov     rax, [rbx]
0x1832c9665  jmp     short loc_1832C966A
0x1832c9667  mov     rax, rbx
0x1832c966a  mov     [rax], r13w
0x1832c966e  or      r9, 0FFFFFFFFFFFFFFFFh
0x1832c9672  xor     r8d, r8d
0x1832c9675  mov     rcx, rbx; void *
0x1832c9678  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1832c967d  nop
0x1832c967e  mov     r8, [rbp+57h+var_70]
0x1832c9682  cmp     r8, 8
0x1832c9686  jb      loc_1832C974A
0x1832c968c  inc     r8
0x1832c968f  mov     rdx, [rbp+57h+Src]
0x1832c9693  lea     rcx, [rbp+57h+Src]
0x1832c9697  call    ?deallocate@?$allocator@_W@std@@QEAAXPEA_W_K@Z; std::allocator<wchar_t>::deallocate(wchar_t *,unsigned __int64)
0x1832c969c  jmp     loc_1832C974A
0x1832c96a1  lea     rdx, aBadConversion; "bad conversion"
0x1832c96a8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1832c96ac  call    ??0range_error@std@@QEAA@PEBD@Z; std::range_error::range_error(char const *)
0x1832c96b1  lea     rdx, _TI3?AVrange_error@std@@; pThrowInfo
0x1832c96b8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1832c96bc  call    _CxxThrowException_0
0x1832c96c2  cmp     byte ptr [r14+6Ah], 0
0x1832c96c7  jnz     short loc_1832C964B
0x1832c96c9  lea     rdx, aBadConversion; "bad conversion"
0x1832c96d0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1832c96d4  call    ??0range_error@std@@QEAA@PEBD@Z; std::range_error::range_error(char const *)
0x1832c96d9  lea     rdx, _TI3?AVrange_error@std@@; pThrowInfo
0x1832c96e0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1832c96e4  call    _CxxThrowException_0
0x1832c96ea  mov     qword ptr [rbx+18h], 7
0x1832c96f2  mov     [rbx+10h], r13
0x1832c96f6  cmp     qword ptr [rbx+18h], 8
0x1832c96fb  jb      short loc_1832C9702
0x1832c96fd  mov     rax, [rbx]
0x1832c9700  jmp     short loc_1832C9705
0x1832c9702  mov     rax, rbx
0x1832c9705  mov     [rax], r13w
0x1832c9709  mov     rcx, [rbp+57h+var_70]
0x1832c970d  cmp     rcx, 8
0x1832c9711  jnb     short loc_1832C9733
0x1832c9713  mov     r8, [rbp+57h+var_78]
0x1832c9717  add     r8, 1
0x1832c971b  jz      short loc_1832C973E
0x1832c971d  add     r8, r8; Size
0x1832c9720  lea     rdx, [rbp+57h+Src]; Src
0x1832c9724  mov     rcx, rbx; void *
0x1832c9727  call    cs:__imp_memmove
0x1832c972d  mov     rcx, [rbp+57h+var_70]
0x1832c9731  jmp     short loc_1832C973E
0x1832c9733  mov     rax, [rbp+57h+Src]
0x1832c9737  mov     [rbx], rax
0x1832c973a  mov     [rbp+57h+Src], r13
0x1832c973e  mov     rax, [rbp+57h+var_78]
0x1832c9742  mov     [rbx+10h], rax
0x1832c9746  mov     [rbx+18h], rcx
0x1832c974a  mov     [rbp+57h+var_70], 7
0x1832c9752  mov     [rbp+57h+var_78], r13
0x1832c9756  mov     word ptr [rbp+57h+Src], r13w
0x1832c975b  mov     r8, [rbp+57h+var_50]
0x1832c975f  cmp     r8, 8
0x1832c9763  jb      short loc_1832C9775
0x1832c9765  inc     r8
0x1832c9768  mov     rdx, [rbp+57h+var_68]
0x1832c976c  lea     rcx, [rbp+57h+var_68]
0x1832c9770  call    ?deallocate@?$allocator@_W@std@@QEAAXPEA_W_K@Z; std::allocator<wchar_t>::deallocate(wchar_t *,unsigned __int64)
0x1832c9775  mov     rax, rbx
0x1832c9778  mov     rcx, [rbp+57h+var_48]
0x1832c977c  xor     rcx, rsp; StackCookie
0x1832c977f  call    __security_check_cookie
0x1832c9784  add     rsp, 0C8h
0x1832c978b  pop     r15
0x1832c978d  pop     r14
0x1832c978f  pop     r13
0x1832c9791  pop     r12
0x1832c9793  pop     rdi
0x1832c9794  pop     rsi
0x1832c9795  pop     rbx
0x1832c9796  pop     rbp
0x1832c9797  retn
```
