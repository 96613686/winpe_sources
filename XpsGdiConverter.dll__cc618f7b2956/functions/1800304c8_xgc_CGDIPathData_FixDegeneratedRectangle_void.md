# xgc::CGDIPathData::FixDegeneratedRectangle(void)

- ea: `0x1800304c8`
- end: `0x18003065a`
- name: `?FixDegeneratedRectangle@CGDIPathData@xgc@@AEAAXXZ`
- size: `402`
- prototype: `void __fastcall(xgc::CGDIPathData *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002e550`

## callees

- `0x180008830`
- `0x18000d428`
- `0x18002ca38`
- `0x1800304c8`
- `0x180030660`
- `0x180030904`
- `0x18003098c`
- `0x1800372e4`

## pseudocode

```c
void __fastcall xgc::CGDIPathData::FixDegeneratedRectangle(xgc::CGDIPathData *this)
{
  const char *v2; // rdx
  __int64 v3; // r8
  _QWORD *v4; // rsi
  __int64 v5; // r9
  __int64 v6; // rbx
  int v7; // ebx
  xpsrdr *v8; // rcx
  __int64 v9; // rcx
  int v10; // r8d
  __int64 v11; // r9
  __int64 i; // r8
  int v13; // r8d
  int v14; // r10d
  int v15; // r8d
  int v16; // r9d
  int v17; // r10d
  __int64 j; // rdi
  int v19; // [rsp+20h] [rbp-38h] BYREF
  __int128 v20; // [rsp+24h] [rbp-34h] BYREF
  __int128 v21; // [rsp+34h] [rbp-24h] BYREF
  int v22; // [rsp+44h] [rbp-14h]

  if ( xgc::CGDIPathData::IsAxisAlignedRectangle(this) )
  {
    v3 = *((unsigned int *)this + 22);
    v4 = (_QWORD *)((char *)this + 40);
    v5 = *((_QWORD *)this + 5);
    v6 = *((_QWORD *)this + 6) - v5;
    v22 = 0;
    v7 = (v6 >> 3) - v3;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    if ( (unsigned int)(v7 - 4) > 1 )
    {
      v8 = (xpsrdr *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          10,
          WPP_00624022ad39391a483a764a1c0090f0_Traceguids,
          (unsigned int)v7);
      xpsrdr::ThrowLogicException(v8, v2, v3);
    }
    if ( (unsigned __int8)xgc::operator==(v5 + 8 * v3, v5 + 8LL * (unsigned int)(v3 + 1))
      || (unsigned __int8)xgc::operator==(v9, v11 + 8LL * (unsigned int)(v10 + 3)) )
    {
      for ( i = (unsigned int)(v7 - 1); (int)i >= 0; i = (unsigned int)(v13 - 1) )
      {
        *((_QWORD *)&v19 + i) = *(_QWORD *)(*v4 + 8LL * (unsigned int)(i + *((_DWORD *)this + 22)));
        std::vector<tagPOINT>::pop_back((char *)this + 40);
      }
      if ( (unsigned __int8)xgc::operator==(&v19, (char *)&v20 + 4) )
      {
        if ( v14 == HIDWORD(v20) )
        {
          ++DWORD1(v20);
          ++HIDWORD(v20);
        }
        else if ( (_DWORD)v20 == (_DWORD)v21 )
        {
          ++DWORD2(v20);
          LODWORD(v21) = v21 + 1;
        }
      }
      if ( (unsigned __int8)xgc::operator==(&v19, (char *)&v21 + 4) )
      {
        if ( v17 == v16 )
        {
          ++DWORD1(v21);
          HIDWORD(v20) = v16 + 1;
        }
        else if ( (_DWORD)v20 == v15 )
        {
          ++DWORD2(v21);
          LODWORD(v21) = v15 + 1;
        }
      }
      for ( j = 0; (int)j < v7; j = (unsigned int)(j + 1) )
        std::vector<tagPOINT>::push_back(v4, &v19 + 2 * j);
    }
  }
}

```

## disassembly

