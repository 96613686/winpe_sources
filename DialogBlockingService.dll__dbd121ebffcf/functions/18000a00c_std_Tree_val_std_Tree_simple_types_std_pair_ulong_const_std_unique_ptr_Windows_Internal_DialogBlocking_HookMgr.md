# std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>,void *> *>,std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>,void *> * const)

- ea: `0x18000a00c`
- end: `0x18000a235`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a65c`

## callees

- `0x18000a00c`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r10
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *i; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v5 = a3;
      if ( v5 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v5[2] = a3;
      if ( v5 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v6 = *(_QWORD *)(a3 + 8);
    for ( i = (_QWORD *)a3; ; v6 = i[1] )
    {
      if ( *(_BYTE *)(v6 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return a3;
      }
      v8 = i[1];
      v9 = *(__int64 **)(v8 + 8);
      v10 = *v9;
      if ( v8 == *v9 )
      {
        v10 = v9[2];
        if ( !*(_BYTE *)(v10 + 24) )
          goto LABEL_29;
        v11 = *(_QWORD **)(v8 + 16);
        if ( i == v11 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)(v8 + 16) = *v11;
          if ( !*(_BYTE *)(*v11 + 25LL) )
            *(_QWORD *)(*v11 + 8LL) = v8;
          v11[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v11;
          }
          else
          {
            v12 = *(_QWORD **)(v8 + 8);
            if ( v8 == *v12 )
              *v12 = v11;
            else
              v12[2] = v11;
          }
          *v11 = v8;
          *(_QWORD *)(v8 + 8) = v11;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)*v13;
        *v13 = *(_QWORD *)(*v13 + 16LL);
        v15 = v14[2];
        if ( !*(_BYTE *)(v15 + 25) )
          *(_QWORD *)(v15 + 8) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v16 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)v16[2] )
            v16[2] = v14;
          else
            *v16 = v14;
        }
        v14[2] = v13;
      }
      else
      {
        if ( !*(_BYTE *)(v10 + 24) )
        {
LABEL_29:
          *(_BYTE *)(v8 + 24) = 1;
          *(_BYTE *)(v10 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
          i = *(_QWORD **)(i[1] + 8LL);
          continue;
        }
        v17 = *(_QWORD **)v8;
        if ( i == *(_QWORD **)v8 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)v8 = v17[2];
          v18 = v17[2];
          if ( !*(_BYTE *)(v18 + 25) )
            *(_QWORD *)(v18 + 8) = v8;
          v17[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v17;
          }
          else
          {
            v19 = *(_QWORD **)(v8 + 8);
            if ( v8 == v19[2] )
              v19[2] = v17;
            else
              *v19 = v17;
          }
          v17[2] = v8;
          *(_QWORD *)(v8 + 8) = v17;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)v13[2];
        v13[2] = *v14;
        if ( !*(_BYTE *)(*v14 + 25LL) )
          *(_QWORD *)(*v14 + 8LL) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v20 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)*v20 )
            *v20 = v14;
          else
            v20[2] = v14;
        }
        *v14 = v13;
      }
      v13[1] = v14;
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return a3;
}

```

## disassembly

