# UpdateRPCCacheEntry

- ea: `0x18000a840`
- end: `0x18000aa00`
- name: `UpdateRPCCacheEntry`
- size: `448`
- prototype: `void __fastcall(__int64, struct CReadWriteLock *, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1800080dc`

## callees

- `0x180002d0c`
- `0x180002df0`
- `0x180004230`
- `0x180005fb8`
- `0x18000a840`
- `0x18000c4f4`
- `0x18000c614`
- `0x18000de20`
- `0x18000df04`
- `0x18000e068`
- `0x18000f214`
- `0x18000f5f0`

## import_xrefs

- `msvcrt!free` at `0x18000a89f`
- `msvcrt!free` at `0x18000a89f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UpdateRPCCacheEntry(__int64 a1, struct CReadWriteLock *a2, char a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rbx
  struct CReadWriteLock *v9; // r8
  _QWORD *v10; // rcx
  int v11; // eax
  int v12; // eax
  int v13; // r8d
  __int64 v14; // [rsp+30h] [rbp-50h] BYREF
  CReadWriteLock *v15; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-30h] BYREF
  void *Block; // [rsp+58h] [rbp-28h]
  unsigned __int64 v19; // [rsp+70h] [rbp-10h]

  CSW::CSW((CSW *)&v15, a2);
  std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>(
    v17,
    a1);
  std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::equal_range(
    v6,
    v16,
    v17);
  if ( v19 >= 0x10 )
    free(Block);
  v8 = v16[0];
  v14 = v16[0];
  while ( v8 != v16[1] )
  {
    v9 = *(struct CReadWriteLock **)(v8 + 64);
    if ( v9 == a2 )
    {
      if ( a3 && *(_BYTE *)(v8 + 76) )
      {
        *(_BYTE *)(v8 + 76) = 0;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
        {
          WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, (_DWORD)v9, a1, (char)v9, *(_DWORD *)(v8 + 72));
          goto LABEL_12;
        }
      }
      else
      {
LABEL_12:
        v10 = WPP_GLOBAL_Control;
      }
      v11 = *(_DWORD *)(v8 + 72);
      if ( v11 > 0 )
      {
        *(_DWORD *)(v8 + 72) = v11 - 1;
        goto LABEL_18;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 2) != 0 )
      {
        WPP_SF_qd(v10[12], v7, v9, *(_QWORD *)(v8 + 64), *(_DWORD *)(v8 + 72));
LABEL_18:
        v10 = WPP_GLOBAL_Control;
      }
      v12 = *(_DWORD *)(v8 + 72);
      if ( v12 || *(_BYTE *)(v8 + 76) )
      {
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 4) != 0 )
          WPP_SF_sqd(v10[12], 43, (_DWORD)v9, a1, *(_QWORD *)(v8 + 64), v12);
      }
      else
      {
        FreeRpcBindHandle(*(_QWORD *)(v8 + 64));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
          WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, v13, a1, *(_QWORD *)(v8 + 64));
        std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::erase(
          &qword_180017CB0,
          &v14,
          v8);
      }
      break;
    }
    std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::iterator::operator++(&v14);
    v8 = v14;
  }
  if ( v15 )
    CReadWriteLock::UnlockWrite(v15);
}

```

## disassembly