```asm
0x1800304c8  push    rbp
0x1800304ca  push    rbx
0x1800304cb  push    rsi
0x1800304cc  push    rdi
0x1800304cd  mov     rbp, rsp
0x1800304d0  sub     rsp, 58h
0x1800304d4  mov     rax, cs:__security_cookie
0x1800304db  xor     rax, rsp
0x1800304de  mov     [rbp+var_10], rax
0x1800304e2  mov     rdi, rcx
0x1800304e5  call    ?IsAxisAlignedRectangle@CGDIPathData@xgc@@AEBA_NXZ; xgc::CGDIPathData::IsAxisAlignedRectangle(void)
0x1800304ea  test    al, al
0x1800304ec  jz      loc_180030645
0x1800304f2  mov     r8d, [rdi+58h]
0x1800304f6  lea     rsi, [rdi+28h]
0x1800304fa  mov     r9, [rsi]
0x1800304fd  xor     eax, eax
0x1800304ff  mov     rbx, [rsi+8]
0x180030503  xor     r10d, r10d
0x180030506  sub     rbx, r9
0x180030509  mov     [rbp+var_14], eax
0x18003050c  sar     rbx, 3
0x180030510  xorps   xmm0, xmm0
0x180030513  sub     ebx, r8d
0x180030516  mov     dword ptr [rbp+var_38], r10d
0x18003051a  movups  xmmword ptr [rbp+var_38+4], xmm0
0x18003051e  movups  [rbp+var_24], xmm0
0x180030522  lea     eax, [rbx-4]
0x180030525  cmp     eax, 1
0x180030528  jbe     short loc_180030566
0x18003052a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030531  lea     rax, WPP_GLOBAL_Control
0x180030538  cmp     rcx, rax
0x18003053b  jz      short loc_180030560
0x18003053d  test    byte ptr [rcx+0E4h], 1
0x180030544  jz      short loc_180030560
0x180030546  mov     rcx, [rcx+0D8h]
0x18003054d  lea     edx, [r10+0Ah]
0x180030551  mov     r9d, ebx
0x180030554  lea     r8, WPP_00624022ad39391a483a764a1c0090f0_Traceguids
0x18003055b  call    WPP_SF_d
0x180030560  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x180030566  lea     eax, [r8+1]
0x18003056a  lea     rdx, [r9+rax*8]
0x18003056e  lea     rcx, [r9+r8*8]
0x180030572  call    ??8xgc@@YA_NAEBUtagPOINT@@0@Z; xgc::operator==(tagPOINT const &,tagPOINT const &)
0x180030577  test    al, al
0x180030579  jnz     short loc_180030590
0x18003057b  lea     eax, [r8+3]
0x18003057f  lea     rdx, [r9+rax*8]
0x180030583  call    ??8xgc@@YA_NAEBUtagPOINT@@0@Z; xgc::operator==(tagPOINT const &,tagPOINT const &)
0x180030588  test    al, al
0x18003058a  jz      loc_180030645
0x180030590  lea     r8d, [rbx-1]
0x180030594  test    r8d, r8d
0x180030597  js      short loc_1800305BD
0x180030599  mov     ecx, [rdi+58h]
0x18003059c  mov     rax, [rsi]
0x18003059f  add     ecx, r8d
0x1800305a2  mov     rax, [rax+rcx*8]
0x1800305a6  mov     rcx, rsi
0x1800305a9  mov     [rbp+r8*8+var_38], rax
0x1800305ae  call    ?pop_back@?$vector@UtagPOINT@@V?$allocator@UtagPOINT@@@std@@@std@@QEAAXXZ; std::vector<tagPOINT>::pop_back(void)
0x1800305b3  sub     r8d, 1
0x1800305b7  jns     short loc_180030599
0x1800305b9  mov     r10d, dword ptr [rbp+var_38]
0x1800305bd  lea     rdx, [rbp+var_30]
0x1800305c1  lea     rcx, [rbp+var_38]
0x1800305c5  call    ??8xgc@@YA_NAEBUtagPOINT@@0@Z; xgc::operator==(tagPOINT const &,tagPOINT const &)
0x1800305ca  mov     r9d, [rbp+var_28]
0x1800305ce  mov     r8d, dword ptr [rbp+var_24]
0x1800305d2  test    al, al
0x1800305d4  jz      short loc_1800305F7
0x1800305d6  cmp     r10d, r9d
0x1800305d9  jnz     short loc_1800305E7
0x1800305db  inc     [rbp+var_30]
0x1800305de  inc     r9d
0x1800305e1  mov     [rbp+var_28], r9d
0x1800305e5  jmp     short loc_1800305F7
0x1800305e7  cmp     dword ptr [rbp+var_38+4], r8d
0x1800305eb  jnz     short loc_1800305F7
0x1800305ed  inc     [rbp+var_2C]
0x1800305f0  inc     r8d
0x1800305f3  mov     dword ptr [rbp+var_24], r8d
0x1800305f7  lea     rdx, [rbp+var_24+4]
0x1800305fb  lea     rcx, [rbp+var_38]
0x1800305ff  call    ??8xgc@@YA_NAEBUtagPOINT@@0@Z; xgc::operator==(tagPOINT const &,tagPOINT const &)
0x180030604  test    al, al
0x180030606  jz      short loc_180030629
0x180030608  cmp     r10d, r9d
0x18003060b  jnz     short loc_180030619
0x18003060d  inc     r9d
0x180030610  inc     dword ptr [rbp+var_24+4]
0x180030613  mov     [rbp+var_28], r9d
0x180030617  jmp     short loc_180030629
0x180030619  cmp     dword ptr [rbp+var_38+4], r8d
0x18003061d  jnz     short loc_180030629
0x18003061f  inc     r8d
0x180030622  inc     dword ptr [rbp+var_24+8]
0x180030625  mov     dword ptr [rbp+var_24], r8d
0x180030629  xor     edi, edi
0x18003062b  test    ebx, ebx
0x18003062d  jle     short loc_180030645
0x18003062f  lea     rdx, [rbp+var_38]
0x180030633  mov     rcx, rsi
0x180030636  lea     rdx, [rdx+rdi*8]
0x18003063a  call    ?push_back@?$vector@UtagPOINT@@V?$allocator@UtagPOINT@@@std@@@std@@QEAAXAEBUtagPOINT@@@Z; std::vector<tagPOINT>::push_back(tagPOINT const &)
0x18003063f  inc     edi
0x180030641  cmp     edi, ebx
0x180030643  jl      short loc_18003062F
0x180030645  mov     rcx, [rbp+var_10]
0x180030649  xor     rcx, rsp; StackCookie
0x18003064c  call    __security_check_cookie
0x180030651  add     rsp, 58h
0x180030655  pop     rdi
0x180030656  pop     rsi
0x180030657  pop     rbx
0x180030658  pop     rbp
0x180030659  retn
```
