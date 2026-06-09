# _lambda_fbd43cb40cbfca8789c624713de35da6_::operator()

- ea: `0x1800050d0`
- end: `0x1800051a1`
- name: `_lambda_fbd43cb40cbfca8789c624713de35da6_::operator()`
- size: `209`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002e88`
- `0x180003760`
- `0x180004fa0`

## callees

- `0x180004500`
- `0x1800050d0`
- `0x180011b9c`
- `0x18001659e`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180005133`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180005133`

## pseudocode

```c
int __fastcall lambda_fbd43cb40cbfca8789c624713de35da6_::operator()(__int64 *a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  const WCHAR *lpString2; // rax
  const WCHAR *v7; // r8
  size_t v8; // rax
  size_t v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r9

  v3 = *a1;
  v5 = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
  lpString2 = (const WCHAR *)(v5 + 24);
  if ( *(_QWORD *)(v5 + 48) > 7u )
    lpString2 = *(const WCHAR **)lpString2;
  v7 = (const WCHAR *)(v3 + 24);
  if ( *(_QWORD *)(v3 + 48) > 7u )
    v7 = *(const WCHAR **)v7;
  LODWORD(v8) = CompareStringEx(&LocaleName, 1u, v7, *(_DWORD *)(v3 + 40), lpString2, *(_DWORD *)(v5 + 40), 0, 0, 0);
  if ( (_DWORD)v8 == 2 )
  {
    v8 = *(_QWORD *)(v5 + 8) - *(_QWORD *)v5;
    v9 = *(_QWORD *)(v3 + 8) - *(_QWORD *)v3;
    if ( v9 >= v8 && v9 <= v8 )
    {
      LODWORD(v8) = memcmp_0(*(const void **)v3, *(const void **)v5, v9);
      if ( !(_DWORD)v8 )
      {
        v10 = a1[1];
        v11 = *(_QWORD *)(v10 + 8);
        if ( v11 == *(_QWORD *)(v10 + 16) )
        {
          LODWORD(v8) = std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Emplace_reallocate<std::shared_ptr<Broker::BrokerEvent> const &>(
                          a1[1],
                          *(_QWORD *)(v10 + 8),
                          a2);
        }
        else
        {
          LODWORD(v8) = std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(v11, a2);
          *(_QWORD *)(v12 + 8) += 16LL;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800050d0  push    rbx
0x1800050d2  push    rsi
0x1800050d3  push    rdi
0x1800050d4  push    r14
0x1800050d6  sub     rsp, 58h
0x1800050da  mov     rax, [rdx]
0x1800050dd  mov     r14, rcx
0x1800050e0  mov     rbx, [rcx]
0x1800050e3  mov     rsi, rdx
0x1800050e6  mov     rdi, [rax+30h]
0x1800050ea  cmp     qword ptr [rdi+30h], 7
0x1800050ef  lea     rax, [rdi+18h]
0x1800050f3  mov     ecx, [rdi+28h]
0x1800050f6  jbe     short loc_1800050FB
0x1800050f8  mov     rax, [rax]
0x1800050fb  cmp     qword ptr [rbx+30h], 7
0x180005100  lea     r8, [rbx+18h]
0x180005104  jbe     short loc_180005109
0x180005106  mov     r8, [r8]; lpString1
0x180005109  mov     r9d, [rbx+28h]; cchCount1
0x18000510d  xor     edx, edx
0x18000510f  mov     [rsp+78h+lParam], rdx; lParam
0x180005114  mov     [rsp+78h+lpReserved], rdx; lpReserved
0x180005119  mov     [rsp+78h+lpVersionInformation], rdx; lpVersionInformation
0x18000511e  mov     edx, 1; dwCmpFlags
0x180005123  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180005127  lea     rcx, LocaleName; lpLocaleName
0x18000512e  mov     [rsp+78h+lpString2], rax; lpString2
0x180005133  call    cs:__imp_CompareStringEx
0x180005139  cmp     eax, 2
0x18000513c  jnz     short loc_180005162
0x18000513e  mov     rdx, [rdi]; Buf2
0x180005141  mov     rax, [rdi+8]
0x180005145  mov     rcx, [rbx]; Buf1
0x180005148  sub     rax, rdx
0x18000514b  mov     r8, [rbx+8]
0x18000514f  sub     r8, rcx; Size
0x180005152  cmp     r8, rax
0x180005155  jb      short loc_180005162
0x180005157  ja      short loc_180005162
0x180005159  call    memcmp_0
0x18000515e  test    eax, eax
0x180005160  jz      short loc_18000516C
0x180005162  add     rsp, 58h
0x180005166  pop     r14
0x180005168  pop     rdi
0x180005169  pop     rsi
0x18000516a  pop     rbx
0x18000516b  retn
0x18000516c  mov     r9, [r14+8]
0x180005170  mov     rcx, [r9+8]
0x180005174  cmp     rcx, [r9+10h]
0x180005178  jz      short loc_180005191
0x18000517a  mov     rdx, rsi
0x18000517d  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x180005182  add     qword ptr [r9+8], 10h
0x180005187  add     rsp, 58h
0x18000518b  pop     r14
0x18000518d  pop     rdi
0x18000518e  pop     rsi
0x18000518f  pop     rbx
0x180005190  retn
0x180005191  mov     rdx, rcx
0x180005194  mov     r8, rsi
0x180005197  mov     rcx, r9
0x18000519a  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VBrokerEvent@Broker@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Emplace_reallocate<std::shared_ptr<Broker::BrokerEvent> const &>(std::shared_ptr<Broker::BrokerEvent> * const,std::shared_ptr<Broker::BrokerEvent> const &)
0x18000519f  jmp     short loc_180005162
```
