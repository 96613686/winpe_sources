# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x18001ab34`
- end: `0x18001ad5d`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `553`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a51c`
- `0x18001a734`
- `0x18001a970`

## callees

- `0x18001ab34`
- `0x18001ad64`
- `0x180032712`
- `0x180032774`
- `0x180032828`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001abfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001abfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001abcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001abcb`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rbx
  LPVOID v8; // rax
  _WORD *v9; // rax
  int v10; // ebx
  unsigned __int64 v11; // rsi
  wchar_t *v12; // r14
  size_t v13; // rsi
  int v14; // eax
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  int Value[18]; // [rsp+20h] [rbp-48h] BYREF
  va_list Args; // [rsp+80h] [rbp+18h] BYREF

  va_start(Args, a2);
  *(_QWORD *)Value = 0;
  v4 = 32;
  while ( 1 )
  {
    v5 = v4 + 1;
    if ( v4 + 1 < v4 )
    {
LABEL_27:
      v10 = -2147024362;
      goto LABEL_24;
    }
    v6 = *(_QWORD *)(a1 + 16);
    if ( v6 == -1 )
    {
      v17 = *(_QWORD *)(a1 + 8);
      if ( v17 == -1 )
      {
        if ( *(_QWORD *)a1 )
        {
          do
            ++v17;
          while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v17) );
        }
        else
        {
          v17 = 0;
        }
        *(_QWORD *)(a1 + 8) = v17;
      }
      v6 = (v17 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
      *(_QWORD *)(a1 + 16) = v6;
    }
    if ( v6 )
      break;
    *(_QWORD *)Value = 0;
    if ( !is_mul_ok(v5, 2u) )
      goto LABEL_27;
    v9 = CoTaskMemAlloc(2 * v5);
    if ( v9 )
    {
      *(_QWORD *)(a1 + 16) = v5;
      v10 = 0;
      *(_QWORD *)a1 = v9;
      *v9 = 0;
    }
    else
    {
      v10 = -2147024882;
    }
    if ( v10 < 0 )
      goto LABEL_33;
LABEL_17:
    v11 = *(_QWORD *)(a1 + 16);
    v12 = *(wchar_t **)a1;
    set_errno(0);
    if ( v11 )
    {
      if ( v11 > 0x7FFFFFFF )
      {
        *v12 = 0;
LABEL_30:
        v10 = -2147024809;
        goto LABEL_24;
      }
      v13 = v11 - 1;
      v14 = vsnwprintf(v12, v13, a2, Args);
      if ( v14 < 0 || v14 > v13 )
      {
        v12[v13] = 0;
        v10 = -2147024774;
      }
      else
      {
        v10 = 0;
        if ( v14 == v13 )
          v12[v13] = 0;
      }
    }
    else
    {
      v10 = -2147024809;
    }
    if ( v10 != -2147024774 )
      goto LABEL_24;
    Value[0] = 0;
    get_errno(Value);
    if ( Value[0] == 22 )
      goto LABEL_30;
    v16 = *(_QWORD *)(a1 + 16);
    v4 = v16 + 32;
    if ( v16 + 32 < v16 )
    {
      v10 = -2147024362;
      goto LABEL_33;
    }
  }
  if ( v5 <= v6 )
    goto LABEL_17;
  *(_QWORD *)Value = 0;
  v7 = 2 * v6;
  if ( !is_mul_ok(v6, 2u) )
    goto LABEL_27;
  if ( v6 > 0x800 )
    v7 = v6 + 2048;
  if ( v5 > v7 )
    v7 = v5;
  v8 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v7);
  if ( v8 )
  {
    *(_QWORD *)(a1 + 16) = v7;
    *(_QWORD *)a1 = v8;
    goto LABEL_17;
  }
  v10 = -2147024882;
LABEL_24:
  if ( v10 >= 0 )
  {
    *(_QWORD *)(a1 + 8) = -1;
    return (unsigned int)v10;
  }
