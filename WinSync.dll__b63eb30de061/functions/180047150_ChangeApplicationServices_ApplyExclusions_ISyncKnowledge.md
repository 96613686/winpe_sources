# ChangeApplicationServices::ApplyExclusions(ISyncKnowledge *)

- ea: `0x180047150`
- end: `0x1800472ba`
- name: `?ApplyExclusions@ChangeApplicationServices@@AEAAJPEAUISyncKnowledge@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncKnowledge *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180047900`
- `0x180047a60`

## callees

- `0x1800084ec`
- `0x18001a038`
- `0x18001ae20`
- `0x1800209f4`
- `0x180047150`
- `0x180094010`

## string_xrefs

- `0x180047183`: `ChangeApplicationServices::ApplyExclusions`
- `0x180047292`: `ChangeApplicationServices::ApplyExclusions`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ApplyExclusions(
        ChangeApplicationServices *this,
        struct ISyncKnowledge *a2)
{
  int v4; // ebx
  __int64 NextElement; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  _QWORD v13[2]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v14[7]; // [rsp+40h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ApplyExclusions");
  }
  v4 = 0;
  v13[0] = (char *)this + 176;
  v13[1] = 0;
  while ( 1 )
  {
    NextElement = TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(v13);
    v6 = NextElement;
    if ( !NextElement )
      break;
    v7 = *(_QWORD *)(NextElement + 16);
    if ( *(_DWORD *)(v7 + 72) )
    {
      v14[0] = v7 + 56;
      v14[1] = 0;
      while ( 1 )
      {
        v9 = TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(v14);
        if ( !v9 )
          break;
        if ( *(_DWORD *)(*(_QWORD *)(v9 + 16) + 20LL) )
        {
          v10 = *(_QWORD *)(v9 + 8);
          v11 = *(_QWORD *)(v6 + 8);
          if ( (*(_DWORD *)(v9 + 4) & 0x20000) == 0 )
            v10 += 4;
          if ( (*(_DWORD *)(v6 + 4) & 0x20000) == 0 )
            v11 += 4;
          v4 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64, __int64))a2->lpVtbl->ExcludeChangeUnit)(
                 a2,
                 v11,
                 v10);
        }
        if ( v4 < 0 )
          goto LABEL_21;
      }
    }
    else
    {
      if ( *(_DWORD *)(v7 + 20) )
      {
        v8 = *(_QWORD *)(v6 + 8);
        if ( (*(_DWORD *)(v6 + 4) & 0x20000) == 0 )
          v8 += 4;
        v4 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64))a2->lpVtbl->ExcludeItem)(a2, v8);
      }
LABEL_21:
      if ( v4 < 0 )
        break;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ApplyExclusions",
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047150  push    rbx
0x180047152  push    rsi
0x180047153  push    rdi
0x180047154  push    r14
0x180047156  sub     rsp, 58h
0x18004715a  mov     rsi, rdx
0x18004715d  mov     rdi, rcx
0x180047160  mov     rcx, cs:WPP_GLOBAL_Control
0x180047167  lea     r14, WPP_GLOBAL_Control
0x18004716e  cmp     rcx, r14
0x180047171  jz      short loc_18004719B
0x180047173  test    byte ptr [rcx+1Ch], 80h
0x180047177  jz      short loc_18004719B
0x180047179  cmp     byte ptr [rcx+19h], 5
0x18004717d  jb      short loc_18004719B
0x18004717f  mov     rcx, [rcx+10h]
0x180047183  lea     r9, aChangeapplicat_33; "ChangeApplicationServices::ApplyExclusi"...
0x18004718a  mov     edx, 34h ; '4'
0x18004718f  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180047196  call    WPP_SF_s
0x18004719b  xor     ebx, ebx
0x18004719d  lea     rax, [rdi+0B0h]
0x1800471a4  mov     [rsp+78h+var_48], rax
0x1800471a9  mov     [rsp+78h+var_40], rbx
0x1800471ae  lea     rcx, [rsp+78h+var_48]
0x1800471b3  call    ?GetNextElement@?$TableEnumerator@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::GetNextElement(void)
0x1800471b8  mov     rdi, rax
0x1800471bb  test    rax, rax
0x1800471be  jz      loc_180047276
0x1800471c4  mov     rax, [rax+10h]
0x1800471c8  lea     rcx, [rax+38h]
0x1800471cc  cmp     dword ptr [rcx+10h], 0
0x1800471d0  jnz     short loc_180047205
0x1800471d2  cmp     dword ptr [rax+14h], 0
0x1800471d6  jz      loc_18004726E
0x1800471dc  mov     rdx, [rdi+8]
0x1800471e0  mov     rcx, rsi
0x1800471e3  mov     r8, [rsi]
0x1800471e6  test    dword ptr [rdi+4], 20000h
0x1800471ed  lea     rax, [rdx+4]
0x1800471f1  cmovz   rdx, rax
0x1800471f5  mov     rax, [r8+88h]
0x1800471fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047201  mov     ebx, eax
0x180047203  jmp     short loc_18004726E
0x180047205  mov     [rsp+78h+var_38], rcx
0x18004720a  mov     [rsp+78h+var_30], 0
0x180047213  test    ebx, ebx
0x180047215  js      short loc_180047276
0x180047217  lea     rcx, [rsp+78h+var_38]
0x18004721c  call    ?GetNextElement@?$TableEnumerator@VSyncId@@HVDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@HVDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(void)
0x180047221  test    rax, rax
0x180047224  jz      short loc_1800471AE
0x180047226  mov     rcx, [rax+10h]
0x18004722a  cmp     dword ptr [rcx+14h], 0
0x18004722e  jz      short loc_18004726A
0x180047230  test    dword ptr [rax+4], 20000h
0x180047237  mov     rcx, rsi
0x18004723a  mov     r8, [rax+8]
0x18004723e  mov     rdx, [rdi+8]
0x180047242  mov     r9, [rsi]
0x180047245  lea     rax, [r8+4]
0x180047249  cmovz   r8, rax
0x18004724d  test    dword ptr [rdi+4], 20000h
0x180047254  lea     rax, [rdx+4]
0x180047258  cmovz   rdx, rax
0x18004725c  mov     rax, [r9+90h]
0x180047263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047268  mov     ebx, eax
0x18004726a  test    ebx, ebx
0x18004726c  jns     short loc_180047217
0x18004726e  test    ebx, ebx
0x180047270  jns     loc_1800471AE
0x180047276  mov     rcx, cs:WPP_GLOBAL_Control
0x18004727d  cmp     rcx, r14
0x180047280  jz      short loc_1800472AE
0x180047282  test    byte ptr [rcx+1Ch], 80h
0x180047286  jz      short loc_1800472AE
0x180047288  cmp     byte ptr [rcx+19h], 5
0x18004728c  jb      short loc_1800472AE
0x18004728e  mov     rcx, [rcx+10h]
0x180047292  lea     r9, aChangeapplicat_33; "ChangeApplicationServices::ApplyExclusi"...
0x180047299  mov     edx, 35h ; '5'
0x18004729e  mov     [rsp+78h+var_58], ebx
0x1800472a2  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800472a9  call    WPP_SF_sD
0x1800472ae  mov     eax, ebx
0x1800472b0  add     rsp, 58h
0x1800472b4  pop     r14
0x1800472b6  pop     rdi
0x1800472b7  pop     rsi
0x1800472b8  pop     rbx
0x1800472b9  retn
```
