# CNetworkItemFactory::_DuplicateDetection(IFunctionInstance *,CNetworkItem * *,int *)

- ea: `0x180004074`
- end: `0x1800042a5`
- name: `?_DuplicateDetection@CNetworkItemFactory@@AEAAJPEAUIFunctionInstance@@PEAPEAVCNetworkItem@@PEAH@Z`
- size: `561`
- prototype: `__int64 __fastcall(CNetworkItemFactory *this, struct IFunctionInstance *, struct CNetworkItem **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000488c`

## callees

- `0x180004074`
- `0x18000433c`
- `0x1800058c4`
- `0x1800070f4`
- `0x180008354`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004158`
- `ole32!CoTaskMemFree` at `0x180004238`
- `ole32!CoTaskMemFree` at `0x180004277`
- `ole32!CoTaskMemFree` at `0x18000428e`
- `ole32!CoTaskMemFree` at `0x180004158`
- `ole32!CoTaskMemFree` at `0x180004238`
- `ole32!CoTaskMemFree` at `0x180004277`
- `ole32!CoTaskMemFree` at `0x18000428e`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_DuplicateDetection(
        CNetworkItemFactory *this,
        struct IFunctionInstance *a2,
        struct CNetworkItem **a3,
        int *a4)
{
  int ComputerNameAlloc; // ebx
  __int64 v9; // r8
  LPVOID v10; // rsi
  struct CNetworkItem *v11; // rcx
  __int64 v12; // r8
  void *v13; // rsi
  struct CNetworkItem *v14; // rcx
  LPVOID pv; // [rsp+68h] [rbp+48h] BYREF
  LPVOID v17; // [rsp+70h] [rbp+50h] BYREF
  void *lpMem; // [rsp+78h] [rbp+58h] BYREF

  *a3 = 0;
  *a4 = 0;
  v17 = 0;
  ComputerNameAlloc = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))a2->lpVtbl->GetID)(a2, &v17);
  if ( ComputerNameAlloc >= 0 )
  {
    pv = 0;
    if ( (unsigned int)LKRhash::CLKRHashTable::FindKey(*((_QWORD *)this + 10), v17, &pv) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v9, v17);
      }
      pv = 0;
      ComputerNameAlloc = CNetworkItemFactory::_GetComputerNameAlloc(a2, (unsigned __int16 **)&pv);
      if ( ComputerNameAlloc < 0 )
      {
        if ( ComputerNameAlloc == -2147023288 )
          ComputerNameAlloc = 0;
      }
      else
      {
        lpMem = 0;
        if ( (unsigned int)LKRhash::CLKRHashTable::FindKey(*((_QWORD *)this + 11), pv, &lpMem) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v12, pv);
          }
        }
        else
        {
          v13 = lpMem;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v12, pv);
          }
          v14 = (struct CNetworkItem *)*((_QWORD *)v13 + 1);
          *a3 = v14;
          (*(void (__fastcall **)(struct CNetworkItem *))(*(_QWORD *)v14 + 8LL))(v14);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 4, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 1) + 16LL))(*((_QWORD *)v13 + 1));
            CoTaskMemFree(*(LPVOID *)v13);
            operator delete(v13);
          }
        }
        CoTaskMemFree(pv);
      }
    }
    else
    {
      v10 = pv;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v9, v17);
      }
      v11 = (struct CNetworkItem *)*((_QWORD *)v10 + 1);
      *a3 = v11;
      (*(void (__fastcall **)(struct CNetworkItem *))(*(_QWORD *)v11 + 8LL))(v11);
      *a4 = 1;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 1) + 16LL))(*((_QWORD *)v10 + 1));
        CoTaskMemFree(*(LPVOID *)v10);
        operator delete(v10);
      }
    }
    CoTaskMemFree(v17);
  }
  return (unsigned int)ComputerNameAlloc;
}

```

## disassembly

