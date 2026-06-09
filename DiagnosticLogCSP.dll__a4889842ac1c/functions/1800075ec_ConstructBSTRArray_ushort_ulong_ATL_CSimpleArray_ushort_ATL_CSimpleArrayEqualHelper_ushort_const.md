# ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)

- ea: `0x1800075ec`
- end: `0x1800076ca`
- name: `?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007ca0`
- `0x180008b90`
- `0x180009a10`

## callees

- `0x1800073e0`
- `0x1800075ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076a1`
- `OLEAUT32!__imp_SysAllocString` at `0x180007663`
- `OLEAUT32!__imp_SysAllocString` at `0x180007663`
- `OLEAUT32!__imp_SysFreeString` at `0x180007692`
- `OLEAUT32!__imp_SysFreeString` at `0x180007692`

## pseudocode

```c
__int64 __fastcall ConstructBSTRArray(_QWORD *a1, _DWORD *a2, __int64 a3)
{
  unsigned int v6; // ebp
  SIZE_T v7; // rbx
  _BYTE *v8; // rax
  _QWORD *v9; // rsi
  unsigned int j; // ebx
  __int64 i; // rdi
  BSTR v12; // rax
  __int64 v13; // rbp

  if ( a1 && a2 )
  {
    v6 = *(_DWORD *)(a3 + 8);
    v7 = 8LL * v6;
    v8 = CoTaskMemAlloc(v7);
    v9 = v8;
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
            ATL::_AtlRaiseException(0xC000008C);
            JUMPOUT(0x1800076C9LL);
          }
          v12 = SysAllocString(*(const OLECHAR **)(*(_QWORD *)a3 + 8LL * (int)i));
          v9[i] = v12;
          if ( !v12 )
            break;
          i = (unsigned int)(i + 1);
          if ( (unsigned int)i >= v6 )
            goto LABEL_12;
        }
        v13 = 0;
        for ( j = -2147024882; (unsigned int)v13 < (unsigned int)i; v13 = (unsigned int)(v13 + 1) )
          SysFreeString((BSTR)v9[v13]);
        CoTaskMemFree(v9);
      }
      else
      {
LABEL_12:
        *a1 = v9;
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
0x1800075ec  push    rbx
0x1800075ee  push    rbp
0x1800075ef  push    rsi
0x1800075f0  push    rdi
0x1800075f1  push    r12
0x1800075f3  push    r14
0x1800075f5  push    r15
0x1800075f7  sub     rsp, 20h
0x1800075fb  mov     r15, r8
0x1800075fe  mov     r14, rdx
0x180007601  mov     r12, rcx
0x180007604  test    rcx, rcx
0x180007607  jz      loc_1800076A9
0x18000760d  test    rdx, rdx
0x180007610  jz      loc_1800076A9
0x180007616  mov     ebp, [r8+8]
0x18000761a  mov     ebx, ebp
0x18000761c  shl     rbx, 3
0x180007620  mov     rcx, rbx; cb
0x180007623  call    cs:__imp_CoTaskMemAlloc
0x180007629  mov     rsi, rax
0x18000762c  test    rax, rax
0x18000762f  jnz     short loc_180007638
0x180007631  mov     ebx, 8007000Eh
0x180007636  jmp     short loc_1800076AE
0x180007638  xor     edi, edi
0x18000763a  test    rbx, rbx
0x18000763d  jz      short loc_18000764B
0x18000763f  mov     [rax], dil
0x180007642  inc     rax
0x180007645  sub     rbx, 1
0x180007649  jnz     short loc_18000763F
0x18000764b  test    ebp, ebp
0x18000764d  jz      short loc_180007678
0x18000764f  test    edi, edi
0x180007651  js      short loc_1800076BF
0x180007653  cmp     edi, [r15+8]
0x180007657  jge     short loc_1800076BF
0x180007659  mov     rcx, [r15]
0x18000765c  movsxd  rax, edi
0x18000765f  mov     rcx, [rcx+rax*8]; psz
0x180007663  call    cs:__imp_SysAllocString
0x180007669  mov     [rsi+rdi*8], rax
0x18000766d  test    rax, rax
0x180007670  jz      short loc_180007683
0x180007672  inc     edi
0x180007674  cmp     edi, ebp
0x180007676  jb      short loc_18000764F
0x180007678  mov     [r12], rsi
0x18000767c  xor     ebx, ebx
0x18000767e  mov     [r14], edi
0x180007681  jmp     short loc_1800076AE
0x180007683  xor     ebp, ebp
0x180007685  mov     ebx, 8007000Eh
0x18000768a  test    edi, edi
0x18000768c  jz      short loc_18000769E
0x18000768e  mov     rcx, [rsi+rbp*8]; bstrString
0x180007692  call    cs:__imp_SysFreeString
0x180007698  inc     ebp
0x18000769a  cmp     ebp, edi
0x18000769c  jb      short loc_18000768E
0x18000769e  mov     rcx, rsi; pv
0x1800076a1  call    cs:__imp_CoTaskMemFree
0x1800076a7  jmp     short loc_1800076AE
0x1800076a9  mov     ebx, 80070057h
0x1800076ae  mov     eax, ebx
0x1800076b0  add     rsp, 20h
0x1800076b4  pop     r15
0x1800076b6  pop     r14
0x1800076b8  pop     r12
0x1800076ba  pop     rdi
0x1800076bb  pop     rsi
0x1800076bc  pop     rbp
0x1800076bd  pop     rbx
0x1800076be  retn
0x1800076bf  mov     ecx, 0C000008Ch; unsigned int
0x1800076c4  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