```asm
0x18000a00c  mov     [rsp+arg_0], rbx
0x18000a011  inc     qword ptr [rcx+8]
0x18000a015  mov     r11, rcx
0x18000a018  mov     r10, [rcx]
0x18000a01b  mov     rax, [rdx]
0x18000a01e  mov     [r8+8], rax
0x18000a022  cmp     rax, r10
0x18000a025  jnz     short loc_18000A03C
0x18000a027  mov     [r10], r8
0x18000a02a  mov     [r10+8], r8
0x18000a02e  mov     [r10+10h], r8
0x18000a032  mov     byte ptr [r8+18h], 1
0x18000a037  jmp     loc_18000A22C
0x18000a03c  xor     ebx, ebx
0x18000a03e  cmp     [rdx+8], ebx
0x18000a041  jnz     short loc_18000A053
0x18000a043  mov     [rax+10h], r8
0x18000a047  cmp     rax, [r10+10h]
0x18000a04b  jnz     short loc_18000A05E
0x18000a04d  mov     [r10+10h], r8
0x18000a051  jmp     short loc_18000A05E
0x18000a053  mov     [rax], r8
0x18000a056  cmp     rax, [r10]
0x18000a059  jnz     short loc_18000A05E
0x18000a05b  mov     [r10], r8
0x18000a05e  mov     rax, [r8+8]
0x18000a062  mov     rdx, r8
0x18000a065  jmp     loc_18000A21B
0x18000a06a  mov     rcx, [rdx+8]
0x18000a06e  mov     r9, [rcx+8]
0x18000a072  mov     rax, [r9]
0x18000a075  cmp     rcx, rax
0x18000a078  jnz     loc_18000A13F
0x18000a07e  mov     rax, [r9+10h]
0x18000a082  cmp     [rax+18h], bl
0x18000a085  jz      loc_18000A144
0x18000a08b  mov     r9, [rcx+10h]
0x18000a08f  cmp     rdx, r9
0x18000a092  jnz     short loc_18000A0DA
0x18000a094  mov     rax, [r9]
0x18000a097  mov     rdx, rcx
0x18000a09a  mov     [rcx+10h], rax
0x18000a09e  mov     rax, [r9]
0x18000a0a1  cmp     [rax+19h], bl
0x18000a0a4  jnz     short loc_18000A0AA
0x18000a0a6  mov     [rax+8], rcx
0x18000a0aa  mov     rax, [rcx+8]
0x18000a0ae  mov     [r9+8], rax
0x18000a0b2  mov     rax, [r11]
0x18000a0b5  cmp     rcx, [rax+8]
0x18000a0b9  jnz     short loc_18000A0C1
0x18000a0bb  mov     [rax+8], r9
0x18000a0bf  jmp     short loc_18000A0D3
0x18000a0c1  mov     rax, [rcx+8]
0x18000a0c5  cmp     rcx, [rax]
0x18000a0c8  jnz     short loc_18000A0CF
0x18000a0ca  mov     [rax], r9
0x18000a0cd  jmp     short loc_18000A0D3
0x18000a0cf  mov     [rax+10h], r9
0x18000a0d3  mov     [r9], rcx
0x18000a0d6  mov     [rcx+8], r9
0x18000a0da  mov     rax, [rdx+8]
0x18000a0de  mov     byte ptr [rax+18h], 1
0x18000a0e2  mov     rax, [rdx+8]
0x18000a0e6  mov     rcx, [rax+8]
0x18000a0ea  mov     [rcx+18h], bl
0x18000a0ed  mov     rax, [rdx+8]
0x18000a0f1  mov     rcx, [rax+8]
0x18000a0f5  mov     r9, [rcx]
0x18000a0f8  mov     rax, [r9+10h]
0x18000a0fc  mov     [rcx], rax
0x18000a0ff  mov     rax, [r9+10h]
0x18000a103  cmp     [rax+19h], bl
0x18000a106  jnz     short loc_18000A10C
0x18000a108  mov     [rax+8], rcx
0x18000a10c  mov     rax, [rcx+8]
0x18000a110  mov     [r9+8], rax
0x18000a114  mov     rax, [r11]
0x18000a117  cmp     rcx, [rax+8]
0x18000a11b  jnz     short loc_18000A123
0x18000a11d  mov     [rax+8], r9
0x18000a121  jmp     short loc_18000A136
0x18000a123  mov     rax, [rcx+8]
0x18000a127  cmp     rcx, [rax+10h]
0x18000a12b  jnz     short loc_18000A133
0x18000a12d  mov     [rax+10h], r9
0x18000a131  jmp     short loc_18000A136
0x18000a133  mov     [rax], r9
0x18000a136  mov     [r9+10h], rcx
0x18000a13a  jmp     loc_18000A213
0x18000a13f  cmp     [rax+18h], bl
0x18000a142  jnz     short loc_18000A164
0x18000a144  mov     byte ptr [rcx+18h], 1
0x18000a148  mov     byte ptr [rax+18h], 1
0x18000a14c  mov     rax, [rdx+8]
0x18000a150  mov     rcx, [rax+8]
0x18000a154  mov     [rcx+18h], bl
0x18000a157  mov     rax, [rdx+8]
0x18000a15b  mov     rdx, [rax+8]
0x18000a15f  jmp     loc_18000A217
0x18000a164  mov     r9, [rcx]
0x18000a167  cmp     rdx, r9
0x18000a16a  jnz     short loc_18000A1B5
0x18000a16c  mov     rax, [r9+10h]
0x18000a170  mov     rdx, rcx
0x18000a173  mov     [rcx], rax
0x18000a176  mov     rax, [r9+10h]
0x18000a17a  cmp     [rax+19h], bl
0x18000a17d  jnz     short loc_18000A183
0x18000a17f  mov     [rax+8], rcx
0x18000a183  mov     rax, [rcx+8]
0x18000a187  mov     [r9+8], rax
0x18000a18b  mov     rax, [r11]
0x18000a18e  cmp     rcx, [rax+8]
0x18000a192  jnz     short loc_18000A19A
0x18000a194  mov     [rax+8], r9
0x18000a198  jmp     short loc_18000A1AD
0x18000a19a  mov     rax, [rcx+8]
0x18000a19e  cmp     rcx, [rax+10h]
0x18000a1a2  jnz     short loc_18000A1AA
0x18000a1a4  mov     [rax+10h], r9
0x18000a1a8  jmp     short loc_18000A1AD
0x18000a1aa  mov     [rax], r9
0x18000a1ad  mov     [r9+10h], rcx
0x18000a1b1  mov     [rcx+8], r9
0x18000a1b5  mov     rax, [rdx+8]
0x18000a1b9  mov     byte ptr [rax+18h], 1
0x18000a1bd  mov     rax, [rdx+8]
0x18000a1c1  mov     rcx, [rax+8]
0x18000a1c5  mov     [rcx+18h], bl
0x18000a1c8  mov     rax, [rdx+8]
0x18000a1cc  mov     rcx, [rax+8]
0x18000a1d0  mov     r9, [rcx+10h]
0x18000a1d4  mov     rax, [r9]
0x18000a1d7  mov     [rcx+10h], rax
0x18000a1db  mov     rax, [r9]
0x18000a1de  cmp     [rax+19h], bl
0x18000a1e1  jnz     short loc_18000A1E7
0x18000a1e3  mov     [rax+8], rcx
0x18000a1e7  mov     rax, [rcx+8]
0x18000a1eb  mov     [r9+8], rax
0x18000a1ef  mov     rax, [r11]
0x18000a1f2  cmp     rcx, [rax+8]
0x18000a1f6  jnz     short loc_18000A1FE
0x18000a1f8  mov     [rax+8], r9
0x18000a1fc  jmp     short loc_18000A210
0x18000a1fe  mov     rax, [rcx+8]
0x18000a202  cmp     rcx, [rax]
0x18000a205  jnz     short loc_18000A20C
0x18000a207  mov     [rax], r9
0x18000a20a  jmp     short loc_18000A210
0x18000a20c  mov     [rax+10h], r9
0x18000a210  mov     [r9], rcx
0x18000a213  mov     [rcx+8], r9
0x18000a217  mov     rax, [rdx+8]
0x18000a21b  cmp     [rax+18h], bl
0x18000a21e  jz      loc_18000A06A
0x18000a224  mov     rax, [r10+8]
0x18000a228  mov     byte ptr [rax+18h], 1
0x18000a22c  mov     rbx, [rsp+arg_0]
0x18000a231  mov     rax, r8
0x18000a234  retn
```
