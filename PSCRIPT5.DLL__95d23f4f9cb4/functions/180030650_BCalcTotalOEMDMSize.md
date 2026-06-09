# BCalcTotalOEMDMSize

- ea: `0x180030650`
- end: `0x1800307c4`
- name: `BCalcTotalOEMDMSize`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800033f4`
- `0x18003005c`

## callees

- `0x1800028d8`
- `0x180030650`
- `0x180030bcc`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall BCalcTotalOEMDMSize(__int64 a1, __int64 *a2, _DWORD *a3)
{
  int v6; // ebp
  int v7; // r14d
  __int64 *i; // rbx
  __int64 v9; // rsi
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ecx
  unsigned int (__fastcall *v14)(__int64, int *); // rax
  int v16; // [rsp+20h] [rbp-88h] BYREF
  __int64 v17; // [rsp+28h] [rbp-80h]
  __int64 v18; // [rsp+30h] [rbp-78h]
  __int64 v19; // [rsp+38h] [rbp-70h]
  int v20; // [rsp+60h] [rbp-48h]

  memset_0(&v16, 0, 0x48u);
  v6 = *((_DWORD *)a2 + 2);
  *a3 = 0;
  if ( !v6 )
    return 1;
  v7 = 0;
  for ( i = a2 + 3; ; i += 22 )
  {
    v9 = i[4];
    if ( v9 )
      break;
LABEL_20:
    if ( !--v6 )
    {
      *a3 = v7;
      return 1;
    }
  }
  v10 = *((_DWORD *)i + 12);
  if ( (v10 & 4) != 0 )
    goto LABEL_19;
  *((_DWORD *)i + 12) = v10 | 4;
  memset_0(&v16, 0, 0x48u);
  v11 = i[9];
  v12 = *a2;
  v16 = 72;
  v17 = v12;
  v18 = a1;
  v19 = v9;
  if ( !v11 )
  {
    if ( (*((_BYTE *)i + 100) & 2) == 0 )
    {
      v14 = (unsigned int (__fastcall *)(__int64, int *))PGetOemEntrypointAddress(i, 1);
      if ( v14 )
      {
        if ( !v14(1, &v16) )
          goto LABEL_23;
        goto LABEL_17;
      }
    }
LABEL_19:
    v7 += *((_DWORD *)i + 16);
    goto LABEL_20;
  }
  if ( i[10] == *(_QWORD *)&IID_IPrintOemPS.Data1 && i[11] == *(_QWORD *)IID_IPrintOemPS.Data4
    || i[10] == *(_QWORD *)&IID_IPrintOemPS2.Data1 && i[11] == *(_QWORD *)IID_IPrintOemPS2.Data4 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v11 + 32LL))(v11, 1, &v16);
    if ( (int)(v13 + 0x80000000) < 0 || v13 == -2147467263 )
    {
      if ( ~v13 < 0 )
      {
LABEL_17:
        if ( (unsigned int)(v20 - 1) <= 0xA )
          goto LABEL_23;
        *((_DWORD *)i + 16) = v20;
        goto LABEL_19;
      }
      goto LABEL_19;
    }
  }
LABEL_23:
  *((_DWORD *)i + 12) &= ~4u;
  return 0;
}

```

## disassembly

