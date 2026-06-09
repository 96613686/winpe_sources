# CSession::DoNodeDiff(std::list<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>> &)

- ea: `0x18000d604`
- end: `0x18000d74b`
- name: `?DoNodeDiff@CSession@@QEAAJAEAV?$list@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(__int64, _QWORD ***)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000db7c`

## callees

- `0x1800024b4`
- `0x18000c890`
- `0x18000cf60`
- `0x18000d0dc`
- `0x18000d604`
- `0x18000dd5c`
- `0x180010b54`
- `0x18001e020`

## pseudocode

```c
__int64 __fastcall CSession::DoNodeDiff(__int64 a1, _QWORD ***a2)
{
  __int64 *v4; // rax
  _QWORD **v5; // rdi
  _QWORD *v6; // rbx
  CInformationNode **v7; // rdi
  CInformationNode *v8; // rbx
  __int64 v9; // rax
  CInformationNode **v10; // rcx
  CInformationNode **v11; // rdx
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-68h] BYREF
  int v15; // [rsp+24h] [rbp-64h] BYREF
  _QWORD *v16; // [rsp+28h] [rbp-60h] BYREF
  __int64 v17; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v18[3]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v19; // [rsp+50h] [rbp-38h] BYREF
  char v20[24]; // [rsp+58h] [rbp-30h] BYREF

  v14 = 0;
  v15 = 0;
  strcpy(v20, "CSession::DoNodeDiff");
  v18[0] = v20;
  v18[1] = &v15;
  v18[2] = &v14;
  lambda_bf8b15b5edd5c1a326ead5341ea61cf1_::operator()(v18);
  v15 = 1;
  v16 = v18;
  v4 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v19, a1);
  v5 = *a2;
  v17 = *v4;
  v6 = *v5;
  while ( v6 != v5 )
  {
    try
    {
      lambda_a357537c8111a8a3155e329953580b13_::operator()(&v17, v6 + 2);
      v6 = (_QWORD *)*v6;
    }
    catch ( std::bad_alloc )
    {
      v14 = -2147024882;
      WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1____::_WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1____(&v16);
      return 2147942414LL;
    }
  }
  v7 = *(CInformationNode ***)(a1 + 424);
  v8 = *v7;
  while ( v8 != (CInformationNode *)v7 )
  {
    v9 = *((_QWORD *)v8 + 2);
    if ( *(_BYTE *)(v9 + 88) )
    {
      *(_BYTE *)(v9 + 88) = 0;
      v8 = *(CInformationNode **)v8;
    }
    else
    {
      CInformationNode::Destroy(*((CInformationNode **)v8 + 2));
      v10 = (CInformationNode **)*((_QWORD *)v8 + 1);
      v11 = (CInformationNode **)v8;
      v8 = *(CInformationNode **)v8;
      *v10 = v8;
      *((_QWORD *)v8 + 1) = v10;
      std::_List_buy<std::unique_ptr<CInformationNode>>::_Freenode((__int64)v10, v11);
      --*(_QWORD *)(a1 + 432);
    }
  }
  v12 = v14;
  WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1____::_WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1____(&v16);
  return v12;
}

```

## disassembly

