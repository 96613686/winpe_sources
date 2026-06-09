# CNetworkItemFactory::_SendNotification(long,INetworkItem *)

- ea: `0x180004fb0`
- end: `0x180005052`
- name: `?_SendNotification@CNetworkItemFactory@@AEAAJJPEAUINetworkItem@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(CNetworkItemFactory *this, LONG, struct INetworkItem *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000488c`
- `0x1800049f4`

## callees

- `0x180004fb0`
- `0x18000b010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18000502f`
- `SHELL32!SHChangeNotify` at `0x18000502f`
- `SHELL32!__imp_ILFree` at `0x18000503a`
- `SHELL32!__imp_ILFree` at `0x18000503a`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_SendNotification(CNetworkItemFactory *this, LONG a2, struct INetworkItem *a3)
{
  __int64 v3; // rax
  int v6; // esi
  __int64 v7; // rcx
  int v9; // [rsp+30h] [rbp+8h] BYREF
  LPCVOID dwItem1; // [rsp+48h] [rbp+20h] BYREF

  v3 = *(_QWORD *)this;
  dwItem1 = 0;
  v6 = (*(__int64 (__fastcall **)(CNetworkItemFactory *, struct INetworkItem *, LPCVOID *))(v3 + 56))(
         this,
         a3,
         &dwItem1);
  if ( v6 >= 0 )
  {
    v7 = *(_QWORD *)a3;
    v9 = 0;
    if ( (*(int (__fastcall **)(struct INetworkItem *, int *))(v7 + 48))(a3, &v9) >= 0 && v9 )
    {
      if ( a2 == 2 )
      {
        a2 = 8;
      }
      else if ( a2 == 4 )
      {
        a2 = 16;
      }
    }
    SHChangeNotify(a2, 0, dwItem1, 0);
    ILFree((LPITEMIDLIST)dwItem1);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004fb0  mov     r11, rsp
0x180004fb3  mov     [r11+10h], rbx
0x180004fb7  mov     [r11+18h], rsi
0x180004fbb  push    rdi
0x180004fbc  sub     rsp, 20h
0x180004fc0  mov     rax, [rcx]
0x180004fc3  mov     rdi, r8
0x180004fc6  mov     ebx, edx
0x180004fc8  mov     qword ptr [r11+20h], 0
0x180004fd0  lea     r8, [r11+20h]
0x180004fd4  mov     rdx, rdi
0x180004fd7  mov     rax, [rax+38h]
0x180004fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe0  mov     esi, eax
0x180004fe2  test    eax, eax
0x180004fe4  js      short loc_180005040
0x180004fe6  mov     rcx, [rdi]
0x180004fe9  lea     rdx, [rsp+28h+arg_0]
0x180004fee  mov     [rsp+28h+arg_0], 0
0x180004ff6  mov     rax, [rcx+30h]
0x180004ffa  mov     rcx, rdi
0x180004ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005002  test    eax, eax
0x180005004  js      short loc_180005023
0x180005006  cmp     [rsp+28h+arg_0], 0
0x18000500b  jz      short loc_180005023
0x18000500d  cmp     ebx, 2
0x180005010  jz      short loc_18000501E
0x180005012  cmp     ebx, 4
0x180005015  jnz     short loc_180005023
0x180005017  mov     ebx, 10h
0x18000501c  jmp     short loc_180005023
0x18000501e  mov     ebx, 8
0x180005023  mov     r8, [rsp+28h+dwItem1]; dwItem1
0x180005028  xor     r9d, r9d; dwItem2
0x18000502b  xor     edx, edx; uFlags
0x18000502d  mov     ecx, ebx; wEventId
0x18000502f  call    cs:__imp_SHChangeNotify
0x180005035  mov     rcx, [rsp+28h+dwItem1]; pidl
0x18000503a  call    cs:__imp_ILFree
0x180005040  mov     rbx, [rsp+28h+arg_8]
0x180005045  mov     eax, esi
0x180005047  mov     rsi, [rsp+28h+arg_10]
0x18000504c  add     rsp, 20h
0x180005050  pop     rdi
0x180005051  retn
```
