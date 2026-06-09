# CWMDSPPropImpl2::internalGetValue(ulong,tagPROPVARIANT *)

- ea: `0x180083b10`
- end: `0x180083c90`
- name: `?internalGetValue@CWMDSPPropImpl2@@MEAAJKPEAUtagPROPVARIANT@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(CWMDSPPropImpl2 *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18006ba30`

## callees

- `0x180083768`
- `0x1800837a4`
- `0x180083b10`
- `0x180084690`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180083bf5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180083bf5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180083c16`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180083c16`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180083c4c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180083c4c`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl2::internalGetValue(CWMDSPPropImpl2 *this, unsigned int a2, struct tagPROPVARIANT *a3)
{
  _QWORD *v5; // rsi
  __int64 v6; // rcx
  HRESULT v7; // edi
  __int64 v8; // r15
  signed int v9; // r10d
  int v10; // r12d
  __int64 v11; // rdx
  __int64 v12; // r14
  signed int v13; // r9d
  __int64 v14; // r8
  _QWORD *v15; // rcx
  SAFEARRAY *v16; // rax
  int v17; // eax
  void *ppvData; // [rsp+60h] [rbp+18h] BYREF

  if ( (a3->vt & 0x2000) != 0 )
  {
    v5 = (_QWORD *)((char *)this + 96);
    ppvData = 0;
    if ( *((_QWORD *)this + 12)
      && (v6 = *(int *)(96LL * a2 + *((_QWORD *)this + 2) + 92), (int)v6 >= 0)
      && (int)v6 < *((_DWORD *)this + 22) )
    {
      v7 = 0;
      _mm_lfence();
      v8 = 3 * v6;
      v9 = 0;
      v10 = 1;
      v11 = *(int *)(96LL * a2 + *((_QWORD *)this + 2) + 92);
      v12 = 8 * v6;
      v13 = *(_DWORD *)(*v5 + 24 * v6 + 4);
      if ( v13 <= 0 )
      {
        v15 = (_QWORD *)((char *)this + 96);
      }
      else
      {
        v14 = 0;
        do
        {
          ++v9;
          *(_DWORD *)(*((_QWORD *)this + 15) + 8 * v14 + 4) = 1;
          *(_DWORD *)(*((_QWORD *)this + 15) + 8 * v14) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 8 * v6)
                                                                    + 4 * v14);
          v10 *= *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 8 * v6) + 4 * v14++);
        }
        while ( v9 < v13 );
        v15 = (_QWORD *)((char *)this + 96);
      }
      v16 = SafeArrayCreate(*(_WORD *)(*v15 + 24 * v11), v13, *((SAFEARRAYBOUND **)this + 15));
      a3->hVal.QuadPart = (LONGLONG)v16;
      if ( v16 && *(_QWORD *)(v12 + *((_QWORD *)this + 13)) )
      {
        v7 = SafeArrayAccessData(v16, &ppvData);
        if ( v7 >= 0 )
        {
          v17 = WMDSPPropMemSize(*(_WORD *)(*v5 + 8 * v8));
          memcpy_0(ppvData, *(const void **)(v12 + *((_QWORD *)this + 13)), v10 * v17);
          return (unsigned int)SafeArrayUnaccessData(a3->parray);
        }
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
    return (unsigned int)v7;
  }
  else
  {
    WMDSPPropVal2Var(a3, *((_QWORD *)this + 3) + 8 * (9LL * a2 + 1));
    return 0;
  }
}

```

## disassembly

