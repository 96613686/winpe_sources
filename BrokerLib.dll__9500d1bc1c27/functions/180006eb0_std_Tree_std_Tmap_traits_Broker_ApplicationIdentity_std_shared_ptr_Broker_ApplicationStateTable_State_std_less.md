# std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>> &&)

- ea: `0x180006eb0`
- end: `0x1800070e8`
- name: `??$_Emplace@U?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@1@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007be0`

## callees

- `0x180006aa0`
- `0x180006eb0`
- `0x1800070f0`
- `0x180008210`
- `0x180014a40`
- `0x180015b14`
- `0x18001659e`
- `0x1800165da`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800070e1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800070e1`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180006f7f`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180006f7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // r13
  unsigned int v8; // esi
  __int64 *v9; // rbx
  size_t v10; // r8
  int v11; // eax
  int v12; // esi
  const WCHAR *lpString2; // rax
  const WCHAR *v14; // r8
  int v15; // eax
  __int64 *v16; // rdi
  _QWORD *v17; // rbx
  int v19; // eax
  __int64 *v20; // [rsp+50h] [rbp-88h] BYREF
  __int64 v21; // [rsp+58h] [rbp-80h]
  _BYTE pExceptionObject[120]; // [rsp+60h] [rbp-78h] BYREF

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8);
  v8 = 0;
  v9 = v7;
  if ( !*((_BYTE *)v7 + 25) )
  {
    while ( 1 )
    {
      v7 = v9;
      v10 = v9[5] - v9[4];
      if ( v10 < *(_QWORD *)(a3 + 8) - *(_QWORD *)a3 )
        goto LABEL_19;
      if ( v10 <= *(_QWORD *)(a3 + 8) - *(_QWORD *)a3 )
        break;
      v12 = 1;
LABEL_6:
      if ( *(_QWORD *)(a3 + 48) <= 7u )
        lpString2 = (const WCHAR *)(a3 + 24);
      else
        lpString2 = *(const WCHAR **)(a3 + 24);
      v14 = (const WCHAR *)(v9 + 7);
      if ( (unsigned __int64)v9[10] > 7 )
        v14 = *(const WCHAR **)v14;
      v15 = CompareStringEx(&LocaleName, 1u, v14, *((_DWORD *)v9 + 18), lpString2, *(_DWORD *)(a3 + 40), 0, 0, 0) - 1;
      if ( v15 )
      {
        v19 = v15 - 1;
        if ( v19 )
        {
          if ( v19 != 1 )
          {
            Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
            throw (Broker::Win32Error *)pExceptionObject;
          }
LABEL_23:
          v8 = 1;
          v6 = v9;
          v9 = (__int64 *)*v9;
          goto LABEL_12;
        }
        if ( v12 != -1 )
          goto LABEL_23;
      }
      v8 = 0;
      v9 = (__int64 *)v9[2];
LABEL_12:
      if ( *((_BYTE *)v9 + 25) )
        goto LABEL_13;
    }
    v11 = memcmp_0((const void *)v9[4], *(const void **)a3, v10);
    if ( v11 >= 0 )
    {
      v12 = v11 > 0;
      goto LABEL_6;
    }
LABEL_19:
    v12 = -1;
    goto LABEL_6;
  }
