# CCorrAPOBase::UpdateFeaturesEnabled(ulong,ulong *)

- ea: `0x1800093b0`
- end: `0x1800094a2`
- name: `?UpdateFeaturesEnabled@CCorrAPOBase@@IEAAXKPEAK@Z`
- size: `242`
- prototype: `void __fastcall(CCorrAPOBase *this, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180008df0`
- `0x180009040`
- `0x1800090e0`

## callees

- `0x1800093b0`
- `0x1800094a8`
- `0x180086010`

## pseudocode

```c
void __fastcall CCorrAPOBase::UpdateFeaturesEnabled(CCorrAPOBase *this, unsigned int a2, unsigned int *a3)
{
  int v4; // eax
  unsigned int v5; // edx
  __int64 v6; // r9
  unsigned int *v7; // r8
  unsigned int v8; // ebx
  int v9; // edi
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  _BYTE v16[56]; // [rsp+20h] [rbp-38h] BYREF

  v4 = PropIdx2FeatureIdx(a2);
  v8 = *v7;
  if ( v4 >= 0 )
  {
    v9 = 1 << v4;
    if ( !*(_WORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v6 + 184LL))(v6, v16, v5) )
    {
      v8 &= ~v9;
      goto LABEL_4;
    }
LABEL_9:
    v8 |= v9;
    goto LABEL_4;
  }
  if ( v5 == 11 )
  {
    v9 = 0;
    v11 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 184LL))(v6, v16);
    if ( v11 )
    {
      v15 = v11 - 1;
      if ( v15 )
      {
        if ( v15 == 1 )
          v9 = 64;
      }
      else
      {
        v9 = 1;
      }
    }
    v8 &= 0xFFFFFFBE;
    goto LABEL_9;
  }
  if ( v5 == 9 )
  {
    v9 = 0;
    v10 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 184LL))(v6, v16);
    if ( v10 )
    {
      v12 = v10 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 == 1 )
              v9 = 32;
          }
          else
          {
            v9 = 16;
          }
        }
        else
        {
          v9 = 2;
        }
      }
    }
    v8 &= 0xFFFFFF4D;
    goto LABEL_9;
  }
LABEL_4:
  *a3 = v8;
}

```

## disassembly

```asm
0x1800093b0  push    rbx
0x1800093b2  push    rbp
0x1800093b3  push    rsi
0x1800093b4  push    rdi
0x1800093b5  sub     rsp, 38h
0x1800093b9  mov     r9, rcx
0x1800093bc  mov     rsi, r8
0x1800093bf  mov     ecx, edx; unsigned int
0x1800093c1  call    ?PropIdx2FeatureIdx@@YAHK@Z; PropIdx2FeatureIdx(ulong)
0x1800093c6  mov     ebx, [r8]
0x1800093c9  xor     ebp, ebp
0x1800093cb  test    eax, eax
0x1800093cd  jns     short loc_1800093EC
0x1800093cf  lea     r8d, [rbp+0Bh]
0x1800093d3  cmp     edx, r8d
0x1800093d6  jz      short loc_180009443
0x1800093d8  lea     r8d, [rbp+9]
0x1800093dc  cmp     edx, r8d
0x1800093df  jz      short loc_18000941A
0x1800093e1  mov     [rsi], ebx
0x1800093e3  add     rsp, 38h
0x1800093e7  pop     rdi
0x1800093e8  pop     rsi
0x1800093e9  pop     rbp
0x1800093ea  pop     rbx
0x1800093eb  retn
0x1800093ec  mov     ecx, eax
0x1800093ee  mov     r8d, edx
0x1800093f1  mov     rax, [r9]
0x1800093f4  lea     rdx, [rsp+58h+var_38]
0x1800093f9  mov     edi, 1
0x1800093fe  shl     edi, cl
0x180009400  mov     rcx, r9
0x180009403  mov     rax, [rax+0B8h]
0x18000940a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000940f  cmp     [rax], bp
0x180009412  jnz     short loc_18000943F
0x180009414  not     edi
0x180009416  and     ebx, edi
0x180009418  jmp     short loc_1800093E1
0x18000941a  mov     rax, [r9]
0x18000941d  lea     rdx, [rsp+58h+var_38]
0x180009422  mov     rcx, r9
0x180009425  mov     edi, ebp
0x180009427  mov     rax, [rax+0B8h]
0x18000942e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009433  mov     edx, [rax]
0x180009435  test    edx, edx
0x180009437  jnz     short loc_180009467
0x180009439  and     ebx, 0FFFFFF4Dh
0x18000943f  or      ebx, edi
0x180009441  jmp     short loc_1800093E1
0x180009443  mov     rax, [r9]
0x180009446  lea     rdx, [rsp+58h+var_38]
0x18000944b  mov     rcx, r9
0x18000944e  mov     edi, ebp
0x180009450  mov     rax, [rax+0B8h]
0x180009457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000945c  mov     edx, [rax]
0x18000945e  test    edx, edx
0x180009460  jnz     short loc_180009485
0x180009462  and     ebx, 0FFFFFFBEh
0x180009465  jmp     short loc_18000943F
0x180009467  sub     edx, 1
0x18000946a  jz      short loc_180009439
0x18000946c  sub     edx, 1
0x18000946f  jz      short loc_18000949B
0x180009471  sub     edx, 1
0x180009474  jnz     short loc_18000947B
0x180009476  lea     edi, [rdx+10h]
0x180009479  jmp     short loc_180009439
0x18000947b  cmp     edx, 1
0x18000947e  jnz     short loc_180009439
0x180009480  lea     edi, [rdx+1Fh]
0x180009483  jmp     short loc_180009439
0x180009485  sub     edx, 1
0x180009488  jz      short loc_180009494
0x18000948a  cmp     edx, 1
0x18000948d  jnz     short loc_180009462
0x18000948f  lea     edi, [rdx+3Fh]
0x180009492  jmp     short loc_180009462
0x180009494  mov     edi, 1
0x180009499  jmp     short loc_180009462
0x18000949b  mov     edi, 2
0x1800094a0  jmp     short loc_180009439
```
