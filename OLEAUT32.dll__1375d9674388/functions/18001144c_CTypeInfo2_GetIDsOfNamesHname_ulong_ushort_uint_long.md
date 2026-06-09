# CTypeInfo2::GetIDsOfNamesHname(ulong,ushort * *,uint,long *)

- ea: `0x18001144c`
- end: `0x1800117f6`
- name: `?GetIDsOfNamesHname@CTypeInfo2@@QEAAJKPEAPEAGIPEAJ@Z`
- size: `938`
- prototype: `__int64 __fastcall(CTypeInfo2 *__hidden this, unsigned int, unsigned __int16 **, unsigned int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011b24`
- `0x180011bf0`

## callees

- `0x18000f570`
- `0x180010d5c`
- `0x18001144c`
- `0x180011b24`
- `0x1800173cc`
- `0x180017570`
- `0x18004d900`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800114eb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800114eb`
- `KERNELBASE!CompareStringA` at `0x1800117a0`
- `KERNELBASE!CompareStringA` at `0x1800117a0`

## pseudocode

```c
int __fastcall CTypeInfo2::GetIDsOfNamesHname(
        CTypeInfo2 *this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned int a4,
        int *a5)
{
  unsigned int i; // edi
  CTypeLib2 **v8; // r15
  int result; // eax
  CTypeLib2 *v10; // rsi
  ULONG v11; // eax
  __int16 v12; // bp
  unsigned int v13; // eax
  __int64 v14; // rbx
  int v15; // ebp
  __int64 v16; // rdx
  _DWORD *v17; // rax
  __int64 j; // rdx
  __int64 v19; // rcx
  unsigned int v20; // r9d
  unsigned int v21; // eax
  _QWORD *v22; // rbx
  unsigned __int16 *v23; // r8
  unsigned int v24; // edi
  unsigned int v25; // esi
  char *v26; // r14
  unsigned int v27; // ebx
  unsigned int k; // ecx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  unsigned int v32; // [rsp+40h] [rbp-458h] BYREF
  unsigned __int16 **v33; // [rsp+48h] [rbp-450h]
  CHAR MultiByteStr[1024]; // [rsp+50h] [rbp-448h] BYREF

  v33 = a3;
  i = a2;
  v32 = a2;
  v8 = (CTypeLib2 **)((char *)this + 32);
  if ( a2 == -2 )
  {
    if ( (*((_BYTE *)*v8 + 212) & 8) == 0 )
    {
      result = CTypeLib2::ReadNames(*v8);
      if ( result < 0 )
        return result;
      a3 = v33;
    }
    v10 = *v8;
    if ( !WideCharToMultiByte(0, 0, *a3, -1, MultiByteStr, 1024, 0, 0) )
      return -2147024882;
    v11 = LHashValOfNameSysA((SYSKIND)(*((_WORD *)v10 + 202) & 3), *((_DWORD *)v10 + 99), MultiByteStr);
    v12 = v11;
    for ( i = *(_DWORD *)(*((_QWORD *)v10 + 24) + 4LL * (v11 % *((_DWORD *)v10 + 115))); i != -1; i = *(_DWORD *)(v31 + 4) )
    {
      v31 = i < *((_DWORD *)v10 + 51) ? *((_QWORD *)v10 + 27) + i : 0LL;
      if ( *(_WORD *)(v31 + 10) == v12
        && CompareStringA(
             *((_DWORD *)v10 + 99),
             0x30001u,
             (PCNZCH)(v31 + 12),
             *(_WORD *)(v31 + 8) & 0x3FF,
             MultiByteStr,
             -1) == 2 )
      {
        break;
      }
    }
    a3 = v33;
    v32 = i;
  }
  v13 = *((_DWORD *)this + 6);
  if ( v13 >= *((_DWORD *)*v8 + 9) )
    v14 = 0;
  else
    v14 = *((_QWORD *)*v8 + 6) + v13;
  v15 = *(unsigned __int16 *)(v14 + 96);
  if ( *(_WORD *)(v14 + 96) && (*(_DWORD *)(v14 + 68) & 0x2000) != 0 )
  {
    result = CTypeInfo2::GetIDsOfNamesHnameBase(this, (struct InfoDef *)v14, i, a3, a4, a5);
    if ( result != -2147352570 )
      return result;
    v15 = 0;
  }
  if ( i != -1 )
  {
    v16 = *((_QWORD *)this + 4);
    v17 = i >= *(_DWORD *)(v16 + 204) ? 0LL : (_DWORD *)(*(_QWORD *)(v16 + 216) + i);
    if ( *v17 != -1 )
    {
      if ( (*(_DWORD *)(v14 + 20) & 0x18) != 8 )
      {
        result = ElemInfoTable::Read((ElemInfoTable *)(v14 + 8), (struct CTypeLib2 *)v16, 0);
        if ( result < 0 )
          return result;
      }
      for ( j = 0;
            (unsigned int)j < *(unsigned __int16 *)(v14 + 32) + (unsigned int)*(unsigned __int16 *)(v14 + 34);
            j = (unsigned int)(j + 1) )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v14 + 48) + 4 * j) == i )
        {
          if ( (_DWORD)j == -1 )
            break;
          *a5 = *(_DWORD *)(*(_QWORD *)(v14 + 40) + 4 * j);
          if ( a4 > 1 && (unsigned int)j < *(unsigned __int16 *)(v14 + 32) )
          {
            v19 = *(_QWORD *)(v14 + 56);
            v20 = *(_DWORD *)(v14 + 12);
            v21 = *(_DWORD *)(v19 + 4 * j);
            if ( v21 >= v20 )
            {
              v23 = 0;
              v22 = (_QWORD *)(v14 + 24);
            }
            else
            {
              v22 = (_QWORD *)(v14 + 24);
              v23 = (unsigned __int16 *)(*v22 + v21);
            }
            do
            {
              if ( (v23[8] & 0x60) == 0 )
                break;
              v30 = v23[9];
              v23 = *(_DWORD *)(v19 + 4 * v30) >= v20
                  ? 0LL
                  : (unsigned __int16 *)(*v22 + *(unsigned int *)(v19 + 4 * v30));
            }
            while ( v23[1] != (_DWORD)j );
            v24 = 1;
            v25 = (unsigned __int16)(v23[10] - (v23[8] >> 14)) - 1;
            if ( (v23[8] & 0x60) == 0 )
              v25 = (unsigned __int16)(v23[10] - (v23[8] >> 14));
            v26 = (char *)v23 + *v23 - 12LL * v23[10];
            v27 = 0;
            while ( v24 < a4 )
            {
              result = CTypeLib2::HnameOfStrWIfExists(*v8, v33[v24], 0, &v32);
              if ( result < 0 )
                return result;
              if ( v32 == -1 )
                return -2147352570;
              for ( k = 0; k < v25; ++k )
              {
                v29 = 0;
                if ( v27 != v25 )
                  v29 = v27;
                v27 = v29;
                if ( *(_DWORD *)&v26[12 * v29 + 4] == v32 )
                {
                  a5[v24] = v29;
                  goto LABEL_65;
                }
                v27 = v29 + 1;
              }
              if ( k == v25 )
                return -2147352570;
LABEL_65:
              ++v27;
              ++v24;
            }
          }
          return 0;
        }
      }
    }
  }
  if ( v15 )
    return CTypeInfo2::GetIDsOfNamesHnameBase(this, (struct InfoDef *)v14, i, v33, a4, a5);
  else
    return -2147352570;
}

