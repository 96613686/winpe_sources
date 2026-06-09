# GlobalRoutingInfoMethodEnumerator(_ROUTING_METHOD *,void *)

- ea: `0x140015030`
- end: `0x1400152a4`
- name: `?GlobalRoutingInfoMethodEnumerator@@YAHPEAU_ROUTING_METHOD@@PEAX@Z`
- size: `628`
- prototype: `__int64 __fastcall(struct _ROUTING_METHOD *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140015030`
- `0x14006aec0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140015149`
- `ole32!CoTaskMemFree` at `0x140015149`
- `ole32!StringFromIID` at `0x140015061`
- `ole32!StringFromIID` at `0x140015171`
- `ole32!StringFromIID` at `0x140015061`
- `ole32!StringFromIID` at `0x140015171`

## pseudocode

```c
__int64 __fastcall GlobalRoutingInfoMethodEnumerator(struct _ROUTING_METHOD *a1, unsigned int *a2)
{
  bool v3; // zf
  LPVOID v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // edx
  unsigned int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int v13; // r10d
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  int v17; // r9d
  __int64 v18; // rax
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // edx
  void *v22; // rcx
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  v3 = *a2 == 1;
  pv = 0;
  if ( v3 )
  {
    a2[1] += 48;
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    v5 = pv;
    v6 = -1;
    if ( pv )
    {
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)pv + v7) );
      v8 = 2 * v7 + 2;
    }
    else
    {
      v8 = 0;
    }
    v9 = v8 + a2[1];
    a2[1] = v9;
    v10 = *((_QWORD *)a1 + 7);
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v12 = 0;
    }
    v13 = v12 + v9;
    a2[1] = v12 + v9;
    v14 = *((_QWORD *)a1 + 8);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v16 = 0;
    }
    v17 = v16 + v13;
    a2[1] = v16 + v13;
    if ( *((_QWORD *)a1 + 11) == -572 )
    {
      v19 = 0;
    }
    else
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 572LL + 2 * v18) );
      v19 = 2 * v18 + 2;
    }
    a2[1] = v19 + v17;
    if ( *((_QWORD *)a1 + 11) == -52 )
    {
      v20 = 0;
    }
    else
    {
      do
        ++v6;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 52LL + 2 * v6) );
      v20 = 2 * v6 + 2;
    }
    v21 = v20 + v19 + v17;
    v22 = v5;
    a2[1] = v21;
    goto LABEL_27;
  }
  if ( *a2 == 2 )
  {
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    *(_DWORD *)(*((_QWORD *)a2 + 2) + 48LL * a2[1]) = 48;
    *(_DWORD *)(*((_QWORD *)a2 + 2) + 48LL * a2[1] + 4) = *((_DWORD *)a1 + 12);
    StoreString(
      (unsigned __int16 *)pv,
      (_QWORD *)(48LL * a2[1] + *((_QWORD *)a2 + 2) + 8LL),
      *((_QWORD *)a2 + 2),
      (_QWORD *)a2 + 1,
      a2[6]);
    StoreString(
      *((unsigned __int16 **)a1 + 8),
      (_QWORD *)(48LL * a2[1] + *((_QWORD *)a2 + 2) + 16LL),
      *((_QWORD *)a2 + 2),
      (_QWORD *)a2 + 1,
      a2[6]);
    StoreString(
      *((unsigned __int16 **)a1 + 7),
      (_QWORD *)(48LL * a2[1] + *((_QWORD *)a2 + 2) + 24LL),
      *((_QWORD *)a2 + 2),
      (_QWORD *)a2 + 1,
      a2[6]);
    StoreString(
      (unsigned __int16 *)(*((_QWORD *)a1 + 11) + 572LL),
      (_QWORD *)(48LL * a2[1] + *((_QWORD *)a2 + 2) + 32LL),
      *((_QWORD *)a2 + 2),
      (_QWORD *)a2 + 1,
      a2[6]);
    StoreString(
      (unsigned __int16 *)(*((_QWORD *)a1 + 11) + 52LL),
      (_QWORD *)(48LL * a2[1]++ + *((_QWORD *)a2 + 2) + 40LL),
      *((_QWORD *)a2 + 2),
      (_QWORD *)a2 + 1,
      a2[6]);
    v22 = pv;
LABEL_27:
    CoTaskMemFree(v22);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140015030  mov     rax, rsp
0x140015033  mov     [rax+8], rbx
0x140015037  mov     [rax+18h], rsi
0x14001503b  push    rdi
0x14001503c  sub     rsp, 30h
0x140015040  xor     ebx, ebx
0x140015042  mov     rdi, rdx
0x140015045  cmp     dword ptr [rdx], 1
0x140015048  mov     rsi, rcx
0x14001504b  mov     [rax+10h], rbx
0x14001504f  jnz     loc_14001515F
0x140015055  add     dword ptr [rdx+4], 30h ; '0'
0x140015059  add     rcx, 20h ; ' '; rclsid
0x14001505d  lea     rdx, [rax+10h]; lplpsz
0x140015061  call    cs:__imp_StringFromIID
0x140015068  nop     dword ptr [rax+rax+00h]
0x14001506d  mov     r8, [rsp+38h+pv]
0x140015072  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140015076  test    r8, r8
0x140015079  jz      short loc_140015092
0x14001507b  mov     rax, rcx
0x14001507e  inc     rax
0x140015081  cmp     [r8+rax*2], bx
0x140015086  jnz     short loc_14001507E
0x140015088  lea     rdx, ds:2[rax*2]
0x140015090  jmp     short loc_140015095
0x140015092  mov     rdx, rbx
0x140015095  mov     r9d, [rdi+4]
0x140015099  add     r9d, edx
0x14001509c  mov     [rdi+4], r9d
0x1400150a0  mov     rdx, [rsi+38h]
0x1400150a4  test    rdx, rdx
0x1400150a7  jz      short loc_1400150BF
0x1400150a9  mov     rax, rcx
0x1400150ac  inc     rax
0x1400150af  cmp     [rdx+rax*2], bx
0x1400150b3  jnz     short loc_1400150AC
0x1400150b5  lea     rax, ds:2[rax*2]
0x1400150bd  jmp     short loc_1400150C2
0x1400150bf  mov     rax, rbx
0x1400150c2  lea     r10d, [rax+r9]
0x1400150c6  mov     [rdi+4], r10d
0x1400150ca  mov     rdx, [rsi+40h]
0x1400150ce  test    rdx, rdx
0x1400150d1  jz      short loc_1400150E9
0x1400150d3  mov     rax, rcx
0x1400150d6  inc     rax
0x1400150d9  cmp     [rdx+rax*2], bx
0x1400150dd  jnz     short loc_1400150D6
0x1400150df  lea     rax, ds:2[rax*2]
0x1400150e7  jmp     short loc_1400150EC
0x1400150e9  mov     rax, rbx
0x1400150ec  lea     r9d, [rax+r10]
0x1400150f0  mov     [rdi+4], r9d
0x1400150f4  mov     rdx, [rsi+58h]
0x1400150f8  add     rdx, 23Ch
0x1400150ff  jz      short loc_140015117
0x140015101  mov     rax, rcx
0x140015104  inc     rax
0x140015107  cmp     [rdx+rax*2], bx
0x14001510b  jnz     short loc_140015104
0x14001510d  lea     rax, ds:2[rax*2]
0x140015115  jmp     short loc_14001511A
0x140015117  mov     rax, rbx
0x14001511a  lea     edx, [rax+r9]
0x14001511e  mov     [rdi+4], edx
0x140015121  mov     rax, [rsi+58h]
0x140015125  add     rax, 34h ; '4'
0x140015129  jz      short loc_14001513E
0x14001512b  inc     rcx
0x14001512e  cmp     [rax+rcx*2], bx
0x140015132  jnz     short loc_14001512B
0x140015134  lea     rcx, ds:2[rcx*2]
0x14001513c  jmp     short loc_140015141
0x14001513e  mov     rcx, rbx
0x140015141  add     edx, ecx
0x140015143  mov     rcx, r8; pv
0x140015146  mov     [rdi+4], edx
0x140015149  call    cs:__imp_CoTaskMemFree
0x140015150  nop     dword ptr [rax+rax+00h]
0x140015155  mov     eax, 1
0x14001515a  jmp     loc_140015293
0x14001515f  cmp     dword ptr [rdx], 2
0x140015162  jnz     loc_140015291
0x140015168  add     rcx, 20h ; ' '; rclsid
0x14001516c  lea     rdx, [rsp+38h+pv]; lplpsz
0x140015171  call    cs:__imp_StringFromIID
0x140015178  nop     dword ptr [rax+rax+00h]
0x14001517d  mov     eax, [rdi+4]
0x140015180  lea     rbx, [rdi+8]
0x140015184  mov     r9, rbx
0x140015187  lea     rcx, [rax+rax*2]
0x14001518b  mov     rax, [rdi+10h]
0x14001518f  add     rcx, rcx
0x140015192  mov     dword ptr [rax+rcx*8], 30h ; '0'
0x140015199  mov     eax, [rdi+4]
0x14001519c  mov     rcx, [rdi+10h]
0x1400151a0  lea     rdx, [rax+rax*2]
0x1400151a4  mov     eax, [rsi+30h]
0x1400151a7  add     rdx, rdx
0x1400151aa  mov     [rcx+rdx*8+4], eax
0x1400151ae  mov     eax, [rdi+4]
0x1400151b1  mov     r8, [rdi+10h]
0x1400151b5  lea     rcx, [rax+rax*2]
0x1400151b9  mov     eax, [rdi+18h]
0x1400151bc  shl     rcx, 4
0x1400151c0  lea     rdx, [r8+8]
0x1400151c4  add     rdx, rcx
0x1400151c7  mov     [rsp+38h+var_18], eax; int
0x1400151cb  mov     rcx, [rsp+38h+pv]; unsigned __int16 *
0x1400151d0  call    StoreString
0x1400151d5  mov     eax, [rdi+4]
0x1400151d8  mov     r9, rbx
0x1400151db  mov     r8, [rdi+10h]
0x1400151df  lea     rcx, [rax+rax*2]
0x1400151e3  mov     eax, [rdi+18h]
0x1400151e6  shl     rcx, 4
0x1400151ea  lea     rdx, [r8+10h]
0x1400151ee  add     rdx, rcx
0x1400151f1  mov     [rsp+38h+var_18], eax; int
0x1400151f5  mov     rcx, [rsi+40h]; unsigned __int16 *
0x1400151f9  call    StoreString
0x1400151fe  mov     eax, [rdi+4]
0x140015201  mov     r9, rbx
0x140015204  mov     r8, [rdi+10h]
0x140015208  lea     rcx, [rax+rax*2]
0x14001520c  mov     eax, [rdi+18h]
0x14001520f  shl     rcx, 4
0x140015213  lea     rdx, [r8+18h]
0x140015217  add     rdx, rcx
0x14001521a  mov     [rsp+38h+var_18], eax; int
0x14001521e  mov     rcx, [rsi+38h]; unsigned __int16 *
0x140015222  call    StoreString
0x140015227  mov     eax, [rdi+4]
0x14001522a  mov     r9, rbx
0x14001522d  mov     r8, [rdi+10h]
0x140015231  lea     rcx, [rax+rax*2]
0x140015235  mov     eax, [rdi+18h]
0x140015238  shl     rcx, 4
0x14001523c  lea     rdx, [r8+20h]
0x140015240  add     rdx, rcx
0x140015243  mov     [rsp+38h+var_18], eax; int
0x140015247  mov     rcx, [rsi+58h]
0x14001524b  add     rcx, 23Ch; unsigned __int16 *
0x140015252  call    StoreString
0x140015257  mov     eax, [rdi+4]
0x14001525a  mov     r9, rbx
0x14001525d  mov     r8, [rdi+10h]
0x140015261  lea     rcx, [rax+rax*2]
0x140015265  mov     eax, [rdi+18h]
0x140015268  shl     rcx, 4
0x14001526c  lea     rdx, [r8+28h]
0x140015270  add     rdx, rcx
0x140015273  mov     [rsp+38h+var_18], eax; int
0x140015277  mov     rcx, [rsi+58h]
0x14001527b  add     rcx, 34h ; '4'; unsigned __int16 *
0x14001527f  call    StoreString
0x140015284  inc     dword ptr [rdi+4]
0x140015287  mov     rcx, [rsp+38h+pv]
0x14001528c  jmp     loc_140015149
0x140015291  xor     eax, eax
0x140015293  mov     rbx, [rsp+38h+arg_0]
0x140015298  mov     rsi, [rsp+38h+arg_10]
0x14001529d  add     rsp, 30h
0x1400152a1  pop     rdi
0x1400152a2  retn
```
