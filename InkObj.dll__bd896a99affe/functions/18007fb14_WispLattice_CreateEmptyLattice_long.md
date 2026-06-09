# WispLattice::CreateEmptyLattice(long)

- ea: `0x18007fb14`
- end: `0x18007fcd4`
- name: `?CreateEmptyLattice@WispLattice@@QEAAJJ@Z`
- size: `448`
- prototype: `__int64 __fastcall(WispLattice *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a4064`

## callees

- `0x18007fb14`
- `0x180083580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fbc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fb81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fbc5`

## pseudocode

```c
__int64 __fastcall WispLattice::CreateEmptyLattice(WispLattice *this, int a2)
{
  __int64 v2; // rsi
  unsigned int v4; // edi
  LPVOID v5; // rax
  LPVOID v6; // rax
  LPVOID v7; // rcx
  unsigned int *v8; // rax
  _DWORD *v9; // rax
  unsigned int v10; // r8d
  unsigned int v11; // edx

  v2 = a2;
  v4 = 0;
  if ( *(_QWORD *)this )
  {
    **(_DWORD **)this = 1;
    *(_QWORD *)(*(_QWORD *)this + 8LL) = CoTaskMemAlloc(56LL * **(unsigned int **)this);
    *(_DWORD *)(*(_QWORD *)this + 32LL) = 1;
    *(_QWORD *)(*(_QWORD *)this + 40LL) = CoTaskMemAlloc(4LL * *(unsigned int *)(*(_QWORD *)this + 32LL));
    *(_QWORD *)(*(_QWORD *)this + 48LL) = CoTaskMemAlloc(4LL * *(unsigned int *)(*(_QWORD *)this + 32LL));
    *(_DWORD *)(*(_QWORD *)this + 16LL) = 0;
    *(_QWORD *)(*(_QWORD *)this + 24LL) = 0;
    v5 = CoTaskMemAlloc(4 * v2);
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = v5;
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 21) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    v6 = CoTaskMemAlloc(0x28u);
    *((_QWORD *)this + 6) = v6;
    v7 = v6;
    v8 = *(unsigned int **)this;
    if ( *(_QWORD *)(*(_QWORD *)this + 40LL) && *((_QWORD *)v8 + 6) && *((_QWORD *)this + 2) && v7 )
    {
      v9 = (_DWORD *)*((_QWORD *)v8 + 1);
      v10 = v2;
      v11 = 0;
      if ( (int)v2 <= 0 )
        v10 = 0;
      *v9 = 0;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 8LL) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 16LL) = 0;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 24LL) = v2;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 32LL) = *((_QWORD *)this + 2);
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 40LL) = 1;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 48LL) = *((_QWORD *)this + 6);
      **(_DWORD **)(*(_QWORD *)this + 40LL) = 0;
      **(_DWORD **)(*(_QWORD *)this + 48LL) = 0;
      while ( v11 < v10 )
      {
        *(_DWORD *)(*((_QWORD *)this + 2) + 4LL * v11) = v11;
        ++v11;
      }
      **((_DWORD **)this + 6) = 0;
      *(_WORD *)(*((_QWORD *)this + 6) + 4LL) = 0;
      *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = &qword_180125668;
      *(_DWORD *)(*((_QWORD *)this + 6) + 16LL) = 1;
      *(_DWORD *)(*((_QWORD *)this + 6) + 20LL) = v2;
      *(_DWORD *)(*((_QWORD *)this + 6) + 24LL) = 0;
      *(_QWORD *)(*((_QWORD *)this + 6) + 32LL) = 0;
    }
    else
    {
      WispLattice::Reset(this);
      return (unsigned int)-2147024882;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18007fb14  push    rbx
0x18007fb16  push    rbp
0x18007fb17  push    rsi
0x18007fb18  push    rdi
0x18007fb19  sub     rsp, 28h
0x18007fb1d  mov     rax, [rcx]
0x18007fb20  xor     ebp, ebp
0x18007fb22  movsxd  rsi, edx
0x18007fb25  mov     rbx, rcx
0x18007fb28  mov     edi, ebp
0x18007fb2a  test    rax, rax
0x18007fb2d  jz      loc_18007FCC9
0x18007fb33  mov     dword ptr [rax], 1
0x18007fb39  mov     rax, [rcx]
0x18007fb3c  mov     r8d, [rax]
0x18007fb3f  imul    rcx, r8, 38h ; '8'; cb
0x18007fb43  call    cs:__imp_CoTaskMemAlloc
0x18007fb49  mov     rdx, rax
0x18007fb4c  mov     rax, [rbx]
0x18007fb4f  mov     [rax+8], rdx
0x18007fb53  mov     rax, [rbx]
0x18007fb56  mov     dword ptr [rax+20h], 1
0x18007fb5d  mov     rax, [rbx]
0x18007fb60  mov     ecx, [rax+20h]
0x18007fb63  shl     rcx, 2; cb
0x18007fb67  call    cs:__imp_CoTaskMemAlloc
0x18007fb6d  mov     rcx, rax
0x18007fb70  mov     rax, [rbx]
0x18007fb73  mov     [rax+28h], rcx
0x18007fb77  mov     rax, [rbx]
0x18007fb7a  mov     ecx, [rax+20h]
0x18007fb7d  shl     rcx, 2; cb
0x18007fb81  call    cs:__imp_CoTaskMemAlloc
0x18007fb87  mov     rcx, rax
0x18007fb8a  mov     rax, [rbx]
0x18007fb8d  mov     [rax+30h], rcx
0x18007fb91  mov     rcx, rsi
0x18007fb94  mov     rax, [rbx]
0x18007fb97  shl     rcx, 2; cb
0x18007fb9b  mov     [rax+10h], ebp
0x18007fb9e  mov     rax, [rbx]
0x18007fba1  mov     [rax+18h], rbp
0x18007fba5  call    cs:__imp_CoTaskMemAlloc
0x18007fbab  lea     ecx, [rbp+28h]; cb
0x18007fbae  mov     [rbx+8], rbp
0x18007fbb2  mov     [rbx+10h], rax
0x18007fbb6  mov     [rbx+18h], rbp
0x18007fbba  mov     [rbx+54h], ebp
0x18007fbbd  mov     [rbx+20h], rbp
0x18007fbc1  mov     [rbx+28h], rbp
0x18007fbc5  call    cs:__imp_CoTaskMemAlloc
0x18007fbcb  mov     [rbx+30h], rax
0x18007fbcf  mov     rcx, rax
0x18007fbd2  mov     rax, [rbx]
0x18007fbd5  cmp     [rax+28h], rbp
0x18007fbd9  jz      loc_18007FCBC
0x18007fbdf  cmp     [rax+30h], rbp
0x18007fbe3  jz      loc_18007FCBC
0x18007fbe9  cmp     [rbx+10h], rbp
0x18007fbed  jz      loc_18007FCBC
0x18007fbf3  test    rcx, rcx
0x18007fbf6  jz      loc_18007FCBC
0x18007fbfc  mov     rax, [rax+8]
0x18007fc00  test    esi, esi
0x18007fc02  mov     r8d, esi
0x18007fc05  mov     edx, ebp
0x18007fc07  cmovle  r8d, ebp
0x18007fc0b  mov     [rax], ebp
0x18007fc0d  mov     rax, [rbx]
0x18007fc10  mov     rcx, [rax+8]
0x18007fc14  mov     [rcx+8], ebp
0x18007fc17  mov     rax, [rbx]
0x18007fc1a  mov     rcx, [rax+8]
0x18007fc1e  mov     [rcx+10h], rbp
0x18007fc22  mov     rax, [rbx]
0x18007fc25  mov     rcx, [rax+8]
0x18007fc29  mov     [rcx+18h], esi
0x18007fc2c  mov     rax, [rbx]
0x18007fc2f  mov     rcx, [rax+8]
0x18007fc33  mov     rax, [rbx+10h]
0x18007fc37  mov     [rcx+20h], rax
0x18007fc3b  mov     rax, [rbx]
0x18007fc3e  mov     rcx, [rax+8]
0x18007fc42  mov     dword ptr [rcx+28h], 1
0x18007fc49  mov     rax, [rbx]
0x18007fc4c  mov     rcx, [rax+8]
0x18007fc50  mov     rax, [rbx+30h]
0x18007fc54  mov     [rcx+30h], rax
0x18007fc58  mov     rax, [rbx]
0x18007fc5b  mov     rcx, [rax+28h]
0x18007fc5f  mov     [rcx], ebp
0x18007fc61  mov     rax, [rbx]
0x18007fc64  mov     rcx, [rax+30h]
0x18007fc68  mov     [rcx], ebp
0x18007fc6a  cmp     edx, r8d
0x18007fc6d  jnb     short loc_18007FC7C
0x18007fc6f  mov     rax, [rbx+10h]
0x18007fc73  mov     ecx, edx
0x18007fc75  mov     [rax+rcx*4], edx
0x18007fc78  inc     edx
0x18007fc7a  jmp     short loc_18007FC6A
0x18007fc7c  mov     rax, [rbx+30h]
0x18007fc80  mov     [rax], ebp
0x18007fc82  mov     rcx, [rbx+30h]
0x18007fc86  mov     [rcx+4], bp
0x18007fc8a  lea     rcx, qword_180125668
0x18007fc91  mov     rax, [rbx+30h]
0x18007fc95  mov     [rax+8], rcx
0x18007fc99  mov     rax, [rbx+30h]
0x18007fc9d  mov     dword ptr [rax+10h], 1
0x18007fca4  mov     rax, [rbx+30h]
0x18007fca8  mov     [rax+14h], esi
0x18007fcab  mov     rax, [rbx+30h]
0x18007fcaf  mov     [rax+18h], ebp
0x18007fcb2  mov     rax, [rbx+30h]
0x18007fcb6  mov     [rax+20h], rbp
0x18007fcba  jmp     short loc_18007FCC9
0x18007fcbc  mov     rcx, rbx; this
0x18007fcbf  call    ?Reset@WispLattice@@QEAAXXZ; WispLattice::Reset(void)
0x18007fcc4  mov     edi, 8007000Eh
0x18007fcc9  mov     eax, edi
0x18007fccb  add     rsp, 28h
0x18007fccf  pop     rdi
0x18007fcd0  pop     rsi
0x18007fcd1  pop     rbp
0x18007fcd2  pop     rbx
0x18007fcd3  retn
```
