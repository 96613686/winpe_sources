# CWMDSPPropImpl2::internalSetValue(ulong,tagPROPVARIANT const &)

- ea: `0x180083cd0`
- end: `0x180083e52`
- name: `?internalSetValue@CWMDSPPropImpl2@@MEAAJKAEBUtagPROPVARIANT@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(CWMDSPPropImpl2 *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18006bb30`

## callees

- `0x18000abfc`
- `0x18000b1b0`
- `0x1800836a8`
- `0x180083768`
- `0x18008389c`
- `0x180083cd0`
- `0x180084690`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180083dda`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180083dda`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180083df6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180083df6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180083daa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180083daa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180083dca`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180083dca`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl2::internalSetValue(
        CWMDSPPropImpl2 *this,
        unsigned int a2,
        const struct tagPROPVARIANT *a3)
{
  bool v5; // zf
  __int64 v6; // rbp
  HRESULT UBound; // ebx
  __int64 v8; // r15
  int v9; // eax
  size_t v10; // r14
  void *v11; // rbp
  void *v12; // rcx
  signed int Dim; // r12d
  signed int i; // ebp
  __int64 v15; // rdx
  void *ppvData; // [rsp+20h] [rbp-38h] BYREF
  int v18; // [rsp+70h] [rbp+18h] BYREF
  LONG plUbound; // [rsp+78h] [rbp+20h] BYREF

  if ( (a3->vt & 0x2000) != 0 )
  {
    v5 = *((_QWORD *)this + 12) == 0;
    ppvData = 0;
    v18 = 0;
    plUbound = 0;
    if ( v5 )
      return (unsigned int)-2147418113;
    v6 = *(int *)(96LL * a2 + *((_QWORD *)this + 2) + 92);
    if ( (int)v6 < 0 || (int)v6 >= *((_DWORD *)this + 22) )
    {
      return (unsigned int)-2147418113;
    }
    else
    {
      UBound = CWMDSPPropImpl2::SizeFromPropVar(this, a2, a3, &v18);
      if ( UBound >= 0 )
      {
        v8 = v6;
        v9 = WMDSPPropMemSize(*(_WORD *)(*((_QWORD *)this + 12) + 24 * v6));
        v10 = v18 * v9;
        v11 = operator new(v10);
        v12 = *(void **)(*((_QWORD *)this + 13) + 8 * v8);
        if ( v12 )
          operator delete(v12);
        *(_QWORD *)(*((_QWORD *)this + 13) + 8 * v8) = v11;
        UBound = SafeArrayAccessData(a3->parray, &ppvData);
        if ( UBound >= 0 )
        {
          memcpy_0(v11, ppvData, v10);
          UBound = SafeArrayUnaccessData(a3->parray);
          if ( UBound >= 0 )
          {
            Dim = SafeArrayGetDim(a3->parray);
            for ( i = 0; i < Dim; ++i )
            {
              UBound = SafeArrayGetUBound(a3->parray, i + 1, &plUbound);
              if ( UBound < 0 )
                break;
              v15 = i;
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 8 * v8) + 4 * v15) = plUbound;
            }
          }
        }
      }
    }
    return (unsigned int)UBound;
  }
  else
  {
    WMDSPPropValFromVar(a3, *((_QWORD *)this + 3) + 8 * (9LL * a2 + 1));
    return 0;
  }
}