```asm
0x180004074  push    rbp
0x180004076  push    rbx
0x180004077  push    rsi
0x180004078  push    rdi
0x180004079  push    r12
0x18000407b  push    r14
0x18000407d  push    r15
0x18000407f  mov     rbp, rsp
0x180004082  sub     rsp, 20h
0x180004086  mov     r15, r9
0x180004089  mov     r12, r8
0x18000408c  mov     rsi, rdx
0x18000408f  mov     r14, rcx
0x180004092  mov     qword ptr [r8], 0
0x180004099  mov     dword ptr [r9], 0
0x1800040a0  mov     [rbp+arg_10], 0
0x1800040a8  mov     rax, [rdx]
0x1800040ab  lea     rdx, [rbp+arg_10]
0x1800040af  mov     rcx, rsi
0x1800040b2  mov     rax, [rax+20h]
0x1800040b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040bb  mov     ebx, eax
0x1800040bd  test    eax, eax
0x1800040bf  js      loc_180004294
0x1800040c5  mov     [rbp+pv], 0
0x1800040cd  lea     r8, [rbp+pv]
0x1800040d1  mov     rdx, [rbp+arg_10]
0x1800040d5  mov     rcx, [r14+50h]
0x1800040d9  call    ?FindKey@CLKRHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800040de  test    eax, eax
0x1800040e0  jnz     loc_18000416C
0x1800040e6  mov     rsi, [rbp+pv]
0x1800040ea  lea     rdi, WPP_GLOBAL_Control
0x1800040f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040f8  cmp     rcx, rdi
0x1800040fb  jz      short loc_180004119
0x1800040fd  cmp     byte ptr [rcx+19h], 5
0x180004101  jb      short loc_180004119
0x180004103  test    byte ptr [rcx+1Ch], 2
0x180004107  jz      short loc_180004119
0x180004109  lea     edx, [rax+0Eh]
0x18000410c  mov     r9, [rbp+arg_10]
0x180004110  mov     rcx, [rcx+10h]
0x180004114  call    WPP_SF_S
0x180004119  mov     rcx, [rsi+8]
0x18000411d  mov     [r12], rcx
0x180004121  mov     rax, [rcx]
0x180004124  mov     rax, [rax+8]
0x180004128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000412d  mov     dword ptr [r15], 1
0x180004134  or      eax, 0FFFFFFFFh
0x180004137  lock xadd [rsi+10h], eax
0x18000413c  cmp     eax, 1
0x18000413f  jnz     loc_18000428A
0x180004145  mov     rcx, [rsi+8]
0x180004149  mov     rax, [rcx]
0x18000414c  mov     rax, [rax+10h]
0x180004150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004155  mov     rcx, [rsi]; pv
0x180004158  call    cs:__imp_CoTaskMemFree
0x18000415e  nop
0x18000415f  mov     rcx, rsi; lpMem
0x180004162  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004167  jmp     loc_18000428A
0x18000416c  lea     rdi, WPP_GLOBAL_Control
0x180004173  mov     rcx, cs:WPP_GLOBAL_Control
0x18000417a  cmp     rcx, rdi
0x18000417d  jz      short loc_18000419D
0x18000417f  cmp     byte ptr [rcx+19h], 5
0x180004183  jb      short loc_18000419D
0x180004185  test    byte ptr [rcx+1Ch], 2
0x180004189  jz      short loc_18000419D
0x18000418b  mov     edx, 0Fh
0x180004190  mov     r9, [rbp+arg_10]
0x180004194  mov     rcx, [rcx+10h]
0x180004198  call    WPP_SF_S
0x18000419d  mov     [rbp+pv], 0
0x1800041a5  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1800041a9  mov     rcx, rsi; struct IFunctionInstance *
0x1800041ac  call    ?_GetComputerNameAlloc@CNetworkItemFactory@@CAJPEAUIFunctionInstance@@PEAPEAG@Z; CNetworkItemFactory::_GetComputerNameAlloc(IFunctionInstance *,ushort * *)
0x1800041b1  mov     ebx, eax
0x1800041b3  test    eax, eax
0x1800041b5  js      loc_18000427F
0x1800041bb  mov     [rbp+lpMem], 0
0x1800041c3  lea     r8, [rbp+lpMem]
0x1800041c7  mov     rdx, [rbp+pv]
0x1800041cb  mov     rcx, [r14+58h]
0x1800041cf  call    ?FindKey@CLKRHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800041d4  test    eax, eax
0x1800041d6  jnz     short loc_180004249
0x1800041d8  mov     rsi, [rbp+lpMem]
0x1800041dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041e3  cmp     rcx, rdi
0x1800041e6  jz      short loc_180004204
0x1800041e8  cmp     byte ptr [rcx+19h], 5
0x1800041ec  jb      short loc_180004204
0x1800041ee  test    byte ptr [rcx+1Ch], 2
0x1800041f2  jz      short loc_180004204
0x1800041f4  lea     edx, [rax+10h]
0x1800041f7  mov     r9, [rbp+pv]
0x1800041fb  mov     rcx, [rcx+10h]
0x1800041ff  call    WPP_SF_S
0x180004204  mov     rcx, [rsi+8]
0x180004208  mov     [r12], rcx
0x18000420c  mov     rax, [rcx]
0x18000420f  mov     rax, [rax+8]
0x180004213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004218  or      eax, 0FFFFFFFFh
0x18000421b  lock xadd [rsi+10h], eax
0x180004220  cmp     eax, 1
0x180004223  jnz     short loc_180004273
0x180004225  mov     rcx, [rsi+8]
0x180004229  mov     rax, [rcx]
0x18000422c  mov     rax, [rax+10h]
0x180004230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004235  mov     rcx, [rsi]; pv
0x180004238  call    cs:__imp_CoTaskMemFree
0x18000423e  nop
0x18000423f  mov     rcx, rsi; lpMem
0x180004242  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004247  jmp     short loc_180004273
0x180004249  mov     rcx, cs:WPP_GLOBAL_Control
0x180004250  cmp     rcx, rdi
0x180004253  jz      short loc_180004273
0x180004255  cmp     byte ptr [rcx+19h], 5
0x180004259  jb      short loc_180004273
0x18000425b  test    byte ptr [rcx+1Ch], 2
0x18000425f  jz      short loc_180004273
0x180004261  mov     edx, 11h
0x180004266  mov     r9, [rbp+pv]
0x18000426a  mov     rcx, [rcx+10h]
0x18000426e  call    WPP_SF_S
0x180004273  mov     rcx, [rbp+pv]; pv
0x180004277  call    cs:__imp_CoTaskMemFree
0x18000427d  jmp     short loc_18000428A
0x18000427f  xor     eax, eax
0x180004281  cmp     ebx, 80070648h
0x180004287  cmovz   ebx, eax
0x18000428a  mov     rcx, [rbp+arg_10]; pv
0x18000428e  call    cs:__imp_CoTaskMemFree
0x180004294  mov     eax, ebx
0x180004296  add     rsp, 20h
0x18000429a  pop     r15
0x18000429c  pop     r14
0x18000429e  pop     r12
0x1800042a0  pop     rdi
0x1800042a1  pop     rsi
0x1800042a2  pop     rbx
0x1800042a3  pop     rbp
0x1800042a4  retn
```
