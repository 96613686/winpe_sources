# LookupRPCConnectionFromCache

- ea: `0x180007988`
- end: `0x180007b29`
- name: `LookupRPCConnectionFromCache`
- size: `417`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006834`

## callees

- `0x180002d0c`
- `0x180003938`
- `0x180004230`
- `0x180007988`
- `0x18000c4f4`
- `0x18000e124`
- `0x18000f0c8`
- `0x18000f2e0`
- `0x18000f5f0`

## import_xrefs

- `msvcrt!free` at `0x180007a8e`
- `msvcrt!free` at `0x180007a8e`
- `KERNEL32!Sleep` at `0x180007a1a`
- `KERNEL32!Sleep` at `0x180007a1a`
- `KERNEL32!WaitForSingleObject` at `0x180007a61`
- `KERNEL32!WaitForSingleObject` at `0x180007a61`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LookupRPCConnectionFromCache(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  signed __int32 v5; // ebx
  unsigned int v6; // eax
  void *WaiterSemaphore; // r8
  __int64 v8; // rcx
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 i; // [rsp+30h] [rbp-50h] BYREF
  void *v15; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-30h] BYREF
  void *Block; // [rsp+58h] [rbp-28h]
  unsigned __int64 v19; // [rsp+70h] [rbp-10h]

  v15 = &s_rwlockRpcTable;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, &s_rwlockRpcTable);
  v4 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v5 = dword_180017C9C;
        if ( (unsigned int)dword_180017C9C >= 0x3FF )
          break;
        if ( v5 == _InterlockedCompareExchange(&dword_180017C9C, dword_180017C9C + 1, dword_180017C9C) )
          goto LABEL_14;
      }
      if ( (dword_180017C9C & 0x3FF) != 0x3FF && (dword_180017C9C & 0x3FF000) != 0x3FF000 )
        break;
      Sleep(0x3E8u);
    }
    v6 = v4++;
    if ( v6 >= s_rwlockRpcTable )
    {
      WaiterSemaphore = CReadWriteLock::GetReadWaiterSemaphore((CReadWriteLock *)&s_rwlockRpcTable);
      if ( v5 == _InterlockedCompareExchange(&dword_180017C9C, v5 + 4096, v5) )
        break;
    }
  }
  WaitForSingleObject(WaiterSemaphore, 0xFFFFFFFF);
LABEL_14:
  std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>(
    v17,
    a1);
  std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::equal_range(
    v8,
    v16,
    v17);
  if ( v19 >= 0x10 )
    free(Block);
  v11 = v16[0];
  for ( i = v16[0]; ; v11 = i )
  {
    if ( v11 == v16[1] )
    {
      v12 = 0;
      goto LABEL_25;
    }
    if ( *(_BYTE *)(v11 + 76) )
      break;
    std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::iterator::operator++(&i);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    WPP_SF_sql(*((_QWORD *)WPP_GLOBAL_Control + 12), v9, v10, a1, *(_QWORD *)(v11 + 64), *(_DWORD *)(v11 + 72));
  _InterlockedIncrement((volatile signed __int32 *)(v11 + 72));
  v12 = *(_QWORD *)(v11 + 64);
LABEL_25:
  CSR::~CSR((CSR *)&v15);
  return v12;
}

```

## disassembly

