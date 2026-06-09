# std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::find(Broker::ApplicationIdentity const &)

- ea: `0x180001540`
- end: `0x180001782`
- name: `?find@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@@2@AEBUApplicationIdentity@Broker@@@Z`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000147c`

## callees

- `0x180001540`
- `0x180014a40`
- `0x18001659e`
- `0x1800165da`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800015fe`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800016b9`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800015fe`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800016b9`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::find(
        __int64 **a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v3; // rbp
  __int64 **v6; // rsi
  int v7; // r12d
  __int64 *v8; // rbx
  const void *v9; // rcx
  size_t v10; // rax
  size_t v11; // r8
  int v12; // eax
  int v13; // esi
  const WCHAR *lpString2; // rcx
  const WCHAR *v15; // r8
  int v16; // eax
  const void *v17; // rdx
  size_t v18; // rax
  size_t v19; // r8
  int v20; // eax
  const WCHAR *v21; // rax
  const WCHAR *v22; // r8
  int v23; // eax
  int v25; // eax
  int v26; // eax
  _BYTE pExceptionObject[12]; // [rsp+50h] [rbp-78h] BYREF
  int v28; // [rsp+5Ch] [rbp-6Ch]

  v3 = *a1;
  v28 = 0;
  v6 = a1;
  v7 = -1;
  v8 = (__int64 *)v3[1];
  if ( *((_BYTE *)v8 + 25) )
    goto LABEL_16;
  do
  {
    v9 = (const void *)v8[4];
    v10 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
    v11 = v8[5] - (_QWORD)v9;
    if ( v11 < v10 )
    {
      v13 = -1;
    }
    else if ( v11 > v10 )
    {
      v13 = 1;
    }
    else
    {
      v12 = memcmp_0(v9, *(const void **)a3, v11);
      if ( v12 < 0 )
        v13 = -1;
      else
        v13 = v12 > 0;
    }
    if ( *(_QWORD *)(a3 + 48) <= 7u )
      lpString2 = (const WCHAR *)(a3 + 24);
    else
      lpString2 = *(const WCHAR **)(a3 + 24);
    v15 = (const WCHAR *)(v8 + 7);
    if ( (unsigned __int64)v8[10] > 7 )
      v15 = *(const WCHAR **)v15;
    v16 = CompareStringEx(&LocaleName, 1u, v15, *((_DWORD *)v8 + 18), lpString2, *(_DWORD *)(a3 + 40), 0, 0, 0);
    if ( v16 == 1 )
    {
LABEL_11:
      v8 += 2;
      goto LABEL_12;
    }
    v25 = v16 - 2;
    if ( v25 )
    {
      if ( v25 != 1 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
        throw (Broker::Win32Error *)pExceptionObject;
      }
    }
    else if ( v13 == -1 )
    {
      goto LABEL_11;
    }
    v3 = v8;
LABEL_12:
    v8 = (__int64 *)*v8;
  }
  while ( !*((_BYTE *)v8 + 25) );
  v6 = a1;
LABEL_16:
  if ( *((_BYTE *)v3 + 25) )
    goto LABEL_26;
  v17 = (const void *)v3[4];
  v18 = v3[5] - (_QWORD)v17;
  v19 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
  if ( v19 >= v18 )
  {
    if ( v19 > v18 )
    {
      v7 = 1;
    }
    else
    {
      v20 = memcmp_0(*(const void **)a3, v17, v19);
      if ( v20 >= 0 )
        v7 = v20 > 0;
    }
  }
  v21 = (const WCHAR *)(v3 + 7);
  if ( (unsigned __int64)v3[10] > 7 )
    v21 = *(const WCHAR **)v21;
  v22 = (const WCHAR *)(a3 + 24);
  if ( *(_QWORD *)(a3 + 48) > 7u )
    v22 = *(const WCHAR **)v22;
  v23 = CompareStringEx(&LocaleName, 1u, v22, *(_DWORD *)(a3 + 40), v21, *((_DWORD *)v3 + 18), 0, 0, 0);
  if ( v23 == 1 )
  {
LABEL_26:
    v3 = *v6;
  }
  else
  {
    v26 = v23 - 2;
    if ( v26 )
    {
      if ( v26 != 1 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
        throw (Broker::Win32Error *)pExceptionObject;
      }
    }
    else if ( v7 == -1 )
    {
      goto LABEL_26;
    }
  }
  *a2 = v3;
  return a2;
}

```

