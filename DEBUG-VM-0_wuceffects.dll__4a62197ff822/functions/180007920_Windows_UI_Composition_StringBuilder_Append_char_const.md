# Windows::UI::Composition::StringBuilder::Append(char const *)

- ea: `0x180007920`
- end: `0x180007bba`
- name: `?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z`
- size: `666`
- prototype: `void __fastcall(Windows::UI::Composition::StringBuilder *__hidden this, const char *)`
- caller_count: `34`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800010b0`
- `0x180001200`
- `0x180001410`
- `0x180001950`
- `0x180001da0`
- `0x180002080`
- `0x180006470`
- `0x1800066e0`
- `0x180006e1c`
- `0x180007394`
- `0x180008220`
- `0x180008320`
- `0x180008550`
- `0x180008730`
- `0x1800088a0`
- `0x18001f220`
- `0x18001f800`
- `0x18001fc70`
- `0x180020150`
- `0x180020570`
- `0x1800259f0`
- `0x180025e20`
- `0x180026770`
- `0x180026c40`
- `0x180027090`
- `0x180027170`
- `0x1800274d0`
- `0x180027810`
- `0x180027920`
- `0x180027ad0`
- `0x180027cd0`
- `0x180027de0`
- `0x180028920`
- `0x180028ba0`

## callees

- `0x180006410`
- `0x180007920`
- `0x180007bc0`
- `0x180028b20`
- `0x18002b8b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007a1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007a1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a09`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::UI::Composition::StringBuilder::Append(
        Windows::UI::Composition::StringBuilder *this,
        const char *a2)
{
  const char *v2; // rbx
  __int64 v4; // rax
  const char *v5; // r15
  unsigned __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  __int64 v10; // r12
  HANDLE ProcessHeap; // rax
  LPVOID v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  const char *v16; // r14
  unsigned __int64 v17; // r12
  __int64 v18; // r13
  unsigned __int64 v19; // rax
  const char *v20; // rbx
  const char *v21; // rsi
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  const char *v23; // [rsp+28h] [rbp-30h]
  __int64 v24; // [rsp+30h] [rbp-28h]
  Windows::UI::Composition::StringBuilder *v25; // [rsp+40h] [rbp-18h] BYREF
  const char *v26; // [rsp+48h] [rbp-10h]

  v2 = a2;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = &a2[v4];
  if ( a2 != &a2[v4] )
  {
    v6 = *((_QWORD *)this + 4);
    v25 = this;
    v26 = (const char *)v6;
    if ( v6 <= v6 >> 1 )
    {
      v13 = v6;
      do
      {
        --v5;
        if ( (*((_BYTE *)this + 24) & 0xF) == 0 && *((_QWORD *)this + 2) <= (unsigned __int64)(v13 + 16) >> 4 )
          std::deque<char>::_Growmap(this);
        v14 = *((_QWORD *)this + 2);
        v15 = *((_QWORD *)this + 3) & (16 * v14 - 1);
        *((_QWORD *)this + 3) = v15;
        if ( !v15 )
          v15 = 16 * v14;
        v16 = (const char *)(v15 - 1);
        v17 = (unsigned __int64)(v15 - 1) >> 4;
        v18 = 8 * (v17 & (v14 - 1));
        if ( !*(_QWORD *)(*((_QWORD *)this + 1) + v18) )
          *(_QWORD *)(*((_QWORD *)this + 1) + v18) = operator new(0x10u);
        *(_BYTE *)(((unsigned __int8)v16 & 0xF)
                 + *(_QWORD *)(*((_QWORD *)this + 1) + 8 * (v17 & (*((_QWORD *)this + 2) - 1LL)))) = *v5;
        *((_QWORD *)this + 3) = v16;
        v13 = *((_QWORD *)this + 4) + 1LL;
        *((_QWORD *)this + 4) = v13;
      }
      while ( v5 != v2 );
      v19 = v13 - v6;
      v20 = &v16[v19];
      if ( v16 != &v16[v19] )
      {
        v21 = &v20[v6];
        if ( v20 != v21 )
        {
          pExceptionObject = (void **)this;
          v23 = &v16[v19];
          v25 = this;
          v26 = v16;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
            &v25,
            &pExceptionObject);
          v25 = this;
          v26 = v21;
          pExceptionObject = (void **)this;
          v23 = v20;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
            &pExceptionObject,
            &v25);
          v25 = this;
          v26 = v21;
          pExceptionObject = (void **)this;
          v23 = v16;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
            &pExceptionObject,
            &v25);
        }
      }
    }
    else
    {
      do
      {
        if ( ((*((_BYTE *)this + 24) + (_BYTE)v6) & 0xF) == 0 && *((_QWORD *)this + 2) <= (v6 + 16) >> 4 )
          std::deque<char>::_Growmap(this);
        v7 = *((_QWORD *)this + 2);
        v8 = *((_QWORD *)this + 3) & (16 * v7 - 1);
        *((_QWORD *)this + 3) = v8;
        v9 = v8 + *((_QWORD *)this + 4);
        v10 = 8 * ((v9 >> 4) & (v7 - 1));
        if ( !*(_QWORD *)(v10 + *((_QWORD *)this + 1)) )
        {
          ProcessHeap = GetProcessHeap();
          v12 = HeapAlloc(ProcessHeap, 0, 0x10u);
          if ( !v12 )
          {
            v24 = 0;
            v23 = "bad allocation";
            pExceptionObject = &std::bad_alloc::`vftable';
            throw (std::bad_alloc *)&pExceptionObject;
          }
          *(_QWORD *)(v10 + *((_QWORD *)this + 1)) = v12;
        }
        *(_BYTE *)((v9 & 0xF) + *(_QWORD *)(*((_QWORD *)this + 1) + 8 * ((v9 >> 4) & (*((_QWORD *)this + 2) - 1LL)))) = *v2;
        v6 = ++*((_QWORD *)this + 4);
        ++v2;
      }
      while ( v2 != v5 );
    }
  }
}

