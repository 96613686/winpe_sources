# CXMLReader::ProcessUpdate(CXMLRowset *,SYMBOL_TYPE)

- ea: `0x1800276d0`
- end: `0x180027834`
- name: `?ProcessUpdate@CXMLReader@@AEAAJPEAVCXMLRowset@@W4SYMBOL_TYPE@@@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180025654`

## callees

- `0x180025654`
- `0x180026270`
- `0x1800276d0`
- `0x180028ee0`

## pseudocode

```c
__int64 __fastcall CXMLReader::ProcessUpdate(__int64 a1, struct CXMLRowset *a2)
{
  __int64 *v2; // rax
  int v3; // r14d
  __int64 v6; // rsi
  unsigned int v7; // ebp
  unsigned int v8; // r15d
  __int64 v9; // rdi
  int v10; // eax
  unsigned int v11; // r8d
  unsigned __int16 *v12; // rdx
  CCollectionList *v13; // rcx
  bool v14; // zf
  unsigned __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  int v17; // [rsp+48h] [rbp-40h]
  int v18; // [rsp+4Ch] [rbp-3Ch]
  __int64 v19; // [rsp+50h] [rbp-38h]
  unsigned __int64 v20; // [rsp+90h] [rbp+8h] BYREF

  v2 = *(__int64 **)(a1 + 424);
  v3 = 0;
  v6 = *v2;
  v7 = 1;
  v8 = *(_DWORD *)(*v2 + 24);
  *(_DWORD *)(a1 + 476) = 8;
  while ( v7 < v8 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 424) + 8LL * v7);
    if ( *(_QWORD *)(v9 + 16) == v6 && *(_DWORD *)(v9 + 8) == 1 )
    {
      if ( CXMLReader::IsMatch(
             a1,
             *(unsigned __int16 **)(v9 + 32),
             *(_DWORD *)v9,
             *(_DWORD *)(v9 + 4),
             (wchar_t *)&wszOriginal,
             8,
             3) )
      {
        v6 = v9;
      }
      else
      {
        v10 = *(_DWORD *)(v9 + 44);
        v11 = *(_DWORD *)v9;
        v12 = *(unsigned __int16 **)(v9 + 32);
        v18 = 0;
        v16 = 0;
        v20 = 0;
        v13 = *(CCollectionList **)(a1 + 136);
        v19 = v9;
        v17 = v10;
        CCollectionList::LookUpByKey(v13, v12, v11, &v20);
        *(_QWORD *)(a1 + 456) = v20;
        *(_QWORD *)(a1 + 136) = *((_QWORD *)a2 + 79);
        v3 = CXMLReader::Fetch((CXMLReader *)a1, a2, (__int64)&v16);
        if ( v3 < 0 )
          return (unsigned int)v3;
        v14 = *(_DWORD *)(a1 + 476) == 8;
        *(_QWORD *)(a1 + 136) = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 48LL);
        if ( v14 )
        {
          *(_DWORD *)(a1 + 476) = 2;
          v6 = *(_QWORD *)(v6 + 16);
        }
      }
    }
    ++v7;
  }
  *(_DWORD *)(a1 + 476) = 8;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800276d0  mov     [rsp+arg_8], rbx
0x1800276d5  mov     [rsp+arg_10], rbp
0x1800276da  push    rsi
0x1800276db  push    rdi
0x1800276dc  push    r13
0x1800276de  push    r14
0x1800276e0  push    r15
0x1800276e2  sub     rsp, 60h
0x1800276e6  mov     rax, [rcx+1A8h]
0x1800276ed  xor     r14d, r14d
0x1800276f0  mov     r13, rdx
0x1800276f3  mov     rbx, rcx
0x1800276f6  mov     rsi, [rax]
0x1800276f9  lea     ebp, [r14+1]
0x1800276fd  mov     r15d, [rsi+18h]
0x180027701  mov     dword ptr [rcx+1DCh], 8
0x18002770b  cmp     ebp, r15d
0x18002770e  jnb     loc_18002780E
0x180027714  mov     rax, [rbx+1A8h]
0x18002771b  mov     ecx, ebp
0x18002771d  mov     rdi, [rax+rcx*8]
0x180027721  cmp     [rdi+10h], rsi
0x180027725  jnz     loc_180027807
0x18002772b  cmp     dword ptr [rdi+8], 1
0x18002772f  jnz     loc_180027807
0x180027735  mov     r9d, [rdi+4]
0x180027739  lea     rax, ?wszOriginal@@3PAGA; "original"
0x180027740  mov     r8d, [rdi]
0x180027743  mov     rcx, rbx
0x180027746  mov     rdx, [rdi+20h]
0x18002774a  mov     [rsp+88h+var_58], 3
0x180027752  mov     [rsp+88h+var_60], 8
0x18002775a  mov     [rsp+88h+var_68], rax
0x18002775f  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180027764  xor     ecx, ecx
0x180027766  test    al, al
0x180027768  jz      short loc_180027772
0x18002776a  mov     rsi, rdi
0x18002776d  jmp     loc_180027807
0x180027772  mov     eax, [rdi+2Ch]
0x180027775  lea     r9, [rsp+88h+arg_0]; unsigned __int64 *
0x18002777d  mov     r8d, [rdi]; unsigned int
0x180027780  mov     rdx, [rdi+20h]; unsigned __int16 *
0x180027784  mov     [rsp+88h+var_3C], ecx
0x180027788  mov     [rsp+88h+var_48], rcx
0x18002778d  mov     [rsp+88h+arg_0], rcx
0x180027795  mov     rcx, [rbx+88h]; this
0x18002779c  mov     [rsp+88h+var_38], rdi
0x1800277a1  mov     [rsp+88h+var_40], eax
0x1800277a5  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800277aa  mov     rax, [rsp+88h+arg_0]
0x1800277b2  lea     r8, [rsp+88h+var_48]; unsigned __int64
0x1800277b7  mov     [rbx+1C8h], rax
0x1800277be  mov     rdx, r13; struct CXMLRowset *
0x1800277c1  mov     rax, [r13+278h]
0x1800277c8  mov     rcx, rbx; this
0x1800277cb  mov     [rbx+88h], rax
0x1800277d2  call    ?Fetch@CXMLReader@@QEAAJPEAVCXMLRowset@@_K@Z; CXMLReader::Fetch(CXMLRowset *,unsigned __int64)
0x1800277d7  mov     r14d, eax
0x1800277da  test    eax, eax
0x1800277dc  js      short loc_180027818
0x1800277de  cmp     dword ptr [rbx+1DCh], 8
0x1800277e5  mov     rcx, [rbx+88h]
0x1800277ec  mov     rdx, [rcx+30h]
0x1800277f0  mov     [rbx+88h], rdx
0x1800277f7  jnz     short loc_180027807
0x1800277f9  mov     dword ptr [rbx+1DCh], 2
0x180027803  mov     rsi, [rsi+10h]
0x180027807  inc     ebp
0x180027809  jmp     loc_18002770B
0x18002780e  mov     dword ptr [rbx+1DCh], 8
0x180027818  lea     r11, [rsp+88h+var_28]
0x18002781d  mov     eax, r14d
0x180027820  mov     rbx, [r11+38h]
0x180027824  mov     rbp, [r11+40h]
0x180027828  mov     rsp, r11
0x18002782b  pop     r15
0x18002782d  pop     r14
0x18002782f  pop     r13
0x180027831  pop     rdi
0x180027832  pop     rsi
0x180027833  retn
```