```

## disassembly

```asm
0x180083cd0  mov     r11, rsp
0x180083cd3  mov     [r11+8], rbx
0x180083cd7  mov     [r11+10h], rbp
0x180083cdb  push    rsi
0x180083cdc  push    rdi
0x180083cdd  push    r12
0x180083cdf  push    r14
0x180083ce1  push    r15
0x180083ce3  sub     rsp, 30h
0x180083ce7  mov     rdi, rcx
0x180083cea  mov     eax, edx
0x180083cec  mov     ecx, 2000h
0x180083cf1  mov     rsi, r8
0x180083cf4  test    [r8], cx
0x180083cf8  jz      loc_180083E21
0x180083cfe  cmp     qword ptr [rdi+60h], 0
0x180083d03  mov     qword ptr [r11-38h], 0
0x180083d0b  mov     [rsp+58h+arg_10], 0
0x180083d13  mov     [rsp+58h+plUbound], 0
0x180083d1b  jz      loc_180083E18
0x180083d21  lea     rcx, [rax+rax*2]
0x180083d25  mov     rax, [rdi+10h]
0x180083d29  shl     rcx, 5
0x180083d2d  movsxd  rbp, dword ptr [rcx+rax+5Ch]
0x180083d32  test    ebp, ebp
0x180083d34  js      loc_180083E18
0x180083d3a  cmp     ebp, [rdi+58h]
0x180083d3d  jge     loc_180083E18
0x180083d43  lea     r9, [r11+18h]; int *
0x180083d47  mov     rcx, rdi; this
0x180083d4a  call    ?SizeFromPropVar@CWMDSPPropImpl2@@IEAAJKPEBUtagPROPVARIANT@@PEAJ@Z; CWMDSPPropImpl2::SizeFromPropVar(ulong,tagPROPVARIANT const *,long *)
0x180083d4f  mov     ebx, eax
0x180083d51  test    eax, eax
0x180083d53  js      loc_180083E1D
0x180083d59  mov     rcx, [rdi+60h]
0x180083d5d  lea     rax, ds:0[rbp*2]
0x180083d65  add     rax, rbp
0x180083d68  mov     r15, rbp
0x180083d6b  movzx   ecx, word ptr [rcx+rax*8]; unsigned __int16
0x180083d6f  call    ?WMDSPPropMemSize@@YAJG@Z; WMDSPPropMemSize(ushort)
0x180083d74  imul    eax, [rsp+58h+arg_10]
0x180083d79  movsxd  r14, eax
0x180083d7c  mov     rcx, r14; Size
0x180083d7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083d84  mov     rcx, [rdi+68h]
0x180083d88  mov     rbp, rax
0x180083d8b  mov     rcx, [rcx+r15*8]; Block
0x180083d8f  test    rcx, rcx
0x180083d92  jz      short loc_180083D99
0x180083d94  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180083d99  mov     rcx, [rdi+68h]
0x180083d9d  lea     rdx, [rsp+58h+ppvData]; ppvData
0x180083da2  mov     [rcx+r15*8], rbp
0x180083da6  mov     rcx, [rsi+8]; psa
0x180083daa  call    cs:__imp_SafeArrayAccessData
0x180083db0  mov     ebx, eax
0x180083db2  test    eax, eax
0x180083db4  js      short loc_180083E1D
0x180083db6  mov     rdx, [rsp+58h+ppvData]; Src
0x180083dbb  mov     r8, r14; Size
0x180083dbe  mov     rcx, rbp; void *
0x180083dc1  call    memcpy_0
0x180083dc6  mov     rcx, [rsi+8]; psa
0x180083dca  call    cs:__imp_SafeArrayUnaccessData
0x180083dd0  mov     ebx, eax
0x180083dd2  test    eax, eax
0x180083dd4  js      short loc_180083E1D
0x180083dd6  mov     rcx, [rsi+8]; psa
0x180083dda  call    cs:__imp_SafeArrayGetDim
0x180083de0  mov     r12d, eax
0x180083de3  xor     ebp, ebp
0x180083de5  cmp     ebp, r12d
0x180083de8  jge     short loc_180083E1D
0x180083dea  mov     rcx, [rsi+8]; psa
0x180083dee  lea     r8, [rsp+58h+plUbound]; plUbound
0x180083df3  lea     edx, [rbp+1]; nDim
0x180083df6  call    cs:__imp_SafeArrayGetUBound
0x180083dfc  mov     ebx, eax
0x180083dfe  test    eax, eax
0x180083e00  js      short loc_180083E1D
0x180083e02  mov     rax, [rdi+70h]
0x180083e06  movsxd  rdx, ebp
0x180083e09  inc     ebp
0x180083e0b  mov     rcx, [rax+r15*8]
0x180083e0f  mov     eax, [rsp+58h+plUbound]
0x180083e13  mov     [rcx+rdx*4], eax
0x180083e16  jmp     short loc_180083DE5
0x180083e18  mov     ebx, 8000FFFFh
0x180083e1d  mov     eax, ebx
0x180083e1f  jmp     short loc_180083E3B
0x180083e21  lea     rcx, [rax+rax*8]
0x180083e25  mov     rax, [rdi+18h]
0x180083e29  lea     rcx, [rcx+1]
0x180083e2d  lea     rdx, [rax+rcx*8]
0x180083e31  mov     rcx, rsi
0x180083e34  call    WMDSPPropValFromVar
0x180083e39  xor     eax, eax
0x180083e3b  mov     rbx, [rsp+58h+arg_0]
0x180083e40  mov     rbp, [rsp+58h+arg_8]
0x180083e45  add     rsp, 30h
0x180083e49  pop     r15
0x180083e4b  pop     r14
0x180083e4d  pop     r12
0x180083e4f  pop     rdi
0x180083e50  pop     rsi
0x180083e51  retn
```
