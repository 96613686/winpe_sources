# std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Find_lower_bound<Broker::ApplicationIdentity>(Broker::ApplicationIdentity const &)

- ea: `0x1800116a0`
- end: `0x1800117e9`
- name: `??$_Find_lower_bound@UApplicationIdentity@Broker@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@1@AEBUApplicationIdentity@Broker@@@Z`
- size: `329`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a054`

## callees

- `0x1800116a0`
- `0x18001732c`
- `0x18001d9ac`
- `0x180022434`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180011748`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180011748`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Find_lower_bound<Broker::ApplicationIdentity>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  const void *v7; // rcx
  size_t v8; // rax
  size_t v9; // r8
  int v10; // edi
  const WCHAR *lpString2; // rax
  const WCHAR *v12; // r8
  int v13; // eax
  int v14; // eax
  int v16; // eax
  int v17; // eax
  _BYTE pExceptionObject[104]; // [rsp+50h] [rbp-68h] BYREF

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = (const void *)v6[4];
    v8 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
    v9 = v6[5] - (_QWORD)v7;
    if ( v9 >= v8 )
    {
      if ( v9 <= v8 )
      {
        v16 = memcmp_0(v7, *(const void **)a3, v9);
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
    if ( *(_QWORD *)(a3 + 48) <= 7u )
      lpString2 = (const WCHAR *)(a3 + 24);
    else
      lpString2 = *(const WCHAR **)(a3 + 24);
    v12 = (const WCHAR *)(v6 + 7);
    if ( (unsigned __int64)v6[10] > 7 )
      v12 = *(const WCHAR **)v12;
    v13 = CompareStringEx(&LocaleName, 1u, v12, *((_DWORD *)v6 + 18), lpString2, *(_DWORD *)(a3 + 40), 0, 0, 0);
    if ( v13 != 1 )
    {
      v17 = v13 - 2;
      if ( v17 )
      {
        if ( v17 != 1 )
        {
          Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
          throw (Broker::Win32Error *)pExceptionObject;
        }
LABEL_18:
        a2[2] = v6;
        v14 = 1;
        goto LABEL_10;
      }
      if ( v10 != -1 )
        goto LABEL_18;
    }
    v6 += 2;
    v14 = 0;
LABEL_10:
    *((_DWORD *)a2 + 2) = v14;
  }
  return a2;
}

```

## disassembly

```asm
0x1800116a0  push    rbx
0x1800116a2  push    rbp
0x1800116a3  push    rsi
0x1800116a4  push    rdi
0x1800116a5  push    r14
0x1800116a7  push    r15
0x1800116a9  sub     rsp, 88h
0x1800116b0  mov     rax, [rcx]
0x1800116b3  xor     ebp, ebp
0x1800116b5  mov     r14, r8
0x1800116b8  mov     rsi, rdx
0x1800116bb  mov     r9, [rax+8]
0x1800116bf  mov     [rdx], r9
0x1800116c2  mov     rbx, r9
0x1800116c5  mov     [rdx+8], rbp
0x1800116c9  mov     rax, [rcx]
0x1800116cc  mov     [rdx+10h], rax
0x1800116d0  cmp     [r9+19h], bpl
0x1800116d4  jnz     loc_180011769
0x1800116da  nop     word ptr [rax+rax+00h]
0x1800116e0  mov     [rsi], rbx
0x1800116e3  mov     rdx, [r14]; Buf2
0x1800116e6  mov     rax, [r14+8]
0x1800116ea  mov     rcx, [rbx+20h]; Buf1
0x1800116ee  sub     rax, rdx
0x1800116f1  mov     r8, [rbx+28h]
0x1800116f5  sub     r8, rcx; Size
0x1800116f8  cmp     r8, rax
0x1800116fb  jnb     loc_180011787
0x180011701  mov     edi, 0FFFFFFFFh
0x180011706  cmp     qword ptr [r14+30h], 7
0x18001170b  mov     ecx, [r14+28h]
0x18001170f  jbe     short loc_18001177C
0x180011711  mov     rax, [r14+18h]
0x180011715  cmp     qword ptr [rbx+50h], 7
0x18001171a  lea     r8, [rbx+38h]; lpString1
0x18001171e  ja      short loc_180011782
0x180011720  mov     r9d, [rbx+48h]; cchCount1
0x180011724  mov     edx, 1; dwCmpFlags
0x180011729  mov     [rsp+0B8h+lParam], rbp; lParam
0x18001172e  mov     [rsp+0B8h+lpReserved], rbp; lpReserved
0x180011733  mov     [rsp+0B8h+lpVersionInformation], rbp; lpVersionInformation
0x180011738  mov     [rsp+0B8h+cchCount2], ecx; cchCount2
0x18001173c  lea     rcx, LocaleName; lpLocaleName
0x180011743  mov     [rsp+0B8h+lpString2], rax; lpString2
0x180011748  call    cs:__imp_CompareStringEx
0x18001174e  cmp     eax, 1
0x180011751  jnz     short loc_1800117C3
0x180011753  add     rbx, 10h
0x180011757  mov     eax, ebp
0x180011759  mov     [rsi+8], eax
0x18001175c  mov     rbx, [rbx]
0x18001175f  cmp     [rbx+19h], bpl
0x180011763  jz      loc_1800116E0
0x180011769  mov     rax, rsi
0x18001176c  add     rsp, 88h
0x180011773  pop     r15
0x180011775  pop     r14
0x180011777  pop     rdi
0x180011778  pop     rsi
0x180011779  pop     rbp
0x18001177a  pop     rbx
0x18001177b  retn
0x18001177c  lea     rax, [r14+18h]
0x180011780  jmp     short loc_180011715
0x180011782  mov     r8, [r8]
0x180011785  jmp     short loc_180011720
0x180011787  jbe     short loc_180011793
0x180011789  mov     edi, 1
0x18001178e  jmp     loc_180011706
0x180011793  call    memcmp_0
0x180011798  test    eax, eax
0x18001179a  js      short loc_1800117B9
0x18001179c  test    eax, eax
0x18001179e  mov     edi, ebp
0x1800117a0  setnle  dil
0x1800117a4  jmp     loc_180011706
0x1800117a9  cmp     edi, 0FFFFFFFFh
0x1800117ac  jz      short loc_180011753
0x1800117ae  mov     [rsi+10h], rbx
0x1800117b2  mov     eax, 1
0x1800117b7  jmp     short loc_180011759
0x1800117b9  mov     edi, 0FFFFFFFFh
0x1800117be  jmp     loc_180011706
0x1800117c3  sub     eax, 2
0x1800117c6  jz      short loc_1800117A9
0x1800117c8  cmp     eax, 1
0x1800117cb  jz      short loc_1800117AE
0x1800117cd  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x1800117d2  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800117d7  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800117de  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x1800117e3  call    _CxxThrowException_0
```
