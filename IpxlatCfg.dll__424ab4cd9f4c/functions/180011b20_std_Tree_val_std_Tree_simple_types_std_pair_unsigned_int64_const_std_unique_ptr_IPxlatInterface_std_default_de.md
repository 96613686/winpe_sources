# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,void *> * const)

- ea: `0x180011b20`
- end: `0x180011d49`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e91c`

## callees

- `0x180011b20`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Insert_node(
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
0x180011b20  mov     [rsp+arg_0], rbx
0x180011b25  inc     qword ptr [rcx+8]
0x180011b29  mov     r11, rcx
0x180011b2c  mov     r10, [rcx]
0x180011b2f  mov     rax, [rdx]
0x180011b32  mov     [r8+8], rax
0x180011b36  cmp     rax, r10
0x180011b39  jnz     short loc_180011B50
0x180011b3b  mov     [r10], r8
0x180011b3e  mov     [r10+8], r8
0x180011b42  mov     [r10+10h], r8
0x180011b46  mov     byte ptr [r8+18h], 1
0x180011b4b  jmp     loc_180011D40
0x180011b50  xor     ebx, ebx
0x180011b52  cmp     [rdx+8], ebx
0x180011b55  jnz     short loc_180011B67
0x180011b57  mov     [rax+10h], r8
0x180011b5b  cmp     rax, [r10+10h]
0x180011b5f  jnz     short loc_180011B72
0x180011b61  mov     [r10+10h], r8
0x180011b65  jmp     short loc_180011B72
0x180011b67  mov     [rax], r8
0x180011b6a  cmp     rax, [r10]
0x180011b6d  jnz     short loc_180011B72
0x180011b6f  mov     [r10], r8
0x180011b72  mov     rax, [r8+8]
0x180011b76  mov     rdx, r8
0x180011b79  jmp     loc_180011D2F
0x180011b7e  mov     rcx, [rdx+8]
0x180011b82  mov     r9, [rcx+8]
0x180011b86  mov     rax, [r9]
0x180011b89  cmp     rcx, rax
0x180011b8c  jnz     loc_180011C53
0x180011b92  mov     rax, [r9+10h]
0x180011b96  cmp     [rax+18h], bl
0x180011b99  jz      loc_180011C58
0x180011b9f  mov     r9, [rcx+10h]
0x180011ba3  cmp     rdx, r9
0x180011ba6  jnz     short loc_180011BEE
0x180011ba8  mov     rax, [r9]
0x180011bab  mov     rdx, rcx
0x180011bae  mov     [rcx+10h], rax
0x180011bb2  mov     rax, [r9]
0x180011bb5  cmp     [rax+19h], bl
0x180011bb8  jnz     short loc_180011BBE
0x180011bba  mov     [rax+8], rcx
0x180011bbe  mov     rax, [rcx+8]
0x180011bc2  mov     [r9+8], rax
0x180011bc6  mov     rax, [r11]
0x180011bc9  cmp     rcx, [rax+8]
0x180011bcd  jnz     short loc_180011BD5
0x180011bcf  mov     [rax+8], r9
0x180011bd3  jmp     short loc_180011BE7
0x180011bd5  mov     rax, [rcx+8]
0x180011bd9  cmp     rcx, [rax]
0x180011bdc  jnz     short loc_180011BE3
0x180011bde  mov     [rax], r9
0x180011be1  jmp     short loc_180011BE7
0x180011be3  mov     [rax+10h], r9
0x180011be7  mov     [r9], rcx
0x180011bea  mov     [rcx+8], r9
0x180011bee  mov     rax, [rdx+8]
0x180011bf2  mov     byte ptr [rax+18h], 1
0x180011bf6  mov     rax, [rdx+8]
0x180011bfa  mov     rcx, [rax+8]
0x180011bfe  mov     [rcx+18h], bl
0x180011c01  mov     rax, [rdx+8]
0x180011c05  mov     rcx, [rax+8]
0x180011c09  mov     r9, [rcx]
0x180011c0c  mov     rax, [r9+10h]
0x180011c10  mov     [rcx], rax
0x180011c13  mov     rax, [r9+10h]
0x180011c17  cmp     [rax+19h], bl
0x180011c1a  jnz     short loc_180011C20
0x180011c1c  mov     [rax+8], rcx
0x180011c20  mov     rax, [rcx+8]
0x180011c24  mov     [r9+8], rax
0x180011c28  mov     rax, [r11]
0x180011c2b  cmp     rcx, [rax+8]
0x180011c2f  jnz     short loc_180011C37
0x180011c31  mov     [rax+8], r9
0x180011c35  jmp     short loc_180011C4A
0x180011c37  mov     rax, [rcx+8]
0x180011c3b  cmp     rcx, [rax+10h]
0x180011c3f  jnz     short loc_180011C47
0x180011c41  mov     [rax+10h], r9
0x180011c45  jmp     short loc_180011C4A
0x180011c47  mov     [rax], r9
0x180011c4a  mov     [r9+10h], rcx
0x180011c4e  jmp     loc_180011D27
0x180011c53  cmp     [rax+18h], bl
0x180011c56  jnz     short loc_180011C78
0x180011c58  mov     byte ptr [rcx+18h], 1
0x180011c5c  mov     byte ptr [rax+18h], 1
0x180011c60  mov     rax, [rdx+8]
0x180011c64  mov     rcx, [rax+8]
0x180011c68  mov     [rcx+18h], bl
0x180011c6b  mov     rax, [rdx+8]
0x180011c6f  mov     rdx, [rax+8]
0x180011c73  jmp     loc_180011D2B
0x180011c78  mov     r9, [rcx]
0x180011c7b  cmp     rdx, r9
0x180011c7e  jnz     short loc_180011CC9
0x180011c80  mov     rax, [r9+10h]
0x180011c84  mov     rdx, rcx
0x180011c87  mov     [rcx], rax
0x180011c8a  mov     rax, [r9+10h]
0x180011c8e  cmp     [rax+19h], bl
0x180011c91  jnz     short loc_180011C97
0x180011c93  mov     [rax+8], rcx
0x180011c97  mov     rax, [rcx+8]
0x180011c9b  mov     [r9+8], rax
0x180011c9f  mov     rax, [r11]
0x180011ca2  cmp     rcx, [rax+8]
0x180011ca6  jnz     short loc_180011CAE
0x180011ca8  mov     [rax+8], r9
0x180011cac  jmp     short loc_180011CC1
0x180011cae  mov     rax, [rcx+8]
0x180011cb2  cmp     rcx, [rax+10h]
0x180011cb6  jnz     short loc_180011CBE
0x180011cb8  mov     [rax+10h], r9
0x180011cbc  jmp     short loc_180011CC1
0x180011cbe  mov     [rax], r9
0x180011cc1  mov     [r9+10h], rcx
0x180011cc5  mov     [rcx+8], r9
0x180011cc9  mov     rax, [rdx+8]
0x180011ccd  mov     byte ptr [rax+18h], 1
0x180011cd1  mov     rax, [rdx+8]
0x180011cd5  mov     rcx, [rax+8]
0x180011cd9  mov     [rcx+18h], bl
0x180011cdc  mov     rax, [rdx+8]
0x180011ce0  mov     rcx, [rax+8]
0x180011ce4  mov     r9, [rcx+10h]
0x180011ce8  mov     rax, [r9]
0x180011ceb  mov     [rcx+10h], rax
0x180011cef  mov     rax, [r9]
0x180011cf2  cmp     [rax+19h], bl
0x180011cf5  jnz     short loc_180011CFB
0x180011cf7  mov     [rax+8], rcx
0x180011cfb  mov     rax, [rcx+8]
0x180011cff  mov     [r9+8], rax
0x180011d03  mov     rax, [r11]
0x180011d06  cmp     rcx, [rax+8]
0x180011d0a  jnz     short loc_180011D12
0x180011d0c  mov     [rax+8], r9
0x180011d10  jmp     short loc_180011D24
0x180011d12  mov     rax, [rcx+8]
0x180011d16  cmp     rcx, [rax]
0x180011d19  jnz     short loc_180011D20
0x180011d1b  mov     [rax], r9
0x180011d1e  jmp     short loc_180011D24
0x180011d20  mov     [rax+10h], r9
0x180011d24  mov     [r9], rcx
0x180011d27  mov     [rcx+8], r9
0x180011d2b  mov     rax, [rdx+8]
0x180011d2f  cmp     [rax+18h], bl
0x180011d32  jz      loc_180011B7E
0x180011d38  mov     rax, [r10+8]
0x180011d3c  mov     byte ptr [rax+18h], 1
0x180011d40  mov     rbx, [rsp+arg_0]
0x180011d45  mov     rax, r8
0x180011d48  retn
```