```

## disassembly

```asm
0x180007920  push    rbp
0x180007922  push    rbx
0x180007923  push    rsi
0x180007924  push    rdi
0x180007925  push    r12
0x180007927  push    r13
0x180007929  push    r14
0x18000792b  push    r15
0x18000792d  mov     rbp, rsp
0x180007930  sub     rsp, 58h
0x180007934  mov     rbx, rdx
0x180007937  mov     rdi, rcx
0x18000793a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180007941  lea     rax, [rax+1]
0x180007945  cmp     byte ptr [rdx+rax], 0
0x180007949  jnz     short loc_180007941
0x18000794b  lea     r15, [rax+rdx]
0x18000794f  cmp     rbx, r15
0x180007952  jz      loc_1800079F8
0x180007958  mov     rsi, [rcx+20h]
0x18000795c  mov     rax, rsi
0x18000795f  shr     rax, 1
0x180007962  mov     [rbp+var_18], rdi
0x180007966  mov     [rbp+var_10], rsi
0x18000796a  cmp     rsi, rax
0x18000796d  jbe     loc_180007A34
0x180007973  nop     dword ptr [rax+00h]
0x180007977  nop     word ptr [rax+rax+00000000h]
0x180007980  movzx   eax, sil
0x180007984  add     al, [rdi+18h]
0x180007987  test    al, 0Fh
0x180007989  jz      loc_180007B37
0x18000798f  mov     rdx, [rdi+10h]
0x180007993  mov     rcx, rdx
0x180007996  shl     rcx, 4
0x18000799a  dec     rcx
0x18000799d  and     rcx, [rdi+18h]
0x1800079a1  mov     [rdi+18h], rcx
0x1800079a5  mov     rsi, [rdi+20h]
0x1800079a9  add     rsi, rcx
0x1800079ac  mov     r14, rsi
0x1800079af  shr     r14, 4
0x1800079b3  lea     rax, [rdx-1]
0x1800079b7  and     rax, r14
0x1800079ba  lea     r12, ds:0[rax*8]
0x1800079c2  mov     rax, [rdi+8]
0x1800079c6  cmp     qword ptr [r12+rax], 0
0x1800079cb  jz      short loc_180007A09
0x1800079cd  mov     rax, [rdi+10h]
0x1800079d1  dec     rax
0x1800079d4  and     rax, r14
0x1800079d7  mov     rcx, [rdi+8]
0x1800079db  and     esi, 0Fh
0x1800079de  mov     rcx, [rcx+rax*8]
0x1800079e2  movzx   eax, byte ptr [rbx]
0x1800079e5  mov     [rsi+rcx], al
0x1800079e8  inc     qword ptr [rdi+20h]
0x1800079ec  mov     rsi, [rdi+20h]
0x1800079f0  inc     rbx
0x1800079f3  cmp     rbx, r15
0x1800079f6  jnz     short loc_180007980
0x1800079f8  add     rsp, 58h
0x1800079fc  pop     r15
0x1800079fe  pop     r14
0x180007a00  pop     r13
0x180007a02  pop     r12
0x180007a04  pop     rdi
0x180007a05  pop     rsi
0x180007a06  pop     rbx
0x180007a07  pop     rbp
0x180007a08  retn
0x180007a09  call    cs:__imp_GetProcessHeap
0x180007a0f  nop
0x180007a10  mov     rcx, rax; hHeap
0x180007a13  xor     edx, edx; dwFlags
0x180007a15  mov     r8d, 10h; dwBytes
0x180007a1b  call    cs:__imp_HeapAlloc
0x180007a21  test    rax, rax
0x180007a24  jz      loc_180007B8C
0x180007a2a  mov     rcx, [rdi+8]
0x180007a2e  mov     [r12+rcx], rax
0x180007a32  jmp     short loc_1800079CD
0x180007a34  mov     rax, rsi
0x180007a37  dec     r15
0x180007a3a  test    byte ptr [rdi+18h], 0Fh
0x180007a3e  jz      loc_180007B56
0x180007a44  mov     rdx, [rdi+10h]
0x180007a48  mov     rcx, rdx
0x180007a4b  shl     rcx, 4
0x180007a4f  lea     rax, [rcx-1]
0x180007a53  and     rax, [rdi+18h]
0x180007a57  mov     [rdi+18h], rax
0x180007a5b  cmovz   rax, rcx
0x180007a5f  lea     r14, [rax-1]
0x180007a63  mov     r12, r14
0x180007a66  shr     r12, 4
0x180007a6a  lea     rax, [rdx-1]
0x180007a6e  and     rax, r12
0x180007a71  lea     r13, ds:0[rax*8]
0x180007a79  mov     rax, [rdi+8]
0x180007a7d  cmp     qword ptr [rax+r13], 0
0x180007a82  jz      loc_180007B75
0x180007a88  mov     rax, [rdi+10h]
0x180007a8c  dec     rax
0x180007a8f  and     rax, r12
0x180007a92  mov     rcx, [rdi+8]
0x180007a96  mov     rdx, r14
0x180007a99  and     edx, 0Fh
0x180007a9c  mov     rcx, [rcx+rax*8]
0x180007aa0  movzx   eax, byte ptr [r15]
0x180007aa4  mov     [rdx+rcx], al
0x180007aa7  mov     [rdi+18h], r14
0x180007aab  mov     rax, [rdi+20h]
0x180007aaf  inc     rax
0x180007ab2  mov     [rdi+20h], rax
0x180007ab6  cmp     r15, rbx
0x180007ab9  jnz     loc_180007A37
0x180007abf  sub     rax, rsi
0x180007ac2  lea     rbx, [rax+r14]
0x180007ac6  cmp     r14, rbx
0x180007ac9  jz      loc_1800079F8
0x180007acf  add     rsi, rbx
0x180007ad2  cmp     rbx, rsi
0x180007ad5  jz      loc_1800079F8
0x180007adb  mov     [rbp+pExceptionObject], rdi
0x180007adf  mov     qword ptr [rbp+var_30], rbx
0x180007ae3  mov     [rbp+var_18], rdi
0x180007ae7  mov     [rbp+var_10], r14
0x180007aeb  lea     rdx, [rbp+pExceptionObject]
0x180007aef  lea     rcx, [rbp+var_18]
0x180007af3  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x180007af8  mov     [rbp+var_18], rdi
0x180007afc  mov     [rbp+var_10], rsi
0x180007b00  mov     [rbp+pExceptionObject], rdi
0x180007b04  mov     qword ptr [rbp+var_30], rbx
0x180007b08  lea     rdx, [rbp+var_18]
0x180007b0c  lea     rcx, [rbp+pExceptionObject]
0x180007b10  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x180007b15  mov     [rbp+var_18], rdi
0x180007b19  mov     [rbp+var_10], rsi
0x180007b1d  mov     [rbp+pExceptionObject], rdi
0x180007b21  mov     qword ptr [rbp+var_30], r14
0x180007b25  lea     rdx, [rbp+var_18]
0x180007b29  lea     rcx, [rbp+pExceptionObject]
0x180007b2d  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x180007b32  jmp     loc_1800079F8
0x180007b37  lea     rax, [rsi+10h]
0x180007b3b  shr     rax, 4
0x180007b3f  cmp     [rdi+10h], rax
0x180007b43  ja      loc_18000798F
0x180007b49  mov     rcx, rdi
0x180007b4c  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x180007b51  jmp     loc_18000798F
0x180007b56  add     rax, 10h
0x180007b5a  shr     rax, 4
0x180007b5e  cmp     [rdi+10h], rax
0x180007b62  ja      loc_180007A44
0x180007b68  mov     rcx, rdi
0x180007b6b  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x180007b70  jmp     loc_180007A44
0x180007b75  mov     ecx, 10h; dwBytes
0x180007b7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b7f  mov     rcx, [rdi+8]
0x180007b83  mov     [rcx+r13], rax
0x180007b87  jmp     loc_180007A88
0x180007b8c  xorps   xmm0, xmm0
0x180007b8f  movups  [rbp+var_30], xmm0
0x180007b93  lea     rax, aBadAllocation; "bad allocation"
0x180007b9a  mov     qword ptr [rbp+var_30], rax
0x180007b9e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180007ba5  mov     [rbp+pExceptionObject], rax
0x180007ba9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180007bb0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007bb4  call    _CxxThrowException_0
```
