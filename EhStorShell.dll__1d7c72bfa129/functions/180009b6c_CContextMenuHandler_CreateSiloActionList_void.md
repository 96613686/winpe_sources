# CContextMenuHandler::CreateSiloActionList(void)

- ea: `0x180009b6c`
- end: `0x180009d4a`
- name: `?CreateSiloActionList@CContextMenuHandler@@QEAAJXZ`
- size: `478`
- prototype: `__int64 __fastcall(CContextMenuHandler *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180003a98`

## callees

- `0x180005a10`
- `0x180006260`
- `0x1800064cc`
- `0x18000684c`
- `0x180009b6c`
- `0x18000c010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180009c4e`
- `ole32!CoTaskMemFree` at `0x180009d25`
- `ole32!CoTaskMemFree` at `0x180009c4e`
- `ole32!CoTaskMemFree` at `0x180009d25`

## pseudocode

```c
__int64 __fastcall CContextMenuHandler::CreateSiloActionList(
        CContextMenuHandler *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // eax
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  unsigned int k; // ebx
  __int64 v9; // rdx
  unsigned int i; // ebx
  int v12; // eax
  unsigned int j; // r14d
  unsigned __int64 v14; // r15
  _QWORD *v15; // rax
  __int64 v16; // r12
  _QWORD *v17; // [rsp+20h] [rbp-18h]
  unsigned int v18; // [rsp+80h] [rbp+48h] BYREF
  unsigned int v19; // [rsp+88h] [rbp+50h] BYREF
  LPVOID v20; // [rsp+90h] [rbp+58h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+60h] BYREF

  pv = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
  v5 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, unsigned int *))(**((_QWORD **)this + 3) + 64LL))(
         *((_QWORD *)this + 3),
         &pv,
         &v18);
  v6 = v5;
  if ( v5 >= 0 )
  {
    for ( i = 0; i < v18; ++i )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, unsigned int *))(**((_QWORD **)pv + i) + 32LL))(
              *((_QWORD *)pv + i),
              &v20,
              &v19);
      v6 = v12;
      if ( v12 >= 0 )
      {
        for ( j = 0; j < v19; *((_QWORD *)v20 + v16) = 0 )
        {
          v14 = *((_QWORD *)this + 5);
          v15 = v20;
          v16 = j;
          v17 = v20;
          if ( v14 >= *((_QWORD *)this + 6) )
          {
            if ( !(unsigned __int8)ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::GrowBuffer(
                                     (char *)this + 32,
                                     v14 + 1) )
              ATL::AtlThrowImpl(-2147024882);
            v15 = v17;
          }
          ++j;
          *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v14) = v15[v16];
          ++*((_QWORD *)this + 5);
        }
        CoTaskMemFree(v20);
        v20 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids,
            (unsigned int)v12);
        v6 = 0;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids,
      (unsigned int)v5);
  }
  v7 = pv;
  if ( pv )
  {
    for ( k = 0; k < v18; ++k )
    {
      v9 = v7[k];
      if ( v9 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 16LL))(v7[k]);
        *((_QWORD *)pv + k) = 0;
        v7 = pv;
      }
    }
    CoTaskMemFree(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x180009b6c  push    rbp
0x180009b6e  push    rbx
0x180009b6f  push    rsi
0x180009b70  push    rdi
0x180009b71  push    r12
0x180009b73  push    r13
0x180009b75  push    r14
0x180009b77  push    r15
0x180009b79  mov     rbp, rsp
0x180009b7c  sub     rsp, 38h
0x180009b80  xor     r15d, r15d
0x180009b83  mov     r13, rcx
0x180009b86  mov     [rbp+pv], r15
0x180009b8a  mov     [rbp+arg_0], r15d
0x180009b8e  mov     [rbp+arg_10], r15
0x180009b92  mov     [rbp+arg_8], r15d
0x180009b96  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b9d  lea     rsi, WPP_GLOBAL_Control
0x180009ba4  cmp     rcx, rsi
0x180009ba7  jz      short loc_180009BC3
0x180009ba9  test    byte ptr [rcx+1Ch], 20h
0x180009bad  jz      short loc_180009BC3
0x180009baf  mov     rcx, [rcx+10h]
0x180009bb3  lea     edx, [r15+0Dh]
0x180009bb7  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009bbe  call    WPP_SF_
0x180009bc3  mov     rcx, [r13+18h]
0x180009bc7  lea     r8, [rbp+arg_0]
0x180009bcb  lea     rdx, [rbp+pv]
0x180009bcf  mov     rax, [rcx]
0x180009bd2  mov     rax, [rax+40h]
0x180009bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bdb  mov     edi, eax
0x180009bdd  test    eax, eax
0x180009bdf  jns     loc_180009C67
0x180009be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bec  cmp     rcx, rsi
0x180009bef  jz      short loc_180009C0F
0x180009bf1  test    byte ptr [rcx+1Ch], 2
0x180009bf5  jz      short loc_180009C0F
0x180009bf7  mov     rcx, [rcx+10h]
0x180009bfb  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009c02  mov     edx, 0Eh
0x180009c07  mov     r9d, eax
0x180009c0a  call    WPP_SF_d
0x180009c0f  mov     rcx, [rbp+pv]
0x180009c13  test    rcx, rcx
0x180009c16  jz      short loc_180009C54
0x180009c18  mov     ebx, r15d
0x180009c1b  cmp     [rbp+arg_0], r15d
0x180009c1f  jbe     short loc_180009C4E
0x180009c21  mov     esi, ebx
0x180009c23  mov     rdx, [rcx+rsi*8]
0x180009c27  test    rdx, rdx
0x180009c2a  jz      short loc_180009C47
0x180009c2c  mov     rax, [rdx]
0x180009c2f  mov     rcx, rdx
0x180009c32  mov     rax, [rax+10h]
0x180009c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3b  mov     rax, [rbp+pv]
0x180009c3f  mov     [rax+rsi*8], r15
0x180009c43  mov     rcx, [rbp+pv]; pv
0x180009c47  inc     ebx
0x180009c49  cmp     ebx, [rbp+arg_0]
0x180009c4c  jb      short loc_180009C21
0x180009c4e  call    cs:__imp_CoTaskMemFree
0x180009c54  mov     eax, edi
0x180009c56  add     rsp, 38h
0x180009c5a  pop     r15
0x180009c5c  pop     r14
0x180009c5e  pop     r13
0x180009c60  pop     r12
0x180009c62  pop     rdi
0x180009c63  pop     rsi
0x180009c64  pop     rbx
0x180009c65  pop     rbp
0x180009c66  retn
0x180009c67  mov     ebx, r15d
0x180009c6a  cmp     [rbp+arg_0], r15d
0x180009c6e  jbe     short loc_180009C0F
0x180009c70  mov     rax, [rbp+pv]
0x180009c74  lea     r8, [rbp+arg_8]
0x180009c78  mov     ecx, ebx
0x180009c7a  lea     rdx, [rbp+arg_10]
0x180009c7e  mov     rcx, [rax+rcx*8]
0x180009c82  mov     rax, [rcx]
0x180009c85  mov     rax, [rax+20h]
0x180009c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c8e  mov     edi, eax
0x180009c90  test    eax, eax
0x180009c92  jns     short loc_180009CC3
0x180009c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c9b  cmp     rcx, rsi
0x180009c9e  jz      short loc_180009CBE
0x180009ca0  test    byte ptr [rcx+1Ch], 4
0x180009ca4  jz      short loc_180009CBE
0x180009ca6  mov     rcx, [rcx+10h]
0x180009caa  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180009cb1  mov     edx, 0Fh
0x180009cb6  mov     r9d, eax
0x180009cb9  call    WPP_SF_d
0x180009cbe  mov     edi, r15d
0x180009cc1  jmp     short loc_180009D2F
0x180009cc3  mov     r14d, r15d
0x180009cc6  cmp     [rbp+arg_8], r15d
0x180009cca  jbe     short loc_180009D21
0x180009ccc  mov     r15, [r13+28h]
0x180009cd0  mov     rax, [rbp+arg_10]
0x180009cd4  mov     r12d, r14d
0x180009cd7  mov     [rbp+var_18], rax
0x180009cdb  cmp     r15, [r13+30h]
0x180009cdf  jb      short loc_180009CF6
0x180009ce1  lea     rdx, [r15+1]
0x180009ce5  lea     rcx, [r13+20h]
0x180009ce9  call    ?GrowBuffer@?$CAtlArray@PEAUIEnhancedStorageSiloAction@@V?$CElementTraits@PEAUIEnhancedStorageSiloAction@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<IEnhancedStorageSiloAction *,ATL::CElementTraits<IEnhancedStorageSiloAction *>>::GrowBuffer(unsigned __int64)
0x180009cee  test    al, al
0x180009cf0  jz      short loc_180009D3F
0x180009cf2  mov     rax, [rbp+var_18]
0x180009cf6  mov     rax, [rax+r12*8]
0x180009cfa  inc     r14d
0x180009cfd  mov     rcx, [r13+20h]
0x180009d01  mov     [rcx+r15*8], rax
0x180009d05  xor     r15d, r15d
0x180009d08  inc     qword ptr [r13+28h]
0x180009d0c  mov     rax, [rbp+arg_10]
0x180009d10  mov     [rax+r12*8], r15
0x180009d14  cmp     r14d, [rbp+arg_8]
0x180009d18  jb      short loc_180009CCC
0x180009d1a  lea     rsi, WPP_GLOBAL_Control
0x180009d21  mov     rcx, [rbp+arg_10]; pv
0x180009d25  call    cs:__imp_CoTaskMemFree
0x180009d2b  mov     [rbp+arg_10], r15
0x180009d2f  inc     ebx
0x180009d31  cmp     ebx, [rbp+arg_0]
0x180009d34  jb      loc_180009C70
0x180009d3a  jmp     loc_180009C0F
0x180009d3f  mov     ecx, 8007000Eh; int
0x180009d44  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