LABEL_13:
  if ( *((_BYTE *)v6 + 25) || (unsigned __int8)Broker::ApplicationIdentity::operator<(a3, v6 + 4) )
  {
    if ( a1[1] == 0x1E1E1E1E1E1E1E1LL )
      std::_Xlength_error("map/set too long");
    v16 = (__int64 *)*a1;
    v20 = a1;
    v21 = 0;
    v17 = operator new(0x88u);
    Broker::ApplicationIdentity::ApplicationIdentity(v17 + 4, a3);
    v17[15] = 0;
    v17[16] = 0;
    v17[15] = *(_QWORD *)(a3 + 88);
    v17[16] = *(_QWORD *)(a3 + 96);
    *(_QWORD *)(a3 + 88) = 0;
    *(_QWORD *)(a3 + 96) = 0;
    *v17 = v16;
    v17[1] = v16;
    v17[2] = v16;
    *((_WORD *)v17 + 12) = 0;
    v20 = v7;
    v21 = v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Insert_node(
                      a1,
                      &v20,
                      v17);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180006eb0  push    rbx
0x180006eb2  push    rbp
0x180006eb3  push    rsi
0x180006eb4  push    rdi
0x180006eb5  push    r12
0x180006eb7  push    r13
0x180006eb9  push    r14
0x180006ebb  push    r15
0x180006ebd  sub     rsp, 98h
0x180006ec4  mov     r15, r8
0x180006ec7  mov     r14, rdx
0x180006eca  mov     r12, rcx
0x180006ecd  mov     rdi, [rcx]
0x180006ed0  mov     r13, [rdi+8]
0x180006ed4  xor     ebp, ebp
0x180006ed6  mov     esi, ebp
0x180006ed8  xor     eax, eax
0x180006eda  mov     [rsp+0D8h+arg_0], rax
0x180006ee2  mov     rbx, r13
0x180006ee5  cmp     [r13+19h], bpl
0x180006ee9  jnz     loc_180006F9E
0x180006eef  mov     r13, rbx
0x180006ef2  mov     r8, [rbx+28h]
0x180006ef6  sub     r8, [rbx+20h]; Size
0x180006efa  mov     rcx, [r15+8]
0x180006efe  mov     rax, rcx
0x180006f01  sub     rax, [r15]
0x180006f04  cmp     r8, rax
0x180006f07  jb      loc_180007080
0x180006f0d  sub     rcx, [r15]
0x180006f10  cmp     r8, rcx
0x180006f13  ja      loc_180007088
0x180006f19  mov     rdx, [r15]; Buf2
0x180006f1c  mov     rcx, [rbx+20h]; Buf1
0x180006f20  call    memcmp_0
0x180006f25  test    eax, eax
0x180006f27  js      loc_180007080
0x180006f2d  xor     esi, esi
0x180006f2f  test    eax, eax
0x180006f31  setnle  sil
0x180006f35  mov     ecx, [r15+28h]
0x180006f39  cmp     qword ptr [r15+30h], 7
0x180006f3e  jbe     loc_18000706F
0x180006f44  mov     rax, [r15+18h]
0x180006f48  lea     r8, [rbx+38h]; lpString1
0x180006f4c  cmp     qword ptr [r8+18h], 7
0x180006f51  ja      loc_180007078
0x180006f57  mov     [rsp+0D8h+lParam], rbp; lParam
0x180006f5c  mov     [rsp+0D8h+lpReserved], rbp; lpReserved
0x180006f61  mov     [rsp+0D8h+lpVersionInformation], rbp; lpVersionInformation
0x180006f66  mov     [rsp+0D8h+cchCount2], ecx; cchCount2
0x180006f6a  mov     [rsp+0D8h+lpString2], rax; lpString2
0x180006f6f  mov     r9d, [rbx+48h]; cchCount1
0x180006f73  mov     edx, 1; dwCmpFlags
0x180006f78  lea     rcx, LocaleName; lpLocaleName
0x180006f7f  call    cs:__imp_CompareStringEx
0x180006f85  sub     eax, 1
0x180006f88  jnz     loc_1800070B4
0x180006f8e  xor     esi, esi
0x180006f90  mov     rbx, [rbx+10h]
0x180006f94  cmp     [rbx+19h], bpl
0x180006f98  jz      loc_180006EEF
0x180006f9e  cmp     [rdi+19h], bpl
0x180006fa2  jnz     short loc_180006FB8
0x180006fa4  lea     rdx, [rdi+20h]
0x180006fa8  mov     rcx, r15
0x180006fab  call    ??MApplicationIdentity@Broker@@QEBA_NAEBU01@@Z; Broker::ApplicationIdentity::operator<(Broker::ApplicationIdentity const &)
0x180006fb0  test    al, al
0x180006fb2  jz      loc_180007092
0x180006fb8  mov     rax, 1E1E1E1E1E1E1E1h
0x180006fc2  cmp     [r12+8], rax
0x180006fc7  jz      loc_1800070DA
0x180006fcd  mov     rdi, [r12]
0x180006fd1  mov     [rsp+0D8h+var_88], r12
0x180006fd6  mov     [rsp+0D8h+var_80], rbp
0x180006fdb  mov     ecx, 88h; Size
0x180006fe0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006fe5  mov     rbx, rax
0x180006fe8  mov     rdx, r15
0x180006feb  lea     rcx, [rax+20h]
0x180006fef  call    ??0ApplicationIdentity@Broker@@QEAA@$$QEAU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity &&)
0x180006ff4  mov     [rbx+78h], rbp
0x180006ff8  mov     [rbx+80h], rbp
0x180006fff  mov     rcx, [r15+58h]
0x180007003  mov     [rbx+78h], rcx
0x180007007  mov     rcx, [r15+60h]
0x18000700b  mov     [rbx+80h], rcx
0x180007012  mov     [r15+58h], rbp
0x180007016  mov     [r15+60h], rbp
0x18000701a  mov     [rbx], rdi
0x18000701d  mov     [rbx+8], rdi
0x180007021  mov     [rbx+10h], rdi
0x180007025  mov     word ptr [rbx+18h], 0
0x18000702b  mov     [rsp+0D8h+var_88], r13
0x180007030  mov     dword ptr [rsp+0D8h+var_80], esi
0x180007034  mov     rax, [rsp+0D8h+arg_0]
0x18000703c  mov     dword ptr [rsp+0D8h+var_80+4], eax
0x180007040  mov     r8, rbx
0x180007043  lea     rdx, [rsp+0D8h+var_88]
0x180007048  mov     rcx, r12
0x18000704b  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *>,std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> * const)
0x180007050  mov     [r14], rax
0x180007053  mov     byte ptr [r14+8], 1
0x180007058  mov     rax, r14
0x18000705b  add     rsp, 98h
0x180007062  pop     r15
0x180007064  pop     r14
0x180007066  pop     r13
0x180007068  pop     r12
0x18000706a  pop     rdi
0x18000706b  pop     rsi
0x18000706c  pop     rbp
0x18000706d  pop     rbx
0x18000706e  retn
0x18000706f  lea     rax, [r15+18h]
0x180007073  jmp     loc_180006F48
0x180007078  mov     r8, [r8]
0x18000707b  jmp     loc_180006F57
0x180007080  or      esi, 0FFFFFFFFh
0x180007083  jmp     loc_180006F35
0x180007088  mov     esi, 1
0x18000708d  jmp     loc_180006F35
0x180007092  mov     [r14], rdi
0x180007095  mov     [r14+8], bpl
0x180007099  jmp     short loc_180007058
0x18000709b  cmp     esi, 0FFFFFFFFh
0x18000709e  jz      loc_180006F8E
0x1800070a4  mov     esi, 1
0x1800070a9  mov     rdi, rbx
0x1800070ac  mov     rbx, [rbx]
0x1800070af  jmp     loc_180006F94
0x1800070b4  sub     eax, 1
0x1800070b7  jz      short loc_18000709B
0x1800070b9  cmp     eax, 1
0x1800070bc  jz      short loc_1800070A4
0x1800070be  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x1800070c3  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800070c8  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800070cf  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800070d4  call    _CxxThrowException_0
0x1800070da  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800070e1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