```asm
0x180030650  push    rbx
0x180030652  push    rbp
0x180030653  push    rsi
0x180030654  push    r12
0x180030656  push    r13
0x180030658  push    r14
0x18003065a  push    r15
0x18003065c  sub     rsp, 70h
0x180030660  mov     r15, rdx
0x180030663  mov     r12, r8
0x180030666  xor     edx, edx; Val
0x180030668  mov     r13, rcx
0x18003066b  lea     rcx, [rsp+0A8h+var_88]; void *
0x180030670  lea     r8d, [rdx+48h]; Size
0x180030674  call    memset_0
0x180030679  mov     ebp, [r15+8]
0x18003067d  mov     dword ptr [r12], 0
0x180030685  test    ebp, ebp
0x180030687  jz      loc_1800307A7
0x18003068d  xor     r14d, r14d
0x180030690  lea     rbx, [r15+18h]
0x180030694  mov     rsi, [rbx+20h]
0x180030698  test    rsi, rsi
0x18003069b  jz      loc_180030793
0x1800306a1  mov     eax, [rbx+30h]
0x1800306a4  test    al, 4
0x1800306a6  jnz     loc_18003078F
0x1800306ac  xor     edx, edx; Val
0x1800306ae  lea     rcx, [rsp+0A8h+var_88]; void *
0x1800306b3  or      eax, 4
0x1800306b6  mov     [rbx+30h], eax
0x1800306b9  lea     r8d, [rdx+48h]; Size
0x1800306bd  call    memset_0
0x1800306c2  mov     rcx, [rbx+48h]
0x1800306c6  mov     rax, [r15]
0x1800306c9  mov     [rsp+0A8h+var_88], 48h ; 'H'
0x1800306d1  mov     [rsp+0A8h+var_80], rax
0x1800306d6  mov     [rsp+0A8h+var_78], r13
0x1800306db  mov     [rsp+0A8h+var_70], rsi
0x1800306e0  test    rcx, rcx
0x1800306e3  jz      short loc_180030755
0x1800306e5  mov     rax, [rbx+50h]
0x1800306e9  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x1800306f0  jnz     short loc_1800306FF
0x1800306f2  mov     rax, [rbx+58h]
0x1800306f6  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x1800306fd  jz      short loc_180030721
0x1800306ff  mov     rax, [rbx+50h]
0x180030703  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18003070a  jnz     loc_1800307BC
0x180030710  mov     rax, [rbx+58h]
0x180030714  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18003071b  jnz     loc_1800307BC
0x180030721  mov     rax, [rcx]
0x180030724  lea     r8, [rsp+0A8h+var_88]
0x180030729  mov     edx, 1
0x18003072e  mov     rax, [rax+20h]
0x180030732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030737  mov     edx, 80000000h
0x18003073c  mov     ecx, eax
0x18003073e  lea     eax, [rax+rdx]
0x180030741  test    edx, eax
0x180030743  jnz     short loc_18003074D
0x180030745  cmp     ecx, 80004001h
0x18003074b  jnz     short loc_1800307BC
0x18003074d  not     ecx
0x18003074f  test    edx, ecx
0x180030751  jz      short loc_18003078F
0x180030753  jmp     short loc_180030780
0x180030755  test    byte ptr [rbx+64h], 2
0x180030759  jnz     short loc_18003078F
0x18003075b  mov     edx, 1
0x180030760  mov     rcx, rbx
0x180030763  call    PGetOemEntrypointAddress
0x180030768  test    rax, rax
0x18003076b  jz      short loc_18003078F
0x18003076d  lea     rdx, [rsp+0A8h+var_88]
0x180030772  mov     ecx, 1
0x180030777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003077c  test    eax, eax
0x18003077e  jz      short loc_1800307BC
0x180030780  mov     ecx, [rsp+0A8h+var_48]
0x180030784  lea     eax, [rcx-1]
0x180030787  cmp     eax, 0Ah
0x18003078a  jbe     short loc_1800307BC
0x18003078c  mov     [rbx+40h], ecx
0x18003078f  add     r14d, [rbx+40h]
0x180030793  add     rbx, 0B0h
0x18003079a  add     ebp, 0FFFFFFFFh
0x18003079d  jnz     loc_180030694
0x1800307a3  mov     [r12], r14d
0x1800307a7  mov     eax, 1
0x1800307ac  add     rsp, 70h
0x1800307b0  pop     r15
0x1800307b2  pop     r14
0x1800307b4  pop     r13
0x1800307b6  pop     r12
0x1800307b8  pop     rsi
0x1800307b9  pop     rbp
0x1800307ba  pop     rbx
0x1800307bb  retn
0x1800307bc  and     dword ptr [rbx+30h], 0FFFFFFFBh
0x1800307c0  xor     eax, eax
0x1800307c2  jmp     short loc_1800307AC
```