```

## disassembly

```asm
0x18001144c  mov     [rsp+arg_18], rbx
0x180011451  push    rbp
0x180011452  push    rsi
0x180011453  push    rdi
0x180011454  push    r12
0x180011456  push    r13
0x180011458  push    r14
0x18001145a  push    r15
0x18001145c  sub     rsp, 460h
0x180011463  mov     rax, cs:__security_cookie
0x18001146a  xor     rax, rsp
0x18001146d  mov     [rsp+498h+var_48], rax
0x180011475  mov     r13, [rsp+498h+arg_20]
0x18001147d  mov     r12d, r9d
0x180011480  mov     [rsp+498h+var_450], r8
0x180011485  mov     edi, edx
0x180011487  mov     [rsp+498h+var_458], edx
0x18001148b  mov     r14, rcx
0x18001148e  lea     r15, [rcx+20h]
0x180011492  cmp     edx, 0FFFFFFFEh
0x180011495  jnz     loc_180011539
0x18001149b  mov     rcx, [r15]; this
0x18001149e  test    byte ptr [rcx+0D4h], 8
0x1800114a5  jnz     short loc_1800114B9
0x1800114a7  call    ?ReadNames@CTypeLib2@@QEAAJXZ; CTypeLib2::ReadNames(void)
0x1800114ac  test    eax, eax
0x1800114ae  js      loc_1800115EF
0x1800114b4  mov     r8, [rsp+498h+var_450]
0x1800114b9  mov     r8, [r8]; lpWideCharStr
0x1800114bc  lea     rax, [rsp+498h+MultiByteStr]
0x1800114c1  mov     rsi, [r15]
0x1800114c4  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800114c8  mov     [rsp+498h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800114d1  xor     edx, edx; dwFlags
0x1800114d3  mov     [rsp+498h+lpDefaultChar], 0; lpDefaultChar
0x1800114dc  xor     ecx, ecx; CodePage
0x1800114de  mov     [rsp+498h+cbMultiByte], 400h; cbMultiByte
0x1800114e6  mov     [rsp+498h+lpMultiByteStr], rax; lpMultiByteStr
0x1800114eb  call    cs:__imp_WideCharToMultiByte
0x1800114f1  test    eax, eax
0x1800114f3  jz      loc_1800117D6
0x1800114f9  movzx   ecx, word ptr [rsi+194h]
0x180011500  lea     r8, [rsp+498h+MultiByteStr]; szName
0x180011505  mov     edx, [rsi+18Ch]; lcid
0x18001150b  and     ecx, 3; syskind
0x18001150e  call    LHashValOfNameSysA
0x180011513  mov     rcx, [rsi+0C0h]
0x18001151a  xor     edx, edx
0x18001151c  mov     ebp, eax
0x18001151e  div     dword ptr [rsi+1CCh]
0x180011524  mov     edi, [rcx+rdx*4]
0x180011527  cmp     edi, 0FFFFFFFFh
0x18001152a  jnz     loc_180011763
0x180011530  mov     r8, [rsp+498h+var_450]
0x180011535  mov     [rsp+498h+var_458], edi
0x180011539  mov     rcx, [r15]
0x18001153c  mov     esi, edi
0x18001153e  mov     eax, [r14+18h]
0x180011542  cmp     eax, [rcx+24h]
0x180011545  jnb     loc_180011755
0x18001154b  mov     ebx, eax
0x18001154d  add     rbx, [rcx+30h]
0x180011551  movzx   ebp, word ptr [rbx+60h]
0x180011555  test    ebp, ebp
0x180011557  jz      short loc_180011566
0x180011559  test    dword ptr [rbx+44h], 2000h
0x180011560  jnz     loc_18001161A
0x180011566  or      r9d, 0FFFFFFFFh
0x18001156a  cmp     esi, r9d
0x18001156d  jz      short loc_1800115CA
0x18001156f  mov     rdx, [r14+20h]; struct CTypeLib2 *
0x180011573  cmp     esi, [rdx+0CCh]
0x180011579  jnb     loc_18001175C
0x18001157f  mov     eax, esi
0x180011581  add     rax, [rdx+0D8h]
0x180011588  cmp     [rax], r9d
0x18001158b  jz      short loc_1800115CA
0x18001158d  mov     eax, [rbx+14h]
0x180011590  and     al, 18h
0x180011592  cmp     al, 8
0x180011594  jz      short loc_1800115AA
0x180011596  xor     r8d, r8d; int
0x180011599  lea     rcx, [rbx+8]; this
0x18001159d  call    ?Read@ElemInfoTable@@QEAAJPEAVCTypeLib2@@H@Z; ElemInfoTable::Read(CTypeLib2 *,int)
0x1800115a2  test    eax, eax
0x1800115a4  js      short loc_1800115EF
0x1800115a6  or      r9d, 0FFFFFFFFh
0x1800115aa  movzx   r8d, word ptr [rbx+22h]
0x1800115af  xor     edx, edx
0x1800115b1  movzx   eax, word ptr [rbx+20h]
0x1800115b5  add     r8d, eax
0x1800115b8  cmp     edx, r8d
0x1800115bb  jnb     short loc_1800115CA
0x1800115bd  mov     rax, [rbx+30h]
0x1800115c1  cmp     [rax+rdx*4], edi
0x1800115c4  jz      short loc_180011643
0x1800115c6  inc     edx
0x1800115c8  jmp     short loc_1800115B8
0x1800115ca  test    ebp, ebp
0x1800115cc  jz      loc_18001165D
0x1800115d2  mov     r9, [rsp+498h+var_450]; unsigned __int16 **
0x1800115d7  mov     r8d, edi; unsigned int
0x1800115da  mov     qword ptr [rsp+498h+cbMultiByte], r13; int *
0x1800115df  mov     rdx, rbx; struct InfoDef *
0x1800115e2  mov     rcx, r14; this
0x1800115e5  mov     dword ptr [rsp+498h+lpMultiByteStr], r12d; unsigned int
0x1800115ea  call    ?GetIDsOfNamesHnameBase@CTypeInfo2@@QEAAJPEAVInfoDef@@KPEAPEAGIPEAJ@Z; CTypeInfo2::GetIDsOfNamesHnameBase(InfoDef *,ulong,ushort * *,uint,long *)
0x1800115ef  mov     rcx, [rsp+498h+var_48]
0x1800115f7  xor     rcx, rsp; StackCookie
0x1800115fa  call    __security_check_cookie
0x1800115ff  mov     rbx, [rsp+498h+arg_18]
0x180011607  add     rsp, 460h
0x18001160e  pop     r15
0x180011610  pop     r14
0x180011612  pop     r13
0x180011614  pop     r12
0x180011616  pop     rdi
0x180011617  pop     rsi
0x180011618  pop     rbp
0x180011619  retn
0x18001161a  mov     r9, r8; unsigned __int16 **
0x18001161d  mov     qword ptr [rsp+498h+cbMultiByte], r13; int *
0x180011622  mov     r8d, edi; unsigned int
0x180011625  mov     dword ptr [rsp+498h+lpMultiByteStr], r12d; unsigned int
0x18001162a  mov     rdx, rbx; struct InfoDef *
0x18001162d  mov     rcx, r14; this
0x180011630  call    ?GetIDsOfNamesHnameBase@CTypeInfo2@@QEAAJPEAVInfoDef@@KPEAPEAGIPEAJ@Z; CTypeInfo2::GetIDsOfNamesHnameBase(InfoDef *,ulong,ushort * *,uint,long *)
0x180011635  cmp     eax, 80020006h
0x18001163a  jnz     short loc_1800115EF
0x18001163c  xor     ebp, ebp
0x18001163e  jmp     loc_180011566
0x180011643  cmp     edx, r9d
0x180011646  jz      short loc_1800115CA
0x180011648  mov     rax, [rbx+28h]
0x18001164c  mov     ecx, [rax+rdx*4]
0x18001164f  mov     [r13+0], ecx
0x180011653  cmp     r12d, 1
0x180011657  ja      short loc_180011664
0x180011659  xor     eax, eax
0x18001165b  jmp     short loc_1800115EF
0x18001165d  mov     eax, 80020006h
0x180011662  jmp     short loc_1800115EF
0x180011664  movzx   eax, word ptr [rbx+20h]
0x180011668  cmp     edx, eax
0x18001166a  jnb     short loc_180011659
0x18001166c  mov     rcx, [rbx+38h]
0x180011670  mov     r9d, [rbx+0Ch]
0x180011674  mov     eax, [rcx+rdx*4]
0x180011677  cmp     eax, r9d
0x18001167a  jnb     loc_1800117C2
0x180011680  add     rbx, 18h
0x180011684  mov     r8d, eax
0x180011687  add     r8, [rbx]
0x18001168a  test    byte ptr [r8+10h], 60h
0x18001168f  jnz     loc_18001172D
0x180011695  movzx   edx, word ptr [r8+14h]
0x18001169a  mov     edi, 1
0x18001169f  movzx   ecx, word ptr [r8+10h]
0x1800116a4  movzx   eax, dx
0x1800116a7  movzx   r14d, word ptr [r8]
0x1800116ab  shr     cx, 0Eh
0x1800116af  sub     ax, cx
0x1800116b2  test    byte ptr [r8+10h], 60h
0x1800116b7  movzx   ecx, ax
0x1800116ba  lea     rax, [rdx+rdx*2]
0x1800116be  lea     esi, [rcx-1]
0x1800116c1  cmovz   esi, ecx
0x1800116c4  shl     rax, 2
0x1800116c8  sub     r14, rax
0x1800116cb  add     r14, r8
0x1800116ce  xor     ebx, ebx
0x1800116d0  cmp     edi, r12d
0x1800116d3  jnb     short loc_180011659
0x1800116d5  mov     rax, [rsp+498h+var_450]
0x1800116da  lea     r9, [rsp+498h+var_458]; unsigned int *
0x1800116df  mov     rcx, [r15]; this
0x1800116e2  xor     r8d, r8d; unsigned int
0x1800116e5  mov     ebp, edi
0x1800116e7  mov     rdx, [rax+rbp*8]; lpWideCharStr
0x1800116eb  call    ?HnameOfStrWIfExists@CTypeLib2@@QEAAJPEAGKPEAK@Z; CTypeLib2::HnameOfStrWIfExists(ushort *,ulong,ulong *)
0x1800116f0  test    eax, eax
0x1800116f2  js      loc_1800115EF
0x1800116f8  mov     edx, [rsp+498h+var_458]
0x1800116fc  cmp     edx, 0FFFFFFFFh
0x1800116ff  jz      loc_18001165D
0x180011705  xor     ecx, ecx
0x180011707  cmp     ecx, esi
0x180011709  jnb     loc_1800117E7
0x18001170f  xor     eax, eax
0x180011711  cmp     ebx, esi
0x180011713  cmovnz  eax, ebx
0x180011716  mov     ebx, eax
0x180011718  lea     rax, [rax+rax*2]
0x18001171c  cmp     [r14+rax*4+4], edx
0x180011721  jz      loc_1800117E0
0x180011727  inc     ecx
0x180011729  inc     ebx
0x18001172b  jmp     short loc_180011707
0x18001172d  movzx   eax, word ptr [r8+12h]
0x180011732  cmp     [rcx+rax*4], r9d
0x180011736  jnb     loc_1800117CE
0x18001173c  mov     r8d, [rcx+rax*4]
0x180011740  add     r8, [rbx]
0x180011743  movzx   eax, word ptr [r8+2]
0x180011748  cmp     eax, edx
0x18001174a  jnz     loc_18001168A
0x180011750  jmp     loc_180011695
0x180011755  xor     ebx, ebx
0x180011757  jmp     loc_180011551
0x18001175c  xor     eax, eax
0x18001175e  jmp     loc_180011588
0x180011763  cmp     edi, [rsi+0CCh]
0x180011769  jb      short loc_1800117B7
0x18001176b  xor     ebx, ebx
0x18001176d  cmp     [rbx+0Ah], bp
0x180011771  jnz     short loc_1800117AF
0x180011773  movzx   r9d, word ptr [rbx+8]
0x180011778  lea     rax, [rsp+498h+MultiByteStr]
0x18001177d  mov     ecx, [rsi+18Ch]; Locale
0x180011783  lea     r8, [rbx+0Ch]; lpString1
0x180011787  and     r9d, 3FFh; cchCount1
0x18001178e  mov     [rsp+498h+cbMultiByte], 0FFFFFFFFh; cchCount2
0x180011796  mov     edx, 30001h; dwCmpFlags
0x18001179b  mov     [rsp+498h+lpMultiByteStr], rax; lpString2
0x1800117a0  call    cs:__imp_CompareStringA
0x1800117a6  cmp     eax, 2
0x1800117a9  jz      loc_180011530
0x1800117af  mov     edi, [rbx+4]
0x1800117b2  jmp     loc_180011527
0x1800117b7  mov     ebx, edi
0x1800117b9  add     rbx, [rsi+0D8h]
0x1800117c0  jmp     short loc_18001176D
0x1800117c2  xor     r8d, r8d
0x1800117c5  add     rbx, 18h
0x1800117c9  jmp     loc_18001168A
0x1800117ce  xor     r8d, r8d
0x1800117d1  jmp     loc_180011743
0x1800117d6  mov     eax, 8007000Eh
0x1800117db  jmp     loc_1800115EF
0x1800117e0  mov     [r13+rbp*4+0], ebx
0x1800117e5  jmp     short loc_1800117ED
0x1800117e7  jz      loc_18001165D
0x1800117ed  inc     ebx
0x1800117ef  inc     edi
0x1800117f1  jmp     loc_1800116D0
```