```asm
0x18000a840  mov     [rsp-18h+arg_8], rbx
0x18000a845  mov     [rsp-18h+arg_10], rsi
0x18000a84a  push    rbp
0x18000a84b  push    rdi
0x18000a84c  push    r14
0x18000a84e  mov     rbp, rsp
0x18000a851  sub     rsp, 80h
0x18000a858  mov     rax, cs:__security_cookie
0x18000a85f  xor     rax, rsp
0x18000a862  mov     [rbp+var_8], rax
0x18000a866  mov     sil, r8b
0x18000a869  mov     rdi, rdx
0x18000a86c  mov     r14, rcx
0x18000a86f  lea     rcx, [rbp+var_48]; this
0x18000a873  call    ??0CSW@@QEAA@AEAVCReadWriteLock@@@Z; CSW::CSW(CReadWriteLock &)
0x18000a878  nop
0x18000a879  mov     rdx, r14
0x18000a87c  lea     rcx, [rbp+var_30]
0x18000a880  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>(char const *)
0x18000a885  nop
0x18000a886  lea     r8, [rbp+var_30]
0x18000a88a  lea     rdx, [rbp+var_40]
0x18000a88e  call    ?equal_range@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@V123@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::equal_range(std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const &)
0x18000a893  nop
0x18000a894  cmp     [rbp+var_10], 10h
0x18000a899  jb      short loc_18000A8A6
0x18000a89b  mov     rcx, [rbp+Block]; Block
0x18000a89f  call    cs:__imp_free
0x18000a8a5  nop
0x18000a8a6  mov     rbx, [rbp+var_40]
0x18000a8aa  mov     [rbp+var_50], rbx
0x18000a8ae  cmp     rbx, [rbp+var_38]
0x18000a8b2  jz      loc_18000A9CD
0x18000a8b8  mov     r8, [rbx+40h]
0x18000a8bc  cmp     r8, rdi
0x18000a8bf  jz      short loc_18000A8D0
0x18000a8c1  lea     rcx, [rbp+var_50]
0x18000a8c5  call    ??Eiterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@QEAAAEAV012@XZ; std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::iterator::operator++(void)
0x18000a8ca  mov     rbx, [rbp+var_50]
0x18000a8ce  jmp     short loc_18000A8AE
0x18000a8d0  lea     rdi, WPP_GLOBAL_Control
0x18000a8d7  test    sil, sil
0x18000a8da  jz      short loc_18000A915
0x18000a8dc  cmp     byte ptr [rbx+4Ch], 0
0x18000a8e0  jz      short loc_18000A915
0x18000a8e2  mov     byte ptr [rbx+4Ch], 0
0x18000a8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8ed  cmp     rcx, rdi
0x18000a8f0  jz      short loc_18000A91C
0x18000a8f2  test    byte ptr [rcx+6Ch], 4
0x18000a8f6  jz      short loc_18000A91C
0x18000a8f8  mov     edx, 28h ; '('
0x18000a8fd  mov     eax, [rbx+48h]
0x18000a900  mov     [rsp+80h+var_58], eax
0x18000a904  mov     [rsp+80h+var_60], r8
0x18000a909  mov     r9, r14
0x18000a90c  mov     rcx, [rcx+60h]
0x18000a910  call    WPP_SF_sqd
0x18000a915  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a91c  mov     eax, [rbx+48h]
0x18000a91f  test    eax, eax
0x18000a921  jle     short loc_18000A92A
0x18000a923  dec     eax
0x18000a925  mov     [rbx+48h], eax
0x18000a928  jmp     short loc_18000A946
0x18000a92a  cmp     rcx, rdi
0x18000a92d  jz      short loc_18000A94D
0x18000a92f  test    byte ptr [rcx+6Ch], 2
0x18000a933  jz      short loc_18000A94D
0x18000a935  mov     dword ptr [rsp+80h+var_60], eax
0x18000a939  mov     r9, [rbx+40h]
0x18000a93d  mov     rcx, [rcx+60h]
0x18000a941  call    WPP_SF_qd
0x18000a946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a94d  mov     eax, [rbx+48h]
0x18000a950  test    eax, eax
0x18000a952  jnz     short loc_18000A9A3
0x18000a954  cmp     [rbx+4Ch], al
0x18000a957  jnz     short loc_18000A9A3
0x18000a959  mov     rcx, [rbx+40h]
0x18000a95d  call    FreeRpcBindHandle
0x18000a962  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a969  cmp     rcx, rdi
0x18000a96c  jz      short loc_18000A98E
0x18000a96e  test    byte ptr [rcx+6Ch], 4
0x18000a972  jz      short loc_18000A98E
0x18000a974  mov     edx, 2Ah ; '*'
0x18000a979  mov     rax, [rbx+40h]
0x18000a97d  mov     [rsp+80h+var_60], rax
0x18000a982  mov     r9, r14
0x18000a985  mov     rcx, [rcx+60h]
0x18000a989  call    WPP_SF_sq
0x18000a98e  mov     r8, rbx
0x18000a991  lea     rdx, [rbp+var_50]
0x18000a995  lea     rcx, qword_180017CB0
0x18000a99c  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@QEAA?AViterator@12@V312@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::erase(std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::iterator)
0x18000a9a1  jmp     short loc_18000A9CD
0x18000a9a3  cmp     rcx, rdi
0x18000a9a6  jz      short loc_18000A9CD
0x18000a9a8  test    byte ptr [rcx+6Ch], 4
0x18000a9ac  jz      short loc_18000A9CD
0x18000a9ae  mov     edx, 2Bh ; '+'
0x18000a9b3  mov     [rsp+80h+var_58], eax
0x18000a9b7  mov     rax, [rbx+40h]
0x18000a9bb  mov     [rsp+80h+var_60], rax
0x18000a9c0  mov     r9, r14
0x18000a9c3  mov     rcx, [rcx+60h]
0x18000a9c7  call    WPP_SF_sqd
0x18000a9cc  nop
0x18000a9cd  mov     rcx, [rbp+var_48]; this
0x18000a9d1  test    rcx, rcx
0x18000a9d4  jz      short loc_18000A9DC
0x18000a9d6  call    ?UnlockWrite@CReadWriteLock@@QEAAXXZ; CReadWriteLock::UnlockWrite(void)
0x18000a9db  nop
0x18000a9dc  mov     rcx, [rbp+var_8]
0x18000a9e0  xor     rcx, rsp; StackCookie
0x18000a9e3  call    __security_check_cookie
0x18000a9e8  lea     r11, [rsp+80h+var_s0]
0x18000a9f0  mov     rbx, [r11+28h]
0x18000a9f4  mov     rsi, [r11+30h]
0x18000a9f8  mov     rsp, r11
0x18000a9fb  pop     r14
0x18000a9fd  pop     rdi
0x18000a9fe  pop     rbp
0x18000a9ff  retn
```