## disassembly

```asm
0x180001540  mov     [rsp+arg_0], rcx
0x180001545  push    rbx
0x180001546  push    rbp
0x180001547  push    rsi
0x180001548  push    rdi
0x180001549  push    r12
0x18000154b  push    r13
0x18000154d  push    r14
0x18000154f  push    r15
0x180001551  sub     rsp, 88h
0x180001558  mov     rbp, [rcx]
0x18000155b  xor     eax, eax
0x18000155d  xor     r9d, r9d
0x180001560  mov     [rsp+0C8h+var_6C], eax
0x180001564  mov     rdi, r8
0x180001567  mov     r13, rdx
0x18000156a  mov     rsi, rcx
0x18000156d  mov     r12d, 0FFFFFFFFh
0x180001573  mov     rbx, [rbp+8]
0x180001577  cmp     [rbx+19h], al
0x18000157a  jnz     loc_180001635
0x180001580  mov     rdx, [rdi]; Buf2
0x180001583  mov     rax, [rdi+8]
0x180001587  mov     rcx, [rbx+20h]; Buf1
0x18000158b  sub     rax, rdx
0x18000158e  mov     r8, [rbx+28h]
0x180001592  sub     r8, rcx; Size
0x180001595  cmp     r8, rax
0x180001598  jb      loc_1800016E6
0x18000159e  ja      loc_180001702
0x1800015a4  call    memcmp_0
0x1800015a9  xor     r9d, r9d
0x1800015ac  test    eax, eax
0x1800015ae  js      loc_1800016EE
0x1800015b4  test    eax, eax
0x1800015b6  mov     esi, r9d
0x1800015b9  setnle  sil
0x1800015bd  cmp     qword ptr [rdi+30h], 7
0x1800015c2  mov     eax, [rdi+28h]
0x1800015c5  jbe     short loc_180001622
0x1800015c7  mov     rcx, [rdi+18h]
0x1800015cb  cmp     qword ptr [rbx+50h], 7
0x1800015d0  lea     r8, [rbx+38h]; lpString1
0x1800015d4  ja      short loc_180001628
0x1800015d6  mov     [rsp+0C8h+lParam], r9; lParam
0x1800015db  mov     edx, 1; dwCmpFlags
0x1800015e0  mov     [rsp+0C8h+lpReserved], r9; lpReserved
0x1800015e5  mov     [rsp+0C8h+lpVersionInformation], r9; lpVersionInformation
0x1800015ea  mov     r9d, [rbx+48h]; cchCount1
0x1800015ee  mov     [rsp+0C8h+cchCount2], eax; cchCount2
0x1800015f2  mov     [rsp+0C8h+lpString2], rcx; lpString2
0x1800015f7  lea     rcx, LocaleName; lpLocaleName
0x1800015fe  call    cs:__imp_CompareStringEx
0x180001604  cmp     eax, 1
0x180001607  jnz     loc_180001732
0x18000160d  add     rbx, 10h
0x180001611  mov     rbx, [rbx]
0x180001614  cmp     byte ptr [rbx+19h], 0
0x180001618  jnz     short loc_18000162D
0x18000161a  xor     r9d, r9d
0x18000161d  jmp     loc_180001580
0x180001622  lea     rcx, [rdi+18h]
0x180001626  jmp     short loc_1800015CB
0x180001628  mov     r8, [r8]
0x18000162b  jmp     short loc_1800015D6
0x18000162d  mov     rsi, [rsp+0C8h+arg_0]
0x180001635  cmp     byte ptr [rbp+19h], 0
0x180001639  jnz     loc_1800016C8
0x18000163f  mov     rdx, [rbp+20h]; Buf2
0x180001643  mov     rax, [rbp+28h]
0x180001647  mov     rcx, [rdi]; Buf1
0x18000164a  sub     rax, rdx
0x18000164d  mov     r8, [rdi+8]
0x180001651  sub     r8, rcx; Size
0x180001654  cmp     r8, rax
0x180001657  jb      loc_1800016FB
0x18000165d  ja      loc_18000170C
0x180001663  call    memcmp_0
0x180001668  xor     edx, edx
0x18000166a  test    eax, eax
0x18000166c  js      short loc_180001675
0x18000166e  mov     r12d, edx
0x180001671  setnle  r12b
0x180001675  cmp     qword ptr [rbp+50h], 7
0x18000167a  lea     rax, [rbp+38h]
0x18000167e  mov     ecx, [rbp+48h]
0x180001681  jbe     short loc_180001686
0x180001683  mov     rax, [rax]
0x180001686  cmp     qword ptr [rdi+30h], 7
0x18000168b  lea     r8, [rdi+18h]; lpString1
0x18000168f  ja      short loc_1800016F6
0x180001691  mov     r9d, [rdi+28h]; cchCount1
0x180001695  mov     [rsp+0C8h+lParam], rdx; lParam
0x18000169a  mov     [rsp+0C8h+lpReserved], rdx; lpReserved
0x18000169f  mov     [rsp+0C8h+lpVersionInformation], rdx; lpVersionInformation
0x1800016a4  mov     edx, 1; dwCmpFlags
0x1800016a9  mov     [rsp+0C8h+cchCount2], ecx; cchCount2
0x1800016ad  lea     rcx, LocaleName; lpLocaleName
0x1800016b4  mov     [rsp+0C8h+lpString2], rax; lpString2
0x1800016b9  call    cs:__imp_CompareStringEx
0x1800016bf  cmp     eax, 1
0x1800016c2  jnz     loc_180001758
0x1800016c8  mov     rbp, [rsi]
0x1800016cb  mov     [r13+0], rbp
0x1800016cf  mov     rax, r13
0x1800016d2  add     rsp, 88h
0x1800016d9  pop     r15
0x1800016db  pop     r14
0x1800016dd  pop     r13
0x1800016df  pop     r12
0x1800016e1  pop     rdi
0x1800016e2  pop     rsi
0x1800016e3  pop     rbp
0x1800016e4  pop     rbx
0x1800016e5  retn
0x1800016e6  mov     esi, r12d
0x1800016e9  jmp     loc_1800015BD
0x1800016ee  mov     esi, r12d
0x1800016f1  jmp     loc_1800015BD
0x1800016f6  mov     r8, [r8]
0x1800016f9  jmp     short loc_180001691
0x1800016fb  xor     edx, edx
0x1800016fd  jmp     loc_180001675
0x180001702  mov     esi, 1
0x180001707  jmp     loc_1800015BD
0x18000170c  xor     edx, edx
0x18000170e  mov     r12d, 1
0x180001714  jmp     loc_180001675
0x180001719  cmp     esi, r12d
0x18000171c  jz      loc_18000160D
0x180001722  mov     rbp, rbx
0x180001725  jmp     loc_180001611
0x18000172a  cmp     r12d, 0FFFFFFFFh
0x18000172e  jnz     short loc_1800016CB
0x180001730  jmp     short loc_1800016C8
0x180001732  sub     eax, 2
0x180001735  jz      short loc_180001719
0x180001737  cmp     eax, 1
0x18000173a  jz      short loc_180001722
0x18000173c  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x180001741  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180001746  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000174d  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180001752  call    _CxxThrowException_0
0x180001758  sub     eax, 2
0x18000175b  jz      short loc_18000172A
0x18000175d  cmp     eax, 1
0x180001760  jz      loc_1800016CB
0x180001766  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x18000176b  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180001770  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180001777  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000177c  call    _CxxThrowException_0
```
