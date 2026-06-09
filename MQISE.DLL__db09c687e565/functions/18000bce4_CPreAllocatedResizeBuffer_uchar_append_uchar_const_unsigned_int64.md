# CPreAllocatedResizeBuffer<uchar>::append(uchar const *,unsigned __int64)

- ea: `0x18000bce4`
- end: `0x18000be14`
- name: `?append@?$CPreAllocatedResizeBuffer@E@@QEAAXPEBE_K@Z`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800071c4`
- `0x18000d3e0`

## callees

- `0x180001c0c`
- `0x180003140`
- `0x18000bce4`
- `0x18000be1c`
- `0x18000cc28`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000bdae`
- `msvcrt!memmove_s` at `0x18000bdae`

## pseudocode

```c
int __fastcall CPreAllocatedResizeBuffer<unsigned char>::append(__int64 *a1, const void *a2, rsize_t a3)
{
  const void *v4; // rbp
  __int64 v5; // r8
  _QWORD *v7; // rcx
  rsize_t v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  _BYTE *v13; // rdx
  _BYTE *v14; // rax
  _BYTE *v15; // r8
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v4 = a2;
  v5 = a1[6];
  if ( !v5 )
  {
    v7 = a1 + 1;
LABEL_3:
    LODWORD(v8) = CResizeBuffer<unsigned char>::append(v7, a2, a3);
    return v8;
  }
  v9 = *a1;
  v8 = *a1 + a3;
  if ( v8 < a3 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  v10 = a1[7];
  if ( v10 < v8 )
  {
    v11 = v10 + a3;
    if ( v10 + a3 < a3 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v12 = 2 * v11;
    if ( !is_mul_ok(v11, 2u) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    if ( v12 > v10 )
    {
      CResizeBuffer<unsigned char>::reserve(a1 + 1, v12);
      v13 = (_BYTE *)a1[6];
      v14 = (_BYTE *)a1[3];
      v15 = &v13[*a1];
      while ( v13 != v15 )
        *v14++ = *v13++;
      a1[1] = *a1;
      a1[6] = 0;
    }
    a2 = v4;
    v7 = a1 + 1;
    goto LABEL_3;
  }
  if ( (__int64)a3 > 0 )
    LODWORD(v8) = memmove_s((void *const)(v9 + v5), a3, v4, a3);
  *a1 += a3;
  return v8;
}

```

## disassembly

```asm
0x18000bce4  push    rbx
0x18000bce6  push    rbp
0x18000bce7  push    rsi
0x18000bce8  push    rdi
0x18000bce9  sub     rsp, 48h
0x18000bced  mov     rdi, r8
0x18000bcf0  mov     rbp, rdx
0x18000bcf3  mov     r8, [rcx+30h]
0x18000bcf7  mov     rbx, rcx
0x18000bcfa  test    r8, r8
0x18000bcfd  jnz     short loc_18000BD10
0x18000bcff  add     rcx, 8
0x18000bd03  mov     r8, rdi
0x18000bd06  call    ?append@?$CResizeBuffer@E@@QEAAXPEBE_K@Z; CResizeBuffer<uchar>::append(uchar const *,unsigned __int64)
0x18000bd0b  jmp     loc_18000BDB7
0x18000bd10  mov     rdx, [rcx]
0x18000bd13  lea     rax, [rdx+rdi]
0x18000bd17  cmp     rax, rdi
0x18000bd1a  jb      loc_18000BDC0
0x18000bd20  mov     rcx, [rcx+38h]
0x18000bd24  cmp     rcx, rax
0x18000bd27  jnb     short loc_18000BD9C
0x18000bd29  lea     rdx, [rcx+rdi]
0x18000bd2d  cmp     rdx, rdi
0x18000bd30  jb      loc_18000BDDC
0x18000bd36  mov     eax, 2
0x18000bd3b  mov     [rsp+68h+arg_0], 0
0x18000bd44  mul     rdx
0x18000bd47  test    rdx, rdx
0x18000bd4a  jnz     loc_18000BDF8
0x18000bd50  lea     rsi, [rbx+8]
0x18000bd54  cmp     rax, rcx
0x18000bd57  jbe     short loc_18000BD91
0x18000bd59  mov     rdx, rax
0x18000bd5c  mov     rcx, rsi
0x18000bd5f  call    ?reserve@?$CResizeBuffer@E@@QEAAX_K@Z; CResizeBuffer<uchar>::reserve(unsigned __int64)
0x18000bd64  mov     rdx, [rbx+30h]
0x18000bd68  mov     r8, [rbx]
0x18000bd6b  mov     rax, [rbx+18h]
0x18000bd6f  add     r8, rdx
0x18000bd72  jmp     short loc_18000BD7E
0x18000bd74  mov     cl, [rdx]
0x18000bd76  mov     [rax], cl
0x18000bd78  inc     rax
0x18000bd7b  inc     rdx
0x18000bd7e  cmp     rdx, r8
0x18000bd81  jnz     short loc_18000BD74
0x18000bd83  mov     rax, [rbx]
0x18000bd86  mov     [rsi], rax
0x18000bd89  mov     qword ptr [rbx+30h], 0
0x18000bd91  mov     rdx, rbp
0x18000bd94  mov     rcx, rsi
0x18000bd97  jmp     loc_18000BD03
0x18000bd9c  test    rdi, rdi
0x18000bd9f  jle     short loc_18000BDB4
0x18000bda1  lea     rcx, [rdx+r8]; Destination
0x18000bda5  mov     r9, rdi; SourceSize
0x18000bda8  mov     r8, rbp; Source
0x18000bdab  mov     rdx, rdi; DestinationSize
0x18000bdae  call    cs:__imp_memmove_s
0x18000bdb4  add     [rbx], rdi
0x18000bdb7  add     rsp, 48h
0x18000bdbb  pop     rdi
0x18000bdbc  pop     rsi
0x18000bdbd  pop     rbp
0x18000bdbe  pop     rbx
0x18000bdbf  retn
0x18000bdc0  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000bdc5  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000bdca  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000bdd1  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000bdd6  call    _CxxThrowException_0
0x18000bddc  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000bde1  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000bde6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000bded  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000bdf2  call    _CxxThrowException_0
0x18000bdf8  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000bdfd  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000be02  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000be09  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000be0e  call    _CxxThrowException_0
```
