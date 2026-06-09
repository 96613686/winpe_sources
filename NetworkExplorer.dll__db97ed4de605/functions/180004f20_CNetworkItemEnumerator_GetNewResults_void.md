# CNetworkItemEnumerator::_GetNewResults(void)

- ea: `0x180004f20`
- end: `0x180005147`
- name: `?_GetNewResults@CNetworkItemEnumerator@@AEAAHXZ`
- size: `551`
- prototype: `__int64 __fastcall(CNetworkItemEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003610`

## callees

- `0x180004f20`
- `0x1800051c4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000505d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000505d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004fb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004fb4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005020`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005020`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800050ae`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800050ae`

## pseudocode

```c
__int64 __fastcall CNetworkItemEnumerator::_GetNewResults(CNetworkItemEnumerator *this)
{
  __int64 v2; // rcx
  unsigned int v3; // r15d
  __int64 v4; // rcx
  unsigned int v6; // r13d
  _QWORD *v7; // r12
  unsigned int i; // ebp
  unsigned int j; // ebx
  unsigned int v10; // eax
  unsigned int *v11; // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // r8d
  __int64 v16; // rax
  unsigned int v17; // [rsp+70h] [rbp+8h] BYREF
  int v18; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 **v19; // [rsp+80h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 6);
  v18 = 0;
  v3 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v2 + 96LL))(v2, &v18) >= 0 )
  {
    if ( !v18 )
    {
      v12 = 2 * *((_DWORD *)this + 15);
      *((_DWORD *)this + 15) = v12;
      if ( v12 > 16 )
      {
        v12 = 16;
        *((_DWORD *)this + 15) = 16;
      }
      Sleep(1000 * v12);
    }
    v4 = *((_QWORD *)this + 6);
    v19 = 0;
    v17 = 0;
    if ( (*(int (__fastcall **)(__int64, unsigned __int16 ***, unsigned int *))(*(_QWORD *)v4 + 40LL))(v4, &v19, &v17) >= 0
      && v17 )
    {
      v6 = *((_DWORD *)this + 4);
      v7 = CoTaskMemAlloc(8LL * (v17 + v6));
      if ( v7 )
      {
        for ( i = 0; i < v17; ++i )
        {
          for ( j = 0; j < *((_DWORD *)this + 4); ++j )
          {
            if ( CompareStringW(0x7Fu, 0, *(PCNZWCH *)(*((_QWORD *)this + 4) + 8LL * j), -1, v19[i], -1) == 2 )
              break;
          }
          if ( j == *((_DWORD *)this + 4) )
          {
            v13 = v6++;
            v14 = i;
            v7[v13] = v19[v14];
            v19[v14] = 0;
          }
        }
        v10 = *((_DWORD *)this + 4);
        v11 = (unsigned int *)((char *)this + 16);
        if ( v6 > v10 )
        {
          v15 = 0;
          if ( v10 )
          {
            do
            {
              v16 = v15++;
              v7[v16] = *(_QWORD *)(8 * v16 + *((_QWORD *)this + 4));
            }
            while ( v15 < *((_DWORD *)this + 4) );
            v11 = (unsigned int *)((char *)this + 16);
          }
          CoTaskMemFree(*((LPVOID *)this + 4));
          *((_QWORD *)this + 4) = v7;
          *v11 = v6;
        }
        else
        {
          CoTaskMemFree(v7);
        }
        if ( !v18 && *((int *)this + 15) < 16 )
          v3 = 1;
      }
      FreeStringArray(v19, v17);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180004f20  push    rsi
0x180004f22  push    rdi
0x180004f23  push    r15
0x180004f25  sub     rsp, 50h
0x180004f29  mov     rdi, rcx
0x180004f2c  lea     rdx, [rsp+68h+arg_8]
0x180004f31  mov     rcx, [rcx+30h]
0x180004f35  xor     esi, esi
0x180004f37  mov     [rsp+68h+arg_8], esi
0x180004f3b  mov     r15d, esi
0x180004f3e  mov     rax, [rcx]
0x180004f41  mov     rax, [rax+60h]
0x180004f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4a  test    eax, eax
0x180004f4c  js      short loc_180004F85
0x180004f4e  cmp     [rsp+68h+arg_8], esi
0x180004f52  jz      loc_18000509B
0x180004f58  mov     rcx, [rdi+30h]
0x180004f5c  lea     r8, [rsp+68h+arg_0]
0x180004f61  mov     [rsp+68h+arg_10], rsi
0x180004f69  lea     rdx, [rsp+68h+arg_10]
0x180004f71  mov     [rsp+68h+arg_0], esi
0x180004f75  mov     rax, [rcx]
0x180004f78  mov     rax, [rax+28h]
0x180004f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f81  test    eax, eax
0x180004f83  jns     short loc_180004F91
0x180004f85  mov     eax, r15d
0x180004f88  add     rsp, 50h
0x180004f8c  pop     r15
0x180004f8e  pop     rdi
0x180004f8f  pop     rsi
0x180004f90  retn
0x180004f91  mov     eax, [rsp+68h+arg_0]
0x180004f95  test    eax, eax
0x180004f97  jz      short loc_180004F85
0x180004f99  mov     [rsp+68h+var_28], r12
0x180004f9e  mov     [rsp+68h+var_30], r13
0x180004fa3  mov     r13d, [rdi+10h]
0x180004fa7  mov     [rsp+68h+var_38], r14
0x180004fac  lea     ecx, [rax+r13]
0x180004fb0  shl     rcx, 3; cb
0x180004fb4  call    cs:__imp_CoTaskMemAlloc
0x180004fba  mov     r12, rax
0x180004fbd  test    rax, rax
0x180004fc0  jz      loc_180005076
0x180004fc6  mov     [rsp+68h+arg_18], rbx
0x180004fce  mov     [rsp+68h+var_20], rbp
0x180004fd3  mov     ebp, esi
0x180004fd5  cmp     [rsp+68h+arg_0], esi
0x180004fd9  jbe     short loc_180005045
0x180004fdb  nop     dword ptr [rax+rax+00h]
0x180004fe0  mov     ebx, esi
0x180004fe2  cmp     [rdi+10h], r15d
0x180004fe6  jbe     short loc_180005034
0x180004fe8  mov     esi, ebp
0x180004fea  nop     word ptr [rax+rax+00h]
0x180004ff0  mov     rax, [rsp+68h+arg_10]
0x180004ff8  mov     r9d, 0FFFFFFFFh; cchCount1
0x180004ffe  mov     r8, [rdi+20h]
0x180005002  mov     edx, ebx
0x180005004  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000500c  mov     rcx, [rax+rsi*8]
0x180005010  mov     [rsp+68h+lpString2], rcx; lpString2
0x180005015  mov     ecx, 7Fh; Locale
0x18000501a  mov     r8, [r8+rdx*8]; lpString1
0x18000501e  xor     edx, edx; dwCmpFlags
0x180005020  call    cs:__imp_CompareStringW
0x180005026  cmp     eax, 2
0x180005029  jz      short loc_180005032
0x18000502b  inc     ebx
0x18000502d  cmp     ebx, [rdi+10h]
0x180005030  jb      short loc_180004FF0
0x180005032  xor     esi, esi
0x180005034  cmp     ebx, [rdi+10h]
0x180005037  jz      loc_1800050C3
0x18000503d  inc     ebp
0x18000503f  cmp     ebp, [rsp+68h+arg_0]
0x180005043  jb      short loc_180004FE0
0x180005045  mov     eax, [rdi+10h]
0x180005048  lea     rbx, [rdi+10h]
0x18000504c  mov     rbp, [rsp+68h+var_20]
0x180005051  cmp     r13d, eax
0x180005054  ja      loc_1800050F4
0x18000505a  mov     rcx, r12; pv
0x18000505d  call    cs:__imp_CoTaskMemFree
0x180005063  mov     rbx, [rsp+68h+arg_18]
0x18000506b  cmp     [rsp+68h+arg_8], r15d
0x180005070  jz      loc_180005135
0x180005076  mov     edx, [rsp+68h+arg_0]; unsigned int
0x18000507a  mov     rcx, [rsp+68h+arg_10]; unsigned __int16 **
0x180005082  call    ?FreeStringArray@@YAXPEAPEAGI@Z; FreeStringArray(ushort * *,uint)
0x180005087  mov     r14, [rsp+68h+var_38]
0x18000508c  mov     r13, [rsp+68h+var_30]
0x180005091  mov     r12, [rsp+68h+var_28]
0x180005096  jmp     loc_180004F85
0x18000509b  mov     eax, [rdi+3Ch]
0x18000509e  add     eax, eax
0x1800050a0  mov     [rdi+3Ch], eax
0x1800050a3  cmp     eax, 10h
0x1800050a6  jg      short loc_1800050B9
0x1800050a8  imul    ecx, eax, 3E8h; dwMilliseconds
0x1800050ae  call    cs:__imp_Sleep
0x1800050b4  jmp     loc_180004F58
0x1800050b9  mov     eax, 10h
0x1800050be  mov     [rdi+3Ch], eax
0x1800050c1  jmp     short loc_1800050A8
0x1800050c3  mov     eax, ebp
0x1800050c5  mov     edx, r13d
0x1800050c8  inc     r13d
0x1800050cb  lea     r8, ds:0[rax*8]
0x1800050d3  mov     rax, [rsp+68h+arg_10]
0x1800050db  mov     rcx, [r8+rax]
0x1800050df  mov     [r12+rdx*8], rcx
0x1800050e3  mov     rax, [rsp+68h+arg_10]
0x1800050eb  mov     [r8+rax], rsi
0x1800050ef  jmp     loc_18000503D
0x1800050f4  mov     r8d, esi
0x1800050f7  test    eax, eax
0x1800050f9  jz      short loc_18000511F
0x1800050fb  mov     eax, r8d
0x1800050fe  inc     r8d
0x180005101  lea     rdx, ds:0[rax*8]
0x180005109  mov     rax, [rdi+20h]
0x18000510d  mov     rcx, [rdx+rax]
0x180005111  mov     [rdx+r12], rcx
0x180005115  cmp     r8d, [rdi+10h]
0x180005119  jb      short loc_1800050FB
0x18000511b  lea     rbx, [rdi+10h]
0x18000511f  mov     rcx, [rdi+20h]; pv
0x180005123  call    cs:__imp_CoTaskMemFree
0x180005129  mov     [rdi+20h], r12
0x18000512d  mov     [rbx], r13d
0x180005130  jmp     loc_180005063
0x180005135  cmp     dword ptr [rdi+3Ch], 10h
0x180005139  mov     eax, 1
0x18000513e  cmovl   r15d, eax
0x180005142  jmp     loc_180005076
```