```asm
0x180083b10  mov     [rsp+arg_0], rbx
0x180083b15  mov     [rsp+arg_8], rbp
0x180083b1a  push    rsi
0x180083b1b  push    rdi
0x180083b1c  push    r12
0x180083b1e  push    r14
0x180083b20  push    r15
0x180083b22  sub     rsp, 20h
0x180083b26  mov     rbx, rcx
0x180083b29  mov     eax, edx
0x180083b2b  mov     ecx, 2000h
0x180083b30  mov     rbp, r8
0x180083b33  test    [r8], cx
0x180083b37  jz      loc_180083C5F
0x180083b3d  lea     rsi, [rbx+60h]
0x180083b41  mov     [rsp+48h+ppvData], 0
0x180083b4a  cmp     qword ptr [rsi], 0
0x180083b4e  jz      loc_180083C56
0x180083b54  lea     rdx, [rax+rax*2]
0x180083b58  mov     rax, [rbx+10h]
0x180083b5c  shl     rdx, 5
0x180083b60  movsxd  rcx, dword ptr [rdx+rax+5Ch]
0x180083b65  test    ecx, ecx
0x180083b67  js      loc_180083C56
0x180083b6d  cmp     ecx, [rbx+58h]
0x180083b70  jge     loc_180083C56
0x180083b76  xor     edi, edi
0x180083b78  lfence
0x180083b7b  mov     rax, [rsi]
0x180083b7e  lea     r15, [rcx+rcx*2]
0x180083b82  xor     r10d, r10d
0x180083b85  lea     r12d, [rdi+1]
0x180083b89  mov     rdx, rcx
0x180083b8c  lea     r14, ds:0[rcx*8]
0x180083b94  mov     r9d, [rax+r15*8+4]
0x180083b99  test    r9d, r9d
0x180083b9c  jle     short loc_180083BE0
0x180083b9e  xor     r8d, r8d
0x180083ba1  mov     rax, [rbx+78h]
0x180083ba5  inc     r10d
0x180083ba8  mov     dword ptr [rax+r8*8+4], 1
0x180083bb1  mov     rax, [rbx+70h]
0x180083bb5  mov     rcx, [rbx+78h]
0x180083bb9  mov     rax, [rax+r14]
0x180083bbd  mov     eax, [rax+r8*4]
0x180083bc1  mov     [rcx+r8*8], eax
0x180083bc5  mov     rax, [rbx+70h]
0x180083bc9  mov     rcx, [rax+r14]
0x180083bcd  imul    r12d, [rcx+r8*4]
0x180083bd2  inc     r8
0x180083bd5  cmp     r10d, r9d
0x180083bd8  jl      short loc_180083BA1
0x180083bda  lea     rcx, [rbx+60h]
0x180083bde  jmp     short loc_180083BE3
0x180083be0  mov     rcx, rsi
0x180083be3  mov     rcx, [rcx]
0x180083be6  lea     rax, [rdx+rdx*2]
0x180083bea  mov     r8, [rbx+78h]; rgsabound
0x180083bee  mov     edx, r9d; cDims
0x180083bf1  movzx   ecx, word ptr [rcx+rax*8]; vt
0x180083bf5  call    cs:__imp_SafeArrayCreate
0x180083bfb  mov     [rbp+8], rax
0x180083bff  mov     rcx, rax; psa
0x180083c02  test    rax, rax
0x180083c05  jz      short loc_180083C5B
0x180083c07  mov     rax, [rbx+68h]
0x180083c0b  cmp     [r14+rax], rdi
0x180083c0f  jz      short loc_180083C5B
0x180083c11  lea     rdx, [rsp+48h+ppvData]; ppvData
0x180083c16  call    cs:__imp_SafeArrayAccessData
0x180083c1c  mov     edi, eax
0x180083c1e  test    eax, eax
0x180083c20  js      short loc_180083C5B
0x180083c22  mov     rcx, [rsi]
0x180083c25  movzx   ecx, word ptr [rcx+r15*8]; unsigned __int16
0x180083c2a  call    ?WMDSPPropMemSize@@YAJG@Z; WMDSPPropMemSize(ushort)
0x180083c2f  mov     rdx, [rbx+68h]
0x180083c33  mov     rcx, [rsp+48h+ppvData]; void *
0x180083c38  imul    eax, r12d
0x180083c3c  mov     rdx, [r14+rdx]; Src
0x180083c40  movsxd  r8, eax; Size
0x180083c43  call    memcpy_0
0x180083c48  mov     rcx, [rbp+8]; psa
0x180083c4c  call    cs:__imp_SafeArrayUnaccessData
0x180083c52  mov     edi, eax
0x180083c54  jmp     short loc_180083C5B
0x180083c56  mov     edi, 8000FFFFh
0x180083c5b  mov     eax, edi
0x180083c5d  jmp     short loc_180083C79
0x180083c5f  lea     rcx, [rax+rax*8]
0x180083c63  mov     rax, [rbx+18h]
0x180083c67  lea     rcx, [rcx+1]
0x180083c6b  lea     rdx, [rax+rcx*8]
0x180083c6f  mov     rcx, rbp
0x180083c72  call    WMDSPPropVal2Var
0x180083c77  xor     eax, eax
0x180083c79  mov     rbx, [rsp+48h+arg_0]
0x180083c7e  mov     rbp, [rsp+48h+arg_8]
0x180083c83  add     rsp, 20h
0x180083c87  pop     r15
0x180083c89  pop     r14
0x180083c8b  pop     r12
0x180083c8d  pop     rdi
0x180083c8e  pop     rsi
0x180083c8f  retn
```
