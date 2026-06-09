# UpdateFileCountsMap(_FILE_ID_EXTD_DIR_INFORMATION *,std::map<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>> *)

- ea: `0x18001d608`
- end: `0x18001d6ba`
- name: `?UpdateFileCountsMap@@YAXPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001ad40`
- `0x18001d8b0`

## callees

- `0x180017dc8`
- `0x18001d608`

## pseudocode

```c
_QWORD *__fastcall UpdateFileCountsMap(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  bool v9; // cc
  _QWORD *result; // rax
  int v11; // [rsp+50h] [rbp+28h] BYREF

  v2 = *(_QWORD *)(a1 + 48);
  v11 = 5;
  v5 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a2, (__int64)&v11);
  *v5 += v2;
  v6 = *(_QWORD *)(a1 + 40);
  v11 = 6;
  v7 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a2, (__int64)&v11);
  *v7 += v6;
  v11 = 1;
  v8 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a2, (__int64)&v11);
  ++*v8;
  if ( *(__int64 *)(a1 + 40) > 1024 )
  {
    if ( *(__int64 *)(a1 + 40) > 4096 )
    {
      v9 = *(_QWORD *)(a1 + 40) <= 20971520LL;
      v11 = 45;
      if ( !v9 )
        v11 = 46;
    }
    else
    {
      v11 = 44;
    }
  }
  else
  {
    v11 = 43;
  }
  result = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a2, (__int64)&v11);
  ++*result;
  return result;
}

```

## disassembly

```asm
0x18001d608  push    rbp
0x18001d60a  push    rbx
0x18001d60b  push    rsi
0x18001d60c  push    rdi
0x18001d60d  mov     rbp, rsp
0x18001d610  sub     rsp, 28h
0x18001d614  mov     rbx, [rcx+30h]
0x18001d618  mov     rsi, rdx
0x18001d61b  mov     rdi, rcx
0x18001d61e  mov     [rbp+arg_0], 5
0x18001d625  mov     rcx, rsi
0x18001d628  lea     rdx, [rbp+arg_0]
0x18001d62c  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d631  lea     rdx, [rbp+arg_0]
0x18001d635  mov     rcx, rsi
0x18001d638  add     [rax], rbx
0x18001d63b  mov     rbx, [rdi+28h]
0x18001d63f  mov     [rbp+arg_0], 6
0x18001d646  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d64b  lea     rdx, [rbp+arg_0]
0x18001d64f  mov     rcx, rsi
0x18001d652  add     [rax], rbx
0x18001d655  mov     [rbp+arg_0], 1
0x18001d65c  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d661  inc     qword ptr [rax]
0x18001d664  cmp     qword ptr [rdi+28h], 400h
0x18001d66c  jg      short loc_18001D677
0x18001d66e  mov     [rbp+arg_0], 2Bh ; '+'
0x18001d675  jmp     short loc_18001D6A2
0x18001d677  cmp     qword ptr [rdi+28h], 1000h
0x18001d67f  jg      short loc_18001D68A
0x18001d681  mov     [rbp+arg_0], 2Ch ; ','
0x18001d688  jmp     short loc_18001D6A2
0x18001d68a  cmp     qword ptr [rdi+28h], 1400000h
0x18001d692  mov     [rbp+arg_0], 2Dh ; '-'
0x18001d699  jle     short loc_18001D6A2
0x18001d69b  mov     [rbp+arg_0], 2Eh ; '.'
0x18001d6a2  lea     rdx, [rbp+arg_0]
0x18001d6a6  mov     rcx, rsi
0x18001d6a9  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d6ae  inc     qword ptr [rax]
0x18001d6b1  add     rsp, 28h
0x18001d6b5  pop     rdi
0x18001d6b6  pop     rsi
0x18001d6b7  pop     rbx
0x18001d6b8  pop     rbp
0x18001d6b9  retn
```