LABEL_33:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001ab34  mov     rax, rsp
0x18001ab37  mov     [rax+10h], rdx
0x18001ab3b  mov     [rax+18h], r8
0x18001ab3f  mov     [rax+20h], r9
0x18001ab43  push    rbx
0x18001ab44  push    rbp
0x18001ab45  push    rsi
0x18001ab46  push    rdi
0x18001ab47  push    r14
0x18001ab49  push    r15
0x18001ab4b  sub     rsp, 38h
0x18001ab4f  xor     r15d, r15d
0x18001ab52  mov     rdi, rcx
0x18001ab55  mov     rbp, rdx
0x18001ab58  mov     [rax-48h], r15
0x18001ab5c  lea     ecx, [r15+20h]
0x18001ab60  lea     rsi, [rcx+1]
0x18001ab64  lea     rbx, [rsp+68h+Args]
0x18001ab6c  cmp     rsi, rcx
0x18001ab6f  jb      loc_18001AC99
0x18001ab75  mov     r8, [rdi+10h]
0x18001ab79  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001ab7d  jz      loc_18001ACF0
0x18001ab83  test    r8, r8
0x18001ab86  jz      short loc_18001ABE3
0x18001ab88  cmp     rsi, r8
0x18001ab8b  jbe     loc_18001AC29
0x18001ab91  mov     eax, 2
0x18001ab96  mov     qword ptr [rsp+68h+Value], r15
0x18001ab9b  mul     r8
0x18001ab9e  mov     rbx, rax
0x18001aba1  test    rdx, rdx
0x18001aba4  jnz     loc_18001AC99
0x18001abaa  mov     rcx, rax
0x18001abad  sub     rcx, r8
0x18001abb0  cmp     rcx, 800h
0x18001abb7  ja      loc_18001AD3A
0x18001abbd  mov     rcx, [rdi]; pv
0x18001abc0  cmp     rsi, rbx
0x18001abc3  cmova   rbx, rsi
0x18001abc7  lea     rdx, [rbx+rbx]; cb
0x18001abcb  call    cs:__imp_CoTaskMemRealloc
0x18001abd1  test    rax, rax
0x18001abd4  jz      loc_18001ACE9
0x18001abda  mov     [rdi+10h], rbx
0x18001abde  mov     [rdi], rax
0x18001abe1  jmp     short loc_18001AC21
0x18001abe3  mov     eax, 2
0x18001abe8  mov     qword ptr [rsp+68h+Value], r15
0x18001abed  mul     rsi
0x18001abf0  test    rdx, rdx
0x18001abf3  jnz     loc_18001AC99
0x18001abf9  mov     rcx, rax; cb
0x18001abfc  call    cs:__imp_CoTaskMemAlloc
0x18001ac02  test    rax, rax
0x18001ac05  jz      loc_18001AD30
0x18001ac0b  mov     [rdi+10h], rsi
0x18001ac0f  mov     ebx, r15d
0x18001ac12  mov     [rdi], rax
0x18001ac15  mov     [rax], r15w
0x18001ac19  test    ebx, ebx
0x18001ac1b  js      loc_18001ACDF
0x18001ac21  lea     rbx, [rsp+68h+Args]
0x18001ac29  mov     rsi, [rdi+10h]
0x18001ac2d  xor     ecx, ecx; Value
0x18001ac2f  mov     r14, [rdi]
0x18001ac32  call    _set_errno
0x18001ac37  test    rsi, rsi
0x18001ac3a  jz      loc_18001AD46
0x18001ac40  cmp     rsi, 7FFFFFFFh
0x18001ac47  ja      loc_18001AD54
0x18001ac4d  dec     rsi
0x18001ac50  mov     r9, rbx; Args
0x18001ac53  mov     rdx, rsi; BufferCount
0x18001ac56  mov     r8, rbp; Format
0x18001ac59  mov     rcx, r14; Buffer
0x18001ac5c  call    _vsnwprintf
0x18001ac61  test    eax, eax
0x18001ac63  js      short loc_18001ACA0
0x18001ac65  cdqe
0x18001ac67  cmp     rax, rsi
0x18001ac6a  ja      short loc_18001ACA0
0x18001ac6c  mov     ebx, r15d
0x18001ac6f  jnz     short loc_18001AC76
0x18001ac71  mov     [r14+rsi*2], r15w
0x18001ac76  cmp     ebx, 8007007Ah
0x18001ac7c  jz      short loc_18001ACAC
0x18001ac7e  test    ebx, ebx
0x18001ac80  js      short loc_18001ACDF
0x18001ac82  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18001ac8a  mov     eax, ebx
0x18001ac8c  add     rsp, 38h
0x18001ac90  pop     r15
0x18001ac92  pop     r14
0x18001ac94  pop     rdi
0x18001ac95  pop     rsi
0x18001ac96  pop     rbp
0x18001ac97  pop     rbx
0x18001ac98  retn
0x18001ac99  mov     ebx, 80070216h
0x18001ac9e  jmp     short loc_18001AC7E
0x18001aca0  mov     [r14+rsi*2], r15w
0x18001aca5  mov     ebx, 8007007Ah
0x18001acaa  jmp     short loc_18001AC76
0x18001acac  lea     rcx, [rsp+68h+Value]; Value
0x18001acb1  mov     [rsp+68h+Value], r15d
0x18001acb6  call    _get_errno
0x18001acbb  cmp     [rsp+68h+Value], 16h
0x18001acc0  jnz     short loc_18001ACC9
0x18001acc2  mov     ebx, 80070057h
0x18001acc7  jmp     short loc_18001AC7E
0x18001acc9  mov     rax, [rdi+10h]
0x18001accd  lea     rcx, [rax+20h]
0x18001acd1  cmp     rcx, rax
0x18001acd4  jnb     loc_18001AB60
0x18001acda  mov     ebx, 80070216h
0x18001acdf  mov     rcx, rdi
0x18001ace2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001ace7  jmp     short loc_18001AC8A
0x18001ace9  mov     ebx, 8007000Eh
0x18001acee  jmp     short loc_18001AC7E
0x18001acf0  mov     rcx, [rdi+8]
0x18001acf4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001acf8  jnz     short loc_18001AD18
0x18001acfa  mov     rax, [rdi]
0x18001acfd  test    rax, rax
0x18001ad00  jz      short loc_18001AD11
0x18001ad02  or      rcx, rcx
0x18001ad05  inc     rcx
0x18001ad08  cmp     [rax+rcx*2], r15w
0x18001ad0d  jnz     short loc_18001AD05
0x18001ad0f  jmp     short loc_18001AD14
0x18001ad11  mov     rcx, r15
0x18001ad14  mov     [rdi+8], rcx
0x18001ad18  mov     rax, [rdi]
0x18001ad1b  inc     rcx
0x18001ad1e  neg     rax
0x18001ad21  sbb     r8, r8
0x18001ad24  and     r8, rcx
0x18001ad27  mov     [rdi+10h], r8
0x18001ad2b  jmp     loc_18001AB83
0x18001ad30  mov     ebx, 8007000Eh
0x18001ad35  jmp     loc_18001AC19
0x18001ad3a  lea     rbx, [r8+800h]
0x18001ad41  jmp     loc_18001ABBD
0x18001ad46  mov     ebx, 80070057h
0x18001ad4b  test    rsi, rsi
0x18001ad4e  jz      loc_18001AC76
0x18001ad54  mov     [r14], r15w
0x18001ad58  jmp     loc_18001ACC2
```
