# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeHelper<_lambda_fe718337787c493ce2d833414db25eba_>(ushort const *,char *,_lambda_fe718337787c493ce2d833414db25eba_ const &)

- ea: `0x1400022f0`
- end: `0x14000250e`
- name: `??$_InitializeHelper@V_lambda_fe718337787c493ce2d833414db25eba_@@@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBGPEADAEBV_lambda_fe718337787c493ce2d833414db25eba_@@@Z`
- size: `542`
- prototype: `__int64(__int64, const wchar_t *, va_list, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140002dc0`

## callees

- `0x1400022f0`

## import_xrefs

- `msvcrt!_get_errno` at `0x140002499`
- `msvcrt!_get_errno` at `0x140002499`
- `msvcrt!_set_errno` at `0x1400023bc`
- `msvcrt!_set_errno` at `0x1400023bc`
- `msvcrt!_vsnwprintf` at `0x1400023e7`
- `msvcrt!_vsnwprintf` at `0x1400023e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140002390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140002390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140002450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x140002450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400024e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400024e8`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeHelper<_lambda_fe718337787c493ce2d833414db25eba_>(
        __int64 a1,
        const wchar_t *a2,
        va_list a3,
        ...)
{
  __int64 v3; // r15
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rbp
  unsigned __int64 *v9; // rdi
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  _WORD *v12; // rax
  int v13; // ebx
  unsigned __int64 v14; // rbp
  wchar_t *v15; // r14
  size_t v16; // rbp
  int v17; // eax
  unsigned __int64 v18; // rbx
  LPVOID v19; // rax
  __int64 Value; // [rsp+88h] [rbp+20h] BYREF
  va_list Valuea; // [rsp+88h] [rbp+20h]
  va_list va1; // [rsp+90h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(Valuea, a3);
  Value = va_arg(va1, _QWORD);
  v3 = -1;
  v7 = 32;
  while ( 1 )
  {
    v8 = v7 + 1;
    v9 = (unsigned __int64 *)(a1 + 16);
    if ( v7 + 1 < v7 )
      break;
    v10 = *v9;
    if ( *v9 == -1 )
    {
      v11 = *(_QWORD *)(a1 + 8);
      if ( v11 == -1 )
      {
        if ( *(_QWORD *)a1 )
        {
          v11 = -1;
          do
            ++v11;
          while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v11) );
        }
        else
        {
          v11 = 0;
        }
        *(_QWORD *)(a1 + 8) = v11;
      }
      v10 = (v11 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
      *v9 = v10;
    }
    if ( !v10 )
    {
      Value = 0;
      if ( !is_mul_ok(v8, 2u) )
        break;
      v12 = CoTaskMemAlloc(2 * v8);
      if ( v12 )
      {
        *v9 = v8;
        *(_QWORD *)a1 = v12;
        *v12 = 0;
        goto LABEL_18;
      }
      v13 = -2147024882;
LABEL_17:
      if ( v13 < 0 )
        goto LABEL_43;
      goto LABEL_18;
    }
    v13 = 0;
    if ( v8 <= v10 )
      goto LABEL_17;
    Value = 0;
    v18 = 2 * v10;
    if ( !is_mul_ok(v10, 2u) )
      break;
    if ( v10 > 0x800 )
      v18 = v10 + 2048;
    if ( v8 > v18 )
      v18 = v8;
    v19 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v18);
    if ( !v19 )
    {
      v13 = -2147024882;
      goto LABEL_42;
    }
    *v9 = v18;
    *(_QWORD *)a1 = v19;
LABEL_18:
    v14 = *v9;
    v15 = *(wchar_t **)a1;
    _set_errno(0);
    if ( v14 )
    {
      if ( v14 > 0x7FFFFFFF )
      {
        *v15 = 0;
LABEL_40:
        v13 = -2147024809;
        goto LABEL_42;
      }
      v16 = v14 - 1;
      v17 = _vsnwprintf(v15, v16, a2, a3);
      if ( v17 < 0 || v17 > v16 )
      {
        v13 = -2147024774;
        v15[v16] = 0;
      }
      else
      {
        v13 = 0;
        if ( v17 == v16 )
          v15[v16] = 0;
      }
    }
    else
    {
      v13 = -2147024809;
    }
    if ( v13 != -2147024774 )
      goto LABEL_42;
    LODWORD(Value) = 0;
    _get_errno((int *)Valuea);
    if ( (_DWORD)Value == 22 )
      goto LABEL_40;
    v7 = *v9 + 32;
    if ( v7 < *v9 )
    {
      v13 = -2147024362;
      goto LABEL_43;
    }
  }
  v13 = -2147024362;
