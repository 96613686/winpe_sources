# ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)

- ea: `0x18000774c`
- end: `0x180007846`
- name: `?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z`
- size: `250`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007e30`
- `0x180008d90`
- `0x180009ca0`

## callees

- `0x180007530`
- `0x18000774c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007816`
- `OLEAUT32!__imp_SysAllocString` at `0x1800077cc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800077cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180007801`
- `OLEAUT32!__imp_SysFreeString` at `0x180007801`

## pseudocode

```c
__int64 __fastcall ConstructBSTRArray(_QWORD *a1, _DWORD *a2, __int64 a3)
{
  unsigned int v6; // ebp
  SIZE_T v7; // rbx
  _BYTE *v8; // rax
  unsigned int v9; // edx
  _QWORD *v10; // rsi
  unsigned int j; // ebx
  __int64 i; // rdi
  BSTR v13; // rax
  __int64 v14; // rbp

  if ( a1 && a2 )
  {
    v6 = *(_DWORD *)(a3 + 8);
    v7 = 8LL * v6;
    v8 = CoTaskMemAlloc(v7);
    v10 = v8;
    if ( v8 )
    {
      for ( i = 0; v7; --v7 )
        *v8++ = 0;
      if ( v6 )
      {
        while ( 1 )
        {
          if ( (int)i < 0 || (int)i >= *(_DWORD *)(a3 + 8) )
          {
            ATL::_AtlRaiseException(0xC000008C, v9);
            JUMPOUT(0x180007845LL);
          }
          v13 = SysAllocString(*(const OLECHAR **)(*(_QWORD *)a3 + 8LL * (int)i));
          v10[i] = v13;
          if ( !v13 )
            break;
          i = (unsigned int)(i + 1);
          if ( (unsigned int)i >= v6 )
            goto LABEL_12;
        }
        v14 = 0;
        for ( j = -2147024882; (unsigned int)v14 < (unsigned int)i; v14 = (unsigned int)(v14 + 1) )
          SysFreeString((BSTR)v10[v14]);
        CoTaskMemFree(v10);
      }
      else
      {
LABEL_12:
        *a1 = v10;
        j = 0;
        *a2 = i;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return j;
}

```

## disassembly

```asm
0x18000774c  push    rbx
0x18000774e  push    rbp
0x18000774f  push    rsi
0x180007750  push    rdi
0x180007751  push    r12
0x180007753  push    r14
0x180007755  push    r15
0x180007757  sub     rsp, 20h
0x18000775b  mov     r15, r8
0x18000775e  mov     r14, rdx
0x180007761  mov     r12, rcx
0x180007764  test    rcx, rcx
0x180007767  jz      loc_180007824
0x18000776d  test    rdx, rdx
0x180007770  jz      loc_180007824
0x180007776  mov     ebp, [r8+8]
0x18000777a  mov     ebx, ebp
0x18000777c  shl     rbx, 3
0x180007780  mov     rcx, rbx; cb
0x180007783  call    cs:__imp_CoTaskMemAlloc
0x18000778a  nop     dword ptr [rax+rax+00h]
0x18000778f  mov     rsi, rax
0x180007792  test    rax, rax
0x180007795  jnz     short loc_1800077A1
0x180007797  mov     ebx, 8007000Eh
0x18000779c  jmp     loc_180007829
0x1800077a1  xor     edi, edi
0x1800077a3  test    rbx, rbx
0x1800077a6  jz      short loc_1800077B4
0x1800077a8  mov     [rax], dil
0x1800077ab  inc     rax
0x1800077ae  sub     rbx, 1
0x1800077b2  jnz     short loc_1800077A8
0x1800077b4  test    ebp, ebp
0x1800077b6  jz      short loc_1800077E7
0x1800077b8  test    edi, edi
0x1800077ba  js      short loc_18000783B
0x1800077bc  cmp     edi, [r15+8]
0x1800077c0  jge     short loc_18000783B
0x1800077c2  mov     rcx, [r15]
0x1800077c5  movsxd  rax, edi
0x1800077c8  mov     rcx, [rcx+rax*8]; psz
0x1800077cc  call    cs:__imp_SysAllocString
0x1800077d3  nop     dword ptr [rax+rax+00h]
0x1800077d8  mov     [rsi+rdi*8], rax
0x1800077dc  test    rax, rax
0x1800077df  jz      short loc_1800077F2
0x1800077e1  inc     edi
0x1800077e3  cmp     edi, ebp
0x1800077e5  jb      short loc_1800077B8
0x1800077e7  mov     [r12], rsi
0x1800077eb  xor     ebx, ebx
0x1800077ed  mov     [r14], edi
0x1800077f0  jmp     short loc_180007829
0x1800077f2  xor     ebp, ebp
0x1800077f4  mov     ebx, 8007000Eh
0x1800077f9  test    edi, edi
0x1800077fb  jz      short loc_180007813
0x1800077fd  mov     rcx, [rsi+rbp*8]; bstrString
0x180007801  call    cs:__imp_SysFreeString
0x180007808  nop     dword ptr [rax+rax+00h]
0x18000780d  inc     ebp
0x18000780f  cmp     ebp, edi
0x180007811  jb      short loc_1800077FD
0x180007813  mov     rcx, rsi; pv
0x180007816  call    cs:__imp_CoTaskMemFree
0x18000781d  nop     dword ptr [rax+rax+00h]
0x180007822  jmp     short loc_180007829
0x180007824  mov     ebx, 80070057h
0x180007829  mov     eax, ebx
0x18000782b  add     rsp, 20h
0x18000782f  pop     r15
0x180007831  pop     r14
0x180007833  pop     r12
0x180007835  pop     rdi
0x180007836  pop     rsi
0x180007837  pop     rbp
0x180007838  pop     rbx
0x180007839  retn
0x18000783b  mov     ecx, 0C000008Ch; unsigned int
0x180007840  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
