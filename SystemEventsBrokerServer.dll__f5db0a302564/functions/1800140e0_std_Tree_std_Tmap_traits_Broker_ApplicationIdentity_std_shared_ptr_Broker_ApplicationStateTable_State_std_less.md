# std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Lower_bound_duplicate<Broker::ApplicationIdentity>(std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> * const,Broker::ApplicationIdentity const &)

- ea: `0x1800140e0`
- end: `0x180014204`
- name: `??$_Lower_bound_duplicate@UApplicationIdentity@Broker@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@1@AEBUApplicationIdentity@Broker@@@Z`
- size: `292`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a054`

## callees

- `0x1800140e0`
- `0x18001732c`
- `0x18001d9ac`
- `0x180022434`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180014186`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180014186`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Lower_bound_duplicate<Broker::ApplicationIdentity>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const void *v6; // rcx
  const void *v7; // rdx
  size_t v8; // r8
  size_t v9; // rax
  int v10; // esi
  int cchCount2; // eax
  const WCHAR *lpString2; // rbx
  const WCHAR *v13; // r8
  int v14; // eax
  int v15; // eax
  int v16; // eax
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-38h] BYREF

  if ( *(_BYTE *)(a2 + 25) )
    return 0;
  v6 = *(const void **)a3;
  v7 = *(const void **)(a2 + 32);
  v8 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
  v9 = *(_QWORD *)(a2 + 40) - (_QWORD)v7;
  if ( v8 >= v9 )
  {
    if ( v8 <= v9 )
    {
      v16 = memcmp_0(v6, v7, v8);
      if ( v16 < 0 )
        v10 = -1;
      else
        v10 = v16 > 0;
    }
    else
    {
      v10 = 1;
    }
  }
  else
  {
    v10 = -1;
  }
  cchCount2 = *(_DWORD *)(a2 + 72);
  lpString2 = (const WCHAR *)(a2 + 56);
  if ( *((_QWORD *)lpString2 + 3) > 7u )
    lpString2 = *(const WCHAR **)lpString2;
  v13 = (const WCHAR *)(a3 + 24);
  if ( *(_QWORD *)(a3 + 48) > 7u )
    v13 = *(const WCHAR **)v13;
  v14 = CompareStringEx(&LocaleName, 1u, v13, *(_DWORD *)(a3 + 40), lpString2, cchCount2, 0, 0, 0);
  if ( v14 == 1 )
    return 0;
  v15 = v14 - 2;
  if ( v15 )
  {
    if ( v15 != 1 )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
      throw (Broker::Win32Error *)pExceptionObject;
    }
    return 1;
  }
  return v10 != -1;
}

```

## disassembly

```asm
0x1800140e0  mov     [rsp+arg_8], rbx
0x1800140e5  mov     [rsp+arg_10], rsi
0x1800140ea  push    rdi
0x1800140eb  sub     rsp, 80h
0x1800140f2  cmp     byte ptr [rdx+19h], 0
0x1800140f6  mov     rdi, r8
0x1800140f9  mov     rbx, rdx
0x1800140fc  jz      short loc_180014115
0x1800140fe  xor     al, al
0x180014100  lea     r11, [rsp+88h+var_8]
0x180014108  mov     rbx, [r11+18h]
0x18001410c  mov     rsi, [r11+20h]
0x180014110  mov     rsp, r11
0x180014113  pop     rdi
0x180014114  retn
0x180014115  mov     rcx, [r8]; Buf1
0x180014118  mov     r8, [r8+8]
0x18001411c  mov     rdx, [rdx+20h]; Buf2
0x180014120  sub     r8, rcx; Size
0x180014123  mov     rax, [rbx+28h]
0x180014127  mov     [rsp+88h+arg_0], rbp
0x18001412f  sub     rax, rdx
0x180014132  xor     ebp, ebp
0x180014134  cmp     r8, rax
0x180014137  jnb     loc_1800141C3
0x18001413d  mov     esi, 0FFFFFFFFh
0x180014142  mov     eax, [rbx+48h]
0x180014145  add     rbx, 38h ; '8'
0x180014149  cmp     qword ptr [rbx+18h], 7
0x18001414e  jbe     short loc_180014153
0x180014150  mov     rbx, [rbx]
0x180014153  cmp     qword ptr [rdi+30h], 7
0x180014158  lea     r8, [rdi+18h]; lpString1
0x18001415c  ja      short loc_1800141CF
0x18001415e  mov     r9d, [rdi+28h]; cchCount1
0x180014162  lea     rcx, LocaleName; lpLocaleName
0x180014169  mov     [rsp+88h+lParam], rbp; lParam
0x18001416e  mov     edx, 1; dwCmpFlags
0x180014173  mov     [rsp+88h+lpReserved], rbp; lpReserved
0x180014178  mov     [rsp+88h+lpVersionInformation], rbp; lpVersionInformation
0x18001417d  mov     [rsp+88h+cchCount2], eax; cchCount2
0x180014181  mov     [rsp+88h+lpString2], rbx; lpString2
0x180014186  call    cs:__imp_CompareStringEx
0x18001418c  mov     rbp, [rsp+88h+arg_0]
0x180014194  cmp     eax, 1
0x180014197  jz      loc_1800140FE
0x18001419d  sub     eax, 2
0x1800141a0  jz      short loc_1800141EA
0x1800141a2  cmp     eax, 1
0x1800141a5  jz      short loc_1800141F3
0x1800141a7  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800141ac  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800141b1  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800141b8  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800141bd  call    _CxxThrowException_0
0x1800141c3  jbe     short loc_1800141D4
0x1800141c5  mov     esi, 1
0x1800141ca  jmp     loc_180014142
0x1800141cf  mov     r8, [r8]
0x1800141d2  jmp     short loc_18001415E
0x1800141d4  call    memcmp_0
0x1800141d9  test    eax, eax
0x1800141db  js      short loc_1800141FA
0x1800141dd  test    eax, eax
0x1800141df  mov     esi, ebp
0x1800141e1  setnle  sil
0x1800141e5  jmp     loc_180014142
0x1800141ea  cmp     esi, 0FFFFFFFFh
0x1800141ed  jz      loc_1800140FE
0x1800141f3  mov     al, 1
0x1800141f5  jmp     loc_180014100
0x1800141fa  mov     esi, 0FFFFFFFFh
0x1800141ff  jmp     loc_180014142
```