```asm
0x180007988  mov     [rsp-18h+arg_8], rbx
0x18000798d  mov     [rsp-18h+arg_10], rsi
0x180007992  push    rbp
0x180007993  push    rdi
0x180007994  push    r14
0x180007996  mov     rbp, rsp
0x180007999  sub     rsp, 80h
0x1800079a0  mov     rax, cs:__security_cookie
0x1800079a7  xor     rax, rsp
0x1800079aa  mov     [rbp+var_8], rax
0x1800079ae  mov     rsi, rcx
0x1800079b1  lea     r14, ?s_rwlockRpcTable@@3VCReadWriteLock@@A; CReadWriteLock s_rwlockRpcTable
0x1800079b8  mov     [rbp+var_48], r14
0x1800079bc  lea     rax, WPP_GLOBAL_Control
0x1800079c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079ca  cmp     rcx, rax
0x1800079cd  jz      short loc_1800079E6
0x1800079cf  test    byte ptr [rcx+1Ch], 4
0x1800079d3  jz      short loc_1800079E6
0x1800079d5  mov     edx, 0Ah
0x1800079da  mov     r9, r14
0x1800079dd  mov     rcx, [rcx+10h]
0x1800079e1  call    WPP_SF_q
0x1800079e6  xor     edi, edi
0x1800079e8  mov     ebx, cs:dword_180017C9C
0x1800079ee  mov     eax, ebx
0x1800079f0  cmp     ebx, 3FFh
0x1800079f6  jnb     short loc_180007A09
0x1800079f8  lea     ecx, [rbx+1]
0x1800079fb  lock cmpxchg cs:dword_180017C9C, ecx
0x180007a03  cmp     ebx, eax
0x180007a05  jnz     short loc_1800079E8
0x180007a07  jmp     short loc_180007A68
0x180007a09  and     eax, 3FFh
0x180007a0e  cmp     eax, 3FFh
0x180007a13  jnz     short loc_180007A22
0x180007a15  mov     ecx, 3E8h; dwMilliseconds
0x180007a1a  call    cs:__imp_Sleep
0x180007a20  jmp     short loc_1800079E8
0x180007a22  mov     eax, ebx
0x180007a24  and     eax, 3FF000h
0x180007a29  cmp     eax, 3FF000h
0x180007a2e  jz      short loc_180007A15
0x180007a30  mov     eax, edi
0x180007a32  inc     edi
0x180007a34  cmp     eax, cs:?s_rwlockRpcTable@@3VCReadWriteLock@@A; CReadWriteLock s_rwlockRpcTable
0x180007a3a  jb      short loc_1800079E8
0x180007a3c  mov     rcx, r14; this
0x180007a3f  call    ?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetReadWaiterSemaphore(void)
0x180007a44  mov     r8, rax
0x180007a47  lea     ecx, [rbx+1000h]
0x180007a4d  mov     eax, ebx
0x180007a4f  lock cmpxchg cs:dword_180017C9C, ecx
0x180007a57  cmp     ebx, eax
0x180007a59  jnz     short loc_1800079E8
0x180007a5b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007a5e  mov     rcx, r8; hHandle
0x180007a61  call    cs:__imp_WaitForSingleObject
0x180007a67  nop
0x180007a68  mov     rdx, rsi
0x180007a6b  lea     rcx, [rbp+var_30]
0x180007a6f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>(char const *)
0x180007a74  nop
0x180007a75  lea     r8, [rbp+var_30]
0x180007a79  lea     rdx, [rbp+var_40]
0x180007a7d  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@V123@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::equal_range(std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const &)
0x180007a82  nop
0x180007a83  cmp     [rbp+var_10], 10h
0x180007a88  jb      short loc_180007A95
0x180007a8a  mov     rcx, [rbp+Block]; Block
0x180007a8e  call    cs:__imp_free
0x180007a94  nop
0x180007a95  mov     rbx, [rbp+var_40]
0x180007a99  mov     [rbp+var_50], rbx
0x180007a9d  cmp     rbx, [rbp+var_38]
0x180007aa1  jz      short loc_180007AF7
0x180007aa3  cmp     byte ptr [rbx+4Ch], 0
0x180007aa7  jnz     short loc_180007AB8
0x180007aa9  lea     rcx, [rbp+var_50]
0x180007aad  call    ??Eiterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@QEAAAEAV012@XZ; std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::iterator::operator++(void)
0x180007ab2  mov     rbx, [rbp+var_50]
0x180007ab6  jmp     short loc_180007A9D
0x180007ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007abf  lea     rax, WPP_GLOBAL_Control
0x180007ac6  cmp     rcx, rax
0x180007ac9  jz      short loc_180007AED
0x180007acb  test    byte ptr [rcx+6Ch], 4
0x180007acf  jz      short loc_180007AED
0x180007ad1  mov     eax, [rbx+48h]
0x180007ad4  mov     [rsp+80h+var_58], eax
0x180007ad8  mov     rax, [rbx+40h]
0x180007adc  mov     [rsp+80h+var_60], rax
0x180007ae1  mov     r9, rsi
0x180007ae4  mov     rcx, [rcx+60h]
0x180007ae8  call    WPP_SF_sql
0x180007aed  lock inc dword ptr [rbx+48h]
0x180007af1  mov     rbx, [rbx+40h]
0x180007af5  jmp     short loc_180007AF9
0x180007af7  xor     ebx, ebx
0x180007af9  lea     rcx, [rbp+var_48]; this
0x180007afd  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x180007b02  mov     rax, rbx
0x180007b05  mov     rcx, [rbp+var_8]
0x180007b09  xor     rcx, rsp; StackCookie
0x180007b0c  call    __security_check_cookie
0x180007b11  lea     r11, [rsp+80h+var_s0]
0x180007b19  mov     rbx, [r11+28h]
0x180007b1d  mov     rsi, [r11+30h]
0x180007b21  mov     rsp, r11
0x180007b24  pop     r14
0x180007b26  pop     rdi
0x180007b27  pop     rbp
0x180007b28  retn
```
