# std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Insert_nohint<std::pair<ushort * const,CObject *>,std::_Nil>(bool,std::pair<ushort * const,CObject *> &&,std::_Nil)

- ea: `0x140008d80`
- end: `0x140008eb5`
- name: `??$_Insert_nohint@U?$pair@QEAGPEAVCObject@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGPEAVCObject@@@std@@@std@@@std@@@std@@_N@1@_N$$QEAU?$pair@QEAGPEAVCObject@@@1@U_Nil@1@@Z`
- size: `309`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64, LPCWSTR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009638`

## callees

- `0x140008c10`
- `0x140008d80`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140008daf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140008e6b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140008daf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140008e6b`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Insert_nohint<std::pair<unsigned short * const,CObject *>,std::_Nil>(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        LPCWSTR *a4)
{
  __int64 v7; // rbx
  __int64 v8; // rsi
  int v9; // eax
  unsigned int v10; // r14d
  __int64 *v11; // rsi
  __int64 result; // rax
  __int64 j; // rax
  __int64 i; // rax
  __int64 v15; // [rsp+70h] [rbp+8h] BYREF

  try
  {
    v7 = (__int64)*a1;
    v8 = (*a1)[1];
    if ( *(_BYTE *)(v8 + 25) )
    {
      LOBYTE(v10) = 1;
      v11 = *a1;
    }
    else
    {
      do
      {
        v7 = v8;
        v9 = lstrcmpW(*a4, *(LPCWSTR *)(v8 + 32));
        v10 = (unsigned int)v9 >> 31;
        if ( v9 >= 0 )
          v8 = *(_QWORD *)(v8 + 16);
        else
          v8 = *(_QWORD *)v8;
      }
      while ( !*(_BYTE *)(v8 + 25) );
      v11 = (__int64 *)v7;
      if ( v9 >= 0 )
        goto LABEL_25;
    }
    if ( v11 != (__int64 *)**a1 )
    {
      if ( *((_BYTE *)v11 + 25) )
      {
        v7 = v11[2];
      }
      else if ( *(_BYTE *)(*v11 + 25) )
      {
        for ( i = v11[1]; !*(_BYTE *)(i + 25) && v7 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
          v7 = i;
        if ( !*(_BYTE *)(v7 + 25) )
          v7 = i;
      }
      else
      {
        v7 = *v11;
        for ( j = *(_QWORD *)(*v11 + 16); !*(_BYTE *)(j + 25); j = *(_QWORD *)(v7 + 16) )
          v7 = *(_QWORD *)(v7 + 16);
      }
LABEL_25:
      if ( lstrcmpW(*(LPCWSTR *)(v7 + 32), *a4) >= 0 )
      {
        *(_QWORD *)a2 = v7;
        *(_BYTE *)(a2 + 8) = 0;
      }
      else
      {
        *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Insert_at<std::pair<unsigned short * const,CObject *>,std::_Nil>(
                           a1,
                           &v15,
                           v10,
                           v11,
                           (__int64)a4);
        *(_BYTE *)(a2 + 8) = 1;
      }
      return a2;
    }
    *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Insert_at<std::pair<unsigned short * const,CObject *>,std::_Nil>(
                       a1,
                       &v15,
                       1,
                       v11,
                       (__int64)a4);
    *(_BYTE *)(a2 + 8) = 1;
    result = a2;
  }
  catch ( ... )
  {
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x140008d80  push    rbx
0x140008d82  push    rsi
0x140008d83  push    rdi
0x140008d84  push    r12
0x140008d86  push    r14
0x140008d88  push    r15
0x140008d8a  sub     rsp, 38h
0x140008d8e  mov     r12, r9
0x140008d91  mov     rdi, rdx
0x140008d94  mov     r15, rcx
0x140008d97  mov     rbx, [rcx]
0x140008d9a  mov     rsi, [rbx+8]
0x140008d9e  cmp     byte ptr [rsi+19h], 0
0x140008da2  jnz     short loc_140008DDD
0x140008da4  mov     rbx, rsi
0x140008da7  mov     rdx, [rsi+20h]; lpString2
0x140008dab  mov     rcx, [r12]; lpString1
0x140008daf  call    cs:__imp_lstrcmpW
0x140008db5  mov     r14d, eax
0x140008db8  shr     r14d, 1Fh
0x140008dbc  test    r14b, r14b
0x140008dbf  jz      short loc_140008DC6
0x140008dc1  mov     rsi, [rsi]
0x140008dc4  jmp     short loc_140008DCA
0x140008dc6  mov     rsi, [rsi+10h]
0x140008dca  cmp     byte ptr [rsi+19h], 0
0x140008dce  jz      short loc_140008DA4
0x140008dd0  mov     rsi, rbx
0x140008dd3  test    r14b, r14b
0x140008dd6  jnz     short loc_140008DE3
0x140008dd8  jmp     loc_140008E63
0x140008ddd  mov     r14b, 1
0x140008de0  mov     rsi, rbx
0x140008de3  mov     rax, [r15]
0x140008de6  cmp     rsi, [rax]
0x140008de9  jnz     short loc_140008E15
0x140008deb  mov     [rsp+68h+var_48], r12
0x140008df0  mov     r9, rsi
0x140008df3  mov     r8b, 1
0x140008df6  lea     rdx, [rsp+68h+arg_0]
0x140008dfb  mov     rcx, r15
0x140008dfe  call    ??$_Insert_at@U?$pair@QEAGPEAVCObject@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGPEAVCObject@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@1@$$QEAU?$pair@QEAGPEAVCObject@@@1@U_Nil@1@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Insert_at<std::pair<ushort * const,CObject *>,std::_Nil>(bool,std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *,std::pair<ushort * const,CObject *> &&,std::_Nil)
0x140008e03  mov     rax, [rax]
0x140008e06  mov     [rdi], rax
0x140008e09  mov     byte ptr [rdi+8], 1
0x140008e0d  mov     rax, rdi
0x140008e10  jmp     loc_140008EA6
0x140008e15  cmp     byte ptr [rsi+19h], 0
0x140008e19  jz      short loc_140008E21
0x140008e1b  mov     rbx, [rsi+10h]
0x140008e1f  jmp     short loc_140008E63
0x140008e21  mov     rax, [rsi]
0x140008e24  cmp     byte ptr [rax+19h], 0
0x140008e28  jnz     short loc_140008E43
0x140008e2a  mov     rbx, rax
0x140008e2d  mov     rax, [rax+10h]
0x140008e31  jmp     short loc_140008E3B
0x140008e33  mov     rbx, [rbx+10h]
0x140008e37  mov     rax, [rbx+10h]
0x140008e3b  cmp     byte ptr [rax+19h], 0
0x140008e3f  jz      short loc_140008E33
0x140008e41  jmp     short loc_140008E63
0x140008e43  mov     rax, [rsi+8]
0x140008e47  jmp     short loc_140008E55
0x140008e49  cmp     rbx, [rax]
0x140008e4c  jnz     short loc_140008E5B
0x140008e4e  mov     rbx, rax
0x140008e51  mov     rax, [rax+8]
0x140008e55  cmp     byte ptr [rax+19h], 0
0x140008e59  jz      short loc_140008E49
0x140008e5b  cmp     byte ptr [rbx+19h], 0
0x140008e5f  cmovz   rbx, rax
0x140008e63  mov     rdx, [r12]; lpString2
0x140008e67  mov     rcx, [rbx+20h]; lpString1
0x140008e6b  call    cs:__imp_lstrcmpW
0x140008e71  test    eax, eax
0x140008e73  jns     short loc_140008E9C
0x140008e75  mov     [rsp+68h+var_48], r12
0x140008e7a  mov     r9, rsi
0x140008e7d  mov     r8b, r14b
0x140008e80  lea     rdx, [rsp+68h+arg_0]
0x140008e85  mov     rcx, r15
0x140008e88  call    ??$_Insert_at@U?$pair@QEAGPEAVCObject@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGPEAVCObject@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@1@$$QEAU?$pair@QEAGPEAVCObject@@@1@U_Nil@1@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Insert_at<std::pair<ushort * const,CObject *>,std::_Nil>(bool,std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *,std::pair<ushort * const,CObject *> &&,std::_Nil)
0x140008e8d  mov     rax, [rax]
0x140008e90  mov     [rdi], rax
0x140008e93  mov     byte ptr [rdi+8], 1
0x140008e97  mov     rax, rdi
0x140008e9a  jmp     short loc_140008EA6
0x140008e9c  mov     [rdi], rbx
0x140008e9f  mov     byte ptr [rdi+8], 0
0x140008ea3  mov     rax, rdi
0x140008ea6  add     rsp, 38h
0x140008eaa  pop     r15
0x140008eac  pop     r14
0x140008eae  pop     r12
0x140008eb0  pop     rdi
0x140008eb1  pop     rsi
0x140008eb2  pop     rbx
0x140008eb3  retn
```