```asm
0x18000d604  mov     r11, rsp
0x18000d607  mov     [r11+10h], rbx
0x18000d60b  mov     [r11+18h], rsi
0x18000d60f  push    rdi
0x18000d610  sub     rsp, 80h
0x18000d617  mov     rax, cs:__security_cookie
0x18000d61e  xor     rax, rsp
0x18000d621  mov     [rsp+88h+var_18], rax
0x18000d626  mov     rdi, rdx
0x18000d629  mov     rsi, rcx
0x18000d62c  mov     [rsp+88h+var_68], 0
0x18000d634  mov     [rsp+88h+var_64], 0
0x18000d63c  movups  xmm0, xmmword ptr cs:aCsessionDonode; "CSession::DoNodeDiff"
0x18000d643  movups  xmmword ptr [rsp+88h+var_30], xmm0
0x18000d648  movsd   xmm1, qword ptr cs:aCsessionDonode+0Dh; "odeDiff"
0x18000d650  movsd   qword ptr [rsp+88h+var_30+0Dh], xmm1
0x18000d656  lea     rax, [r11-30h]
0x18000d65a  mov     [r11-50h], rax
0x18000d65e  lea     rax, [r11-64h]
0x18000d662  mov     [r11-48h], rax
0x18000d666  lea     rax, [r11-68h]
0x18000d66a  mov     [r11-40h], rax
0x18000d66e  lea     rcx, [r11-50h]
0x18000d672  call    _lambda_bf8b15b5edd5c1a326ead5341ea61cf1___operator__
0x18000d677  mov     [rsp+88h+var_64], 1
0x18000d67f  lea     rax, [rsp+88h+var_50]
0x18000d684  mov     [rsp+88h+var_60], rax
0x18000d689  mov     rdx, rsi
0x18000d68c  lea     rcx, [rsp+88h+var_38]
0x18000d691  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000d696  mov     rdi, [rdi]
0x18000d699  mov     rax, [rax]
0x18000d69c  mov     [rsp+88h+var_58], rax
0x18000d6a1  mov     rbx, [rdi]
0x18000d6a4  cmp     rbx, rdi
0x18000d6a7  jnz     short loc_18000D707
0x18000d6a9  mov     rdi, [rsi+1A8h]
0x18000d6b0  mov     rbx, [rdi]
0x18000d6b3  jmp     short loc_18000D6F0
0x18000d6b5  mov     rax, [rbx+10h]
0x18000d6b9  cmp     byte ptr [rax+58h], 0
0x18000d6bd  jnz     short loc_18000D6E9
0x18000d6bf  mov     rcx, rax; this
0x18000d6c2  call    ?Destroy@CInformationNode@@QEAAJXZ; CInformationNode::Destroy(void)
0x18000d6c7  mov     rcx, [rbx+8]
0x18000d6cb  mov     rdx, rbx
0x18000d6ce  mov     rax, [rbx]
0x18000d6d1  mov     rbx, rax
0x18000d6d4  mov     [rcx], rax
0x18000d6d7  mov     [rax+8], rcx
0x18000d6db  call    ?_Freenode@?$_List_buy@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@QEAAXPEAU?$_List_node@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@PEAX@2@@Z; std::_List_buy<std::unique_ptr<CInformationNode>>::_Freenode(std::_List_node<std::unique_ptr<CInformationNode>,void *> *)
0x18000d6e0  dec     qword ptr [rsi+1B0h]
0x18000d6e7  jmp     short loc_18000D6F0
0x18000d6e9  mov     byte ptr [rax+58h], 0
0x18000d6ed  mov     rbx, [rbx]
0x18000d6f0  cmp     rbx, rdi
0x18000d6f3  jnz     short loc_18000D6B5
0x18000d6f5  mov     ebx, [rsp+88h+var_68]
0x18000d6f9  lea     rcx, [rsp+88h+var_60]
0x18000d6fe  call    WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1_______WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1____
0x18000d703  mov     eax, ebx
0x18000d705  jmp     short loc_18000D729
0x18000d707  lea     rdx, [rbx+10h]
0x18000d70b  lea     rcx, [rsp+88h+var_58]
0x18000d710  call    _lambda_a357537c8111a8a3155e329953580b13___operator__
0x18000d715  mov     rbx, [rbx]
0x18000d718  jmp     short loc_18000D6A4
0x18000d71a  lea     rcx, [rsp+88h+var_60]
0x18000d71f  call    WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1_______WppTraceUnwinder__lambda_bf8b15b5edd5c1a326ead5341ea61cf1____
0x18000d724  mov     eax, 8007000Eh
0x18000d729  mov     rcx, [rsp+88h+var_18]
0x18000d72e  xor     rcx, rsp; StackCookie
0x18000d731  call    __security_check_cookie
0x18000d736  lea     r11, [rsp+88h+var_8]
0x18000d73e  mov     rbx, [r11+18h]
0x18000d742  mov     rsi, [r11+20h]
0x18000d746  mov     rsp, r11
0x18000d749  pop     rdi
0x18000d74a  retn
```