LABEL_42:
  if ( v13 >= 0 )
    goto LABEL_46;
LABEL_43:
  if ( *(_QWORD *)a1 )
  {
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
  }
  *v9 = 0;
  v3 = 0;
LABEL_46:
  *(_QWORD *)(a1 + 8) = v3;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400022f0  mov     [rsp+Value], r9
0x1400022f5  push    rbx
0x1400022f6  push    rbp
0x1400022f7  push    rsi
0x1400022f8  push    rdi
0x1400022f9  push    r12
0x1400022fb  push    r13
0x1400022fd  push    r14
0x1400022ff  push    r15
0x140002301  sub     rsp, 28h
0x140002305  or      r15, 0FFFFFFFFFFFFFFFFh
0x140002309  mov     rsi, rcx
0x14000230c  xor     r14d, r14d
0x14000230f  mov     r12, r8
0x140002312  mov     r13, rdx
0x140002315  mov     ecx, 20h ; ' '
0x14000231a  lea     rbp, [rcx+1]
0x14000231e  lea     rdi, [rsi+10h]
0x140002322  cmp     rbp, rcx
0x140002325  jb      loc_1400024D7
0x14000232b  mov     r8, [rdi]
0x14000232e  cmp     r8, r15
0x140002331  jnz     short loc_14000236C
0x140002333  mov     rcx, [rsi+8]
0x140002337  cmp     rcx, r15
0x14000233a  jnz     short loc_14000235A
0x14000233c  mov     rax, [rsi]
0x14000233f  test    rax, rax
0x140002342  jz      short loc_140002353
0x140002344  mov     rcx, r15
0x140002347  inc     rcx
0x14000234a  cmp     [rax+rcx*2], r14w
0x14000234f  jnz     short loc_140002347
0x140002351  jmp     short loc_140002356
0x140002353  mov     rcx, r14
0x140002356  mov     [rsi+8], rcx
0x14000235a  mov     rax, [rsi]
0x14000235d  inc     rcx
0x140002360  neg     rax
0x140002363  sbb     r8, r8
0x140002366  and     r8, rcx
0x140002369  mov     [rdi], r8
0x14000236c  test    r8, r8
0x14000236f  jnz     loc_140002408
0x140002375  lea     eax, [r8+2]
0x140002379  mov     [rsp+68h+Value], r14
0x140002381  mul     rbp
0x140002384  test    rdx, rdx
0x140002387  jnz     loc_1400024D7
0x14000238d  mov     rcx, rax; cb
0x140002390  call    cs:__imp_CoTaskMemAlloc
0x140002396  test    rax, rax
0x140002399  jz      short loc_1400023A7
0x14000239b  mov     [rdi], rbp
0x14000239e  mov     [rsi], rax
0x1400023a1  mov     [rax], r14w
0x1400023a5  jmp     short loc_1400023B4
0x1400023a7  mov     ebx, 8007000Eh
0x1400023ac  test    ebx, ebx
0x1400023ae  js      loc_1400024E0
0x1400023b4  mov     rbp, [rdi]
0x1400023b7  xor     ecx, ecx; Value
0x1400023b9  mov     r14, [rsi]
0x1400023bc  call    cs:__imp__set_errno
0x1400023c2  test    rbp, rbp
0x1400023c5  jz      loc_140002474
0x1400023cb  cmp     rbp, 7FFFFFFFh
0x1400023d2  ja      loc_1400024C7
0x1400023d8  dec     rbp
0x1400023db  mov     r9, r12; Args
0x1400023de  mov     rdx, rbp; BufferCount
0x1400023e1  mov     r8, r13; Format
0x1400023e4  mov     rcx, r14; Buffer
0x1400023e7  call    cs:__imp__vsnwprintf
0x1400023ed  test    eax, eax
0x1400023ef  js      short loc_140002466
0x1400023f1  cdqe
0x1400023f3  cmp     rax, rbp
0x1400023f6  ja      short loc_140002466
0x1400023f8  xor     ebx, ebx
0x1400023fa  cmp     rax, rbp
0x1400023fd  jnz     short loc_14000247E
0x1400023ff  xor     eax, eax
0x140002401  mov     [r14+rbp*2], ax
0x140002406  jmp     short loc_14000247E
0x140002408  mov     ebx, r14d
0x14000240b  cmp     rbp, r8
0x14000240e  jbe     short loc_1400023AC
0x140002410  mov     eax, 2
0x140002415  mov     [rsp+68h+Value], r14
0x14000241d  mul     r8
0x140002420  mov     rbx, rax
0x140002423  test    rdx, rdx
0x140002426  jnz     loc_1400024D7
0x14000242c  mov     rcx, rax
0x14000242f  sub     rcx, r8
0x140002432  cmp     rcx, 800h
0x140002439  jbe     short loc_140002442
0x14000243b  lea     rbx, [r8+800h]
0x140002442  mov     rcx, [rsi]; pv
0x140002445  cmp     rbp, rbx
0x140002448  cmova   rbx, rbp
0x14000244c  lea     rdx, [rbx+rbx]; cb
0x140002450  call    cs:__imp_CoTaskMemRealloc
0x140002456  test    rax, rax
0x140002459  jz      short loc_1400024C0
0x14000245b  mov     [rdi], rbx
0x14000245e  mov     [rsi], rax
0x140002461  jmp     loc_1400023B4
0x140002466  xor     eax, eax
0x140002468  mov     ebx, 8007007Ah
0x14000246d  mov     [r14+rbp*2], ax
0x140002472  jmp     short loc_14000247E
0x140002474  mov     ebx, 80070057h
0x140002479  test    rbp, rbp
0x14000247c  jnz     short loc_1400024C7
0x14000247e  xor     r14d, r14d
0x140002481  cmp     ebx, 8007007Ah
0x140002487  jnz     short loc_1400024DC
0x140002489  lea     rcx, [rsp+68h+Value]; Value
0x140002491  mov     dword ptr [rsp+68h+Value], r14d
0x140002499  call    cs:__imp__get_errno
0x14000249f  cmp     dword ptr [rsp+68h+Value], 16h
0x1400024a7  jz      short loc_1400024D0
0x1400024a9  mov     rax, [rdi]
0x1400024ac  lea     rcx, [rax+20h]
0x1400024b0  cmp     rcx, rax
0x1400024b3  jnb     loc_14000231A
0x1400024b9  mov     ebx, 80070216h
0x1400024be  jmp     short loc_1400024E0
0x1400024c0  mov     ebx, 8007000Eh
0x1400024c5  jmp     short loc_1400024DC
0x1400024c7  xor     eax, eax
0x1400024c9  mov     [r14], ax
0x1400024cd  xor     r14d, r14d
0x1400024d0  mov     ebx, 80070057h
0x1400024d5  jmp     short loc_1400024DC
0x1400024d7  mov     ebx, 80070216h
0x1400024dc  test    ebx, ebx
0x1400024de  jns     short loc_1400024F7
0x1400024e0  mov     rcx, [rsi]; pv
0x1400024e3  test    rcx, rcx
0x1400024e6  jz      short loc_1400024F1
0x1400024e8  call    cs:__imp_CoTaskMemFree
0x1400024ee  mov     [rsi], r14
0x1400024f1  mov     [rdi], r14
0x1400024f4  mov     r15, r14
0x1400024f7  mov     [rsi+8], r15
0x1400024fb  mov     eax, ebx
0x1400024fd  add     rsp, 28h
0x140002501  pop     r15
0x140002503  pop     r14
0x140002505  pop     r13
0x140002507  pop     r12
0x140002509  pop     rdi
0x14000250a  pop     rsi
0x14000250b  pop     rbp
0x14000250c  pop     rbx
0x14000250d  retn
```
